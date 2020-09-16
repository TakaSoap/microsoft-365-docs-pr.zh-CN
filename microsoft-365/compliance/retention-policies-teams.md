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
ms.openlocfilehash: 04ca027b9ce8ad1b36e0d4e60c4e10308a822a63
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816735"
---
# <a name="learn-about-retention-for-microsoft-teams"></a><span data-ttu-id="31956-103">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="31956-103">Learn about retention for Microsoft Teams</span></span>

><span data-ttu-id="31956-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="31956-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="31956-105">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Microsoft Teams 的信息。</span><span class="sxs-lookup"><span data-stu-id="31956-105">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Microsoft Teams.</span></span>

## <a name="how-retention-works-with-microsoft-teams"></a><span data-ttu-id="31956-106">用于 Microsoft Teams 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="31956-106">How retention works with Microsoft Teams</span></span>

<span data-ttu-id="31956-107">可使用保留策略保留 Teams 中的聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="31956-107">You can use a retention policy to retain chats and channel messages in Teams.</span></span> <span data-ttu-id="31956-108">Teams 聊天存储在参与聊天的每个用户的邮箱中的隐藏文件夹内，Teams 频道消息存储在团队组邮箱中类似的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="31956-108">Teams chats are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span>

<span data-ttu-id="31956-109">务必了解，Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。</span><span class="sxs-lookup"><span data-stu-id="31956-109">It's important to understand that Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data indefinitely.</span></span> <span data-ttu-id="31956-110">因此，建议创建保留策略来使用 Teams 位置保留和删除此 Teams 数据。</span><span class="sxs-lookup"><span data-stu-id="31956-110">For this reason, we recommend that you create a retention policy that uses the Teams locations to retain and delete this Teams data.</span></span> <span data-ttu-id="31956-111">此保留策略可以从 Exchange 邮箱和由 Azure 提供技术支持的基础聊天服务中永久删除数据。</span><span class="sxs-lookup"><span data-stu-id="31956-111">This retention policy can permanently delete data from both the Exchange mailboxes and the underlying Azure-powered chat service.</span></span> <span data-ttu-id="31956-112">有关详细信息，请参阅 [Microsoft Teams 中的安全性和合规性](https://go.microsoft.com/fwlink/?linkid=871258)，特别是[信息保护体系结构](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)部分。</span><span class="sxs-lookup"><span data-stu-id="31956-112">For more information, see [Security and compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) and specifically, the [Information Protection Architecture](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture) section.</span></span>

<span data-ttu-id="31956-113">Teams 聊天和频道消息不受针对用户或组邮箱配置的保留策略影响。</span><span class="sxs-lookup"><span data-stu-id="31956-113">Teams chats and channel messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="31956-114">即使 Teams 聊天和频道消息存储在 Exchange 中，此 Teams 数据仍将仅包含在针对 **Teams 频道消息**和 \*\* Teams 聊天\*\*位置配置的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="31956-114">Even though Teams chats and channel messages are stored in Exchange, this Teams data is included only by a retention policy that's configured for the **Teams channel messages** and **Teams chats** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="31956-115">如果用户包含在保留 Teams 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Teams 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="31956-115">If a user is included in an active retention policy that retains Teams data and you a delete a mailbox of a user who is included in this policy, to retain the Teams data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="31956-116">如果不需要为用户保留此 Teams 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="31956-116">If you don't need to retain this Teams data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="31956-117">为聊天和频道消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Teams 消息的隐藏文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="31956-117">After a retention policy is configured for chat and channel messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Teams messages are stored.</span></span> <span data-ttu-id="31956-118">计时器作业最多需要 7 天才能运行。</span><span class="sxs-lookup"><span data-stu-id="31956-118">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="31956-119">这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的另一个隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。</span><span class="sxs-lookup"><span data-stu-id="31956-119">When these items have expired their retention period, they are moved to the SubstrateHolds folder—another hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="31956-120">为聊天和频道消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="31956-120">After a retention policy is configured for chat and channel messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="31956-121">如果保留策略为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="31956-121">When the retention policy is to retain and then delete:</span></span>

![Teams 聊天和频道消息的保留流关系图](../media/teamsretentionlifecycle.png)

<span data-ttu-id="31956-123">对于图中的两条路径：</span><span class="sxs-lookup"><span data-stu-id="31956-123">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="31956-124">**如果用户在保留期内编辑或删除了聊天或频道消息**，则该原始消息将被立即复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="31956-124">**If a chat or channel message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="31956-125">消息将存储在此处，直到保留期到期，然后在 24 小时之内将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="31956-125">The message is stored there until the retention period expires and then the message is permanently deleted within 24 hours.</span></span>

