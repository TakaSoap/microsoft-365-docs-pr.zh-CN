---
title: 欧盟国家身份证号
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
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: c83644fc8870975634651e44e114f2a8e0cf7692
ms.sourcegitcommit: a2dd93943f68362220b123e3e4b0f7b3facbdd03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43955299"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="60258-104">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="60258-104">EU National Identification Number</span></span>

<span data-ttu-id="60258-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。</span><span class="sxs-lookup"><span data-stu-id="60258-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="60258-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="60258-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="60258-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="60258-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="60258-108">Format</span><span class="sxs-lookup"><span data-stu-id="60258-108">Format</span></span>

<span data-ttu-id="60258-109">字母、数字和特殊字符的24个字符的组合</span><span class="sxs-lookup"><span data-stu-id="60258-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-110">模式</span><span class="sxs-lookup"><span data-stu-id="60258-110">Pattern</span></span>

<span data-ttu-id="60258-111">24个字符：</span><span class="sxs-lookup"><span data-stu-id="60258-111">24 characters:</span></span>
  
-  <span data-ttu-id="60258-112">22个字母（不区分大小写）、数字、反斜杠、正斜杠或加号</span><span class="sxs-lookup"><span data-stu-id="60258-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="60258-113">两个字母（不区分大小写）、数字、反斜杠、正斜杠、加号或等号</span><span class="sxs-lookup"><span data-stu-id="60258-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-114">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-114">Checksum</span></span>

<span data-ttu-id="60258-115">不适用</span><span class="sxs-lookup"><span data-stu-id="60258-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-116">定义</span><span class="sxs-lookup"><span data-stu-id="60258-116">Definition</span></span>

<span data-ttu-id="60258-117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-118">正则表达式`Regex_austria_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-119">找到了中`Keywords_austria_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-120">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="60258-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="60258-122">奥地利身份证号码</span><span class="sxs-lookup"><span data-stu-id="60258-122">austrian identity number</span></span>
  
<span data-ttu-id="60258-123">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="60258-123">national identity number</span></span>
  
<span data-ttu-id="60258-124">标识号码</span><span class="sxs-lookup"><span data-stu-id="60258-124">identity number</span></span>
  
<span data-ttu-id="60258-125">national id</span><span class="sxs-lookup"><span data-stu-id="60258-125">national id</span></span>
  
<span data-ttu-id="60258-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="60258-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="60258-127">比利时</span><span class="sxs-lookup"><span data-stu-id="60258-127">Belgium</span></span>

<span data-ttu-id="60258-128">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "比利时国家数" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="60258-129">保加利亚</span><span class="sxs-lookup"><span data-stu-id="60258-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="60258-130">Format</span><span class="sxs-lookup"><span data-stu-id="60258-130">Format</span></span>

<span data-ttu-id="60258-131">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-132">模式</span><span class="sxs-lookup"><span data-stu-id="60258-132">Pattern</span></span>

<span data-ttu-id="60258-133">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="60258-134">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="60258-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="60258-135">与出生顺序对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="60258-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="60258-136">与性别对应的一位数字：男的偶数位和用于女的奇数位</span><span class="sxs-lookup"><span data-stu-id="60258-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="60258-137">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-138">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-138">Checksum</span></span>

<span data-ttu-id="60258-139">是</span><span class="sxs-lookup"><span data-stu-id="60258-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-140">定义</span><span class="sxs-lookup"><span data-stu-id="60258-140">Definition</span></span>

