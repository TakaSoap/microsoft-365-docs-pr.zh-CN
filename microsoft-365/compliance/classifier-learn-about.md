---
title: 了解可训练的分类器
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 可Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的正面和负面示例来识别各种类型的内容。 对分类器进行培训后，您确认其结果准确无误。 然后，使用它搜索组织的内容，并进行分类以应用保留或敏感度标签，或将其包括在 DLP 策略或保留策略 (数据丢失) 中。
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114048"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="ec270-105">了解可训练的分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="ec270-106">对内容进行分类和标记，以便可以保护和正确处理内容是信息保护规范的起点。</span><span class="sxs-lookup"><span data-stu-id="ec270-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="ec270-107">Microsoft 365三种方法对内容进行分类。</span><span class="sxs-lookup"><span data-stu-id="ec270-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="ec270-108">手动</span><span class="sxs-lookup"><span data-stu-id="ec270-108">Manually</span></span>

<span data-ttu-id="ec270-109">此方法需要人为判断和操作。</span><span class="sxs-lookup"><span data-stu-id="ec270-109">This method requires human judgment and action.</span></span> <span data-ttu-id="ec270-110">管理员可以使用预先存在的标签和敏感信息类型，也可以创建自己的标签和敏感信息类型，然后发布它们。</span><span class="sxs-lookup"><span data-stu-id="ec270-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="ec270-111">用户和管理员在遇到内容时将其应用于内容。</span><span class="sxs-lookup"><span data-stu-id="ec270-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="ec270-112">然后，您可以保护内容并管理其处置。</span><span class="sxs-lookup"><span data-stu-id="ec270-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="ec270-113">自动模式匹配</span><span class="sxs-lookup"><span data-stu-id="ec270-113">Automated pattern matching</span></span>

