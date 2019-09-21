---
title: EU 护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37074868"
---
# <a name="eu-passport-number"></a><span data-ttu-id="8bed5-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-104">EU Passport Number</span></span>

<span data-ttu-id="8bed5-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="8bed5-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="8bed5-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8bed5-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="8bed5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-108">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-108">Format</span></span>

<span data-ttu-id="8bed5-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-110">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-110">Pattern</span></span>

<span data-ttu-id="8bed5-111">一个字母、七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="8bed5-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="8bed5-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8bed5-113">一个空格（可选）</span><span class="sxs-lookup"><span data-stu-id="8bed5-113">One space (optional)</span></span>
    
- <span data-ttu-id="8bed5-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-115">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-115">Checksum</span></span>

<span data-ttu-id="8bed5-116">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-117">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-117">Definition</span></span>

<span data-ttu-id="8bed5-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-121">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-121">Keywords</span></span>

<span data-ttu-id="8bed5-122">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-122"></span></span>
|<span data-ttu-id="8bed5-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-124">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-124">passport number</span></span>  <br/> <span data-ttu-id="8bed5-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-125">austrian passport number</span></span>  <br/> <span data-ttu-id="8bed5-126">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-126">passport no</span></span>  <br/> <span data-ttu-id="8bed5-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="8bed5-127">reisepass</span></span>  <br/> <span data-ttu-id="8bed5-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="8bed5-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8bed5-129">比利时</span><span class="sxs-lookup"><span data-stu-id="8bed5-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-130">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-130">Format</span></span>

<span data-ttu-id="8bed5-131">两个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-132">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-132">Pattern</span></span>

<span data-ttu-id="8bed5-133">两个字母，后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-134">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-134">Checksum</span></span>

<span data-ttu-id="8bed5-135">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-136">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-136">Definition</span></span>

<span data-ttu-id="8bed5-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-140">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-140">Keywords</span></span>

<span data-ttu-id="8bed5-141">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-141"></span></span>
|<span data-ttu-id="8bed5-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-143">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-143">passport number</span></span>  <br/> <span data-ttu-id="8bed5-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-144">belgian passport number</span></span>  <br/> <span data-ttu-id="8bed5-145">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-145">passport no</span></span>  <br/> <span data-ttu-id="8bed5-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="8bed5-146">paspoort</span></span>  <br/> <span data-ttu-id="8bed5-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="8bed5-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="8bed5-148">reisepass kein</span></span>  <br/> <span data-ttu-id="8bed5-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="8bed5-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8bed5-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="8bed5-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-151">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-151">Format</span></span>

<span data-ttu-id="8bed5-152">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-153">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-153">Pattern</span></span>

 <span data-ttu-id="8bed5-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8bed5-155">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-155">Checksum</span></span>

<span data-ttu-id="8bed5-156">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-157">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-157">Definition</span></span>

<span data-ttu-id="8bed5-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-161">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-161">Keywords</span></span>

<span data-ttu-id="8bed5-162">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-162"></span></span>
|<span data-ttu-id="8bed5-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-164">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-164">passport number</span></span>  <br/> <span data-ttu-id="8bed5-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="8bed5-166">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-166">passport no</span></span>  <br/> <span data-ttu-id="8bed5-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="8bed5-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8bed5-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="8bed5-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-169">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-169">Format</span></span>

<span data-ttu-id="8bed5-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-171">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-171">Pattern</span></span>

 <span data-ttu-id="8bed5-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8bed5-173">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-173">Checksum</span></span>

<span data-ttu-id="8bed5-174">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-175">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-175">Definition</span></span>

<span data-ttu-id="8bed5-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-179">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-179">Keywords</span></span>

<span data-ttu-id="8bed5-180">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-180"></span></span>
|<span data-ttu-id="8bed5-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-182">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-182">passport number</span></span>  <br/> <span data-ttu-id="8bed5-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-183">croatian passport number</span></span>  <br/> <span data-ttu-id="8bed5-184">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-184">passport no</span></span>  <br/> <span data-ttu-id="8bed5-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="8bed5-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8bed5-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="8bed5-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-187">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-187">Format</span></span>

<span data-ttu-id="8bed5-188">一个字母后跟6-8 个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-189">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-189">Pattern</span></span>

<span data-ttu-id="8bed5-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-191">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-191">Checksum</span></span>

<span data-ttu-id="8bed5-192">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-193">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-193">Definition</span></span>

<span data-ttu-id="8bed5-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-197">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-197">Keywords</span></span>

