---
title: 欧盟驾驶执照号码
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟驱动程序的敏感信息类型时，应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592653"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="f02e5-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-104">EU Driver's License Number</span></span>

<span data-ttu-id="f02e5-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟驱动程序的敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="f02e5-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="f02e5-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f02e5-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="f02e5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-108">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-108">Format</span></span>

<span data-ttu-id="f02e5-109">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-110">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-110">Pattern</span></span>

<span data-ttu-id="f02e5-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-112">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-112">Checksum</span></span>

<span data-ttu-id="f02e5-113">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-114">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-114">Definition</span></span>

<span data-ttu-id="f02e5-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="f02e5-118">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-118">Keywords</span></span>

<span data-ttu-id="f02e5-119">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-119">| |</span></span>
|<span data-ttu-id="f02e5-120">**Keywords_austria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-121">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-121">dl#</span></span>  <br/> <span data-ttu-id="f02e5-122">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-122">driver license</span></span>  <br/> <span data-ttu-id="f02e5-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-123">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-124">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-125">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-126">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-127">driver's licence</span></span>  <br/> <span data-ttu-id="f02e5-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-128">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-129">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="f02e5-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-131">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-132">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="f02e5-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="f02e5-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="f02e5-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="f02e5-135">比利时</span><span class="sxs-lookup"><span data-stu-id="f02e5-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-136">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-136">Format</span></span>

<span data-ttu-id="f02e5-137">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-138">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-138">Pattern</span></span>

<span data-ttu-id="f02e5-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-140">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-140">Checksum</span></span>

<span data-ttu-id="f02e5-141">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-142">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-142">Definition</span></span>

<span data-ttu-id="f02e5-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f02e5-146">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-146">Keywords</span></span>

<span data-ttu-id="f02e5-147">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-147">| |</span></span>
|<span data-ttu-id="f02e5-148">**Keywords__belgium_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-149">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-149">dl#</span></span>  <br/> <span data-ttu-id="f02e5-150">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-150">driver license</span></span>  <br/> <span data-ttu-id="f02e5-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-151">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-152">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-153">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-154">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-155">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-156">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-157">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-158">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-159">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f02e5-160">rijbewijs</span></span>  <br/> <span data-ttu-id="f02e5-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="f02e5-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="f02e5-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="f02e5-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="f02e5-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="f02e5-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="f02e5-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="f02e5-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="f02e5-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="f02e5-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="f02e5-168">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="f02e5-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-169">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-169">Format</span></span>

<span data-ttu-id="f02e5-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-171">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-171">Pattern</span></span>

<span data-ttu-id="f02e5-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-173">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-173">Checksum</span></span>

<span data-ttu-id="f02e5-174">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-175">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-175">Definition</span></span>

<span data-ttu-id="f02e5-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="f02e5-179">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-179">Keywords</span></span>

<span data-ttu-id="f02e5-180">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-180">| |</span></span>
|<span data-ttu-id="f02e5-181">**Keywords_bulgaria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-182">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-182">dl#</span></span>  <br/> <span data-ttu-id="f02e5-183">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-183">driver license</span></span>  <br/> <span data-ttu-id="f02e5-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-184">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-185">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-186">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-187">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-188">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-189">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-190">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-191">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-192">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-193">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="f02e5-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="f02e5-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="f02e5-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="f02e5-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="f02e5-196">сумпс</span></span>  <br/> <span data-ttu-id="f02e5-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="f02e5-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="f02e5-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="f02e5-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-199">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-199">Format</span></span>

<span data-ttu-id="f02e5-200">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-201">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-201">Pattern</span></span>

<span data-ttu-id="f02e5-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-203">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-203">Checksum</span></span>

<span data-ttu-id="f02e5-204">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-205">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-205">Definition</span></span>

<span data-ttu-id="f02e5-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f02e5-209">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-209">Keywords</span></span>

<span data-ttu-id="f02e5-210">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-210">| |</span></span>
|<span data-ttu-id="f02e5-211">**Keywords_croatia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-212">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-212">dl#</span></span>  <br/> <span data-ttu-id="f02e5-213">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-213">driver license</span></span>  <br/> <span data-ttu-id="f02e5-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-214">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-215">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-216">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-217">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-218">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-219">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-220">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-221">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-222">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-223">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="f02e5-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="f02e5-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="f02e5-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-226">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-226">Format</span></span>

