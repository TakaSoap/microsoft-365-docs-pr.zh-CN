---
title: 欧盟驾驶执照号码
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805955"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="2ea71-104">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-104">EU Driver's License Number</span></span>

<span data-ttu-id="2ea71-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟驱动程序的敏感信息类型时，应查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="2ea71-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="2ea71-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2ea71-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="2ea71-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-108">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-108">Format</span></span>

<span data-ttu-id="2ea71-109">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-110">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-110">Pattern</span></span>

<span data-ttu-id="2ea71-111">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-112">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-112">Checksum</span></span>

<span data-ttu-id="2ea71-113">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-114">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-114">Definition</span></span>

<span data-ttu-id="2ea71-115">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-116">正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-117">找到了中`Keywords_austria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="2ea71-118">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-118">Keywords</span></span>

<span data-ttu-id="2ea71-119">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-119"></span></span>
|<span data-ttu-id="2ea71-120">**Keywords_austria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-121">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-121">dl#</span></span>  <br/> <span data-ttu-id="2ea71-122">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-122">driver license</span></span>  <br/> <span data-ttu-id="2ea71-123">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-123">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-124">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-124">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-125">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-125">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-126">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-127">driver's licence</span></span>  <br/> <span data-ttu-id="2ea71-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-128">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-129">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-129">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-130">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="2ea71-131">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-131">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-132">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2ea71-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="2ea71-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="2ea71-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="2ea71-135">比利时</span><span class="sxs-lookup"><span data-stu-id="2ea71-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-136">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-136">Format</span></span>

<span data-ttu-id="2ea71-137">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-138">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-138">Pattern</span></span>

<span data-ttu-id="2ea71-139">10 个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-140">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-140">Checksum</span></span>

<span data-ttu-id="2ea71-141">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-142">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-142">Definition</span></span>

<span data-ttu-id="2ea71-143">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-144">正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-145">找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="2ea71-146">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-146">Keywords</span></span>

<span data-ttu-id="2ea71-147">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-147"></span></span>
|<span data-ttu-id="2ea71-148">**Keywords__belgium_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-149">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-149">dl#</span></span>  <br/> <span data-ttu-id="2ea71-150">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-150">driver license</span></span>  <br/> <span data-ttu-id="2ea71-151">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-151">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-152">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-152">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-153">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-153">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-154">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-155">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-156">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-157">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-157">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-158">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-158">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-159">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="2ea71-160">rijbewijs</span></span>  <br/> <span data-ttu-id="2ea71-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="2ea71-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="2ea71-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="2ea71-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="2ea71-165">führerschein-nr-nr</span><span class="sxs-lookup"><span data-stu-id="2ea71-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="2ea71-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="2ea71-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="2ea71-167">fuehrerschein-nr</span><span class="sxs-lookup"><span data-stu-id="2ea71-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="2ea71-168">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="2ea71-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-169">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-169">Format</span></span>

<span data-ttu-id="2ea71-170">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-171">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-171">Pattern</span></span>

<span data-ttu-id="2ea71-172">九个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-173">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-173">Checksum</span></span>

<span data-ttu-id="2ea71-174">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-175">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-175">Definition</span></span>

<span data-ttu-id="2ea71-176">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-177">正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-178">找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="2ea71-179">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-179">Keywords</span></span>

<span data-ttu-id="2ea71-180">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-180"></span></span>
|<span data-ttu-id="2ea71-181">**Keywords_bulgaria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-182">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-182">dl#</span></span>  <br/> <span data-ttu-id="2ea71-183">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-183">driver license</span></span>  <br/> <span data-ttu-id="2ea71-184">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-184">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-185">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-185">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-186">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-186">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-187">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-188">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-189">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-190">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-190">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-191">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-191">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-192">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-192">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-193">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="2ea71-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="2ea71-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="2ea71-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="2ea71-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="2ea71-196">сумпс</span></span>  <br/> <span data-ttu-id="2ea71-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="2ea71-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="2ea71-198">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="2ea71-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-199">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-199">Format</span></span>

<span data-ttu-id="2ea71-200">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-201">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-201">Pattern</span></span>

<span data-ttu-id="2ea71-202">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-203">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-203">Checksum</span></span>

<span data-ttu-id="2ea71-204">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-205">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-205">Definition</span></span>

<span data-ttu-id="2ea71-206">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-207">正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-208">找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="2ea71-209">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-209">Keywords</span></span>

<span data-ttu-id="2ea71-210">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-210"></span></span>
|<span data-ttu-id="2ea71-211">**Keywords_croatia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-212">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-212">dl#</span></span>  <br/> <span data-ttu-id="2ea71-213">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-213">driver license</span></span>  <br/> <span data-ttu-id="2ea71-214">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-214">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-215">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-215">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-216">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-216">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-217">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-218">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-219">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-220">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-220">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-221">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-221">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-222">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-222">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-223">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="2ea71-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="2ea71-225">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="2ea71-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-226">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-226">Format</span></span>

<span data-ttu-id="2ea71-227">12个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-228">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-228">Pattern</span></span>

<span data-ttu-id="2ea71-229">12 个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-230">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-230">Checksum</span></span>

<span data-ttu-id="2ea71-231">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-232">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-232">Definition</span></span>

<span data-ttu-id="2ea71-233">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-234">正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-235">找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-236">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-236">Keywords</span></span>

<span data-ttu-id="2ea71-237">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-237"></span></span>
|<span data-ttu-id="2ea71-238">**Keywords_cyprus_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-239">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-239">dl#</span></span>  <br/> <span data-ttu-id="2ea71-240">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-240">driver license</span></span>  <br/> <span data-ttu-id="2ea71-241">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-241">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-242">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-242">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-243">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-243">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-244">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-245">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-246">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-246">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-247">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-247">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-248">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-248">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-249">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="2ea71-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="2ea71-251">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="2ea71-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-252">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-252">Format</span></span>

<span data-ttu-id="2ea71-253">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-254">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-254">Pattern</span></span>

<span data-ttu-id="2ea71-255">八个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="2ea71-256">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="2ea71-257">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="2ea71-257">A space (optional)</span></span>
    
- <span data-ttu-id="2ea71-258">六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-259">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-259">Checksum</span></span>

<span data-ttu-id="2ea71-260">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-261">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-261">Definition</span></span>

<span data-ttu-id="2ea71-262">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-263">正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-264">找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="2ea71-265">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-265">Keywords</span></span>

<span data-ttu-id="2ea71-266">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-266"></span></span>
|<span data-ttu-id="2ea71-267">**Keywords_czech_republic_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-268">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-268">dl#</span></span>  <br/> <span data-ttu-id="2ea71-269">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-269">driver license</span></span>  <br/> <span data-ttu-id="2ea71-270">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-270">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-271">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-271">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-272">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-272">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-273">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-274">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-275">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-276">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-276">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-277">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-277">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-278">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-278">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-279">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-279">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-280">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="2ea71-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="2ea71-282">丹麦</span><span class="sxs-lookup"><span data-stu-id="2ea71-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-283">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-283">Format</span></span>

<span data-ttu-id="2ea71-284">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-285">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-285">Pattern</span></span>

<span data-ttu-id="2ea71-286">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-287">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-287">Checksum</span></span>

<span data-ttu-id="2ea71-288">是</span><span class="sxs-lookup"><span data-stu-id="2ea71-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-289">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-289">Definition</span></span>

<span data-ttu-id="2ea71-290">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-291">正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-292">找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="2ea71-293">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-293">Keywords</span></span>

<span data-ttu-id="2ea71-294">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-294"></span></span>
|<span data-ttu-id="2ea71-295">**Keywords_denmark_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-296">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-296">dl#</span></span>  <br/> <span data-ttu-id="2ea71-297">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-297">driver license</span></span>  <br/> <span data-ttu-id="2ea71-298">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-298">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-299">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-299">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-300">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-300">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-301">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-302">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-303">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-304">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-304">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-305">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-305">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-306">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-306">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-307">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="2ea71-308">kørekort</span></span>  <br/> <span data-ttu-id="2ea71-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="2ea71-310">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="2ea71-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-311">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-311">Format</span></span>

<span data-ttu-id="2ea71-312">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-313">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-313">Pattern</span></span>

<span data-ttu-id="2ea71-314">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="2ea71-315">字母 "ET" （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="2ea71-316">六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-317">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-317">Checksum</span></span>

<span data-ttu-id="2ea71-318">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-319">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-319">Definition</span></span>

<span data-ttu-id="2ea71-320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-321">正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-322">找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-323">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-323">Keywords</span></span>

<span data-ttu-id="2ea71-324">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-324"></span></span>
|<span data-ttu-id="2ea71-325">**Keywords_estonia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-326">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-326">dl#</span></span>  <br/> <span data-ttu-id="2ea71-327">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-327">driver license</span></span>  <br/> <span data-ttu-id="2ea71-328">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-328">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-329">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-329">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-330">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-330">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-331">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-331">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-332">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-333">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-334">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-335">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-335">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-336">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-336">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-337">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="2ea71-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="2ea71-339">芬兰</span><span class="sxs-lookup"><span data-stu-id="2ea71-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-340">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-340">Format</span></span>

<span data-ttu-id="2ea71-341">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="2ea71-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-342">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-342">Pattern</span></span>

<span data-ttu-id="2ea71-343">10个数字，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="2ea71-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="2ea71-344">六位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-344">Six digits</span></span> 
    
- <span data-ttu-id="2ea71-345">一个连字符</span><span class="sxs-lookup"><span data-stu-id="2ea71-345">A hyphen</span></span>
    
-  <span data-ttu-id="2ea71-346">四个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2ea71-347">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-347">Checksum</span></span>

<span data-ttu-id="2ea71-348">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-349">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-349">Definition</span></span>

<span data-ttu-id="2ea71-350">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-351">正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-352">找到了中`Keywords_finland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-353">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-353">Keywords</span></span>

