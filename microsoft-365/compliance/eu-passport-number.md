---
title: EU 护照号码
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592113"
---
# <a name="eu-passport-number"></a><span data-ttu-id="3232c-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-104">EU Passport Number</span></span>

<span data-ttu-id="3232c-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="3232c-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="3232c-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3232c-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="3232c-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3232c-108">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-108">Format</span></span>

<span data-ttu-id="3232c-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-110">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-110">Pattern</span></span>

<span data-ttu-id="3232c-111">一个字母、七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="3232c-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="3232c-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3232c-113">一个空格（可选）</span><span class="sxs-lookup"><span data-stu-id="3232c-113">One space (optional)</span></span>
    
- <span data-ttu-id="3232c-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-115">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-115">Checksum</span></span>

<span data-ttu-id="3232c-116">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-117">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-117">Definition</span></span>

<span data-ttu-id="3232c-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-121">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-121">Keywords</span></span>

<span data-ttu-id="3232c-122">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-122">| |</span></span>
|<span data-ttu-id="3232c-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-124">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-124">passport number</span></span>  <br/> <span data-ttu-id="3232c-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-125">austrian passport number</span></span>  <br/> <span data-ttu-id="3232c-126">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-126">passport no</span></span>  <br/> <span data-ttu-id="3232c-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="3232c-127">reisepass</span></span>  <br/> <span data-ttu-id="3232c-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="3232c-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3232c-129">比利时</span><span class="sxs-lookup"><span data-stu-id="3232c-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3232c-130">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-130">Format</span></span>

<span data-ttu-id="3232c-131">两个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-132">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-132">Pattern</span></span>

<span data-ttu-id="3232c-133">两个字母，后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-134">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-134">Checksum</span></span>

<span data-ttu-id="3232c-135">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-136">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-136">Definition</span></span>

<span data-ttu-id="3232c-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-140">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-140">Keywords</span></span>

<span data-ttu-id="3232c-141">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-141">| |</span></span>
|<span data-ttu-id="3232c-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-143">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-143">passport number</span></span>  <br/> <span data-ttu-id="3232c-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-144">belgian passport number</span></span>  <br/> <span data-ttu-id="3232c-145">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-145">passport no</span></span>  <br/> <span data-ttu-id="3232c-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="3232c-146">paspoort</span></span>  <br/> <span data-ttu-id="3232c-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3232c-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="3232c-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="3232c-148">reisepass kein</span></span>  <br/> <span data-ttu-id="3232c-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="3232c-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3232c-150">保加利亚</span><span class="sxs-lookup"><span data-stu-id="3232c-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3232c-151">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-151">Format</span></span>

<span data-ttu-id="3232c-152">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-153">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-153">Pattern</span></span>

 <span data-ttu-id="3232c-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3232c-155">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-155">Checksum</span></span>

<span data-ttu-id="3232c-156">否</span><span class="sxs-lookup"><span data-stu-id="3232c-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-157">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-157">Definition</span></span>

<span data-ttu-id="3232c-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-161">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-161">Keywords</span></span>

<span data-ttu-id="3232c-162">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-162">| |</span></span>
|<span data-ttu-id="3232c-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-164">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-164">passport number</span></span>  <br/> <span data-ttu-id="3232c-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="3232c-166">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-166">passport no</span></span>  <br/> <span data-ttu-id="3232c-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="3232c-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3232c-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="3232c-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3232c-169">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-169">Format</span></span>

<span data-ttu-id="3232c-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-171">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-171">Pattern</span></span>

 <span data-ttu-id="3232c-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3232c-173">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-173">Checksum</span></span>

<span data-ttu-id="3232c-174">否</span><span class="sxs-lookup"><span data-stu-id="3232c-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-175">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-175">Definition</span></span>

<span data-ttu-id="3232c-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-179">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-179">Keywords</span></span>

<span data-ttu-id="3232c-180">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-180">| |</span></span>
|<span data-ttu-id="3232c-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-182">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-182">passport number</span></span>  <br/> <span data-ttu-id="3232c-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-183">croatian passport number</span></span>  <br/> <span data-ttu-id="3232c-184">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-184">passport no</span></span>  <br/> <span data-ttu-id="3232c-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="3232c-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3232c-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="3232c-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3232c-187">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-187">Format</span></span>

<span data-ttu-id="3232c-188">一个字母后跟6-8 个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-189">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-189">Pattern</span></span>

<span data-ttu-id="3232c-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-191">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-191">Checksum</span></span>

<span data-ttu-id="3232c-192">否</span><span class="sxs-lookup"><span data-stu-id="3232c-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-193">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-193">Definition</span></span>

