---
title: 带有Microsoft 365 Defender的事件响应
description: 调查在Microsoft 365 Defender门户中跨设备、用户和邮箱看到的事件。
keywords: 事件， 警报， 调查， 分析， 响应， 相关性， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 70f75fd5986a5d837e33b3caf0b7cb23239ddce5
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731583"
---
# <a name="incident-response-with-microsoft-365-defender"></a>带有Microsoft 365 Defender的事件响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender中的事件是构成攻击事件的相关警报和关联数据的集合。

Microsoft 365 服务和应用将在检测到可疑或恶意事件或活动时创建警报。 单个警报可提供有关已完成或持续攻击的有价值的线索。 但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用多种技术。 结果是租户中的多个实体将收到多个警报。

由于将单个警报组合在一起以深入了解攻击可能非常困难且耗时，Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender如何将实体中的事件关联到事件。" lightbox="../../media/incidents-overview/incidents.png":::

观看Microsoft 365 Defender (4 分钟内) 事件的简短概述。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

将相关警报组合为一个事件可使你对攻击具有全面了解。 例如，你可以看到：

- 攻击开始的位置。
- 使用了什么策略。
- 攻击侵入租户的程度。
- 攻击范围，例如受影响的设备、用户和邮箱数。
- 与攻击有关的所有数据。

如果[启用](m365d-enable.md)，Microsoft 365 Defender可以通过自动化[和人工智能自动调查和解决](m365d-autoir.md)警报。 还可以执行其他修正步骤来解决攻击问题。

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender门户中的事件和警报

可在快速启动Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>时 **管理事件&警报>事件**。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender门户中的&quot;事件&quot;页。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

选择事件名称会显示事件摘要，并提供对选项卡的访问权限以及附加信息。 下面是一个示例。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 Defender门户中事件的摘要页" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

事件的其他选项卡包括：

- 警报

  与事件相关的所有警报及其信息。

- 设备

  已确定为事件一部分或与事件相关的所有设备。

- 用户

  已确定为事件一部分或与事件相关的所有用户。

- 邮箱

  已确定为事件一部分或与事件相关的所有邮箱。

- 调查

  事件中的警报触发的所有 [自动调查](m365d-autoir.md) 。

- 证据和响应

  事件警报中支持的所有事件和可疑实体。

- Graph (预览) 

  攻击的可视化表示形式，用于将参与攻击的不同可疑实体与其相关资产（如用户、设备和邮箱）连接起来。

下面是事件与其数据之间的关系，以及Microsoft 365 Defender门户中事件的选项卡。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="事件及其数据与Microsoft 365 Defender门户中事件选项卡的关系。" lightbox="../../media/incidents-overview/incidents-security-center.png":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender 的事件响应工作流示例

下面是一个示例工作流，用于使用Microsoft 365 Defender门户响应Microsoft 365中的事件。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 Defender门户的事件响应工作流示例。" lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

在持续进行的基础上，确定事件队列中的最高优先级事件以进行分析和解决，并为响应做好准备。 此操作包括以下步骤：

- [通过](incident-queue.md) 筛选和排序事件队列来确定优先级最高的事件。
- 通过修改事件的标题、将事件分配给分析师以及添加标记和注释来[管理](manage-incidents.md)事件。

对于你自己的事件响应工作流，请考虑以下步骤：

1. 对于每个事件，请开始 [攻击和警报调查和分析](investigate-incidents.md)：

   1. 查看事件摘要，了解事件的范围和严重性，以及"**摘要**"和 **"Graph" (** 预览) 选项卡影响的实体。

   1. 使用 **"警报"** 选项卡开始分析警报以了解警报的来源、范围和严重性。

   1. 根据需要，使用 **"设备**"、" **用户**"和"邮箱"选项卡收集有关受影响的设备、用户和 **邮箱** 的信息。

   1. 查看Microsoft 365 Defender如何使用"**调查**"选项卡 [自动解析某些警报](m365d-autoir.md)。

   1. 根据需要，使用事件数据集中的信息，使用" **证据和响应** "选项卡获取详细信息。

2. 在分析后或分析期间，执行遏制以减少攻击的任何其他影响并根除安全威胁。

3. 通过将租户资源还原到事件发生前所处的状态，尽可能从攻击中恢复。

