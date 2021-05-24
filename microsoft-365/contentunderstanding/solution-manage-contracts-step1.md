---
title: 步骤 1. 使用 SharePoint Syntex 标识协定文件并提取数据
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 了解如何使用 SharePoint Syntex 来识别合约文件，并使用 Microsoft 365 提取数据。
ms.openlocfilehash: b4b11b1bdb980b0ee7629af0cbecbb126a5ae5e5
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636202"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="a25e7-104">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="a25e7-104">Step 1.</span></span> <span data-ttu-id="a25e7-105">使用 SharePoint Syntex 标识协定文件并提取数据</span><span class="sxs-lookup"><span data-stu-id="a25e7-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="a25e7-106">贵组织需要一种方法从您收到的许多文件中标识所有合同文档并对这些文档进行分类。</span><span class="sxs-lookup"><span data-stu-id="a25e7-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="a25e7-107">您还需要能够快速查看每个识别为 (合同文件中的几个关键元素，例如，Client、Contract 和 Fee  *amount*) 。 </span><span class="sxs-lookup"><span data-stu-id="a25e7-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="a25e7-108">为此，可以使用[Syntex](index.md) SharePoint文档理解模型，并应用到文档库。</span><span class="sxs-lookup"><span data-stu-id="a25e7-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="a25e7-109">过程概述</span><span class="sxs-lookup"><span data-stu-id="a25e7-109">Overview of the process</span></span>

<span data-ttu-id="a25e7-110">[文档理解](document-understanding-overview.md) 使用人工智能 (AI) 模型来自动分类文件和提取信息。</span><span class="sxs-lookup"><span data-stu-id="a25e7-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="a25e7-111">从非结构化和半结构化文档提取信息时，文档理解模型也是最佳选择，其中您需要的信息未包含在表或表单（如合同）中。</span><span class="sxs-lookup"><span data-stu-id="a25e7-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="a25e7-112">首先，您需要查找至少五个示例文件，您可以使用这些文件对模型进行"训练"，以搜索特定于您尝试识别合同内容类型 (的特征) 。</span><span class="sxs-lookup"><span data-stu-id="a25e7-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="a25e7-113">使用 SharePoint Syntex，创建新的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="a25e7-114">使用示例文件，需要 [创建分类器](create-a-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="a25e7-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="a25e7-115">通过使用示例文件对分类器进行培训，可以指导它搜索特定于公司合同内容的特征。</span><span class="sxs-lookup"><span data-stu-id="a25e7-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="a25e7-116">例如，[创建一个"说明"，](create-a-classifier.md#create-an-explanation)搜索您的合同（如服务协议、协议条款和补偿）中的特定 *字符串*。 </span><span class="sxs-lookup"><span data-stu-id="a25e7-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="a25e7-117">甚至可以对说明进行培训，以在文档的特定节中查找这些字符串，或查找位于其他字符串旁边的字符串。</span><span class="sxs-lookup"><span data-stu-id="a25e7-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="a25e7-118">如果您认为已使用分类器所需的信息对分类器进行培训，您可以对示例文件集测试模型，以查看其效率。</span><span class="sxs-lookup"><span data-stu-id="a25e7-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="a25e7-119">测试后，如果需要，可以选择更改说明，使其更高效。</span><span class="sxs-lookup"><span data-stu-id="a25e7-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="a25e7-120">在你的模型中，可以创建 [提取程序](create-an-extractor.md) 以从每个合约中提取特定部分的数据。</span><span class="sxs-lookup"><span data-stu-id="a25e7-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="a25e7-121">例如，对于每个合同，您最关心的信息是客户是谁、承包商的名称和总成本。</span><span class="sxs-lookup"><span data-stu-id="a25e7-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="a25e7-122">成功创建模型后，[请应用于SharePoint库](apply-a-model.md)。</span><span class="sxs-lookup"><span data-stu-id="a25e7-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="a25e7-123">当您将文档上载到文档库时，您的文档理解模型将运行，并识别与模型中定义的合同内容类型匹配的所有文件，并对这些文件进行分类。</span><span class="sxs-lookup"><span data-stu-id="a25e7-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="a25e7-124">归类为合同的所有文件都将在自定义库视图中显示。</span><span class="sxs-lookup"><span data-stu-id="a25e7-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="a25e7-125">这些文件还将显示在提取程序中定义的每个合约的值。</span><span class="sxs-lookup"><span data-stu-id="a25e7-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![文档库中的协定](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="a25e7-127">如果你对合同有保留要求，则还可使用模型应用保留标签，防止在[](apply-a-retention-label-to-a-model.md)指定的时段内删除合同。</span><span class="sxs-lookup"><span data-stu-id="a25e7-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="a25e7-128">创建和训练模型的步骤</span><span class="sxs-lookup"><span data-stu-id="a25e7-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="a25e7-129">对于这些步骤，可以使用合同管理解决方案资产存储库中 [的示例文件](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。</span><span class="sxs-lookup"><span data-stu-id="a25e7-129">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="a25e7-130">此存储库中的示例包含文档了解模型文件和用于训练模型的文件。</span><span class="sxs-lookup"><span data-stu-id="a25e7-130">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="a25e7-131">创建合同模型</span><span class="sxs-lookup"><span data-stu-id="a25e7-131">Create a Contract model</span></span>

