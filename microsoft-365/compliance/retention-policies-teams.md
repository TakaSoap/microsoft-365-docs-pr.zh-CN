---
title: 了解用于 Teams 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解适用于 Microsoft Teams 的保留策略。
ms.openlocfilehash: 985131900a5e07188c0af641fb86f794d558f80b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919778"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>了解用于 Microsoft Teams 的保留

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 如果在 Teams 中显示一条消息，显示聊天或邮件已被保留策略删除，请参阅 [Teams 中有关保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本页上的信息适用于管理这些保留策略的 IT 管理员。

本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Microsoft Teams 消息的信息。

有关其他工作负载，请参阅：

- [了解用于 SharePoint 和 OneDrive 的保留](retention-policies-sharepoint.md)
- [了解用于 Yammer 的保留](retention-policies-yammer.md)
- [了解用于 Exchange 的保留](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保留和删除包括哪些内容

可使用 Teams 的保留策略来保留和删除以下 Teams 项目：聊天和频道消息，包括嵌入的图像、表格、超文本链接、其它 Teams 消息和文件的链接，以及 [卡片内容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。 聊天消息包括聊天中所有人员的姓名；频道消息包含团队名称和消息标题（如有提供）。 

> [!NOTE]
> 包括卡内容是最近添加的一项功能，现在已完全推出给租户。 有关详细信息，请参阅 [通过 Teams 中应用 Microsoft 365 用于自适应卡片内容的合规功能现已可用](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)。

专用频道中的 Teams 消息目前不支持保留策略。 当你对 Teams 使用保留策略时，代码片段、来自 Teams 移动客户端的语音备忘录、缩略图、公告图像和来自其他人的图释的反应不包含在内。

通过 Teams 使用的电子邮件和文件不包括在 Teams 的保留策略内。 这些项目有自己的保留策略。

## <a name="how-retention-works-with-microsoft-teams"></a>用于 Microsoft Teams 的保留的工作原理

可使用保留策略保留和删除 Teams 中的聊天和频道消息的数据。 Exchange 邮箱用于在后台存储这些邮件。 Teams 聊天中的数据存储在聊天中包含的每个用户的邮箱中的隐藏文件夹中，组邮箱中的类似隐藏文件夹用于 Teams 频道消息。

通过RecipientTypeDetails属性列出这些邮箱：

- **MailUser**：这些邮箱存储基于云的 Teams 用户的消息。
- **UserMailbox**：这些邮箱存储 [本地 Teams 用户](search-cloud-based-mailboxes-for-on-premises-users.md) 的消息。
- **组邮件**：这些邮箱为 Teams 频道存储信息。

其他邮箱类型，如用于Teams会议室的RoomMailbox，不支持Teams的保留策略。

务必了解，Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。 因此，如果你因合规性原因需要删除 Teams 消息，则建议你对 Teams 使用保留策略，因为这样可以从 Exchange 邮箱和 Azure 支持的基础聊天服务中永久删除此数据。 有关基础架构的详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](/MicrosoftTeams/security-compliance-overview)，特别是[信息保护体系结构](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。

即使 Teams 聊天和频道消息存储在邮箱中，此 Teams 数据仍将仅包含在针对 **Teams 频道消息** 和 **Teams 聊天** 位置配置的保留策略中。 Teams 聊天和频道消息不受针对 Exchange 用户或组邮箱配置的保留策略影响。

> [!NOTE]
> 如果用户包含在保留 Teams 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。 如果不需要为用户保留此 Teams 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。

为聊天和频道消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Teams 消息的隐藏文件夹中的项目。 计时器作业最多需要 7 天才能运行。 这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的另一个隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。

为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。

如果保留策略为“保留后删除”：

![Teams 聊天和频道消息的保留流关系图](../media/teamsretentionlifecycle.png)

对于图中的两条路径：

1. **如果用户在保留期内编辑或删除了聊天或频道消息**，则该原始消息将在 21 天内复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中。 消息将存储在此处，直到保留期到期，然后在 24 小时之内将其永久删除。

2. **如果未删除聊天或频道消息**，并且对于编辑后的当前消息，则保留期到期后，消息将被移至 SubstrateHolds 文件夹。 此操作自到期之日起最多需要 7 天。 消息位于 SubstrateHolds 文件夹中时，它将在 24 小时内被永久删除。 

> [!NOTE]
> 可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。 从此 SubstrateHolds 文件夹中删除消息之前，仍可以由电子数据展示工具搜索。

如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。

### <a name="content-paths-for-retain-only-retention-policy"></a>“仅保留”保留策略的内容路径

1. **如果编辑或删除了聊天消息或频道消息**：21 天内在 SubstrateHolds 文件夹中创建原始消息的副本，并将其保留在那里，直到保留期到期。 然后，此消息会在 24 小时内从 SubstrateHolds 文件夹中永久删除。

2. **如果项目在保持期内未遭修改或删除** 以及保留期内编辑后的当前消息：保留期前后无变化；消息仍保留在原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>“仅删除”保留策略的内容路径

1. **如果消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。 此操作自到期之日起最多需要 7 天。 然后，此消息会在 24 小时内从 SubstrateHolds 文件夹中永久删除。

2. **如果用户在保留期内删除项目**，该项目将在 21 天内移至 SubstrateHolds 文件夹，然后在 24 小时内被永久删除。


## <a name="skype-for-business-and-teams-interop-chats"></a>Skype for Business 和 Teams 互操作聊天

当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。 Teams 保留策略将从 Teams 线程应用于这些消息。 

但是，如果已为 Skype for Business 开启对话历史记录，并且从 Skype for Business 客户端将其保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。 对于此内容，请使用为 Skype for Business 配置的保留策略。

## <a name="meetings-and-external-users"></a>会议和外部用户

频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息** 位置。

即兴和预定会议消息的存储方式与群组聊天消息相同，因此对于这些数据，请在配置保留策略时选择 **Teams 聊天** 位置。

当外部用户加入你的组织主持的会议时：

- 如果外部用户使用租户中的来宾帐户加入，此用户将有一个影子邮箱，可遵循组织的 Teams 保留策略。 会议中的任何邮件都存储在用户的邮箱和影子邮箱中。 

- 如果外部用户使用来自其他 Microsoft 365 组织的帐户加入，则你的保留策略无法删除此用户的邮件，因为它们存储在该用户在其他租户中的邮箱中。 但是对于同一会议，你的保留策略可以为你的用户删除邮件。

## <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

如果在 Exchange Online 中有邮箱的用户离开了你的组织，并且他们的 Microsoft 365 帐户被删除，则他们要保留的聊天邮件将存储在非活动邮箱中。 聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。 有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。 

如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

我们正在不断努力优化 Teams 中的保留功能。 在此期间，在对 Teams 频道消息和聊天使用保留时，需要注意以下几个限制：

- **Outlook 错误显示的问题**。 如果为 Skype 或 Teams 位置创建保留策略，则当用户在 Outlook 桌面客户端中查看邮箱文件夹的属性时，这些策略中的某个策略将显示为默认文件夹策略。 这是 Outlook 中的错误显示问题，也是一个[已知问题](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。 应作为默认文件夹策略显示的是应用于该文件夹的邮箱保留策略。 Skype 或 Teams 保留策略不适用于用户的邮箱。

- **配置问题**： 
    - 为“**Teams 频道消息**”位置选择“**选择团队**”时，你可能会看到不属于团队的 Microsoft 365 组。 不要选择这些组。
    
    - 为“**Teams 聊天**”位置选择“**选择用户**”时，你可能会看到来宾和非邮箱用户。 保留策略并非专为这些用户设计的，因此请不要选择他们。

## <a name="configuration-guidance"></a>配置指南

如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。

如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。