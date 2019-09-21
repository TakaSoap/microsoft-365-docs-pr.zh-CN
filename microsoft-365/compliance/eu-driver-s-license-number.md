---
title: 欧盟驾驶执照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟驱动程序的敏感信息类型时，应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37074880"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="d76f9-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-104">EU Driver's License Number</span></span>

<span data-ttu-id="d76f9-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟驱动程序的敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="d76f9-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="d76f9-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d76f9-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="d76f9-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-108">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-108">Format</span></span>

<span data-ttu-id="d76f9-109">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-110">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-110">Pattern</span></span>

<span data-ttu-id="d76f9-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-112">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-112">Checksum</span></span>

<span data-ttu-id="d76f9-113">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-114">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-114">Definition</span></span>

<span data-ttu-id="d76f9-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="d76f9-118">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-118">Keywords</span></span>

<span data-ttu-id="d76f9-119">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-119"></span></span>
|<span data-ttu-id="d76f9-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-121">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-121">dl#</span></span>  <br/> <span data-ttu-id="d76f9-122">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-122">driver license</span></span>  <br/> <span data-ttu-id="d76f9-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-123">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-124">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-125">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-126">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-127">driver's licence</span></span>  <br/> <span data-ttu-id="d76f9-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-128">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-129">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="d76f9-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-131">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-132">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="d76f9-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="d76f9-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="d76f9-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="d76f9-135">比利时</span><span class="sxs-lookup"><span data-stu-id="d76f9-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-136">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-136">Format</span></span>

<span data-ttu-id="d76f9-137">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-138">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-138">Pattern</span></span>

<span data-ttu-id="d76f9-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-140">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-140">Checksum</span></span>

<span data-ttu-id="d76f9-141">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-142">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-142">Definition</span></span>

<span data-ttu-id="d76f9-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="d76f9-146">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-146">Keywords</span></span>

<span data-ttu-id="d76f9-147">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-147"></span></span>
|<span data-ttu-id="d76f9-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-149">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-149">dl#</span></span>  <br/> <span data-ttu-id="d76f9-150">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-150">driver license</span></span>  <br/> <span data-ttu-id="d76f9-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-151">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-152">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-153">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-154">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-155">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-156">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-157">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-158">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-159">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="d76f9-160">rijbewijs</span></span>  <br/> <span data-ttu-id="d76f9-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="d76f9-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="d76f9-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="d76f9-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="d76f9-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="d76f9-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="d76f9-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="d76f9-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="d76f9-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="d76f9-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="d76f9-168">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="d76f9-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-169">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-169">Format</span></span>

<span data-ttu-id="d76f9-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-171">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-171">Pattern</span></span>

<span data-ttu-id="d76f9-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-173">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-173">Checksum</span></span>

<span data-ttu-id="d76f9-174">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-175">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-175">Definition</span></span>

<span data-ttu-id="d76f9-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="d76f9-179">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-179">Keywords</span></span>

<span data-ttu-id="d76f9-180">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-180"></span></span>
|<span data-ttu-id="d76f9-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-182">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-182">dl#</span></span>  <br/> <span data-ttu-id="d76f9-183">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-183">driver license</span></span>  <br/> <span data-ttu-id="d76f9-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-184">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-185">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-186">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-187">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-188">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-189">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-190">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-191">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-192">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-193">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="d76f9-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="d76f9-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="d76f9-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="d76f9-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="d76f9-196">сумпс</span></span>  <br/> <span data-ttu-id="d76f9-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="d76f9-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="d76f9-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="d76f9-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-199">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-199">Format</span></span>

<span data-ttu-id="d76f9-200">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-201">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-201">Pattern</span></span>

<span data-ttu-id="d76f9-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-203">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-203">Checksum</span></span>

<span data-ttu-id="d76f9-204">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-205">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-205">Definition</span></span>

<span data-ttu-id="d76f9-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="d76f9-209">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-209">Keywords</span></span>

