---
title: 使用敏感信息类型查找什么
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全&amp;合规中心中的数据丢失防护（DLP）包括可供您在 DLP 策略中使用的80敏感信息类型。 本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。
ms.openlocfilehash: aa3a08961ccad92c9986db16c1d8180d9b0cd17e
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240277"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="146d1-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="146d1-104">What the sensitive information types look for</span></span>

<span data-ttu-id="146d1-105">Office 365 安全&amp;合规中心中的数据丢失防护（DLP）包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="146d1-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="146d1-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="146d1-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="146d1-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="146d1-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="146d1-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="146d1-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="146d1-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="146d1-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="146d1-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-111">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-111">Format</span></span>

<span data-ttu-id="146d1-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="146d1-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-113">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-113">Pattern</span></span>

<span data-ttu-id="146d1-114">格式</span><span class="sxs-lookup"><span data-stu-id="146d1-114">Formatted:</span></span>
- <span data-ttu-id="146d1-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="146d1-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="146d1-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-116">A hyphen</span></span>
- <span data-ttu-id="146d1-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-117">Four digits</span></span>
- <span data-ttu-id="146d1-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-118">A hyphen</span></span>
- <span data-ttu-id="146d1-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-119">A digit</span></span>

<span data-ttu-id="146d1-120">无格式：9个连续的数字，以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="146d1-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="146d1-121">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-121">Checksum</span></span>

<span data-ttu-id="146d1-122">否</span><span class="sxs-lookup"><span data-stu-id="146d1-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-123">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-123">Definition</span></span>

<span data-ttu-id="146d1-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="146d1-127">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="146d1-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="146d1-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="146d1-129">aba</span><span class="sxs-lookup"><span data-stu-id="146d1-129">aba</span></span>
- <span data-ttu-id="146d1-130">aba #</span><span class="sxs-lookup"><span data-stu-id="146d1-130">aba #</span></span>
- <span data-ttu-id="146d1-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="146d1-131">aba routing #</span></span>
- <span data-ttu-id="146d1-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="146d1-132">aba routing number</span></span>
- <span data-ttu-id="146d1-133">aba#</span><span class="sxs-lookup"><span data-stu-id="146d1-133">aba#</span></span>
- <span data-ttu-id="146d1-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="146d1-134">abarouting#</span></span>
- <span data-ttu-id="146d1-135">aba number</span><span class="sxs-lookup"><span data-stu-id="146d1-135">aba number</span></span>
- <span data-ttu-id="146d1-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-136">abaroutingnumber</span></span>
- <span data-ttu-id="146d1-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="146d1-137">american bank association routing #</span></span>
- <span data-ttu-id="146d1-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="146d1-138">american bank association routing number</span></span>
- <span data-ttu-id="146d1-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="146d1-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="146d1-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="146d1-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="146d1-141">bank routing number</span></span>
- <span data-ttu-id="146d1-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="146d1-142">bankrouting#</span></span>
- <span data-ttu-id="146d1-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-143">bankroutingnumber</span></span>
- <span data-ttu-id="146d1-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="146d1-144">routing transit number</span></span>
- <span data-ttu-id="146d1-145">RTN</span><span class="sxs-lookup"><span data-stu-id="146d1-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="146d1-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="146d1-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-147">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-147">Format</span></span>

<span data-ttu-id="146d1-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="146d1-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-149">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-149">Pattern</span></span>

<span data-ttu-id="146d1-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-150">Eight digits:</span></span>
- <span data-ttu-id="146d1-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-151">Two digits</span></span>
- <span data-ttu-id="146d1-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-152">A period</span></span>
- <span data-ttu-id="146d1-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-153">Three digits</span></span>
- <span data-ttu-id="146d1-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-154">A period</span></span>
- <span data-ttu-id="146d1-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-156">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-156">Checksum</span></span>

<span data-ttu-id="146d1-157">否</span><span class="sxs-lookup"><span data-stu-id="146d1-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-158">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-158">Definition</span></span>

<span data-ttu-id="146d1-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-162">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="146d1-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="146d1-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="146d1-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="146d1-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="146d1-165">标识</span><span class="sxs-lookup"><span data-stu-id="146d1-165">Identity</span></span> 
- <span data-ttu-id="146d1-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="146d1-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="146d1-167">DNI</span><span class="sxs-lookup"><span data-stu-id="146d1-167">DNI</span></span> 
- <span data-ttu-id="146d1-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="146d1-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="146d1-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="146d1-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="146d1-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="146d1-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="146d1-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="146d1-171">Identidad</span></span> 
- <span data-ttu-id="146d1-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="146d1-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="146d1-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-174">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-174">Format</span></span>

<span data-ttu-id="146d1-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="146d1-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-176">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-176">Pattern</span></span>

<span data-ttu-id="146d1-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="146d1-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="146d1-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="146d1-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="146d1-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-179">Three digits</span></span> 
- <span data-ttu-id="146d1-180">连字符</span><span class="sxs-lookup"><span data-stu-id="146d1-180">A hyphen</span></span> 
- <span data-ttu-id="146d1-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-182">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-182">Checksum</span></span>

<span data-ttu-id="146d1-183">否</span><span class="sxs-lookup"><span data-stu-id="146d1-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-184">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-184">Definition</span></span>

<span data-ttu-id="146d1-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="146d1-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="146d1-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="146d1-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="146d1-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-192">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="146d1-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="146d1-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="146d1-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="146d1-194">swift bank code</span></span>
- <span data-ttu-id="146d1-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="146d1-195">correspondent bank</span></span>
- <span data-ttu-id="146d1-196">base currency</span><span class="sxs-lookup"><span data-stu-id="146d1-196">base currency</span></span>
- <span data-ttu-id="146d1-197">usa account</span><span class="sxs-lookup"><span data-stu-id="146d1-197">usa account</span></span>
- <span data-ttu-id="146d1-198">holder address</span><span class="sxs-lookup"><span data-stu-id="146d1-198">holder address</span></span>
- <span data-ttu-id="146d1-199">bank address</span><span class="sxs-lookup"><span data-stu-id="146d1-199">bank address</span></span>
- <span data-ttu-id="146d1-200">information account</span><span class="sxs-lookup"><span data-stu-id="146d1-200">information account</span></span>
- <span data-ttu-id="146d1-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="146d1-201">fund transfers</span></span>
- <span data-ttu-id="146d1-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="146d1-202">bank charges</span></span>
- <span data-ttu-id="146d1-203">bank details</span><span class="sxs-lookup"><span data-stu-id="146d1-203">bank details</span></span>
- <span data-ttu-id="146d1-204">banking information</span><span class="sxs-lookup"><span data-stu-id="146d1-204">banking information</span></span>
- <span data-ttu-id="146d1-205">full names</span><span class="sxs-lookup"><span data-stu-id="146d1-205">full names</span></span>
- <span data-ttu-id="146d1-206">iaea</span><span class="sxs-lookup"><span data-stu-id="146d1-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="146d1-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-208">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-208">Format</span></span>

<span data-ttu-id="146d1-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="146d1-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-210">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-210">Pattern</span></span>

<span data-ttu-id="146d1-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="146d1-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-213">Two digits</span></span> 
- <span data-ttu-id="146d1-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="146d1-215">OR</span><span class="sxs-lookup"><span data-stu-id="146d1-215">OR</span></span>

- <span data-ttu-id="146d1-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-217">4-9 digits</span></span>

<span data-ttu-id="146d1-218">OR</span><span class="sxs-lookup"><span data-stu-id="146d1-218">OR</span></span>

- <span data-ttu-id="146d1-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-220">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-220">Checksum</span></span>

<span data-ttu-id="146d1-221">否</span><span class="sxs-lookup"><span data-stu-id="146d1-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-222">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-222">Definition</span></span>

<span data-ttu-id="146d1-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="146d1-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-227">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="146d1-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="146d1-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="146d1-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="146d1-229">international driving permits</span></span>
- <span data-ttu-id="146d1-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="146d1-230">australian automobile association</span></span>
- <span data-ttu-id="146d1-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="146d1-231">international driving permit</span></span>
- <span data-ttu-id="146d1-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-232">DriverLicence</span></span>
- <span data-ttu-id="146d1-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-233">DriverLicences</span></span>
- <span data-ttu-id="146d1-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-234">Driver Lic</span></span>
- <span data-ttu-id="146d1-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-235">Driver Licence</span></span>
- <span data-ttu-id="146d1-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-236">Driver Licences</span></span>
- <span data-ttu-id="146d1-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="146d1-237">DriversLic</span></span>
- <span data-ttu-id="146d1-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-238">DriversLicence</span></span>
- <span data-ttu-id="146d1-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-239">DriversLicences</span></span>
- <span data-ttu-id="146d1-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-240">Drivers Lic</span></span>
- <span data-ttu-id="146d1-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-241">Drivers Lics</span></span>
- <span data-ttu-id="146d1-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-242">Drivers Licence</span></span>
- <span data-ttu-id="146d1-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-243">Drivers Licences</span></span>
- <span data-ttu-id="146d1-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-244">Driver'Lic</span></span>
- <span data-ttu-id="146d1-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-245">Driver'Lics</span></span>
- <span data-ttu-id="146d1-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-246">Driver'Licence</span></span>
- <span data-ttu-id="146d1-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-247">Driver'Licences</span></span>
- <span data-ttu-id="146d1-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-248">Driver' Lic</span></span>
- <span data-ttu-id="146d1-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-249">Driver' Lics</span></span>
- <span data-ttu-id="146d1-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-250">Driver' Licence</span></span>
- <span data-ttu-id="146d1-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-251">Driver' Licences</span></span>
- <span data-ttu-id="146d1-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="146d1-252">Driver'sLic</span></span>
- <span data-ttu-id="146d1-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="146d1-253">Driver'sLics</span></span>
- <span data-ttu-id="146d1-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-254">Driver'sLicence</span></span>
- <span data-ttu-id="146d1-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-255">Driver'sLicences</span></span>
- <span data-ttu-id="146d1-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-256">Driver's Lic</span></span>
- <span data-ttu-id="146d1-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-257">Driver's Lics</span></span>
- <span data-ttu-id="146d1-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-258">Driver's Licence</span></span>
- <span data-ttu-id="146d1-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-259">Driver's Licences</span></span>
- <span data-ttu-id="146d1-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-260">DriverLic#</span></span>
- <span data-ttu-id="146d1-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-261">DriverLics#</span></span>
- <span data-ttu-id="146d1-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-262">DriverLicence#</span></span>
- <span data-ttu-id="146d1-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-263">DriverLicences#</span></span>
- <span data-ttu-id="146d1-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-264">Driver Lic#</span></span>
- <span data-ttu-id="146d1-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-265">Driver Lics#</span></span>
- <span data-ttu-id="146d1-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-266">Driver Licence#</span></span>
- <span data-ttu-id="146d1-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-267">Driver Licences#</span></span>
- <span data-ttu-id="146d1-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-268">DriversLic#</span></span>
- <span data-ttu-id="146d1-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-269">DriversLics#</span></span>
- <span data-ttu-id="146d1-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-270">DriversLicence#</span></span>
- <span data-ttu-id="146d1-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-271">DriversLicences#</span></span>
- <span data-ttu-id="146d1-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-272">Drivers Lic#</span></span>
- <span data-ttu-id="146d1-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-273">Drivers Lics#</span></span>
- <span data-ttu-id="146d1-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-274">Drivers Licence#</span></span>
- <span data-ttu-id="146d1-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-275">Drivers Licences#</span></span>
- <span data-ttu-id="146d1-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-276">Driver'Lic#</span></span>
- <span data-ttu-id="146d1-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-277">Driver'Lics#</span></span>
- <span data-ttu-id="146d1-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-278">Driver'Licence#</span></span>
- <span data-ttu-id="146d1-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-279">Driver'Licences#</span></span>
- <span data-ttu-id="146d1-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-280">Driver' Lic#</span></span>
- <span data-ttu-id="146d1-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-281">Driver' Lics#</span></span>
- <span data-ttu-id="146d1-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-282">Driver' Licence#</span></span>
- <span data-ttu-id="146d1-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-283">Driver' Licences#</span></span>
- <span data-ttu-id="146d1-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-284">Driver'sLic#</span></span>
- <span data-ttu-id="146d1-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-285">Driver'sLics#</span></span>
- <span data-ttu-id="146d1-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-286">Driver'sLicence#</span></span>
- <span data-ttu-id="146d1-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-287">Driver'sLicences#</span></span>
- <span data-ttu-id="146d1-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-288">Driver's Lic#</span></span>
- <span data-ttu-id="146d1-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-289">Driver's Lics#</span></span>
- <span data-ttu-id="146d1-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-290">Driver's Licence#</span></span>
- <span data-ttu-id="146d1-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="146d1-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="146d1-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="146d1-293">aaa</span><span class="sxs-lookup"><span data-stu-id="146d1-293">aaa</span></span>
- <span data-ttu-id="146d1-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-294">DriverLicense</span></span>
- <span data-ttu-id="146d1-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-295">DriverLicenses</span></span>
- <span data-ttu-id="146d1-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="146d1-296">Driver License</span></span>
- <span data-ttu-id="146d1-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-297">Driver Licenses</span></span>
- <span data-ttu-id="146d1-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-298">DriversLicense</span></span>
- <span data-ttu-id="146d1-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-299">DriversLicenses</span></span>
- <span data-ttu-id="146d1-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="146d1-300">Drivers License</span></span>
- <span data-ttu-id="146d1-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-301">Drivers Licenses</span></span>
- <span data-ttu-id="146d1-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="146d1-302">Driver'License</span></span>
- <span data-ttu-id="146d1-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-303">Driver'Licenses</span></span>
- <span data-ttu-id="146d1-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="146d1-304">Driver' License</span></span>
- <span data-ttu-id="146d1-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-305">Driver' Licenses</span></span>
- <span data-ttu-id="146d1-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-306">Driver'sLicense</span></span>
- <span data-ttu-id="146d1-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-307">Driver'sLicenses</span></span>
- <span data-ttu-id="146d1-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="146d1-308">Driver's License</span></span>
- <span data-ttu-id="146d1-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-309">Driver's Licenses</span></span>
- <span data-ttu-id="146d1-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-310">DriverLicense#</span></span>
- <span data-ttu-id="146d1-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-311">DriverLicenses#</span></span>
- <span data-ttu-id="146d1-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="146d1-312">Driver License#</span></span>
- <span data-ttu-id="146d1-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-313">Driver Licenses#</span></span>
- <span data-ttu-id="146d1-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-314">DriversLicense#</span></span>
- <span data-ttu-id="146d1-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-315">DriversLicenses#</span></span>
- <span data-ttu-id="146d1-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="146d1-316">Drivers License#</span></span>
- <span data-ttu-id="146d1-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-317">Drivers Licenses#</span></span>
- <span data-ttu-id="146d1-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="146d1-318">Driver'License#</span></span>
- <span data-ttu-id="146d1-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-319">Driver'Licenses#</span></span>
- <span data-ttu-id="146d1-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="146d1-320">Driver' License#</span></span>
- <span data-ttu-id="146d1-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-321">Driver' Licenses#</span></span>
- <span data-ttu-id="146d1-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-322">Driver'sLicense#</span></span>
- <span data-ttu-id="146d1-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="146d1-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="146d1-324">Driver's License#</span></span>
- <span data-ttu-id="146d1-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="146d1-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-327">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-327">Format</span></span>

<span data-ttu-id="146d1-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-329">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-329">Pattern</span></span>

<span data-ttu-id="146d1-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-330">10-11 digits:</span></span>
- <span data-ttu-id="146d1-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="146d1-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="146d1-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="146d1-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="146d1-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="146d1-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="146d1-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-335">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-335">Checksum</span></span>

<span data-ttu-id="146d1-336">是</span><span class="sxs-lookup"><span data-stu-id="146d1-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-337">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-337">Definition</span></span>

<span data-ttu-id="146d1-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="146d1-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-341">The checksum passes.</span></span>

<span data-ttu-id="146d1-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-345">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="146d1-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="146d1-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="146d1-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="146d1-347">bank account details</span></span>
- <span data-ttu-id="146d1-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="146d1-348">medicare payments</span></span>
- <span data-ttu-id="146d1-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="146d1-349">mortgage account</span></span>
- <span data-ttu-id="146d1-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="146d1-350">bank payments</span></span>
- <span data-ttu-id="146d1-351">information branch</span><span class="sxs-lookup"><span data-stu-id="146d1-351">information branch</span></span>
- <span data-ttu-id="146d1-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="146d1-352">credit card loan</span></span>
- <span data-ttu-id="146d1-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="146d1-353">department of human services</span></span>
- <span data-ttu-id="146d1-354">local service</span><span class="sxs-lookup"><span data-stu-id="146d1-354">local service</span></span>
- <span data-ttu-id="146d1-355">medicare</span><span class="sxs-lookup"><span data-stu-id="146d1-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="146d1-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="146d1-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-357">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-357">Format</span></span>

<span data-ttu-id="146d1-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-359">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-359">Pattern</span></span>

<span data-ttu-id="146d1-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-361">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-361">Checksum</span></span>

<span data-ttu-id="146d1-362">否</span><span class="sxs-lookup"><span data-stu-id="146d1-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-363">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-363">Definition</span></span>

<span data-ttu-id="146d1-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-366">找到 Keyword_passport 或 Keyword_australia_passport_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="146d1-367">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="146d1-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-368">Keyword_passport</span></span>

- <span data-ttu-id="146d1-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="146d1-369">Passport Number</span></span>
- <span data-ttu-id="146d1-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="146d1-370">Passport No</span></span>
- <span data-ttu-id="146d1-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-371">Passport #</span></span>
- <span data-ttu-id="146d1-372">登记卡#</span><span class="sxs-lookup"><span data-stu-id="146d1-372">Passport#</span></span>
- <span data-ttu-id="146d1-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="146d1-373">PassportID</span></span>
- <span data-ttu-id="146d1-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="146d1-374">Passportno</span></span>
- <span data-ttu-id="146d1-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-375">passportnumber</span></span>
- <span data-ttu-id="146d1-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-376">パスポート</span></span>
- <span data-ttu-id="146d1-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-377">パスポート番号</span></span>
- <span data-ttu-id="146d1-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-378">パスポートのNum</span></span>
- <span data-ttu-id="146d1-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="146d1-379">パスポート ＃</span></span> 
- <span data-ttu-id="146d1-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="146d1-380">Numéro de passeport</span></span>
- <span data-ttu-id="146d1-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="146d1-381">Passeport n °</span></span>
- <span data-ttu-id="146d1-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="146d1-382">Passeport Non</span></span>
- <span data-ttu-id="146d1-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="146d1-383">Passeport #</span></span>
- <span data-ttu-id="146d1-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="146d1-384">Passeport#</span></span>
- <span data-ttu-id="146d1-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="146d1-385">PasseportNon</span></span>
- <span data-ttu-id="146d1-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="146d1-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="146d1-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="146d1-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="146d1-388">passport</span></span>
- <span data-ttu-id="146d1-389">passport details</span><span class="sxs-lookup"><span data-stu-id="146d1-389">passport details</span></span>
- <span data-ttu-id="146d1-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="146d1-390">immigration and citizenship</span></span>
- <span data-ttu-id="146d1-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="146d1-391">commonwealth of australia</span></span>
- <span data-ttu-id="146d1-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="146d1-392">department of immigration</span></span>
- <span data-ttu-id="146d1-393">residential address</span><span class="sxs-lookup"><span data-stu-id="146d1-393">residential address</span></span>
- <span data-ttu-id="146d1-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="146d1-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="146d1-395">反之</span><span class="sxs-lookup"><span data-stu-id="146d1-395">visa</span></span>
- <span data-ttu-id="146d1-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-396">national identity card</span></span>
- <span data-ttu-id="146d1-397">passport number</span><span class="sxs-lookup"><span data-stu-id="146d1-397">passport number</span></span>
- <span data-ttu-id="146d1-398">travel document</span><span class="sxs-lookup"><span data-stu-id="146d1-398">travel document</span></span>
- <span data-ttu-id="146d1-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="146d1-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="146d1-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="146d1-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-401">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-401">Format</span></span>

<span data-ttu-id="146d1-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-403">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-403">Pattern</span></span>

<span data-ttu-id="146d1-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="146d1-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="146d1-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-405">Three digits</span></span> 
- <span data-ttu-id="146d1-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="146d1-406">An optional space</span></span> 
- <span data-ttu-id="146d1-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-407">Three digits</span></span> 
- <span data-ttu-id="146d1-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="146d1-408">An optional space</span></span> 
- <span data-ttu-id="146d1-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-410">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-410">Checksum</span></span>

<span data-ttu-id="146d1-411">是</span><span class="sxs-lookup"><span data-stu-id="146d1-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-412">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-412">Definition</span></span>

<span data-ttu-id="146d1-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="146d1-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-417">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="146d1-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="146d1-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="146d1-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="146d1-419">australian business number</span></span>
- <span data-ttu-id="146d1-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="146d1-420">marginal tax rate</span></span>
- <span data-ttu-id="146d1-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="146d1-421">medicare levy</span></span>
- <span data-ttu-id="146d1-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="146d1-422">portfolio number</span></span>
- <span data-ttu-id="146d1-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="146d1-423">service veterans</span></span>
- <span data-ttu-id="146d1-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="146d1-424">withholding tax</span></span>
- <span data-ttu-id="146d1-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="146d1-425">individual tax return</span></span>
- <span data-ttu-id="146d1-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="146d1-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="146d1-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="146d1-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="146d1-428">00000000</span><span class="sxs-lookup"><span data-stu-id="146d1-428">00000000</span></span>
- <span data-ttu-id="146d1-429">11111111</span><span class="sxs-lookup"><span data-stu-id="146d1-429">11111111</span></span>
- <span data-ttu-id="146d1-430">22222222</span><span class="sxs-lookup"><span data-stu-id="146d1-430">22222222</span></span>
- <span data-ttu-id="146d1-431">33333333</span><span class="sxs-lookup"><span data-stu-id="146d1-431">33333333</span></span>
- <span data-ttu-id="146d1-432">44444444</span><span class="sxs-lookup"><span data-stu-id="146d1-432">44444444</span></span>
- <span data-ttu-id="146d1-433">55555555</span><span class="sxs-lookup"><span data-stu-id="146d1-433">55555555</span></span>
- <span data-ttu-id="146d1-434">66666666</span><span class="sxs-lookup"><span data-stu-id="146d1-434">66666666</span></span>
- <span data-ttu-id="146d1-435">77777777</span><span class="sxs-lookup"><span data-stu-id="146d1-435">77777777</span></span>
- <span data-ttu-id="146d1-436">88888888</span><span class="sxs-lookup"><span data-stu-id="146d1-436">88888888</span></span>
- <span data-ttu-id="146d1-437">99999999</span><span class="sxs-lookup"><span data-stu-id="146d1-437">99999999</span></span>
- <span data-ttu-id="146d1-438">000000000</span><span class="sxs-lookup"><span data-stu-id="146d1-438">000000000</span></span>
- <span data-ttu-id="146d1-439">111111111</span><span class="sxs-lookup"><span data-stu-id="146d1-439">111111111</span></span>
- <span data-ttu-id="146d1-440">222222222</span><span class="sxs-lookup"><span data-stu-id="146d1-440">222222222</span></span>
- <span data-ttu-id="146d1-441">333333333</span><span class="sxs-lookup"><span data-stu-id="146d1-441">333333333</span></span>
- <span data-ttu-id="146d1-442">444444444</span><span class="sxs-lookup"><span data-stu-id="146d1-442">444444444</span></span>
- <span data-ttu-id="146d1-443">555555555</span><span class="sxs-lookup"><span data-stu-id="146d1-443">555555555</span></span>
- <span data-ttu-id="146d1-444">666666666</span><span class="sxs-lookup"><span data-stu-id="146d1-444">666666666</span></span>
- <span data-ttu-id="146d1-445">777777777</span><span class="sxs-lookup"><span data-stu-id="146d1-445">777777777</span></span>
- <span data-ttu-id="146d1-446">888888888</span><span class="sxs-lookup"><span data-stu-id="146d1-446">888888888</span></span>
- <span data-ttu-id="146d1-447">999999999</span><span class="sxs-lookup"><span data-stu-id="146d1-447">999999999</span></span>
- <span data-ttu-id="146d1-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="146d1-448">0000000000</span></span>
- <span data-ttu-id="146d1-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="146d1-449">1111111111</span></span>
- <span data-ttu-id="146d1-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="146d1-450">2222222222</span></span>
- <span data-ttu-id="146d1-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="146d1-451">3333333333</span></span>
- <span data-ttu-id="146d1-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="146d1-452">4444444444</span></span>
- <span data-ttu-id="146d1-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="146d1-453">5555555555</span></span>
- <span data-ttu-id="146d1-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="146d1-454">6666666666</span></span>
- <span data-ttu-id="146d1-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="146d1-455">7777777777</span></span>
- <span data-ttu-id="146d1-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="146d1-456">8888888888</span></span>
- <span data-ttu-id="146d1-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="146d1-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="146d1-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="146d1-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="146d1-459">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-459">Format</span></span>

<span data-ttu-id="146d1-460">字符串 "DocumentDb"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="146d1-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-461">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-461">Pattern</span></span>

- <span data-ttu-id="146d1-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="146d1-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="146d1-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-464">大于号（>）、等号（=）、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="146d1-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="146d1-465">86字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-466">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-467">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-467">Checksum</span></span>

<span data-ttu-id="146d1-468">否</span><span class="sxs-lookup"><span data-stu-id="146d1-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-469">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-469">Definition</span></span>

<span data-ttu-id="146d1-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-472">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-473">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-475">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-476">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-476">contoso</span></span>
- <span data-ttu-id="146d1-477">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-477">fabrikam</span></span>
- <span data-ttu-id="146d1-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-478">northwind</span></span>
- <span data-ttu-id="146d1-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-479">sandbox</span></span>
- <span data-ttu-id="146d1-480">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-480">onebox</span></span>
- <span data-ttu-id="146d1-481">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-481">localhost</span></span>
- <span data-ttu-id="146d1-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-482">127.0.0.1</span></span>
- <span data-ttu-id="146d1-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-484">com</span><span class="sxs-lookup"><span data-stu-id="146d1-484">com</span></span>
- <span data-ttu-id="146d1-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-486">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="146d1-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="146d1-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="146d1-488">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-488">Format</span></span>

<span data-ttu-id="146d1-489">字符串 "Server"、"server" 或 "data source"，后跟下面模式中所述的字符和字符串，包括字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="146d1-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-490">com "或" cloudapp "。</span><span class="sxs-lookup"><span data-stu-id="146d1-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="146d1-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-492">net "和字符串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="146d1-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-493">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-493">Pattern</span></span>

- <span data-ttu-id="146d1-494">字符串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="146d1-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="146d1-495">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-496">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-496">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-498">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-499">字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="146d1-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-500">com "，" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="146d1-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="146d1-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-502">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-502">net"</span></span>
- <span data-ttu-id="146d1-503">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-504">字符串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="146d1-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="146d1-505">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-506">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-506">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-507">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-508">一个或多个不是分号（;)、引号（"）或撇号（'）的字符</span><span class="sxs-lookup"><span data-stu-id="146d1-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="146d1-509">分号（;)、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="146d1-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-510">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-510">Checksum</span></span>

<span data-ttu-id="146d1-511">否</span><span class="sxs-lookup"><span data-stu-id="146d1-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-512">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-512">Definition</span></span>

<span data-ttu-id="146d1-513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-514">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-515">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-516">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-518">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-519">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-519">contoso</span></span>
- <span data-ttu-id="146d1-520">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-520">fabrikam</span></span>
- <span data-ttu-id="146d1-521">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-521">northwind</span></span>
- <span data-ttu-id="146d1-522">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-522">sandbox</span></span>
- <span data-ttu-id="146d1-523">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-523">onebox</span></span>
- <span data-ttu-id="146d1-524">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-524">localhost</span></span>
- <span data-ttu-id="146d1-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-525">127.0.0.1</span></span>
- <span data-ttu-id="146d1-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-527">com</span><span class="sxs-lookup"><span data-stu-id="146d1-527">com</span></span>
- <span data-ttu-id="146d1-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-529">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="146d1-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="146d1-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="146d1-531">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-531">Format</span></span>

