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
description: 了解如何在高级电子数据展示中批量计算后使用"测试"选项卡来测试、比较和验证处理的总体质量。
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769167"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="6878f-103">在高级电子数据展示中测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="6878f-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="6878f-104">高级电子数据展示中的"测试"选项卡使您能够测试、比较和验证处理的总体质量。</span><span class="sxs-lookup"><span data-stu-id="6878f-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="6878f-105">这些测试在批计算后执行。</span><span class="sxs-lookup"><span data-stu-id="6878f-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="6878f-106">通过标记集合中的文件，专家可以最终判断每个标记的文件是否与案例相关。</span><span class="sxs-lookup"><span data-stu-id="6878f-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="6878f-107">在单一和多问题方案中，测试通常按问题执行。</span><span class="sxs-lookup"><span data-stu-id="6878f-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="6878f-108">可以在每个测试后查看结果，并且可以使用指定的示例测试文件对测试结果进行重新修改。</span><span class="sxs-lookup"><span data-stu-id="6878f-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="6878f-109">测试其余部分</span><span class="sxs-lookup"><span data-stu-id="6878f-109">Testing the rest</span></span>

<span data-ttu-id="6878f-110">例如，"测试 Rest"测试用于验证剔除决策，以便根据最终高级电子数据展示结果仅查看特定相关性截止分数之上的文件。</span><span class="sxs-lookup"><span data-stu-id="6878f-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="6878f-111">专家查看所选截止分数下的文件示例，以评估该集合中相关文件的数量。</span><span class="sxs-lookup"><span data-stu-id="6878f-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="6878f-112">此测试提供审阅集与"测试 Rest"总体之间的统计信息和比较。</span><span class="sxs-lookup"><span data-stu-id="6878f-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="6878f-113">审阅集的结果由"培训"期间的相关性计算得出的结果。</span><span class="sxs-lookup"><span data-stu-id="6878f-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="6878f-114">结果包括基于设置和输入参数的计算，例如：</span><span class="sxs-lookup"><span data-stu-id="6878f-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="6878f-115">测试示例和标识的相关文件中文件数的示例统计信息。</span><span class="sxs-lookup"><span data-stu-id="6878f-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="6878f-116">审阅集的 Population 参数和 Rest 的表格比较，例如，文件数、相关文件的估计数量、估计的丰富度以及查找其他相关文件的平均成本。</span><span class="sxs-lookup"><span data-stu-id="6878f-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="6878f-117">成本参数设置可以由管理员设置。</span><span class="sxs-lookup"><span data-stu-id="6878f-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="6878f-118">若要运行"测试 Rest"测试：</span><span class="sxs-lookup"><span data-stu-id="6878f-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="6878f-119">打开 **"相关性测试 \> "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6878f-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="6878f-120">在"**测试"** 选项卡中，单击 **"新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="6878f-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="6878f-121">将显示 **"** 创建测试"对话框，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="6878f-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![相关性测试其余结果](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="6878f-123">在 **"测试** 名称" **和"说明**"中，键入名称和说明。</span><span class="sxs-lookup"><span data-stu-id="6878f-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="6878f-124">在" **测试类型** "列表中， **选择"测试 Rest"**</span><span class="sxs-lookup"><span data-stu-id="6878f-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="6878f-125">在 **"问题/类别** "列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="6878f-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="6878f-126">在 **"加载** "列表中，选择负载。</span><span class="sxs-lookup"><span data-stu-id="6878f-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="6878f-127">在 **"读取百** 分比"中，接受默认值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="6878f-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="6878f-128">在 **"设置** 大小"中，或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="6878f-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="6878f-129">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="6878f-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="6878f-130">单击 **"开始"标记**。</span><span class="sxs-lookup"><span data-stu-id="6878f-130">Click **Start tagging**.</span></span> <span data-ttu-id="6878f-131">将生成一个测试示例。</span><span class="sxs-lookup"><span data-stu-id="6878f-131">A test sample is generated.</span></span>

10. <span data-ttu-id="6878f-132">查看并标记"相关性标记"选项卡中的 **\> 每个** 文件，完成后，单击"**计算"。**</span><span class="sxs-lookup"><span data-stu-id="6878f-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="6878f-133">在"测试"选项卡中，可以单击 **"查看结果** "以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="6878f-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="6878f-134">以下屏幕截图中显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="6878f-134">An example is shown in the following screenshot.</span></span>

    ![测试其余结果](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="6878f-136">在上一张屏幕截图中，表的"示例参数"部分包含有关专家标记的示例中的文件数以及该示例中找到的相关文件数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6878f-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="6878f-137">表的"填充参数"部分包含测试结果，包括分数低于选定截止时间的文件的审阅集总体和得分高于选定截止时间的文件的"Rest"总体。</span><span class="sxs-lookup"><span data-stu-id="6878f-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="6878f-138">对于每个总体，将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="6878f-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="6878f-139">包含读取百分比 - 已说明的截止文件</span><span class="sxs-lookup"><span data-stu-id="6878f-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="6878f-140">文件总数</span><span class="sxs-lookup"><span data-stu-id="6878f-140">The total number of files</span></span>

- <span data-ttu-id="6878f-141">相关文件的估计数量</span><span class="sxs-lookup"><span data-stu-id="6878f-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="6878f-142">估计的丰富度</span><span class="sxs-lookup"><span data-stu-id="6878f-142">The estimated richness</span></span>

- <span data-ttu-id="6878f-143">查找其他相关文件的平均审阅成本</span><span class="sxs-lookup"><span data-stu-id="6878f-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="6878f-144">测试切片</span><span class="sxs-lookup"><span data-stu-id="6878f-144">Testing the slice</span></span>

<span data-ttu-id="6878f-145">"测试切片"测试执行的测试与"测试 Rest"测试类似，但与相关性读取 %指定的文件集的段类似。</span><span class="sxs-lookup"><span data-stu-id="6878f-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="6878f-146">若要运行"测试切片"测试：</span><span class="sxs-lookup"><span data-stu-id="6878f-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="6878f-147">打开 **"相关性测试 \> "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6878f-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="6878f-148">在"**测试"** 选项卡中，单击 **"新建测试"。**</span><span class="sxs-lookup"><span data-stu-id="6878f-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="6878f-149">将显示 **"创建** 测试"对话框。</span><span class="sxs-lookup"><span data-stu-id="6878f-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="6878f-150">在 **"测试** 名称和 **说明"中**，键入信息。</span><span class="sxs-lookup"><span data-stu-id="6878f-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="6878f-151">在"**测试类型**"列表中，选择 **"测试切片"。**</span><span class="sxs-lookup"><span data-stu-id="6878f-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="6878f-152">在 **"问题** "列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="6878f-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="6878f-153">在 **"加载** "列表中，选择负载。</span><span class="sxs-lookup"><span data-stu-id="6878f-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="6878f-154">在 **"读取百分比"中**，接受默认的低范围和高范围值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="6878f-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="6878f-155">在 **"设置** 大小"中，选择一个值或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="6878f-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="6878f-156">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="6878f-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="6878f-157">单击 **"开始"标记**。</span><span class="sxs-lookup"><span data-stu-id="6878f-157">Click **Start tagging**.</span></span> <span data-ttu-id="6878f-158">将生成一个测试示例。</span><span class="sxs-lookup"><span data-stu-id="6878f-158">A test sample is generated.</span></span>

10. <span data-ttu-id="6878f-159">查看并标记"相关性标记"选项卡中的 **\> 每个** 文件，完成后，单击"**计算"。**</span><span class="sxs-lookup"><span data-stu-id="6878f-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="6878f-160">在"测试"选项卡中，可以单击 **"查看结果** "以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="6878f-160">In the Test tab, you can click **View results** to see the test results.</span></span>
