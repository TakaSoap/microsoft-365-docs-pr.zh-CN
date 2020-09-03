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
description: 使用保留策略，可主动决定是保留内容还是删除内容，亦或是先保留再删除内容；可将一个策略应用于整个组织，或应用于特定位置或用户；并能将策略应用于所有内容，或应用于满足特定条件的内容。
ms.openlocfilehash: 5b0b81d18afad9f0f9cba6ec24e157ad8f96e4ef
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315841"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="93ced-103">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-103">Create and configure retention policies</span></span>

><span data-ttu-id="93ced-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="93ced-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="93ced-105">使用保留策略来主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-105">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="93ced-106">透过将相同的保留设置依照位置如网站或信箱层级的内容进行指派，保留策略可让你工作的更有效率。</span><span class="sxs-lookup"><span data-stu-id="93ced-106">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="93ced-107">如果你不确定是使用保留策略还是保留标签，请参阅[保留策略和保留标签](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="93ced-107">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="93ced-108">有关保留策略的保留工作方式的详细信息，请参阅[了解保留策略](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="93ced-108">For more information about retention policies and how retention works, see [Learn about retention](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="93ced-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="93ced-109">Before you begin</span></span>

<span data-ttu-id="93ced-110">组织的全局管理员具有创建和编辑保留策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="93ced-110">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="93ced-111">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="93ced-111">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="93ced-112">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-112">Create and configure a retention policy</span></span>

<span data-ttu-id="93ced-113">虽然保留策略可支持多个位置，但你无法创建包含所有受支持位置的单个保留策略：</span><span class="sxs-lookup"><span data-stu-id="93ced-113">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>
- <span data-ttu-id="93ced-114">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="93ced-114">Exchange email</span></span>
- <span data-ttu-id="93ced-115">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="93ced-115">SharePoint site</span></span>
- <span data-ttu-id="93ced-116">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="93ced-116">OneDrive accounts</span></span>
- <span data-ttu-id="93ced-117">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="93ced-117">Microsoft 365 groups</span></span>
- <span data-ttu-id="93ced-118">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="93ced-118">Skype for Business</span></span>
- <span data-ttu-id="93ced-119">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="93ced-119">Exchange public folders</span></span>
- <span data-ttu-id="93ced-120">Teams 通道消息</span><span class="sxs-lookup"><span data-stu-id="93ced-120">Teams channel messages</span></span>
- <span data-ttu-id="93ced-121">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="93ced-121">Teams chats</span></span>

<span data-ttu-id="93ced-122">当您在创建保留策略时选择其中一个 Teams 位置时，其他位置将被自动排除。</span><span class="sxs-lookup"><span data-stu-id="93ced-122">When you select either of the Teams locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="93ced-123">因此，请依照你是否需要包含 Teams 地点来取决于要遵循的指示:</span><span class="sxs-lookup"><span data-stu-id="93ced-123">Therefore, the instructions to follow depend on whether you need to include the Teams locations:</span></span>

