---
title: 创建提取程序
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 了解如何在 Microsoft SharePoint Syntex 中创建提取程序。
ms.openlocfilehash: 99d2a4602c03d8a7207736ea17ed500626ce43ac
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087459"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d7968-103">在 Microsoft SharePoint Syntex 中创建提取程序</span><span class="sxs-lookup"><span data-stu-id="d7968-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="d7968-104">在创建分类器模型以自动识别和分类特定文档类型之前或之后，可选择性地选择将提取程序添加到模型中以从这些文档中提取特定信息。</span><span class="sxs-lookup"><span data-stu-id="d7968-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="d7968-105">例如，你可能希望模型不仅可以标识所有添加到文档库中的“*合同续订*”文档，还可将每个文档的“*服务开始日期*”显示为文档库中的列值。</span><span class="sxs-lookup"><span data-stu-id="d7968-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="d7968-106">需要为要所提取的文档中的每个实体创建一个提取程序。</span><span class="sxs-lookup"><span data-stu-id="d7968-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="d7968-107">在本示例中，从模型识别的每个“ **合同续订**” 文档中，我们要从中提取“ **服务开始日期** ”。</span><span class="sxs-lookup"><span data-stu-id="d7968-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="d7968-108">我们希望能够在文档库中看到所有“ **合同续订**” 文档的视图，其中一列显示每个文档的“**服务开始** 日期值”。</span><span class="sxs-lookup"><span data-stu-id="d7968-108">We want to be able to see a view in the document library of all  **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7968-109">为创建提取程序，请使用之前所上载的训练分类器的相同文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="d7968-110">命名提取程序</span><span class="sxs-lookup"><span data-stu-id="d7968-110">Name your extractor</span></span>

1. <span data-ttu-id="d7968-111">在模型主页的“**创建和培训提取程序**”磁贴中，单击“**培训提取器**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="d7968-112">在“**新实体提取程序**”屏幕上，在“**新提取程序名称**”字段中键入提取程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d7968-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="d7968-113">例如，如果想要从每个”合同续订文档”中提取服务开始日期，请将其命名为“**服务开始日期**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="d7968-114">也可以选择重复使用以前创建的列（例如，托管元数据列）。</span><span class="sxs-lookup"><span data-stu-id="d7968-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="d7968-115">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="d7968-116">添加标签</span><span class="sxs-lookup"><span data-stu-id="d7968-116">Add a label</span></span>

<span data-ttu-id="d7968-117">下一步是在示例培训文件中标记想要提取的实体。</span><span class="sxs-lookup"><span data-stu-id="d7968-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="d7968-118">创建提取程序会打开提程序 页面。</span><span class="sxs-lookup"><span data-stu-id="d7968-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="d7968-119">此时，将看到示例文件的列表，并在查看器中显示列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="d7968-120">从查看器中，选择要从文件中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="d7968-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="d7968-121">例如，如果想要提取“*开始服务日期*”，请突出显示第一个文件中的日期值（*星期一，2019 年 10 月 14 日*）。</span><span class="sxs-lookup"><span data-stu-id="d7968-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="d7968-122">然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-122">and then click **Save**.</span></span>  <span data-ttu-id="d7968-123">在“**标签**”列下，你应该会在“已标记示例”列表中看到从文件显示的值。</span><span class="sxs-lookup"><span data-stu-id="d7968-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="d7968-124">选择“**下一个文件**”可自动保存并打开查看器列表中的下一个文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="d7968-125">或选择“**保存**”，然后从“**已标记的示例**”列表中中选择另一个文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="d7968-126">在查看器中，重复第 1 步和第 2 步，然后重复执行，直到将标签保存到所有五个文件中。</span><span class="sxs-lookup"><span data-stu-id="d7968-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![高级设置](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="d7968-128">标记了五个文件后，将显示一条通知横幅，告知你移动到培训。</span><span class="sxs-lookup"><span data-stu-id="d7968-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="d7968-129">你可以选择更多标签，更多文档或前进到培训。</span><span class="sxs-lookup"><span data-stu-id="d7968-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="d7968-130">添加说明</span><span class="sxs-lookup"><span data-stu-id="d7968-130">Add an explanation</span></span>

