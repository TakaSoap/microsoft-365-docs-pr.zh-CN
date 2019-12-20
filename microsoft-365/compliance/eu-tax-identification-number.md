---
title: EU 税标识号
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟税务识别号敏感信息类型时，应查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805845"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="9de30-104">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-104">EU Tax Identification Number</span></span>

<span data-ttu-id="9de30-105">本主题介绍了数据丢失防护（DLP）策略在检测到欧盟纳税标识号（TIN）敏感信息类型时的查找内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="9de30-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="9de30-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9de30-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="9de30-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9de30-108">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-108">Format</span></span>

<span data-ttu-id="9de30-109">9个数字，带可选连字符和正斜线</span><span class="sxs-lookup"><span data-stu-id="9de30-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-110">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-110">Pattern</span></span>

<span data-ttu-id="9de30-111">9个带可选连字符和正斜线的数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="9de30-112">两位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-112">Two digits</span></span> 
    
- <span data-ttu-id="9de30-113">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="9de30-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="9de30-114">三位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-114">Three digits</span></span>
    
- <span data-ttu-id="9de30-115">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="9de30-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="9de30-116">四位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-117">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-117">Checksum</span></span>

<span data-ttu-id="9de30-118">是</span><span class="sxs-lookup"><span data-stu-id="9de30-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-119">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-119">Definition</span></span>

<span data-ttu-id="9de30-120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-121">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-122">找到了中`Keywords_austria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-123">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-124">函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-125">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="9de30-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-127">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-127">tax number</span></span>
  
<span data-ttu-id="9de30-128">number</span><span class="sxs-lookup"><span data-stu-id="9de30-128">number</span></span>
  
<span data-ttu-id="9de30-129">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="9de30-129">tax registration number</span></span>
  
<span data-ttu-id="9de30-130">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-130">tax id</span></span>
  
<span data-ttu-id="9de30-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="9de30-131">st.nr.</span></span>
  
<span data-ttu-id="9de30-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="9de30-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="9de30-133">比利时</span><span class="sxs-lookup"><span data-stu-id="9de30-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9de30-134">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-134">Format</span></span>

<span data-ttu-id="9de30-135">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-136">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-136">Pattern</span></span>

<span data-ttu-id="9de30-137">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-137">11 digits:</span></span>
  
- <span data-ttu-id="9de30-138">两位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-138">Two digits</span></span>
    
- <span data-ttu-id="9de30-139">"0" 或 "1"</span><span class="sxs-lookup"><span data-stu-id="9de30-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="9de30-140">一位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-140">One digit</span></span>
    
- <span data-ttu-id="9de30-141">"0" 或 "1" 或 "2" 或 "3"</span><span class="sxs-lookup"><span data-stu-id="9de30-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="9de30-142">六个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-143">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-143">Checksum</span></span>

<span data-ttu-id="9de30-144">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-145">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-145">Definition</span></span>

<span data-ttu-id="9de30-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-147">正则表达式`Regex_belgium_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-148">找到了中`Keywords_belgium_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-149">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="9de30-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-151">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-151">tax number</span></span>
  
<span data-ttu-id="9de30-152">国家注册号码</span><span class="sxs-lookup"><span data-stu-id="9de30-152">national registration number</span></span>
  
<span data-ttu-id="9de30-153">税务登记编号</span><span class="sxs-lookup"><span data-stu-id="9de30-153">tax registration number</span></span>
  
<span data-ttu-id="9de30-154">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-154">tax id</span></span>
  
<span data-ttu-id="9de30-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="9de30-155">nif</span></span>
  
<span data-ttu-id="9de30-156">\n\n#</span><span class="sxs-lookup"><span data-stu-id="9de30-156">nif#</span></span>
  
<span data-ttu-id="9de30-157">numéro de registre 国</span><span class="sxs-lookup"><span data-stu-id="9de30-157">numéro de registre national</span></span>
  
<span data-ttu-id="9de30-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="9de30-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="9de30-159">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="9de30-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9de30-160">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-160">Format</span></span>

<span data-ttu-id="9de30-161">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-162">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-162">Pattern</span></span>

<span data-ttu-id="9de30-163">10 个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-164">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-164">Checksum</span></span>

<span data-ttu-id="9de30-165">是</span><span class="sxs-lookup"><span data-stu-id="9de30-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-166">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-166">Definition</span></span>

<span data-ttu-id="9de30-167">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-168">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-169">找到了中`Keywords_bulgaria_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-170">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-171">函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-172">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="9de30-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-174">bucn</span><span class="sxs-lookup"><span data-stu-id="9de30-174">bucn</span></span>
  
<span data-ttu-id="9de30-175">统一的民事号码</span><span class="sxs-lookup"><span data-stu-id="9de30-175">uniform civil number</span></span>
  
<span data-ttu-id="9de30-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="9de30-176">bucn#</span></span>
  
<span data-ttu-id="9de30-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="9de30-178">统一的民事 id</span><span class="sxs-lookup"><span data-stu-id="9de30-178">uniform civil id</span></span>
  
<span data-ttu-id="9de30-179">统一的民事无</span><span class="sxs-lookup"><span data-stu-id="9de30-179">uniform civil no</span></span>
  
<span data-ttu-id="9de30-180">egn</span><span class="sxs-lookup"><span data-stu-id="9de30-180">egn</span></span>
  
<span data-ttu-id="9de30-181">保加利亚语统一民事号码</span><span class="sxs-lookup"><span data-stu-id="9de30-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="9de30-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="9de30-182">uniformcivilno#</span></span>
  
<span data-ttu-id="9de30-183">egn#</span><span class="sxs-lookup"><span data-stu-id="9de30-183">egn#</span></span>
  
<span data-ttu-id="9de30-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="9de30-184">униформ граждански номер</span></span>
  
<span data-ttu-id="9de30-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="9de30-185">униформ id</span></span>
  
<span data-ttu-id="9de30-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="9de30-186">униформ граждански id</span></span>
  
<span data-ttu-id="9de30-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="9de30-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="9de30-188">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="9de30-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9de30-189">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-189">Format</span></span>

<span data-ttu-id="9de30-190">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-191">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-191">Pattern</span></span>

<span data-ttu-id="9de30-192">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-192">11 digits:</span></span>
  
- <span data-ttu-id="9de30-193">10个数字，随机选择</span><span class="sxs-lookup"><span data-stu-id="9de30-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="9de30-194">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-195">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-195">Checksum</span></span>

<span data-ttu-id="9de30-196">是</span><span class="sxs-lookup"><span data-stu-id="9de30-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-197">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-197">Definition</span></span>

<span data-ttu-id="9de30-198">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-199">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-200">找到了中`Keywords_croatia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-202">函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-203">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="9de30-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-205">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-205">tax number</span></span>
  
<span data-ttu-id="9de30-206">税种</span><span class="sxs-lookup"><span data-stu-id="9de30-206">tax</span></span>
  
<span data-ttu-id="9de30-207">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-207">tax id</span></span>
  
<span data-ttu-id="9de30-208">oid</span><span class="sxs-lookup"><span data-stu-id="9de30-208">oid</span></span>
  
<span data-ttu-id="9de30-209">排列#</span><span class="sxs-lookup"><span data-stu-id="9de30-209">oid#</span></span>
  
