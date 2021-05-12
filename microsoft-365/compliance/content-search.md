---
title: 在 Microsoft 365 合规中心中创建并运行内容搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
description: 使用合规中心中的内容搜索电子数据展示工具，搜索各种 Microsoft 365 服务中的内容。
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311651"
---
# <a name="create-a-content-search"></a><span data-ttu-id="c3156-103">创建内容搜索</span><span class="sxs-lookup"><span data-stu-id="c3156-103">Create a content search</span></span>

<span data-ttu-id="c3156-104">可以使用 Microsoft 365 合规中心中的内容搜索电子数据展示工具来搜索就地内容，例如组织中的电子邮件、文档和即时消息会话。</span><span class="sxs-lookup"><span data-stu-id="c3156-104">You can use the Content search eDiscovery tool in the Microsoft 365 compliance center to search for in-place content such as email, documents, and instant messaging conversations in your organization.</span></span> <span data-ttu-id="c3156-105">使用此工具搜索以下 Microsoft 365 数据源中的内容：</span><span class="sxs-lookup"><span data-stu-id="c3156-105">Use this tool to search for content in these Microsoft 365 data sources:</span></span>
  
- <span data-ttu-id="c3156-106">Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="c3156-106">Exchange Online mailboxes</span></span>

- <span data-ttu-id="c3156-107">SharePoint Online 网站和 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="c3156-107">SharePoint Online sites and OneDrive for Business accounts</span></span>

- <span data-ttu-id="c3156-108">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3156-108">Microsoft Teams</span></span>

- <span data-ttu-id="c3156-109">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="c3156-109">Microsoft 365 Groups</span></span>

- <span data-ttu-id="c3156-110">Yammer 组</span><span class="sxs-lookup"><span data-stu-id="c3156-110">Yammer Groups</span></span>

<span data-ttu-id="c3156-111">运行搜索后，内容位置的数量和搜索结果的估计数量将会显示在搜索弹出页面上。</span><span class="sxs-lookup"><span data-stu-id="c3156-111">After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page.</span></span> <span data-ttu-id="c3156-112">可以快速查看统计信息，例如具有与搜索查询匹配的最多项的内容位置。</span><span class="sxs-lookup"><span data-stu-id="c3156-112">You can quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="c3156-113">运行搜索后，可预览结果或将其导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="c3156-113">After you run a search, you can preview the results or export them to a local computer.</span></span>

## <a name="create-and-run-a-search"></a><span data-ttu-id="c3156-114">创建并运行搜索</span><span class="sxs-lookup"><span data-stu-id="c3156-114">Create and run a search</span></span>

<span data-ttu-id="c3156-115">若要访问 Microsoft 365 合规中心的“**内容搜索**”页面（以运行搜索和预览并导出结果），管理员、合规专员或电子数据展示管理员必须是安全与合规中心的电子数据展示管理员角色组中的成员。</span><span class="sxs-lookup"><span data-stu-id="c3156-115">To access to the **Content search** page in the Microsoft 365 compliance center (to run searches and preview results and export results), an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in Security & Compliance Center.</span></span> <span data-ttu-id="c3156-116">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c3156-116">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="c3156-117">转到 <https://compliance.microsoft.com>，并使用已分配相应权限的帐户凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="c3156-117">Go to <https://compliance.microsoft.com> and sign in using the credentials of an account that's been assigned the appropriate permissions.</span></span>

2. <span data-ttu-id="c3156-118">在 Microsoft 365 合规中心的左侧导航窗格中，单击“**显示所有**”，然后单击“**内容搜索**”。</span><span class="sxs-lookup"><span data-stu-id="c3156-118">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="c3156-119">在“**内容搜索**”页面，单击“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="c3156-119">On the **Content search** page, click **New search**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3156-120">“**按 ID 列表搜索**”选项使你可以使用 Exchange ID 列表搜索特定电子邮件和其他邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="c3156-120">The **Search by ID list** option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="c3156-121">若要创建 ID 列表搜索，你可以提交一个用于标识要搜索的特定邮箱项的逗号分隔符值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="c3156-121">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="c3156-122">有关说明，请参阅 [为 ID 列表搜索准备 CSV 文件](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c3156-122">For instructions, see [Prepare a CSV file for an ID list search](csv-file-for-an-id-list-content-search.md).</span></span>