<span data-ttu-id="d7968-131">在我们的示例中，我们将创建一个说明来提供关于实体格式本身的提示以及其在示例文档中可能存在的差异。</span><span class="sxs-lookup"><span data-stu-id="d7968-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="d7968-132">例如，日期值可以采用多种不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="d7968-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="d7968-133">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="d7968-133">10/14/2019</span></span>
- <span data-ttu-id="d7968-134">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d7968-134">October 14, 2019</span></span>
- <span data-ttu-id="d7968-135">星期一，2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d7968-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="d7968-136">为帮助标识“*服务开始日期*”，可创建模式说明。</span><span class="sxs-lookup"><span data-stu-id="d7968-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="d7968-137">在“说明”部分中，选择“**新建**”，然后键入名称（例如，“*日期*”）。</span><span class="sxs-lookup"><span data-stu-id="d7968-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="d7968-138">对于“类型”，请选择“**模式列表**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="d7968-139">对于“数值”，请提供示例文件中显示的日期变体。</span><span class="sxs-lookup"><span data-stu-id="d7968-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="d7968-140">例如，如果你的日期格式显示为 0/00/0000，则可在文档中输入显示的任何变体，如：</span><span class="sxs-lookup"><span data-stu-id="d7968-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="d7968-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="d7968-141">0/0/0000</span></span>
    - <span data-ttu-id="d7968-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="d7968-142">0/00/0000</span></span>
    - <span data-ttu-id="d7968-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="d7968-143">00/0/0000</span></span>
    - <span data-ttu-id="d7968-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="d7968-144">00/00/0000</span></span>
4. <span data-ttu-id="d7968-145">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d7968-146">有关更多关于说明类型的详细信息，请参阅“[说明类型](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)”。</span><span class="sxs-lookup"><span data-stu-id="d7968-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="d7968-147">使用“说明库”</span><span class="sxs-lookup"><span data-stu-id="d7968-147">Use the Explanation library</span></span>

