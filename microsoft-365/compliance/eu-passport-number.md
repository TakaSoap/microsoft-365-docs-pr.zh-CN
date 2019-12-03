---
title: EU 护照号码
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662797"
---
# <a name="eu-passport-number"></a><span data-ttu-id="0527d-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-104">EU Passport Number</span></span>

<span data-ttu-id="0527d-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="0527d-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="0527d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="0527d-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="0527d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="0527d-108">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-108">Format</span></span>

<span data-ttu-id="0527d-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-110">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-110">Pattern</span></span>

<span data-ttu-id="0527d-111">一个字母、七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="0527d-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="0527d-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="0527d-113">一个空格（可选）</span><span class="sxs-lookup"><span data-stu-id="0527d-113">One space (optional)</span></span>
    
- <span data-ttu-id="0527d-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-115">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-115">Checksum</span></span>

<span data-ttu-id="0527d-116">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-117">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-117">Definition</span></span>

<span data-ttu-id="0527d-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-121">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-121">Keywords</span></span>

<span data-ttu-id="0527d-122">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-122"></span></span>
|<span data-ttu-id="0527d-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-124">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-124">passport number</span></span>  <br/> <span data-ttu-id="0527d-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-125">austrian passport number</span></span>  <br/> <span data-ttu-id="0527d-126">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-126">passport no</span></span>  <br/> <span data-ttu-id="0527d-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="0527d-127">reisepass</span></span>  <br/> <span data-ttu-id="0527d-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="0527d-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="0527d-129">比利时</span><span class="sxs-lookup"><span data-stu-id="0527d-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="0527d-130">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-130">Format</span></span>

<span data-ttu-id="0527d-131">两个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-132">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-132">Pattern</span></span>

<span data-ttu-id="0527d-133">两个字母，后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-134">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-134">Checksum</span></span>

<span data-ttu-id="0527d-135">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-136">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-136">Definition</span></span>

<span data-ttu-id="0527d-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-140">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-140">Keywords</span></span>

<span data-ttu-id="0527d-141">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-141"></span></span>
|<span data-ttu-id="0527d-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-143">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-143">passport number</span></span>  <br/> <span data-ttu-id="0527d-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-144">belgian passport number</span></span>  <br/> <span data-ttu-id="0527d-145">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-145">passport no</span></span>  <br/> <span data-ttu-id="0527d-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="0527d-146">paspoort</span></span>  <br/> <span data-ttu-id="0527d-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="0527d-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="0527d-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="0527d-148">reisepass kein</span></span>  <br/> <span data-ttu-id="0527d-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="0527d-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="0527d-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="0527d-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="0527d-151">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-151">Format</span></span>

<span data-ttu-id="0527d-152">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-153">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-153">Pattern</span></span>

 <span data-ttu-id="0527d-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0527d-155">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-155">Checksum</span></span>

<span data-ttu-id="0527d-156">否</span><span class="sxs-lookup"><span data-stu-id="0527d-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-157">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-157">Definition</span></span>

<span data-ttu-id="0527d-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-161">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-161">Keywords</span></span>

<span data-ttu-id="0527d-162">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-162"></span></span>
|<span data-ttu-id="0527d-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-164">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-164">passport number</span></span>  <br/> <span data-ttu-id="0527d-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="0527d-166">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-166">passport no</span></span>  <br/> <span data-ttu-id="0527d-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="0527d-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="0527d-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="0527d-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="0527d-169">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-169">Format</span></span>

<span data-ttu-id="0527d-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-171">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-171">Pattern</span></span>

 <span data-ttu-id="0527d-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0527d-173">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-173">Checksum</span></span>

<span data-ttu-id="0527d-174">否</span><span class="sxs-lookup"><span data-stu-id="0527d-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-175">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-175">Definition</span></span>

<span data-ttu-id="0527d-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-179">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-179">Keywords</span></span>