<span data-ttu-id="60258-141">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-142">函数`Func_bulgaria_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-142">The function  `Func_bulgaria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-143">找到了中`Keywords_bulgaria_national_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="60258-144">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-145">函数`Func_bulgaria_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-145">The function  `Func_bulgaria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-146">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="60258-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="60258-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="60258-148">egn</span><span class="sxs-lookup"><span data-stu-id="60258-148">egn</span></span>
  
<span data-ttu-id="60258-149">egn#</span><span class="sxs-lookup"><span data-stu-id="60258-149">egn#</span></span>
  
<span data-ttu-id="60258-150">保加利亚语国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="60258-150">bulgarian national number</span></span>
  
<span data-ttu-id="60258-151">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="60258-151">national number</span></span>
  
<span data-ttu-id="60258-152">social security number</span><span class="sxs-lookup"><span data-stu-id="60258-152">social security number</span></span>
  
<span data-ttu-id="60258-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-153">nationalnumber#</span></span>
  
<span data-ttu-id="60258-154">ssn#</span><span class="sxs-lookup"><span data-stu-id="60258-154">ssn#</span></span>
  
<span data-ttu-id="60258-155">ssn</span><span class="sxs-lookup"><span data-stu-id="60258-155">ssn</span></span>
  
<span data-ttu-id="60258-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="60258-156">nationalnumber</span></span>
  
<span data-ttu-id="60258-157">bnn#</span><span class="sxs-lookup"><span data-stu-id="60258-157">bnn#</span></span>
  
<span data-ttu-id="60258-158">bnn</span><span class="sxs-lookup"><span data-stu-id="60258-158">bnn</span></span>
  
<span data-ttu-id="60258-159">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-159">personal id number</span></span>
  
<span data-ttu-id="60258-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-160">personalidnumber#</span></span>
  
<span data-ttu-id="60258-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="60258-161">единен граждански номер</span></span>
  
<span data-ttu-id="60258-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="60258-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="60258-163">егн</span><span class="sxs-lookup"><span data-stu-id="60258-163">егн</span></span>
  
<span data-ttu-id="60258-164">егн#</span><span class="sxs-lookup"><span data-stu-id="60258-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="60258-165">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="60258-165">Croatia</span></span>

<span data-ttu-id="60258-166">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分中的 "克罗地亚恒等号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="60258-167">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="60258-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="60258-168">Format</span><span class="sxs-lookup"><span data-stu-id="60258-168">Format</span></span>

<span data-ttu-id="60258-169">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-170">模式</span><span class="sxs-lookup"><span data-stu-id="60258-170">Pattern</span></span>

 <span data-ttu-id="60258-171">10位数字</span><span class="sxs-lookup"><span data-stu-id="60258-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="60258-172">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-172">Checksum</span></span>

<span data-ttu-id="60258-173">不适用</span><span class="sxs-lookup"><span data-stu-id="60258-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-174">定义</span><span class="sxs-lookup"><span data-stu-id="60258-174">Definition</span></span>

<span data-ttu-id="60258-175">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-176">正则表达式`Regex_cyprus_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-177">找到了中`Keywords_cyprus_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-178">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="60258-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="60258-180">id 卡号</span><span class="sxs-lookup"><span data-stu-id="60258-180">id card number</span></span>
  
<span data-ttu-id="60258-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="60258-181">national identification number</span></span>
  
<span data-ttu-id="60258-182">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-182">personal id number</span></span>
  
<span data-ttu-id="60258-183">标识卡号</span><span class="sxs-lookup"><span data-stu-id="60258-183">identity card number</span></span>
  
<span data-ttu-id="60258-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="60258-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="60258-185">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="60258-185">Czech Republic</span></span>

<span data-ttu-id="60258-186">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "捷克国家身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="60258-187">丹麦</span><span class="sxs-lookup"><span data-stu-id="60258-187">Denmark</span></span>

<span data-ttu-id="60258-188">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "丹麦个人识别码" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="60258-189">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="60258-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="60258-190">Format</span><span class="sxs-lookup"><span data-stu-id="60258-190">Format</span></span>

<span data-ttu-id="60258-191">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-192">模式</span><span class="sxs-lookup"><span data-stu-id="60258-192">Pattern</span></span>

<span data-ttu-id="60258-193">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="60258-193">11 digits:</span></span>
  
- <span data-ttu-id="60258-194">一种数字，对应于性别和出生世纪（奇数号男，甚至是数字女; 1-2：19世纪; 3-4：20世纪; 5-6：21世纪）</span><span class="sxs-lookup"><span data-stu-id="60258-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="60258-195">六个数字，对应于出生日期（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="60258-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="60258-196">三个数字，对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="60258-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="60258-197">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-198">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-198">Checksum</span></span>

<span data-ttu-id="60258-199">是</span><span class="sxs-lookup"><span data-stu-id="60258-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-200">定义</span><span class="sxs-lookup"><span data-stu-id="60258-200">Definition</span></span>

<span data-ttu-id="60258-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-202">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-203">找到了中`Keywords_estonia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-204">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-205">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-206">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="60258-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="60258-208">个人标识代码</span><span class="sxs-lookup"><span data-stu-id="60258-208">personal identification code</span></span>
  
<span data-ttu-id="60258-209">个人标识号</span><span class="sxs-lookup"><span data-stu-id="60258-209">personal identification number</span></span>
  
<span data-ttu-id="60258-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="60258-210">national identification number</span></span>
  
<span data-ttu-id="60258-211">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="60258-211">national number</span></span>
  
<span data-ttu-id="60258-212">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-212">personal id number</span></span>
  
<span data-ttu-id="60258-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-213">personalidnumber#</span></span>
  
<span data-ttu-id="60258-214">ik</span><span class="sxs-lookup"><span data-stu-id="60258-214">ik</span></span>
  
<span data-ttu-id="60258-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="60258-215">isikukood</span></span>
  
<span data-ttu-id="60258-216">id-kaart</span><span class="sxs-lookup"><span data-stu-id="60258-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="60258-217">芬兰</span><span class="sxs-lookup"><span data-stu-id="60258-217">Finland</span></span>

