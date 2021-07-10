---
title: 创建和配置保留策略以自动保留或删除内容
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
description: 使用保留策略有效掌控用户使用电子邮件、文档和对话生成的内容。 保留所需内容并删除不需要的内容。
ms.openlocfilehash: 97b90cc84e2b14e5c63779ea8b941a5ffe64bcd7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362326"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="f0b21-104">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-104">Create and configure retention policies</span></span>

><span data-ttu-id="f0b21-105">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="f0b21-105">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="f0b21-106">使用保留策略通过主动决定是保留内容、删除内容还是保留然后删除内容来管理组织的数据。</span><span class="sxs-lookup"><span data-stu-id="f0b21-106">Use a retention policy to manage the data for your organization by deciding proactively whether to retain content, delete content, or retain and then delete the content.</span></span>

<span data-ttu-id="f0b21-107">保留策略在容器级别分配相同的保留设置，以通过该容器中的内容自动继承，使你能够高效率地完成这一操作。</span><span class="sxs-lookup"><span data-stu-id="f0b21-107">A retention policy lets you do this very efficiently by assigning the same retention settings at the container level to be automatically inherited by content in that container.</span></span> <span data-ttu-id="f0b21-108">例如，SharePoint 网站中的所有项目、用户的 Exchange 邮箱中的所有电子邮件、用于 Microsoft Teams 的团队的所有频道邮件。</span><span class="sxs-lookup"><span data-stu-id="f0b21-108">For example, all items in SharePoint sites, all email messages in users' Exchange mailboxes, all channel messages for teams that are used with Microsoft Teams.</span></span> <span data-ttu-id="f0b21-109">如果不确定是使用容器级别的保留策略，还是使用项级别的保留标签，请参阅保留 [和保留标签](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-109">If you're not sure whether to use a retention policy at the container level or a retention label at the item level, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="f0b21-110">若要深入了解保留策略以及 Microsoft 365 中保留的工作原理，请参阅 [保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-110">For more information about retention policies and how retention works in Microsoft 365, see [Learn about retention policies and retention labels](retention.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f0b21-111">本页上的信息适用于合规性管理员。</span><span class="sxs-lookup"><span data-stu-id="f0b21-111">The information on this page is for compliance administrators.</span></span> <span data-ttu-id="f0b21-112">如果你不是管理员，并且希望了解为使用的应用配置保留策略的信息，请联系技术支持、IT 部门或管理员。</span><span class="sxs-lookup"><span data-stu-id="f0b21-112">If you are not an administrator and want to understand how retention policies have been configured for the apps that you use, contact your help desk, IT department, or administrator.</span></span> <span data-ttu-id="f0b21-113">如果在 Teams 聊天和频道消息中看见保留策略消息，可能会发现查看 [Teams 中有关保留策略的消息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-113">If you're seeing messages about retention policies in Teams chats and channel messages, you might find it helpful to review [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f0b21-114">准备工作</span><span class="sxs-lookup"><span data-stu-id="f0b21-114">Before you begin</span></span>

<span data-ttu-id="f0b21-115">组织的全局管理员具有创建和编辑保留策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="f0b21-115">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="f0b21-116">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="f0b21-117">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-117">Create and configure a retention policy</span></span>

<span data-ttu-id="f0b21-118">虽然保留策略可以支持在保留策略中标识为"位置"的多个服务，但无法创建包含所有受支持位置的单个保留策略：</span><span class="sxs-lookup"><span data-stu-id="f0b21-118">Although a retention policy can support multiple services that are identified as "locations" in the retention policy, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="f0b21-119">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="f0b21-119">Exchange email</span></span>
- <span data-ttu-id="f0b21-120">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="f0b21-120">SharePoint site</span></span>
- <span data-ttu-id="f0b21-121">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="f0b21-121">OneDrive accounts</span></span>
- <span data-ttu-id="f0b21-122">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="f0b21-122">Microsoft 365 groups</span></span>
- <span data-ttu-id="f0b21-123">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b21-123">Skype for Business</span></span>
- <span data-ttu-id="f0b21-124">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="f0b21-124">Exchange public folders</span></span>
- <span data-ttu-id="f0b21-125">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="f0b21-125">Teams channel messages</span></span>
- <span data-ttu-id="f0b21-126">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="f0b21-126">Teams chats</span></span>
- <span data-ttu-id="f0b21-127">yammer 社区消息</span><span class="sxs-lookup"><span data-stu-id="f0b21-127">Yammer community messages</span></span>
- <span data-ttu-id="f0b21-128">Yammer 用户消息</span><span class="sxs-lookup"><span data-stu-id="f0b21-128">Yammer user messages</span></span>

<span data-ttu-id="f0b21-129">如果你在创建保留策略时选择 Teams 或 Yammer 位置，其他位置将被自动排除。</span><span class="sxs-lookup"><span data-stu-id="f0b21-129">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="f0b21-130">这意味着遵循的说明取决于你需要包括 Teams 还是 Yammer 位置：</span><span class="sxs-lookup"><span data-stu-id="f0b21-130">This means that the instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- [<span data-ttu-id="f0b21-131">有关 Teams 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="f0b21-131">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="f0b21-132">有关 Yammer 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="f0b21-132">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- [<span data-ttu-id="f0b21-133">有关 Teams 和 Yammer 以外位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="f0b21-133">Instructions for a retention policy for locations other than Teams and Yammer</span></span>](#retention-policy-for-locations-other-than-teams-and-yammer)

<span data-ttu-id="f0b21-134">如果你有多个保留策略，但同时你又有使用保留标签，请参阅[保留原则或优先原则？](retention.md#the-principles-of-retention-or-what-takes-precedence)了解多个保留设置应用于同一内容时的结果。</span><span class="sxs-lookup"><span data-stu-id="f0b21-134">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="f0b21-135">Teams 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-135">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="f0b21-136">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="f0b21-136">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="f0b21-137">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-137">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="f0b21-138">对于 **选择要应用策略的位置** 页面，请为 Teams 选择任何或所有位置:</span><span class="sxs-lookup"><span data-stu-id="f0b21-138">For the **Choose locations to apply the policy** page, select any or all of the locations for Teams:</span></span>
    - <span data-ttu-id="f0b21-139">**Teams 频道消息**: 来自标准频道聊天和标准频道会议的消息，但不包括来自具有其自己策略位置的 [私人频道](/microsoftteams/private-channels)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-139">**Teams channel message**: Messages from standard channel chats and standard channel meetings, but not from [private channels](/microsoftteams/private-channels) that have their own policy location.</span></span>
    - <span data-ttu-id="f0b21-140">**Teams 聊天**: 来自私人 1:1 聊天、群组聊天和会议聊天的消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-140">**Teams chats**: Messages from private 1:1 chats, group chats, and meeting chats.</span></span>
    - <span data-ttu-id="f0b21-141">**Teams 专用频道消息**: 来自私人频道聊天和私人频道会议的消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-141">**Teams private channel messages**: Messages from private channel chats and private channel meetings.</span></span> <span data-ttu-id="f0b21-142">此选项当前以预览版推出，如果未显示，请在几天后重试。</span><span class="sxs-lookup"><span data-stu-id="f0b21-142">This option is currently rolling out in preview and if you don't see it displayed, try again in a few days.</span></span>
    
   <span data-ttu-id="f0b21-143">默认情况下，[选择所有团队和所有用户](#a-policy-that-applies-to-entire-locations)，但你可以通过选择“**编辑**”选项来优化此设置，以为 [特定包含项或排除项](#a-policy-with-specific-inclusions-or-exclusions) 配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-143">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the **Edit** options to configure a retention policy for [specific inclusions or exclusions](#a-policy-with-specific-inclusions-or-exclusions).</span></span> <span data-ttu-id="f0b21-144">但是，在更改默认设置之前，请注意保留策略在配置为包含或排除邮件时删除邮件的下列影响：</span><span class="sxs-lookup"><span data-stu-id="f0b21-144">However, before you change the default, be aware of the following consequences for a retention policy that deletes messages when it's configured for includes or excludes:</span></span>
    
    - <span data-ttu-id="f0b21-145">对于群组聊天信息和私人频道信息，由于信息的副本保存在每个参加聊天的用户的邮箱中，所以在 eDiscovery 结果中会继续返回未分配策略用户的信息副本。</span><span class="sxs-lookup"><span data-stu-id="f0b21-145">For group chat messages and private channel messages, because a copy of messages are saved in each user's mailbox who are included in the chat, copies of messages will continue to be returned in eDiscovery results from users who weren't assigned the policy.</span></span>
    - <span data-ttu-id="f0b21-146">对于未分配策略的用户，已删除的邮件将返回其 Teams 搜索结果中，但不会显示邮件内容，因为从分配给用户的策略被永久删除。</span><span class="sxs-lookup"><span data-stu-id="f0b21-146">For users who weren't assigned the policy, deleted messages will be returned in their Teams search results but won't display the contents of the message as a result of the permanent deletion from the policy assigned to users.</span></span>

4. <span data-ttu-id="f0b21-147">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="f0b21-147">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="f0b21-148">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-148">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="f0b21-149">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-149">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="f0b21-150">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-150">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="f0b21-151">有关何时对 Teams 使用保留策略并了解最终用户体验的指南，请参阅 [管理 Microsoft Teams](/microsoftteams/retention-policies) 保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-151">For guidance when to use retention policies for Teams and understand the end user experience, see [Manage retention policies for Microsoft Teams](/microsoftteams/retention-policies) from the Teams documentation.</span></span>

<span data-ttu-id="f0b21-152">有关保留对 Teams 的工作原理的技术详细信息，包括通过演练确定保留和计时信息时支持哪些邮件元素，请参阅 [了解 Microsoft Teams](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-152">For technical details about how retention works for Teams, including what elements of messages are supported for retention and timing information with example walkthroughs, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).</span></span>

#### <a name="known-configuration-issues"></a><span data-ttu-id="f0b21-153">已知的配置问题</span><span class="sxs-lookup"><span data-stu-id="f0b21-153">Known configuration issues</span></span>

- <span data-ttu-id="f0b21-154">虽然可以选择从上次修改项目时开始保留期的选项，但始终使用 **从项目创建时** 的值。</span><span class="sxs-lookup"><span data-stu-id="f0b21-154">Although you can select the option to start the retention period when items were last modified, the value of **When items were created** is always used.</span></span> <span data-ttu-id="f0b21-155">对于已编辑的邮件，将保存一份带有原始时间戳的原始邮件副本，以标识创建此预编辑邮件的时间，并且该编辑后邮件具有较新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="f0b21-155">For messages that are edited, a copy of the original message is saved with its original timestamp to identify when this pre-edited message was created, and the post-edited message has a newer timestamp.</span></span>

- <span data-ttu-id="f0b21-156">为 **Teams 频道消息** 位置选择“**编辑**”时，你可能会看到不属于团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="f0b21-156">When you select **Edit** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="f0b21-157">不要选择这些组。</span><span class="sxs-lookup"><span data-stu-id="f0b21-157">Don't select these groups.</span></span>

- <span data-ttu-id="f0b21-158">在为 Teams 聊天位置选择“**编辑**”时，可能看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-158">When you select **Edit** for the Teams chats location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="f0b21-159">保留策略并非专为这些用户设计，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="f0b21-159">Retention policies aren't designed for these users, so don't select them.</span></span>


#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="f0b21-160">支持团队所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-160">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="f0b21-161">Teams 不只是聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-161">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="f0b21-162">如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应使用 **Microsoft 365 组** 位置来额外配置一个包括该 Microsoft 365 组的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-162">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="f0b21-163">此保留策略适用于组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-163">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="f0b21-164">如果你有团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站** 或 **OneDrive 帐户** 位置的保留策略来保留和删除 Teams 中的文件：</span><span class="sxs-lookup"><span data-stu-id="f0b21-164">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="f0b21-165">聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="f0b21-165">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="f0b21-166">上传到频道的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="f0b21-166">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="f0b21-167">当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-167">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="f0b21-168">应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-168">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="f0b21-169">在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="f0b21-169">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="f0b21-170">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="f0b21-170">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="f0b21-171">Yammer 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-171">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="f0b21-172">Yammer 的保留策略处于预览状态，当前不会在由于保留策略而删除消息时通知用户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-172">Retention policies for Yammer are in preview and currently do not inform users when messages are deleted as a result of a retention policy.</span></span>
>
> <span data-ttu-id="f0b21-173">若要使用此功能，Yammer 网络必须为[“本机模式”](/yammer/configure-your-yammer-network/overview-native-mode)，而不是“混合模式”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-173">To use this feature, your Yammer network must be [Native Mode](/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="f0b21-174">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="f0b21-174">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="f0b21-175">选择 **新保留策略** 创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-175">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="f0b21-176">对于 **选择位置以应用策略** 页面，请切换 Yammer 的一个或两个位置：**Yammer 社区邮件**，**Yammer 用户邮件**。</span><span class="sxs-lookup"><span data-stu-id="f0b21-176">For the **Choose locations to apply the policy** page, toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer user messages**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0b21-177">虽然可以创建仅限于 Yammer 用户邮件的保留策略，但此位置的保留策略可以从 Yammer 应用中删除所有社区成员的社区邮件。</span><span class="sxs-lookup"><span data-stu-id="f0b21-177">Although you can create a retention policy for just Yammer user messages, a retention policy for this location can delete community messages from the Yammer app for all community members.</span></span>
    > 
    > <span data-ttu-id="f0b21-178">如果选择此选项，并且保留策略将配置为删除用户邮件，请确保你已了解这一含义。</span><span class="sxs-lookup"><span data-stu-id="f0b21-178">If you choose this option and the retention policy will be configured to delete user messages, make sure you understand this implication.</span></span> <span data-ttu-id="f0b21-179">有关详细信息，请参阅 [Yammer 如何使用保留](retention-policies-yammer.md#how-retention-works-with-yammer)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-179">For more information, see [How retention works with Yammer](retention-policies-yammer.md#how-retention-works-with-yammer).</span></span>
    
    <span data-ttu-id="f0b21-180">默认情况下，将选中所有社区和用户，但你可以通过指定要包括或排除的社区和用户来优化此设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-180">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="f0b21-181">对于 Yammer 用户消息：</span><span class="sxs-lookup"><span data-stu-id="f0b21-181">For Yammer user messages:</span></span> 
    - <span data-ttu-id="f0b21-182">如果你保留 **“所有”** 默认值，则不包含 Azure B2B 来宾用户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-182">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="f0b21-183">如果为 **包含** 列选择“**编辑**”，则可以向外部用户应用保留策略（如果你知道其帐户）。</span><span class="sxs-lookup"><span data-stu-id="f0b21-183">If you select **Edit** for the **Included** column, you can apply a retention policy to external users if you know their account.</span></span>

4. <span data-ttu-id="f0b21-184">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="f0b21-184">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="f0b21-185">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-185">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="f0b21-186">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-186">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="f0b21-187">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-187">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="f0b21-188">有关 Yammer 的保留策略工作方式的详细信息，请参阅[了解 Yammer 的保留](retention-policies-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-188">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="f0b21-189">支持 Yammer 所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-189">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="f0b21-190">Yammer 不仅仅是社区消息和私人消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-190">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="f0b21-191">若要保留和删除 Yammer 网络的电子邮件，请使用 **Microsoft 365 组** 位置来配置额外的保留策略，该策略包括任何用于 Yammer 的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="f0b21-191">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="f0b21-192">如需保留和删除存储在 Yammer 中的文件，则需要一个包括 **SharePoint 网站** 或 **OneDrive 帐户** 位置的保留策略：</span><span class="sxs-lookup"><span data-stu-id="f0b21-192">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="f0b21-193">私人消息中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="f0b21-193">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="f0b21-194">上传到社区的文件存储在 Yammer 社区的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="f0b21-194">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="f0b21-195">应用于 SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Yammer 消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="f0b21-195">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="f0b21-196">在这种情况下，该文件仍显示在 Yammer 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="f0b21-196">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="f0b21-197">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="f0b21-197">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="f0b21-198">Teams 和 Yammer 之外的位置保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-198">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="f0b21-199">对于适用于以下任何服务的保留策略，请按照以下说明进行操作：</span><span class="sxs-lookup"><span data-stu-id="f0b21-199">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="f0b21-200">Exchange：电子邮件和公共文件夹</span><span class="sxs-lookup"><span data-stu-id="f0b21-200">Exchange: Email and public folders</span></span>
- <span data-ttu-id="f0b21-201">SharePoint：网站</span><span class="sxs-lookup"><span data-stu-id="f0b21-201">SharePoint: Sites</span></span>
- <span data-ttu-id="f0b21-202">OneDrive：帐户</span><span class="sxs-lookup"><span data-stu-id="f0b21-202">OneDrive: Accounts</span></span>
- <span data-ttu-id="f0b21-203">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="f0b21-203">Microsoft 365 groups</span></span>
- <span data-ttu-id="f0b21-204">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b21-204">Skype for Business</span></span>

1. <span data-ttu-id="f0b21-205">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="f0b21-205">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="f0b21-206">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-206">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="f0b21-207">在“**选择位置以应用策略**”页面，切换打开或关闭除 Teams 位置之外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-207">For the **Choose locations to apply the policy** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="f0b21-208">对于每个位置，可将其保持为默认的“[将策略应用到整个位置](#a-policy-that-applies-to-entire-locations)”，或者“[指定所包含的和所排除的](#a-policy-with-specific-inclusions-or-exclusions)”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-208">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="f0b21-209">特定于位置的信息：</span><span class="sxs-lookup"><span data-stu-id="f0b21-209">Information specific to locations:</span></span>
    - [<span data-ttu-id="f0b21-210">交换电子邮件和交换公共文件夹</span><span class="sxs-lookup"><span data-stu-id="f0b21-210">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="f0b21-211">SharePoint 网站和 OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="f0b21-211">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="f0b21-212">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="f0b21-212">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="f0b21-213">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b21-213">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="f0b21-214">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="f0b21-214">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="f0b21-215">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-215">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="f0b21-216">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-216">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="f0b21-217">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-217">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="f0b21-218">Exchange 电子邮件和 Exchange 公用文件夹的配置信息</span><span class="sxs-lookup"><span data-stu-id="f0b21-218">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="f0b21-219">通过在邮箱级别应用保留设置，**Exchange 电子邮件** 位置支持用户的电子邮件、日历和其他邮箱项的保留。</span><span class="sxs-lookup"><span data-stu-id="f0b21-219">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span> <span data-ttu-id="f0b21-220">还支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="f0b21-220">Shared mailboxes are also supported.</span></span>

<span data-ttu-id="f0b21-221">将保留设置应用于 **所有收件人** 时，将包括所有 [非活动邮箱](create-and-manage-inactive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-221">When you apply the retention settings to **All recipients**, any [inactive mailboxes](create-and-manage-inactive-mailboxes.md) are included.</span></span> <span data-ttu-id="f0b21-222">但是，如果更改此默认值并配置 [特定包含或排除](#a-policy-with-specific-inclusions-or-exclusions)，则不支持非活动邮箱，并且不会在这些邮箱中应用或排除保留设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-222">However, if you change this default and configure [specific inclusions or exclusions](#a-policy-with-specific-inclusions-or-exclusions), inactive mailboxes aren't supported and retention settings won't be applied or excluded for those mailboxes.</span></span>

<span data-ttu-id="f0b21-223">此外，资源邮箱和 Microsoft 365 组邮箱不支持 **所有收件人** 默认设置，也不支持特定包含或排除。</span><span class="sxs-lookup"><span data-stu-id="f0b21-223">Additionally, resource mailboxes and Microsoft 365 group mailboxes are not supported for the **All recipients** default, or for specific inclusions or exclusions.</span></span> <span data-ttu-id="f0b21-224">对于 Microsoft 365 群组邮箱，请选择 **Microsoft 365 群组** 位置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-224">For Microsoft 365 group mailboxes, select the **Microsoft 365 Groups** location instead.</span></span>

<span data-ttu-id="f0b21-225">如果确实选择了要包括或排除的收件人，则可以选择通讯组和启用电子邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="f0b21-225">If you do choose recipients to include or exclude, you can select distribution groups and email-enabled security groups.</span></span> <span data-ttu-id="f0b21-226">在后台，这些组会在配置时自动展开，以选择组内用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f0b21-226">Behind the scenes, these groups are automatically expanded at the time of configuration to select the mailboxes of the users in the group.</span></span> <span data-ttu-id="f0b21-227">如果这些组的成员身份稍后发生更改，也不会自动更新现有保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-227">If the membership of those groups later change, an existing retention policy isn't automatically updated.</span></span>

<span data-ttu-id="f0b21-228">有关在为 Exchange 配置保留设置时包括和排除哪些邮箱项目的详细信息，请参阅[保留和删除哪些内容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="f0b21-228">For detailed information about which mailbox items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="f0b21-229">**Exchange 公用文件夹** 位置将保留设置应用于所有公共文件夹，并且不能在文件夹或邮箱级别应用。</span><span class="sxs-lookup"><span data-stu-id="f0b21-229">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="f0b21-230">SharePoint 网站的配置信息和 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="f0b21-230">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="f0b21-231">选择 **SharePoint 网站** 位置时，保留策略可以保留和删除 SharePoint 通信网站、未通过 Microsoft 365 组连接的团队网站以及经典网站中的文档。</span><span class="sxs-lookup"><span data-stu-id="f0b21-231">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites.</span></span> <span data-ttu-id="f0b21-232">因为此选项不支持通过 Microsoft 365 组连接的团队网站，所以请改用 **Microsoft 365 组** 位置，该位置适用于该组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-232">Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="f0b21-233">尽管保留策略应用于站点级别，但只有文档具有应用于其的保留设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-233">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="f0b21-234">有关在配置 SharePoint 和 OneDrive 的保留设置时应包含和排除哪些内容的详细信息，请参阅[保留和删除哪些内容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-234">For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="f0b21-235">如果为 SharePoint 网站或 OneDrive 账户指定位置，无需网站访问权限，且在 **编辑位置** 页上指定 URL 时不会进行任何验证。</span><span class="sxs-lookup"><span data-stu-id="f0b21-235">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="f0b21-236">不过，系统会检查你指定的 SharePoint 网站是否在向导结束时存在。</span><span class="sxs-lookup"><span data-stu-id="f0b21-236">However, the SharePoint sites that you specify are checked that they exist at the end of the wizard.</span></span> <span data-ttu-id="f0b21-237">如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-237">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="f0b21-238">如果你看到此消息，请返回到向导，以更改 URL 或删除保留策略中的网站。</span><span class="sxs-lookup"><span data-stu-id="f0b21-238">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="f0b21-239">若要指定单个 OneDrive 帐户包含或排除的，URL 具有以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="f0b21-239">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="f0b21-240">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="f0b21-240">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="f0b21-241">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-241">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="f0b21-242">Microsoft 365 组的配置信息</span><span class="sxs-lookup"><span data-stu-id="f0b21-242">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="f0b21-243">若要保留或删除 Microsoft 365 组（以前称为 Office 365 组）的内容，请使用 **Microsoft 365 组** 位置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-243">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="f0b21-244">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件** 位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-244">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="f0b21-245">此外，尽管 **Exchange 电子邮件** 位置最初允许你指定包括或排除组邮箱，但在尝试保存保留策略时，仍将收到一条错误消息，表明“RemoteGroupMailbox”不是 Exchange 位置的有效选择内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-245">Although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you'll see an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="f0b21-246">默认情况下，应用于 Microsoft 365 组的保留策略包含组邮箱和 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="f0b21-246">By default, a retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site.</span></span> <span data-ttu-id="f0b21-247">存储在 SharePoint 团队网站中的文件与此位置有关，但 Teams 聊天或 Teams 频道与此位置无关，它们拥有自己的保留策略位置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-247">Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

<span data-ttu-id="f0b21-248">因为你希望保留策略仅应用于 Microsoft 365 邮箱或已连接的 SharePoint 团队网站，若要更改默认设置，请使用带有值为以下之一的参数 *应用程序* 的 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f0b21-248">To change the default because you want the retention policy to apply to either just the Microsoft 365 mailboxes, or just the connected SharePoint teams sites, use the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet with the *Applications* parameter with one of the following values:</span></span>

- <span data-ttu-id="f0b21-249">`Group:Exchange` 仅适用于已连接到组的 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f0b21-249">`Group:Exchange` for just Microsoft 365 mailboxes that are connected to the group.</span></span>
- <span data-ttu-id="f0b21-250">`Group:SharePoint` 仅适用于已连接到组的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="f0b21-250">`Group:SharePoint` for just SharePoint sites that are connected to the group.</span></span>

<span data-ttu-id="f0b21-251">若要返回到所选 Microsoft 365 组的邮箱和 SharePoint 网站的默认值，请指定 `Group:Exchange,SharePoint`。</span><span class="sxs-lookup"><span data-stu-id="f0b21-251">To return to the default value of both the mailbox and SharePoint site for the selected Microsoft 365 groups, specify `Group:Exchange,SharePoint`.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="f0b21-252">Skype for Business 的配置信息</span><span class="sxs-lookup"><span data-stu-id="f0b21-252">Configuration information for Skype for Business</span></span>

<span data-ttu-id="f0b21-253">与其他位置不同，无法将 Skype 位置的状态切换为自动包含所有用户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-253">Unlike other locations, you can't toggle the status of the Skype location on to automatically include all users.</span></span> <span data-ttu-id="f0b21-254">相反，当您打开该位置时，您必须选择 **“编辑”** 选项以手动选择要保留其对话的用户：</span><span class="sxs-lookup"><span data-stu-id="f0b21-254">Instead, when you turn on that location, you must then select the **Edit** option to manually choose the users whose conversations you want to retain:</span></span>

![编辑 Skype 位置以使用保留策略](../media/skype-location-retention-policies.png)

<span data-ttu-id="f0b21-256">选择此 **编辑** 选项后，在 **Skype for Business** 窗格中，您可以通过选择 **名称** 列前的隐藏框快速包含所有用户。</span><span class="sxs-lookup"><span data-stu-id="f0b21-256">After you select this **Edit** option, in the **Skype for Business** pane you can quickly include all users by selecting the hidden box before the **Name** column.</span></span> <span data-ttu-id="f0b21-257">但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-257">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="f0b21-258">因此，如果通过选中此框包括 1，000 个用户，这与手动选择要包括的 1，000 个用户相同，这是 Skype for Business 支持的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f0b21-258">So if you include 1,000 users by selecting this box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="f0b21-259">请注意，Outlook 中的“**对话历史记录**”文件夹是一个与 Skype 存档没有任何关系的功能。</span><span class="sxs-lookup"><span data-stu-id="f0b21-259">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="f0b21-260">最终用户可以关闭“**对话历史记录**”，但是 Skype 的存档功能是将 Skype 对话的副本存储到隐藏的文件夹。电子数据展示可以访问该文件夹，但用户不可以。</span><span class="sxs-lookup"><span data-stu-id="f0b21-260">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="f0b21-261">保留和删除内容的设置</span><span class="sxs-lookup"><span data-stu-id="f0b21-261">Settings for retaining and deleting content</span></span>

<span data-ttu-id="f0b21-262">通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="f0b21-262">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="f0b21-263">仅保留</span><span class="sxs-lookup"><span data-stu-id="f0b21-263">Retain-only</span></span>

    <span data-ttu-id="f0b21-264">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：不执行任何操作**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-264">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="f0b21-265">或者，选择“**永久保留项目**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-265">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="f0b21-266">保留后删除</span><span class="sxs-lookup"><span data-stu-id="f0b21-266">Retain and then delete</span></span>

    <span data-ttu-id="f0b21-267">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：自动删除项目**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-267">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="f0b21-268">仅删除</span><span class="sxs-lookup"><span data-stu-id="f0b21-268">Delete-only</span></span>

    <span data-ttu-id="f0b21-269">对于此配置，请选择“**仅在达到特定年龄时删除项目”**。</span><span class="sxs-lookup"><span data-stu-id="f0b21-269">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="f0b21-270">将内容保留一段特定时间</span><span class="sxs-lookup"><span data-stu-id="f0b21-270">Retaining content for a specific period of time</span></span>

<span data-ttu-id="f0b21-271">配置保留策略时，可选择将内容保留至特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="f0b21-271">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="f0b21-272">或者，永久保留项目。</span><span class="sxs-lookup"><span data-stu-id="f0b21-272">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="f0b21-273">配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="f0b21-273">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="f0b21-274">保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。</span><span class="sxs-lookup"><span data-stu-id="f0b21-274">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="f0b21-275">针对保留期的开始，你还可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Microsoft 365 组）。</span><span class="sxs-lookup"><span data-stu-id="f0b21-275">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups, when the content was last modified.</span></span>

<span data-ttu-id="f0b21-276">示例：</span><span class="sxs-lookup"><span data-stu-id="f0b21-276">Examples:</span></span>

- <span data-ttu-id="f0b21-p135">SharePoint：如果希望将某个网站集中的项目自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留一 年。如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留七年。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p135">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="f0b21-p136">Exchange：如果想将邮箱中的项目保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。对于 Exchange 项目，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。根据最后一次修改的时间来保留项目这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p136">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email. Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="f0b21-282">保留期结束后，选择是否要永久删除内容：</span><span class="sxs-lookup"><span data-stu-id="f0b21-282">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="f0b21-284">删除超过特定年限的内容</span><span class="sxs-lookup"><span data-stu-id="f0b21-284">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="f0b21-285">保留策略既可以先保留再删除项目，也可以不保留即删除旧项目。</span><span class="sxs-lookup"><span data-stu-id="f0b21-285">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="f0b21-286">在这两种情况下，如果保留策略删除项目，请务必了解为保留策略指定的时间期限是从项目创建或修改时开始计算，而不是从策略分配时开始计算。</span><span class="sxs-lookup"><span data-stu-id="f0b21-286">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="f0b21-p137">因此首次分配保留策略前，尤其是当该策略会删除项目时，请先考虑现有内容的年龄，以及该策略对该内容有何影响。在分配策略之前，你还需要与用户就新的策略进行沟通，以便其有时间评估可能的影响。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p137">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content. You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="f0b21-289">应用于位置整体的策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-289">A policy that applies to entire locations</span></span>

<span data-ttu-id="f0b21-290">选择位置时（Skype for Business 除外），当位置的状态是“**开启**”时，默认设置是“**全部**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-290">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="f0b21-291">如果将保留策略应用于整个位置的任意组合，则不会限制该策略可以包含的收件人、网站、帐户和组等数量。</span><span class="sxs-lookup"><span data-stu-id="f0b21-291">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="f0b21-p138">例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和收件人的数量有多少，都会对其应用策略。并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。</span><span class="sxs-lookup"><span data-stu-id="f0b21-p138">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="f0b21-294">包含或排除特定位置、用户或组的策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-294">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="f0b21-295">注意，当使用可选配置将保留设置搜索范围缩小到特定用户、特定 Microsoft 365 组或特定网站时，才需要注意每个策略的限制。</span><span class="sxs-lookup"><span data-stu-id="f0b21-295">Be aware that if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of.</span></span> <span data-ttu-id="f0b21-296">有关详细信息，请参阅《[保留策略和保留标签策略的限制](retention-limits.md)》。</span><span class="sxs-lookup"><span data-stu-id="f0b21-296">For more information, see [Limits for retention policies and retention label policies](retention-limits.md).</span></span> 

<span data-ttu-id="f0b21-297">若要使用可选配置限定保留设置的范围，请确保该位置的“**状态**”为“**开启**”，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。</span><span class="sxs-lookup"><span data-stu-id="f0b21-297">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="f0b21-298">如果你配置了包含项，然后删除了最后一项，则配置会将位置的设置还原为“**所有**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-298">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="f0b21-299">保存策略之前，请确保这是你期望的配置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-299">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="f0b21-300">例如，如果你指定了一个 要在根据配置删除数据的保留策略中包含的 SharePoint 网站，然后删除了这个网站，那么默认情况下，所有 SharePoint 网站都将受到永久删除数据的保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="f0b21-300">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="f0b21-301">这同样适用于针对 Exchange 收件人、OneDrive 帐户和 Teams 聊天用户等进行包含设置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-301">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="f0b21-302">在这种情况下，如果不希望“**所有**”这一位置设置受制于保留策略，请关闭位置。</span><span class="sxs-lookup"><span data-stu-id="f0b21-302">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="f0b21-303">或者，指定将不受该策略约束的排除项。</span><span class="sxs-lookup"><span data-stu-id="f0b21-303">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="f0b21-304">更新保留策略</span><span class="sxs-lookup"><span data-stu-id="f0b21-304">Updating retention policies</span></span>

<span data-ttu-id="f0b21-305">某些设置无法在创建并保存保留策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="f0b21-305">Some settings can't be changed after a retention policy is created and saved, which include:</span></span>
- <span data-ttu-id="f0b21-306">保留策略名称和保留期以外的其他保留设置以及何时开始保留期。</span><span class="sxs-lookup"><span data-stu-id="f0b21-306">The retention policy name and the retention settings except the retention period and when to start the retention period.</span></span>

<span data-ttu-id="f0b21-307">如果你编辑保留策略，并且项目已遵循保留策略中的原始设置，则除了新识别的项目之外，更新后的设置将自动应用于此项目。</span><span class="sxs-lookup"><span data-stu-id="f0b21-307">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="f0b21-308">此更新通常非常快，但可能需要数天。</span><span class="sxs-lookup"><span data-stu-id="f0b21-308">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="f0b21-309">完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。</span><span class="sxs-lookup"><span data-stu-id="f0b21-309">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="f0b21-310">锁定策略以防止更改</span><span class="sxs-lookup"><span data-stu-id="f0b21-310">Locking the policy to prevent changes</span></span>

<span data-ttu-id="f0b21-311">如果需要确保任何人都无法关闭策略、删除策略或降低其限制性，请参阅[使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b21-311">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