<span data-ttu-id="8bed5-198">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-198"></span></span>
|<span data-ttu-id="8bed5-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-200">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-200">passport number</span></span>  <br/> <span data-ttu-id="8bed5-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="8bed5-202">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-202">passport no</span></span>  <br/> <span data-ttu-id="8bed5-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="8bed5-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8bed5-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="8bed5-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-205">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-205">Format</span></span>

<span data-ttu-id="8bed5-206">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-207">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-207">Pattern</span></span>

<span data-ttu-id="8bed5-208">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-209">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-209">Checksum</span></span>

<span data-ttu-id="8bed5-210">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-211">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-211">Definition</span></span>

<span data-ttu-id="8bed5-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-215">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-215">Keywords</span></span>

<span data-ttu-id="8bed5-216">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-216"></span></span>
|<span data-ttu-id="8bed5-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-218">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-218">passport number</span></span>  <br/> <span data-ttu-id="8bed5-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-219">czech passport number</span></span>  <br/> <span data-ttu-id="8bed5-220">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-220">passport no</span></span>  <br/> <span data-ttu-id="8bed5-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="8bed5-221">cestovní pas</span></span>  <br/> <span data-ttu-id="8bed5-222">pas</span><span class="sxs-lookup"><span data-stu-id="8bed5-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8bed5-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="8bed5-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-224">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-224">Format</span></span>

<span data-ttu-id="8bed5-225">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-226">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-226">Pattern</span></span>

 <span data-ttu-id="8bed5-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8bed5-228">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-228">Checksum</span></span>

<span data-ttu-id="8bed5-229">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-230">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-230">Definition</span></span>

<span data-ttu-id="8bed5-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-234">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-234">Keywords</span></span>

<span data-ttu-id="8bed5-235">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-235"></span></span>
|<span data-ttu-id="8bed5-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-237">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-237">passport number</span></span>  <br/> <span data-ttu-id="8bed5-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-238">danish passport number</span></span>  <br/> <span data-ttu-id="8bed5-239">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-239">passport no</span></span>  <br/> <span data-ttu-id="8bed5-240">pas</span><span class="sxs-lookup"><span data-stu-id="8bed5-240">pas</span></span>  <br/> <span data-ttu-id="8bed5-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8bed5-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="8bed5-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-243">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-243">Format</span></span>

<span data-ttu-id="8bed5-244">一个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-245">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-245">Pattern</span></span>

<span data-ttu-id="8bed5-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-247">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-247">Checksum</span></span>

<span data-ttu-id="8bed5-248">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-249">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-249">Definition</span></span>

<span data-ttu-id="8bed5-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-253">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-253">Keywords</span></span>

<span data-ttu-id="8bed5-254">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-254"></span></span>
|<span data-ttu-id="8bed5-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-256">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-256">passport number</span></span>  <br/> <span data-ttu-id="8bed5-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-257">estonian passport number</span></span>  <br/> <span data-ttu-id="8bed5-258">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-258">passport no</span></span>  <br/> <span data-ttu-id="8bed5-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="8bed5-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8bed5-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="8bed5-260">Finland</span></span>

<span data-ttu-id="8bed5-261">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8bed5-262">法国</span><span class="sxs-lookup"><span data-stu-id="8bed5-262">France</span></span>

<span data-ttu-id="8bed5-263">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8bed5-264">德国</span><span class="sxs-lookup"><span data-stu-id="8bed5-264">Germany</span></span>

<span data-ttu-id="8bed5-265">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8bed5-266">希腊</span><span class="sxs-lookup"><span data-stu-id="8bed5-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-267">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-267">Format</span></span>

<span data-ttu-id="8bed5-268">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-269">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-269">Pattern</span></span>

<span data-ttu-id="8bed5-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-271">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-271">Checksum</span></span>

<span data-ttu-id="8bed5-272">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-273">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-273">Definition</span></span>

<span data-ttu-id="8bed5-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-277">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-277">Keywords</span></span>

<span data-ttu-id="8bed5-278">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-278"></span></span>
|<span data-ttu-id="8bed5-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-280">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-280">passport number</span></span>  <br/> <span data-ttu-id="8bed5-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-281">greek passport number</span></span>  <br/> <span data-ttu-id="8bed5-282">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-282">passport no</span></span>  <br/> <span data-ttu-id="8bed5-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="8bed5-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8bed5-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8bed5-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-285">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-285">Format</span></span>

<span data-ttu-id="8bed5-286">两个字母后跟6个或7个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-287">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-287">Pattern</span></span>

