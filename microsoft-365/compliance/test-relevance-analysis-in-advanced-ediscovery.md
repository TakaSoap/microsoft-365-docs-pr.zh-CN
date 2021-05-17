---
title: 在高级电子数据展示中测试相关性分析
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在高级电子数据展示中批量计算后使用"测试"选项卡来测试、比较和验证总体处理质量。
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769167"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="bfb5b-103">在高级电子数据展示中测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="bfb5b-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="bfb5b-104">高级电子数据展示中的"测试"选项卡使您能够测试、比较和验证总体处理质量。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="bfb5b-105">这些测试在批计算后执行。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="bfb5b-106">通过标记集合中的文件，专家可以最终判断每个标记的文件是否与案例相关。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="bfb5b-107">在单问题和多问题方案中，测试通常按问题执行。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="bfb5b-108">可以在每个测试之后查看结果，并且可以使用指定的示例测试文件对测试结果进行重新修改。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="bfb5b-109">测试其余部分</span><span class="sxs-lookup"><span data-stu-id="bfb5b-109">Testing the rest</span></span>

<span data-ttu-id="bfb5b-110">例如，"测试 Rest"测试用于验证剔除决策，以便根据最终的高级电子数据展示结果仅查看特定相关性截止分数之上的文件。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="bfb5b-111">专家查看选定截止分数下的文件示例，以评估该集合中相关文件的数量。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="bfb5b-112">此测试提供"审阅集"和"测试 Rest"总体之间的统计信息和比较。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="bfb5b-113">审阅集的结果由培训期间相关性计算的结果。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="bfb5b-114">结果包括基于设置和输入参数的计算，例如：</span><span class="sxs-lookup"><span data-stu-id="bfb5b-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="bfb5b-115">测试样本中文件数和确定的相关文件数的统计信息示例。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="bfb5b-116">审阅集和 Rest 的 Population 参数的表格比较，例如文件数、相关文件的估计数量、估计的丰富度以及查找其他相关文件的平均成本。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="bfb5b-117">成本参数设置由管理员设置。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="bfb5b-118">若要运行"测试 Rest"测试：</span><span class="sxs-lookup"><span data-stu-id="bfb5b-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="bfb5b-119">打开 **"相关性测试 \> "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="bfb5b-120">在"**测试"** 选项卡中，单击"**新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="bfb5b-121">将显示 **"** 创建测试"对话框，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![相关性测试其余结果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="bfb5b-123">在 **"测试名称**"和" **说明**"中，键入名称和说明。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="bfb5b-124">在" **测试类型"** 列表中，选择 **"测试其余内容"**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="bfb5b-125">在" **问题/类别** "列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="bfb5b-126">在" **加载** "列表中，选择加载。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="bfb5b-127">在 **"读取百** 分比"中，接受默认值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="bfb5b-128">在 **"设置大小**"中，或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="bfb5b-129">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="bfb5b-130">单击 **"开始标记"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-130">Click **Start tagging**.</span></span> <span data-ttu-id="bfb5b-131">将生成一个测试示例。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-131">A test sample is generated.</span></span>

10. <span data-ttu-id="bfb5b-132">查看并标记"相关性标记"选项卡中的 **\>** 每个文件，完成后，单击"计算 **"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="bfb5b-133">在"测试"选项卡中，可以单击 **"** 查看结果"以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="bfb5b-134">以下屏幕截图中显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-134">An example is shown in the following screenshot.</span></span>

    ![测试其余结果](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="bfb5b-136">在上一张屏幕截图中，表的 **"示例** 参数"部分包含有关专家标记的示例中文件数以及该示例中找到的相关文件数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="bfb5b-137">表的 **Population** 参数部分包含测试结果，包括分数低于选定截止时间的审阅集文件总体和分数高于选定截止时间的文件的"其余"总体。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="bfb5b-138">对于每个总体，将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="bfb5b-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="bfb5b-139">包含具有读取百分比 - 已说明截止的文件</span><span class="sxs-lookup"><span data-stu-id="bfb5b-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="bfb5b-140">文件总数</span><span class="sxs-lookup"><span data-stu-id="bfb5b-140">The total number of files</span></span>

- <span data-ttu-id="bfb5b-141">估计的相关文件数</span><span class="sxs-lookup"><span data-stu-id="bfb5b-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="bfb5b-142">估计的丰富程度</span><span class="sxs-lookup"><span data-stu-id="bfb5b-142">The estimated richness</span></span>

- <span data-ttu-id="bfb5b-143">查找其他相关文件的平均审阅成本</span><span class="sxs-lookup"><span data-stu-id="bfb5b-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="bfb5b-144">测试切片</span><span class="sxs-lookup"><span data-stu-id="bfb5b-144">Testing the slice</span></span>

<span data-ttu-id="bfb5b-145">"测试切片"测试执行的测试类似于"测试 Rest"测试，但执行到相关性读取 %指定的文件段。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="bfb5b-146">若要运行"测试切片"测试：</span><span class="sxs-lookup"><span data-stu-id="bfb5b-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="bfb5b-147">打开 **"相关性测试 \> "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="bfb5b-148">在"**测试"** 选项卡中，单击"**新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="bfb5b-149">将显示 **"创建** 测试"对话框。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="bfb5b-150">在 **"测试名称和\*\*\*\*说明"** 中，键入信息。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="bfb5b-151">在"**测试类型"** 列表中，选择 **"测试切片"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="bfb5b-152">在" **问题** "列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="bfb5b-153">在" **加载** "列表中，选择加载。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="bfb5b-154">在 **"读取 % between"** 中，接受默认的低/高范围值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="bfb5b-155">在 **"设置** 大小"中，选择一个值或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="bfb5b-156">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="bfb5b-157">单击 **"开始标记"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-157">Click **Start tagging**.</span></span> <span data-ttu-id="bfb5b-158">将生成一个测试示例。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-158">A test sample is generated.</span></span>

10. <span data-ttu-id="bfb5b-159">查看并标记"相关性标记"选项卡中的 **\>** 每个文件，完成后，单击"计算 **"。**</span><span class="sxs-lookup"><span data-stu-id="bfb5b-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="bfb5b-160">在"测试"选项卡中，可以单击 **"** 查看结果"以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-160">In the Test tab, you can click **View results** to see the test results.</span></span>
