---
title: '了解 trainable 分类 (预览) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分类器是一种工具，可通过提供要查看的正负样本来识别各种类型的内容。 在分类器经过培训之后，您确认其结果是准确的。 然后，使用它来搜索组织的内容，并对其进行分类以应用保留或敏感度标签，或将其包含在数据丢失防护 (DLP) 或保留策略中。
ms.openlocfilehash: 9a628eec748681e0a22911bf7cf3774895b10ead
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132321"
---
# <a name="learn-about-classifiers-preview"></a><span data-ttu-id="97cab-105">了解 (预览的分类器) </span><span class="sxs-lookup"><span data-stu-id="97cab-105">Learn about classifiers (preview)</span></span>

<span data-ttu-id="97cab-106">对内容进行分类和标记，以便可以对其进行保护和正确处理，这是信息保护训练科目的起始位置。</span><span class="sxs-lookup"><span data-stu-id="97cab-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="97cab-107">Microsoft 365 有三种对内容进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="97cab-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="97cab-108">手动</span><span class="sxs-lookup"><span data-stu-id="97cab-108">Manually</span></span>

<span data-ttu-id="97cab-109">此方法需要人为判断力和行动。</span><span class="sxs-lookup"><span data-stu-id="97cab-109">This method requires human judgment and action.</span></span> <span data-ttu-id="97cab-110">管理员既可以使用预先存在的标签和敏感信息类型，也可以创建它们自己的，然后发布它们。</span><span class="sxs-lookup"><span data-stu-id="97cab-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="97cab-111">用户和管理员会在遇到问题时将其应用于内容。</span><span class="sxs-lookup"><span data-stu-id="97cab-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="97cab-112">然后，您可以保护内容并管理其处置。</span><span class="sxs-lookup"><span data-stu-id="97cab-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="97cab-113">自动模式匹配</span><span class="sxs-lookup"><span data-stu-id="97cab-113">Automated pattern matching</span></span>