<span data-ttu-id="8bed5-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-289">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-289">Checksum</span></span>

<span data-ttu-id="8bed5-290">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-291">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-291">Definition</span></span>

<span data-ttu-id="8bed5-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-295">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-295">Keywords</span></span>

<span data-ttu-id="8bed5-296">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-296"></span></span>
|<span data-ttu-id="8bed5-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-298">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-298">passport number</span></span>  <br/> <span data-ttu-id="8bed5-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="8bed5-300">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-300">passport no</span></span>  <br/> <span data-ttu-id="8bed5-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="8bed5-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8bed5-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="8bed5-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-303">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-303">Format</span></span>

<span data-ttu-id="8bed5-304">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-305">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-305">Pattern</span></span>

<span data-ttu-id="8bed5-306">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="8bed5-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8bed5-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8bed5-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-309">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-309">Checksum</span></span>

<span data-ttu-id="8bed5-310">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-311">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-311">Definition</span></span>

<span data-ttu-id="8bed5-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-315">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-315">Keywords</span></span>

<span data-ttu-id="8bed5-316">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-316"></span></span>
|<span data-ttu-id="8bed5-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-318">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-318">passport number</span></span>  <br/> <span data-ttu-id="8bed5-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-319">irish passport number</span></span>  <br/> <span data-ttu-id="8bed5-320">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-320">passport no</span></span>  <br/> <span data-ttu-id="8bed5-321">pas</span><span class="sxs-lookup"><span data-stu-id="8bed5-321">pas</span></span>  <br/> <span data-ttu-id="8bed5-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="8bed5-322">passport</span></span>  <br/> <span data-ttu-id="8bed5-323">passeport</span><span class="sxs-lookup"><span data-stu-id="8bed5-323">passeport</span></span>  <br/> <span data-ttu-id="8bed5-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="8bed5-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8bed5-325">意大利</span><span class="sxs-lookup"><span data-stu-id="8bed5-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-326">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-326">Format</span></span>

<span data-ttu-id="8bed5-327">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-328">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-328">Pattern</span></span>

<span data-ttu-id="8bed5-329">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="8bed5-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8bed5-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8bed5-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-332">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-332">Checksum</span></span>

<span data-ttu-id="8bed5-333">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-334">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-334">Definition</span></span>

<span data-ttu-id="8bed5-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-338">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-338">Keywords</span></span>

<span data-ttu-id="8bed5-339">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-339"></span></span>
|<span data-ttu-id="8bed5-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-341">italian passport number</span></span>  <br/> <span data-ttu-id="8bed5-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="8bed5-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="8bed5-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="8bed5-343">passaporto</span></span>  <br/> <span data-ttu-id="8bed5-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="8bed5-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="8bed5-345">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-345">passport number</span></span>  <br/> <span data-ttu-id="8bed5-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8bed5-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="8bed5-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8bed5-347">passaporto numero</span></span>  <br/> <span data-ttu-id="8bed5-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="8bed5-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="8bed5-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="8bed5-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="8bed5-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="8bed5-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-351">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-351">Format</span></span>

<span data-ttu-id="8bed5-352">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-353">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-353">Pattern</span></span>

<span data-ttu-id="8bed5-354">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="8bed5-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8bed5-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8bed5-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-357">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-357">Checksum</span></span>

<span data-ttu-id="8bed5-358">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-359">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-359">Definition</span></span>

<span data-ttu-id="8bed5-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-363">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-363">Keywords</span></span>

<span data-ttu-id="8bed5-364">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-364"></span></span>
|<span data-ttu-id="8bed5-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-366">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-366">passport number</span></span>  <br/> <span data-ttu-id="8bed5-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-367">latvian passport number</span></span>  <br/> <span data-ttu-id="8bed5-368">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-368">passport no</span></span>  <br/> <span data-ttu-id="8bed5-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="8bed5-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8bed5-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="8bed5-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-371">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-371">Format</span></span>

<span data-ttu-id="8bed5-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-373">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-373">Pattern</span></span>

<span data-ttu-id="8bed5-374">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-375">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-375">Checksum</span></span>

<span data-ttu-id="8bed5-376">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-377">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-377">Definition</span></span>

<span data-ttu-id="8bed5-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-381">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-381">Keywords</span></span>

<span data-ttu-id="8bed5-382">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-382"></span></span>
|<span data-ttu-id="8bed5-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-384">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-384">passport number</span></span>  <br/> <span data-ttu-id="8bed5-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="8bed5-386">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-386">passport no</span></span>  <br/> <span data-ttu-id="8bed5-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="8bed5-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8bed5-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="8bed5-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-389">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-389">Format</span></span>

