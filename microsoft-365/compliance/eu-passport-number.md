---
title: EU 护照号码
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
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805945"
---
# <a name="eu-passport-number"></a><span data-ttu-id="c4b3b-104">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-104">EU Passport Number</span></span>

<span data-ttu-id="c4b3b-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟护照号敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="c4b3b-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c4b3b-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="c4b3b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-108">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-108">Format</span></span>

<span data-ttu-id="c4b3b-109">一个字母后跟一个可选空格和七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-110">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-110">Pattern</span></span>

<span data-ttu-id="c4b3b-111">一个字母、七个数字和一个空格的组合：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="c4b3b-112">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="c4b3b-113">一个空格（可选）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-113">One space (optional)</span></span>
    
- <span data-ttu-id="c4b3b-114">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-115">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-115">Checksum</span></span>

<span data-ttu-id="c4b3b-116">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-117">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-117">Definition</span></span>

<span data-ttu-id="c4b3b-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-119">正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-120">找到了中`Keywords_austria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-121">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-121">Keywords</span></span>

<span data-ttu-id="c4b3b-122">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-122"></span></span>
|<span data-ttu-id="c4b3b-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-124">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-124">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-125">奥地利护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-125">austrian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-126">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-126">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="c4b3b-127">reisepass</span></span>  <br/> <span data-ttu-id="c4b3b-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="c4b3b-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="c4b3b-129">比利时</span><span class="sxs-lookup"><span data-stu-id="c4b3b-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-130">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-130">Format</span></span>

<span data-ttu-id="c4b3b-131">两个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-132">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-132">Pattern</span></span>

<span data-ttu-id="c4b3b-133">两个字母，后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-134">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-134">Checksum</span></span>

<span data-ttu-id="c4b3b-135">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-136">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-136">Definition</span></span>

<span data-ttu-id="c4b3b-137">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-138">正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-139">找到了中`Keywords_belgium_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-140">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-140">Keywords</span></span>

<span data-ttu-id="c4b3b-141">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-141"></span></span>
|<span data-ttu-id="c4b3b-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-143">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-143">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-144">比利时护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-144">belgian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-145">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-145">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="c4b3b-146">paspoort</span></span>  <br/> <span data-ttu-id="c4b3b-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="c4b3b-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="c4b3b-148">reisepass kein</span></span>  <br/> <span data-ttu-id="c4b3b-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="c4b3b-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="c4b3b-150">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="c4b3b-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-151">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-151">Format</span></span>

<span data-ttu-id="c4b3b-152">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-153">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-153">Pattern</span></span>

 <span data-ttu-id="c4b3b-154">九个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-155">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-155">Checksum</span></span>

<span data-ttu-id="c4b3b-156">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-157">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-157">Definition</span></span>

<span data-ttu-id="c4b3b-158">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-159">正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-160">找到了中`Keywords_bulgaria_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-161">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-161">Keywords</span></span>

<span data-ttu-id="c4b3b-162">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-162"></span></span>
|<span data-ttu-id="c4b3b-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-164">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-164">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-165">保加利亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-166">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-166">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="c4b3b-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="c4b3b-168">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="c4b3b-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-169">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-169">Format</span></span>

<span data-ttu-id="c4b3b-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-171">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-171">Pattern</span></span>

 <span data-ttu-id="c4b3b-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-173">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-173">Checksum</span></span>

<span data-ttu-id="c4b3b-174">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-175">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-175">Definition</span></span>

<span data-ttu-id="c4b3b-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-177">正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-178">找到了中`Keywords_croatia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-179">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-179">Keywords</span></span>

<span data-ttu-id="c4b3b-180">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-180"></span></span>
|<span data-ttu-id="c4b3b-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-182">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-182">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-183">克罗地亚护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-183">croatian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-184">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-184">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="c4b3b-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="c4b3b-186">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="c4b3b-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-187">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-187">Format</span></span>

