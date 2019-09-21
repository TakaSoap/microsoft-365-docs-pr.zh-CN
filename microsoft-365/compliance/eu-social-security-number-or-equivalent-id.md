---
title: 欧盟社会安全号码或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时，将会查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37074865"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="04c57-104">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="04c57-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="04c57-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟社会保险号码（SSN）或等效 ID 敏感信息类型时，会查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="04c57-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="04c57-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="04c57-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="04c57-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="04c57-108">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-108">Format</span></span>

<span data-ttu-id="04c57-109">以指定格式表示的10个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-110">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-110">Pattern</span></span>

<span data-ttu-id="04c57-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="04c57-111">10 digits:</span></span>
  
-  <span data-ttu-id="04c57-112">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="04c57-113">一个校验位</span><span class="sxs-lookup"><span data-stu-id="04c57-113">One check digit</span></span>
    
- <span data-ttu-id="04c57-114">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="04c57-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-115">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-115">Checksum</span></span>

<span data-ttu-id="04c57-116">是</span><span class="sxs-lookup"><span data-stu-id="04c57-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-117">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-117">Definition</span></span>

<span data-ttu-id="04c57-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-119">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-120">找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-122">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-123">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-125">社会保障号</span><span class="sxs-lookup"><span data-stu-id="04c57-125">social security no</span></span>
  
<span data-ttu-id="04c57-126">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-126">social security number</span></span>
  
<span data-ttu-id="04c57-127">social security code</span><span class="sxs-lookup"><span data-stu-id="04c57-127">social security code</span></span>
  
<span data-ttu-id="04c57-128">保险号</span><span class="sxs-lookup"><span data-stu-id="04c57-128">insurance number</span></span>
  
<span data-ttu-id="04c57-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-129">austrian ssn</span></span>
  
<span data-ttu-id="04c57-130">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-130">ssn#</span></span>
  
<span data-ttu-id="04c57-131">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-131">ssn</span></span>
  
<span data-ttu-id="04c57-132">保险费代码</span><span class="sxs-lookup"><span data-stu-id="04c57-132">insurance code</span></span>
  
<span data-ttu-id="04c57-133">保险费代码#</span><span class="sxs-lookup"><span data-stu-id="04c57-133">insurance code#</span></span>
  
<span data-ttu-id="04c57-134">socialsecurityno#</span><span class="sxs-lookup"><span data-stu-id="04c57-134">socialsecurityno#</span></span>
  
<span data-ttu-id="04c57-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="04c57-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="04c57-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="04c57-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="04c57-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="04c57-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="04c57-138">比利时</span><span class="sxs-lookup"><span data-stu-id="04c57-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="04c57-139">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-139">Format</span></span>

<span data-ttu-id="04c57-140">11位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="04c57-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-141">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-141">Pattern</span></span>

<span data-ttu-id="04c57-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="04c57-143">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-143">Checksum</span></span>

<span data-ttu-id="04c57-144">是</span><span class="sxs-lookup"><span data-stu-id="04c57-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-145">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-145">Definition</span></span>

<span data-ttu-id="04c57-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-147">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-148">找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-150">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-151">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="04c57-153">belgian national number</span></span>
  
<span data-ttu-id="04c57-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="04c57-154">national number</span></span>
  
<span data-ttu-id="04c57-155">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-155">social security number</span></span>
  
<span data-ttu-id="04c57-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-156">nationalnumber#</span></span>
  
<span data-ttu-id="04c57-157">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-157">ssn#</span></span>
  
<span data-ttu-id="04c57-158">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-158">ssn</span></span>
  
<span data-ttu-id="04c57-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="04c57-159">nationalnumber</span></span>
  
<span data-ttu-id="04c57-160">bnn#</span><span class="sxs-lookup"><span data-stu-id="04c57-160">bnn#</span></span>
  
<span data-ttu-id="04c57-161">bnn</span><span class="sxs-lookup"><span data-stu-id="04c57-161">bnn</span></span>
  
<span data-ttu-id="04c57-162">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-162">personal id number</span></span>
  
<span data-ttu-id="04c57-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-163">personalidnumber#</span></span>
  
