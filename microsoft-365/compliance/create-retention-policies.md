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
ms.openlocfilehash: 3e5fec9117a0ce63b80b700c8771cf092b44a69e
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169588"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="043e2-104">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-104">Create and configure retention policies</span></span>

><span data-ttu-id="043e2-105">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="043e2-105">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="043e2-106">使用保留策略通过主动决定是保留内容、删除内容还是保留然后删除内容来管理组织的数据。</span><span class="sxs-lookup"><span data-stu-id="043e2-106">Use a retention policy to manage the data for your organization by deciding proactively whether to retain content, delete content, or retain and then delete the content.</span></span>

<span data-ttu-id="043e2-107">保留策略在容器级别分配相同的保留设置，以通过该容器中的内容自动继承，使你能够高效率地完成这一操作。</span><span class="sxs-lookup"><span data-stu-id="043e2-107">A retention policy lets you do this very efficiently by assigning the same retention settings at the container level to be automatically inherited by content in that container.</span></span> <span data-ttu-id="043e2-108">例如，SharePoint 网站中的所有项目、用户的 Exchange 邮箱中的所有电子邮件、用于 Microsoft Teams 的团队的所有频道邮件。</span><span class="sxs-lookup"><span data-stu-id="043e2-108">For example, all items in SharePoint sites, all email messages in users' Exchange mailboxes, all channel messages for teams that are used with Microsoft Teams.</span></span> <span data-ttu-id="043e2-109">如果不确定是使用容器级别的保留策略，还是使用项级别的保留标签，请参阅保留 [和保留标签](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="043e2-109">If you're not sure whether to use a retention policy at the container level or a retention label at the item level, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="043e2-110">若要深入了解保留策略以及 Microsoft 365 中保留的工作原理，请参阅 [保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="043e2-110">For more information about retention policies and how retention works in Microsoft 365, see [Learn about retention policies and retention labels](retention.md).</span></span>

> [!NOTE]
> <span data-ttu-id="043e2-111">本页上的信息适用于合规性管理员。</span><span class="sxs-lookup"><span data-stu-id="043e2-111">The information on this page is for compliance administrators.</span></span> <span data-ttu-id="043e2-112">如果你不是管理员，并且希望了解为使用的应用配置保留策略的信息，请联系技术支持、IT 部门或管理员。</span><span class="sxs-lookup"><span data-stu-id="043e2-112">If you are not an administrator and want to understand how retention policies have been configured for the apps that you use, contact your help desk, IT department, or administrator.</span></span> <span data-ttu-id="043e2-113">如果在 Teams 聊天和频道消息中看见保留策略消息，可能会发现查看 [Teams 中有关保留策略的消息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="043e2-113">If you're seeing messages about retention policies in Teams chats and channel messages, you might find it helpful to review [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="043e2-114">准备工作</span><span class="sxs-lookup"><span data-stu-id="043e2-114">Before you begin</span></span>

<span data-ttu-id="043e2-115">组织的全局管理员具有创建和编辑保留策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="043e2-115">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="043e2-116">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="043e2-116">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="043e2-117">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-117">Create and configure a retention policy</span></span>

<span data-ttu-id="043e2-118">虽然保留策略可以支持在保留策略中标识为"位置"的多个服务，但无法创建包含所有受支持位置的单个保留策略：</span><span class="sxs-lookup"><span data-stu-id="043e2-118">Although a retention policy can support multiple services that are identified as "locations" in the retention policy, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="043e2-119">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="043e2-119">Exchange email</span></span>
- <span data-ttu-id="043e2-120">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="043e2-120">SharePoint site</span></span>
- <span data-ttu-id="043e2-121">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="043e2-121">OneDrive accounts</span></span>
- <span data-ttu-id="043e2-122">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="043e2-122">Microsoft 365 groups</span></span>
- <span data-ttu-id="043e2-123">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="043e2-123">Skype for Business</span></span>
- <span data-ttu-id="043e2-124">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="043e2-124">Exchange public folders</span></span>
- <span data-ttu-id="043e2-125">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="043e2-125">Teams channel messages</span></span>
- <span data-ttu-id="043e2-126">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="043e2-126">Teams chats</span></span>
- <span data-ttu-id="043e2-127">yammer 社区消息</span><span class="sxs-lookup"><span data-stu-id="043e2-127">Yammer community messages</span></span>
- <span data-ttu-id="043e2-128">Yammer 用户消息</span><span class="sxs-lookup"><span data-stu-id="043e2-128">Yammer user messages</span></span>

<span data-ttu-id="043e2-129">如果你在创建保留策略时选择 Teams 或 Yammer 位置，其他位置将被自动排除。</span><span class="sxs-lookup"><span data-stu-id="043e2-129">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="043e2-130">这意味着遵循的说明取决于你需要包括 Teams 还是 Yammer 位置：</span><span class="sxs-lookup"><span data-stu-id="043e2-130">This means that the instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- [<span data-ttu-id="043e2-131">有关 Teams 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="043e2-131">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="043e2-132">有关 Yammer 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="043e2-132">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- [<span data-ttu-id="043e2-133">有关 Teams 和 Yammer 以外位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="043e2-133">Instructions for a retention policy for locations other than Teams and Yammer</span></span>](#retention-policy-for-locations-other-than-teams-and-yammer)

<span data-ttu-id="043e2-134">如果你有多个保留策略，但同时你又有使用保留标签，请参阅[保留原则或优先原则？](retention.md#the-principles-of-retention-or-what-takes-precedence)了解多个保留设置应用于同一内容时的结果。</span><span class="sxs-lookup"><span data-stu-id="043e2-134">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="043e2-135">Teams 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-135">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="043e2-136">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="043e2-136">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="043e2-137">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-137">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="043e2-138">在“**选择要应用策略的位置**” 页面上，选择 Teams 的一个或两个位置：“**Teams 频道消息**”和“**Teams 聊天**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-138">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="043e2-139">请注意，对于 **Teams 频道消息**，将包括来自标准频道的消息，但不包括来自 [专用频道](/microsoftteams/private-channels)的消息。</span><span class="sxs-lookup"><span data-stu-id="043e2-139">For **Teams channel messages**, message from standard channels but not [private channels](/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="043e2-140">保留策略目前不支持专用频道。</span><span class="sxs-lookup"><span data-stu-id="043e2-140">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="043e2-141">默认情况下，[所有团队和所有用户](#a-policy-that-applies-to-entire-locations)会被选择，但你但是你可以通过选择 [“**选择**”和“**排除**” 选项](#a-policy-with-specific-inclusions-or-exclusions)”来进行优化。</span><span class="sxs-lookup"><span data-stu-id="043e2-141">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span> <span data-ttu-id="043e2-142">但是，在更改默认设置之前，请注意保留策略在配置为包含或排除邮件时删除邮件的下列影响：</span><span class="sxs-lookup"><span data-stu-id="043e2-142">However, before you change the default, be aware of the following consequences for a retention policy that deletes messages when it's configured for includes or excludes:</span></span>
    
    - <span data-ttu-id="043e2-143">对于群组聊天，由于聊天中包含的每个用户邮箱中都保存有邮件副本，因此未分配策略的用户将继续在电子数据展示结果中返回邮件副本。</span><span class="sxs-lookup"><span data-stu-id="043e2-143">For group chats, because a copy of messages are saved in each user's mailbox who are included in the chat, copies of messages will continue to be returned in eDiscovery results from users who weren't assigned the policy.</span></span>
    - <span data-ttu-id="043e2-144">对于未分配策略的用户，已删除的邮件将返回其 Teams 搜索结果中，但不会显示邮件内容，因为从分配给用户的策略被永久删除。</span><span class="sxs-lookup"><span data-stu-id="043e2-144">For users who weren't assigned the policy, deleted messages will be returned in their Teams search results but won't display the contents of the message as a result of the permanent deletion from the policy assigned to users.</span></span>

4. <span data-ttu-id="043e2-145">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="043e2-145">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="043e2-146">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-146">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="043e2-147">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="043e2-147">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="043e2-148">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-148">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="043e2-149">有关何时对 Teams 使用保留策略并了解最终用户体验的指南，请参阅 [管理 Microsoft Teams](/microsoftteams/retention-policies) 保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-149">For guidance when to use retention policies for Teams and understand the end user experience, see [Manage retention policies for Microsoft Teams](/microsoftteams/retention-policies) from the Teams documentation.</span></span>

<span data-ttu-id="043e2-150">有关保留对 Teams 的工作原理的技术详细信息，包括通过演练确定保留和计时信息时支持哪些邮件元素，请参阅 [了解 Microsoft Teams](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="043e2-150">For technical details about how retention works for Teams, including what elements of messages are supported for retention and timing information with example walkthroughs, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).</span></span>

#### <a name="known-configuration-issues"></a><span data-ttu-id="043e2-151">已知的配置问题</span><span class="sxs-lookup"><span data-stu-id="043e2-151">Known configuration issues</span></span>

- <span data-ttu-id="043e2-152">虽然可以选择从上次修改项目时开始保留期的选项，但始终使用 **从项目创建时** 的值。</span><span class="sxs-lookup"><span data-stu-id="043e2-152">Although you can select the option to start the retention period when items were last modified, the value of **When items were created** is always used.</span></span> <span data-ttu-id="043e2-153">对于已编辑的邮件，将保存一份带有原始时间戳的原始邮件副本，以标识创建此预编辑邮件的时间，并且该编辑后邮件具有较新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="043e2-153">For messages that are edited, a copy of the original message is saved with its original timestamp to identify when this pre-edited message was created, and the post-edited message has a newer timestamp.</span></span>

- <span data-ttu-id="043e2-154">为“**Teams 频道消息**”位置选择“**选择团队**”时，你可能会看到不属于团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="043e2-154">When you select **Choose teams** for the **Teams channel messages** location, you might see Microsoft 365 groups that aren't also teams.</span></span> <span data-ttu-id="043e2-155">不要选择这些组。</span><span class="sxs-lookup"><span data-stu-id="043e2-155">Don't select these groups.</span></span>

- <span data-ttu-id="043e2-156">在选择“**为 Teams 聊天选择用户**”位置时，可能看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="043e2-156">When you select **Choose users for the Teams chats** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="043e2-157">保留策略并非专为这些用户设计，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="043e2-157">Retention policies aren't designed for these users, so don't select them.</span></span>


#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="043e2-158">支持团队所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-158">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="043e2-159">Teams 不只是聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="043e2-159">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="043e2-160">如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应使用 **Microsoft 365 组** 位置来额外配置一个包括该 Microsoft 365 组的保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-160">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="043e2-161">此保留策略适用于组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-161">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="043e2-162">如果你有团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站** 或 **OneDrive 帐户** 位置的保留策略来保留和删除 Teams 中的文件：</span><span class="sxs-lookup"><span data-stu-id="043e2-162">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="043e2-163">聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="043e2-163">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="043e2-164">上传到频道的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="043e2-164">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="043e2-165">当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="043e2-165">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="043e2-166">应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="043e2-166">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="043e2-167">在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="043e2-167">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="043e2-168">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="043e2-168">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="043e2-169">Yammer 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-169">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="043e2-170">Yammer 的保留策略处于预览状态，当前不会在由于保留策略而删除消息时通知用户。</span><span class="sxs-lookup"><span data-stu-id="043e2-170">Retention policies for Yammer are in preview and currently do not inform users when messages are deleted as a result of a retention policy.</span></span>
>
> <span data-ttu-id="043e2-171">若要使用此功能，Yammer 网络必须为[“本机模式”](/yammer/configure-your-yammer-network/overview-native-mode)，而不是“混合模式”。</span><span class="sxs-lookup"><span data-stu-id="043e2-171">To use this feature, your Yammer network must be [Native Mode](/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="043e2-172">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="043e2-172">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="043e2-173">选择 **新保留策略** 创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-173">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="043e2-174">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="043e2-174">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="043e2-175">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-175">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="043e2-176">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="043e2-176">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

4. <span data-ttu-id="043e2-177">有关 **选择位置** 的页面，请选择 **“让我选择特定位置”**。</span><span class="sxs-lookup"><span data-stu-id="043e2-177">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="043e2-178">然后切换到 Yammer 的一个或两个位置：**Yammer 社区消息** 和 **Yammer 用户消息**。</span><span class="sxs-lookup"><span data-stu-id="043e2-178">Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer user messages**.</span></span>
    
    <span data-ttu-id="043e2-179">默认情况下，将选中所有社区和用户，但你可以通过指定要包括或排除的社区和用户来优化此设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-179">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="043e2-180">对于 Yammer 用户消息：</span><span class="sxs-lookup"><span data-stu-id="043e2-180">For Yammer user messages:</span></span> 
    - <span data-ttu-id="043e2-181">如果你保留 **“所有”** 默认值，则不包含 Azure B2B 来宾用户。</span><span class="sxs-lookup"><span data-stu-id="043e2-181">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="043e2-182">如果使用 **“选择用户”** 并指定其帐户，则可以向外部用户应用保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-182">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="043e2-183">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-183">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="043e2-184">有关 Yammer 的保留策略工作方式的详细信息，请参阅[了解 Yammer 的保留](retention-policies-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="043e2-184">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="043e2-185">支持 Yammer 所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-185">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="043e2-186">Yammer 不仅仅是社区消息和私人消息。</span><span class="sxs-lookup"><span data-stu-id="043e2-186">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="043e2-187">若要保留和删除 Yammer 网络的电子邮件，请使用 **Microsoft 365 组** 位置来配置额外的保留策略，该策略包括任何用于 Yammer 的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="043e2-187">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="043e2-188">如需保留和删除存储在 Yammer 中的文件，则需要一个包括 **SharePoint 网站** 或 **OneDrive 帐户** 位置的保留策略：</span><span class="sxs-lookup"><span data-stu-id="043e2-188">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="043e2-189">私人消息中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="043e2-189">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="043e2-190">上传到社区的文件存储在 Yammer 社区的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="043e2-190">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="043e2-191">应用于 SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Yammer 消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="043e2-191">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="043e2-192">在这种情况下，该文件仍显示在 Yammer 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="043e2-192">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="043e2-193">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="043e2-193">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="043e2-194">Teams 和 Yammer 之外的位置保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-194">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="043e2-195">对于适用于以下任何服务的保留策略，请按照以下说明进行操作：</span><span class="sxs-lookup"><span data-stu-id="043e2-195">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="043e2-196">Exchange：电子邮件和公共文件夹</span><span class="sxs-lookup"><span data-stu-id="043e2-196">Exchange: Email and public folders</span></span>
- <span data-ttu-id="043e2-197">SharePoint：网站</span><span class="sxs-lookup"><span data-stu-id="043e2-197">SharePoint: Sites</span></span>
- <span data-ttu-id="043e2-198">OneDrive：帐户</span><span class="sxs-lookup"><span data-stu-id="043e2-198">OneDrive: Accounts</span></span>
- <span data-ttu-id="043e2-199">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="043e2-199">Microsoft 365 groups</span></span>
- <span data-ttu-id="043e2-200">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="043e2-200">Skype for Business</span></span>

1. <span data-ttu-id="043e2-201">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择 **策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="043e2-201">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="043e2-202">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-202">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="043e2-203">在“**选择位置**”页面，切换打开或关闭除 Teams 位置之外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="043e2-203">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="043e2-204">对于每个位置，可将其保持为默认的“[将策略应用到整个位置](#a-policy-that-applies-to-entire-locations)”，或者“[指定所包含的和所排除的](#a-policy-with-specific-inclusions-or-exclusions)”。</span><span class="sxs-lookup"><span data-stu-id="043e2-204">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="043e2-205">特定于位置的信息：</span><span class="sxs-lookup"><span data-stu-id="043e2-205">Information specific to locations:</span></span>
    - [<span data-ttu-id="043e2-206">交换电子邮件和交换公共文件夹</span><span class="sxs-lookup"><span data-stu-id="043e2-206">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="043e2-207">SharePoint 网站和 OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="043e2-207">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="043e2-208">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="043e2-208">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="043e2-209">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="043e2-209">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="043e2-210">有关 **保留内容、删除内容，还是同时删除** 向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="043e2-210">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="043e2-211">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-211">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="043e2-212">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="043e2-212">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="043e2-213">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-213">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="043e2-214">Exchange 电子邮件和 Exchange 公用文件夹的配置信息</span><span class="sxs-lookup"><span data-stu-id="043e2-214">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="043e2-215">通过在邮箱级别应用保留设置，**Exchange 电子邮件** 位置支持用户的电子邮件、日历和其他邮箱项的保留。</span><span class="sxs-lookup"><span data-stu-id="043e2-215">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="043e2-216">有关在配置 Exchange 的保留设置时应包含和排除哪些项目的详细信息，请参阅[保留和删除哪些内容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="043e2-216">For detailed information about which items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="043e2-217">请注意，即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件** 位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-217">Note that even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="043e2-218">若要保留这些邮箱中的内容，请选择 **Microsoft 365 组** 位置。</span><span class="sxs-lookup"><span data-stu-id="043e2-218">To retain content in these mailboxes, select the **Microsoft 365 Groups** location.</span></span>

<span data-ttu-id="043e2-219">**Exchange 公用文件夹** 位置将保留设置应用于所有公共文件夹，并且不能在文件夹或邮箱级别应用。</span><span class="sxs-lookup"><span data-stu-id="043e2-219">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="043e2-220">SharePoint 网站的配置信息和 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="043e2-220">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="043e2-221">选择 **SharePoint 网站** 位置时，保留策略可以保留和删除 SharePoint 通信网站、未通过 Microsoft 365 组连接的团队网站以及经典网站中的文档。</span><span class="sxs-lookup"><span data-stu-id="043e2-221">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites.</span></span> <span data-ttu-id="043e2-222">因为此选项不支持通过 Microsoft 365 组连接的团队网站，所以请改用 **Microsoft 365 组** 位置，该位置适用于该组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-222">Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="043e2-223">尽管保留策略应用于站点级别，但只有文档具有应用于其的保留设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-223">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="043e2-224">有关在配置 SharePoint 和 OneDrive 的保留设置时应包含和排除哪些内容的详细信息，请参阅[保留和删除哪些内容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="043e2-224">For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="043e2-225">如果为 SharePoint 网站或 OneDrive 账户指定位置，无需网站访问权限，且在 **编辑位置** 页上指定 URL 时不会进行任何验证。</span><span class="sxs-lookup"><span data-stu-id="043e2-225">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="043e2-226">不过，系统会检查你指定的 SharePoint 网站是否在向导结束时存在。</span><span class="sxs-lookup"><span data-stu-id="043e2-226">However, the SharePoint sites that you specify are checked that they exist at the end of the wizard.</span></span> <span data-ttu-id="043e2-227">如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-227">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="043e2-228">如果你看到此消息，请返回到向导，以更改 URL 或删除保留策略中的网站。</span><span class="sxs-lookup"><span data-stu-id="043e2-228">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="043e2-229">若要指定单个 OneDrive 帐户包含或排除的，URL 具有以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="043e2-229">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="043e2-230">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="043e2-230">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="043e2-231">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="043e2-231">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="043e2-232">Microsoft 365 组的配置信息</span><span class="sxs-lookup"><span data-stu-id="043e2-232">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="043e2-233">若要保留或删除 Microsoft 365 组（以前称为 Office 365 组）的内容，请使用 **Microsoft 365 组** 位置。</span><span class="sxs-lookup"><span data-stu-id="043e2-233">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="043e2-234">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件** 位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-234">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="043e2-235">此外，尽管 **Exchange 电子邮件** 位置最初允许你指定包括或排除组邮箱，但在尝试保存保留策略时，仍将收到一条错误消息，表明“RemoteGroupMailbox”不是 Exchange 位置的有效选择内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-235">Although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you'll see an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="043e2-236">默认情况下，应用于 Microsoft 365 组的保留策略包含组邮箱和 SharePoint 团队网站。</span><span class="sxs-lookup"><span data-stu-id="043e2-236">By default, a retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site.</span></span> <span data-ttu-id="043e2-237">存储在 SharePoint 团队网站中的文件与此位置有关，但 Teams 聊天或 Teams 频道与此位置无关，它们拥有自己的保留策略位置。</span><span class="sxs-lookup"><span data-stu-id="043e2-237">Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

<span data-ttu-id="043e2-238">因为你希望保留策略仅应用于 Microsoft 365 邮箱或已连接的 SharePoint 团队网站，若要更改默认设置，请使用带有值为以下之一的参数 *应用程序* 的 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="043e2-238">To change the default because you want the retention policy to apply to either just the Microsoft 365 mailboxes, or just the connected SharePoint teams sites, use the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell cmdlet with the *Applications* parameter with one of the following values:</span></span>

- <span data-ttu-id="043e2-239">`Group:Exchange` 仅适用于已连接到组的 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="043e2-239">`Group:Exchange` for just Microsoft 365 mailboxes that are connected to the group.</span></span>
- <span data-ttu-id="043e2-240">`Group:SharePoint` 仅适用于已连接到组的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="043e2-240">`Group:SharePoint` for just SharePoint sites that are connected to the group.</span></span>

<span data-ttu-id="043e2-241">若要返回到所选 Microsoft 365 组的邮箱和 SharePoint 网站的默认值，请指定 `Group:Exchange,SharePoint`。</span><span class="sxs-lookup"><span data-stu-id="043e2-241">To return to the default value of both the mailbox and SharePoint site for the selected Microsoft 365 groups, specify `Group:Exchange,SharePoint`.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="043e2-242">Skype for Business 的配置信息</span><span class="sxs-lookup"><span data-stu-id="043e2-242">Configuration information for Skype for Business</span></span>

<span data-ttu-id="043e2-243">与其他位置不同，无法将 Skype 位置的状态切换为自动包含所有用户。</span><span class="sxs-lookup"><span data-stu-id="043e2-243">Unlike other locations, you can't toggle the status of the Skype location on to automatically include all users.</span></span> <span data-ttu-id="043e2-244">相反，当您打开该位置时，您必须选择 **“编辑”** 选项以手动选择要保留其对话的用户：</span><span class="sxs-lookup"><span data-stu-id="043e2-244">Instead, when you turn on that location, you must then select the **Edit** option to manually choose the users whose conversations you want to retain:</span></span>

![编辑 Skype 位置以使用保留策略](../media/skype-location-retention-policies.png)

<span data-ttu-id="043e2-246">选择此 **编辑** 选项后，在 **Skype for Business** 窗格中，您可以通过选择 **名称** 列前的隐藏框快速包含所有用户。</span><span class="sxs-lookup"><span data-stu-id="043e2-246">After you select this **Edit** option, in the **Skype for Business** pane you can quickly include all users by selecting the hidden box before the **Name** column.</span></span> <span data-ttu-id="043e2-247">但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-247">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="043e2-248">因此，如果通过选中此框包括 1，000 个用户，这与手动选择要包括的 1，000 个用户相同，这是 Skype for Business 支持的最大数量。</span><span class="sxs-lookup"><span data-stu-id="043e2-248">So if you include 1,000 users by selecting this box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="043e2-249">请注意，Outlook 中的“**对话历史记录**”文件夹是一个与 Skype 存档没有任何关系的功能。</span><span class="sxs-lookup"><span data-stu-id="043e2-249">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="043e2-250">最终用户可以关闭“**对话历史记录**”，但是 Skype 的存档功能是将 Skype 对话的副本存储到隐藏的文件夹。电子数据展示可以访问该文件夹，但用户不可以。</span><span class="sxs-lookup"><span data-stu-id="043e2-250">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="043e2-251">保留和删除内容的设置</span><span class="sxs-lookup"><span data-stu-id="043e2-251">Settings for retaining and deleting content</span></span>

<span data-ttu-id="043e2-252">通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="043e2-252">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="043e2-253">仅保留</span><span class="sxs-lookup"><span data-stu-id="043e2-253">Retain-only</span></span>

    <span data-ttu-id="043e2-254">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：不执行任何操作**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-254">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="043e2-255">或者，选择“**永久保留项目**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-255">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="043e2-256">保留后删除</span><span class="sxs-lookup"><span data-stu-id="043e2-256">Retain and then delete</span></span>

    <span data-ttu-id="043e2-257">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：自动删除项目**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-257">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="043e2-258">仅删除</span><span class="sxs-lookup"><span data-stu-id="043e2-258">Delete-only</span></span>

    <span data-ttu-id="043e2-259">对于此配置，请选择“**仅在达到特定年龄时删除项目”**。</span><span class="sxs-lookup"><span data-stu-id="043e2-259">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="043e2-260">将内容保留一段特定时间</span><span class="sxs-lookup"><span data-stu-id="043e2-260">Retaining content for a specific period of time</span></span>

<span data-ttu-id="043e2-261">配置保留策略时，可选择将内容保留至特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="043e2-261">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="043e2-262">或者，永久保留项目。</span><span class="sxs-lookup"><span data-stu-id="043e2-262">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="043e2-263">配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="043e2-263">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="043e2-264">保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。</span><span class="sxs-lookup"><span data-stu-id="043e2-264">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="043e2-265">针对保留期的开始，你还可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Microsoft 365 组）。</span><span class="sxs-lookup"><span data-stu-id="043e2-265">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups, when the content was last modified.</span></span>

<span data-ttu-id="043e2-266">示例：</span><span class="sxs-lookup"><span data-stu-id="043e2-266">Examples:</span></span>

- <span data-ttu-id="043e2-p132">SharePoint：如果希望将某个网站集中的项目自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留一 年。如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留七年。</span><span class="sxs-lookup"><span data-stu-id="043e2-p132">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified. If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="043e2-p133">Exchange：如果想将邮箱中的项目保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。对于 Exchange 项目，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。根据最后一次修改的时间来保留项目这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。</span><span class="sxs-lookup"><span data-stu-id="043e2-p133">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year. For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email. Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="043e2-272">保留期结束后，选择是否要永久删除内容：</span><span class="sxs-lookup"><span data-stu-id="043e2-272">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="043e2-274">删除超过特定年限的内容</span><span class="sxs-lookup"><span data-stu-id="043e2-274">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="043e2-275">保留策略既可以先保留再删除项目，也可以不保留即删除旧项目。</span><span class="sxs-lookup"><span data-stu-id="043e2-275">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="043e2-276">在这两种情况下，如果保留策略删除项目，请务必了解为保留策略指定的时间期限是从项目创建或修改时开始计算，而不是从策略分配时开始计算。</span><span class="sxs-lookup"><span data-stu-id="043e2-276">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="043e2-p134">因此首次分配保留策略前，尤其是当该策略会删除项目时，请先考虑现有内容的年龄，以及该策略对该内容有何影响。在分配策略之前，你还需要与用户就新的策略进行沟通，以便其有时间评估可能的影响。</span><span class="sxs-lookup"><span data-stu-id="043e2-p134">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content. You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="043e2-279">应用于位置整体的策略</span><span class="sxs-lookup"><span data-stu-id="043e2-279">A policy that applies to entire locations</span></span>

<span data-ttu-id="043e2-280">选择位置时（Skype for Business 除外），当位置的状态是“**开启**”时，默认设置是“**全部**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-280">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="043e2-281">如果将保留策略应用于整个位置的任意组合，则不会限制该策略可以包含的收件人、网站、帐户和组等数量。</span><span class="sxs-lookup"><span data-stu-id="043e2-281">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="043e2-p135">例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和收件人的数量有多少，都会对其应用策略。并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。</span><span class="sxs-lookup"><span data-stu-id="043e2-p135">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many. And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="043e2-284">包含或排除特定位置、用户或组的策略</span><span class="sxs-lookup"><span data-stu-id="043e2-284">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="043e2-285">注意，当使用可选配置将保留设置搜索范围缩小到特定用户、特定 Microsoft 365 组或特定网站时，才需要注意每个策略的限制。</span><span class="sxs-lookup"><span data-stu-id="043e2-285">Be aware that if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of.</span></span> <span data-ttu-id="043e2-286">有关详细信息，请参阅《[保留策略和保留标签策略的限制](retention-limits.md)》。</span><span class="sxs-lookup"><span data-stu-id="043e2-286">For more information, see [Limits for retention policies and retention label policies](retention-limits.md).</span></span> 

<span data-ttu-id="043e2-287">若要使用可选配置限定保留设置的范围，请确保该位置的“**状态**”为“**开启**”，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。</span><span class="sxs-lookup"><span data-stu-id="043e2-287">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="043e2-288">如果你配置了包含项，然后删除了最后一项，则配置会将位置的设置还原为“**所有**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-288">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="043e2-289">保存策略之前，请确保这是你期望的配置。</span><span class="sxs-lookup"><span data-stu-id="043e2-289">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="043e2-290">例如，如果你指定了一个 要在根据配置删除数据的保留策略中包含的 SharePoint 网站，然后删除了这个网站，那么默认情况下，所有 SharePoint 网站都将受到永久删除数据的保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="043e2-290">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="043e2-291">这同样适用于针对 Exchange 收件人、OneDrive 帐户和 Teams 聊天用户等进行包含设置。</span><span class="sxs-lookup"><span data-stu-id="043e2-291">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="043e2-292">在这种情况下，如果不希望“**所有**”这一位置设置受制于保留策略，请关闭位置。</span><span class="sxs-lookup"><span data-stu-id="043e2-292">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="043e2-293">或者，指定将不受该策略约束的排除项。</span><span class="sxs-lookup"><span data-stu-id="043e2-293">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="043e2-294">更新保留策略</span><span class="sxs-lookup"><span data-stu-id="043e2-294">Updating retention policies</span></span>

<span data-ttu-id="043e2-295">某些设置无法在创建并保存保留策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="043e2-295">Some settings can't be changed after a retention policy is created and saved, which include:</span></span>
- <span data-ttu-id="043e2-296">保留策略名称和保留期以外的其他保留设置以及何时开始保留期。</span><span class="sxs-lookup"><span data-stu-id="043e2-296">The retention policy name and the retention settings except the retention period and when to start the retention period.</span></span>

<span data-ttu-id="043e2-297">如果你编辑保留策略，并且项目已遵循保留策略中的原始设置，则除了新识别的项目之外，更新后的设置将自动应用于此项目。</span><span class="sxs-lookup"><span data-stu-id="043e2-297">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="043e2-298">此更新通常非常快，但可能需要数天。</span><span class="sxs-lookup"><span data-stu-id="043e2-298">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="043e2-299">完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。</span><span class="sxs-lookup"><span data-stu-id="043e2-299">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="043e2-300">锁定策略以防止更改</span><span class="sxs-lookup"><span data-stu-id="043e2-300">Locking the policy to prevent changes</span></span>

<span data-ttu-id="043e2-301">如果需要确保任何人都无法关闭策略、删除策略或降低其限制性，请参阅[使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="043e2-301">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