<span data-ttu-id="0527d-180">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-180"></span></span>
|<span data-ttu-id="0527d-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-182">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-182">passport number</span></span>  <br/> <span data-ttu-id="0527d-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-183">croatian passport number</span></span>  <br/> <span data-ttu-id="0527d-184">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-184">passport no</span></span>  <br/> <span data-ttu-id="0527d-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="0527d-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="0527d-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="0527d-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="0527d-187">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-187">Format</span></span>

<span data-ttu-id="0527d-188">一个字母后跟6-8 个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-189">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-189">Pattern</span></span>

<span data-ttu-id="0527d-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-191">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-191">Checksum</span></span>

<span data-ttu-id="0527d-192">否</span><span class="sxs-lookup"><span data-stu-id="0527d-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-193">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-193">Definition</span></span>

<span data-ttu-id="0527d-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-197">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-197">Keywords</span></span>

<span data-ttu-id="0527d-198">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-198"></span></span>
|<span data-ttu-id="0527d-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-200">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-200">passport number</span></span>  <br/> <span data-ttu-id="0527d-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="0527d-202">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-202">passport no</span></span>  <br/> <span data-ttu-id="0527d-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="0527d-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="0527d-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="0527d-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="0527d-205">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-205">Format</span></span>

<span data-ttu-id="0527d-206">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-207">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-207">Pattern</span></span>

<span data-ttu-id="0527d-208">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-209">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-209">Checksum</span></span>

<span data-ttu-id="0527d-210">否</span><span class="sxs-lookup"><span data-stu-id="0527d-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-211">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-211">Definition</span></span>

<span data-ttu-id="0527d-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-215">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-215">Keywords</span></span>

<span data-ttu-id="0527d-216">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-216"></span></span>
|<span data-ttu-id="0527d-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-218">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-218">passport number</span></span>  <br/> <span data-ttu-id="0527d-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-219">czech passport number</span></span>  <br/> <span data-ttu-id="0527d-220">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-220">passport no</span></span>  <br/> <span data-ttu-id="0527d-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="0527d-221">cestovní pas</span></span>  <br/> <span data-ttu-id="0527d-222">pas</span><span class="sxs-lookup"><span data-stu-id="0527d-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="0527d-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="0527d-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="0527d-224">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-224">Format</span></span>

<span data-ttu-id="0527d-225">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-226">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-226">Pattern</span></span>

 <span data-ttu-id="0527d-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0527d-228">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-228">Checksum</span></span>

<span data-ttu-id="0527d-229">否</span><span class="sxs-lookup"><span data-stu-id="0527d-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-230">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-230">Definition</span></span>

<span data-ttu-id="0527d-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-234">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-234">Keywords</span></span>

<span data-ttu-id="0527d-235">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-235"></span></span>
|<span data-ttu-id="0527d-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-237">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-237">passport number</span></span>  <br/> <span data-ttu-id="0527d-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-238">danish passport number</span></span>  <br/> <span data-ttu-id="0527d-239">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-239">passport no</span></span>  <br/> <span data-ttu-id="0527d-240">pas</span><span class="sxs-lookup"><span data-stu-id="0527d-240">pas</span></span>  <br/> <span data-ttu-id="0527d-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="0527d-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="0527d-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="0527d-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="0527d-243">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-243">Format</span></span>

<span data-ttu-id="0527d-244">一个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-245">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-245">Pattern</span></span>

<span data-ttu-id="0527d-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-247">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-247">Checksum</span></span>

<span data-ttu-id="0527d-248">否</span><span class="sxs-lookup"><span data-stu-id="0527d-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-249">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-249">Definition</span></span>

<span data-ttu-id="0527d-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-253">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-253">Keywords</span></span>

