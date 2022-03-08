---
title: 事件响应和Microsoft 365 Defender
description: 调查在 Microsoft 365 Defender 门户中跨设备、用户和邮箱Microsoft 365 Defender事件。
keywords: 事件， 警报， 调查， 分析， 响应， 相关， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
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
ms.openlocfilehash: 25cdc0610f11d1bcd7e8c27faa1cdc9453677d51
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320869"
---
# <a name="incident-response-with-microsoft-365-defender"></a>事件响应和Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

事件Microsoft 365 Defender是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。 

Microsoft 365 服务和应用将在检测到可疑或恶意事件或活动时创建警报。 单个警报可提供有关已完成或持续攻击的有价值的线索。 但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用多种技术。 结果是租户中的多个实体将收到多个警报。 

由于将单个警报组合在一起以深入了解攻击可能非常困难且耗时，Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="如何将Microsoft 365 Defender事件关联到事件中。" lightbox="../../media/incidents-overview/incidents.png":::

观看此简短事件概述，Microsoft 365 Defender (4 分钟内) 。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

将相关警报组合为一个事件可使你对攻击具有全面了解。 例如，你可以看到：

- 攻击开始的位置。
- 使用了什么策略。
- 攻击侵入租户的程度。
- 攻击范围，例如受影响的设备、用户和邮箱数。 
- 与攻击有关的所有数据。

如果[启用，](m365d-enable.md)Microsoft 365 Defender[自动化和](m365d-autoir.md)人工智能自动调查和解决警报。 还可以执行其他修正步骤来解决攻击。 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的事件和警报

通过快速启动 &门户>**事件** 或事件管理事件Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">事件</a>。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件门户中的Microsoft 365 Defender页面。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。 下面是一个示例。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="事件门户中事件的&quot;摘要&quot;Microsoft 365 Defender示例" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

事件的其他选项卡包括：

- 警报 

  与事件及其信息相关的所有警报。

- 设备

  标识为事件的一部分或与事件相关的所有设备。

- 用户

  标识为事件的一部分或与事件相关的所有用户。

- 邮箱

  已标识为事件的一部分或与事件相关的所有邮箱。

- 调查

  事件 [警报](m365d-autoir.md) 触发的所有自动调查。

- 证据和响应

  事件警报中支持的所有事件和可疑实体。

- Graph (预览) 

  攻击的直观表示形式，该攻击将属于攻击的不同可疑实体与用户、设备和邮箱等相关资产连接在一起。

下面是事件及其数据与事件门户中事件选项卡Microsoft 365 Defender关系。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="事件及其数据与事件门户中事件选项卡Microsoft 365 Defender关系。" lightbox="../../media/incidents-overview/incidents-security-center.png":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>示例事件响应工作流Microsoft 365 Defender

下面是一个使用 Microsoft 365 Defender 门户响应 Microsoft 365 事件的示例工作流。

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="事件响应工作流的示例Microsoft 365。" lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

在持续进行的基础上，确定事件队列中的最高优先级事件以进行分析和解决，并为响应做好准备。 此操作包括以下步骤：

- [通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级的事件的会审。
- [通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。

对于您自己的事件响应工作流，请考虑以下步骤：

1. 对于每个事件，开始 [攻击和警报调查和分析](investigate-incidents.md)：
 
   1. 查看事件的摘要，了解事件的范围和严重性，以及哪些实体受"摘要"和"Graph (预览") 影响。

   1. 通过"警报"选项卡开始分析警报以了解其来源、范围 **和** 严重性。

   1. 根据需要，使用"设备、用户"和"邮箱"选项卡收集有关受影响设备、用户 **和邮箱** 的信息。 

   1. 查看Microsoft 365 Defender"调查 ["选项卡自动](m365d-autoir.md)解决 **某些警报。**
   
   1. 根据需要，使用事件数据集中的信息，通过"证据和响应"选项卡 **获取** 详细信息。

2. 在分析后或分析期间，执行遏制以减少攻击的任何其他影响并根除安全威胁。

3. 通过将租户资源还原到事件发生前所处的状态，尽可能从攻击中恢复。