<span data-ttu-id="146d1-532">字符串 "HostName"，后跟下面模式中所示的字符和字符串，包括字符串 "azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="146d1-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="146d1-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-534">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-534">Pattern</span></span>

- <span data-ttu-id="146d1-535">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="146d1-535">The string "HostName"</span></span>
- <span data-ttu-id="146d1-536">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-537">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-537">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-538">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-539">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-540">字符串 "azure 设备。</span><span class="sxs-lookup"><span data-stu-id="146d1-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-541">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-541">net"</span></span>
- <span data-ttu-id="146d1-542">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-543">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="146d1-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="146d1-544">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-545">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-545">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-546">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-547">43字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-548">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-549">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-549">Checksum</span></span>

<span data-ttu-id="146d1-550">否</span><span class="sxs-lookup"><span data-stu-id="146d1-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-551">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-551">Definition</span></span>

<span data-ttu-id="146d1-552">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-553">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-554">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-555">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-557">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-558">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-558">contoso</span></span>
- <span data-ttu-id="146d1-559">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-559">fabrikam</span></span>
- <span data-ttu-id="146d1-560">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-560">northwind</span></span>
- <span data-ttu-id="146d1-561">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-561">sandbox</span></span>
- <span data-ttu-id="146d1-562">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-562">onebox</span></span>
- <span data-ttu-id="146d1-563">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-563">localhost</span></span>
- <span data-ttu-id="146d1-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-564">127.0.0.1</span></span>
- <span data-ttu-id="146d1-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-566">com</span><span class="sxs-lookup"><span data-stu-id="146d1-566">com</span></span>
- <span data-ttu-id="146d1-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-568">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="146d1-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="146d1-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="146d1-570">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-570">Format</span></span>

<span data-ttu-id="146d1-571">字符串 "userpwd ="，后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="146d1-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-572">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-572">Pattern</span></span>

- <span data-ttu-id="146d1-573">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="146d1-573">The string "userpwd="</span></span>
- <span data-ttu-id="146d1-574">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="146d1-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="146d1-575">一个引号（"）</span><span class="sxs-lookup"><span data-stu-id="146d1-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-576">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-576">Checksum</span></span>

<span data-ttu-id="146d1-577">否</span><span class="sxs-lookup"><span data-stu-id="146d1-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-578">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-578">Definition</span></span>

<span data-ttu-id="146d1-579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-581">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-582">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-584">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-585">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-585">contoso</span></span>
- <span data-ttu-id="146d1-586">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-586">fabrikam</span></span>
- <span data-ttu-id="146d1-587">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-587">northwind</span></span>
- <span data-ttu-id="146d1-588">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-588">sandbox</span></span>
- <span data-ttu-id="146d1-589">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-589">onebox</span></span>
- <span data-ttu-id="146d1-590">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-590">localhost</span></span>
- <span data-ttu-id="146d1-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-591">127.0.0.1</span></span>
- <span data-ttu-id="146d1-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-593">com</span><span class="sxs-lookup"><span data-stu-id="146d1-593">com</span></span>
- <span data-ttu-id="146d1-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-595">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="146d1-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="146d1-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="146d1-597">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-597">Format</span></span>

<span data-ttu-id="146d1-598">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="146d1-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-599">net "，后跟下面的模式中所述的字符和字符串，包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="146d1-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-600">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-600">Pattern</span></span>

- <span data-ttu-id="146d1-601">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="146d1-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-602">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-602">net"</span></span>
- <span data-ttu-id="146d1-603">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-604">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="146d1-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="146d1-605">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-606">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-606">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-607">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-608">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="146d1-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-609">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-610">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-610">Checksum</span></span>

<span data-ttu-id="146d1-611">否</span><span class="sxs-lookup"><span data-stu-id="146d1-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-612">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-612">Definition</span></span>

<span data-ttu-id="146d1-613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-614">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="146d1-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="146d1-615">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-616">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-618">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-619">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-619">contoso</span></span>
- <span data-ttu-id="146d1-620">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-620">fabrikam</span></span>
- <span data-ttu-id="146d1-621">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-621">northwind</span></span>
- <span data-ttu-id="146d1-622">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-622">sandbox</span></span>
- <span data-ttu-id="146d1-623">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-623">onebox</span></span>
- <span data-ttu-id="146d1-624">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-624">localhost</span></span>
- <span data-ttu-id="146d1-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-625">127.0.0.1</span></span>
- <span data-ttu-id="146d1-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-627">com</span><span class="sxs-lookup"><span data-stu-id="146d1-627">com</span></span>
- <span data-ttu-id="146d1-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-629">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="146d1-630">Azure SA</span><span class="sxs-lookup"><span data-stu-id="146d1-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="146d1-631">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-631">Format</span></span>

<span data-ttu-id="146d1-632">字符串 "sig"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="146d1-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-633">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-633">Pattern</span></span>

- <span data-ttu-id="146d1-634">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="146d1-634">The string "sig"</span></span>
- <span data-ttu-id="146d1-635">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-636">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-636">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-637">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-638">介于43-53 个字符和小写字母、数字或百分比符号（%）之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="146d1-639">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="146d1-639">The string "%3d"</span></span>
- <span data-ttu-id="146d1-640">不是字母或大写字符、数字或百分号（%）的任何字符</span><span class="sxs-lookup"><span data-stu-id="146d1-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-641">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-641">Checksum</span></span>

<span data-ttu-id="146d1-642">否</span><span class="sxs-lookup"><span data-stu-id="146d1-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-643">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-643">Definition</span></span>

<span data-ttu-id="146d1-644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-645">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="146d1-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="146d1-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="146d1-647">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-647">Format</span></span>

<span data-ttu-id="146d1-648">字符串 "终结点"，后跟下面模式中所示的字符和字符串，包括字符串 "</span><span class="sxs-lookup"><span data-stu-id="146d1-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="146d1-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-650">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-650">Pattern</span></span>

- <span data-ttu-id="146d1-651">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="146d1-651">The string "EndPoint"</span></span>
- <span data-ttu-id="146d1-652">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-653">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-653">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-654">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-655">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-656">字符串 "</span><span class="sxs-lookup"><span data-stu-id="146d1-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-657">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-657">net"</span></span>
- <span data-ttu-id="146d1-658">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-659">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="146d1-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="146d1-660">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-661">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-661">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-662">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-663">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="146d1-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-664">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-665">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-665">Checksum</span></span>

<span data-ttu-id="146d1-666">否</span><span class="sxs-lookup"><span data-stu-id="146d1-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-667">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-667">Definition</span></span>

<span data-ttu-id="146d1-668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-669">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="146d1-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="146d1-670">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-671">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-673">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-674">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-674">contoso</span></span>
- <span data-ttu-id="146d1-675">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-675">fabrikam</span></span>
- <span data-ttu-id="146d1-676">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-676">northwind</span></span>
- <span data-ttu-id="146d1-677">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-677">sandbox</span></span>
- <span data-ttu-id="146d1-678">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-678">onebox</span></span>
- <span data-ttu-id="146d1-679">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-679">localhost</span></span>
- <span data-ttu-id="146d1-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-680">127.0.0.1</span></span>
- <span data-ttu-id="146d1-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-682">com</span><span class="sxs-lookup"><span data-stu-id="146d1-682">com</span></span>
- <span data-ttu-id="146d1-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-684">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="146d1-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="146d1-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="146d1-686">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-686">Format</span></span>

<span data-ttu-id="146d1-687">字符串 "DefaultEndpointsProtocol"，后跟下面模式中所述的字符和字符串，包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="146d1-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-688">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-688">Pattern</span></span>

- <span data-ttu-id="146d1-689">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="146d1-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="146d1-690">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-691">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-691">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-692">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-693">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-694">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="146d1-694">The string "AccountKey"</span></span>
- <span data-ttu-id="146d1-695">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-696">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-696">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-697">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="146d1-698">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="146d1-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-699">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-700">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-700">Checksum</span></span>

<span data-ttu-id="146d1-701">否</span><span class="sxs-lookup"><span data-stu-id="146d1-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-702">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-702">Definition</span></span>

<span data-ttu-id="146d1-703">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-704">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-705">正则表达式**CEP_AzureEmulatorStorageAccountFilter 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-706">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-707">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="146d1-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="146d1-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="146d1-709">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="146d1-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-712">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-713">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-713">contoso</span></span>
- <span data-ttu-id="146d1-714">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-714">fabrikam</span></span>
- <span data-ttu-id="146d1-715">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-715">northwind</span></span>
- <span data-ttu-id="146d1-716">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-716">sandbox</span></span>
- <span data-ttu-id="146d1-717">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-717">onebox</span></span>
- <span data-ttu-id="146d1-718">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-718">localhost</span></span>
- <span data-ttu-id="146d1-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-719">127.0.0.1</span></span>
- <span data-ttu-id="146d1-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-721">com</span><span class="sxs-lookup"><span data-stu-id="146d1-721">com</span></span>
- <span data-ttu-id="146d1-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-723">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="146d1-724">Azure 存储帐户密钥（常规）</span><span class="sxs-lookup"><span data-stu-id="146d1-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-725">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-725">Format</span></span>

<span data-ttu-id="146d1-726">任何86位或大写字母、数字、正斜杠（/）或加号（+）的任意组合，前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="146d1-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-727">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-727">Pattern</span></span>

- <span data-ttu-id="146d1-728">大于号（>）、撇号（'）、等号（=）、引号（"）或数字符号（#）的0-1</span><span class="sxs-lookup"><span data-stu-id="146d1-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="146d1-729">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="146d1-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="146d1-730">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="146d1-731">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-731">Checksum</span></span>

<span data-ttu-id="146d1-732">否</span><span class="sxs-lookup"><span data-stu-id="146d1-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-733">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-733">Definition</span></span>

<span data-ttu-id="146d1-734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-735">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="146d1-736">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="146d1-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-737">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-737">Format</span></span>

<span data-ttu-id="146d1-738">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="146d1-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-739">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-739">Pattern</span></span>

<span data-ttu-id="146d1-740">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="146d1-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="146d1-741">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="146d1-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="146d1-742">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-742">A hyphen</span></span> 
- <span data-ttu-id="146d1-743">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="146d1-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="146d1-744">一个点</span><span class="sxs-lookup"><span data-stu-id="146d1-744">A period</span></span> 
- <span data-ttu-id="146d1-745">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-746">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-746">Checksum</span></span>

<span data-ttu-id="146d1-747">是</span><span class="sxs-lookup"><span data-stu-id="146d1-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-748">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-748">Definition</span></span>

<span data-ttu-id="146d1-749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-750">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-751">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="146d1-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-753">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="146d1-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="146d1-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="146d1-755">标识</span><span class="sxs-lookup"><span data-stu-id="146d1-755">Identity</span></span>
- <span data-ttu-id="146d1-756">注册</span><span class="sxs-lookup"><span data-stu-id="146d1-756">Registration</span></span>
- <span data-ttu-id="146d1-757">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-757">Identification</span></span> 
- <span data-ttu-id="146d1-758">ID</span><span class="sxs-lookup"><span data-stu-id="146d1-758">ID</span></span> 
- <span data-ttu-id="146d1-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="146d1-759">Identiteitskaart</span></span>
- <span data-ttu-id="146d1-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="146d1-760">Registratie nummer</span></span> 
- <span data-ttu-id="146d1-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="146d1-761">Identificatie nummer</span></span> 
- <span data-ttu-id="146d1-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="146d1-762">Identiteit</span></span>
- <span data-ttu-id="146d1-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="146d1-763">Registratie</span></span>
- <span data-ttu-id="146d1-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="146d1-764">Identificatie</span></span> 
- <span data-ttu-id="146d1-765">D'identité</span><span class="sxs-lookup"><span data-stu-id="146d1-765">Carte d'identité</span></span> 
- <span data-ttu-id="146d1-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="146d1-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="146d1-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="146d1-767">numéro d'identification</span></span>
- <span data-ttu-id="146d1-768">identité</span><span class="sxs-lookup"><span data-stu-id="146d1-768">identité</span></span> 
- <span data-ttu-id="146d1-769">inscription</span><span class="sxs-lookup"><span data-stu-id="146d1-769">inscription</span></span> 
- <span data-ttu-id="146d1-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="146d1-770">Identifikation</span></span>
- <span data-ttu-id="146d1-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="146d1-771">Identifizierung</span></span>
- <span data-ttu-id="146d1-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-772">Identifikationsnummer</span></span>
- <span data-ttu-id="146d1-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="146d1-773">Personalausweis</span></span>
- <span data-ttu-id="146d1-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="146d1-774">Registrierung</span></span>
- <span data-ttu-id="146d1-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="146d1-776">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="146d1-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-777">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-777">Format</span></span>

<span data-ttu-id="146d1-778">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="146d1-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-779">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-779">Pattern</span></span>

<span data-ttu-id="146d1-780">格式</span><span class="sxs-lookup"><span data-stu-id="146d1-780">Formatted:</span></span>
- <span data-ttu-id="146d1-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-781">Three digits</span></span> 
- <span data-ttu-id="146d1-782">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-782">A period</span></span> 
- <span data-ttu-id="146d1-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-783">Three digits</span></span> 
- <span data-ttu-id="146d1-784">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-784">A period</span></span> 
- <span data-ttu-id="146d1-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-785">Three digits</span></span> 
- <span data-ttu-id="146d1-786">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-786">A hyphen</span></span> 
- <span data-ttu-id="146d1-787">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-787">Two digits which are check digits</span></span>

<span data-ttu-id="146d1-788">纯</span><span class="sxs-lookup"><span data-stu-id="146d1-788">Unformatted:</span></span>
- <span data-ttu-id="146d1-789">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-790">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-790">Checksum</span></span>

<span data-ttu-id="146d1-791">是</span><span class="sxs-lookup"><span data-stu-id="146d1-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-792">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-792">Definition</span></span>

<span data-ttu-id="146d1-793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-794">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-795">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="146d1-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-796">The checksum passes.</span></span>

<span data-ttu-id="146d1-797">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-798">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-800">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="146d1-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="146d1-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="146d1-802">CPF</span><span class="sxs-lookup"><span data-stu-id="146d1-802">CPF</span></span>
- <span data-ttu-id="146d1-803">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-803">Identification</span></span>
- <span data-ttu-id="146d1-804">注册</span><span class="sxs-lookup"><span data-stu-id="146d1-804">Registration</span></span>
- <span data-ttu-id="146d1-805">营业</span><span class="sxs-lookup"><span data-stu-id="146d1-805">Revenue</span></span>
- <span data-ttu-id="146d1-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="146d1-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="146d1-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="146d1-807">Imposto</span></span> 
- <span data-ttu-id="146d1-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="146d1-808">Identificação</span></span> 
- <span data-ttu-id="146d1-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="146d1-809">Inscrição</span></span> 
- <span data-ttu-id="146d1-810">Receita</span><span class="sxs-lookup"><span data-stu-id="146d1-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="146d1-811">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="146d1-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-812">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-812">Format</span></span>

<span data-ttu-id="146d1-813">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="146d1-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-814">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-814">Pattern</span></span>
<span data-ttu-id="146d1-815">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="146d1-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="146d1-816">两个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-816">Two digits</span></span> 
- <span data-ttu-id="146d1-817">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-817">A period</span></span> 
- <span data-ttu-id="146d1-818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-818">Three digits</span></span> 
- <span data-ttu-id="146d1-819">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-819">A period</span></span> 
- <span data-ttu-id="146d1-820">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="146d1-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="146d1-821">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="146d1-821">A forward slash</span></span> 
- <span data-ttu-id="146d1-822">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="146d1-822">Four-digit branch number</span></span> 
- <span data-ttu-id="146d1-823">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-823">A hyphen</span></span> 
- <span data-ttu-id="146d1-824">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-825">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-825">Checksum</span></span>

<span data-ttu-id="146d1-826">是</span><span class="sxs-lookup"><span data-stu-id="146d1-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-827">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-827">Definition</span></span>

<span data-ttu-id="146d1-828">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-829">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-830">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="146d1-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-831">The checksum passes.</span></span>

<span data-ttu-id="146d1-832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-833">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-835">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="146d1-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="146d1-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="146d1-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="146d1-837">CNPJ</span></span> 
- <span data-ttu-id="146d1-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="146d1-838">CNPJ/MF</span></span> 
- <span data-ttu-id="146d1-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="146d1-839">CNPJ-MF</span></span> 
- <span data-ttu-id="146d1-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="146d1-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="146d1-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="146d1-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="146d1-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="146d1-842">Legal entity</span></span> 
- <span data-ttu-id="146d1-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="146d1-843">Legal entities</span></span> 
- <span data-ttu-id="146d1-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="146d1-844">Registration Status</span></span> 
- <span data-ttu-id="146d1-845">商业版</span><span class="sxs-lookup"><span data-stu-id="146d1-845">Business</span></span> 
- <span data-ttu-id="146d1-846">Company</span><span class="sxs-lookup"><span data-stu-id="146d1-846">Company</span></span>
- <span data-ttu-id="146d1-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="146d1-847">CNPJ</span></span> 
- <span data-ttu-id="146d1-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="146d1-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="146d1-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="146d1-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="146d1-850">CGC</span><span class="sxs-lookup"><span data-stu-id="146d1-850">CGC</span></span> 
- <span data-ttu-id="146d1-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="146d1-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="146d1-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="146d1-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="146d1-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="146d1-853">Situação cadastral</span></span> 
- <span data-ttu-id="146d1-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="146d1-854">Inscrição</span></span> 
- <span data-ttu-id="146d1-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="146d1-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="146d1-856">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="146d1-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-857">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-857">Format</span></span>

<span data-ttu-id="146d1-858">Registro Geral （旧格式）：9个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="146d1-859">Registro de Identidade （RIC）（新格式）：11个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-860">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-860">Pattern</span></span>

<span data-ttu-id="146d1-861">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="146d1-862">两个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-862">Two digits</span></span> 
- <span data-ttu-id="146d1-863">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-863">A period</span></span> 
- <span data-ttu-id="146d1-864">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-864">Three digits</span></span> 
- <span data-ttu-id="146d1-865">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-865">A period</span></span> 
- <span data-ttu-id="146d1-866">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-866">Three digits</span></span> 
- <span data-ttu-id="146d1-867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-867">A hyphen</span></span> 
- <span data-ttu-id="146d1-868">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-868">One digit which is a check digit</span></span>

<span data-ttu-id="146d1-869">Registro de Identidade （RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="146d1-870">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-870">10 digits</span></span> 
- <span data-ttu-id="146d1-871">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-871">A hyphen</span></span> 
- <span data-ttu-id="146d1-872">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-873">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-873">Checksum</span></span>

<span data-ttu-id="146d1-874">是</span><span class="sxs-lookup"><span data-stu-id="146d1-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-875">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-875">Definition</span></span>

<span data-ttu-id="146d1-876">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-877">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-878">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="146d1-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-879">The checksum passes.</span></span>

<span data-ttu-id="146d1-880">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-881">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-883">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="146d1-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="146d1-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="146d1-885">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG （此关键字区分大小写） RIC （此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="146d1-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-887">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-887">Format</span></span>

<span data-ttu-id="146d1-888">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-889">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-889">Pattern</span></span>

<span data-ttu-id="146d1-890">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="146d1-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="146d1-891">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="146d1-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="146d1-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-892">Five digits</span></span> 
- <span data-ttu-id="146d1-893">连字符</span><span class="sxs-lookup"><span data-stu-id="146d1-893">A hyphen</span></span> 
- <span data-ttu-id="146d1-894">三位数字或</span><span class="sxs-lookup"><span data-stu-id="146d1-894">Three digits OR</span></span>
- <span data-ttu-id="146d1-895">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="146d1-895">A zero "0"</span></span> 
- <span data-ttu-id="146d1-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-897">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-897">Checksum</span></span>

<span data-ttu-id="146d1-898">否</span><span class="sxs-lookup"><span data-stu-id="146d1-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-899">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-899">Definition</span></span>

<span data-ttu-id="146d1-900">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-901">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-902">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="146d1-903">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="146d1-904">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-905">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-906">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-907">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="146d1-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="146d1-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="146d1-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="146d1-909">canada savings bonds</span></span>
- <span data-ttu-id="146d1-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="146d1-910">canada revenue agency</span></span>
- <span data-ttu-id="146d1-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="146d1-911">canadian financial institution</span></span>
- <span data-ttu-id="146d1-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="146d1-912">direct deposit form</span></span>
- <span data-ttu-id="146d1-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="146d1-913">canadian citizen</span></span>
- <span data-ttu-id="146d1-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="146d1-914">legal representative</span></span>
- <span data-ttu-id="146d1-915">notary public</span><span class="sxs-lookup"><span data-stu-id="146d1-915">notary public</span></span>
- <span data-ttu-id="146d1-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="146d1-916">commissioner for oaths</span></span>
- <span data-ttu-id="146d1-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="146d1-917">child care benefit</span></span>
- <span data-ttu-id="146d1-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="146d1-918">universal child care</span></span>
- <span data-ttu-id="146d1-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="146d1-919">canada child tax benefit</span></span>
- <span data-ttu-id="146d1-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="146d1-920">income tax benefit</span></span>
- <span data-ttu-id="146d1-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="146d1-921">harmonized sales tax</span></span>
- <span data-ttu-id="146d1-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="146d1-922">social insurance number</span></span>
- <span data-ttu-id="146d1-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="146d1-923">income tax refund</span></span>
- <span data-ttu-id="146d1-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="146d1-924">child tax benefit</span></span>
- <span data-ttu-id="146d1-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="146d1-925">territorial payments</span></span>
- <span data-ttu-id="146d1-926">institution number</span><span class="sxs-lookup"><span data-stu-id="146d1-926">institution number</span></span>
- <span data-ttu-id="146d1-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="146d1-927">deposit request</span></span>
- <span data-ttu-id="146d1-928">banking information</span><span class="sxs-lookup"><span data-stu-id="146d1-928">banking information</span></span>
- <span data-ttu-id="146d1-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="146d1-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="146d1-930">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-931">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-931">Format</span></span>

<span data-ttu-id="146d1-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="146d1-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-933">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-933">Pattern</span></span>

<span data-ttu-id="146d1-934">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="146d1-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-935">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-935">Checksum</span></span>

<span data-ttu-id="146d1-936">否</span><span class="sxs-lookup"><span data-stu-id="146d1-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-937">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-937">Definition</span></span>

<span data-ttu-id="146d1-938">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-939">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-940">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="146d1-941">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-942">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="146d1-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="146d1-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="146d1-944">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="146d1-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="146d1-945">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="146d1-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="146d1-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="146d1-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="146d1-947">通讯</span><span class="sxs-lookup"><span data-stu-id="146d1-947">DL</span></span>
- <span data-ttu-id="146d1-948">DLS</span><span class="sxs-lookup"><span data-stu-id="146d1-948">DLS</span></span>
- <span data-ttu-id="146d1-949">采用</span><span class="sxs-lookup"><span data-stu-id="146d1-949">CDL</span></span>
- <span data-ttu-id="146d1-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="146d1-950">CDLS</span></span>
- <span data-ttu-id="146d1-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="146d1-951">DriverLic</span></span>
- <span data-ttu-id="146d1-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="146d1-952">DriverLics</span></span>
- <span data-ttu-id="146d1-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-953">DriverLicense</span></span>
- <span data-ttu-id="146d1-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-954">DriverLicenses</span></span>
- <span data-ttu-id="146d1-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-955">DriverLicence</span></span>
- <span data-ttu-id="146d1-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-956">DriverLicences</span></span>
- <span data-ttu-id="146d1-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-957">Driver Lic</span></span>
- <span data-ttu-id="146d1-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-958">Driver Lics</span></span>
- <span data-ttu-id="146d1-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="146d1-959">Driver License</span></span>
- <span data-ttu-id="146d1-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-960">Driver Licenses</span></span>
- <span data-ttu-id="146d1-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-961">Driver Licence</span></span>
- <span data-ttu-id="146d1-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-962">Driver Licences</span></span>
- <span data-ttu-id="146d1-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="146d1-963">DriversLic</span></span>
- <span data-ttu-id="146d1-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="146d1-964">DriversLics</span></span>
- <span data-ttu-id="146d1-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-965">DriversLicence</span></span>
- <span data-ttu-id="146d1-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-966">DriversLicences</span></span>
- <span data-ttu-id="146d1-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-967">DriversLicense</span></span>
- <span data-ttu-id="146d1-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-968">DriversLicenses</span></span>
- <span data-ttu-id="146d1-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-969">Drivers Lic</span></span>
- <span data-ttu-id="146d1-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-970">Drivers Lics</span></span>
- <span data-ttu-id="146d1-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="146d1-971">Drivers License</span></span>
- <span data-ttu-id="146d1-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-972">Drivers Licenses</span></span>
- <span data-ttu-id="146d1-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-973">Drivers Licence</span></span>
- <span data-ttu-id="146d1-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-974">Drivers Licences</span></span>
- <span data-ttu-id="146d1-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-975">Driver'Lic</span></span>
- <span data-ttu-id="146d1-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-976">Driver'Lics</span></span>
- <span data-ttu-id="146d1-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="146d1-977">Driver'License</span></span>
- <span data-ttu-id="146d1-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-978">Driver'Licenses</span></span>
- <span data-ttu-id="146d1-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-979">Driver'Licence</span></span>
- <span data-ttu-id="146d1-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-980">Driver'Licences</span></span>
- <span data-ttu-id="146d1-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-981">Driver' Lic</span></span>
- <span data-ttu-id="146d1-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-982">Driver' Lics</span></span>
- <span data-ttu-id="146d1-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="146d1-983">Driver' License</span></span>
- <span data-ttu-id="146d1-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-984">Driver' Licenses</span></span>
- <span data-ttu-id="146d1-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-985">Driver' Licence</span></span>
- <span data-ttu-id="146d1-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-986">Driver' Licences</span></span>
- <span data-ttu-id="146d1-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="146d1-987">Driver'sLic</span></span>
- <span data-ttu-id="146d1-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="146d1-988">Driver'sLics</span></span>
- <span data-ttu-id="146d1-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-989">Driver'sLicense</span></span>
- <span data-ttu-id="146d1-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-990">Driver'sLicenses</span></span>
- <span data-ttu-id="146d1-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="146d1-991">Driver'sLicence</span></span>
- <span data-ttu-id="146d1-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="146d1-992">Driver'sLicences</span></span>
- <span data-ttu-id="146d1-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-993">Driver's Lic</span></span>
- <span data-ttu-id="146d1-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-994">Driver's Lics</span></span>
- <span data-ttu-id="146d1-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="146d1-995">Driver's License</span></span>
- <span data-ttu-id="146d1-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-996">Driver's Licenses</span></span>
- <span data-ttu-id="146d1-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-997">Driver's Licence</span></span>
- <span data-ttu-id="146d1-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-998">Driver's Licences</span></span>
- <span data-ttu-id="146d1-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="146d1-999">Permis de Conduire</span></span>
- <span data-ttu-id="146d1-1000">id</span><span class="sxs-lookup"><span data-stu-id="146d1-1000">id</span></span>
- <span data-ttu-id="146d1-1001">ids</span><span class="sxs-lookup"><span data-stu-id="146d1-1001">ids</span></span>
- <span data-ttu-id="146d1-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="146d1-1002">idcard number</span></span>
- <span data-ttu-id="146d1-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1003">idcard numbers</span></span>
- <span data-ttu-id="146d1-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="146d1-1004">idcard #</span></span>
- <span data-ttu-id="146d1-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="146d1-1005">idcard #s</span></span>
- <span data-ttu-id="146d1-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="146d1-1006">idcard card</span></span>
- <span data-ttu-id="146d1-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1007">idcard cards</span></span>
- <span data-ttu-id="146d1-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1008">idcard</span></span>
- <span data-ttu-id="146d1-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-1009">identification number</span></span>
- <span data-ttu-id="146d1-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1010">identification numbers</span></span>
- <span data-ttu-id="146d1-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="146d1-1011">identification #</span></span>
- <span data-ttu-id="146d1-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="146d1-1012">identification #s</span></span>
- <span data-ttu-id="146d1-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="146d1-1013">identification card</span></span>
- <span data-ttu-id="146d1-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1014">identification cards</span></span>
- <span data-ttu-id="146d1-1015">id</span><span class="sxs-lookup"><span data-stu-id="146d1-1015">identification</span></span> 
- <span data-ttu-id="146d1-1016">通讯#</span><span class="sxs-lookup"><span data-stu-id="146d1-1016">DL#</span></span>
- <span data-ttu-id="146d1-1017">DLS#</span><span class="sxs-lookup"><span data-stu-id="146d1-1017">DLS#</span></span> 
- <span data-ttu-id="146d1-1018">采用#</span><span class="sxs-lookup"><span data-stu-id="146d1-1018">CDL#</span></span> 
- <span data-ttu-id="146d1-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="146d1-1019">CDLS#</span></span> 
- <span data-ttu-id="146d1-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1020">DriverLic#</span></span> 
- <span data-ttu-id="146d1-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1021">DriverLics#</span></span> 
- <span data-ttu-id="146d1-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-1022">DriverLicense#</span></span> 
- <span data-ttu-id="146d1-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="146d1-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1024">DriverLicence#</span></span> 
- <span data-ttu-id="146d1-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1025">DriverLicences#</span></span> 
- <span data-ttu-id="146d1-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1026">Driver Lic#</span></span>
- <span data-ttu-id="146d1-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1027">Driver Lics#</span></span> 
- <span data-ttu-id="146d1-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1028">Driver License#</span></span> 
- <span data-ttu-id="146d1-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="146d1-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1030">Driver License#</span></span> 
- <span data-ttu-id="146d1-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1031">Driver Licences#</span></span> 
- <span data-ttu-id="146d1-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1032">DriversLic#</span></span> 
- <span data-ttu-id="146d1-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1033">DriversLics#</span></span> 
- <span data-ttu-id="146d1-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-1034">DriversLicense#</span></span> 
- <span data-ttu-id="146d1-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="146d1-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1036">DriversLicence#</span></span> 
- <span data-ttu-id="146d1-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1037">DriversLicences#</span></span> 
- <span data-ttu-id="146d1-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="146d1-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="146d1-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1040">Drivers License#</span></span> 
- <span data-ttu-id="146d1-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="146d1-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="146d1-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="146d1-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="146d1-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="146d1-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1046">Driver'License#</span></span> 
- <span data-ttu-id="146d1-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="146d1-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="146d1-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="146d1-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="146d1-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="146d1-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1052">Driver' License#</span></span> 
- <span data-ttu-id="146d1-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="146d1-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="146d1-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="146d1-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="146d1-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="146d1-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="146d1-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="146d1-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="146d1-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="146d1-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="146d1-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="146d1-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="146d1-1064">Driver's License#</span></span> 
- <span data-ttu-id="146d1-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="146d1-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="146d1-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="146d1-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="146d1-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="146d1-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="146d1-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="146d1-1069">号#</span><span class="sxs-lookup"><span data-stu-id="146d1-1069">id#</span></span> 
- <span data-ttu-id="146d1-1070">id#</span><span class="sxs-lookup"><span data-stu-id="146d1-1070">ids#</span></span> 
- <span data-ttu-id="146d1-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="146d1-1071">idcard card#</span></span> 
- <span data-ttu-id="146d1-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="146d1-1072">idcard cards#</span></span> 
- <span data-ttu-id="146d1-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="146d1-1073">idcard#</span></span> 
- <span data-ttu-id="146d1-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="146d1-1074">identification card#</span></span> 
- <span data-ttu-id="146d1-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="146d1-1075">identification cards#</span></span> 
- <span data-ttu-id="146d1-1076">id#</span><span class="sxs-lookup"><span data-stu-id="146d1-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="146d1-1077">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="146d1-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1078">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1078">Format</span></span>