<span data-ttu-id="0527d-254">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-254"></span></span>
|<span data-ttu-id="0527d-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-256">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-256">passport number</span></span>  <br/> <span data-ttu-id="0527d-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-257">estonian passport number</span></span>  <br/> <span data-ttu-id="0527d-258">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-258">passport no</span></span>  <br/> <span data-ttu-id="0527d-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="0527d-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="0527d-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="0527d-260">Finland</span></span>

<span data-ttu-id="0527d-261">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="0527d-262">法国</span><span class="sxs-lookup"><span data-stu-id="0527d-262">France</span></span>

<span data-ttu-id="0527d-263">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="0527d-264">德国</span><span class="sxs-lookup"><span data-stu-id="0527d-264">Germany</span></span>

<span data-ttu-id="0527d-265">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="0527d-266">希腊</span><span class="sxs-lookup"><span data-stu-id="0527d-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="0527d-267">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-267">Format</span></span>

<span data-ttu-id="0527d-268">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-269">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-269">Pattern</span></span>

<span data-ttu-id="0527d-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-271">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-271">Checksum</span></span>

<span data-ttu-id="0527d-272">否</span><span class="sxs-lookup"><span data-stu-id="0527d-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-273">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-273">Definition</span></span>

<span data-ttu-id="0527d-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-277">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-277">Keywords</span></span>

<span data-ttu-id="0527d-278">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-278"></span></span>
|<span data-ttu-id="0527d-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-280">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-280">passport number</span></span>  <br/> <span data-ttu-id="0527d-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-281">greek passport number</span></span>  <br/> <span data-ttu-id="0527d-282">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-282">passport no</span></span>  <br/> <span data-ttu-id="0527d-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="0527d-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="0527d-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="0527d-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="0527d-285">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-285">Format</span></span>

<span data-ttu-id="0527d-286">两个字母后跟6个或7个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-287">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-287">Pattern</span></span>

<span data-ttu-id="0527d-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-289">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-289">Checksum</span></span>

<span data-ttu-id="0527d-290">否</span><span class="sxs-lookup"><span data-stu-id="0527d-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-291">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-291">Definition</span></span>

<span data-ttu-id="0527d-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-295">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-295">Keywords</span></span>

<span data-ttu-id="0527d-296">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-296"></span></span>
|<span data-ttu-id="0527d-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-298">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-298">passport number</span></span>  <br/> <span data-ttu-id="0527d-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="0527d-300">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-300">passport no</span></span>  <br/> <span data-ttu-id="0527d-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="0527d-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="0527d-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="0527d-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="0527d-303">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-303">Format</span></span>

<span data-ttu-id="0527d-304">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-305">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-305">Pattern</span></span>

<span data-ttu-id="0527d-306">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="0527d-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="0527d-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="0527d-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-309">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-309">Checksum</span></span>

<span data-ttu-id="0527d-310">否</span><span class="sxs-lookup"><span data-stu-id="0527d-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-311">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-311">Definition</span></span>

<span data-ttu-id="0527d-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-315">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-315">Keywords</span></span>

<span data-ttu-id="0527d-316">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-316"></span></span>
|<span data-ttu-id="0527d-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-318">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-318">passport number</span></span>  <br/> <span data-ttu-id="0527d-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-319">irish passport number</span></span>  <br/> <span data-ttu-id="0527d-320">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-320">passport no</span></span>  <br/> <span data-ttu-id="0527d-321">pas</span><span class="sxs-lookup"><span data-stu-id="0527d-321">pas</span></span>  <br/> <span data-ttu-id="0527d-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="0527d-322">passport</span></span>  <br/> <span data-ttu-id="0527d-323">passeport</span><span class="sxs-lookup"><span data-stu-id="0527d-323">passeport</span></span>  <br/> <span data-ttu-id="0527d-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="0527d-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="0527d-325">意大利</span><span class="sxs-lookup"><span data-stu-id="0527d-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="0527d-326">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-326">Format</span></span>

<span data-ttu-id="0527d-327">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-328">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-328">Pattern</span></span>