4. [解决](manage-incidents.md#resolve-an-incident) 事件并花时间了解事件后：

   - 了解攻击的类型及其影响。
   - 研究威胁分析 [和安全](threat-analytics.md) 社区中的攻击，以寻找安全攻击趋势。
   - 回忆用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和 playbook。
   - 确定是否需要更改安全配置并实现这些更改。

如果你是安全分析的新增人员，请参阅第一[](incidents-overview.md)个事件响应简介，了解其他信息并逐步查看示例事件。

有关跨 Microsoft 产品的事件响应详细信息，请参阅 [本文](/security/compass/incident-response-overview)。

## <a name="example-security-operations-for-microsoft-365-defender"></a>示例安全操作Microsoft 365 Defender

下面是使用 SecOps (安全) 示例Microsoft 365 Defender。

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="安全操作示例Microsoft 365 Defender。" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

日常任务可能包括：

- [管理](manage-incidents.md) 事件
- 查看 [操作中心中的 AIR (自动调查和 ](m365d-action-center.md)) 操作
- 查看最新的 [威胁分析](threat-analytics.md)
- [响应](investigate-incidents.md) 事件

每月任务可能包括：

- 查看 [AIR 设置](m365d-configure-auto-investigation-response.md)
- 查看[安全分数和](microsoft-secure-score-improvement-actions.md)[威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 报告给 IT 安全管理链

季度任务可包括向 CISO (首席信息安全官报告并) 。

年度任务可能包括执行重大事件或泄露练习，以测试员工、系统和流程。 

每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。

有关[更多详细信息Microsoft 365 Defender集成到安全](integrate-microsoft-365-defender-secops.md)操作。

### <a name="secops-resources-across-microsoft-products"></a>跨 Microsoft 产品的 SecOps 资源

有关 Microsoft 产品中 SecOps 详细信息，请参阅以下资源：

- [Capabilities](/security/compass/security-operations-capabilities)
- [最佳做法](/security/compass/security-operations)
- [视频和幻灯片](/security/compass/security-operations-videos-and-decks)


## <a name="get-incident-notifications-by-email"></a>通过电子邮件获取事件通知

你可以设置Microsoft 365 Defender通知员工有关新事件或现有事件更新的电子邮件。 可以选择基于以下选项获取通知：

- 事件严重性。
- 设备组。
- 仅在每个事件的第一次更新时。

电子邮件通知包含有关事件的重要详细信息，如事件名称、严重性和类别等。 您还可以直接转到事件并立即开始分析。 有关详细信息，请参阅调查 [事件](investigate-incidents.md)。

可以在电子邮件通知中添加或删除收件人。 新收件人在添加事件后会收到通知。 

>[!NOTE]
>您需要" **管理安全设置"** 权限才能配置电子邮件通知设置。 如果选择使用基本权限管理，则具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。 <br> <br>
同样，如果组织使用基于角色的访问控制 (RBAC) ，则只能根据允许管理的设备组创建、编辑、删除和接收通知。

### <a name="create-a-rule-for-email-notifications"></a>为电子邮件通知创建规则

按照以下步骤创建新规则并自定义电子邮件通知设置。

1. 在导航窗格中，选择"**设置 > Microsoft 365 Defender >事件电子邮件通知"**。
2. 选择 **"添加项"**。
3. 在" **基本信息"** 页上，键入规则名称和说明，然后选择"下一步 **"**。
4. 在" **通知设置"** 页上，配置：
    - **警报严重程度** - 选择将触发事件通知的警报严重程度。 例如，如果只想通知你有关高严重性事件，请选择"高 **"**。
    - **设备组范围** - 可以指定所有设备组或从租户中的设备组列表中进行选择。
    - **仅在每个事件第一次发生时进行通知** - 选择是否仅需要对与其他所选内容相匹配的第一个警报进行通知。 与事件相关的后续更新或警报不会发送额外通知。
    - **在电子邮件中包含组织名称** - 选择是否希望组织名称显示在电子邮件通知中。
    - **包括特定于租户的门户链接** - 选择是否要在电子邮件通知中添加包含租户 ID 的链接，以便访问特定的 Microsoft 365 租户。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="事件电子邮件通知的通知设置。" lightbox="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png":::

5. 选择“**下一步**”。 在 **"收件人"** 页上，添加将接收事件通知的电子邮件地址。 键入 **每个** 新电子邮件地址后，选择"添加"。 若要测试通知并确保收件人在收件箱中收到通知，请选择" **发送测试电子邮件"**。 
6. 选择“**下一步**”。 在" **复查规则** "页上，查看规则的设置，然后选择"创建 **规则"**。 收件人将开始根据设置通过电子邮件接收事件通知。

若要编辑现有规则，请从规则列表中选择它。 在具有规则名称的窗格中，选择"编辑规则"，在"基本信息"、"通知设置"和"**收件人"页上进行更改**。

若要删除规则，请从规则列表中选择它。 在具有规则名称的窗格中，选择"删除 **"**。


## <a name="training-for-security-analysts"></a>针对安全分析师的培训

使用此 Microsoft Learn 的学习模块可了解如何使用 Microsoft 365 Defender事件和警报。

|培训：|使用 Microsoft 365 Defender 调查事件|
|---|---|
|![使用培训图标Microsoft 365 Defender事件。](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender来自多个服务的威胁数据，并使用 AI 将它们合并到事件和警报中。 了解如何尽可能缩短事件发生和管理之间的时间，以便后续响应和解决。 <p> 27 分钟 - 6 个单位 |

> [!div class="nextstepaction"]
> [开始>](/learn/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>后续步骤

根据安全团队的体验级别或角色，使用列出的步骤。

### <a name="experience-level"></a>体验级别

请遵循此表，获得安全分析和事件响应的体验级别。

| 级别 | 步骤 |
|:-------|:-----|
| **New** | <ol><li> 请参阅[响应你的第](first-incident-overview.md)一个事件演练，获取有关示例攻击的 Microsoft 365 Defender 门户中分析、修正和事后评审的典型流程的引导教程。 </li><li> 查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。 </li><li> [管理事件](manage-incidents.md)，其中包括根据事件管理工作流重命名、分配、分类和添加标记和注释。</li></ol> |
| **有经验的** | <ol><li> 从事件门户的"事件 **"页开始** Microsoft 365 Defender队列。 从这里您可以： </li> <ul><li> 查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。 </li><li> [管理事件](manage-incidents.md)，其中包括根据事件管理工作流重命名、分配、分类和添加标记和注释。 </li><li> [执行事件](investigate-incidents.md)调查。 </li></ul> </li><li> 使用威胁分析跟踪和响应 [新出现的威胁](threat-analytics.md)。 </li><li>  使用高级威胁搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。 </li><li> 请参阅 [这些事件响应手册，](/security/compass/incident-response-playbooks) 获取网络钓鱼、密码加密以及应用许可授予攻击的详细指南。 </li></ol> |


### <a name="security-team-role"></a>安全团队角色

请根据安全团队角色遵循此表。

| Role | 步骤 |
|:-------|:-----|
| 第 1 层 (事件响应)  | 从事件门户的"事件 **"页开始** Microsoft 365 Defender队列。 从这里您可以： <ul><li> 查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。 </li><li> [管理事件](manage-incidents.md)，其中包括根据事件管理工作流重命名、分配、分类和添加标记和注释。 </li></ul> |
| 第 2 层 (或分析员)  | <ol><li> 从 [事件](investigate-incidents.md)门户的"事件 **"页Microsoft 365 Defender** 事件。 </li><li> 请参阅 [这些事件响应手册，](/security/compass/incident-response-playbooks) 获取网络钓鱼、密码加密以及应用许可授予攻击的详细指南。 </li></ol> |
| 第 3 层 (高级安全分析师或威胁)  | <ol><li>从 [事件](investigate-incidents.md)门户的"事件 **"页Microsoft 365 Defender** 事件。 </li><li> 使用威胁分析跟踪和响应 [新出现的威胁](threat-analytics.md)。 </li><li> 使用高级威胁搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。 </li><li> 请参阅 [这些事件响应手册，](/security/compass/incident-response-playbooks) 获取网络钓鱼、密码加密以及应用许可授予攻击的详细指南。 |
| SOC 管理器 | 了解如何将安全[Microsoft 365 Defender中心与 SOC (集成) ](integrate-microsoft-365-defender-secops.md)。 |