<span data-ttu-id="3232c-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-197">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-197">Keywords</span></span>

<span data-ttu-id="3232c-198">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-198">| |</span></span>
|<span data-ttu-id="3232c-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-200">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-200">passport number</span></span>  <br/> <span data-ttu-id="3232c-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="3232c-202">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-202">passport no</span></span>  <br/> <span data-ttu-id="3232c-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="3232c-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3232c-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="3232c-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3232c-205">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-205">Format</span></span>

<span data-ttu-id="3232c-206">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-207">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-207">Pattern</span></span>

<span data-ttu-id="3232c-208">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-209">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-209">Checksum</span></span>

<span data-ttu-id="3232c-210">否</span><span class="sxs-lookup"><span data-stu-id="3232c-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-211">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-211">Definition</span></span>

<span data-ttu-id="3232c-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-215">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-215">Keywords</span></span>

<span data-ttu-id="3232c-216">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-216">| |</span></span>
|<span data-ttu-id="3232c-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-218">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-218">passport number</span></span>  <br/> <span data-ttu-id="3232c-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-219">czech passport number</span></span>  <br/> <span data-ttu-id="3232c-220">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-220">passport no</span></span>  <br/> <span data-ttu-id="3232c-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="3232c-221">cestovní pas</span></span>  <br/> <span data-ttu-id="3232c-222">pas</span><span class="sxs-lookup"><span data-stu-id="3232c-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3232c-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="3232c-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3232c-224">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-224">Format</span></span>

<span data-ttu-id="3232c-225">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-226">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-226">Pattern</span></span>

 <span data-ttu-id="3232c-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3232c-228">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-228">Checksum</span></span>

<span data-ttu-id="3232c-229">否</span><span class="sxs-lookup"><span data-stu-id="3232c-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-230">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-230">Definition</span></span>

<span data-ttu-id="3232c-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-234">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-234">Keywords</span></span>

<span data-ttu-id="3232c-235">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-235">| |</span></span>
|<span data-ttu-id="3232c-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-237">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-237">passport number</span></span>  <br/> <span data-ttu-id="3232c-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-238">danish passport number</span></span>  <br/> <span data-ttu-id="3232c-239">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-239">passport no</span></span>  <br/> <span data-ttu-id="3232c-240">pas</span><span class="sxs-lookup"><span data-stu-id="3232c-240">pas</span></span>  <br/> <span data-ttu-id="3232c-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="3232c-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3232c-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="3232c-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3232c-243">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-243">Format</span></span>

<span data-ttu-id="3232c-244">一个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-245">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-245">Pattern</span></span>

<span data-ttu-id="3232c-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-247">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-247">Checksum</span></span>

<span data-ttu-id="3232c-248">否</span><span class="sxs-lookup"><span data-stu-id="3232c-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-249">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-249">Definition</span></span>

<span data-ttu-id="3232c-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-253">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-253">Keywords</span></span>

<span data-ttu-id="3232c-254">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-254">| |</span></span>
|<span data-ttu-id="3232c-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-256">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-256">passport number</span></span>  <br/> <span data-ttu-id="3232c-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-257">estonian passport number</span></span>  <br/> <span data-ttu-id="3232c-258">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-258">passport no</span></span>  <br/> <span data-ttu-id="3232c-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="3232c-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3232c-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="3232c-260">Finland</span></span>

<span data-ttu-id="3232c-261">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="3232c-262">法国</span><span class="sxs-lookup"><span data-stu-id="3232c-262">France</span></span>

<span data-ttu-id="3232c-263">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3232c-264">德国</span><span class="sxs-lookup"><span data-stu-id="3232c-264">Germany</span></span>

<span data-ttu-id="3232c-265">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3232c-266">希腊</span><span class="sxs-lookup"><span data-stu-id="3232c-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3232c-267">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-267">Format</span></span>

<span data-ttu-id="3232c-268">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-269">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-269">Pattern</span></span>

<span data-ttu-id="3232c-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-271">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-271">Checksum</span></span>

<span data-ttu-id="3232c-272">否</span><span class="sxs-lookup"><span data-stu-id="3232c-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-273">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-273">Definition</span></span>

<span data-ttu-id="3232c-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-277">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-277">Keywords</span></span>

<span data-ttu-id="3232c-278">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-278">| |</span></span>
|<span data-ttu-id="3232c-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-280">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-280">passport number</span></span>  <br/> <span data-ttu-id="3232c-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-281">greek passport number</span></span>  <br/> <span data-ttu-id="3232c-282">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-282">passport no</span></span>  <br/> <span data-ttu-id="3232c-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="3232c-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3232c-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="3232c-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3232c-285">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-285">Format</span></span>

