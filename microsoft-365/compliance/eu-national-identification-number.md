---
title: 欧盟国家身份证号
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: f001d23ec3d6d8a2b3aa9575d4a9d602c4315e13
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592233"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="d2c88-104">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="d2c88-104">EU National Identification Number</span></span>

<span data-ttu-id="d2c88-105">本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。</span><span class="sxs-lookup"><span data-stu-id="d2c88-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="d2c88-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="d2c88-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d2c88-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="d2c88-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-108">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-108">Format</span></span>

<span data-ttu-id="d2c88-109">字母、数字和特殊字符的24个字符的组合</span><span class="sxs-lookup"><span data-stu-id="d2c88-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-110">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-110">Pattern</span></span>

<span data-ttu-id="d2c88-111">24个字符：</span><span class="sxs-lookup"><span data-stu-id="d2c88-111">24 characters:</span></span>
  
-  <span data-ttu-id="d2c88-112">22个字母（不区分大小写）、数字、反斜杠、正斜杠或加号</span><span class="sxs-lookup"><span data-stu-id="d2c88-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="d2c88-113">两个字母（不区分大小写）、数字、反斜杠、正斜杠、加号或等号</span><span class="sxs-lookup"><span data-stu-id="d2c88-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-114">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-114">Checksum</span></span>

<span data-ttu-id="d2c88-115">不适用</span><span class="sxs-lookup"><span data-stu-id="d2c88-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-116">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-116">Definition</span></span>

<span data-ttu-id="d2c88-117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-118">正则表达式`Regex_austria_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-119">找到了中`Keywords_austria_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2c88-120">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="d2c88-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-122">奥地利身份证号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-122">austrian identity number</span></span>
  
<span data-ttu-id="d2c88-123">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-123">national identity number</span></span>
  
<span data-ttu-id="d2c88-124">标识号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-124">identity number</span></span>
  
<span data-ttu-id="d2c88-125">national id</span><span class="sxs-lookup"><span data-stu-id="d2c88-125">national id</span></span>
  
<span data-ttu-id="d2c88-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="d2c88-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="d2c88-127">比利时</span><span class="sxs-lookup"><span data-stu-id="d2c88-127">Belgium</span></span>

<span data-ttu-id="d2c88-128">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "比利时国家数" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="d2c88-129">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="d2c88-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-130">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-130">Format</span></span>

<span data-ttu-id="d2c88-131">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-132">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-132">Pattern</span></span>

<span data-ttu-id="d2c88-133">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="d2c88-134">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="d2c88-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d2c88-135">与出生顺序对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="d2c88-136">与性别对应的一位数字：男的偶数位和用于女的奇数位</span><span class="sxs-lookup"><span data-stu-id="d2c88-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="d2c88-137">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-138">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-138">Checksum</span></span>

<span data-ttu-id="d2c88-139">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-140">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-140">Definition</span></span>

<span data-ttu-id="d2c88-141">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-142">函数`Func_bulgaria_national_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-143">找到了中`Keywords_bulgaria_national_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="d2c88-144">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-145">函数`Func_bulgaria_national_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2c88-146">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="d2c88-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="d2c88-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="d2c88-148">egn</span><span class="sxs-lookup"><span data-stu-id="d2c88-148">egn</span></span>
  
<span data-ttu-id="d2c88-149">egn#</span><span class="sxs-lookup"><span data-stu-id="d2c88-149">egn#</span></span>
  
<span data-ttu-id="d2c88-150">保加利亚语国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-150">bulgarian national number</span></span>
  
<span data-ttu-id="d2c88-151">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-151">national number</span></span>
  
<span data-ttu-id="d2c88-152">social security number</span><span class="sxs-lookup"><span data-stu-id="d2c88-152">social security number</span></span>
  
<span data-ttu-id="d2c88-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-153">nationalnumber#</span></span>
  
<span data-ttu-id="d2c88-154">ssn#</span><span class="sxs-lookup"><span data-stu-id="d2c88-154">ssn#</span></span>
  
<span data-ttu-id="d2c88-155">ssn</span><span class="sxs-lookup"><span data-stu-id="d2c88-155">ssn</span></span>
  
<span data-ttu-id="d2c88-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d2c88-156">nationalnumber</span></span>
  
<span data-ttu-id="d2c88-157">bnn#</span><span class="sxs-lookup"><span data-stu-id="d2c88-157">bnn#</span></span>
  