<span data-ttu-id="c4b3b-188">一个字母后跟6-8 个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-189">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-189">Pattern</span></span>

<span data-ttu-id="c4b3b-190">一个字母后跟6到8个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-191">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-191">Checksum</span></span>

<span data-ttu-id="c4b3b-192">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-193">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-193">Definition</span></span>

<span data-ttu-id="c4b3b-194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-195">正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-196">找到了中`Keywords_cyprus_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-197">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-197">Keywords</span></span>

<span data-ttu-id="c4b3b-198">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-198"></span></span>
|<span data-ttu-id="c4b3b-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-200">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-200">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-201">塞浦路斯护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="c4b3b-202">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-202">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="c4b3b-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="c4b3b-204">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="c4b3b-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-205">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-205">Format</span></span>

<span data-ttu-id="c4b3b-206">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-207">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-207">Pattern</span></span>

<span data-ttu-id="c4b3b-208">8位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-209">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-209">Checksum</span></span>

<span data-ttu-id="c4b3b-210">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-211">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-211">Definition</span></span>

<span data-ttu-id="c4b3b-212">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-213">正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-214">找到了中`Keywords_czech_republic_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-215">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-215">Keywords</span></span>

<span data-ttu-id="c4b3b-216">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-216"></span></span>
|<span data-ttu-id="c4b3b-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-218">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-218">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-219">捷克语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-219">czech passport number</span></span>  <br/> <span data-ttu-id="c4b3b-220">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-220">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="c4b3b-221">cestovní pas</span></span>  <br/> <span data-ttu-id="c4b3b-222">pas</span><span class="sxs-lookup"><span data-stu-id="c4b3b-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="c4b3b-223">丹麦</span><span class="sxs-lookup"><span data-stu-id="c4b3b-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-224">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-224">Format</span></span>

<span data-ttu-id="c4b3b-225">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-226">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-226">Pattern</span></span>

 <span data-ttu-id="c4b3b-227">九个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-228">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-228">Checksum</span></span>

<span data-ttu-id="c4b3b-229">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-230">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-230">Definition</span></span>

<span data-ttu-id="c4b3b-231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-232">正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-233">找到了中`Keywords_denmark_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-234">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-234">Keywords</span></span>

<span data-ttu-id="c4b3b-235">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-235"></span></span>
|<span data-ttu-id="c4b3b-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-237">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-237">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-238">丹麦护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-238">danish passport number</span></span>  <br/> <span data-ttu-id="c4b3b-239">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-239">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-240">pas</span><span class="sxs-lookup"><span data-stu-id="c4b3b-240">pas</span></span>  <br/> <span data-ttu-id="c4b3b-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="c4b3b-242">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="c4b3b-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-243">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-243">Format</span></span>

<span data-ttu-id="c4b3b-244">一个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-245">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-245">Pattern</span></span>

<span data-ttu-id="c4b3b-246">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-247">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-247">Checksum</span></span>

<span data-ttu-id="c4b3b-248">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-249">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-249">Definition</span></span>

<span data-ttu-id="c4b3b-250">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-251">正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-252">找到了中`Keywords_estonia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-253">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-253">Keywords</span></span>

<span data-ttu-id="c4b3b-254">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-254"></span></span>
|<span data-ttu-id="c4b3b-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-256">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-256">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-257">爱沙尼亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-257">estonian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-258">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-258">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="c4b3b-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="c4b3b-260">芬兰</span><span class="sxs-lookup"><span data-stu-id="c4b3b-260">Finland</span></span>

<span data-ttu-id="c4b3b-261">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="c4b3b-262">法国</span><span class="sxs-lookup"><span data-stu-id="c4b3b-262">France</span></span>

<span data-ttu-id="c4b3b-263">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="c4b3b-264">德国</span><span class="sxs-lookup"><span data-stu-id="c4b3b-264">Germany</span></span>

<span data-ttu-id="c4b3b-265">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="c4b3b-266">希腊</span><span class="sxs-lookup"><span data-stu-id="c4b3b-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-267">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-267">Format</span></span>

<span data-ttu-id="c4b3b-268">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-269">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-269">Pattern</span></span>

<span data-ttu-id="c4b3b-270">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-271">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-271">Checksum</span></span>

<span data-ttu-id="c4b3b-272">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-273">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-273">Definition</span></span>

<span data-ttu-id="c4b3b-274">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-275">正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-276">找到了中`Keywords_greece_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-277">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-277">Keywords</span></span>

