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
ms.openlocfilehash: 11e374dac4e1e0a13d3bdbc642922dca1b8954f4
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127379"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>了解用于 Microsoft Teams 的保留

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Microsoft Teams 的信息。

## <a name="how-retention-works-with-microsoft-teams"></a>用于 Microsoft Teams 的保留的工作原理

可使用保留策略保留 Teams 中的聊天和频道消息。 Teams 聊天存储在参与聊天的每个用户的邮箱中的隐藏文件夹内，Teams 频道消息存储在团队组邮箱中类似的隐藏文件夹中。 

务必了解，Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。 因此，建议创建保留策略来使用 Teams 位置保留和删除此 Teams 数据。 此保留策略可以从 Exchange 邮箱和由 Azure 提供技术支持的基础聊天服务中永久删除数据。 有关详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](https://go.microsoft.com/fwlink/?linkid=871258)，特别是[信息保护体系结构](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。

Teams 聊天和频道消息不受针对用户或组邮箱配置的保留策略影响。 即使 Teams 聊天和频道消息存储在 Exchange 中，此 Teams 数据仍将仅包含在针对 **Teams 频道消息**和 ** Teams 聊天**位置配置的保留策略中。

> [!NOTE]
> 如果用户包含在保留 Teams 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。 如果不需要为用户保留此 Teams 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。

为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。

如果保留策略为“保留后删除”：

![Teams 聊天和频道消息的保留流关系图](../media/TeamsRetentionLifecycle.png)

1. **如果在保留期内用户修改或删除了聊天或频道消息**，则该消息将移动（或在编辑的情况下复制）到 SubstrateHolds 文件夹（它是每个用户或组邮箱中的隐藏文件夹），并保留在该文件夹中，直到保留期到期。 在保留期到期之日，该消息将被永久删除。

2. **如果在保留期内未删除聊天或频道消息**，则该消息将在保留期到期后的一天内（ 0 到 24 小时）移至 SubstrateHolds 文件夹。 将消息移至 SubstrateHolds 文件夹一天后，该消息将被永久删除。 

> [!NOTE]
> 可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。 永久删除消息后，它不会在电子数据展示搜索中返回。

如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。

### <a name="content-paths-for-retain-only-retention-policy"></a>“仅保留”保留策略的内容路径

1. **如果有人在保留期内修改或删除聊天或频道消息**：会在 SubstrateHolds 文件夹中创建原始消息的副本，并保留到保留期结束，然后 SubstrateHolds 文件夹中的副本会在该项到期后永久删除。 

2. **如果项目在保持期内未遭修改或删除**：保留期前后无变化；消息仍保留在原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>“仅删除”保留策略的内容路径

1. **如果消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。 

2. **如果用户在保留期内删除项目**，该项目将立即移至 SubstrateHolds 文件夹。 如果用户从 SubstrateHolds 文件夹中删除消息或清空此文件夹，该项目将被永久删除。 否则，该消息将在移至 SubstrateHolds 文件夹一天后被永久删除。


## <a name="skype-for-business-and-teams-interop-chats"></a>Skype for Business 和 Teams 互操作聊天

当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。 Teams 保留策略将从 Teams 线程应用于这些消息。 

但是，如果已为 Skype for Business 开启对话历史记录，并且从 Skype for Business 客户端将其保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。 对于此内容，请使用为 Skype for Business 配置的保留策略。

## <a name="meetings-and-external-users"></a>会议和外部用户

频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息**位置。

临时会议邮件的存储方式与群组聊天消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 聊天**位置。

当外部用户加入你的组织主持的会议时：

- 如果外部用户使用租户中的来宾帐户加入，此用户将有一个影子邮箱，可遵循组织的 Teams 保留策略。 会议中的任何邮件都存储在用户的邮箱和影子邮箱中。 

- 如果外部用户使用来自其他 Microsoft 365 组织的帐户加入，则你的保留策略无法删除此用户的邮件，因为它们存储在该用户在其他租户中的邮箱中。 但是对于同一会议，你的保留策略可以为你的用户删除邮件。

## <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的聊天消息将存储在非活动邮箱中。 聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。 有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。 

如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

我们正在不断努力优化 Teams 中的保留功能。 在此期间，在对 Teams 频道消息和聊天使用保留时，需要注意以下几个限制：
  
- **Teams 需要单独的保留策略**。 创建保留策略并切换到 Teams 位置时，所有其他位置都会切换为关闭。 带有 Teams 的保留策略仅可包含 Teams，不可包含其他位置。

- **组织范围策略不包含 Teams**。 若要创建全组织范围策略，则不包括 Teams 频道消息和 Teams 聊天，因为它们需要单独的保留策略。

- **Teams 不支持高级保留**。 创建保留策略时，如果选择“[标识满足特定条件的内容的高级设置](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)”，则 Teams 位置不可用。 目前，当你选择这些位置时，Teams 中的保留适用于所有聊天和频道消息内容。

- **配置 Teams 频道消息的保留策略时，不包括专用频道中的 Teams 消息**。 保留策略目前不支持专用频道。 

- **Teams 最多可能需要七天的时间来清理过期的消息**。 应用于 Teams 的保留策略将在保留期到期时删除聊天和频道消息。 但是，它最多可能需要三到七天的时间来清理这些消息并永久删除它们。 此外，在保留期到期后和永久删除消息期间，可以使用电子数据展示工具搜索聊天和频道消息。
    
    > [!NOTE]
    > 过去的情况是，保留策略无法删除短于 30 天的 Teams 内容，但是我们已经删除了此限制。 现在，Teams 内容的保留期可以是你选择的任意天数，它可以短至 1 天。 如果保留期为一天，则在保留期到期后的最多七天内将永久删除消息。

- **Outlook 错误显示的问题**。 如果为 Skype 或 Teams 位置创建保留策略，则当用户在 Outlook 桌面客户端中查看邮箱文件夹的属性时，这些策略中的某个策略将显示为默认文件夹策略。 这是 Outlook 中的错误显示问题，也是一个[已知问题](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。 应作为默认文件夹策略显示的是应用于该文件夹的邮箱保留策略。 Skype 或 Teams 保留策略不适用于用户的邮箱。

- **配置问题**： 
    - 为“**Teams 频道消息**”位置选择“**选择团队**”时，你可能会看到不属于团队的 Microsoft 365 组。 不要选择这些组。
    
    - 为“**Teams 聊天**”位置选择“**选择用户**”时，你可能会看到来宾和非邮箱用户。 保留策略并非专为这些用户设计的，因此请不要选择他们。

## <a name="configuration-guidance"></a>配置指南

如果你已准备好在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。
