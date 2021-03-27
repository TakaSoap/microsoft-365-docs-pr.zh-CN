---
title: 在 Microsoft Defender ATP 中创建自定义检测规则
ms.reviewer: ''
description: 了解如何基于高级搜寻查询创建自定义检测规则
keywords: 自定义检测， 创建， 管理， 警报， 编辑， 按需运行， 频率， 间隔， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 48b1f1bf9506acc8491887fca49295d5e4ccbd69
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382705"
---
# <a name="create-custom-detection-rules"></a>创建自定义检测规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

通过高级搜寻 [查询](advanced-hunting-overview.md) 构建的自定义检测规则，你可以主动监视各种事件和系统状态，包括可疑的泄露活动和错误配置的设备。 你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。

阅读本文，了解如何创建新的自定义检测规则。 或者 [，请参阅查看和管理现有规则](custom-detections-manage.md)。

> [!NOTE]
> 若要创建或管理自定义检测， [你的](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 角色需要具有 **管理安全设置** 权限。

## <a name="1-prepare-the-query"></a>1。准备查询。

在 Microsoft Defender 安全中心中，转到高级 **搜寻** 并选择现有查询或创建新查询。 使用新查询时，运行查询以标识错误并了解可能的结果。

>[!IMPORTANT]
>为了防止服务返回太多警报，每个规则都限制为每次运行时仅生成 100 个警报。 创建规则之前，请调整查询以避免提醒正常、日常活动。

### <a name="required-columns-in-the-query-results"></a>查询结果中的必需列

若要对自定义检测规则使用查询，该查询必须返回以下列：

- `Timestamp`
- `DeviceId`
- `ReportId`

简单查询（例如不使用 or 运算符自定义或聚合结果的查询） `project` `summarize` 通常返回这些常用列。

有各种方法可以确保更复杂的查询返回这些列。 例如，如果你更喜欢聚合和计数，你仍然可以返回，并且通过从涉及每个设备的最新事件 `DeviceId` `Timestamp` `ReportId` 获取它们。

下面的示例查询计算使用防病毒检测 () 的唯一设备数，并使用此查询仅查找具有超过五个检测 `DeviceId` 的设备。 若要返回最新 `Timestamp` 和相应的 `ReportId` ，它将 `summarize` 运算符与 `arg_max` 函数一同使用。

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> 为了提升查询性能，请设置一个与规则预期运行频率相匹配的时间筛选器。 由于运行频率最低，每 24 小时一次，因此对过去一天的筛选将涵盖所有新数据。

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. 创建新规则并提供警报详细信息。

使用查询编辑器中的查询，选择 **"创建检测规则** "并指定以下警报详细信息：

- **检测名称**— 检测规则的名称
- **Frequency**— 运行查询和采取措施的时间间隔。 [请参阅下面的其他指南](#rule-frequency)
- **警报标题**- 显示的标题与规则触发的警报一起显示
- **严重性**- 规则标识的组件或活动的潜在风险。 [阅读警报严重性](alerts-queue.md#severity)
- **类别**— 威胁组件或活动的类型（如果有）。 [阅读有关警报类别](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK** 技术 - 一种或多种攻击技术，由 MITRE ATT 和 CK 框架中记录的规则&攻击技术。 本部分不适用于某些警报类别，如恶意软件、勒索软件、可疑活动和不需要的软件
- **说明**-有关规则标识的组件或活动详细信息 
- **建议的操作**- 响应者为响应警报可能执行的其他操作

有关警报详细信息的显示方式的详细信息， [请阅读有关警报队列的信息](alerts-queue.md)。

### <a name="rule-frequency"></a>规则频率

保存后，新的自定义检测规则会立即运行并检查过去 30 天的数据中的匹配。 然后，该规则将按固定间隔再次运行，并基于您选择的频率重新运行回看持续时间：

- **每 24 小时** 运行一次 ，每 24 小时运行一次，检查过去 30 天的数据
- **每 12 小时** 运行一次，每 12 小时运行一次，检查过去 24 小时内的数据
- **每 3 小时** 运行一次，每 3 小时运行一次，检查过去 6 小时的数据
- **每小时** 运行一次，每小时运行一次，检查过去 2 小时的数据

编辑规则时，它将在计划的下一个运行时中根据设置的频率运行应用的更改。


> [!TIP]
> 将查询中的时间筛选器与回看持续时间相匹配。 将忽略超出回视持续时间的结果。

选择与您希望监视检测的频率相匹配的频率，并考虑您的组织响应警报的能力。

## <a name="3-choose-the-impacted-entities"></a>3. 选择影响的实体。

确定查询结果中预期要查找主要受影响或受影响的实体的列。 例如，查询可能同时返回设备和用户 ID。 确定哪些列表示主要影响的实体，可帮助服务聚合相关警报、关联事件和目标响应操作。

只能为每种实体类型选择一列。 无法选择查询未返回的列。

## <a name="4-specify-actions"></a>4. 指定操作。

自定义检测规则可以自动对查询返回的文件或设备执行操作。

### <a name="actions-on-devices"></a>对设备的操作

这些操作适用于查询结果 `DeviceId` 列中的设备：

- **隔离设备** 应用完全网络隔离，阻止设备连接到任何应用程序或服务，Defender for Endpoint 服务除外。 [详细了解设备隔离](respond-machine-alerts.md#isolate-devices-from-the-network)
- **收集调查包**- 在 ZIP 文件中收集设备信息。 [详细了解调查包](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **运行防病毒扫描**- 在设备上执行完全 Microsoft Defender 防病毒扫描
- **启动调查**— 在 [设备上](automated-investigations.md) 启动自动调查
- **限制应用** 执行 — 在设备上设置限制，以仅允许使用 Microsoft 颁发的证书签名的文件运行。 [详细了解如何限制应用执行](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>对文件的操作

这些操作将应用于查询结果的 `SHA1` 或 `InitiatingProcessSHA1` 列中的文件：

- **允许/** 阻止 — 自动将文件添加到 [自定义指示器](manage-indicators.md) 列表，以便它始终允许运行或阻止运行。 你可以设置此操作的范围，以便仅在所选设备组上执行该操作。 此范围与规则的范围无关。
- **隔离** 文件 — 从文件的当前位置删除文件，将副本隔离

### <a name="actions-on-users"></a>用户操作

- **将用户标记为已泄露**— 在 Azure Active Directory 中，将用户的风险级别设置为"高"，从而触发相应的 [标识保护策略](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。

## <a name="5-set-the-rule-scope"></a>5. 设置规则范围。

设置范围以指定规则涵盖的设备：

- 所有设备
- 特定设备组

将仅查询作用域中设备的数据。 此外，将仅在这些设备上执行操作。

## <a name="6-review-and-turn-on-the-rule"></a>6. 查看并启用规则。

查看规则后，选择" **创建"** 以保存它。 自定义检测规则会立即运行。 它根据配置的频率再次运行，以检查匹配项、生成警报以及执行响应操作。

可以查看 [和管理自定义检测规则](custom-detections-manage.md)，检查其之前的运行，并查看已触发的警报。 您还可以按需运行规则并对其进行修改。

## <a name="related-topics"></a>相关主题

- [查看和管理自定义检测规则](custom-detections-manage.md)
- [自定义检测概述](overview-custom-detections.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解高级搜寻查询语言](advanced-hunting-query-language.md)
- [查看和组织警报](alerts-queue.md)