<span data-ttu-id="d76f9-210">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-210"></span></span>
|<span data-ttu-id="d76f9-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-212">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-212">dl#</span></span>  <br/> <span data-ttu-id="d76f9-213">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-213">driver license</span></span>  <br/> <span data-ttu-id="d76f9-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-214">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-215">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-216">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-217">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-218">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-219">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-220">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-221">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-222">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-223">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="d76f9-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="d76f9-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="d76f9-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-226">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-226">Format</span></span>

<span data-ttu-id="d76f9-227">12个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-228">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-228">Pattern</span></span>

<span data-ttu-id="d76f9-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-230">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-230">Checksum</span></span>

<span data-ttu-id="d76f9-231">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-232">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-232">Definition</span></span>

<span data-ttu-id="d76f9-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-236">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-236">Keywords</span></span>

<span data-ttu-id="d76f9-237">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-237"></span></span>
|<span data-ttu-id="d76f9-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-239">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-239">dl#</span></span>  <br/> <span data-ttu-id="d76f9-240">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-240">driver license</span></span>  <br/> <span data-ttu-id="d76f9-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-241">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-242">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-243">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-244">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-245">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-246">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-247">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-248">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-249">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="d76f9-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="d76f9-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="d76f9-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-252">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-252">Format</span></span>

<span data-ttu-id="d76f9-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-254">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-254">Pattern</span></span>

<span data-ttu-id="d76f9-255">八个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="d76f9-256">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="d76f9-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="d76f9-257">A space (optional)</span></span>
    
- <span data-ttu-id="d76f9-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-259">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-259">Checksum</span></span>

<span data-ttu-id="d76f9-260">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-261">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-261">Definition</span></span>

<span data-ttu-id="d76f9-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="d76f9-265">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-265">Keywords</span></span>

<span data-ttu-id="d76f9-266">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-266"></span></span>
|<span data-ttu-id="d76f9-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-268">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-268">dl#</span></span>  <br/> <span data-ttu-id="d76f9-269">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-269">driver license</span></span>  <br/> <span data-ttu-id="d76f9-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-270">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-271">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-272">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-273">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-274">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-275">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-276">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-277">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-278">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-279">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-280">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="d76f9-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="d76f9-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="d76f9-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-283">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-283">Format</span></span>

<span data-ttu-id="d76f9-284">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-285">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-285">Pattern</span></span>

<span data-ttu-id="d76f9-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-287">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-287">Checksum</span></span>

<span data-ttu-id="d76f9-288">是</span><span class="sxs-lookup"><span data-stu-id="d76f9-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-289">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-289">Definition</span></span>

<span data-ttu-id="d76f9-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="d76f9-293">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-293">Keywords</span></span>

<span data-ttu-id="d76f9-294">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-294"></span></span>
|<span data-ttu-id="d76f9-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-296">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-296">dl#</span></span>  <br/> <span data-ttu-id="d76f9-297">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-297">driver license</span></span>  <br/> <span data-ttu-id="d76f9-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-298">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-299">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-300">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-301">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-302">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-303">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-304">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-305">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-306">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-307">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="d76f9-308">kørekort</span></span>  <br/> <span data-ttu-id="d76f9-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="d76f9-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="d76f9-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-311">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-311">Format</span></span>

<span data-ttu-id="d76f9-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-313">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-313">Pattern</span></span>

<span data-ttu-id="d76f9-314">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="d76f9-315">字母 "ET" （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="d76f9-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-317">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-317">Checksum</span></span>

<span data-ttu-id="d76f9-318">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-319">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-319">Definition</span></span>

<span data-ttu-id="d76f9-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-323">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-323">Keywords</span></span>

<span data-ttu-id="d76f9-324">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-324"></span></span>
|<span data-ttu-id="d76f9-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-326">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-326">dl#</span></span>  <br/> <span data-ttu-id="d76f9-327">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-327">driver license</span></span>  <br/> <span data-ttu-id="d76f9-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-328">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-329">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-330">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-331">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-332">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-333">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-334">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-335">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-336">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-337">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="d76f9-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="d76f9-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="d76f9-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-340">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-340">Format</span></span>

<span data-ttu-id="d76f9-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="d76f9-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-342">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-342">Pattern</span></span>