<span data-ttu-id="f02e5-227">12个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-228">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-228">Pattern</span></span>

<span data-ttu-id="f02e5-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-230">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-230">Checksum</span></span>

<span data-ttu-id="f02e5-231">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-232">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-232">Definition</span></span>

<span data-ttu-id="f02e5-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-236">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-236">Keywords</span></span>

<span data-ttu-id="f02e5-237">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-237">| |</span></span>
|<span data-ttu-id="f02e5-238">**Keywords_cyprus_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-239">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-239">dl#</span></span>  <br/> <span data-ttu-id="f02e5-240">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-240">driver license</span></span>  <br/> <span data-ttu-id="f02e5-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-241">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-242">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-243">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-244">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-245">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-246">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-247">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-248">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-249">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="f02e5-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="f02e5-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="f02e5-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-252">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-252">Format</span></span>

<span data-ttu-id="f02e5-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-254">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-254">Pattern</span></span>

<span data-ttu-id="f02e5-255">八个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="f02e5-256">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="f02e5-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="f02e5-257">A space (optional)</span></span>
    
- <span data-ttu-id="f02e5-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-259">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-259">Checksum</span></span>

<span data-ttu-id="f02e5-260">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-261">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-261">Definition</span></span>

<span data-ttu-id="f02e5-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f02e5-265">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-265">Keywords</span></span>

<span data-ttu-id="f02e5-266">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-266">| |</span></span>
|<span data-ttu-id="f02e5-267">**Keywords_czech_republic_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-268">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-268">dl#</span></span>  <br/> <span data-ttu-id="f02e5-269">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-269">driver license</span></span>  <br/> <span data-ttu-id="f02e5-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-270">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-271">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-272">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-273">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-274">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-275">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-276">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-277">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-278">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-279">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-280">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="f02e5-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="f02e5-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="f02e5-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-283">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-283">Format</span></span>

<span data-ttu-id="f02e5-284">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-285">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-285">Pattern</span></span>

<span data-ttu-id="f02e5-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-287">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-287">Checksum</span></span>

<span data-ttu-id="f02e5-288">是</span><span class="sxs-lookup"><span data-stu-id="f02e5-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-289">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-289">Definition</span></span>

<span data-ttu-id="f02e5-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="f02e5-293">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-293">Keywords</span></span>

<span data-ttu-id="f02e5-294">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-294">| |</span></span>
|<span data-ttu-id="f02e5-295">**Keywords_denmark_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-296">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-296">dl#</span></span>  <br/> <span data-ttu-id="f02e5-297">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-297">driver license</span></span>  <br/> <span data-ttu-id="f02e5-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-298">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-299">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-300">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-301">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-302">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-303">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-304">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-305">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-306">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-307">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="f02e5-308">kørekort</span></span>  <br/> <span data-ttu-id="f02e5-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="f02e5-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="f02e5-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-311">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-311">Format</span></span>

<span data-ttu-id="f02e5-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-313">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-313">Pattern</span></span>

<span data-ttu-id="f02e5-314">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f02e5-315">字母 "ET" （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f02e5-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-317">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-317">Checksum</span></span>

<span data-ttu-id="f02e5-318">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-319">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-319">Definition</span></span>

<span data-ttu-id="f02e5-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-323">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-323">Keywords</span></span>

<span data-ttu-id="f02e5-324">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-324">| |</span></span>
|<span data-ttu-id="f02e5-325">**Keywords_estonia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-326">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-326">dl#</span></span>  <br/> <span data-ttu-id="f02e5-327">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-327">driver license</span></span>  <br/> <span data-ttu-id="f02e5-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-328">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-329">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-330">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-331">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-332">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-333">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-334">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-335">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-336">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-337">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f02e5-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="f02e5-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="f02e5-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-340">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-340">Format</span></span>

<span data-ttu-id="f02e5-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="f02e5-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-342">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-342">Pattern</span></span>

<span data-ttu-id="f02e5-343">10个数字，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="f02e5-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f02e5-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-344">Six digits</span></span> 
    
