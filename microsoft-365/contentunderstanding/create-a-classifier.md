---
title: 创建分类器
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何创建分类器
ms.openlocfilehash: 9f2cfe65140aa3f8d4c1c4ff5b8f2e3b9e8591f6
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975905"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="97b24-103">在 Microsoft SharePoint Syntex 中创建分类器</span><span class="sxs-lookup"><span data-stu-id="97b24-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="97b24-104">分类器是一种模型类型，可用于自动化文档类型的标识和分类。</span><span class="sxs-lookup"><span data-stu-id="97b24-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="97b24-105">例如，你可能想要标识所有添加到文档库中的“*合同续订*”文档，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="97b24-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![“合同续订”文档](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="97b24-107">创建分类器使你能够创建将与模型关联的新 [SharePoint 内容类型](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="97b24-107">Creating a classifier enables you to create a new [SharePoint content type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="97b24-108">创建分类器时，需要创建 *说明* 来定义模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="97b24-109">这可以使你记下预期会一贯地找到此文档类型的常见数据。</span><span class="sxs-lookup"><span data-stu-id="97b24-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="97b24-110">使用文档类型的示例（“示例文件”）来“培训”你的模型，以便识别具有相同内容类型的文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="97b24-111">若要创建分类器，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97b24-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="97b24-112">命名模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-112">Name your model.</span></span>
2. <span data-ttu-id="97b24-113">添加示例文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-113">Add your example files.</span></span>
3. <span data-ttu-id="97b24-114">标记示例文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-114">Label your example files.</span></span>
4. <span data-ttu-id="97b24-115">创建说明。</span><span class="sxs-lookup"><span data-stu-id="97b24-115">Create an explanation.</span></span>
5. <span data-ttu-id="97b24-116">测试模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="97b24-117">虽然你的模型使用分类器来标识和分类文档类型，但是你也可以选择从模型识别的每个文件中提取特定信息。</span><span class="sxs-lookup"><span data-stu-id="97b24-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="97b24-118">可通过创建 **提取程序** 并添加到模型中来实现此操作。</span><span class="sxs-lookup"><span data-stu-id="97b24-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="97b24-119">请参阅“[创建提取程序](create-an-extractor.md)”。</span><span class="sxs-lookup"><span data-stu-id="97b24-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="97b24-120">命名模型</span><span class="sxs-lookup"><span data-stu-id="97b24-120">Name your model</span></span>

<span data-ttu-id="97b24-121">创建模型的第一步是为其命名：</span><span class="sxs-lookup"><span data-stu-id="97b24-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="97b24-122">从内容中心中，选择“**新建**”，然后选择“**创建模型**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-122">From the content center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="97b24-123">在“**新的了解模型文档**”窗格中，在“**名称**”的字段中键入模型的名称。</span><span class="sxs-lookup"><span data-stu-id="97b24-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="97b24-124">例如，如果想要标识合同续订文档，可将该模型命名“*合同续订*”。</span><span class="sxs-lookup"><span data-stu-id="97b24-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="97b24-125">选择 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="97b24-125">Choose **Create**.</span></span> <span data-ttu-id="97b24-126">这将为该模型创建主页。</span><span class="sxs-lookup"><span data-stu-id="97b24-126">This creates a home page for the model.</span></span></br>

    ![分类器模型主页](../media/content-understanding/model-home.png)

<span data-ttu-id="97b24-128">创建模型时，也将创建新的网站内容类型。</span><span class="sxs-lookup"><span data-stu-id="97b24-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="97b24-129">内容类型表示具有共同特征的文档类别，并共享该特定内容的列或元数据属性的集合。</span><span class="sxs-lookup"><span data-stu-id="97b24-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="97b24-130">可通过“[内容类型库](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)”管理 SharePoint 内容类型。</span><span class="sxs-lookup"><span data-stu-id="97b24-130">SharePoint content types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="97b24-131">在此示例中，创建模型时，将创建新的“*合同续订*”内容类型。</span><span class="sxs-lookup"><span data-stu-id="97b24-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="97b24-132">如果想要将此模型映射到 SharePoint 内容类型库中的现有企业内容类型以使用其架构，请选择“**高级设置**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="97b24-133">企业内容类型存储在 SharePoint 管理中心中的内容类型中心中，并与租户中的所有网站联合。</span><span class="sxs-lookup"><span data-stu-id="97b24-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="97b24-134">请注意，虽然可使用现有内容类型，利用其架构来帮助标识和分类，但仍需训练模型从识别的文件中提取信息。</span><span class="sxs-lookup"><span data-stu-id="97b24-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![高级设置](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="97b24-136">添加示例文件</span><span class="sxs-lookup"><span data-stu-id="97b24-136">Add your example files</span></span>

<span data-ttu-id="97b24-137">在模型主页上，添加帮助训练模型识别文档类型的示例文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="97b24-138">应为分类器和[提取程序培训](create-an-extractor.md)使用相同的文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="97b24-139">你始终可以选择稍后再添加更多，但你通常可以添加完整的示例文件集。</span><span class="sxs-lookup"><span data-stu-id="97b24-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="97b24-140">标记一些文件以培训模型，并测试其余未标记的文件以评估模型适用性。</span><span class="sxs-lookup"><span data-stu-id="97b24-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="97b24-141">对于你的培训集，你应该要使用正例和反例：</span><span class="sxs-lookup"><span data-stu-id="97b24-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="97b24-142">正例：表示文档类型的文档。</span><span class="sxs-lookup"><span data-stu-id="97b24-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="97b24-143">其中包含始终属于此类型文档内的字符串和信息。</span><span class="sxs-lookup"><span data-stu-id="97b24-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="97b24-144">反例：任何不表示你想要分类的文档的其他文档。</span><span class="sxs-lookup"><span data-stu-id="97b24-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="97b24-145">请务必使用至少五个正例，以及至少一个反例来培新模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="97b24-146">你应该要创建额外示例，以便在培训过程之后测试你的模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="97b24-147">添加示例文件：</span><span class="sxs-lookup"><span data-stu-id="97b24-147">To add example files:</span></span>

1. <span data-ttu-id="97b24-148">在模型主页上的“**添加示例文件**”磁贴中，单击“**添加文件**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="97b24-149">在“**为模型选择示例文件**”页面上，从内容中心的”培训文件”库中选择示例文件。</span><span class="sxs-lookup"><span data-stu-id="97b24-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="97b24-150">如果尚未上传到其中，请单击“**上传**”来选择立即上传它们，以便把它们复制到“培训文件”库中，。</span><span class="sxs-lookup"><span data-stu-id="97b24-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="97b24-151">选择用于培训模型的示例文件后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![选择示例文件](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="97b24-153">标记示例文件</span><span class="sxs-lookup"><span data-stu-id="97b24-153">Label your example files</span></span>

<span data-ttu-id="97b24-154">添加示例文件后，需要将其标记为正例或反例。</span><span class="sxs-lookup"><span data-stu-id="97b24-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="97b24-155">在模型主页的“**分类文件并运行培训**”磁贴中，单击“**训练分类器**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-155">From the model home page, on the **Classify files and run training** tile, click **Train classifier**.</span></span>
   <span data-ttu-id="97b24-156">这将显示一个标签页，该页将显示示例文件的列表，第一个文件可见于查看器中。</span><span class="sxs-lookup"><span data-stu-id="97b24-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="97b24-157">在查看器中第一个示例文件的顶部那里，你会看到询问该文件是否为刚创建模型的示例的文本。</span><span class="sxs-lookup"><span data-stu-id="97b24-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="97b24-158">如果是正例，请选择 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="97b24-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="97b24-159">如果是反例，请选择 **“否”**。</span><span class="sxs-lookup"><span data-stu-id="97b24-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="97b24-160">在左侧“**已标记示例**”的列表中，选择要用作示例的附加文件，然后为其添加标签。</span><span class="sxs-lookup"><span data-stu-id="97b24-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分类器主页](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="97b24-162">标记至少五个正例。</span><span class="sxs-lookup"><span data-stu-id="97b24-162">Label at least five positive examples.</span></span> <span data-ttu-id="97b24-163">还必须标记至少一个反例。</span><span class="sxs-lookup"><span data-stu-id="97b24-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="97b24-164">创建说明</span><span class="sxs-lookup"><span data-stu-id="97b24-164">Create an explanation</span></span>

<span data-ttu-id="97b24-165">下一步是让你在“培训”页面上创建说明。</span><span class="sxs-lookup"><span data-stu-id="97b24-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="97b24-166">说明有助于模型理解如何识别文档。</span><span class="sxs-lookup"><span data-stu-id="97b24-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="97b24-167">例如，“合同续订”文档始终包含“*请求附加说明*”的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="97b24-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="97b24-168">与提取程序配合使用时，说明将会识别你想要从文档中提取的字符串。</span><span class="sxs-lookup"><span data-stu-id="97b24-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="97b24-169">要创建说明，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97b24-169">To create an explanation:</span></span>

1. <span data-ttu-id="97b24-170">在模型主页中，选择“**培训**”选项卡以转到“培训”页面。</span><span class="sxs-lookup"><span data-stu-id="97b24-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="97b24-171">在“培训”页面上的“**已培训文件**”部分中，你应该会看到先前标记的示例文件列表。</span><span class="sxs-lookup"><span data-stu-id="97b24-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="97b24-172">从列表中选择其中一个正例文件，然后它将在查看器中显示。</span><span class="sxs-lookup"><span data-stu-id="97b24-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="97b24-173">在“说明”部分中，选择“**新建**”，然后“**空白**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="97b24-174">在“**创建说明**”页面上：</span><span class="sxs-lookup"><span data-stu-id="97b24-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="97b24-175">a.</span><span class="sxs-lookup"><span data-stu-id="97b24-175">a.</span></span> <span data-ttu-id="97b24-176">键入“**名称**”（例如，“说明文本块”）。</span><span class="sxs-lookup"><span data-stu-id="97b24-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="97b24-177">b.</span><span class="sxs-lookup"><span data-stu-id="97b24-177">b.</span></span> <span data-ttu-id="97b24-178">选择“**类型**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-178">Select the **Type**.</span></span> <span data-ttu-id="97b24-179">对于示例，请选择“**短语列表**”，因为添加了文本字符串。</span><span class="sxs-lookup"><span data-stu-id="97b24-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="97b24-180">c.</span><span class="sxs-lookup"><span data-stu-id="97b24-180">c.</span></span> <span data-ttu-id="97b24-181">在“**在此处键入**”框中，键入字符串。</span><span class="sxs-lookup"><span data-stu-id="97b24-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="97b24-182">对于示例，请添加“请求附加说明”。</span><span class="sxs-lookup"><span data-stu-id="97b24-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="97b24-183">如果字符串需要区分大小写，则可以选择“**区分大小写**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="97b24-184">d.</span><span class="sxs-lookup"><span data-stu-id="97b24-184">d.</span></span> <span data-ttu-id="97b24-185">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-185">Click **Save**.</span></span>

    ![创建说明](../media/content-understanding/explanation.png) 
    
5. <span data-ttu-id="97b24-187">现在，内容中心将检查你创建的说明是否完整，足以正确地识别其他已标记的示例文件为正例和反例。</span><span class="sxs-lookup"><span data-stu-id="97b24-187">The Content Center now checks to see if the explanation you created is complete enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="97b24-188">在“已培训文件”的部分中，训练完成后，检查“**评估**”列以查看结果。</span><span class="sxs-lookup"><span data-stu-id="97b24-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="97b24-189">如果你创建的说明足以匹配标记为正例或反例的内容，则文件显示“**匹配**”。</span><span class="sxs-lookup"><span data-stu-id="97b24-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![匹配值](../media/content-understanding/match.png) 

<span data-ttu-id="97b24-191">如果在已标记的文件上收到“**不匹配**”，则可能需要创建额外的说明，以便为模型提供更多标识文档类型的信息。</span><span class="sxs-lookup"><span data-stu-id="97b24-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="97b24-192">如果发生这种情况，请单击文件以获取更多有关发生不匹配情况的原因详情。</span><span class="sxs-lookup"><span data-stu-id="97b24-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="97b24-193">测试模型</span><span class="sxs-lookup"><span data-stu-id="97b24-193">Test your model</span></span>

<span data-ttu-id="97b24-194">如果你在已标记的示例文件上收到“匹配”，则现在可以在其余未标记且模型未见过的示例文件上测试模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="97b24-195">这是一个可选但很有用的步骤，可在使用模型之前评估其“适用性”和“就绪度”，方法是在该模型之前未见过的文件上对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="97b24-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="97b24-196">在模型主页中，选择“**测试**”选项卡。这将在未标记的示例文件上运行模型。</span><span class="sxs-lookup"><span data-stu-id="97b24-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="97b24-197">在“**测试文件**”列表中，将列出并显示示例文件（如果模型将其预测为正例或反例的话）。</span><span class="sxs-lookup"><span data-stu-id="97b24-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="97b24-198">使用此信息以帮助确定分类器在文档识别中的有效性。</span><span class="sxs-lookup"><span data-stu-id="97b24-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![未标记文件的测试](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="97b24-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97b24-200">See Also</span></span>
[<span data-ttu-id="97b24-201">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="97b24-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="97b24-202">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="97b24-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="97b24-203">说明类型</span><span class="sxs-lookup"><span data-stu-id="97b24-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="97b24-204">应用模型</span><span class="sxs-lookup"><span data-stu-id="97b24-204">Apply a model</span></span>](apply-a-model.md) 
