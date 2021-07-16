---
title: 了解敏感信息类型
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 本文概述了敏感信息类型及其检测敏感信息（如社会保险、信用卡或银行帐号）以识别敏感项目
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453617"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="70769-103">了解敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70769-103">Learn about sensitive information types</span></span>

<span data-ttu-id="70769-104">标识和分类组织控制下的敏感项目是信息保护规范的第一 [步](./information-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="70769-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="70769-105">Microsoft 365提供了三种标识项目的方法，以便对这些项目进行分类：</span><span class="sxs-lookup"><span data-stu-id="70769-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="70769-106">用户手动执行</span><span class="sxs-lookup"><span data-stu-id="70769-106">manually by users</span></span>
- <span data-ttu-id="70769-107">自动模式识别，如敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70769-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="70769-108">机器学习</span><span class="sxs-lookup"><span data-stu-id="70769-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="70769-109">敏感信息类型是基于模式的分类器。</span><span class="sxs-lookup"><span data-stu-id="70769-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="70769-110">它们检测敏感信息（如社会保险、信用卡或银行帐号）以标识敏感项目，请参阅敏感信息 [类型实体定义](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="70769-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="70769-111">敏感信息类型用于</span><span class="sxs-lookup"><span data-stu-id="70769-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="70769-112">数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="70769-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="70769-113">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70769-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="70769-114">保留标签</span><span class="sxs-lookup"><span data-stu-id="70769-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="70769-115">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="70769-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="70769-116">通信合规性</span><span class="sxs-lookup"><span data-stu-id="70769-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="70769-117">自动标记策略</span><span class="sxs-lookup"><span data-stu-id="70769-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="70769-118">隐私管理 (预览) </span><span class="sxs-lookup"><span data-stu-id="70769-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="70769-119">敏感信息类型的基本部分</span><span class="sxs-lookup"><span data-stu-id="70769-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="70769-120">每个敏感信息类型实体由以下字段定义：</span><span class="sxs-lookup"><span data-stu-id="70769-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="70769-121">name：敏感信息类型引用</span><span class="sxs-lookup"><span data-stu-id="70769-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="70769-122">description：描述敏感信息类型正在查找的内容</span><span class="sxs-lookup"><span data-stu-id="70769-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="70769-123">pattern：模式定义敏感信息类型检测到的信息。</span><span class="sxs-lookup"><span data-stu-id="70769-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="70769-124">它由以下组件组成</span><span class="sxs-lookup"><span data-stu-id="70769-124">It consists of the following components</span></span>
    - <span data-ttu-id="70769-125">Primary 元素 – 敏感信息类型要查找的主元素。</span><span class="sxs-lookup"><span data-stu-id="70769-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="70769-126">它可以 **是包含或** 不带校验和验证、关键字列表 **、关键字词典** 或函数的 **正则表达式**。</span><span class="sxs-lookup"><span data-stu-id="70769-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="70769-127">Supporting 元素 – 用作支持性证据的元素，有助于提高匹配可信度。</span><span class="sxs-lookup"><span data-stu-id="70769-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="70769-128">例如，与 SSN 号码接近的关键字"SSN"。</span><span class="sxs-lookup"><span data-stu-id="70769-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="70769-129">它可以是包含或不带校验和验证、关键字列表、关键字词典的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="70769-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="70769-130">可信度 - 高 (、中、低) 可信度反映与主要元素一起检测到的支持性证据量。</span><span class="sxs-lookup"><span data-stu-id="70769-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="70769-131">项目包含的支持性证据越充分，匹配项包含所查找敏感信息的置信度越高。</span><span class="sxs-lookup"><span data-stu-id="70769-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="70769-132">邻近度 – 主要元素和支持元素之间的字符数</span><span class="sxs-lookup"><span data-stu-id="70769-132">Proximity – Number of characters between primary and supporting element</span></span>

![确证性证据和接近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="70769-134">在此视频中了解有关可信度级别更多信息</span><span class="sxs-lookup"><span data-stu-id="70769-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="70769-135">敏感信息类型示例</span><span class="sxs-lookup"><span data-stu-id="70769-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="70769-136">阿根廷国家/ (DNI) 号码</span><span class="sxs-lookup"><span data-stu-id="70769-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="70769-137">格式</span><span class="sxs-lookup"><span data-stu-id="70769-137">Format</span></span>

<span data-ttu-id="70769-138">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="70769-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="70769-139">模式</span><span class="sxs-lookup"><span data-stu-id="70769-139">Pattern</span></span>

<span data-ttu-id="70769-140">八个数字：</span><span class="sxs-lookup"><span data-stu-id="70769-140">Eight digits:</span></span>
- <span data-ttu-id="70769-141">两个数字</span><span class="sxs-lookup"><span data-stu-id="70769-141">two digits</span></span>
- <span data-ttu-id="70769-142">a period</span><span class="sxs-lookup"><span data-stu-id="70769-142">a period</span></span>
- <span data-ttu-id="70769-143">三个数字</span><span class="sxs-lookup"><span data-stu-id="70769-143">three digits</span></span>
- <span data-ttu-id="70769-144">a period</span><span class="sxs-lookup"><span data-stu-id="70769-144">a period</span></span>
- <span data-ttu-id="70769-145">三个数字</span><span class="sxs-lookup"><span data-stu-id="70769-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="70769-146">校验和</span><span class="sxs-lookup"><span data-stu-id="70769-146">Checksum</span></span>

<span data-ttu-id="70769-147">否</span><span class="sxs-lookup"><span data-stu-id="70769-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="70769-148">定义</span><span class="sxs-lookup"><span data-stu-id="70769-148">Definition</span></span>

<span data-ttu-id="70769-149">DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：</span><span class="sxs-lookup"><span data-stu-id="70769-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="70769-150">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="70769-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="70769-151">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="70769-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="70769-152">关键字</span><span class="sxs-lookup"><span data-stu-id="70769-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="70769-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="70769-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="70769-154">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="70769-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="70769-155">标识</span><span class="sxs-lookup"><span data-stu-id="70769-155">Identity</span></span> 
- <span data-ttu-id="70769-156">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="70769-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="70769-157">DNI</span><span class="sxs-lookup"><span data-stu-id="70769-157">DNI</span></span> 
- <span data-ttu-id="70769-158">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="70769-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="70769-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="70769-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="70769-160">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="70769-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="70769-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="70769-161">Identidad</span></span> 
- <span data-ttu-id="70769-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="70769-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="70769-163">有关可信度的更多</span><span class="sxs-lookup"><span data-stu-id="70769-163">More on confidence levels</span></span>

<span data-ttu-id="70769-164">在敏感信息类型实体定义中，可信度反映除了主要元素之外检测到的支持性证据的多少。</span><span class="sxs-lookup"><span data-stu-id="70769-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="70769-165">项目包含的支持性证据越充分，匹配项包含所查找敏感信息的置信度越高。</span><span class="sxs-lookup"><span data-stu-id="70769-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="70769-166">例如，高可信度的匹配将包含与主要元素接近的更多支持性证据，而低可信度的匹配将包含几乎或没有任何接近度的支持性证据。</span><span class="sxs-lookup"><span data-stu-id="70769-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="70769-167">高可信度返回最小的误报，但可能会导致更多的误报。</span><span class="sxs-lookup"><span data-stu-id="70769-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="70769-168">低或中等可信度返回更多的误报，但漏报很少。</span><span class="sxs-lookup"><span data-stu-id="70769-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="70769-169">**低可信度**：值 65，匹配项将包含最小的漏报，但误报最多。</span><span class="sxs-lookup"><span data-stu-id="70769-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="70769-170">低可信度返回所有低、中和高可信度匹配。</span><span class="sxs-lookup"><span data-stu-id="70769-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="70769-171">**中等可信度**：值为 75，匹配项将包含误报和漏报的平均数量。</span><span class="sxs-lookup"><span data-stu-id="70769-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="70769-172">中置信度返回所有中高可信度匹配。</span><span class="sxs-lookup"><span data-stu-id="70769-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="70769-173">**高** 可信度：值为 85 时，匹配的项将包含最小的误报，但包含最多的漏报。</span><span class="sxs-lookup"><span data-stu-id="70769-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="70769-174">高可信度仅返回高可信度匹配。</span><span class="sxs-lookup"><span data-stu-id="70769-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="70769-175">你应该将高可信度模式与较低的计数（如 5 到 10）和低可信度模式（如 20 个或多个）一同使用。</span><span class="sxs-lookup"><span data-stu-id="70769-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="70769-176">如果你有现有的策略或自定义敏感信息类型 (SIT) 使用基于数字的可信度 (也知道为准确性) ，则它们将自动映射到三个离散可信度;整个安全 @ 合规中心 UI 中的低可信度、中等可信度和高可信度。</span><span class="sxs-lookup"><span data-stu-id="70769-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="70769-177">置信度在 76 和 100 之间的最低准确度或自定义 SIT 模式的所有策略都将映射到高可信度。</span><span class="sxs-lookup"><span data-stu-id="70769-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="70769-178">置信度在 66 和 75 之间的最低准确度或自定义 SIT 模式的所有策略都将映射到中等可信度。</span><span class="sxs-lookup"><span data-stu-id="70769-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="70769-179">置信度低于或等于 65 的所有策略或自定义 SIT 模式都将映射到低可信度。</span><span class="sxs-lookup"><span data-stu-id="70769-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="70769-180">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70769-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="70769-181">若要在安全与合规中心内创建自定义敏感信息类型，可使用以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="70769-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="70769-182">**使用 UI** 可以使用安全与合规中心 UI 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70769-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="70769-183">通过此方法，你可以使用正则表达式、关键字和关键字字典。</span><span class="sxs-lookup"><span data-stu-id="70769-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="70769-184">若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="70769-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="70769-185">**使用 EDM** 可以使用基于精确数据匹配 (EDM) 的分类创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70769-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="70769-186">通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70769-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="70769-187">请参阅[使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="70769-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="70769-188">**使用 PowerShell** 可以使用 PowerShell 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70769-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="70769-189">尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。</span><span class="sxs-lookup"><span data-stu-id="70769-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="70769-190">请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="70769-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="70769-191">改进的可信度可在 Microsoft 365 服务的数据丢失防护、Microsoft 信息保护 Microsoft 365 服务、通信合规性、信息管理和记录管理中立即使用。</span><span class="sxs-lookup"><span data-stu-id="70769-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="70769-192">Microsoft 365信息保护现在支持双字节字符集语言，</span><span class="sxs-lookup"><span data-stu-id="70769-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="70769-193">简体中文</span><span class="sxs-lookup"><span data-stu-id="70769-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="70769-194">繁体中文</span><span class="sxs-lookup"><span data-stu-id="70769-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="70769-195">韩语</span><span class="sxs-lookup"><span data-stu-id="70769-195">Korean</span></span>
> - <span data-ttu-id="70769-196">日语</span><span class="sxs-lookup"><span data-stu-id="70769-196">Japanese</span></span>
> 
> <span data-ttu-id="70769-197">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70769-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="70769-198">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="70769-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="70769-199">若要检测含有中文/日文字符和单字节字符的模式，或检测含有中文/日文和英文的模式，则需要定义两个变体的关键词或词组。</span><span class="sxs-lookup"><span data-stu-id="70769-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="70769-200">例如，若要检测像“机密的文件”这样的关键词，则要使用该关键词的两个变体; 一个是在日语和英语文本之间有空格，另一个是在日语和英语文本之间没有空格。</span><span class="sxs-lookup"><span data-stu-id="70769-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="70769-201">因此，在 SIT 中要添加的关键词应该是“机密的 文档”和“机密的文档”。</span><span class="sxs-lookup"><span data-stu-id="70769-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="70769-202">同样，若要检测短语 "東京オリンピック2020"，则应该使用两个变体;“東京オリンピック 2020”和“東京オリンピック2020”。</span><span class="sxs-lookup"><span data-stu-id="70769-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="70769-p118">当使用双字节连字符或双字节句号创建 regex 时，请确保像在 regex 中转义连字符或句号一样转义这两个字符。以下是供参考的示例 regex：</span><span class="sxs-lookup"><span data-stu-id="70769-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="70769-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="70769-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="70769-206">我们建议在关键字列表中使用字符串匹配而不是单词匹配。</span><span class="sxs-lookup"><span data-stu-id="70769-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="70769-207">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="70769-207">For further information</span></span>
- [<span data-ttu-id="70769-208">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="70769-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="70769-209">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70769-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="70769-210">在 PowerShell 中创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70769-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="70769-211">若要了解如何使用敏感信息类型来遵守数据隐私法规，请参阅使用 Microsoft 365 (aka.ms/m365dataprivacy) 为数据隐私[法规部署](../solutions/information-protection-deploy.md)信息保护。</span><span class="sxs-lookup"><span data-stu-id="70769-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
