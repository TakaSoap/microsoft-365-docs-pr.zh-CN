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
description: ''
ms.openlocfilehash: 91366e8f255d277d4d40de4c4cd3330283da718c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166447"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="42552-102">了解敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-102">Learn about sensitive information types</span></span>

<span data-ttu-id="42552-103">标识和分类组织控制下的敏感项目是信息保护规范 [的第一步](protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="42552-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="42552-104">Microsoft 365 提供了三种标识项目的方法，以便对项目进行分类：</span><span class="sxs-lookup"><span data-stu-id="42552-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="42552-105">用户手动</span><span class="sxs-lookup"><span data-stu-id="42552-105">manually by users</span></span>
- <span data-ttu-id="42552-106">自动模式识别，如敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="42552-107">机器学习</span><span class="sxs-lookup"><span data-stu-id="42552-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="42552-108">敏感信息类型是基于模式的分类器。</span><span class="sxs-lookup"><span data-stu-id="42552-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="42552-109">它们检测敏感信息（如社会保险、信用卡或银行帐号）以标识敏感项目，请参阅敏感信息 [类型实体定义](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="42552-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="42552-110">敏感信息类型用于</span><span class="sxs-lookup"><span data-stu-id="42552-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="42552-111">数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="42552-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="42552-112">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="42552-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="42552-113">保留标签</span><span class="sxs-lookup"><span data-stu-id="42552-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="42552-114">通信合规性</span><span class="sxs-lookup"><span data-stu-id="42552-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="42552-115">自动标记策略</span><span class="sxs-lookup"><span data-stu-id="42552-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="42552-116">敏感信息类型的基本部分</span><span class="sxs-lookup"><span data-stu-id="42552-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="42552-117">每个敏感信息类型实体由以下字段定义：</span><span class="sxs-lookup"><span data-stu-id="42552-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="42552-118">name：如何引用敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="42552-119">description： 描述敏感信息类型正在查找的内容</span><span class="sxs-lookup"><span data-stu-id="42552-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="42552-120">模式：模式定义敏感信息类型检测到的信息。</span><span class="sxs-lookup"><span data-stu-id="42552-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="42552-121">它由以下组件组成</span><span class="sxs-lookup"><span data-stu-id="42552-121">It consists of the following components</span></span>
    - <span data-ttu-id="42552-122">主元素 – 敏感信息类型要查找的主元素。</span><span class="sxs-lookup"><span data-stu-id="42552-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="42552-123">它可以 **是具有或** 不带校验和验证、关键字列表、关键字词典或函数的 **正则表达式**。 </span><span class="sxs-lookup"><span data-stu-id="42552-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="42552-124">支持元素 – 用作支持证据的元素，有助于提高匹配可信度。</span><span class="sxs-lookup"><span data-stu-id="42552-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="42552-125">例如，与 SSN 号码邻近的关键字"SSN"。</span><span class="sxs-lookup"><span data-stu-id="42552-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="42552-126">它可以是包含或不带校验和验证、关键字列表、关键字词典的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="42552-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="42552-127">可信度 - 置信 (高、中、低) 反映与主要元素一起检测到的支持性证据量。</span><span class="sxs-lookup"><span data-stu-id="42552-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="42552-128">项目包含的支持性证据越多，匹配项包含的敏感信息的置信度越高。</span><span class="sxs-lookup"><span data-stu-id="42552-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="42552-129">邻近度 – 主要元素和支持元素之间的字符数</span><span class="sxs-lookup"><span data-stu-id="42552-129">Proximity – Number of characters between primary and supporting element</span></span>

![确证性证据和接近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="42552-131">在此视频中了解有关可信度的更多信息</span><span class="sxs-lookup"><span data-stu-id="42552-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="42552-132">敏感信息类型示例</span><span class="sxs-lookup"><span data-stu-id="42552-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="42552-133">阿根廷国家/ (DNI) 号码</span><span class="sxs-lookup"><span data-stu-id="42552-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="42552-134">Format</span><span class="sxs-lookup"><span data-stu-id="42552-134">Format</span></span>

<span data-ttu-id="42552-135">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="42552-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="42552-136">模式</span><span class="sxs-lookup"><span data-stu-id="42552-136">Pattern</span></span>

<span data-ttu-id="42552-137">八个数字：</span><span class="sxs-lookup"><span data-stu-id="42552-137">Eight digits:</span></span>
- <span data-ttu-id="42552-138">两个数字</span><span class="sxs-lookup"><span data-stu-id="42552-138">two digits</span></span>
- <span data-ttu-id="42552-139">a period</span><span class="sxs-lookup"><span data-stu-id="42552-139">a period</span></span>
- <span data-ttu-id="42552-140">三个数字</span><span class="sxs-lookup"><span data-stu-id="42552-140">three digits</span></span>
- <span data-ttu-id="42552-141">a period</span><span class="sxs-lookup"><span data-stu-id="42552-141">a period</span></span>
- <span data-ttu-id="42552-142">三个数字</span><span class="sxs-lookup"><span data-stu-id="42552-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="42552-143">校验和</span><span class="sxs-lookup"><span data-stu-id="42552-143">Checksum</span></span>

<span data-ttu-id="42552-144">否</span><span class="sxs-lookup"><span data-stu-id="42552-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="42552-145">定义</span><span class="sxs-lookup"><span data-stu-id="42552-145">Definition</span></span>

<span data-ttu-id="42552-146">在 300 个字符的邻近度内，DLP 策略具有中等可信度，即检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="42552-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="42552-147">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="42552-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="42552-148">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="42552-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42552-149">关键字</span><span class="sxs-lookup"><span data-stu-id="42552-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="42552-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="42552-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="42552-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="42552-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="42552-152">标识</span><span class="sxs-lookup"><span data-stu-id="42552-152">Identity</span></span> 
- <span data-ttu-id="42552-153">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="42552-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="42552-154">DNI</span><span class="sxs-lookup"><span data-stu-id="42552-154">DNI</span></span> 
- <span data-ttu-id="42552-155">NIC 国家/个人注册表</span><span class="sxs-lookup"><span data-stu-id="42552-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="42552-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="42552-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="42552-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="42552-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="42552-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="42552-158">Identidad</span></span> 
- <span data-ttu-id="42552-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="42552-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="42552-160">有关可信度的更多方面</span><span class="sxs-lookup"><span data-stu-id="42552-160">More on confidence levels</span></span>

<span data-ttu-id="42552-161">在敏感信息类型实体定义中，可信度反映除了主要元素之外检测到多少支持证据。</span><span class="sxs-lookup"><span data-stu-id="42552-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="42552-162">项目包含的支持性证据越多，匹配项包含的敏感信息的置信度越高。</span><span class="sxs-lookup"><span data-stu-id="42552-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="42552-163">例如，高可信度的匹配项将包含与主要元素接近的更多支持性证据，而置信度较低的匹配将几乎不包含接近度的支持性证据。</span><span class="sxs-lookup"><span data-stu-id="42552-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="42552-164">高可信度返回最小的误报，但可能会导致漏报数更多。</span><span class="sxs-lookup"><span data-stu-id="42552-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="42552-165">低或中等可信度返回更多的误报，但漏报很少到零。</span><span class="sxs-lookup"><span data-stu-id="42552-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="42552-166">**低可信度**：值 65，匹配项将包含最小的漏报，但误报最多。</span><span class="sxs-lookup"><span data-stu-id="42552-166">**low confidence**: value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span>  
- <span data-ttu-id="42552-167">**中置** 信度 ：值 75，匹配项将包含误报和漏报的平均数量。</span><span class="sxs-lookup"><span data-stu-id="42552-167">**medium confidence**: value of 75, matched items will contain an average amount of false positives and false negatives.</span></span>  
- <span data-ttu-id="42552-168">**高可信度**：值 85，匹配的项将包含最小的误报，但包含最多的漏报。</span><span class="sxs-lookup"><span data-stu-id="42552-168">**high confidence**: value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span>  

<span data-ttu-id="42552-169">你应该将高可信度模式与较低的计数（如 5 到 10）和低可信度模式（例如 20 个或多个）一起用于较高的计数。</span><span class="sxs-lookup"><span data-stu-id="42552-169">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="42552-170">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-170">Creating custom sensitive information types</span></span>

<span data-ttu-id="42552-171">若要在安全与合规中心内创建自定义敏感信息类型，可使用以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="42552-171">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="42552-172">**使用 UI** 可以使用安全与合规中心 UI 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42552-172">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="42552-173">通过此方法，你可以使用正则表达式、关键字和关键字字典。</span><span class="sxs-lookup"><span data-stu-id="42552-173">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="42552-174">若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="42552-174">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="42552-175">**使用 EDM** 可以使用基于精确数据匹配 (EDM) 的分类创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42552-175">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="42552-176">通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42552-176">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="42552-177">请参阅[使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。</span><span class="sxs-lookup"><span data-stu-id="42552-177">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="42552-178">**使用 PowerShell** 可以使用 PowerShell 创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42552-178">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="42552-179">尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。</span><span class="sxs-lookup"><span data-stu-id="42552-179">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="42552-180">请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="42552-180">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="42552-181">改进的可信度可用于 Microsoft 365 服务的数据丢失防护、Microsoft 365 服务的 Microsoft 信息保护、通信合规性、信息管理和记录管理。</span><span class="sxs-lookup"><span data-stu-id="42552-181">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="42552-182">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="42552-182">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="42552-183">简体中文</span><span class="sxs-lookup"><span data-stu-id="42552-183">Chinese (simplified)</span></span>
> - <span data-ttu-id="42552-184">繁体中文</span><span class="sxs-lookup"><span data-stu-id="42552-184">Chinese (traditional)</span></span>
> - <span data-ttu-id="42552-185">韩语</span><span class="sxs-lookup"><span data-stu-id="42552-185">Korean</span></span>
> - <span data-ttu-id="42552-186">日语</span><span class="sxs-lookup"><span data-stu-id="42552-186">Japanese</span></span>

><span data-ttu-id="42552-187">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="42552-187">This support is available for sensitive information types.</span></span> <span data-ttu-id="42552-188">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="42552-188">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="42552-189">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="42552-189">For further information</span></span>
- [<span data-ttu-id="42552-190">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="42552-190">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="42552-191">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-191">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="42552-192">在 PowerShell 中创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="42552-192">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
