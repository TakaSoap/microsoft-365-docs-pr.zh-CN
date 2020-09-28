---
title: 创建提取程序
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft SharePoint Syntex 中创建提取程序。
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295452"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="3b054-103">创建提取程序 (预览) </span><span class="sxs-lookup"><span data-stu-id="3b054-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="3b054-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="3b054-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="3b054-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="3b054-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="3b054-106">在创建分类器模型以自动进行特定文档类型的标识和分类之后，您可以选择将提取程序添加到您的模型中，以从这些文档中提取特定信息。</span><span class="sxs-lookup"><span data-stu-id="3b054-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="3b054-107">例如，您可能需要您的模型不仅标识所有添加到文档库中的 *合同续订* 文档，还可以将每个文档的 *服务开始日期* 显示为文档库中的一列。</span><span class="sxs-lookup"><span data-stu-id="3b054-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="3b054-108">您需要为要提取的文档中的每个实体创建一个提取程序。</span><span class="sxs-lookup"><span data-stu-id="3b054-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="3b054-109">在示例中，您想要提取由模型标识的每个*合同续订*文档的*服务开始日期*。</span><span class="sxs-lookup"><span data-stu-id="3b054-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="3b054-110">当您想要查看所有 *合同续订* 文档的文档库中的视图时，如果该列显示每个文档的服务开始日期值，则必须发生此情况。</span><span class="sxs-lookup"><span data-stu-id="3b054-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="3b054-111">在创建提取程序之前，您需要 [添加示例文件](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) ，以帮助训练模型以确定要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="3b054-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="3b054-112">使用用于创建分类器的相同示例文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="3b054-113">命名您的提取程序</span><span class="sxs-lookup"><span data-stu-id="3b054-113">Name your extractor</span></span>

1. <span data-ttu-id="3b054-114">在模型主页中的 " **创建和培训提取程序** " 磁贴中，单击 " **训练提取**程序"。</span><span class="sxs-lookup"><span data-stu-id="3b054-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="3b054-115">在 " **新建实体提取** 程序" 屏幕上，在 " **新的提取程序名称** " 字段中键入提取程序的名称。</span><span class="sxs-lookup"><span data-stu-id="3b054-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="3b054-116">例如，如果您想要从每个合同续订文档中提取服务开始日期，请将 it **服务开始日期** 命名为 "名称"。</span><span class="sxs-lookup"><span data-stu-id="3b054-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="3b054-117">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="3b054-118">添加标签</span><span class="sxs-lookup"><span data-stu-id="3b054-118">Add a label</span></span>

<span data-ttu-id="3b054-119">下一步是在示例培训文件中标记要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="3b054-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="3b054-120">创建提取器将打开 "提取程序" 页。</span><span class="sxs-lookup"><span data-stu-id="3b054-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="3b054-121">在这里，你将看到示例文件的列表，并在查看器中显示列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="3b054-122">从查看器中，选择要从文件中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="3b054-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="3b054-123">例如，如果要提取 " *开始服务日期*"，请突出显示第一个文件中的日期值 (*星期一，2019) 年10月 14* 日。</span><span class="sxs-lookup"><span data-stu-id="3b054-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="3b054-124">，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-124">and then click **Save**.</span></span>  <span data-ttu-id="3b054-125">您应该会看到值显示在 "标记的示例" 列表中的 " **标签** " 列下的文件中。</span><span class="sxs-lookup"><span data-stu-id="3b054-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="3b054-126">选择 " **下一个文件** " 以自动保存，并在查看器中打开列表中的下一个文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="3b054-127">或者选择 " **保存** "，然后从 " **标记的示例** " 列表中选择另一个文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="3b054-128">在查看器中，重复步骤1和2，然后重复执行，直到将标签保存到所有五个文件中。</span><span class="sxs-lookup"><span data-stu-id="3b054-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![高级设置](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="3b054-130">添加一个否定性示例</span><span class="sxs-lookup"><span data-stu-id="3b054-130">Add a negative example</span></span>

