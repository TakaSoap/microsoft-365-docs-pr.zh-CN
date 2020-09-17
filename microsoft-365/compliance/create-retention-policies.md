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
description: 使用保留策略可以非常高效地控制用户使用电子邮件、文档和对话生成的内容。 保留所需内容并删除不需要的内容。
ms.openlocfilehash: b992452cffbe7fa2df5e7ad02726ca337fbe0f45
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816844"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="5d171-104">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-104">Create and configure retention policies</span></span>

><span data-ttu-id="5d171-105">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="5d171-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5d171-106">使用保留策略来主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="5d171-107">透过将相同的保留设置依照位置如网站或信箱层级的内容进行指派，保留策略可让你工作的更有效率。</span><span class="sxs-lookup"><span data-stu-id="5d171-107">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="5d171-108">如果你不确定是使用保留策略还是保留标签，请参阅[保留策略和保留标签](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="5d171-108">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="5d171-109">有关保留策略和保留的工作方式的详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="5d171-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5d171-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="5d171-110">Before you begin</span></span>

<span data-ttu-id="5d171-111">组织的全局管理员具有创建和编辑保留策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="5d171-111">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="5d171-112">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="5d171-112">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="5d171-113">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-113">Create and configure a retention policy</span></span>

<span data-ttu-id="5d171-114">虽然保留策略可支持多个位置，但你无法创建包含所有受支持位置的单个保留策略：</span><span class="sxs-lookup"><span data-stu-id="5d171-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>
- <span data-ttu-id="5d171-115">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d171-115">Exchange email</span></span>
- <span data-ttu-id="5d171-116">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="5d171-116">SharePoint site</span></span>
- <span data-ttu-id="5d171-117">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="5d171-117">OneDrive accounts</span></span>
- <span data-ttu-id="5d171-118">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="5d171-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="5d171-119">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5d171-119">Skype for Business</span></span>
- <span data-ttu-id="5d171-120">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="5d171-120">Exchange public folders</span></span>
- <span data-ttu-id="5d171-121">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="5d171-121">Teams channel messages</span></span>
- <span data-ttu-id="5d171-122">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="5d171-122">Teams chats</span></span>

<span data-ttu-id="5d171-123">当您在创建保留策略时选择其中一个 Teams 位置时，其他位置将被自动排除。</span><span class="sxs-lookup"><span data-stu-id="5d171-123">When you select either of the Teams locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="5d171-124">因此，请依照你是否需要包含 Teams 地点来取决于要遵循的指示:</span><span class="sxs-lookup"><span data-stu-id="5d171-124">Therefore, the instructions to follow depend on whether you need to include the Teams locations:</span></span>

- [<span data-ttu-id="5d171-125">有关 Teams 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="5d171-125">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="5d171-126">有关 Teams 以外位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="5d171-126">Instructions for a retention policy for locations other than Teams</span></span>](#retention-policy-for-locations-other-than-teams)

<span data-ttu-id="5d171-127">如果你有多个保留策略，但同时你又有使用保留标签，请参阅[保留原则或优先原则？](retention.md#the-principles-of-retention-or-what-takes-precedence)了解多个保留设置应用于同一内容时的结果。</span><span class="sxs-lookup"><span data-stu-id="5d171-127">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="5d171-128">Teams 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-128">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="5d171-129">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="5d171-129">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="5d171-130">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-130">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="5d171-131">在“**选择要应用策略的位置**” 页面上，选择 Teams 的一个或两个位置：“**Teams 频道消息**”和“**Teams 聊天**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-131">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>
     
    <span data-ttu-id="5d171-132">请注意，对于**Teams 频道消息**，将包括来自标准频道的消息，但不包括来自[专用频道](https://docs.microsoft.com/microsoftteams/private-channels)的消息。</span><span class="sxs-lookup"><span data-stu-id="5d171-132">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="5d171-133">保留策略目前不支持专用频道。</span><span class="sxs-lookup"><span data-stu-id="5d171-133">Currently, private channels aren't supported by retention policies.</span></span>
    
    <span data-ttu-id="5d171-134">默认情况下，[所有团队和所有用户](#a-policy-that-applies-to-entire-locations)会被选择，但你但是你可以通过选择[“**选择**”和“**排除**” 选项](#a-policy-with-specific-inclusions-or-exclusions)”来进行优化。</span><span class="sxs-lookup"><span data-stu-id="5d171-134">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="5d171-135">有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="5d171-135">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>
    
    <span data-ttu-id="5d171-136">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-136">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="5d171-137">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="5d171-137">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
5. <span data-ttu-id="5d171-138">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="5d171-138">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="5d171-139">有关 Teams 保留策略的详细信息，请参阅[Microsoft Teams 中的 保留策略](https://docs.microsoft.com/microsoftteams/retention-policies)来自 Teams 文档。</span><span class="sxs-lookup"><span data-stu-id="5d171-139">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="5d171-140">支持团队所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-140">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="5d171-141">Teams 不只是聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="5d171-141">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="5d171-142">如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应另外使用 **Office 365 组**位置来配置包括该 Microsoft 365 组的保留策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-142">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="5d171-143">此保留策略适用于组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-143">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="5d171-144">如果你有团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站**或 **OneDrive 帐户**位置的保留策略来保留和删除 Teams 中的文件：</span><span class="sxs-lookup"><span data-stu-id="5d171-144">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="5d171-145">聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="5d171-145">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="5d171-146">上传到频道的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="5d171-146">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="5d171-147">当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="5d171-147">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="5d171-148">应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="5d171-148">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="5d171-149">在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="5d171-149">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="5d171-150">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5d171-150">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>


### <a name="retention-policy-for-locations-other-than-teams"></a><span data-ttu-id="5d171-151">团队以外位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-151">Retention policy for locations other than Teams</span></span>

1. <span data-ttu-id="5d171-152">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="5d171-152">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="5d171-153">选择“**新保留策略**”来开始“创建保留策略向导”，并命名新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-153">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="5d171-154">在“**选择位置**”页面，切换打开或关闭除 Teams 位置之外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-154">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="5d171-155">对于每个位置，可将其保持为默认的“[将策略应用到整个位置](#a-policy-that-applies-to-entire-locations)”，或者“[指定所包含的和所排除的](#a-policy-with-specific-inclusions-or-exclusions)”。</span><span class="sxs-lookup"><span data-stu-id="5d171-155">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span> 
    
    <span data-ttu-id="5d171-156">特定于位置的信息：</span><span class="sxs-lookup"><span data-stu-id="5d171-156">Information specific to locations:</span></span>
    - [<span data-ttu-id="5d171-157">交换电子邮件和交换公共文件夹</span><span class="sxs-lookup"><span data-stu-id="5d171-157">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="5d171-158">SharePoint 网站和 OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="5d171-158">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="5d171-159">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="5d171-159">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="5d171-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5d171-160">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="5d171-161">有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="5d171-161">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>
    
    <span data-ttu-id="5d171-162">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-162">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="5d171-163">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="5d171-163">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="5d171-164">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="5d171-164">Complete the wizard to save your settings.</span></span>


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="5d171-165">Exchange 电子邮件和 Exchange 公用文件夹的配置信息</span><span class="sxs-lookup"><span data-stu-id="5d171-165">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="5d171-166">通过在邮箱级别应用保留设置，**Exchange 电子邮件**位置支持用户的电子邮件、日历和其他邮箱项的保留。</span><span class="sxs-lookup"><span data-stu-id="5d171-166">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="5d171-167">以下邮件项目包含在内：包含任何附件的邮件（包括草稿）、任务和日历项目（如果有结束日期）以及便签。</span><span class="sxs-lookup"><span data-stu-id="5d171-167">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="5d171-168">其中不包括不具备结束日期的任何联系人、任务和日历项目。</span><span class="sxs-lookup"><span data-stu-id="5d171-168">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="5d171-169">存储在邮箱中的其他项目（如 Skype 和 Teams 保存的消息）并不包含在其位置中。</span><span class="sxs-lookup"><span data-stu-id="5d171-169">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="5d171-170">这些项目有自己的保留位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-170">These items have their own retention locations.</span></span>

<span data-ttu-id="5d171-171">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-171">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="5d171-172">若要保留这些邮箱中的内容，请选择 **Office 365 组**的位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-172">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="5d171-173">**Exchange 公用文件夹** 位置将保留设置应用于所有公共文件夹，并且不能在文件夹或邮箱级别应用。</span><span class="sxs-lookup"><span data-stu-id="5d171-173">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="5d171-174">SharePoint 网站的配置信息和 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="5d171-174">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="5d171-175">选择 **SharePoint 网站**位置时，保留策略可以保留和删除在 SharePoint 通信网站的文件、未通过 Office 365 组连接的团队网站以及经典网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-175">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="5d171-176">因为此选项不支持通过 Office 365 组连接的团队网站，所以请改用“**Office 365 组**”位置，该位置适用于该组的邮箱、站点和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-176">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="5d171-177">尽管保留策略应用于站点级别，但只有文档具有应用于其的保留设置。</span><span class="sxs-lookup"><span data-stu-id="5d171-177">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="5d171-178">保留设置不适用于站点内包括库、列表和文件夹的组织结构。</span><span class="sxs-lookup"><span data-stu-id="5d171-178">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span> 

<span data-ttu-id="5d171-179">如果为 SharePoint 网站或 OneDrive 账户指定位置，无需网站访问权限，且在**编辑位置**页上指定 URL 时不会进行任何验证。</span><span class="sxs-lookup"><span data-stu-id="5d171-179">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="5d171-180">不过，必须将 SharePoint 网站编入索引，系统会检查你指定的网站是否在向导结束时存在。</span><span class="sxs-lookup"><span data-stu-id="5d171-180">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="5d171-181">如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-181">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="5d171-182">如果你看到此消息，请返回到向导，以更改 URL 或删除保留策略中的网站。</span><span class="sxs-lookup"><span data-stu-id="5d171-182">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="5d171-183">若要指定单个 OneDrive 帐户包含或排除的，URL 具有以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="5d171-183">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="5d171-184">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="5d171-184">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="5d171-185">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="5d171-185">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="5d171-186">Microsoft 365 组的配置信息</span><span class="sxs-lookup"><span data-stu-id="5d171-186">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="5d171-187">若要保留或删除 Microsoft 365 组（以前称为 Office 365 组）的内容，请使用 **Office 365 组**位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-187">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="5d171-188">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-188">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="5d171-189">此外，尽管 **Exchange 电子邮件**位置最初允许你指定包括或排除组邮箱，但在尝试保存保留策略时，你将收到一条错误消息，表明“RemoteGroupMailbox”不是有效的 Exchange 位置选项。</span><span class="sxs-lookup"><span data-stu-id="5d171-189">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="5d171-190">如果在创建组时选择了某个团队网站或之后向该组添加了一个团队网站，则 Microsoft 365 组应用的保留策略将包括组邮箱和团队网站。</span><span class="sxs-lookup"><span data-stu-id="5d171-190">A retention policy applied to a Microsoft 365 group includes the group mailbox and teams site, if a teams site was selected at the time the group was created or later added to the group.</span></span> <span data-ttu-id="5d171-191">存储在团队网站中的文件与此位置有关，但 Teams 聊天或 Teams 频道与此位置无关，它们拥有自己的保留策略位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-191">Files stored in the teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="5d171-192">Skype for Business 的配置信息</span><span class="sxs-lookup"><span data-stu-id="5d171-192">Configuration information for Skype for Business</span></span>

<span data-ttu-id="5d171-193">与 Exchange 电子邮件不同，将 Skype 位置的状态切换为“开”并不能添加所有用户，但启用相应位置后，就必须手动选择要保留哪些用户的对话：</span><span class="sxs-lookup"><span data-stu-id="5d171-193">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![选择用于保留策略的 Skype 位置](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="5d171-195">当你选择“**选择用户**”时，可通过选择“**全选**”框来快速包含所有用户。</span><span class="sxs-lookup"><span data-stu-id="5d171-195">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="5d171-196">但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-196">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="5d171-197">因此，如果通过选择“**全选**”框来包含 1000 名用户，则与手动选择要包含的 1000 名用户相同，这是 Skype for Business 所支持的最大上限。</span><span class="sxs-lookup"><span data-stu-id="5d171-197">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="5d171-198">请注意，Outlook 中的“**对话历史记录**”文件夹是一个与 Skype 存档没有任何关系的功能。</span><span class="sxs-lookup"><span data-stu-id="5d171-198">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="5d171-199">最终用户可以关闭“**对话历史记录**”，但是 Skype 的存档功能是将 Skype 对话的副本存储到隐藏的文件夹。电子数据展示可以访问该文件夹，但用户不可以。</span><span class="sxs-lookup"><span data-stu-id="5d171-199">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="5d171-200">保留和删除内容的设置</span><span class="sxs-lookup"><span data-stu-id="5d171-200">Settings for retaining and deleting content</span></span>

<span data-ttu-id="5d171-201">通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="5d171-201">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="5d171-202">仅保留</span><span class="sxs-lookup"><span data-stu-id="5d171-202">Retain-only</span></span>
    
    <span data-ttu-id="5d171-203">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：不执行任何操作**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-203">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="5d171-204">或者，选择“**永久保留项目**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-204">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="5d171-205">保留后删除</span><span class="sxs-lookup"><span data-stu-id="5d171-205">Retain and then delete</span></span>
    
    <span data-ttu-id="5d171-206">对于此配置，请选择“**将项目保留至特定时间段**”和“**保留期结束：自动删除项目**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-206">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="5d171-207">仅删除</span><span class="sxs-lookup"><span data-stu-id="5d171-207">Delete-only</span></span>
    
    <span data-ttu-id="5d171-208">对于此配置，请选择“**仅在达到特定年龄时删除项目”**。</span><span class="sxs-lookup"><span data-stu-id="5d171-208">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="5d171-209">将内容保留一段特定时间</span><span class="sxs-lookup"><span data-stu-id="5d171-209">Retaining content for a specific period of time</span></span>

<span data-ttu-id="5d171-210">配置保留策略时，可选择将内容保留至特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="5d171-210">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="5d171-211">或者，永久保留项目。</span><span class="sxs-lookup"><span data-stu-id="5d171-211">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="5d171-212">配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="5d171-212">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="5d171-213">保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。</span><span class="sxs-lookup"><span data-stu-id="5d171-213">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span> 

<span data-ttu-id="5d171-214">对于保留期的开始，你还可以选择内容创建的时间，或者上次修改内容的时间（仅支持文件和 SharePoint、OneDrive 和 Office 365 位置）。</span><span class="sxs-lookup"><span data-stu-id="5d171-214">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Office 365 locations, when the content was last modified.</span></span>

<span data-ttu-id="5d171-215">示例：</span><span class="sxs-lookup"><span data-stu-id="5d171-215">Examples:</span></span>
  
- <span data-ttu-id="5d171-216">SharePoint：如果希望将某个网站集中的项目自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留 1 年。</span><span class="sxs-lookup"><span data-stu-id="5d171-216">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="5d171-217">如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留 7 年。</span><span class="sxs-lookup"><span data-stu-id="5d171-217">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="5d171-218">Exchange：如果想将邮箱中的项目保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。</span><span class="sxs-lookup"><span data-stu-id="5d171-218">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="5d171-219">对于 Exchange 项目，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。</span><span class="sxs-lookup"><span data-stu-id="5d171-219">For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="5d171-220">根据最后一次修改的时间来保留项目这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。</span><span class="sxs-lookup"><span data-stu-id="5d171-220">Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="5d171-221">保留期结束后，选择是否要永久删除内容：</span><span class="sxs-lookup"><span data-stu-id="5d171-221">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="5d171-223">删除超过特定年限的内容</span><span class="sxs-lookup"><span data-stu-id="5d171-223">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="5d171-224">保留策略既可以先保留再删除项目，也可以不保留即删除旧项目。</span><span class="sxs-lookup"><span data-stu-id="5d171-224">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>
  
<span data-ttu-id="5d171-225">在这两种情况下，如果保留策略删除项目，请务必了解为保留策略指定的时间期限是从项目创建或修改时开始计算，而不是从策略分配时开始计算。</span><span class="sxs-lookup"><span data-stu-id="5d171-225">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="5d171-226">因此首次分配保留策略前，尤其是当该策略会删除项目时，请先考虑现有内容的年龄，以及该策略对该内容有何影响。</span><span class="sxs-lookup"><span data-stu-id="5d171-226">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="5d171-227">在分配策略之前，你还需要与用户就新的策略进行沟通，以便其有时间评估可能的影响。</span><span class="sxs-lookup"><span data-stu-id="5d171-227">You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="5d171-228">应用于位置整体的策略</span><span class="sxs-lookup"><span data-stu-id="5d171-228">A policy that applies to entire locations</span></span>

<span data-ttu-id="5d171-229">选择位置时（Skype for Business 除外），当位置的状态是“**开启**”时，默认设置是“**全部**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-229">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>
  
<span data-ttu-id="5d171-230">如果将保留策略应用于整个位置的任意组合，则不会限制该策略可以包含的收件人、网站、帐户和组等数量。</span><span class="sxs-lookup"><span data-stu-id="5d171-230">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups etc that the policy can include.</span></span> 

<span data-ttu-id="5d171-231">例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和收件人的数量有多少，都会对其应用策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-231">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many.</span></span> <span data-ttu-id="5d171-232">并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-232">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="5d171-233">包含或排除特定位置、用户或组的策略</span><span class="sxs-lookup"><span data-stu-id="5d171-233">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="5d171-234">你还可以将保留策略应用于特定用户、特定 Microsoft 365 组或特定网站。</span><span class="sxs-lookup"><span data-stu-id="5d171-234">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="5d171-235">若要执行此操作，请确保该位置的“**状态**”为“**开启**”，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。</span><span class="sxs-lookup"><span data-stu-id="5d171-235">To do so, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="5d171-236">但是，如果保留策略包含或排除的特定对象超过 1,000 个，则使用此配置会有一些限制：</span><span class="sxs-lookup"><span data-stu-id="5d171-236">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific objects:</span></span>
  
- <span data-ttu-id="5d171-237">保留策略的最大数量：</span><span class="sxs-lookup"><span data-stu-id="5d171-237">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="5d171-238">1,000 个邮箱</span><span class="sxs-lookup"><span data-stu-id="5d171-238">1,000 mailboxes</span></span>
    - <span data-ttu-id="5d171-239">1,000 个 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="5d171-239">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="5d171-240">1000 个用户的 Teams 私人聊天</span><span class="sxs-lookup"><span data-stu-id="5d171-240">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="5d171-241">100 个网站（OneDrive 或 SharePoint）</span><span class="sxs-lookup"><span data-stu-id="5d171-241">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="5d171-242">租户支持的最大策略数：10,000。</span><span class="sxs-lookup"><span data-stu-id="5d171-242">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="5d171-243">这些项目包括保留策略、保留标签策略和自动应用保留策略。</span><span class="sxs-lookup"><span data-stu-id="5d171-243">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="5d171-244">如果你的保留策略可能受到这些限制，请选择适用于整个位置的配置选项。</span><span class="sxs-lookup"><span data-stu-id="5d171-244">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations.</span></span>

> [!WARNING]
> <span data-ttu-id="5d171-245">如果你配置了包含项，然后删除了最后一项，则配置会将位置的设置还原为“**所有**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-245">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="5d171-246">保存策略之前，请确保这是你期望的配置。</span><span class="sxs-lookup"><span data-stu-id="5d171-246">Make sure this is the configuration that you intend before you save the policy.</span></span>
> 
> <span data-ttu-id="5d171-247">例如，如果你指定了一个 要在根据配置删除数据的保留策略中包含的 SharePoint 网站，然后删除了这个网站，那么默认情况下，所有 SharePoint 网站都将受到永久删除数据的保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="5d171-247">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="5d171-248">这同样适用于针对 Exchange 收件人、OneDrive 帐户和 Teams 聊天用户等进行包含设置。</span><span class="sxs-lookup"><span data-stu-id="5d171-248">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
> 
> <span data-ttu-id="5d171-249">在这种情况下，如果不希望“**所有**”这一位置设置受制于保留策略，请关闭位置。</span><span class="sxs-lookup"><span data-stu-id="5d171-249">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="5d171-250">或者，指定将不受该策略约束的排除项。</span><span class="sxs-lookup"><span data-stu-id="5d171-250">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="5d171-251">更新保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-251">Updating retention policies</span></span>

<span data-ttu-id="5d171-252">如果你编辑保留策略，并且项目已遵循保留策略中的原始设置，则除了新识别的项目之外，更新后的设置将自动应用于此项目。</span><span class="sxs-lookup"><span data-stu-id="5d171-252">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="5d171-253">此更新通常非常快，但可能需要数天。</span><span class="sxs-lookup"><span data-stu-id="5d171-253">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="5d171-254">完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。</span><span class="sxs-lookup"><span data-stu-id="5d171-254">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="5d171-255">使用 PowerShell 锁定保留策略</span><span class="sxs-lookup"><span data-stu-id="5d171-255">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="5d171-256">如果需要使用“[保留锁定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)”来满足法规要求，则必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5d171-256">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span> <span data-ttu-id="5d171-257">由于管理员无法在应用保留锁定后禁用或删除保留策略，因此 UI 中不提供启用此功能，以防意外配置。</span><span class="sxs-lookup"><span data-stu-id="5d171-257">Because administrators can't disable or delete a retention policy after a preservation lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="5d171-258">具有任何配置的所有保留策略均支持“保留锁定”。</span><span class="sxs-lookup"><span data-stu-id="5d171-258">All retention policies with any configuration support Preservation Lock.</span></span> <span data-ttu-id="5d171-259">但是，在使用以下 PowerShell 命令时，你会注意到 **Workload** 参数始终显示 **Exchange、SharePoint、OneDriveForBusines、Skype、ModernGroup**，而不是策略中配置的实际工作负载。</span><span class="sxs-lookup"><span data-stu-id="5d171-259">However, when you use the PowerShell commands that follow, you'll notice that the **Workload** parameter always displays **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** rather than reflect the actual workloads configured in the policy.</span></span> <span data-ttu-id="5d171-260">这只是显示问题。</span><span class="sxs-lookup"><span data-stu-id="5d171-260">This is a display issue only.</span></span>

1. <span data-ttu-id="5d171-261">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5d171-261">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="5d171-262">运行 [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy)，列出保留策略并查找要锁定的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="5d171-262">List your retention policies and find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="5d171-263">例如：</span><span class="sxs-lookup"><span data-stu-id="5d171-263">For example:</span></span>
    
   ![PowerShell 中的保留策略列表](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="5d171-265">若要对保留策略应用保留锁定，请运行带有保留策略名称的 [Set-RetentionCompliancePolicy]( ) cmdlet，并将 *RestrictiveRetention* 参数设置为 true：</span><span class="sxs-lookup"><span data-stu-id="5d171-265">To place a Preservation Lock on a retention policy, run the [Set-RetentionCompliancePolicy]( ) cmdlet with the name of the retention policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="5d171-266">例如：</span><span class="sxs-lookup"><span data-stu-id="5d171-266">For example:</span></span>
    
    ![PowerShell 中的 RestrictiveRetention 参数](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="5d171-268">出现提示时，请阅读并通过输入**Y**确认这个配置随附的限制：</span><span class="sxs-lookup"><span data-stu-id="5d171-268">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![用于确认你要在 PowerShell 中锁定保留策略的提示](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="5d171-270">现在，为保留策略提供了“保留锁定”功能。</span><span class="sxs-lookup"><span data-stu-id="5d171-270">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="5d171-271">若要确认，请再次运行 `Get-RetentionCompliancePolicy`，但指定保留策略名称并显示策略参数：</span><span class="sxs-lookup"><span data-stu-id="5d171-271">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the retention policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="5d171-272">应看到 **RestrictiveRetention** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="5d171-272">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="5d171-273">例如：</span><span class="sxs-lookup"><span data-stu-id="5d171-273">For example:</span></span>

![已在 PowerShell 中显示所有参数的锁定策略](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

