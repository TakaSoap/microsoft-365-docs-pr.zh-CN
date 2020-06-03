---
title: 在 Microsoft 威胁防护中创建和管理自定义检测规则
description: 了解如何创建和管理基于高级搜寻查询的自定义检测规则
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、规则、架构、kusto、microsoft 365、Microsoft 威胁防护、RBAC、权限、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a84c568d1411cf21c23e59cabad955c40c18ac6
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498359"
---
# <a name="create-and-manage-custom-detections-rules"></a>创建和管理自定义检测规则

**适用于：**
- Microsoft 威胁防护

通过[先进的搜寻](advanced-hunting-overview.md)查询生成的自定义检测规则使您能够主动监视各种事件和系统状态，包括可疑的违规活动和错误配置的终结点。 您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。

## <a name="required-permissions-for-managing-custom-detections"></a>管理自定义检测项所需的权限

若要管理自定义检测，您需要分配以下角色之一：

- **安全管理员**-安全管理员或安全管理员角色是用于管理 Microsoft 365 安全中心和各种门户和服务中的各种安全设置的[Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)。

- **安全操作员**—安全操作员角色是用于管理警报的[Azure Active Directory 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)，它具有与安全相关的功能（包括 Microsoft 365 安全中心中的所有信息）的全局只读访问权限。 仅当在 Microsoft Defender ATP 中关闭基于角色的访问控制（RBAC）时，此角色才足够管理自定义检测。 如果配置了 RBAC，则还需要具有 Microsoft Defender ATP 的 "**管理安全设置**" 权限。

若要管理所需的权限，**全局管理员**可以执行以下操作：