<span data-ttu-id="146d1-1079">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1080">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1080">Pattern</span></span>

<span data-ttu-id="146d1-1081">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1082">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1082">Checksum</span></span>

<span data-ttu-id="146d1-1083">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1084">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1084">Definition</span></span>

<span data-ttu-id="146d1-1085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1086">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1087">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1088">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="146d1-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="146d1-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="146d1-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="146d1-1090">personal health number</span></span>
- <span data-ttu-id="146d1-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="146d1-1091">patient information</span></span>
- <span data-ttu-id="146d1-1092">health services</span><span class="sxs-lookup"><span data-stu-id="146d1-1092">health services</span></span>
- <span data-ttu-id="146d1-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="146d1-1093">speciality services</span></span>
- <span data-ttu-id="146d1-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="146d1-1094">automobile accident</span></span>
- <span data-ttu-id="146d1-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="146d1-1095">patient hospital</span></span>
- <span data-ttu-id="146d1-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="146d1-1096">psychiatrist</span></span>
- <span data-ttu-id="146d1-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="146d1-1097">workers compensation</span></span>
- <span data-ttu-id="146d1-1098">障碍</span><span class="sxs-lookup"><span data-stu-id="146d1-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="146d1-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1100">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1100">Format</span></span>

<span data-ttu-id="146d1-1101">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1102">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1102">Pattern</span></span>

<span data-ttu-id="146d1-1103">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1104">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1104">Checksum</span></span>

<span data-ttu-id="146d1-1105">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1106">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1106">Definition</span></span>

<span data-ttu-id="146d1-1107">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1108">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1109">找到 Keyword_canada_passport_number 或 Keyword_passport 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1110">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="146d1-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="146d1-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="146d1-1112">canadian citizenship</span></span>
- <span data-ttu-id="146d1-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="146d1-1113">canadian passport</span></span>
- <span data-ttu-id="146d1-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="146d1-1114">passport application</span></span>
- <span data-ttu-id="146d1-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="146d1-1115">passport photos</span></span>
- <span data-ttu-id="146d1-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="146d1-1116">certified translator</span></span>
- <span data-ttu-id="146d1-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="146d1-1117">canadian citizens</span></span>
- <span data-ttu-id="146d1-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="146d1-1118">processing times</span></span>
- <span data-ttu-id="146d1-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="146d1-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="146d1-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-1120">Keyword_passport</span></span>

- <span data-ttu-id="146d1-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="146d1-1121">Passport Number</span></span>
- <span data-ttu-id="146d1-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="146d1-1122">Passport No</span></span>
- <span data-ttu-id="146d1-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-1123">Passport #</span></span>
- <span data-ttu-id="146d1-1124">登记卡#</span><span class="sxs-lookup"><span data-stu-id="146d1-1124">Passport#</span></span>
- <span data-ttu-id="146d1-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="146d1-1125">PassportID</span></span>
- <span data-ttu-id="146d1-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="146d1-1126">Passportno</span></span>
- <span data-ttu-id="146d1-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-1127">passportnumber</span></span>
- <span data-ttu-id="146d1-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-1128">パスポート</span></span>
- <span data-ttu-id="146d1-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-1129">パスポート番号</span></span>
- <span data-ttu-id="146d1-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-1130">パスポートのNum</span></span>
- <span data-ttu-id="146d1-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="146d1-1131">パスポート＃</span></span>
- <span data-ttu-id="146d1-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="146d1-1132">Numéro de passeport</span></span>
- <span data-ttu-id="146d1-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="146d1-1133">Passeport n °</span></span>
- <span data-ttu-id="146d1-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="146d1-1134">Passeport Non</span></span>
- <span data-ttu-id="146d1-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="146d1-1135">Passeport #</span></span>
- <span data-ttu-id="146d1-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="146d1-1136">Passeport#</span></span>
- <span data-ttu-id="146d1-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="146d1-1137">PasseportNon</span></span>
- <span data-ttu-id="146d1-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="146d1-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="146d1-1139">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="146d1-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1140">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1140">Format</span></span>

<span data-ttu-id="146d1-1141">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1142">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1142">Pattern</span></span>

<span data-ttu-id="146d1-1143">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1144">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1144">Checksum</span></span>

<span data-ttu-id="146d1-1145">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1146">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1146">Definition</span></span>

<span data-ttu-id="146d1-1147">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-1148">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="146d1-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1149">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="146d1-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="146d1-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="146d1-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="146d1-1151">social insurance number</span></span>
- <span data-ttu-id="146d1-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="146d1-1152">health information act</span></span>
- <span data-ttu-id="146d1-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="146d1-1153">income tax information</span></span>
- <span data-ttu-id="146d1-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="146d1-1154">manitoba health</span></span>
- <span data-ttu-id="146d1-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="146d1-1155">health registration</span></span>
- <span data-ttu-id="146d1-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="146d1-1156">prescription purchases</span></span>
- <span data-ttu-id="146d1-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="146d1-1157">benefit eligibility</span></span>
- <span data-ttu-id="146d1-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="146d1-1158">personal health</span></span>
- <span data-ttu-id="146d1-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="146d1-1159">power of attorney</span></span>
- <span data-ttu-id="146d1-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="146d1-1160">registration number</span></span>
- <span data-ttu-id="146d1-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="146d1-1161">personal health number</span></span>
- <span data-ttu-id="146d1-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="146d1-1162">practitioner referral</span></span>
- <span data-ttu-id="146d1-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="146d1-1163">wellness professional</span></span>
- <span data-ttu-id="146d1-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="146d1-1164">patient referral</span></span>
- <span data-ttu-id="146d1-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="146d1-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="146d1-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="146d1-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="146d1-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="146d1-1167">Nunavut</span></span>
- <span data-ttu-id="146d1-1168">省</span><span class="sxs-lookup"><span data-stu-id="146d1-1168">Quebec</span></span>
- <span data-ttu-id="146d1-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="146d1-1169">Northwest Territories</span></span>
- <span data-ttu-id="146d1-1170">省</span><span class="sxs-lookup"><span data-stu-id="146d1-1170">Ontario</span></span>
- <span data-ttu-id="146d1-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="146d1-1171">British Columbia</span></span>
- <span data-ttu-id="146d1-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="146d1-1172">Alberta</span></span>
- <span data-ttu-id="146d1-1173">彻</span><span class="sxs-lookup"><span data-stu-id="146d1-1173">Saskatchewan</span></span>
- <span data-ttu-id="146d1-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="146d1-1174">Manitoba</span></span>
- <span data-ttu-id="146d1-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="146d1-1175">Yukon</span></span>
- <span data-ttu-id="146d1-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="146d1-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="146d1-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="146d1-1177">New Brunswick</span></span>
- <span data-ttu-id="146d1-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="146d1-1178">Nova Scotia</span></span>
- <span data-ttu-id="146d1-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="146d1-1179">Prince Edward Island</span></span>
- <span data-ttu-id="146d1-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="146d1-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="146d1-1181">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1182">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1182">Format</span></span>

<span data-ttu-id="146d1-1183">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="146d1-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1184">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1184">Pattern</span></span>

<span data-ttu-id="146d1-1185">格式</span><span class="sxs-lookup"><span data-stu-id="146d1-1185">Formatted:</span></span>
- <span data-ttu-id="146d1-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1186">Three digits</span></span> 
- <span data-ttu-id="146d1-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="146d1-1187">A hyphen or space</span></span> 
- <span data-ttu-id="146d1-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1188">Three digits</span></span> 
- <span data-ttu-id="146d1-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="146d1-1189">A hyphen or space</span></span> 
- <span data-ttu-id="146d1-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1190">Three digits</span></span>

<span data-ttu-id="146d1-1191">未格式化：9个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1192">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1192">Checksum</span></span>

<span data-ttu-id="146d1-1193">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1194">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1194">Definition</span></span>

<span data-ttu-id="146d1-1195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1196">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1197">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="146d1-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="146d1-1198">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="146d1-1199">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="146d1-1200">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="146d1-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1201">The checksum passes.</span></span>

<span data-ttu-id="146d1-1202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1203">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1204">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="146d1-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1206">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="146d1-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="146d1-1207">Keyword_sin</span></span>

- <span data-ttu-id="146d1-1208">sin</span><span class="sxs-lookup"><span data-stu-id="146d1-1208">sin</span></span> 
- <span data-ttu-id="146d1-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="146d1-1209">social insurance</span></span> 
- <span data-ttu-id="146d1-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="146d1-1211">罪</span><span class="sxs-lookup"><span data-stu-id="146d1-1211">sins</span></span> 
- <span data-ttu-id="146d1-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="146d1-1212">ssn</span></span> 
- <span data-ttu-id="146d1-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="146d1-1213">ssns</span></span> 
- <span data-ttu-id="146d1-1214">social security</span><span class="sxs-lookup"><span data-stu-id="146d1-1214">social security</span></span> 
- <span data-ttu-id="146d1-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="146d1-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="146d1-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-1216">national identification number</span></span> 
- <span data-ttu-id="146d1-1217">national id</span><span class="sxs-lookup"><span data-stu-id="146d1-1217">national id</span></span> 
- <span data-ttu-id="146d1-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="146d1-1218">sin#</span></span> 
- <span data-ttu-id="146d1-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="146d1-1219">soc ins</span></span> 
- <span data-ttu-id="146d1-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="146d1-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="146d1-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="146d1-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="146d1-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="146d1-1222">driver's license</span></span> 
- <span data-ttu-id="146d1-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="146d1-1223">drivers license</span></span> 
- <span data-ttu-id="146d1-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="146d1-1224">driver's licence</span></span> 
- <span data-ttu-id="146d1-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="146d1-1225">drivers licence</span></span> 
- <span data-ttu-id="146d1-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="146d1-1226">DOB</span></span> 
- <span data-ttu-id="146d1-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="146d1-1227">Birthdate</span></span> 
- <span data-ttu-id="146d1-1228">一定</span><span class="sxs-lookup"><span data-stu-id="146d1-1228">Birthday</span></span> 
- <span data-ttu-id="146d1-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="146d1-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="146d1-1230">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1231">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1231">Format</span></span>

<span data-ttu-id="146d1-1232">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1233">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1233">Pattern</span></span>

<span data-ttu-id="146d1-1234">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="146d1-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="146d1-1235">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-1235">1-2 digits</span></span> 
- <span data-ttu-id="146d1-1236">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-1236">A period</span></span> 
- <span data-ttu-id="146d1-1237">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-1237">Three digits</span></span> 
- <span data-ttu-id="146d1-1238">一个点 </span><span class="sxs-lookup"><span data-stu-id="146d1-1238">A period</span></span> 
- <span data-ttu-id="146d1-1239">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-1239">Three digits</span></span> 
- <span data-ttu-id="146d1-1240">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="146d1-1240">A dash</span></span> 
- <span data-ttu-id="146d1-1241">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1242">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1242">Checksum</span></span>

<span data-ttu-id="146d1-1243">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1244">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1244">Definition</span></span>

<span data-ttu-id="146d1-1245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1246">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1247">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="146d1-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1248">The checksum passes.</span></span>

<span data-ttu-id="146d1-1249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1250">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1252">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="146d1-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="146d1-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="146d1-1254">National Identification Number</span></span> 
- <span data-ttu-id="146d1-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-1255">Identity card</span></span> 
- <span data-ttu-id="146d1-1256">ID</span><span class="sxs-lookup"><span data-stu-id="146d1-1256">ID</span></span> 
- <span data-ttu-id="146d1-1257">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-1257">Identification</span></span> 
- <span data-ttu-id="146d1-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="146d1-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="146d1-1259">以</span><span class="sxs-lookup"><span data-stu-id="146d1-1259">RUN</span></span> 
- <span data-ttu-id="146d1-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="146d1-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="146d1-1261">墨守成规</span><span class="sxs-lookup"><span data-stu-id="146d1-1261">RUT</span></span> 
- <span data-ttu-id="146d1-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="146d1-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="146d1-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="146d1-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="146d1-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="146d1-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="146d1-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="146d1-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="146d1-1266">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1267">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1267">Format</span></span>

<span data-ttu-id="146d1-1268">18 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1269">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1269">Pattern</span></span>

<span data-ttu-id="146d1-1270">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-1270">18 digits:</span></span>
- <span data-ttu-id="146d1-1271">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="146d1-1272">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="146d1-1273">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="146d1-1274">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1275">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1275">Checksum</span></span>

<span data-ttu-id="146d1-1276">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1277">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1277">Definition</span></span>

<span data-ttu-id="146d1-1278">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1279">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1280">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="146d1-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1281">The checksum passes.</span></span>

<span data-ttu-id="146d1-1282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1283">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1285">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="146d1-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="146d1-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="146d1-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="146d1-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="146d1-1288">台湾</span><span class="sxs-lookup"><span data-stu-id="146d1-1288">PRC</span></span> 
- <span data-ttu-id="146d1-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="146d1-1289">National Identification Card</span></span> 
- <span data-ttu-id="146d1-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="146d1-1290">身份证</span></span> 
- <span data-ttu-id="146d1-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="146d1-1291">居民 身份证</span></span> 
- <span data-ttu-id="146d1-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="146d1-1292">居民身份证</span></span> 
- <span data-ttu-id="146d1-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="146d1-1293">鉴定</span></span> 
- <span data-ttu-id="146d1-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-1294">身分證</span></span> 
- <span data-ttu-id="146d1-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-1295">居民 身份證</span></span>
- <span data-ttu-id="146d1-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="146d1-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="146d1-1297">信用卡号</span><span class="sxs-lookup"><span data-stu-id="146d1-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1298">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1298">Format</span></span>

<span data-ttu-id="146d1-1299">14到16个数字，可以是格式化或无格式（dddddddddddddddd），并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="146d1-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1300">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1300">Pattern</span></span>

<span data-ttu-id="146d1-1301">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="146d1-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1302">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1302">Checksum</span></span>

<span data-ttu-id="146d1-1303">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1304">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1304">Definition</span></span>

<span data-ttu-id="146d1-1305">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1306">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1307">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-1307">One of the following is true:</span></span>
    - <span data-ttu-id="146d1-1308">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="146d1-1309">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="146d1-1310">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="146d1-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1311">The checksum passes.</span></span>

<span data-ttu-id="146d1-1312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1313">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1315">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="146d1-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="146d1-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="146d1-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="146d1-1317">card verification</span></span>
- <span data-ttu-id="146d1-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-1318">card identification number</span></span>
- <span data-ttu-id="146d1-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="146d1-1319">cvn</span></span>
- <span data-ttu-id="146d1-1320">cid</span><span class="sxs-lookup"><span data-stu-id="146d1-1320">cid</span></span>
- <span data-ttu-id="146d1-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="146d1-1321">cvc2</span></span>
- <span data-ttu-id="146d1-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="146d1-1322">cvv2</span></span>
- <span data-ttu-id="146d1-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="146d1-1323">pin block</span></span>
- <span data-ttu-id="146d1-1324">security code</span><span class="sxs-lookup"><span data-stu-id="146d1-1324">security code</span></span>
- <span data-ttu-id="146d1-1325">security number</span><span class="sxs-lookup"><span data-stu-id="146d1-1325">security number</span></span>
- <span data-ttu-id="146d1-1326">security no</span><span class="sxs-lookup"><span data-stu-id="146d1-1326">security no</span></span>
- <span data-ttu-id="146d1-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="146d1-1327">issue number</span></span>
- <span data-ttu-id="146d1-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="146d1-1328">issue no</span></span>
- <span data-ttu-id="146d1-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="146d1-1329">cryptogramme</span></span>
- <span data-ttu-id="146d1-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="146d1-1330">numéro de sécurité</span></span>
- <span data-ttu-id="146d1-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="146d1-1331">numero de securite</span></span>
- <span data-ttu-id="146d1-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="146d1-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="146d1-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="146d1-1334">prüfziffer</span></span>
- <span data-ttu-id="146d1-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="146d1-1335">prufziffer</span></span>
- <span data-ttu-id="146d1-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="146d1-1336">sicherheits Kode</span></span>
- <span data-ttu-id="146d1-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="146d1-1337">sicherheitscode</span></span>
- <span data-ttu-id="146d1-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="146d1-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1339">verfalldatum</span></span>
- <span data-ttu-id="146d1-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="146d1-1340">codice di verifica</span></span>
- <span data-ttu-id="146d1-1341">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1341">cod.</span></span> <span data-ttu-id="146d1-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1342">sicurezza</span></span>
- <span data-ttu-id="146d1-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1343">cod sicurezza</span></span>
- <span data-ttu-id="146d1-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="146d1-1344">n autorizzazione</span></span>
- <span data-ttu-id="146d1-1345">código</span><span class="sxs-lookup"><span data-stu-id="146d1-1345">código</span></span>
- <span data-ttu-id="146d1-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="146d1-1346">codigo</span></span>
- <span data-ttu-id="146d1-1347">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1347">cod.</span></span> <span data-ttu-id="146d1-1348">seg</span><span class="sxs-lookup"><span data-stu-id="146d1-1348">seg</span></span>
- <span data-ttu-id="146d1-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="146d1-1349">cod seg</span></span>
- <span data-ttu-id="146d1-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1350">código de segurança</span></span>
- <span data-ttu-id="146d1-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1351">codigo de seguranca</span></span>
- <span data-ttu-id="146d1-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1352">codigo de segurança</span></span>
- <span data-ttu-id="146d1-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1353">código de seguranca</span></span>
- <span data-ttu-id="146d1-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="146d1-1354">cód.</span></span> <span data-ttu-id="146d1-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1355">segurança</span></span>
- <span data-ttu-id="146d1-1356">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1356">cod.</span></span> <span data-ttu-id="146d1-1357">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="146d1-1357">seguranca cod.</span></span> <span data-ttu-id="146d1-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1358">segurança</span></span>
- <span data-ttu-id="146d1-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="146d1-1359">cód.</span></span> <span data-ttu-id="146d1-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1360">seguranca</span></span>
- <span data-ttu-id="146d1-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1361">cód segurança</span></span>
- <span data-ttu-id="146d1-1362">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="146d1-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1363">cód seguranca</span></span>
- <span data-ttu-id="146d1-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="146d1-1364">número de verificação</span></span>
- <span data-ttu-id="146d1-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="146d1-1365">numero de verificacao</span></span>
- <span data-ttu-id="146d1-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="146d1-1366">ablauf</span></span>
- <span data-ttu-id="146d1-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="146d1-1367">gültig bis</span></span>
- <span data-ttu-id="146d1-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="146d1-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="146d1-1369">gultig bis</span></span>
- <span data-ttu-id="146d1-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="146d1-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="146d1-1371">scadenza</span></span>
- <span data-ttu-id="146d1-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="146d1-1372">data scad</span></span>
- <span data-ttu-id="146d1-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="146d1-1373">fecha de expiracion</span></span>
- <span data-ttu-id="146d1-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="146d1-1374">fecha de venc</span></span>
- <span data-ttu-id="146d1-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="146d1-1375">vencimiento</span></span>
- <span data-ttu-id="146d1-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="146d1-1376">válido hasta</span></span>
- <span data-ttu-id="146d1-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="146d1-1377">valido hasta</span></span>
- <span data-ttu-id="146d1-1378">vto</span><span class="sxs-lookup"><span data-stu-id="146d1-1378">vto</span></span>
- <span data-ttu-id="146d1-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="146d1-1379">data de expiração</span></span>
- <span data-ttu-id="146d1-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="146d1-1380">data de expiracao</span></span>
- <span data-ttu-id="146d1-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="146d1-1381">data em que expira</span></span>
- <span data-ttu-id="146d1-1382">validade</span><span class="sxs-lookup"><span data-stu-id="146d1-1382">validade</span></span>
- <span data-ttu-id="146d1-1383">valor</span><span class="sxs-lookup"><span data-stu-id="146d1-1383">valor</span></span>
- <span data-ttu-id="146d1-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="146d1-1384">vencimento</span></span>
- <span data-ttu-id="146d1-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="146d1-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="146d1-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="146d1-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="146d1-1387">amex</span><span class="sxs-lookup"><span data-stu-id="146d1-1387">amex</span></span>
- <span data-ttu-id="146d1-1388">american express</span><span class="sxs-lookup"><span data-stu-id="146d1-1388">american express</span></span>
- <span data-ttu-id="146d1-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="146d1-1389">americanexpress</span></span>
- <span data-ttu-id="146d1-1390">反之</span><span class="sxs-lookup"><span data-stu-id="146d1-1390">Visa</span></span>
- <span data-ttu-id="146d1-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="146d1-1391">mastercard</span></span>
- <span data-ttu-id="146d1-1392">Master Card</span><span class="sxs-lookup"><span data-stu-id="146d1-1392">master card</span></span>
- <span data-ttu-id="146d1-1393">emc</span><span class="sxs-lookup"><span data-stu-id="146d1-1393">mc</span></span> 
- <span data-ttu-id="146d1-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="146d1-1394">mastercards</span></span>
- <span data-ttu-id="146d1-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1395">master cards</span></span>
- <span data-ttu-id="146d1-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="146d1-1396">diner's Club</span></span>
- <span data-ttu-id="146d1-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="146d1-1397">diners club</span></span>
- <span data-ttu-id="146d1-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="146d1-1398">dinersclub</span></span>
- <span data-ttu-id="146d1-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="146d1-1399">discover card</span></span>
- <span data-ttu-id="146d1-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="146d1-1400">discovercard</span></span>
- <span data-ttu-id="146d1-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1401">discover cards</span></span>
- <span data-ttu-id="146d1-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="146d1-1402">JCB</span></span>
- <span data-ttu-id="146d1-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="146d1-1403">japanese card bureau</span></span>
- <span data-ttu-id="146d1-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="146d1-1404">carte blanche</span></span>
- <span data-ttu-id="146d1-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="146d1-1405">carteblanche</span></span>
- <span data-ttu-id="146d1-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="146d1-1406">credit card</span></span>
- <span data-ttu-id="146d1-1407">收件人#</span><span class="sxs-lookup"><span data-stu-id="146d1-1407">cc#</span></span>
- <span data-ttu-id="146d1-1408">cc #：</span><span class="sxs-lookup"><span data-stu-id="146d1-1408">cc#:</span></span>
- <span data-ttu-id="146d1-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="146d1-1409">expiration date</span></span>
- <span data-ttu-id="146d1-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="146d1-1410">exp date</span></span>
- <span data-ttu-id="146d1-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="146d1-1411">expiry date</span></span>
- <span data-ttu-id="146d1-1412">日期 d'expiration</span><span class="sxs-lookup"><span data-stu-id="146d1-1412">date d'expiration</span></span>
- <span data-ttu-id="146d1-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="146d1-1413">date d'exp</span></span>
- <span data-ttu-id="146d1-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="146d1-1414">date expiration</span></span>
- <span data-ttu-id="146d1-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="146d1-1415">bank card</span></span>
- <span data-ttu-id="146d1-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1416">bankcard</span></span>
- <span data-ttu-id="146d1-1417">card number</span><span class="sxs-lookup"><span data-stu-id="146d1-1417">card number</span></span>
- <span data-ttu-id="146d1-1418">card num</span><span class="sxs-lookup"><span data-stu-id="146d1-1418">card num</span></span>
- <span data-ttu-id="146d1-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-1419">cardnumber</span></span>
- <span data-ttu-id="146d1-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1420">cardnumbers</span></span>
- <span data-ttu-id="146d1-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1421">card numbers</span></span>
- <span data-ttu-id="146d1-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1422">creditcard</span></span>
- <span data-ttu-id="146d1-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1423">credit cards</span></span>
- <span data-ttu-id="146d1-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1424">creditcards</span></span>
- <span data-ttu-id="146d1-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="146d1-1425">ccn</span></span>
- <span data-ttu-id="146d1-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="146d1-1426">card holder</span></span>
- <span data-ttu-id="146d1-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="146d1-1427">cardholder</span></span>
- <span data-ttu-id="146d1-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="146d1-1428">card holders</span></span>
- <span data-ttu-id="146d1-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="146d1-1429">cardholders</span></span>
- <span data-ttu-id="146d1-1430">check card</span><span class="sxs-lookup"><span data-stu-id="146d1-1430">check card</span></span>
- <span data-ttu-id="146d1-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1431">checkcard</span></span>
- <span data-ttu-id="146d1-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1432">check cards</span></span>
- <span data-ttu-id="146d1-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1433">checkcards</span></span>
- <span data-ttu-id="146d1-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="146d1-1434">debit card</span></span>
- <span data-ttu-id="146d1-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1435">debitcard</span></span>
- <span data-ttu-id="146d1-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1436">debit cards</span></span>
- <span data-ttu-id="146d1-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1437">debitcards</span></span>
- <span data-ttu-id="146d1-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="146d1-1438">atm card</span></span>
- <span data-ttu-id="146d1-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1439">atmcard</span></span>
- <span data-ttu-id="146d1-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1440">atm cards</span></span>
- <span data-ttu-id="146d1-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1441">atmcards</span></span>
- <span data-ttu-id="146d1-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="146d1-1442">enroute</span></span>
- <span data-ttu-id="146d1-1443">en route</span><span class="sxs-lookup"><span data-stu-id="146d1-1443">en route</span></span>
- <span data-ttu-id="146d1-1444">card type</span><span class="sxs-lookup"><span data-stu-id="146d1-1444">card type</span></span>
- <span data-ttu-id="146d1-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="146d1-1445">carte bancaire</span></span>
- <span data-ttu-id="146d1-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="146d1-1446">carte de crédit</span></span>
- <span data-ttu-id="146d1-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="146d1-1447">carte de credit</span></span>
- <span data-ttu-id="146d1-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1448">numéro de carte</span></span>
- <span data-ttu-id="146d1-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1449">numero de carte</span></span>
- <span data-ttu-id="146d1-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1450">nº de la carte</span></span>
- <span data-ttu-id="146d1-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1451">nº de carte</span></span>
- <span data-ttu-id="146d1-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="146d1-1452">kreditkarte</span></span>
- <span data-ttu-id="146d1-1453">karte</span><span class="sxs-lookup"><span data-stu-id="146d1-1453">karte</span></span>
- <span data-ttu-id="146d1-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="146d1-1454">karteninhaber</span></span>
- <span data-ttu-id="146d1-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="146d1-1455">karteninhabers</span></span>
- <span data-ttu-id="146d1-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="146d1-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="146d1-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="146d1-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="146d1-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="146d1-1458">kreditkartentyp</span></span>
- <span data-ttu-id="146d1-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="146d1-1459">eigentümername</span></span>
- <span data-ttu-id="146d1-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="146d1-1460">kartennr</span></span> 
- <span data-ttu-id="146d1-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1461">kartennummer</span></span>
- <span data-ttu-id="146d1-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1462">kreditkartennummer</span></span>
- <span data-ttu-id="146d1-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="146d1-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1464">carta di credito</span></span>
- <span data-ttu-id="146d1-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1465">carta credito</span></span>
- <span data-ttu-id="146d1-1466">carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1466">carta</span></span>
- <span data-ttu-id="146d1-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1467">n carta</span></span>
- <span data-ttu-id="146d1-1468">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="146d1-1468">nr.</span></span> <span data-ttu-id="146d1-1469">carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1469">carta</span></span>
- <span data-ttu-id="146d1-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1470">nr carta</span></span>
- <span data-ttu-id="146d1-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1471">numero carta</span></span>
- <span data-ttu-id="146d1-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1472">numero della carta</span></span>
- <span data-ttu-id="146d1-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1473">numero di carta</span></span>
- <span data-ttu-id="146d1-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1474">tarjeta credito</span></span>
- <span data-ttu-id="146d1-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1475">tarjeta de credito</span></span>
- <span data-ttu-id="146d1-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1476">tarjeta crédito</span></span>
- <span data-ttu-id="146d1-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="146d1-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="146d1-1478">tarjeta de atm</span></span>
- <span data-ttu-id="146d1-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="146d1-1479">tarjeta atm</span></span>
- <span data-ttu-id="146d1-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1480">tarjeta debito</span></span>
- <span data-ttu-id="146d1-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1481">tarjeta de debito</span></span>
- <span data-ttu-id="146d1-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1482">tarjeta débito</span></span>
- <span data-ttu-id="146d1-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1483">tarjeta de débito</span></span>
- <span data-ttu-id="146d1-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1484">nº de tarjeta</span></span>
- <span data-ttu-id="146d1-1485">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1485">no.</span></span> <span data-ttu-id="146d1-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1486">de tarjeta</span></span>
- <span data-ttu-id="146d1-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1487">no de tarjeta</span></span>
- <span data-ttu-id="146d1-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1488">numero de tarjeta</span></span>
- <span data-ttu-id="146d1-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1489">número de tarjeta</span></span>
- <span data-ttu-id="146d1-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="146d1-1490">tarjeta no</span></span>
- <span data-ttu-id="146d1-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="146d1-1491">tarjetahabiente</span></span>
- <span data-ttu-id="146d1-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1492">cartão de crédito</span></span>
- <span data-ttu-id="146d1-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1493">cartão de credito</span></span>
- <span data-ttu-id="146d1-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1494">cartao de crédito</span></span>
- <span data-ttu-id="146d1-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1495">cartao de credito</span></span>
- <span data-ttu-id="146d1-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1496">cartão de débito</span></span>
- <span data-ttu-id="146d1-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1497">cartao de débito</span></span>
- <span data-ttu-id="146d1-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1498">cartão de debito</span></span>
- <span data-ttu-id="146d1-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1499">cartao de debito</span></span>
- <span data-ttu-id="146d1-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="146d1-1500">débito automático</span></span>
- <span data-ttu-id="146d1-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="146d1-1501">debito automatico</span></span>
- <span data-ttu-id="146d1-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1502">número do cartão</span></span>
- <span data-ttu-id="146d1-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1503">numero do cartão</span></span> 
- <span data-ttu-id="146d1-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1504">número do cartao</span></span>
- <span data-ttu-id="146d1-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1505">numero do cartao</span></span>
- <span data-ttu-id="146d1-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1506">número de cartão</span></span>
- <span data-ttu-id="146d1-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1507">numero de cartão</span></span>
- <span data-ttu-id="146d1-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1508">número de cartao</span></span>
- <span data-ttu-id="146d1-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1509">numero de cartao</span></span>
- <span data-ttu-id="146d1-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1510">nº do cartão</span></span>
- <span data-ttu-id="146d1-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1511">nº do cartao</span></span>
- <span data-ttu-id="146d1-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="146d1-1512">nº.</span></span> <span data-ttu-id="146d1-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1513">do cartão</span></span>
- <span data-ttu-id="146d1-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1514">no do cartão</span></span>
- <span data-ttu-id="146d1-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1515">no do cartao</span></span>
- <span data-ttu-id="146d1-1516">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1516">no.</span></span> <span data-ttu-id="146d1-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1517">do cartão</span></span>
- <span data-ttu-id="146d1-1518">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1518">no.</span></span> <span data-ttu-id="146d1-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="146d1-1520">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1521">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1521">Format</span></span>