<span data-ttu-id="c4b3b-278">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-278"></span></span>
|<span data-ttu-id="c4b3b-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-280">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-280">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-281">希腊护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-281">greek passport number</span></span>  <br/> <span data-ttu-id="c4b3b-282">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-282">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="c4b3b-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="c4b3b-284">匈牙利</span><span class="sxs-lookup"><span data-stu-id="c4b3b-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-285">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-285">Format</span></span>

<span data-ttu-id="c4b3b-286">两个字母后跟6个或7个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-287">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-287">Pattern</span></span>

<span data-ttu-id="c4b3b-288">两个字母后跟六个或七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-289">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-289">Checksum</span></span>

<span data-ttu-id="c4b3b-290">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-291">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-291">Definition</span></span>

<span data-ttu-id="c4b3b-292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-293">正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-294">找到了中`Keywords_hungary_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-295">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-295">Keywords</span></span>

<span data-ttu-id="c4b3b-296">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-296"></span></span>
|<span data-ttu-id="c4b3b-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-298">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-298">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-299">匈牙利语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-300">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-300">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="c4b3b-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="c4b3b-302">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="c4b3b-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-303">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-303">Format</span></span>

<span data-ttu-id="c4b3b-304">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-305">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-305">Pattern</span></span>

<span data-ttu-id="c4b3b-306">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c4b3b-307">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c4b3b-308">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-309">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-309">Checksum</span></span>

<span data-ttu-id="c4b3b-310">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-311">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-311">Definition</span></span>

<span data-ttu-id="c4b3b-312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-313">正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-314">找到了中`Keywords_ireland_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-315">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-315">Keywords</span></span>

<span data-ttu-id="c4b3b-316">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-316"></span></span>
|<span data-ttu-id="c4b3b-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-318">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-318">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-319">爱尔兰护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-319">irish passport number</span></span>  <br/> <span data-ttu-id="c4b3b-320">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-320">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-321">pas</span><span class="sxs-lookup"><span data-stu-id="c4b3b-321">pas</span></span>  <br/> <span data-ttu-id="c4b3b-322">登记卡</span><span class="sxs-lookup"><span data-stu-id="c4b3b-322">passport</span></span>  <br/> <span data-ttu-id="c4b3b-323">passeport</span><span class="sxs-lookup"><span data-stu-id="c4b3b-323">passeport</span></span>  <br/> <span data-ttu-id="c4b3b-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="c4b3b-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="c4b3b-325">意大利</span><span class="sxs-lookup"><span data-stu-id="c4b3b-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-326">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-326">Format</span></span>

<span data-ttu-id="c4b3b-327">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-328">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-328">Pattern</span></span>

<span data-ttu-id="c4b3b-329">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c4b3b-330">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c4b3b-331">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-332">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-332">Checksum</span></span>

<span data-ttu-id="c4b3b-333">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-334">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-334">Definition</span></span>

<span data-ttu-id="c4b3b-335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-336">正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-337">找到了中`Keywords_italy_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-338">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-338">Keywords</span></span>

<span data-ttu-id="c4b3b-339">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-339"></span></span>
|<span data-ttu-id="c4b3b-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-341">意大利护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-341">italian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="c4b3b-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="c4b3b-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="c4b3b-343">passaporto</span></span>  <br/> <span data-ttu-id="c4b3b-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="c4b3b-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="c4b3b-345">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-345">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="c4b3b-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="c4b3b-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="c4b3b-347">passaporto numero</span></span>  <br/> <span data-ttu-id="c4b3b-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="c4b3b-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="c4b3b-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="c4b3b-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="c4b3b-350">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="c4b3b-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-351">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-351">Format</span></span>