<span data-ttu-id="d76f9-343">10个数字，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="d76f9-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="d76f9-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-344">Six digits</span></span> 
    
- <span data-ttu-id="d76f9-345">一个连字符</span><span class="sxs-lookup"><span data-stu-id="d76f9-345">A hyphen</span></span>
    
-  <span data-ttu-id="d76f9-346">四个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="d76f9-347">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-347">Checksum</span></span>

<span data-ttu-id="d76f9-348">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-349">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-349">Definition</span></span>

<span data-ttu-id="d76f9-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-353">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-353">Keywords</span></span>

<span data-ttu-id="d76f9-354">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-354"></span></span>
|<span data-ttu-id="d76f9-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-356">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-356">dl#</span></span>  <br/> <span data-ttu-id="d76f9-357">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-357">driver license</span></span>  <br/> <span data-ttu-id="d76f9-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-358">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-359">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-360">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-361">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-362">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-363">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-364">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-365">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-366">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-367">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="d76f9-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="d76f9-369">法国</span><span class="sxs-lookup"><span data-stu-id="d76f9-369">France</span></span>

<span data-ttu-id="d76f9-370">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d76f9-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d76f9-371">德国</span><span class="sxs-lookup"><span data-stu-id="d76f9-371">Germany</span></span>

<span data-ttu-id="d76f9-372">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d76f9-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d76f9-373">希腊</span><span class="sxs-lookup"><span data-stu-id="d76f9-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-374">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-374">Format</span></span>

<span data-ttu-id="d76f9-375">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-376">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-376">Pattern</span></span>

 <span data-ttu-id="d76f9-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d76f9-378">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-378">Checksum</span></span>

<span data-ttu-id="d76f9-379">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-380">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-380">Definition</span></span>

<span data-ttu-id="d76f9-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-384">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-384">Keywords</span></span>

<span data-ttu-id="d76f9-385">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-385"></span></span>
|<span data-ttu-id="d76f9-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="d76f9-387">dlL#</span></span>  <br/> <span data-ttu-id="d76f9-388">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-388">driver license</span></span>  <br/> <span data-ttu-id="d76f9-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-389">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-390">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-391">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-392">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-393">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-394">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-395">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-396">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-397">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-398">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="d76f9-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="d76f9-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="d76f9-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="d76f9-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="d76f9-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-402">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-402">Format</span></span>

<span data-ttu-id="d76f9-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-404">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-404">Pattern</span></span>

<span data-ttu-id="d76f9-405">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="d76f9-406">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="d76f9-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-408">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-408">Checksum</span></span>

<span data-ttu-id="d76f9-409">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-410">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-410">Definition</span></span>

<span data-ttu-id="d76f9-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-414">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-414">Keywords</span></span>

<span data-ttu-id="d76f9-415">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-415"></span></span>
|<span data-ttu-id="d76f9-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-417">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-417">dl#</span></span>  <br/> <span data-ttu-id="d76f9-418">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-418">driver license</span></span>  <br/> <span data-ttu-id="d76f9-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-419">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-420">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-421">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-422">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-423">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-424">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-425">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-426">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-427">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-428">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="d76f9-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="d76f9-430">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="d76f9-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-431">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-431">Format</span></span>

<span data-ttu-id="d76f9-432">6位数，后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="d76f9-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-433">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-433">Pattern</span></span>

<span data-ttu-id="d76f9-434">6位数字和四个字母：</span><span class="sxs-lookup"><span data-stu-id="d76f9-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="d76f9-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-435">Six digits</span></span>
    
- <span data-ttu-id="d76f9-436">四个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-437">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-437">Checksum</span></span>

<span data-ttu-id="d76f9-438">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-439">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-439">Definition</span></span>

<span data-ttu-id="d76f9-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-443">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-443">Keywords</span></span>

<span data-ttu-id="d76f9-444">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-444"></span></span>
|<span data-ttu-id="d76f9-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-446">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-446">dl#</span></span>  <br/> <span data-ttu-id="d76f9-447">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-447">driver license</span></span>  <br/> <span data-ttu-id="d76f9-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-448">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-449">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-450">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-451">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-452">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-453">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-454">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-455">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-456">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-457">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="d76f9-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="d76f9-459">意大利</span><span class="sxs-lookup"><span data-stu-id="d76f9-459">Italy</span></span>

