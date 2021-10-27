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
ms.openlocfilehash: 39c456b3f7ad31181d47318570176710840ad8b2
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587977"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>查看并组织 Microsoft Defender for Endpoint 警报队列

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)。

**警报队列** 显示从网络中设备标记的警报列表。 默认情况下，队列在分组视图中显示最近 30 天内看到的警报。 最新警报在列表顶部显示，有助于你先查看最新警报。

> [!NOTE]
> 通过自动调查和修正显著减少警报队列，使安全运营专家可以专注于更复杂的威胁和其他高价值计划。 当警报包含用于自动调查的支持实体 (例如，文件) 支持的操作系统的设备中，可以启动自动调查和修正。 有关自动调查详细信息，请参阅 [自动调查概述](automated-investigations.md)。

有几种选项可供选择以自定义警报队列视图。

在顶部导航上，你可以：

- 选择分组视图或列表视图
- 自定义列以添加或删除列
- 选择要按页显示的项目
- 在页面之间导航
- 应用筛选器

![警报队列的图像。](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>对警报队列进行排序、筛选和分组

可以应用以下筛选器来限制警报列表，并更集中地查看警报。

### <a name="severity"></a>Severity

警报严重性|说明
---|---
高 <br>  (红色) |通常看到的与 APT 高级永久性威胁 (警报) 。 这些警报表明存在高风险，因为它们可能会损坏设备的严重性。 例如：凭据盗窃工具活动、未与任何组关联的勒索软件活动、篡改安全传感器或任何恶意活动，这些活动会指示人类对手。
中 <br>  (橙色) |终结点检测和响应泄露后行为的警报，这些行为可能是 APT 高级永久性威胁 (的) 。 这包括观察到的攻击阶段的典型行为、异常注册表更改、执行可疑文件等。 尽管其中一些可能是内部安全测试的一部分，但它需要进行调查，因为它也可能属于高级攻击。
低 <br>  (黄色) |与流行恶意软件相关的威胁警报。 例如，黑客工具、非恶意软件黑客工具（如运行探索命令、清除日志等）通常不会指示面向组织的高级威胁。 它还可能来自组织中用户隔离的安全工具测试。
信息 <br>  (灰色) |可能被视为对网络有害的警报，但可以提升组织对潜在安全问题的安全意识。

#### <a name="understanding-alert-severity"></a>了解警报严重性

Microsoft Defender 防病毒 (Microsoft Defender AV) 和 Defender for Endpoint 警报严重性是不同的，因为它们表示不同的范围。

威胁Microsoft Defender 防病毒威胁严重性表示检测到的威胁 (恶意软件) 的绝对严重性，并基于单个设备的潜在风险（如果受感染）进行分配。

Defender for Endpoint 警报严重性表示检测到的行为的严重性，即设备的实际风险，但更重要的是对组织带来潜在风险。

例如：

- 有关检测到的已完全阻止Microsoft Defender 防病毒未感染设备的已检测到威胁的 Defender for Endpoint 警报的严重性被归类为"信息"，因为没有实际损害。
- 有关商业恶意软件的警报在执行时被检测到，但被 Microsoft Defender AV 阻止和修复，被分类为"低"，因为它可能给单个设备造成一些损坏，但不构成组织威胁。
- 有关在执行时检测到的恶意软件的警报，不仅会对单个设备造成威胁，而且会对组织造成威胁，无论最终是否被阻止，都将被排名为"中"或"高"。
- 根据相同的组织威胁注意事项，未阻止或修正的可疑行为警报将被排名为"低"、"中"或"高"。

#### <a name="understanding-alert-categories"></a>了解警报类别

我们重新定义了警报类别，以与 MITRE [](https://attack.mitre.org/tactics/enterprise/) ATT 和 CK 矩阵中的企业&[策略一致](https://attack.mitre.org/)。 新类别名称适用于所有新警报。 现有警报将保留以前的类别名称。

下表列出了当前类别及其通常如何映射到以前的类别。

|新类别|API 类别名称|检测到威胁活动或组件|
|---|---|---|
|集合|集合|定位和收集数据以用于筛选。|
|命令和控件|CommandAndControl|连接到攻击者控制的网络基础结构以中继数据或接收命令。|
|凭据访问|CredentialAccess|获取有效凭据以扩展对网络中设备和其他资源的控制。|
|防御者|DefenseEvasion|例如，通过关闭安全应用、删除芯片和运行 rootkit 来避免安全控制。|
|Discovery|Discovery|收集有关重要设备和资源（如管理员计算机、域控制器和文件服务器）的信息。|
|执行|执行|启动攻击者工具和恶意代码，包括 RAT 和后门。|
|外泄|外泄|将数据从网络提取到外部攻击者控制的位置。|
|攻击|攻击|攻击代码和可能的利用活动。|
|初始访问|InitialAccess|获取目标网络的初始条目，通常涉及密码猜测、攻击或钓鱼电子邮件。|
|横向移动|LateralMovement|在目标网络中设备之间移动以到达关键资源或获得网络持久性。|
|恶意软件|恶意软件|后门、特洛伊木马和其他类型的恶意代码。|
|持久性|持久性|创建自动启动扩展点 (ASP) 保持活动状态，并保存系统重新启动。|
|特权提升|PrivilegeEscalation|在特权进程或帐户上下文中运行代码，以获取更高的代码权限级别。|
|勒索软件|勒索软件|加密文件和扩展付款以还原访问权限的恶意软件。|
|可疑活动|SuspiciousActivity|可能是恶意软件活动或攻击一部分的非典型活动。|
|不需要的软件|UnwantedSoftware|影响工作效率和用户体验的低信誉应用和应用;检测为 PUA (可能不需要) 。|

### <a name="status"></a>状态

可以选择根据警报的状态限制警报列表。

### <a name="investigation-state"></a>调查状态

对应于自动调查状态。

### <a name="category"></a>类别

你可以选择筛选队列以显示特定类型的恶意活动。

### <a name="assigned-to"></a>分配到

可以选择显示分配给你的警报还是自动显示。

### <a name="detection-source"></a>检测源

选择触发警报检测的源。 Microsoft 威胁专家预览参与者现在可以筛选和查看来自新威胁专家托管的搜寻服务的检测。

> [!NOTE]
> 防病毒筛选器仅在设备将 Microsoft Defender 防病毒用作默认的实时保护反恶意软件产品时显示。

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

### <a name="os-platform"></a>OS 平台

通过选择你感兴趣的操作系统平台来限制警报队列视图。

### <a name="device-group"></a>设备组

如果你有对检查感兴趣的特定设备组，可以选择这些组来限制警报队列视图。

### <a name="associated-threat"></a>关联威胁

使用此筛选器专注于与高配置文件威胁相关的警报。 你可以查看威胁分析中的高配置文件威胁 [的完整列表](threat-analytics.md)。

## <a name="related-topics"></a>相关主题

- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