4. [解决](manage-incidents.md#resolve-an-incident) 该事件，并花些时间进行事后学习：

   - 了解攻击的类型及其影响。
   - 研究 [威胁分析](threat-analytics.md) 和安全社区中针对安全攻击趋势的攻击。
   - 回忆用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和 playbook。
   - 确定是否需要更改安全配置并实现这些更改。

如果你不了解安全分析，请参阅 [有关响应第一个事件的简介](incidents-overview.md) ，了解其他信息，并逐步了解示例事件。

有关 Microsoft 产品中的事件响应的详细信息，请参 [阅本文](/security/compass/incident-response-overview)。

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender的安全操作示例

下面是用于Microsoft 365 Defender的 SecOps)  (安全操作的示例。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Microsoft 365 Defender的安全操作示例" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

日常任务可以包括：

- [管理](manage-incidents.md) 事件
- 在操作中心[查看 AIR) 操作 (自动调查和响应 ](m365d-action-center.md)
- 查看最新的 [威胁分析](threat-analytics.md)
- [响应](investigate-incidents.md) 事件

每月任务可以包括：

- 查看 [AIR 设置](m365d-configure-auto-investigation-response.md)
- 查看 [安全分数](microsoft-secure-score-improvement-actions.md) 和 [威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 向 IT 安全管理链报告

季度任务可以包括向首席信息安全官 (CISO) 报告和介绍安全结果。

年度任务可以包括执行重大事件或违规练习来测试员工、系统和流程。

每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。

有关更多详细信息，请参阅将[Microsoft 365 Defender集成到安全操作](integrate-microsoft-365-defender-secops.md)中。

### <a name="secops-resources-across-microsoft-products"></a>Microsoft 产品中的 SecOps 资源

有关 Microsoft 产品中的 SecOps 的详细信息，请参阅以下资源：

- [Capabilities](/security/compass/security-operations-capabilities)
- [最佳做法](/security/compass/security-operations)
- [视频和幻灯片](/security/compass/security-operations-videos-and-decks)

## <a name="get-incident-notifications-by-email"></a>通过电子邮件获取事件通知

可以设置Microsoft 365 Defender，通过电子邮件通知员工有关新事件或现有事件的更新。 可以选择根据以下情况获取通知：

- 事件严重性。
- 设备组。
- 仅在每个事件的第一次更新。

电子邮件通知包含有关事件的重要详细信息，例如事件名称、严重性和类别等。 还可以直接转到事件并立即开始分析。 有关详细信息，请参阅 ["调查事件](investigate-incidents.md)"。

可以在电子邮件通知中添加或删除收件人。 新收件人添加事件后会收到有关事件的通知。

> [!NOTE]
> 需要管理 **安全设置权** 限才能配置电子邮件通知设置。 如果选择使用基本权限管理，具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。 <br> <br>
同样，如果组织使用基于角色的访问控制 (RBAC) ，则只能根据允许管理的设备组创建、编辑、删除和接收通知。

### <a name="create-a-rule-for-email-notifications"></a>为电子邮件通知创建规则

按照以下步骤创建新规则并自定义电子邮件通知设置。

1. 在导航窗格中，选择 **设置 > Microsoft 365 Defender >事件电子邮件通知**。
2. 选择 **"添加项**"。
3. 在 **"基本信息** "页上，键入规则名称和说明，然后选择 **"下一步**"。
4. 在 **"通知设置"** 页上，配置：
    - **警报严重程度** - 选择将触发事件通知的警报严重程度。 例如，如果只想了解高严重性事件，请选择 **"高**"。
    - **设备组范围** - 可以指定所有设备组或从租户中的设备组列表中进行选择。
    - **仅在每个事件第一次发生时进行通知** - 选择是否仅需要对与其他所选内容相匹配的第一个警报进行通知。 与事件相关的后续更新或警报不会发送额外通知。
    - **在电子邮件中包含组织名称** - 选择是否希望组织名称显示在电子邮件通知中。
    - **包括特定于租户的门户链接** - 选择是否要在电子邮件通知中添加包含租户 ID 的链接，以便访问特定的 Microsoft 365 租户。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Microsoft 365 Defender门户中事件电子邮件通知的通知设置页。" lightbox="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png":::

5. 选择 **下一步**。 在 **"收件人"** 页上，添加将接收事件通知的电子邮件地址。 键入每个新电子邮件地址后选择 **"添加** "。 若要测试通知并确保收件人收到收件箱中的通知，请选择 **"发送测试电子邮件**"。
6. 选择 **下一步**。 在 **"审阅规则** "页上，查看规则的设置，然后选择 **"创建规则**"。 收件人将开始根据设置通过电子邮件接收事件通知。

若要编辑现有规则，请从规则列表中选择它。 在包含规则名称的窗格上，选择 **"编辑规则** "，并在 **"基本信息**"、" **通知设置**"和" **收件人** "页上进行更改。

若要删除规则，请从规则列表中选择它。 在包含规则名称的窗格上，选择 **"删除**"。

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

使用 Microsoft Learn 中的此学习模块了解如何使用Microsoft 365 Defender来管理事件和警报。

|培训：|使用 Microsoft 365 Defender 调查事件|
|---|---|
|![使用Microsoft 365 Defender训练图标调查事件。](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender将来自多个服务的威胁数据统一，并使用 AI 将其合并到事件和警报中。 了解如何尽可能缩短事件发生和管理之间的时间，以便后续响应和解决。 <p> 27 分钟 - 6 个单位 |

> [!div class="nextstepaction"]
> [开始>](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>后续步骤

根据你在安全团队中的经验级别或角色使用列出的步骤。

### <a name="experience-level"></a>体验级别

请按照下表了解安全分析和事件响应方面的经验级别。

| 级别 | 步骤 |
|:-------|:-----|
| **New** | <ol><li> 请参阅["响应你的第一个事件"演练](first-incident-overview.md)，在Microsoft 365 Defender门户中通过示例攻击来指导分析、修正和事后审查的典型过程。 </li><li> 查看应根据严重性和其他因素确定哪些事件 [的优先级](incident-queue.md) 。 </li><li> [管理事件](manage-incidents.md)，包括基于事件管理工作流重命名、分配、分类和添加标记和注释。</li></ol> |
| **经历** | <ol><li> 从Microsoft 365 Defender门户的 **"事件**"页开始事件队列。 从这里您可以： </li> <ul><li> 查看应根据严重性和其他因素确定哪些事件 [的优先级](incident-queue.md) 。 </li><li> [管理事件](manage-incidents.md)，包括基于事件管理工作流重命名、分配、分类和添加标记和注释。 </li><li> [对事件](investigate-incidents.md)进行调查。 </li></ul> </li><li> 使用 [威胁分析](threat-analytics.md)跟踪和响应新出现的威胁。 </li><li>  通过 [高级威胁搜寻](advanced-hunting-overview.md)主动搜寻威胁。 </li><li> 有关网络钓鱼、密码喷射和应用许可授予攻击的详细指南，请参阅这些 [事件响应 playbook](/security/compass/incident-response-playbooks) 。 </li></ol> |

### <a name="security-team-role"></a>安全团队角色

根据安全团队角色遵循此表。

| Role | 步骤 |
|---|---|
| 事件响应者 (第 1 层)  | 从Microsoft 365 Defender门户的 **"事件**"页开始事件队列。 从这里您可以： <ul><li> 查看应根据严重性和其他因素确定哪些事件 [的优先级](incident-queue.md) 。 </li><li> [管理事件](manage-incidents.md)，包括基于事件管理工作流重命名、分配、分类和添加标记和注释。 </li></ul> |
| 安全调查员或分析师 (第 2 层)  | <ol><li> [从Microsoft 365 Defender](investigate-incidents.md)门户的 **"事件**"页对事件进行调查。 </li><li> 有关网络钓鱼、密码喷射和应用许可授予攻击的详细指南，请参阅这些 [事件响应 playbook](/security/compass/incident-response-playbooks) 。 </li></ol> |
| 高级安全分析师或威胁猎人 (第 3 层)  | <ol><li>[从Microsoft 365 Defender](investigate-incidents.md)门户的 **"事件**"页对事件进行调查。 </li><li> 使用 [威胁分析](threat-analytics.md)跟踪和响应新出现的威胁。 </li><li> 通过 [高级威胁搜寻](advanced-hunting-overview.md)主动搜寻威胁。 </li><li> 有关网络钓鱼、密码喷射和应用许可授予攻击的详细指南，请参阅这些 [事件响应 playbook](/security/compass/incident-response-playbooks) 。 |
| SOC 管理器 | 了解如何[将Microsoft 365 Defender集成到安全运营中心 (SOC) ](integrate-microsoft-365-defender-secops.md)。 |