<span data-ttu-id="146d1-1522">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1523">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1523">Pattern</span></span>

<span data-ttu-id="146d1-1524">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1525">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1525">Checksum</span></span>

<span data-ttu-id="146d1-1526">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1527">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1527">Definition</span></span>

<span data-ttu-id="146d1-1528">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1529">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1530">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1531">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="146d1-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="146d1-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-1533">Croatian identity card</span></span>
- <span data-ttu-id="146d1-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="146d1-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="146d1-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="146d1-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1536">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1536">Format</span></span>

<span data-ttu-id="146d1-1537">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1538">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1538">Pattern</span></span>

<span data-ttu-id="146d1-1539">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-1539">11 digits:</span></span>
- <span data-ttu-id="146d1-1540">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1540">10 digits</span></span> 
- <span data-ttu-id="146d1-1541">最后一个数字是用于国际数据交换目的的校验位，字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1542">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1542">Checksum</span></span>

<span data-ttu-id="146d1-1543">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1544">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1544">Definition</span></span>

<span data-ttu-id="146d1-1545">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1546">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1547">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="146d1-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1548">The checksum passes.</span></span>

<span data-ttu-id="146d1-1549">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1550">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1552">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="146d1-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="146d1-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="146d1-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="146d1-1554">Personal Identification Number</span></span>
- <span data-ttu-id="146d1-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="146d1-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="146d1-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="146d1-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="146d1-1557">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="146d1-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1558">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1558">Format</span></span>

<span data-ttu-id="146d1-1559">9个带可选正斜杠（旧格式）的数字，带可选正斜杠的10个数字（新的格式）</span><span class="sxs-lookup"><span data-stu-id="146d1-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1560">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1560">Pattern</span></span>

<span data-ttu-id="146d1-1561">9个数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="146d1-1562">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1562">Nine digits</span></span>

<span data-ttu-id="146d1-1563">OR</span><span class="sxs-lookup"><span data-stu-id="146d1-1563">OR</span></span>

- <span data-ttu-id="146d1-1564">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="146d1-1565">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="146d1-1565">A forward slash</span></span>
- <span data-ttu-id="146d1-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1566">Three digits</span></span>

<span data-ttu-id="146d1-1567">10个数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-1567">10 digits (new format):</span></span>
- <span data-ttu-id="146d1-1568">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1568">10 digits</span></span>

<span data-ttu-id="146d1-1569">OR</span><span class="sxs-lookup"><span data-stu-id="146d1-1569">OR</span></span>

- <span data-ttu-id="146d1-1570">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="146d1-1571">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="146d1-1571">A forward slash</span></span> 
- <span data-ttu-id="146d1-1572">四个数字，其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1573">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1573">Checksum</span></span>

<span data-ttu-id="146d1-1574">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1575">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1575">Definition</span></span>

<span data-ttu-id="146d1-1576">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-1577">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="146d1-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="146d1-1579">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1579">Keywords</span></span>

- <span data-ttu-id="146d1-1580">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="146d1-1580">czech personal identity number</span></span>
- <span data-ttu-id="146d1-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="146d1-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="146d1-1582">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1583">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1583">Format</span></span>

<span data-ttu-id="146d1-1584">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="146d1-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1585">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1585">Pattern</span></span>

<span data-ttu-id="146d1-1586">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-1586">10 digits:</span></span>
- <span data-ttu-id="146d1-1587">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="146d1-1588">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-1588">A hyphen</span></span> 
- <span data-ttu-id="146d1-1589">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1590">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1590">Checksum</span></span>

<span data-ttu-id="146d1-1591">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1592">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1592">Definition</span></span>

<span data-ttu-id="146d1-1593">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-1594">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="146d1-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1596">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="146d1-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="146d1-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="146d1-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="146d1-1598">Personal Identification Number</span></span>
- <span data-ttu-id="146d1-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="146d1-1599">CPR</span></span>
- <span data-ttu-id="146d1-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="146d1-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="146d1-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="146d1-1602">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1603">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1603">Format</span></span>

<span data-ttu-id="146d1-1604">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1605">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1605">Pattern</span></span>

<span data-ttu-id="146d1-1606">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="146d1-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="146d1-1607">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="146d1-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="146d1-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="146d1-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="146d1-1609">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1610">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1610">Checksum</span></span>

<span data-ttu-id="146d1-1611">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1612">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1612">Definition</span></span>

<span data-ttu-id="146d1-1613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1614">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1616">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1616">Keywords</span></span>

<span data-ttu-id="146d1-1617">无</span><span class="sxs-lookup"><span data-stu-id="146d1-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="146d1-1618">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="146d1-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1619">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1619">Format</span></span>

<span data-ttu-id="146d1-1620">16 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1621">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1621">Pattern</span></span>

<span data-ttu-id="146d1-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1623">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1623">Checksum</span></span>

<span data-ttu-id="146d1-1624">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1625">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1625">Definition</span></span>

<span data-ttu-id="146d1-1626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1627">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1628">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="146d1-1629">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="146d1-1630">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="146d1-1631">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="146d1-1632">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="146d1-1633">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="146d1-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1635">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="146d1-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="146d1-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="146d1-1637">account number</span><span class="sxs-lookup"><span data-stu-id="146d1-1637">account number</span></span> 
- <span data-ttu-id="146d1-1638">card number</span><span class="sxs-lookup"><span data-stu-id="146d1-1638">card number</span></span> 
- <span data-ttu-id="146d1-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="146d1-1639">card no.</span></span> 
- <span data-ttu-id="146d1-1640">security number</span><span class="sxs-lookup"><span data-stu-id="146d1-1640">security number</span></span> 
- <span data-ttu-id="146d1-1641">收件人#</span><span class="sxs-lookup"><span data-stu-id="146d1-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="146d1-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="146d1-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="146d1-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="146d1-1643">acct nbr</span></span> 
- <span data-ttu-id="146d1-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="146d1-1644">acct num</span></span> 
- <span data-ttu-id="146d1-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="146d1-1645">acct no</span></span> 
- <span data-ttu-id="146d1-1646">american express</span><span class="sxs-lookup"><span data-stu-id="146d1-1646">american express</span></span> 
- <span data-ttu-id="146d1-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="146d1-1647">americanexpress</span></span> 
- <span data-ttu-id="146d1-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="146d1-1648">americano espresso</span></span> 
- <span data-ttu-id="146d1-1649">amex</span><span class="sxs-lookup"><span data-stu-id="146d1-1649">amex</span></span> 
- <span data-ttu-id="146d1-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="146d1-1650">atm card</span></span> 
- <span data-ttu-id="146d1-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1651">atm cards</span></span> 
- <span data-ttu-id="146d1-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1652">atm kaart</span></span> 
- <span data-ttu-id="146d1-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1653">atmcard</span></span> 
- <span data-ttu-id="146d1-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1654">atmcards</span></span> 
- <span data-ttu-id="146d1-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1655">atmkaart</span></span> 
- <span data-ttu-id="146d1-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="146d1-1656">atmkaarten</span></span> 
- <span data-ttu-id="146d1-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="146d1-1657">bancontact</span></span> 
- <span data-ttu-id="146d1-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="146d1-1658">bank card</span></span> 
- <span data-ttu-id="146d1-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1659">bankkaart</span></span> 
- <span data-ttu-id="146d1-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="146d1-1660">card holder</span></span> 
- <span data-ttu-id="146d1-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="146d1-1661">card holders</span></span> 
- <span data-ttu-id="146d1-1662">card num</span><span class="sxs-lookup"><span data-stu-id="146d1-1662">card num</span></span> 
- <span data-ttu-id="146d1-1663">card number</span><span class="sxs-lookup"><span data-stu-id="146d1-1663">card number</span></span> 
- <span data-ttu-id="146d1-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1664">card numbers</span></span> 
- <span data-ttu-id="146d1-1665">card type</span><span class="sxs-lookup"><span data-stu-id="146d1-1665">card type</span></span> 
- <span data-ttu-id="146d1-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="146d1-1666">cardano numerico</span></span> 
- <span data-ttu-id="146d1-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="146d1-1667">cardholder</span></span> 
- <span data-ttu-id="146d1-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="146d1-1668">cardholders</span></span> 
- <span data-ttu-id="146d1-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-1669">cardnumber</span></span> 
- <span data-ttu-id="146d1-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="146d1-1670">cardnumbers</span></span> 
- <span data-ttu-id="146d1-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="146d1-1671">carta bianca</span></span> 
- <span data-ttu-id="146d1-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1672">carta credito</span></span> 
- <span data-ttu-id="146d1-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1673">carta di credito</span></span> 
- <span data-ttu-id="146d1-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1674">cartao de credito</span></span> 
- <span data-ttu-id="146d1-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1675">cartao de crédito</span></span> 
- <span data-ttu-id="146d1-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1676">cartao de debito</span></span> 
- <span data-ttu-id="146d1-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1677">cartao de débito</span></span> 
- <span data-ttu-id="146d1-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="146d1-1678">carte bancaire</span></span> 
- <span data-ttu-id="146d1-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="146d1-1679">carte blanche</span></span> 
- <span data-ttu-id="146d1-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="146d1-1680">carte bleue</span></span> 
- <span data-ttu-id="146d1-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="146d1-1681">carte de credit</span></span> 
- <span data-ttu-id="146d1-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="146d1-1682">carte de crédit</span></span> 
- <span data-ttu-id="146d1-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1683">carte di credito</span></span> 
- <span data-ttu-id="146d1-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="146d1-1684">carteblanche</span></span> 
- <span data-ttu-id="146d1-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1685">cartão de credito</span></span> 
- <span data-ttu-id="146d1-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="146d1-1686">cartão de crédito</span></span> 
- <span data-ttu-id="146d1-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1687">cartão de debito</span></span> 
- <span data-ttu-id="146d1-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="146d1-1688">cartão de débito</span></span> 
- <span data-ttu-id="146d1-1689">cb</span><span class="sxs-lookup"><span data-stu-id="146d1-1689">cb</span></span> 
- <span data-ttu-id="146d1-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="146d1-1690">ccn</span></span> 
- <span data-ttu-id="146d1-1691">check card</span><span class="sxs-lookup"><span data-stu-id="146d1-1691">check card</span></span> 
- <span data-ttu-id="146d1-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1692">check cards</span></span> 
- <span data-ttu-id="146d1-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1693">checkcard</span></span>
- <span data-ttu-id="146d1-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1694">checkcards</span></span> 
- <span data-ttu-id="146d1-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1695">chequekaart</span></span> 
- <span data-ttu-id="146d1-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="146d1-1696">cirrus</span></span> 
- <span data-ttu-id="146d1-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="146d1-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="146d1-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1698">controlekaart</span></span> 
- <span data-ttu-id="146d1-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="146d1-1699">controlekaarten</span></span> 
- <span data-ttu-id="146d1-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="146d1-1700">credit card</span></span> 
- <span data-ttu-id="146d1-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1701">credit cards</span></span> 
- <span data-ttu-id="146d1-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1702">creditcard</span></span> 
- <span data-ttu-id="146d1-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1703">creditcards</span></span> 
- <span data-ttu-id="146d1-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1704">debetkaart</span></span> 
- <span data-ttu-id="146d1-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="146d1-1705">debetkaarten</span></span> 
- <span data-ttu-id="146d1-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="146d1-1706">debit card</span></span> 
- <span data-ttu-id="146d1-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1707">debit cards</span></span> 
- <span data-ttu-id="146d1-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="146d1-1708">debitcard</span></span> 
- <span data-ttu-id="146d1-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="146d1-1709">debitcards</span></span> 
- <span data-ttu-id="146d1-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="146d1-1710">debito automatico</span></span> 
- <span data-ttu-id="146d1-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="146d1-1711">diners club</span></span> 
- <span data-ttu-id="146d1-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="146d1-1712">dinersclub</span></span> 
- <span data-ttu-id="146d1-1713">确定</span><span class="sxs-lookup"><span data-stu-id="146d1-1713">discover</span></span> 
- <span data-ttu-id="146d1-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="146d1-1714">discover card</span></span> 
- <span data-ttu-id="146d1-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1715">discover cards</span></span> 
- <span data-ttu-id="146d1-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="146d1-1716">discovercard</span></span> 
- <span data-ttu-id="146d1-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="146d1-1717">discovercards</span></span> 
- <span data-ttu-id="146d1-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="146d1-1718">débito automático</span></span>
- <span data-ttu-id="146d1-1719">edc</span><span class="sxs-lookup"><span data-stu-id="146d1-1719">edc</span></span> 
- <span data-ttu-id="146d1-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="146d1-1720">eigentümername</span></span> 
- <span data-ttu-id="146d1-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="146d1-1721">european debit card</span></span> 
- <span data-ttu-id="146d1-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1722">hoofdkaart</span></span> 
- <span data-ttu-id="146d1-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="146d1-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="146d1-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="146d1-1724">in viaggio</span></span> 
- <span data-ttu-id="146d1-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="146d1-1725">japanese card bureau</span></span> 
- <span data-ttu-id="146d1-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="146d1-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="146d1-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="146d1-1727">jcb</span></span> 
- <span data-ttu-id="146d1-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="146d1-1728">kaart</span></span> 
- <span data-ttu-id="146d1-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="146d1-1729">kaart num</span></span> 
- <span data-ttu-id="146d1-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="146d1-1730">kaartaantal</span></span> 
- <span data-ttu-id="146d1-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="146d1-1731">kaartaantallen</span></span> 
- <span data-ttu-id="146d1-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="146d1-1732">kaarthouder</span></span> 
- <span data-ttu-id="146d1-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="146d1-1733">kaarthouders</span></span> 
- <span data-ttu-id="146d1-1734">karte</span><span class="sxs-lookup"><span data-stu-id="146d1-1734">karte</span></span>  
- <span data-ttu-id="146d1-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="146d1-1735">karteninhaber</span></span> 
- <span data-ttu-id="146d1-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="146d1-1736">karteninhabers</span></span>
- <span data-ttu-id="146d1-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="146d1-1737">kartennr</span></span> 
- <span data-ttu-id="146d1-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1738">kartennummer</span></span> 
- <span data-ttu-id="146d1-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="146d1-1739">kreditkarte</span></span> 
- <span data-ttu-id="146d1-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="146d1-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="146d1-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="146d1-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="146d1-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="146d1-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="146d1-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="146d1-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="146d1-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="146d1-1745">maestro</span></span> 
- <span data-ttu-id="146d1-1746">Master Card</span><span class="sxs-lookup"><span data-stu-id="146d1-1746">master card</span></span> 
- <span data-ttu-id="146d1-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="146d1-1747">master cards</span></span> 
- <span data-ttu-id="146d1-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="146d1-1748">mastercard</span></span> 
- <span data-ttu-id="146d1-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="146d1-1749">mastercards</span></span> 
- <span data-ttu-id="146d1-1750">emc</span><span class="sxs-lookup"><span data-stu-id="146d1-1750">mc</span></span> 
- <span data-ttu-id="146d1-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="146d1-1751">mister cash</span></span> 
- <span data-ttu-id="146d1-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1752">n carta</span></span> 
- <span data-ttu-id="146d1-1753">carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1753">carta</span></span> 
- <span data-ttu-id="146d1-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1754">no de tarjeta</span></span> 
- <span data-ttu-id="146d1-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1755">no do cartao</span></span> 
- <span data-ttu-id="146d1-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1756">no do cartão</span></span> 
- <span data-ttu-id="146d1-1757">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1757">no.</span></span> <span data-ttu-id="146d1-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1758">de tarjeta</span></span> 
- <span data-ttu-id="146d1-1759">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1759">no.</span></span> <span data-ttu-id="146d1-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1760">do cartao</span></span> 
- <span data-ttu-id="146d1-1761">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1761">no.</span></span> <span data-ttu-id="146d1-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1762">do cartão</span></span> 
- <span data-ttu-id="146d1-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1763">nr carta</span></span> 
- <span data-ttu-id="146d1-1764">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="146d1-1764">nr.</span></span> <span data-ttu-id="146d1-1765">carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1765">carta</span></span> 
- <span data-ttu-id="146d1-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1766">numeri di scheda</span></span> 
- <span data-ttu-id="146d1-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1767">numero carta</span></span> 
- <span data-ttu-id="146d1-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1768">numero de cartao</span></span> 
- <span data-ttu-id="146d1-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1769">numero de carte</span></span> 
- <span data-ttu-id="146d1-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1770">numero de cartão</span></span> 
- <span data-ttu-id="146d1-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1771">numero de tarjeta</span></span>
- <span data-ttu-id="146d1-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1772">numero della carta</span></span> 
- <span data-ttu-id="146d1-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1773">numero di carta</span></span> 
- <span data-ttu-id="146d1-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1774">numero di scheda</span></span> 
- <span data-ttu-id="146d1-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1775">numero do cartao</span></span> 
- <span data-ttu-id="146d1-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1776">numero do cartão</span></span> 
- <span data-ttu-id="146d1-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1777">numéro de carte</span></span> 
- <span data-ttu-id="146d1-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="146d1-1778">nº carta</span></span> 
- <span data-ttu-id="146d1-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1779">nº de carte</span></span> 
- <span data-ttu-id="146d1-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="146d1-1780">nº de la carte</span></span> 
- <span data-ttu-id="146d1-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="146d1-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1782">nº do cartao</span></span> 
- <span data-ttu-id="146d1-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1783">nº do cartão</span></span> 
- <span data-ttu-id="146d1-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="146d1-1784">nº.</span></span> <span data-ttu-id="146d1-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1785">do cartão</span></span> 
- <span data-ttu-id="146d1-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1786">número de cartao</span></span> 
- <span data-ttu-id="146d1-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="146d1-1787">número de cartão</span></span> 
- <span data-ttu-id="146d1-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="146d1-1788">número de tarjeta</span></span> 
- <span data-ttu-id="146d1-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="146d1-1789">número do cartao</span></span> 
- <span data-ttu-id="146d1-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="146d1-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="146d1-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="146d1-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="146d1-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="146d1-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="146d1-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="146d1-1793">scheda della banca</span></span> 
- <span data-ttu-id="146d1-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="146d1-1794">scheda di controllo</span></span> 
- <span data-ttu-id="146d1-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1795">scheda di debito</span></span> 
- <span data-ttu-id="146d1-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="146d1-1796">scheda matrice</span></span> 
- <span data-ttu-id="146d1-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="146d1-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="146d1-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="146d1-1798">schede di controllo</span></span> 
- <span data-ttu-id="146d1-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1799">schede di debito</span></span> 
- <span data-ttu-id="146d1-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="146d1-1800">schede matrici</span></span> 
- <span data-ttu-id="146d1-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="146d1-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="146d1-1802">scoprono le schede</span></span> 
- <span data-ttu-id="146d1-1803">solo</span><span class="sxs-lookup"><span data-stu-id="146d1-1803">solo</span></span> 
- <span data-ttu-id="146d1-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1804">supporti di scheda</span></span> 
- <span data-ttu-id="146d1-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1805">supporto di scheda</span></span> 
- <span data-ttu-id="146d1-1806">器</span><span class="sxs-lookup"><span data-stu-id="146d1-1806">switch</span></span> 
- <span data-ttu-id="146d1-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="146d1-1807">tarjeta atm</span></span> 
- <span data-ttu-id="146d1-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1808">tarjeta credito</span></span> 
- <span data-ttu-id="146d1-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="146d1-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="146d1-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="146d1-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="146d1-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="146d1-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="146d1-1812">tarjeta debito</span></span> 
- <span data-ttu-id="146d1-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="146d1-1813">tarjeta no</span></span>
- <span data-ttu-id="146d1-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="146d1-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="146d1-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1815">tipo della scheda</span></span> 
- <span data-ttu-id="146d1-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="146d1-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="146d1-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1817">scheda</span></span> 
- <span data-ttu-id="146d1-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="146d1-1818">v pay</span></span> 
- <span data-ttu-id="146d1-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="146d1-1819">v-pay</span></span> 
- <span data-ttu-id="146d1-1820">反之</span><span class="sxs-lookup"><span data-stu-id="146d1-1820">visa</span></span> 
- <span data-ttu-id="146d1-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="146d1-1821">visa plus</span></span> 
- <span data-ttu-id="146d1-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="146d1-1822">visa electron</span></span> 
- <span data-ttu-id="146d1-1823">visto</span><span class="sxs-lookup"><span data-stu-id="146d1-1823">visto</span></span> 
- <span data-ttu-id="146d1-1824">visum</span><span class="sxs-lookup"><span data-stu-id="146d1-1824">visum</span></span> 
- <span data-ttu-id="146d1-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="146d1-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="146d1-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="146d1-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="146d1-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-1827">card identification number</span></span>
- <span data-ttu-id="146d1-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="146d1-1828">card verification</span></span> 
- <span data-ttu-id="146d1-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="146d1-1829">cardi la verifica</span></span> 
- <span data-ttu-id="146d1-1830">cid</span><span class="sxs-lookup"><span data-stu-id="146d1-1830">cid</span></span> 
- <span data-ttu-id="146d1-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="146d1-1831">cod seg</span></span> 
- <span data-ttu-id="146d1-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1832">cod seguranca</span></span> 
- <span data-ttu-id="146d1-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1833">cod segurança</span></span> 
- <span data-ttu-id="146d1-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1834">cod sicurezza</span></span> 
- <span data-ttu-id="146d1-1835">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1835">cod.</span></span> <span data-ttu-id="146d1-1836">seg</span><span class="sxs-lookup"><span data-stu-id="146d1-1836">seg</span></span> 
- <span data-ttu-id="146d1-1837">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1837">cod.</span></span> <span data-ttu-id="146d1-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1838">seguranca</span></span> 
- <span data-ttu-id="146d1-1839">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1839">cod.</span></span> <span data-ttu-id="146d1-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1840">segurança</span></span> 
- <span data-ttu-id="146d1-1841">货.</span><span class="sxs-lookup"><span data-stu-id="146d1-1841">cod.</span></span> <span data-ttu-id="146d1-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1842">sicurezza</span></span> 
- <span data-ttu-id="146d1-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="146d1-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="146d1-1844">codice di verifica</span></span> 
- <span data-ttu-id="146d1-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="146d1-1845">codigo</span></span> 
- <span data-ttu-id="146d1-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="146d1-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1847">codigo de segurança</span></span> 
- <span data-ttu-id="146d1-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="146d1-1848">crittogramma</span></span> 
- <span data-ttu-id="146d1-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="146d1-1849">cryptogram</span></span> 
- <span data-ttu-id="146d1-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="146d1-1850">cryptogramme</span></span> 
- <span data-ttu-id="146d1-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="146d1-1851">cv2</span></span> 
- <span data-ttu-id="146d1-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="146d1-1852">cvc</span></span> 
- <span data-ttu-id="146d1-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="146d1-1853">cvc2</span></span> 
- <span data-ttu-id="146d1-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="146d1-1854">cvn</span></span> 
- <span data-ttu-id="146d1-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="146d1-1855">cvv</span></span> 
- <span data-ttu-id="146d1-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="146d1-1856">cvv2</span></span> 
- <span data-ttu-id="146d1-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1857">cód seguranca</span></span> 
- <span data-ttu-id="146d1-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1858">cód segurança</span></span> 
- <span data-ttu-id="146d1-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="146d1-1859">cód.</span></span> <span data-ttu-id="146d1-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1860">seguranca</span></span> 
- <span data-ttu-id="146d1-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="146d1-1861">cód.</span></span> <span data-ttu-id="146d1-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1862">segurança</span></span> 
- <span data-ttu-id="146d1-1863">código</span><span class="sxs-lookup"><span data-stu-id="146d1-1863">código</span></span> 
- <span data-ttu-id="146d1-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="146d1-1864">código de seguranca</span></span> 
- <span data-ttu-id="146d1-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="146d1-1865">código de segurança</span></span> 
- <span data-ttu-id="146d1-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="146d1-1866">de kaart controle</span></span> 
- <span data-ttu-id="146d1-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="146d1-1867">geeft nr uit</span></span> 
- <span data-ttu-id="146d1-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="146d1-1868">issue no</span></span> 
- <span data-ttu-id="146d1-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="146d1-1869">issue number</span></span> 
- <span data-ttu-id="146d1-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="146d1-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="146d1-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="146d1-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="146d1-1873">kwestieaantal</span></span> 
- <span data-ttu-id="146d1-1874">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1874">no.</span></span> <span data-ttu-id="146d1-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="146d1-1875">dell'edizione</span></span> 
- <span data-ttu-id="146d1-1876">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-1876">no.</span></span> <span data-ttu-id="146d1-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1877">di sicurezza</span></span> 
- <span data-ttu-id="146d1-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="146d1-1878">numero de securite</span></span> 
- <span data-ttu-id="146d1-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="146d1-1879">numero de verificacao</span></span> 
- <span data-ttu-id="146d1-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="146d1-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="146d1-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="146d1-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="146d1-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="146d1-1882">scheda</span></span> 
- <span data-ttu-id="146d1-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="146d1-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="146d1-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="146d1-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="146d1-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="146d1-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="146d1-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="146d1-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="146d1-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="146d1-1887">número de verificação</span></span> 
- <span data-ttu-id="146d1-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="146d1-1888">perno il blocco</span></span> 
- <span data-ttu-id="146d1-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="146d1-1889">pin block</span></span> 
- <span data-ttu-id="146d1-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="146d1-1890">prufziffer</span></span> 
- <span data-ttu-id="146d1-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="146d1-1891">prüfziffer</span></span> 
- <span data-ttu-id="146d1-1892">security code</span><span class="sxs-lookup"><span data-stu-id="146d1-1892">security code</span></span> 
- <span data-ttu-id="146d1-1893">security no</span><span class="sxs-lookup"><span data-stu-id="146d1-1893">security no</span></span> 
- <span data-ttu-id="146d1-1894">security number</span><span class="sxs-lookup"><span data-stu-id="146d1-1894">security number</span></span> 
- <span data-ttu-id="146d1-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="146d1-1895">sicherheits kode</span></span> 
- <span data-ttu-id="146d1-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="146d1-1896">sicherheitscode</span></span> 
- <span data-ttu-id="146d1-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="146d1-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="146d1-1898">speldblok</span></span> 
- <span data-ttu-id="146d1-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="146d1-1899">veiligheid nr</span></span> 
- <span data-ttu-id="146d1-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="146d1-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="146d1-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="146d1-1901">veiligheidscode</span></span> 
- <span data-ttu-id="146d1-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="146d1-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="146d1-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="146d1-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="146d1-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="146d1-1905">ablauf</span></span> 
- <span data-ttu-id="146d1-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="146d1-1906">data de expiracao</span></span> 
- <span data-ttu-id="146d1-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="146d1-1907">data de expiração</span></span> 
- <span data-ttu-id="146d1-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="146d1-1908">data del exp</span></span> 
- <span data-ttu-id="146d1-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="146d1-1909">data di exp</span></span> 
- <span data-ttu-id="146d1-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="146d1-1910">data di scadenza</span></span> 
- <span data-ttu-id="146d1-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="146d1-1911">data em que expira</span></span> 
- <span data-ttu-id="146d1-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="146d1-1912">data scad</span></span> 
- <span data-ttu-id="146d1-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="146d1-1913">data scadenza</span></span> 
- <span data-ttu-id="146d1-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="146d1-1914">date de validité</span></span> 
- <span data-ttu-id="146d1-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="146d1-1915">datum afloop</span></span> 
- <span data-ttu-id="146d1-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="146d1-1916">datum van exp</span></span> 
- <span data-ttu-id="146d1-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="146d1-1917">de afloop</span></span> 
- <span data-ttu-id="146d1-1918">espira</span><span class="sxs-lookup"><span data-stu-id="146d1-1918">espira</span></span> 
- <span data-ttu-id="146d1-1919">espira</span><span class="sxs-lookup"><span data-stu-id="146d1-1919">espira</span></span> 
- <span data-ttu-id="146d1-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="146d1-1920">exp date</span></span> 
- <span data-ttu-id="146d1-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="146d1-1921">exp datum</span></span> 
- <span data-ttu-id="146d1-1922">时间</span><span class="sxs-lookup"><span data-stu-id="146d1-1922">expiration</span></span> 
- <span data-ttu-id="146d1-1923">何时</span><span class="sxs-lookup"><span data-stu-id="146d1-1923">expire</span></span> 
- <span data-ttu-id="146d1-1924">不久</span><span class="sxs-lookup"><span data-stu-id="146d1-1924">expires</span></span> 
- <span data-ttu-id="146d1-1925">过期</span><span class="sxs-lookup"><span data-stu-id="146d1-1925">expiry</span></span> 
- <span data-ttu-id="146d1-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="146d1-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="146d1-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="146d1-1927">fecha de venc</span></span> 
- <span data-ttu-id="146d1-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="146d1-1928">gultig bis</span></span> 
- <span data-ttu-id="146d1-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="146d1-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="146d1-1930">gültig bis</span></span> 
- <span data-ttu-id="146d1-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="146d1-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="146d1-1932">la scadenza</span></span> 
- <span data-ttu-id="146d1-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="146d1-1933">scadenza</span></span> 
- <span data-ttu-id="146d1-1934">valable</span><span class="sxs-lookup"><span data-stu-id="146d1-1934">valable</span></span> 
- <span data-ttu-id="146d1-1935">validade</span><span class="sxs-lookup"><span data-stu-id="146d1-1935">validade</span></span> 
- <span data-ttu-id="146d1-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="146d1-1936">valido hasta</span></span> 
- <span data-ttu-id="146d1-1937">valor</span><span class="sxs-lookup"><span data-stu-id="146d1-1937">valor</span></span> 
- <span data-ttu-id="146d1-1938">venc</span><span class="sxs-lookup"><span data-stu-id="146d1-1938">venc</span></span> 
- <span data-ttu-id="146d1-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="146d1-1939">vencimento</span></span> 
- <span data-ttu-id="146d1-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="146d1-1940">vencimiento</span></span> 
- <span data-ttu-id="146d1-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="146d1-1941">verloopt</span></span> 
- <span data-ttu-id="146d1-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="146d1-1942">vervaldag</span></span> 
- <span data-ttu-id="146d1-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="146d1-1943">vervaldatum</span></span> 
- <span data-ttu-id="146d1-1944">vto</span><span class="sxs-lookup"><span data-stu-id="146d1-1944">vto</span></span> 
- <span data-ttu-id="146d1-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="146d1-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="146d1-1946">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1946">EU Driver's License Number</span></span>