- <span data-ttu-id="f02e5-345">一个连字符</span><span class="sxs-lookup"><span data-stu-id="f02e5-345">A hyphen</span></span>
    
-  <span data-ttu-id="f02e5-346">四个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f02e5-347">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-347">Checksum</span></span>

<span data-ttu-id="f02e5-348">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-349">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-349">Definition</span></span>

<span data-ttu-id="f02e5-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-353">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-353">Keywords</span></span>

<span data-ttu-id="f02e5-354">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-354">| |</span></span>
|<span data-ttu-id="f02e5-355">**Keywords_finland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-356">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-356">dl#</span></span>  <br/> <span data-ttu-id="f02e5-357">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-357">driver license</span></span>  <br/> <span data-ttu-id="f02e5-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-358">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-359">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-360">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-361">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-362">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-363">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-364">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-365">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-366">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-367">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="f02e5-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="f02e5-369">法国</span><span class="sxs-lookup"><span data-stu-id="f02e5-369">France</span></span>

<span data-ttu-id="f02e5-370">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="f02e5-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="f02e5-371">德国</span><span class="sxs-lookup"><span data-stu-id="f02e5-371">Germany</span></span>

<span data-ttu-id="f02e5-372">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="f02e5-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="f02e5-373">希腊</span><span class="sxs-lookup"><span data-stu-id="f02e5-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-374">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-374">Format</span></span>

<span data-ttu-id="f02e5-375">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-376">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-376">Pattern</span></span>

 <span data-ttu-id="f02e5-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f02e5-378">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-378">Checksum</span></span>

<span data-ttu-id="f02e5-379">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-380">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-380">Definition</span></span>

<span data-ttu-id="f02e5-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-384">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-384">Keywords</span></span>

<span data-ttu-id="f02e5-385">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-385">| |</span></span>
|<span data-ttu-id="f02e5-386">**Keywords_greece_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="f02e5-387">dlL#</span></span>  <br/> <span data-ttu-id="f02e5-388">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-388">driver license</span></span>  <br/> <span data-ttu-id="f02e5-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-389">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-390">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-391">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-392">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-393">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-394">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-395">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-396">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-397">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-398">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="f02e5-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="f02e5-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="f02e5-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="f02e5-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="f02e5-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-402">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-402">Format</span></span>

<span data-ttu-id="f02e5-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-404">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-404">Pattern</span></span>

<span data-ttu-id="f02e5-405">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="f02e5-406">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f02e5-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-408">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-408">Checksum</span></span>

<span data-ttu-id="f02e5-409">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-410">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-410">Definition</span></span>

<span data-ttu-id="f02e5-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-414">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-414">Keywords</span></span>

<span data-ttu-id="f02e5-415">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-415">| |</span></span>
|<span data-ttu-id="f02e5-416">**Keywords_hungary_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-417">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-417">dl#</span></span>  <br/> <span data-ttu-id="f02e5-418">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-418">driver license</span></span>  <br/> <span data-ttu-id="f02e5-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-419">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-420">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-421">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-422">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-423">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-424">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-425">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-426">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-427">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-428">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="f02e5-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="f02e5-430">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="f02e5-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-431">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-431">Format</span></span>

<span data-ttu-id="f02e5-432">6位数，后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="f02e5-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-433">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-433">Pattern</span></span>

<span data-ttu-id="f02e5-434">6位数字和四个字母：</span><span class="sxs-lookup"><span data-stu-id="f02e5-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="f02e5-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-435">Six digits</span></span>
    
- <span data-ttu-id="f02e5-436">四个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-437">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-437">Checksum</span></span>

<span data-ttu-id="f02e5-438">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-439">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-439">Definition</span></span>

<span data-ttu-id="f02e5-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-443">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-443">Keywords</span></span>

<span data-ttu-id="f02e5-444">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-444">| |</span></span>
|<span data-ttu-id="f02e5-445">**Keywords_ireland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-446">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-446">dl#</span></span>  <br/> <span data-ttu-id="f02e5-447">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-447">driver license</span></span>  <br/> <span data-ttu-id="f02e5-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-448">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-449">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-450">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-451">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-452">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-453">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-454">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-455">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-456">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-457">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="f02e5-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="f02e5-459">意大利</span><span class="sxs-lookup"><span data-stu-id="f02e5-459">Italy</span></span>