<span data-ttu-id="0527d-329">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="0527d-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="0527d-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="0527d-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-332">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-332">Checksum</span></span>

<span data-ttu-id="0527d-333">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-334">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-334">Definition</span></span>

<span data-ttu-id="0527d-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-338">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-338">Keywords</span></span>

<span data-ttu-id="0527d-339">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-339"></span></span>
|<span data-ttu-id="0527d-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-341">italian passport number</span></span>  <br/> <span data-ttu-id="0527d-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="0527d-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="0527d-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="0527d-343">passaporto</span></span>  <br/> <span data-ttu-id="0527d-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="0527d-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="0527d-345">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-345">passport number</span></span>  <br/> <span data-ttu-id="0527d-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="0527d-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="0527d-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="0527d-347">passaporto numero</span></span>  <br/> <span data-ttu-id="0527d-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="0527d-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="0527d-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="0527d-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="0527d-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="0527d-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="0527d-351">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-351">Format</span></span>

<span data-ttu-id="0527d-352">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-353">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-353">Pattern</span></span>

<span data-ttu-id="0527d-354">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="0527d-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="0527d-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="0527d-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-357">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-357">Checksum</span></span>

<span data-ttu-id="0527d-358">否</span><span class="sxs-lookup"><span data-stu-id="0527d-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-359">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-359">Definition</span></span>

<span data-ttu-id="0527d-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-363">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-363">Keywords</span></span>

<span data-ttu-id="0527d-364">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-364"></span></span>
|<span data-ttu-id="0527d-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-366">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-366">passport number</span></span>  <br/> <span data-ttu-id="0527d-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-367">latvian passport number</span></span>  <br/> <span data-ttu-id="0527d-368">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-368">passport no</span></span>  <br/> <span data-ttu-id="0527d-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="0527d-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="0527d-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="0527d-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="0527d-371">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-371">Format</span></span>

<span data-ttu-id="0527d-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-373">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-373">Pattern</span></span>

<span data-ttu-id="0527d-374">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-375">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-375">Checksum</span></span>

<span data-ttu-id="0527d-376">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-377">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-377">Definition</span></span>

<span data-ttu-id="0527d-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-381">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-381">Keywords</span></span>

<span data-ttu-id="0527d-382">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-382"></span></span>
|<span data-ttu-id="0527d-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-384">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-384">passport number</span></span>  <br/> <span data-ttu-id="0527d-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="0527d-386">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-386">passport no</span></span>  <br/> <span data-ttu-id="0527d-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="0527d-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="0527d-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="0527d-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="0527d-389">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-389">Format</span></span>

<span data-ttu-id="0527d-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-391">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-391">Pattern</span></span>

<span data-ttu-id="0527d-392">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-393">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-393">Checksum</span></span>

<span data-ttu-id="0527d-394">否</span><span class="sxs-lookup"><span data-stu-id="0527d-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-395">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-395">Definition</span></span>

<span data-ttu-id="0527d-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-399">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-399">Keywords</span></span>

<span data-ttu-id="0527d-400">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-400"></span></span>
|<span data-ttu-id="0527d-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-402">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-402">passport number</span></span>  <br/> <span data-ttu-id="0527d-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-403">latvian passport number</span></span>  <br/> <span data-ttu-id="0527d-404">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-404">passport no</span></span>  <br/> <span data-ttu-id="0527d-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="0527d-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="0527d-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="0527d-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="0527d-407">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-407">Format</span></span>

<span data-ttu-id="0527d-408">七位数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-409">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-409">Pattern</span></span>

 <span data-ttu-id="0527d-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0527d-411">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-411">Checksum</span></span>

<span data-ttu-id="0527d-412">否</span><span class="sxs-lookup"><span data-stu-id="0527d-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-413">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-413">Definition</span></span>

<span data-ttu-id="0527d-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-417">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-417">Keywords</span></span>