<span data-ttu-id="9de30-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="9de30-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="9de30-211">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="9de30-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9de30-212">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-212">Format</span></span>

<span data-ttu-id="9de30-213">指定模式中的八个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-214">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-214">Pattern</span></span>

<span data-ttu-id="9de30-215">八个数字和一个字母：</span><span class="sxs-lookup"><span data-stu-id="9de30-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="9de30-216">一个 "0"</span><span class="sxs-lookup"><span data-stu-id="9de30-216">A "0"</span></span> 
    
- <span data-ttu-id="9de30-217">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-217">Seven digits</span></span>
    
- <span data-ttu-id="9de30-218">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-219">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-219">Checksum</span></span>

<span data-ttu-id="9de30-220">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-221">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-221">Definition</span></span>

<span data-ttu-id="9de30-222">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-223">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-224">找到了中`Keywords_cyprus_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-226">函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-227">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="9de30-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-229">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-229">tax number</span></span>
  
<span data-ttu-id="9de30-230">税种</span><span class="sxs-lookup"><span data-stu-id="9de30-230">tax</span></span>
  
<span data-ttu-id="9de30-231">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-231">tax id</span></span>
  
<span data-ttu-id="9de30-232">税标识代码</span><span class="sxs-lookup"><span data-stu-id="9de30-232">tax identification code</span></span>
  
<span data-ttu-id="9de30-233">和</span><span class="sxs-lookup"><span data-stu-id="9de30-233">tic</span></span>
  
<span data-ttu-id="9de30-234">和#</span><span class="sxs-lookup"><span data-stu-id="9de30-234">tic#</span></span>
  
<span data-ttu-id="9de30-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="9de30-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="9de30-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="9de30-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="9de30-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="9de30-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="9de30-238">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="9de30-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9de30-239">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-239">Format</span></span>

<span data-ttu-id="9de30-240">9个或10个数字，带可选反斜杠</span><span class="sxs-lookup"><span data-stu-id="9de30-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-241">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-241">Pattern</span></span>

<span data-ttu-id="9de30-242">9个或10个数字，可选 backslashl：</span><span class="sxs-lookup"><span data-stu-id="9de30-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="9de30-243">六位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-243">Six digits</span></span> 
    
- <span data-ttu-id="9de30-244">反斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="9de30-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="9de30-245">三个或四个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-246">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-246">Checksum</span></span>

<span data-ttu-id="9de30-247">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-248">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-248">Definition</span></span>

<span data-ttu-id="9de30-249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-250">正则表达式`Regex_czech_republic_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-251">找到了中`Keywords_czech_republic_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-252">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="9de30-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-254">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-254">tax number</span></span>
  
<span data-ttu-id="9de30-255">税种</span><span class="sxs-lookup"><span data-stu-id="9de30-255">tax</span></span>
  
<span data-ttu-id="9de30-256">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-256">tax id</span></span>
  
<span data-ttu-id="9de30-257">个人号码</span><span class="sxs-lookup"><span data-stu-id="9de30-257">personal number</span></span>
  
<span data-ttu-id="9de30-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="9de30-258">daňové číslo</span></span>
  
<span data-ttu-id="9de30-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="9de30-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="9de30-260">丹麦</span><span class="sxs-lookup"><span data-stu-id="9de30-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9de30-261">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-261">Format</span></span>

<span data-ttu-id="9de30-262">10个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="9de30-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-263">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-263">Pattern</span></span>

<span data-ttu-id="9de30-264">包含 hyphenl 的10个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="9de30-265">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="9de30-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="9de30-266">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="9de30-266">A hyphen</span></span>
    
- <span data-ttu-id="9de30-267">与序列号对应的四个数字，其中第一个数字对应于出生世纪，最后一个数字对应于个人的性别（对于男为奇数，甚至对于母版）</span><span class="sxs-lookup"><span data-stu-id="9de30-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-268">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-268">Checksum</span></span>

<span data-ttu-id="9de30-269">是</span><span class="sxs-lookup"><span data-stu-id="9de30-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-270">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-270">Definition</span></span>

<span data-ttu-id="9de30-271">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-272">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-273">找到了中`Keywords_denmark_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-275">函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-276">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="9de30-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-278">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-278">tax number</span></span>
  
<span data-ttu-id="9de30-279">税种</span><span class="sxs-lookup"><span data-stu-id="9de30-279">tax</span></span>
  
<span data-ttu-id="9de30-280">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-280">tax id</span></span>
  
<span data-ttu-id="9de30-281">cpr 编号</span><span class="sxs-lookup"><span data-stu-id="9de30-281">cpr number</span></span>
  
<span data-ttu-id="9de30-282">cpr#</span><span class="sxs-lookup"><span data-stu-id="9de30-282">cpr#</span></span>
  
<span data-ttu-id="9de30-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="9de30-283">skat nummer</span></span>
  
<span data-ttu-id="9de30-284">skat id</span><span class="sxs-lookup"><span data-stu-id="9de30-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="9de30-285">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="9de30-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9de30-286">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-286">Format</span></span>

<span data-ttu-id="9de30-287">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-288">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-288">Pattern</span></span>

<span data-ttu-id="9de30-289">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-289">11 digits:</span></span>
  
-  <span data-ttu-id="9de30-290">一种与性别和世纪相对应的数字，其中奇数表示男，偶数表示女，如下所示：1，2代表19世纪;3，4表示20世纪;对于21世纪，为5，6</span><span class="sxs-lookup"><span data-stu-id="9de30-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="9de30-291">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9de30-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="9de30-292">三个数字，对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="9de30-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="9de30-293">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-294">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-294">Checksum</span></span>

<span data-ttu-id="9de30-295">是</span><span class="sxs-lookup"><span data-stu-id="9de30-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-296">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-296">Definition</span></span>

<span data-ttu-id="9de30-297">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-298">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-299">找到了中`Keywords_estonia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-300">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-301">函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-302">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="9de30-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-304">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-304">tax number</span></span>
  
<span data-ttu-id="9de30-305">税种</span><span class="sxs-lookup"><span data-stu-id="9de30-305">tax</span></span>
  
<span data-ttu-id="9de30-306">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-306">tax id</span></span>
  
<span data-ttu-id="9de30-307">个人代码</span><span class="sxs-lookup"><span data-stu-id="9de30-307">personal code</span></span>
  
<span data-ttu-id="9de30-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="9de30-308">maksunumber</span></span>
  
<span data-ttu-id="9de30-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="9de30-309">maksu id</span></span>
  
<span data-ttu-id="9de30-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="9de30-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="9de30-311">芬兰</span><span class="sxs-lookup"><span data-stu-id="9de30-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="9de30-312">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-312">Format</span></span>

<span data-ttu-id="9de30-313">一个11字符组合的数字、字母、加号和减号</span><span class="sxs-lookup"><span data-stu-id="9de30-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-314">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-314">Pattern</span></span>

<span data-ttu-id="9de30-315">一个11个字符的数字、字母和加号和减号的组合：</span><span class="sxs-lookup"><span data-stu-id="9de30-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="9de30-316">六位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-316">Six digits</span></span>
    
- <span data-ttu-id="9de30-317">以下之一：加号、减号或字母 "A" （不区分大小写），其中加号表示介于1800-1899 之间，负号表示在1900-1999 之间，而 "A" 表示出生2000和之后</span><span class="sxs-lookup"><span data-stu-id="9de30-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="9de30-318">三位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-318">Three digits</span></span>
    