<span data-ttu-id="f02e5-460">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="f02e5-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f02e5-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="f02e5-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-462">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-462">Format</span></span>

<span data-ttu-id="f02e5-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-464">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-464">Pattern</span></span>

<span data-ttu-id="f02e5-465">三个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="f02e5-466">三个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f02e5-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-468">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-468">Checksum</span></span>

<span data-ttu-id="f02e5-469">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-470">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-470">Definition</span></span>

<span data-ttu-id="f02e5-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-474">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-474">Keywords</span></span>

<span data-ttu-id="f02e5-475">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-475">| |</span></span>
|<span data-ttu-id="f02e5-476">**Keywords_latvia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-477">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-477">dl#</span></span>  <br/> <span data-ttu-id="f02e5-478">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-478">driver license</span></span>  <br/> <span data-ttu-id="f02e5-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-479">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-480">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-481">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-482">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-483">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-484">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-485">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-486">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-487">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-488">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="f02e5-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="f02e5-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="f02e5-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-491">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-491">Format</span></span>

<span data-ttu-id="f02e5-492">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-493">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-493">Pattern</span></span>

 <span data-ttu-id="f02e5-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f02e5-495">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-495">Checksum</span></span>

<span data-ttu-id="f02e5-496">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-497">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-497">Definition</span></span>

<span data-ttu-id="f02e5-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-501">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-501">Keywords</span></span>

<span data-ttu-id="f02e5-502">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-502">| |</span></span>
|<span data-ttu-id="f02e5-503">**Keywords_lithuania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-504">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-504">dl#</span></span>  <br/> <span data-ttu-id="f02e5-505">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-505">driver license</span></span>  <br/> <span data-ttu-id="f02e5-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-506">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-507">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-508">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-509">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-510">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-511">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-512">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-513">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-514">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-515">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="f02e5-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="f02e5-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="f02e5-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-518">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-518">Format</span></span>

<span data-ttu-id="f02e5-519">6位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-520">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-520">Pattern</span></span>

 <span data-ttu-id="f02e5-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f02e5-522">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-522">Checksum</span></span>

<span data-ttu-id="f02e5-523">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-524">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-524">Definition</span></span>

<span data-ttu-id="f02e5-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-528">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-528">Keywords</span></span>

<span data-ttu-id="f02e5-529">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-529">| |</span></span>
|<span data-ttu-id="f02e5-530">**Keywords_luxemburg_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-531">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-531">dl#</span></span>  <br/> <span data-ttu-id="f02e5-532">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-532">driver license</span></span>  <br/> <span data-ttu-id="f02e5-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-533">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-534">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-535">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-536">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-537">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-538">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-539">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-540">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-541">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-542">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="f02e5-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="f02e5-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="f02e5-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-545">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-545">Format</span></span>

<span data-ttu-id="f02e5-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="f02e5-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-547">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-547">Pattern</span></span>

<span data-ttu-id="f02e5-548">两个字符和六个数字的组合：</span><span class="sxs-lookup"><span data-stu-id="f02e5-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="f02e5-549">两个字符（数字或字母，而不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="f02e5-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="f02e5-550">A space (optional)</span></span>
    
- <span data-ttu-id="f02e5-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="f02e5-551">Three digits</span></span>
    
- <span data-ttu-id="f02e5-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="f02e5-552">A space (optional)</span></span>
    
- <span data-ttu-id="f02e5-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-554">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-554">Checksum</span></span>

<span data-ttu-id="f02e5-555">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-556">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-556">Definition</span></span>

<span data-ttu-id="f02e5-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-560">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-560">Keywords</span></span>

<span data-ttu-id="f02e5-561">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-561">| |</span></span>
|<span data-ttu-id="f02e5-562">**Keywords_malta_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-563">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-563">dl#</span></span>  <br/> <span data-ttu-id="f02e5-564">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-564">driver license</span></span>  <br/> <span data-ttu-id="f02e5-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-565">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-566">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-567">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-568">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-569">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-570">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-571">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-572">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-573">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-574">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="f02e5-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="f02e5-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="f02e5-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-577">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-577">Format</span></span>