<span data-ttu-id="04c57-164">numéro 国家</span><span class="sxs-lookup"><span data-stu-id="04c57-164">numéro national</span></span>
  
<span data-ttu-id="04c57-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="04c57-165">numéro de sécurité</span></span>
  
<span data-ttu-id="04c57-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="04c57-166">numéro d'assuré</span></span>
  
<span data-ttu-id="04c57-167">identifiant 国家</span><span class="sxs-lookup"><span data-stu-id="04c57-167">identifiant national</span></span>
  
<span data-ttu-id="04c57-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="04c57-168">identifiantnational#</span></span>
  
<span data-ttu-id="04c57-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="04c57-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="04c57-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="04c57-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="04c57-171">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-171">Format</span></span>

<span data-ttu-id="04c57-172">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="04c57-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-173">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-173">Pattern</span></span>

 <span data-ttu-id="04c57-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="04c57-174">11 digits:</span></span> 
  
-  <span data-ttu-id="04c57-175">10位数字</span><span class="sxs-lookup"><span data-stu-id="04c57-175">Ten digits</span></span> 
    
- <span data-ttu-id="04c57-176">一个校验位</span><span class="sxs-lookup"><span data-stu-id="04c57-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-177">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-177">Checksum</span></span>

<span data-ttu-id="04c57-178">是</span><span class="sxs-lookup"><span data-stu-id="04c57-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-179">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-179">Definition</span></span>

<span data-ttu-id="04c57-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-181">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-182">找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-184">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-185">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-187">个人标识号</span><span class="sxs-lookup"><span data-stu-id="04c57-187">personal identification number</span></span>
  
<span data-ttu-id="04c57-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="04c57-188">master citizen number</span></span>
  
<span data-ttu-id="04c57-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-189">national identification number</span></span>
  
<span data-ttu-id="04c57-190">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-190">social security number</span></span>
  
<span data-ttu-id="04c57-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-191">nationalnumber#</span></span>
  
<span data-ttu-id="04c57-192">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-192">ssn#</span></span>
  
<span data-ttu-id="04c57-193">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-193">ssn</span></span>
  
<span data-ttu-id="04c57-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="04c57-194">nationalnumber</span></span>
  
<span data-ttu-id="04c57-195">bnn#</span><span class="sxs-lookup"><span data-stu-id="04c57-195">bnn#</span></span>
  
<span data-ttu-id="04c57-196">bnn</span><span class="sxs-lookup"><span data-stu-id="04c57-196">bnn</span></span>
  
<span data-ttu-id="04c57-197">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-197">personal id number</span></span>
  
<span data-ttu-id="04c57-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-198">personalidnumber#</span></span>
  
<span data-ttu-id="04c57-199">oib</span><span class="sxs-lookup"><span data-stu-id="04c57-199">oib</span></span>
  
<span data-ttu-id="04c57-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="04c57-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="04c57-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="04c57-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="04c57-202">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-202">Format</span></span>

<span data-ttu-id="04c57-203">指定模式中的10个数字和一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="04c57-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-204">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-204">Pattern</span></span>

<span data-ttu-id="04c57-205">10个数字和一个反斜杠：</span><span class="sxs-lookup"><span data-stu-id="04c57-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="04c57-206">与出生日期对应的6个数字（YYMMDD）：</span><span class="sxs-lookup"><span data-stu-id="04c57-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="04c57-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="04c57-207">A backslash</span></span>
    
- <span data-ttu-id="04c57-208">与一个序列号相对应的三个数字，用于分隔出生于同一日期的人员</span><span class="sxs-lookup"><span data-stu-id="04c57-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="04c57-209">一个校验位</span><span class="sxs-lookup"><span data-stu-id="04c57-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-210">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-210">Checksum</span></span>

<span data-ttu-id="04c57-211">是</span><span class="sxs-lookup"><span data-stu-id="04c57-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-212">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-212">Definition</span></span>

<span data-ttu-id="04c57-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-214">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-215">找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-217">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-218">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="04c57-220">birth number</span></span>
  
<span data-ttu-id="04c57-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-221">national identification number</span></span>
  