- <span data-ttu-id="9de30-319">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-320">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-320">Checksum</span></span>

<span data-ttu-id="9de30-321">是</span><span class="sxs-lookup"><span data-stu-id="9de30-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-322">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-322">Definition</span></span>

<span data-ttu-id="9de30-323">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-324">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-325">找到了中`Keywords_finland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-326">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-327">函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-328">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="9de30-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-330">identification number</span><span class="sxs-lookup"><span data-stu-id="9de30-330">identification number</span></span>
  
<span data-ttu-id="9de30-331">个人 id</span><span class="sxs-lookup"><span data-stu-id="9de30-331">personal id</span></span>
  
<span data-ttu-id="9de30-332">标识号码</span><span class="sxs-lookup"><span data-stu-id="9de30-332">identity number</span></span>
  
<span data-ttu-id="9de30-333">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-333">finnish national id number</span></span>
  
<span data-ttu-id="9de30-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-334">personalidnumber#</span></span>
  
<span data-ttu-id="9de30-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="9de30-335">national identification number</span></span>
  
<span data-ttu-id="9de30-336">id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-336">id number</span></span>
  
<span data-ttu-id="9de30-337">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="9de30-337">national id no.</span></span>
  
<span data-ttu-id="9de30-338">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-338">national id number</span></span>
  
<span data-ttu-id="9de30-339">id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-339">id no</span></span>
  
<span data-ttu-id="9de30-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9de30-340">tunnistenumero</span></span>
  
<span data-ttu-id="9de30-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9de30-341">henkilötunnus</span></span>
  
<span data-ttu-id="9de30-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9de30-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="9de30-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="9de30-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="9de30-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="9de30-344">identiteetti numero</span></span>
  
<span data-ttu-id="9de30-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9de30-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="9de30-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="9de30-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="9de30-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9de30-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="9de30-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="9de30-348">tunnusnumero</span></span>
  
<span data-ttu-id="9de30-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="9de30-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="9de30-350">法国</span><span class="sxs-lookup"><span data-stu-id="9de30-350">France</span></span>

### <a name="format"></a><span data-ttu-id="9de30-351">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-351">Format</span></span>

<span data-ttu-id="9de30-352">13位数的个人和九个数字的实体</span><span class="sxs-lookup"><span data-stu-id="9de30-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-353">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-353">Pattern</span></span>

<span data-ttu-id="9de30-354">适用于个人的13个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="9de30-355">一个数字，必须为0、1、2或3</span><span class="sxs-lookup"><span data-stu-id="9de30-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="9de30-356">12 个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-356">12 digits</span></span>
    
<span data-ttu-id="9de30-357">9个图元数字</span><span class="sxs-lookup"><span data-stu-id="9de30-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-358">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-358">Checksum</span></span>

<span data-ttu-id="9de30-359">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-360">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-360">Definition</span></span>

<span data-ttu-id="9de30-361">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-362">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-363">找到了中`Keywords_france_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-365">函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-366">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="9de30-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-368">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-368">tax identification number</span></span>
  
<span data-ttu-id="9de30-369">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-369">tax number</span></span>
  
<span data-ttu-id="9de30-370">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-370">tax id</span></span>
  
<span data-ttu-id="9de30-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="9de30-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="9de30-372">德国</span><span class="sxs-lookup"><span data-stu-id="9de30-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="9de30-373">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-373">Format</span></span>

<span data-ttu-id="9de30-374">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-375">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-375">Pattern</span></span>

<span data-ttu-id="9de30-376">11位数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-376">11 digits :</span></span>
  
-  <span data-ttu-id="9de30-377">10位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-377">Ten digits</span></span> 
    
- <span data-ttu-id="9de30-378">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-379">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-379">Checksum</span></span>

<span data-ttu-id="9de30-380">是</span><span class="sxs-lookup"><span data-stu-id="9de30-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-381">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-381">Definition</span></span>

<span data-ttu-id="9de30-382">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-383">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-384">找到了中`Keywords_germany_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-385">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-386">函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-387">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="9de30-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-389">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-389">tax number</span></span>
  
<span data-ttu-id="9de30-390">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-390">tax no.</span></span>
  
<span data-ttu-id="9de30-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-391">taxno#</span></span>
  
<span data-ttu-id="9de30-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-392">taxnumber#</span></span>
  
<span data-ttu-id="9de30-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-393">taxnumber</span></span>
  
<span data-ttu-id="9de30-394">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-394">tax id</span></span>
  
<span data-ttu-id="9de30-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-395">taxid#</span></span>
  
<span data-ttu-id="9de30-396">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-396">tax identification number</span></span>
  
<span data-ttu-id="9de30-397">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-397">tax identification no.</span></span>
  
<span data-ttu-id="9de30-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="9de30-398">steuernummer</span></span>
  
<span data-ttu-id="9de30-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="9de30-399">steuer id</span></span>
  
<span data-ttu-id="9de30-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="9de30-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="9de30-401">希腊</span><span class="sxs-lookup"><span data-stu-id="9de30-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="9de30-402">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-402">Format</span></span>

<span data-ttu-id="9de30-403">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-404">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-404">Pattern</span></span>

<span data-ttu-id="9de30-405">九个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-406">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-406">Checksum</span></span>

<span data-ttu-id="9de30-407">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-408">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-408">Definition</span></span>

<span data-ttu-id="9de30-409">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-410">正则表达式`Regex_greece_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-411">找到了中`Keywords_greece_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-412">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="9de30-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-414">afm</span><span class="sxs-lookup"><span data-stu-id="9de30-414">afm</span></span>
  
<span data-ttu-id="9de30-415">锡</span><span class="sxs-lookup"><span data-stu-id="9de30-415">tin</span></span>
  
<span data-ttu-id="9de30-416">税号编号</span><span class="sxs-lookup"><span data-stu-id="9de30-416">tax id no.</span></span>
  
<span data-ttu-id="9de30-417">税号编号</span><span class="sxs-lookup"><span data-stu-id="9de30-417">tax id no</span></span>
  
<span data-ttu-id="9de30-418">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-418">tax identification number</span></span>
  
<span data-ttu-id="9de30-419">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="9de30-419">tax registry number</span></span>
  
<span data-ttu-id="9de30-420">税务注册表号</span><span class="sxs-lookup"><span data-stu-id="9de30-420">tax registry no.</span></span>
  
<span data-ttu-id="9de30-421">afm#</span><span class="sxs-lookup"><span data-stu-id="9de30-421">afm#</span></span>
  
<span data-ttu-id="9de30-422">锡#</span><span class="sxs-lookup"><span data-stu-id="9de30-422">tin#</span></span>
  
<span data-ttu-id="9de30-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="9de30-423">taxidno#</span></span>
  
<span data-ttu-id="9de30-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="9de30-424">taxregistryno#</span></span>
  
<span data-ttu-id="9de30-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="9de30-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="9de30-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="9de30-426">aφμ</span></span>
  
<span data-ttu-id="9de30-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="9de30-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="9de30-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="9de30-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="9de30-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="9de30-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="9de30-430">匈牙利</span><span class="sxs-lookup"><span data-stu-id="9de30-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9de30-431">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-431">Format</span></span>