<span data-ttu-id="60258-218">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰国 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="60258-219">法国</span><span class="sxs-lookup"><span data-stu-id="60258-219">France</span></span>

<span data-ttu-id="60258-220">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国国家 ID 卡（CNI）" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="60258-221">德国</span><span class="sxs-lookup"><span data-stu-id="60258-221">Germany</span></span>

<span data-ttu-id="60258-222">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="60258-223">希腊</span><span class="sxs-lookup"><span data-stu-id="60258-223">Greece</span></span>

<span data-ttu-id="60258-224">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="60258-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="60258-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="60258-226">Format</span><span class="sxs-lookup"><span data-stu-id="60258-226">Format</span></span>

<span data-ttu-id="60258-227">11 个数字</span><span class="sxs-lookup"><span data-stu-id="60258-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-228">模式</span><span class="sxs-lookup"><span data-stu-id="60258-228">Pattern</span></span>

<span data-ttu-id="60258-229">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="60258-229">11 digits:</span></span>
  
-  <span data-ttu-id="60258-230">一种与性别对应的数字（1--男，2-母，其他号码也适用于在两个公民前出生的公民的1900或公民）</span><span class="sxs-lookup"><span data-stu-id="60258-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="60258-231">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="60258-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="60258-232">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="60258-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="60258-233">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-234">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-234">Checksum</span></span>

<span data-ttu-id="60258-235">是</span><span class="sxs-lookup"><span data-stu-id="60258-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-236">定义</span><span class="sxs-lookup"><span data-stu-id="60258-236">Definition</span></span>

<span data-ttu-id="60258-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-238">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-239">找到了中`Keywords_hungary_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-240">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-241">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-242">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="60258-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="60258-244">个人标识号</span><span class="sxs-lookup"><span data-stu-id="60258-244">personal identification number</span></span>
  
<span data-ttu-id="60258-245">identification number</span><span class="sxs-lookup"><span data-stu-id="60258-245">identification number</span></span>
  
<span data-ttu-id="60258-246">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-246">personal id number</span></span>
  
<span data-ttu-id="60258-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="60258-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="60258-248">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="60258-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="60258-249">Format</span><span class="sxs-lookup"><span data-stu-id="60258-249">Format</span></span>

<span data-ttu-id="60258-250">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="60258-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-251">模式</span><span class="sxs-lookup"><span data-stu-id="60258-251">Pattern</span></span>

<span data-ttu-id="60258-252">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="60258-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="60258-253">从01年1月2013到现在：</span><span class="sxs-lookup"><span data-stu-id="60258-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="60258-254">七个数字 </span><span class="sxs-lookup"><span data-stu-id="60258-254">Seven digits</span></span> 
    
- <span data-ttu-id="60258-255">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-255">One check digit</span></span>
    
- <span data-ttu-id="60258-256">一个空格或大写的字母 "W" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="60258-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="60258-257">在01月1日之前1月2013：</span><span class="sxs-lookup"><span data-stu-id="60258-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="60258-258">七个数字 </span><span class="sxs-lookup"><span data-stu-id="60258-258">Seven digits</span></span> 
    
- <span data-ttu-id="60258-259">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-259">One check digit</span></span>
    
- <span data-ttu-id="60258-260">一个空格或大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="60258-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-261">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-261">Checksum</span></span>

<span data-ttu-id="60258-262">是</span><span class="sxs-lookup"><span data-stu-id="60258-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-263">定义</span><span class="sxs-lookup"><span data-stu-id="60258-263">Definition</span></span>

<span data-ttu-id="60258-264">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-265">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="60258-266">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-266">A keyword from is found.</span></span>
    
<span data-ttu-id="60258-267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-268">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-269">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="60258-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="60258-271">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="60258-271">personal public service number</span></span>
  
<span data-ttu-id="60258-272">pps no</span><span class="sxs-lookup"><span data-stu-id="60258-272">pps no</span></span>
  
<span data-ttu-id="60258-273">收入和社会保险电话号码</span><span class="sxs-lookup"><span data-stu-id="60258-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="60258-274">rsi no</span><span class="sxs-lookup"><span data-stu-id="60258-274">rsi no</span></span>
  
<span data-ttu-id="60258-275">个人标识号</span><span class="sxs-lookup"><span data-stu-id="60258-275">personal identification number</span></span>
  
<span data-ttu-id="60258-276">identification number</span><span class="sxs-lookup"><span data-stu-id="60258-276">identification number</span></span>
  
<span data-ttu-id="60258-277">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-277">personal id number</span></span>
  
