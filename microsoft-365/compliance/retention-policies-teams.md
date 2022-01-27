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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解适用于 Microsoft Teams 的保留策略。
ms.openlocfilehash: 39fb6ce1614c59bf97dbea23e6d6f3e80c7f36dd
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241827"
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

可以通过使用 Teams 的保留策略删除 Teams 聊天消息、频道消息、专用频道消息，除了消息中的文本外，以下项目可以因合规性原因而保留。嵌入的图像、表格、超文本链接、到其他 Teams 消息和文件的链接，以及[卡内容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。 聊天消息和专用频道消息包括对话中所有人员的姓名；频道消息包含团队名称和消息标题（如有提供）。 

当你对 Teams 使用保留策略时，来自 Teams 移动客户端的代码片段、来自 Teams 移动客户端的语音备忘录、缩略图、公告图像以及其他人的图释反应不会保留。

在 Teams 中所使用的电子邮件和文件不包括在 Teams 的保留政策中。这些项目有它们自己的保留政策。

## <a name="how-retention-works-with-microsoft-teams"></a>用于 Microsoft Teams 的保留工作原理

使用本节了解合规性要求是如何通过后端存储和流程满足的，应该由电子数据展示工具来验证，而非由目前在 Teams 应用程序中显示的消息来验证。

可以使用保留策略来保留 Teams 中的聊天记录和频道消息的数据，并删除这些聊天记录和消息。 Exchange 邮箱在后台用于存储这些消息中复制的数据。 Teams 聊天中的数据存储在聊天中包含的每个用户的邮箱中的隐藏文件夹中，组邮箱中的类似隐藏文件夹用于 Teams 频道消息。 这些隐藏的文件夹不是为了供用户或管理员直接访问，而是存储合规性管理员可以使用电子数据展示工具搜索的数据。

通过 RecipientTypeDetails 属性列出这些邮箱:

- **UserMailbox**: 这些邮箱存储基于云的 Teams 用户的消息。
- **MailUser**: 这些邮箱存储 [本地 Teams 用户](search-cloud-based-mailboxes-for-on-premises-users.md) 的消息。
- **GroupMailbox**：这些邮箱存储 Teams 标准频道的邮件数据。

其他邮箱类型，如用于Teams会议室的RoomMailbox，不支持Teams的保留策略。

Teams 使用 Azure 支持的聊天服务作为其所有消息 (聊天和频道消息) 的主要存储。 如果因合规性原因需要删除 Teams 消息，Teams 的保留策略可以根据消息的创建时间，在指定期限后删除消息。 然后，消息会从存储合规性操作的 Exchange 邮箱以及由基础 Azure 驱动的聊天服务所使用的主存储中永久删除。 有关基础体系结构的详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](/MicrosoftTeams/security-compliance-overview)，特别是[信息保护体系结构](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。

即使这些来自 Teams 聊天和频道消息的数据存储在邮箱中，但必须为 **Teams 频道消息** 和 **Teams 聊天** 位置配置保留策略。 Teams 聊天和频道消息不包括在为 Exchange 用户或组邮箱配置的保留策略中。 如果将用户添加到聊天中，则会将与其共享的所有邮件的副本引入到其邮箱中。 邮件的创建日期不会为新用户而更改，并对所有用户保持不变。

> [!NOTE]
> 如果用户包含在保留 Teams 消息的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。 如果不需要为用户保留此 Teams 数据，请在删除用户邮箱之前，将用户帐户从保留策略中排除，并 [等待此更改生效](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)。

为聊天和频道消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Teams 消息的隐藏文件夹中的项目。 计时器作业通常需要 1-7 天的时间来运行。 这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的另一个隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。 

消息在 SubstrateHolds 文件夹中至少保留 1 天，然后如果它们符合删除条件，定时器工作将在下次运行时永久地删除它们。

> [!IMPORTANT]
> 由于保留[第一原则](retention.md#the-principles-of-retention-or-what-takes-precedence)，并且由于 Teams 聊天和频道邮件存储在 Exchange Online 邮箱中，因此，如果邮箱受另一保留策略（包括应用于 Exchange 位置的策略）、诉讼保留、延迟保留，或者出于法律或诉讼原因对邮箱应用电子数据展示保留，则始终暂停从 SubstrateHolds 文件夹永久删除。
>
> 虽然邮箱包含在适用的保留中，但已删除的 Teams 聊天和频道邮件将不再在 Teams 应用中可见，但将继续通过电子数据展示进行发现。

为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。

如果保留策略为“保留后删除”：

![Teams 聊天和频道消息的保留流关系图。](../media/teamsretentionlifecycle.png)

对于图中的两条路径：

1. **如果用户在保留期内编辑或删除聊天或频道消息**，则会复制 (如果编辑) 或移除 (如果删除) 该原始消息到 SubstrateHolds 文件夹中。 该消息会在那里至少存储 1 天。 当保留期到期后，在下一次定时器作业运行时 (通常在 1-7 天内)，将永久删除该信息。

2. **如果用户未删除聊天或频道消息**，对于编辑后的当前消息，在保留期到期后，将会移懂该消息到 SubstrateHolds 文件夹。 此操作通常需要在到期日后的 1-7 天内完成。 当消息在 SubstrateHolds 文件夹中时，它在那里至少会保留 1 天，然后在下一次定时器作业运行时 (通常在 1-7 天之间)，将永久删除该消息。 

> [!NOTE]
> 利用电子数据展示工具可搜索存储在邮箱中的邮件（包括隐藏文件夹）。 在消息从 SubstrateHolds 文件夹中永久删除之前，仍然可以使用电子数据展示工具搜索到它们。

当消息从 SubstrateHolds 文件夹中永久删除时，删除操作会传达给后端 Azure 聊天服务，然后该服务将同样的操作转发给 Teams 客户端应用程序。 此通信或缓存的延迟可以解释为什么在短时间内，用户可能仍然在他们的团队应用程序中看到这些消息，但这些消息的数据在电子数据展示搜索中却没有返回。 在 Teams 应用程序中可见的消息并无法准确反映是该保留还是永久删除它们的合规要求。

如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。

### <a name="content-paths-for-retain-only-retention-policy"></a>“仅保留”保留策略的内容路径

1. **如果用户在保留期内编辑或删除了聊天或频道消息。** 会复制原始信息 (如果已编辑) 或移动 (如果已删除) 到 SubstrateHolds 文件夹，并在那里保留至少 1 天。 如果保留策略配置为永久保留，那么该项目则会一直保留在那里。 如果保留策略有一个保留期的结束日期，并且该日期已过，那么在下一次定时器工作运行时 (通常在 1-7 天之内)，将永久删除该邮件。

2. **如果聊天或频道消息未遭到用户修改或删除** 以及在保留期内进行编辑后的当前消息: 在保留期之前和之后都不会发生任何事情; 消息仍然在原来的位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>“仅删除”保留策略的内容路径

1. **如果用户在保留期内编辑或删除聊天或频道消息**: 则会复制 (如果编辑) 或移除 (如果删除) 该原始消息到 SubstrateHolds 文件夹中。 该消息在那里至少保留 1 天，并在下次定时器工作运行时 (通常在 1-7 天之内) 永久删除。

2. **如果用户在保持期内未删除聊天或频道消息**: 在保持期结束时，消息将移至 SubstrateHolds 文件夹。 此操作通常需要在到期日后的 1-7 天内完成。 该消息在那里至少保留 1 天，然后在下一次定时器作业运行时永久删除 (通常在 1-7 天之间)。

#### <a name="example-flows-and-timings-for-retention-policies"></a>保留策略的流和计时示例

使用下面的示例，查看前面部分中解释的过程和时间是如何应用于具有以下配置的保留策略的:

- [示例 1: 仅保留 7 年](#example-1-retain-only-for-7-years)
- [示例 2: 保留 30 天，然后删除](#example-2-retain-for-30-days-and-then-delete)
- [示例 3: 1 天后仅删除](#example-3-delete-only-after-1-day)

对于所有提到永久删除的示例，由于[保留原则](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果该消息受到另一个保留策略的约束以保留该项目，或者它受到电子数据展示的保留，就会暂停该操作。

##### <a name="example-1-retain-only-for-7-years"></a>示例 1: 仅保留 7 年

第 1 天，用户创建聊天或频道消息。

第 5 天，用户编辑此消息。

第 30 天，用户删除当前消息。

保留结果:

- 对于原始消息:
    - 第 5 天，复制消息到 SubstrateHolds 文件夹，从第 1 天起至少 7 年内 (保留期) 仍可使用电子数据展示工具进行搜索。

- 对于当前 (已编辑) 消息:
    - 第 30 天，移动消息到 SubstrateHolds 文件夹，在那里它仍然可以用电子数据展示工具进行搜索，从第 1 天起至少 7 年 (保留期)。

如果用户在指定保留期之后，而不是在保留期内删除了当前消息，那么该消息仍然会移到 SubstrateHolds 文件夹中。 然而，现在保留期已过，信息将在至少 1 天后永久删除，然后通常在 1-7 天内删除。

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>示例 2: 保留 30 天，然后删除

第 1 天，用户创建聊天或频道消息。

第 10 天，用户编辑此消息。

用户不会进行进一步的编辑，且不会删除消息。

保留结果:

- 对于原始消息:
    - 第 10 天，复制消息到 SubstrateHolds 文件夹，在那里仍然可以用电子数据展示工具进行搜索。
    - 在保留期结束时 (从第 1 天开始的 30 天)，该消息通常在至少 1 天后的 1-7 天内永久删除，然后电子数据展示不会再搜索到它们。

- 对于当前 (已编辑) 消息:
    - 在保留期结束时 (从第 1 天起 30 天)，消息通常在 1-7 天内转移到 SubstrateHolds 文件夹，在那里仍然可以用电子数据展示工具进行搜索。
    - 然后，通常在 1-7 天内永久删除该消息，至少 1 天后，电子数据展示就无法搜索到它们。

##### <a name="example-3-delete-only-after-1-day"></a>示例 3: 1 天之后仅删除

> [!NOTE]
> 由于此配置的持续时间很短，并且保留过程在 1-7 天的时间段内运作，因此本节显示了在典型时间范围内的示例时间。

第 1 天，用户创建聊天或频道消息。

如果用户不编辑或删除信息，则保留结果的示例:

- 第 5 天(通常在第 2 天保留期开始后的 1-7 天):
    - 消息会移动到 SubstrateHolds 文件夹中，并在那里停留至少 1 天且仍可使用电子数据展示工具进行搜索。

- 第 9 天 (通常是在 SubstrateHolds 文件夹中至少 1 天后的 1-7 天):
    - 永久删除该消息，然后电子数据展示就无法搜索到它们。

正如该例子所示，尽管可以配置保留策略以在一天后删除消息，但该服务要经过多个过程以确保合规的删除。 因此，1 天后的删除操作可能需要 16 天才能将消息永久删除，以便在电子数据展示搜索中不再返回。

## <a name="skype-for-business-and-teams-interop-chats"></a>Skype for Business 和 Teams 互操作聊天

当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。 Teams 保留策略将从 Teams 线程应用于这些消息。 

但是，如果打开 Skype for Business 的对话历史，并且从 Skype for Business 客户端来看，该历史已保存到邮箱中，那么该聊天数据就不会遭到 Teams 保留策略的处理。对于这些内容，请使用为 Skype for Business 配置的保留策略。

## <a name="meetings-and-external-users"></a>会议和外部用户

频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息** 位置。

即兴和预定会议消息的存储方式与群组聊天消息相同，因此对于这些数据，请在配置保留策略时选择 **Teams 聊天** 位置。

当外部用户加入你的组织主持的会议时：

- 如果外部用户使用租户中的来宾帐户加入，则来自会议的任何邮件都存储在用户邮箱和授予来宾帐户的影子邮箱中。 但是，影子邮箱不支持保留策略，即使可以将它们报告为包含在整个位置的保留策略中（有时称为“组织范围的策略”）。

- 如果外部用户使用另一个 Microsoft 365 组织的账户加入，你的保留策略则不能删除该用户的邮件，因为它们存储在另一个租户的用户邮箱中。然而，对于同样的会议，你的保留策略却可以删除你的用户的邮件。

## <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

如果在 Exchange Online 中有邮箱的用户离开了你的组织，并且他们的 Microsoft 365 帐户被删除，则他们要保留的聊天邮件将存储在非活动邮箱中。 聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。 有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。 

如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="configuration-guidance"></a>配置指南

如果你不熟悉如何在Microsoft 365中配置保留期，请参阅[开始使用信息治理](get-started-with-information-governance.md)。

如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。