<span data-ttu-id="ec270-114">此分类机制类别包括按以下方法查找内容：</span><span class="sxs-lookup"><span data-stu-id="ec270-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="ec270-115">关键字或元数据值 (关键字查询语言) 。</span><span class="sxs-lookup"><span data-stu-id="ec270-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="ec270-116">使用之前标识的敏感信息模式，如社会保险、信用卡或银行帐户 ([敏感信息类型实体定义) 。 ](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="ec270-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="ec270-117">识别项，因为它是模板上的变体 ([文档手指) 。 ](document-fingerprinting.md)</span><span class="sxs-lookup"><span data-stu-id="ec270-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="ec270-118">使用存在确切字符串 ([数据完全匹配) 。 ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="ec270-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="ec270-119">然后，可以自动应用敏感度和保留标签，使内容可供在了解数据丢失防护策略[](dlp-learn-about-dlp.md)和自动应用保留) 策略中[使用](apply-retention-labels-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="ec270-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [Learn about data loss prevention](dlp-learn-about-dlp.md)) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="ec270-120">分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-120">Classifiers</span></span>

<span data-ttu-id="ec270-121">此分类方法特别适用于无法通过手动或自动模式匹配方法轻松标识的内容。</span><span class="sxs-lookup"><span data-stu-id="ec270-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="ec270-122">这种分类方法更多的是训练一个分类器，以根据项目是什么来识别项目，而不是通过项目中的元素（模式匹配）。</span><span class="sxs-lookup"><span data-stu-id="ec270-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="ec270-123">分类器通过查看对分类感兴趣的内容的数百个示例来了解如何识别内容类型。</span><span class="sxs-lookup"><span data-stu-id="ec270-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="ec270-124">首先馈送该类别中肯定属于该类别的示例。</span><span class="sxs-lookup"><span data-stu-id="ec270-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="ec270-125">处理这些示例后，通过提供匹配和非匹配示例的组合来测试它。</span><span class="sxs-lookup"><span data-stu-id="ec270-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="ec270-126">然后，分类器将预测任何给定项目是否属于你正在构建的类别。</span><span class="sxs-lookup"><span data-stu-id="ec270-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="ec270-127">然后确认其结果，对真正的正数、负数、误报和漏报进行排序，以帮助提高预测的准确性。</span><span class="sxs-lookup"><span data-stu-id="ec270-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="ec270-128">发布分类器时，分类器会按 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。</span><span class="sxs-lookup"><span data-stu-id="ec270-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="ec270-129">发布分类器后，可以继续使用与初始培训过程类似的反馈流程对分类器进行培训。</span><span class="sxs-lookup"><span data-stu-id="ec270-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="ec270-130">在哪里可以使用可训练分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="ec270-131">内置分类器和可训练分类器都作为一个条件，Office敏感度标签[](apply-sensitivity-label-automatically.md)自动标记，根据条件和通信合规性自动应用保留[标签策略](communication-compliance.md)。 [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)</span><span class="sxs-lookup"><span data-stu-id="ec270-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="ec270-132">敏感度标签可以使用分类器作为条件，请参阅自动将 [敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="ec270-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec270-133">分类器仅适用于未加密且使用英语的项目。</span><span class="sxs-lookup"><span data-stu-id="ec270-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="ec270-134">分类器的类型</span><span class="sxs-lookup"><span data-stu-id="ec270-134">Types of classifiers</span></span>

- <span data-ttu-id="ec270-135">**预先训练的分类** 器 - Microsoft 已创建大量分类器，并对这些分类器进行预先训练，无需培训即可开始使用这些分类器。</span><span class="sxs-lookup"><span data-stu-id="ec270-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="ec270-136">这些分类器将显示为 状态 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="ec270-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="ec270-137">**自定义分类** 器 - 如果你的分类需求超出了预先训练的分类器涵盖范围，可以创建并训练自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="ec270-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="ec270-138">预先训练的分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-138">Pre-trained classifiers</span></span>

<span data-ttu-id="ec270-139">Microsoft 365五个预先训练的分类器：</span><span class="sxs-lookup"><span data-stu-id="ec270-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="ec270-140">我们弃用冒犯性 **语言** 预先训练的分类器，因为它一直产生大量误报。</span><span class="sxs-lookup"><span data-stu-id="ec270-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="ec270-141">请勿使用，如果当前正在使用，应将业务流程从其中移开。</span><span class="sxs-lookup"><span data-stu-id="ec270-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="ec270-142">我们建议改为使用 **威胁**、**亵亵和\*\*\*\*骚扰** 预先训练的分类器。</span><span class="sxs-lookup"><span data-stu-id="ec270-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="ec270-143">**简历**：检测是收信人个人、教育、专业资格、工作体验和其他个人识别信息的文本帐户的项目</span><span class="sxs-lookup"><span data-stu-id="ec270-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="ec270-144">**源代码 ：** 检测包含一组使用前 25 种使用计算机编程语言编写的指令和语句GitHub</span><span class="sxs-lookup"><span data-stu-id="ec270-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="ec270-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="ec270-145">ActionScript</span></span>
    - <span data-ttu-id="ec270-146">C</span><span class="sxs-lookup"><span data-stu-id="ec270-146">C</span></span>
    - <span data-ttu-id="ec270-147">C#</span><span class="sxs-lookup"><span data-stu-id="ec270-147">C#</span></span>
    - <span data-ttu-id="ec270-148">C++</span><span class="sxs-lookup"><span data-stu-id="ec270-148">C++</span></span>
    - <span data-ttu-id="ec270-149">一些</span><span class="sxs-lookup"><span data-stu-id="ec270-149">Clojure</span></span>
    - <span data-ttu-id="ec270-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="ec270-150">CoffeeScript</span></span>
    - <span data-ttu-id="ec270-151">转到</span><span class="sxs-lookup"><span data-stu-id="ec270-151">Go</span></span>
    - <span data-ttu-id="ec270-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="ec270-152">Haskell</span></span>
    - <span data-ttu-id="ec270-153">Java</span><span class="sxs-lookup"><span data-stu-id="ec270-153">Java</span></span>
    - <span data-ttu-id="ec270-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="ec270-154">JavaScript</span></span>
    - <span data-ttu-id="ec270-155">Lua</span><span class="sxs-lookup"><span data-stu-id="ec270-155">Lua</span></span>
    - <span data-ttu-id="ec270-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="ec270-156">MATLAB</span></span>
    - <span data-ttu-id="ec270-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="ec270-157">Objective-C</span></span>
    - <span data-ttu-id="ec270-158">Perl</span><span class="sxs-lookup"><span data-stu-id="ec270-158">Perl</span></span>
    - <span data-ttu-id="ec270-159">PHP</span><span class="sxs-lookup"><span data-stu-id="ec270-159">PHP</span></span>
    - <span data-ttu-id="ec270-160">Python</span><span class="sxs-lookup"><span data-stu-id="ec270-160">Python</span></span>
    - <span data-ttu-id="ec270-161">R</span><span class="sxs-lookup"><span data-stu-id="ec270-161">R</span></span>
    - <span data-ttu-id="ec270-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="ec270-162">Ruby</span></span>
    - <span data-ttu-id="ec270-163">Scala</span><span class="sxs-lookup"><span data-stu-id="ec270-163">Scala</span></span>
    - <span data-ttu-id="ec270-164">命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="ec270-164">Shell</span></span>
    - <span data-ttu-id="ec270-165">Swift</span><span class="sxs-lookup"><span data-stu-id="ec270-165">Swift</span></span>
    - <span data-ttu-id="ec270-166">Tex</span><span class="sxs-lookup"><span data-stu-id="ec270-166">Tex</span></span>
    - <span data-ttu-id="ec270-167">Vim 脚本</span><span class="sxs-lookup"><span data-stu-id="ec270-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="ec270-168">源代码经过训练，可检测大量文本何时是源代码。</span><span class="sxs-lookup"><span data-stu-id="ec270-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="ec270-169">它不会检测与纯文本交错的源代码文本。</span><span class="sxs-lookup"><span data-stu-id="ec270-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="ec270-170">**冒犯**：根据以下特征检测与针对一个或多个个人的冒犯行为相关的特定冒犯性语言文本项类别：种族、国家/地区、性别、性取向、年龄、残障</span><span class="sxs-lookup"><span data-stu-id="ec270-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="ec270-171">**冒犯性**：检测特定类别的冒犯性语言文本项，这些文本项包含使大多数用户感同的表达式</span><span class="sxs-lookup"><span data-stu-id="ec270-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="ec270-172">**威胁**：检测与威胁相关的特定类别的冒犯性语言文本项，以实施暴力或对人员或属性进行物理损害或损害</span><span class="sxs-lookup"><span data-stu-id="ec270-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="ec270-173">这些记录Microsoft 365数据  >  **分类**  >  **可训练分类** 器视图，状态为 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="ec270-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="ec270-175">请注意，冒犯性语言、冒犯性、亵亵和威胁分类器仅适用于可搜索文本，并不详尽或完整。</span><span class="sxs-lookup"><span data-stu-id="ec270-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="ec270-176">此外，语言和文化标准会不断改变，并且鉴于这些创新，Microsoft 保留自行决定更新这些分类器的权利。</span><span class="sxs-lookup"><span data-stu-id="ec270-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="ec270-177">虽然分类器可帮助组织监视使用的攻击性语言和其他语言，但分类器不会解决此类语言的后果，也不用于提供组织监视或响应此类语言使用的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="ec270-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="ec270-178">贵组织（而不是 Microsoft 或其子公司）仍负责与监视、强制执行、阻止、删除和保留由预先训练的分类器标识的任何内容相关的所有决策。</span><span class="sxs-lookup"><span data-stu-id="ec270-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="ec270-179">自定义分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-179">Custom classifiers</span></span>

<span data-ttu-id="ec270-180">如果预先训练的分类器无法满足您的需求，您可以创建并训练自己的分类器。</span><span class="sxs-lookup"><span data-stu-id="ec270-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="ec270-181">创建自己的工作涉及明显更多工作，但它们可以更好地根据组织需求进行定制。</span><span class="sxs-lookup"><span data-stu-id="ec270-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="ec270-182">例如，你可以为：</span><span class="sxs-lookup"><span data-stu-id="ec270-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="ec270-183">法律文档 - 例如律师客户特权、结束集、工作说明</span><span class="sxs-lookup"><span data-stu-id="ec270-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="ec270-184">战略业务文档 - 如新闻稿、合并和收购、交易、业务或市场营销计划、知识产权、专利、设计文档</span><span class="sxs-lookup"><span data-stu-id="ec270-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="ec270-185">定价信息 - 如发票、报价、工作订单、采购文档</span><span class="sxs-lookup"><span data-stu-id="ec270-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="ec270-186">财务信息 - 如组织投资、季度或年度结果</span><span class="sxs-lookup"><span data-stu-id="ec270-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="ec270-187">创建自定义分类器的过程流</span><span class="sxs-lookup"><span data-stu-id="ec270-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="ec270-188">创建和发布分类器以用于合规性解决方案（如保留策略和通信监督）遵循此流程。</span><span class="sxs-lookup"><span data-stu-id="ec270-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="ec270-189">有关创建自定义可训练分类器的详细信息，请参阅 [创建自定义分类器](classifier-get-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="ec270-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![进程流自定义分类器](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="ec270-191">重新分类器</span><span class="sxs-lookup"><span data-stu-id="ec270-191">Retraining classifiers</span></span>

<span data-ttu-id="ec270-192">通过提供有关自定义分类器及其所执行分类的准确性的反馈，可以帮助提高所有自定义分类器以及一些预先训练的分类器的准确性。</span><span class="sxs-lookup"><span data-stu-id="ec270-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="ec270-193">这称为重新培训并遵循此工作流。</span><span class="sxs-lookup"><span data-stu-id="ec270-193">This is called retraining and follow this workflow.</span></span>

![分类器重新分类工作流](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="ec270-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec270-195">See also</span></span>

- [<span data-ttu-id="ec270-196">保留标签</span><span class="sxs-lookup"><span data-stu-id="ec270-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="ec270-197">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="ec270-197">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="ec270-198">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="ec270-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="ec270-199">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="ec270-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="ec270-200">文档手指打印</span><span class="sxs-lookup"><span data-stu-id="ec270-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="ec270-201">精确数据匹配</span><span class="sxs-lookup"><span data-stu-id="ec270-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