<span data-ttu-id="2ea71-354">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-354"></span></span>
|<span data-ttu-id="2ea71-355">**Keywords_finland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-356">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-356">dl#</span></span>  <br/> <span data-ttu-id="2ea71-357">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-357">driver license</span></span>  <br/> <span data-ttu-id="2ea71-358">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-358">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-359">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-359">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-360">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-360">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-361">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-362">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-363">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-364">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-364">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-365">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-365">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-366">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-366">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-367">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="2ea71-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="2ea71-369">法国</span><span class="sxs-lookup"><span data-stu-id="2ea71-369">France</span></span>

<span data-ttu-id="2ea71-370">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="2ea71-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2ea71-371">德国</span><span class="sxs-lookup"><span data-stu-id="2ea71-371">Germany</span></span>

<span data-ttu-id="2ea71-372">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="2ea71-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2ea71-373">希腊</span><span class="sxs-lookup"><span data-stu-id="2ea71-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-374">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-374">Format</span></span>

<span data-ttu-id="2ea71-375">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-376">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-376">Pattern</span></span>

 <span data-ttu-id="2ea71-377">九个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2ea71-378">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-378">Checksum</span></span>

<span data-ttu-id="2ea71-379">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-380">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-380">Definition</span></span>

<span data-ttu-id="2ea71-381">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-382">正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-383">找到了中`Keywords_greece_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-384">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-384">Keywords</span></span>

<span data-ttu-id="2ea71-385">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-385"></span></span>
|<span data-ttu-id="2ea71-386">**Keywords_greece_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-387">dlL#</span><span class="sxs-lookup"><span data-stu-id="2ea71-387">dlL#</span></span>  <br/> <span data-ttu-id="2ea71-388">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-388">driver license</span></span>  <br/> <span data-ttu-id="2ea71-389">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-389">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-390">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-390">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-391">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-391">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-392">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-393">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-394">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-395">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-395">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-396">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-396">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-397">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-397">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-398">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="2ea71-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="2ea71-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="2ea71-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="2ea71-401">匈牙利</span><span class="sxs-lookup"><span data-stu-id="2ea71-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-402">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-402">Format</span></span>

<span data-ttu-id="2ea71-403">两个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-404">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-404">Pattern</span></span>

<span data-ttu-id="2ea71-405">两个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="2ea71-406">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="2ea71-407">六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-408">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-408">Checksum</span></span>

<span data-ttu-id="2ea71-409">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-410">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-410">Definition</span></span>

<span data-ttu-id="2ea71-411">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-412">正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-413">找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-414">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-414">Keywords</span></span>

<span data-ttu-id="2ea71-415">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-415"></span></span>
|<span data-ttu-id="2ea71-416">**Keywords_hungary_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-417">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-417">dl#</span></span>  <br/> <span data-ttu-id="2ea71-418">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-418">driver license</span></span>  <br/> <span data-ttu-id="2ea71-419">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-419">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-420">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-420">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-421">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-421">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-422">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-423">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-424">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-425">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-425">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-426">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-426">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-427">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-427">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-428">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="2ea71-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="2ea71-430">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="2ea71-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-431">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-431">Format</span></span>

<span data-ttu-id="2ea71-432">6位数，后跟四个字母</span><span class="sxs-lookup"><span data-stu-id="2ea71-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-433">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-433">Pattern</span></span>

<span data-ttu-id="2ea71-434">6位数字和四个字母：</span><span class="sxs-lookup"><span data-stu-id="2ea71-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="2ea71-435">六位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-435">Six digits</span></span>
    
- <span data-ttu-id="2ea71-436">四个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-437">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-437">Checksum</span></span>

<span data-ttu-id="2ea71-438">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-439">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-439">Definition</span></span>

<span data-ttu-id="2ea71-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-441">正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-442">找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-443">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-443">Keywords</span></span>

<span data-ttu-id="2ea71-444">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-444"></span></span>
|<span data-ttu-id="2ea71-445">**Keywords_ireland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-446">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-446">dl#</span></span>  <br/> <span data-ttu-id="2ea71-447">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-447">driver license</span></span>  <br/> <span data-ttu-id="2ea71-448">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-448">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-449">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-449">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-450">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-450">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-451">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-452">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-453">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-454">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-454">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-455">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-455">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-456">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-456">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-457">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="2ea71-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="2ea71-459">意大利</span><span class="sxs-lookup"><span data-stu-id="2ea71-459">Italy</span></span>

<span data-ttu-id="2ea71-460">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="2ea71-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="2ea71-461">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="2ea71-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-462">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-462">Format</span></span>

<span data-ttu-id="2ea71-463">三个字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-464">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-464">Pattern</span></span>

<span data-ttu-id="2ea71-465">三个字母和六个数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="2ea71-466">三个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="2ea71-467">六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-468">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-468">Checksum</span></span>

<span data-ttu-id="2ea71-469">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-470">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-470">Definition</span></span>

<span data-ttu-id="2ea71-471">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-472">正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-473">找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-474">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-474">Keywords</span></span>

<span data-ttu-id="2ea71-475">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-475"></span></span>
|<span data-ttu-id="2ea71-476">**Keywords_latvia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-477">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-477">dl#</span></span>  <br/> <span data-ttu-id="2ea71-478">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-478">driver license</span></span>  <br/> <span data-ttu-id="2ea71-479">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-479">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-480">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-480">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-481">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-481">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-482">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-483">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-484">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-485">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-485">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-486">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-486">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-487">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-487">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-488">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="2ea71-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="2ea71-490">立陶宛</span><span class="sxs-lookup"><span data-stu-id="2ea71-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-491">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-491">Format</span></span>

<span data-ttu-id="2ea71-492">8位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-493">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-493">Pattern</span></span>

 <span data-ttu-id="2ea71-494">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2ea71-495">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-495">Checksum</span></span>

<span data-ttu-id="2ea71-496">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-497">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-497">Definition</span></span>

<span data-ttu-id="2ea71-498">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-499">正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-500">找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-501">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-501">Keywords</span></span>

<span data-ttu-id="2ea71-502">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-502"></span></span>
|<span data-ttu-id="2ea71-503">**Keywords_lithuania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-504">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-504">dl#</span></span>  <br/> <span data-ttu-id="2ea71-505">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-505">driver license</span></span>  <br/> <span data-ttu-id="2ea71-506">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-506">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-507">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-507">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-508">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-508">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-509">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-510">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-511">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-512">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-512">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-513">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-513">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-514">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-514">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-515">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="2ea71-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="2ea71-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="2ea71-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-518">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-518">Format</span></span>

<span data-ttu-id="2ea71-519">6位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-520">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-520">Pattern</span></span>

 <span data-ttu-id="2ea71-521">六个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2ea71-522">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-522">Checksum</span></span>

<span data-ttu-id="2ea71-523">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-524">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-524">Definition</span></span>

<span data-ttu-id="2ea71-525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-526">正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-527">找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-528">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-528">Keywords</span></span>

<span data-ttu-id="2ea71-529">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-529"></span></span>
|<span data-ttu-id="2ea71-530">**Keywords_luxemburg_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-531">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-531">dl#</span></span>  <br/> <span data-ttu-id="2ea71-532">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-532">driver license</span></span>  <br/> <span data-ttu-id="2ea71-533">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-533">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-534">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-534">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-535">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-535">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-536">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-537">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-538">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-539">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-539">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-540">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-540">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-541">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-541">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-542">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="2ea71-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="2ea71-544">马耳他</span><span class="sxs-lookup"><span data-stu-id="2ea71-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-545">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-545">Format</span></span>

<span data-ttu-id="2ea71-546">两个字符与指定模式中的六个数字的组合</span><span class="sxs-lookup"><span data-stu-id="2ea71-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-547">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-547">Pattern</span></span>

<span data-ttu-id="2ea71-548">两个字符和六个数字的组合：</span><span class="sxs-lookup"><span data-stu-id="2ea71-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="2ea71-549">两个字符（数字或字母，而不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="2ea71-550">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="2ea71-550">A space (optional)</span></span>
    
- <span data-ttu-id="2ea71-551">三个数字 </span><span class="sxs-lookup"><span data-stu-id="2ea71-551">Three digits</span></span>
    
- <span data-ttu-id="2ea71-552">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="2ea71-552">A space (optional)</span></span>
    
- <span data-ttu-id="2ea71-553">三位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-554">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-554">Checksum</span></span>

<span data-ttu-id="2ea71-555">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-556">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-556">Definition</span></span>

<span data-ttu-id="2ea71-557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-558">正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-559">找到了中`Keywords_malta_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-560">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-560">Keywords</span></span>