<span data-ttu-id="d2c88-158">bnn</span><span class="sxs-lookup"><span data-stu-id="d2c88-158">bnn</span></span>
  
<span data-ttu-id="d2c88-159">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-159">personal id number</span></span>
  
<span data-ttu-id="d2c88-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-160">personalidnumber#</span></span>
  
<span data-ttu-id="d2c88-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="d2c88-161">единен граждански номер</span></span>
  
<span data-ttu-id="d2c88-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="d2c88-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="d2c88-163">егн</span><span class="sxs-lookup"><span data-stu-id="d2c88-163">егн</span></span>
  
<span data-ttu-id="d2c88-164">егн#</span><span class="sxs-lookup"><span data-stu-id="d2c88-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="d2c88-165">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="d2c88-165">Croatia</span></span>

<span data-ttu-id="d2c88-166">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分中的 "克罗地亚恒等号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="d2c88-167">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="d2c88-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-168">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-168">Format</span></span>

<span data-ttu-id="d2c88-169">10个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-170">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-170">Pattern</span></span>

 <span data-ttu-id="d2c88-171">10位数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d2c88-172">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-172">Checksum</span></span>

<span data-ttu-id="d2c88-173">不适用</span><span class="sxs-lookup"><span data-stu-id="d2c88-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-174">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-174">Definition</span></span>

<span data-ttu-id="d2c88-175">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-176">正则表达式`Regex_cyprus_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-177">找到了中`Keywords_cyprus_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2c88-178">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="d2c88-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-180">id 卡号</span><span class="sxs-lookup"><span data-stu-id="d2c88-180">id card number</span></span>
  
<span data-ttu-id="d2c88-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-181">national identification number</span></span>
  
<span data-ttu-id="d2c88-182">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-182">personal id number</span></span>
  
<span data-ttu-id="d2c88-183">标识卡号</span><span class="sxs-lookup"><span data-stu-id="d2c88-183">identity card number</span></span>
  
<span data-ttu-id="d2c88-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="d2c88-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="d2c88-185">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="d2c88-185">Czech Republic</span></span>

<span data-ttu-id="d2c88-186">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "捷克国家身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="d2c88-187">丹麦</span><span class="sxs-lookup"><span data-stu-id="d2c88-187">Denmark</span></span>

<span data-ttu-id="d2c88-188">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "丹麦个人识别码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="d2c88-189">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="d2c88-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-190">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-190">Format</span></span>

<span data-ttu-id="d2c88-191">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-192">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-192">Pattern</span></span>

<span data-ttu-id="d2c88-193">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="d2c88-193">11 digits:</span></span>
  
- <span data-ttu-id="d2c88-194">一种数字，对应于性别和出生世纪（奇数号男，甚至是数字女; 1-2：19世纪; 3-4：20世纪; 5-6：21世纪）</span><span class="sxs-lookup"><span data-stu-id="d2c88-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="d2c88-195">六个数字，对应于出生日期（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="d2c88-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="d2c88-196">三个数字，对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="d2c88-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="d2c88-197">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-198">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-198">Checksum</span></span>

<span data-ttu-id="d2c88-199">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-200">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-200">Definition</span></span>

<span data-ttu-id="d2c88-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-202">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-203">找到了中`Keywords_estonia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-204">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-205">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-206">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="d2c88-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-208">个人标识代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-208">personal identification code</span></span>
  
<span data-ttu-id="d2c88-209">个人标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-209">personal identification number</span></span>
  
<span data-ttu-id="d2c88-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-210">national identification number</span></span>
  
<span data-ttu-id="d2c88-211">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-211">national number</span></span>
  
<span data-ttu-id="d2c88-212">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-212">personal id number</span></span>
  
<span data-ttu-id="d2c88-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-213">personalidnumber#</span></span>
  
<span data-ttu-id="d2c88-214">ik</span><span class="sxs-lookup"><span data-stu-id="d2c88-214">ik</span></span>
  
<span data-ttu-id="d2c88-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="d2c88-215">isikukood</span></span>
  
<span data-ttu-id="d2c88-216">id-kaart</span><span class="sxs-lookup"><span data-stu-id="d2c88-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="d2c88-217">芬兰</span><span class="sxs-lookup"><span data-stu-id="d2c88-217">Finland</span></span>

<span data-ttu-id="d2c88-218">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰国 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d2c88-219">法国</span><span class="sxs-lookup"><span data-stu-id="d2c88-219">France</span></span>

