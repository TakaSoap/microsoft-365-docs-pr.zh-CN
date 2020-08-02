---
title: 创建分类器（预览）
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何创建分类器
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536962"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="dc823-103">创建分类器（预览）</span><span class="sxs-lookup"><span data-stu-id="dc823-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="dc823-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="dc823-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="dc823-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="dc823-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="dc823-106">分类器是一种自动标识和分类文档类型的模型。</span><span class="sxs-lookup"><span data-stu-id="dc823-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="dc823-107">例如，您可能想要确定添加到文档库中的所有*合同续订*文档，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dc823-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![合同续订文档](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="dc823-109">创建一个分类器将创建一个新的[SharePoint 内容类型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)，该类型将与模型相关联。</span><span class="sxs-lookup"><span data-stu-id="dc823-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="dc823-110">创建分类器时，您需要创建*说明*，以帮助定义模型，方法是通过对此文档类型的预期持续查找的常用数据进行标注。</span><span class="sxs-lookup"><span data-stu-id="dc823-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="dc823-111">您可以使用文档类型（"示例文件"）的示例来帮助 "培训" 您的模型，以确定具有相同内容类型的文件。</span><span class="sxs-lookup"><span data-stu-id="dc823-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="dc823-112">若要创建分类器，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dc823-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="dc823-113">命名模型</span><span class="sxs-lookup"><span data-stu-id="dc823-113">Name your model</span></span>
2. <span data-ttu-id="dc823-114">添加示例文件</span><span class="sxs-lookup"><span data-stu-id="dc823-114">Add your example files</span></span>
3. <span data-ttu-id="dc823-115">为示例文件添加标签</span><span class="sxs-lookup"><span data-stu-id="dc823-115">Label your example files</span></span>
4. <span data-ttu-id="dc823-116">创建说明</span><span class="sxs-lookup"><span data-stu-id="dc823-116">Create an explanation</span></span>
5. <span data-ttu-id="dc823-117">测试模型</span><span class="sxs-lookup"><span data-stu-id="dc823-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="dc823-118">虽然您的模型使用分类符来标识和分类文档类型，但您也可以选择从模型所标识的每个文件中提取特定的信息部分。</span><span class="sxs-lookup"><span data-stu-id="dc823-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="dc823-119">为此，请创建要添加到模型中的**提取**程序，这将在[创建提取程序](create-an-extractor.md)中进行说明。</span><span class="sxs-lookup"><span data-stu-id="dc823-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="dc823-120">命名模型</span><span class="sxs-lookup"><span data-stu-id="dc823-120">Name your model</span></span>

<span data-ttu-id="dc823-121">第一步是在内容中心中创建模型，方法是为其提供名称：</span><span class="sxs-lookup"><span data-stu-id="dc823-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="dc823-122">在内容中心中，单击 "**新建**"，然后单击 "**创建模型**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="dc823-123">在 "**新建文档理解模型**" 窗格中的 "**名称**" 字段中，键入模型的名称。</span><span class="sxs-lookup"><span data-stu-id="dc823-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="dc823-124">对于我们的示例，如果我们想要确定合同续订文档，我们可以命名此模型*合同续订*。</span><span class="sxs-lookup"><span data-stu-id="dc823-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="dc823-125">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="dc823-125">Click **Create**.</span></span> <span data-ttu-id="dc823-126">这将为模型创建主页。</span><span class="sxs-lookup"><span data-stu-id="dc823-126">This will create a home page for the model.</span></span></br>

    ![分类器模型主页](../media/content-understanding/model-home.png)