<span data-ttu-id="60258-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="60258-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="60258-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="60258-279">uimh.</span></span> <span data-ttu-id="60258-280">psp</span><span class="sxs-lookup"><span data-stu-id="60258-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="60258-281">意大利</span><span class="sxs-lookup"><span data-stu-id="60258-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="60258-282">Format</span><span class="sxs-lookup"><span data-stu-id="60258-282">Format</span></span>

<span data-ttu-id="60258-283">在指定模式中，由16个字符组成的字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="60258-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-284">模式</span><span class="sxs-lookup"><span data-stu-id="60258-284">Pattern</span></span>

<span data-ttu-id="60258-285">字母和数字的16个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="60258-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="60258-286">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="60258-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="60258-287">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="60258-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="60258-288">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="60258-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="60258-289">一个与出生月份的字母对应的字母–字母按字母顺序使用，但仅使用字母 A 到 E、H、L、M、P、R 和 T （因此，一月为 A，10月为 R）</span><span class="sxs-lookup"><span data-stu-id="60258-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="60258-290">与出生月份的某一天对应的两个数字，为了区分 genders，40已添加到女性的出生日。</span><span class="sxs-lookup"><span data-stu-id="60258-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="60258-291">与专用于 municipality 的区域代码相对应的四个数字（国家/地区内的国家/地区代码适用于外国国家）</span><span class="sxs-lookup"><span data-stu-id="60258-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="60258-292">一个奇偶校验数字</span><span class="sxs-lookup"><span data-stu-id="60258-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-293">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-293">Checksum</span></span>

<span data-ttu-id="60258-294">是</span><span class="sxs-lookup"><span data-stu-id="60258-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-295">定义</span><span class="sxs-lookup"><span data-stu-id="60258-295">Definition</span></span>

<span data-ttu-id="60258-296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-297">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-298">找到了中`Keywords_italy_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-299">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-300">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-301">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="60258-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="60258-303">个人代码</span><span class="sxs-lookup"><span data-stu-id="60258-303">personal code</span></span>
  
<span data-ttu-id="60258-304">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="60258-304">personal code number</span></span>
  
<span data-ttu-id="60258-305">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="60258-305">personal certificate number</span></span>
  
<span data-ttu-id="60258-306">会计代码</span><span class="sxs-lookup"><span data-stu-id="60258-306">fiscal code</span></span>
  
<span data-ttu-id="60258-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="60258-307">personalcodeno#</span></span>
  
<span data-ttu-id="60258-308">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-308">personal id number</span></span>
  
<span data-ttu-id="60258-309">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="60258-309">personal id code</span></span>
  
<span data-ttu-id="60258-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="60258-310">codice personale</span></span>
  
<span data-ttu-id="60258-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="60258-311">numero certificato personale</span></span>
  
<span data-ttu-id="60258-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="60258-312">numero personale</span></span>
  
<span data-ttu-id="60258-313">numero id personale</span><span class="sxs-lookup"><span data-stu-id="60258-313">numero id personale</span></span>
  
<span data-ttu-id="60258-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="60258-314">codice id personale</span></span>
  
<span data-ttu-id="60258-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="60258-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="60258-316">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="60258-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="60258-317">Format</span><span class="sxs-lookup"><span data-stu-id="60258-317">Format</span></span>

<span data-ttu-id="60258-318">11位数字和指定格式的连字符</span><span class="sxs-lookup"><span data-stu-id="60258-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-319">模式</span><span class="sxs-lookup"><span data-stu-id="60258-319">Pattern</span></span>

<span data-ttu-id="60258-320">11个数字和一个连字符：</span><span class="sxs-lookup"><span data-stu-id="60258-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="60258-321">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="60258-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="60258-322">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="60258-322">A hyphen</span></span>
    
- <span data-ttu-id="60258-323">一个数字，对应于出生世纪（"0" 表示19世纪，"1" 表示20世纪，"2" 表示21世纪）</span><span class="sxs-lookup"><span data-stu-id="60258-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="60258-324">四个数字，随机生成</span><span class="sxs-lookup"><span data-stu-id="60258-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-325">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-325">Checksum</span></span>

<span data-ttu-id="60258-326">是</span><span class="sxs-lookup"><span data-stu-id="60258-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-327">定义</span><span class="sxs-lookup"><span data-stu-id="60258-327">Definition</span></span>