<span data-ttu-id="d76f9-460">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d76f9-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="d76f9-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="d76f9-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-462">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-462">Format</span></span>

<span data-ttu-id="d76f9-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-464">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-464">Pattern</span></span>

<span data-ttu-id="d76f9-465">三个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="d76f9-466">三个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="d76f9-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-468">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-468">Checksum</span></span>

<span data-ttu-id="d76f9-469">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-470">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-470">Definition</span></span>

<span data-ttu-id="d76f9-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-474">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-474">Keywords</span></span>

<span data-ttu-id="d76f9-475">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-475"></span></span>
|<span data-ttu-id="d76f9-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-477">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-477">dl#</span></span>  <br/> <span data-ttu-id="d76f9-478">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-478">driver license</span></span>  <br/> <span data-ttu-id="d76f9-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-479">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-480">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-481">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-482">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-483">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-484">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-485">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-486">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-487">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-488">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="d76f9-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="d76f9-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="d76f9-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-491">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-491">Format</span></span>

<span data-ttu-id="d76f9-492">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-493">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-493">Pattern</span></span>

 <span data-ttu-id="d76f9-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d76f9-495">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-495">Checksum</span></span>

<span data-ttu-id="d76f9-496">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-497">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-497">Definition</span></span>

<span data-ttu-id="d76f9-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-501">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-501">Keywords</span></span>

<span data-ttu-id="d76f9-502">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-502"></span></span>
|<span data-ttu-id="d76f9-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-504">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-504">dl#</span></span>  <br/> <span data-ttu-id="d76f9-505">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-505">driver license</span></span>  <br/> <span data-ttu-id="d76f9-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-506">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-507">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-508">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-509">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-510">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-511">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-512">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-513">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-514">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-515">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="d76f9-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="d76f9-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="d76f9-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-518">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-518">Format</span></span>

<span data-ttu-id="d76f9-519">6位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-520">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-520">Pattern</span></span>

 <span data-ttu-id="d76f9-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d76f9-522">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-522">Checksum</span></span>

<span data-ttu-id="d76f9-523">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-524">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-524">Definition</span></span>

<span data-ttu-id="d76f9-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-528">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-528">Keywords</span></span>

<span data-ttu-id="d76f9-529">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-529"></span></span>
|<span data-ttu-id="d76f9-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-531">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-531">dl#</span></span>  <br/> <span data-ttu-id="d76f9-532">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-532">driver license</span></span>  <br/> <span data-ttu-id="d76f9-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-533">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-534">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-535">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-536">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-537">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-538">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-539">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-540">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-541">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-542">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="d76f9-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="d76f9-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="d76f9-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-545">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-545">Format</span></span>

<span data-ttu-id="d76f9-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="d76f9-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-547">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-547">Pattern</span></span>

<span data-ttu-id="d76f9-548">两个字符和六个数字的组合：</span><span class="sxs-lookup"><span data-stu-id="d76f9-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="d76f9-549">两个字符（数字或字母，而不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="d76f9-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="d76f9-550">A space (optional)</span></span>
    
- <span data-ttu-id="d76f9-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="d76f9-551">Three digits</span></span>
    
- <span data-ttu-id="d76f9-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="d76f9-552">A space (optional)</span></span>
    
- <span data-ttu-id="d76f9-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-554">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-554">Checksum</span></span>

<span data-ttu-id="d76f9-555">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-556">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-556">Definition</span></span>

<span data-ttu-id="d76f9-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-560">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-560">Keywords</span></span>

<span data-ttu-id="d76f9-561">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-561"></span></span>
|<span data-ttu-id="d76f9-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-563">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-563">dl#</span></span>  <br/> <span data-ttu-id="d76f9-564">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-564">driver license</span></span>  <br/> <span data-ttu-id="d76f9-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-565">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-566">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-567">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-568">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-569">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-570">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-571">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-572">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-573">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-574">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="d76f9-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="d76f9-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="d76f9-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-577">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-577">Format</span></span>