<span data-ttu-id="3232c-286">两个字母后跟6个或7个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-287">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-287">Pattern</span></span>

<span data-ttu-id="3232c-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-289">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-289">Checksum</span></span>

<span data-ttu-id="3232c-290">否</span><span class="sxs-lookup"><span data-stu-id="3232c-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-291">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-291">Definition</span></span>

<span data-ttu-id="3232c-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-295">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-295">Keywords</span></span>

<span data-ttu-id="3232c-296">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-296">| |</span></span>
|<span data-ttu-id="3232c-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-298">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-298">passport number</span></span>  <br/> <span data-ttu-id="3232c-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="3232c-300">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-300">passport no</span></span>  <br/> <span data-ttu-id="3232c-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="3232c-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3232c-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="3232c-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3232c-303">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-303">Format</span></span>

<span data-ttu-id="3232c-304">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-305">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-305">Pattern</span></span>

<span data-ttu-id="3232c-306">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="3232c-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3232c-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3232c-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-309">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-309">Checksum</span></span>

<span data-ttu-id="3232c-310">否</span><span class="sxs-lookup"><span data-stu-id="3232c-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-311">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-311">Definition</span></span>

<span data-ttu-id="3232c-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-315">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-315">Keywords</span></span>

<span data-ttu-id="3232c-316">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-316">| |</span></span>
|<span data-ttu-id="3232c-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-318">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-318">passport number</span></span>  <br/> <span data-ttu-id="3232c-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-319">irish passport number</span></span>  <br/> <span data-ttu-id="3232c-320">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-320">passport no</span></span>  <br/> <span data-ttu-id="3232c-321">pas</span><span class="sxs-lookup"><span data-stu-id="3232c-321">pas</span></span>  <br/> <span data-ttu-id="3232c-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="3232c-322">passport</span></span>  <br/> <span data-ttu-id="3232c-323">passeport</span><span class="sxs-lookup"><span data-stu-id="3232c-323">passeport</span></span>  <br/> <span data-ttu-id="3232c-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="3232c-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3232c-325">意大利</span><span class="sxs-lookup"><span data-stu-id="3232c-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="3232c-326">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-326">Format</span></span>

<span data-ttu-id="3232c-327">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-328">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-328">Pattern</span></span>

<span data-ttu-id="3232c-329">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="3232c-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3232c-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3232c-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-332">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-332">Checksum</span></span>

<span data-ttu-id="3232c-333">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-334">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-334">Definition</span></span>

<span data-ttu-id="3232c-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-338">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-338">Keywords</span></span>

<span data-ttu-id="3232c-339">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-339">| |</span></span>
|<span data-ttu-id="3232c-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-341">italian passport number</span></span>  <br/> <span data-ttu-id="3232c-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="3232c-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="3232c-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="3232c-343">passaporto</span></span>  <br/> <span data-ttu-id="3232c-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="3232c-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="3232c-345">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-345">passport number</span></span>  <br/> <span data-ttu-id="3232c-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3232c-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="3232c-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="3232c-347">passaporto numero</span></span>  <br/> <span data-ttu-id="3232c-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="3232c-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="3232c-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="3232c-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="3232c-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="3232c-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3232c-351">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-351">Format</span></span>

<span data-ttu-id="3232c-352">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-353">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-353">Pattern</span></span>

<span data-ttu-id="3232c-354">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="3232c-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="3232c-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="3232c-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-357">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-357">Checksum</span></span>

<span data-ttu-id="3232c-358">否</span><span class="sxs-lookup"><span data-stu-id="3232c-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-359">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-359">Definition</span></span>

<span data-ttu-id="3232c-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-363">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-363">Keywords</span></span>

<span data-ttu-id="3232c-364">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-364">| |</span></span>
|<span data-ttu-id="3232c-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-366">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-366">passport number</span></span>  <br/> <span data-ttu-id="3232c-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-367">latvian passport number</span></span>  <br/> <span data-ttu-id="3232c-368">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-368">passport no</span></span>  <br/> <span data-ttu-id="3232c-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="3232c-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3232c-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="3232c-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3232c-371">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-371">Format</span></span>

<span data-ttu-id="3232c-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-373">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-373">Pattern</span></span>

<span data-ttu-id="3232c-374">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-375">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-375">Checksum</span></span>

<span data-ttu-id="3232c-376">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-377">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-377">Definition</span></span>

<span data-ttu-id="3232c-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-381">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-381">Keywords</span></span>