<span data-ttu-id="60258-328">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-329">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-330">找到了中`Keywords_latvia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-331">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-332">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-333">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="60258-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="60258-335">个人代码</span><span class="sxs-lookup"><span data-stu-id="60258-335">personal code</span></span>
  
<span data-ttu-id="60258-336">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="60258-336">personal code number</span></span>
  
<span data-ttu-id="60258-337">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="60258-337">personal certificate number</span></span>
  
<span data-ttu-id="60258-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="60258-338">personalcodeno#</span></span>
  
<span data-ttu-id="60258-339">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-339">personal id number</span></span>
  
<span data-ttu-id="60258-340">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="60258-340">personal id code</span></span>
  
<span data-ttu-id="60258-341">角色 kods</span><span class="sxs-lookup"><span data-stu-id="60258-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="60258-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="60258-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="60258-343">Format</span><span class="sxs-lookup"><span data-stu-id="60258-343">Format</span></span>

<span data-ttu-id="60258-344">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-345">模式</span><span class="sxs-lookup"><span data-stu-id="60258-345">Pattern</span></span>

<span data-ttu-id="60258-346">11个数字，不含空格和分隔符：</span><span class="sxs-lookup"><span data-stu-id="60258-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="60258-347">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="60258-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="60258-348">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="60258-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="60258-349">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="60258-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="60258-350">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-351">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-351">Checksum</span></span>

<span data-ttu-id="60258-352">是</span><span class="sxs-lookup"><span data-stu-id="60258-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-353">定义</span><span class="sxs-lookup"><span data-stu-id="60258-353">Definition</span></span>

<span data-ttu-id="60258-354">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-355">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-356">找到了中`Keywords_lithuania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-357">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-358">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-359">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="60258-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="60258-361">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="60258-361">personal numeric code</span></span>
  
<span data-ttu-id="60258-362">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-362">unique identification number</span></span>
  
<span data-ttu-id="60258-363">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="60258-363">citizen service number</span></span>
  
<span data-ttu-id="60258-364">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-364">unique identity number</span></span>
  
<span data-ttu-id="60258-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="60258-366">个人代码。</span><span class="sxs-lookup"><span data-stu-id="60258-366">personal code.</span></span>
  
<span data-ttu-id="60258-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="60258-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="60258-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="60258-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="60258-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="60258-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="60258-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="60258-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="60258-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="60258-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="60258-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="60258-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="60258-373">Format</span><span class="sxs-lookup"><span data-stu-id="60258-373">Format</span></span>

<span data-ttu-id="60258-374">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-375">模式</span><span class="sxs-lookup"><span data-stu-id="60258-375">Pattern</span></span>

<span data-ttu-id="60258-376">11 个数字</span><span class="sxs-lookup"><span data-stu-id="60258-376">11 digits</span></span>
  
- <span data-ttu-id="60258-377">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="60258-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="60258-378">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="60258-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="60258-379">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="60258-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="60258-380">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-381">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-381">Checksum</span></span>

<span data-ttu-id="60258-382">不适用</span><span class="sxs-lookup"><span data-stu-id="60258-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-383">定义</span><span class="sxs-lookup"><span data-stu-id="60258-383">Definition</span></span>

<span data-ttu-id="60258-384">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-385">正则表达式`Regex_luxemburg_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-386">找到了中`Keywords_luxemburg_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-387">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="60258-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="60258-389">个人 id</span><span class="sxs-lookup"><span data-stu-id="60258-389">personal id</span></span>
  
<span data-ttu-id="60258-390">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-390">personal id number</span></span>
  
<span data-ttu-id="60258-391">personalidno#</span><span class="sxs-lookup"><span data-stu-id="60258-391">personalidno#</span></span>
  
<span data-ttu-id="60258-392">唯一 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-392">unique id number</span></span>
  
<span data-ttu-id="60258-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-393">personalidnumber#</span></span>
  
<span data-ttu-id="60258-394">唯一 id 键</span><span class="sxs-lookup"><span data-stu-id="60258-394">unique id key</span></span>
  
<span data-ttu-id="60258-395">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="60258-395">personal id code</span></span>
  
<span data-ttu-id="60258-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="60258-396">uniqueidkey#</span></span>
  
<span data-ttu-id="60258-397">单个代码</span><span class="sxs-lookup"><span data-stu-id="60258-397">individual code</span></span>
  
<span data-ttu-id="60258-398">个人 id</span><span class="sxs-lookup"><span data-stu-id="60258-398">individual id</span></span>
  
<span data-ttu-id="60258-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="60258-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="60258-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="60258-400">eindeutige id</span></span>
  
<span data-ttu-id="60258-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="60258-401">id personnelle</span></span>
  
<span data-ttu-id="60258-402">numéro d'identification 人员</span><span class="sxs-lookup"><span data-stu-id="60258-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="60258-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="60258-403">idpersonnelle#</span></span>
  
<span data-ttu-id="60258-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="60258-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="60258-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="60258-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="60258-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="60258-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="60258-407">Format</span><span class="sxs-lookup"><span data-stu-id="60258-407">Format</span></span>

<span data-ttu-id="60258-408">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="60258-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-409">模式</span><span class="sxs-lookup"><span data-stu-id="60258-409">Pattern</span></span>

<span data-ttu-id="60258-410">七位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="60258-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="60258-411">七个数字 </span><span class="sxs-lookup"><span data-stu-id="60258-411">Seven digits</span></span> 
    
- <span data-ttu-id="60258-412">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="60258-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-413">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-413">Checksum</span></span>

<span data-ttu-id="60258-414">不适用</span><span class="sxs-lookup"><span data-stu-id="60258-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-415">定义</span><span class="sxs-lookup"><span data-stu-id="60258-415">Definition</span></span>

<span data-ttu-id="60258-416">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-417">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-418">找到了中`Keywords_malta_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-419">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-420">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-421">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="60258-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="60258-423">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="60258-423">personal numeric code</span></span>
  