<span data-ttu-id="d76f9-578">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-579">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-579">Pattern</span></span>

<span data-ttu-id="d76f9-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-581">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-581">Checksum</span></span>

<span data-ttu-id="d76f9-582">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-583">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-583">Definition</span></span>

<span data-ttu-id="d76f9-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-587">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-587">Keywords</span></span>

<span data-ttu-id="d76f9-588">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-588"></span></span>
|<span data-ttu-id="d76f9-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-590">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-590">dl#</span></span>  <br/> <span data-ttu-id="d76f9-591">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-591">driver license</span></span>  <br/> <span data-ttu-id="d76f9-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-592">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-593">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-594">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-595">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-596">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-597">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-598">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-599">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-600">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-601">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="d76f9-602">permis de conduire</span></span>  <br/> <span data-ttu-id="d76f9-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="d76f9-603">rijbewijs</span></span>  <br/> <span data-ttu-id="d76f9-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="d76f9-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="d76f9-605">波兰</span><span class="sxs-lookup"><span data-stu-id="d76f9-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-606">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-606">Format</span></span>

<span data-ttu-id="d76f9-607">14位数，包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="d76f9-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-608">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-608">Pattern</span></span>

<span data-ttu-id="d76f9-609">14位数和2正斜杠：</span><span class="sxs-lookup"><span data-stu-id="d76f9-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="d76f9-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-610">Five digits</span></span> 
    
- <span data-ttu-id="d76f9-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="d76f9-611">A forward slash</span></span>
    
- <span data-ttu-id="d76f9-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-612">Two digits</span></span>
    
- <span data-ttu-id="d76f9-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="d76f9-613">A forward slash</span></span>
    
- <span data-ttu-id="d76f9-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-615">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-615">Checksum</span></span>

<span data-ttu-id="d76f9-616">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-617">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-617">Definition</span></span>

<span data-ttu-id="d76f9-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-621">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-621">Keywords</span></span>

<span data-ttu-id="d76f9-622">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-622"></span></span>
|<span data-ttu-id="d76f9-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-624">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-624">dl#</span></span>  <br/> <span data-ttu-id="d76f9-625">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-625">driver license</span></span>  <br/> <span data-ttu-id="d76f9-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-626">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-627">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-628">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-629">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-630">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-631">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-632">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-633">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-634">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-635">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="d76f9-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="d76f9-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="d76f9-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-638">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-638">Format</span></span>

<span data-ttu-id="d76f9-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-640">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-640">Pattern</span></span>

<span data-ttu-id="d76f9-641">两个字母后跟七个包含特殊字符的数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="d76f9-642">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="d76f9-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d76f9-643">A hyphen</span></span>
    
- <span data-ttu-id="d76f9-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-644">Six digits</span></span>
    
- <span data-ttu-id="d76f9-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="d76f9-645">A space</span></span>
    
- <span data-ttu-id="d76f9-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-647">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-647">Checksum</span></span>

<span data-ttu-id="d76f9-648">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-649">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-649">Definition</span></span>

<span data-ttu-id="d76f9-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-653">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-653">Keywords</span></span>

<span data-ttu-id="d76f9-654">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-654"></span></span>
|<span data-ttu-id="d76f9-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-656">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-656">dl#</span></span>  <br/> <span data-ttu-id="d76f9-657">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-657">driver license</span></span>  <br/> <span data-ttu-id="d76f9-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-658">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-659">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-660">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-661">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-662">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-663">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-664">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-665">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-666">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-667">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="d76f9-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="d76f9-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="d76f9-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-670">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-670">Format</span></span>

<span data-ttu-id="d76f9-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-672">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-672">Pattern</span></span>

<span data-ttu-id="d76f9-673">一个字符后跟八个数字：</span><span class="sxs-lookup"><span data-stu-id="d76f9-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="d76f9-674">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="d76f9-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-676">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-676">Checksum</span></span>

<span data-ttu-id="d76f9-677">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-678">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-678">Definition</span></span>

<span data-ttu-id="d76f9-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-682">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-682">Keywords</span></span>

