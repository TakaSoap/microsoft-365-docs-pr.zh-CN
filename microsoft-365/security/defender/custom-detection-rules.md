---
title: 创建和管理自定义检测规则Microsoft 365 Defender
description: 了解如何创建和管理基于高级搜寻查询的自定义检测规则
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 规则， 架构， kusto， RBAC， 权限， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3066ccf803d5a2cad907ae7f983f3cafbb41112d
ms.sourcegitcommit: b3c4816b55657b87ed4a5f6a4abe3d505392218e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725848"
---
# <a name="create-and-manage-custom-detections-rules"></a>创建和管理自定义检测规则

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

自定义检测规则是可以使用高级搜寻查询设计和 [调整](advanced-hunting-overview.md) 的规则。 通过这些规则，您可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。 你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。

## <a name="required-permissions-for-managing-custom-detections"></a>管理自定义检测所需的权限

若要管理自定义检测，需要分配有以下角色之一：

- **安全管理员**- 具有 [此Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)角色的用户可以在安全中心Microsoft 365和其他门户和服务中管理安全设置。

- **安全** 操作员 - 具有 [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)此 Azure Active Directory 角色的用户可以管理警报，并且对安全相关功能（包括安全中心内Microsoft 365具有全局只读访问权限。 只有在 Microsoft Defender for Endpoint 中关闭基于角色的访问控制 (RBAC) ，此角色才足以管理自定义检测。 如果已配置 RBAC，则还需要 Defender for Endpoint **的** "管理安全设置"权限。

若要管理所需的权限，全局 **管理员可以** ：