<span data-ttu-id="04c57-222">个人标识号</span><span class="sxs-lookup"><span data-stu-id="04c57-222">personal identification number</span></span>
  
<span data-ttu-id="04c57-223">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-223">social security number</span></span>
  
<span data-ttu-id="04c57-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-224">nationalnumber#</span></span>
  
<span data-ttu-id="04c57-225">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-225">ssn#</span></span>
  
<span data-ttu-id="04c57-226">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-226">ssn</span></span>
  
<span data-ttu-id="04c57-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="04c57-227">national number</span></span>
  
<span data-ttu-id="04c57-228">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-228">personal id number</span></span>
  
<span data-ttu-id="04c57-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-229">personalidnumber#</span></span>
  
<span data-ttu-id="04c57-230">rč</span><span class="sxs-lookup"><span data-stu-id="04c57-230">rč</span></span>
  
<span data-ttu-id="04c57-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="04c57-231">rodné číslo</span></span>
  
<span data-ttu-id="04c57-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="04c57-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="04c57-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="04c57-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="04c57-234">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-234">Format</span></span>

<span data-ttu-id="04c57-235">指定模式中的10个数字和一个连字符</span><span class="sxs-lookup"><span data-stu-id="04c57-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-236">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-236">Pattern</span></span>

<span data-ttu-id="04c57-237">10个数字和一个连字符：</span><span class="sxs-lookup"><span data-stu-id="04c57-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="04c57-238">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="04c57-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="04c57-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="04c57-239">A hyphen</span></span>
    
- <span data-ttu-id="04c57-240">与序列号对应的四个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-241">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-241">Checksum</span></span>

<span data-ttu-id="04c57-242">是</span><span class="sxs-lookup"><span data-stu-id="04c57-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-243">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-243">Definition</span></span>

<span data-ttu-id="04c57-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-245">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-246">找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-248">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-249">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-251">个人标识号</span><span class="sxs-lookup"><span data-stu-id="04c57-251">personal identification number</span></span>
  
<span data-ttu-id="04c57-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-252">national identification number</span></span>
  
<span data-ttu-id="04c57-253">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-253">social security number</span></span>
  
<span data-ttu-id="04c57-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-254">nationalnumber#</span></span>
  
<span data-ttu-id="04c57-255">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-255">ssn#</span></span>
  
<span data-ttu-id="04c57-256">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-256">ssn</span></span>
  
<span data-ttu-id="04c57-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="04c57-257">national number</span></span>
  
<span data-ttu-id="04c57-258">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-258">personal id number</span></span>
  
<span data-ttu-id="04c57-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-259">personalidnumber#</span></span>
  
<span data-ttu-id="04c57-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="04c57-260">cpr-nummer</span></span>
  
<span data-ttu-id="04c57-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="04c57-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="04c57-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="04c57-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="04c57-263">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-263">Format</span></span>

<span data-ttu-id="04c57-264">指定格式的11个字符的组合</span><span class="sxs-lookup"><span data-stu-id="04c57-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-265">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-265">Pattern</span></span>

<span data-ttu-id="04c57-266">指定格式的11个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="04c57-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="04c57-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="04c57-267">Six digits</span></span> 
    
- <span data-ttu-id="04c57-268">以下任一实例：</span><span class="sxs-lookup"><span data-stu-id="04c57-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="04c57-269">加号符号</span><span class="sxs-lookup"><span data-stu-id="04c57-269">Plus symbol</span></span>
    
  - <span data-ttu-id="04c57-270">负号</span><span class="sxs-lookup"><span data-stu-id="04c57-270">Minus symbol</span></span>
    
  - <span data-ttu-id="04c57-271">字母 "A" （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="04c57-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="04c57-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="04c57-272">Three digits</span></span>
    
- <span data-ttu-id="04c57-273">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-274">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-274">Checksum</span></span>

<span data-ttu-id="04c57-275">是</span><span class="sxs-lookup"><span data-stu-id="04c57-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-276">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-276">Definition</span></span>

<span data-ttu-id="04c57-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-278">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-279">找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-281">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-282">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-284">identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-284">identification number</span></span>
  