<span data-ttu-id="d76f9-683">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-683"></span></span>
|<span data-ttu-id="d76f9-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-685">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-685">dl#</span></span>  <br/> <span data-ttu-id="d76f9-686">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-686">driver license</span></span>  <br/> <span data-ttu-id="d76f9-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-687">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-688">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-689">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-690">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-691">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-692">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-693">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-694">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-695">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-696">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="d76f9-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="d76f9-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="d76f9-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-699">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-699">Format</span></span>

<span data-ttu-id="d76f9-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-701">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-701">Pattern</span></span>

<span data-ttu-id="d76f9-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="d76f9-703">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="d76f9-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="d76f9-705">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-705">Checksum</span></span>

<span data-ttu-id="d76f9-706">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-707">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-707">Definition</span></span>

<span data-ttu-id="d76f9-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-711">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-711">Keywords</span></span>

<span data-ttu-id="d76f9-712">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-712"></span></span>
|<span data-ttu-id="d76f9-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-714">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-714">dl#</span></span>  <br/> <span data-ttu-id="d76f9-715">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-715">driver license</span></span>  <br/> <span data-ttu-id="d76f9-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-716">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-717">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-718">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-719">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-720">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-721">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-722">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-723">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-724">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-725">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="d76f9-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="d76f9-727">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="d76f9-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-728">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-728">Format</span></span>

<span data-ttu-id="d76f9-729">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d76f9-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-730">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-730">Pattern</span></span>

<span data-ttu-id="d76f9-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d76f9-732">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-732">Checksum</span></span>

<span data-ttu-id="d76f9-733">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-734">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-734">Definition</span></span>

<span data-ttu-id="d76f9-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-738">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-738">Keywords</span></span>

<span data-ttu-id="d76f9-739">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-739"></span></span>
|<span data-ttu-id="d76f9-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-741">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-741">dl#</span></span>  <br/> <span data-ttu-id="d76f9-742">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-742">driver license</span></span>  <br/> <span data-ttu-id="d76f9-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-743">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-744">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-745">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-746">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-747">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-748">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-749">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-750">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-751">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-752">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="d76f9-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="d76f9-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="d76f9-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-755">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-755">Format</span></span>

<span data-ttu-id="d76f9-756">8位数，后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="d76f9-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-757">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-757">Pattern</span></span>

<span data-ttu-id="d76f9-758">8位数，后跟一个字符：</span><span class="sxs-lookup"><span data-stu-id="d76f9-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="d76f9-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-759">Eight digits</span></span> 
    
- <span data-ttu-id="d76f9-760">一个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d76f9-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-761">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-761">Checksum</span></span>

<span data-ttu-id="d76f9-762">是</span><span class="sxs-lookup"><span data-stu-id="d76f9-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-763">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-763">Definition</span></span>

<span data-ttu-id="d76f9-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d76f9-767">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-767">Keywords</span></span>

<span data-ttu-id="d76f9-768">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-768"></span></span>
|<span data-ttu-id="d76f9-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-770">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-771">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-771">dl#</span></span>  <br/> <span data-ttu-id="d76f9-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-772">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-773">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-774">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-774">driver license</span></span>  <br/> <span data-ttu-id="d76f9-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-775">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-776">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-777">driver's licence</span></span>  <br/> <span data-ttu-id="d76f9-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-778">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-779">driving licence</span></span>  <br/> <span data-ttu-id="d76f9-780">driving license</span><span class="sxs-lookup"><span data-stu-id="d76f9-780">driving license</span></span>  <br/> <span data-ttu-id="d76f9-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-781">driver licence number</span></span>  <br/> <span data-ttu-id="d76f9-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-782">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-783">drivers licence number</span></span>  <br/> <span data-ttu-id="d76f9-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-784">drivers license number</span></span>  <br/> <span data-ttu-id="d76f9-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-785">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-786">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-787">driving licence number</span></span>  <br/> <span data-ttu-id="d76f9-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-788">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="d76f9-789">driving permit</span></span>  <br/> <span data-ttu-id="d76f9-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-790">driving permit number</span></span>  <br/> <span data-ttu-id="d76f9-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="d76f9-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="d76f9-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="d76f9-792">permiso conducción</span></span>  <br/> <span data-ttu-id="d76f9-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="d76f9-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="d76f9-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="d76f9-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-796">licencia conducir</span></span>  <br/> <span data-ttu-id="d76f9-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="d76f9-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="d76f9-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="d76f9-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-800">permiso conducir</span></span>  <br/> <span data-ttu-id="d76f9-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="d76f9-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="d76f9-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="d76f9-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="d76f9-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="d76f9-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="d76f9-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="d76f9-805">Format</span><span class="sxs-lookup"><span data-stu-id="d76f9-805">Format</span></span>