<span data-ttu-id="60258-424">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-424">unique identification number</span></span>
  
<span data-ttu-id="60258-425">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="60258-425">citizen service number</span></span>
  
<span data-ttu-id="60258-426">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-426">unique identity number</span></span>
  
<span data-ttu-id="60258-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="60258-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="60258-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="60258-429">numru ta "identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="60258-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="60258-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="60258-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="60258-431">numru ta "identità uniku</span><span class="sxs-lookup"><span data-stu-id="60258-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="60258-432">荷兰</span><span class="sxs-lookup"><span data-stu-id="60258-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="60258-433">Format</span><span class="sxs-lookup"><span data-stu-id="60258-433">Format</span></span>

<span data-ttu-id="60258-434">9个数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-435">模式</span><span class="sxs-lookup"><span data-stu-id="60258-435">Pattern</span></span>

<span data-ttu-id="60258-436">九个数字</span><span class="sxs-lookup"><span data-stu-id="60258-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="60258-437">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-437">Checksum</span></span>

<span data-ttu-id="60258-438">是</span><span class="sxs-lookup"><span data-stu-id="60258-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-439">定义</span><span class="sxs-lookup"><span data-stu-id="60258-439">Definition</span></span>

<span data-ttu-id="60258-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-441">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-442">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-442">A keyword from is found.</span></span>
    
<span data-ttu-id="60258-443">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-444">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-445">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="60258-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="60258-447">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="60258-447">personal numeric code</span></span>
  
<span data-ttu-id="60258-448">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-448">unique identification number</span></span>
  
<span data-ttu-id="60258-449">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="60258-449">citizen service number</span></span>
  
<span data-ttu-id="60258-450">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-450">unique identity number</span></span>
  
<span data-ttu-id="60258-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="60258-452">bsn</span><span class="sxs-lookup"><span data-stu-id="60258-452">bsn</span></span>
  
<span data-ttu-id="60258-453">bsn#</span><span class="sxs-lookup"><span data-stu-id="60258-453">bsn#</span></span>
  
<span data-ttu-id="60258-454">persoonlijke numerieke 代码</span><span class="sxs-lookup"><span data-stu-id="60258-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="60258-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="60258-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="60258-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="60258-456">burgerservicenummer</span></span>
  
<span data-ttu-id="60258-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="60258-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="60258-458">波兰</span><span class="sxs-lookup"><span data-stu-id="60258-458">Poland</span></span>

<span data-ttu-id="60258-459">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰国家 ID （PESEL）" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="60258-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="60258-460">Portugal</span></span>

<span data-ttu-id="60258-461">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="60258-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="60258-462">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="60258-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="60258-463">Format</span><span class="sxs-lookup"><span data-stu-id="60258-463">Format</span></span>

<span data-ttu-id="60258-464">13位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-465">模式</span><span class="sxs-lookup"><span data-stu-id="60258-465">Pattern</span></span>

<span data-ttu-id="60258-466">13 位数字</span><span class="sxs-lookup"><span data-stu-id="60258-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="60258-467">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-467">Checksum</span></span>

<span data-ttu-id="60258-468">是</span><span class="sxs-lookup"><span data-stu-id="60258-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-469">定义</span><span class="sxs-lookup"><span data-stu-id="60258-469">Definition</span></span>

<span data-ttu-id="60258-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-471">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-472">找到了中`Keywords_romania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-474">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-475">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="60258-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="60258-477">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="60258-477">personal numeric code</span></span>
  
<span data-ttu-id="60258-478">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-478">unique identification number</span></span>
  
<span data-ttu-id="60258-479">cnp</span><span class="sxs-lookup"><span data-stu-id="60258-479">cnp</span></span>
  
<span data-ttu-id="60258-480">cnp#</span><span class="sxs-lookup"><span data-stu-id="60258-480">cnp#</span></span>
  
<span data-ttu-id="60258-481">针</span><span class="sxs-lookup"><span data-stu-id="60258-481">pin</span></span>
  
<span data-ttu-id="60258-482">针#</span><span class="sxs-lookup"><span data-stu-id="60258-482">pin#</span></span>
  
<span data-ttu-id="60258-483">保险号</span><span class="sxs-lookup"><span data-stu-id="60258-483">insurance number</span></span>
  
