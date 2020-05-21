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
ms.openlocfilehash: 99d1d9039ef70347515f80da73a487f40534d2e7
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327754"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a><span data-ttu-id="a4c98-105">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="a4c98-105">Getting started with trainable classifiers (preview)</span></span>

<span data-ttu-id="a4c98-106">对内容进行分类和标记，以便可以对其进行保护和正确处理，这是信息保护训练科目的起始位置。</span><span class="sxs-lookup"><span data-stu-id="a4c98-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="a4c98-107">Microsoft 365 有三种对内容进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="a4c98-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="a4c98-108">手动</span><span class="sxs-lookup"><span data-stu-id="a4c98-108">Manually</span></span>

<span data-ttu-id="a4c98-109">此方法需要人为判断力和行动。</span><span class="sxs-lookup"><span data-stu-id="a4c98-109">This method requires human judgment and action.</span></span> <span data-ttu-id="a4c98-110">管理员既可以使用预先存在的标签和敏感信息类型，也可以创建它们自己的，然后发布它们。</span><span class="sxs-lookup"><span data-stu-id="a4c98-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="a4c98-111">用户和管理员会在遇到问题时将其应用于内容。</span><span class="sxs-lookup"><span data-stu-id="a4c98-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="a4c98-112">然后，您可以保护内容并管理其处置。</span><span class="sxs-lookup"><span data-stu-id="a4c98-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="a4c98-113">自动模式匹配</span><span class="sxs-lookup"><span data-stu-id="a4c98-113">Automated pattern matching</span></span>

<span data-ttu-id="a4c98-114">此类别的分类机制包括通过以下方式查找内容：</span><span class="sxs-lookup"><span data-stu-id="a4c98-114">This category of classification mechanisms includes finding content by:</span></span>

- <span data-ttu-id="a4c98-115">关键字或元数据值（关键字查询语言）</span><span class="sxs-lookup"><span data-stu-id="a4c98-115">keywords or metadata values (keyword query language)</span></span>
- <span data-ttu-id="a4c98-116">使用以前确定的敏感信息模式，如社会安全性、信用卡或银行帐户号码[（敏感信息类型实体定义）](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="a4c98-116">using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md)</span></span>
- <span data-ttu-id="a4c98-117">识别项目，因为它是模板的变体[（文档指纹打印）](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="a4c98-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md)</span></span>
- <span data-ttu-id="a4c98-118">使用确切的字符串[（精确数据匹配）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)的状态。</span><span class="sxs-lookup"><span data-stu-id="a4c98-118">using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).'</span></span>