<span data-ttu-id="2ea71-561">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-561"></span></span>
|<span data-ttu-id="2ea71-562">**Keywords_malta_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-563">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-563">dl#</span></span>  <br/> <span data-ttu-id="2ea71-564">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-564">driver license</span></span>  <br/> <span data-ttu-id="2ea71-565">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-565">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-566">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-566">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-567">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-567">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-568">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-569">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-570">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-571">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-571">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-572">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-572">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-573">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-573">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-574">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="2ea71-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="2ea71-576">荷兰</span><span class="sxs-lookup"><span data-stu-id="2ea71-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-577">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-577">Format</span></span>

<span data-ttu-id="2ea71-578">10个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-579">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-579">Pattern</span></span>

<span data-ttu-id="2ea71-580">10 个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-581">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-581">Checksum</span></span>

<span data-ttu-id="2ea71-582">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-583">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-583">Definition</span></span>

<span data-ttu-id="2ea71-584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-585">正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-586">找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-587">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-587">Keywords</span></span>

<span data-ttu-id="2ea71-588">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-588"></span></span>
|<span data-ttu-id="2ea71-589">**Keywords_netherlands_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-590">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-590">dl#</span></span>  <br/> <span data-ttu-id="2ea71-591">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-591">driver license</span></span>  <br/> <span data-ttu-id="2ea71-592">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-592">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-593">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-593">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-594">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-594">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-595">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-596">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-597">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-598">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-598">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-599">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-599">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-600">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-600">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-601">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="2ea71-602">permis de conduire</span></span>  <br/> <span data-ttu-id="2ea71-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="2ea71-603">rijbewijs</span></span>  <br/> <span data-ttu-id="2ea71-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="2ea71-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="2ea71-605">波兰</span><span class="sxs-lookup"><span data-stu-id="2ea71-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-606">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-606">Format</span></span>