<span data-ttu-id="60258-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="60258-484">insurancenumber#</span></span>
  
<span data-ttu-id="60258-485">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-485">unique identity number</span></span>
  
<span data-ttu-id="60258-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="60258-487">付款的个人数字</span><span class="sxs-lookup"><span data-stu-id="60258-487">cod numeric personal</span></span>
  
<span data-ttu-id="60258-488">货到 identificare 个人</span><span class="sxs-lookup"><span data-stu-id="60258-488">cod identificare personal</span></span>
  
<span data-ttu-id="60258-489">货到付款 unic identificare</span><span class="sxs-lookup"><span data-stu-id="60258-489">cod unic identificare</span></span>
  
<span data-ttu-id="60258-490">număr 个人 unic</span><span class="sxs-lookup"><span data-stu-id="60258-490">număr personal unic</span></span>
  
<span data-ttu-id="60258-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="60258-491">număr identitate</span></span>
  
<span data-ttu-id="60258-492">număr identificare 个人</span><span class="sxs-lookup"><span data-stu-id="60258-492">număr identificare personal</span></span>
  
<span data-ttu-id="60258-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="60258-493">număridentitate#</span></span>
  
<span data-ttu-id="60258-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="60258-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="60258-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="60258-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="60258-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="60258-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="60258-497">Format</span><span class="sxs-lookup"><span data-stu-id="60258-497">Format</span></span>

<span data-ttu-id="60258-498">10个数字，包含一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="60258-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-499">模式</span><span class="sxs-lookup"><span data-stu-id="60258-499">Pattern</span></span>

<span data-ttu-id="60258-500">10个数字，包含一个反斜杠：</span><span class="sxs-lookup"><span data-stu-id="60258-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="60258-501">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-501">Checksum</span></span>

<span data-ttu-id="60258-502">是</span><span class="sxs-lookup"><span data-stu-id="60258-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-503">定义</span><span class="sxs-lookup"><span data-stu-id="60258-503">Definition</span></span>

<span data-ttu-id="60258-504">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-505">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-506">找到了中`Keywords_slovakia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-508">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-509">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="60258-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="60258-511">出生号码</span><span class="sxs-lookup"><span data-stu-id="60258-511">birth number</span></span>
  
<span data-ttu-id="60258-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="60258-512">national identification number</span></span>
  
<span data-ttu-id="60258-513">个人标识号</span><span class="sxs-lookup"><span data-stu-id="60258-513">personal identification number</span></span>
  
<span data-ttu-id="60258-514">social security number</span><span class="sxs-lookup"><span data-stu-id="60258-514">social security number</span></span>
  
<span data-ttu-id="60258-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-515">nationalnumber#</span></span>
  
<span data-ttu-id="60258-516">ssn#</span><span class="sxs-lookup"><span data-stu-id="60258-516">ssn#</span></span>
  
<span data-ttu-id="60258-517">ssn</span><span class="sxs-lookup"><span data-stu-id="60258-517">ssn</span></span>
  
<span data-ttu-id="60258-518">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="60258-518">national number</span></span>
  
<span data-ttu-id="60258-519">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="60258-519">personal id number</span></span>
  
<span data-ttu-id="60258-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="60258-520">personalidnumber#</span></span>
  
<span data-ttu-id="60258-521">rč</span><span class="sxs-lookup"><span data-stu-id="60258-521">rč</span></span>
  
<span data-ttu-id="60258-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="60258-522">rodné číslo</span></span>
  
<span data-ttu-id="60258-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="60258-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="60258-524">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="60258-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="60258-525">Format</span><span class="sxs-lookup"><span data-stu-id="60258-525">Format</span></span>

<span data-ttu-id="60258-526">13位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="60258-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-527">模式</span><span class="sxs-lookup"><span data-stu-id="60258-527">Pattern</span></span>

<span data-ttu-id="60258-528">指定模式中的13个数字：</span><span class="sxs-lookup"><span data-stu-id="60258-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="60258-529">与出生日期（DDMMLLL）对应的七位数，其中 "LLL" 对应于出生年份的后三个数字</span><span class="sxs-lookup"><span data-stu-id="60258-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="60258-530">与出生区域对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="60258-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="60258-531">三个数字，对应于出生在同一天的人的性别和序列号组合（000-499 的男和500-999 的女）</span><span class="sxs-lookup"><span data-stu-id="60258-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="60258-532">一个校验位</span><span class="sxs-lookup"><span data-stu-id="60258-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-533">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-533">Checksum</span></span>

<span data-ttu-id="60258-534">是</span><span class="sxs-lookup"><span data-stu-id="60258-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-535">定义</span><span class="sxs-lookup"><span data-stu-id="60258-535">Definition</span></span>

<span data-ttu-id="60258-536">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-537">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-538">找到了中`Keywords_slovenia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="60258-539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-540">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-541">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="60258-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="60258-543">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="60258-543">personal numeric code</span></span>
  
