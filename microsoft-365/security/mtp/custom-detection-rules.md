---
title: 在 Microsoft 365 Defender 中创建自定义检测规则
description: 了解如何基于高级搜寻查询创建和管理自定义检测规则
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 规则， 架构， kusto， microsoft 365， Microsoft 威胁防护， RBAC， 权限， Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932918"
---
# <a name="create-and-manage-custom-detections-rules"></a>创建和管理自定义检测规则

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

自定义检测规则是可以使用高级搜寻查询设计和 [调整](advanced-hunting-overview.md) 的规则。 通过这些规则，您可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。 你可以将它们设置为定期运行，生成警报，并随时执行响应操作。

## <a name="required-permissions-for-managing-custom-detections"></a>管理自定义检测所需的权限

若要管理自定义检测，需要分配以下角色之一：

- **安全管理员**- 具有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以在 Microsoft 365 安全中心和其他门户和服务中管理安全设置。

- **安全操作员**— 具有 [此 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 角色的用户可以管理警报，并且对与安全相关的功能（包括 Microsoft 365 安全中心内的所有信息）具有全局只读访问权限。 只有在 Microsoft Defender for Endpoint 中关闭基于角色的访问控制 (RBAC) ，此角色才足以管理自定义检测。 如果已配置 RBAC，则还需要 Defender for Endpoint **的** 安全设置权限。

若要管理所需的权限，全局 **管理员可以** ：

- 在 **Microsoft** [365](https://admin.microsoft.com/)管理 **中心的**"角色安全管理员"下分配 **安全管理员或**  >  **安全操作员角色**。
- 在"设置权限角色"下检查 Microsoft Defender 安全中心中 [适用于终结点的 Microsoft Defender](https://securitycenter.windows.com/)的 RBAC  >    >  **设置**。 选择相应的角色以分配 **管理安全设置** 权限。

> [!NOTE]
> 若要管理自定义检测，如果RBAC 已打开，安全操作员将需要在 Microsoft Defender for Endpoint 中管理安全设置权限。

## <a name="create-a-custom-detection-rule"></a>创建自定义检测规则
### <a name="1-prepare-the-query"></a>1. 准备查询。

在 Microsoft 365 安全中心，转到" **高级** 搜寻"并选择现有查询或创建新查询。 使用新查询时，运行查询以识别错误并了解可能的结果。

>[!IMPORTANT]
>为了防止服务返回过多警报，每个规则都限制为每次运行时仅生成 100 个警报。 在创建规则之前，请调整查询以避免对正常的日常活动发出警报。


#### <a name="required-columns-in-the-query-results"></a>查询结果中的必需列
若要创建自定义检测规则，查询必须返回以下列：

- `Timestamp`—用于设置生成的警报的时间戳
- `ReportId`— 启用对原始记录的查找
- 标识特定设备、用户或邮箱的以下列之一：
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (信封发件人或Return-Path地址) 
    - `SenderMailFromAddress` (客户端服务器显示) 
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>当新表添加到高级搜寻架构时，将添加对其他 [实体的支持](advanced-hunting-schema-tables.md)。

简单查询（如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。

有多种方式可以确保更复杂的查询返回这些列。 例如，如果你更希望按列下的实体进行聚合和计数，你仍然可以返回它，并且通过从涉及每个唯一的最近事件获取 `DeviceId` `Timestamp` `ReportId` 它 `DeviceId` 。

下面的示例查询对使用防病毒检测 () 设备数进行计数，并使用此计数仅查找检测次数超过 `DeviceId` 五的设备。 为了返回最新 `Timestamp` 和相应的值 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 为了提升查询性能，请设置与规则预期运行频率相匹配的时间筛选器。 由于运行频率最低是 _每 24 小时_ 一次，因此对过去一天的筛选将覆盖所有新数据。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 创建新规则并提供警报详细信息。

使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：

- **检测名称**- 检测规则的名称
- **频率**— 运行查询和采取措施的时间间隔。 [请参阅下面的其他指南](#rule-frequency)
- **警报标题**- 显示由规则触发的警报的标题
- **严重性**- 规则标识的组件或活动的潜在风险
- **类别**— 规则标识的威胁组件或活动
- **MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 [MITRE ATT](https://attack.mitre.org/)和 CK 框架中记录的规则&攻击技术。 本部分对某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件）隐藏
- **说明**- 有关规则标识的组件或活动详细信息 
- **建议的操作**- 响应者为响应警报可能执行的其他操作

#### <a name="rule-frequency"></a>规则频率
保存或编辑新规则时，它将运行并检查过去 30 天的数据中的匹配项。 然后，规则以固定间隔再次运行，并基于你选择的频率应用回发持续时间：

- **每 24 小时** 运行一次，每 24 小时运行一次，检查过去 30 天的数据
- **每 12 小时** 运行一次 ，每 12 小时运行一次，检查过去 24 小时的数据
- **每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据
- **每小时** 运行一次，检查过去 2 小时的数据

>[!TIP]
> 将查询中的时间筛选器与回发持续时间相匹配。 将忽略回发持续时间之外的结果。  

选择与要监视检测的频率相匹配的频率。 考虑组织响应警报的能力。

### <a name="3-choose-the-impacted-entities"></a>3. 选择受到影响的实体。
在查询结果中标识希望找到主要受影响或受影响的实体的列。 例如，查询可能返回发件人 (`SenderFromAddress` 或) `SenderMailFromAddress` 收件人 () `RecipientEmailAddress` 地址。 确定哪些列表示主要影响的实体可帮助服务聚合相关警报、关联事件和目标响应操作。

只能为邮箱、用户或设备 (实体类型选择一) 。 无法选择查询未返回的列。

### <a name="4-specify-actions"></a>4. 指定操作。
自定义检测规则可以自动对查询返回的设备、文件或用户执行操作。

#### <a name="actions-on-devices"></a>对设备的操作
这些操作将应用于查询结果 `DeviceId` 列中的设备：
- **隔离设备**— 使用 Microsoft Defender for Endpoint 应用完全网络隔离，阻止设备连接到任何应用程序或服务。 [了解有关适用于终结点计算机隔离的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **收集调查包**— 在 ZIP 文件中收集设备信息。 [详细了解 Microsoft Defender for Endpoint 调查包](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **运行防病毒扫描**- 在设备上执行Windows Defender防病毒扫描
- **启动调查**— 在 [设备上](mtp-autoir.md) 启动自动调查
- **限制应用** 执行 — 在设备上设置限制以仅允许使用 Microsoft 颁发的证书签名的文件运行。 [详细了解 Microsoft Defender for Endpoint 的应用限制](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>对文件的操作
选择后，可以选择对查询结果的、 或列中的文件应用隔离 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 文件操作。 此操作将从文件的当前位置删除文件，并隔离副本。

#### <a name="actions-on-users"></a>用户操作
选中后， **将用户标记为** 已泄露，将针对查询结果的 `AccountObjectId` 、 `InitiatingProcessAccountObjectId` 或 `RecipientObjectId` 列中的用户执行该操作。 此操作将 Azure Active Directory 中的用户风险级别设置为"高"，从而触发相应的 [标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> Microsoft 365 Defender 当前不支持自定义检测规则的允许或阻止操作。

### <a name="5-set-the-rule-scope"></a>5. 设置规则范围。
设置范围以指定规则涵盖哪些设备。 作用域影响检查设备的规则，而不影响仅检查邮箱和用户帐户或标识的规则。

设置范围时，可以选择：

- 所有设备
- 特定设备组

将仅查询范围内设备的数据。 此外，仅对这些设备执行操作。

### <a name="6-review-and-turn-on-the-rule"></a>6. 查看并打开规则。
查看规则后，选择 **"创建"** 以保存它。 自定义检测规则会立即运行。 它将基于配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。

## <a name="manage-existing-custom-detection-rules"></a>管理现有自定义检测规则
您可以查看现有自定义检测规则的列表，检查其之前的运行，并查看已触发的警报。 您还可以按需运行规则并对其进行修改。

### <a name="view-existing-rules"></a>查看现有规则

若要查看所有现有的自定义检测规则，请导航到 **"搜寻**  >  **自定义检测"。** 该页列出了具有以下运行信息的所有规则：

- **上次运行**- 上次运行规则以检查查询匹配项并生成警报时
- **上次运行状态**— 规则是否成功运行
- **下一次** 运行 - 下一次计划运行
- **状态**— 规则是已打开还是关闭

### <a name="view-rule-details-modify-rule-and-run-rule"></a>查看规则详细信息、修改规则并运行规则

若要查看有关自定义检测规则的综合信息，请转到"搜寻  >  **自定义检测**"，然后选择规则的名称。 然后，您可以查看有关规则的常规信息，包括其运行状态和范围信息。 该页还提供触发的警报和操作的列表。

![自定义检测规则详细信息页](../../media/custom-detection-details.png)<br>
*自定义检测规则详细信息*

您还可以从此页面对规则执行以下操作：

- **运行**-立即运行规则。 这还会重置下一次运行的时间间隔。
- **编辑**- 在不更改查询的情况下修改规则
- **修改查询**— 在高级搜寻中编辑查询
- **打开**  / **关闭**- 启用规则或阻止其运行
- **删除**- 关闭并删除规则

### <a name="view-and-manage-triggered-alerts"></a>查看和管理触发的警报

在规则详细信息屏幕 (搜索自定义检测  >    >  **[规则名称]**) ，转到"触发的警报"，其中列出了规则匹配项生成的警报。 选择警报以查看有关它的详细信息，并执行以下操作：

- 通过将警报的状态和分类设置为 true 或 false (来管理警报) 
- 将警报链接到事件
- 运行在高级搜寻时触发警报的查询

### <a name="review-actions"></a>查看操作
在规则详细信息屏幕 (搜索自定义检测  >    >  **[规则名称]**) ，转到"触发的操作"，其中列出了根据规则匹配项采取的操作。

>[!TIP]
>若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。

## <a name="related-topic"></a>相关主题
- [自定义检测概述](custom-detections-overview.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解高级搜寻查询语言](advanced-hunting-query-language.md)