<span data-ttu-id="2ea71-607">14位数，包含2个正斜杠</span><span class="sxs-lookup"><span data-stu-id="2ea71-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-608">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-608">Pattern</span></span>

<span data-ttu-id="2ea71-609">14位数和2正斜杠：</span><span class="sxs-lookup"><span data-stu-id="2ea71-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="2ea71-610">五位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-610">Five digits</span></span> 
    
- <span data-ttu-id="2ea71-611">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="2ea71-611">A forward slash</span></span>
    
- <span data-ttu-id="2ea71-612">两位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-612">Two digits</span></span>
    
- <span data-ttu-id="2ea71-613">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="2ea71-613">A forward slash</span></span>
    
- <span data-ttu-id="2ea71-614">七个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-615">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-615">Checksum</span></span>

<span data-ttu-id="2ea71-616">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-617">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-617">Definition</span></span>

<span data-ttu-id="2ea71-618">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-619">正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-620">找到了中`Keywords_poland_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-621">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-621">Keywords</span></span>

<span data-ttu-id="2ea71-622">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-622"></span></span>
|<span data-ttu-id="2ea71-623">**Keywords_poland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-624">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-624">dl#</span></span>  <br/> <span data-ttu-id="2ea71-625">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-625">driver license</span></span>  <br/> <span data-ttu-id="2ea71-626">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-626">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-627">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-627">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-628">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-628">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-629">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-630">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-631">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-632">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-632">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-633">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-633">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-634">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-634">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-635">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="2ea71-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="2ea71-637">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="2ea71-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-638">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-638">Format</span></span>

<span data-ttu-id="2ea71-639">两个字母后跟指定模式中的七个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-640">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-640">Pattern</span></span>

<span data-ttu-id="2ea71-641">两个字母后跟七个包含特殊字符的数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="2ea71-642">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="2ea71-643">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="2ea71-643">A hyphen</span></span>
    
- <span data-ttu-id="2ea71-644">六位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-644">Six digits</span></span>
    
- <span data-ttu-id="2ea71-645">一个空格</span><span class="sxs-lookup"><span data-stu-id="2ea71-645">A space</span></span>
    
- <span data-ttu-id="2ea71-646">一个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-647">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-647">Checksum</span></span>

<span data-ttu-id="2ea71-648">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-649">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-649">Definition</span></span>

<span data-ttu-id="2ea71-650">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-651">正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-652">找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-653">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-653">Keywords</span></span>

<span data-ttu-id="2ea71-654">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-654"></span></span>
|<span data-ttu-id="2ea71-655">**Keywords_portugal_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-656">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-656">dl#</span></span>  <br/> <span data-ttu-id="2ea71-657">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-657">driver license</span></span>  <br/> <span data-ttu-id="2ea71-658">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-658">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-659">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-659">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-660">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-660">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-661">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-662">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-663">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-664">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-664">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-665">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-665">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-666">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-666">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-667">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="2ea71-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="2ea71-669">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="2ea71-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-670">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-670">Format</span></span>

<span data-ttu-id="2ea71-671">一个字符后跟八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-672">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-672">Pattern</span></span>

<span data-ttu-id="2ea71-673">一个字符后跟八个数字：</span><span class="sxs-lookup"><span data-stu-id="2ea71-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="2ea71-674">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="2ea71-675">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-676">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-676">Checksum</span></span>

<span data-ttu-id="2ea71-677">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-678">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-678">Definition</span></span>

<span data-ttu-id="2ea71-679">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-680">正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-681">找到了中`Keywords_romania_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-682">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-682">Keywords</span></span>

