---
title: 查看并组织 Microsoft Defender for Endpoint 警报队列
description: 了解 Microsoft Defender for Endpoint 警报队列如何工作，以及如何对警报列表进行排序和筛选。
keywords: 警报， 队列， 警报队列， 排序， 顺序， 筛选， 管理警报， 新， 正在进行， 已解决， 最新， 队列中的时间， 严重性， 时间段， Microsoft 威胁专家警报
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 0d6b012d2e3dbe6778c8d9c70552cf24427f8a3d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472036"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>查看并组织 Microsoft Defender for Endpoint 警报队列

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)。

**警报队列** 显示从网络中设备标记的警报列表。 默认情况下，队列在分组视图中显示最近 30 天内看到的警报。 最新警报显示在列表顶部，有助于你先查看最新警报。

> [!NOTE]
> 通过自动调查和修正显著减少警报，使安全运营专家可以专注于更复杂的威胁和其他高价值计划。 当警报包含用于自动调查的支持实体 (例如，文件) 支持的操作系统的设备中，可以启动自动调查和修正。 有关自动调查详细信息，请参阅 [自动调查概述](automated-investigations.md)。

有几种选项可供选择以自定义通知视图。

在顶部导航上，你可以：

- 自定义列以添加或删除列
- 应用筛选器
- 显示特定持续时间（如 1 天、3 天、1 周、30 天和 6 个月）的警报
- 将警报列表导出到 excel
- 管理通知

:::image type="content" source="images/alerts-queue-list.png" alt-text="警报队列页面" lightbox="images/alerts-queue-list.png":::

## <a name="sort-and-filter-alerts"></a>排序和筛选警报 

可以应用以下筛选器来限制警报列表，并更集中地查看警报。

### <a name="severity"></a>Severity

警报严重性|说明
---|---
高 <br>  (红色) |通常看到的与 APT 高级永久性威胁 (警报) 。 这些警报表明存在高风险，因为它们可能会损坏设备的严重性。 例如：凭据盗窃工具活动、未与任何组关联的勒索软件活动、篡改安全传感器或任何恶意活动，这些活动会指示人类对手。
中 <br>  (橙色) |终结点检测和响应泄露后行为的警报，这些警报可能是 APT 高级永久性威胁 (的) 。 这些行为包括观察到的攻击阶段的典型行为、异常注册表更改、执行可疑文件等。 尽管其中一些可能是内部安全测试的一部分，但它需要进行调查，因为它也可能属于高级攻击。
低 <br>  (黄色) |与流行恶意软件相关的威胁警报。 例如，黑客工具、非恶意软件黑客工具（如运行探索命令、清除日志等）通常不会指示面向组织的高级威胁。 它还可能来自组织中用户隔离的安全工具测试。
信息 <br>  (灰色) |可能被视为对网络有害的警报，但可以提升组织对潜在安全问题的安全意识。

#### <a name="understanding-alert-severity"></a>了解警报严重性

Microsoft Defender 防病毒 (Microsoft Defender AV) 和 Defender for Endpoint 警报严重性是不同的，因为它们表示不同的范围。

威胁Microsoft Defender 防病毒表示检测到的威胁威胁的绝对严重性 (恶意软件) ，并基于单个设备的潜在风险（如果受感染）进行分配。

Defender for Endpoint 警报严重性表示检测到的行为的严重性，即设备的实际风险，但更重要的是对组织带来潜在风险。

例如：

- 由于没有实际损害，因此有关已检测到Microsoft Defender 防病毒未感染设备的已检测到威胁的 Defender for Endpoint 警报的严重性归类为"信息"。
- 有关商业恶意软件的警报在执行时被检测到，但被 Microsoft Defender AV 阻止和修复，被分类为"低"，因为它可能给单个设备造成一些损坏，但不构成组织威胁。
- 有关在执行时检测到的恶意软件的警报，不仅会对单个设备造成威胁，而且会对组织造成威胁，无论最终是否被阻止，都将被排名为"中"或"高"。
- 根据相同的组织威胁注意事项，未阻止或修正的可疑行为警报将被排名为"低"、"中"或"高"。

### <a name="status"></a>状态

可以选择根据警报的"状态"筛选警报列表。

### <a name="categories"></a>类别

我们重新定义了警报类别，以与 [MITRE ATT 和 CK](https://attack.mitre.org/) 矩阵中的企业&策略一致。[](https://attack.mitre.org/tactics/enterprise/) 新类别名称适用于所有新警报。 现有警报将保留以前的类别名称。

### <a name="service-sources"></a>服务源

Microsoft 威胁专家预览参与者现在可以筛选和查看来自新威胁专家托管的搜寻服务的检测。

根据以下服务源筛选警报：

- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Endpoint
- Microsoft 365 Defender
- Microsoft Defender for Office 365
- 应用治理
- AAD Identity Protection

> [!NOTE]
> 防病毒筛选器仅在设备将 Microsoft Defender 防病毒用作默认的实时保护反恶意软件产品时显示。

### <a name="tags"></a>标记

你可以根据分配给警报的标记筛选警报。

### <a name="policy"></a>Policy 

可以基于以下策略筛选警报：

|检测源|API 值|
|---|---|
|第三方传感器|ThirdPartySensors|
|防病毒|WindowsDefenderAv|
|自动调查|AutomatedInvestigation|
|自定义检测|CustomDetection|
|自定义 TI|CustomerTI|
|EDR|WindowsDefenderAtp|
|Microsoft 365 Defender|MTP|
|Microsoft Defender for Office 365|OfficeATP|
|Microsoft 威胁专家|ThreatExperts|
|SmartScreen|WindowsDefenderSmartScreen|

### <a name="entities"></a>实体

可以基于实体名称或 ID 筛选警报。 

### <a name="automated-investigation-state"></a>自动调查状态

可以选择根据警报的自动调查状态筛选警报。



## <a name="related-topics"></a>相关主题

- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