<span data-ttu-id="d2c88-220">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国国家 ID 卡（CNI）" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d2c88-221">德国</span><span class="sxs-lookup"><span data-stu-id="d2c88-221">Germany</span></span>

<span data-ttu-id="d2c88-222">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d2c88-223">希腊</span><span class="sxs-lookup"><span data-stu-id="d2c88-223">Greece</span></span>

<span data-ttu-id="d2c88-224">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="d2c88-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="d2c88-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-226">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-226">Format</span></span>

<span data-ttu-id="d2c88-227">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-228">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-228">Pattern</span></span>

<span data-ttu-id="d2c88-229">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="d2c88-229">11 digits:</span></span>
  
-  <span data-ttu-id="d2c88-230">一种与性别对应的数字（1--男，2-母，其他号码也适用于在两个公民前出生的公民的1900或公民）</span><span class="sxs-lookup"><span data-stu-id="d2c88-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="d2c88-231">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="d2c88-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="d2c88-232">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="d2c88-233">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-234">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-234">Checksum</span></span>

<span data-ttu-id="d2c88-235">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-236">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-236">Definition</span></span>

<span data-ttu-id="d2c88-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-238">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-239">找到了中`Keywords_hungary_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-240">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-241">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-242">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="d2c88-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-244">个人标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-244">personal identification number</span></span>
  
<span data-ttu-id="d2c88-245">identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-245">identification number</span></span>
  
<span data-ttu-id="d2c88-246">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-246">personal id number</span></span>
  
<span data-ttu-id="d2c88-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="d2c88-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="d2c88-248">爱尔兰</span><span class="sxs-lookup"><span data-stu-id="d2c88-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-249">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-249">Format</span></span>

<span data-ttu-id="d2c88-250">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="d2c88-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-251">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-251">Pattern</span></span>

<span data-ttu-id="d2c88-252">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="d2c88-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="d2c88-253">从01年1月2013到现在：</span><span class="sxs-lookup"><span data-stu-id="d2c88-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="d2c88-254">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d2c88-254">Seven digits</span></span> 
    
- <span data-ttu-id="d2c88-255">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-255">One check digit</span></span>
    
- <span data-ttu-id="d2c88-256">一个空格或大写的字母 "W" （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d2c88-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="d2c88-257">在01月1日之前1月2013：</span><span class="sxs-lookup"><span data-stu-id="d2c88-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="d2c88-258">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d2c88-258">Seven digits</span></span> 
    
- <span data-ttu-id="d2c88-259">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-259">One check digit</span></span>
    
- <span data-ttu-id="d2c88-260">一个空格或大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d2c88-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-261">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-261">Checksum</span></span>

<span data-ttu-id="d2c88-262">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-263">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-263">Definition</span></span>

<span data-ttu-id="d2c88-264">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-265">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="d2c88-266">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-266">A keyword from is found.</span></span>
    
<span data-ttu-id="d2c88-267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-268">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-269">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="d2c88-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-271">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-271">personal public service number</span></span>
  
<span data-ttu-id="d2c88-272">pps no</span><span class="sxs-lookup"><span data-stu-id="d2c88-272">pps no</span></span>
  
<span data-ttu-id="d2c88-273">收入和社会保险电话号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="d2c88-274">rsi no</span><span class="sxs-lookup"><span data-stu-id="d2c88-274">rsi no</span></span>
  
<span data-ttu-id="d2c88-275">个人标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-275">personal identification number</span></span>
  
<span data-ttu-id="d2c88-276">identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-276">identification number</span></span>
  
<span data-ttu-id="d2c88-277">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-277">personal id number</span></span>
  
<span data-ttu-id="d2c88-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="d2c88-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="d2c88-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="d2c88-279">uimh.</span></span> <span data-ttu-id="d2c88-280">psp</span><span class="sxs-lookup"><span data-stu-id="d2c88-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="d2c88-281">意大利</span><span class="sxs-lookup"><span data-stu-id="d2c88-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-282">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-282">Format</span></span>

<span data-ttu-id="d2c88-283">在指定模式中，由16个字符组成的字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="d2c88-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-284">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-284">Pattern</span></span>