- 在**角色**安全管理员下的[Microsoft 365 管理中心](https://admin.microsoft.com/)中分配**安全管理员**或**安全操作员**角色  >  **Security admin**。
- 在 "**设置**权限角色" 下的 " [microsoft defender 安全中心](https://securitycenter.windows.com/)" 中检查 microsoft defender ATP 的 RBAC 设置  >  **Permissions**  >  **Roles**。 选择相应的角色以分配**管理安全设置**权限。

> [!NOTE]
> 若要管理自定义检测，如果 RBAC 已打开，**安全操作员**将需要 MICROSOFT Defender ATP 中的 "**管理安全设置**" 权限。

## <a name="create-a-custom-detection-rule"></a>创建自定义检测规则
### <a name="1-prepare-the-query"></a>1. 准备查询。

在 Microsoft 365 安全中心中，转到 "**高级**搜索"，然后选择一个现有查询或创建新的查询。 使用新查询时，请运行查询以确定错误并了解可能的结果。

#### <a name="required-columns-in-the-query-results"></a>查询结果中的必需列
若要创建自定义检测规则，查询必须返回以下列：

- `Timestamp`
- 下列设备、用户或邮箱列之一：
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`（信封发件人或寄信人路径地址）
    - `SenderMailFromAddress`（电子邮件客户端显示的发件人地址）
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>在向[高级搜寻架构](advanced-hunting-schema-tables.md)中添加新表时，将添加对其他实体的支持。

简单查询（例如，不使用 `project` or `summarize` 运算符自定义或聚合结果的查询）通常返回这些常见的列。

有多种方法可确保更复杂的查询返回这些列。 例如，如果您希望在等列下按实体进行聚合和计数 `DeviceId` ，则仍可 `Timestamp` 通过获取每个唯一涉及的最新事件来返回 `DeviceId` 。

下面的示例查询计算带有防病毒检测的独特设备（）的数量 `DeviceId` ，并使用此计数来仅查找检测到五个以上的设备。 若要返回最新的 `Timestamp` ，它会将 `summarize` 运算符与函数一起使用 `arg_max` 。

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 创建新规则并提供警报详细信息。

使用查询编辑器中的查询，选择 "**创建检测规则**"，并指定以下警报详细信息：

- **检测名称**—检测规则的名称
- **Frequency** —运行查询和采取操作的时间间隔。 [请参阅下面的其他指导](#rule-frequency)
- **通知标题**—与规则触发的警报一起显示的标题
- **严重性**—由规则标识的组件或活动的潜在风险
- **Category** -由规则标识的威胁组件或活动
- **MITRE ATT&CK 技术**—由规则标识的一个或多个攻击技术，如[MITRE ATT&CK framework](https://attack.mitre.org/)中所述。 对于某些警报类别（包括恶意软件、勒索软件、可疑活动和不需要的软件），本节不适用且隐藏。
- **说明**—有关由规则标识的组件或活动的详细信息 
- **建议的操作**，响应者可能会采取的其他操作来响应警报

#### <a name="rule-frequency"></a>规则频率
保存后，新的或编辑的自定义检测规则会立即运行并检查来自过去30天数据的匹配项。 然后，该规则将根据您选择的频率在固定时间间隔和 lookback 持续时间内再次运行：

- **每24小时一**次，从过去30天中检查数据，每24小时运行一次
- **每12个小时一**次，从过去24小时内检查数据，每12小时运行一次
- **每3小时一**次，每3小时运行一次，检查过去6个小时的数据
- **每小时一次—每**小时运行一次，检查过去2个小时内的数据

选择与您要监视检测结果的接近程度相匹配的频率，并考虑组织的容量来响应警报。

### <a name="3-choose-the-impacted-entities"></a>3. 选择受影响的实体。
确定您希望在其中查找受影响的主要或受影响的实体的查询结果中的列。 例如，查询可能会返回发件人（ `SenderFromAddress` 或 `SenderMailFromAddress` ）和收件人（ `RecipientEmailAddress` ）地址。 确定哪些列代表主要受影响的实体可帮助服务聚合相关警报、关联事件和目标响应操作。

您只能为每个实体类型（邮箱、用户或设备）选择一列。 无法选择查询未返回的列。

### <a name="4-specify-actions"></a>4. 指定操作。
您的自定义检测规则可以对查询返回的设备、文件或用户自动执行操作。

#### <a name="actions-on-devices"></a>对设备的操作
这些操作适用于 `DeviceId` 查询结果列中的设备：
- **隔离设备**—使用 MICROSOFT Defender ATP 应用完全网络隔离，以阻止设备连接到任何应用程序或服务。 [了解有关 Microsoft Defender ATP 计算机隔离的详细信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **收集调查包**—收集 ZIP 文件中的设备信息。 [了解有关 Microsoft Defender ATP 调查包的详细信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **运行防病毒扫描**—在设备上执行完整的 Windows Defender 防病毒扫描
- **启动调查**—启动对设备的[自动调查](mtp-autoir.md)
- **限制应用程序执行**—将对设备的限制设置为仅允许使用 Microsoft 颁发的证书签名的文件运行。 [了解有关 Microsoft Defender ATP 的应用限制的详细信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>对文件执行的操作
如果选择此选项，则可以选择对查询结果的、、或列中的文件应用**隔离文件**操作 `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 。 此操作将从文件的当前位置删除文件，并将副本放在 "隔离" 中。

#### <a name="actions-on-users"></a>对用户的操作
如果选择此选项，则会对查询结果的、或列中的用户执行 "将**用户标记为受到威胁**" 操作 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 。 此操作在 Azure Active Directory 中将用户风险级别设置为 "高"，从而触发相应的[标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

> [!NOTE]
> Microsoft 威胁防护目前不支持自定义检测规则的允许或阻止操作。

### <a name="5-set-the-rule-scope"></a>5. 设置规则作用域。
设置作用域以指定规则所涵盖的设备。 作用域会影响检查设备的规则，而不会影响仅检查邮箱和用户帐户或标识的规则。

设置作用域时，可以选择：

- 所有设备
- 特定设备组

仅会查询范围内设备中的数据。 此外，操作只会在这些设备上执行。

### <a name="6-review-and-turn-on-the-rule"></a>6. 查看并启用规则。
检查规则后，单击 "**创建**" 以保存该规则。 自定义检测规则将立即运行。 它将根据配置的频率再次运行，以检查匹配项、生成警报并采取响应操作。

## <a name="manage-existing-custom-detection-rules"></a>管理现有的自定义检测规则
您可以查看现有的自定义检测规则的列表，检查其以前的运行，并查看它们触发的警报。 您还可以按需运行规则并对其进行修改。

### <a name="view-existing-rules"></a>查看现有规则

若要查看所有现有的自定义检测规则，请导航到 "**搜寻**  >  **自定义**检测"。 页面列出了包含以下运行信息的所有规则：

- **上次运行**时间—上次运行规则以检查查询匹配项并生成警报
- **上次运行状态**—规则是否成功运行
- **下次运行**—下一次计划的运行
- **状态**—是否已打开或关闭规则

### <a name="view-rule-details-modify-rule-and-run-rule"></a>查看规则详细信息、修改规则和运行规则

若要查看有关自定义检测规则的完整信息，请从 "**搜寻**  >  **自定义检测**" 中的规则列表中选择规则的名称。 这将打开有关该规则的常规信息的自定义检测规则页面，包括警报、运行状态和范围的详细信息。 它还提供触发警报和触发操作的列表。

!["自定义检测规则详细信息" 页](../../media/custom-detection-details.png)<br>
*自定义检测规则详细信息*

此外，还可以对此页面中的规则执行以下操作：

- **运行**—立即运行该规则。 这还会重置下一次运行的时间间隔。
- **编辑**—在不更改查询的情况下修改规则
- **修改查询**—在高级搜寻中编辑查询
- **打开**  / **关闭**—启用或停止运行规则
- **删除**-关闭规则并将其删除

### <a name="view-and-manage-triggered-alerts"></a>查看和管理触发的警报

在 "规则详细信息"**屏幕（**  >  搜索**自定义检测**  >  **[规则名称]**）中，转到 "**触发警报**" 以查看与该规则匹配生成的警报列表。 选择一个警报以查看有关该通知的详细信息，并对该警报执行以下操作：

- 通过设置警报的状态和分类来管理警报（true 或 false 警报）
- 将警报链接到事件
- 在高级搜寻中运行触发警报的查询

### <a name="review-actions"></a>查看操作
在 "规则详细信息"**屏幕（**  >  搜索**自定义检测**  >  **[规则名称]**）中，转到 "**触发操作**"，以根据与规则的匹配项查看所执行的操作的列表。

>[!TIP]
>若要快速查看信息并对表中的项目执行操作，请使用表左侧的选择列 [&#10003;]。

## <a name="related-topic"></a>相关主题
- [自定义检测概述](custom-detections-overview.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解高级搜寻查询语言](advanced-hunting-query-language.md)