<span data-ttu-id="04c57-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="04c57-285">personal id</span></span>
  
<span data-ttu-id="04c57-286">标识号码</span><span class="sxs-lookup"><span data-stu-id="04c57-286">identity number</span></span>
  
<span data-ttu-id="04c57-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-287">finnish national id number</span></span>
  
<span data-ttu-id="04c57-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-288">personalidnumber#</span></span>
  
<span data-ttu-id="04c57-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-289">national identification number</span></span>
  
<span data-ttu-id="04c57-290">id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-290">id number</span></span>
  
<span data-ttu-id="04c57-291">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="04c57-291">national id no.</span></span>
  
<span data-ttu-id="04c57-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-292">national id number</span></span>
  
<span data-ttu-id="04c57-293">id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-293">id no</span></span>
  
<span data-ttu-id="04c57-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="04c57-294">tunnistenumero</span></span>
  
<span data-ttu-id="04c57-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="04c57-295">henkilötunnus</span></span>
  
<span data-ttu-id="04c57-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="04c57-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="04c57-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="04c57-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="04c57-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="04c57-298">identiteetti numero</span></span>
  
<span data-ttu-id="04c57-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="04c57-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="04c57-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="04c57-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="04c57-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="04c57-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="04c57-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="04c57-302">tunnusnumero</span></span>
  
<span data-ttu-id="04c57-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="04c57-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="04c57-304">hetu</span><span class="sxs-lookup"><span data-stu-id="04c57-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="04c57-305">法国</span><span class="sxs-lookup"><span data-stu-id="04c57-305">France</span></span>

<span data-ttu-id="04c57-306">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码（INSEE）" 一节。</span><span class="sxs-lookup"><span data-stu-id="04c57-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="04c57-307">德国</span><span class="sxs-lookup"><span data-stu-id="04c57-307">Germany</span></span>

<span data-ttu-id="04c57-308">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="04c57-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="04c57-309">希腊</span><span class="sxs-lookup"><span data-stu-id="04c57-309">Greece</span></span>

<span data-ttu-id="04c57-310">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="04c57-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="04c57-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="04c57-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="04c57-312">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-312">Format</span></span>

<span data-ttu-id="04c57-313">9个数字，不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="04c57-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-314">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-314">Pattern</span></span>

<span data-ttu-id="04c57-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="04c57-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="04c57-316">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-316">Checksum</span></span>

<span data-ttu-id="04c57-317">是</span><span class="sxs-lookup"><span data-stu-id="04c57-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-318">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-318">Definition</span></span>

<span data-ttu-id="04c57-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-320">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-321">找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-323">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-324">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-326">匈牙利语社会安全号码</span><span class="sxs-lookup"><span data-stu-id="04c57-326">hungarian social security number</span></span>
  
<span data-ttu-id="04c57-327">social security number</span><span class="sxs-lookup"><span data-stu-id="04c57-327">social security number</span></span>
  
<span data-ttu-id="04c57-328">socialsecuritynumber#</span><span class="sxs-lookup"><span data-stu-id="04c57-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="04c57-329">hssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-329">hssn#</span></span>
  
<span data-ttu-id="04c57-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="04c57-330">socialsecuritynno</span></span>
  
<span data-ttu-id="04c57-331">hssn</span><span class="sxs-lookup"><span data-stu-id="04c57-331">hssn</span></span>
  
<span data-ttu-id="04c57-332">taj</span><span class="sxs-lookup"><span data-stu-id="04c57-332">taj</span></span>
  
<span data-ttu-id="04c57-333">taj#</span><span class="sxs-lookup"><span data-stu-id="04c57-333">taj#</span></span>
  
<span data-ttu-id="04c57-334">ssn</span><span class="sxs-lookup"><span data-stu-id="04c57-334">ssn</span></span>
  
<span data-ttu-id="04c57-335">ssn#</span><span class="sxs-lookup"><span data-stu-id="04c57-335">ssn#</span></span>
  
<span data-ttu-id="04c57-336">社会保障号</span><span class="sxs-lookup"><span data-stu-id="04c57-336">social security no</span></span>
  