<span data-ttu-id="dc823-128">创建模型时，将创建新的 SharePoint 内容类型。</span><span class="sxs-lookup"><span data-stu-id="dc823-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="dc823-129">SharePoint 内容类型表示具有共同特征的文档类别，并共享该特定内容的一组列或元数据属性。</span><span class="sxs-lookup"><span data-stu-id="dc823-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="dc823-130">SharePoint 内容类型通过[内容类型库]()进行管理。</span><span class="sxs-lookup"><span data-stu-id="dc823-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="dc823-131">在我们的示例中，创建模型时，我们将创建新的*合同续订*内容类型。</span><span class="sxs-lookup"><span data-stu-id="dc823-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="dc823-132">如果要将此模型映射到 SharePoint 内容类型库中的现有内容类型以使用其架构，请选择 "**高级设置**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="dc823-133">请注意，虽然您可以使用现有内容类型来帮助进行标识和分类，但您仍需要对模型进行训练，以便从它标识的文件提取信息。</span><span class="sxs-lookup"><span data-stu-id="dc823-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![高级设置](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="dc823-135">添加示例文件</span><span class="sxs-lookup"><span data-stu-id="dc823-135">Add your example files</span></span>

<span data-ttu-id="dc823-136">在模型主页上，您可以添加示例文件，您需要这些文件来帮助训练模型以标识您的文档类型。</span><span class="sxs-lookup"><span data-stu-id="dc823-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="dc823-137">对于分类器和[提取器培训](create-an-extractor.md)，应使用相同的文件。</span><span class="sxs-lookup"><span data-stu-id="dc823-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="dc823-138">你始终可以选择添加更多的更高版本，但通常应添加完整的示例文件集。</span><span class="sxs-lookup"><span data-stu-id="dc823-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="dc823-139">您将标记一些以培训您的模型，并测试其余未标记的模型以评估模型适用性。</span><span class="sxs-lookup"><span data-stu-id="dc823-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="dc823-140">对于你的培训集，你将需要使用正则示例和消极示例：</span><span class="sxs-lookup"><span data-stu-id="dc823-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="dc823-141">正则示例：表示文档类型的文档。</span><span class="sxs-lookup"><span data-stu-id="dc823-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="dc823-142">它们包含的字符串和信息总是在这种类型的文档中。</span><span class="sxs-lookup"><span data-stu-id="dc823-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="dc823-143">负示例：不代表文档类型的文档。</span><span class="sxs-lookup"><span data-stu-id="dc823-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="dc823-144">这些类型的文档中缺少需要的字符串和信息。</span><span class="sxs-lookup"><span data-stu-id="dc823-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="dc823-145">你将需要使用至少5个正则示例和一个负示例来培训你的模型。</span><span class="sxs-lookup"><span data-stu-id="dc823-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="dc823-146">你将需要其他附加的用户才能在培训后测试你的模型。</span><span class="sxs-lookup"><span data-stu-id="dc823-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="dc823-147">添加示例文件：</span><span class="sxs-lookup"><span data-stu-id="dc823-147">To add sample files:</span></span>

1. <span data-ttu-id="dc823-148">在模型主页上的 "**生成示例库**" 磁贴中，单击 "**添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="dc823-149">在 "**选择模型的示例文件**" 页上，从内容中心的示例文件库中选择示例文件。</span><span class="sxs-lookup"><span data-stu-id="dc823-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="dc823-150">如果尚未将其上传到那里，则可以通过单击 "**上载**" 将其移到示例文件库中，选择立即上载。</span><span class="sxs-lookup"><span data-stu-id="dc823-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="dc823-151">选择用于培训模型的示例文件后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![选择示例文件](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="dc823-153">为示例文件添加标签</span><span class="sxs-lookup"><span data-stu-id="dc823-153">Label your example files</span></span>

<span data-ttu-id="dc823-154">添加示例文件后，需要将其标记为正示例或负示例。</span><span class="sxs-lookup"><span data-stu-id="dc823-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="dc823-155">在模型主页上的 "对**文件进行分类和运行培训**图块" 中，单击 "**训练分类器**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="dc823-156">这将显示 "标签" 页面，其中显示了示例文件的列表，查看器中的第一个文件可见。</span><span class="sxs-lookup"><span data-stu-id="dc823-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="dc823-157">在查看器中，第一个示例文件的顶部，您将看到文本，询问您文件是否是您刚创建的模型的示例。</span><span class="sxs-lookup"><span data-stu-id="dc823-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="dc823-158">如果是一个正则示例，请选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="dc823-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="dc823-159">如果它是一个负示例，请选择 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="dc823-160">从左侧的 "**标记的示例**" 列表中，选择要用作示例的其他文件，并标记这些文件。</span><span class="sxs-lookup"><span data-stu-id="dc823-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![分类器模型主页](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="dc823-162">至少为五个正则的示例添加标签和一个负的示例。</span><span class="sxs-lookup"><span data-stu-id="dc823-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="dc823-163">创建说明</span><span class="sxs-lookup"><span data-stu-id="dc823-163">Create an explanation</span></span>

<span data-ttu-id="dc823-164">下一步是在 "培训" 页面上创建一个说明。</span><span class="sxs-lookup"><span data-stu-id="dc823-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="dc823-165">解释是一个提示或线索，可帮助模型了解如何识别此文档。</span><span class="sxs-lookup"><span data-stu-id="dc823-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="dc823-166">例如，我们的合同续订文档始终包含一个*请求以获取额外的泄露*文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dc823-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="dc823-167">在与提取程序一起使用时，使用说明来标识要从文档中提取的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc823-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="dc823-168">若要创建说明：</span><span class="sxs-lookup"><span data-stu-id="dc823-168">To create an explanation:</span></span>

1. <span data-ttu-id="dc823-169">在模型主页上，单击 "**定型**" 选项卡以转到 "培训" 页面。</span><span class="sxs-lookup"><span data-stu-id="dc823-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="dc823-170">在 "培训" 页上的 "**训练有素的文件**" 部分中，您将看到先前已标记的示例文件的列表。</span><span class="sxs-lookup"><span data-stu-id="dc823-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="dc823-171">从列表中选择一个正则文件，它将显示在查看器中。</span><span class="sxs-lookup"><span data-stu-id="dc823-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="dc823-172">在 "说明" 部分，单击 "**新建**"，然后单击 "**空白**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="dc823-173">在 "**创建说明**" 页上：</span><span class="sxs-lookup"><span data-stu-id="dc823-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="dc823-174">a.</span><span class="sxs-lookup"><span data-stu-id="dc823-174">a.</span></span> <span data-ttu-id="dc823-175">键入**名称**（例如，"披露 Block"）。</span><span class="sxs-lookup"><span data-stu-id="dc823-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="dc823-176">b.</span><span class="sxs-lookup"><span data-stu-id="dc823-176">b.</span></span> <span data-ttu-id="dc823-177">选择 "**类型**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-177">Select the **Type**.</span></span> <span data-ttu-id="dc823-178">对于我们的示例，我们将选择**短语 "列表**"，因为我们要添加文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dc823-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="dc823-179">c.</span><span class="sxs-lookup"><span data-stu-id="dc823-179">c.</span></span> <span data-ttu-id="dc823-180">在 "**请键入此处**" 框中，键入字符串。</span><span class="sxs-lookup"><span data-stu-id="dc823-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="dc823-181">对于我们的示例，我们将添加 "请求其他披露"。</span><span class="sxs-lookup"><span data-stu-id="dc823-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="dc823-182">如果字符串需要区分大小写，则可以选择 "区分**大小写**"。</span><span class="sxs-lookup"><span data-stu-id="dc823-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="dc823-183">d.</span><span class="sxs-lookup"><span data-stu-id="dc823-183">d.</span></span> <span data-ttu-id="dc823-184">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="dc823-184">Click **Save**.</span></span>

    ![创建说明](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="dc823-186">模型现在将检查您创建的解释是否足够好，以确定剩余的标记的示例文件正确无误，如正面和负数示例。</span><span class="sxs-lookup"><span data-stu-id="dc823-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="dc823-187">在 "训练有素的文件" 部分中，选中 "完成培训后的**评估**" 列以查看结果。</span><span class="sxs-lookup"><span data-stu-id="dc823-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="dc823-188">如果您创建的解释足以匹配已标记为（正数或负数）的内容，则文件将显示**匹配**的值。</span><span class="sxs-lookup"><span data-stu-id="dc823-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![创建说明](../media/content-understanding/match.png) 

<span data-ttu-id="dc823-190">如果您在标记的文件上收到**不匹配**项，则可能需要创建其他说明，以提供模型以详细了解该文档类型。</span><span class="sxs-lookup"><span data-stu-id="dc823-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="dc823-191">您可以单击文件以获取有关为什么发生不匹配的原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc823-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="dc823-192">测试模型</span><span class="sxs-lookup"><span data-stu-id="dc823-192">Test your model</span></span>

<span data-ttu-id="dc823-193">如果您在标记的示例文件中接收到匹配项，则现在可以在剩余的未标记的示例文件上测试模型。</span><span class="sxs-lookup"><span data-stu-id="dc823-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="dc823-194">在模型主页上，单击 "**测试**" 选项卡。 这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="dc823-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="dc823-195">在 "**测试文件**" 列表中，将显示示例文件，并显示该模型是否将它们预测为正数或负数示例。</span><span class="sxs-lookup"><span data-stu-id="dc823-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="dc823-196">您可以使用此信息来帮助您确定您的分类程序的有效性，以标识您的文档。</span><span class="sxs-lookup"><span data-stu-id="dc823-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![未标记文件的测试](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="dc823-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc823-198">See Also</span></span>
[<span data-ttu-id="dc823-199">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="dc823-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="dc823-200">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="dc823-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="dc823-201">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="dc823-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="dc823-202">应用模型</span><span class="sxs-lookup"><span data-stu-id="dc823-202">Apply a model</span></span>](apply-a-model.md) 