<span data-ttu-id="d76f9-806">10个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="d76f9-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d76f9-807">模式</span><span class="sxs-lookup"><span data-stu-id="d76f9-807">Pattern</span></span>

<span data-ttu-id="d76f9-808">10位数，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="d76f9-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="d76f9-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-809">Six digits</span></span> 
    
- <span data-ttu-id="d76f9-810">一个连字符</span><span class="sxs-lookup"><span data-stu-id="d76f9-810">A hyphen</span></span>
    
- <span data-ttu-id="d76f9-811">四个数字</span><span class="sxs-lookup"><span data-stu-id="d76f9-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d76f9-812">校验和</span><span class="sxs-lookup"><span data-stu-id="d76f9-812">Checksum</span></span>

<span data-ttu-id="d76f9-813">否</span><span class="sxs-lookup"><span data-stu-id="d76f9-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d76f9-814">定义</span><span class="sxs-lookup"><span data-stu-id="d76f9-814">Definition</span></span>

<span data-ttu-id="d76f9-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d76f9-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d76f9-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d76f9-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d76f9-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d76f9-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="d76f9-818">关键字</span><span class="sxs-lookup"><span data-stu-id="d76f9-818">Keywords</span></span>

<span data-ttu-id="d76f9-819">| |</span><span class="sxs-lookup"><span data-stu-id="d76f9-819"></span></span>
|<span data-ttu-id="d76f9-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="d76f9-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="d76f9-821">通讯#</span><span class="sxs-lookup"><span data-stu-id="d76f9-821">dl#</span></span>  <br/> <span data-ttu-id="d76f9-822">driver license</span><span class="sxs-lookup"><span data-stu-id="d76f9-822">driver license</span></span>  <br/> <span data-ttu-id="d76f9-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-823">driver license number</span></span>  <br/> <span data-ttu-id="d76f9-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="d76f9-824">driver licence</span></span>  <br/> <span data-ttu-id="d76f9-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d76f9-825">drivers lic.</span></span>  <br/> <span data-ttu-id="d76f9-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="d76f9-826">drivers license</span></span>  <br/> <span data-ttu-id="d76f9-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="d76f9-827">drivers licence</span></span>  <br/> <span data-ttu-id="d76f9-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="d76f9-828">driver's license</span></span>  <br/> <span data-ttu-id="d76f9-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-829">driver's license number</span></span>  <br/> <span data-ttu-id="d76f9-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="d76f9-830">driver's licence number</span></span>  <br/> <span data-ttu-id="d76f9-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="d76f9-831">driving license number</span></span>  <br/> <span data-ttu-id="d76f9-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="d76f9-832">dlno#</span></span>  <br/> <span data-ttu-id="d76f9-833">körkort</span><span class="sxs-lookup"><span data-stu-id="d76f9-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="d76f9-834">英国</span><span class="sxs-lookup"><span data-stu-id="d76f9-834">UK</span></span>

<span data-ttu-id="d76f9-835">有关详细信息，请参阅部分 "英国</span><span class="sxs-lookup"><span data-stu-id="d76f9-835">For details, see the section "U.K.</span></span> <span data-ttu-id="d76f9-836">"[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)" 中的 "驾驶执照号码"。</span><span class="sxs-lookup"><span data-stu-id="d76f9-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d76f9-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d76f9-837">See also</span></span>

[<span data-ttu-id="d76f9-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="d76f9-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