2. <span data-ttu-id="31956-126">**如果未删除聊天或频道消息**，并且对于编辑后的当前消息，则保留期到期后，消息将被移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="31956-126">**If a chat or channel message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="31956-127">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="31956-127">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="31956-128">消息位于 SubstrateHolds 文件夹中时，它将在 24 小时内被永久删除。</span><span class="sxs-lookup"><span data-stu-id="31956-128">When the message is in the SubstrateHolds folder, it is then permanently deleted within 24 hours.</span></span> 

> [!NOTE]
> <span data-ttu-id="31956-129">可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。</span><span class="sxs-lookup"><span data-stu-id="31956-129">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="31956-130">消息被永久删除（位于 SubstrateHolds 文件夹中）前，仍可由 eDiscovery 工具搜索。</span><span class="sxs-lookup"><span data-stu-id="31956-130">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="31956-131">如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。</span><span class="sxs-lookup"><span data-stu-id="31956-131">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="31956-132">“仅保留”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="31956-132">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="31956-133">**如果编辑或删除了聊天消息或频道消息**：立即在 SubstrateHolds 文件夹中创建原始消息的副本，并将其保留在那里，直到保留期到期。</span><span class="sxs-lookup"><span data-stu-id="31956-133">**If a chat or channel message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="31956-134">然后，此消息会在 24 小时内从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="31956-134">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="31956-135">**如果项目在保持期内未遭修改或删除**以及保留期内编辑后的当前消息：保留期前后无变化；消息仍保留在原始位置。</span><span class="sxs-lookup"><span data-stu-id="31956-135">**If the item is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="31956-136">“仅删除”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="31956-136">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="31956-137">**如果消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="31956-137">**If the message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="31956-138">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="31956-138">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="31956-139">然后，此消息会在 24 小时内从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="31956-139">Then the message is permanently deleted from the SubstrateHolds folder within 24 hours.</span></span>

2. <span data-ttu-id="31956-140">**如果用户在保留期内删除项目**，该项目将立即移至 SubstrateHolds 文件夹，并在 24 小时内将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="31956-140">**If the item is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is permanently deleted within 24 hours.</span></span>


## <a name="skype-for-business-and-teams-interop-chats"></a><span data-ttu-id="31956-141">Skype for Business 和 Teams 互操作聊天</span><span class="sxs-lookup"><span data-stu-id="31956-141">Skype for Business and Teams interop chats</span></span>

<span data-ttu-id="31956-142">当 Skype for Business 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="31956-142">When a Skype for Business chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="31956-143">Teams 保留策略将从 Teams 线程应用于这些消息。</span><span class="sxs-lookup"><span data-stu-id="31956-143">Teams retention policies will apply to these messages from the Teams thread.</span></span> 

<span data-ttu-id="31956-144">但是，如果已为 Skype for Business 开启对话历史记录，并且从 Skype for Business 客户端将其保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。</span><span class="sxs-lookup"><span data-stu-id="31956-144">However, if conversation history is turned on for Skype for Business and from the Skype for Business client side that history is being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span> <span data-ttu-id="31956-145">对于此内容，请使用为 Skype for Business 配置的保留策略。</span><span class="sxs-lookup"><span data-stu-id="31956-145">For this content, use a retention policy that's configured for Skype for Business.</span></span>

## <a name="meetings-and-external-users"></a><span data-ttu-id="31956-146">会议和外部用户</span><span class="sxs-lookup"><span data-stu-id="31956-146">Meetings and external users</span></span>

<span data-ttu-id="31956-147">频道会议邮件的存储方式与频道消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 频道消息**位置。</span><span class="sxs-lookup"><span data-stu-id="31956-147">Channel meeting messages are stored the same way as channel messages, so for this data, select the **Teams channel messages** location when you configure your retention policy.</span></span>

<span data-ttu-id="31956-148">临时会议邮件的存储方式与群组聊天消息相同，因此对于此数据，在配置保留策略时，请选择 **Teams 聊天**位置。</span><span class="sxs-lookup"><span data-stu-id="31956-148">Impromptu meeting messages are stored in the same way as group chat messages, so for this data, select the **Teams chats** location when you configure your retention policy.</span></span>

<span data-ttu-id="31956-149">当外部用户加入你的组织主持的会议时：</span><span class="sxs-lookup"><span data-stu-id="31956-149">When external users are included in a meeting that your organization hosts:</span></span>

- <span data-ttu-id="31956-150">如果外部用户使用租户中的来宾帐户加入，此用户将有一个影子邮箱，可遵循组织的 Teams 保留策略。</span><span class="sxs-lookup"><span data-stu-id="31956-150">If an external user joins by using a guest account in your tenant, this user has a shadow mailbox that can be subject to your organization's retention policy for Teams.</span></span> <span data-ttu-id="31956-151">会议中的任何邮件都存储在用户的邮箱和影子邮箱中。</span><span class="sxs-lookup"><span data-stu-id="31956-151">Any messages from the meeting are stored in both your users' mailbox and the shadow mailbox.</span></span> 