<span data-ttu-id="d2c88-285">字母和数字的16个字符的组合：</span><span class="sxs-lookup"><span data-stu-id="d2c88-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="d2c88-286">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="d2c88-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="d2c88-287">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="d2c88-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="d2c88-288">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="d2c88-289">一个与出生月份的字母对应的字母–字母按字母顺序使用，但仅使用字母 A 到 E、H、L、M、P、R 和 T （因此，一月为 A，10月为 R）</span><span class="sxs-lookup"><span data-stu-id="d2c88-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="d2c88-290">与出生月份的某一天对应的两个数字，为了区分 genders，40已添加到女性的出生日。</span><span class="sxs-lookup"><span data-stu-id="d2c88-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="d2c88-291">与专用于 municipality 的区域代码相对应的四个数字（国家/地区内的国家/地区代码适用于外国国家）</span><span class="sxs-lookup"><span data-stu-id="d2c88-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="d2c88-292">一个奇偶校验数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-293">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-293">Checksum</span></span>

<span data-ttu-id="d2c88-294">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-295">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-295">Definition</span></span>

<span data-ttu-id="d2c88-296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-297">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-298">找到了中`Keywords_italy_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-299">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-300">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-301">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="d2c88-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-303">个人代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-303">personal code</span></span>
  
<span data-ttu-id="d2c88-304">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="d2c88-304">personal code number</span></span>
  
<span data-ttu-id="d2c88-305">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-305">personal certificate number</span></span>
  
<span data-ttu-id="d2c88-306">会计代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-306">fiscal code</span></span>
  
<span data-ttu-id="d2c88-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-307">personalcodeno#</span></span>
  
<span data-ttu-id="d2c88-308">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-308">personal id number</span></span>
  
<span data-ttu-id="d2c88-309">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-309">personal id code</span></span>
  
<span data-ttu-id="d2c88-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="d2c88-310">codice personale</span></span>
  
<span data-ttu-id="d2c88-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="d2c88-311">numero certificato personale</span></span>
  
<span data-ttu-id="d2c88-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="d2c88-312">numero personale</span></span>
  
<span data-ttu-id="d2c88-313">numero id personale</span><span class="sxs-lookup"><span data-stu-id="d2c88-313">numero id personale</span></span>
  
<span data-ttu-id="d2c88-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="d2c88-314">codice id personale</span></span>
  
<span data-ttu-id="d2c88-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="d2c88-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="d2c88-316">拉脱维亚</span><span class="sxs-lookup"><span data-stu-id="d2c88-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-317">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-317">Format</span></span>

<span data-ttu-id="d2c88-318">11位数字和指定格式的连字符</span><span class="sxs-lookup"><span data-stu-id="d2c88-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-319">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-319">Pattern</span></span>

<span data-ttu-id="d2c88-320">11个数字和一个连字符：</span><span class="sxs-lookup"><span data-stu-id="d2c88-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="d2c88-321">与出生日期对应的6个数字（DDMMYY）</span><span class="sxs-lookup"><span data-stu-id="d2c88-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="d2c88-322">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="d2c88-322">A hyphen</span></span>
    
- <span data-ttu-id="d2c88-323">一个数字，对应于出生世纪（"0" 表示19世纪，"1" 表示20世纪，"2" 表示21世纪）</span><span class="sxs-lookup"><span data-stu-id="d2c88-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="d2c88-324">四个数字，随机生成</span><span class="sxs-lookup"><span data-stu-id="d2c88-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-325">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-325">Checksum</span></span>

<span data-ttu-id="d2c88-326">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-327">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-327">Definition</span></span>

<span data-ttu-id="d2c88-328">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-329">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-330">找到了中`Keywords_latvia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-331">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-332">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-333">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="d2c88-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-335">个人代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-335">personal code</span></span>
  
<span data-ttu-id="d2c88-336">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="d2c88-336">personal code number</span></span>
  
<span data-ttu-id="d2c88-337">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-337">personal certificate number</span></span>
  
<span data-ttu-id="d2c88-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-338">personalcodeno#</span></span>
  
<span data-ttu-id="d2c88-339">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-339">personal id number</span></span>
  
<span data-ttu-id="d2c88-340">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-340">personal id code</span></span>
  
<span data-ttu-id="d2c88-341">角色 kods</span><span class="sxs-lookup"><span data-stu-id="d2c88-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="d2c88-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="d2c88-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-343">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-343">Format</span></span>

<span data-ttu-id="d2c88-344">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-345">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-345">Pattern</span></span>

<span data-ttu-id="d2c88-346">11个数字，不含空格和分隔符：</span><span class="sxs-lookup"><span data-stu-id="d2c88-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="d2c88-347">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d2c88-348">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="d2c88-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d2c88-349">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d2c88-350">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-351">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-351">Checksum</span></span>

<span data-ttu-id="d2c88-352">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-353">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-353">Definition</span></span>

<span data-ttu-id="d2c88-354">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-355">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-356">找到了中`Keywords_lithuania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-357">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-358">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-359">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="d2c88-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-361">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-361">personal numeric code</span></span>
  
