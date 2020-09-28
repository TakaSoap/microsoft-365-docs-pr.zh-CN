---
title: 创建类元
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
description: 了解如何创建分类器
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294898"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="6296f-103">在 Microsoft SharePoint Syntex 中创建分类器</span><span class="sxs-lookup"><span data-stu-id="6296f-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="6296f-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="6296f-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="6296f-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="6296f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="6296f-106">分类器是一种类型的模型，可用于自动执行文档类型的标识和分类。</span><span class="sxs-lookup"><span data-stu-id="6296f-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="6296f-107">例如，您可能想要确定添加到文档库中的所有 *合同续订* 文档，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="6296f-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![合同续订文档](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="6296f-109">通过创建分类器，可以创建将与模型关联的新 [SharePoint 内容类型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) 。</span><span class="sxs-lookup"><span data-stu-id="6296f-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="6296f-110">创建分类器时，需要创建 *说明* 以定义模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="6296f-111">这样一来，你便可以注意到你希望一致地找到此文档类型的常见数据。</span><span class="sxs-lookup"><span data-stu-id="6296f-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="6296f-112">使用文档类型示例 ( "示例文件" ) "培训" 您的模型以确定具有相同内容类型的文件。</span><span class="sxs-lookup"><span data-stu-id="6296f-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="6296f-113">若要创建分类器，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6296f-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="6296f-114">命名模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-114">Name your model.</span></span>
2. <span data-ttu-id="6296f-115">添加示例文件。</span><span class="sxs-lookup"><span data-stu-id="6296f-115">Add your example files.</span></span>
3. <span data-ttu-id="6296f-116">为示例文件添加标签。</span><span class="sxs-lookup"><span data-stu-id="6296f-116">Label your example files.</span></span>
4. <span data-ttu-id="6296f-117">创建说明。</span><span class="sxs-lookup"><span data-stu-id="6296f-117">Create an explanation.</span></span>
5. <span data-ttu-id="6296f-118">测试您的模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="6296f-119">虽然您的模型使用分类器来标识和分类文档类型，但您也可以选择从模型标识的每个文件中提取特定的信息部分。</span><span class="sxs-lookup"><span data-stu-id="6296f-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="6296f-120">为此，请创建要添加到您的模型的 **提取** 程序。</span><span class="sxs-lookup"><span data-stu-id="6296f-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="6296f-121">请参阅 [创建提取程序](create-an-extractor.md)。</span><span class="sxs-lookup"><span data-stu-id="6296f-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="6296f-122">命名模型</span><span class="sxs-lookup"><span data-stu-id="6296f-122">Name your model</span></span>

<span data-ttu-id="6296f-123">创建模型的第一步是为其指定名称：</span><span class="sxs-lookup"><span data-stu-id="6296f-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="6296f-124">在内容中心中，选择 " **新建**"，然后 **创建一个模型**。</span><span class="sxs-lookup"><span data-stu-id="6296f-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="6296f-125">在 " **新建文档理解模型** " 窗格中，在 " **名称** " 字段中键入模型的名称。</span><span class="sxs-lookup"><span data-stu-id="6296f-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="6296f-126">例如，如果您想要标识合同续订文档，可以命名模型 *合同续订*。</span><span class="sxs-lookup"><span data-stu-id="6296f-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="6296f-127">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="6296f-127">Choose **Create**.</span></span> <span data-ttu-id="6296f-128">这将为模型创建一个主页。</span><span class="sxs-lookup"><span data-stu-id="6296f-128">This creates a home page for the model.</span></span></br>

    ![分类器模型主页](../media/content-understanding/model-home.png)

<span data-ttu-id="6296f-130">创建模型时，还将创建新的 SharePoint 内容类型。</span><span class="sxs-lookup"><span data-stu-id="6296f-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="6296f-131">SharePoint 内容类型表示具有共同特征的文档类别，并共享该特定内容的一组列或元数据属性。</span><span class="sxs-lookup"><span data-stu-id="6296f-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="6296f-132">SharePoint 内容类型通过 [内容类型库](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)进行管理。</span><span class="sxs-lookup"><span data-stu-id="6296f-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="6296f-133">在此示例中，在创建模型时，将创建新的 *合同续订* 内容类型。</span><span class="sxs-lookup"><span data-stu-id="6296f-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="6296f-134">如果要将此模型映射到 SharePoint 内容类型库中的现有内容类型以使用其架构，请选择 " **高级设置** "。</span><span class="sxs-lookup"><span data-stu-id="6296f-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="6296f-135">请注意，虽然您可以使用现有内容类型来帮助确定和分类，但仍需要对模型进行训练，以便从标识的文件中提取信息。</span><span class="sxs-lookup"><span data-stu-id="6296f-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![高级设置](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="6296f-137">添加示例文件</span><span class="sxs-lookup"><span data-stu-id="6296f-137">Add your example files</span></span>

<span data-ttu-id="6296f-138">在模型主页上，添加帮助培训模型以标识文档类型所需的示例文件。</span><span class="sxs-lookup"><span data-stu-id="6296f-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="6296f-139">对于分类器和 [提取器培训](create-an-extractor.md)，应使用相同的文件。</span><span class="sxs-lookup"><span data-stu-id="6296f-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="6296f-140">您始终可以选择添加更多更高版本，但通常可以添加完整的示例文件集。</span><span class="sxs-lookup"><span data-stu-id="6296f-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="6296f-141">将一些标签标记为培训您的模型，并测试其余未标记的模型以评估模型适用性。</span><span class="sxs-lookup"><span data-stu-id="6296f-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="6296f-142">对于您的培训集，您想要使用正面和负面示例：</span><span class="sxs-lookup"><span data-stu-id="6296f-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="6296f-143">正则示例：表示文档类型的文档。</span><span class="sxs-lookup"><span data-stu-id="6296f-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="6296f-144">这些文档中包含的字符串和信息总是在这种类型的文档中。</span><span class="sxs-lookup"><span data-stu-id="6296f-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="6296f-145">负示例：不代表文档类型的文档。</span><span class="sxs-lookup"><span data-stu-id="6296f-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="6296f-146">这些类型的文档中缺少需要的字符串和信息。</span><span class="sxs-lookup"><span data-stu-id="6296f-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="6296f-147">请务必使用至少5个正的示例和至少一个负的示例来培训您的模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="6296f-148">您想要创建其他模板，以便在培训过程之后测试您的模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="6296f-149">添加示例文件：</span><span class="sxs-lookup"><span data-stu-id="6296f-149">To add sample files:</span></span>

1. <span data-ttu-id="6296f-150">从模型主页的 " **生成示例库** " 磁贴中，单击 " **添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="6296f-151">在 " **选择模型的示例文件** " 页上，从内容中心的示例文件库中选择示例文件。</span><span class="sxs-lookup"><span data-stu-id="6296f-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="6296f-152">如果尚未将其上传到，请通过单击 " **上载** " 将其移到示例文件库中，选择立即上载。</span><span class="sxs-lookup"><span data-stu-id="6296f-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="6296f-153">选择用于培训模型的示例文件后，单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![选择示例文件](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="6296f-155">为示例文件添加标签</span><span class="sxs-lookup"><span data-stu-id="6296f-155">Label your example files</span></span>

<span data-ttu-id="6296f-156">添加示例文件后，需要将其标记为正数或负数示例。</span><span class="sxs-lookup"><span data-stu-id="6296f-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="6296f-157">在模型主页中的 "对 **文件进行分类和运行培训** 图块" 中，单击 " **训练分类器**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="6296f-158">这将显示 "标签" 页面，其中显示了示例文件的列表，查看器中的第一个文件可见。</span><span class="sxs-lookup"><span data-stu-id="6296f-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="6296f-159">在第一个示例文件顶部的查看器中，您应该会看到文本，询问文件是否为您刚创建的模型的示例。</span><span class="sxs-lookup"><span data-stu-id="6296f-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="6296f-160">如果是一个正则示例，请选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="6296f-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="6296f-161">如果它是一个负示例，请选择 " **否**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="6296f-162">从左侧的 " **标记的示例** " 列表中，选择要用作示例的其他文件，并为其添加标签。</span><span class="sxs-lookup"><span data-stu-id="6296f-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分类器主页](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="6296f-164">至少为五个正则的示例添加标签和一个负的示例。</span><span class="sxs-lookup"><span data-stu-id="6296f-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="6296f-165">创建说明</span><span class="sxs-lookup"><span data-stu-id="6296f-165">Create an explanation</span></span>

<span data-ttu-id="6296f-166">下一步是在 "培训" 页面上创建一个说明。</span><span class="sxs-lookup"><span data-stu-id="6296f-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="6296f-167">说明可帮助模型了解如何识别文档。</span><span class="sxs-lookup"><span data-stu-id="6296f-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="6296f-168">例如，合同续订文档始终包含 *对其他泄露文本字符串的请求* 。</span><span class="sxs-lookup"><span data-stu-id="6296f-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="6296f-169">当与提取程序一起使用时，说明标识要从文档中提取的字符串。</span><span class="sxs-lookup"><span data-stu-id="6296f-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="6296f-170">若要创建说明：</span><span class="sxs-lookup"><span data-stu-id="6296f-170">To create an explanation:</span></span>

1. <span data-ttu-id="6296f-171">从模型主页中，选择 " **定型** " 选项卡以转到 "培训" 页面。</span><span class="sxs-lookup"><span data-stu-id="6296f-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="6296f-172">在 "培训" 页上的 " **训练有素的文件** " 部分，您应该会看到先前标记的示例文件的列表。</span><span class="sxs-lookup"><span data-stu-id="6296f-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="6296f-173">从列表中选择一个正则文件，它将显示在查看器中。</span><span class="sxs-lookup"><span data-stu-id="6296f-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="6296f-174">在 "说明" 部分，选择 " **新建** "，然后选择 " **空白**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="6296f-175">在 " **创建说明** " 页上：</span><span class="sxs-lookup"><span data-stu-id="6296f-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="6296f-176">a.</span><span class="sxs-lookup"><span data-stu-id="6296f-176">a.</span></span> <span data-ttu-id="6296f-177">键入 **名称** (例如，"披露 Block" ) 。</span><span class="sxs-lookup"><span data-stu-id="6296f-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="6296f-178">b.</span><span class="sxs-lookup"><span data-stu-id="6296f-178">b.</span></span> <span data-ttu-id="6296f-179">选择 " **类型**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-179">Select the **Type**.</span></span> <span data-ttu-id="6296f-180">有关示例，请选择 " **短语列表**"，因为您添加了文本字符串。</span><span class="sxs-lookup"><span data-stu-id="6296f-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="6296f-181">c.</span><span class="sxs-lookup"><span data-stu-id="6296f-181">c.</span></span> <span data-ttu-id="6296f-182">在 " **请键入此处** " 框中，键入字符串。</span><span class="sxs-lookup"><span data-stu-id="6296f-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="6296f-183">对于示例，添加 "请求其他披露"。</span><span class="sxs-lookup"><span data-stu-id="6296f-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="6296f-184">如果字符串需要区分大小写，则可以选择 "区分 **大小写** "。</span><span class="sxs-lookup"><span data-stu-id="6296f-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="6296f-185">d.</span><span class="sxs-lookup"><span data-stu-id="6296f-185">d.</span></span> <span data-ttu-id="6296f-186">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6296f-186">Click **Save**.</span></span>

    ![创建说明](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="6296f-188">模型现在将检查您创建的解释是否足够好，以确定剩余的标记的示例文件是否正确，如正面和负数示例。</span><span class="sxs-lookup"><span data-stu-id="6296f-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="6296f-189">在 "训练有素的文件" 部分，选中 "完成培训后检查 **评估** " 列以查看结果。</span><span class="sxs-lookup"><span data-stu-id="6296f-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="6296f-190">如果您创建的解释足以匹配标记为正数或负数的内容，则文件显示值 " **匹配**"。</span><span class="sxs-lookup"><span data-stu-id="6296f-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![匹配值](../media/content-understanding/match.png) 

<span data-ttu-id="6296f-192">如果您在标记的文件上收到 **不匹配** 项，则可能需要创建其他说明，以提供详细的模型信息来标识文档类型。</span><span class="sxs-lookup"><span data-stu-id="6296f-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="6296f-193">如果发生这种情况，请单击文件以获取有关为什么发生不匹配的原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6296f-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="6296f-194">测试模型</span><span class="sxs-lookup"><span data-stu-id="6296f-194">Test your model</span></span>

<span data-ttu-id="6296f-195">如果您在标记的示例文件中接收到匹配项，则现在可以在剩余的未标记的示例文件上测试模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="6296f-196">从模型主页中，选择 " **测试** " 选项卡。 这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="6296f-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="6296f-197">在 " **测试文件** " 列表中，您的示例文件显示并显示，如果模型预测它们是正数还是负数。</span><span class="sxs-lookup"><span data-stu-id="6296f-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="6296f-198">使用此信息有助于在识别文档时确定分类程序的有效性。</span><span class="sxs-lookup"><span data-stu-id="6296f-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![未标记文件的测试](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="6296f-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6296f-200">See Also</span></span>
[<span data-ttu-id="6296f-201">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="6296f-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="6296f-202">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="6296f-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="6296f-203">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="6296f-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="6296f-204">应用模型</span><span class="sxs-lookup"><span data-stu-id="6296f-204">Apply a model</span></span>](apply-a-model.md) 