<span data-ttu-id="0527d-418">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-418"></span></span>
|<span data-ttu-id="0527d-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-420">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-420">passport number</span></span>  <br/> <span data-ttu-id="0527d-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-421">maltese passport number</span></span>  <br/> <span data-ttu-id="0527d-422">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-422">passport no</span></span>  <br/> <span data-ttu-id="0527d-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="0527d-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="0527d-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="0527d-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="0527d-425">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-425">Format</span></span>

<span data-ttu-id="0527d-426">九个字母或数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-427">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-427">Pattern</span></span>

<span data-ttu-id="0527d-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="0527d-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-429">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-429">Checksum</span></span>

<span data-ttu-id="0527d-430">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-431">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-431">Definition</span></span>

<span data-ttu-id="0527d-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-435">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-435">Keywords</span></span>

<span data-ttu-id="0527d-436">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-436"></span></span>
|<span data-ttu-id="0527d-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-438">dutch passport number</span></span>  <br/> <span data-ttu-id="0527d-439">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-439">passport number</span></span>  <br/> <span data-ttu-id="0527d-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="0527d-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="0527d-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="0527d-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="0527d-442">paspoort</span></span>  <br/> <span data-ttu-id="0527d-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="0527d-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="0527d-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="0527d-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="0527d-445">波兰</span><span class="sxs-lookup"><span data-stu-id="0527d-445">Poland</span></span>

<span data-ttu-id="0527d-446">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="0527d-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="0527d-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="0527d-448">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-448">Format</span></span>

<span data-ttu-id="0527d-449">一个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-450">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-450">Pattern</span></span>

<span data-ttu-id="0527d-451">一个字母后跟六个数字：</span><span class="sxs-lookup"><span data-stu-id="0527d-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="0527d-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="0527d-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="0527d-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-454">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-454">Checksum</span></span>

<span data-ttu-id="0527d-455">否</span><span class="sxs-lookup"><span data-stu-id="0527d-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-456">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-456">Definition</span></span>

<span data-ttu-id="0527d-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-460">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-460">Keywords</span></span>

<span data-ttu-id="0527d-461">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-461"></span></span>
|<span data-ttu-id="0527d-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-463">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-463">passport number</span></span>  <br/> <span data-ttu-id="0527d-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="0527d-465">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-465">passport no</span></span>  <br/> <span data-ttu-id="0527d-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="0527d-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="0527d-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="0527d-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="0527d-468">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-468">Format</span></span>

<span data-ttu-id="0527d-469">八个或9个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-470">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-470">Pattern</span></span>

<span data-ttu-id="0527d-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-472">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-472">Checksum</span></span>

<span data-ttu-id="0527d-473">否</span><span class="sxs-lookup"><span data-stu-id="0527d-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-474">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-474">Definition</span></span>

<span data-ttu-id="0527d-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-478">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-478">Keywords</span></span>

<span data-ttu-id="0527d-479">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-479"></span></span>
|<span data-ttu-id="0527d-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-481">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-481">passport number</span></span>  <br/> <span data-ttu-id="0527d-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-482">romanian passport number</span></span>  <br/> <span data-ttu-id="0527d-483">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-483">passport no</span></span>  <br/> <span data-ttu-id="0527d-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="0527d-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="0527d-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="0527d-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="0527d-486">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-486">Format</span></span>

<span data-ttu-id="0527d-487">一个数字或字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-488">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-488">Pattern</span></span>

<span data-ttu-id="0527d-489">一个数字或字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0527d-490">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-490">Checksum</span></span>

<span data-ttu-id="0527d-491">否</span><span class="sxs-lookup"><span data-stu-id="0527d-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-492">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-492">Definition</span></span>

<span data-ttu-id="0527d-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-496">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-496">Keywords</span></span>