<span data-ttu-id="a25e7-132">第一步是创建合同模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="a25e7-133">从内容中心中，选择“**新建**”，然后选择“**创建模型**”。</span><span class="sxs-lookup"><span data-stu-id="a25e7-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="a25e7-134">在" **新建文档理解模型** "窗格的" **名称** "字段中，键入模型的名称。</span><span class="sxs-lookup"><span data-stu-id="a25e7-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="a25e7-135">对于此合同管理解决方案，您可以命名模型 *合同*。</span><span class="sxs-lookup"><span data-stu-id="a25e7-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="a25e7-136">选择 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-136">Choose **Create**.</span></span> <span data-ttu-id="a25e7-137">这将为该模型创建主页。</span><span class="sxs-lookup"><span data-stu-id="a25e7-137">This creates a home page for the model.</span></span></br>

    ![合同主页的屏幕截图。](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="a25e7-139">培训模型以对文件类型进行分类</span><span class="sxs-lookup"><span data-stu-id="a25e7-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="a25e7-140">为模型添加示例文件</span><span class="sxs-lookup"><span data-stu-id="a25e7-140">Add example files for your model</span></span>

<span data-ttu-id="a25e7-141">您需要添加至少五个作为合同文档的示例文件，以及一个不是合同文档的示例文件 (例如，工作) 。</span><span class="sxs-lookup"><span data-stu-id="a25e7-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="a25e7-142">在"**模型>"** 页上的"**关键操作**  >  **""添加示例文件"下**，选择"**添加文件"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![显示突出显示"添加示例文件"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="a25e7-144">在"**为模型选择示例** 文件"页上，打开"合同"文件夹，选择想要使用的文件，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="a25e7-145">如果没有示例文件，请选择 **Upload添加它们**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="a25e7-146">将文件标记为正或负示例</span><span class="sxs-lookup"><span data-stu-id="a25e7-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="a25e7-147">On the **Models > Contract** page， under Key **actions** Classify files and  >  **run training，** select Train **classifier**.</span><span class="sxs-lookup"><span data-stu-id="a25e7-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![显示突出显示了"分类文件并运行培训"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="a25e7-149">在"模型>合同>分类器"页上，第一个示例文件顶部的查看器中，你将看到询问该文件是否就是您创建的合同模型示例的文本。</span><span class="sxs-lookup"><span data-stu-id="a25e7-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="a25e7-150">如果是正例，请选择 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="a25e7-151">如果是反例，请选择 **“否”**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="a25e7-152">从 **左侧的"已** 标记示例"列表中，选择要用作示例的其他文件，然后标记它们。</span><span class="sxs-lookup"><span data-stu-id="a25e7-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![分类器主页](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;a25e7-154&quot;>至少添加一个解释来训练分类器</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;a25e7-155&quot;>在&quot; **合同>分类>&quot;** 页上，选择&quot; **训练&quot;** 选项卡。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;a25e7-156&quot;>在 **&quot;训练文件** &quot;部分，你将看到之前标记的示例文件列表。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;a25e7-157&quot;>从列表中选择一个正文件，以在查看器中显示。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;a25e7-158&quot;>在&quot;**说明&quot;** 部分，选择 **&quot;新建&quot;，** 然后选择&quot;**空白&quot;。**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;a25e7-159&quot;>在“**创建说明**”页面上：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;a25e7-160&quot;>a.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a25e7-160&quot;>a.</span></span> <span data-ttu-id=&quot;a25e7-161&quot;>在 **&quot;名称** &quot;字段中，键入说明名称 (&quot;协议") 。</span><span class="sxs-lookup"><span data-stu-id="a25e7-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="a25e7-162">b.</span><span class="sxs-lookup"><span data-stu-id="a25e7-162">b.</span></span> <span data-ttu-id="a25e7-163">在" **说明类型"** 字段中，选择" **短语列表"，** 因为您添加了文本字符串。</span><span class="sxs-lookup"><span data-stu-id="a25e7-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="a25e7-164">c.</span><span class="sxs-lookup"><span data-stu-id="a25e7-164">c.</span></span> <span data-ttu-id="a25e7-165">在" **短语"列表** 框中，键入字符串 ("AGREEMENT") 。</span><span class="sxs-lookup"><span data-stu-id="a25e7-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="a25e7-166">如果字符串 **需要区分** 大小写，可以选择区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a25e7-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="a25e7-167">d.</span><span class="sxs-lookup"><span data-stu-id="a25e7-167">d.</span></span> <span data-ttu-id="a25e7-168">选择 **保存并训练**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-168">Select **Save and train**.</span></span>

    !["创建说明"面板的屏幕截图。](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="a25e7-170">测试模型</span><span class="sxs-lookup"><span data-stu-id="a25e7-170">Test your model</span></span>

<span data-ttu-id="a25e7-171">你可以对之前未看到的示例文件测试合同模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="a25e7-172">这是可选的，但它可能是一种有用的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="a25e7-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="a25e7-173">在" **模型>合同>分类** 器"页上，选择"测试 **"** 选项卡。这将对未标记的示例文件运行模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="a25e7-174">在 **"测试文件** "列表中，示例文件显示并显示模型是否预测它们为正数或负数。</span><span class="sxs-lookup"><span data-stu-id="a25e7-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="a25e7-175">使用此信息以帮助确定分类器在文档识别中的有效性。</span><span class="sxs-lookup"><span data-stu-id="a25e7-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    !["文本文件"列表中未标记文件的屏幕截图](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="a25e7-177">完成后，选择退出 **培训**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="a25e7-178">创建和训练提取程序</span><span class="sxs-lookup"><span data-stu-id="a25e7-178">Create and train an extractor</span></span>

1. <span data-ttu-id="a25e7-179">On the **Models > Contract** page， under Key **actions** Create and  >  **train extractors，** select Create **extractor**.</span><span class="sxs-lookup"><span data-stu-id="a25e7-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![显示突出显示了"创建和训练提取程序"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="a25e7-181">在" **新建实体提取程序"** 面板的" **新建名称** "字段中，键入提取程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a25e7-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="a25e7-182">例如， *如果要从每个* 合约中提取客户端的名称，则将它取名称为 Client。</span><span class="sxs-lookup"><span data-stu-id="a25e7-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="a25e7-183">完成后，选择创建 **。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="a25e7-184">标记要提取的实体</span><span class="sxs-lookup"><span data-stu-id="a25e7-184">Label the entity you want to extract</span></span>

<span data-ttu-id="a25e7-185">创建提取程序时，将打开提取程序页。</span><span class="sxs-lookup"><span data-stu-id="a25e7-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="a25e7-186">此时，将看到示例文件的列表，并在查看器中显示列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="a25e7-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

!["客户端提取程序标记的示例"页的屏幕截图。](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="a25e7-188">若要标记实体，</span><span class="sxs-lookup"><span data-stu-id="a25e7-188">To label the entity:</span></span>

1. <span data-ttu-id="a25e7-189">从查看器中，选择要从文件中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="a25e7-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="a25e7-190">例如，如果要提取 *客户端*，请突出显示此示例中第一个文件 ("最适合您有机 *) ，* 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="a25e7-191">你将看到"标签"列下的"已标记示例"列表中文件 **显示** 的值。</span><span class="sxs-lookup"><span data-stu-id="a25e7-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="a25e7-192">选择 **"下** 一个文件"以自动保存，然后打开查看器列表中的下一个文件。</span><span class="sxs-lookup"><span data-stu-id="a25e7-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="a25e7-193">或选择 **"保存**"，然后从"已 **标记的示例"列表中选择另一** 个文件。</span><span class="sxs-lookup"><span data-stu-id="a25e7-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="a25e7-194">在查看器中，重复步骤 1 和 2，然后重复，直到将标签保存在所有文件中。</span><span class="sxs-lookup"><span data-stu-id="a25e7-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="a25e7-195">标记文件后，将显示通知横幅，通知你移动到培训。</span><span class="sxs-lookup"><span data-stu-id="a25e7-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="a25e7-196">可以选择标记更多文档或继续培训。</span><span class="sxs-lookup"><span data-stu-id="a25e7-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="a25e7-197">添加说明</span><span class="sxs-lookup"><span data-stu-id="a25e7-197">Add an explanation</span></span>

<span data-ttu-id="a25e7-198">你可以创建一个说明，该说明提供有关实体格式本身及其在示例文件中可能具有的变体的提示。</span><span class="sxs-lookup"><span data-stu-id="a25e7-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="a25e7-199">例如，日期值可能采用许多不同的格式，例如：</span><span class="sxs-lookup"><span data-stu-id="a25e7-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="a25e7-200">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="a25e7-200">10/14/2019</span></span>
- <span data-ttu-id="a25e7-201">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="a25e7-201">October 14, 2019</span></span>
- <span data-ttu-id="a25e7-202">星期一，2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="a25e7-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="a25e7-203">为了帮助确定 *合同开始日期*，可以创建模式说明。</span><span class="sxs-lookup"><span data-stu-id="a25e7-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="a25e7-204">在"**说明"** 部分，选择 **"新建"，** 然后选择"**空白"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="a25e7-205">在“**创建说明**”页面上：</span><span class="sxs-lookup"><span data-stu-id="a25e7-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="a25e7-206">a.</span><span class="sxs-lookup"><span data-stu-id="a25e7-206">a.</span></span> <span data-ttu-id="a25e7-207">在 **"名称** "字段中，键入说明的名称 (如 *Date*) 。</span><span class="sxs-lookup"><span data-stu-id="a25e7-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="a25e7-208">b.</span><span class="sxs-lookup"><span data-stu-id="a25e7-208">b.</span></span> <span data-ttu-id="a25e7-209">在"**说明类型"** 字段中，选择"**模式列表"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="a25e7-210">c.</span><span class="sxs-lookup"><span data-stu-id="a25e7-210">c.</span></span> <span data-ttu-id="a25e7-211">在 **"值** "字段中，提供显示在示例文件中的日期变体。</span><span class="sxs-lookup"><span data-stu-id="a25e7-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="a25e7-212">例如，如果你的日期格式显示为 0/00/0000，则可在文档中输入显示的任何变体，如：</span><span class="sxs-lookup"><span data-stu-id="a25e7-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="a25e7-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="a25e7-213">0/0/0000</span></span>
    - <span data-ttu-id="a25e7-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="a25e7-214">0/00/0000</span></span>
    - <span data-ttu-id="a25e7-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="a25e7-215">00/0/0000</span></span>
    - <span data-ttu-id="a25e7-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="a25e7-216">00/00/0000</span></span>

4. <span data-ttu-id="a25e7-217">选择 **保存并训练**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="a25e7-218">再次测试模型</span><span class="sxs-lookup"><span data-stu-id="a25e7-218">Test your model again</span></span>

<span data-ttu-id="a25e7-219">你可以对之前未看到的示例文件测试合同模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="a25e7-220">这是可选的，但它可能是一种有用的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="a25e7-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="a25e7-221">在" **模型>合同>分类** 器"页上，选择"测试 **"** 选项卡。这将对未标记的示例文件运行模型。</span><span class="sxs-lookup"><span data-stu-id="a25e7-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="a25e7-222">在 **"测试文件** "列表中，示例文件显示并显示模型能否提取您需要的信息。</span><span class="sxs-lookup"><span data-stu-id="a25e7-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="a25e7-223">使用此信息以帮助确定分类器在文档识别中的有效性。</span><span class="sxs-lookup"><span data-stu-id="a25e7-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="a25e7-224">完成后，选择退出 **培训**。</span><span class="sxs-lookup"><span data-stu-id="a25e7-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="a25e7-225">将模型应用到文档库</span><span class="sxs-lookup"><span data-stu-id="a25e7-225">Apply your model to a document library</span></span>

<span data-ttu-id="a25e7-226">若要将模型应用到SharePoint库：</span><span class="sxs-lookup"><span data-stu-id="a25e7-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="a25e7-227">在"**模型>"** 页上 **的"将** 模型应用到库的关键操作"下，  >  选择"**应用模型"。**</span><span class="sxs-lookup"><span data-stu-id="a25e7-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Screenshot showing the Contracts page with Apply model to libraries option highlighted.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="a25e7-229">在 **"添加** 合同"SharePoint，选择包含要应用模型的文档库的网站。</span><span class="sxs-lookup"><span data-stu-id="a25e7-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="a25e7-230">如果该网站未显示在列表中，请使用搜索框进行查找。</span><span class="sxs-lookup"><span data-stu-id="a25e7-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="a25e7-231">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a25e7-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a25e7-232">你必须拥有 *管理列表* 权限，或者 *编辑* 对应用模型的文档库的权限。</span><span class="sxs-lookup"><span data-stu-id="a25e7-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="a25e7-233">选择网站后，选择要应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="a25e7-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="a25e7-234">由于模型与内容类型相关联，因此在将模型应用到库时，它将添加内容类型及其视图，其中提取的标签以列显示。</span><span class="sxs-lookup"><span data-stu-id="a25e7-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="a25e7-235">默认情况下，此视图是库的默认视图，但可以选择不作为默认视图，选择"高级设置"并清除"将这个新视图设置为 **默认视图"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="a25e7-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="a25e7-236">选择 **“添加”** 将模型应用到库中。</span><span class="sxs-lookup"><span data-stu-id="a25e7-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="a25e7-237">在 **"模型>合约**"页上的"具有此模型的库"部分，你将看到列出的SharePoint URL。</span><span class="sxs-lookup"><span data-stu-id="a25e7-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![显示"具有此模型的库"部分合同主页的屏幕截图。](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="a25e7-239">将模型应用到文档库后，您可以开始将文档上载到网站并查看结果。</span><span class="sxs-lookup"><span data-stu-id="a25e7-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="a25e7-240">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a25e7-240">Next step</span></span>

[<span data-ttu-id="a25e7-241">步骤 2.使用Microsoft Teams创建合同管理通道</span><span class="sxs-lookup"><span data-stu-id="a25e7-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)