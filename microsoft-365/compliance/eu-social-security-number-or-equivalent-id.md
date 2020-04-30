---
title: 欧盟社会安全号码或等效 ID
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时，将会查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 276b9f2d20c2c682df2a2072c1103ab9fc67a098
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938690"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="7e943-104">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="7e943-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="7e943-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟社会保险号码（SSN）或等效 ID 敏感信息类型时，会查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="7e943-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="7e943-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7e943-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="7e943-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7e943-108">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-108">Format</span></span>

<span data-ttu-id="7e943-109">以指定格式表示的10个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-110">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-110">Pattern</span></span>

<span data-ttu-id="7e943-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="7e943-111">10 digits:</span></span>
  
-  <span data-ttu-id="7e943-112">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="7e943-113">一个校验位</span><span class="sxs-lookup"><span data-stu-id="7e943-113">One check digit</span></span>
    
- <span data-ttu-id="7e943-114">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="7e943-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-115">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-115">Checksum</span></span>

<span data-ttu-id="7e943-116">是</span><span class="sxs-lookup"><span data-stu-id="7e943-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-117">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-117">Definition</span></span>

<span data-ttu-id="7e943-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-119">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-120">找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-122">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-123">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-125">社会保障号</span><span class="sxs-lookup"><span data-stu-id="7e943-125">social security no</span></span>
  
<span data-ttu-id="7e943-126">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-126">social security number</span></span>
  
<span data-ttu-id="7e943-127">social security code</span><span class="sxs-lookup"><span data-stu-id="7e943-127">social security code</span></span>
  
<span data-ttu-id="7e943-128">保险号</span><span class="sxs-lookup"><span data-stu-id="7e943-128">insurance number</span></span>
  
<span data-ttu-id="7e943-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-129">austrian ssn</span></span>
  
<span data-ttu-id="7e943-130">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-130">ssn#</span></span>
  
<span data-ttu-id="7e943-131">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-131">ssn</span></span>
  
<span data-ttu-id="7e943-132">保险费代码</span><span class="sxs-lookup"><span data-stu-id="7e943-132">insurance code</span></span>
  
<span data-ttu-id="7e943-133">保险费代码#</span><span class="sxs-lookup"><span data-stu-id="7e943-133">insurance code#</span></span>
  
<span data-ttu-id="7e943-134">socialsecurityno#</span><span class="sxs-lookup"><span data-stu-id="7e943-134">socialsecurityno#</span></span>
  
<span data-ttu-id="7e943-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7e943-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="7e943-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="7e943-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="7e943-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7e943-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="7e943-138">比利时</span><span class="sxs-lookup"><span data-stu-id="7e943-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="7e943-139">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-139">Format</span></span>

<span data-ttu-id="7e943-140">11位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="7e943-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-141">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-141">Pattern</span></span>

<span data-ttu-id="7e943-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7e943-143">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-143">Checksum</span></span>

<span data-ttu-id="7e943-144">是</span><span class="sxs-lookup"><span data-stu-id="7e943-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-145">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-145">Definition</span></span>

<span data-ttu-id="7e943-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-147">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-148">找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-150">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-151">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="7e943-153">belgian national number</span></span>
  
<span data-ttu-id="7e943-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="7e943-154">national number</span></span>
  
<span data-ttu-id="7e943-155">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-155">social security number</span></span>
  
<span data-ttu-id="7e943-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-156">nationalnumber#</span></span>
  
<span data-ttu-id="7e943-157">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-157">ssn#</span></span>
  
<span data-ttu-id="7e943-158">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-158">ssn</span></span>
  
<span data-ttu-id="7e943-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="7e943-159">nationalnumber</span></span>
  
<span data-ttu-id="7e943-160">bnn#</span><span class="sxs-lookup"><span data-stu-id="7e943-160">bnn#</span></span>
  
<span data-ttu-id="7e943-161">bnn</span><span class="sxs-lookup"><span data-stu-id="7e943-161">bnn</span></span>
  
<span data-ttu-id="7e943-162">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-162">personal id number</span></span>
  
<span data-ttu-id="7e943-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-163">personalidnumber#</span></span>
  