<span data-ttu-id="60258-544">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-544">unique identification number</span></span>
  
<span data-ttu-id="60258-545">唯一注册号码</span><span class="sxs-lookup"><span data-stu-id="60258-545">unique registration number</span></span>
  
<span data-ttu-id="60258-546">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-546">unique identity number</span></span>
  
<span data-ttu-id="60258-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="60258-548">唯一的主公民号码</span><span class="sxs-lookup"><span data-stu-id="60258-548">unique master citizen number</span></span>
  
<span data-ttu-id="60258-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="60258-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="60258-550">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="60258-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="60258-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="60258-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="60258-552">emšo</span><span class="sxs-lookup"><span data-stu-id="60258-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="60258-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="60258-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="60258-554">Format</span><span class="sxs-lookup"><span data-stu-id="60258-554">Format</span></span>

<span data-ttu-id="60258-555">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="60258-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="60258-556">模式</span><span class="sxs-lookup"><span data-stu-id="60258-556">Pattern</span></span>

<span data-ttu-id="60258-557">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="60258-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="60258-558">七个数字 </span><span class="sxs-lookup"><span data-stu-id="60258-558">Seven digits</span></span>
    
- <span data-ttu-id="60258-559">一个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="60258-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="60258-560">校验和</span><span class="sxs-lookup"><span data-stu-id="60258-560">Checksum</span></span>

<span data-ttu-id="60258-561">不适用</span><span class="sxs-lookup"><span data-stu-id="60258-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="60258-562">定义</span><span class="sxs-lookup"><span data-stu-id="60258-562">Definition</span></span>

<span data-ttu-id="60258-563">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="60258-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="60258-564">正则表达式`Regex_spain_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="60258-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="60258-565">找到了中`Keywords_spain_eu_national_id_card"`的关键字。</span><span class="sxs-lookup"><span data-stu-id="60258-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="60258-566">关键字</span><span class="sxs-lookup"><span data-stu-id="60258-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="60258-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="60258-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="60258-568">dni</span><span class="sxs-lookup"><span data-stu-id="60258-568">dni</span></span>
  
<span data-ttu-id="60258-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="60258-569">national identification number</span></span>
  
<span data-ttu-id="60258-570">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="60258-570">national identity number</span></span>
  
<span data-ttu-id="60258-571">保险号</span><span class="sxs-lookup"><span data-stu-id="60258-571">insurance number</span></span>
  
<span data-ttu-id="60258-572">个人标识号</span><span class="sxs-lookup"><span data-stu-id="60258-572">personal identification number</span></span>
  
<span data-ttu-id="60258-573">国家标识</span><span class="sxs-lookup"><span data-stu-id="60258-573">national identity</span></span>
  
<span data-ttu-id="60258-574">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="60258-574">personal identity no</span></span>
  
<span data-ttu-id="60258-575">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="60258-575">unique identity number</span></span>
  
<span data-ttu-id="60258-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="60258-576">nationalidno#</span></span>
  
<span data-ttu-id="60258-577">uniqueid#</span><span class="sxs-lookup"><span data-stu-id="60258-577">uniqueid#</span></span>
  
<span data-ttu-id="60258-578">dni#</span><span class="sxs-lookup"><span data-stu-id="60258-578">dni#</span></span>
  
<span data-ttu-id="60258-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="60258-579">nationalid#</span></span>
  
<span data-ttu-id="60258-580">nie#</span><span class="sxs-lookup"><span data-stu-id="60258-580">nie#</span></span>
  
<span data-ttu-id="60258-581">nie</span><span class="sxs-lookup"><span data-stu-id="60258-581">nie</span></span>
  
<span data-ttu-id="60258-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="60258-582">nienúmero#</span></span>
  
<span data-ttu-id="60258-583">nie número</span><span class="sxs-lookup"><span data-stu-id="60258-583">nie número</span></span>
  
<span data-ttu-id="60258-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="60258-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="60258-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="60258-585">identidad único</span></span>
  
<span data-ttu-id="60258-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="60258-586">número nacional identidad</span></span>
  
<span data-ttu-id="60258-587">dni número</span><span class="sxs-lookup"><span data-stu-id="60258-587">dni número</span></span>
  
<span data-ttu-id="60258-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="60258-588">dninúmero#</span></span>
  
<span data-ttu-id="60258-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="60258-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="60258-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="60258-590">Sweden</span></span>

<span data-ttu-id="60258-591">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典国家 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="60258-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="60258-592">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60258-592">See also</span></span>

[<span data-ttu-id="60258-593">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="60258-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