<span data-ttu-id="3232c-382">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-382">| |</span></span>
|<span data-ttu-id="3232c-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-384">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-384">passport number</span></span>  <br/> <span data-ttu-id="3232c-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="3232c-386">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-386">passport no</span></span>  <br/> <span data-ttu-id="3232c-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="3232c-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3232c-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="3232c-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3232c-389">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-389">Format</span></span>

<span data-ttu-id="3232c-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-391">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-391">Pattern</span></span>

<span data-ttu-id="3232c-392">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-393">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-393">Checksum</span></span>

<span data-ttu-id="3232c-394">否</span><span class="sxs-lookup"><span data-stu-id="3232c-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-395">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-395">Definition</span></span>

<span data-ttu-id="3232c-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-399">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-399">Keywords</span></span>

<span data-ttu-id="3232c-400">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-400">| |</span></span>
|<span data-ttu-id="3232c-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-402">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-402">passport number</span></span>  <br/> <span data-ttu-id="3232c-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-403">latvian passport number</span></span>  <br/> <span data-ttu-id="3232c-404">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-404">passport no</span></span>  <br/> <span data-ttu-id="3232c-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="3232c-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3232c-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="3232c-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3232c-407">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-407">Format</span></span>

<span data-ttu-id="3232c-408">七位数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-409">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-409">Pattern</span></span>

 <span data-ttu-id="3232c-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3232c-411">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-411">Checksum</span></span>

<span data-ttu-id="3232c-412">否</span><span class="sxs-lookup"><span data-stu-id="3232c-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-413">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-413">Definition</span></span>

<span data-ttu-id="3232c-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-417">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-417">Keywords</span></span>

<span data-ttu-id="3232c-418">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-418">| |</span></span>
|<span data-ttu-id="3232c-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-420">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-420">passport number</span></span>  <br/> <span data-ttu-id="3232c-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-421">maltese passport number</span></span>  <br/> <span data-ttu-id="3232c-422">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-422">passport no</span></span>  <br/> <span data-ttu-id="3232c-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="3232c-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3232c-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="3232c-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3232c-425">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-425">Format</span></span>

<span data-ttu-id="3232c-426">九个字母或数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-427">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-427">Pattern</span></span>

<span data-ttu-id="3232c-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="3232c-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-429">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-429">Checksum</span></span>

<span data-ttu-id="3232c-430">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-431">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-431">Definition</span></span>

<span data-ttu-id="3232c-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-435">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-435">Keywords</span></span>

<span data-ttu-id="3232c-436">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-436">| |</span></span>
|<span data-ttu-id="3232c-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-438">dutch passport number</span></span>  <br/> <span data-ttu-id="3232c-439">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-439">passport number</span></span>  <br/> <span data-ttu-id="3232c-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="3232c-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="3232c-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="3232c-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="3232c-442">paspoort</span></span>  <br/> <span data-ttu-id="3232c-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3232c-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="3232c-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="3232c-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3232c-445">波兰</span><span class="sxs-lookup"><span data-stu-id="3232c-445">Poland</span></span>

<span data-ttu-id="3232c-446">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="3232c-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="3232c-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3232c-448">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-448">Format</span></span>

<span data-ttu-id="3232c-449">一个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-450">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-450">Pattern</span></span>

<span data-ttu-id="3232c-451">一个字母后跟六个数字：</span><span class="sxs-lookup"><span data-stu-id="3232c-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="3232c-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="3232c-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="3232c-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-454">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-454">Checksum</span></span>

<span data-ttu-id="3232c-455">否</span><span class="sxs-lookup"><span data-stu-id="3232c-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-456">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-456">Definition</span></span>

<span data-ttu-id="3232c-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-460">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-460">Keywords</span></span>

<span data-ttu-id="3232c-461">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-461">| |</span></span>
|<span data-ttu-id="3232c-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-463">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-463">passport number</span></span>  <br/> <span data-ttu-id="3232c-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="3232c-465">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-465">passport no</span></span>  <br/> <span data-ttu-id="3232c-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="3232c-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3232c-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="3232c-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3232c-468">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-468">Format</span></span>

<span data-ttu-id="3232c-469">八个或9个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-470">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-470">Pattern</span></span>

<span data-ttu-id="3232c-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-472">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-472">Checksum</span></span>

<span data-ttu-id="3232c-473">否</span><span class="sxs-lookup"><span data-stu-id="3232c-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-474">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-474">Definition</span></span>

<span data-ttu-id="3232c-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-478">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-478">Keywords</span></span>

<span data-ttu-id="3232c-479">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-479">| |</span></span>
|<span data-ttu-id="3232c-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-481">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-481">passport number</span></span>  <br/> <span data-ttu-id="3232c-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-482">romanian passport number</span></span>  <br/> <span data-ttu-id="3232c-483">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-483">passport no</span></span>  <br/> <span data-ttu-id="3232c-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="3232c-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3232c-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="3232c-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3232c-486">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-486">Format</span></span>