<span data-ttu-id="146d1-1947">若要了解详细信息，请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="146d1-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="146d1-1948">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-1948">EU National Identification Number</span></span>

<span data-ttu-id="146d1-1949">若要了解详细信息，请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="146d1-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="146d1-1950">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1950">EU Passport Number</span></span>

<span data-ttu-id="146d1-1951">若要了解详细信息，请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="146d1-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="146d1-1952">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="146d1-1953">若要了解详细信息，请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="146d1-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="146d1-1954">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="146d1-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="146d1-1955">若要了解详细信息，请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="146d1-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="146d1-1956">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1957">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1957">Format</span></span>

<span data-ttu-id="146d1-1958">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1959">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1959">Pattern</span></span>

<span data-ttu-id="146d1-1960">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="146d1-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="146d1-1961">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="146d1-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="146d1-1962">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="146d1-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="146d1-1963">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="146d1-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="146d1-1964">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1965">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1965">Checksum</span></span>

<span data-ttu-id="146d1-1966">是</span><span class="sxs-lookup"><span data-stu-id="146d1-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1967">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1967">Definition</span></span>

<span data-ttu-id="146d1-1968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1969">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1970">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="146d1-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-1972">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1972">Keywords</span></span>

- <span data-ttu-id="146d1-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="146d1-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="146d1-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="146d1-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="146d1-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="146d1-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="146d1-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="146d1-1976">Personbeteckning</span></span>
- <span data-ttu-id="146d1-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="146d1-1978">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="146d1-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1979">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1979">Format</span></span>
<span data-ttu-id="146d1-1980">九个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="146d1-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1981">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1981">Pattern</span></span>
<span data-ttu-id="146d1-1982">九个字母和数字的组合：两个字母（不区分大小写）七位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1983">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1983">Checksum</span></span>
<span data-ttu-id="146d1-1984">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-1985">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-1985">Definition</span></span>
<span data-ttu-id="146d1-1986">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-1987">正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-1988">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="146d1-1989">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-1989">Keywords</span></span>
- <span data-ttu-id="146d1-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="146d1-1991">登记卡</span><span class="sxs-lookup"><span data-stu-id="146d1-1991">Passport</span></span>
- <span data-ttu-id="146d1-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="146d1-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="146d1-1993">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-1994">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-1994">Format</span></span>

<span data-ttu-id="146d1-1995">12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-1996">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-1996">Pattern</span></span>

<span data-ttu-id="146d1-1997">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="146d1-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-1998">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-1998">Checksum</span></span>

<span data-ttu-id="146d1-1999">否</span><span class="sxs-lookup"><span data-stu-id="146d1-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2000">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2000">Definition</span></span>

<span data-ttu-id="146d1-2001">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2002">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2003">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="146d1-2004">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="146d1-2005">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-2005">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2006">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="146d1-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="146d1-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="146d1-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2008">drivers licence</span></span>
- <span data-ttu-id="146d1-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="146d1-2009">drivers license</span></span>
- <span data-ttu-id="146d1-2010">driving licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2010">driving licence</span></span>
- <span data-ttu-id="146d1-2011">driving license</span><span class="sxs-lookup"><span data-stu-id="146d1-2011">driving license</span></span>
- <span data-ttu-id="146d1-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="146d1-2012">permis de conduire</span></span>
- <span data-ttu-id="146d1-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="146d1-2013">licence number</span></span>
- <span data-ttu-id="146d1-2014">license number</span><span class="sxs-lookup"><span data-stu-id="146d1-2014">license number</span></span>
- <span data-ttu-id="146d1-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-2015">licence numbers</span></span>
- <span data-ttu-id="146d1-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="146d1-2017">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="146d1-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2018">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2018">Format</span></span>

<span data-ttu-id="146d1-2019">12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2020">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2020">Pattern</span></span>

<span data-ttu-id="146d1-2021">12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2022">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2022">Checksum</span></span>

<span data-ttu-id="146d1-2023">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2024">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2024">Definition</span></span>

<span data-ttu-id="146d1-2025">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2026">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2027">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2027">Keywords</span></span>

<span data-ttu-id="146d1-2028">无</span><span class="sxs-lookup"><span data-stu-id="146d1-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="146d1-2029">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2030">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2030">Format</span></span>

<span data-ttu-id="146d1-2031">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2032">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2032">Pattern</span></span>

<span data-ttu-id="146d1-2033">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="146d1-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="146d1-2034">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2034">Two digits</span></span> 
- <span data-ttu-id="146d1-2035">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2036">五位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2037">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2037">Checksum</span></span>

<span data-ttu-id="146d1-2038">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2039">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2039">Definition</span></span>

<span data-ttu-id="146d1-2040">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2041">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2042">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2043">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="146d1-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-2044">Keyword_passport</span></span>

- <span data-ttu-id="146d1-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2045">Passport Number</span></span>
- <span data-ttu-id="146d1-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="146d1-2046">Passport No</span></span>
- <span data-ttu-id="146d1-2047">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-2047">Passport #</span></span>
- <span data-ttu-id="146d1-2048">登记卡#</span><span class="sxs-lookup"><span data-stu-id="146d1-2048">Passport#</span></span>
- <span data-ttu-id="146d1-2049">PassportID</span><span class="sxs-lookup"><span data-stu-id="146d1-2049">PassportID</span></span>
- <span data-ttu-id="146d1-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="146d1-2050">Passportno</span></span>
- <span data-ttu-id="146d1-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-2051">passportnumber</span></span>
- <span data-ttu-id="146d1-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-2052">パスポート</span></span>
- <span data-ttu-id="146d1-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2053">パスポート番号</span></span>
- <span data-ttu-id="146d1-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-2054">パスポートのNum</span></span>
- <span data-ttu-id="146d1-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2055">パスポート ＃</span></span> 
- <span data-ttu-id="146d1-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="146d1-2056">Numéro de passeport</span></span>
- <span data-ttu-id="146d1-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="146d1-2057">Passeport n °</span></span>
- <span data-ttu-id="146d1-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="146d1-2058">Passeport Non</span></span>
- <span data-ttu-id="146d1-2059">Passeport #</span><span class="sxs-lookup"><span data-stu-id="146d1-2059">Passeport #</span></span>
- <span data-ttu-id="146d1-2060">Passeport#</span><span class="sxs-lookup"><span data-stu-id="146d1-2060">Passeport#</span></span>
- <span data-ttu-id="146d1-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="146d1-2061">PasseportNon</span></span>
- <span data-ttu-id="146d1-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="146d1-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="146d1-2063">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="146d1-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2064">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2064">Format</span></span>

<span data-ttu-id="146d1-2065">15 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2066">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2066">Pattern</span></span>

<span data-ttu-id="146d1-2067">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="146d1-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="146d1-2068">13位数，后跟一个空格，后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="146d1-2069">或</span><span class="sxs-lookup"><span data-stu-id="146d1-2069">or</span></span>
- <span data-ttu-id="146d1-2070">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2071">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2071">Checksum</span></span>

<span data-ttu-id="146d1-2072">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2073">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2073">Definition</span></span>

<span data-ttu-id="146d1-2074">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2075">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2076">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="146d1-2077">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2077">The checksum passes.</span></span>

<span data-ttu-id="146d1-2078">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2079">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2080">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="146d1-2081">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2081">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2082">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="146d1-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="146d1-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="146d1-2084">insee</span><span class="sxs-lookup"><span data-stu-id="146d1-2084">insee</span></span>
- <span data-ttu-id="146d1-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-2085">securité sociale</span></span>
- <span data-ttu-id="146d1-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-2086">securite sociale</span></span>
- <span data-ttu-id="146d1-2087">national id</span><span class="sxs-lookup"><span data-stu-id="146d1-2087">national id</span></span>
- <span data-ttu-id="146d1-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="146d1-2088">national identification</span></span>
- <span data-ttu-id="146d1-2089">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="146d1-2089">numéro d'identité</span></span>
- <span data-ttu-id="146d1-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="146d1-2090">no d'identité</span></span>
- <span data-ttu-id="146d1-2091">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-2091">no.</span></span> <span data-ttu-id="146d1-2092">d'identité</span><span class="sxs-lookup"><span data-stu-id="146d1-2092">d'identité</span></span>
- <span data-ttu-id="146d1-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="146d1-2093">numero d'identite</span></span>
- <span data-ttu-id="146d1-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="146d1-2094">no d'identite</span></span>
- <span data-ttu-id="146d1-2095">不。</span><span class="sxs-lookup"><span data-stu-id="146d1-2095">no.</span></span> <span data-ttu-id="146d1-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="146d1-2096">d'identite</span></span>
- <span data-ttu-id="146d1-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="146d1-2097">social security number</span></span>
- <span data-ttu-id="146d1-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="146d1-2098">social security code</span></span>
- <span data-ttu-id="146d1-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="146d1-2099">social insurance number</span></span>
- <span data-ttu-id="146d1-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="146d1-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="146d1-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="146d1-2101">d'identité nationale</span></span>
- <span data-ttu-id="146d1-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="146d1-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="146d1-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="146d1-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="146d1-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="146d1-2105">numéro de sécu</span></span>
- <span data-ttu-id="146d1-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="146d1-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="146d1-2107">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2108">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2108">Format</span></span>

<span data-ttu-id="146d1-2109">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="146d1-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2110">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2110">Pattern</span></span>

<span data-ttu-id="146d1-2111">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="146d1-2112">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2112">A digit or letter</span></span> 
- <span data-ttu-id="146d1-2113">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2113">Two digits</span></span> 
- <span data-ttu-id="146d1-2114">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2114">Six digits or letters</span></span> 
- <span data-ttu-id="146d1-2115">一位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2115">A digit</span></span> 
- <span data-ttu-id="146d1-2116">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2117">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2117">Checksum</span></span>

<span data-ttu-id="146d1-2118">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2119">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2119">Definition</span></span>

<span data-ttu-id="146d1-2120">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2121">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2122">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="146d1-2123">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="146d1-2124">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="146d1-2125">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="146d1-2126">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2126">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2127">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="146d1-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="146d1-2129">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2129">Führerschein</span></span>
- <span data-ttu-id="146d1-2130">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2130">Fuhrerschein</span></span>
- <span data-ttu-id="146d1-2131">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2131">Fuehrerschein</span></span>
- <span data-ttu-id="146d1-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="146d1-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="146d1-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="146d1-2135">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2135">Führerschein-</span></span> 
- <span data-ttu-id="146d1-2136">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="146d1-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="146d1-2137">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="146d1-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="146d1-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="146d1-2139">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="146d1-2140">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="146d1-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="146d1-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="146d1-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="146d1-2144">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="146d1-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="146d1-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="146d1-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="146d1-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="146d1-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="146d1-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="146d1-2151">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="146d1-2152">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="146d1-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="146d1-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="146d1-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="146d1-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="146d1-2156">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="146d1-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="146d1-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="146d1-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="146d1-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="146d1-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="146d1-2162">通讯</span><span class="sxs-lookup"><span data-stu-id="146d1-2162">DL</span></span> 
- <span data-ttu-id="146d1-2163">DLS</span><span class="sxs-lookup"><span data-stu-id="146d1-2163">DLS</span></span>
- <span data-ttu-id="146d1-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-2164">Driv Lic</span></span> 
- <span data-ttu-id="146d1-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="146d1-2165">Driv Licen</span></span> 
- <span data-ttu-id="146d1-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="146d1-2166">Driv License</span></span>
- <span data-ttu-id="146d1-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2167">Driv Licenses</span></span> 
- <span data-ttu-id="146d1-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2168">Driv Licence</span></span> 
- <span data-ttu-id="146d1-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-2169">Driv Licences</span></span> 
- <span data-ttu-id="146d1-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-2170">Driv Lic</span></span> 
- <span data-ttu-id="146d1-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="146d1-2171">Driver Licen</span></span> 
- <span data-ttu-id="146d1-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="146d1-2172">Driver License</span></span> 
- <span data-ttu-id="146d1-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2173">Driver Licenses</span></span> 
- <span data-ttu-id="146d1-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2174">Driver Licence</span></span> 
- <span data-ttu-id="146d1-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-2175">Driver Licences</span></span> 
- <span data-ttu-id="146d1-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-2176">Drivers Lic</span></span> 
- <span data-ttu-id="146d1-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="146d1-2177">Drivers Licen</span></span> 
- <span data-ttu-id="146d1-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="146d1-2178">Drivers License</span></span> 
- <span data-ttu-id="146d1-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="146d1-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2180">Drivers Licence</span></span> 
- <span data-ttu-id="146d1-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-2181">Drivers Licences</span></span> 
- <span data-ttu-id="146d1-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-2182">Driver's Lic</span></span> 
- <span data-ttu-id="146d1-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="146d1-2183">Driver's Licen</span></span> 
- <span data-ttu-id="146d1-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="146d1-2184">Driver's License</span></span> 
- <span data-ttu-id="146d1-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="146d1-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2186">Driver's Licence</span></span> 
- <span data-ttu-id="146d1-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-2187">Driver's Licences</span></span> 
- <span data-ttu-id="146d1-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-2188">Driving Lic</span></span> 
- <span data-ttu-id="146d1-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="146d1-2189">Driving Licen</span></span> 
- <span data-ttu-id="146d1-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="146d1-2190">Driving License</span></span> 
- <span data-ttu-id="146d1-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2191">Driving Licenses</span></span> 
- <span data-ttu-id="146d1-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2192">Driving Licence</span></span> 
- <span data-ttu-id="146d1-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="146d1-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="146d1-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="146d1-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="146d1-2195">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="146d1-2196">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2197">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="146d1-2198">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2198">No-Führerschein</span></span> 
- <span data-ttu-id="146d1-2199">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2200">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="146d1-2201">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2201">N-Führerschein</span></span> 
- <span data-ttu-id="146d1-2202">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2203">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="146d1-2204">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="146d1-2205">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2206">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="146d1-2207">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2207">No-Führerschein</span></span> 
- <span data-ttu-id="146d1-2208">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2209">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="146d1-2210">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2210">N-Führerschein</span></span> 
- <span data-ttu-id="146d1-2211">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="146d1-2212">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="146d1-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="146d1-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="146d1-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="146d1-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="146d1-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="146d1-2215">ausstellungsort</span></span>
- <span data-ttu-id="146d1-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="146d1-2216">ausstellende behöde</span></span>
- <span data-ttu-id="146d1-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="146d1-2217">ausstellende behorde</span></span>
- <span data-ttu-id="146d1-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="146d1-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="146d1-2219">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2220">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2220">Format</span></span>

<span data-ttu-id="146d1-2221">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2222">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2222">Pattern</span></span>

<span data-ttu-id="146d1-2223">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="146d1-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="146d1-2224">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="146d1-2225">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2225">Three digits</span></span> 
- <span data-ttu-id="146d1-2226">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="146d1-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="146d1-2227">一位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2228">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2228">Checksum</span></span>

<span data-ttu-id="146d1-2229">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2230">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2230">Definition</span></span>

<span data-ttu-id="146d1-2231">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2232">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2233">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="146d1-2234">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2234">The checksum passes.</span></span>

<span data-ttu-id="146d1-2235">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2236">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2237">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="146d1-2238">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2238">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2239">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="146d1-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="146d1-2241">reisepass</span><span class="sxs-lookup"><span data-stu-id="146d1-2241">reisepass</span></span>
- <span data-ttu-id="146d1-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="146d1-2242">reisepasse</span></span>
- <span data-ttu-id="146d1-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2243">reisepassnummer</span></span>
- <span data-ttu-id="146d1-2244">登记卡</span><span class="sxs-lookup"><span data-stu-id="146d1-2244">passport</span></span>
- <span data-ttu-id="146d1-2245">passports</span><span class="sxs-lookup"><span data-stu-id="146d1-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="146d1-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="146d1-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="146d1-2247">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-2247">geburtsdatum</span></span>
- <span data-ttu-id="146d1-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="146d1-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="146d1-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="146d1-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="146d1-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="146d1-2251">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="146d1-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="146d1-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="146d1-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="146d1-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="146d1-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="146d1-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="146d1-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="146d1-2255">bnationalit</span><span class="sxs-lookup"><span data-stu-id="146d1-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="146d1-2256">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2257">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2257">Format</span></span>

<span data-ttu-id="146d1-2258">自2010年11月1日起：九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="146d1-2259">从1年4月1987至31年10月2010：10位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2260">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2260">Pattern</span></span>

<span data-ttu-id="146d1-2261">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="146d1-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="146d1-2262">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2263">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2263">Eight digits</span></span>

<span data-ttu-id="146d1-2264">介于1年4月1987至 31 10 月2010：</span><span class="sxs-lookup"><span data-stu-id="146d1-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="146d1-2265">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2266">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2266">Checksum</span></span>

<span data-ttu-id="146d1-2267">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2268">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2268">Definition</span></span>

<span data-ttu-id="146d1-2269">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2270">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2271">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2272">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="146d1-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="146d1-2274">Identity Card</span><span class="sxs-lookup"><span data-stu-id="146d1-2274">Identity Card</span></span>
- <span data-ttu-id="146d1-2275">ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2275">ID</span></span>
- <span data-ttu-id="146d1-2276">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-2276">Identification</span></span>
- <span data-ttu-id="146d1-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="146d1-2277">Personalausweis</span></span>
- <span data-ttu-id="146d1-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="146d1-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="146d1-2279">Ausweis</span></span>
- <span data-ttu-id="146d1-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="146d1-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="146d1-2281">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="146d1-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2282">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2282">Format</span></span>

<span data-ttu-id="146d1-2283">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="146d1-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2284">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2284">Pattern</span></span>

<span data-ttu-id="146d1-2285">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="146d1-2286">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="146d1-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="146d1-2287">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="146d1-2287">A dash</span></span> 
- <span data-ttu-id="146d1-2288">六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2288">Six digits</span></span>

<span data-ttu-id="146d1-2289">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="146d1-2290">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="146d1-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="146d1-2291">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="146d1-2291">A dash</span></span> 
- <span data-ttu-id="146d1-2292">六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2293">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2293">Checksum</span></span>

<span data-ttu-id="146d1-2294">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2295">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2295">Definition</span></span>

<span data-ttu-id="146d1-2296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2297">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2298">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2299">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="146d1-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="146d1-2301">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="146d1-2301">Greek identity Card</span></span>
- <span data-ttu-id="146d1-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="146d1-2302">Tautotita</span></span>
- <span data-ttu-id="146d1-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="146d1-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="146d1-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="146d1-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="146d1-2305">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="146d1-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2306">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2306">Format</span></span>

<span data-ttu-id="146d1-2307">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="146d1-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2308">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2308">Pattern</span></span>

<span data-ttu-id="146d1-2309">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="146d1-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="146d1-2310">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2311">六个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2311">Six digits</span></span> 
- <span data-ttu-id="146d1-2312">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="146d1-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2313">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2313">Checksum</span></span>

<span data-ttu-id="146d1-2314">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2315">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2315">Definition</span></span>

<span data-ttu-id="146d1-2316">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2317">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2318">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="146d1-2319">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2319">The checksum passes.</span></span>

<span data-ttu-id="146d1-2320">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2321">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2322">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2322">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2323">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="146d1-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="146d1-2325">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="146d1-2325">hong kong identity card</span></span>
- <span data-ttu-id="146d1-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="146d1-2326">HKIDC</span></span>
- <span data-ttu-id="146d1-2327">id card</span><span class="sxs-lookup"><span data-stu-id="146d1-2327">id card</span></span>
- <span data-ttu-id="146d1-2328">identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-2328">identity card</span></span>
- <span data-ttu-id="146d1-2329">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="146d1-2329">hk identity card</span></span>
- <span data-ttu-id="146d1-2330">香港 id</span><span class="sxs-lookup"><span data-stu-id="146d1-2330">hong kong id</span></span>
- <span data-ttu-id="146d1-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2331">香港身份證</span></span>
- <span data-ttu-id="146d1-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="146d1-2333">證</span><span class="sxs-lookup"><span data-stu-id="146d1-2333">身份證</span></span>
- <span data-ttu-id="146d1-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2334">身份証</span></span>
- <span data-ttu-id="146d1-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2335">身分證</span></span>
- <span data-ttu-id="146d1-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2336">身分証</span></span>
- <span data-ttu-id="146d1-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2337">香港身份証</span></span>
- <span data-ttu-id="146d1-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2338">香港身分證</span></span>
- <span data-ttu-id="146d1-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2339">香港身分証</span></span>
- <span data-ttu-id="146d1-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2340">香港身份證</span></span>
- <span data-ttu-id="146d1-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2341">香港居民身份證</span></span>
- <span data-ttu-id="146d1-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2342">香港居民身份証</span></span>
- <span data-ttu-id="146d1-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2343">香港居民身分證</span></span>
- <span data-ttu-id="146d1-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2344">香港居民身分証</span></span>
- <span data-ttu-id="146d1-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="146d1-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="146d1-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="146d1-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="146d1-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="146d1-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="146d1-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="146d1-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="146d1-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="146d1-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="146d1-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="146d1-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="146d1-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="146d1-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="146d1-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="146d1-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="146d1-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="146d1-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="146d1-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="146d1-2361">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="146d1-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2362">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2362">Format</span></span>