<span data-ttu-id="d2c88-362">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-362">unique identification number</span></span>
  
<span data-ttu-id="d2c88-363">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-363">citizen service number</span></span>
  
<span data-ttu-id="d2c88-364">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-364">unique identity number</span></span>
  
<span data-ttu-id="d2c88-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="d2c88-366">个人代码。</span><span class="sxs-lookup"><span data-stu-id="d2c88-366">personal code.</span></span>
  
<span data-ttu-id="d2c88-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="d2c88-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="d2c88-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="d2c88-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="d2c88-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="d2c88-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="d2c88-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="d2c88-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="d2c88-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="d2c88-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="d2c88-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="d2c88-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-373">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-373">Format</span></span>

<span data-ttu-id="d2c88-374">11个数字，无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-375">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-375">Pattern</span></span>

<span data-ttu-id="d2c88-376">11 个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-376">11 digits</span></span>
  
- <span data-ttu-id="d2c88-377">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d2c88-378">与出生日期对应的6个数字（YYMMDD）</span><span class="sxs-lookup"><span data-stu-id="d2c88-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d2c88-379">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d2c88-380">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-381">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-381">Checksum</span></span>

<span data-ttu-id="d2c88-382">不适用</span><span class="sxs-lookup"><span data-stu-id="d2c88-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-383">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-383">Definition</span></span>

<span data-ttu-id="d2c88-384">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-385">正则表达式`Regex_luxemburg_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-386">找到了中`Keywords_luxemburg_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2c88-387">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="d2c88-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-389">个人 id</span><span class="sxs-lookup"><span data-stu-id="d2c88-389">personal id</span></span>
  
<span data-ttu-id="d2c88-390">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-390">personal id number</span></span>
  
<span data-ttu-id="d2c88-391">personalidno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-391">personalidno#</span></span>
  
<span data-ttu-id="d2c88-392">唯一 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-392">unique id number</span></span>
  
<span data-ttu-id="d2c88-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-393">personalidnumber#</span></span>
  
<span data-ttu-id="d2c88-394">唯一 id 键</span><span class="sxs-lookup"><span data-stu-id="d2c88-394">unique id key</span></span>
  
<span data-ttu-id="d2c88-395">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-395">personal id code</span></span>
  
<span data-ttu-id="d2c88-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="d2c88-396">uniqueidkey#</span></span>
  
<span data-ttu-id="d2c88-397">单个代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-397">individual code</span></span>
  
<span data-ttu-id="d2c88-398">个人 id</span><span class="sxs-lookup"><span data-stu-id="d2c88-398">individual id</span></span>
  
<span data-ttu-id="d2c88-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="d2c88-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="d2c88-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="d2c88-400">eindeutige id</span></span>
  
<span data-ttu-id="d2c88-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="d2c88-401">id personnelle</span></span>
  
<span data-ttu-id="d2c88-402">numéro d'identification 人员</span><span class="sxs-lookup"><span data-stu-id="d2c88-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="d2c88-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="d2c88-403">idpersonnelle#</span></span>
  
<span data-ttu-id="d2c88-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d2c88-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="d2c88-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="d2c88-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="d2c88-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="d2c88-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-407">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-407">Format</span></span>

<span data-ttu-id="d2c88-408">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="d2c88-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-409">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-409">Pattern</span></span>

<span data-ttu-id="d2c88-410">七位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="d2c88-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="d2c88-411">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d2c88-411">Seven digits</span></span> 
    
- <span data-ttu-id="d2c88-412">一个大写字母（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d2c88-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-413">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-413">Checksum</span></span>

<span data-ttu-id="d2c88-414">不适用</span><span class="sxs-lookup"><span data-stu-id="d2c88-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-415">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-415">Definition</span></span>

<span data-ttu-id="d2c88-416">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-417">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-418">找到了中`Keywords_malta_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-419">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-420">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-421">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="d2c88-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-423">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-423">personal numeric code</span></span>
  
