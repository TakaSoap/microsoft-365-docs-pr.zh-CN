---
title: 了解 Teams 的保留策略
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
ms.openlocfilehash: 8e163aa9f5072e0b2685521fcae37f130d132473
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083490"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a><span data-ttu-id="906c5-103">了解 Microsoft Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="906c5-103">Learn about retention policies for Microsoft Teams</span></span>

><span data-ttu-id="906c5-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="906c5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="906c5-105">本文中的信息是对[了解保留策略](retention-policies.md)的补充，因为它包含特定于 Microsoft Teams 的信息。</span><span class="sxs-lookup"><span data-stu-id="906c5-105">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Microsoft Teams.</span></span>

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a><span data-ttu-id="906c5-106">保留策略如何处理 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="906c5-106">How a retention policy works with Microsoft Teams</span></span>

<span data-ttu-id="906c5-107">可使用保留策略保留 Teams 中的聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-107">You can use a retention policy to retain chats and channel messages in Teams.</span></span> <span data-ttu-id="906c5-108">Teams 聊天存储在参与聊天的每个用户的邮箱中的隐藏文件夹内，Teams 频道消息存储在团队组邮箱中类似的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="906c5-108">Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> 

<span data-ttu-id="906c5-109">务必了解，Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。</span><span class="sxs-lookup"><span data-stu-id="906c5-109">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="906c5-110">因此，我们强烈建议使用 Teams 位置来保留和删除此 Teams 数据。</span><span class="sxs-lookup"><span data-stu-id="906c5-110">For this reason, we strongly recommend that you use the Teams locations to retain and delete this Teams data.</span></span> <span data-ttu-id="906c5-111">使用 Teams 位置将从 Exchange 邮箱和基于 Azure 支持的聊天服务中永久删除数据。</span><span class="sxs-lookup"><span data-stu-id="906c5-111">Using the Teams locations will permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="906c5-112">有关详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](https://go.microsoft.com/fwlink/?linkid=871258)，特别是[信息保护体系结构](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。</span><span class="sxs-lookup"><span data-stu-id="906c5-112">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="906c5-113">Teams 聊天和频道消息不受针对用户或组邮箱配置的保留策略影响。</span><span class="sxs-lookup"><span data-stu-id="906c5-113">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="906c5-114">即使 Teams 聊天和频道消息存储在 Exchange 中，此 Teams 数据仍将仅包含在针对 **Teams 频道消息**和 \*\* Teams 聊天\*\*位置配置的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="906c5-114">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="906c5-115">如果用户包含在保留 Teams 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="906c5-115">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="906c5-116">如果不需要为用户保留此 Teams 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="906c5-116">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="906c5-117">为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="906c5-117">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="906c5-118">如果保留策略为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="906c5-118">When the retention policy is to retain and delete:</span></span>

![Teams 聊天和频道消息的保留流关系图](../media/TeamsRetentionLifecycle.png)

1. <span data-ttu-id="906c5-120">**如果在保留期内用户修改或删除了聊天或频道消息**，则该消息将移动（或在编辑的情况下复制）到 SubstrateHolds 文件夹（它是每个用户或组邮箱中的隐藏文件夹），并保留在该文件夹中，直到保留期到期。</span><span class="sxs-lookup"><span data-stu-id="906c5-120">**If a chat or channel message is modified or deleted** by the user during the retention period, the message is moved (or copied, in the case of edit) to the SubstrateHolds folder (which is a hidden folder in every user or group mailbox) and is stored in this folder until the retention period expires.</span></span> <span data-ttu-id="906c5-121">在保留期到期之日，该消息将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="906c5-121">Messages are permanently deleted on the day the retention period expires.</span></span>

2. <span data-ttu-id="906c5-122">**如果在保留期内未删除聊天或频道消息**，则该消息将在保留期到期后的一天内（ 0 到 24 小时）移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="906c5-122">**If a chat or channel message isn't deleted** during the retention period, the message is moved to the SubstrateHolds folder within one day after the retention period expires (it takes from 0 to 24 hours).</span></span> <span data-ttu-id="906c5-123">将消息移至 SubstrateHolds 文件夹一天后，该消息将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="906c5-123">The message is permanently deleted one day after it is moved to the SubstrateHolds folder.</span></span> 

> [!NOTE]
> <span data-ttu-id="906c5-124">可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-124">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="906c5-125">永久删除消息后，它不会在电子数据展示搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="906c5-125">After a message is permanently deleted, it won't be returned in an eDiscovery search.</span></span>

<span data-ttu-id="906c5-126">如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。</span><span class="sxs-lookup"><span data-stu-id="906c5-126">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="906c5-127">“仅保留”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="906c5-127">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="906c5-128">**如果有人在保留期内修改或删除聊天或频道消息**：会在 SubstrateHolds 文件夹中创建原始消息的副本，并保留到保留期结束，然后 SubstrateHolds 文件夹中的副本会在该项到期后永久删除。</span><span class="sxs-lookup"><span data-stu-id="906c5-128">**If a chat or channel message is modified or deleted** during the retention period: A copy of the original message is created in the SubstrateHolds folder and retained until the end of the retention period, when the copy in the SubstrateHolds folder is permanently deleted one day after the item expires.</span></span> 

2. <span data-ttu-id="906c5-129">**如果项目在保持期内未遭修改或删除**：保留期前后无变化；消息仍保留在原始位置。</span><span class="sxs-lookup"><span data-stu-id="906c5-129">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="906c5-130">“仅删除”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="906c5-130">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="906c5-131">**如果消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="906c5-131">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> 

2. <span data-ttu-id="906c5-132">**如果用户在保留期内删除项目**，该项目将立即移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="906c5-132">**If the item is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="906c5-133">如果用户从 SubstrateHolds 文件夹中删除消息或清空此文件夹，该项目将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="906c5-133">If a user deletes the message from there or empties the SubstrateHolds folder, the item is permanently deleted.</span></span> <span data-ttu-id="906c5-134">否则，该消息将在移至 SubstrateHolds 文件夹一天后被永久删除。</span><span class="sxs-lookup"><span data-stu-id="906c5-134">Otherwise, the message is permanently deleted one day after being in the SubstrateHolds folder.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="906c5-135">Skype for Business 和 Teams 互操作聊天</span><span class="sxs-lookup"><span data-stu-id="906c5-135">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="906c5-136">Skype for Business 和 Teams 互操作聊天适用相同的流程。</span><span class="sxs-lookup"><span data-stu-id="906c5-136">The same flow works for Skype for Business and Teams interop chats.</span></span> <span data-ttu-id="906c5-137">当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="906c5-137">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="906c5-138">Teams 保留策略将从 Teams 线程应用于这些消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-138">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="906c5-139">但是，如果已为 Skype for Business 开启对话历史记录，并且从 Skype for Business 客户端将其保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。</span><span class="sxs-lookup"><span data-stu-id="906c5-139">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="906c5-140">对于此内容，请使用为 Skype for Business 配置的保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-140">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="additional-retention-policies-needed-to-support-teams"></a><span data-ttu-id="906c5-141">支持团队所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="906c5-141">Additional retention policies needed to support Teams</span></span>

<span data-ttu-id="906c5-142">Teams 不只是聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-142">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="906c5-143">如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应另外使用 **Office 365 组**位置来配置包括该 Microsoft 365 组的保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-143">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="906c5-144">此保留策略适用于组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="906c5-144">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="906c5-145">如果团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站**或 **OneDrive 帐户**位置的保留策略来保留和删除 Teams 中的文件：</span><span class="sxs-lookup"><span data-stu-id="906c5-145">If the team site isn't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="906c5-146">聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="906c5-146">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="906c5-147">上传到频道的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="906c5-147">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="906c5-148">当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="906c5-148">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="906c5-149">应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-149">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="906c5-150">在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="906c5-150">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="906c5-151">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="906c5-151">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

> [!NOTE]
> <span data-ttu-id="906c5-152">包含 Teams 频道消息或 Teams 聊天的保留策略只能包含 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="906c5-152">A retention policy that includes Teams channel messages or Teams chats can only include Teams locations.</span></span> <span data-ttu-id="906c5-153">因此，若要保留或删除 Teams 支持的其他内容，则必须创建单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-153">So to retain or delete other content that's supported by Teams, you must create a separate retention policy.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="906c5-154">会议和外部用户</span><span class="sxs-lookup"><span data-stu-id="906c5-154">Meetings and external users</span></span>

<span data-ttu-id="906c5-155">频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息**位置。</span><span class="sxs-lookup"><span data-stu-id="906c5-155">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="906c5-156">临时会议邮件的存储方式与群组聊天消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 聊天**位置。</span><span class="sxs-lookup"><span data-stu-id="906c5-156">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="906c5-157">当外部用户加入你的组织主持的会议时：</span><span class="sxs-lookup"><span data-stu-id="906c5-157">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="906c5-158">如果外部用户使用租户中的来宾帐户加入，此用户将有一个影子邮箱，可遵循组织的 Teams 保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-158">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="906c5-159">会议中的任何邮件都存储在用户的邮箱和影子邮箱中。</span><span class="sxs-lookup"><span data-stu-id="906c5-159">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="906c5-160">如果外部用户使用来自其他 Microsoft 365 组织的帐户加入，则你的保留策略无法删除此用户的邮件，因为它们存储在该用户在其他租户中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="906c5-160">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="906c5-161">但是对于同一会议，你的保留策略可以为你的用户删除邮件。</span><span class="sxs-lookup"><span data-stu-id="906c5-161">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="906c5-162">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="906c5-162">When a user leaves the organization</span></span> 

<span data-ttu-id="906c5-163">如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的聊天消息将存储在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="906c5-163">If a user leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="906c5-164">聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="906c5-164">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="906c5-165">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="906c5-165">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="906c5-166">如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="906c5-166">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="906c5-167">限制</span><span class="sxs-lookup"><span data-stu-id="906c5-167">Limitations</span></span>

<span data-ttu-id="906c5-168">我们正在不断努力优化 Teams 中的保留功能。</span><span class="sxs-lookup"><span data-stu-id="906c5-168">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="906c5-169">同时，下面介绍了应注意的一些限制：</span><span class="sxs-lookup"><span data-stu-id="906c5-169">In the meantime, here are a few limitations to be aware of:</span></span>
  
- <span data-ttu-id="906c5-170">**Teams 需要单独的保留策略**。</span><span class="sxs-lookup"><span data-stu-id="906c5-170">**Teams requires a separate retention policy**.</span></span> <span data-ttu-id="906c5-171">创建保留策略并切换到 Teams 位置时，所有其他位置都会切换为关闭。</span><span class="sxs-lookup"><span data-stu-id="906c5-171">When you create a retention policy and toggle on the Teams locations, all other locations toggle off.</span></span> <span data-ttu-id="906c5-172">带有 Teams 的保留策略仅可包含 Teams，不可包含其他位置。</span><span class="sxs-lookup"><span data-stu-id="906c5-172">A retention policy that includes Teams can include only Teams and no other locations.</span></span>

- <span data-ttu-id="906c5-173">**组织范围策略不包含 Teams**。</span><span class="sxs-lookup"><span data-stu-id="906c5-173">**Teams isn't included in an org-wide policy**.</span></span> <span data-ttu-id="906c5-174">若要创建组织范围策略，其中不会包含 Teams，因为 Teams 必须有单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-174">If you create an org-wide policy, Teams isn't included because it requires a separate retention policy.</span></span>

- <span data-ttu-id="906c5-175">**Teams 不支持高级保留**。</span><span class="sxs-lookup"><span data-stu-id="906c5-175">**Teams doesn't support advanced retention**.</span></span> <span data-ttu-id="906c5-176">创建保留策略时，如果选择“[标识满足特定条件的内容的高级设置](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)”，则 Teams 位置不可用。</span><span class="sxs-lookup"><span data-stu-id="906c5-176">When you create a retention policy, if you choose the [Advanced settings to identify content that meets specific conditions](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), the Teams locations are not available.</span></span> <span data-ttu-id="906c5-177">目前，当你选择这些位置时，Teams 中的保留适用于所有聊天和频道消息内容。</span><span class="sxs-lookup"><span data-stu-id="906c5-177">Currently, retention in Teams applies to all the chat and channel message content when you select those locations.</span></span>

- <span data-ttu-id="906c5-178">**配置 Teams 频道消息的保留策略时，不包括专用频道中的 Teams 消息**。</span><span class="sxs-lookup"><span data-stu-id="906c5-178">**Teams messages in private channels aren't included when you configure a retention policy for Teams channel messages**.</span></span> <span data-ttu-id="906c5-179">保留策略目前不支持专用频道。</span><span class="sxs-lookup"><span data-stu-id="906c5-179">Currently, private channels aren't supported by retention policies.</span></span> 

- <span data-ttu-id="906c5-180">**Teams 最多可能需要七天的时间来清理过期的消息**。</span><span class="sxs-lookup"><span data-stu-id="906c5-180">**Teams may take up to seven days to clean up expired messages**.</span></span> <span data-ttu-id="906c5-181">应用于 Teams 的保留策略将在保留期到期时删除聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-181">A retention policy applied to Teams will delete chat and channel messages when the retention period expires.</span></span> <span data-ttu-id="906c5-182">但是，它最多可能需要三到七天的时间来清理这些消息并永久删除它们。</span><span class="sxs-lookup"><span data-stu-id="906c5-182">However, it may take between three and seven days to clean up these messages and permanently delete them.</span></span> <span data-ttu-id="906c5-183">此外，在保留期到期后和永久删除消息期间，可以使用电子数据展示工具搜索聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-183">Also, chat and channel messages will be searchable with eDiscovery tools during the time after the retention period expires and when messages are permanently deleted.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="906c5-184">过去的情况是，保留策略无法删除短于 30 天的 Teams 内容，但是我们已经删除了此限制。</span><span class="sxs-lookup"><span data-stu-id="906c5-184">It used to be true that a retention policy couldn't delete Teams content that's less than 30 days old, but we've removed this limitation.</span></span> <span data-ttu-id="906c5-185">现在，Teams 内容的保留期可以是你选择的任意天数，它可以短至 1 天。</span><span class="sxs-lookup"><span data-stu-id="906c5-185">Now the retention period for Teams content can be any number of days you choose and as short as one day.</span></span> <span data-ttu-id="906c5-186">如果保留期为一天，则在保留期到期后的最多七天内将永久删除消息。</span><span class="sxs-lookup"><span data-stu-id="906c5-186">If you do have a retention period of one day, it will take up to seven days after the retention period expires before messages are permanently deleted.</span></span>

- <span data-ttu-id="906c5-187">**Outlook 错误显示的问题**。</span><span class="sxs-lookup"><span data-stu-id="906c5-187">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="906c5-188">如果为 Skype 或 Teams 位置创建保留策略，则当用户在 Outlook 桌面客户端中查看邮箱文件夹的属性时，这些策略中的某个策略将显示为默认文件夹策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-188">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="906c5-189">这是 Outlook 中的错误显示问题，也是一个[已知问题](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="906c5-189">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="906c5-190">应作为默认文件夹策略显示的是应用于该文件夹的邮箱保留策略。</span><span class="sxs-lookup"><span data-stu-id="906c5-190">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="906c5-191">Skype 或 Teams 保留策略不适用于用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="906c5-191">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="906c5-192">**配置问题**：</span><span class="sxs-lookup"><span data-stu-id="906c5-192">**Configuration issues**:</span></span> 
    - <span data-ttu-id="906c5-193">为“**Teams 频道消息**”位置选择“**选择团队**”时，你可能会看到不属于团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="906c5-193">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="906c5-194">不要选择这些组。</span><span class="sxs-lookup"><span data-stu-id="906c5-194">Don't select these groups.</span></span>
    
    - <span data-ttu-id="906c5-195">为“**Teams 聊天**”位置选择“**选择用户**”时，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="906c5-195">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="906c5-196">保留策略并非专为这些用户设计的，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="906c5-196">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a><span data-ttu-id="906c5-197">如何配置 Microsoft Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="906c5-197">How to configure a retention policy for Microsoft Teams</span></span>

<span data-ttu-id="906c5-198">按照[创建和配置保留策略](create-retention-policies.md)以及向导的**选择位置**页面的说明，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="906c5-198">Follow the instructions for [Create and configure retention policies](create-retention-policies.md) and for the **Choose locations** page of the wizard, select the following options:</span></span>

- <span data-ttu-id="906c5-199">“**让我选择特定位置**” > “**Teams 频道消息**”和“**Teams 聊天**”</span><span class="sxs-lookup"><span data-stu-id="906c5-199">**Let me choose specific locations** > **Teams channel messages** and **Teams chats**</span></span>

<span data-ttu-id="906c5-200">适用于 Teams 的保留策略可使用“[保留锁定](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)”，这可能出于监管原因必需的设置。</span><span class="sxs-lookup"><span data-stu-id="906c5-200">A retention policy that applies to Teams can use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), which might be required for regulatory reasons.</span></span>

## <a name="related-information"></a><span data-ttu-id="906c5-201">相关信息</span><span class="sxs-lookup"><span data-stu-id="906c5-201">Related information</span></span>

[<span data-ttu-id="906c5-202">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="906c5-202">Retention policies in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/retention-policies)