<span data-ttu-id="8bed5-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-391">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-391">Pattern</span></span>

<span data-ttu-id="8bed5-392">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-393">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-393">Checksum</span></span>

<span data-ttu-id="8bed5-394">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-395">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-395">Definition</span></span>

<span data-ttu-id="8bed5-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-399">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-399">Keywords</span></span>

<span data-ttu-id="8bed5-400">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-400"></span></span>
|<span data-ttu-id="8bed5-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-402">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-402">passport number</span></span>  <br/> <span data-ttu-id="8bed5-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-403">latvian passport number</span></span>  <br/> <span data-ttu-id="8bed5-404">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-404">passport no</span></span>  <br/> <span data-ttu-id="8bed5-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8bed5-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="8bed5-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-407">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-407">Format</span></span>

<span data-ttu-id="8bed5-408">七位数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-409">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-409">Pattern</span></span>

 <span data-ttu-id="8bed5-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8bed5-411">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-411">Checksum</span></span>

<span data-ttu-id="8bed5-412">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-413">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-413">Definition</span></span>

<span data-ttu-id="8bed5-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-417">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-417">Keywords</span></span>

<span data-ttu-id="8bed5-418">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-418"></span></span>
|<span data-ttu-id="8bed5-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-420">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-420">passport number</span></span>  <br/> <span data-ttu-id="8bed5-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-421">maltese passport number</span></span>  <br/> <span data-ttu-id="8bed5-422">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-422">passport no</span></span>  <br/> <span data-ttu-id="8bed5-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="8bed5-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8bed5-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="8bed5-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-425">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-425">Format</span></span>

<span data-ttu-id="8bed5-426">九个字母或数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-427">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-427">Pattern</span></span>

<span data-ttu-id="8bed5-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-429">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-429">Checksum</span></span>

<span data-ttu-id="8bed5-430">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-431">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-431">Definition</span></span>

<span data-ttu-id="8bed5-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-435">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-435">Keywords</span></span>

<span data-ttu-id="8bed5-436">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-436"></span></span>
|<span data-ttu-id="8bed5-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-438">dutch passport number</span></span>  <br/> <span data-ttu-id="8bed5-439">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-439">passport number</span></span>  <br/> <span data-ttu-id="8bed5-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="8bed5-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="8bed5-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="8bed5-442">paspoort</span></span>  <br/> <span data-ttu-id="8bed5-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="8bed5-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8bed5-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8bed5-445">波兰</span><span class="sxs-lookup"><span data-stu-id="8bed5-445">Poland</span></span>

<span data-ttu-id="8bed5-446">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8bed5-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8bed5-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-448">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-448">Format</span></span>

<span data-ttu-id="8bed5-449">一个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-450">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-450">Pattern</span></span>

<span data-ttu-id="8bed5-451">一个字母后跟六个数字：</span><span class="sxs-lookup"><span data-stu-id="8bed5-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="8bed5-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8bed5-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8bed5-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-454">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-454">Checksum</span></span>

<span data-ttu-id="8bed5-455">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-456">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-456">Definition</span></span>

<span data-ttu-id="8bed5-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-460">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-460">Keywords</span></span>

<span data-ttu-id="8bed5-461">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-461"></span></span>
|<span data-ttu-id="8bed5-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-463">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-463">passport number</span></span>  <br/> <span data-ttu-id="8bed5-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="8bed5-465">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-465">passport no</span></span>  <br/> <span data-ttu-id="8bed5-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="8bed5-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8bed5-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="8bed5-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-468">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-468">Format</span></span>

<span data-ttu-id="8bed5-469">八个或9个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-470">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-470">Pattern</span></span>

<span data-ttu-id="8bed5-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-472">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-472">Checksum</span></span>

<span data-ttu-id="8bed5-473">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-474">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-474">Definition</span></span>

<span data-ttu-id="8bed5-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-478">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-478">Keywords</span></span>

<span data-ttu-id="8bed5-479">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-479"></span></span>
|<span data-ttu-id="8bed5-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-481">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-481">passport number</span></span>  <br/> <span data-ttu-id="8bed5-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-482">romanian passport number</span></span>  <br/> <span data-ttu-id="8bed5-483">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-483">passport no</span></span>  <br/> <span data-ttu-id="8bed5-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="8bed5-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8bed5-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="8bed5-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-486">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-486">Format</span></span>