<span data-ttu-id="3232c-487">一个数字或字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-488">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-488">Pattern</span></span>

<span data-ttu-id="3232c-489">一个数字或字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3232c-490">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-490">Checksum</span></span>

<span data-ttu-id="3232c-491">否</span><span class="sxs-lookup"><span data-stu-id="3232c-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-492">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-492">Definition</span></span>

<span data-ttu-id="3232c-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-496">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-496">Keywords</span></span>

<span data-ttu-id="3232c-497">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-497">| |</span></span>
|<span data-ttu-id="3232c-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-499">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-499">passport number</span></span>  <br/> <span data-ttu-id="3232c-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="3232c-501">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-501">passport no</span></span>  <br/> <span data-ttu-id="3232c-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="3232c-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3232c-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="3232c-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3232c-504">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-504">Format</span></span>

<span data-ttu-id="3232c-505">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-506">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-506">Pattern</span></span>

<span data-ttu-id="3232c-507">两个字母后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="3232c-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="3232c-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="3232c-508">The letter "P"</span></span>
    
- <span data-ttu-id="3232c-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="3232c-509">One uppercase letter</span></span>
    
- <span data-ttu-id="3232c-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-511">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-511">Checksum</span></span>

<span data-ttu-id="3232c-512">否</span><span class="sxs-lookup"><span data-stu-id="3232c-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-513">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-513">Definition</span></span>

<span data-ttu-id="3232c-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-517">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-517">Keywords</span></span>

<span data-ttu-id="3232c-518">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-518">| |</span></span>
|<span data-ttu-id="3232c-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-520">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-520">passport number</span></span>  <br/> <span data-ttu-id="3232c-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="3232c-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="3232c-522">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-522">passport no</span></span>  <br/> <span data-ttu-id="3232c-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="3232c-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3232c-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="3232c-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3232c-525">Format</span><span class="sxs-lookup"><span data-stu-id="3232c-525">Format</span></span>

<span data-ttu-id="3232c-526">八个或九个字符的字母和数字的组合，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="3232c-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3232c-527">模式</span><span class="sxs-lookup"><span data-stu-id="3232c-527">Pattern</span></span>

<span data-ttu-id="3232c-528">字母和数字的八个或九个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="3232c-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="3232c-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="3232c-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="3232c-530">一个数字或字母（可选）</span><span class="sxs-lookup"><span data-stu-id="3232c-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="3232c-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="3232c-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3232c-532">校验和</span><span class="sxs-lookup"><span data-stu-id="3232c-532">Checksum</span></span>

<span data-ttu-id="3232c-533">不适用</span><span class="sxs-lookup"><span data-stu-id="3232c-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="3232c-534">定义</span><span class="sxs-lookup"><span data-stu-id="3232c-534">Definition</span></span>

<span data-ttu-id="3232c-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="3232c-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3232c-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="3232c-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3232c-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="3232c-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3232c-538">关键字</span><span class="sxs-lookup"><span data-stu-id="3232c-538">Keywords</span></span>

<span data-ttu-id="3232c-539">| |</span><span class="sxs-lookup"><span data-stu-id="3232c-539">| |</span></span>
|<span data-ttu-id="3232c-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="3232c-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="3232c-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="3232c-541">passport</span></span>  <br/> <span data-ttu-id="3232c-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="3232c-542">spain passport</span></span>  <br/> <span data-ttu-id="3232c-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="3232c-543">passport book</span></span>  <br/> <span data-ttu-id="3232c-544">passport number</span><span class="sxs-lookup"><span data-stu-id="3232c-544">passport number</span></span>  <br/> <span data-ttu-id="3232c-545">护照号</span><span class="sxs-lookup"><span data-stu-id="3232c-545">passport no</span></span>  <br/> <span data-ttu-id="3232c-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="3232c-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="3232c-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="3232c-547">número pasaporte</span></span>  <br/> <span data-ttu-id="3232c-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="3232c-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="3232c-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="3232c-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3232c-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="3232c-550">Sweden</span></span>

<span data-ttu-id="3232c-551">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="3232c-552">英国</span><span class="sxs-lookup"><span data-stu-id="3232c-552">UK</span></span>

<span data-ttu-id="3232c-553">有关详细信息，请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="3232c-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="3232c-554">"Passport 号码"，在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="3232c-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3232c-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3232c-555">See also</span></span>

[<span data-ttu-id="3232c-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="3232c-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