<span data-ttu-id="2ea71-683">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-683"></span></span>
|<span data-ttu-id="2ea71-684">**Keywords_romania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-685">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-685">dl#</span></span>  <br/> <span data-ttu-id="2ea71-686">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-686">driver license</span></span>  <br/> <span data-ttu-id="2ea71-687">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-687">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-688">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-688">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-689">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-689">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-690">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-691">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-692">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-693">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-693">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-694">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-694">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-695">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-695">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-696">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="2ea71-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="2ea71-698">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="2ea71-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-699">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-699">Format</span></span>

<span data-ttu-id="2ea71-700">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-701">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-701">Pattern</span></span>

<span data-ttu-id="2ea71-702">一个字符后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="2ea71-703">一个字母（不区分大小写）或数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="2ea71-704">七个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2ea71-705">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-705">Checksum</span></span>

<span data-ttu-id="2ea71-706">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-707">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-707">Definition</span></span>

<span data-ttu-id="2ea71-708">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-709">正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-710">找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-711">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-711">Keywords</span></span>

<span data-ttu-id="2ea71-712">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-712"></span></span>
|<span data-ttu-id="2ea71-713">**Keywords_slovakia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-714">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-714">dl#</span></span>  <br/> <span data-ttu-id="2ea71-715">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-715">driver license</span></span>  <br/> <span data-ttu-id="2ea71-716">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-716">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-717">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-717">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-718">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-718">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-719">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-720">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-721">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-722">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-722">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-723">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-723">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-724">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-724">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-725">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="2ea71-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="2ea71-727">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="2ea71-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-728">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-728">Format</span></span>

