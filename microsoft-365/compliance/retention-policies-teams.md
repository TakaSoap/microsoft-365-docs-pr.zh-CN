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
ms.openlocfilehash: 5d888232d94ccd6634fc6102c26958e20d88fb4d
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322397"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="f3ccf-103">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="f3ccf-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="f3ccf-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="f3ccf-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="f3ccf-105">如果在 Teams 中显示一条消息，显示聊天或邮件已被保留策略删除，请参阅 [Teams 中有关保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-105">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="f3ccf-106">本页上的信息适用于管理这些保留策略的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-106">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="f3ccf-107">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Microsoft Teams 消息的信息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-107">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams messages.</span></span>

<span data-ttu-id="f3ccf-108">有关其他工作负载，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f3ccf-108">For other workloads, see:</span></span>

- [<span data-ttu-id="f3ccf-109">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="f3ccf-109">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="f3ccf-110">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="f3ccf-110">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="f3ccf-111">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="f3ccf-111">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="f3ccf-112">保留和删除包括哪些内容</span><span class="sxs-lookup"><span data-stu-id="f3ccf-112">What's included for retention and deletion</span></span>

<span data-ttu-id="f3ccf-113">可以通过使用 Teams 的保留策略删除 Teams 聊天消息和频道消息，除了消息中的文本外，以下项目可以因合规性原因而保留。嵌入的图像、表格、超文本链接、到其他 Teams 消息和文件的链接，以及 [卡内容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-113">Teams chats messages and channel messages can be deleted by using retention policies for Teams, and in addition to the text in the messages, the following items can be retained for compliance reasons: Embedded images, tables, hypertext links, links to other Teams messages and files, and [card content](/microsoftteams/platform/task-modules-and-cards/what-are-cards).</span></span> <span data-ttu-id="f3ccf-114">聊天消息包括聊天中所有人员的姓名；频道消息包含团队名称和消息标题（如有提供）。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-114">Chat messages include all the names of the people in the chat, and channel messages include the team name and the message title (if supplied).</span></span> 
> [!NOTE]
> <span data-ttu-id="f3ccf-115">当前以预览版形式推出对专用频道中消息的支持。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-115">Support for messages in private channels is currently rolling out in preview.</span></span>

<span data-ttu-id="f3ccf-116">当你对 Teams 使用保留策略时，来自 Teams 移动客户端的代码片段、来自 Teams 移动客户端的语音备忘录、缩略图、公告图像以及其他人的图释反应不会保留。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-116">Code snippets, recorded voice memos from the Teams mobile client, thumbnails, announcement images, and reactions from others in the form of emoticons are not retained when you use retention policies for Teams.</span></span>

<span data-ttu-id="f3ccf-p102">在 Teams 中所使用的电子邮件和文件不包括在 Teams 的保留政策中。这些项目有它们自己的保留政策。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-p102">Emails and files that you use with Teams aren't included in retention policies for Teams. These items have their own retention policies.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="f3ccf-119">用于 Microsoft Teams 的保留工作原理</span><span class="sxs-lookup"><span data-stu-id="f3ccf-119">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="f3ccf-120">使用本节了解合规性要求是如何通过后端存储和流程满足的，应该由电子数据展示工具来验证，而非由目前在 Teams 应用程序中显示的消息来验证。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-120">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Teams app.</span></span>

<span data-ttu-id="f3ccf-121">可以使用保留策略来保留 Teams 中的聊天记录和频道消息的数据，并删除这些聊天记录和消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-121">You can use a retention policy to retain data from chats and channel messages in Teams, and delete these chats and messages.</span></span> <span data-ttu-id="f3ccf-122">Exchange 邮箱在后台用于存储这些消息中复制的数据。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-122">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="f3ccf-123">Teams 聊天中的数据存储在聊天中包含的每个用户的邮箱中的隐藏文件夹中，组邮箱中的类似隐藏文件夹用于 Teams 频道消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-123">Data from Teams chats is stored in a hidden folder in the mailbox of each user included in the chat, and a similar hidden folder in a group mailbox is used for Teams channel messages.</span></span> <span data-ttu-id="f3ccf-124">这些隐藏的文件夹不是为了供用户或管理员直接访问，而是存储合规性管理员可以使用电子数据展示工具搜索的数据。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-124">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

<span data-ttu-id="f3ccf-125">通过 RecipientTypeDetails 属性列出这些邮箱:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-125">These mailboxes are, listed by their RecipientTypeDetails attribute:</span></span>

- <span data-ttu-id="f3ccf-126">**UserMailbox**: 这些邮箱存储基于云的 Teams 用户的消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-126">**UserMailbox**: These mailboxes store message data for cloud-based Teams users.</span></span>
- <span data-ttu-id="f3ccf-127">**MailUser**: 这些邮箱存储 [本地 Teams 用户](search-cloud-based-mailboxes-for-on-premises-users.md) 的消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-127">**MailUser**: These mailboxes store message data for [on-premises Teams users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
- <span data-ttu-id="f3ccf-128">**GroupMailbox**：这些邮箱存储 Teams 标准频道的邮件数据。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-128">**GroupMailbox**: These mailboxes store message data for Teams standard channels.</span></span>

<span data-ttu-id="f3ccf-129">其他邮箱类型，如用于Teams会议室的RoomMailbox，不支持Teams的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-129">Other mailbox types, such as RoomMailbox that is used for Teams conference rooms, are not supported for Teams retention policies.</span></span>

<span data-ttu-id="f3ccf-130">Teams 使用 Azure 支持的聊天服务作为其所有消息 (聊天和频道消息) 的主要存储。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-130">Teams uses an Azure-powered chat service as its primary storage for all messages (chats and channel messages).</span></span> <span data-ttu-id="f3ccf-131">如果因合规性原因需要删除 Teams 消息，Teams 的保留策略可以根据消息的创建时间，在指定期限后删除消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-131">If you need to delete Teams messages for compliance reasons, retention policies for Teams can delete messages after a specified period, based on when they were created.</span></span> <span data-ttu-id="f3ccf-132">然后，消息会从存储合规性操作的 Exchange 邮箱以及由基础 Azure 驱动的聊天服务所使用的主存储中永久删除。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-132">Messages are then permanently deleted from both the Exchange mailboxes where they stored for compliance operations, and from the primary storage used by the underlying Azure-powered chat service.</span></span> <span data-ttu-id="f3ccf-133">有关基础体系结构的详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](/MicrosoftTeams/security-compliance-overview)，特别是[信息保护体系结构](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-133">For more information about the underlying architecture, see [Security and compliance in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) and specifically, the [Information Protection Architecture](/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="f3ccf-134">即使这些来自 Teams 聊天和频道消息的数据存储在邮箱中，但必须为 **Teams 频道消息** 和 **Teams 聊天** 位置配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-134">Although this data from Teams chats and channel messages are stored in mailboxes, you must configure a retention policy for the **Teams channel messages** and **Teams chats** locations.</span></span> <span data-ttu-id="f3ccf-135">Teams 聊天和频道消息不包括在为 Exchange 用户或组邮箱配置的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-135">Teams chats and channel messages are not included in retention policies that are configured for Exchange user or group mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="f3ccf-136">如果用户包含在保留 Teams 消息的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-136">If a user is included in an active retention policy that retains Teams messages and you delete a mailbox of a user who is included in this policy, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md) to retain the Teams data.</span></span> <span data-ttu-id="f3ccf-137">如果不需要为用户保留此 Teams 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-137">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="f3ccf-138">为聊天和频道消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Teams 消息的隐藏文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-138">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="f3ccf-139">计时器作业通常需要 1-7 天的时间来运行。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-139">The timer job typically takes 1-7 days to run.</span></span> <span data-ttu-id="f3ccf-140">这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的另一个隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-140">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span> 

<span data-ttu-id="f3ccf-141">消息在 SubstrateHolds 文件夹中至少保留 1 天，然后如果它们符合删除条件，定时器工作将在下次运行时永久地删除它们。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-141">Messages remain in the SubstrateHolds folder for at least 1 day, and then if they are eligible for deletion, the timer job permanently deletes them the next time it runs.</span></span>

> [!NOTE]
> <span data-ttu-id="f3ccf-142">由于[第一个保留策略](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果由于另一个保留策略而必须保留同一项目，或者由于法律或调查原因而处于电子数据展示保留状态，则永久删除始终处于暂停状态。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-142">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="f3ccf-143">为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-143">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="f3ccf-144">如果保留策略为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="f3ccf-144">When the retention policy is to retain and then delete:</span></span>

![Teams 聊天和频道消息的保留流关系图](../media/teamsretentionlifecycle.png)

<span data-ttu-id="f3ccf-146">对于图中的两条路径：</span><span class="sxs-lookup"><span data-stu-id="f3ccf-146">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="f3ccf-147">**如果用户在保留期内编辑或删除聊天或频道消息**，则会复制 (如果编辑) 或移除 (如果删除) 该原始消息到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-147">**If a chat or channel message is edited or deleted** by a user during the retention period, the original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="f3ccf-148">该消息会在那里至少存储 1 天。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-148">The message is stored there for at least 1 day.</span></span> <span data-ttu-id="f3ccf-149">当保留期到期后，在下一次定时器作业运行时 (通常在 1-7 天内)，将永久删除该信息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-149">When the retention period expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="f3ccf-150">**如果用户未删除聊天或频道消息**，对于编辑后的当前消息，在保留期到期后，将会移懂该消息到 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-150">**If a chat or channel message is not deleted** by a user and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="f3ccf-151">此操作通常需要在到期日后的 1-7 天内完成。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-151">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="f3ccf-152">当消息在 SubstrateHolds 文件夹中时，它在那里至少会保留 1 天，然后在下一次定时器作业运行时 (通常在 1-7 天之间)，将永久删除该消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-152">When the message is in the SubstrateHolds folder, it is stored there for at least 1 day, and then the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span> 

> [!NOTE]
> <span data-ttu-id="f3ccf-153">利用电子数据展示工具可搜索存储在邮箱中的邮件（包括隐藏文件夹）。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-153">Messages stored in mailboxes, including the hidden folders, are searchable by eDiscovery tools.</span></span> <span data-ttu-id="f3ccf-154">在消息从 SubstrateHolds 文件夹中永久删除之前，仍然可以使用电子数据展示工具搜索到它们。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-154">Until messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="f3ccf-155">当消息从 SubstrateHolds 文件夹中永久删除时，删除操作会传达给后端 Azure 聊天服务，然后该服务将同样的操作转发给 Teams 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-155">When messages are permanently deleted from the SubstrateHolds folder, a delete operation is communicated to the backend Azure chat service, that then relays the same operation to the Teams client app.</span></span> <span data-ttu-id="f3ccf-156">此通信或缓存的延迟可以解释为什么在短时间内，用户可能仍然在他们的团队应用程序中看到这些消息，但这些消息的数据在电子数据展示搜索中却没有返回。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-156">Delays in this communication or caching can explain why, for a short period of time, users might still see these messages in their Teams app, but data from these messages isn't returned in eDiscovery searches.</span></span> <span data-ttu-id="f3ccf-157">在 Teams 应用程序中可见的消息并无法准确反映是该保留还是永久删除它们的合规要求。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-157">Messages visible in the Teams app are not an accurate reflection of whether they are retained or permanently deleted for compliance requirements.</span></span>

<span data-ttu-id="f3ccf-158">如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-158">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="f3ccf-159">“仅保留”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="f3ccf-159">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="f3ccf-160">**如果用户在保留期内编辑或删除了聊天或频道消息。** 会复制原始信息 (如果已编辑) 或移动 (如果已删除) 到 SubstrateHolds 文件夹，并在那里保留至少 1 天。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-160">**If a chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder, and retained there for at least 1 day.</span></span> <span data-ttu-id="f3ccf-161">如果保留策略配置为永久保留，那么该项目则会一直保留在那里。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-161">If the retention policy is configured to retain forever, the item remains there.</span></span> <span data-ttu-id="f3ccf-162">如果保留策略有一个保留期的结束日期，并且该日期已过，那么在下一次定时器工作运行时 (通常在 1-7 天之内)，将永久删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-162">If the retention policy has an end date for the retention period and it expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="f3ccf-163">**如果聊天或频道消息未遭到用户修改或删除** 以及在保留期内进行编辑后的当前消息: 在保留期之前和之后都不会发生任何事情; 消息仍然在原来的位置。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-163">**If the chat or channel message is not modified or deleted** by a user and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="f3ccf-164">“仅删除”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="f3ccf-164">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="f3ccf-165">**如果用户在保留期内编辑或删除聊天或频道消息**: 则会复制 (如果编辑) 或移除 (如果删除) 该原始消息到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-165">**If the chat or channel message is edited or deleted** by a user during the retention period: The original message is copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="f3ccf-166">该消息在那里至少保留 1 天，并在下次定时器工作运行时 (通常在 1-7 天之内) 永久删除。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-166">The message is retained there for at least 1 day and permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

2. <span data-ttu-id="f3ccf-167">**如果用户在保持期内未删除聊天或频道消息**: 在保持期结束时，消息将移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-167">**If a chat or channel message is not deleted** by a user during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="f3ccf-168">此操作通常需要在到期日后的 1-7 天内完成。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-168">This action typically takes between 1-7 days from the expiry date.</span></span> <span data-ttu-id="f3ccf-169">该消息在那里至少保留 1 天，然后在下一次定时器作业运行时永久删除 (通常在 1-7 天之间)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-169">The message is retained there for at least 1 day and then permanently deleted the next time the timer job runs (typically between 1-7 days).</span></span>

#### <a name="example-flows-and-timings-for-retention-policies"></a><span data-ttu-id="f3ccf-170">保留策略的流和计时示例</span><span class="sxs-lookup"><span data-stu-id="f3ccf-170">Example flows and timings for retention policies</span></span>

<span data-ttu-id="f3ccf-171">使用下面的示例，查看前面部分中解释的过程和时间是如何应用于具有以下配置的保留策略的:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-171">Use the following examples to see how the processes and timings explained in the previous sections apply to retention policies that have the following configurations:</span></span>

- [<span data-ttu-id="f3ccf-172">示例 1: 仅保留 7 年</span><span class="sxs-lookup"><span data-stu-id="f3ccf-172">Example 1: Retain-only for 7 years</span></span>](#example-1-retain-only-for-7-years)
- [<span data-ttu-id="f3ccf-173">示例 2: 保留 30 天，然后删除</span><span class="sxs-lookup"><span data-stu-id="f3ccf-173">Example 2: Retain for 30 days and then delete</span></span>](#example-2-retain-for-30-days-and-then-delete)
- [<span data-ttu-id="f3ccf-174">示例 3: 1 天后仅删除</span><span class="sxs-lookup"><span data-stu-id="f3ccf-174">Example 3: Delete-only after 1 day</span></span>](#example-3-delete-only-after-1-day)

<span data-ttu-id="f3ccf-175">对于所有提到永久删除的示例，由于[保留原则](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果该消息受到另一个保留策略的约束以保留该项目，或者它受到电子数据展示的保留，就会暂停该操作。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-175">For all examples that refer to permanent deletion, because of the [principles of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), this action is suspended if the message is subject to another retention policy to retain the item or it is subject to an eDiscovery hold.</span></span>

##### <a name="example-1-retain-only-for-7-years"></a><span data-ttu-id="f3ccf-176">示例 1: 仅保留 7 年</span><span class="sxs-lookup"><span data-stu-id="f3ccf-176">Example 1: Retain-only for 7 years</span></span>

<span data-ttu-id="f3ccf-177">第 1 天，用户创建聊天或频道消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-177">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="f3ccf-178">第 5 天，用户编辑此消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-178">On day 5, the user edits that message.</span></span>

<span data-ttu-id="f3ccf-179">第 30 天，用户删除当前消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-179">On day 30, the user deletes the current message.</span></span>

<span data-ttu-id="f3ccf-180">保留结果:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-180">Retention outcomes:</span></span>

- <span data-ttu-id="f3ccf-181">对于原始消息:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-181">For the original message:</span></span>
    - <span data-ttu-id="f3ccf-182">第 5 天，复制消息到 SubstrateHolds 文件夹，从第 1 天起至少 7 年内 (保留期) 仍可使用电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-182">On day 5, the message is copied to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

- <span data-ttu-id="f3ccf-183">对于当前 (已编辑) 消息:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-183">For the current (edited) message:</span></span>
    - <span data-ttu-id="f3ccf-184">第 30 天，移动消息到 SubstrateHolds 文件夹，在那里它仍然可以用电子数据展示工具进行搜索，从第 1 天起至少 7 年 (保留期)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-184">On day 30, the message moves to the SubstrateHolds folder where it can still be searched with eDiscovery tools for a minimum of 7 years from day 1 (the retention period).</span></span>

<span data-ttu-id="f3ccf-185">如果用户在指定保留期之后，而不是在保留期内删除了当前消息，那么该消息仍然会移到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-185">If the user had deleted the current message after the specified retention period, instead of within the retention period, the message would still be moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="f3ccf-186">然而，现在保留期已过，信息将在至少 1 天后永久删除，然后通常在 1-7 天内删除。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-186">However, now the retention period has expired, the message would be permanently deleted after the minimum of 1 day and then typically within 1-7 days.</span></span>

##### <a name="example-2-retain-for-30-days-and-then-delete"></a><span data-ttu-id="f3ccf-187">示例 2: 保留 30 天，然后删除</span><span class="sxs-lookup"><span data-stu-id="f3ccf-187">Example 2: Retain for 30 days and then delete</span></span>

<span data-ttu-id="f3ccf-188">第 1 天，用户创建聊天或频道消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-188">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="f3ccf-189">第 10 天，用户编辑此消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-189">On day 10, the user edits that message.</span></span>

<span data-ttu-id="f3ccf-190">用户不会进行进一步的编辑，且不会删除消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-190">The user doesn't make further edits and doesn't delete the message.</span></span>

<span data-ttu-id="f3ccf-191">保留结果:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-191">Retention outcomes:</span></span>

- <span data-ttu-id="f3ccf-192">对于原始消息:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-192">For the original message:</span></span>
    - <span data-ttu-id="f3ccf-193">第 10 天，复制消息到 SubstrateHolds 文件夹，在那里仍然可以用电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-193">On day 10, the message is copied to the SubstrateHolds folder, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="f3ccf-194">在保留期结束时 (从第 1 天开始的 30 天)，该消息通常在至少 1 天后的 1-7 天内永久删除，然后电子数据展示不会再搜索到它们。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-194">At the end of the retention period (30 days from day 1), the message is permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

- <span data-ttu-id="f3ccf-195">对于当前 (已编辑) 消息:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-195">For the current (edited) message:</span></span>
    - <span data-ttu-id="f3ccf-196">在保留期结束时 (从第 1 天起 30 天)，消息通常在 1-7 天内转移到 SubstrateHolds 文件夹，在那里仍然可以用电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-196">At the end of the retention period (30 days from day 1), the message moves to the SubstrateHolds folder typically within 1-7 days, where it can still be searched with eDiscovery tools.</span></span>
    - <span data-ttu-id="f3ccf-197">然后，通常在 1-7 天内永久删除该消息，至少 1 天后，电子数据展示就无法搜索到它们。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-197">The message is then permanently deleted typically within 1-7 days after the minimum of 1 day, and then won't be returned with eDiscovery searches.</span></span>

##### <a name="example-3-delete-only-after-1-day"></a><span data-ttu-id="f3ccf-198">示例 3: 1 天之后仅删除</span><span class="sxs-lookup"><span data-stu-id="f3ccf-198">Example 3: Delete-only after 1 day</span></span>

> [!NOTE]
> <span data-ttu-id="f3ccf-199">由于此配置的持续时间很短，并且保留过程在 1-7 天的时间段内运作，因此本节显示了在典型时间范围内的示例时间。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-199">Because of the short one-day duration of this configuration and retention processes that operate within a time period of 1-7 days, this section shows example timings that are within the typical time ranges.</span></span>

<span data-ttu-id="f3ccf-200">第 1 天，用户创建聊天或频道消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-200">On day 1, a user creates a chat or channel message.</span></span>

<span data-ttu-id="f3ccf-201">如果用户不编辑或删除信息，则保留结果的示例:</span><span class="sxs-lookup"><span data-stu-id="f3ccf-201">Example retention outcome if the user doesn't edit or delete the message:</span></span>

- <span data-ttu-id="f3ccf-202">第 5 天(通常在第 2 天保留期开始后的 1-7 天):</span><span class="sxs-lookup"><span data-stu-id="f3ccf-202">Day 5 (typically 1-7 days after the start of the retention period on day 2):</span></span>
    - <span data-ttu-id="f3ccf-203">消息会移动到 SubstrateHolds 文件夹中，并在那里停留至少 1 天且仍可使用电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-203">The message moves to the SubstrateHolds folder and remains there for at least 1 day where it can still be searched with eDiscovery tools.</span></span>

- <span data-ttu-id="f3ccf-204">第 9 天 (通常是在 SubstrateHolds 文件夹中至少 1 天后的 1-7 天):</span><span class="sxs-lookup"><span data-stu-id="f3ccf-204">Day 9 (typically 1-7 days after a minimum of 1 day in the SubstrateHolds folder):</span></span>
    - <span data-ttu-id="f3ccf-205">永久删除该消息，然后电子数据展示就无法搜索到它们。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-205">The message is permanently deleted and then won't be returned with eDiscovery searches.</span></span>

<span data-ttu-id="f3ccf-206">正如该例子所示，尽管可以配置保留策略以在一天后删除消息，但该服务要经过多个过程以确保合规的删除。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-206">As this example shows, although you can configure a retention policy to delete messages after just one day, the service undergoes multiple processes to ensure a compliant deletion.</span></span> <span data-ttu-id="f3ccf-207">因此，1 天后的删除操作可能需要 16 天才能将消息永久删除，以便在电子数据展示搜索中不再返回。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-207">As a result, a delete action after 1 day could take 16 days before the message is permanently deleted so that it's no longer returned in eDiscovery searches.</span></span>

## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="f3ccf-208">Skype for Business 和 Teams 互操作聊天</span><span class="sxs-lookup"><span data-stu-id="f3ccf-208">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="f3ccf-209">当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-209">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="f3ccf-210">Teams 保留策略将从 Teams 线程应用于这些消息。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-210">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="f3ccf-p118">但是，如果打开 Skype for Business 的对话历史，并且从 Skype for Business 客户端来看，该历史已保存到邮箱中，那么该聊天数据就不会遭到 Teams 保留策略的处理。对于这些内容，请使用为 Skype for Business 配置的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-p118">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy. For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="f3ccf-213">会议和外部用户</span><span class="sxs-lookup"><span data-stu-id="f3ccf-213">Meetings and external users</span></span>

<span data-ttu-id="f3ccf-214">频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息** 位置。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-214">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="f3ccf-215">即兴和预定会议消息的存储方式与群组聊天消息相同，因此对于这些数据，请在配置保留策略时选择 **Teams 聊天** 位置。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-215">Impromptu and scheduled meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="f3ccf-216">当外部用户加入你的组织主持的会议时：</span><span class="sxs-lookup"><span data-stu-id="f3ccf-216">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="f3ccf-217">如果外部用户使用租户中的来宾帐户加入，此用户将有一个影子邮箱，可遵循组织的 Teams 保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-217">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="f3ccf-218">会议中的任何邮件都存储在用户的邮箱和影子邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-218">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="f3ccf-p120">如果外部用户使用另一个 Microsoft 365 组织的账户加入，你的保留策略则不能删除该用户的邮件，因为它们存储在另一个租户的用户邮箱中。然而，对于同样的会议，你的保留策略却可以删除你的用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-p120">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant. For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="f3ccf-221">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="f3ccf-221">When a user leaves the organization</span></span> 

<span data-ttu-id="f3ccf-222">如果在 Exchange Online 中有邮箱的用户离开了你的组织，并且他们的 Microsoft 365 帐户被删除，则他们要保留的聊天邮件将存储在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-222">If a user who has a mailbox in Exchange Online leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="f3ccf-223">聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-223">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="f3ccf-224">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-224">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="f3ccf-225">如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-225">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="f3ccf-226">配置指南</span><span class="sxs-lookup"><span data-stu-id="f3ccf-226">Configuration guidance</span></span>

<span data-ttu-id="f3ccf-227">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-227">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="f3ccf-228">如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ccf-228">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>