<span data-ttu-id="9de30-432">10个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-433">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-433">Pattern</span></span>

<span data-ttu-id="9de30-434">10位数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-434">Ten digits:</span></span>
  
-  <span data-ttu-id="9de30-435">一个必须为 "8" 的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="9de30-436">与日期01/01/1867 之间的天数对应的五个数字和个人的出生日期</span><span class="sxs-lookup"><span data-stu-id="9de30-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="9de30-437">三个数字，对应于通过机会区分在同一天的人所生成的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="9de30-438">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-439">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-439">Checksum</span></span>

<span data-ttu-id="9de30-440">是</span><span class="sxs-lookup"><span data-stu-id="9de30-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-441">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-441">Definition</span></span>

<span data-ttu-id="9de30-442">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-443">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-444">找到了中`Keywords_hungary_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-445">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-446">函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-447">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="9de30-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-449">匈牙利语税号标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="9de30-450">匈牙利纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-450">hungarian tin</span></span>
  
<span data-ttu-id="9de30-451">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-451">tax id number</span></span>
  
<span data-ttu-id="9de30-452">vat 号码</span><span class="sxs-lookup"><span data-stu-id="9de30-452">vat number</span></span>
  
<span data-ttu-id="9de30-453">税务主管机构编号</span><span class="sxs-lookup"><span data-stu-id="9de30-453">tax authority no</span></span>
  
<span data-ttu-id="9de30-454">税号纳税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-454">tax id tax identity number</span></span>
  
<span data-ttu-id="9de30-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-455">taxidnumber#</span></span>
  
<span data-ttu-id="9de30-456">锡#</span><span class="sxs-lookup"><span data-stu-id="9de30-456">tin#</span></span>
  
<span data-ttu-id="9de30-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="9de30-457">hungatiantin#</span></span>
  
<span data-ttu-id="9de30-458">税号标识编号</span><span class="sxs-lookup"><span data-stu-id="9de30-458">tax identification no</span></span>
  
<span data-ttu-id="9de30-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="9de30-459">taxidno#</span></span>
  
<span data-ttu-id="9de30-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="9de30-460">adóazonosító szám</span></span>
  
<span data-ttu-id="9de30-461">adószám</span><span class="sxs-lookup"><span data-stu-id="9de30-461">adószám</span></span>
  
<span data-ttu-id="9de30-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="9de30-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="9de30-463">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="9de30-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9de30-464">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-464">Format</span></span>

<span data-ttu-id="9de30-465">七位数字后跟一个不带空格或分隔符的字母</span><span class="sxs-lookup"><span data-stu-id="9de30-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-466">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-466">Pattern</span></span>

<span data-ttu-id="9de30-467">七位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="9de30-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="9de30-468">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-468">Seven digits</span></span> 
    
- <span data-ttu-id="9de30-469">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-470">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-470">Checksum</span></span>

<span data-ttu-id="9de30-471">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-472">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-472">Definition</span></span>

<span data-ttu-id="9de30-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-474">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-475">找到了中`Keywords_ireland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-476">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-477">函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-478">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="9de30-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-480">公共服务编号</span><span class="sxs-lookup"><span data-stu-id="9de30-480">public service no</span></span>
  
<span data-ttu-id="9de30-481">个人公开服务编号</span><span class="sxs-lookup"><span data-stu-id="9de30-481">personal public service no</span></span>
  
<span data-ttu-id="9de30-482">pps no</span><span class="sxs-lookup"><span data-stu-id="9de30-482">pps no</span></span>
  
<span data-ttu-id="9de30-483">个人服务编号</span><span class="sxs-lookup"><span data-stu-id="9de30-483">personal service no</span></span>
  
<span data-ttu-id="9de30-484">pps 服务否</span><span class="sxs-lookup"><span data-stu-id="9de30-484">pps service no</span></span>
  
<span data-ttu-id="9de30-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="9de30-485">ppsno#</span></span>
  
<span data-ttu-id="9de30-486">爱尔兰 pps 否</span><span class="sxs-lookup"><span data-stu-id="9de30-486">irish pps no</span></span>
  
<span data-ttu-id="9de30-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="9de30-487">publicserviceno#</span></span>
  
<span data-ttu-id="9de30-488">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="9de30-488">personal public service number</span></span>
  
<span data-ttu-id="9de30-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="9de30-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="9de30-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="9de30-490">pps uimh</span></span>
  
<span data-ttu-id="9de30-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="9de30-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="9de30-492">意大利</span><span class="sxs-lookup"><span data-stu-id="9de30-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="9de30-493">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-493">Format</span></span>

<span data-ttu-id="9de30-494">指定模式中的16个字母和数字</span><span class="sxs-lookup"><span data-stu-id="9de30-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-495">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-495">Pattern</span></span>

<span data-ttu-id="9de30-496">16个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="9de30-497">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="9de30-498">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="9de30-499">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="9de30-500">一个与出生月份相对应的数字（字母按字母顺序使用），但仅使用字母 A 到 E、H、L、M、P、R 和 T （因此，一月为 A，10月为 R）</span><span class="sxs-lookup"><span data-stu-id="9de30-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="9de30-501">两个数字，对应于出生月份中的某一天，其中40将添加到偶数的出生日，以区别于奇数</span><span class="sxs-lookup"><span data-stu-id="9de30-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="9de30-502">与某人出生的 municipality 特定的区号相对应的四个数字（国家/地区代码用于外国国家/地区）</span><span class="sxs-lookup"><span data-stu-id="9de30-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="9de30-503">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-504">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-504">Checksum</span></span>

<span data-ttu-id="9de30-505">是</span><span class="sxs-lookup"><span data-stu-id="9de30-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-506">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-506">Definition</span></span>

<span data-ttu-id="9de30-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-508">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-509">找到了中`Keywords_italy_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-510">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-511">函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-512">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="9de30-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-514">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-514">tax number</span></span>
  
<span data-ttu-id="9de30-515">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-515">tax no.</span></span>
  
<span data-ttu-id="9de30-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-516">taxno#</span></span>
  
<span data-ttu-id="9de30-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-517">taxnumber#</span></span>
  
<span data-ttu-id="9de30-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-518">taxnumber</span></span>
  
<span data-ttu-id="9de30-519">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-519">tax id</span></span>
  
<span data-ttu-id="9de30-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-520">taxid#</span></span>
  
<span data-ttu-id="9de30-521">会计代码</span><span class="sxs-lookup"><span data-stu-id="9de30-521">fiscal code</span></span>
  
<span data-ttu-id="9de30-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="9de30-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="9de30-523">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="9de30-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="9de30-524">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-524">Format</span></span>

<span data-ttu-id="9de30-525">11个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-526">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-526">Pattern</span></span>

<span data-ttu-id="9de30-527">指定模式中的11位数</span><span class="sxs-lookup"><span data-stu-id="9de30-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="9de30-528">六个数字，对应于出生日期（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="9de30-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="9de30-529">一个与 "出生世纪" 相对应的数字，其中 "0" 对应于19世纪，"1" 对应于20世纪，"2" 对应于21世纪。</span><span class="sxs-lookup"><span data-stu-id="9de30-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="9de30-530">四位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-531">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-531">Checksum</span></span>

<span data-ttu-id="9de30-532">是</span><span class="sxs-lookup"><span data-stu-id="9de30-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-533">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-533">Definition</span></span>

