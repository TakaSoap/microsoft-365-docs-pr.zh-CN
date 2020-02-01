---
title: 可训练分类器入门（预览）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分类器是一种工具，可通过提供要查看的正负样本来识别各种类型的内容。 在分类器经过培训之后，您确认其结果是准确的。 然后，使用它搜索组织的内容，并对其进行分类以应用保留或敏感度标签，或将其包含在数据丢失防护（DLP）或保留策略中。
ms.openlocfilehash: 4b4bfa996b1f68f9db8c206aaaec43878abf3f42
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595899"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="34f85-105">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="34f85-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="34f85-106">对内容进行分类和标记，以便可以对其进行保护和正确处理，这是信息保护训练科目的起始位置。</span><span class="sxs-lookup"><span data-stu-id="34f85-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="34f85-107">Microsoft 365 有三种对内容进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="34f85-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="34f85-108">手动</span><span class="sxs-lookup"><span data-stu-id="34f85-108">Manually</span></span>

<span data-ttu-id="34f85-109">此方法需要人为判断力和行动。</span><span class="sxs-lookup"><span data-stu-id="34f85-109">This method requires human judgment and action.</span></span> <span data-ttu-id="34f85-110">管理员既可以使用预先存在的标签和敏感信息类型，也可以创建它们自己的，然后发布它们。</span><span class="sxs-lookup"><span data-stu-id="34f85-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="34f85-111">用户和管理员会在遇到问题时将其应用于内容。</span><span class="sxs-lookup"><span data-stu-id="34f85-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="34f85-112">然后，您可以保护内容并管理其处置。</span><span class="sxs-lookup"><span data-stu-id="34f85-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="34f85-113">自动模式匹配</span><span class="sxs-lookup"><span data-stu-id="34f85-113">Automated pattern matching</span></span>

