---
title: 内容搜索的功能参考
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 本文包含有关 Microsoft 365 合规中心中的内容搜索电子数据展示工具的参考信息，可帮助你了解有关内容搜索的众多详细信息。
ms.openlocfilehash: f3545cc4644ca8b0a96ee37713d8fe62be7466e5
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332890"
---
# <a name="feature-reference-for-content-search"></a><span data-ttu-id="5cc71-103">内容搜索的功能参考</span><span class="sxs-lookup"><span data-stu-id="5cc71-103">Feature reference for Content search</span></span>

<span data-ttu-id="5cc71-104">本文描述了内容搜索的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="5cc71-104">This article describes features and functionality of Content search.</span></span>

## <a name="content-search-limits"></a><span data-ttu-id="5cc71-105">内容搜索限制</span><span class="sxs-lookup"><span data-stu-id="5cc71-105">Content search limits</span></span>

- <span data-ttu-id="5cc71-106">有关适用于内容搜索的限制说明，请参阅 [内容搜索限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-106">For a description of the limits that are applied to content searches, see [Limits for Content search](limits-for-content-search.md).</span></span>
  
- <span data-ttu-id="5cc71-107">Microsoft 会收集由服务中所有组织运行的内容搜索的性能信息。</span><span class="sxs-lookup"><span data-stu-id="5cc71-107">Microsoft collects performance information for Content searches run by all organizations in the service.</span></span> <span data-ttu-id="5cc71-108">尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="5cc71-108">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="5cc71-109">尽管 Microsoft 未为搜索时间提供服务级别协议，但是下表根据搜索中所含的邮箱数列出了内容搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="5cc71-109">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="5cc71-110">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="5cc71-110">**Number of mailboxes**</span></span>|<span data-ttu-id="5cc71-111">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="5cc71-111">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="5cc71-112">100</span><span class="sxs-lookup"><span data-stu-id="5cc71-112">100</span></span>  <br/> |<span data-ttu-id="5cc71-113">30 秒</span><span class="sxs-lookup"><span data-stu-id="5cc71-113">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="5cc71-114">1,000</span><span class="sxs-lookup"><span data-stu-id="5cc71-114">1,000</span></span>  <br/> |<span data-ttu-id="5cc71-115">45 秒</span><span class="sxs-lookup"><span data-stu-id="5cc71-115">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="5cc71-116">10,000</span><span class="sxs-lookup"><span data-stu-id="5cc71-116">10,000</span></span>  <br/> |<span data-ttu-id="5cc71-117">4 分钟</span><span class="sxs-lookup"><span data-stu-id="5cc71-117">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="5cc71-118">25,000</span><span class="sxs-lookup"><span data-stu-id="5cc71-118">25,000</span></span>  <br/> |<span data-ttu-id="5cc71-119">10 分钟</span><span class="sxs-lookup"><span data-stu-id="5cc71-119">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="5cc71-120">50,000</span><span class="sxs-lookup"><span data-stu-id="5cc71-120">50,000</span></span>  <br/> |<span data-ttu-id="5cc71-121">20 分钟</span><span class="sxs-lookup"><span data-stu-id="5cc71-121">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="5cc71-122">100,000</span><span class="sxs-lookup"><span data-stu-id="5cc71-122">100,000</span></span>  <br/> |<span data-ttu-id="5cc71-123">25 分钟</span><span class="sxs-lookup"><span data-stu-id="5cc71-123">25 minutes</span></span>  <br/> |
  |||
  
## <a name="building-a-search-query"></a><span data-ttu-id="5cc71-124">构建搜索查询</span><span class="sxs-lookup"><span data-stu-id="5cc71-124">Building a search query</span></span>

<span data-ttu-id="5cc71-125">有关创建搜索查询、使用布尔搜索运算符和搜索条件以及搜索敏感信息类型及与组织外部用户共享的内容的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-125">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="5cc71-126">使用关键字列表创建搜索查询时，请注意以下内容。</span><span class="sxs-lookup"><span data-stu-id="5cc71-126">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="5cc71-127">必须选中“**显示关键字列表**”复选框并在单独行中键入每个关键字，才能创建每行中的关键字以 **OR** 运算符连接的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="5cc71-127">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="5cc71-128">如果将关键字列表粘贴至关键字框或者在键入关键字之后按 **Enter** 键，则它们将不会以 **OR** 运算符连接。</span><span class="sxs-lookup"><span data-stu-id="5cc71-128">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="5cc71-129">以下是添加关键字列表的错误和正确示例。</span><span class="sxs-lookup"><span data-stu-id="5cc71-129">Here are incorrect and correct examples of how to add a list of keywords.</span></span>
    
    <span data-ttu-id="5cc71-130">**错误**</span><span class="sxs-lookup"><span data-stu-id="5cc71-130">**Incorrect**</span></span>
    
    ![设置关键字列表格式的不正确方式（通过将列表粘贴至关键字框）](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="5cc71-132">**正确**</span><span class="sxs-lookup"><span data-stu-id="5cc71-132">**Correct**</span></span>
    
    ![设置关键字列表格式的正确方式（在选中复选框后粘贴列表）](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="5cc71-134">还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语列表，然后将你的列表复制粘贴至关键字列表。</span><span class="sxs-lookup"><span data-stu-id="5cc71-134">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="5cc71-135">若要执行此操作，你必须选中“**显示关键字列表**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5cc71-135">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="5cc71-136">然后，单击关键字列表中的第一行并粘贴你的列表。</span><span class="sxs-lookup"><span data-stu-id="5cc71-136">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="5cc71-137">Excel 或文本文件中的每一行均会粘贴至关键字列表中的单独行中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-137">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="5cc71-138">使用关键字列表创建查询后，最好验证搜索查询语法，确保搜索查询适合你的需求。</span><span class="sxs-lookup"><span data-stu-id="5cc71-138">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="5cc71-139">在详细信息窗格的“**查询**”下显示的搜索查询中，关键字将以文本 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="5cc71-139">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="5cc71-140">这表示关键字由功能类似于 **OR** 运算符的逻辑运算符连接。</span><span class="sxs-lookup"><span data-stu-id="5cc71-140">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="5cc71-141">同样，如果搜索查询中包含条件，则关键字和条件将以 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="5cc71-141">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="5cc71-142">这表示关键字由功能类似于 **AND** 运算符的逻辑运算符连接到条件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-142">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5cc71-143">以下是使用关键字列表和条件时创建的搜索查询（显示在详细信息窗格中）示例。</span><span class="sxs-lookup"><span data-stu-id="5cc71-143">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用关键字列表和条件时创建的查询示例](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="5cc71-145">运行内容搜索时，Microsoft 365 将会自动检查搜索查询中是否存在不受支持的字符以及未大写的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="5cc71-145">When you run a content search, Microsoft 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="5cc71-146">不受支持的字符往往会被隐藏，并且通常会引发搜索错误或者返回意外结果。</span><span class="sxs-lookup"><span data-stu-id="5cc71-146">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="5cc71-147">有关检查到的不受支持字符的详细信息，请参阅[检查内容搜索查询中是否存在错误](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-147">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="5cc71-148">如果搜索查询中包含非英语字符（例如中文字符）关键字，则可以单击“**查询语言-国家/地区**”“![内容搜索中的查询语言-国家/地区](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)”并为该搜索选择语言-国家/地区文化代码值。</span><span class="sxs-lookup"><span data-stu-id="5cc71-148">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="5cc71-149">默认语言/区域是中性的。</span><span class="sxs-lookup"><span data-stu-id="5cc71-149">The default language/region is neutral.</span></span> <span data-ttu-id="5cc71-150">如何判断是否需要更改内容搜索的语言设置？</span><span class="sxs-lookup"><span data-stu-id="5cc71-150">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="5cc71-151">如果确定内容位置中包含所搜索的非英语字符，但搜索没有返回结果，则可能是语言设置的原因。</span><span class="sxs-lookup"><span data-stu-id="5cc71-151">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting may be the cause.</span></span> 
  
## <a name="partially-indexed-items"></a><span data-ttu-id="5cc71-152">部分索引项</span><span class="sxs-lookup"><span data-stu-id="5cc71-152">Partially indexed items</span></span>

- <span data-ttu-id="5cc71-153">邮箱中的部分索引项将包括在估计搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-153">Partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="5cc71-154">SharePoint 和 OneDrive 中的部分索引项不会包括在估计搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-154">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> <span data-ttu-id="5cc71-155">有关详细信息，请参阅[电子数据展示中的部分索引项](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-155">For more information, see [Partially indexed items in eDiscovery](partially-indexed-items-in-content-search.md).</span></span>

## <a name="searching-onedrive-accounts"></a><span data-ttu-id="5cc71-156">搜索 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="5cc71-156">Searching OneDrive accounts</span></span>

- <span data-ttu-id="5cc71-157">若要收集组织中的 OneDrive 网站 URL 列表，请参阅[在组织中创建所有 OneDrive 位置的列表](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-157">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span> <span data-ttu-id="5cc71-158">本文中的脚本将创建包含所有 OneDrive 网站的文本文件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-158">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="5cc71-159">若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。</span><span class="sxs-lookup"><span data-stu-id="5cc71-159">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5cc71-160">请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。</span><span class="sxs-lookup"><span data-stu-id="5cc71-160">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="5cc71-161">这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="5cc71-161">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="5cc71-162">下面是用户的 OneDrive 网站的 URL 示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="5cc71-162">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="5cc71-163">在某用户的用户主体名称 (UPN) 发生更改的情况下（这种情况很罕见），其 OneDrive 位置的 URL 将发生更改，以包含新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="5cc71-163">In the rare case of a person's user principal name (UPN) being changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="5cc71-164">如果发生这种情况，则必须通过添加该用户的新 OneDrive URL 并删除旧 URL 来修改内容搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-164">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span> <span data-ttu-id="5cc71-165">有关详细信息，请参阅 [UPN 更改如何影响 OneDrive URL](/onedrive/upn-changes)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-165">For more information, see [How UPN changes affect the OneDrive URL](/onedrive/upn-changes).</span></span>
  
## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a><span data-ttu-id="5cc71-166">搜索 Microsoft Teams 和 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="5cc71-166">Searching Microsoft Teams and Microsoft 365 Groups</span></span>

<span data-ttu-id="5cc71-167">可以搜索与 Microsoft Teams 或 Microsoft 365 组 关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-167">You can search the mailbox that's associated with a Microsoft Team or Microsoft 365 Group.</span></span> <span data-ttu-id="5cc71-168">Microsoft Teams 基于 Microsoft 365 构建，因此，搜索方法类似。</span><span class="sxs-lookup"><span data-stu-id="5cc71-168">Because Microsoft Teams is built on Microsoft 365 Groups, searching them is similar.</span></span> <span data-ttu-id="5cc71-169">在这两种情况下，只会搜索组或团队邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-169">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="5cc71-170">不会搜索组或团队成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-170">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="5cc71-171">若要搜索它们，必须将它们专门添加到搜索中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-171">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="5cc71-172">搜索 Microsoft Teams 和 Microsoft 365 组中的内容时，请注意以下内容。</span><span class="sxs-lookup"><span data-stu-id="5cc71-172">Keep the following things in mind when searching for content in Microsoft Teams and Microsoft 365 Groups.</span></span>
  
- <span data-ttu-id="5cc71-173">若要搜索 Teams 和 Microsoft 365 组中的内容，必须指定与团队或组关联的邮箱和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="5cc71-173">To search for content located in Teams and Microsoft 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>

- <span data-ttu-id="5cc71-174">私人频道的内容将存储在每个用户的邮箱中，而不是团队邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-174">Content from private channels is stored in each user's mailbox, not the team mailbox.</span></span> <span data-ttu-id="5cc71-175">若要搜索私人频道中的内容，请参阅[私人频道的电子数据展示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-175">To search for content in private channels, see [eDiscovery of private channels](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).</span></span>
    
- <span data-ttu-id="5cc71-176">在 Exchange Online 中运行 **Get-UnifiedGroup** cmdlet，以查看团队或 Microsoft 365 组的属性。</span><span class="sxs-lookup"><span data-stu-id="5cc71-176">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or a Microsoft 365 Group.</span></span> <span data-ttu-id="5cc71-177">这是一种获取与团队或组关联的网站 URL 的好方法。</span><span class="sxs-lookup"><span data-stu-id="5cc71-177">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="5cc71-178">例如，以下命令显示名为“高层领导团队”的 Microsoft 365 组的选定属性：</span><span class="sxs-lookup"><span data-stu-id="5cc71-178">For example, the following command displays selected properties for a Microsoft 365 Group named Senior Leadership Team:</span></span> 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > <span data-ttu-id="5cc71-179">若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5cc71-179">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5cc71-180">搜索用户邮箱时，不会搜索该用户作为成员的任何团队或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="5cc71-180">When a user's mailbox is searched, any team or Microsoft 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="5cc71-181">类似地，在搜索团队或 Microsoft 365 组时，只会搜索指定的组邮箱和组网站。</span><span class="sxs-lookup"><span data-stu-id="5cc71-181">Similarly, when you search a team or a Microsoft 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="5cc71-182">不会搜索组成员的邮箱和 OneDrive for Business 帐户，除非你明确将其添加到搜索中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-182">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>

- <span data-ttu-id="5cc71-183">若要获取团队或 Microsoft 365 组的成员列表，可以查看 Microsoft 365 管理中心 **主页 \> 组** 页上的属性。</span><span class="sxs-lookup"><span data-stu-id="5cc71-183">To get a list of the members of a team or a Microsoft 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5cc71-184">或者，可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5cc71-184">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > <span data-ttu-id="5cc71-185">若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5cc71-185">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5cc71-186">属于 Teams 渠道的对话将存储在与团队关联的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-186">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="5cc71-187">同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。</span><span class="sxs-lookup"><span data-stu-id="5cc71-187">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="5cc71-188">因此，必须将团队邮箱和 SharePoint 网站作为内容位置添加到搜索渠道中的对话和文件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-188">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="5cc71-189">或者，属于 Teams 中聊天列表的对话将存储在参与该聊天的用户的 Exchange Online 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-189">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="5cc71-190">用户在聊天对话中共享的文件将存储在共享该文件的用户的 OneDrive for Business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-190">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="5cc71-191">因此，必须将单独的用户邮箱和 OneDrive for Business 帐户作为内容位置添加到聊天列表中的搜索对话和文件中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-191">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cc71-192">在 Exchange 混合部署中，拥有本地邮箱的用户可以参与属于 Teams 中的聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="5cc71-192">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="5cc71-193">在这种情况下，这些对话中的也可搜索，因为对于拥有本地邮箱的用户来说，它已保存至拥有本地邮箱的用户的基于云的存储区（称为 *本地用户的基于云的邮箱*）。</span><span class="sxs-lookup"><span data-stu-id="5cc71-193">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="5cc71-194">有关详细信息，请参阅 [搜索本地用户的 Teams 聊天数据](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-194">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="5cc71-195">每个团队或团队渠道均包含一个用于做笔记和协作的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="5cc71-195">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="5cc71-196">Wiki 内容将会自动保存至采用 .mht 格式的文件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-196">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="5cc71-197">此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-197">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="5cc71-198">可以使用内容搜索工具来搜索 Wiki，方法是将团队的 SharePoint 网站指定为要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="5cc71-198">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cc71-199">搜索团队或渠道 Wiki 的功能（在搜索团队 SharePoint 网站时）已于 2017 年 6 月 22 日发布。</span><span class="sxs-lookup"><span data-stu-id="5cc71-199">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="5cc71-200">可以对在该日期或之后保存或更新的 Wiki 页面进行搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-200">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="5cc71-201">不可搜索最后保存或更新时间早于该日期的 Wiki 页面。</span><span class="sxs-lookup"><span data-stu-id="5cc71-201">Wiki pages last saved or updated before that date aren't available for search.</span></span>

- <span data-ttu-id="5cc71-202">Teams 渠道中的会议和呼叫摘要信息也保存在拨入会议或呼叫的用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-202">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="5cc71-203">这意味着你可以使用内容搜索来搜索这些摘要记录。</span><span class="sxs-lookup"><span data-stu-id="5cc71-203">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="5cc71-204">摘要信息包括：</span><span class="sxs-lookup"><span data-stu-id="5cc71-204">Summary information includes:</span></span>
  
  - <span data-ttu-id="5cc71-205">日期、开始时间、结束时间和会议或呼叫时长</span><span class="sxs-lookup"><span data-stu-id="5cc71-205">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="5cc71-206">每个参与者加入或离开会议或呼叫的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5cc71-206">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="5cc71-207">发送到语音信箱的呼叫</span><span class="sxs-lookup"><span data-stu-id="5cc71-207">Calls sent to voice mail</span></span>

  - <span data-ttu-id="5cc71-208">未接呼叫</span><span class="sxs-lookup"><span data-stu-id="5cc71-208">Missed or unanswered calls</span></span>

  - <span data-ttu-id="5cc71-209">表示为两次单独呼叫的呼叫转移</span><span class="sxs-lookup"><span data-stu-id="5cc71-209">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="5cc71-210">可能需要最多 8 小时之后才能搜索会议和呼叫摘要记录。</span><span class="sxs-lookup"><span data-stu-id="5cc71-210">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="5cc71-211">在搜索结果中，会议摘要在“**类型字段**”将标识为“**会议**”，呼叫摘要将标识为“**呼叫**”。</span><span class="sxs-lookup"><span data-stu-id="5cc71-211">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="5cc71-212">此外，属于 Teams 渠道和 1xN 聊天的对话在“**类型**”字段将标识为 **IM**。</span><span class="sxs-lookup"><span data-stu-id="5cc71-212">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams 会议、呼叫和 1xN 聊天将在“类型”字段中标识](../media/O365-ContentSearch-Teams-MessageKind.png)

   <span data-ttu-id="5cc71-214">有关详细信息，请参阅 [Microsoft Teams 针对通话和会议推出电子数据展示](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-214">For more information, see [Microsoft Teams launches eDiscovery for calls and meetings](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947).</span></span>

- <span data-ttu-id="5cc71-215">Teams 频道中应用、一对一聊天以及一对多人聊天生成的卡片内容存储在邮箱中，并且可以被搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-215">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="5cc71-216">*卡片* 是一个 UI 容器，用于存放内容短片。</span><span class="sxs-lookup"><span data-stu-id="5cc71-216">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="5cc71-217">卡片可具有多个属性和附件，并且可以包括能够触发卡片操作的按钮。</span><span class="sxs-lookup"><span data-stu-id="5cc71-217">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="5cc71-218">有关详细信息，请参阅 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="5cc71-218">For more information, see [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

  <span data-ttu-id="5cc71-219">和其他 Teams 内容一样，卡片内容的存储位置由卡片用在何处来确定。</span><span class="sxs-lookup"><span data-stu-id="5cc71-219">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="5cc71-220">用于 Teams 频道中的卡片内容存储在 Teams 组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-220">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="5cc71-221">一对一和一对多聊天的卡片内容存储在聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5cc71-221">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

  <span data-ttu-id="5cc71-222">若要搜索卡片内容，可以使用 `kind:microsoftteams` 或 `itemclass:IPM.SkypeTeams.Message` 搜索条件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-222">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="5cc71-223">查看搜索结果时，由 Teams 频道中的聊天机器人生成的卡片内容具有 **发送者/作者** 电子邮件属性，如 `<appname>@teams.microsoft.com`，其中 `appname` 则是生成卡片内容的应用名称。</span><span class="sxs-lookup"><span data-stu-id="5cc71-223">When reviewing search results, card content generated by bots in a Teams channel have the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="5cc71-224">如果卡片内容由用户生成，则 **发送者/作者** 的值会标识用户。</span><span class="sxs-lookup"><span data-stu-id="5cc71-224">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

  <span data-ttu-id="5cc71-225">查看内容搜索结果中的卡片内容时，内容显示为电子邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="5cc71-225">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="5cc71-226">附件名为 `appname.html`，其中 `appname` 是生成卡片内容的应用名称。</span><span class="sxs-lookup"><span data-stu-id="5cc71-226">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="5cc71-227">以下屏幕截图显示在 Teams 和搜索结果中如何展示（名为Asana 的应用）卡片内容。</span><span class="sxs-lookup"><span data-stu-id="5cc71-227">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

  <span data-ttu-id="5cc71-228">**Teams 中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="5cc71-228">**Card content in Teams**</span></span>

  ![Teams 频道消息中的卡片内容](../media/CardContentTeams.png)

  <span data-ttu-id="5cc71-230">**搜索结果中的卡片内容**</span><span class="sxs-lookup"><span data-stu-id="5cc71-230">**Card content in search results**</span></span>
  
  ![内容搜索结果中相同的卡片内容](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > <span data-ttu-id="5cc71-232">若要显示此时搜索结果中卡片内容的图像（如上一个屏幕截图中的复选标记），必须登录 Teams（在用于查看搜索结果的同一浏览器会话中另一选项卡的 https://teams.microsoft.com) 处。</span><span class="sxs-lookup"><span data-stu-id="5cc71-232">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="5cc71-233">否则，将显示图像占位符。</span><span class="sxs-lookup"><span data-stu-id="5cc71-233">Otherwise, image placeholders are displayed.</span></span>

- <span data-ttu-id="5cc71-234">可以使用“**类型**”电子邮件属性或“**邮件类型**”搜索条件来搜索 Teams 中的特定内容。</span><span class="sxs-lookup"><span data-stu-id="5cc71-234">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span>
  
  - <span data-ttu-id="5cc71-235">若要将“**类型**”属性用作关键字搜索查询的一部分，请在搜索查询的“**关键字**”框中键入 `kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="5cc71-235">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在“关键字”框中使用 kind:microsoftteams](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="5cc71-237">若要使用搜索条件，请添加“**邮件类型**”条件并使用值 `microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="5cc71-237">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span>

    ![搭配使用“邮件类型”条件和值 microsoftteams。](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   <span data-ttu-id="5cc71-239">条件将通过 **AND** 运算符在逻辑上连接至关键字查询。</span><span class="sxs-lookup"><span data-stu-id="5cc71-239">Conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="5cc71-240">这意味着项必须与关键字查询和搜索条件匹配才能在搜索结果中返回。</span><span class="sxs-lookup"><span data-stu-id="5cc71-240">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="5cc71-241">有关详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的“使用条件指南”一节。</span><span class="sxs-lookup"><span data-stu-id="5cc71-241">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>
  
## <a name="searching-yammer-groups"></a><span data-ttu-id="5cc71-242">搜索 Yammer 组</span><span class="sxs-lookup"><span data-stu-id="5cc71-242">Searching Yammer Groups</span></span>

<span data-ttu-id="5cc71-243">可以使用 **ItemClass** 电子邮件属性或 **Type** 搜索条件来专门搜索 Yammer 组中的对话项。</span><span class="sxs-lookup"><span data-stu-id="5cc71-243">You can use the **ItemClass** email property or the **Type** search condition to search specifically for conversation items in Yammer Groups.</span></span>

  - <span data-ttu-id="5cc71-244">若要将 **ItemClass** 属性用作关键字搜索查询的一部分，可以在搜索查询的“关键字”框中键入以下一个（或所有）property:value 对：</span><span class="sxs-lookup"><span data-stu-id="5cc71-244">To use the **ItemClass** property as part of the keyword search query, in the **Keywords** box of a search query, you can type one (or all) of the following property:value pairs:</span></span>

     - <span data-ttu-id="5cc71-245">ItemClass:IPM.Yammer.message</span><span class="sxs-lookup"><span data-stu-id="5cc71-245">ItemClass:IPM.Yammer.message</span></span>
     - <span data-ttu-id="5cc71-246">ItemClass:IPM.Yammer.poll</span><span class="sxs-lookup"><span data-stu-id="5cc71-246">ItemClass:IPM.Yammer.poll</span></span>
     - <span data-ttu-id="5cc71-247">ItemClass:IPM.Yammer.praise</span><span class="sxs-lookup"><span data-stu-id="5cc71-247">ItemClass:IPM.Yammer.praise</span></span>
     - <span data-ttu-id="5cc71-248">ItemClass:IPM.Yammer.question</span><span class="sxs-lookup"><span data-stu-id="5cc71-248">ItemClass:IPM.Yammer.question</span></span>
  
    <span data-ttu-id="5cc71-249">例如，可以使用下面的搜索查询来返回 Yammer 消息和 Yammer 表扬项：</span><span class="sxs-lookup"><span data-stu-id="5cc71-249">For example, you can use the following search query to return Yammer messages and Yammer praise items:</span></span>

    ![使用 ItemClass 属性搜索 Yammer 项](../media/YammerContentSearch1.png)
  
  - <span data-ttu-id="5cc71-251">也可以使用 **Type** 电子邮件条件，并选择“Yammer 消息”，以返回 Yammer 项。</span><span class="sxs-lookup"><span data-stu-id="5cc71-251">Alternatively, you can use the **Type** email condition and select **Yammer messages** to return Yammer items.</span></span> <span data-ttu-id="5cc71-252">例如，下面的搜索查询返回所有包含关键字“保密”的 Yammer 对话项。</span><span class="sxs-lookup"><span data-stu-id="5cc71-252">For example, the following search query will return all Yammer conversation items that contain the keyword "confidential".</span></span> 

    ![使用 Type 条件卡搜索 Yammer 对话项](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a><span data-ttu-id="5cc71-254">搜索非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5cc71-254">Searching inactive mailboxes</span></span>

<span data-ttu-id="5cc71-255">可以在内容搜索中搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-255">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="5cc71-256">若要获取组织中的非活动邮箱列表，请在 Exchange Online PowerShell 中运行命令 `Get-Mailbox -InactiveMailboxOnly`。</span><span class="sxs-lookup"><span data-stu-id="5cc71-256">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="5cc71-257">或者，你可以转至安全与合规中心中的“**信息管理**”\>“**保留**”，然后单击“**更多**”![导航栏省略号](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \>“**非活动邮箱**”。</span><span class="sxs-lookup"><span data-stu-id="5cc71-257">Alternatively, you can go to **Information governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="5cc71-258">以下是在搜索非活动邮箱时应记住的一些事项。</span><span class="sxs-lookup"><span data-stu-id="5cc71-258">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>

- <span data-ttu-id="5cc71-259">如果现有内容搜索包括用户邮箱，且该邮箱变成了非活动状态，那么在该邮箱转变为非活动状态后重新运行搜索时，内容搜索将继续搜索该非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-259">If an existing content search includes a user mailbox and that mailbox is made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>

- <span data-ttu-id="5cc71-260">有时候，用户可能具有 SMTP 地址相同的活动邮箱和非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-260">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="5cc71-261">在这种情况下，将仅搜索你选为内容搜索位置的特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-261">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="5cc71-262">换言之，如果将用户邮箱添加到搜索中，则无法假定搜索的是其活动和非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-262">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="5cc71-263">系统只会搜索已显式添加到搜索中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-263">Only the mailbox that you explicitly add to the search is searched.</span></span>

- <span data-ttu-id="5cc71-264">可使用安全与合规中心 PowerShell 来创建内容搜索，以搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-264">You can use Security & Compliance Center PowerShell to create a content search to search an inactive mailbox.</span></span> <span data-ttu-id="5cc71-265">若要执行此操作，必须预先附加一个句点 ( .</span><span class="sxs-lookup"><span data-stu-id="5cc71-265">To do this, you have to pre-append a period ( .</span></span> <span data-ttu-id="5cc71-266">) 到非活动邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5cc71-266">) to the email address of the inactive mailbox.</span></span> <span data-ttu-id="5cc71-267">例如，下面的命令可创建一个搜索电子邮件地址为 pavelb@contoso.onmicrosoft.com 的非活动邮箱的内容搜索：</span><span class="sxs-lookup"><span data-stu-id="5cc71-267">For example, the following command creates a content search that searches an inactive mailbox with the email address pavelb@contoso.onmicrosoft.com:</span></span>

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- <span data-ttu-id="5cc71-268">强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="5cc71-268">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="5cc71-269">如果需要重新使用分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或将非活动邮箱中的内容还原到活动邮箱中（或活动邮箱的存档中），然后删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-269">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="5cc71-270">有关详细信息，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="5cc71-270">For more information, see one of the following topics:</span></span>

  - [<span data-ttu-id="5cc71-271">恢复 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5cc71-271">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)

  - [<span data-ttu-id="5cc71-272">还原 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5cc71-272">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)

  - [<span data-ttu-id="5cc71-273">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5cc71-273">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a><span data-ttu-id="5cc71-274">搜索已断开连接或已取消许可的邮箱</span><span class="sxs-lookup"><span data-stu-id="5cc71-274">Searching disconnected or de-licensed mailboxes</span></span>

<span data-ttu-id="5cc71-275">如果从用户帐户或 Azure Active Directory 中删除了 Exchange Online 许可证（或整个 Microsoft 365 许可证），那么用户的邮箱将成为 *断开连接的* 邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-275">If the Exchange Online license (or the entire Microsoft 365 license) is removed from a user account or in Azure Active Directory, the user's mailbox becomes a *disconnected* mailbox.</span></span> <span data-ttu-id="5cc71-276">这意味着邮箱不再与用户帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="5cc71-276">This means that the mailbox is no longer associated with the user account.</span></span> <span data-ttu-id="5cc71-277">下面是搜索已断开连接的邮箱时将发生的情况：</span><span class="sxs-lookup"><span data-stu-id="5cc71-277">Here's what happens when searching disconnected mailboxes:</span></span>

- <span data-ttu-id="5cc71-278">如果已从邮箱中删除许可证，则邮箱将不再可搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-278">If the license is removed from a mailbox, the mailbox is no longer searchable.</span></span> 

- <span data-ttu-id="5cc71-279">如果现有内容搜索包含某个删除了许可证的邮箱，则在重新运行该内容搜索时，将不会返回来自该已断开连接的邮箱的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5cc71-279">If an existing content search includes a mailbox in which the license is removed, no search results from the disconnected mailbox will be returned if you rerun the content search.</span></span>

- <span data-ttu-id="5cc71-280">如果使用 **New-ComplianceSearch** cmdlet 创建内容搜索，并将某个已断开连接的邮箱指定为要搜索的 Exchange 内容位置，则该内容搜索不会返回任何来自该已断开连接的邮箱的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5cc71-280">If you use the **New-ComplianceSearch** cmdlet to create a content search and specify a disconnected mailbox as the Exchange content location to search, the content search won't return any search results from the disconnected mailbox.</span></span>

<span data-ttu-id="5cc71-281">如果需要保留某个已断开连接的邮箱中的数据以使其可搜索，则必须在删除许可证之前保留该邮箱。</span><span class="sxs-lookup"><span data-stu-id="5cc71-281">If you need to preserve the data in a disconnected mailbox so that it's searchable, you must place a hold on the mailbox before removing the license.</span></span> <span data-ttu-id="5cc71-282">这将保留数据并使已断开连接的邮箱保持可搜索，直至保留被删除。</span><span class="sxs-lookup"><span data-stu-id="5cc71-282">This preserves the data and keeps the disconnected mailbox searchable until the hold is removed.</span></span> <span data-ttu-id="5cc71-283">有关保留的详细信息，请参阅[如何识别为 Exchange Online 邮箱设置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc71-283">For more information about holds, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a><span data-ttu-id="5cc71-284">在 SharePoint 多地理位置环境中搜索内容</span><span class="sxs-lookup"><span data-stu-id="5cc71-284">Searching for content in a SharePoint Multi-Geo environment</span></span>

<span data-ttu-id="5cc71-285">如果电子数据展示管理器需要在 [ 多地理位置环境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)中的不同区域内搜索 SharePoint 和 OneDrive 中的内容，则需要执行以下操作来实现这一点：</span><span class="sxs-lookup"><span data-stu-id="5cc71-285">If it's necessary for an eDiscovery manager to search for content in SharePoint and OneDrive in different regions in a [SharePoint multi-geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md), then you need to do the following things to make that happen:</span></span>

1. <span data-ttu-id="5cc71-286">为电子数据展示管理器需要搜索的每个卫星地理位置创建单独的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5cc71-286">Create a separate user account for each satellite geo location that the eDiscovery manager needs to search.</span></span> <span data-ttu-id="5cc71-287">若要在该地理位置搜索网站中的内容，电子数据展示管理器必须登录到为该位置创建的帐户，然后运行内容搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-287">To search for content in sites in that geo location, the eDiscovery manager must sign in to the account you created for that location and then run a content search.</span></span>

2. <span data-ttu-id="5cc71-288">为电子数据展示管理器需要搜索的每个卫星地理位置（和相应用户帐户）创建搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="5cc71-288">Create a search permissions filter for each satellite geo location (and corresponding user account) the eDiscovery manager needs to search.</span></span> <span data-ttu-id="5cc71-289">当电子数据展示管理器登录到与该位置相关联的用户帐户时，其中每一个搜索权限筛选器都会将内容搜索的范围限制为特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="5cc71-289">Each of these search permissions filters limits the scope of the content search to a specific geo location when the eDiscovery manager is signed in to the user account associated with that location.</span></span>

> [!TIP]
> <span data-ttu-id="5cc71-290">使用[高级电子数据展示](overview-ediscovery-20.md)中的搜索工具时，无需使用此策略。</span><span class="sxs-lookup"><span data-stu-id="5cc71-290">You don't have to use this strategy when using the search tool in [Advanced eDiscovery](overview-ediscovery-20.md).</span></span> <span data-ttu-id="5cc71-291">这是因为在高级电子数据展示中搜索 SharePoint 网站和 OneDrive 帐户时，将搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="5cc71-291">That's because all datacenters are searched when you search SharePoint sites and OneDrive accounts in Advanced eDiscovery.</span></span> <span data-ttu-id="5cc71-292">仅当使用内容搜索工具并运行与[电子数据展示事例](./get-started-core-ediscovery.md)相关联的搜索时，才必须使用特定于区域的用户帐户的策略和搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="5cc71-292">You have to use this strategy of region-specific user accounts and search permissions filters only when using the Content Search tool and running searches associated with [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

<span data-ttu-id="5cc71-293">例如，假设电子数据展示管理器需要在北美、欧洲和亚太的卫星位置搜索 SharePoint 和 OneDrive 内容。</span><span class="sxs-lookup"><span data-stu-id="5cc71-293">For example, let's say that an eDiscovery manager needs to search for SharePoint and OneDrive content in satellite locations in North American, Europe, and Asia Pacific.</span></span> <span data-ttu-id="5cc71-294">第一步是创建三个用户帐户，每个帐户对应一个位置。</span><span class="sxs-lookup"><span data-stu-id="5cc71-294">The first step is to create three users accounts, one for each location.</span></span> <span data-ttu-id="5cc71-295">下一步是创建三个搜索权限筛选器，分别对应每个位置 *和* 相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5cc71-295">The next step is to create three search permissions filters, one for each location *and* corresponding user account.</span></span> <span data-ttu-id="5cc71-296">下面是这种情况下三个搜索权限筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="5cc71-296">Here are examples of the three search permissions filters for this scenario.</span></span> <span data-ttu-id="5cc71-297">在上述每个示例中，“**区域**”指定该地理位置的 SharePoint 数据中心位置，而“**Users**”参数指定相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5cc71-297">In each of these examples, the **Region** specifies the SharePoint datacenter location for that geo and the **Users** parameter specifies the corresponding user account.</span></span>

<span data-ttu-id="5cc71-298">**北美**</span><span class="sxs-lookup"><span data-stu-id="5cc71-298">**North America**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

<span data-ttu-id="5cc71-299">**欧洲**</span><span class="sxs-lookup"><span data-stu-id="5cc71-299">**Europe**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

<span data-ttu-id="5cc71-300">**亚太地区**</span><span class="sxs-lookup"><span data-stu-id="5cc71-300">**Asia Pacific**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

<span data-ttu-id="5cc71-301">使用搜索权限筛选器搜索多地理位置环境中的内容时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="5cc71-301">Keep the following things in mind when using search permissions filters to search for content in multi-geo environments:</span></span>

- <span data-ttu-id="5cc71-302">**Region** 参数将搜索定向到指定的卫星位置。</span><span class="sxs-lookup"><span data-stu-id="5cc71-302">The **Region** parameter directs searches to the specified satellite location.</span></span> <span data-ttu-id="5cc71-303">如果电子数据展示管理器仅在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站，则不返回任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5cc71-303">If an eDiscovery manager only searches SharePoint and OneDrive sites outside of the region specified in the search permissions filter, no search results are returned.</span></span> 

- <span data-ttu-id="5cc71-304">**Region** 参数不控制 Exchange 邮箱的搜索。</span><span class="sxs-lookup"><span data-stu-id="5cc71-304">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="5cc71-305">搜索邮箱时，将搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="5cc71-305">All datacenters are searched when you search mailboxes.</span></span>

<span data-ttu-id="5cc71-306">要详细了解如何在多地理位置环境中使用搜索权限筛选器，请参阅[设置电子数据展示调查的合规性边界](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)中的“在多地理位置环境中搜索和导出内容”部分。</span><span class="sxs-lookup"><span data-stu-id="5cc71-306">For more information about using search permissions filters in a multi-geo environment, see the "Searching and exporting content in Multi-Geo environments" section in [Set up compliance boundaries for eDiscovery investigations](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>