<span data-ttu-id="97cab-114">此类别的分类机制包括通过以下方式查找内容：</span><span class="sxs-lookup"><span data-stu-id="97cab-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="97cab-115">关键字或元数据值 (关键字查询语言) 。</span><span class="sxs-lookup"><span data-stu-id="97cab-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="97cab-116">使用以前确定的敏感信息模式，如社会安全性、信用卡或银行帐户号 [ (敏感信息类型实体定义) ](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="97cab-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="97cab-117">识别项目，因为它是模板 [ (文档 finger 打印) ](document-fingerprinting.md)的变体。</span><span class="sxs-lookup"><span data-stu-id="97cab-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="97cab-118">使用确切的字符串的状态 [ (精确的数据匹配) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="97cab-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="97cab-119">然后，可以自动应用敏感度和保留标签，以使内容可用于 [数据丢失防护 (DLP) ](data-loss-prevention-policies.md) 并 [自动应用保留标签的策略](apply-retention-labels-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="97cab-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [data loss prevention (DLP)](data-loss-prevention-policies.md) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="97cab-120">符</span><span class="sxs-lookup"><span data-stu-id="97cab-120">Classifiers</span></span>

<span data-ttu-id="97cab-121">此分类方法尤其适合于手动或自动模式匹配方法无法轻松识别的内容。</span><span class="sxs-lookup"><span data-stu-id="97cab-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="97cab-122">此分类方法详细介绍了如何培训分类器，以根据项目的具体内容（而不是项目 (模式匹配) 中的元素来标识项目。</span><span class="sxs-lookup"><span data-stu-id="97cab-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="97cab-123">分类器了解如何通过查看您感兴趣的内容的数百个示例来标识内容类型。</span><span class="sxs-lookup"><span data-stu-id="97cab-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="97cab-124">首先，我们对类别中明确的示例进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="97cab-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="97cab-125">处理这些程序后，通过为匹配和不匹配的示例提供组合来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="97cab-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="97cab-126">然后，分类器将对任何给定项是否属于您要生成的类别进行预测。</span><span class="sxs-lookup"><span data-stu-id="97cab-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="97cab-127">然后，您可以确认其结果，并对真正的正值、真底片、误报和漏报进行排序，以帮助提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="97cab-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="97cab-128">发布分类器时，它会通过 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。</span><span class="sxs-lookup"><span data-stu-id="97cab-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="97cab-129">发布分类器后，您可以继续使用类似于初始培训过程的反馈流程对其进行训练。</span><span class="sxs-lookup"><span data-stu-id="97cab-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="97cab-130">在哪里可以使用 trainable 分类程序</span><span class="sxs-lookup"><span data-stu-id="97cab-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="97cab-131">内置分类器和 trainable 分类器都可用作[具有灵敏度标签的 Office autolabeling](apply-sensitivity-label-automatically.md)的条件，并根据条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="97cab-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="97cab-132">敏感度标签可以将分类器用作条件，请参阅 [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="97cab-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97cab-133">分类器仅适用于未加密且为英语的项目。</span><span class="sxs-lookup"><span data-stu-id="97cab-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="97cab-134">分类器的类型</span><span class="sxs-lookup"><span data-stu-id="97cab-134">Types of classifiers</span></span>

- <span data-ttu-id="97cab-135">**预先培训的分类** 器-Microsoft 已创建并预先培训多个分类器，您可以开始使用而无需对其进行培训。</span><span class="sxs-lookup"><span data-stu-id="97cab-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="97cab-136">这些分类符的状态将显示为 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="97cab-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="97cab-137">**自定义分类** 器-如果您的分类需求超出预先培训的分类器所涵盖的范围，则可以创建并培训自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="97cab-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="97cab-138">预先培训的分类器</span><span class="sxs-lookup"><span data-stu-id="97cab-138">Pre-trained classifiers</span></span>

<span data-ttu-id="97cab-139">Microsoft 365 附带了五个预先培训的分类器：</span><span class="sxs-lookup"><span data-stu-id="97cab-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="97cab-140">我们正在弃用 **冒犯性语言** 预培训分类器，因为它生成了大量误报。</span><span class="sxs-lookup"><span data-stu-id="97cab-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="97cab-141">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="97cab-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="97cab-142">我们建议您改用 **威胁**、 **猥亵**和 **骚扰** 预培训的分类器。</span><span class="sxs-lookup"><span data-stu-id="97cab-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="97cab-143">**恢复**：检测作为申请人个人、教育、专业资格、工作经验和其他个人身份信息的文本帐户的项目</span><span class="sxs-lookup"><span data-stu-id="97cab-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="97cab-144">**源代码**：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项</span><span class="sxs-lookup"><span data-stu-id="97cab-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="97cab-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="97cab-145">ActionScript</span></span>
    - <span data-ttu-id="97cab-146">C</span><span class="sxs-lookup"><span data-stu-id="97cab-146">C</span></span>
    - <span data-ttu-id="97cab-147">C#</span><span class="sxs-lookup"><span data-stu-id="97cab-147">C#</span></span>
    - <span data-ttu-id="97cab-148">C</span><span class="sxs-lookup"><span data-stu-id="97cab-148">C++</span></span>
    - <span data-ttu-id="97cab-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="97cab-149">Clojure</span></span>
    - <span data-ttu-id="97cab-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="97cab-150">CoffeeScript</span></span>
    - <span data-ttu-id="97cab-151">CSS</span><span class="sxs-lookup"><span data-stu-id="97cab-151">CSS</span></span>
    - <span data-ttu-id="97cab-152">转到</span><span class="sxs-lookup"><span data-stu-id="97cab-152">Go</span></span>
    - <span data-ttu-id="97cab-153">Haskell</span><span class="sxs-lookup"><span data-stu-id="97cab-153">Haskell</span></span>
    - <span data-ttu-id="97cab-154">HTML</span><span class="sxs-lookup"><span data-stu-id="97cab-154">HTML</span></span>
    - <span data-ttu-id="97cab-155">Java</span><span class="sxs-lookup"><span data-stu-id="97cab-155">Java</span></span>
    - <span data-ttu-id="97cab-156">JavaScript</span><span class="sxs-lookup"><span data-stu-id="97cab-156">JavaScript</span></span>
    - <span data-ttu-id="97cab-157">Lua</span><span class="sxs-lookup"><span data-stu-id="97cab-157">Lua</span></span>
    - <span data-ttu-id="97cab-158">MATLAB</span><span class="sxs-lookup"><span data-stu-id="97cab-158">MATLAB</span></span>
    - <span data-ttu-id="97cab-159">Objective-C</span><span class="sxs-lookup"><span data-stu-id="97cab-159">Objective-C</span></span>
    - <span data-ttu-id="97cab-160">编写</span><span class="sxs-lookup"><span data-stu-id="97cab-160">Perl</span></span>
    - <span data-ttu-id="97cab-161">PHP</span><span class="sxs-lookup"><span data-stu-id="97cab-161">PHP</span></span>
    - <span data-ttu-id="97cab-162">Python</span><span class="sxs-lookup"><span data-stu-id="97cab-162">Python</span></span>
    - <span data-ttu-id="97cab-163">R</span><span class="sxs-lookup"><span data-stu-id="97cab-163">R</span></span>
    - <span data-ttu-id="97cab-164">Ruby</span><span class="sxs-lookup"><span data-stu-id="97cab-164">Ruby</span></span>
    - <span data-ttu-id="97cab-165">Scala</span><span class="sxs-lookup"><span data-stu-id="97cab-165">Scala</span></span>
    - <span data-ttu-id="97cab-166">命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="97cab-166">Shell</span></span>
    - <span data-ttu-id="97cab-167">反应</span><span class="sxs-lookup"><span data-stu-id="97cab-167">Swift</span></span>
    - <span data-ttu-id="97cab-168">Tex</span><span class="sxs-lookup"><span data-stu-id="97cab-168">Tex</span></span>
    - <span data-ttu-id="97cab-169">Vim 脚本</span><span class="sxs-lookup"><span data-stu-id="97cab-169">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="97cab-170">源代码经过培训，可在大部分文本是源代码时进行检测。</span><span class="sxs-lookup"><span data-stu-id="97cab-170">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="97cab-171">它不检测与纯文本交错的源代码文本。</span><span class="sxs-lookup"><span data-stu-id="97cab-171">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="97cab-172">**骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、国家/地区、性别、色情方向、年龄、残疾</span><span class="sxs-lookup"><span data-stu-id="97cab-172">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="97cab-173">**猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别</span><span class="sxs-lookup"><span data-stu-id="97cab-173">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="97cab-174">**威胁**：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对人员或属性造成物理伤害或损坏</span><span class="sxs-lookup"><span data-stu-id="97cab-174">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="97cab-175">这些项将显示在**Microsoft 365 合规中心**  >  \*\*数据分类 (preview) \*\*  >  **Trainable 类元**视图，其状态为 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="97cab-175">These appear in the **Microsoft 365 compliance center** > **Data classification (preview)** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![分类器-预先培训的分类器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="97cab-177">请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="97cab-177">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="97cab-178">此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="97cab-178">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="97cab-179">虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。</span><span class="sxs-lookup"><span data-stu-id="97cab-179">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="97cab-180">您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="97cab-180">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="97cab-181">自定义分类器</span><span class="sxs-lookup"><span data-stu-id="97cab-181">Custom classifiers</span></span>

<span data-ttu-id="97cab-182">当预先培训的分类器不能满足您的需求时，您可以创建和培训自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="97cab-182">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="97cab-183">创建你自己的工作有了显著的更多工作，但这些工作会更好地适应你的组织需求。</span><span class="sxs-lookup"><span data-stu-id="97cab-183">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97cab-184">默认情况下，只有创建自定义分类器的用户才可以训练和查看该分类器所做的预测。</span><span class="sxs-lookup"><span data-stu-id="97cab-184">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="97cab-185">如果您希望其他人能够培训和查看分类器预测，请参阅 [为他人定型和审阅权限](classifier-get-started-with.md#give-others-train-and-review-rights)。</span><span class="sxs-lookup"><span data-stu-id="97cab-185">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](classifier-get-started-with.md#give-others-train-and-review-rights).</span></span>

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="97cab-186">创建自定义分类器的过程流</span><span class="sxs-lookup"><span data-stu-id="97cab-186">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="97cab-187">创建和发布在合规性解决方案（如保留策略和通信监督）中使用的分类器遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="97cab-187">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="97cab-188">有关创建自定义 trainable 类元的更多详细信息，请参阅 [创建自定义分类器](classifier-get-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="97cab-188">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![处理流自定义分类器](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="97cab-190">重新培训分类器</span><span class="sxs-lookup"><span data-stu-id="97cab-190">Retraining classifiers</span></span>

<span data-ttu-id="97cab-191">您可以通过向其提供有关其执行的分类准确性的反馈，帮助提高所有自定义分类器和一些预先培训的分类器的准确性。</span><span class="sxs-lookup"><span data-stu-id="97cab-191">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="97cab-192">这称为 "重新培训" 并遵循此工作流。</span><span class="sxs-lookup"><span data-stu-id="97cab-192">This is called retraining and follow this workflow.</span></span>

![分类器重新培训工作流](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="97cab-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97cab-194">See also</span></span>

- [<span data-ttu-id="97cab-195">保留标签</span><span class="sxs-lookup"><span data-stu-id="97cab-195">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="97cab-196">Data loss prevention (DLP)</span><span class="sxs-lookup"><span data-stu-id="97cab-196">Data loss prevention (DLP)</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="97cab-197">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="97cab-197">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="97cab-198">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="97cab-198">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="97cab-199">文档指纹打印</span><span class="sxs-lookup"><span data-stu-id="97cab-199">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="97cab-200">精确数据匹配</span><span class="sxs-lookup"><span data-stu-id="97cab-200">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