<span data-ttu-id="d2c88-424">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-424">unique identification number</span></span>
  
<span data-ttu-id="d2c88-425">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-425">citizen service number</span></span>
  
<span data-ttu-id="d2c88-426">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-426">unique identity number</span></span>
  
<span data-ttu-id="d2c88-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="d2c88-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="d2c88-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="d2c88-429">numru ta "identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="d2c88-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="d2c88-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="d2c88-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="d2c88-431">numru ta "identità uniku</span><span class="sxs-lookup"><span data-stu-id="d2c88-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="d2c88-432">荷兰</span><span class="sxs-lookup"><span data-stu-id="d2c88-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-433">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-433">Format</span></span>

<span data-ttu-id="d2c88-434">9个数字，不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-435">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-435">Pattern</span></span>

<span data-ttu-id="d2c88-436">九个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2c88-437">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-437">Checksum</span></span>

<span data-ttu-id="d2c88-438">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-439">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-439">Definition</span></span>

<span data-ttu-id="d2c88-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-441">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-442">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-442">A keyword from is found.</span></span>
    
<span data-ttu-id="d2c88-443">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-444">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-445">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="d2c88-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-447">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-447">personal numeric code</span></span>
  
<span data-ttu-id="d2c88-448">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-448">unique identification number</span></span>
  
<span data-ttu-id="d2c88-449">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-449">citizen service number</span></span>
  
<span data-ttu-id="d2c88-450">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-450">unique identity number</span></span>
  
<span data-ttu-id="d2c88-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="d2c88-452">bsn</span><span class="sxs-lookup"><span data-stu-id="d2c88-452">bsn</span></span>
  
<span data-ttu-id="d2c88-453">bsn#</span><span class="sxs-lookup"><span data-stu-id="d2c88-453">bsn#</span></span>
  
<span data-ttu-id="d2c88-454">persoonlijke numerieke 代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="d2c88-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="d2c88-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="d2c88-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="d2c88-456">burgerservicenummer</span></span>
  
<span data-ttu-id="d2c88-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="d2c88-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="d2c88-458">波兰</span><span class="sxs-lookup"><span data-stu-id="d2c88-458">Poland</span></span>

<span data-ttu-id="d2c88-459">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰国家 ID （PESEL）" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d2c88-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="d2c88-460">Portugal</span></span>

<span data-ttu-id="d2c88-461">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="d2c88-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="d2c88-462">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="d2c88-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-463">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-463">Format</span></span>

<span data-ttu-id="d2c88-464">13位数，不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-465">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-465">Pattern</span></span>

<span data-ttu-id="d2c88-466">13 位数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2c88-467">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-467">Checksum</span></span>

<span data-ttu-id="d2c88-468">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-469">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-469">Definition</span></span>

<span data-ttu-id="d2c88-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-471">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-472">找到了中`Keywords_romania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-474">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-475">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="d2c88-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-477">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-477">personal numeric code</span></span>
  
<span data-ttu-id="d2c88-478">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-478">unique identification number</span></span>
  
<span data-ttu-id="d2c88-479">cnp</span><span class="sxs-lookup"><span data-stu-id="d2c88-479">cnp</span></span>
  
<span data-ttu-id="d2c88-480">cnp#</span><span class="sxs-lookup"><span data-stu-id="d2c88-480">cnp#</span></span>
  
<span data-ttu-id="d2c88-481">针</span><span class="sxs-lookup"><span data-stu-id="d2c88-481">pin</span></span>
  
<span data-ttu-id="d2c88-482">针#</span><span class="sxs-lookup"><span data-stu-id="d2c88-482">pin#</span></span>
  
<span data-ttu-id="d2c88-483">保险号</span><span class="sxs-lookup"><span data-stu-id="d2c88-483">insurance number</span></span>
  
<span data-ttu-id="d2c88-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-484">insurancenumber#</span></span>
  
<span data-ttu-id="d2c88-485">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-485">unique identity number</span></span>
  
<span data-ttu-id="d2c88-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="d2c88-487">付款的个人数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-487">cod numeric personal</span></span>
  
<span data-ttu-id="d2c88-488">货到 identificare 个人</span><span class="sxs-lookup"><span data-stu-id="d2c88-488">cod identificare personal</span></span>
  