<span data-ttu-id="04c57-337">áfa</span><span class="sxs-lookup"><span data-stu-id="04c57-337">áfa</span></span>
  
<span data-ttu-id="04c57-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="04c57-338">közösségi adószám</span></span>
  
<span data-ttu-id="04c57-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="04c57-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="04c57-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="04c57-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="04c57-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="04c57-341">áfa szám</span></span>
  
<span data-ttu-id="04c57-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="04c57-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="04c57-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="04c57-343">Portugal</span></span>

<span data-ttu-id="04c57-344">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="04c57-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="04c57-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="04c57-345">Spain</span></span>

<span data-ttu-id="04c57-346">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码（SSN）" 一节。</span><span class="sxs-lookup"><span data-stu-id="04c57-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="04c57-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="04c57-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="04c57-348">Format</span><span class="sxs-lookup"><span data-stu-id="04c57-348">Format</span></span>

<span data-ttu-id="04c57-349">12个数字，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="04c57-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="04c57-350">模式</span><span class="sxs-lookup"><span data-stu-id="04c57-350">Pattern</span></span>

<span data-ttu-id="04c57-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="04c57-351">12 digits:</span></span>
  
-  <span data-ttu-id="04c57-352">与出生日期对应的8位数字（YYYYMMDD）</span><span class="sxs-lookup"><span data-stu-id="04c57-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="04c57-353">与序列号对应的三个数字，其中：</span><span class="sxs-lookup"><span data-stu-id="04c57-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="04c57-354">序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别，以及一个 "女" 的偶数号码。</span><span class="sxs-lookup"><span data-stu-id="04c57-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="04c57-355">最多1990，将序列号 corresponded 分配给在其中，号码持有者出生或（如果在1947之前出生）的县（根据纳税记录，在年1月 1947 1 日，使用特殊代码（通常为第七个数字）的特殊代码（通常为9号）immigrants</span><span class="sxs-lookup"><span data-stu-id="04c57-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="04c57-356">一个校验位</span><span class="sxs-lookup"><span data-stu-id="04c57-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="04c57-357">校验和</span><span class="sxs-lookup"><span data-stu-id="04c57-357">Checksum</span></span>

<span data-ttu-id="04c57-358">是</span><span class="sxs-lookup"><span data-stu-id="04c57-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="04c57-359">定义</span><span class="sxs-lookup"><span data-stu-id="04c57-359">Definition</span></span>

<span data-ttu-id="04c57-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-361">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="04c57-362">找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="04c57-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="04c57-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="04c57-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="04c57-364">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="04c57-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="04c57-365">关键字</span><span class="sxs-lookup"><span data-stu-id="04c57-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="04c57-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="04c57-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="04c57-367">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="04c57-367">personal id number</span></span>
  
<span data-ttu-id="04c57-368">identification number</span><span class="sxs-lookup"><span data-stu-id="04c57-368">identification number</span></span>
  
<span data-ttu-id="04c57-369">个人 id 否</span><span class="sxs-lookup"><span data-stu-id="04c57-369">personal id no</span></span>
  
<span data-ttu-id="04c57-370">identity no</span><span class="sxs-lookup"><span data-stu-id="04c57-370">identity no</span></span>
  
<span data-ttu-id="04c57-371">标识否</span><span class="sxs-lookup"><span data-stu-id="04c57-371">identification no</span></span>
  
<span data-ttu-id="04c57-372">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="04c57-372">personal identification no</span></span>
  
<span data-ttu-id="04c57-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="04c57-373">personnummer id</span></span>
  
<span data-ttu-id="04c57-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="04c57-374">personligt id-nummer</span></span>
  
<span data-ttu-id="04c57-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="04c57-375">unikt id-nummer</span></span>
  
<span data-ttu-id="04c57-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="04c57-376">personnummer</span></span>
  
<span data-ttu-id="04c57-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="04c57-377">identifikationsnumret</span></span>
  
<span data-ttu-id="04c57-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="04c57-378">personnummer#</span></span>
  
<span data-ttu-id="04c57-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="04c57-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="04c57-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04c57-380">See also</span></span>

[<span data-ttu-id="04c57-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="04c57-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

