---
title: '创建提取程序 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何创建提取程序
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612758"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="d6958-103">创建提取程序 (预览) </span><span class="sxs-lookup"><span data-stu-id="d6958-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="d6958-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="d6958-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d6958-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="d6958-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="d6958-106">在创建分类器模型以自动进行特定文档类型的标识和分类之后，您可以选择将提取程序添加到您的模型中，以从这些文档中提取特定信息。</span><span class="sxs-lookup"><span data-stu-id="d6958-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="d6958-107">例如，您可能需要您的模型不仅标识已添加到文档库中的所有*合同续订*文档，还可将每个文档的*服务开始日期*显示为文档库中的一列。</span><span class="sxs-lookup"><span data-stu-id="d6958-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="d6958-108">您需要为要提取的文档中的每个实体创建一个提取程序。</span><span class="sxs-lookup"><span data-stu-id="d6958-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="d6958-109">在我们的示例中，我们想要提取由模型标识的每个*合同续订*文档的*服务开始日期*。</span><span class="sxs-lookup"><span data-stu-id="d6958-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="d6958-110">我们希望能够在所有*合同续订*文档的文档库中查看视图，并显示一个显示每个文档的服务开始日期值的列。</span><span class="sxs-lookup"><span data-stu-id="d6958-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="d6958-111">在创建提取程序之前，您需要添加您需要的[示例文件](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files)，以帮助培训模型以确定要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="d6958-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="d6958-112">使用用于创建分类器的相同示例文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="d6958-113">命名您的提取程序</span><span class="sxs-lookup"><span data-stu-id="d6958-113">Name your extractor</span></span>

1. <span data-ttu-id="d6958-114">在模型主页上的 "**创建和培训提取程序**" 磁贴中，单击 "**训练提取**程序"。</span><span class="sxs-lookup"><span data-stu-id="d6958-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="d6958-115">在 "**新建实体提取**程序" 屏幕上，在 "**新的提取程序名称**" 字段中键入提取程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d6958-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="d6958-116">例如，如果我们想要从每个合同续订文档中提取服务开始日期，我们可以将 it**服务开始日期**命名为 "名称"。</span><span class="sxs-lookup"><span data-stu-id="d6958-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="d6958-117">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="d6958-118">添加标签</span><span class="sxs-lookup"><span data-stu-id="d6958-118">Add a label</span></span>

<span data-ttu-id="d6958-119">下一步是在示例培训文件中标记要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="d6958-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="d6958-120">创建提取程序将打开 "提取程序" 页，您将在其中看到示例文件的列表，并在查看器中显示列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="d6958-121">在查看器中，选择要从文件中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="d6958-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="d6958-122">例如，如果要提取 "*开始" 服务日期*，您将在第一个文件中突出显示该日期的日期值 (*2019) 年10月14日星期一*的第一个文件中。</span><span class="sxs-lookup"><span data-stu-id="d6958-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="d6958-123">然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-123">Then click **Save**.</span></span>  <span data-ttu-id="d6958-124">您将在 "**标签**" 列下的 "标记的示例" 列表中看到该文件的值显示。</span><span class="sxs-lookup"><span data-stu-id="d6958-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="d6958-125">选择 "**下一个文件**" 以自动保存并打开查看器列表中的下一个文件，也可以选择 "**保存**"，然后从 "**标记的示例**" 列表中选择另一个文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="d6958-126">在查看器中，重复步骤1和步骤2，在将标签保存到五个文件中之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d6958-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![高级设置](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="d6958-128">添加一个否定性示例</span><span class="sxs-lookup"><span data-stu-id="d6958-128">Add a negative example</span></span>