<span data-ttu-id="c4b3b-352">两个字母或数字后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-353">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-353">Pattern</span></span>

<span data-ttu-id="c4b3b-354">两个字母或数字，后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c4b3b-355">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c4b3b-356">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-357">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-357">Checksum</span></span>

<span data-ttu-id="c4b3b-358">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-359">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-359">Definition</span></span>

<span data-ttu-id="c4b3b-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-361">正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-362">找到了中`Keywords_latvia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-363">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-363">Keywords</span></span>

<span data-ttu-id="c4b3b-364">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-364"></span></span>
|<span data-ttu-id="c4b3b-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-366">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-366">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-367">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-367">latvian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-368">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-368">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="c4b3b-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="c4b3b-370">立陶宛</span><span class="sxs-lookup"><span data-stu-id="c4b3b-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-371">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-371">Format</span></span>

<span data-ttu-id="c4b3b-372">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-373">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-373">Pattern</span></span>

<span data-ttu-id="c4b3b-374">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-375">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-375">Checksum</span></span>

<span data-ttu-id="c4b3b-376">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-377">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-377">Definition</span></span>

<span data-ttu-id="c4b3b-378">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-379">正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-380">找到了中`Keywords_lithuania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-381">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-381">Keywords</span></span>

<span data-ttu-id="c4b3b-382">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-382"></span></span>
|<span data-ttu-id="c4b3b-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-384">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-384">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-385">lithunian 护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-386">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-386">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="c4b3b-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="c4b3b-388">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="c4b3b-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-389">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-389">Format</span></span>

<span data-ttu-id="c4b3b-390">八个数字或字母不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-391">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-391">Pattern</span></span>

<span data-ttu-id="c4b3b-392">八个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-393">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-393">Checksum</span></span>

<span data-ttu-id="c4b3b-394">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-395">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-395">Definition</span></span>

<span data-ttu-id="c4b3b-396">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-397">正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-398">找到了中`Keywords_nation_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-399">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-399">Keywords</span></span>

<span data-ttu-id="c4b3b-400">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-400"></span></span>
|<span data-ttu-id="c4b3b-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-402">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-402">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-403">拉脱维亚语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-403">latvian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-404">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-404">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="c4b3b-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="c4b3b-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-407">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-407">Format</span></span>

<span data-ttu-id="c4b3b-408">七位数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-409">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-409">Pattern</span></span>

 <span data-ttu-id="c4b3b-410">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-411">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-411">Checksum</span></span>

<span data-ttu-id="c4b3b-412">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-413">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-413">Definition</span></span>

<span data-ttu-id="c4b3b-414">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-415">正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-416">找到了中`Keywords_malta_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-417">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-417">Keywords</span></span>

<span data-ttu-id="c4b3b-418">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-418"></span></span>
|<span data-ttu-id="c4b3b-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-420">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-420">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-421">马耳他护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-421">maltese passport number</span></span>  <br/> <span data-ttu-id="c4b3b-422">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-422">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="c4b3b-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="c4b3b-424">荷兰</span><span class="sxs-lookup"><span data-stu-id="c4b3b-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-425">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-425">Format</span></span>

<span data-ttu-id="c4b3b-426">九个字母或数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-427">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-427">Pattern</span></span>

<span data-ttu-id="c4b3b-428">九个字母或数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-429">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-429">Checksum</span></span>

<span data-ttu-id="c4b3b-430">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-431">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-431">Definition</span></span>

<span data-ttu-id="c4b3b-432">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-433">正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-434">找到了中`Keywords_netherlands_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-435">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-435">Keywords</span></span>

