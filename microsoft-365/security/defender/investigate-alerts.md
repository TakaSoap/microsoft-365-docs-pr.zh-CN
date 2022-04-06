---
title: 在 Microsoft 365 Defender 中调查警报
description: 调查跨设备、用户和邮箱看到的警报。
keywords: 事件， 警报， 调查， 分析， 响应， 相关性， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 20ae5bd77b9a4a962093db1e3d92d8f765a9a9a3
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664691"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中调查警报

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

>[!Note]
>本文介绍Microsoft 365 Defender中的安全警报。 但是，当用户在Microsoft 365中执行特定活动时，可以使用活动警报向你自己或其他管理员发送电子邮件通知。 有关详细信息，请参阅[创建活动警报 - Microsoft 365合规性|Microsoft Docs](../../compliance/create-activity-alerts.md)。

警报是所有事件的基础，指示环境中发生恶意或可疑事件。 警报通常是更广泛的攻击的一部分，并提供有关事件的线索。

在Microsoft 365 Defender中，相关警报聚合在一起以形成[事件](incidents-overview.md)。 事件始终提供攻击的更广泛上下文，但是，当需要更深入的分析时，分析警报可能很有价值。

**警报队列** 显示当前的警报集。 在快速启动Microsoft 365 Defender [门户](https://go.microsoft.com/fwlink/p/?linkid=2077139)时，可以从 **事件&警报>警报** 进入警报队列。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Microsoft 365 Defender门户中的&quot;警报&quot;部分" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png":::

来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender）的警报将显示在此处。

默认情况下，Microsoft 365 Defender门户中的警报队列显示过去 30 天内的新警报和正在进行的警报。 最近的警报位于列表顶部，因此可以先查看它。 

在默认警报队列中，可以选择 **"筛选器** "以查看 **"筛选器** "窗格，可从中指定警报的子集。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Microsoft 365 Defender门户中的&quot;筛选器&quot;部分。" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png":::

可以根据以下条件筛选警报：

- Severity
- 状态
- 服务源
- 实体 (受影响的资产) 
- 自动调查状态

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Defender for Office 365警报所需的角色

需要具有以下任一角色才能访问Microsoft Defender for Office 365警报：

- 对于Azure Active Directory (Azure AD) 全局角色：

   - 全局管理员

   - 安全管理员

   - 安全操作员

   - 全局读取者

   - 安全读取者

- Office 365安全&合规性角色组

   - 合规管理员

   - 组织管理 

- [自定义角色](custom-roles.md)

## <a name="analyze-an-alert"></a>分析警报

若要查看主警报页，请选择警报的名称。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 Defender门户中警报的详细信息" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png":::

还可以从"**管理警报**"窗格中选择"**打开主警报页**"操作。

警报页由以下部分组成： 

- 警报故事，这是与此警报相关的事件和警报链，按时间顺序排列
- 摘要详细信息

在整个警报页面中，可以选择 (的省略号 **...**) 任何实体旁边，查看可用操作，例如将警报链接到另一个事件。 可用操作的列表取决于警报的类型。

### <a name="alert-sources"></a>警报源

Microsoft 365 Defender警报可能来自Microsoft Defender for Endpoint、Microsoft Defender for Office 365等解决方案，Microsoft Defender for Cloud Apps，以及用于Microsoft Defender for Cloud Apps的应用治理加载项。 你可能会注意到警报中包含前置字符的警报。 下表提供了指导，帮助你了解基于警报的预置字符的警报源映射。

> [!NOTE]
> - 预置的 GUID 仅特定于统一体验，例如统一警报队列、统一警报页、统一调查和统一事件。
> - 预置字符不会更改警报的 GUID。 对 GUID 的唯一更改是前置组件。

| 警报源 | 预置字符 |
| :---|:--- |
| Microsoft Defender for Office 365 | `fa{GUID}` <br> 例如：`fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Endpoint | `da` 或 `ed` 自定义检测警报 <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> 例如：`aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> 例如：`ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>分析受影响的资产

" **执行的操作"** 部分列出了受此警报影响的资产，例如邮箱、设备和用户。 

还可以 **在操作中心中选择"视图**"，在Microsoft 365 Defender门户中查看 **操作中心的**"**历史记录**"选项卡。 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>跟踪警报在警报故事中的角色

警报故事在进程树视图中显示与警报相关的所有资产或实体。 首次登录所选警报页面时，标题中的警报是焦点。 警报故事中的资产是可展开和可单击的。 它们提供其他信息，并通过允许你在警报页面的上下文中采取正确的操作来加快响应。 

> [!NOTE]
> 警报故事部分可能包含多个警报，其中包含与所选警报之前或之后出现的同一执行树相关的其他警报。

### <a name="view-more-alert-information-on-the-details-page"></a>查看详细信息页上的更多警报信息

详细信息页显示所选警报的详细信息，其中包含与之相关的详细信息和操作。 如果在警报故事中选择任何受影响的资产或实体，详细信息页会更改，以提供所选对象的上下文信息和操作。

选择感兴趣的实体后，详细信息页会更改，以显示有关所选实体类型的信息、可用的历史信息，以及直接从警报页对此实体采取行动的选项。

## <a name="manage-alerts"></a>管理警报

若要管理警报，请在警报页面的摘要详细信息部分中选择" **管理** 警报"。 对于单个警报，下面是" **管理警报** "窗格的示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Microsoft 365 Defender门户中的&quot;管理警报&quot;部分" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png":::

" **管理警报** "窗格允许查看或指定：

- 正在) 的新、已解决 (警报状态。
- 已分配警报的用户帐户。
- 警报的分类：

   - **未设置** (默认) 。

   - **具有** 威胁类型的正数。 对准确指示真实威胁的警报使用此分类。 指定威胁类型可帮助安全团队查看威胁模式，并采取措施以保护组织免受威胁。

   - 具有活动类型的 **信息性预期活动**。 使用此类别中的选项对安全测试、红色团队活动以及受信任应用和用户的预期异常行为的警报进行分类。

   - 即使没有恶意活动，创建的警报类型也为 **误** 报。 将警报分类为误报有助于Microsoft 365 Defender提高检测质量。

- 对警报的注释。

> [!NOTE]
> 通过使用标记管理警报的一种方法。 Microsoft Defender for Office 365的标记功能正在逐步推出，目前处于预览状态。 <br>
> 目前，修改后的标记名称仅应用于更新 *后* 创建的警报。 修改前生成的警报不会反映更新后的标记名称。 

若要管理一 *组类似于特定警报的警报*，请在警报页的摘要详细信息部分的 **INSIGHT** 框中选择 **"查看类似警报**"。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="在Microsoft 365 Defender门户中管理警报":::

在" **管理警报** "窗格中，可以同时对所有相关警报进行分类。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="在Microsoft 365 Defender门户中管理相关警报":::

如果过去已对类似警报进行分类，则可以使用Microsoft 365 Defender建议来节省时间，以了解如何解决其他警报。 在摘要详细信息部分中，选择 **推荐**。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="为警报选择建议的示例":::

**"推荐**"选项卡提供下一步操作和建议，用于调查、修正和预防。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="警报建议示例":::

## <a name="resolve-an-alert"></a>解决警报

分析完警报并可解决后，转到警报或类似 **警报的"管理警报**"窗格，将状态标记为 **"已解决**"，然后将其归类为具有威胁类型、**信息活动、预期活动** 类型或 **误报** 的 **True** 阳性。

分类警报有助于Microsoft 365 Defender提高检测质量。

## <a name="use-power-automate-to-triage-alerts"></a>使用Power Automate对警报进行会审

新式安全操作 (SecOps) 团队需要自动化才能有效工作。 为了专注于搜寻和调查实际威胁，SecOps 团队使用Power Automate对警报列表进行会审，并消除那些不是威胁的威胁。  

### <a name="criteria-for-resolving-alerts"></a>解决警报的条件

- 用户已打开外出消息

- 用户未标记为高风险

如果两者都为 true，则 SecOps 会将警报标记为合法旅行并将其解决。 警报解决后，会在Microsoft Teams中发布通知。

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>连接 Power Automate Microsoft Defender for Cloud Apps

若要创建自动化，需要一个 API 令牌，然后才能将Power Automate连接到Microsoft Defender for Cloud Apps。

1. 单击 **设置**，选择 **"安全扩展**"，然后单击 **"API 令牌**"选项卡中的 **"添加** 令牌"。

2. 为令牌提供名称，然后单击" **生成**"。 保存令牌，因为稍后需要它。

### <a name="create-an-automated-flow"></a>创建自动流

有关详细的分步过程，请 [参阅此处](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)的视频。

此视频还介绍了如何将电源自动连接到Defender for Cloud应用。

## <a name="next-steps"></a>后续步骤

根据进程内事件的需要，继续 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)