<span data-ttu-id="8bed5-487">一个数字或字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-488">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-488">Pattern</span></span>

<span data-ttu-id="8bed5-489">一个数字或字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8bed5-490">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-490">Checksum</span></span>

<span data-ttu-id="8bed5-491">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-492">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-492">Definition</span></span>

<span data-ttu-id="8bed5-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-496">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-496">Keywords</span></span>

<span data-ttu-id="8bed5-497">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-497"></span></span>
|<span data-ttu-id="8bed5-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-499">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-499">passport number</span></span>  <br/> <span data-ttu-id="8bed5-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="8bed5-501">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-501">passport no</span></span>  <br/> <span data-ttu-id="8bed5-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="8bed5-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8bed5-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="8bed5-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-504">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-504">Format</span></span>

<span data-ttu-id="8bed5-505">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-506">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-506">Pattern</span></span>

<span data-ttu-id="8bed5-507">两个字母后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="8bed5-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="8bed5-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="8bed5-508">The letter "P"</span></span>
    
- <span data-ttu-id="8bed5-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="8bed5-509">One uppercase letter</span></span>
    
- <span data-ttu-id="8bed5-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-511">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-511">Checksum</span></span>

<span data-ttu-id="8bed5-512">否</span><span class="sxs-lookup"><span data-stu-id="8bed5-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-513">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-513">Definition</span></span>

<span data-ttu-id="8bed5-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-517">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-517">Keywords</span></span>

<span data-ttu-id="8bed5-518">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-518"></span></span>
|<span data-ttu-id="8bed5-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-520">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-520">passport number</span></span>  <br/> <span data-ttu-id="8bed5-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="8bed5-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="8bed5-522">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-522">passport no</span></span>  <br/> <span data-ttu-id="8bed5-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="8bed5-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8bed5-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="8bed5-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8bed5-525">Format</span><span class="sxs-lookup"><span data-stu-id="8bed5-525">Format</span></span>

<span data-ttu-id="8bed5-526">八个或九个字符的字母和数字的组合，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8bed5-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8bed5-527">模式</span><span class="sxs-lookup"><span data-stu-id="8bed5-527">Pattern</span></span>

<span data-ttu-id="8bed5-528">字母和数字的八个或九个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="8bed5-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="8bed5-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="8bed5-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="8bed5-530">一个数字或字母（可选）</span><span class="sxs-lookup"><span data-stu-id="8bed5-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="8bed5-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="8bed5-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8bed5-532">校验和</span><span class="sxs-lookup"><span data-stu-id="8bed5-532">Checksum</span></span>

<span data-ttu-id="8bed5-533">不适用</span><span class="sxs-lookup"><span data-stu-id="8bed5-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8bed5-534">定义</span><span class="sxs-lookup"><span data-stu-id="8bed5-534">Definition</span></span>

<span data-ttu-id="8bed5-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8bed5-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8bed5-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8bed5-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8bed5-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8bed5-538">关键字</span><span class="sxs-lookup"><span data-stu-id="8bed5-538">Keywords</span></span>

<span data-ttu-id="8bed5-539">| |</span><span class="sxs-lookup"><span data-stu-id="8bed5-539"></span></span>
|<span data-ttu-id="8bed5-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8bed5-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8bed5-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="8bed5-541">passport</span></span>  <br/> <span data-ttu-id="8bed5-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="8bed5-542">spain passport</span></span>  <br/> <span data-ttu-id="8bed5-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="8bed5-543">passport book</span></span>  <br/> <span data-ttu-id="8bed5-544">passport number</span><span class="sxs-lookup"><span data-stu-id="8bed5-544">passport number</span></span>  <br/> <span data-ttu-id="8bed5-545">护照号</span><span class="sxs-lookup"><span data-stu-id="8bed5-545">passport no</span></span>  <br/> <span data-ttu-id="8bed5-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="8bed5-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="8bed5-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="8bed5-547">número pasaporte</span></span>  <br/> <span data-ttu-id="8bed5-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="8bed5-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="8bed5-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8bed5-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8bed5-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="8bed5-550">Sweden</span></span>

<span data-ttu-id="8bed5-551">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="8bed5-552">英国</span><span class="sxs-lookup"><span data-stu-id="8bed5-552">UK</span></span>

<span data-ttu-id="8bed5-553">有关详细信息，请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="8bed5-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="8bed5-554">"Passport 号码"，在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="8bed5-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8bed5-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bed5-555">See also</span></span>

[<span data-ttu-id="8bed5-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8bed5-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