<span data-ttu-id="146d1-2363">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2364">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2364">Pattern</span></span>

<span data-ttu-id="146d1-2365">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2365">10 letters or digits:</span></span>
- <span data-ttu-id="146d1-2366">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2367">四位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2367">Four digits</span></span> 
- <span data-ttu-id="146d1-2368">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2369">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2369">Checksum</span></span>

<span data-ttu-id="146d1-2370">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2371">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2371">Definition</span></span>

<span data-ttu-id="146d1-2372">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2373">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2374">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="146d1-2375">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2376">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="146d1-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="146d1-2378">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="146d1-2379">蛋糕</span><span class="sxs-lookup"><span data-stu-id="146d1-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="146d1-2380">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2381">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2381">Format</span></span>

<span data-ttu-id="146d1-2382">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="146d1-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2383">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2383">Pattern</span></span>

<span data-ttu-id="146d1-2384">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2384">12 digits:</span></span>
- <span data-ttu-id="146d1-2385">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2385">Four digits</span></span> 
- <span data-ttu-id="146d1-2386">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="146d1-2386">An optional space or dash</span></span> 
- <span data-ttu-id="146d1-2387">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2387">Four digits</span></span> 
- <span data-ttu-id="146d1-2388">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="146d1-2388">An optional space or dash</span></span> 
- <span data-ttu-id="146d1-2389">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2390">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2390">Checksum</span></span>

<span data-ttu-id="146d1-2391">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2392">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2392">Definition</span></span>

<span data-ttu-id="146d1-2393">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-2394">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="146d1-2395">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2395">The checksum passes.</span></span>
<span data-ttu-id="146d1-2396">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-2397">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2397">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="146d1-2398">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="146d1-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="146d1-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="146d1-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="146d1-2400">Aadhar</span></span>
- <span data-ttu-id="146d1-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="146d1-2401">Aadhaar</span></span>
- <span data-ttu-id="146d1-2402">UID</span><span class="sxs-lookup"><span data-stu-id="146d1-2402">UID</span></span>
- <span data-ttu-id="146d1-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="146d1-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="146d1-2404">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="146d1-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2405">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2405">Format</span></span>

<span data-ttu-id="146d1-2406">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="146d1-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2407">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2407">Pattern</span></span>

<span data-ttu-id="146d1-2408">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2408">16 digits:</span></span>
- <span data-ttu-id="146d1-2409">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-2409">Two-digit province code</span></span> 
- <span data-ttu-id="146d1-2410">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2410">A period (optional)</span></span> 
- <span data-ttu-id="146d1-2411">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="146d1-2412">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="146d1-2413">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2413">A period (optional)</span></span> 
- <span data-ttu-id="146d1-2414">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="146d1-2415">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2415">A period (optional)</span></span> 
- <span data-ttu-id="146d1-2416">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2417">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2417">Checksum</span></span>

<span data-ttu-id="146d1-2418">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2419">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2419">Definition</span></span>

<span data-ttu-id="146d1-2420">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2421">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2422">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="146d1-2423">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2424">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2425">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="146d1-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="146d1-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="146d1-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="146d1-2427">KTP</span></span>
- <span data-ttu-id="146d1-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="146d1-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="146d1-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="146d1-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="146d1-2430">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="146d1-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2431">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2431">Format</span></span>

<span data-ttu-id="146d1-2432">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="146d1-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2433">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2433">Pattern</span></span>

<span data-ttu-id="146d1-2434">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="146d1-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="146d1-2435">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="146d1-2435">Two-letter country code</span></span>
- <span data-ttu-id="146d1-2436">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="146d1-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="146d1-2437">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="146d1-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="146d1-2438">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2438">1-3 letters or digits</span></span>

<span data-ttu-id="146d1-p133">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="146d1-p133">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="146d1-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="146d1-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2442">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2442">Checksum</span></span>

<span data-ttu-id="146d1-2443">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2444">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2444">Definition</span></span>

<span data-ttu-id="146d1-2445">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2446">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2447">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2448">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2448">Keywords</span></span>

<span data-ttu-id="146d1-2449">无</span><span class="sxs-lookup"><span data-stu-id="146d1-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="146d1-2450">IP 地址</span><span class="sxs-lookup"><span data-stu-id="146d1-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2451">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="146d1-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="146d1-2452">IPv4:</span></span>
<span data-ttu-id="146d1-2453">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="146d1-2454">Ipv4</span><span class="sxs-lookup"><span data-stu-id="146d1-2454">IPv6:</span></span>
<span data-ttu-id="146d1-2455"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2456">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2457">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2457">Checksum</span></span>

<span data-ttu-id="146d1-2458">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2459">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2459">Definition</span></span>

<span data-ttu-id="146d1-2460">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2461">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2462">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="146d1-2463">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2464">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2465">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="146d1-2466">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2467">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2468">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2468">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2469">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="146d1-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="146d1-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="146d1-2471">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="146d1-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="146d1-2472">ip address</span></span> 
- <span data-ttu-id="146d1-2473">ip addresses</span><span class="sxs-lookup"><span data-stu-id="146d1-2473">ip addresses</span></span>
- <span data-ttu-id="146d1-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="146d1-2474">internet protocol</span></span>
- <span data-ttu-id="146d1-2475">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="146d1-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="146d1-2476">国际分类的 Diseases （ICD-10 CM）</span><span class="sxs-lookup"><span data-stu-id="146d1-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2477">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2477">Format</span></span>

<span data-ttu-id="146d1-2478">Dictionary</span><span class="sxs-lookup"><span data-stu-id="146d1-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2479">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2479">Pattern</span></span>

<span data-ttu-id="146d1-2480">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2481">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2481">Checksum</span></span>

<span data-ttu-id="146d1-2482">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2483">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2483">Definition</span></span>

<span data-ttu-id="146d1-2484">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2485">找到 Dictionary_icd_10_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="146d1-2486">找到 Dictionary_icd_10_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="146d1-2487">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2488">找到 Dictionary_icd_10_ 更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="146d1-2489">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2489">Keywords</span></span>

<span data-ttu-id="146d1-2490">Dictionary_icd_10_updated 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="146d1-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="146d1-2491">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="146d1-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="146d1-2492">Dictionary_icd_10_codes 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="146d1-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="146d1-2493">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="146d1-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="146d1-2494">国际分类的 Diseases （ICD-9-CM）</span><span class="sxs-lookup"><span data-stu-id="146d1-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2495">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2495">Format</span></span>

<span data-ttu-id="146d1-2496">Dictionary</span><span class="sxs-lookup"><span data-stu-id="146d1-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2497">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2497">Pattern</span></span>

<span data-ttu-id="146d1-2498">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2499">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2499">Checksum</span></span>

<span data-ttu-id="146d1-2500">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2501">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2501">Definition</span></span>

<span data-ttu-id="146d1-2502">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2503">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="146d1-2504">找到 Dictionary_icd_9_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="146d1-2505">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2506">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2507">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2507">Keywords</span></span>

<span data-ttu-id="146d1-2508">Dictionary_icd_9_updated 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="146d1-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="146d1-2509">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="146d1-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="146d1-2510">Dictionary_icd_9_codes 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="146d1-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="146d1-2511">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="146d1-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="146d1-2512">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2513">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2513">Format</span></span>

<span data-ttu-id="146d1-2514">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="146d1-2515">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="146d1-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="146d1-2516">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="146d1-2517">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="146d1-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2518">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2518">Pattern</span></span>

<span data-ttu-id="146d1-2519">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="146d1-2520">七个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2520">Seven digits</span></span> 
- <span data-ttu-id="146d1-2521">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="146d1-2522">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="146d1-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="146d1-2523">七个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2523">Seven digits</span></span> 
- <span data-ttu-id="146d1-2524">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="146d1-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="146d1-2525">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2526">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2526">Checksum</span></span>

<span data-ttu-id="146d1-2527">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2528">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2528">Definition</span></span>

<span data-ttu-id="146d1-2529">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2530">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2531">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-2531">One of the following is true:</span></span>
    - <span data-ttu-id="146d1-2532">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="146d1-2533">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="146d1-2534">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2534">The checksum passes.</span></span>

<span data-ttu-id="146d1-2535">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2536">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2537">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2537">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2538">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="146d1-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="146d1-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="146d1-2540">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="146d1-2541">PPS Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2541">PPS Number</span></span> 
- <span data-ttu-id="146d1-2542">PPS Num</span><span class="sxs-lookup"><span data-stu-id="146d1-2542">PPS Num</span></span> 
- <span data-ttu-id="146d1-2543">PPS No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2543">PPS No.</span></span> 
- <span data-ttu-id="146d1-2544">PPS #</span><span class="sxs-lookup"><span data-stu-id="146d1-2544">PPS #</span></span> 
- <span data-ttu-id="146d1-2545">.PPS#</span><span class="sxs-lookup"><span data-stu-id="146d1-2545">PPS#</span></span> 
- <span data-ttu-id="146d1-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="146d1-2546">PPSN</span></span> 
- <span data-ttu-id="146d1-2547">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="146d1-2547">Public Services Card</span></span> 
- <span data-ttu-id="146d1-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="146d1-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="146d1-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="146d1-2549">Uimh.</span></span> <span data-ttu-id="146d1-2550">PSP</span><span class="sxs-lookup"><span data-stu-id="146d1-2550">PSP</span></span> 
- <span data-ttu-id="146d1-2551">PSP</span><span class="sxs-lookup"><span data-stu-id="146d1-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="146d1-2552">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2553">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2553">Format</span></span>

<span data-ttu-id="146d1-2554">13 位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2555">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2555">Pattern</span></span>

<span data-ttu-id="146d1-2556">格式</span><span class="sxs-lookup"><span data-stu-id="146d1-2556">Formatted:</span></span>
- <span data-ttu-id="146d1-2557">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2557">Two digits</span></span> 
- <span data-ttu-id="146d1-2558">破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-2558">A dash</span></span> 
- <span data-ttu-id="146d1-2559">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2559">Three digits</span></span> 
- <span data-ttu-id="146d1-2560">破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-2560">A dash</span></span> 
- <span data-ttu-id="146d1-2561">八位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2561">Eight digits</span></span>

<span data-ttu-id="146d1-2562">纯</span><span class="sxs-lookup"><span data-stu-id="146d1-2562">Unformatted:</span></span>
- <span data-ttu-id="146d1-2563">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2564">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2564">Checksum</span></span>

<span data-ttu-id="146d1-2565">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2566">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2566">Definition</span></span>

<span data-ttu-id="146d1-2567">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2568">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2569">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2570">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="146d1-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="146d1-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2572">Bank Account Number</span></span> 
- <span data-ttu-id="146d1-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="146d1-2573">Bank Account</span></span> 
- <span data-ttu-id="146d1-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2574">Account Number</span></span> 
- <span data-ttu-id="146d1-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="146d1-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="146d1-2576">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2577">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2577">Format</span></span>

<span data-ttu-id="146d1-2578">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2579">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2579">Pattern</span></span>

<span data-ttu-id="146d1-2580">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2581">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2581">Checksum</span></span>

<span data-ttu-id="146d1-2582">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2583">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2583">Definition</span></span>

<span data-ttu-id="146d1-2584">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2585">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2586">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="146d1-2587">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2587">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2588">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="146d1-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="146d1-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="146d1-2590">מספר זהות</span></span> 
- <span data-ttu-id="146d1-2591">National ID Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="146d1-2592">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2593">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2593">Format</span></span>

<span data-ttu-id="146d1-2594">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="146d1-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2595">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2595">Pattern</span></span>

- <span data-ttu-id="146d1-2596">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="146d1-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="146d1-2597">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2598">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-2599">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="146d1-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="146d1-2600">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2601">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2601">Checksum</span></span>

<span data-ttu-id="146d1-2602">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2603">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2603">Definition</span></span>

<span data-ttu-id="146d1-2604">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2605">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2606">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2607">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="146d1-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="146d1-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="146d1-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="146d1-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="146d1-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="146d1-2611">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2612">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2612">Format</span></span>

<span data-ttu-id="146d1-2613">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2614">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2614">Pattern</span></span>

<span data-ttu-id="146d1-2615">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="146d1-2615">Bank account number:</span></span>
- <span data-ttu-id="146d1-2616">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2616">Seven or eight digits</span></span>
- <span data-ttu-id="146d1-2617">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="146d1-2617">Bank account branch code:</span></span>
- <span data-ttu-id="146d1-2618">四位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2618">Four digits</span></span> 
- <span data-ttu-id="146d1-2619">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="146d1-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="146d1-2620">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2620">Three digits</span></span>

<span data-ttu-id="146d1-2621">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2621">Checksum</span></span>

<span data-ttu-id="146d1-2622">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2623">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2623">Definition</span></span>

<span data-ttu-id="146d1-2624">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2625">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2626">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="146d1-2627">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-2627">One of the following is true:</span></span>
- <span data-ttu-id="146d1-2628">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2629">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="146d1-2630">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2631">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2632">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2633">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="146d1-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="146d1-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="146d1-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2635">Checking Account Number</span></span> 
- <span data-ttu-id="146d1-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="146d1-2636">Checking Account</span></span> 
- <span data-ttu-id="146d1-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-2637">Checking Account #</span></span> 
- <span data-ttu-id="146d1-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="146d1-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-2639">Checking Acct #</span></span> 
- <span data-ttu-id="146d1-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="146d1-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2641">Checking Account No.</span></span> 
- <span data-ttu-id="146d1-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2642">Bank Account Number</span></span> 
- <span data-ttu-id="146d1-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="146d1-2643">Bank Account</span></span> 
- <span data-ttu-id="146d1-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-2644">Bank Account #</span></span> 
- <span data-ttu-id="146d1-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="146d1-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-2646">Bank Acct #</span></span> 
- <span data-ttu-id="146d1-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="146d1-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2648">Bank Account No.</span></span> 
- <span data-ttu-id="146d1-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2649">Savings Account Number</span></span> 
- <span data-ttu-id="146d1-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="146d1-2650">Savings Account</span></span> 
- <span data-ttu-id="146d1-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-2651">Savings Account #</span></span> 
- <span data-ttu-id="146d1-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="146d1-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-2653">Savings Acct #</span></span> 
- <span data-ttu-id="146d1-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="146d1-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2655">Savings Account No.</span></span> 
- <span data-ttu-id="146d1-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2656">Debit Account Number</span></span> 
- <span data-ttu-id="146d1-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="146d1-2657">Debit Account</span></span> 
- <span data-ttu-id="146d1-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-2658">Debit Account #</span></span> 
- <span data-ttu-id="146d1-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="146d1-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-2660">Debit Acct #</span></span> 
- <span data-ttu-id="146d1-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="146d1-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2662">Debit Account No.</span></span> 
- <span data-ttu-id="146d1-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="146d1-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="146d1-2664">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="146d1-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="146d1-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="146d1-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="146d1-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="146d1-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="146d1-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="146d1-2667">口座番号の確認</span></span> 
- <span data-ttu-id="146d1-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2668">銀行口座番号</span></span> 
- <span data-ttu-id="146d1-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="146d1-2669">銀行口座</span></span> 
- <span data-ttu-id="146d1-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2670">銀行口座＃</span></span> 
- <span data-ttu-id="146d1-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="146d1-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="146d1-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="146d1-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="146d1-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2674">銀行口座番号</span></span>
- <span data-ttu-id="146d1-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="146d1-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="146d1-2676">預金口座</span></span> 
- <span data-ttu-id="146d1-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="146d1-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="146d1-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="146d1-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="146d1-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="146d1-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="146d1-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="146d1-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2683">口座番号</span></span> 
- <span data-ttu-id="146d1-2684">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2684">口座番号＃</span></span> 
- <span data-ttu-id="146d1-2685">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="146d1-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="146d1-2687">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="146d1-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="146d1-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="146d1-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="146d1-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="146d1-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="146d1-2691">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2692">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2692">Format</span></span>

<span data-ttu-id="146d1-2693">12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2694">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2694">Pattern</span></span>

<span data-ttu-id="146d1-2695">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2696">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2696">Checksum</span></span>

<span data-ttu-id="146d1-2697">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2698">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2698">Definition</span></span>

<span data-ttu-id="146d1-2699">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2700">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2701">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2702">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="146d1-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="146d1-2704">通讯#</span><span class="sxs-lookup"><span data-stu-id="146d1-2704">dl#</span></span> 
- <span data-ttu-id="146d1-2705">通讯</span><span class="sxs-lookup"><span data-stu-id="146d1-2705">DL＃</span></span> 
- <span data-ttu-id="146d1-2706">dls#</span><span class="sxs-lookup"><span data-stu-id="146d1-2706">dls#</span></span> 
- <span data-ttu-id="146d1-2707">DLS</span><span class="sxs-lookup"><span data-stu-id="146d1-2707">DLS＃</span></span> 
- <span data-ttu-id="146d1-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="146d1-2708">driver license</span></span> 
- <span data-ttu-id="146d1-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2709">driver licenses</span></span> 
- <span data-ttu-id="146d1-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="146d1-2710">drivers license</span></span> 
- <span data-ttu-id="146d1-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="146d1-2711">driver's license</span></span> 
- <span data-ttu-id="146d1-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2712">drivers licenses</span></span> 
- <span data-ttu-id="146d1-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-2713">driver's licenses</span></span> 
- <span data-ttu-id="146d1-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="146d1-2714">driving licence</span></span> 
- <span data-ttu-id="146d1-2715">.lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-2715">lic#</span></span> 
- <span data-ttu-id="146d1-2716">.LIC</span><span class="sxs-lookup"><span data-stu-id="146d1-2716">LIC＃</span></span> 
- <span data-ttu-id="146d1-2717">driver'lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-2717">lics#</span></span> 
- <span data-ttu-id="146d1-2718">state id</span><span class="sxs-lookup"><span data-stu-id="146d1-2718">state id</span></span> 
- <span data-ttu-id="146d1-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="146d1-2719">state identification</span></span> 
- <span data-ttu-id="146d1-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-2720">state identification number</span></span> 
- <span data-ttu-id="146d1-2721">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2721">低所得国＃</span></span> 
- <span data-ttu-id="146d1-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="146d1-2722">免許証</span></span> 
- <span data-ttu-id="146d1-2723">状態ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2723">状態ID</span></span>
- <span data-ttu-id="146d1-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="146d1-2724">状態の識別</span></span> 
- <span data-ttu-id="146d1-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2725">状態の識別番号</span></span> 
- <span data-ttu-id="146d1-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="146d1-2726">運転免許</span></span> 
- <span data-ttu-id="146d1-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="146d1-2727">運転免許証</span></span> 
- <span data-ttu-id="146d1-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="146d1-2729">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2730">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2730">Format</span></span>

<span data-ttu-id="146d1-2731">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2732">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2732">Pattern</span></span>

<span data-ttu-id="146d1-2733">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2734">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2734">Checksum</span></span>

<span data-ttu-id="146d1-2735">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2736">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2736">Definition</span></span>

<span data-ttu-id="146d1-2737">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2738">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2739">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2740">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="146d1-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="146d1-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-2742">パスポート</span></span> 
- <span data-ttu-id="146d1-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2743">パスポート番号</span></span> 
- <span data-ttu-id="146d1-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-2744">パスポートのNum</span></span> 
- <span data-ttu-id="146d1-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="146d1-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="146d1-2746">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2747">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2747">Format</span></span>

<span data-ttu-id="146d1-2748">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2749">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2749">Pattern</span></span>

<span data-ttu-id="146d1-2750">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2751">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2751">Checksum</span></span>

<span data-ttu-id="146d1-2752">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2753">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2753">Definition</span></span>

<span data-ttu-id="146d1-2754">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2755">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2756">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2757">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="146d1-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="146d1-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2759">Resident Registration Number</span></span>
- <span data-ttu-id="146d1-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2760">Resident Register Number</span></span> 
- <span data-ttu-id="146d1-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="146d1-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="146d1-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2763">Resident Register No.</span></span> 
- <span data-ttu-id="146d1-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="146d1-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="146d1-2766">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="146d1-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="146d1-2767">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="146d1-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="146d1-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="146d1-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="146d1-2770">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="146d1-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2771">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2771">Format</span></span>

<span data-ttu-id="146d1-2772">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2773">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2773">Pattern</span></span>

<span data-ttu-id="146d1-2774">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2774">7-12 digits:</span></span>
- <span data-ttu-id="146d1-2775">四位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2775">Four digits</span></span> 
- <span data-ttu-id="146d1-2776">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="146d1-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="146d1-2777">六位数字或</span><span class="sxs-lookup"><span data-stu-id="146d1-2777">Six digits OR</span></span>
- <span data-ttu-id="146d1-2778">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2779">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2779">Checksum</span></span>

<span data-ttu-id="146d1-2780">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2781">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2781">Definition</span></span>

<span data-ttu-id="146d1-2782">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2783">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2784">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="146d1-2785">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2786">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2787">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2787">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2788">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="146d1-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="146d1-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="146d1-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="146d1-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="146d1-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="146d1-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="146d1-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="146d1-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="146d1-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="146d1-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="146d1-2795">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="146d1-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2796">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2796">Format</span></span>

<span data-ttu-id="146d1-2797">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2798">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2798">Pattern</span></span>

<span data-ttu-id="146d1-2799">12个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2799">12 letters and digits:</span></span>
- <span data-ttu-id="146d1-2800">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="146d1-2801">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2801">Eight digits</span></span> 
- <span data-ttu-id="146d1-2802">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2803">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2803">Checksum</span></span>

<span data-ttu-id="146d1-2804">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2805">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2805">Definition</span></span>

<span data-ttu-id="146d1-2806">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2807">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2808">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2809">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="146d1-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="146d1-2811">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="146d1-2811">Residence card number</span></span>
- <span data-ttu-id="146d1-2812">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="146d1-2812">Residence card no</span></span>
- <span data-ttu-id="146d1-2813">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="146d1-2813">Residence card #</span></span>
- <span data-ttu-id="146d1-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="146d1-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="146d1-2815">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2816">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2816">Format</span></span>

<span data-ttu-id="146d1-2817">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="146d1-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2818">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2818">Pattern</span></span>

<span data-ttu-id="146d1-2819">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2819">12 digits:</span></span>
- <span data-ttu-id="146d1-2820">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="146d1-2821">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2821">A dash (optional)</span></span> 
- <span data-ttu-id="146d1-2822">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="146d1-2823">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2823">A dash (optional)</span></span> 
- <span data-ttu-id="146d1-2824">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2824">Three random digits</span></span> 
- <span data-ttu-id="146d1-2825">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="146d1-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2826">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2826">Checksum</span></span>

<span data-ttu-id="146d1-2827">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2828">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2828">Definition</span></span>

<span data-ttu-id="146d1-2829">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2830">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2831">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2832">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="146d1-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="146d1-2834">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="146d1-2834">digital application card</span></span>
- <span data-ttu-id="146d1-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="146d1-2835">i/c</span></span>
- <span data-ttu-id="146d1-2836">i/c 否</span><span class="sxs-lookup"><span data-stu-id="146d1-2836">i/c no</span></span>
- <span data-ttu-id="146d1-2837">ic</span><span class="sxs-lookup"><span data-stu-id="146d1-2837">ic</span></span>
- <span data-ttu-id="146d1-2838">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="146d1-2838">ic no</span></span>
- <span data-ttu-id="146d1-2839">id card</span><span class="sxs-lookup"><span data-stu-id="146d1-2839">id card</span></span>
- <span data-ttu-id="146d1-2840">标识卡</span><span class="sxs-lookup"><span data-stu-id="146d1-2840">identification Card</span></span>
- <span data-ttu-id="146d1-2841">identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-2841">identity card</span></span>
- <span data-ttu-id="146d1-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="146d1-2842">k/p</span></span>
- <span data-ttu-id="146d1-2843">k/p no</span><span class="sxs-lookup"><span data-stu-id="146d1-2843">k/p no</span></span>
- <span data-ttu-id="146d1-2844">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="146d1-2844">kad akuan diri</span></span>
- <span data-ttu-id="146d1-2845">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="146d1-2846">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="146d1-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="146d1-2847">kp</span><span class="sxs-lookup"><span data-stu-id="146d1-2847">kp</span></span>
- <span data-ttu-id="146d1-2848">kp no</span><span class="sxs-lookup"><span data-stu-id="146d1-2848">kp no</span></span>
- <span data-ttu-id="146d1-2849">mykad</span><span class="sxs-lookup"><span data-stu-id="146d1-2849">mykad</span></span>
- <span data-ttu-id="146d1-2850">mykas</span><span class="sxs-lookup"><span data-stu-id="146d1-2850">mykas</span></span>
- <span data-ttu-id="146d1-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="146d1-2851">mykid</span></span>
- <span data-ttu-id="146d1-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="146d1-2852">mypr</span></span>
- <span data-ttu-id="146d1-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="146d1-2853">mytentera</span></span>
- <span data-ttu-id="146d1-2854">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="146d1-2854">malaysia identity card</span></span>
- <span data-ttu-id="146d1-2855">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="146d1-2855">malaysian identity card</span></span>
- <span data-ttu-id="146d1-2856">nric</span><span class="sxs-lookup"><span data-stu-id="146d1-2856">nric</span></span>
- <span data-ttu-id="146d1-2857">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="146d1-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="146d1-2858">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2859">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2859">Format</span></span>

<span data-ttu-id="146d1-2860">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="146d1-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2861">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2861">Pattern</span></span>

<span data-ttu-id="146d1-2862">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2862">8-9 digits:</span></span>
- <span data-ttu-id="146d1-2863">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2863">Three digits</span></span> 
- <span data-ttu-id="146d1-2864">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2864">A space (optional)</span></span> 
- <span data-ttu-id="146d1-2865">三个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2865">Three digits</span></span> 
- <span data-ttu-id="146d1-2866">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="146d1-2866">A space (optional)</span></span> 
- <span data-ttu-id="146d1-2867">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2868">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2868">Checksum</span></span>

<span data-ttu-id="146d1-2869">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2870">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2870">Definition</span></span>

<span data-ttu-id="146d1-2871">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2872">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2873">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="146d1-2874">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="146d1-2875">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2875">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2876">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="146d1-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="146d1-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="146d1-2878">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="146d1-2878">Citizen service number</span></span> 
- <span data-ttu-id="146d1-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="146d1-2879">BSN</span></span> 
- <span data-ttu-id="146d1-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="146d1-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2881">Sofinummer</span></span> 
- <span data-ttu-id="146d1-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="146d1-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="146d1-2884">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2885">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2885">Format</span></span>

<span data-ttu-id="146d1-2886">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2887">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2887">Pattern</span></span>

<span data-ttu-id="146d1-2888">三个字母（不区分大小写）一个空格（可选）四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2889">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2889">Checksum</span></span>

<span data-ttu-id="146d1-2890">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2891">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2891">Definition</span></span>

<span data-ttu-id="146d1-2892">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2893">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2894">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="146d1-2895">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2895">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="146d1-2896">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2896">Keywords</span></span>

<span data-ttu-id="146d1-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="146d1-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="146d1-2898">NHI</span><span class="sxs-lookup"><span data-stu-id="146d1-2898">NHI</span></span> 
- <span data-ttu-id="146d1-2899">New Zealand</span><span class="sxs-lookup"><span data-stu-id="146d1-2899">New Zealand</span></span> 
- <span data-ttu-id="146d1-2900">运行状况</span><span class="sxs-lookup"><span data-stu-id="146d1-2900">Health</span></span> 
- <span data-ttu-id="146d1-2901">治疗</span><span class="sxs-lookup"><span data-stu-id="146d1-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="146d1-2902">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2903">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2903">Format</span></span>