<span data-ttu-id="7e943-164">numéro 国家</span><span class="sxs-lookup"><span data-stu-id="7e943-164">numéro national</span></span>
  
<span data-ttu-id="7e943-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="7e943-165">numéro de sécurité</span></span>
  
<span data-ttu-id="7e943-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="7e943-166">numéro d'assuré</span></span>
  
<span data-ttu-id="7e943-167">identifiant 国家</span><span class="sxs-lookup"><span data-stu-id="7e943-167">identifiant national</span></span>
  
<span data-ttu-id="7e943-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="7e943-168">identifiantnational#</span></span>
  
<span data-ttu-id="7e943-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="7e943-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="7e943-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="7e943-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="7e943-171">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-171">Format</span></span>

<span data-ttu-id="7e943-172">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7e943-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-173">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-173">Pattern</span></span>

 <span data-ttu-id="7e943-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="7e943-174">11 digits:</span></span> 
  
-  <span data-ttu-id="7e943-175">10位数字</span><span class="sxs-lookup"><span data-stu-id="7e943-175">Ten digits</span></span> 
    
- <span data-ttu-id="7e943-176">一个校验位</span><span class="sxs-lookup"><span data-stu-id="7e943-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-177">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-177">Checksum</span></span>

<span data-ttu-id="7e943-178">是</span><span class="sxs-lookup"><span data-stu-id="7e943-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-179">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-179">Definition</span></span>

<span data-ttu-id="7e943-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-181">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-182">找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-184">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-185">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-187">个人标识号</span><span class="sxs-lookup"><span data-stu-id="7e943-187">personal identification number</span></span>
  
<span data-ttu-id="7e943-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="7e943-188">master citizen number</span></span>
  
<span data-ttu-id="7e943-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-189">national identification number</span></span>
  
<span data-ttu-id="7e943-190">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-190">social security number</span></span>
  
<span data-ttu-id="7e943-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-191">nationalnumber#</span></span>
  
<span data-ttu-id="7e943-192">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-192">ssn#</span></span>
  
<span data-ttu-id="7e943-193">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-193">ssn</span></span>
  
<span data-ttu-id="7e943-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="7e943-194">nationalnumber</span></span>
  
<span data-ttu-id="7e943-195">bnn#</span><span class="sxs-lookup"><span data-stu-id="7e943-195">bnn#</span></span>
  
<span data-ttu-id="7e943-196">bnn</span><span class="sxs-lookup"><span data-stu-id="7e943-196">bnn</span></span>
  
<span data-ttu-id="7e943-197">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-197">personal id number</span></span>
  
<span data-ttu-id="7e943-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-198">personalidnumber#</span></span>
  
<span data-ttu-id="7e943-199">oib</span><span class="sxs-lookup"><span data-stu-id="7e943-199">oib</span></span>
  
<span data-ttu-id="7e943-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="7e943-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="7e943-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="7e943-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="7e943-202">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-202">Format</span></span>

<span data-ttu-id="7e943-203">指定模式中的10个数字和一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="7e943-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-204">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-204">Pattern</span></span>

<span data-ttu-id="7e943-205">10个数字和一个反斜杠：</span><span class="sxs-lookup"><span data-stu-id="7e943-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="7e943-206">与出生日期对应的6个数字（YYMMDD）：</span><span class="sxs-lookup"><span data-stu-id="7e943-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="7e943-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="7e943-207">A backslash</span></span>
    
- <span data-ttu-id="7e943-208">与一个序列号相对应的三个数字，用于分隔出生于同一日期的人员</span><span class="sxs-lookup"><span data-stu-id="7e943-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="7e943-209">一个校验位</span><span class="sxs-lookup"><span data-stu-id="7e943-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-210">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-210">Checksum</span></span>

<span data-ttu-id="7e943-211">是</span><span class="sxs-lookup"><span data-stu-id="7e943-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-212">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-212">Definition</span></span>

<span data-ttu-id="7e943-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-214">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-215">找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-217">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-218">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="7e943-220">birth number</span></span>
  
<span data-ttu-id="7e943-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-221">national identification number</span></span>
  