<span data-ttu-id="d2c88-489">货到付款 unic identificare</span><span class="sxs-lookup"><span data-stu-id="d2c88-489">cod unic identificare</span></span>
  
<span data-ttu-id="d2c88-490">număr 个人 unic</span><span class="sxs-lookup"><span data-stu-id="d2c88-490">număr personal unic</span></span>
  
<span data-ttu-id="d2c88-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="d2c88-491">număr identitate</span></span>
  
<span data-ttu-id="d2c88-492">număr identificare 个人</span><span class="sxs-lookup"><span data-stu-id="d2c88-492">număr identificare personal</span></span>
  
<span data-ttu-id="d2c88-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="d2c88-493">număridentitate#</span></span>
  
<span data-ttu-id="d2c88-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="d2c88-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="d2c88-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="d2c88-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="d2c88-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="d2c88-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-497">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-497">Format</span></span>

<span data-ttu-id="d2c88-498">10个数字，包含一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="d2c88-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-499">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-499">Pattern</span></span>

<span data-ttu-id="d2c88-500">10个数字，包含一个反斜杠：</span><span class="sxs-lookup"><span data-stu-id="d2c88-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2c88-501">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-501">Checksum</span></span>

<span data-ttu-id="d2c88-502">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-503">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-503">Definition</span></span>

<span data-ttu-id="d2c88-504">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-505">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-506">找到了中`Keywords_slovakia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-508">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-509">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="d2c88-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-511">出生号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-511">birth number</span></span>
  
<span data-ttu-id="d2c88-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-512">national identification number</span></span>
  
<span data-ttu-id="d2c88-513">个人标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-513">personal identification number</span></span>
  
<span data-ttu-id="d2c88-514">social security number</span><span class="sxs-lookup"><span data-stu-id="d2c88-514">social security number</span></span>
  
<span data-ttu-id="d2c88-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-515">nationalnumber#</span></span>
  
<span data-ttu-id="d2c88-516">ssn#</span><span class="sxs-lookup"><span data-stu-id="d2c88-516">ssn#</span></span>
  
<span data-ttu-id="d2c88-517">ssn</span><span class="sxs-lookup"><span data-stu-id="d2c88-517">ssn</span></span>
  
<span data-ttu-id="d2c88-518">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-518">national number</span></span>
  
<span data-ttu-id="d2c88-519">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="d2c88-519">personal id number</span></span>
  
<span data-ttu-id="d2c88-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d2c88-520">personalidnumber#</span></span>
  
<span data-ttu-id="d2c88-521">rč</span><span class="sxs-lookup"><span data-stu-id="d2c88-521">rč</span></span>
  
<span data-ttu-id="d2c88-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d2c88-522">rodné číslo</span></span>
  
<span data-ttu-id="d2c88-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="d2c88-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="d2c88-524">斯洛文尼亚</span><span class="sxs-lookup"><span data-stu-id="d2c88-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-525">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-525">Format</span></span>

<span data-ttu-id="d2c88-526">13位数，不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="d2c88-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-527">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-527">Pattern</span></span>

<span data-ttu-id="d2c88-528">指定模式中的13个数字：</span><span class="sxs-lookup"><span data-stu-id="d2c88-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="d2c88-529">与出生日期（DDMMLLL）对应的七位数，其中 "LLL" 对应于出生年份的后三个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="d2c88-530">与出生区域对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="d2c88-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="d2c88-531">三个数字，对应于出生在同一天的人的性别和序列号组合（000-499 的男和500-999 的女）</span><span class="sxs-lookup"><span data-stu-id="d2c88-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="d2c88-532">一个校验位</span><span class="sxs-lookup"><span data-stu-id="d2c88-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-533">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-533">Checksum</span></span>

<span data-ttu-id="d2c88-534">是</span><span class="sxs-lookup"><span data-stu-id="d2c88-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-535">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-535">Definition</span></span>

<span data-ttu-id="d2c88-536">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-537">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-538">找到了中`Keywords_slovenia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d2c88-539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-540">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d2c88-541">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="d2c88-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-543">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="d2c88-543">personal numeric code</span></span>
  
<span data-ttu-id="d2c88-544">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-544">unique identification number</span></span>
  
<span data-ttu-id="d2c88-545">唯一注册号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-545">unique registration number</span></span>
  
<span data-ttu-id="d2c88-546">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-546">unique identity number</span></span>
  
<span data-ttu-id="d2c88-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="d2c88-548">唯一的主公民号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-548">unique master citizen number</span></span>
  