<span data-ttu-id="c4b3b-436">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-436"></span></span>
|<span data-ttu-id="c4b3b-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-438">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-438">dutch passport number</span></span>  <br/> <span data-ttu-id="c4b3b-439">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-439">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-440">荷兰护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="c4b3b-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="c4b3b-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="c4b3b-442">paspoort</span></span>  <br/> <span data-ttu-id="c4b3b-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="c4b3b-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c4b3b-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="c4b3b-445">波兰</span><span class="sxs-lookup"><span data-stu-id="c4b3b-445">Poland</span></span>

<span data-ttu-id="c4b3b-446">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="c4b3b-447">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="c4b3b-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-448">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-448">Format</span></span>

<span data-ttu-id="c4b3b-449">一个字母后跟六个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-450">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-450">Pattern</span></span>

<span data-ttu-id="c4b3b-451">一个字母后跟六个数字：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="c4b3b-452">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="c4b3b-453">六个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-454">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-454">Checksum</span></span>

<span data-ttu-id="c4b3b-455">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-456">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-456">Definition</span></span>

<span data-ttu-id="c4b3b-457">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-458">正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-459">找到了中`Keywords_portugal_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-460">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-460">Keywords</span></span>

<span data-ttu-id="c4b3b-461">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-461"></span></span>
|<span data-ttu-id="c4b3b-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-463">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-463">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-464">葡萄牙语护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="c4b3b-465">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-465">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="c4b3b-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="c4b3b-467">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="c4b3b-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-468">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-468">Format</span></span>

<span data-ttu-id="c4b3b-469">八个或9个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-470">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-470">Pattern</span></span>

<span data-ttu-id="c4b3b-471">8或9个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-472">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-472">Checksum</span></span>

<span data-ttu-id="c4b3b-473">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-474">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-474">Definition</span></span>

<span data-ttu-id="c4b3b-475">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-476">正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-477">找到了中`Keywords_romania_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-478">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-478">Keywords</span></span>

<span data-ttu-id="c4b3b-479">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-479"></span></span>
|<span data-ttu-id="c4b3b-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-481">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-481">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-482">罗马尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-482">romanian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-483">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-483">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="c4b3b-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="c4b3b-485">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="c4b3b-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-486">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-486">Format</span></span>

<span data-ttu-id="c4b3b-487">一个数字或字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-488">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-488">Pattern</span></span>

<span data-ttu-id="c4b3b-489">一个数字或字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c4b3b-490">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-490">Checksum</span></span>

<span data-ttu-id="c4b3b-491">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-492">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-492">Definition</span></span>

<span data-ttu-id="c4b3b-493">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-494">正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-495">找到了中`Keywords_slovakia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-496">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-496">Keywords</span></span>

<span data-ttu-id="c4b3b-497">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-497"></span></span>
|<span data-ttu-id="c4b3b-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-499">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-499">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-500">斯洛伐克护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-501">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-501">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-502">číslo pasu</span><span class="sxs-lookup"><span data-stu-id="c4b3b-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="c4b3b-503">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="c4b3b-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-504">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-504">Format</span></span>

<span data-ttu-id="c4b3b-505">两个字母后跟七个数字，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-506">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-506">Pattern</span></span>

<span data-ttu-id="c4b3b-507">两个字母后跟七个数字：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="c4b3b-508">字母 "P"</span><span class="sxs-lookup"><span data-stu-id="c4b3b-508">The letter "P"</span></span>
    
- <span data-ttu-id="c4b3b-509">一个大写字母</span><span class="sxs-lookup"><span data-stu-id="c4b3b-509">One uppercase letter</span></span>
    
- <span data-ttu-id="c4b3b-510">七个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-511">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-511">Checksum</span></span>

<span data-ttu-id="c4b3b-512">否</span><span class="sxs-lookup"><span data-stu-id="c4b3b-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-513">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-513">Definition</span></span>

<span data-ttu-id="c4b3b-514">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-515">正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-516">找到了中`Keywords_slovenia_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-517">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-517">Keywords</span></span>

