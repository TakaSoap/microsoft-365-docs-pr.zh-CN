---
title: 准备用于 ID 列表内容搜索的 CSV 文件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: 使用现有内容搜索中的 CSV 文件创建返回特定电子邮件项目的 ID 列表搜索。
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311530"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="fff53-103">准备用于 ID 列表内容搜索的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="fff53-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="fff53-104">可以使用特定邮箱电子邮件和其他邮箱项的列表来搜索Exchange条目。</span><span class="sxs-lookup"><span data-stu-id="fff53-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="fff53-105">若要创建 ID 列表搜索，你可以提交一个用于标识要搜索的特定邮箱项的逗号分隔符值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="fff53-106">对于此 CSV 文件，使用 **Results.csv** 文件或在您导出内容搜索结果或从现有内容搜索导出内容搜索报告时包含的 **Unindexed Items.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="fff53-107">然后，编辑其中一个文件以指示要搜索的特定项目、创建新的 ID 列表搜索并提交 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="fff53-108">**为什么要创建 ID 列表搜索？**</span><span class="sxs-lookup"><span data-stu-id="fff53-108">**Why create an ID list search?**</span></span> <span data-ttu-id="fff53-109">如果无法确定项目是否根据 **Results.csv** 或 **Unindexed Items.csv** 文件的元数据响应电子数据展示请求，可以使用 ID 列表搜索来查找、预览该项目，然后导出该项目以确定该项目是否响应正在调查的案例。</span><span class="sxs-lookup"><span data-stu-id="fff53-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="fff53-110">ID 列表搜索通常用于搜索和返回一组特定的未索引项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="fff53-111">以下是创建 ID 列表搜索的过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="fff53-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="fff53-112">在合规性中心创建并运行Microsoft 365搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="fff53-113">导出内容搜索结果或内容搜索报告。</span><span class="sxs-lookup"><span data-stu-id="fff53-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="fff53-114">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="fff53-114">For more information, see:</span></span>

    - [<span data-ttu-id="fff53-115">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="fff53-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="fff53-116">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="fff53-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="fff53-117">编辑 **Results.csv** 文件或 **Unindexed Items.csv** 文件，并确定要包括在 ID 列表搜索中的特定邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="fff53-118">请参阅 [为](#prepare-the-csv-file-for-an-id-list-search) ID 列表搜索准备 CSV 文件的说明。</span><span class="sxs-lookup"><span data-stu-id="fff53-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="fff53-119">创建新的 ID 列表搜索 (查看 [) ](#create-an-id-list-search) 并提交您准备的 CSV 文件的说明。</span><span class="sxs-lookup"><span data-stu-id="fff53-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="fff53-120">创建的搜索查询将仅搜索 CSV 文件中所选的项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="fff53-121">仅邮箱项目支持 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="fff53-122">在 ID 列表搜索SharePoint OneDrive搜索文档和文档。</span><span class="sxs-lookup"><span data-stu-id="fff53-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="fff53-123">准备用于 ID 列表搜索的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="fff53-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="fff53-124">导出搜索结果或搜索报告后，执行以下步骤以准备用于 ID 列表搜索的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="fff53-125">此 CSV 文件标识 ID 列表搜索中的每个项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="fff53-126">可以从搜索（包括网站和帐户SharePoint CSV 文件OneDrive，但只能选择用于 ID 列表搜索的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="fff53-127">如果在文档或搜索SharePoint中选择OneDrive，则创建 ID 列表搜索时 CSV 文件验证失败。</span><span class="sxs-lookup"><span data-stu-id="fff53-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="fff53-128">在Results.csv **打开\*\*\*\*"未** Items.csv索引Excel。</span><span class="sxs-lookup"><span data-stu-id="fff53-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="fff53-129">在 **"所选\*\*\*\*"列中，** 在对应于要搜索的项目的单元格中键入"是"。</span><span class="sxs-lookup"><span data-stu-id="fff53-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="fff53-130">对要搜索的每个项目重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="fff53-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fff53-131">当您在"文档 ID"Excel中打开 CSV 文件时，"文档 **ID"** 列的数据格式可能已更改为 **"常规"。**</span><span class="sxs-lookup"><span data-stu-id="fff53-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="fff53-132">这导致以科学表示法显示项目的文档 ID。</span><span class="sxs-lookup"><span data-stu-id="fff53-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="fff53-133">例如，文档 ID"481037338205"显示为"4.81037E+11"。</span><span class="sxs-lookup"><span data-stu-id="fff53-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="fff53-134">如果发生这种情况，您必须执行以下步骤以将"文档 **ID"** 列的数据格式更改为 **"** 数字"，以还原文档 ID 的正确格式。</span><span class="sxs-lookup"><span data-stu-id="fff53-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="fff53-135">如果不这样做，则使用 CSV 文件的 ID 列表搜索将失败。</span><span class="sxs-lookup"><span data-stu-id="fff53-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="fff53-136">右键单击整个"**文档 ID"** 列，然后选择"**设置单元格格式"。**</span><span class="sxs-lookup"><span data-stu-id="fff53-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="fff53-137">在"**类别"** 框中，单击"**数字"。**</span><span class="sxs-lookup"><span data-stu-id="fff53-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="fff53-138">将小数位数更改为 **0，** 然后单击 **"确定"** 保存更改。</span><span class="sxs-lookup"><span data-stu-id="fff53-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="fff53-139">请注意，"文档 ID"列中的值将更改为数字。</span><span class="sxs-lookup"><span data-stu-id="fff53-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="fff53-140">下面是准备提交用于 ID 列表内容搜索的 CSV 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="fff53-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![目标内容搜索的 CSV 文件示例](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="fff53-142">保存 CSV 文件或使用 **另存为** 保存文件，文件名不同。</span><span class="sxs-lookup"><span data-stu-id="fff53-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="fff53-143">在这两种情况下，请务必使用 CSV 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="fff53-144">创建 ID 列表搜索</span><span class="sxs-lookup"><span data-stu-id="fff53-144">Create an ID list search</span></span>

<span data-ttu-id="fff53-145">下一步是创建新的 ID 列表搜索并提交你在上一步中准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fff53-146">应在导出搜索结果或报告后的 2 天内创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="fff53-147">如果导出的搜索结果或报告超过 2 天，应重新导出搜索结果或报告以生成更新的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="fff53-148">然后，你可以准备其中一个更新的 CSV 文件，并使用它创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="fff53-149">转到 <https://compliance.microsoft.com> 并登录。</span><span class="sxs-lookup"><span data-stu-id="fff53-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="fff53-150">在 Microsoft 365 合规中心的左侧导航窗格中，单击“**显示所有**”，然后单击“**内容搜索**”。</span><span class="sxs-lookup"><span data-stu-id="fff53-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="fff53-151">在"**内容搜索"页上**，单击"**按 ID 列表搜索"。**</span><span class="sxs-lookup"><span data-stu-id="fff53-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="fff53-152">在"**按 ID 搜索** 列表"飞出菜单上，将搜索 (并选择描述它) 然后单击"浏览"，然后选择在上一步中准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="fff53-153">Microsoft 365尝试验证 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="fff53-154">如果验证失败，则会显示一条错误消息，可帮助您解决验证错误。</span><span class="sxs-lookup"><span data-stu-id="fff53-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="fff53-155">CSV 文件必须成功验证，以创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="fff53-156">成功验证 CSV 文件后，单击" **搜索** "创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="fff53-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="fff53-157">下面是 ID 列表搜索中的飞出页示例，其中显示生成的查询和搜索结果的估计数量。</span><span class="sxs-lookup"><span data-stu-id="fff53-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![ID 列表搜索的搜索查询](../media/SearchIDListFlyout.png)

    <span data-ttu-id="fff53-159">在 ID 搜索的统计信息中显示的估计项目数应该与 CSV 文件中所选的项目数相匹配。</span><span class="sxs-lookup"><span data-stu-id="fff53-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="fff53-160">预览或导出 ID 列表搜索返回的项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="fff53-161">更多信息</span><span class="sxs-lookup"><span data-stu-id="fff53-161">More information</span></span>

<span data-ttu-id="fff53-162">如果在创建 ID 列表搜索后移动邮箱，则搜索的查询不会返回指定的项目。</span><span class="sxs-lookup"><span data-stu-id="fff53-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="fff53-163">这是因为移动邮箱时更改了邮箱项目的 **DocumentId** 属性。</span><span class="sxs-lookup"><span data-stu-id="fff53-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="fff53-164">在极少数情况下，当您创建 ID 列表搜索后移动邮箱时，您应创建新的内容搜索 (或更新现有搜索) 然后导出搜索结果或报告以生成可用于创建新的 ID 列表搜索的更新 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="fff53-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
