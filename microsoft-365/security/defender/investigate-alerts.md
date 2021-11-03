---
title: 调查警报Microsoft 365 Defender
description: 调查跨设备、用户和邮箱看到的警报。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 3126523fd68afba29e3401533f7de2313f7df65b
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724759"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>调查警报Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

警报是所有事件的基础，指示环境中出现恶意或可疑事件。 警报通常是更广泛的攻击的一部分，并提供事件线索。

在Microsoft 365 Defender中，相关警报聚合在一起以形成[事件](incidents-overview.md)。 事件将始终提供更广泛的攻击上下文，但是，如果需要更深入的分析，分析警报可能会非常有价值。 

警报 **队列** 显示当前警报集。 在快速启动 Microsoft 365 Defender ( security.microsoft.com) 时，你可以从事件&警报>警报[) 。](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="报告门户中的警报队列Microsoft 365 Defender示例。":::

来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender 警报显示在此处。

默认情况下，Microsoft 365 Defender门户中的警报队列显示过去 30 天内的新警报和正在进行中的警报。 最新警报位于列表顶部，因此你可以先查看它。 

从默认警报队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中指定警报的子集。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="通知门户中警报队列的筛选器窗格Microsoft 365 Defender示例。":::

你可以根据以下条件筛选警报：

- Severity
- 状态
- Category
- 检测源
- 标记
- Policy
- 影响的资产

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Defender for Office 365 警报所需的角色

你需要具有以下任一角色来访问 Microsoft Defender Office 365警报：

- 对于Azure Active Directory (Azure AD) 角色：

   - 全局管理员

   - 安全管理员

   - 安全操作员

   - 全局读取者

   - 安全读取者

- Office 365安全&合规性角色组

   - 合规管理员

   - 组织管理 

- 自定义 [角色](custom-roles.md)

## <a name="analyze-an-alert"></a>分析警报

若要查看主警报页面，请选择警报的名称。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="通知门户中警报的详细信息Microsoft 365 Defender示例。":::

您还可以从"管理 **警报"窗格中** 选择"打开主警报 **页面"** 操作。

警报页面由以下部分组成： 

- 警报情景，它是与此警报相关的事件和警报链（按时间顺序）
- 摘要详细信息

在整个警报页面中，可以选择任意实体旁边的省略号 (**...)** 以查看可用操作，例如打开警报页面或将警报链接到其他事件。

### <a name="alert-sources"></a>警报源
Microsoft 365 Defender警报可能来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 等解决方案，以及适用于 Microsoft Cloud App Security 的应用管理Microsoft Cloud App Security。 你可能会注意到警报中具有预置字符的警报。 下表提供了一些指南，可帮助你根据警报上的预pend字符了解警报源的映射。

> [!NOTE]
> - 预置的 GUID 仅特定于统一体验，如统一警报队列、统一警报页面、统一调查和统一事件。<br>
> - 预置字符不会更改警报的 GUID。 对 GUID 的唯一更改是预置的组件。<br>


警报源 | Prepended 字符 
:---|:---
Microsoft Defender for Office 365 | `fa{GUID}` <br> 例如：`fa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Defender for Endpoint | `da` 或 `ed` 用于自定义检测警报 <br> 
Microsoft Defender for Identity | `aa{GUID}` <br> 例如：`aa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Cloud App Security |`ca{GUID}` <br> 例如：`ca123a456b-c789-1d2e-12f1g33h445h6i` 

### <a name="analyze-affected-assets"></a>分析受影响的资产

" **已采取** 操作"部分包含受影响资产的列表，如受此警报影响的邮箱、设备和用户。 

还可以选择"**在操作中心中** 查看"以查看操作中心的"历史记录"选项卡，Microsoft 365 Defender门户。 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>跟踪警报情景中的警报角色

警报情景在进程树视图中显示与警报相关的所有资产或实体。 标题中的警报是首次登录所选警报的页面时聚焦的警报。 警报情景中的资源可展开且可单击。 它们提供其他信息，并允许你立即在警报页面上下文中采取措施，从而加快响应速度。 

> [!NOTE]
> 警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。

### <a name="view-more-alert-information-on-the-details-page"></a>在详细信息页面上查看更多警报信息

详细信息页面显示所选警报的详细信息，以及相关详细信息和操作。 如果在警报情景中选择任何受影响的资产或实体，详细信息页面将发生更改，以提供所选对象的上下文信息和操作。

选择感兴趣的实体后，详细信息页面将发生更改以显示有关所选实体类型的信息、可用时的历史信息以及直接从警报页面对此实体采取措施的选项。

## <a name="manage-alerts"></a>管理警报

若要管理警报，请在警报队列中的行中选择警报，以查看"管理 **警报"** 窗格。 下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="通知门户中警报的摘要窗格Microsoft 365 Defender示例。":::

" **管理警报** "窗格允许您查看或指定：

- 警报状态 (新建、已解决、正在进行) 。
- 已分配警报的用户帐户
- 警报的分类 (未设置、真警报、假警报) 。
- 对于分类为真正的警报，为"确定"字段中警报 **的威胁** 类型。
- 对警报的注释。

> [!NOTE]
> 通过标记管理警报的一种方法。 Microsoft Defender for Office 365 的标记功能正在逐步推出，目前处于预览阶段。 <br>
> 目前，修改的标记名称仅适用于更新后 *创建的* 警报。 修改之前生成的通知不会反映更新的标记名称。 

在此窗格中，您还可以执行以下附加操作： 

- 打开主警报页面
- 咨询 Microsoft 威胁专家
- 查看提交
- 链接到其他事件
- 在时间线中查看警报
- 创建抑制规则

下面是一个示例。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="事件门户中警报Microsoft 365 Defender示例":::

其他操作的列表取决于警报的类型。

## <a name="resolve-an-alert"></a>解决警报

分析完警报并可以解决后，请转到警报的"管理警报"窗格，将其状态标记为"已解决"，并分类为 **"False** 警报"或"**真警报"。**  对于真正的警报，在"确定"字段中指定警报 **的威胁** 类型。

对警报进行分类并指定它们的决定有助于调整Microsoft 365 Defender，以便提供更多真实警报和更少的假警报。

## <a name="use-power-automate-to-triage-alerts"></a>使用Power Automate对警报分类

SecOps (新式安全) 团队需要自动化才能高效工作。 为了专注于搜寻和调查真实威胁，SecOps 团队Power Automate警报列表进行会审并消除不是威胁的警报。  

### <a name="criteria-for-resolving-alerts"></a>解决警报的条件

- 用户已打开外出消息

- 用户未标记为高风险

如果两者都为 true，则 SecOps 将警报标记为合法旅行并解决。 通知在解决后Microsoft Teams中发布。 

### <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>连接 Power Automate Microsoft Cloud App Security

若要创建自动化，你需要一个 API 令牌，然后才能将Power Automate连接到Microsoft Cloud App Security。 

1. 单击 **设置"，** 选择"**安全扩展"，** 然后单击"API令牌"选项卡中的"**添加令牌**"。 

2. 为令牌提供名称，然后单击"生成 **"。** 保存令牌，因为稍后将需要它。

### <a name="create-an-automated-flow"></a>创建自动化流

有关详细的分步过程，请参阅此处 [的视频](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)。 

此视频还介绍如何将电源自动化连接到云应用安全。 

## <a name="next-steps"></a>后续步骤

如果需要处理内事件，请继续执行 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)