<span data-ttu-id="2ea71-729">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="2ea71-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-730">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-730">Pattern</span></span>

<span data-ttu-id="2ea71-731">九个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2ea71-732">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-732">Checksum</span></span>

<span data-ttu-id="2ea71-733">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-734">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-734">Definition</span></span>

<span data-ttu-id="2ea71-735">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-736">正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-737">找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-738">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-738">Keywords</span></span>

<span data-ttu-id="2ea71-739">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-739"></span></span>
|<span data-ttu-id="2ea71-740">**Keywords_slovenia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-741">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-741">dl#</span></span>  <br/> <span data-ttu-id="2ea71-742">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-742">driver license</span></span>  <br/> <span data-ttu-id="2ea71-743">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-743">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-744">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-744">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-745">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-745">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-746">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-747">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-748">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-749">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-749">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-750">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-750">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-751">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-751">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-752">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="2ea71-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="2ea71-754">西班牙</span><span class="sxs-lookup"><span data-stu-id="2ea71-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-755">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-755">Format</span></span>

<span data-ttu-id="2ea71-756">8位数，后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="2ea71-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-757">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-757">Pattern</span></span>

<span data-ttu-id="2ea71-758">8位数，后跟一个字符：</span><span class="sxs-lookup"><span data-stu-id="2ea71-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="2ea71-759">八个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-759">Eight digits</span></span> 
    