- [<span data-ttu-id="93ced-124">有关 Teams 位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="93ced-124">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="93ced-125">有关 Teams 以外位置的保留策略的说明</span><span class="sxs-lookup"><span data-stu-id="93ced-125">Instructions for a retention policy for locations other than Teams</span></span>](#retention-policy-for-locations-other-than-teams)

<span data-ttu-id="93ced-126">如果你有多个保留策略，但同时你又有使用保留标签，请参阅[保留原则或优先原则？](retention.md#the-principles-of-retention-or-what-takes-precedence)了解多个保留设置应用于同一内容时的结果。</span><span class="sxs-lookup"><span data-stu-id="93ced-126">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="93ced-127">Teams 位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-127">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="93ced-128">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="93ced-128">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="93ced-129">选择**新保留策略**创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-129">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="93ced-130">有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="93ced-130">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="93ced-131">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-131">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="93ced-132">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="93ced-132">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="93ced-133">请勿选择 **使用高级保留设置** ，因为这并不支持 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-133">Do not select **Use advanced retention settings** because this option isn't supported for Teams locations.</span></span> 

4. <span data-ttu-id="93ced-134">有关**选择位置**的页面，请选择**让我选择特定位置**。</span><span class="sxs-lookup"><span data-stu-id="93ced-134">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="93ced-135">然后切换 Teams 的一个或两个位置： **Teams 频道消息** 和 **Teams 聊天**。</span><span class="sxs-lookup"><span data-stu-id="93ced-135">Then toggle on one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>
     
    <span data-ttu-id="93ced-136">请注意，对于**Teams 频道消息**，将包括来自标准频道的消息，但不包括来自[专用频道](https://docs.microsoft.com/microsoftteams/private-channels)的消息。</span><span class="sxs-lookup"><span data-stu-id="93ced-136">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="93ced-137">保留策略目前不支持专用频道。</span><span class="sxs-lookup"><span data-stu-id="93ced-137">Currently, private channels aren't supported by retention policies.</span></span>
    
    <span data-ttu-id="93ced-138">默认情况下，所有团队都处于选中状态，但你可以通过指定要纳入的团队或团队来优化此设置。</span><span class="sxs-lookup"><span data-stu-id="93ced-138">By default, all teams are selected, but you can refine this by specifying teams to be included, or teams to be excluded.</span></span>

5. <span data-ttu-id="93ced-139">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="93ced-139">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="93ced-140">有关 Teams 保留策略的详细信息，请参阅[Microsoft Teams 中的 保留策略](https://docs.microsoft.com/microsoftteams/retention-policies)来自 Teams 文档。</span><span class="sxs-lookup"><span data-stu-id="93ced-140">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="93ced-141">支持团队所需的其他保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-141">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="93ced-142">Teams 不只是聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="93ced-142">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="93ced-143">如果你有从 Microsoft 365 组（以前称为 Office 365 组）创建的团队，则应另外使用 **Office 365 组**位置来配置包括该 Microsoft 365 组的保留策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-143">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="93ced-144">此保留策略适用于组的邮箱、网站和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-144">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="93ced-145">如果你有团队网站未连接到 Microsoft 365 组，则需要一个包括 **SharePoint 网站**或 **OneDrive 帐户**位置的保留策略来保留和删除 Teams 中的文件：</span><span class="sxs-lookup"><span data-stu-id="93ced-145">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="93ced-146">聊天中共享的文件存储在共享文件的用户的 OneDrive 帐户中。</span><span class="sxs-lookup"><span data-stu-id="93ced-146">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="93ced-147">上传到频道的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="93ced-147">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="93ced-148">当特定团队未连接到 Microsoft 365 组时，可以将保留策略应用于该特定团队的文件，方法是选择该团队的 SharePoint 网站以及该团队中用户的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="93ced-148">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="93ced-149">应用于 Microsoft 365 组、SharePoint 网站或 OneDrive 帐户的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="93ced-149">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="93ced-150">在这种情况下，该文件仍显示在 Teams 消息中，但当用户选择该文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="93ced-150">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="93ced-151">此行为并非特定于保留策略，用户从 SharePoint 或 OneDrive 中手动删除文件时，也可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="93ced-151">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>


### <a name="retention-policy-for-locations-other-than-teams"></a><span data-ttu-id="93ced-152">团队以外位置的保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-152">Retention policy for locations other than Teams</span></span>

1. <span data-ttu-id="93ced-153">从 [Microsoft 365 合规中心](https://compliance.microsoft.com/)中，选择**策略** > **保留**。</span><span class="sxs-lookup"><span data-stu-id="93ced-153">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="93ced-154">选择**新保留策略**创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-154">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="93ced-155">有关**保留内容、删除内容，还是同时删除**向导的页面，请指定保留和删除内容的配置选项。</span><span class="sxs-lookup"><span data-stu-id="93ced-155">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="93ced-156">你可以创建一个保留策略，指明仅保留而不删除内容、将内容保留指定的时间段后删除，或者仅在指定的时间段后删除内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-156">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="93ced-157">有关详细信息，请参阅本页上的[保留和删除内容的设置](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="93ced-157">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="93ced-158">然后，确定应将保留策略应用于所有内容还是满足特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-158">Then, decide whether the retention policy should apply to all content, or content that meets specific conditions.</span></span> <span data-ttu-id="93ced-159">有关这些高级保留设置的详细信息，请参阅本页上的[用于识别满足特定条件的内容的高级设置](#advanced-settings-to-identify-content-that-meets-specific-conditions)。</span><span class="sxs-lookup"><span data-stu-id="93ced-159">For more information about these advanced retention settings, see [Advanced settings to identify content that meets specific conditions](#advanced-settings-to-identify-content-that-meets-specific-conditions) on this page.</span></span> 

4. <span data-ttu-id="93ced-160">对于“**选择位置**”页面，选择应将保留策略应用到组织中的所有受支持位置，还是想要指定位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-160">For the **Choose locations** page, select whether the retention policy should apply to all supported locations across your organization, or you want to specify the locations.</span></span> <span data-ttu-id="93ced-161">如果选择特定位置，还可以指定包括和排除项。</span><span class="sxs-lookup"><span data-stu-id="93ced-161">If you choose specific locations, you can also specify includes and excludes.</span></span> 
    
    <span data-ttu-id="93ced-162">有关在组织或特定位置的保留策略之间进行选择的详细信息，请参阅本页上的[将保留策略应用于整个组织或特定位置](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="93ced-162">For more information about choosing between a retention policy for the organization or for specific locations, see [Applying a retention policy to an entire organization or specific locations](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) on this page.</span></span>
    
    <span data-ttu-id="93ced-163">特定于位置的信息：</span><span class="sxs-lookup"><span data-stu-id="93ced-163">Information specific to locations:</span></span>
    - [<span data-ttu-id="93ced-164">交换电子邮件和交换公共文件夹</span><span class="sxs-lookup"><span data-stu-id="93ced-164">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="93ced-165">SharePoint 网站和 OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="93ced-165">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="93ced-166">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="93ced-166">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="93ced-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="93ced-167">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

5. <span data-ttu-id="93ced-168">完成向导以保存设置。</span><span class="sxs-lookup"><span data-stu-id="93ced-168">Complete the wizard to save your settings.</span></span>


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="93ced-169">Exchange 电子邮件和 Exchange 公用文件夹的配置信息</span><span class="sxs-lookup"><span data-stu-id="93ced-169">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="93ced-170">通过在邮箱级别应用保留设置，**Exchange 电子邮件**位置支持用户的电子邮件、日历和其他邮箱项的保留。</span><span class="sxs-lookup"><span data-stu-id="93ced-170">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="93ced-171">以下邮件项目包含在内：包含任何附件的邮件（包括草稿）、任务和日历项目（如果有结束日期）以及便签。</span><span class="sxs-lookup"><span data-stu-id="93ced-171">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="93ced-172">其中不包括不具备结束日期的任何联系人、任务和日历项目。</span><span class="sxs-lookup"><span data-stu-id="93ced-172">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="93ced-173">存储在邮箱中的其他项目（如 Skype 和 Teams 保存的消息）并不包含在其位置中。</span><span class="sxs-lookup"><span data-stu-id="93ced-173">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="93ced-174">这些项目有自己的保留位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-174">These items have their own retention locations.</span></span>

<span data-ttu-id="93ced-175">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-175">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="93ced-176">若要保留这些邮箱中的内容，请选择 **Office 365 组**的位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-176">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="93ced-177">**Exchange 公用文件夹** 位置将保留设置应用于所有公共文件夹，并且不能在文件夹或邮箱级别应用。</span><span class="sxs-lookup"><span data-stu-id="93ced-177">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="93ced-178">SharePoint 网站的配置信息和 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="93ced-178">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="93ced-179">选择 **SharePoint 网站**位置时，保留策略可以保留和删除在 SharePoint 通信网站的文件、未通过 Office 365 组连接的团队网站以及经典网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-179">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="93ced-180">因为此选项不支持通过 Office 365 组连接的团队网站，所以请改用“**Office 365 组**”位置，该位置适用于该组的邮箱、站点和文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-180">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="93ced-181">尽管保留策略应用于站点级别，但只有文档具有应用于其的保留设置。</span><span class="sxs-lookup"><span data-stu-id="93ced-181">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="93ced-182">保留设置不适用于站点内包括库、列表和文件夹的组织结构。</span><span class="sxs-lookup"><span data-stu-id="93ced-182">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span> 

<span data-ttu-id="93ced-183">如果为 SharePoint 网站或 OneDrive 账户指定位置，无需网站访问权限，且在**编辑位置**页上指定 URL 时不会进行任何验证。</span><span class="sxs-lookup"><span data-stu-id="93ced-183">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="93ced-184">不过，必须将 SharePoint 网站编入索引，系统会检查你指定的网站是否在向导结束时存在。</span><span class="sxs-lookup"><span data-stu-id="93ced-184">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="93ced-185">如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-185">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="93ced-186">如果你看到此消息，请返回到向导，以更改 URL 或删除保留策略中的网站。</span><span class="sxs-lookup"><span data-stu-id="93ced-186">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="93ced-187">若要指定单个 OneDrive 帐户包含或排除的，URL 具有以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="93ced-187">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="93ced-188">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="93ced-188">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="93ced-189">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="93ced-189">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="93ced-190">Microsoft 365 组的配置信息</span><span class="sxs-lookup"><span data-stu-id="93ced-190">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="93ced-191">若要保留或删除 Microsoft 365 组（以前称为 Office 365 组）的内容，请使用 **Office 365 组**位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-191">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="93ced-192">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-192">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="93ced-193">此外，尽管 **Exchange 电子邮件**位置最初允许你指定包括或排除组邮箱，但在尝试保存保留策略时，你将收到一条错误消息，表明“RemoteGroupMailbox”不是有效的 Exchange 位置选项。</span><span class="sxs-lookup"><span data-stu-id="93ced-193">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="93ced-194">如果在创建组时选择了某个团队网站或之后向该组添加了一个团队网站，则 Microsoft 365 组应用的保留策略将包括组邮箱和团队网站。</span><span class="sxs-lookup"><span data-stu-id="93ced-194">A retention policy applied to a Microsoft 365 group includes the group mailbox and teams site, if a teams site was selected at the time the group was created or later added to the group.</span></span> <span data-ttu-id="93ced-195">存储在团队网站中的文件与此位置有关，但 Teams 聊天或 Teams 频道与此位置无关，它们拥有自己的保留策略位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-195">Files stored in the teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="93ced-196">Skype for Business 的配置信息</span><span class="sxs-lookup"><span data-stu-id="93ced-196">Configuration information for Skype for Business</span></span>

<span data-ttu-id="93ced-197">与 Exchange 电子邮件不同，将 Skype 位置的状态切换为“开”并不能添加所有用户，但启用相应位置后，就可以手动选择要保留哪些用户的对话：</span><span class="sxs-lookup"><span data-stu-id="93ced-197">Unlike Exchange email, you can't toggle the status of the Skype location on to include all users, but when you turn on that location, you then manually choose the users whose conversations you want to retain:</span></span>

![选择用于保留策略的 Skype 位置](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="93ced-199">选择“选择用户”时，选择列标题中的“名称”\*\*\*\* 框可快速包含所有用户\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="93ced-199">When you select **Choose users**, you can quickly include all users by selecting the **Name** box in the column header.</span></span> <span data-ttu-id="93ced-200">但是，请务必了解每个用户在策略中都被算作一个特定的包含内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-200">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="93ced-201">因此，当包括的用户超过 1,000 位时，会应用上一部分中所述的限制。</span><span class="sxs-lookup"><span data-stu-id="93ced-201">Therefore, if you include over 1,000 users, the limits noted in the previous section apply.</span></span> <span data-ttu-id="93ced-202">这里所说的选择所有 Skype 用户不同于组织范围的策略在默认情况下包含所有 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="93ced-202">Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![用于选择 Skype 用户的页](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="93ced-p121">请注意，Outlook 中的“对话历史记录”\*\*\*\* 文件夹是一项与 Skype 存档无关的功能。“对话历史记录”\*\*\*\* 可以由最终用户禁用，但 Skype 存档是通过将 Skype 对话副本存储在用户无法访问但电子数据展示可访问的隐藏文件夹中而完成。</span><span class="sxs-lookup"><span data-stu-id="93ced-p121">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>


## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="93ced-206">保留和删除内容的设置</span><span class="sxs-lookup"><span data-stu-id="93ced-206">Settings for retaining and deleting content</span></span>

<span data-ttu-id="93ced-207">通过在保留策略中选择保留和删除内容的设置，保留策略将在指定的时间段内具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="93ced-207">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="93ced-208">仅保留</span><span class="sxs-lookup"><span data-stu-id="93ced-208">Retain-only</span></span>
- <span data-ttu-id="93ced-209">保留后删除</span><span class="sxs-lookup"><span data-stu-id="93ced-209">Retain and then delete</span></span>
- <span data-ttu-id="93ced-210">仅删除</span><span class="sxs-lookup"><span data-stu-id="93ced-210">Delete-only</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="93ced-211">将内容保留一段特定时间</span><span class="sxs-lookup"><span data-stu-id="93ced-211">Retaining content for a specific period of time</span></span>

<span data-ttu-id="93ced-212">配置保留策略时，可选择无限期地保留内容，也可将内容保留特定天数、月数或年限。</span><span class="sxs-lookup"><span data-stu-id="93ced-212">When you configure a retention policy, you choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="93ced-213">内容的保留期限是从内容创建的时间开始计算，而不是从应用保留策略的时间开始计算。</span><span class="sxs-lookup"><span data-stu-id="93ced-213">The duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied.</span></span> <span data-ttu-id="93ced-214">可以选择根据内容创建的时间或（针对 OneDrive 和 SharePoint）最后一次修改内容的时间来计算保留期限。</span><span class="sxs-lookup"><span data-stu-id="93ced-214">You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>

<span data-ttu-id="93ced-215">示例：</span><span class="sxs-lookup"><span data-stu-id="93ced-215">Examples:</span></span>
  
- <span data-ttu-id="93ced-216">SharePoint：如果希望将某个网站集中的内容自上次修改以来保留七年，并且该网站集中的某个文档在六年内未进行修改，则该文档在不修改的情况下将仅再保留 1 年。</span><span class="sxs-lookup"><span data-stu-id="93ced-216">SharePoint: If you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="93ced-217">如果再次对该文档进行编辑，则会根据最新修改日期计算文档期限，并将再保留 7 年。</span><span class="sxs-lookup"><span data-stu-id="93ced-217">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="93ced-218">Exchange：如果想将邮箱中的内容保留七年，而有封邮件是六年前发送的，则该邮件将只再保留一年。</span><span class="sxs-lookup"><span data-stu-id="93ced-218">Exchange: If you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="93ced-219">对于 Exchange 内容，期限基于传入电子邮件的接收日期或传出电子邮件的发送日期。</span><span class="sxs-lookup"><span data-stu-id="93ced-219">For Exchange content, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="93ced-220">根据最后一次修改的时间来保留内容这一方式只适用于 OneDrive 和 SharePoint 中的网站内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-220">Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="93ced-221">保留期结束后，选择是否要永久删除内容：</span><span class="sxs-lookup"><span data-stu-id="93ced-221">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![用于设置内容保留的页](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="93ced-223">删除超过特定年限的内容</span><span class="sxs-lookup"><span data-stu-id="93ced-223">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="93ced-224">保留策略既可以先保留再删除内容，也可以删除旧内容，而不保留它。</span><span class="sxs-lookup"><span data-stu-id="93ced-224">A retention policy can both retain and then delete content, or delete old content without retaining it.</span></span>
  
<span data-ttu-id="93ced-225">如果保留策略删除内容，请务必了解为保留策略指定的时间期限是从文件创建或修改时开始计算，而不是从策略分配时开始计算。</span><span class="sxs-lookup"><span data-stu-id="93ced-225">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![内容删除设置](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="93ced-227">例如，假设创建了一个保留策略 - 该策略会在三年后删除内容，然后将该策略分配到所有 OneDrive 帐户，这些帐户中含有许多四五年前创建的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-227">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago.</span></span> <span data-ttu-id="93ced-228">在这种情况下，第一次分配保留策略后将会有许多内容被删除。</span><span class="sxs-lookup"><span data-stu-id="93ced-228">In this case, a lot of content will be deleted soon after assigning the retention policy for the first time.</span></span> <span data-ttu-id="93ced-229">为此，请务必了解删除内容的保留策略会对内容造成重大影响。</span><span class="sxs-lookup"><span data-stu-id="93ced-229">For this reason, it's important to understand that a retention policy that deletes content can have a considerable impact on your content.</span></span> 
  
<span data-ttu-id="93ced-p126">因此，首次将保留策略分配到网站集之前，应先考虑现有内容的年限，以及保留策略可能会对此内容产生的影响。我们还建议在分配策略前向用户传达新策略，让用户有时间评估策略可能会产生的影响。请注意，在创建保留策略前检查策略设置时会看到以下警告。</span><span class="sxs-lookup"><span data-stu-id="93ced-p126">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![内容删除警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a><span data-ttu-id="93ced-234">用于识别满足特定条件的内容的高级设置</span><span class="sxs-lookup"><span data-stu-id="93ced-234">Advanced settings to identify content that meets specific conditions</span></span>

<span data-ttu-id="93ced-235">保留策略可应用于其中所含位置上的全部内容，你也可以选择将保留策略只应用于包含特定关键字或[特定类型敏感信息](what-the-sensitive-information-types-look-for.md)的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-235">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![高级保留选项](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a><span data-ttu-id="93ced-237">识别包含特定关键字的内容</span><span class="sxs-lookup"><span data-stu-id="93ced-237">Identify content that contains specific keywords</span></span>

<span data-ttu-id="93ced-238">可以只对满足特定条件的内容应用保留策略，然后只对这些内容执行保留操作。</span><span class="sxs-lookup"><span data-stu-id="93ced-238">You can apply a retention policy only to content that meets specific conditions, and then take retention actions on just that content.</span></span> <span data-ttu-id="93ced-239">可用的条件支持将保留策略应用于包含特定字词或短语的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-239">The conditions available support applying a retention policy to content that contains specific words or phrases.</span></span> <span data-ttu-id="93ced-240">你可以使用 AND、OR 和 NOT 等搜索运算符优化查询。</span><span class="sxs-lookup"><span data-stu-id="93ced-240">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="93ced-241">有关这些运算符的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="93ced-241">For more information about these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="93ced-242">基于查询的保留策略使用搜索索引来标识内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-242">Query-based retention uses the search index to identify content.</span></span>
  
![查询编辑器](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a><span data-ttu-id="93ced-244">识别包含敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="93ced-244">Identify content that contains sensitive information</span></span>

<span data-ttu-id="93ced-p128">此外，还可以将保留策略只应用于包含[特定类型敏感信息](what-the-sensitive-information-types-look-for.md)的内容。例如，可选择将唯一保留要求只应用于包含个人信息（如纳税人标识号、身份证号或护照号）的内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-p128">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personal information, such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![用于选择敏感信息类型的页](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="93ced-248">注意：</span><span class="sxs-lookup"><span data-stu-id="93ced-248">Notes:</span></span>
  
- <span data-ttu-id="93ced-249">敏感信息的高级保留设置不适用于 Exchange 公用文件夹或 Skype for Business，因为这些位置不支持敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="93ced-249">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="93ced-250">Exchange Online 使用邮件流规则（也称为传输规则）来识别敏感信息，因此这种方式仅适用于传输过程中的邮件，而不适用于已存储在邮箱中的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="93ced-250">Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit—not on all items already stored in a mailbox.</span></span> <span data-ttu-id="93ced-251">对于 Exchange Online，这意味着保留策略可以识别敏感信息，并且只对邮箱应用策略**之后**收到的邮件执行保留操作。</span><span class="sxs-lookup"><span data-stu-id="93ced-251">For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox.</span></span> <span data-ttu-id="93ced-252">上一部分所述的基于查询的保留不受此限制，因为它是通过使用搜索索引来识别内容的。</span><span class="sxs-lookup"><span data-stu-id="93ced-252">Query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="93ced-253">将保留策略应用于整个组织或特定位置</span><span class="sxs-lookup"><span data-stu-id="93ced-253">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="93ced-254">可以将保留策略轻松地应用于整个组织、位置整体，或只应用于特定位置或用户。</span><span class="sxs-lookup"><span data-stu-id="93ced-254">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="93ced-255">组织范围策略</span><span class="sxs-lookup"><span data-stu-id="93ced-255">Org-wide policy</span></span>

<span data-ttu-id="93ced-256">保留策略的最强大功能之一是，它可以应用于 Microsoft 365 中的所有位置，包括：</span><span class="sxs-lookup"><span data-stu-id="93ced-256">One of the most powerful features of a retention policy is that it can apply to locations across Microsoft 365, including:</span></span>
  
- <span data-ttu-id="93ced-257">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="93ced-257">Exchange email</span></span>
    
- <span data-ttu-id="93ced-258">SharePoint 网站集</span><span class="sxs-lookup"><span data-stu-id="93ced-258">SharePoint site collections</span></span>
    
- <span data-ttu-id="93ced-259">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="93ced-259">OneDrive accounts</span></span>
    
- <span data-ttu-id="93ced-260">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="93ced-260">Microsoft 365 groups</span></span>
    
- <span data-ttu-id="93ced-261">Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="93ced-261">Exchange public folders</span></span>
    

![用于选择所有位置的选项](../media/retention-policies-all-locations.png)

<span data-ttu-id="93ced-263">组织范围保留策略的其他重要功能包括：</span><span class="sxs-lookup"><span data-stu-id="93ced-263">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="93ced-264">策略可包含任意多个邮箱或网站。</span><span class="sxs-lookup"><span data-stu-id="93ced-264">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="93ced-265">对于 Exchange，在保留策略应用后新建的任何邮箱都会自动继承策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-265">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="93ced-266">应用于位置整体的策略</span><span class="sxs-lookup"><span data-stu-id="93ced-266">A policy that applies to entire locations</span></span>

<span data-ttu-id="93ced-267">选择位置时，可以轻松包含或排除整体位置，例如 Exchange 电子邮件或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="93ced-267">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts.</span></span> <span data-ttu-id="93ced-268">若要执行此操作，将该位置的“**状态**”切换为开或者关。</span><span class="sxs-lookup"><span data-stu-id="93ced-268">To do so, toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="93ced-269">与组织范围的策略相同，如果策略应用到任意组合的整体位置，则可应用策略的邮箱数或网站数不存在限制。</span><span class="sxs-lookup"><span data-stu-id="93ced-269">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include.</span></span> 

<span data-ttu-id="93ced-270">例如，如果对所有的 Exchange 电子邮件和所有的 SharePoint 网站应用策略，则无论网站和邮箱的数量有多少，都会对其应用策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-270">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many.</span></span> <span data-ttu-id="93ced-271">并且对于 Exchange，在应用策略后创建的任何新邮箱都将自动继承该策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-271">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="93ced-272">包含或排除特定位置、用户或组的策略</span><span class="sxs-lookup"><span data-stu-id="93ced-272">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="93ced-273">你还可以将保留策略应用于特定用户、特定 Microsoft 365 组或特定网站。</span><span class="sxs-lookup"><span data-stu-id="93ced-273">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="93ced-274">若要执行此操作，请将该位置的“**状态**”切换为开，然后使用链接来包含或排除特定用户、Microsoft 365 组或者网站。</span><span class="sxs-lookup"><span data-stu-id="93ced-274">To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="93ced-275">但是，如果保留策略包括或排除的特定位置超过 1,000 个，则使用此配置会有一些限制：</span><span class="sxs-lookup"><span data-stu-id="93ced-275">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific locations:</span></span>
  
- <span data-ttu-id="93ced-276">保留策略的最大数量：</span><span class="sxs-lookup"><span data-stu-id="93ced-276">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="93ced-277">1,000 个邮箱</span><span class="sxs-lookup"><span data-stu-id="93ced-277">1,000 mailboxes</span></span>
    - <span data-ttu-id="93ced-278">1,000 个 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="93ced-278">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="93ced-279">1000 个用户的 Teams 私人聊天</span><span class="sxs-lookup"><span data-stu-id="93ced-279">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="93ced-280">100 个网站（OneDrive 或 SharePoint）</span><span class="sxs-lookup"><span data-stu-id="93ced-280">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="93ced-281">租户支持的最大策略数：10,000。</span><span class="sxs-lookup"><span data-stu-id="93ced-281">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="93ced-282">这些项目包括保留策略、保留标签策略和自动应用保留策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-282">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="93ced-283">如果你的保留策略可能受到这些限制，请选择适用于整个位置的配置选项，或使用组织范围的策略。</span><span class="sxs-lookup"><span data-stu-id="93ced-283">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations, or use an org-wide policy.</span></span>

> [!WARNING]
> <span data-ttu-id="93ced-284">如果你配置了包含项，然后删除了最后一项，则配置会将位置的设置还原为“**所有**”。</span><span class="sxs-lookup"><span data-stu-id="93ced-284">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="93ced-285">保存策略之前，请确保这是你期望的配置。</span><span class="sxs-lookup"><span data-stu-id="93ced-285">Make sure this is the configuration that you intend before you save the policy.</span></span>
> 
> <span data-ttu-id="93ced-286">例如，如果你指定了一个 要在根据配置删除数据的保留策略中包含的 SharePoint 网站，然后删除了这个网站，那么默认情况下，所有 SharePoint 网站都将受到永久删除数据的保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="93ced-286">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="93ced-287">这同样适用于针对 Exchange 收件人、OneDrive 帐户和 Teams 聊天用户等进行包含设置。</span><span class="sxs-lookup"><span data-stu-id="93ced-287">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
> 
> <span data-ttu-id="93ced-288">在这种情况下，如果不希望“**所有**”这一位置设置受制于保留策略，请关闭位置。</span><span class="sxs-lookup"><span data-stu-id="93ced-288">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="93ced-289">或者，指定将不受该策略约束的排除项。</span><span class="sxs-lookup"><span data-stu-id="93ced-289">Alternatively, specify excludes to be exempt from the policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="93ced-290">更新保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-290">Updating retention policies</span></span>

<span data-ttu-id="93ced-291">如果你编辑保留策略，并且内容已遵循保留策略中的原始设置，则除了新识别的内容之外，更新后的设置将自动应用于此内容。</span><span class="sxs-lookup"><span data-stu-id="93ced-291">If you edit a retention policy and content is already subject to the original settings in your retention policy, your updated settings will be automatically applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="93ced-292">此更新通常非常快，但可能需要数天。</span><span class="sxs-lookup"><span data-stu-id="93ced-292">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="93ced-293">完成跨 Microsoft 365 位置的策略复制后，你将看到 Microsoft 365 合规中心中的保留策略状态从“**打开（挂起）**”变为“**打开（成功）**”。</span><span class="sxs-lookup"><span data-stu-id="93ced-293">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="93ced-294">使用 PowerShell 锁定保留策略</span><span class="sxs-lookup"><span data-stu-id="93ced-294">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="93ced-295">如果需要使用“[保留锁定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)”来满足法规要求，则必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="93ced-295">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span> <span data-ttu-id="93ced-296">由于管理员无法在应用保留锁定后禁用或删除保留策略，因此 UI 中不提供启用此功能，以防意外配置。</span><span class="sxs-lookup"><span data-stu-id="93ced-296">Because administrators can't disable or delete a retention policy after a preservation lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="93ced-297">具有任何配置的所有保留策略均支持“保留锁定”。</span><span class="sxs-lookup"><span data-stu-id="93ced-297">All retention policies with any configuration support Preservation Lock.</span></span> <span data-ttu-id="93ced-298">但是，在使用以下 PowerShell 命令时，你会注意到 **Workload** 参数始终显示 **Exchange、SharePoint、OneDriveForBusines、Skype、ModernGroup**，而不是策略中配置的实际工作负载。</span><span class="sxs-lookup"><span data-stu-id="93ced-298">However, when you use the PowerShell commands that follow, you'll notice that the **Workload** parameter always displays **Exchange, SharePoint, OneDriveForBusines, Skype, ModernGroup** rather than reflect the actual workloads configured in the policy.</span></span> <span data-ttu-id="93ced-299">这只是显示问题。</span><span class="sxs-lookup"><span data-stu-id="93ced-299">This is a display issue only.</span></span>

1. <span data-ttu-id="93ced-300">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="93ced-300">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="93ced-301">运行 [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy)，列出保留策略并查找要锁定的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="93ced-301">List your retention policies and find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="93ced-302">例如：</span><span class="sxs-lookup"><span data-stu-id="93ced-302">For example:</span></span>
    
   ![PowerShell 中的保留策略列表](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="93ced-304">若要对保留策略应用保留锁定，请运行带有保留策略名称的 [Set-RetentionCompliancePolicy]( ) cmdlet，并将 *RestrictiveRetention* 参数设置为 true：</span><span class="sxs-lookup"><span data-stu-id="93ced-304">To place a Preservation Lock on a retention policy, run the [Set-RetentionCompliancePolicy]( ) cmdlet with the name of the retention policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="93ced-305">例如：</span><span class="sxs-lookup"><span data-stu-id="93ced-305">For example:</span></span>
    
    ![PowerShell 中的 RestrictiveRetention 参数](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="93ced-307">出现提示时，请阅读并通过输入**Y**确认这个配置随附的限制：</span><span class="sxs-lookup"><span data-stu-id="93ced-307">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![用于确认你要在 PowerShell 中锁定保留策略的提示](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="93ced-309">现在，为保留策略提供了“保留锁定”功能。</span><span class="sxs-lookup"><span data-stu-id="93ced-309">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="93ced-310">若要确认，请再次运行 `Get-RetentionCompliancePolicy`，但指定保留策略名称并显示策略参数：</span><span class="sxs-lookup"><span data-stu-id="93ced-310">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the retention policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="93ced-311">应看到 **RestrictiveRetention** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="93ced-311">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="93ced-312">例如：</span><span class="sxs-lookup"><span data-stu-id="93ced-312">For example:</span></span>

![已在 PowerShell 中显示所有参数的锁定策略](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