<span data-ttu-id="f02e5-578">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-579">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-579">Pattern</span></span>

<span data-ttu-id="f02e5-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-581">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-581">Checksum</span></span>

<span data-ttu-id="f02e5-582">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-583">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-583">Definition</span></span>

<span data-ttu-id="f02e5-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-587">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-587">Keywords</span></span>

<span data-ttu-id="f02e5-588">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-588">| |</span></span>
|<span data-ttu-id="f02e5-589">**Keywords_netherlands_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-590">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-590">dl#</span></span>  <br/> <span data-ttu-id="f02e5-591">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-591">driver license</span></span>  <br/> <span data-ttu-id="f02e5-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-592">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-593">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-594">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-595">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-596">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-597">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-598">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-599">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-600">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-601">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="f02e5-602">permis de conduire</span></span>  <br/> <span data-ttu-id="f02e5-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="f02e5-603">rijbewijs</span></span>  <br/> <span data-ttu-id="f02e5-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="f02e5-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="f02e5-605">波兰</span><span class="sxs-lookup"><span data-stu-id="f02e5-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-606">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-606">Format</span></span>

<span data-ttu-id="f02e5-607">14位数，包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="f02e5-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-608">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-608">Pattern</span></span>

<span data-ttu-id="f02e5-609">14位数和2正斜杠：</span><span class="sxs-lookup"><span data-stu-id="f02e5-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="f02e5-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-610">Five digits</span></span> 
    
- <span data-ttu-id="f02e5-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="f02e5-611">A forward slash</span></span>
    
- <span data-ttu-id="f02e5-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-612">Two digits</span></span>
    
- <span data-ttu-id="f02e5-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="f02e5-613">A forward slash</span></span>
    
- <span data-ttu-id="f02e5-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-615">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-615">Checksum</span></span>

<span data-ttu-id="f02e5-616">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-617">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-617">Definition</span></span>

<span data-ttu-id="f02e5-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-621">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-621">Keywords</span></span>

<span data-ttu-id="f02e5-622">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-622">| |</span></span>
|<span data-ttu-id="f02e5-623">**Keywords_poland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-624">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-624">dl#</span></span>  <br/> <span data-ttu-id="f02e5-625">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-625">driver license</span></span>  <br/> <span data-ttu-id="f02e5-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-626">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-627">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-628">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-629">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-630">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-631">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-632">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-633">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-634">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-635">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="f02e5-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="f02e5-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="f02e5-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-638">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-638">Format</span></span>

<span data-ttu-id="f02e5-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-640">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-640">Pattern</span></span>

<span data-ttu-id="f02e5-641">两个字母后跟七个包含特殊字符的数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="f02e5-642">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="f02e5-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="f02e5-643">A hyphen</span></span>
    
- <span data-ttu-id="f02e5-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-644">Six digits</span></span>
    
- <span data-ttu-id="f02e5-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="f02e5-645">A space</span></span>
    
- <span data-ttu-id="f02e5-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-647">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-647">Checksum</span></span>

<span data-ttu-id="f02e5-648">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-649">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-649">Definition</span></span>

<span data-ttu-id="f02e5-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-653">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-653">Keywords</span></span>

<span data-ttu-id="f02e5-654">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-654">| |</span></span>
|<span data-ttu-id="f02e5-655">**Keywords_portugal_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-656">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-656">dl#</span></span>  <br/> <span data-ttu-id="f02e5-657">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-657">driver license</span></span>  <br/> <span data-ttu-id="f02e5-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-658">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-659">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-660">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-661">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-662">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-663">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-664">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-665">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-666">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-667">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="f02e5-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="f02e5-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="f02e5-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-670">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-670">Format</span></span>

<span data-ttu-id="f02e5-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-672">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-672">Pattern</span></span>

<span data-ttu-id="f02e5-673">一个字符后跟八个数字：</span><span class="sxs-lookup"><span data-stu-id="f02e5-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="f02e5-674">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="f02e5-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-676">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-676">Checksum</span></span>

<span data-ttu-id="f02e5-677">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-678">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-678">Definition</span></span>

<span data-ttu-id="f02e5-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-682">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-682">Keywords</span></span>