<span data-ttu-id="7e943-222">个人标识号</span><span class="sxs-lookup"><span data-stu-id="7e943-222">personal identification number</span></span>
  
<span data-ttu-id="7e943-223">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-223">social security number</span></span>
  
<span data-ttu-id="7e943-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-224">nationalnumber#</span></span>
  
<span data-ttu-id="7e943-225">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-225">ssn#</span></span>
  
<span data-ttu-id="7e943-226">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-226">ssn</span></span>
  
<span data-ttu-id="7e943-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="7e943-227">national number</span></span>
  
<span data-ttu-id="7e943-228">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-228">personal id number</span></span>
  
<span data-ttu-id="7e943-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-229">personalidnumber#</span></span>
  
<span data-ttu-id="7e943-230">rč</span><span class="sxs-lookup"><span data-stu-id="7e943-230">rč</span></span>
  
<span data-ttu-id="7e943-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="7e943-231">rodné číslo</span></span>
  
<span data-ttu-id="7e943-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="7e943-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="7e943-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="7e943-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="7e943-234">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-234">Format</span></span>

<span data-ttu-id="7e943-235">指定模式中的10个数字和一个连字符</span><span class="sxs-lookup"><span data-stu-id="7e943-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-236">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-236">Pattern</span></span>

<span data-ttu-id="7e943-237">10个数字和一个连字符：</span><span class="sxs-lookup"><span data-stu-id="7e943-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="7e943-238">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="7e943-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="7e943-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="7e943-239">A hyphen</span></span>
    
- <span data-ttu-id="7e943-240">与序列号对应的四个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-241">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-241">Checksum</span></span>

<span data-ttu-id="7e943-242">是</span><span class="sxs-lookup"><span data-stu-id="7e943-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-243">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-243">Definition</span></span>

<span data-ttu-id="7e943-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-245">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-246">找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-248">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-249">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-251">个人标识号</span><span class="sxs-lookup"><span data-stu-id="7e943-251">personal identification number</span></span>
  
<span data-ttu-id="7e943-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-252">national identification number</span></span>
  
<span data-ttu-id="7e943-253">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-253">social security number</span></span>
  
<span data-ttu-id="7e943-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-254">nationalnumber#</span></span>
  
<span data-ttu-id="7e943-255">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-255">ssn#</span></span>
  
<span data-ttu-id="7e943-256">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-256">ssn</span></span>
  
<span data-ttu-id="7e943-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="7e943-257">national number</span></span>
  
<span data-ttu-id="7e943-258">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-258">personal id number</span></span>
  
<span data-ttu-id="7e943-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-259">personalidnumber#</span></span>
  
<span data-ttu-id="7e943-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="7e943-260">cpr-nummer</span></span>
  
<span data-ttu-id="7e943-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="7e943-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="7e943-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="7e943-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="7e943-263">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-263">Format</span></span>

<span data-ttu-id="7e943-264">指定格式的11个字符的组合</span><span class="sxs-lookup"><span data-stu-id="7e943-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-265">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-265">Pattern</span></span>

<span data-ttu-id="7e943-266">指定格式的11个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="7e943-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="7e943-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="7e943-267">Six digits</span></span> 
    
- <span data-ttu-id="7e943-268">以下任一实例：</span><span class="sxs-lookup"><span data-stu-id="7e943-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="7e943-269">加号符号</span><span class="sxs-lookup"><span data-stu-id="7e943-269">Plus symbol</span></span>
    
  - <span data-ttu-id="7e943-270">负号</span><span class="sxs-lookup"><span data-stu-id="7e943-270">Minus symbol</span></span>
    
  - <span data-ttu-id="7e943-271">字母 "A" （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="7e943-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="7e943-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="7e943-272">Three digits</span></span>
    
- <span data-ttu-id="7e943-273">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-274">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-274">Checksum</span></span>

<span data-ttu-id="7e943-275">是</span><span class="sxs-lookup"><span data-stu-id="7e943-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-276">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-276">Definition</span></span>

<span data-ttu-id="7e943-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-278">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-279">找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-281">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-282">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-284">identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-284">identification number</span></span>
  