<span data-ttu-id="146d1-2904">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2905">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2905">Pattern</span></span>

<span data-ttu-id="146d1-2906">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2906">11 digits:</span></span>
- <span data-ttu-id="146d1-2907">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="146d1-2908">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="146d1-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="146d1-2909">两个校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2910">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2910">Checksum</span></span>

<span data-ttu-id="146d1-2911">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2912">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2912">Definition</span></span>

<span data-ttu-id="146d1-2913">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2914">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2915">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="146d1-2916">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2916">The checksum passes.</span></span>
- <span data-ttu-id="146d1-2917">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2918">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2919">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2919">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2920">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="146d1-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="146d1-2922">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-2922">Personal identification number</span></span>
- <span data-ttu-id="146d1-2923">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="146d1-2924">ID Number</span><span class="sxs-lookup"><span data-stu-id="146d1-2924">ID Number</span></span>
- <span data-ttu-id="146d1-2925">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-2925">Identification</span></span>
- <span data-ttu-id="146d1-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2926">Personnummer</span></span>
- <span data-ttu-id="146d1-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="146d1-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="146d1-2928">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2929">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2929">Format</span></span>

<span data-ttu-id="146d1-2930">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="146d1-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2931">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2931">Pattern</span></span>

<span data-ttu-id="146d1-2932">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-2932">12 digits:</span></span>
- <span data-ttu-id="146d1-2933">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2933">Four digits</span></span> 
- <span data-ttu-id="146d1-2934">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-2934">A hyphen</span></span> 
- <span data-ttu-id="146d1-2935">七个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-2935">Seven digits</span></span> 
- <span data-ttu-id="146d1-2936">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-2936">A hyphen</span></span> 
- <span data-ttu-id="146d1-2937">一个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2938">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2938">Checksum</span></span>

<span data-ttu-id="146d1-2939">否</span><span class="sxs-lookup"><span data-stu-id="146d1-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2940">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2940">Definition</span></span>

<span data-ttu-id="146d1-2941">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2942">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2943">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2944">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="146d1-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="146d1-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="146d1-2946">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="146d1-2947">UMID</span><span class="sxs-lookup"><span data-stu-id="146d1-2947">UMID</span></span> 
- <span data-ttu-id="146d1-2948">Identity Card</span><span class="sxs-lookup"><span data-stu-id="146d1-2948">Identity Card</span></span> 
- <span data-ttu-id="146d1-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="146d1-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="146d1-2950">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="146d1-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2951">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2951">Format</span></span>

<span data-ttu-id="146d1-2952">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2953">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2953">Pattern</span></span>

<span data-ttu-id="146d1-2954">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2955">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2955">Checksum</span></span>

<span data-ttu-id="146d1-2956">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2957">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2957">Definition</span></span>

<span data-ttu-id="146d1-2958">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="146d1-2959">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="146d1-2960">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2961">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="146d1-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="146d1-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="146d1-2963">Dowód osobisty</span></span>
- <span data-ttu-id="146d1-2964">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="146d1-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="146d1-2965">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="146d1-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="146d1-2966">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="146d1-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="146d1-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="146d1-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="146d1-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="146d1-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="146d1-2969">dow.</span><span class="sxs-lookup"><span data-stu-id="146d1-2969">dow.</span></span> <span data-ttu-id="146d1-2970">os.</span><span class="sxs-lookup"><span data-stu-id="146d1-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="146d1-2971">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="146d1-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2972">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2972">Format</span></span>

<span data-ttu-id="146d1-2973">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2974">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2974">Pattern</span></span>

<span data-ttu-id="146d1-2975">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2976">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2976">Checksum</span></span>

<span data-ttu-id="146d1-2977">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2978">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2978">Definition</span></span>

<span data-ttu-id="146d1-2979">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2980">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2981">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="146d1-2982">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2983">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="146d1-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="146d1-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="146d1-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="146d1-2985">Nr PESEL</span></span>
- <span data-ttu-id="146d1-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="146d1-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="146d1-2987">波兰护照</span><span class="sxs-lookup"><span data-stu-id="146d1-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="146d1-2988">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-2988">Format</span></span>

<span data-ttu-id="146d1-2989">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-2990">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-2990">Pattern</span></span>

<span data-ttu-id="146d1-2991">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-2992">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-2992">Checksum</span></span>

<span data-ttu-id="146d1-2993">是</span><span class="sxs-lookup"><span data-stu-id="146d1-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-2994">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-2994">Definition</span></span>

<span data-ttu-id="146d1-2995">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-2996">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-2997">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="146d1-2998">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-2998">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="146d1-2999">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="146d1-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="146d1-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="146d1-3001">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="146d1-3001">Numer paszportu</span></span>
- <span data-ttu-id="146d1-3002">Führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="146d1-3002">Nr.</span></span> <span data-ttu-id="146d1-3003">Paszportu</span><span class="sxs-lookup"><span data-stu-id="146d1-3003">Paszportu</span></span>
- <span data-ttu-id="146d1-3004">Paszport</span><span class="sxs-lookup"><span data-stu-id="146d1-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="146d1-3005">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3006">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3006">Format</span></span>

<span data-ttu-id="146d1-3007">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3008">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3008">Pattern</span></span>

<span data-ttu-id="146d1-3009">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3010">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3010">Checksum</span></span>

<span data-ttu-id="146d1-3011">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3012">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3012">Definition</span></span>

<span data-ttu-id="146d1-3013">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3014">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3015">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3016">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="146d1-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="146d1-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="146d1-3018">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="146d1-3018">Citizen Card</span></span>
- <span data-ttu-id="146d1-3019">National ID Card</span><span class="sxs-lookup"><span data-stu-id="146d1-3019">National ID Card</span></span>
- <span data-ttu-id="146d1-3020">CC</span><span class="sxs-lookup"><span data-stu-id="146d1-3020">CC</span></span>
- <span data-ttu-id="146d1-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="146d1-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="146d1-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="146d1-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="146d1-3023">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3024">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3024">Format</span></span>

<span data-ttu-id="146d1-3025">10 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3026">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3026">Pattern</span></span>

<span data-ttu-id="146d1-3027">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3028">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3028">Checksum</span></span>

<span data-ttu-id="146d1-3029">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3030">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3030">Definition</span></span>

<span data-ttu-id="146d1-3031">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3032">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3033">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3034">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="146d1-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="146d1-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="146d1-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="146d1-3036">Identification Card</span></span> 
- <span data-ttu-id="146d1-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="146d1-3037">I card number</span></span> 
- <span data-ttu-id="146d1-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="146d1-3038">ID number</span></span> 
- <span data-ttu-id="146d1-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="146d1-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="146d1-3040">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="146d1-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3041">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3041">Format</span></span>

<span data-ttu-id="146d1-3042">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3043">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3043">Pattern</span></span>

- <span data-ttu-id="146d1-3044">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="146d1-3045">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-3046">七个数字 </span><span class="sxs-lookup"><span data-stu-id="146d1-3046">Seven digits</span></span> 
- <span data-ttu-id="146d1-3047">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3048">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3048">Checksum</span></span>

<span data-ttu-id="146d1-3049">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3050">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3050">Definition</span></span>

<span data-ttu-id="146d1-3051">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3052">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3053">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="146d1-3054">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3054">The checksum passes.</span></span>

<span data-ttu-id="146d1-3055">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3056">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3057">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3057">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3058">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="146d1-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="146d1-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="146d1-3060">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="146d1-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="146d1-3061">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3061">Identity Card Number</span></span> 
- <span data-ttu-id="146d1-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="146d1-3062">NRIC</span></span> 
- <span data-ttu-id="146d1-3063">IC</span><span class="sxs-lookup"><span data-stu-id="146d1-3063">IC</span></span> 
- <span data-ttu-id="146d1-3064">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="146d1-3065">FIN</span><span class="sxs-lookup"><span data-stu-id="146d1-3065">FIN</span></span> 
- <span data-ttu-id="146d1-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="146d1-3066">身份证</span></span> 
- <span data-ttu-id="146d1-3067">證</span><span class="sxs-lookup"><span data-stu-id="146d1-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="146d1-3068">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="146d1-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3069">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3069">Format</span></span>

<span data-ttu-id="146d1-3070">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="146d1-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3071">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3071">Pattern</span></span>

<span data-ttu-id="146d1-3072">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3072">13 digits:</span></span>
- <span data-ttu-id="146d1-3073">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="146d1-3074">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3074">Four digits</span></span> 
- <span data-ttu-id="146d1-3075">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="146d1-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="146d1-3076">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="146d1-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="146d1-3077">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="146d1-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3078">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3078">Checksum</span></span>

<span data-ttu-id="146d1-3079">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3080">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3080">Definition</span></span>

<span data-ttu-id="146d1-3081">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3082">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3083">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="146d1-3084">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3085">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="146d1-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="146d1-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="146d1-3087">Identity card</span><span class="sxs-lookup"><span data-stu-id="146d1-3087">Identity card</span></span>
- <span data-ttu-id="146d1-3088">ID</span><span class="sxs-lookup"><span data-stu-id="146d1-3088">ID</span></span>
- <span data-ttu-id="146d1-3089">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="146d1-3090">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3091">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3091">Format</span></span>

<span data-ttu-id="146d1-3092">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="146d1-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3093">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3093">Pattern</span></span>

<span data-ttu-id="146d1-3094">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3094">13 digits:</span></span>
- <span data-ttu-id="146d1-3095">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="146d1-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="146d1-3096">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="146d1-3096">A hyphen</span></span> 
- <span data-ttu-id="146d1-3097">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="146d1-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="146d1-3098">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="146d1-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="146d1-3099">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="146d1-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="146d1-3100">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="146d1-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3101">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3101">Checksum</span></span>

<span data-ttu-id="146d1-3102">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3103">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3103">Definition</span></span>

<span data-ttu-id="146d1-3104">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3105">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3106">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="146d1-3107">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3107">The checksum passes.</span></span>

<span data-ttu-id="146d1-3108">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3109">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3110">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3110">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3111">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="146d1-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="146d1-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="146d1-3113">National ID card</span><span class="sxs-lookup"><span data-stu-id="146d1-3113">National ID card</span></span> 
- <span data-ttu-id="146d1-3114">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="146d1-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="146d1-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="146d1-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="146d1-3116">RRN</span></span> 
- <span data-ttu-id="146d1-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="146d1-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="146d1-3118">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="146d1-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3119">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3119">Format</span></span>

<span data-ttu-id="146d1-3120">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3121">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3121">Pattern</span></span>

<span data-ttu-id="146d1-3122">11-12 位数：</span><span class="sxs-lookup"><span data-stu-id="146d1-3122">11-12 digits:</span></span>
- <span data-ttu-id="146d1-3123">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3123">Two digits</span></span> 
- <span data-ttu-id="146d1-3124">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="146d1-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="146d1-3125">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3125">7-8 digits</span></span> 
- <span data-ttu-id="146d1-3126">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="146d1-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="146d1-3127">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3128">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3128">Checksum</span></span>

<span data-ttu-id="146d1-3129">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3130">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3130">Definition</span></span>

<span data-ttu-id="146d1-3131">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3132">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3133">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3134">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3134">Keywords</span></span>

<span data-ttu-id="146d1-3135">无</span><span class="sxs-lookup"><span data-stu-id="146d1-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="146d1-3136">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="146d1-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3137">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3137">Format</span></span>

<span data-ttu-id="146d1-3138">字符串 "User Id"、"User ID"、"uid" 或 "UserId"，后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="146d1-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3139">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3139">Pattern</span></span>

- <span data-ttu-id="146d1-3140">字符串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="146d1-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="146d1-3141">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="146d1-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="146d1-3142">字符串 "Password" 或 "pwd"，其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="146d1-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="146d1-3143">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-3143">An equal sign (=)</span></span>
- <span data-ttu-id="146d1-3144">任何不是美元符号（$）、百分比符号（%）、大于号（>）、符号（@）、引号（"）、分号（;)、左大括号（[）或左中括号（{）的字符</span><span class="sxs-lookup"><span data-stu-id="146d1-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="146d1-3145">7-128 个字符的任意组合，不是分号（;)、正斜杠（/）或引号（"）</span><span class="sxs-lookup"><span data-stu-id="146d1-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="146d1-3146">一个分号（;)或引号（"）</span><span class="sxs-lookup"><span data-stu-id="146d1-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3147">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3147">Checksum</span></span>

<span data-ttu-id="146d1-3148">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3149">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3149">Definition</span></span>

<span data-ttu-id="146d1-3150">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3151">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3152">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="146d1-3153">正则表达式**CEP_PasswordPlaceHolder 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3154">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3155">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="146d1-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="146d1-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="146d1-3157">部分密码</span><span class="sxs-lookup"><span data-stu-id="146d1-3157">some-password</span></span>
- <span data-ttu-id="146d1-3158">somepassword</span><span class="sxs-lookup"><span data-stu-id="146d1-3158">somepassword</span></span>
- <span data-ttu-id="146d1-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="146d1-3159">secretPassword</span></span>
- <span data-ttu-id="146d1-3160">采用</span><span class="sxs-lookup"><span data-stu-id="146d1-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="146d1-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="146d1-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="146d1-3162">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-3163">密码或密码后跟0-2 个空格、一个等号（=）、0-2 个空格和一个星号（\*）--或--</span><span class="sxs-lookup"><span data-stu-id="146d1-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="146d1-3164">密码或密码后跟：</span><span class="sxs-lookup"><span data-stu-id="146d1-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="146d1-3165">等号（=）</span><span class="sxs-lookup"><span data-stu-id="146d1-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="146d1-3166">小于号（<）</span><span class="sxs-lookup"><span data-stu-id="146d1-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="146d1-3167">1-200 个字符的任意组合，这些字符为大写或小写字母、数字、星号（\*）、连字符（-）、下划线（_）或空白字符</span><span class="sxs-lookup"><span data-stu-id="146d1-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="146d1-3168">大于号（>）</span><span class="sxs-lookup"><span data-stu-id="146d1-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="146d1-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="146d1-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="146d1-3170">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="146d1-3171">尚未</span><span class="sxs-lookup"><span data-stu-id="146d1-3171">contoso</span></span>
- <span data-ttu-id="146d1-3172">送交</span><span class="sxs-lookup"><span data-stu-id="146d1-3172">fabrikam</span></span>
- <span data-ttu-id="146d1-3173">罗斯</span><span class="sxs-lookup"><span data-stu-id="146d1-3173">northwind</span></span>
- <span data-ttu-id="146d1-3174">沙盒</span><span class="sxs-lookup"><span data-stu-id="146d1-3174">sandbox</span></span>
- <span data-ttu-id="146d1-3175">onebox</span><span class="sxs-lookup"><span data-stu-id="146d1-3175">onebox</span></span>
- <span data-ttu-id="146d1-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="146d1-3176">localhost</span></span>
- <span data-ttu-id="146d1-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="146d1-3177">127.0.0.1</span></span>
- <span data-ttu-id="146d1-3178">testacs.</span><span class="sxs-lookup"><span data-stu-id="146d1-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-3179">com</span><span class="sxs-lookup"><span data-stu-id="146d1-3179">com</span></span>
- <span data-ttu-id="146d1-3180">s-int。</span><span class="sxs-lookup"><span data-stu-id="146d1-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="146d1-3181">netmeeting</span><span class="sxs-lookup"><span data-stu-id="146d1-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="146d1-3182">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3183">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3183">Format</span></span>

<span data-ttu-id="146d1-3184">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="146d1-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3185">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3185">Pattern</span></span>

<span data-ttu-id="146d1-3186">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="146d1-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="146d1-3187">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="146d1-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="146d1-3188">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="146d1-3189">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="146d1-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="146d1-3190">四个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3191">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3191">Checksum</span></span>

<span data-ttu-id="146d1-3192">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3193">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3193">Definition</span></span>

<span data-ttu-id="146d1-3194">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3195">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3196">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3197">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3197">Keywords</span></span>

<span data-ttu-id="146d1-3198">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="146d1-3199">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3200">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3200">Format</span></span>

<span data-ttu-id="146d1-3201">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3202">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3202">Pattern</span></span>

<span data-ttu-id="146d1-3203">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3204">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3204">Checksum</span></span>

<span data-ttu-id="146d1-3205">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3206">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3206">Definition</span></span>

<span data-ttu-id="146d1-3207">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3208">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3209">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-3209">One of the following is true:</span></span>
    - <span data-ttu-id="146d1-3210">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="146d1-3211">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3211">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3212">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="146d1-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="146d1-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="146d1-3214">visa requirements</span></span> 
- <span data-ttu-id="146d1-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="146d1-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="146d1-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="146d1-3216">Schengen visas</span></span> 
- <span data-ttu-id="146d1-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="146d1-3217">Schengen visa</span></span> 
- <span data-ttu-id="146d1-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="146d1-3218">Visa Processing</span></span> 
- <span data-ttu-id="146d1-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="146d1-3219">Visa Type</span></span> 
- <span data-ttu-id="146d1-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="146d1-3220">Single Entry</span></span> 
- <span data-ttu-id="146d1-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="146d1-3221">Multiple Entry</span></span> 
- <span data-ttu-id="146d1-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="146d1-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="146d1-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-3223">Keyword_passport</span></span>

- <span data-ttu-id="146d1-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3224">Passport Number</span></span> 
- <span data-ttu-id="146d1-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="146d1-3225">Passport No</span></span> 
- <span data-ttu-id="146d1-3226">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-3226">Passport #</span></span> 
- <span data-ttu-id="146d1-3227">登记卡#</span><span class="sxs-lookup"><span data-stu-id="146d1-3227">Passport#</span></span> 
- <span data-ttu-id="146d1-3228">PassportID</span><span class="sxs-lookup"><span data-stu-id="146d1-3228">PassportID</span></span> 
- <span data-ttu-id="146d1-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="146d1-3229">Passportno</span></span> 
- <span data-ttu-id="146d1-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-3230">passportnumber</span></span> 
- <span data-ttu-id="146d1-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-3231">パスポート</span></span> 
- <span data-ttu-id="146d1-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-3232">パスポート番号</span></span> 
- <span data-ttu-id="146d1-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-3233">パスポートのNum</span></span> 
- <span data-ttu-id="146d1-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="146d1-3234">パスポート＃</span></span> 
- <span data-ttu-id="146d1-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="146d1-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="146d1-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="146d1-3236">Passeport n °</span></span> 
- <span data-ttu-id="146d1-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="146d1-3237">Passeport Non</span></span> 
- <span data-ttu-id="146d1-3238">Passeport #</span><span class="sxs-lookup"><span data-stu-id="146d1-3238">Passeport #</span></span> 
- <span data-ttu-id="146d1-3239">Passeport#</span><span class="sxs-lookup"><span data-stu-id="146d1-3239">Passeport#</span></span> 
- <span data-ttu-id="146d1-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="146d1-3240">PasseportNon</span></span> 
- <span data-ttu-id="146d1-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="146d1-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="146d1-3242">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="146d1-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3243">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3243">Format</span></span>

<span data-ttu-id="146d1-3244">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3245">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3245">Pattern</span></span>

<span data-ttu-id="146d1-3246">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="146d1-3247">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-3248">可选空格</span><span class="sxs-lookup"><span data-stu-id="146d1-3248">An optional space</span></span> 
- <span data-ttu-id="146d1-3249">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="146d1-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="146d1-3250">可选空格</span><span class="sxs-lookup"><span data-stu-id="146d1-3250">An optional space</span></span> 
- <span data-ttu-id="146d1-3251">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="146d1-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3252">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3252">Checksum</span></span>

<span data-ttu-id="146d1-3253">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3254">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3254">Definition</span></span>

<span data-ttu-id="146d1-3255">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3256">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3257">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3258">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="146d1-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="146d1-3259">Keyword_swift</span></span>

- <span data-ttu-id="146d1-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="146d1-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="146d1-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="146d1-3261">iso 9362</span></span> 
- <span data-ttu-id="146d1-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="146d1-3262">iso9362</span></span> 
- <span data-ttu-id="146d1-3263">反应\#</span><span class="sxs-lookup"><span data-stu-id="146d1-3263">swift\#</span></span> 
- <span data-ttu-id="146d1-3264">swiftcode</span><span class="sxs-lookup"><span data-stu-id="146d1-3264">swiftcode</span></span> 
- <span data-ttu-id="146d1-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-3265">swiftnumber</span></span> 
- <span data-ttu-id="146d1-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="146d1-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="146d1-3267">swift code</span></span> 
- <span data-ttu-id="146d1-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="146d1-3268">swift number #</span></span> 
- <span data-ttu-id="146d1-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="146d1-3269">swift routing number</span></span> 
- <span data-ttu-id="146d1-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="146d1-3270">bic number</span></span> 
- <span data-ttu-id="146d1-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="146d1-3271">bic code</span></span> 
- <span data-ttu-id="146d1-3272">numéro\#</span><span class="sxs-lookup"><span data-stu-id="146d1-3272">bic \#</span></span> 
- <span data-ttu-id="146d1-3273">numéro\#</span><span class="sxs-lookup"><span data-stu-id="146d1-3273">bic\#</span></span> 
- <span data-ttu-id="146d1-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="146d1-3274">bank identifier code</span></span> 
- <span data-ttu-id="146d1-3275">標準化9362</span><span class="sxs-lookup"><span data-stu-id="146d1-3275">標準化9362</span></span> 
- <span data-ttu-id="146d1-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="146d1-3276">迅速＃</span></span> 
- <span data-ttu-id="146d1-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="146d1-3277">SWIFTコード</span></span> 
- <span data-ttu-id="146d1-3278">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="146d1-3278">SWIFT番号</span></span> 
- <span data-ttu-id="146d1-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="146d1-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="146d1-3280">BIC番号</span><span class="sxs-lookup"><span data-stu-id="146d1-3280">BIC番号</span></span> 
- <span data-ttu-id="146d1-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="146d1-3281">BICコード</span></span> 
- <span data-ttu-id="146d1-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="146d1-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="146d1-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="146d1-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="146d1-3284">rapide\#</span><span class="sxs-lookup"><span data-stu-id="146d1-3284">rapide \#</span></span> 
- <span data-ttu-id="146d1-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="146d1-3285">code SWIFT</span></span> 
- <span data-ttu-id="146d1-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="146d1-3286">le numéro de swift</span></span> 
- <span data-ttu-id="146d1-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="146d1-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="146d1-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="146d1-3288">le numéro BIC</span></span> 
- <span data-ttu-id="146d1-3289">\#NUMÉRO</span><span class="sxs-lookup"><span data-stu-id="146d1-3289">\# BIC</span></span> 
- <span data-ttu-id="146d1-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="146d1-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="146d1-3291">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="146d1-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3292">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3292">Format</span></span>

<span data-ttu-id="146d1-3293">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3294">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3294">Pattern</span></span>

<span data-ttu-id="146d1-3295">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="146d1-3296">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="146d1-3297">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="146d1-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="146d1-3298">八位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3299">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3299">Checksum</span></span>

<span data-ttu-id="146d1-3300">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3301">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3301">Definition</span></span>

<span data-ttu-id="146d1-3302">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3303">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3304">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="146d1-3305">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3306">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="146d1-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="146d1-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="146d1-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="146d1-3308">身份證字號</span></span> 
- <span data-ttu-id="146d1-3309">證</span><span class="sxs-lookup"><span data-stu-id="146d1-3309">身份證</span></span> 
- <span data-ttu-id="146d1-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="146d1-3310">身份證號碼</span></span> 
- <span data-ttu-id="146d1-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="146d1-3311">身份證號</span></span> 
- <span data-ttu-id="146d1-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="146d1-3312">身分證字號</span></span> 
- <span data-ttu-id="146d1-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="146d1-3313">身分證</span></span> 
- <span data-ttu-id="146d1-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="146d1-3314">身分證號碼</span></span> 
- <span data-ttu-id="146d1-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="146d1-3315">身份證號</span></span> 
- <span data-ttu-id="146d1-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="146d1-3316">身分證統一編號</span></span> 
- <span data-ttu-id="146d1-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="146d1-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="146d1-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="146d1-3318">簽名</span></span> 
- <span data-ttu-id="146d1-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="146d1-3319">蓋章</span></span> 
- <span data-ttu-id="146d1-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="146d1-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="146d1-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="146d1-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="146d1-3322">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3323">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3323">Format</span></span>

- <span data-ttu-id="146d1-3324">生物识别护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="146d1-3325">不带生物的护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3326">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3326">Pattern</span></span>
<span data-ttu-id="146d1-3327">生物识别护照号码：</span><span class="sxs-lookup"><span data-stu-id="146d1-3327">Biometric passport number:</span></span>
- <span data-ttu-id="146d1-3328">数字“3” </span><span class="sxs-lookup"><span data-stu-id="146d1-3328">The digit "3"</span></span> 
- <span data-ttu-id="146d1-3329">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3329">Eight digits</span></span>

<span data-ttu-id="146d1-3330">不带生物的护照号码：</span><span class="sxs-lookup"><span data-stu-id="146d1-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="146d1-3331">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3332">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3332">Checksum</span></span>

<span data-ttu-id="146d1-3333">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3334">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3334">Definition</span></span>

<span data-ttu-id="146d1-3335">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3336">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3337">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3338">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="146d1-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="146d1-3340">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="146d1-3340">ROC passport number</span></span> 
- <span data-ttu-id="146d1-3341">Passport number</span><span class="sxs-lookup"><span data-stu-id="146d1-3341">Passport number</span></span> 
- <span data-ttu-id="146d1-3342">Passport no</span><span class="sxs-lookup"><span data-stu-id="146d1-3342">Passport no</span></span> 
- <span data-ttu-id="146d1-3343">Passport Num</span><span class="sxs-lookup"><span data-stu-id="146d1-3343">Passport Num</span></span> 
- <span data-ttu-id="146d1-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-3344">Passport #</span></span> 
- <span data-ttu-id="146d1-3345">护照</span><span class="sxs-lookup"><span data-stu-id="146d1-3345">护照</span></span> 
- <span data-ttu-id="146d1-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="146d1-3346">中華民國護照</span></span> 
- <span data-ttu-id="146d1-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="146d1-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="146d1-3348">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3349">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3349">Format</span></span>

<span data-ttu-id="146d1-3350">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="146d1-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3351">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3351">Pattern</span></span>

<span data-ttu-id="146d1-3352">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3352">10 letters and digits:</span></span>
- <span data-ttu-id="146d1-3353">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="146d1-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="146d1-3354">八个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3355">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3355">Checksum</span></span>

<span data-ttu-id="146d1-3356">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3357">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3357">Definition</span></span>

<span data-ttu-id="146d1-3358">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3359">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3360">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3361">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="146d1-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="146d1-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="146d1-3363">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="146d1-3363">Resident Certificate</span></span> 
- <span data-ttu-id="146d1-3364">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="146d1-3364">Resident Cert</span></span> 
- <span data-ttu-id="146d1-3365">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="146d1-3365">Resident Cert.</span></span> 
- <span data-ttu-id="146d1-3366">Identification card</span><span class="sxs-lookup"><span data-stu-id="146d1-3366">Identification card</span></span> 
- <span data-ttu-id="146d1-3367">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="146d1-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="146d1-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="146d1-3368">ARC</span></span> 
- <span data-ttu-id="146d1-3369">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="146d1-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="146d1-3370">TARC</span><span class="sxs-lookup"><span data-stu-id="146d1-3370">TARC</span></span> 
- <span data-ttu-id="146d1-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="146d1-3371">居留證</span></span> 
- <span data-ttu-id="146d1-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="146d1-3372">外僑居留證</span></span> 
- <span data-ttu-id="146d1-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="146d1-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="146d1-3374">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="146d1-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3375">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3375">Format</span></span>

<span data-ttu-id="146d1-3376">13 位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3377">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3377">Pattern</span></span>

<span data-ttu-id="146d1-3378">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3378">13 digits:</span></span>
- <span data-ttu-id="146d1-3379">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="146d1-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="146d1-3380">12 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3381">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3381">Checksum</span></span>

<span data-ttu-id="146d1-3382">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3383">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3383">Definition</span></span>