<span data-ttu-id="c4b3b-518">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-518"></span></span>
|<span data-ttu-id="c4b3b-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-520">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-520">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-521">斯洛文尼亚护照号码</span><span class="sxs-lookup"><span data-stu-id="c4b3b-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="c4b3b-522">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-522">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="c4b3b-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="c4b3b-524">西班牙</span><span class="sxs-lookup"><span data-stu-id="c4b3b-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c4b3b-525">Format</span><span class="sxs-lookup"><span data-stu-id="c4b3b-525">Format</span></span>

<span data-ttu-id="c4b3b-526">八个或九个字符的字母和数字的组合，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="c4b3b-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c4b3b-527">模式</span><span class="sxs-lookup"><span data-stu-id="c4b3b-527">Pattern</span></span>

<span data-ttu-id="c4b3b-528">字母和数字的八个或九个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="c4b3b-529">两位数字或字母</span><span class="sxs-lookup"><span data-stu-id="c4b3b-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="c4b3b-530">一个数字或字母（可选）</span><span class="sxs-lookup"><span data-stu-id="c4b3b-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="c4b3b-531">六个数字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c4b3b-532">校验和</span><span class="sxs-lookup"><span data-stu-id="c4b3b-532">Checksum</span></span>

<span data-ttu-id="c4b3b-533">不适用</span><span class="sxs-lookup"><span data-stu-id="c4b3b-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c4b3b-534">定义</span><span class="sxs-lookup"><span data-stu-id="c4b3b-534">Definition</span></span>

<span data-ttu-id="c4b3b-535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="c4b3b-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c4b3b-536">正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c4b3b-537">找到了中`Keywords_spain_eu_passport_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c4b3b-538">关键字</span><span class="sxs-lookup"><span data-stu-id="c4b3b-538">Keywords</span></span>

<span data-ttu-id="c4b3b-539">| |</span><span class="sxs-lookup"><span data-stu-id="c4b3b-539"></span></span>
|<span data-ttu-id="c4b3b-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c4b3b-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c4b3b-541">登记卡</span><span class="sxs-lookup"><span data-stu-id="c4b3b-541">passport</span></span>  <br/> <span data-ttu-id="c4b3b-542">西班牙护照</span><span class="sxs-lookup"><span data-stu-id="c4b3b-542">spain passport</span></span>  <br/> <span data-ttu-id="c4b3b-543">护照书籍</span><span class="sxs-lookup"><span data-stu-id="c4b3b-543">passport book</span></span>  <br/> <span data-ttu-id="c4b3b-544">passport number</span><span class="sxs-lookup"><span data-stu-id="c4b3b-544">passport number</span></span>  <br/> <span data-ttu-id="c4b3b-545">护照号</span><span class="sxs-lookup"><span data-stu-id="c4b3b-545">passport no</span></span>  <br/> <span data-ttu-id="c4b3b-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="c4b3b-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="c4b3b-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="c4b3b-547">número pasaporte</span></span>  <br/> <span data-ttu-id="c4b3b-548">西班牙 pasaporte</span><span class="sxs-lookup"><span data-stu-id="c4b3b-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="c4b3b-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="c4b3b-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="c4b3b-550">瑞典</span><span class="sxs-lookup"><span data-stu-id="c4b3b-550">Sweden</span></span>

<span data-ttu-id="c4b3b-551">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="c4b3b-552">英国</span><span class="sxs-lookup"><span data-stu-id="c4b3b-552">UK</span></span>

<span data-ttu-id="c4b3b-553">有关详细信息，请参阅 "美国/英国" 一节。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="c4b3b-554">"Passport 号码"，在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。</span><span class="sxs-lookup"><span data-stu-id="c4b3b-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4b3b-555">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b3b-555">See also</span></span>

[<span data-ttu-id="c4b3b-556">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="c4b3b-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