4. <span data-ttu-id="c3156-123">键入搜索名称以及帮助标识搜索的可选描述。</span><span class="sxs-lookup"><span data-stu-id="c3156-123">Type a name for the search, an optional description that helps identify the search.</span></span> <span data-ttu-id="c3156-124">搜索名称在你的组织中必须保持唯一。</span><span class="sxs-lookup"><span data-stu-id="c3156-124">The name of the search must be unique in your organization.</span></span>

5. <span data-ttu-id="c3156-125">在“**位置**”页面上，选择你希望搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="c3156-125">On the **Locations** page, choose the content locations that you want to search.</span></span> <span data-ttu-id="c3156-126">可以搜索邮箱、站点和公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3156-126">You can search mailboxes, sites, and public folders.</span></span>

    ![选择将其置于保留状态的内容位置](../media/ContentSearchLocations.png)
  
   1. <span data-ttu-id="c3156-128">**Exchange 邮箱**：将切换设置为“**打开**”，然后单击“**选择用户、组或团队**”，以指定要置于保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c3156-128">**Exchange mailboxes**: Set the toggle to **On** and then click **Choose users, groups, or teams** to specify the mailboxes to place on hold.</span></span> <span data-ttu-id="c3156-129">使用搜索框查找用户邮箱和通讯组（将组成员的邮箱置于保留状态）以置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="c3156-129">Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold.</span></span> <span data-ttu-id="c3156-130">可以搜索与 Microsoft Team（适用于频道消息）、Office 365 组和 Yammer 组关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c3156-130">You can also search the mailbox associated with a Microsoft Team (for channel messages), Office 365 Group, and Yammer Group.</span></span> <span data-ttu-id="c3156-131">有关存储在邮箱中的应用程序数据的详细信息，请参阅 [存储在邮箱中的电子数据展示内容](what-is-stored-in-exo-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="c3156-131">For more information about the application data stored in mailboxes, see [Content stored in mailboxes for eDiscovery](what-is-stored-in-exo-mailbox.md).</span></span>

   2. <span data-ttu-id="c3156-132">**SharePoint 站点**：将切换设置为“**打开**”，然后单击“**选择站点** ”，以指定要置于保留状态的 SharePoint 站点和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="c3156-132">**SharePoint sites**: Set the toggle to **On** and then click **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold.</span></span> <span data-ttu-id="c3156-133">键入你想要置于保留状态的每个站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="c3156-133">Type the URL for each site that you want to place on hold.</span></span> <span data-ttu-id="c3156-134">还可以为 Microsoft Team、Office 365 组或 Yammer 组添加 SharePoint 站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="c3156-134">You can also add the URL for the SharePoint site for a Microsoft Team, Office 365 Group, or Yammer Group.</span></span>
  
   3. <span data-ttu-id="c3156-135">**Exchange 公用文件夹**：将切换设置为“**打开**”，从而把 Exchange Online 组织中的所有公用文件夹置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="c3156-135">**Exchange public folders**: Set the toggle to **On** to put all public folders in your Exchange Online organization on hold.</span></span> <span data-ttu-id="c3156-136">无法选择要置于保留状态的特定公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3156-136">You can't choose specific public folders to put on hold.</span></span> <span data-ttu-id="c3156-137">如果不想把公用文件夹置于保留状态，请让切换开关保持关闭。</span><span class="sxs-lookup"><span data-stu-id="c3156-137">Leave the toggle switch off if you don't want to put a hold on public folders.</span></span>
  
   4. <span data-ttu-id="c3156-138">选中此复选框，以搜索本地用户的 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="c3156-138">Keep this checkbox selected to search for Teams content for on-premises users.</span></span> <span data-ttu-id="c3156-139">例如，如果你搜索组织中的所有 Exchange 邮箱并选中此复选框，用于存储本地用户的 Teams 聊天数据的基于云的存储将包括在搜索范围内。</span><span class="sxs-lookup"><span data-stu-id="c3156-139">For example, if you search all Exchange mailboxes in the organization and this checkbox is selected, the cloud-based storage used to store Teams chat data for on-premises users will be included in the scope of the search.</span></span> <span data-ttu-id="c3156-140">有关详细信息，请参阅[搜索本地用户的 Teams 聊天数据](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c3156-140">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

6. <span data-ttu-id="c3156-141">在“**定义搜索条件**”页面上，键入关键字查询，并在必要时将条件添加到搜索查询。</span><span class="sxs-lookup"><span data-stu-id="c3156-141">On the **Define your search conditions** page, type a keyword query and add conditions to the search query if necessary.</span></span>

   ![配置搜索查询](../media/ContentSearchQuery.png)

   1. <span data-ttu-id="c3156-143">指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="c3156-143">Specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="c3156-144">可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="c3156-144">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="c3156-145">如果将关键字框留空，则指定内容位置中的所有内容都将包括在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="c3156-145">If you leave the keyword box empty, all content located in the specified content locations is included in the search results.</span></span> <span data-ttu-id="c3156-146">有关详细信息，请参阅[适用于电子数据展示的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="c3156-146">For more information, see [Keyword queries and search conditions for eDiscovery](keyword-queries-and-search-conditions.md).</span></span>

   2. <span data-ttu-id="c3156-147">或者，可以单击“**显示关键字列表**”复选框，然后在每一行键入一个关键字。</span><span class="sxs-lookup"><span data-stu-id="c3156-147">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="c3156-148">如果执行此操作，则每行上的关键字将由逻辑运算符连接 (**c:s**)，类似于所创建的搜索创建中的 **OR** 运算符功能。</span><span class="sxs-lookup"><span data-stu-id="c3156-148">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span>

      <span data-ttu-id="c3156-149">为什么使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="c3156-149">Why use the keyword list?</span></span> <span data-ttu-id="c3156-150">可以获取与每个关键字匹配的项数量的统计信息。</span><span class="sxs-lookup"><span data-stu-id="c3156-150">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="c3156-151">这可以帮助你快速标识哪些关键字最有效和最无效。</span><span class="sxs-lookup"><span data-stu-id="c3156-151">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="c3156-152">还可以在行中使用关键字短语（使用括号包围）。</span><span class="sxs-lookup"><span data-stu-id="c3156-152">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="c3156-153">有关关键字列表和搜索统计信息的详细信息，请参阅[获取搜索的关键字统计信息](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="c3156-153">For more information about the keyword list and search statistics, see [Get keyword statistics for searches](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span>

      > [!NOTE]
      > <span data-ttu-id="c3156-154">为了帮助减少因海量关键字列表导致的问题，已将关键字列表中的最大行数限制为 20 行。</span><span class="sxs-lookup"><span data-stu-id="c3156-154">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

   3. <span data-ttu-id="c3156-155">可以添加搜索条件来缩小搜索范围并返回更精确的结果集。</span><span class="sxs-lookup"><span data-stu-id="c3156-155">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="c3156-156">每个条件向开始搜索时创建和运行的搜索查询添加一个子句。</span><span class="sxs-lookup"><span data-stu-id="c3156-156">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="c3156-157">可通过使用功能类似于 **AND** 运算符的逻辑运算符 (**c:c**) 在逻辑上将条件连接至关键字查询（在关键字框中指定）。</span><span class="sxs-lookup"><span data-stu-id="c3156-157">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="c3156-158">这意味着，项必须满足关键字查询和要在结果中包括的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="c3156-158">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="c3156-159">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="c3156-159">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="c3156-160">有关可在搜索查询中使用的条件的列表和说明，请参阅[搜索条件](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="c3156-160">For a list and description of conditions that you can use in a search query, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>

7. <span data-ttu-id="c3156-161">查看搜索设置（并在必要时进行编辑），然后提交搜索以开始搜索。</span><span class="sxs-lookup"><span data-stu-id="c3156-161">Review the search settings (and edit if necessary), and then submit the search to start it.</span></span>
  
<span data-ttu-id="c3156-162">若要再次访问此内容搜索或者访问“**内容搜索**”页面上列出的其他内容搜索，请选择搜索，然后单击“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="c3156-162">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c3156-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c3156-163">Next steps</span></span>

<span data-ttu-id="c3156-164">以下是创建并运行内容搜索后要执行的后续步骤列表。</span><span class="sxs-lookup"><span data-stu-id="c3156-164">Here's a list of next steps to perform after you create and run a Content search.</span></span>

- [<span data-ttu-id="c3156-165">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="c3156-165">Preview search results</span></span>](preview-ediscovery-search-results.md)

- [<span data-ttu-id="c3156-166">查看搜索结果的统计信息</span><span class="sxs-lookup"><span data-stu-id="c3156-166">View statistics for search results</span></span>](view-keyword-statistics-for-content-search.md)

- [<span data-ttu-id="c3156-167">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="c3156-167">Export search results</span></span>](export-search-results.md)

- [<span data-ttu-id="c3156-168">导出搜索报告</span><span class="sxs-lookup"><span data-stu-id="c3156-168">Export a search report</span></span>](export-a-content-search-report.md)