<span data-ttu-id="7e943-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="7e943-285">personal id</span></span>
  
<span data-ttu-id="7e943-286">标识号码</span><span class="sxs-lookup"><span data-stu-id="7e943-286">identity number</span></span>
  
<span data-ttu-id="7e943-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-287">finnish national id number</span></span>
  
<span data-ttu-id="7e943-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-288">personalidnumber#</span></span>
  
<span data-ttu-id="7e943-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-289">national identification number</span></span>
  
<span data-ttu-id="7e943-290">id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-290">id number</span></span>
  
<span data-ttu-id="7e943-291">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="7e943-291">national id no.</span></span>
  
<span data-ttu-id="7e943-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-292">national id number</span></span>
  
<span data-ttu-id="7e943-293">id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-293">id no</span></span>
  
<span data-ttu-id="7e943-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7e943-294">tunnistenumero</span></span>
  
<span data-ttu-id="7e943-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7e943-295">henkilötunnus</span></span>
  
<span data-ttu-id="7e943-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7e943-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="7e943-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="7e943-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="7e943-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="7e943-298">identiteetti numero</span></span>
  
<span data-ttu-id="7e943-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7e943-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="7e943-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="7e943-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="7e943-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7e943-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="7e943-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="7e943-302">tunnusnumero</span></span>
  
<span data-ttu-id="7e943-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="7e943-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="7e943-304">hetu</span><span class="sxs-lookup"><span data-stu-id="7e943-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="7e943-305">法国</span><span class="sxs-lookup"><span data-stu-id="7e943-305">France</span></span>

<span data-ttu-id="7e943-306">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码（INSEE）" 一节。</span><span class="sxs-lookup"><span data-stu-id="7e943-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="7e943-307">德国</span><span class="sxs-lookup"><span data-stu-id="7e943-307">Germany</span></span>

<span data-ttu-id="7e943-308">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="7e943-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="7e943-309">希腊</span><span class="sxs-lookup"><span data-stu-id="7e943-309">Greece</span></span>

<span data-ttu-id="7e943-310">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="7e943-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="7e943-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="7e943-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7e943-312">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-312">Format</span></span>

<span data-ttu-id="7e943-313">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7e943-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-314">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-314">Pattern</span></span>

<span data-ttu-id="7e943-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="7e943-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7e943-316">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-316">Checksum</span></span>

<span data-ttu-id="7e943-317">是</span><span class="sxs-lookup"><span data-stu-id="7e943-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-318">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-318">Definition</span></span>

<span data-ttu-id="7e943-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-320">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-321">找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-323">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-324">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-326">匈牙利语社会安全号码</span><span class="sxs-lookup"><span data-stu-id="7e943-326">hungarian social security number</span></span>
  
<span data-ttu-id="7e943-327">social security number</span><span class="sxs-lookup"><span data-stu-id="7e943-327">social security number</span></span>
  
<span data-ttu-id="7e943-328">socialsecuritynumber#</span><span class="sxs-lookup"><span data-stu-id="7e943-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="7e943-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-329">hssn#</span></span>
  
<span data-ttu-id="7e943-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="7e943-330">socialsecuritynno</span></span>
  
<span data-ttu-id="7e943-331">hssn</span><span class="sxs-lookup"><span data-stu-id="7e943-331">hssn</span></span>
  
<span data-ttu-id="7e943-332">taj</span><span class="sxs-lookup"><span data-stu-id="7e943-332">taj</span></span>
  
<span data-ttu-id="7e943-333">taj#</span><span class="sxs-lookup"><span data-stu-id="7e943-333">taj#</span></span>
  
<span data-ttu-id="7e943-334">ssn</span><span class="sxs-lookup"><span data-stu-id="7e943-334">ssn</span></span>
  
<span data-ttu-id="7e943-335">ssn#</span><span class="sxs-lookup"><span data-stu-id="7e943-335">ssn#</span></span>
  
<span data-ttu-id="7e943-336">社会保障号</span><span class="sxs-lookup"><span data-stu-id="7e943-336">social security no</span></span>
  