<span data-ttu-id="9de30-534">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-535">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-536">找到了中`Keywords_latvia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-537">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-538">函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-539">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="9de30-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-541">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-541">tax number</span></span>
  
<span data-ttu-id="9de30-542">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-542">tax no.</span></span>
  
<span data-ttu-id="9de30-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-543">taxno#</span></span>
  
<span data-ttu-id="9de30-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-544">taxnumber#</span></span>
  
<span data-ttu-id="9de30-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-545">taxnumber</span></span>
  
<span data-ttu-id="9de30-546">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-546">tax id</span></span>
  
<span data-ttu-id="9de30-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-547">taxid#</span></span>
  
<span data-ttu-id="9de30-548">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-548">tax identification number</span></span>
  
<span data-ttu-id="9de30-549">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-549">tax identification no.</span></span>
  
<span data-ttu-id="9de30-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="9de30-550">nodokļa numurs</span></span>
  
<span data-ttu-id="9de30-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="9de30-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="9de30-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="9de30-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="9de30-553">立陶宛</span><span class="sxs-lookup"><span data-stu-id="9de30-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9de30-554">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-554">Format</span></span>

<span data-ttu-id="9de30-555">11位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-556">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-556">Pattern</span></span>

<span data-ttu-id="9de30-557">11 个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-558">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-558">Checksum</span></span>

<span data-ttu-id="9de30-559">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-560">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-560">Definition</span></span>

<span data-ttu-id="9de30-561">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-562">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-563">找到了中`Keywords_lithuania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-564">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-565">函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-566">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="9de30-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-568">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-568">tax number</span></span>
  
<span data-ttu-id="9de30-569">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-569">tax no.</span></span>
  
<span data-ttu-id="9de30-570">免税#</span><span class="sxs-lookup"><span data-stu-id="9de30-570">tax no#</span></span>
  
<span data-ttu-id="9de30-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-571">taxnumber#</span></span>
  
<span data-ttu-id="9de30-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-572">taxnumber</span></span>
  
<span data-ttu-id="9de30-573">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-573">tax id</span></span>
  
<span data-ttu-id="9de30-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-574">taxid#</span></span>
  
<span data-ttu-id="9de30-575">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-575">tax identification number</span></span>
  
<span data-ttu-id="9de30-576">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-576">tax identification no.</span></span>
  
<span data-ttu-id="9de30-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="9de30-577">mokesčių id</span></span>
  
<span data-ttu-id="9de30-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="9de30-578">mokesčių numeris</span></span>
  
<span data-ttu-id="9de30-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="9de30-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="9de30-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="9de30-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9de30-581">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-581">Format</span></span>

<span data-ttu-id="9de30-582">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-583">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-583">Pattern</span></span>

<span data-ttu-id="9de30-584">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-584">13 digits:</span></span>
  
-  <span data-ttu-id="9de30-585">11 个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-585">11 digits</span></span> 
    
- <span data-ttu-id="9de30-586">两个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-587">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-587">Checksum</span></span>

<span data-ttu-id="9de30-588">是</span><span class="sxs-lookup"><span data-stu-id="9de30-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-589">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-589">Definition</span></span>

<span data-ttu-id="9de30-590">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-591">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-592">找到了中`Keywords_luxemburg_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-593">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-594">函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-595">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="9de30-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-597">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-597">tax number</span></span>
  
<span data-ttu-id="9de30-598">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-598">tax no.</span></span>
  
<span data-ttu-id="9de30-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-599">taxno#</span></span>
  
<span data-ttu-id="9de30-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-600">taxnumber#</span></span>
  
<span data-ttu-id="9de30-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-601">taxnumber</span></span>
  
<span data-ttu-id="9de30-602">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-602">tax id</span></span>
  
<span data-ttu-id="9de30-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-603">taxid#</span></span>
  
<span data-ttu-id="9de30-604">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-604">tax identification number</span></span>
  
<span data-ttu-id="9de30-605">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-605">tax identification no.</span></span>
  
<span data-ttu-id="9de30-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="9de30-606">steuernummer</span></span>
  
<span data-ttu-id="9de30-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="9de30-607">steuer id</span></span>
  
<span data-ttu-id="9de30-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="9de30-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="9de30-609">马耳他</span><span class="sxs-lookup"><span data-stu-id="9de30-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9de30-610">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-610">Format</span></span>

<span data-ttu-id="9de30-611">对于马耳他 nationals：7位数和指定模式中的一个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="9de30-612">非马耳他语 nationals 和马耳他语实体：9个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-613">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-613">Pattern</span></span>

<span data-ttu-id="9de30-614">马耳他 nationals：7个数字和一个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="9de30-615">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-615">Seven digits</span></span> 
    
- <span data-ttu-id="9de30-616">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="9de30-617">非马耳他语 nationals 和马耳他语实体：9个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="9de30-618">九个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9de30-619">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-619">Checksum</span></span>

<span data-ttu-id="9de30-620">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-621">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-621">Definition</span></span>

<span data-ttu-id="9de30-622">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-623">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-624">找到了中`Keywords_malta_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-626">函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-627">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="9de30-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-629">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-629">tax number</span></span>
  
<span data-ttu-id="9de30-630">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-630">tax no.</span></span>
  
<span data-ttu-id="9de30-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-631">taxno#</span></span>
  
<span data-ttu-id="9de30-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-632">taxnumber#</span></span>
  
<span data-ttu-id="9de30-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-633">taxnumber</span></span>
  
<span data-ttu-id="9de30-634">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-634">tax id</span></span>
  
<span data-ttu-id="9de30-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-635">taxid#</span></span>
  
<span data-ttu-id="9de30-636">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-636">tax identification number</span></span>
  
<span data-ttu-id="9de30-637">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-637">tax identification no.</span></span>
  
<span data-ttu-id="9de30-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="9de30-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="9de30-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="9de30-639">id tat-taxxa</span></span>
  
<span data-ttu-id="9de30-640">numru ta "identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="9de30-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="9de30-641">荷兰</span><span class="sxs-lookup"><span data-stu-id="9de30-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9de30-642">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-642">Format</span></span>

<span data-ttu-id="9de30-643">9个数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-644">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-644">Pattern</span></span>

<span data-ttu-id="9de30-645">九个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9de30-646">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-646">Checksum</span></span>

<span data-ttu-id="9de30-647">是</span><span class="sxs-lookup"><span data-stu-id="9de30-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-648">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-648">Definition</span></span>