<span data-ttu-id="d6958-129">与在创建分类器时添加负示例文件的方式类似，您需要为提取器添加一个负的示例。</span><span class="sxs-lookup"><span data-stu-id="d6958-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="d6958-130">对于我们的示例，它应是一个不包含服务开始日期值的文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="d6958-131">从 "**标记的示例**" 列表中，选择一个负的示例。</span><span class="sxs-lookup"><span data-stu-id="d6958-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="d6958-132">在查看器中，在文章顶部，选择 "**不存在标签**"。</span><span class="sxs-lookup"><span data-stu-id="d6958-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="d6958-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-133">Click **Save**.</span></span>
 
<span data-ttu-id="d6958-134">标记了5个文件后，会显示一条通知横幅，告知您转到 "培训"。</span><span class="sxs-lookup"><span data-stu-id="d6958-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="d6958-135">你可以选择更多文档或推进培训。</span><span class="sxs-lookup"><span data-stu-id="d6958-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="d6958-136">添加说明</span><span class="sxs-lookup"><span data-stu-id="d6958-136">Add an explanation</span></span>

<span data-ttu-id="d6958-137">对于我们的示例，我们将创建一个说明，该说明提供有关实体格式本身以及示例文档中可能存在的变体的提示。</span><span class="sxs-lookup"><span data-stu-id="d6958-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="d6958-138">例如，日期值可以是多种不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="d6958-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="d6958-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="d6958-139">10/14/2019</span></span>
- <span data-ttu-id="d6958-140">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d6958-140">October 14, 2019</span></span>
- <span data-ttu-id="d6958-141">2019年10月14日星期一</span><span class="sxs-lookup"><span data-stu-id="d6958-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="d6958-142">若要帮助确定*服务开始日期*，可以创建模式说明。</span><span class="sxs-lookup"><span data-stu-id="d6958-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="d6958-143">在 "说明" 部分，选择 "**新建**"，然后键入名称 (例如， *Date*) 。</span><span class="sxs-lookup"><span data-stu-id="d6958-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="d6958-144">对于 "类型"，选择 "**模式列表**"。</span><span class="sxs-lookup"><span data-stu-id="d6958-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="d6958-145">对于值，需要提供在示例文件中显示的日期变体。</span><span class="sxs-lookup"><span data-stu-id="d6958-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="d6958-146">例如，如果您的日期格式显示为 "0/00/0000"，则可以在文档中输入可能出现的任何变体，如：</span><span class="sxs-lookup"><span data-stu-id="d6958-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="d6958-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="d6958-147">0/0/0000</span></span>
    - <span data-ttu-id="d6958-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="d6958-148">0/00/0000</span></span>
    - <span data-ttu-id="d6958-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="d6958-149">00/0/0000</span></span>
    - <span data-ttu-id="d6958-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="d6958-150">00/00/0000</span></span>
4. <span data-ttu-id="d6958-151">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="d6958-152">使用解释库</span><span class="sxs-lookup"><span data-stu-id="d6958-152">Use the Explanation library</span></span>

