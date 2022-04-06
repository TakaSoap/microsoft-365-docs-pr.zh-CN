---
title: 步骤 1. 对第一个事件进行会审和分析
description: 如何在Microsoft 365 Defender中对第一个事件进行会审和开始分析。
keywords: 事件， 警报， 调查， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c58bc4eb30c819ae0cbc1654173e8d9dc4ecb7a7
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664911"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>步骤 1. 对第一个事件进行会审和分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

当你花一些时间根据组织的标准建立、实施和维护安全措施时，你可以设置安全解决方案来帮助你快速识别安全风险和威胁。 Microsoft 365 Defender允许你通过单窗格的玻璃体验来检测、会审和调查事件，你可以在其中找到及时做出决策所需的信息。

检测到安全事件后，Microsoft 365 Defender会提供详细信息，需要对事件或事件进行会审或确定其优先级。 确定优先级后，分析师可以将精力集中在调查分配给他们的案件上。

## <a name="detection-by-microsoft-365-defender"></a>按Microsoft 365 Defender检测

Microsoft 365 Defender从多个 Microsoft 安全平台接收警报和事件作为检测源，以创建恶意活动的整体情况和上下文。 可能的检测源包括：

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)是使用 Microsoft Security Graph使用 Microsoft Defender 防病毒和启用云的高级威胁防护的终结点检测和响应解决方案 (EDR) 。 Defender for Endpoint 是一个统一的平台，用于预防性保护、违规后检测、自动调查和响应。 它保护终结点免受网络威胁，检测高级攻击和数据泄露，自动执行安全事件，并改善安全状况。
- [Microsoft Defender for Identity](/defender-for-identity/what-is)是基于云的安全解决方案，它使用本地 Active Directory域服务 (AD DS) 信号来识别、检测和调查针对组织的高级威胁、泄露标识和恶意内部操作。
- [Microsoft Defender for Cloud Apps](/cloud-app-security/)充当看门人，在企业用户与其使用的云资源之间实时代理访问，无论用户位于何处，无论他们使用何种设备。
- [Microsoft Defender for Office 365](../office-365-security/overview.md)保护组织免受电子邮件、链接 (URL) 和协作工具中的恶意威胁。
- [Azure 安全中心](/azure/security-center/security-center-introduction)是一个统一的基础结构安全管理系统，可加强数据中心的安全状况，并在云和本地的混合工作负荷中提供高级威胁防护。


在Microsoft 365 Defender中，[事件](incidents-overview.md)是通过关联来自这些不同检测源的警报来识别的。 无需将资源串联在一起或将多个警报区分为各自的事件，而是可以立即从Microsoft 365 Defender的事件队列开始。 此方法允许跨终结点、标识、电子邮件和应用程序高效地对事件进行会审，并减少攻击造成的损害。

## <a name="triage-your-incidents"></a>对事件进行会审

使用组织建议的优先级方法对事件列表进行会审后，Microsoft 365 Defender中的事件响应将启动。 会审意味着为事件分配一定程度的重要性或紧迫性，然后确定调查事件的顺序。

一个有用的示例指南，用于确定要在Microsoft 365 Defender中确定哪个事件的优先级，可通过以下公式进行汇总：*严重性 + 影响 = 优先级*。

- **严重性** 是由Microsoft 365 Defender及其集成安全组件指定的级别。
- **影响** 由组织决定，通常包括但不限于受影响的用户、设备、受影响的服务 (或) 的组合，甚至警报类型。

然后，分析师根据组织设置的 **优先级** 标准启动调查。

事件优先级可能因组织而异。 NIST 还建议考虑事件的功能和信息影响以及可恢复性。

下面介绍了一种会审方法：