<span data-ttu-id="9de30-649">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-650">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-651">找到了中`Keywords_netherlands_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-652">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-653">函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-654">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="9de30-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-656">荷兰税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="9de30-657">荷兰税务标识</span><span class="sxs-lookup"><span data-stu-id="9de30-657">netherlands tax identification</span></span>
  
<span data-ttu-id="9de30-658">netherland 的税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="9de30-659">netherland 的税标识</span><span class="sxs-lookup"><span data-stu-id="9de30-659">netherland's tax identification</span></span>
  
<span data-ttu-id="9de30-660">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-660">tax identification number</span></span>
  
<span data-ttu-id="9de30-661">荷兰税号</span><span class="sxs-lookup"><span data-stu-id="9de30-661">dutch tax id</span></span>
  
<span data-ttu-id="9de30-662">荷兰纳税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-662">dutch tax identification number</span></span>
  
<span data-ttu-id="9de30-663">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-663">tax id</span></span>
  
<span data-ttu-id="9de30-664">税号#</span><span class="sxs-lookup"><span data-stu-id="9de30-664">tax id#</span></span>
  
<span data-ttu-id="9de30-665">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-665">tax number</span></span>
  
<span data-ttu-id="9de30-666">免税#</span><span class="sxs-lookup"><span data-stu-id="9de30-666">tax no#</span></span>
  
<span data-ttu-id="9de30-667">税种#</span><span class="sxs-lookup"><span data-stu-id="9de30-667">tax#</span></span>
  
<span data-ttu-id="9de30-668">锡</span><span class="sxs-lookup"><span data-stu-id="9de30-668">tin</span></span>
  
<span data-ttu-id="9de30-669">锡#</span><span class="sxs-lookup"><span data-stu-id="9de30-669">tin#</span></span>
  
<span data-ttu-id="9de30-670">荷属安的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-670">netherlands tin</span></span>
  
<span data-ttu-id="9de30-671">netherland 的纳税人标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-671">netherland's tin</span></span>
  
<span data-ttu-id="9de30-672">荷兰语 belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="9de30-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="9de30-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="9de30-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="9de30-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="9de30-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="9de30-675">荷兰语 belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="9de30-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="9de30-676">荷兰语 belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="9de30-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="9de30-677">荷兰语 belastingnummer</span><span class="sxs-lookup"><span data-stu-id="9de30-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="9de30-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="9de30-678">btw nummer</span></span>
  
<span data-ttu-id="9de30-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="9de30-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="9de30-680">波兰</span><span class="sxs-lookup"><span data-stu-id="9de30-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="9de30-681">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-681">Format</span></span>

<span data-ttu-id="9de30-682">不带空格或分隔符的11个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-683">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-683">Pattern</span></span>

<span data-ttu-id="9de30-684">11位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-685">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-685">Checksum</span></span>

<span data-ttu-id="9de30-686">是</span><span class="sxs-lookup"><span data-stu-id="9de30-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-687">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-687">Definition</span></span>

<span data-ttu-id="9de30-688">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-689">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-690">找到了中`Keywords_poland_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-691">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-692">函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-693">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="9de30-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-695">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-695">tax number</span></span>
  
<span data-ttu-id="9de30-696">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-696">tax no.</span></span>
  
<span data-ttu-id="9de30-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-697">taxno#</span></span>
  
<span data-ttu-id="9de30-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-698">taxnumber#</span></span>
  
<span data-ttu-id="9de30-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-699">taxnumber</span></span>
  
<span data-ttu-id="9de30-700">nip</span><span class="sxs-lookup"><span data-stu-id="9de30-700">nip</span></span>
  
<span data-ttu-id="9de30-701">nip#</span><span class="sxs-lookup"><span data-stu-id="9de30-701">nip#</span></span>
  
<span data-ttu-id="9de30-702">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-702">tax id</span></span>
  
<span data-ttu-id="9de30-703">税号#</span><span class="sxs-lookup"><span data-stu-id="9de30-703">tax id#</span></span>
  
<span data-ttu-id="9de30-704">nip id</span><span class="sxs-lookup"><span data-stu-id="9de30-704">nip id</span></span>
  
<span data-ttu-id="9de30-705">nip id#</span><span class="sxs-lookup"><span data-stu-id="9de30-705">nip id#</span></span>
  
<span data-ttu-id="9de30-706">税标识号</span><span class="sxs-lookup"><span data-stu-id="9de30-706">tax identification number</span></span>
  
<span data-ttu-id="9de30-707">税号标识号。</span><span class="sxs-lookup"><span data-stu-id="9de30-707">tax identification no.</span></span>
  
<span data-ttu-id="9de30-708">vat 号码</span><span class="sxs-lookup"><span data-stu-id="9de30-708">vat number</span></span>
  
<span data-ttu-id="9de30-709">vat 编号</span><span class="sxs-lookup"><span data-stu-id="9de30-709">vat no.</span></span>
  
<span data-ttu-id="9de30-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="9de30-710">vatno#</span></span>
  
<span data-ttu-id="9de30-711">vat id</span><span class="sxs-lookup"><span data-stu-id="9de30-711">vat id</span></span>
  
<span data-ttu-id="9de30-712">vat id#</span><span class="sxs-lookup"><span data-stu-id="9de30-712">vat id#</span></span>
  
<span data-ttu-id="9de30-713">器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="9de30-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="9de30-714">polski 器 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="9de30-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="9de30-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="9de30-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9de30-716">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="9de30-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="9de30-717">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-717">Format</span></span>

<span data-ttu-id="9de30-718">9个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-719">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-719">Pattern</span></span>

<span data-ttu-id="9de30-720">九个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-721">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-721">Checksum</span></span>

<span data-ttu-id="9de30-722">是</span><span class="sxs-lookup"><span data-stu-id="9de30-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-723">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-723">Definition</span></span>

<span data-ttu-id="9de30-724">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-725">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-726">找到了中`Keywords_portugal_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-728">函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-729">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="9de30-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-731">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-731">tax number</span></span>
  
<span data-ttu-id="9de30-732">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-732">tax no.</span></span>
  
<span data-ttu-id="9de30-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-733">taxno#</span></span>
  
<span data-ttu-id="9de30-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="9de30-734">taxnumber#</span></span>
  
<span data-ttu-id="9de30-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="9de30-735">taxnumber</span></span>
  
<span data-ttu-id="9de30-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="9de30-736">nif</span></span>
  
<span data-ttu-id="9de30-737">\n\n#</span><span class="sxs-lookup"><span data-stu-id="9de30-737">nif#</span></span>
  
<span data-ttu-id="9de30-738">numero 会计</span><span class="sxs-lookup"><span data-stu-id="9de30-738">numero fiscal</span></span>
  
<span data-ttu-id="9de30-739">número de identificação 会计</span><span class="sxs-lookup"><span data-stu-id="9de30-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="9de30-740">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="9de30-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9de30-741">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-741">Format</span></span>

<span data-ttu-id="9de30-742">13个不带空格或分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="9de30-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-743">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-743">Pattern</span></span>

<span data-ttu-id="9de30-744">13 位数字</span><span class="sxs-lookup"><span data-stu-id="9de30-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-745">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-745">Checksum</span></span>

<span data-ttu-id="9de30-746">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-747">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-747">Definition</span></span>

<span data-ttu-id="9de30-748">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-749">正则表达式`Regex_romania_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-750">找到了中`Keywords_romania_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-751">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="9de30-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-753">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-753">tax id</span></span>
  
<span data-ttu-id="9de30-754">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-754">tax id number</span></span>
  
<span data-ttu-id="9de30-755">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-755">tax file no</span></span>
  
<span data-ttu-id="9de30-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="9de30-756">tax file number</span></span>
  
<span data-ttu-id="9de30-757">免税</span><span class="sxs-lookup"><span data-stu-id="9de30-757">tax no</span></span>
  
<span data-ttu-id="9de30-758">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-758">tax number</span></span>
  
<span data-ttu-id="9de30-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-759">taxid#</span></span>
  
<span data-ttu-id="9de30-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-760">taxno#</span></span>
  
<span data-ttu-id="9de30-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="9de30-761">id-ul taxei</span></span>
  