- <span data-ttu-id="2ea71-760">一个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="2ea71-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-761">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-761">Checksum</span></span>

<span data-ttu-id="2ea71-762">是</span><span class="sxs-lookup"><span data-stu-id="2ea71-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-763">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-763">Definition</span></span>

<span data-ttu-id="2ea71-764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-765">函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-766">找到了中`Keywords_spain_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2ea71-767">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-767">Keywords</span></span>

<span data-ttu-id="2ea71-768">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-768"></span></span>
|<span data-ttu-id="2ea71-769">**Keywords_spain_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-770">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-771">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-771">dl#</span></span>  <br/> <span data-ttu-id="2ea71-772">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-772">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-773">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-773">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-774">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-774">driver license</span></span>  <br/> <span data-ttu-id="2ea71-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-775">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-776">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-777">driver's licence</span></span>  <br/> <span data-ttu-id="2ea71-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-778">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-779">driving licence</span></span>  <br/> <span data-ttu-id="2ea71-780">driving license</span><span class="sxs-lookup"><span data-stu-id="2ea71-780">driving license</span></span>  <br/> <span data-ttu-id="2ea71-781">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-781">driver licence number</span></span>  <br/> <span data-ttu-id="2ea71-782">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-782">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-783">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-783">drivers licence number</span></span>  <br/> <span data-ttu-id="2ea71-784">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-784">drivers license number</span></span>  <br/> <span data-ttu-id="2ea71-785">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-785">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-786">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-786">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-787">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-787">driving licence number</span></span>  <br/> <span data-ttu-id="2ea71-788">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-788">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-789">促进允许</span><span class="sxs-lookup"><span data-stu-id="2ea71-789">driving permit</span></span>  <br/> <span data-ttu-id="2ea71-790">驾驶允许号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-790">driving permit number</span></span>  <br/> <span data-ttu-id="2ea71-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="2ea71-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="2ea71-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="2ea71-792">permiso conducción</span></span>  <br/> <span data-ttu-id="2ea71-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="2ea71-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="2ea71-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="2ea71-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-796">licencia conducir</span></span>  <br/> <span data-ttu-id="2ea71-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="2ea71-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="2ea71-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="2ea71-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-800">permiso conducir</span></span>  <br/> <span data-ttu-id="2ea71-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="2ea71-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="2ea71-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="2ea71-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="2ea71-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="2ea71-804">瑞典</span><span class="sxs-lookup"><span data-stu-id="2ea71-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="2ea71-805">Format</span><span class="sxs-lookup"><span data-stu-id="2ea71-805">Format</span></span>