<span data-ttu-id="7e943-337">áfa</span><span class="sxs-lookup"><span data-stu-id="7e943-337">áfa</span></span>
  
<span data-ttu-id="7e943-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="7e943-338">közösségi adószám</span></span>
  
<span data-ttu-id="7e943-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="7e943-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="7e943-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="7e943-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="7e943-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="7e943-341">áfa szám</span></span>
  
<span data-ttu-id="7e943-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="7e943-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="7e943-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="7e943-343">Portugal</span></span>

<span data-ttu-id="7e943-344">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="7e943-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="7e943-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="7e943-345">Spain</span></span>

<span data-ttu-id="7e943-346">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码（SSN）" 一节。</span><span class="sxs-lookup"><span data-stu-id="7e943-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="7e943-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="7e943-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="7e943-348">Format</span><span class="sxs-lookup"><span data-stu-id="7e943-348">Format</span></span>

<span data-ttu-id="7e943-349">12个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="7e943-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7e943-350">模式</span><span class="sxs-lookup"><span data-stu-id="7e943-350">Pattern</span></span>

<span data-ttu-id="7e943-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="7e943-351">12 digits:</span></span>
  
-  <span data-ttu-id="7e943-352">与出生日期对应的8位数字（YYYYMMDD）</span><span class="sxs-lookup"><span data-stu-id="7e943-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="7e943-353">与序列号对应的三个数字，其中：</span><span class="sxs-lookup"><span data-stu-id="7e943-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="7e943-354">序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别，以及一个 "女" 的偶数号码。</span><span class="sxs-lookup"><span data-stu-id="7e943-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="7e943-355">最多1990，将序列号的分配 corresponded 到在其中，号码持有者出生或（如果在1947之前出生）的县，在此之前/她已经在其居住的地方（如果是在之前），对于 immigrants，使用特殊代码（通常为9的1947第七位数字）。</span><span class="sxs-lookup"><span data-stu-id="7e943-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="7e943-356">一个校验位</span><span class="sxs-lookup"><span data-stu-id="7e943-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7e943-357">校验和</span><span class="sxs-lookup"><span data-stu-id="7e943-357">Checksum</span></span>

<span data-ttu-id="7e943-358">是</span><span class="sxs-lookup"><span data-stu-id="7e943-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7e943-359">定义</span><span class="sxs-lookup"><span data-stu-id="7e943-359">Definition</span></span>

<span data-ttu-id="7e943-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-361">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7e943-362">找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="7e943-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7e943-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="7e943-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7e943-364">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="7e943-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e943-365">关键字</span><span class="sxs-lookup"><span data-stu-id="7e943-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="7e943-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7e943-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7e943-367">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="7e943-367">personal id number</span></span>
  
<span data-ttu-id="7e943-368">identification number</span><span class="sxs-lookup"><span data-stu-id="7e943-368">identification number</span></span>
  
<span data-ttu-id="7e943-369">个人 id 否</span><span class="sxs-lookup"><span data-stu-id="7e943-369">personal id no</span></span>
  
<span data-ttu-id="7e943-370">identity no</span><span class="sxs-lookup"><span data-stu-id="7e943-370">identity no</span></span>
  
<span data-ttu-id="7e943-371">标识否</span><span class="sxs-lookup"><span data-stu-id="7e943-371">identification no</span></span>
  
<span data-ttu-id="7e943-372">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="7e943-372">personal identification no</span></span>
  
<span data-ttu-id="7e943-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="7e943-373">personnummer id</span></span>
  
<span data-ttu-id="7e943-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="7e943-374">personligt id-nummer</span></span>
  
<span data-ttu-id="7e943-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="7e943-375">unikt id-nummer</span></span>
  
<span data-ttu-id="7e943-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="7e943-376">personnummer</span></span>
  
<span data-ttu-id="7e943-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="7e943-377">identifikationsnumret</span></span>
  
<span data-ttu-id="7e943-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="7e943-378">personnummer#</span></span>
  
<span data-ttu-id="7e943-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="7e943-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7e943-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e943-380">See also</span></span>

[<span data-ttu-id="7e943-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="7e943-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

