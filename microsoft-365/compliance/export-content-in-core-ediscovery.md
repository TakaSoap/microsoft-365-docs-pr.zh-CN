---
title: 从核心电子数据展示案例导出和下载内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 介绍如何从 Microsoft 365 中的核心电子数据展示案例导出和下载Microsoft 365。
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310834"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="070e7-103">从核心电子数据展示事例导出内容</span><span class="sxs-lookup"><span data-stu-id="070e7-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="070e7-104">成功运行与核心电子数据展示案例关联的搜索后，可以导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="070e7-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="070e7-105">导出搜索结果时，邮箱项目以 PST 文件或单个邮件方式下载。</span><span class="sxs-lookup"><span data-stu-id="070e7-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="070e7-106">从网站和网站SharePoint内容OneDrive for Business，将导出本机文档Office文档和其他文档的副本。</span><span class="sxs-lookup"><span data-stu-id="070e7-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="070e7-107">一Results.csv导出的每个项目的信息的清单文件，以及包含有关每个搜索结果的信息 (XML 格式) 清单文件也导出。</span><span class="sxs-lookup"><span data-stu-id="070e7-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="070e7-108">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="070e7-108">Export search results</span></span>

1. <span data-ttu-id="070e7-109">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后使用已分配有相应电子数据展示权限的用户帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="070e7-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="070e7-110">在合规性中心的左侧导航窗格中，Microsoft 365全部显示"，然后单击"电子数据展示>**核心"。**</span><span class="sxs-lookup"><span data-stu-id="070e7-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="070e7-111">在 **"核心电子数据展示"** 页上，单击要创建保留的案例的名称。</span><span class="sxs-lookup"><span data-stu-id="070e7-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="070e7-112">在案例 **的主页** 上，单击"搜索 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="070e7-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="070e7-113">在弹出 **页** 底部的"操作"菜单上，单击"**导出结果"。**</span><span class="sxs-lookup"><span data-stu-id="070e7-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   !["操作"菜单中的"导出结果"选项](../media/ActionMenuExportResults.png)

   <span data-ttu-id="070e7-115">导出与核心电子数据展示案例关联的搜索结果的工作流与导出内容搜索页面上搜索的 **搜索结果相同** 。</span><span class="sxs-lookup"><span data-stu-id="070e7-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="070e7-116">有关分步说明，请参阅导出 [内容搜索结果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="070e7-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="070e7-117">导出搜索结果时，可以选择启用重复数据删除，以便只导出电子邮件的一个副本，即使搜索到的邮箱中可能找到同一邮件的多个实例。</span><span class="sxs-lookup"><span data-stu-id="070e7-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="070e7-118">有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中 [的重复数据删除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="070e7-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="070e7-119">开始导出后，搜索结果将准备下载，这意味着它们将被转移到 Microsoft 提供Azure 存储 Microsoft 云中的位置。</span><span class="sxs-lookup"><span data-stu-id="070e7-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="070e7-120">如果 **为导出** ，请单击"导出"选项卡以显示导出作业的列表。</span><span class="sxs-lookup"><span data-stu-id="070e7-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![在核心电子数据展示案例的"导出"选项卡上导出作业](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="070e7-122">您可能必须 **单击"刷新** "来更新导出作业的列表，以便它显示您创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="070e7-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="070e7-123">导出作业的名称与相应的搜索同名，_Export搜索名称后面。</span><span class="sxs-lookup"><span data-stu-id="070e7-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="070e7-124">单击创建的导出作业，在飞出页上显示状态信息。</span><span class="sxs-lookup"><span data-stu-id="070e7-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="070e7-125">此信息包括已转移到其他位置Azure 存储百分比。</span><span class="sxs-lookup"><span data-stu-id="070e7-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="070e7-126">在转移所有项目后，单击 **"下载结果** "以将搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="070e7-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="070e7-127">有关下载搜索结果的信息，请参阅导出内容搜索结果中的步骤 2 [](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="070e7-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="070e7-128">有关从案例导出搜索详细信息</span><span class="sxs-lookup"><span data-stu-id="070e7-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="070e7-129">有关导出搜索结果时包含的导出文件详细信息，请参阅导出 [内容搜索报告](export-a-content-search-report.md#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="070e7-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="070e7-130">如果重新启动导出，则任何对搜索查询的更改（这些搜索是导出作业的一部分）不会影响检索到的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="070e7-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="070e7-131">重新启动导出时，将再次运行创建导出作业时运行的相同组合搜索查询作业。</span><span class="sxs-lookup"><span data-stu-id="070e7-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="070e7-132">此外，如果重新启动导出，复制到导出位置的搜索结果Azure 存储之前的结果。</span><span class="sxs-lookup"><span data-stu-id="070e7-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="070e7-133">无法下载以前复制的结果。</span><span class="sxs-lookup"><span data-stu-id="070e7-133">The previous results that were copied won't be available to be downloaded.</span></span>