<span data-ttu-id="9de30-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="9de30-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="9de30-763">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="9de30-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9de30-764">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-764">Format</span></span>

<span data-ttu-id="9de30-765">10个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-766">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-766">Pattern</span></span>

<span data-ttu-id="9de30-767">10 个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-768">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-768">Checksum</span></span>

<span data-ttu-id="9de30-769">不适用</span><span class="sxs-lookup"><span data-stu-id="9de30-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-770">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-770">Definition</span></span>

<span data-ttu-id="9de30-771">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-772">正则表达式`Regex_slovakia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-773">找到了中`Keywords_slovakia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-774">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="9de30-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-776">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-776">tax id</span></span>
  
<span data-ttu-id="9de30-777">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-777">tax id number</span></span>
  
<span data-ttu-id="9de30-778">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="9de30-778">tin id</span></span>
  
<span data-ttu-id="9de30-779">tin 编号</span><span class="sxs-lookup"><span data-stu-id="9de30-779">tin no</span></span>
  
<span data-ttu-id="9de30-780">斯洛伐克纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="9de30-780">slovakian tin id</span></span>
  
<span data-ttu-id="9de30-781">锡</span><span class="sxs-lookup"><span data-stu-id="9de30-781">tin</span></span>
  
<span data-ttu-id="9de30-782">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-782">tax file no</span></span>
  
<span data-ttu-id="9de30-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="9de30-783">tax file number</span></span>
  
<span data-ttu-id="9de30-784">免税</span><span class="sxs-lookup"><span data-stu-id="9de30-784">tax no</span></span>
  
<span data-ttu-id="9de30-785">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-785">tax number</span></span>
  
<span data-ttu-id="9de30-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-786">taxid#</span></span>
  
<span data-ttu-id="9de30-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-787">taxno#</span></span>
  
<span data-ttu-id="9de30-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="9de30-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="9de30-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="9de30-789">daňové číslo</span></span>
  
<span data-ttu-id="9de30-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="9de30-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="9de30-791">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="9de30-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9de30-792">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-792">Format</span></span>

<span data-ttu-id="9de30-793">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-794">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-794">Pattern</span></span>

<span data-ttu-id="9de30-795">八个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-796">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-796">Checksum</span></span>

<span data-ttu-id="9de30-797">是</span><span class="sxs-lookup"><span data-stu-id="9de30-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-798">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-798">Definition</span></span>

<span data-ttu-id="9de30-799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-800">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-801">找到了中`Keywords_slovenia_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-803">函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-804">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="9de30-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-806">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-806">tax id</span></span>
  
<span data-ttu-id="9de30-807">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-807">tax id number</span></span>
  
<span data-ttu-id="9de30-808">纳税人 id</span><span class="sxs-lookup"><span data-stu-id="9de30-808">tin id</span></span>
  
<span data-ttu-id="9de30-809">tin 编号</span><span class="sxs-lookup"><span data-stu-id="9de30-809">tin no</span></span>
  
<span data-ttu-id="9de30-810">斯洛文尼亚纳税人标识号 id</span><span class="sxs-lookup"><span data-stu-id="9de30-810">slovenian tin id</span></span>
  
<span data-ttu-id="9de30-811">锡</span><span class="sxs-lookup"><span data-stu-id="9de30-811">tin</span></span>
  
<span data-ttu-id="9de30-812">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-812">tax file no</span></span>
  
<span data-ttu-id="9de30-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="9de30-813">tax file number</span></span>
  
<span data-ttu-id="9de30-814">免税</span><span class="sxs-lookup"><span data-stu-id="9de30-814">tax no</span></span>
  
<span data-ttu-id="9de30-815">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-815">tax number</span></span>
  
<span data-ttu-id="9de30-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-816">taxid#</span></span>
  
<span data-ttu-id="9de30-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-817">taxno#</span></span>
  
<span data-ttu-id="9de30-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="9de30-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="9de30-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="9de30-819">davčna številka</span></span>
  
<span data-ttu-id="9de30-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="9de30-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="9de30-821">西班牙</span><span class="sxs-lookup"><span data-stu-id="9de30-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9de30-822">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-822">Format</span></span>

<span data-ttu-id="9de30-823">七个或8个数字以及指定模式中的一个或两个字母</span><span class="sxs-lookup"><span data-stu-id="9de30-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-824">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-824">Pattern</span></span>

<span data-ttu-id="9de30-825">具有西班牙国家标识卡片的西班牙语自然人：</span><span class="sxs-lookup"><span data-stu-id="9de30-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="9de30-826">八个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-826">Eight digits</span></span> 
    
- <span data-ttu-id="9de30-827">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="9de30-828">不包含西班牙国家的非居民 Spaniards 国家标识卡片</span><span class="sxs-lookup"><span data-stu-id="9de30-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="9de30-829">一个大写字母 "L" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="9de30-830">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-830">Seven digits</span></span>
    
- <span data-ttu-id="9de30-831">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="9de30-832">在没有西班牙国内身份证的14年年龄下的居民 Spaniards：</span><span class="sxs-lookup"><span data-stu-id="9de30-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="9de30-833">一个大写字母 "K" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="9de30-834">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-834">Seven digits</span></span> 
    
- <span data-ttu-id="9de30-835">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="9de30-836">带有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="9de30-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="9de30-837">一个大写的字母，为 "X"、"Y" 或 "Z" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="9de30-838">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-838">Seven digits</span></span>
    
- <span data-ttu-id="9de30-839">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="9de30-840">没有 Foreigner 标识号的 Foreigners</span><span class="sxs-lookup"><span data-stu-id="9de30-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="9de30-841">一个大写的字母 "M" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="9de30-842">七个数字 </span><span class="sxs-lookup"><span data-stu-id="9de30-842">Seven digits</span></span>
    
- <span data-ttu-id="9de30-843">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="9de30-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="9de30-844">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-844">Checksum</span></span>

<span data-ttu-id="9de30-845">是</span><span class="sxs-lookup"><span data-stu-id="9de30-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-846">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-846">Definition</span></span>