<span data-ttu-id="a4c98-119">然后，可以自动应用敏感度和保留标签，以使内容可用于[数据丢失防护（DLP）](data-loss-prevention-policies.md)和[保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c98-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [retention policies](retention-policies.md).</span></span>

## <a name="trainable-classifiers"></a><span data-ttu-id="a4c98-120">Trainable 类元</span><span class="sxs-lookup"><span data-stu-id="a4c98-120">Trainable classifiers</span></span>

<span data-ttu-id="a4c98-121">此分类方法尤其适合于手动或自动模式匹配方法无法轻松识别的内容。</span><span class="sxs-lookup"><span data-stu-id="a4c98-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="a4c98-122">此分类方法详细介绍了如何培训分类器，以根据项目的具体内容（而不是项目中的元素）来标识项目（模式匹配）。</span><span class="sxs-lookup"><span data-stu-id="a4c98-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="a4c98-123">分类器了解如何通过查看您感兴趣的内容的数百个示例来标识内容类型。</span><span class="sxs-lookup"><span data-stu-id="a4c98-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="a4c98-124">首先，我们对类别中明确的示例进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="a4c98-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="a4c98-125">处理这些程序后，通过为匹配和不匹配的示例提供组合来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="a4c98-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="a4c98-126">然后，分类器将对任何给定项是否属于您要生成的类别进行预测。</span><span class="sxs-lookup"><span data-stu-id="a4c98-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="a4c98-127">然后，确认其结果，并对误报、负、误报和漏报进行排序，以帮助提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="a4c98-127">You then confirm its results, sorting out the positives, negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> <span data-ttu-id="a4c98-128">在发布训练有素的分类器时，它会通过 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。</span><span class="sxs-lookup"><span data-stu-id="a4c98-128">When you publish the trained classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4c98-129">内置分类器和 trainable 分类器都可用作基于条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)的条件。</span><span class="sxs-lookup"><span data-stu-id="a4c98-129">Both built-in classifiers and trainable classifiers are available as a condition for [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and [communication compliance](communication-compliance.md).</span></span> <span data-ttu-id="a4c98-130">敏感度标签只能将内置分类器用作条件，请参阅[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c98-130">Sensitivity labels can only use built-in classifiers as a condition, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4c98-131">Trainable 类元仅适用于未加密且为英语的项目。</span><span class="sxs-lookup"><span data-stu-id="a4c98-131">Trainable classifiers only work with items that are not encrypted and are in English.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="a4c98-132">许可要求</span><span class="sxs-lookup"><span data-stu-id="a4c98-132">Licensing requirements</span></span>

<span data-ttu-id="a4c98-133">Trainable 分类器是 Microsoft 365 E5 或 E5 合规性功能。</span><span class="sxs-lookup"><span data-stu-id="a4c98-133">Trainable classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="a4c98-134">您必须拥有其中一种订阅才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="a4c98-134">You must have one of these subscriptions to make use of them.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="a4c98-135">分类器的类型</span><span class="sxs-lookup"><span data-stu-id="a4c98-135">Types of classifiers</span></span>

<span data-ttu-id="a4c98-136">有内置的分类器和 trainable 分类器。</span><span class="sxs-lookup"><span data-stu-id="a4c98-136">There are built-in classifiers and trainable classifiers.</span></span> <span data-ttu-id="a4c98-137">将 trainable 类元获取为可发布的状态需要进行一次投资培训。</span><span class="sxs-lookup"><span data-stu-id="a4c98-137">Getting a trainable classifier to a publishable state requires a time investment to train it.</span></span> <span data-ttu-id="a4c98-138">为了帮助您开始使用分类器，Microsoft 365 附带了几个内置的分类符。</span><span class="sxs-lookup"><span data-stu-id="a4c98-138">To help you get started using classifiers, Microsoft 365 comes with a few built-in classifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="a4c98-139">在分类和标记工作流中使用任何内置分类器之前，应根据您认为符合该类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="a4c98-139">Before using any built-in classifier in your classification and labeling workflow, you should test it against a sample of your organizations content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

### <a name="understanding-built-in-classifiers"></a><span data-ttu-id="a4c98-140">了解内置分类器</span><span class="sxs-lookup"><span data-stu-id="a4c98-140">Understanding built-in classifiers</span></span>

<span data-ttu-id="a4c98-141">Microsoft 365 附带了五个建议的内置分类器：</span><span class="sxs-lookup"><span data-stu-id="a4c98-141">Microsoft 365 comes with five recommended built-in classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="a4c98-142">我们正在弃用采用**冒犯性语言**的内置分类器，因为它生成了大量误报。</span><span class="sxs-lookup"><span data-stu-id="a4c98-142">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="a4c98-143">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="a4c98-143">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="a4c98-144">我们建议改为使用**威胁**、**猥亵**和**骚扰**内置分类符。</span><span class="sxs-lookup"><span data-stu-id="a4c98-144">We recommend using the **Threat**, **Profanity**, and **Harassment** built-in classifiers instead.</span></span>

- <span data-ttu-id="a4c98-145">**恢复**：检测作为申请人个人、教育、专业资格、工作经验和其他个人身份信息的文本帐户的项目</span><span class="sxs-lookup"><span data-stu-id="a4c98-145">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="a4c98-146">**源代码**：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项</span><span class="sxs-lookup"><span data-stu-id="a4c98-146">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>

|<span data-ttu-id="a4c98-147">语言名称</span><span class="sxs-lookup"><span data-stu-id="a4c98-147">language name</span></span>|||||
|---------|---------|---------|---------|---------|
|<span data-ttu-id="a4c98-148">ActionScript</span><span class="sxs-lookup"><span data-stu-id="a4c98-148">ActionScript</span></span>|<span data-ttu-id="a4c98-149">C</span><span class="sxs-lookup"><span data-stu-id="a4c98-149">C</span></span>        |<span data-ttu-id="a4c98-150">C#</span><span class="sxs-lookup"><span data-stu-id="a4c98-150">C#</span></span>       |<span data-ttu-id="a4c98-151">C</span><span class="sxs-lookup"><span data-stu-id="a4c98-151">C++</span></span>     |<span data-ttu-id="a4c98-152">Clojure</span><span class="sxs-lookup"><span data-stu-id="a4c98-152">Clojure</span></span>  |
|<span data-ttu-id="a4c98-153">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="a4c98-153">CoffeeScript</span></span>|<span data-ttu-id="a4c98-154">CSS</span><span class="sxs-lookup"><span data-stu-id="a4c98-154">CSS</span></span>     |<span data-ttu-id="a4c98-155">转到</span><span class="sxs-lookup"><span data-stu-id="a4c98-155">Go</span></span>       |<span data-ttu-id="a4c98-156">Haskell</span><span class="sxs-lookup"><span data-stu-id="a4c98-156">Haskell</span></span> |<span data-ttu-id="a4c98-157">HTML</span><span class="sxs-lookup"><span data-stu-id="a4c98-157">HTML</span></span>     |
|<span data-ttu-id="a4c98-158">Java</span><span class="sxs-lookup"><span data-stu-id="a4c98-158">Java</span></span>     |<span data-ttu-id="a4c98-159">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a4c98-159">JavaScript</span></span>|<span data-ttu-id="a4c98-160">Lua</span><span class="sxs-lookup"><span data-stu-id="a4c98-160">Lua</span></span>      |<span data-ttu-id="a4c98-161">MATLAB</span><span class="sxs-lookup"><span data-stu-id="a4c98-161">MATLAB</span></span>   |<span data-ttu-id="a4c98-162">Objective-C</span><span class="sxs-lookup"><span data-stu-id="a4c98-162">Objective-C</span></span>|
|<span data-ttu-id="a4c98-163">编写</span><span class="sxs-lookup"><span data-stu-id="a4c98-163">Perl</span></span>     |<span data-ttu-id="a4c98-164">PHP</span><span class="sxs-lookup"><span data-stu-id="a4c98-164">PHP</span></span>      |<span data-ttu-id="a4c98-165">Python</span><span class="sxs-lookup"><span data-stu-id="a4c98-165">Python</span></span>   |<span data-ttu-id="a4c98-166">R</span><span class="sxs-lookup"><span data-stu-id="a4c98-166">R</span></span>        |<span data-ttu-id="a4c98-167">Ruby</span><span class="sxs-lookup"><span data-stu-id="a4c98-167">Ruby</span></span>     |
|<span data-ttu-id="a4c98-168">Scala</span><span class="sxs-lookup"><span data-stu-id="a4c98-168">Scala</span></span>    |<span data-ttu-id="a4c98-169">命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="a4c98-169">Shell</span></span>    |<span data-ttu-id="a4c98-170">反应</span><span class="sxs-lookup"><span data-stu-id="a4c98-170">Swift</span></span>    |<span data-ttu-id="a4c98-171">Tex</span><span class="sxs-lookup"><span data-stu-id="a4c98-171">Tex</span></span>      |<span data-ttu-id="a4c98-172">Vim 脚本</span><span class="sxs-lookup"><span data-stu-id="a4c98-172">Vim Script</span></span>|

> [!NOTE]
> <span data-ttu-id="a4c98-173">源代码经过培训，可在大部分文本是源代码时进行检测。</span><span class="sxs-lookup"><span data-stu-id="a4c98-173">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="a4c98-174">它不检测与纯文本交错的源代码文本。</span><span class="sxs-lookup"><span data-stu-id="a4c98-174">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="a4c98-175">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、国家/地区、性别、色情方向、年龄、残疾</span><span class="sxs-lookup"><span data-stu-id="a4c98-175">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="a4c98-176">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别</span><span class="sxs-lookup"><span data-stu-id="a4c98-176">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="a4c98-177">**威胁**：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对人员或属性造成物理伤害或损坏</span><span class="sxs-lookup"><span data-stu-id="a4c98-177">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="a4c98-178">这些显示在**Microsoft 365 合规中心**  >  **数据分类（预览版）**  >  **Trainable 类元**视图中，状态为 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="a4c98-178">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分类器-可供使用的类元](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="a4c98-180">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="a4c98-180">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="a4c98-181">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="a4c98-181">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="a4c98-182">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。</span><span class="sxs-lookup"><span data-stu-id="a4c98-182">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="a4c98-183">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="a4c98-183">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

#### <a name="process-flow-for-using-built-in-classifiers"></a><span data-ttu-id="a4c98-184">使用内置分类器的过程流</span><span class="sxs-lookup"><span data-stu-id="a4c98-184">Process flow for using built-in classifiers</span></span>

<span data-ttu-id="a4c98-185">内置的类元不需要接受培训，但您需要确认他们能够在合规性解决方案中使用它们之前确定所需的内容类型。</span><span class="sxs-lookup"><span data-stu-id="a4c98-185">Built-in classifiers don't need to be trained, but you do need to confirm that they will identify the types of content that you need them to before you use them in compliance solutions.</span></span> <span data-ttu-id="a4c98-186">测试预先培训的类元将遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="a4c98-186">Testing a pre-trained classifier follows this flow.</span></span>

![处理预先培训的分类器的过程流](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a><span data-ttu-id="a4c98-188">了解 trainable 类元</span><span class="sxs-lookup"><span data-stu-id="a4c98-188">Understanding trainable classifiers</span></span>

<span data-ttu-id="a4c98-189">当内置分类器不能满足您的需求时，您可以创建和培训自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="a4c98-189">When the built-in classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="a4c98-190">创建你自己的工作有了显著的更多工作，但这些工作会更好地适应你的组织需求。</span><span class="sxs-lookup"><span data-stu-id="a4c98-190">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> <span data-ttu-id="a4c98-191">有关如何使用预先培训的分类器的详细信息，请参阅[Using a 内置分类器](classifier-using-a-ready-to-use-classifier.md)</span><span class="sxs-lookup"><span data-stu-id="a4c98-191">For more detail on how to use a pre-trained classifier, see [Using a built-in classifier](classifier-using-a-ready-to-use-classifier.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4c98-192">只有创建 trainable 分类器的用户才可以培训和查看该分类器所做的预测。</span><span class="sxs-lookup"><span data-stu-id="a4c98-192">Only the user who creates a trainable classifier can train and review predictions made by that classifier.</span></span>

#### <a name="process-flow-for-creating-trainable-classifiers"></a><span data-ttu-id="a4c98-193">创建 trainable 类元的过程流</span><span class="sxs-lookup"><span data-stu-id="a4c98-193">Process flow for creating trainable classifiers</span></span>

<span data-ttu-id="a4c98-194">创建和发布在合规性解决方案（如保留策略和通信监督）中使用的 trainable 分类程序遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="a4c98-194">Creating and publishing a trainable classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="a4c98-195">有关创建 trainable 类元的更多详细信息，请参阅[创建 trainable 分类器](classifier-creating-a-trainable-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c98-195">For more detail on creating a trainable classifier see, [Creating a trainable classifier](classifier-creating-a-trainable-classifier.md).</span></span>

![process flow trainable 类元](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a><span data-ttu-id="a4c98-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c98-197">See also</span></span>

- [<span data-ttu-id="a4c98-198">保留标签</span><span class="sxs-lookup"><span data-stu-id="a4c98-198">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a4c98-199">保留策略</span><span class="sxs-lookup"><span data-stu-id="a4c98-199">Retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="a4c98-200">Data loss prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="a4c98-200">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="a4c98-201">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a4c98-201">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a4c98-202">敏感信息类型实体定义</span><span class="sxs-lookup"><span data-stu-id="a4c98-202">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="a4c98-203">文档指纹打印</span><span class="sxs-lookup"><span data-stu-id="a4c98-203">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="a4c98-204">精确数据匹配</span><span class="sxs-lookup"><span data-stu-id="a4c98-204">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)