<span data-ttu-id="34f85-114">此类别的分类机制包括通过以下方式查找内容：</span><span class="sxs-lookup"><span data-stu-id="34f85-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="34f85-115">关键字或元数据值（关键字查询语言）</span><span class="sxs-lookup"><span data-stu-id="34f85-115">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="34f85-116">使用以前确定的敏感信息模式，如社会安全性、信用卡或银行帐户号码[（敏感信息类型）](what-the-sensitive-information-types-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="34f85-116">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(sensitive information types)](what-the-sensitive-information-types-look-for.md)</span></span>
- <span data-ttu-id="34f85-117">识别项目，因为它是模板的变体[（文档指纹打印）](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="34f85-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="34f85-118">使用完全字符串的状态[（精确数据匹配）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="34f85-118">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="34f85-119">然后，可以自动应用敏感度和保留标签，以使内容可用于[数据丢失防护（DLP）](data-loss-prevention-policies.md)和[保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="34f85-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="34f85-120">Trainable 类元</span><span class="sxs-lookup"><span data-stu-id="34f85-120">Trainable classifiers</span></span>

<span data-ttu-id="34f85-121">此分类方法尤其适合于手动或自动模式匹配方法无法轻松识别的内容。</span><span class="sxs-lookup"><span data-stu-id="34f85-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="34f85-122">此分类方法详细介绍了如何培训分类器，以根据项目的具体内容（而不是项目中的元素）来标识项目（模式匹配）。</span><span class="sxs-lookup"><span data-stu-id="34f85-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="34f85-123">分类器了解如何通过查看您感兴趣的内容的数百个示例来标识内容类型。</span><span class="sxs-lookup"><span data-stu-id="34f85-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="34f85-124">首先，我们对类别中明确的示例进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="34f85-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="34f85-125">处理这些程序后，通过为匹配和不匹配的示例提供组合来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="34f85-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="34f85-126">然后，分类器将对任何给定项是否属于您要生成的类别进行预测。</span><span class="sxs-lookup"><span data-stu-id="34f85-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="34f85-127">然后，确认其结果，并对误报、负、误报和漏报进行排序，以帮助提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="34f85-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="34f85-128">在发布训练有素的分类器时，它会通过 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。</span><span class="sxs-lookup"><span data-stu-id="34f85-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f85-129">这两种类型的分类器都可作为基于条件和[通信合规性](communication-compliance.md)的[自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)的条件。</span><span class="sxs-lookup"><span data-stu-id="34f85-129">Both types of classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [Communication compliance](communication-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f85-130">Trainable 类元仅适用于未加密且为英语的项目。</span><span class="sxs-lookup"><span data-stu-id="34f85-130">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="34f85-131">分类器的类型</span><span class="sxs-lookup"><span data-stu-id="34f85-131">Types of classifiers</span></span>

<span data-ttu-id="34f85-132">可以使用分类器和 trainable 分类器。</span><span class="sxs-lookup"><span data-stu-id="34f85-132">There are ready to use classifiers and trainable classifiers.</span></span> <span data-ttu-id="34f85-133">将 trainable 类元获取为可发布的状态需要进行一次投资培训。</span><span class="sxs-lookup"><span data-stu-id="34f85-133">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="34f85-134">为了帮助您开始使用分类器，Microsoft 365 附带了一些准备好使用分类器的准备工作。</span><span class="sxs-lookup"><span data-stu-id="34f85-134">To help you get started using classifiers, Microsoft 365 comes with a few ready to use classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="34f85-135">在分类和标记工作流中使用任何已准备好的分类程序之前，应根据您认为适合类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="34f85-135">Before using any ready to use classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-ready-to-use-classifiers"></a><span data-ttu-id="34f85-136">了解已准备好使用类元</span><span class="sxs-lookup"><span data-stu-id="34f85-136">Understanding ready to use classifiers</span></span>

<span data-ttu-id="34f85-137">Microsoft 365 附带6个可供使用的分类器：</span><span class="sxs-lookup"><span data-stu-id="34f85-137">Microsoft 365 comes with six ready to use classifiers:</span></span>

- <span data-ttu-id="34f85-138">**冒犯性语言**：检测包含 profanities、slurs、taunts 和伪装的表达式的文本项（这是与更具冒犯性的术语具有相同意义的表达式）。</span><span class="sxs-lookup"><span data-stu-id="34f85-138">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="34f85-139">**恢复**：检测作为申请人个人、教育、专业资格、工作经验以及其他个人标识信息的文本帐户的项目。</span><span class="sxs-lookup"><span data-stu-id="34f85-139">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="34f85-140">**SourceCode**：检测包含一组用广泛使用的计算机编程语言编写的指令和语句的项。</span><span class="sxs-lookup"><span data-stu-id="34f85-140">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="34f85-141">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、民族、性别、色情方向、年龄、残疾。</span><span class="sxs-lookup"><span data-stu-id="34f85-141">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="34f85-142">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别。</span><span class="sxs-lookup"><span data-stu-id="34f85-142">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="34f85-143">**威胁**：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对个人或属性造成物理伤害或损坏。</span><span class="sxs-lookup"><span data-stu-id="34f85-143">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property.</span></span>

<span data-ttu-id="34f85-144">这些显示在**Microsoft 365 合规中心** > **数据分类（预览版）** > **Trainable 类元**视图中，状态为`Ready to use`。</span><span class="sxs-lookup"><span data-stu-id="34f85-144">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分类器-可供使用的类元](media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="34f85-146">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="34f85-146">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="34f85-147">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="34f85-147">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="34f85-148">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不打算提供组织的唯一方法来监视或响应使用此类语言。</span><span class="sxs-lookup"><span data-stu-id="34f85-148">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="34f85-149">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="34f85-149">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a><span data-ttu-id="34f85-150">使用已准备好使用类元的过程流</span><span class="sxs-lookup"><span data-stu-id="34f85-150">Process flow for using ready to use classifiers</span></span>

<span data-ttu-id="34f85-151">准备好使用类元不需要接受培训，但您需要确认他们能够在合规性解决方案中使用它们之前确定所需的内容类型。</span><span class="sxs-lookup"><span data-stu-id="34f85-151">Ready to use classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="34f85-152">测试预先培训的类元将遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="34f85-152">Testing a pre-trained classifier follows this flow.</span></span>

![处理预先培训的分类器的过程流](media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="34f85-154">了解 trainable 类元</span><span class="sxs-lookup"><span data-stu-id="34f85-154">Understanding trainable classifiers</span></span>

<span data-ttu-id="34f85-155">当准备好使用分类器不能满足您的需求时，您可以创建和培训自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="34f85-155">When the ready to use classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="34f85-156">创建你自己的工作有了显著的更多工作，但这些工作会更好地适应你的组织需求。</span><span class="sxs-lookup"><span data-stu-id="34f85-156">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="34f85-157">有关如何使用预先培训的分类器的详细信息，请参阅[使用已准备好使用分类器](classifier-using-a-ready-to-use-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="34f85-157">For more detail on how to use a pre-trained classifier, see [Using a ready to use classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f85-158">只有创建 trainable 分类器的用户才可以培训和查看该分类器所做的预测。</span><span class="sxs-lookup"><span data-stu-id="34f85-158">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="34f85-159">创建 trainable 类元的过程流</span><span class="sxs-lookup"><span data-stu-id="34f85-159">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="34f85-160">创建和发布在合规性解决方案（如保留策略和通信监督）中使用的 trainable 分类程序遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="34f85-160">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="34f85-161">有关创建 trainable 类元的更多详细信息，请参阅[创建 trainable 分类器](classifier-creating-a-trainable-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="34f85-161">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![process flow trainable 类元](media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="34f85-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34f85-163">See also</span></span>

- [<span data-ttu-id="34f85-164">保留标签</span><span class="sxs-lookup"><span data-stu-id="34f85-164">retention labels</span></span>](labels.md)
- [<span data-ttu-id="34f85-165">保留策略</span><span class="sxs-lookup"><span data-stu-id="34f85-165">retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="34f85-166">数据丢失防护（DLP）</span><span class="sxs-lookup"><span data-stu-id="34f85-166">data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="34f85-167">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="34f85-167">sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="34f85-168">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="34f85-168">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="34f85-169">文档指纹打印</span><span class="sxs-lookup"><span data-stu-id="34f85-169">document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="34f85-170">精确数据匹配</span><span class="sxs-lookup"><span data-stu-id="34f85-170">exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