<span data-ttu-id="9de30-847">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-848">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-849">找到了中`Keywords_spain_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-850">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-851">函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-852">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="9de30-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-854">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-854">tax id</span></span>
  
<span data-ttu-id="9de30-855">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-855">tax id number</span></span>
  
<span data-ttu-id="9de30-856">cif id</span><span class="sxs-lookup"><span data-stu-id="9de30-856">cif id</span></span>
  
<span data-ttu-id="9de30-857">cif no</span><span class="sxs-lookup"><span data-stu-id="9de30-857">cif no</span></span>
  
<span data-ttu-id="9de30-858">西班牙语 cif id</span><span class="sxs-lookup"><span data-stu-id="9de30-858">spanish cif id</span></span>
  
<span data-ttu-id="9de30-859">cif</span><span class="sxs-lookup"><span data-stu-id="9de30-859">cif</span></span>
  
<span data-ttu-id="9de30-860">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-860">tax file no</span></span>
  
<span data-ttu-id="9de30-861">西班牙语 cif 号码</span><span class="sxs-lookup"><span data-stu-id="9de30-861">spanish cif number</span></span>
  
<span data-ttu-id="9de30-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="9de30-862">tax file number</span></span>
  
<span data-ttu-id="9de30-863">西班牙语 cif no</span><span class="sxs-lookup"><span data-stu-id="9de30-863">spanish cif no</span></span>
  
<span data-ttu-id="9de30-864">免税</span><span class="sxs-lookup"><span data-stu-id="9de30-864">tax no</span></span>
  
<span data-ttu-id="9de30-865">税号</span><span class="sxs-lookup"><span data-stu-id="9de30-865">tax number</span></span>
  
<span data-ttu-id="9de30-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-866">taxid#</span></span>
  
<span data-ttu-id="9de30-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="9de30-867">taxno#</span></span>
  
<span data-ttu-id="9de30-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="9de30-868">cifid#</span></span>
  
<span data-ttu-id="9de30-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="9de30-869">spanishcifid#</span></span>
  
<span data-ttu-id="9de30-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="9de30-870">spanishcifno#</span></span>
  
<span data-ttu-id="9de30-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="9de30-871">número de contribuyente</span></span>
  
<span data-ttu-id="9de30-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="9de30-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="9de30-873">número de identificación 会计</span><span class="sxs-lookup"><span data-stu-id="9de30-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="9de30-874">cif número</span><span class="sxs-lookup"><span data-stu-id="9de30-874">cif número</span></span>
  
<span data-ttu-id="9de30-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="9de30-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="9de30-876">瑞典</span><span class="sxs-lookup"><span data-stu-id="9de30-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="9de30-877">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-877">Format</span></span>

<span data-ttu-id="9de30-878">10个数字和指定模式中的符号</span><span class="sxs-lookup"><span data-stu-id="9de30-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-879">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-879">Pattern</span></span>

<span data-ttu-id="9de30-880">10个数字和一个符号：</span><span class="sxs-lookup"><span data-stu-id="9de30-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="9de30-881">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="9de30-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9de30-882">加号、减号或反斜杠</span><span class="sxs-lookup"><span data-stu-id="9de30-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="9de30-883">在以下位置使标识号唯一的三个数字：</span><span class="sxs-lookup"><span data-stu-id="9de30-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="9de30-884">对于在1990之前发出的号码，第七和第八位数字标识出生的县或外部人</span><span class="sxs-lookup"><span data-stu-id="9de30-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="9de30-885">第九个位置中的数字表示为奇数或甚至是女的性别</span><span class="sxs-lookup"><span data-stu-id="9de30-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="9de30-886">一个校验位</span><span class="sxs-lookup"><span data-stu-id="9de30-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9de30-887">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-887">Checksum</span></span>

<span data-ttu-id="9de30-888">是</span><span class="sxs-lookup"><span data-stu-id="9de30-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-889">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-889">Definition</span></span>

<span data-ttu-id="9de30-890">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-891">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-892">找到了中`Keywords_sweden_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="9de30-893">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-894">函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-895">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="9de30-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-897">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-897">tax id</span></span>
  
<span data-ttu-id="9de30-898">税号编号</span><span class="sxs-lookup"><span data-stu-id="9de30-898">tax id no.</span></span>
  
<span data-ttu-id="9de30-899">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-899">tax id number</span></span>
  
<span data-ttu-id="9de30-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="9de30-900">tax identification</span></span>
  
<span data-ttu-id="9de30-901">纳税标识#</span><span class="sxs-lookup"><span data-stu-id="9de30-901">tax identification#</span></span>
  
<span data-ttu-id="9de30-902">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-902">tax no.</span></span>
  
<span data-ttu-id="9de30-903">税种#</span><span class="sxs-lookup"><span data-stu-id="9de30-903">tax#</span></span>
  
<span data-ttu-id="9de30-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-904">taxid#</span></span>
  
<span data-ttu-id="9de30-905">税文件</span><span class="sxs-lookup"><span data-stu-id="9de30-905">tax file</span></span>
  
<span data-ttu-id="9de30-906">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-906">tax file no.</span></span>
  
<span data-ttu-id="9de30-907">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-907">personal id number</span></span>
  
<span data-ttu-id="9de30-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="9de30-908">skatt id nummer</span></span>
  
<span data-ttu-id="9de30-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="9de30-909">skatt identifikation</span></span>
  
<span data-ttu-id="9de30-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="9de30-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="9de30-911">英国</span><span class="sxs-lookup"><span data-stu-id="9de30-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="9de30-912">Format</span><span class="sxs-lookup"><span data-stu-id="9de30-912">Format</span></span>

<span data-ttu-id="9de30-913">唯一的纳税人参考（UTR）：10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="9de30-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="9de30-914">国家保险业号码（NINO）：有关详细信息，请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="9de30-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="9de30-915">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码（NINO）。</span><span class="sxs-lookup"><span data-stu-id="9de30-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9de30-916">模式</span><span class="sxs-lookup"><span data-stu-id="9de30-916">Pattern</span></span>

<span data-ttu-id="9de30-917">唯一的纳税人引用（UTR）：10个数字</span><span class="sxs-lookup"><span data-stu-id="9de30-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="9de30-918">国家保险业号码（NINO）：有关详细信息，请参阅 "英国</span><span class="sxs-lookup"><span data-stu-id="9de30-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="9de30-919">[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的国家保险业号码（NINO）。</span><span class="sxs-lookup"><span data-stu-id="9de30-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9de30-920">校验和</span><span class="sxs-lookup"><span data-stu-id="9de30-920">Checksum</span></span>

<span data-ttu-id="9de30-921">是</span><span class="sxs-lookup"><span data-stu-id="9de30-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9de30-922">定义</span><span class="sxs-lookup"><span data-stu-id="9de30-922">Definition</span></span>

<span data-ttu-id="9de30-923">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="9de30-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9de30-924">函数`Func_uk_eu_tax_file_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="9de30-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9de30-925">找到了中`Keywords_uk_eu_tax_file_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="9de30-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9de30-926">关键字</span><span class="sxs-lookup"><span data-stu-id="9de30-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="9de30-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="9de30-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="9de30-928">tax id</span><span class="sxs-lookup"><span data-stu-id="9de30-928">tax id</span></span>
  
<span data-ttu-id="9de30-929">税号编号</span><span class="sxs-lookup"><span data-stu-id="9de30-929">tax id no.</span></span>
  
<span data-ttu-id="9de30-930">税务 id 号</span><span class="sxs-lookup"><span data-stu-id="9de30-930">tax id number</span></span>
  
<span data-ttu-id="9de30-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="9de30-931">tax identification</span></span>
  
<span data-ttu-id="9de30-932">纳税标识#</span><span class="sxs-lookup"><span data-stu-id="9de30-932">tax identification#</span></span>
  
<span data-ttu-id="9de30-933">纳税编号</span><span class="sxs-lookup"><span data-stu-id="9de30-933">tax no.</span></span>
  
<span data-ttu-id="9de30-934">税种#</span><span class="sxs-lookup"><span data-stu-id="9de30-934">tax#</span></span>
  
<span data-ttu-id="9de30-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="9de30-935">taxid#</span></span>
  
<span data-ttu-id="9de30-936">税文件</span><span class="sxs-lookup"><span data-stu-id="9de30-936">tax file</span></span>
  
<span data-ttu-id="9de30-937">税文件编号</span><span class="sxs-lookup"><span data-stu-id="9de30-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9de30-938">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9de30-938">See also</span></span>

[<span data-ttu-id="9de30-939">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="9de30-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