<span data-ttu-id="d2c88-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="d2c88-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="d2c88-550">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="d2c88-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="d2c88-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="d2c88-552">emšo</span><span class="sxs-lookup"><span data-stu-id="d2c88-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="d2c88-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="d2c88-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d2c88-554">Format</span><span class="sxs-lookup"><span data-stu-id="d2c88-554">Format</span></span>

<span data-ttu-id="d2c88-555">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="d2c88-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2c88-556">模式</span><span class="sxs-lookup"><span data-stu-id="d2c88-556">Pattern</span></span>

<span data-ttu-id="d2c88-557">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="d2c88-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="d2c88-558">七个数字 </span><span class="sxs-lookup"><span data-stu-id="d2c88-558">Seven digits</span></span>
    
- <span data-ttu-id="d2c88-559">一个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="d2c88-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2c88-560">校验和</span><span class="sxs-lookup"><span data-stu-id="d2c88-560">Checksum</span></span>

<span data-ttu-id="d2c88-561">不适用</span><span class="sxs-lookup"><span data-stu-id="d2c88-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2c88-562">定义</span><span class="sxs-lookup"><span data-stu-id="d2c88-562">Definition</span></span>

<span data-ttu-id="d2c88-563">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="d2c88-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2c88-564">正则表达式`Regex_spain_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c88-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2c88-565">找到了中`Keywords_spain_eu_national_id_card"`的关键字。</span><span class="sxs-lookup"><span data-stu-id="d2c88-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2c88-566">关键字</span><span class="sxs-lookup"><span data-stu-id="d2c88-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="d2c88-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d2c88-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="d2c88-568">dni</span><span class="sxs-lookup"><span data-stu-id="d2c88-568">dni</span></span>
  
<span data-ttu-id="d2c88-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="d2c88-569">national identification number</span></span>
  
<span data-ttu-id="d2c88-570">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="d2c88-570">national identity number</span></span>
  
<span data-ttu-id="d2c88-571">保险号</span><span class="sxs-lookup"><span data-stu-id="d2c88-571">insurance number</span></span>
  
<span data-ttu-id="d2c88-572">个人标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-572">personal identification number</span></span>
  
<span data-ttu-id="d2c88-573">国家标识</span><span class="sxs-lookup"><span data-stu-id="d2c88-573">national identity</span></span>
  
<span data-ttu-id="d2c88-574">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="d2c88-574">personal identity no</span></span>
  
<span data-ttu-id="d2c88-575">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="d2c88-575">unique identity number</span></span>
  
<span data-ttu-id="d2c88-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="d2c88-576">nationalidno#</span></span>
  
<span data-ttu-id="d2c88-577">uniqueid#</span><span class="sxs-lookup"><span data-stu-id="d2c88-577">uniqueid#</span></span>
  
<span data-ttu-id="d2c88-578">dni#</span><span class="sxs-lookup"><span data-stu-id="d2c88-578">dni#</span></span>
  
<span data-ttu-id="d2c88-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="d2c88-579">nationalid#</span></span>
  
<span data-ttu-id="d2c88-580">nie#</span><span class="sxs-lookup"><span data-stu-id="d2c88-580">nie#</span></span>
  
<span data-ttu-id="d2c88-581">nie</span><span class="sxs-lookup"><span data-stu-id="d2c88-581">nie</span></span>
  
<span data-ttu-id="d2c88-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="d2c88-582">nienúmero#</span></span>
  
<span data-ttu-id="d2c88-583">nie número</span><span class="sxs-lookup"><span data-stu-id="d2c88-583">nie número</span></span>
  
<span data-ttu-id="d2c88-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="d2c88-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="d2c88-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="d2c88-585">identidad único</span></span>
  
<span data-ttu-id="d2c88-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="d2c88-586">número nacional identidad</span></span>
  
<span data-ttu-id="d2c88-587">dni número</span><span class="sxs-lookup"><span data-stu-id="d2c88-587">dni número</span></span>
  
<span data-ttu-id="d2c88-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="d2c88-588">dninúmero#</span></span>
  
<span data-ttu-id="d2c88-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="d2c88-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="d2c88-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="d2c88-590">Sweden</span></span>

<span data-ttu-id="d2c88-591">有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典国家 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="d2c88-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2c88-592">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c88-592">See also</span></span>

[<span data-ttu-id="d2c88-593">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="d2c88-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