<span data-ttu-id="f02e5-683">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-683">| |</span></span>
|<span data-ttu-id="f02e5-684">**Keywords_romania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-685">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-685">dl#</span></span>  <br/> <span data-ttu-id="f02e5-686">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-686">driver license</span></span>  <br/> <span data-ttu-id="f02e5-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-687">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-688">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-689">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-690">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-691">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-692">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-693">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-694">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-695">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-696">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="f02e5-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="f02e5-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="f02e5-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-699">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-699">Format</span></span>

<span data-ttu-id="f02e5-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-701">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-701">Pattern</span></span>

<span data-ttu-id="f02e5-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="f02e5-703">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="f02e5-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f02e5-705">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-705">Checksum</span></span>

<span data-ttu-id="f02e5-706">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-707">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-707">Definition</span></span>

<span data-ttu-id="f02e5-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-711">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-711">Keywords</span></span>

<span data-ttu-id="f02e5-712">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-712">| |</span></span>
|<span data-ttu-id="f02e5-713">**Keywords_slovakia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-714">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-714">dl#</span></span>  <br/> <span data-ttu-id="f02e5-715">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-715">driver license</span></span>  <br/> <span data-ttu-id="f02e5-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-716">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-717">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-718">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-719">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-720">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-721">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-722">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-723">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-724">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-725">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="f02e5-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="f02e5-727">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="f02e5-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-728">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-728">Format</span></span>

<span data-ttu-id="f02e5-729">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="f02e5-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-730">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-730">Pattern</span></span>

<span data-ttu-id="f02e5-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f02e5-732">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-732">Checksum</span></span>

<span data-ttu-id="f02e5-733">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-734">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-734">Definition</span></span>

<span data-ttu-id="f02e5-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-738">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-738">Keywords</span></span>

<span data-ttu-id="f02e5-739">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-739">| |</span></span>
|<span data-ttu-id="f02e5-740">**Keywords_slovenia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-741">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-741">dl#</span></span>  <br/> <span data-ttu-id="f02e5-742">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-742">driver license</span></span>  <br/> <span data-ttu-id="f02e5-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-743">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-744">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-745">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-746">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-747">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-748">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-749">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-750">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-751">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-752">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="f02e5-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="f02e5-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="f02e5-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-755">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-755">Format</span></span>

<span data-ttu-id="f02e5-756">8位数，后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="f02e5-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-757">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-757">Pattern</span></span>

<span data-ttu-id="f02e5-758">8位数，后跟一个字符：</span><span class="sxs-lookup"><span data-stu-id="f02e5-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="f02e5-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-759">Eight digits</span></span> 
    
- <span data-ttu-id="f02e5-760">一个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="f02e5-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-761">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-761">Checksum</span></span>

<span data-ttu-id="f02e5-762">是</span><span class="sxs-lookup"><span data-stu-id="f02e5-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-763">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-763">Definition</span></span>

<span data-ttu-id="f02e5-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f02e5-767">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-767">Keywords</span></span>

<span data-ttu-id="f02e5-768">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-768">| |</span></span>
|<span data-ttu-id="f02e5-769">**Keywords_spain_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-770">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-771">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-771">dl#</span></span>  <br/> <span data-ttu-id="f02e5-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-772">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-773">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-774">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-774">driver license</span></span>  <br/> <span data-ttu-id="f02e5-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-775">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-776">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-777">driver's licence</span></span>  <br/> <span data-ttu-id="f02e5-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-778">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-779">driving licence</span></span>  <br/> <span data-ttu-id="f02e5-780">driving license</span><span class="sxs-lookup"><span data-stu-id="f02e5-780">driving license</span></span>  <br/> <span data-ttu-id="f02e5-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-781">driver licence number</span></span>  <br/> <span data-ttu-id="f02e5-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-782">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-783">drivers licence number</span></span>  <br/> <span data-ttu-id="f02e5-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-784">drivers license number</span></span>  <br/> <span data-ttu-id="f02e5-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-785">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-786">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-787">driving licence number</span></span>  <br/> <span data-ttu-id="f02e5-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-788">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="f02e5-789">driving permit</span></span>  <br/> <span data-ttu-id="f02e5-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-790">driving permit number</span></span>  <br/> <span data-ttu-id="f02e5-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="f02e5-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="f02e5-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="f02e5-792">permiso conducción</span></span>  <br/> <span data-ttu-id="f02e5-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="f02e5-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="f02e5-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="f02e5-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-796">licencia conducir</span></span>  <br/> <span data-ttu-id="f02e5-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="f02e5-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="f02e5-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="f02e5-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-800">permiso conducir</span></span>  <br/> <span data-ttu-id="f02e5-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="f02e5-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="f02e5-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="f02e5-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="f02e5-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="f02e5-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="f02e5-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f02e5-805">Format</span><span class="sxs-lookup"><span data-stu-id="f02e5-805">Format</span></span>