<span data-ttu-id="d6958-153">若要创建对日期等事物的说明，使用说明库要比手动输入所有变体更简单。</span><span class="sxs-lookup"><span data-stu-id="d6958-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="d6958-154">解释库是一组预构建的短语和模式说明。</span><span class="sxs-lookup"><span data-stu-id="d6958-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="d6958-155">库尝试为常见短语或模式列表提供所有格式，如日期、电话号码、邮政编码和许多其他。</span><span class="sxs-lookup"><span data-stu-id="d6958-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="d6958-156">对于我们的*服务开始日期*示例，在解释库中使用预构建的*日期*说明更有效：</span><span class="sxs-lookup"><span data-stu-id="d6958-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="d6958-157">在 "**说明" 部分**，\* \* 选择 "**新建**"，然后选择 "**来自解释库**"。</span><span class="sxs-lookup"><span data-stu-id="d6958-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="d6958-158">从 "解释" 库中，选择 "**日期**"。</span><span class="sxs-lookup"><span data-stu-id="d6958-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="d6958-159">您可以查看将识别的日期的所有变体。</span><span class="sxs-lookup"><span data-stu-id="d6958-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="d6958-160">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-160">Select **Add**.</span></span></br>

    ![解释库](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="d6958-162">在 "**创建说明**" 页面上，"解释" 库中的*日期*信息将自动填充字段。</span><span class="sxs-lookup"><span data-stu-id="d6958-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="d6958-163">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-163">Select **Save**.</span></span></br>

    ![解释库](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="d6958-165">训练模型</span><span class="sxs-lookup"><span data-stu-id="d6958-165">Train the model</span></span> 

<span data-ttu-id="d6958-166">保存您的说明将开始进行培训。</span><span class="sxs-lookup"><span data-stu-id="d6958-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="d6958-167">如果您的模型有足够的信息从标记的示例文件中提取数据，您将看到标记为 "**匹配**" 的每个文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![解释库](../media/content-understanding/match2.png) 

<span data-ttu-id="d6958-169">如果说明没有足够的信息来查找要提取的数据，则每个文件都将标记为**不匹配**。</span><span class="sxs-lookup"><span data-stu-id="d6958-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="d6958-170">您可以单击不匹配的文件以查看有关为何不匹配的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6958-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="d6958-171">添加另一个说明</span><span class="sxs-lookup"><span data-stu-id="d6958-171">Add another explanation</span></span>

<span data-ttu-id="d6958-172">通常，不匹配是指我们提供的解释没有提供足够的信息，无法提取服务开始日期值以匹配我们标记的文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="d6958-173">您可能需要对其进行编辑或添加其他说明。</span><span class="sxs-lookup"><span data-stu-id="d6958-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="d6958-174">对于我们的示例，我们注意到文本字符串的*开始服务日期*始终在实际值之前。</span><span class="sxs-lookup"><span data-stu-id="d6958-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="d6958-175">为了帮助确定服务开始日期，我们可以创建短语说明。</span><span class="sxs-lookup"><span data-stu-id="d6958-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="d6958-176">在 "说明" 部分，选择 "**新建**"，然后键入名称 (例如，*前缀 String*) 。</span><span class="sxs-lookup"><span data-stu-id="d6958-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="d6958-177">对于 "类型"，选择 "**短语列表**"。</span><span class="sxs-lookup"><span data-stu-id="d6958-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="d6958-178">使用*服务开始日期*作为值。</span><span class="sxs-lookup"><span data-stu-id="d6958-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="d6958-179">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6958-179">Select **Save**.</span></span>

    ![解释库](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="d6958-181">训练模型</span><span class="sxs-lookup"><span data-stu-id="d6958-181">Train the model</span></span>

<span data-ttu-id="d6958-182">保存您的说明将再次开始进行训练，这次将在我们的示例中使用这两个说明。</span><span class="sxs-lookup"><span data-stu-id="d6958-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="d6958-183">如果您的模型有足够的信息从标记的示例文件中提取数据，您将看到标记为 "**匹配**" 的每个文件。</span><span class="sxs-lookup"><span data-stu-id="d6958-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="d6958-184">如果再次收到带标签的文件的**不匹配**项，则可能需要创建另一条说明，以提供模型以详细了解该文档类型，或查看对现有文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d6958-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="d6958-185">测试模型</span><span class="sxs-lookup"><span data-stu-id="d6958-185">Test your model</span></span>

<span data-ttu-id="d6958-186">如果您在标记的示例文件中接收到匹配项，则现在可以在剩余的未标记的示例文件上测试模型。</span><span class="sxs-lookup"><span data-stu-id="d6958-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="d6958-187">在模型主页上，单击 "**测试**" 选项卡。 这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="d6958-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="d6958-188">在 "**测试文件**" 列表中，将显示示例文件，并显示该模型是否能够从这些文件中提取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d6958-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="d6958-189">您可以使用此信息来帮助您确定您的分类程序的有效性，以标识您的文档。</span><span class="sxs-lookup"><span data-stu-id="d6958-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![对文件进行测试](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="d6958-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6958-191">See Also</span></span>
  




