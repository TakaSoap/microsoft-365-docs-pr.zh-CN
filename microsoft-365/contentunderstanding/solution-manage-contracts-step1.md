---
title: 步骤 1. 使用 SharePoint Syntex 标识协定文件并提取数据
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何使用 SharePoint Syntex 来识别合约文件，并使用 Microsoft 365 提取数据。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281088"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="57494-104">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="57494-104">Step 1.</span></span> <span data-ttu-id="57494-105">使用 SharePoint Syntex 标识协定文件并提取数据</span><span class="sxs-lookup"><span data-stu-id="57494-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="57494-106">贵组织需要一种方法从您收到的许多文件中标识所有合同文档并对这些文档进行分类。</span><span class="sxs-lookup"><span data-stu-id="57494-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="57494-107">您还需要能够快速查看每个识别为 (合同文件中的几个关键元素，例如，Client、Contract 和 Fee  *amount*) 。 </span><span class="sxs-lookup"><span data-stu-id="57494-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="57494-108">为此，可以使用[Syntex](index.md) SharePoint文档理解模型，并应用到文档库。</span><span class="sxs-lookup"><span data-stu-id="57494-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

<span data-ttu-id="57494-109">[文档理解](document-understanding-overview.md) 使用人工智能 (AI) 模型来自动分类文件和提取信息。</span><span class="sxs-lookup"><span data-stu-id="57494-109">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="57494-110">从非结构化和半结构化文档提取信息时，文档理解模型也是最佳选择，其中您需要的信息未包含在表或表单（如合同）中。</span><span class="sxs-lookup"><span data-stu-id="57494-110">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="57494-111">首先，您需要查找至少五个示例文件，您可以使用这些文件对模型进行"训练"，以搜索特定于您尝试识别合同内容类型 (的特征) 。</span><span class="sxs-lookup"><span data-stu-id="57494-111">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="57494-112">使用 SharePoint Syntex，创建新的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="57494-112">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="57494-113">使用示例文件，需要 [创建分类器](create-a-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="57494-113">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="57494-114">通过使用示例文件对分类器进行培训，可以指导它搜索特定于公司合同内容的特征。</span><span class="sxs-lookup"><span data-stu-id="57494-114">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="57494-115">例如，[创建一个"说明"，](create-a-classifier.md#create-an-explanation)搜索您的合同（如服务协议、协议条款和补偿）中的特定 *字符串*。 </span><span class="sxs-lookup"><span data-stu-id="57494-115">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="57494-116">甚至可以对说明进行培训，以在文档的特定节中查找这些字符串，或查找位于其他字符串旁边的字符串。</span><span class="sxs-lookup"><span data-stu-id="57494-116">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="57494-117">如果您认为已使用分类器所需的信息对分类器进行培训，您可以对示例文件集测试模型，以查看其效率。</span><span class="sxs-lookup"><span data-stu-id="57494-117">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="57494-118">测试后，如果需要，可以选择更改说明，使其更高效。</span><span class="sxs-lookup"><span data-stu-id="57494-118">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="57494-119">在你的模型中，可以创建 [提取程序](create-an-extractor.md) 以从每个合约中提取特定部分的数据。</span><span class="sxs-lookup"><span data-stu-id="57494-119">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="57494-120">例如，对于每个合同，您最关心的信息是客户是谁、承包商的名称和总成本。</span><span class="sxs-lookup"><span data-stu-id="57494-120">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="57494-121">成功创建模型后，[请应用于SharePoint库](apply-a-model.md)。</span><span class="sxs-lookup"><span data-stu-id="57494-121">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="57494-122">当您将文档上载到文档库时，您的文档理解模型将运行，并识别与模型中定义的合同内容类型匹配的所有文件，并对这些文件进行分类。</span><span class="sxs-lookup"><span data-stu-id="57494-122">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="57494-123">归类为合同的所有文件都将在自定义库视图中显示。</span><span class="sxs-lookup"><span data-stu-id="57494-123">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="57494-124">这些文件还将显示在提取程序中定义的每个合约的值。</span><span class="sxs-lookup"><span data-stu-id="57494-124">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![文档库中的协定](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="57494-126">此外，如果您有合同保留要求，您还可以使用模型应用保留标签，以防止在指定的时段内[](apply-a-retention-label-to-a-model.md)删除合同。</span><span class="sxs-lookup"><span data-stu-id="57494-126">Additionally, if you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="next-step"></a><span data-ttu-id="57494-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="57494-127">Next step</span></span>

[<span data-ttu-id="57494-128">步骤 2.使用Microsoft Teams创建合同管理通道</span><span class="sxs-lookup"><span data-stu-id="57494-128">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)