<span data-ttu-id="3b054-131">与在创建分类器时添加负示例文件的方式类似，您需要为提取器添加一个负样本。</span><span class="sxs-lookup"><span data-stu-id="3b054-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="3b054-132">它应该是一个不包含 "服务开始" 日期值的文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="3b054-133">从 " **标记的示例** " 列表中，选择一个负的示例。</span><span class="sxs-lookup"><span data-stu-id="3b054-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="3b054-134">在文章顶部的 "查看器" 中，选择 " **不存在标签**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="3b054-135">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-135">Click **Save**.</span></span>
 
<span data-ttu-id="3b054-136">标记了5个文件后，会显示一条通知横幅，告知你转到 "培训"。</span><span class="sxs-lookup"><span data-stu-id="3b054-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="3b054-137">你可以选择更多文档或推进培训。</span><span class="sxs-lookup"><span data-stu-id="3b054-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="3b054-138">添加说明</span><span class="sxs-lookup"><span data-stu-id="3b054-138">Add an explanation</span></span>

<span data-ttu-id="3b054-139">在该示例中，您将创建一个说明，以提供有关实体格式本身以及它在示例文档中可能具有的变体的提示。</span><span class="sxs-lookup"><span data-stu-id="3b054-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="3b054-140">例如，日期值可以是多种不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="3b054-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="3b054-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="3b054-141">10/14/2019</span></span>
- <span data-ttu-id="3b054-142">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="3b054-142">October 14, 2019</span></span>
- <span data-ttu-id="3b054-143">2019年10月14日星期一</span><span class="sxs-lookup"><span data-stu-id="3b054-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="3b054-144">为了帮助确定 *服务开始日期* ，您创建了一个模式说明。</span><span class="sxs-lookup"><span data-stu-id="3b054-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="3b054-145">在 "说明" 部分，选择 " **新建** "，然后键入名称 (例如， *Date*) 。</span><span class="sxs-lookup"><span data-stu-id="3b054-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="3b054-146">对于 "类型"，选择 " **模式列表**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="3b054-147">对于 "值"，提供在示例文件中显示的日期变体。</span><span class="sxs-lookup"><span data-stu-id="3b054-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="3b054-148">例如，如果您的日期格式显示为0/00/0000，则输入文档中出现的任何变体，如：</span><span class="sxs-lookup"><span data-stu-id="3b054-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="3b054-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="3b054-149">0/0/0000</span></span>
    - <span data-ttu-id="3b054-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="3b054-150">0/00/0000</span></span>
    - <span data-ttu-id="3b054-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="3b054-151">00/0/0000</span></span>
    - <span data-ttu-id="3b054-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="3b054-152">00/00/0000</span></span>
4. <span data-ttu-id="3b054-153">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="3b054-154">使用解释库</span><span class="sxs-lookup"><span data-stu-id="3b054-154">Use the Explanation library</span></span>