<span data-ttu-id="f02e5-806">10个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="f02e5-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f02e5-807">模式</span><span class="sxs-lookup"><span data-stu-id="f02e5-807">Pattern</span></span>

<span data-ttu-id="f02e5-808">10位数，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="f02e5-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="f02e5-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-809">Six digits</span></span> 
    
- <span data-ttu-id="f02e5-810">一个连字符</span><span class="sxs-lookup"><span data-stu-id="f02e5-810">A hyphen</span></span>
    
- <span data-ttu-id="f02e5-811">四个数字</span><span class="sxs-lookup"><span data-stu-id="f02e5-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f02e5-812">校验和</span><span class="sxs-lookup"><span data-stu-id="f02e5-812">Checksum</span></span>

<span data-ttu-id="f02e5-813">否</span><span class="sxs-lookup"><span data-stu-id="f02e5-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="f02e5-814">定义</span><span class="sxs-lookup"><span data-stu-id="f02e5-814">Definition</span></span>

<span data-ttu-id="f02e5-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="f02e5-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f02e5-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="f02e5-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f02e5-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="f02e5-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="f02e5-818">关键字</span><span class="sxs-lookup"><span data-stu-id="f02e5-818">Keywords</span></span>

<span data-ttu-id="f02e5-819">| |</span><span class="sxs-lookup"><span data-stu-id="f02e5-819">| |</span></span>
|<span data-ttu-id="f02e5-820">**Keywords_sweden_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="f02e5-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="f02e5-821">通讯#</span><span class="sxs-lookup"><span data-stu-id="f02e5-821">dl#</span></span>  <br/> <span data-ttu-id="f02e5-822">driver license</span><span class="sxs-lookup"><span data-stu-id="f02e5-822">driver license</span></span>  <br/> <span data-ttu-id="f02e5-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-823">driver license number</span></span>  <br/> <span data-ttu-id="f02e5-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="f02e5-824">driver licence</span></span>  <br/> <span data-ttu-id="f02e5-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="f02e5-825">drivers lic.</span></span>  <br/> <span data-ttu-id="f02e5-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="f02e5-826">drivers license</span></span>  <br/> <span data-ttu-id="f02e5-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="f02e5-827">drivers licence</span></span>  <br/> <span data-ttu-id="f02e5-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="f02e5-828">driver's license</span></span>  <br/> <span data-ttu-id="f02e5-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-829">driver's license number</span></span>  <br/> <span data-ttu-id="f02e5-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="f02e5-830">driver's licence number</span></span>  <br/> <span data-ttu-id="f02e5-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="f02e5-831">driving license number</span></span>  <br/> <span data-ttu-id="f02e5-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="f02e5-832">dlno#</span></span>  <br/> <span data-ttu-id="f02e5-833">körkort</span><span class="sxs-lookup"><span data-stu-id="f02e5-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="f02e5-834">英国</span><span class="sxs-lookup"><span data-stu-id="f02e5-834">UK</span></span>

<span data-ttu-id="f02e5-835">有关详细信息，请参阅部分 "英国</span><span class="sxs-lookup"><span data-stu-id="f02e5-835">For details, see the section "U.K.</span></span> <span data-ttu-id="f02e5-836">"[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)" 中的 "驾驶执照号码"。</span><span class="sxs-lookup"><span data-stu-id="f02e5-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f02e5-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f02e5-837">See also</span></span>

[<span data-ttu-id="f02e5-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="f02e5-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