<span data-ttu-id="0527d-497">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-497"></span></span>
|<span data-ttu-id="0527d-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-499">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-499">passport number</span></span>  <br/> <span data-ttu-id="0527d-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="0527d-501">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-501">passport no</span></span>  <br/> <span data-ttu-id="0527d-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="0527d-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="0527d-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="0527d-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="0527d-504">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-504">Format</span></span>

<span data-ttu-id="0527d-505">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-506">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-506">Pattern</span></span>

<span data-ttu-id="0527d-507">两个字母后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="0527d-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="0527d-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="0527d-508">The letter "P"</span></span>
    
- <span data-ttu-id="0527d-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="0527d-509">One uppercase letter</span></span>
    
- <span data-ttu-id="0527d-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-511">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-511">Checksum</span></span>

<span data-ttu-id="0527d-512">否</span><span class="sxs-lookup"><span data-stu-id="0527d-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-513">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-513">Definition</span></span>

<span data-ttu-id="0527d-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-517">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-517">Keywords</span></span>

<span data-ttu-id="0527d-518">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-518"></span></span>
|<span data-ttu-id="0527d-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-520">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-520">passport number</span></span>  <br/> <span data-ttu-id="0527d-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="0527d-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="0527d-522">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-522">passport no</span></span>  <br/> <span data-ttu-id="0527d-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="0527d-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="0527d-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="0527d-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="0527d-525">Format</span><span class="sxs-lookup"><span data-stu-id="0527d-525">Format</span></span>

<span data-ttu-id="0527d-526">八个或九个字符的字母和数字的组合，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="0527d-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0527d-527">模式</span><span class="sxs-lookup"><span data-stu-id="0527d-527">Pattern</span></span>

<span data-ttu-id="0527d-528">字母和数字的八个或九个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="0527d-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="0527d-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="0527d-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="0527d-530">一个数字或字母（可选）</span><span class="sxs-lookup"><span data-stu-id="0527d-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="0527d-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="0527d-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0527d-532">校验和</span><span class="sxs-lookup"><span data-stu-id="0527d-532">Checksum</span></span>

<span data-ttu-id="0527d-533">不适用</span><span class="sxs-lookup"><span data-stu-id="0527d-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="0527d-534">定义</span><span class="sxs-lookup"><span data-stu-id="0527d-534">Definition</span></span>

<span data-ttu-id="0527d-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="0527d-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0527d-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="0527d-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0527d-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="0527d-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0527d-538">关键字</span><span class="sxs-lookup"><span data-stu-id="0527d-538">Keywords</span></span>

<span data-ttu-id="0527d-539">| |</span><span class="sxs-lookup"><span data-stu-id="0527d-539"></span></span>
|<span data-ttu-id="0527d-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="0527d-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="0527d-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="0527d-541">passport</span></span>  <br/> <span data-ttu-id="0527d-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="0527d-542">spain passport</span></span>  <br/> <span data-ttu-id="0527d-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="0527d-543">passport book</span></span>  <br/> <span data-ttu-id="0527d-544">passport number</span><span class="sxs-lookup"><span data-stu-id="0527d-544">passport number</span></span>  <br/> <span data-ttu-id="0527d-545">护照号</span><span class="sxs-lookup"><span data-stu-id="0527d-545">passport no</span></span>  <br/> <span data-ttu-id="0527d-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="0527d-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="0527d-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="0527d-547">número pasaporte</span></span>  <br/> <span data-ttu-id="0527d-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="0527d-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="0527d-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="0527d-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="0527d-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="0527d-550">Sweden</span></span>

<span data-ttu-id="0527d-551">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="0527d-552">英国</span><span class="sxs-lookup"><span data-stu-id="0527d-552">UK</span></span>

<span data-ttu-id="0527d-553">有关详细信息，请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="0527d-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="0527d-554">"Passport 号码"，在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="0527d-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0527d-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0527d-555">See also</span></span>

[<span data-ttu-id="0527d-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="0527d-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