1. 转到 [事件](incidents-overview.md) 页以启动会审。 此处可以看到影响组织的事件列表。 默认情况下，它们是从最近的事件安排到最早的事件。 在此处，还可以看到每个事件的不同列，其中显示了其严重性、类别、活动警报数和受影响实体等。 通过选择列名称，可以自定义列集并按其中某些列对事件队列进行排序。 还可以根据需要筛选事件队列。 有关可用筛选器的完整列表，请参阅 [优先级事件](incident-queue.md#available-filters)。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Microsoft 365安全门户中的事件" lightbox="../../media/first-incident-analyze/first-incident-analyze-queue.png":::

    针对这组事件执行会审的一个示例是确定影响更多用户和设备的事件的优先级。 在此示例中，你可能会优先考虑事件 ID 6769，因为它影响的最大实体数：7 台设备、6 个用户和 2 个邮箱。 此外，该事件似乎包含来自Microsoft Defender for Identity的警报，这些警报指示基于标识的警报和可能的凭据被盗。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="&quot;事件&quot;页显示Microsoft 365安全门户中影响很大的事件的示例" lightbox="../../media/first-incident-analyze/first-incident-analyze-high-impact.png":::

2. 选择事件名称旁边的圆圈以查看详细信息。 右侧将显示一个侧窗格，其中包含可进一步协助会审的其他信息。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="&quot;事件&quot;页显示Microsoft 365安全门户中事件侧窗格的示例" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png":::

   例如，通过查看攻击者根据事件类别使用的 [MITRE ATT&CK](https://attack.mitre.org/) 策略，你可能会优先考虑此事件，因为攻击者使用了被盗凭据、建立命令和控制、执行横向移动以及泄露了一些数据。 这些操作表明，攻击者已经深入网络，并可能窃取机密信息。

   此外，如果组织已实现零信任框架，则会将凭据访问视为值得优先处理的重要安全冲突。

   向下滚动侧窗格时，会看到特定受影响的实体，例如用户、设备和邮箱。 可以检查每个设备的曝光级别以及受影响邮箱的所有者。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="事件侧窗格详细信息" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png":::

3. 在侧窗格的后面，可以找到关联的警报。 Microsoft 365 Defender已经执行了上述警报与单个事件的相关性，节省了修复攻击所需的时间和资源。 警报是可疑的，因此可能是恶意系统事件，表明攻击者在网络上存在。

   在此示例中，87 个单独的警报被确定为一个安全事件的一部分。 可以查看所有警报，快速了解攻击的运行方式。

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Microsoft 365安全门户中事件端窗格中的警报" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png":::

## <a name="analyze-your-first-incident"></a>分析第一个事件

了解围绕警报的上下文同样重要。 通常，警报不是单个独立事件。 创建的进程链、命令和操作可能未同时发生。 因此，分析师必须在设备时间线中查找可疑实体的第一个和最后一个活动，以了解警报的上下文。

有多种使用Microsoft 365 Defender读取和分析数据的方法，但分析师的最终目标是尽快响应事件。 虽然Microsoft 365 Defender可以通过行业领先的[自动调查和响应](m365d-autoir.md)功能显著缩短修正[ (MTTR) 的平均时间](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/)，但始终存在需要手动分析的情况。

下面是一个示例：

1. 确定会审优先级后，分析师将通过选择事件名称开始深入分析。 此页将显示 **事件摘要** ，其中数据显示在选项卡中，以帮助进行分析。 在 **"警报"** 选项卡下，将显示警报的类型。 分析人员可以单击每个警报，向下钻取到各自的检测源。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="事件的&quot;摘要&quot;选项卡" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

    有关每个检测源涵盖的域的快速指南，请查看本文的 ["检测"](#detection-by-microsoft-365-defender) 部分。

2. 从 **"警报"** 选项卡，可以透视到检测源，以进行更深入的调查和分析。 例如，选择Microsoft Defender for Cloud Apps作为检测源的恶意软件检测会将分析员带到其相应的警报页面。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="显示选择事件警报的示例的&quot;事件&quot;页。" lightbox="../../media/first-incident-analyze/first-incident-analyze-select-alert.png":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Microsoft Defender for Cloud Apps中的相应页面" lightbox="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png":::

3. 若要进一步调查我们的示例，请滚动到页面底部以查看 **受影响的用户**。 若要查看恶意软件检测周围的活动和上下文，请选择 Annette Hill 的用户页面。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="用户页" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-page.png":::

4. 用户页按时间顺序列出事件，从 *TOR 网络 IP 地址警报中的风险登录* 开始。 虽然活动的可疑性取决于组织开展业务的方式的性质，但在大多数情况下，使用 Onion 路由器 (TOR) （一种允许用户匿名浏览 Web 的网络）在企业环境中可能被认为极不可能且不需要定期联机操作。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="用户的事件时间顺序列表" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png":::

5. 可以选择每个警报以获取有关活动的详细信息。 例如， **从 Tor IP 地址警报中选择活动** 会使你进入该警报自己的页面。 Annette 是Office 365管理员，它指示提升的权限，并且源事件可能导致访问机密信息。

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Microsoft Defender for Cloud Apps的警报详细信息" lightbox="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" :::

6. 通过选择其他警报，可以获取攻击的完整图片。

## <a name="next-step"></a>后续步骤

:::image type="content" source="../../media/first-incident-overview/first-incident-path-step2.png" alt-text="响应第一个事件页中的&quot;修正&quot;选项" lightbox="../../media/first-incident-overview/first-incident-path-step2.png":::

了解如何 [修正事件](first-incident-remediate.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