<span data-ttu-id="146d1-3384">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3385">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3386">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="146d1-3387">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3388">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3389">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="146d1-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="146d1-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="146d1-3391">ID Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3391">ID Number</span></span>
- <span data-ttu-id="146d1-3392">标识号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3392">Identification Number</span></span>
- <span data-ttu-id="146d1-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="146d1-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="146d1-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="146d1-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="146d1-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="146d1-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="146d1-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="146d1-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="146d1-3397">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3398">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3398">Format</span></span>

<span data-ttu-id="146d1-3399">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3400">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3400">Pattern</span></span>

<span data-ttu-id="146d1-3401">11 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3402">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3402">Checksum</span></span>

<span data-ttu-id="146d1-3403">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3404">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3404">Definition</span></span>

<span data-ttu-id="146d1-3405">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3406">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3407">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="146d1-3408">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3409">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3410">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="146d1-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="146d1-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="146d1-3412">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="146d1-3412">TC Kimlik No</span></span>
- <span data-ttu-id="146d1-3413">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="146d1-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="146d1-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="146d1-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="146d1-3415">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="146d1-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="146d1-p142">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3418">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3418">Format</span></span>

<span data-ttu-id="146d1-3419">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="146d1-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3420">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3420">Pattern</span></span>

<span data-ttu-id="146d1-3421">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3421">18 letters and digits:</span></span>
- <span data-ttu-id="146d1-3422">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="146d1-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="146d1-3423">一位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3423">One digit</span></span> 
- <span data-ttu-id="146d1-3424">MMDDY 的日期格式的五个数字（如果驱动程序是女，第七个字符增加50，即51到62而不是01到12）</span><span class="sxs-lookup"><span data-stu-id="146d1-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="146d1-3425">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="146d1-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="146d1-3426">五位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3427">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3427">Checksum</span></span>

<span data-ttu-id="146d1-3428">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3429">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3429">Definition</span></span>

<span data-ttu-id="146d1-3430">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3431">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3432">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="146d1-3433">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3434">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="146d1-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="146d1-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="146d1-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="146d1-3436">DVLA</span></span> 
- <span data-ttu-id="146d1-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="146d1-3437">light vans</span></span> 
- <span data-ttu-id="146d1-3438">quadbikes</span><span class="sxs-lookup"><span data-stu-id="146d1-3438">quadbikes</span></span> 
- <span data-ttu-id="146d1-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="146d1-3439">motor cars</span></span> 
- <span data-ttu-id="146d1-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="146d1-3440">125cc</span></span> 
- <span data-ttu-id="146d1-3441">sidecar</span><span class="sxs-lookup"><span data-stu-id="146d1-3441">sidecar</span></span> 
- <span data-ttu-id="146d1-3442">tricycles</span><span class="sxs-lookup"><span data-stu-id="146d1-3442">tricycles</span></span> 
- <span data-ttu-id="146d1-3443">motorcycles</span><span class="sxs-lookup"><span data-stu-id="146d1-3443">motorcycles</span></span> 
- <span data-ttu-id="146d1-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="146d1-3444">photocard licence</span></span> 
- <span data-ttu-id="146d1-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="146d1-3445">learner drivers</span></span> 
- <span data-ttu-id="146d1-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="146d1-3446">licence holder</span></span> 
- <span data-ttu-id="146d1-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="146d1-3447">licence holders</span></span> 
- <span data-ttu-id="146d1-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="146d1-3448">driving licences</span></span> 
- <span data-ttu-id="146d1-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="146d1-3449">driving licence</span></span> 
- <span data-ttu-id="146d1-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="146d1-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="146d1-p143">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="146d1-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3453">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3453">Format</span></span>

<span data-ttu-id="146d1-3454">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3455">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3455">Pattern</span></span>

<span data-ttu-id="146d1-3456">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3457">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3457">Checksum</span></span>

<span data-ttu-id="146d1-3458">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3459">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3459">Definition</span></span>

<span data-ttu-id="146d1-3460">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3461">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3462">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3462">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3463">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="146d1-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="146d1-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="146d1-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="146d1-3465">council nomination</span></span> 
- <span data-ttu-id="146d1-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="146d1-3466">nomination form</span></span> 
- <span data-ttu-id="146d1-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="146d1-3467">electoral register</span></span> 
- <span data-ttu-id="146d1-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="146d1-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="146d1-p144">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="146d1-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3471">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3471">Format</span></span>

<span data-ttu-id="146d1-3472">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="146d1-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3473">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3473">Pattern</span></span>

<span data-ttu-id="146d1-3474">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="146d1-3474">10-17 digits:</span></span>
- <span data-ttu-id="146d1-3475">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="146d1-3476">一个空格</span><span class="sxs-lookup"><span data-stu-id="146d1-3476">A space</span></span> 
- <span data-ttu-id="146d1-3477">三位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3477">Three digits</span></span> 
- <span data-ttu-id="146d1-3478">一个空格</span><span class="sxs-lookup"><span data-stu-id="146d1-3478">A space</span></span> 
- <span data-ttu-id="146d1-3479">四位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3480">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3480">Checksum</span></span>

<span data-ttu-id="146d1-3481">是</span><span class="sxs-lookup"><span data-stu-id="146d1-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3482">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3482">Definition</span></span>

<span data-ttu-id="146d1-3483">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3484">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3485">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-3485">One of the following is true:</span></span>
    - <span data-ttu-id="146d1-3486">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="146d1-3487">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="146d1-3488">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="146d1-3489">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="146d1-3489">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3490">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="146d1-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="146d1-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="146d1-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="146d1-3492">national health service</span></span> 
- <span data-ttu-id="146d1-3493">nhs</span><span class="sxs-lookup"><span data-stu-id="146d1-3493">nhs</span></span> 
- <span data-ttu-id="146d1-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="146d1-3494">health services authority</span></span> 
- <span data-ttu-id="146d1-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="146d1-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="146d1-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="146d1-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="146d1-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="146d1-3497">patient id</span></span> 
- <span data-ttu-id="146d1-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="146d1-3498">patient identification</span></span> 
- <span data-ttu-id="146d1-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="146d1-3499">patient no</span></span> 
- <span data-ttu-id="146d1-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="146d1-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="146d1-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="146d1-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="146d1-3502">GP</span><span class="sxs-lookup"><span data-stu-id="146d1-3502">GP</span></span> 
- <span data-ttu-id="146d1-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="146d1-3503">DOB</span></span> 
- <span data-ttu-id="146d1-3504">D. B。</span><span class="sxs-lookup"><span data-stu-id="146d1-3504">D.O.B</span></span> 
- <span data-ttu-id="146d1-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="146d1-3505">Date of Birth</span></span> 
- <span data-ttu-id="146d1-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="146d1-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="146d1-p145">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="146d1-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3509">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3509">Format</span></span>

<span data-ttu-id="146d1-3510">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="146d1-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3511">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3511">Pattern</span></span>

<span data-ttu-id="146d1-3512">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="146d1-3512">Two possible patterns:</span></span>

- <span data-ttu-id="146d1-3513">两个字母（有效 NINOs 仅使用此前缀中的特定字符，此格式将对此进行验证; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="146d1-3514">六位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3514">Six digits</span></span>
- <span data-ttu-id="146d1-3515">"A"、"B"、"C" 或 "d" （与前缀一样，后缀中只允许有某些字符; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="146d1-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="146d1-3516">OR</span><span class="sxs-lookup"><span data-stu-id="146d1-3516">OR</span></span>

- <span data-ttu-id="146d1-3517">两个字母</span><span class="sxs-lookup"><span data-stu-id="146d1-3517">Two letters</span></span>
- <span data-ttu-id="146d1-3518">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3518">A space or dash</span></span>
- <span data-ttu-id="146d1-3519">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3519">Two digits</span></span>
- <span data-ttu-id="146d1-3520">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3520">A space or dash</span></span>
- <span data-ttu-id="146d1-3521">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3521">Two digits</span></span>
- <span data-ttu-id="146d1-3522">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3522">A space or dash</span></span>
- <span data-ttu-id="146d1-3523">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3523">Two digits</span></span>
- <span data-ttu-id="146d1-3524">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3524">A space or dash</span></span>
- <span data-ttu-id="146d1-3525">要么是 "A"、"B"、"C"，要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="146d1-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3526">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3526">Checksum</span></span>

<span data-ttu-id="146d1-3527">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3528">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3528">Definition</span></span>

<span data-ttu-id="146d1-3529">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3530">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3531">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="146d1-3532">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3533">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3534">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3534">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3535">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="146d1-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="146d1-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="146d1-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="146d1-3537">national insurance number</span></span> 
- <span data-ttu-id="146d1-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="146d1-3538">national insurance contributions</span></span> 
- <span data-ttu-id="146d1-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="146d1-3539">protection act</span></span> 
- <span data-ttu-id="146d1-3540">方面</span><span class="sxs-lookup"><span data-stu-id="146d1-3540">insurance</span></span> 
- <span data-ttu-id="146d1-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="146d1-3541">social security number</span></span> 
- <span data-ttu-id="146d1-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="146d1-3542">insurance application</span></span> 
- <span data-ttu-id="146d1-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="146d1-3543">medical application</span></span> 
- <span data-ttu-id="146d1-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="146d1-3544">social insurance</span></span> 
- <span data-ttu-id="146d1-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="146d1-3545">medical attention</span></span> 
- <span data-ttu-id="146d1-3546">social security</span><span class="sxs-lookup"><span data-stu-id="146d1-3546">social security</span></span> 
- <span data-ttu-id="146d1-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="146d1-3547">great britain</span></span> 
- <span data-ttu-id="146d1-3548">方面</span><span class="sxs-lookup"><span data-stu-id="146d1-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="146d1-p146">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="146d1-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3551">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3551">Format</span></span>

<span data-ttu-id="146d1-3552">九个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3553">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3553">Pattern</span></span>

<span data-ttu-id="146d1-3554">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3555">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3555">Checksum</span></span>

<span data-ttu-id="146d1-3556">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3557">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3557">Definition</span></span>

<span data-ttu-id="146d1-3558">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3559">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3560">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3561">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="146d1-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="146d1-3562">Keyword_passport</span></span>

- <span data-ttu-id="146d1-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3563">Passport Number</span></span> 
- <span data-ttu-id="146d1-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="146d1-3564">Passport No</span></span> 
- <span data-ttu-id="146d1-3565">Passport #</span><span class="sxs-lookup"><span data-stu-id="146d1-3565">Passport #</span></span> 
- <span data-ttu-id="146d1-3566">登记卡#</span><span class="sxs-lookup"><span data-stu-id="146d1-3566">Passport#</span></span> 
- <span data-ttu-id="146d1-3567">PassportID</span><span class="sxs-lookup"><span data-stu-id="146d1-3567">PassportID</span></span> 
- <span data-ttu-id="146d1-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="146d1-3568">Passportno</span></span> 
- <span data-ttu-id="146d1-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="146d1-3569">passportnumber</span></span> 
- <span data-ttu-id="146d1-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="146d1-3570">パスポート</span></span> 
- <span data-ttu-id="146d1-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="146d1-3571">パスポート番号</span></span> 
- <span data-ttu-id="146d1-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="146d1-3572">パスポートのNum</span></span> 
- <span data-ttu-id="146d1-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="146d1-3573">パスポート＃</span></span> 
- <span data-ttu-id="146d1-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="146d1-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="146d1-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="146d1-3575">Passeport n °</span></span> 
- <span data-ttu-id="146d1-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="146d1-3576">Passeport Non</span></span> 
- <span data-ttu-id="146d1-3577">Passeport #</span><span class="sxs-lookup"><span data-stu-id="146d1-3577">Passeport #</span></span> 
- <span data-ttu-id="146d1-3578">Passeport#</span><span class="sxs-lookup"><span data-stu-id="146d1-3578">Passeport#</span></span> 
- <span data-ttu-id="146d1-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="146d1-3579">PasseportNon</span></span> 
- <span data-ttu-id="146d1-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="146d1-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="146d1-3581">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="146d1-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3582">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3582">Format</span></span>

<span data-ttu-id="146d1-3583">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3584">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3584">Pattern</span></span>

<span data-ttu-id="146d1-3585">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3586">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3586">Checksum</span></span>

<span data-ttu-id="146d1-3587">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3588">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3588">Definition</span></span>

<span data-ttu-id="146d1-3589">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3590">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3591">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3592">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="146d1-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="146d1-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="146d1-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3594">Checking Account Number</span></span> 
- <span data-ttu-id="146d1-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="146d1-3595">Checking Account</span></span> 
- <span data-ttu-id="146d1-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-3596">Checking Account #</span></span> 
- <span data-ttu-id="146d1-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="146d1-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-3598">Checking Acct #</span></span> 
- <span data-ttu-id="146d1-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="146d1-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3600">Checking Account No.</span></span> 
- <span data-ttu-id="146d1-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3601">Bank Account Number</span></span> 
- <span data-ttu-id="146d1-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-3602">Bank Account #</span></span> 
- <span data-ttu-id="146d1-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="146d1-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-3604">Bank Acct #</span></span> 
- <span data-ttu-id="146d1-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="146d1-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3606">Bank Account No.</span></span> 
- <span data-ttu-id="146d1-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3607">Savings Account Number</span></span> 
- <span data-ttu-id="146d1-3608">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="146d1-3608">Savings Account.</span></span> 
- <span data-ttu-id="146d1-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-3609">Savings Account #</span></span> 
- <span data-ttu-id="146d1-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="146d1-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-3611">Savings Acct #</span></span> 
- <span data-ttu-id="146d1-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="146d1-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3613">Savings Account No.</span></span> 
- <span data-ttu-id="146d1-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3614">Debit Account Number</span></span> 
- <span data-ttu-id="146d1-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="146d1-3615">Debit Account</span></span> 
- <span data-ttu-id="146d1-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="146d1-3616">Debit Account #</span></span> 
- <span data-ttu-id="146d1-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="146d1-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="146d1-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="146d1-3618">Debit Acct #</span></span> 
- <span data-ttu-id="146d1-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="146d1-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="146d1-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="146d1-3621">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="146d1-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3622">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3622">Format</span></span>

<span data-ttu-id="146d1-3623">取决于州</span><span class="sxs-lookup"><span data-stu-id="146d1-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3624">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3624">Pattern</span></span>

<span data-ttu-id="146d1-3625">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="146d1-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="146d1-3626">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="146d1-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="146d1-3627">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="146d1-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3628">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3628">Checksum</span></span>

<span data-ttu-id="146d1-3629">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3630">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3630">Definition</span></span>

<span data-ttu-id="146d1-3631">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3632">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3633">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="146d1-3634">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="146d1-3635">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3636">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3637">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="146d1-3638">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="146d1-3639">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3640">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="146d1-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="146d1-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="146d1-3642">通讯</span><span class="sxs-lookup"><span data-stu-id="146d1-3642">DL</span></span> 
- <span data-ttu-id="146d1-3643">DLS</span><span class="sxs-lookup"><span data-stu-id="146d1-3643">DLS</span></span> 
- <span data-ttu-id="146d1-3644">采用</span><span class="sxs-lookup"><span data-stu-id="146d1-3644">CDL</span></span> 
- <span data-ttu-id="146d1-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="146d1-3645">CDLS</span></span> 
- <span data-ttu-id="146d1-3646">ID</span><span class="sxs-lookup"><span data-stu-id="146d1-3646">ID</span></span> 
- <span data-ttu-id="146d1-3647">Id</span><span class="sxs-lookup"><span data-stu-id="146d1-3647">IDs</span></span> 
- <span data-ttu-id="146d1-3648">通讯#</span><span class="sxs-lookup"><span data-stu-id="146d1-3648">DL#</span></span> 
- <span data-ttu-id="146d1-3649">DLS#</span><span class="sxs-lookup"><span data-stu-id="146d1-3649">DLS#</span></span> 
- <span data-ttu-id="146d1-3650">采用#</span><span class="sxs-lookup"><span data-stu-id="146d1-3650">CDL#</span></span> 
- <span data-ttu-id="146d1-3651">CDLS#</span><span class="sxs-lookup"><span data-stu-id="146d1-3651">CDLS#</span></span> 
- <span data-ttu-id="146d1-3652">号#</span><span class="sxs-lookup"><span data-stu-id="146d1-3652">ID#</span></span>
- <span data-ttu-id="146d1-3653">Id#</span><span class="sxs-lookup"><span data-stu-id="146d1-3653">IDs#</span></span> 
- <span data-ttu-id="146d1-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="146d1-3654">ID number</span></span> 
- <span data-ttu-id="146d1-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-3655">ID numbers</span></span> 
- <span data-ttu-id="146d1-3656">.LIC</span><span class="sxs-lookup"><span data-stu-id="146d1-3656">LIC</span></span> 
- <span data-ttu-id="146d1-3657">.LIC#</span><span class="sxs-lookup"><span data-stu-id="146d1-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="146d1-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="146d1-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="146d1-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="146d1-3659">DriverLic</span></span> 
- <span data-ttu-id="146d1-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="146d1-3660">DriverLics</span></span> 
- <span data-ttu-id="146d1-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-3661">DriverLicense</span></span> 
- <span data-ttu-id="146d1-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3662">DriverLicenses</span></span> 
- <span data-ttu-id="146d1-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-3663">Driver Lic</span></span> 
- <span data-ttu-id="146d1-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-3664">Driver Lics</span></span> 
- <span data-ttu-id="146d1-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="146d1-3665">Driver License</span></span> 
- <span data-ttu-id="146d1-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3666">Driver Licenses</span></span> 
- <span data-ttu-id="146d1-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="146d1-3667">DriversLic</span></span> 
- <span data-ttu-id="146d1-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="146d1-3668">DriversLics</span></span> 
- <span data-ttu-id="146d1-3669">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-3669">DriversLicense</span></span> 
- <span data-ttu-id="146d1-3670">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3670">DriversLicenses</span></span> 
- <span data-ttu-id="146d1-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-3671">Drivers Lic</span></span> 
- <span data-ttu-id="146d1-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-3672">Drivers Lics</span></span> 
- <span data-ttu-id="146d1-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="146d1-3673">Drivers License</span></span> 
- <span data-ttu-id="146d1-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="146d1-3675">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-3675">Driver'Lic</span></span> 
- <span data-ttu-id="146d1-3676">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-3676">Driver'Lics</span></span> 
- <span data-ttu-id="146d1-3677">Driver'License</span><span class="sxs-lookup"><span data-stu-id="146d1-3677">Driver'License</span></span> 
- <span data-ttu-id="146d1-3678">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="146d1-3679">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-3679">Driver' Lic</span></span> 
- <span data-ttu-id="146d1-3680">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-3680">Driver' Lics</span></span> 
- <span data-ttu-id="146d1-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="146d1-3681">Driver' License</span></span> 
- <span data-ttu-id="146d1-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3682">Driver' Licenses</span></span>
- <span data-ttu-id="146d1-3683">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="146d1-3683">Driver'sLic</span></span> 
- <span data-ttu-id="146d1-3684">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="146d1-3684">Driver'sLics</span></span> 
- <span data-ttu-id="146d1-3685">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="146d1-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="146d1-3686">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="146d1-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="146d1-3687">Driver's Lic</span></span> 
- <span data-ttu-id="146d1-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="146d1-3688">Driver's Lics</span></span> 
- <span data-ttu-id="146d1-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="146d1-3689">Driver's License</span></span> 
- <span data-ttu-id="146d1-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="146d1-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="146d1-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="146d1-3691">identification number</span></span> 
- <span data-ttu-id="146d1-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="146d1-3692">identification numbers</span></span> 
- <span data-ttu-id="146d1-3693">identification #</span><span class="sxs-lookup"><span data-stu-id="146d1-3693">identification #</span></span> 
- <span data-ttu-id="146d1-3694">id card</span><span class="sxs-lookup"><span data-stu-id="146d1-3694">id card</span></span> 
- <span data-ttu-id="146d1-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="146d1-3695">id cards</span></span> 
- <span data-ttu-id="146d1-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="146d1-3696">identification card</span></span> 
- <span data-ttu-id="146d1-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="146d1-3697">identification cards</span></span> 
- <span data-ttu-id="146d1-3698">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3698">DriverLic#</span></span> 
- <span data-ttu-id="146d1-3699">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3699">DriverLics#</span></span> 
- <span data-ttu-id="146d1-3700">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-3700">DriverLicense#</span></span> 
- <span data-ttu-id="146d1-3701">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="146d1-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3702">Driver Lic#</span></span> 
- <span data-ttu-id="146d1-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3703">Driver Lics#</span></span> 
- <span data-ttu-id="146d1-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="146d1-3704">Driver License#</span></span> 
- <span data-ttu-id="146d1-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="146d1-3706">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3706">DriversLic#</span></span> 
- <span data-ttu-id="146d1-3707">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3707">DriversLics#</span></span> 
- <span data-ttu-id="146d1-3708">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-3708">DriversLicense#</span></span> 
- <span data-ttu-id="146d1-3709">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="146d1-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="146d1-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="146d1-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="146d1-3712">Drivers License#</span></span> 
- <span data-ttu-id="146d1-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="146d1-3714">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="146d1-3715">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="146d1-3716">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="146d1-3716">Driver'License#</span></span> 
- <span data-ttu-id="146d1-3717">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="146d1-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="146d1-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="146d1-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="146d1-3720">Driver' License#</span></span> 
- <span data-ttu-id="146d1-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="146d1-3722">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="146d1-3723">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="146d1-3724">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="146d1-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="146d1-3725">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="146d1-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="146d1-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="146d1-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="146d1-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="146d1-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="146d1-3728">Driver's License#</span></span> 
- <span data-ttu-id="146d1-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="146d1-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="146d1-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="146d1-3730">id card#</span></span> 
- <span data-ttu-id="146d1-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="146d1-3731">id cards#</span></span> 
- <span data-ttu-id="146d1-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="146d1-3732">identification card#</span></span> 
- <span data-ttu-id="146d1-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="146d1-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="146d1-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="146d1-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="146d1-3735">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="146d1-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="146d1-3736">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="146d1-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="146d1-3737">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="146d1-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3738">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3738">Format</span></span>

<span data-ttu-id="146d1-3739">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="146d1-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3740">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3740">Pattern</span></span>

<span data-ttu-id="146d1-3741">格式</span><span class="sxs-lookup"><span data-stu-id="146d1-3741">Formatted:</span></span>
- <span data-ttu-id="146d1-3742">数字“9”</span><span class="sxs-lookup"><span data-stu-id="146d1-3742">The digit "9"</span></span> 
- <span data-ttu-id="146d1-3743">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3743">Two digits</span></span> 
- <span data-ttu-id="146d1-3744">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3744">A space or dash</span></span> 
- <span data-ttu-id="146d1-3745">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="146d1-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="146d1-3746">一位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3746">A digit</span></span> 
- <span data-ttu-id="146d1-3747">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="146d1-3747">A space, or dash</span></span> 
- <span data-ttu-id="146d1-3748">四位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3748">Four digits</span></span>

<span data-ttu-id="146d1-3749">纯</span><span class="sxs-lookup"><span data-stu-id="146d1-3749">Unformatted:</span></span>
- <span data-ttu-id="146d1-3750">数字“9”</span><span class="sxs-lookup"><span data-stu-id="146d1-3750">The digit "9"</span></span> 
- <span data-ttu-id="146d1-3751">两位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3751">Two digits</span></span> 
- <span data-ttu-id="146d1-3752">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="146d1-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="146d1-3753">五位数字</span><span class="sxs-lookup"><span data-stu-id="146d1-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3754">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3754">Checksum</span></span>

<span data-ttu-id="146d1-3755">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="146d1-3756">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3756">Definition</span></span>

<span data-ttu-id="146d1-3757">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3758">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3759">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="146d1-3760">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="146d1-3761">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="146d1-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="146d1-3762">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="146d1-3763">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="146d1-3764">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3765">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3766">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="146d1-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="146d1-3767">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="146d1-3768">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="146d1-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="146d1-3769">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="146d1-3769">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3770">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="146d1-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="146d1-3771">Keyword_itin</span></span>

- <span data-ttu-id="146d1-3772">报税</span><span class="sxs-lookup"><span data-stu-id="146d1-3772">taxpayer</span></span> 
- <span data-ttu-id="146d1-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="146d1-3773">tax id</span></span> 
- <span data-ttu-id="146d1-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="146d1-3774">tax identification</span></span> 
- <span data-ttu-id="146d1-3775">itin</span><span class="sxs-lookup"><span data-stu-id="146d1-3775">itin</span></span> 
- <span data-ttu-id="146d1-3776">ssn</span><span class="sxs-lookup"><span data-stu-id="146d1-3776">ssn</span></span> 
- <span data-ttu-id="146d1-3777">锡</span><span class="sxs-lookup"><span data-stu-id="146d1-3777">tin</span></span> 
- <span data-ttu-id="146d1-3778">social security</span><span class="sxs-lookup"><span data-stu-id="146d1-3778">social security</span></span> 
- <span data-ttu-id="146d1-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="146d1-3779">tax payer</span></span> 
- <span data-ttu-id="146d1-3780">itins</span><span class="sxs-lookup"><span data-stu-id="146d1-3780">itins</span></span> 
- <span data-ttu-id="146d1-3781">taxid</span><span class="sxs-lookup"><span data-stu-id="146d1-3781">taxid</span></span> 
- <span data-ttu-id="146d1-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="146d1-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="146d1-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="146d1-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="146d1-3784">许可证</span><span class="sxs-lookup"><span data-stu-id="146d1-3784">License</span></span> 
- <span data-ttu-id="146d1-3785">通讯</span><span class="sxs-lookup"><span data-stu-id="146d1-3785">DL</span></span> 
- <span data-ttu-id="146d1-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="146d1-3786">DOB</span></span> 
- <span data-ttu-id="146d1-3787">出生日期</span><span class="sxs-lookup"><span data-stu-id="146d1-3787">Birthdate</span></span> 
- <span data-ttu-id="146d1-3788">一定</span><span class="sxs-lookup"><span data-stu-id="146d1-3788">Birthday</span></span> 
- <span data-ttu-id="146d1-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="146d1-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="146d1-3790">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="146d1-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="146d1-3791">Format</span><span class="sxs-lookup"><span data-stu-id="146d1-3791">Format</span></span>

<span data-ttu-id="146d1-3792">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="146d1-3793">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="146d1-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="146d1-3794">模式</span><span class="sxs-lookup"><span data-stu-id="146d1-3794">Pattern</span></span>

<span data-ttu-id="146d1-3795">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="146d1-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="146d1-3796">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="146d1-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="146d1-3797">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="146d1-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="146d1-3798">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="146d1-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="146d1-3799">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="146d1-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="146d1-3800">校验和</span><span class="sxs-lookup"><span data-stu-id="146d1-3800">Checksum</span></span>

<span data-ttu-id="146d1-3801">否</span><span class="sxs-lookup"><span data-stu-id="146d1-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="146d1-3802">定义</span><span class="sxs-lookup"><span data-stu-id="146d1-3802">Definition</span></span>

<span data-ttu-id="146d1-3803">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3804">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3805">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="146d1-3806">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3807">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3808">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="146d1-3809">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3810">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3811">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="146d1-3812">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="146d1-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="146d1-3813">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="146d1-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="146d1-3814">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="146d1-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="146d1-3815">关键字</span><span class="sxs-lookup"><span data-stu-id="146d1-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="146d1-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="146d1-3816">Keyword_ssn</span></span>

- <span data-ttu-id="146d1-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="146d1-3817">Social Security</span></span> 
- <span data-ttu-id="146d1-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="146d1-3818">Social Security#</span></span> 
- <span data-ttu-id="146d1-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="146d1-3819">Soc Sec</span></span> 
- <span data-ttu-id="146d1-3820">SSN</span><span class="sxs-lookup"><span data-stu-id="146d1-3820">SSN</span></span> 
- <span data-ttu-id="146d1-3821">SSN</span><span class="sxs-lookup"><span data-stu-id="146d1-3821">SSNS</span></span> 
- <span data-ttu-id="146d1-3822">SSN#</span><span class="sxs-lookup"><span data-stu-id="146d1-3822">SSN#</span></span> 
- <span data-ttu-id="146d1-3823">SS#</span><span class="sxs-lookup"><span data-stu-id="146d1-3823">SS#</span></span> 
- <span data-ttu-id="146d1-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="146d1-3824">SSID</span></span> 
   