<span data-ttu-id="d7968-148">若要创建日期等项目的说明，[使用说明库](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library)比手动输入所有变体来得更加简单。</span><span class="sxs-lookup"><span data-stu-id="d7968-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="d7968-149">说明库是一组预建短语和模式说明。</span><span class="sxs-lookup"><span data-stu-id="d7968-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="d7968-150">库会尝试为常见短语或模式列表提供所有格式，如日期、电话号码、邮政编码和其他许多格式。</span><span class="sxs-lookup"><span data-stu-id="d7968-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="d7968-151">对于“*服务开始日期*”示例，在说明库中使用“*日期”* 的预建说明会更高效 ：</span><span class="sxs-lookup"><span data-stu-id="d7968-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="d7968-152">在“**说明**”部分中，选择“**新建**”，然后选择“**从说明库中**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="d7968-153">从说明库中，选择“**日期**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="d7968-154">可查看所识别的日期的所有变体。</span><span class="sxs-lookup"><span data-stu-id="d7968-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="d7968-155">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-155">Select **Add**.</span></span></br>

    ![说明库](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="d7968-157">在“**创建说明**”页面上，说明库中的“*日期*”信息将自动填充字段。</span><span class="sxs-lookup"><span data-stu-id="d7968-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="d7968-158">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-158">Select **Save**.</span></span></br>

    ![日期](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="d7968-160">培训模型</span><span class="sxs-lookup"><span data-stu-id="d7968-160">Train the model</span></span> 

<span data-ttu-id="d7968-161">保存说明开始培训。</span><span class="sxs-lookup"><span data-stu-id="d7968-161">Saving your explanation start the training.</span></span> <span data-ttu-id="d7968-162">如果你的模型具有足够的信息，可以从已标记的示例文件中提取数据，你将看到每个文件都标记了“**匹配**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![匹配](../media/content-understanding/match2.png) 

<span data-ttu-id="d7968-164">如果说明没有足够的信息来查找你想要提取的数据，则每个文件都将标记 “**不匹配**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="d7968-165">可单击“**不匹配**”的文件，查看有关为何不匹配的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7968-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="d7968-166">添加另一个说明</span><span class="sxs-lookup"><span data-stu-id="d7968-166">Add another explanation</span></span>

<span data-ttu-id="d7968-167">通常不匹配是指我们提供的说明未提供足够的信息来提取服务开始日期值以匹配标记的文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="d7968-168">可能需要对其进行编辑，或添加其他说明。</span><span class="sxs-lookup"><span data-stu-id="d7968-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="d7968-169">在我们的示例中，请注意，文本字符串“*开始服务日期*”始终在实际值之前。</span><span class="sxs-lookup"><span data-stu-id="d7968-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="d7968-170">若要帮助标识“服务开始日期”，需要创建短语说明。</span><span class="sxs-lookup"><span data-stu-id="d7968-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="d7968-171">在“说明”部分中，选择“**新建**”，然后键入名称（例如，*前缀字符串*）。</span><span class="sxs-lookup"><span data-stu-id="d7968-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="d7968-172">对于“类型”，选择“**短语列表**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="d7968-173">使用“*服务开始日期*”作为值。</span><span class="sxs-lookup"><span data-stu-id="d7968-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="d7968-174">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-174">Select **Save**.</span></span>

    ![前缀字符串](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="d7968-176">再次培训模型</span><span class="sxs-lookup"><span data-stu-id="d7968-176">Train the model again</span></span>

<span data-ttu-id="d7968-177">保存说明会再次启动培训，这次将在示例中使用两个说明。</span><span class="sxs-lookup"><span data-stu-id="d7968-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="d7968-178">如果你的模型拥有足够的信息来提取已标记示例文件中的数据，你将看到每个文件都标记了“**匹配**”。</span><span class="sxs-lookup"><span data-stu-id="d7968-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="d7968-179">如果你在已标记的文件上再次收到“**不匹配**”，则可能需要创建其他说明，以便为模型提供更多用来标识文档类型的信息，或考虑对现有的说明进行更改。</span><span class="sxs-lookup"><span data-stu-id="d7968-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="d7968-180">测试模型</span><span class="sxs-lookup"><span data-stu-id="d7968-180">Test your model</span></span>

<span data-ttu-id="d7968-181">如果你在标记的示例文件上收到匹配，则现在可以在其余未标记的示例文件中测试模型。</span><span class="sxs-lookup"><span data-stu-id="d7968-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="d7968-182">这是一个可选但很有用的步骤，可在使用模型之前评估其的“适用性”和“准备度”，方法是在该模型之前未见过的文件上对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="d7968-182">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="d7968-183">在模型主页中，单击“**测试**”选项卡。 这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="d7968-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="d7968-184">在“**测试文件**”列表中，如果模型能够提取所需的信息，将显示出陈列的示例文件。</span><span class="sxs-lookup"><span data-stu-id="d7968-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="d7968-185">使用此信息以帮助确定分类器在文档识别中的有效性。</span><span class="sxs-lookup"><span data-stu-id="d7968-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![对文件进行测试](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="d7968-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7968-187">See Also</span></span>
[<span data-ttu-id="d7968-188">创建分类器</span><span class="sxs-lookup"><span data-stu-id="d7968-188">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d7968-189">说明类型</span><span class="sxs-lookup"><span data-stu-id="d7968-189">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="d7968-190">创建提取程序时利用术语库分类</span><span class="sxs-lookup"><span data-stu-id="d7968-190">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="d7968-191">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="d7968-191">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d7968-192">应用模型</span><span class="sxs-lookup"><span data-stu-id="d7968-192">Apply a model</span></span>](apply-a-model.md) 