- <span data-ttu-id="31956-152">如果外部用户使用来自其他 Microsoft 365 组织的帐户加入，则你的保留策略无法删除此用户的邮件，因为它们存储在该用户在其他租户中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="31956-152">If an external user joins by using an account from another Microsoft 365 organization, your retention policies can't delete messages for this user because they are stored in that user's mailbox in another tenant.</span></span> <span data-ttu-id="31956-153">但是对于同一会议，你的保留策略可以为你的用户删除邮件。</span><span class="sxs-lookup"><span data-stu-id="31956-153">For the same meeting however, your retention policies can delete messages for your users.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="31956-154">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="31956-154">When a user leaves the organization</span></span> 

<span data-ttu-id="31956-155">如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的聊天消息将存储在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="31956-155">If a user leaves your organization and their Microsoft 365 account is deleted, their chat messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="31956-156">聊天消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="31956-156">The chat messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="31956-157">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="31956-157">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="31956-158">如果用户在 Teams 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="31956-158">If the user stored any files in Teams, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="31956-159">限制</span><span class="sxs-lookup"><span data-stu-id="31956-159">Limitations</span></span>

<span data-ttu-id="31956-160">我们正在不断努力优化 Teams 中的保留功能。</span><span class="sxs-lookup"><span data-stu-id="31956-160">We're continuously working on optimizing retention functionality in Teams.</span></span> <span data-ttu-id="31956-161">在此期间，在对 Teams 频道消息和聊天使用保留时，需要注意以下几个限制：</span><span class="sxs-lookup"><span data-stu-id="31956-161">In the meantime, here are a few limitations to be aware of when you use retention for Teams channel messages and chats:</span></span>

- <span data-ttu-id="31956-162">**配置 Teams 频道消息的保留策略时，不包括专用频道中的 Teams 消息**。</span><span class="sxs-lookup"><span data-stu-id="31956-162">**Teams messages in private channels aren't included when you configure a retention policy for Teams channel messages**.</span></span> <span data-ttu-id="31956-163">保留策略目前不支持专用频道。</span><span class="sxs-lookup"><span data-stu-id="31956-163">Currently, private channels aren't supported by retention policies.</span></span> 

- <span data-ttu-id="31956-164">**Teams 聊天和频道消息不会保留赞和其他反应**。</span><span class="sxs-lookup"><span data-stu-id="31956-164">**Likes and other reactions are not retained for Teams chat and channel messages**.</span></span> <span data-ttu-id="31956-165">保留策略不支持其他人以表情符形式所做的反应。</span><span class="sxs-lookup"><span data-stu-id="31956-165">Reactions from others in the form of emoticons aren't supported by retention policies.</span></span>

- <span data-ttu-id="31956-166">**Outlook 错误显示的问题**。</span><span class="sxs-lookup"><span data-stu-id="31956-166">**Incorrect display issue in Outlook**.</span></span> <span data-ttu-id="31956-167">如果为 Skype 或 Teams 位置创建保留策略，则当用户在 Outlook 桌面客户端中查看邮箱文件夹的属性时，这些策略中的某个策略将显示为默认文件夹策略。</span><span class="sxs-lookup"><span data-stu-id="31956-167">If you create retention policies for Skype or Teams locations, one of those policies is shown as the default folder policy when a user views the properties of a mailbox folder in the Outlook desktop client.</span></span> <span data-ttu-id="31956-168">这是 Outlook 中的错误显示问题，也是一个[已知问题](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="31956-168">This is an incorrect display issue in Outlook and [a known issue](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies).</span></span> <span data-ttu-id="31956-169">应作为默认文件夹策略显示的是应用于该文件夹的邮箱保留策略。</span><span class="sxs-lookup"><span data-stu-id="31956-169">What should be displayed as the default folder policy is the mailbox retention policy that's applied to the folder.</span></span> <span data-ttu-id="31956-170">Skype 或 Teams 保留策略不适用于用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="31956-170">The Skype or Teams retention policy is not applied to the user's mailbox.</span></span>

- <span data-ttu-id="31956-171">**配置问题**：</span><span class="sxs-lookup"><span data-stu-id="31956-171">**Configuration issues**:</span></span> 
    - <span data-ttu-id="31956-172">为“**Teams 频道消息**”位置选择“**选择团队**”时，你可能会看到不属于团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="31956-172">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="31956-173">不要选择这些组。</span><span class="sxs-lookup"><span data-stu-id="31956-173">Don't select these groups.</span></span>
    
    - <span data-ttu-id="31956-174">为“**Teams 聊天**”位置选择“**选择用户**”时，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="31956-174">When you select **Choose users** for the **Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="31956-175">保留策略并非专为这些用户设计的，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="31956-175">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="31956-176">配置指南</span><span class="sxs-lookup"><span data-stu-id="31956-176">Configuration guidance</span></span>

<span data-ttu-id="31956-177">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="31956-177">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="31956-178">如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="31956-178">If you're ready to configure a retention policy for Teams, see [Create and configure retention policies](create-retention-policies.md).</span></span>