- 在角色 **安全** 管理员下 **分配** 安全管理员Microsoft 365 管理中心 [](https://admin.microsoft.com/)  >  **安全操作员角色**。
- Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender 安全中心](https://securitycenter.windows.com/)under **设置**  >  **Permissions**  >  **Roles**. 选择相应的角色以分配 **管理安全设置** 权限。

> [!NOTE]
> 若要管理自定义检测，**如果** RBAC 已打开，安全操作员将需要 Microsoft Defender for Endpoint 中的管理安全设置权限。

## <a name="create-a-custom-detection-rule"></a>创建自定义检测规则
### <a name="1-prepare-the-query"></a>1。准备查询。

在Microsoft 365安全中心，转到"**高级** 搜寻"并选择现有查询或创建新查询。 使用新查询时，运行查询以标识错误并了解可能的结果。

>[!IMPORTANT]
>为了防止服务返回太多警报，每个规则都限制为每次运行时仅生成 100 个警报。 创建规则之前，请调整查询以避免提醒正常、日常活动。


#### <a name="required-columns-in-the-query-results"></a>查询结果中的必需列
若要创建自定义检测规则，查询必须返回以下列：

- `Timestamp`用于设置生成的警报的时间戳
- `ReportId`— 启用对原始记录的查找
- 标识特定设备、用户或邮箱的以下列之一：
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (信封发件人或Return-Path地址) 
    - `SenderMailFromAddress` (客户端邮箱显示发件人) 
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>将新表添加到高级搜寻架构时，将添加对其他 [实体的支持](advanced-hunting-schema-tables.md)。

简单查询（例如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。

有各种方法可以确保更复杂的查询返回这些列。 例如，如果你更希望按列下的实体（如 ）进行聚合和计数，你仍然可以返回 ，并且通过从涉及每个唯一的 的最新事件获取 `DeviceId` `Timestamp` `ReportId` `DeviceId` 它。


> [!IMPORTANT]
> 避免使用列筛选自定义 `Timestamp` 检测。 用于自定义检测的数据根据检测频率进行预筛选。


下面的示例查询计算使用防病毒检测 () 的唯一设备数，并使用此计数仅查找检测次数超过 `DeviceId` 五的设备。 若要返回最新 `Timestamp` 和相应的 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 为了提升查询性能，请设置一个与规则预期运行频率相匹配的时间筛选器。 由于运行频率最低，每 _24 小时_ 一次，因此对过去一天的筛选将覆盖所有新数据。

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 创建新规则并提供警报详细信息。

使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：

- **检测名称**— 检测规则的名称
- **Frequency**— 运行查询和采取措施的时间间隔。 [请参阅下面的其他指南](#rule-frequency)
- **警报标题**- 显示的标题与规则触发的警报一起显示
- **严重性**- 规则标识的组件或活动的潜在风险
- **类别**— 规则标识的威胁组件或活动
- **MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 [MITRE ATT](https://attack.mitre.org/)和 CK 框架中记录的规则&攻击技术。 本部分对某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件）隐藏
- **说明**-有关规则标识的组件或活动详细信息 
- **建议的操作**- 响应者为响应警报可能执行的其他操作

#### <a name="rule-frequency"></a>规则频率
保存新规则时，它将运行并检查过去 30 天的数据中的匹配。 然后，该规则以固定间隔再次运行，并基于你选择的频率应用回看持续时间：

- **每 24 小时** 运行一次 ，每 24 小时运行一次，检查过去 30 天的数据
- **每 12 小时** 运行一次，每 12 小时运行一次，检查过去 24 小时内的数据
- **每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据
- **每小时** 运行一次，每小时运行一次，检查过去 2 小时的数据

编辑规则时，它将在计划的下一个运行时中根据设置的频率运行应用的更改。



>[!TIP]
> 将查询中的时间筛选器与回看持续时间相匹配。 将忽略超出回视持续时间的结果。  

选择与要监视检测的频率相匹配的频率。 考虑组织响应警报的能力。

### <a name="3-choose-the-impacted-entities"></a>3. 选择影响的实体。
确定查询结果中预期要查找主要受影响或受影响的实体的列。 例如，查询可能会返回发件人 (`SenderFromAddress` 或) `SenderMailFromAddress` 收件人 () `RecipientEmailAddress` 地址。 确定哪些列表示主要影响的实体，可帮助服务聚合相关警报、关联事件和目标响应操作。

只能为邮箱、用户或设备 (每个实体类型选择一) 。 无法选择查询未返回的列。

### <a name="4-specify-actions"></a>4. 指定操作。
自定义检测规则可以自动对查询返回的设备、文件或用户执行操作。

#### <a name="actions-on-devices"></a>对设备的操作
这些操作适用于查询结果 `DeviceId` 列中的设备：
- **隔离设备**— 使用 Microsoft Defender for Endpoint 应用完全网络隔离，阻止设备连接到任何应用程序或服务。 [了解有关适用于终结点计算机隔离的 Microsoft Defender 有关详细信息](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **收集调查包**- 在 ZIP 文件中收集设备信息。 [了解有关适用于终结点的 Microsoft Defender 调查包的更多信息](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **运行防病毒扫描**- 在设备上Windows Defender 防病毒完全扫描
- **启动调查**— 在 [设备上](m365d-autoir.md) 启动自动调查
- **限制应用** 执行 — 在设备上设置限制，以仅允许使用 Microsoft 颁发的证书签名的文件运行。 [详细了解 Microsoft Defender for Endpoint 的应用限制](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>对文件的操作
选中后，您可以选择对查询结果的、 、 或 列中 `SHA1` 的文件应用隔离 `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 文件操作。 此操作将文件从当前位置删除，并隔离副本。

#### <a name="actions-on-users"></a>用户操作
选中后 **，将针对** 查询结果的 、 或 列中的用户执行"将用户标记为已泄露 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` "操作。 此操作将用户风险级别在 Azure Active Directory中，从而触发相应的[标识保护策略](/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> 自定义检测规则的允许或阻止操作当前在自定义检测Microsoft 365 Defender。

### <a name="5-set-the-rule-scope"></a>5. 设置规则范围。
设置范围以指定规则涵盖的设备。 作用域影响检查设备的规则，而不影响仅检查邮箱和用户帐户或标识的规则。

设置范围时，可以选择：

- 所有设备
- 特定设备组

将仅查询作用域中设备的数据。 此外，将仅在这些设备上执行操作。

### <a name="6-review-and-turn-on-the-rule"></a>6. 查看并启用规则。
查看规则后，选择" **创建"** 以保存它。 自定义检测规则会立即运行。 它根据配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。


>[!Important] 
>应定期检查自定义检测的效率和有效性。 若要确保创建触发真实警报的检测，请花时间按照管理现有自定义检测规则中的步骤检查现有的 [自定义检测](#manage-existing-custom-detection-rules)。 <br>  
您可以保持对自定义检测的广泛性和特定性的控制，以便由自定义检测生成的任何假警报可能表示需要修改规则的某些参数。


## <a name="manage-existing-custom-detection-rules"></a>管理现有自定义检测规则
可以查看现有自定义检测规则的列表，检查其之前的运行，并查看已触发的警报。 您还可以按需运行规则并对其进行修改。

>[!TIP]
> 通过警报和事件 API 提供由自定义检测引发警报。 有关详细信息，请参阅受支持的[Microsoft 365 Defender API。](api-supported.md)

### <a name="view-existing-rules"></a>查看现有规则

若要查看所有现有的自定义检测规则，请导航到"**搜寻**  >  **自定义检测"。** 该页列出了包含以下运行信息的所有规则：

- **上次运行**- 上次运行规则以检查查询匹配并生成警报时
- **上次运行状态**— 规则是否成功运行
- **下一** 次运行 - 下一个计划运行
- **状态**— 规则是已打开还是关闭

### <a name="view-rule-details-modify-rule-and-run-rule"></a>查看规则详细信息、修改规则并运行规则

若要查看有关自定义检测规则的综合信息，请转到"搜寻  >  **自定义检测**"，然后选择规则的名称。 然后，您可以查看有关规则的常规信息，包括其运行状态和范围的信息。 该页面还提供触发的警报和操作列表。

![自定义检测规则详细信息页](../../media/custom-detection-details.png)<br>
*自定义检测规则详细信息*

您还可以从此页对规则执行以下操作：

- **运行** 立即运行规则。 这还会重置下次运行的间隔。
- **编辑** 在不更改查询的情况下修改规则
- **修改查询**— 在高级搜寻中编辑查询
- **打开**  / **关闭**- 启用规则或阻止其运行
- **删除**- 关闭并删除规则

### <a name="view-and-manage-triggered-alerts"></a>查看和管理触发的警报

在规则详细信息屏幕中 (搜索自定义检测  >    >  **[规则名称]**) ，转到触发的警报 ，其中列出了规则匹配项生成的警报。 选择警报以查看有关它的详细信息，并执行以下操作：

- 通过将警报的状态和分类设置为 true 或 false (来管理警报) 
- 将警报链接到事件
- 运行触发高级搜寻警报的查询

### <a name="review-actions"></a>查看操作
在规则详细信息屏幕中 (搜索自定义检测  >    >  **[规则名称]**) ，转到触发的操作，其中列出了基于规则匹配项采取的操作。

>[!TIP]
>若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。

>[!NOTE]
>本文中的某些列在 Microsoft Defender for Endpoint 中可能不可用。 [打开"Microsoft 365 Defender，](m365d-enable.md)以使用更多数据源搜寻威胁。 你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到[Microsoft 365 Defender。](advanced-hunting-migrate-from-mde.md)

## <a name="see-also"></a>另请参阅
- [自定义检测概述](custom-detections-overview.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解高级搜寻查询语言](advanced-hunting-query-language.md)
- [从 Microsoft Defender for Endpoint 迁移高级搜寻查询](advanced-hunting-migrate-from-mde.md)