<span data-ttu-id="2ea71-806">10个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="2ea71-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2ea71-807">模式</span><span class="sxs-lookup"><span data-stu-id="2ea71-807">Pattern</span></span>

<span data-ttu-id="2ea71-808">10位数，包含连字符：</span><span class="sxs-lookup"><span data-stu-id="2ea71-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="2ea71-809">六位数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-809">Six digits</span></span> 
    
- <span data-ttu-id="2ea71-810">一个连字符</span><span class="sxs-lookup"><span data-stu-id="2ea71-810">A hyphen</span></span>
    
- <span data-ttu-id="2ea71-811">四个数字</span><span class="sxs-lookup"><span data-stu-id="2ea71-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2ea71-812">校验和</span><span class="sxs-lookup"><span data-stu-id="2ea71-812">Checksum</span></span>

<span data-ttu-id="2ea71-813">否</span><span class="sxs-lookup"><span data-stu-id="2ea71-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="2ea71-814">定义</span><span class="sxs-lookup"><span data-stu-id="2ea71-814">Definition</span></span>

<span data-ttu-id="2ea71-815">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="2ea71-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2ea71-816">正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="2ea71-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2ea71-817">找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="2ea71-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="2ea71-818">关键字</span><span class="sxs-lookup"><span data-stu-id="2ea71-818">Keywords</span></span>

<span data-ttu-id="2ea71-819">| |</span><span class="sxs-lookup"><span data-stu-id="2ea71-819"></span></span>
|<span data-ttu-id="2ea71-820">**Keywords_sweden_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="2ea71-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="2ea71-821">通讯#</span><span class="sxs-lookup"><span data-stu-id="2ea71-821">dl#</span></span>  <br/> <span data-ttu-id="2ea71-822">driver license</span><span class="sxs-lookup"><span data-stu-id="2ea71-822">driver license</span></span>  <br/> <span data-ttu-id="2ea71-823">驱动程序许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-823">driver license number</span></span>  <br/> <span data-ttu-id="2ea71-824">驱动程序许可证</span><span class="sxs-lookup"><span data-stu-id="2ea71-824">driver licence</span></span>  <br/> <span data-ttu-id="2ea71-825">驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="2ea71-825">drivers lic.</span></span>  <br/> <span data-ttu-id="2ea71-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="2ea71-826">drivers license</span></span>  <br/> <span data-ttu-id="2ea71-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2ea71-827">drivers licence</span></span>  <br/> <span data-ttu-id="2ea71-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="2ea71-828">driver's license</span></span>  <br/> <span data-ttu-id="2ea71-829">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-829">driver's license number</span></span>  <br/> <span data-ttu-id="2ea71-830">驾驶许可证编号</span><span class="sxs-lookup"><span data-stu-id="2ea71-830">driver's licence number</span></span>  <br/> <span data-ttu-id="2ea71-831">驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="2ea71-831">driving license number</span></span>  <br/> <span data-ttu-id="2ea71-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="2ea71-832">dlno#</span></span>  <br/> <span data-ttu-id="2ea71-833">körkort</span><span class="sxs-lookup"><span data-stu-id="2ea71-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="2ea71-834">英国</span><span class="sxs-lookup"><span data-stu-id="2ea71-834">UK</span></span>

<span data-ttu-id="2ea71-835">有关详细信息，请参阅部分 "英国</span><span class="sxs-lookup"><span data-stu-id="2ea71-835">For details, see the section "U.K.</span></span> <span data-ttu-id="2ea71-836">"[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)" 中的 "驾驶执照号码"。</span><span class="sxs-lookup"><span data-stu-id="2ea71-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ea71-837">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ea71-837">See also</span></span>

[<span data-ttu-id="2ea71-838">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="2ea71-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