<span data-ttu-id="3b054-155">若要创建对日期等项目的说明，使用说明库要比手动输入所有变体更简单。</span><span class="sxs-lookup"><span data-stu-id="3b054-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="3b054-156">解释库是一组预构建的短语和模式说明。</span><span class="sxs-lookup"><span data-stu-id="3b054-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="3b054-157">库提供了常见短语或模式列表的所有格式，如日期、电话号码、邮政编码等。</span><span class="sxs-lookup"><span data-stu-id="3b054-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="3b054-158">在 " *服务开始日期* " 示例中，使用 "解释" 库中的 *日期* 的预生成说明更有效：</span><span class="sxs-lookup"><span data-stu-id="3b054-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="3b054-159">在 " **说明" 部分**，选择 " **新建**"，然后选择 " **来自解释库**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="3b054-160">从 "解释" 库中，选择 " **日期**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="3b054-161">您可以查看可识别的日期的所有变体。</span><span class="sxs-lookup"><span data-stu-id="3b054-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="3b054-162">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-162">Select **Add**.</span></span></br>

    ![解释库](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="3b054-164">在 " **创建说明** " 页面上，"解释" 库中的 *日期* 信息将自动填充字段。</span><span class="sxs-lookup"><span data-stu-id="3b054-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="3b054-165">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-165">Select **Save**.</span></span></br>

    ![Date](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="3b054-167">训练模型</span><span class="sxs-lookup"><span data-stu-id="3b054-167">Train the model</span></span> 

<span data-ttu-id="3b054-168">保存您的说明开始培训。</span><span class="sxs-lookup"><span data-stu-id="3b054-168">Saving your explanation start the training.</span></span> <span data-ttu-id="3b054-169">如果您的模型有足够的信息从标记的示例文件中提取数据，您将看到标记为 " **匹配**" 的每个文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="3b054-171">如果说明没有足够的信息来查找要提取的数据，则每个文件都将标记为 **不匹配**。</span><span class="sxs-lookup"><span data-stu-id="3b054-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="3b054-172">您可以单击不 **匹配** 的文件以查看有关为何不匹配的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b054-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="3b054-173">添加另一个说明</span><span class="sxs-lookup"><span data-stu-id="3b054-173">Add another explanation</span></span>

<span data-ttu-id="3b054-174">通常，不匹配是指我们提供的解释没有提供足够的信息，无法提取服务开始日期值以匹配我们标记的文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="3b054-175">您可能需要对其进行编辑或添加其他说明。</span><span class="sxs-lookup"><span data-stu-id="3b054-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="3b054-176">对于此示例，请注意，文本字符串的 *开始服务日期* 始终在实际值之前。</span><span class="sxs-lookup"><span data-stu-id="3b054-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="3b054-177">若要帮助确定服务的开始日期，您需要创建短语说明。</span><span class="sxs-lookup"><span data-stu-id="3b054-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="3b054-178">在 "说明" 部分，选择 " **新建**"，然后键入名称 (例如， *前缀 String*) 。</span><span class="sxs-lookup"><span data-stu-id="3b054-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="3b054-179">对于 "类型"，选择 " **短语列表**"。</span><span class="sxs-lookup"><span data-stu-id="3b054-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="3b054-180">使用 *服务开始日期* 作为值。</span><span class="sxs-lookup"><span data-stu-id="3b054-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="3b054-181">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3b054-181">Select **Save**.</span></span>

    ![前缀字符串](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="3b054-183">再次训练模型</span><span class="sxs-lookup"><span data-stu-id="3b054-183">Train the model again</span></span>

<span data-ttu-id="3b054-184">保存说明再次开始进行训练，这次在示例中使用这两个说明。</span><span class="sxs-lookup"><span data-stu-id="3b054-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="3b054-185">如果您的模型具有足够的信息，可以从标记的示例文件中提取数据，则会看到标记为 " **匹配**" 的每个文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="3b054-186">如果再次收到带标签的文件的 **不匹配** 项，则可能需要创建另一个说明，以提供模型以详细了解该文档类型，或考虑对示例模型进行更改。</span><span class="sxs-lookup"><span data-stu-id="3b054-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="3b054-187">测试模型</span><span class="sxs-lookup"><span data-stu-id="3b054-187">Test your model</span></span>

<span data-ttu-id="3b054-188">如果您在标记的示例文件中接收到匹配项，则现在可以在其余未标记的示例文件上测试模型。</span><span class="sxs-lookup"><span data-stu-id="3b054-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="3b054-189">在模型主页中，单击 " **测试** " 选项卡。 这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="3b054-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="3b054-190">在 " **测试文件** " 列表中，如果模型能够提取所需的信息，则显示示例文件。</span><span class="sxs-lookup"><span data-stu-id="3b054-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="3b054-191">使用此信息有助于在识别文档时确定分类程序的有效性。</span><span class="sxs-lookup"><span data-stu-id="3b054-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![对文件进行测试](../media/content-understanding/test-filies-extractor.png) 
