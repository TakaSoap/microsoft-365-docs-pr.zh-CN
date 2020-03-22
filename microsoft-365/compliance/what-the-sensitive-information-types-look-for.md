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
ms.openlocfilehash: bd74551b7e8b2d659724a1222e115a479db76ec8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894295"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="aab42-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="aab42-104">What the sensitive information types look for</span></span>

<span data-ttu-id="aab42-105">Office 365 安全&amp;合规中心中的数据丢失防护（DLP）包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="aab42-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="aab42-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="aab42-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="aab42-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="aab42-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="aab42-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="aab42-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="aab42-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="aab42-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="aab42-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-111">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-111">Format</span></span>

<span data-ttu-id="aab42-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="aab42-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-113">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-113">Pattern</span></span>

<span data-ttu-id="aab42-114">格式</span><span class="sxs-lookup"><span data-stu-id="aab42-114">Formatted:</span></span>
- <span data-ttu-id="aab42-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="aab42-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="aab42-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-116">A hyphen</span></span>
- <span data-ttu-id="aab42-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-117">Four digits</span></span>
- <span data-ttu-id="aab42-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-118">A hyphen</span></span>
- <span data-ttu-id="aab42-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-119">A digit</span></span>

<span data-ttu-id="aab42-120">无格式：9个连续的数字，以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="aab42-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="aab42-121">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-121">Checksum</span></span>

<span data-ttu-id="aab42-122">否</span><span class="sxs-lookup"><span data-stu-id="aab42-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-123">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-123">Definition</span></span>

<span data-ttu-id="aab42-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="aab42-127">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="aab42-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="aab42-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="aab42-129">aba</span><span class="sxs-lookup"><span data-stu-id="aab42-129">aba</span></span>
- <span data-ttu-id="aab42-130">aba #</span><span class="sxs-lookup"><span data-stu-id="aab42-130">aba #</span></span>
- <span data-ttu-id="aab42-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="aab42-131">aba routing #</span></span>
- <span data-ttu-id="aab42-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="aab42-132">aba routing number</span></span>
- <span data-ttu-id="aab42-133">aba#</span><span class="sxs-lookup"><span data-stu-id="aab42-133">aba#</span></span>
- <span data-ttu-id="aab42-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="aab42-134">abarouting#</span></span>
- <span data-ttu-id="aab42-135">aba number</span><span class="sxs-lookup"><span data-stu-id="aab42-135">aba number</span></span>
- <span data-ttu-id="aab42-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-136">abaroutingnumber</span></span>
- <span data-ttu-id="aab42-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="aab42-137">american bank association routing #</span></span>
- <span data-ttu-id="aab42-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="aab42-138">american bank association routing number</span></span>
- <span data-ttu-id="aab42-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="aab42-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="aab42-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="aab42-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="aab42-141">bank routing number</span></span>
- <span data-ttu-id="aab42-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="aab42-142">bankrouting#</span></span>
- <span data-ttu-id="aab42-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-143">bankroutingnumber</span></span>
- <span data-ttu-id="aab42-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="aab42-144">routing transit number</span></span>
- <span data-ttu-id="aab42-145">RTN</span><span class="sxs-lookup"><span data-stu-id="aab42-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="aab42-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="aab42-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-147">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-147">Format</span></span>

<span data-ttu-id="aab42-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="aab42-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-149">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-149">Pattern</span></span>

<span data-ttu-id="aab42-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-150">Eight digits:</span></span>
- <span data-ttu-id="aab42-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-151">Two digits</span></span>
- <span data-ttu-id="aab42-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-152">A period</span></span>
- <span data-ttu-id="aab42-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-153">Three digits</span></span>
- <span data-ttu-id="aab42-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-154">A period</span></span>
- <span data-ttu-id="aab42-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-156">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-156">Checksum</span></span>

<span data-ttu-id="aab42-157">否</span><span class="sxs-lookup"><span data-stu-id="aab42-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-158">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-158">Definition</span></span>

<span data-ttu-id="aab42-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-162">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="aab42-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="aab42-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="aab42-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="aab42-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="aab42-165">标识</span><span class="sxs-lookup"><span data-stu-id="aab42-165">Identity</span></span> 
- <span data-ttu-id="aab42-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="aab42-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="aab42-167">DNI</span><span class="sxs-lookup"><span data-stu-id="aab42-167">DNI</span></span> 
- <span data-ttu-id="aab42-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="aab42-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="aab42-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="aab42-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="aab42-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="aab42-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="aab42-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="aab42-171">Identidad</span></span> 
- <span data-ttu-id="aab42-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="aab42-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="aab42-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-174">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-174">Format</span></span>

<span data-ttu-id="aab42-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="aab42-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-176">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-176">Pattern</span></span>

<span data-ttu-id="aab42-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="aab42-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="aab42-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="aab42-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="aab42-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-179">Three digits</span></span> 
- <span data-ttu-id="aab42-180">连字符</span><span class="sxs-lookup"><span data-stu-id="aab42-180">A hyphen</span></span> 
- <span data-ttu-id="aab42-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-182">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-182">Checksum</span></span>

<span data-ttu-id="aab42-183">否</span><span class="sxs-lookup"><span data-stu-id="aab42-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-184">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-184">Definition</span></span>

<span data-ttu-id="aab42-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="aab42-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="aab42-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="aab42-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="aab42-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-192">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="aab42-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="aab42-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="aab42-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="aab42-194">swift bank code</span></span>
- <span data-ttu-id="aab42-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="aab42-195">correspondent bank</span></span>
- <span data-ttu-id="aab42-196">base currency</span><span class="sxs-lookup"><span data-stu-id="aab42-196">base currency</span></span>
- <span data-ttu-id="aab42-197">usa account</span><span class="sxs-lookup"><span data-stu-id="aab42-197">usa account</span></span>
- <span data-ttu-id="aab42-198">holder address</span><span class="sxs-lookup"><span data-stu-id="aab42-198">holder address</span></span>
- <span data-ttu-id="aab42-199">bank address</span><span class="sxs-lookup"><span data-stu-id="aab42-199">bank address</span></span>
- <span data-ttu-id="aab42-200">information account</span><span class="sxs-lookup"><span data-stu-id="aab42-200">information account</span></span>
- <span data-ttu-id="aab42-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="aab42-201">fund transfers</span></span>
- <span data-ttu-id="aab42-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="aab42-202">bank charges</span></span>
- <span data-ttu-id="aab42-203">bank details</span><span class="sxs-lookup"><span data-stu-id="aab42-203">bank details</span></span>
- <span data-ttu-id="aab42-204">banking information</span><span class="sxs-lookup"><span data-stu-id="aab42-204">banking information</span></span>
- <span data-ttu-id="aab42-205">full names</span><span class="sxs-lookup"><span data-stu-id="aab42-205">full names</span></span>
- <span data-ttu-id="aab42-206">iaea</span><span class="sxs-lookup"><span data-stu-id="aab42-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="aab42-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-208">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-208">Format</span></span>

<span data-ttu-id="aab42-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="aab42-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-210">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-210">Pattern</span></span>

<span data-ttu-id="aab42-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="aab42-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-213">Two digits</span></span> 
- <span data-ttu-id="aab42-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="aab42-215">或</span><span class="sxs-lookup"><span data-stu-id="aab42-215">OR</span></span>

- <span data-ttu-id="aab42-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-217">4-9 digits</span></span>

<span data-ttu-id="aab42-218">或</span><span class="sxs-lookup"><span data-stu-id="aab42-218">OR</span></span>

- <span data-ttu-id="aab42-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-220">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-220">Checksum</span></span>

<span data-ttu-id="aab42-221">否</span><span class="sxs-lookup"><span data-stu-id="aab42-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-222">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-222">Definition</span></span>

<span data-ttu-id="aab42-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="aab42-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-227">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="aab42-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="aab42-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="aab42-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="aab42-229">international driving permits</span></span>
- <span data-ttu-id="aab42-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="aab42-230">australian automobile association</span></span>
- <span data-ttu-id="aab42-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="aab42-231">international driving permit</span></span>
- <span data-ttu-id="aab42-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-232">DriverLicence</span></span>
- <span data-ttu-id="aab42-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-233">DriverLicences</span></span>
- <span data-ttu-id="aab42-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-234">Driver Lic</span></span>
- <span data-ttu-id="aab42-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-235">Driver Licence</span></span>
- <span data-ttu-id="aab42-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-236">Driver Licences</span></span>
- <span data-ttu-id="aab42-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="aab42-237">DriversLic</span></span>
- <span data-ttu-id="aab42-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-238">DriversLicence</span></span>
- <span data-ttu-id="aab42-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-239">DriversLicences</span></span>
- <span data-ttu-id="aab42-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-240">Drivers Lic</span></span>
- <span data-ttu-id="aab42-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-241">Drivers Lics</span></span>
- <span data-ttu-id="aab42-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-242">Drivers Licence</span></span>
- <span data-ttu-id="aab42-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-243">Drivers Licences</span></span>
- <span data-ttu-id="aab42-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-244">Driver'Lic</span></span>
- <span data-ttu-id="aab42-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-245">Driver'Lics</span></span>
- <span data-ttu-id="aab42-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-246">Driver'Licence</span></span>
- <span data-ttu-id="aab42-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-247">Driver'Licences</span></span>
- <span data-ttu-id="aab42-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-248">Driver' Lic</span></span>
- <span data-ttu-id="aab42-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-249">Driver' Lics</span></span>
- <span data-ttu-id="aab42-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-250">Driver' Licence</span></span>
- <span data-ttu-id="aab42-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-251">Driver' Licences</span></span>
- <span data-ttu-id="aab42-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="aab42-252">Driver'sLic</span></span>
- <span data-ttu-id="aab42-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="aab42-253">Driver'sLics</span></span>
- <span data-ttu-id="aab42-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-254">Driver'sLicence</span></span>
- <span data-ttu-id="aab42-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-255">Driver'sLicences</span></span>
- <span data-ttu-id="aab42-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-256">Driver's Lic</span></span>
- <span data-ttu-id="aab42-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-257">Driver's Lics</span></span>
- <span data-ttu-id="aab42-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-258">Driver's Licence</span></span>
- <span data-ttu-id="aab42-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-259">Driver's Licences</span></span>
- <span data-ttu-id="aab42-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-260">DriverLic#</span></span>
- <span data-ttu-id="aab42-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-261">DriverLics#</span></span>
- <span data-ttu-id="aab42-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-262">DriverLicence#</span></span>
- <span data-ttu-id="aab42-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-263">DriverLicences#</span></span>
- <span data-ttu-id="aab42-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-264">Driver Lic#</span></span>
- <span data-ttu-id="aab42-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-265">Driver Lics#</span></span>
- <span data-ttu-id="aab42-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-266">Driver Licence#</span></span>
- <span data-ttu-id="aab42-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-267">Driver Licences#</span></span>
- <span data-ttu-id="aab42-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-268">DriversLic#</span></span>
- <span data-ttu-id="aab42-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-269">DriversLics#</span></span>
- <span data-ttu-id="aab42-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-270">DriversLicence#</span></span>
- <span data-ttu-id="aab42-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-271">DriversLicences#</span></span>
- <span data-ttu-id="aab42-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-272">Drivers Lic#</span></span>
- <span data-ttu-id="aab42-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-273">Drivers Lics#</span></span>
- <span data-ttu-id="aab42-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-274">Drivers Licence#</span></span>
- <span data-ttu-id="aab42-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-275">Drivers Licences#</span></span>
- <span data-ttu-id="aab42-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-276">Driver'Lic#</span></span>
- <span data-ttu-id="aab42-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-277">Driver'Lics#</span></span>
- <span data-ttu-id="aab42-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-278">Driver'Licence#</span></span>
- <span data-ttu-id="aab42-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-279">Driver'Licences#</span></span>
- <span data-ttu-id="aab42-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-280">Driver' Lic#</span></span>
- <span data-ttu-id="aab42-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-281">Driver' Lics#</span></span>
- <span data-ttu-id="aab42-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-282">Driver' Licence#</span></span>
- <span data-ttu-id="aab42-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-283">Driver' Licences#</span></span>
- <span data-ttu-id="aab42-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-284">Driver'sLic#</span></span>
- <span data-ttu-id="aab42-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-285">Driver'sLics#</span></span>
- <span data-ttu-id="aab42-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-286">Driver'sLicence#</span></span>
- <span data-ttu-id="aab42-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-287">Driver'sLicences#</span></span>
- <span data-ttu-id="aab42-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-288">Driver's Lic#</span></span>
- <span data-ttu-id="aab42-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-289">Driver's Lics#</span></span>
- <span data-ttu-id="aab42-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-290">Driver's Licence#</span></span>
- <span data-ttu-id="aab42-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="aab42-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="aab42-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="aab42-293">aaa</span><span class="sxs-lookup"><span data-stu-id="aab42-293">aaa</span></span>
- <span data-ttu-id="aab42-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-294">DriverLicense</span></span>
- <span data-ttu-id="aab42-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-295">DriverLicenses</span></span>
- <span data-ttu-id="aab42-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="aab42-296">Driver License</span></span>
- <span data-ttu-id="aab42-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-297">Driver Licenses</span></span>
- <span data-ttu-id="aab42-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-298">DriversLicense</span></span>
- <span data-ttu-id="aab42-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-299">DriversLicenses</span></span>
- <span data-ttu-id="aab42-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="aab42-300">Drivers License</span></span>
- <span data-ttu-id="aab42-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-301">Drivers Licenses</span></span>
- <span data-ttu-id="aab42-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="aab42-302">Driver'License</span></span>
- <span data-ttu-id="aab42-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-303">Driver'Licenses</span></span>
- <span data-ttu-id="aab42-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="aab42-304">Driver' License</span></span>
- <span data-ttu-id="aab42-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-305">Driver' Licenses</span></span>
- <span data-ttu-id="aab42-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-306">Driver'sLicense</span></span>
- <span data-ttu-id="aab42-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-307">Driver'sLicenses</span></span>
- <span data-ttu-id="aab42-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="aab42-308">Driver's License</span></span>
- <span data-ttu-id="aab42-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-309">Driver's Licenses</span></span>
- <span data-ttu-id="aab42-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-310">DriverLicense#</span></span>
- <span data-ttu-id="aab42-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-311">DriverLicenses#</span></span>
- <span data-ttu-id="aab42-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="aab42-312">Driver License#</span></span>
- <span data-ttu-id="aab42-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-313">Driver Licenses#</span></span>
- <span data-ttu-id="aab42-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-314">DriversLicense#</span></span>
- <span data-ttu-id="aab42-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-315">DriversLicenses#</span></span>
- <span data-ttu-id="aab42-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="aab42-316">Drivers License#</span></span>
- <span data-ttu-id="aab42-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-317">Drivers Licenses#</span></span>
- <span data-ttu-id="aab42-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="aab42-318">Driver'License#</span></span>
- <span data-ttu-id="aab42-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-319">Driver'Licenses#</span></span>
- <span data-ttu-id="aab42-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="aab42-320">Driver' License#</span></span>
- <span data-ttu-id="aab42-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-321">Driver' Licenses#</span></span>
- <span data-ttu-id="aab42-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-322">Driver'sLicense#</span></span>
- <span data-ttu-id="aab42-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="aab42-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="aab42-324">Driver's License#</span></span>
- <span data-ttu-id="aab42-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="aab42-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-327">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-327">Format</span></span>

<span data-ttu-id="aab42-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-329">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-329">Pattern</span></span>

<span data-ttu-id="aab42-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-330">10-11 digits:</span></span>
- <span data-ttu-id="aab42-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="aab42-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="aab42-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="aab42-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="aab42-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="aab42-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="aab42-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-335">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-335">Checksum</span></span>

<span data-ttu-id="aab42-336">是</span><span class="sxs-lookup"><span data-stu-id="aab42-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-337">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-337">Definition</span></span>

<span data-ttu-id="aab42-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="aab42-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-341">The checksum passes.</span></span>

<span data-ttu-id="aab42-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-345">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="aab42-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="aab42-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="aab42-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="aab42-347">bank account details</span></span>
- <span data-ttu-id="aab42-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="aab42-348">medicare payments</span></span>
- <span data-ttu-id="aab42-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="aab42-349">mortgage account</span></span>
- <span data-ttu-id="aab42-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="aab42-350">bank payments</span></span>
- <span data-ttu-id="aab42-351">information branch</span><span class="sxs-lookup"><span data-stu-id="aab42-351">information branch</span></span>
- <span data-ttu-id="aab42-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="aab42-352">credit card loan</span></span>
- <span data-ttu-id="aab42-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="aab42-353">department of human services</span></span>
- <span data-ttu-id="aab42-354">local service</span><span class="sxs-lookup"><span data-stu-id="aab42-354">local service</span></span>
- <span data-ttu-id="aab42-355">medicare</span><span class="sxs-lookup"><span data-stu-id="aab42-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="aab42-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="aab42-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-357">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-357">Format</span></span>

<span data-ttu-id="aab42-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-359">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-359">Pattern</span></span>

<span data-ttu-id="aab42-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-361">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-361">Checksum</span></span>

<span data-ttu-id="aab42-362">否</span><span class="sxs-lookup"><span data-stu-id="aab42-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-363">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-363">Definition</span></span>

<span data-ttu-id="aab42-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-366">找到 Keyword_passport 或 Keyword_australia_passport_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-367">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="aab42-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-368">Keyword_passport</span></span>

- <span data-ttu-id="aab42-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="aab42-369">Passport Number</span></span>
- <span data-ttu-id="aab42-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="aab42-370">Passport No</span></span>
- <span data-ttu-id="aab42-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-371">Passport #</span></span>
- <span data-ttu-id="aab42-372">登记卡#</span><span class="sxs-lookup"><span data-stu-id="aab42-372">Passport#</span></span>
- <span data-ttu-id="aab42-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="aab42-373">PassportID</span></span>
- <span data-ttu-id="aab42-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="aab42-374">Passportno</span></span>
- <span data-ttu-id="aab42-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-375">passportnumber</span></span>
- <span data-ttu-id="aab42-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-376">パスポート</span></span>
- <span data-ttu-id="aab42-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-377">パスポート番号</span></span>
- <span data-ttu-id="aab42-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-378">パスポートのNum</span></span>
- <span data-ttu-id="aab42-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="aab42-379">パスポート ＃</span></span> 
- <span data-ttu-id="aab42-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="aab42-380">Numéro de passeport</span></span>
- <span data-ttu-id="aab42-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="aab42-381">Passeport n °</span></span>
- <span data-ttu-id="aab42-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="aab42-382">Passeport Non</span></span>
- <span data-ttu-id="aab42-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="aab42-383">Passeport #</span></span>
- <span data-ttu-id="aab42-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="aab42-384">Passeport#</span></span>
- <span data-ttu-id="aab42-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="aab42-385">PasseportNon</span></span>
- <span data-ttu-id="aab42-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="aab42-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="aab42-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="aab42-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="aab42-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="aab42-388">passport</span></span>
- <span data-ttu-id="aab42-389">passport details</span><span class="sxs-lookup"><span data-stu-id="aab42-389">passport details</span></span>
- <span data-ttu-id="aab42-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="aab42-390">immigration and citizenship</span></span>
- <span data-ttu-id="aab42-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="aab42-391">commonwealth of australia</span></span>
- <span data-ttu-id="aab42-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="aab42-392">department of immigration</span></span>
- <span data-ttu-id="aab42-393">residential address</span><span class="sxs-lookup"><span data-stu-id="aab42-393">residential address</span></span>
- <span data-ttu-id="aab42-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="aab42-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="aab42-395">反之</span><span class="sxs-lookup"><span data-stu-id="aab42-395">visa</span></span>
- <span data-ttu-id="aab42-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-396">national identity card</span></span>
- <span data-ttu-id="aab42-397">passport number</span><span class="sxs-lookup"><span data-stu-id="aab42-397">passport number</span></span>
- <span data-ttu-id="aab42-398">travel document</span><span class="sxs-lookup"><span data-stu-id="aab42-398">travel document</span></span>
- <span data-ttu-id="aab42-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="aab42-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="aab42-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="aab42-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-401">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-401">Format</span></span>

<span data-ttu-id="aab42-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-403">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-403">Pattern</span></span>

<span data-ttu-id="aab42-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aab42-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="aab42-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-405">Three digits</span></span> 
- <span data-ttu-id="aab42-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="aab42-406">An optional space</span></span> 
- <span data-ttu-id="aab42-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-407">Three digits</span></span> 
- <span data-ttu-id="aab42-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="aab42-408">An optional space</span></span> 
- <span data-ttu-id="aab42-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-410">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-410">Checksum</span></span>

<span data-ttu-id="aab42-411">是</span><span class="sxs-lookup"><span data-stu-id="aab42-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-412">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-412">Definition</span></span>

<span data-ttu-id="aab42-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="aab42-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-417">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="aab42-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="aab42-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="aab42-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="aab42-419">australian business number</span></span>
- <span data-ttu-id="aab42-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="aab42-420">marginal tax rate</span></span>
- <span data-ttu-id="aab42-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="aab42-421">medicare levy</span></span>
- <span data-ttu-id="aab42-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="aab42-422">portfolio number</span></span>
- <span data-ttu-id="aab42-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="aab42-423">service veterans</span></span>
- <span data-ttu-id="aab42-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="aab42-424">withholding tax</span></span>
- <span data-ttu-id="aab42-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="aab42-425">individual tax return</span></span>
- <span data-ttu-id="aab42-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="aab42-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="aab42-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="aab42-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="aab42-428">00000000</span><span class="sxs-lookup"><span data-stu-id="aab42-428">00000000</span></span>
- <span data-ttu-id="aab42-429">11111111</span><span class="sxs-lookup"><span data-stu-id="aab42-429">11111111</span></span>
- <span data-ttu-id="aab42-430">22222222</span><span class="sxs-lookup"><span data-stu-id="aab42-430">22222222</span></span>
- <span data-ttu-id="aab42-431">33333333</span><span class="sxs-lookup"><span data-stu-id="aab42-431">33333333</span></span>
- <span data-ttu-id="aab42-432">44444444</span><span class="sxs-lookup"><span data-stu-id="aab42-432">44444444</span></span>
- <span data-ttu-id="aab42-433">55555555</span><span class="sxs-lookup"><span data-stu-id="aab42-433">55555555</span></span>
- <span data-ttu-id="aab42-434">66666666</span><span class="sxs-lookup"><span data-stu-id="aab42-434">66666666</span></span>
- <span data-ttu-id="aab42-435">77777777</span><span class="sxs-lookup"><span data-stu-id="aab42-435">77777777</span></span>
- <span data-ttu-id="aab42-436">88888888</span><span class="sxs-lookup"><span data-stu-id="aab42-436">88888888</span></span>
- <span data-ttu-id="aab42-437">99999999</span><span class="sxs-lookup"><span data-stu-id="aab42-437">99999999</span></span>
- <span data-ttu-id="aab42-438">000000000</span><span class="sxs-lookup"><span data-stu-id="aab42-438">000000000</span></span>
- <span data-ttu-id="aab42-439">111111111</span><span class="sxs-lookup"><span data-stu-id="aab42-439">111111111</span></span>
- <span data-ttu-id="aab42-440">222222222</span><span class="sxs-lookup"><span data-stu-id="aab42-440">222222222</span></span>
- <span data-ttu-id="aab42-441">333333333</span><span class="sxs-lookup"><span data-stu-id="aab42-441">333333333</span></span>
- <span data-ttu-id="aab42-442">444444444</span><span class="sxs-lookup"><span data-stu-id="aab42-442">444444444</span></span>
- <span data-ttu-id="aab42-443">555555555</span><span class="sxs-lookup"><span data-stu-id="aab42-443">555555555</span></span>
- <span data-ttu-id="aab42-444">666666666</span><span class="sxs-lookup"><span data-stu-id="aab42-444">666666666</span></span>
- <span data-ttu-id="aab42-445">777777777</span><span class="sxs-lookup"><span data-stu-id="aab42-445">777777777</span></span>
- <span data-ttu-id="aab42-446">888888888</span><span class="sxs-lookup"><span data-stu-id="aab42-446">888888888</span></span>
- <span data-ttu-id="aab42-447">999999999</span><span class="sxs-lookup"><span data-stu-id="aab42-447">999999999</span></span>
- <span data-ttu-id="aab42-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="aab42-448">0000000000</span></span>
- <span data-ttu-id="aab42-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="aab42-449">1111111111</span></span>
- <span data-ttu-id="aab42-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="aab42-450">2222222222</span></span>
- <span data-ttu-id="aab42-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="aab42-451">3333333333</span></span>
- <span data-ttu-id="aab42-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="aab42-452">4444444444</span></span>
- <span data-ttu-id="aab42-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="aab42-453">5555555555</span></span>
- <span data-ttu-id="aab42-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="aab42-454">6666666666</span></span>
- <span data-ttu-id="aab42-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="aab42-455">7777777777</span></span>
- <span data-ttu-id="aab42-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="aab42-456">8888888888</span></span>
- <span data-ttu-id="aab42-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="aab42-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="aab42-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="aab42-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="aab42-459">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-459">Format</span></span>

<span data-ttu-id="aab42-460">字符串 "DocumentDb"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="aab42-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-461">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-461">Pattern</span></span>

- <span data-ttu-id="aab42-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="aab42-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="aab42-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-464">大于号（>）、等号（=）、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="aab42-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="aab42-465">86字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-466">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-467">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-467">Checksum</span></span>

<span data-ttu-id="aab42-468">否</span><span class="sxs-lookup"><span data-stu-id="aab42-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-469">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-469">Definition</span></span>

<span data-ttu-id="aab42-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-472">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-473">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-475">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-476">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-476">contoso</span></span>
- <span data-ttu-id="aab42-477">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-477">fabrikam</span></span>
- <span data-ttu-id="aab42-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-478">northwind</span></span>
- <span data-ttu-id="aab42-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-479">sandbox</span></span>
- <span data-ttu-id="aab42-480">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-480">onebox</span></span>
- <span data-ttu-id="aab42-481">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-481">localhost</span></span>
- <span data-ttu-id="aab42-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-482">127.0.0.1</span></span>
- <span data-ttu-id="aab42-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-484">com</span><span class="sxs-lookup"><span data-stu-id="aab42-484">com</span></span>
- <span data-ttu-id="aab42-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-486">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="aab42-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="aab42-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="aab42-488">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-488">Format</span></span>

<span data-ttu-id="aab42-489">字符串 "Server"、"server" 或 "data source"，后跟下面模式中所述的字符和字符串，包括字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="aab42-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-490">com "或" cloudapp "。</span><span class="sxs-lookup"><span data-stu-id="aab42-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="aab42-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-492">net "和字符串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="aab42-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-493">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-493">Pattern</span></span>

- <span data-ttu-id="aab42-494">字符串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="aab42-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="aab42-495">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-496">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-496">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-498">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-499">字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="aab42-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-500">com "，" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="aab42-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="aab42-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-502">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-502">net"</span></span>
- <span data-ttu-id="aab42-503">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-504">字符串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="aab42-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="aab42-505">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-506">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-506">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-507">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-508">一个或多个不是分号（;)、引号（"）或撇号（'）的字符</span><span class="sxs-lookup"><span data-stu-id="aab42-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="aab42-509">分号（;)、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="aab42-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-510">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-510">Checksum</span></span>

<span data-ttu-id="aab42-511">否</span><span class="sxs-lookup"><span data-stu-id="aab42-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-512">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-512">Definition</span></span>

<span data-ttu-id="aab42-513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-514">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-515">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-516">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-518">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-519">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-519">contoso</span></span>
- <span data-ttu-id="aab42-520">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-520">fabrikam</span></span>
- <span data-ttu-id="aab42-521">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-521">northwind</span></span>
- <span data-ttu-id="aab42-522">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-522">sandbox</span></span>
- <span data-ttu-id="aab42-523">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-523">onebox</span></span>
- <span data-ttu-id="aab42-524">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-524">localhost</span></span>
- <span data-ttu-id="aab42-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-525">127.0.0.1</span></span>
- <span data-ttu-id="aab42-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-527">com</span><span class="sxs-lookup"><span data-stu-id="aab42-527">com</span></span>
- <span data-ttu-id="aab42-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-529">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="aab42-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="aab42-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="aab42-531">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-531">Format</span></span>

<span data-ttu-id="aab42-532">字符串 "HostName"，后跟下面模式中所示的字符和字符串，包括字符串 "azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="aab42-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="aab42-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-534">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-534">Pattern</span></span>

- <span data-ttu-id="aab42-535">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="aab42-535">The string "HostName"</span></span>
- <span data-ttu-id="aab42-536">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-537">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-537">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-538">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-539">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-540">字符串 "azure 设备。</span><span class="sxs-lookup"><span data-stu-id="aab42-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-541">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-541">net"</span></span>
- <span data-ttu-id="aab42-542">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-543">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="aab42-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="aab42-544">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-545">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-545">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-546">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-547">43字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-548">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-549">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-549">Checksum</span></span>

<span data-ttu-id="aab42-550">否</span><span class="sxs-lookup"><span data-stu-id="aab42-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-551">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-551">Definition</span></span>

<span data-ttu-id="aab42-552">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-553">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-554">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-555">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-557">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-558">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-558">contoso</span></span>
- <span data-ttu-id="aab42-559">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-559">fabrikam</span></span>
- <span data-ttu-id="aab42-560">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-560">northwind</span></span>
- <span data-ttu-id="aab42-561">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-561">sandbox</span></span>
- <span data-ttu-id="aab42-562">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-562">onebox</span></span>
- <span data-ttu-id="aab42-563">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-563">localhost</span></span>
- <span data-ttu-id="aab42-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-564">127.0.0.1</span></span>
- <span data-ttu-id="aab42-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-566">com</span><span class="sxs-lookup"><span data-stu-id="aab42-566">com</span></span>
- <span data-ttu-id="aab42-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-568">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="aab42-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="aab42-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="aab42-570">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-570">Format</span></span>

<span data-ttu-id="aab42-571">字符串 "userpwd ="，后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="aab42-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-572">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-572">Pattern</span></span>

- <span data-ttu-id="aab42-573">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="aab42-573">The string "userpwd="</span></span>
- <span data-ttu-id="aab42-574">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="aab42-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="aab42-575">一个引号（"）</span><span class="sxs-lookup"><span data-stu-id="aab42-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-576">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-576">Checksum</span></span>

<span data-ttu-id="aab42-577">否</span><span class="sxs-lookup"><span data-stu-id="aab42-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-578">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-578">Definition</span></span>

<span data-ttu-id="aab42-579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-581">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="aab42-582">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-584">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-585">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-585">contoso</span></span>
- <span data-ttu-id="aab42-586">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-586">fabrikam</span></span>
- <span data-ttu-id="aab42-587">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-587">northwind</span></span>
- <span data-ttu-id="aab42-588">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-588">sandbox</span></span>
- <span data-ttu-id="aab42-589">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-589">onebox</span></span>
- <span data-ttu-id="aab42-590">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-590">localhost</span></span>
- <span data-ttu-id="aab42-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-591">127.0.0.1</span></span>
- <span data-ttu-id="aab42-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-593">com</span><span class="sxs-lookup"><span data-stu-id="aab42-593">com</span></span>
- <span data-ttu-id="aab42-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-595">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="aab42-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="aab42-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="aab42-597">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-597">Format</span></span>

<span data-ttu-id="aab42-598">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="aab42-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-599">net "，后跟下面的模式中所述的字符和字符串，包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="aab42-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-600">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-600">Pattern</span></span>

- <span data-ttu-id="aab42-601">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="aab42-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-602">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-602">net"</span></span>
- <span data-ttu-id="aab42-603">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-604">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="aab42-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="aab42-605">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-606">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-606">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-607">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-608">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="aab42-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-609">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-610">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-610">Checksum</span></span>

<span data-ttu-id="aab42-611">否</span><span class="sxs-lookup"><span data-stu-id="aab42-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-612">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-612">Definition</span></span>

<span data-ttu-id="aab42-613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-614">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="aab42-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="aab42-615">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-616">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-618">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-619">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-619">contoso</span></span>
- <span data-ttu-id="aab42-620">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-620">fabrikam</span></span>
- <span data-ttu-id="aab42-621">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-621">northwind</span></span>
- <span data-ttu-id="aab42-622">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-622">sandbox</span></span>
- <span data-ttu-id="aab42-623">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-623">onebox</span></span>
- <span data-ttu-id="aab42-624">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-624">localhost</span></span>
- <span data-ttu-id="aab42-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-625">127.0.0.1</span></span>
- <span data-ttu-id="aab42-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-627">com</span><span class="sxs-lookup"><span data-stu-id="aab42-627">com</span></span>
- <span data-ttu-id="aab42-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-629">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="aab42-630">Azure SA</span><span class="sxs-lookup"><span data-stu-id="aab42-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="aab42-631">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-631">Format</span></span>

<span data-ttu-id="aab42-632">字符串 "sig"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="aab42-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-633">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-633">Pattern</span></span>

- <span data-ttu-id="aab42-634">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="aab42-634">The string "sig"</span></span>
- <span data-ttu-id="aab42-635">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-636">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-636">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-637">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-638">介于43-53 个字符和小写字母、数字或百分比符号（%）之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="aab42-639">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="aab42-639">The string "%3d"</span></span>
- <span data-ttu-id="aab42-640">不是字母或大写字符、数字或百分号（%）的任何字符</span><span class="sxs-lookup"><span data-stu-id="aab42-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-641">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-641">Checksum</span></span>

<span data-ttu-id="aab42-642">否</span><span class="sxs-lookup"><span data-stu-id="aab42-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-643">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-643">Definition</span></span>

<span data-ttu-id="aab42-644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-645">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="aab42-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="aab42-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="aab42-647">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-647">Format</span></span>

<span data-ttu-id="aab42-648">字符串 "终结点"，后跟下面模式中所示的字符和字符串，包括字符串 "</span><span class="sxs-lookup"><span data-stu-id="aab42-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="aab42-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-650">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-650">Pattern</span></span>

- <span data-ttu-id="aab42-651">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="aab42-651">The string "EndPoint"</span></span>
- <span data-ttu-id="aab42-652">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-653">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-653">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-654">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-655">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-656">字符串 "</span><span class="sxs-lookup"><span data-stu-id="aab42-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-657">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-657">net"</span></span>
- <span data-ttu-id="aab42-658">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-659">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="aab42-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="aab42-660">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-661">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-661">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-662">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-663">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="aab42-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-664">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-665">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-665">Checksum</span></span>

<span data-ttu-id="aab42-666">否</span><span class="sxs-lookup"><span data-stu-id="aab42-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-667">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-667">Definition</span></span>

<span data-ttu-id="aab42-668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-669">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="aab42-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="aab42-670">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-671">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-673">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-674">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-674">contoso</span></span>
- <span data-ttu-id="aab42-675">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-675">fabrikam</span></span>
- <span data-ttu-id="aab42-676">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-676">northwind</span></span>
- <span data-ttu-id="aab42-677">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-677">sandbox</span></span>
- <span data-ttu-id="aab42-678">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-678">onebox</span></span>
- <span data-ttu-id="aab42-679">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-679">localhost</span></span>
- <span data-ttu-id="aab42-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-680">127.0.0.1</span></span>
- <span data-ttu-id="aab42-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-682">com</span><span class="sxs-lookup"><span data-stu-id="aab42-682">com</span></span>
- <span data-ttu-id="aab42-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-684">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="aab42-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="aab42-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="aab42-686">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-686">Format</span></span>

<span data-ttu-id="aab42-687">字符串 "DefaultEndpointsProtocol"，后跟下面模式中所述的字符和字符串，包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="aab42-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-688">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-688">Pattern</span></span>

- <span data-ttu-id="aab42-689">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="aab42-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="aab42-690">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-691">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-691">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-692">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-693">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-694">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="aab42-694">The string "AccountKey"</span></span>
- <span data-ttu-id="aab42-695">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-696">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-696">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-697">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="aab42-698">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="aab42-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-699">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-700">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-700">Checksum</span></span>

<span data-ttu-id="aab42-701">否</span><span class="sxs-lookup"><span data-stu-id="aab42-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-702">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-702">Definition</span></span>

<span data-ttu-id="aab42-703">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-704">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-705">正则表达式**CEP_AzureEmulatorStorageAccountFilter 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-706">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-707">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="aab42-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="aab42-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="aab42-709">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="aab42-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-712">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-713">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-713">contoso</span></span>
- <span data-ttu-id="aab42-714">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-714">fabrikam</span></span>
- <span data-ttu-id="aab42-715">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-715">northwind</span></span>
- <span data-ttu-id="aab42-716">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-716">sandbox</span></span>
- <span data-ttu-id="aab42-717">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-717">onebox</span></span>
- <span data-ttu-id="aab42-718">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-718">localhost</span></span>
- <span data-ttu-id="aab42-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-719">127.0.0.1</span></span>
- <span data-ttu-id="aab42-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-721">com</span><span class="sxs-lookup"><span data-stu-id="aab42-721">com</span></span>
- <span data-ttu-id="aab42-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-723">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="aab42-724">Azure 存储帐户密钥（常规）</span><span class="sxs-lookup"><span data-stu-id="aab42-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-725">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-725">Format</span></span>

<span data-ttu-id="aab42-726">任何86位或大写字母、数字、正斜杠（/）或加号（+）的任意组合，前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="aab42-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-727">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-727">Pattern</span></span>

- <span data-ttu-id="aab42-728">大于号（>）、撇号（'）、等号（=）、引号（"）或数字符号（#）的0-1</span><span class="sxs-lookup"><span data-stu-id="aab42-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="aab42-729">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="aab42-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="aab42-730">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="aab42-731">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-731">Checksum</span></span>

<span data-ttu-id="aab42-732">否</span><span class="sxs-lookup"><span data-stu-id="aab42-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-733">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-733">Definition</span></span>

<span data-ttu-id="aab42-734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-735">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="aab42-736">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="aab42-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-737">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-737">Format</span></span>

<span data-ttu-id="aab42-738">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="aab42-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-739">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-739">Pattern</span></span>

<span data-ttu-id="aab42-740">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="aab42-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="aab42-741">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="aab42-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="aab42-742">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-742">A hyphen</span></span> 
- <span data-ttu-id="aab42-743">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="aab42-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="aab42-744">一个点</span><span class="sxs-lookup"><span data-stu-id="aab42-744">A period</span></span> 
- <span data-ttu-id="aab42-745">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-746">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-746">Checksum</span></span>

<span data-ttu-id="aab42-747">是</span><span class="sxs-lookup"><span data-stu-id="aab42-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-748">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-748">Definition</span></span>

<span data-ttu-id="aab42-749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-750">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-751">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="aab42-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-753">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="aab42-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="aab42-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="aab42-755">标识</span><span class="sxs-lookup"><span data-stu-id="aab42-755">Identity</span></span>
- <span data-ttu-id="aab42-756">注册</span><span class="sxs-lookup"><span data-stu-id="aab42-756">Registration</span></span>
- <span data-ttu-id="aab42-757">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-757">Identification</span></span> 
- <span data-ttu-id="aab42-758">ID</span><span class="sxs-lookup"><span data-stu-id="aab42-758">ID</span></span> 
- <span data-ttu-id="aab42-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="aab42-759">Identiteitskaart</span></span>
- <span data-ttu-id="aab42-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="aab42-760">Registratie nummer</span></span> 
- <span data-ttu-id="aab42-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="aab42-761">Identificatie nummer</span></span> 
- <span data-ttu-id="aab42-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="aab42-762">Identiteit</span></span>
- <span data-ttu-id="aab42-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="aab42-763">Registratie</span></span>
- <span data-ttu-id="aab42-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="aab42-764">Identificatie</span></span> 
- <span data-ttu-id="aab42-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="aab42-765">Carte d’identité</span></span> 
- <span data-ttu-id="aab42-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="aab42-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="aab42-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="aab42-767">numéro d'identification</span></span>
- <span data-ttu-id="aab42-768">identité</span><span class="sxs-lookup"><span data-stu-id="aab42-768">identité</span></span> 
- <span data-ttu-id="aab42-769">inscription</span><span class="sxs-lookup"><span data-stu-id="aab42-769">inscription</span></span> 
- <span data-ttu-id="aab42-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="aab42-770">Identifikation</span></span>
- <span data-ttu-id="aab42-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="aab42-771">Identifizierung</span></span>
- <span data-ttu-id="aab42-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-772">Identifikationsnummer</span></span>
- <span data-ttu-id="aab42-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="aab42-773">Personalausweis</span></span>
- <span data-ttu-id="aab42-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="aab42-774">Registrierung</span></span>
- <span data-ttu-id="aab42-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="aab42-776">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="aab42-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-777">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-777">Format</span></span>

<span data-ttu-id="aab42-778">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="aab42-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-779">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-779">Pattern</span></span>

<span data-ttu-id="aab42-780">格式</span><span class="sxs-lookup"><span data-stu-id="aab42-780">Formatted:</span></span>
- <span data-ttu-id="aab42-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-781">Three digits</span></span> 
- <span data-ttu-id="aab42-782">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-782">A period</span></span> 
- <span data-ttu-id="aab42-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-783">Three digits</span></span> 
- <span data-ttu-id="aab42-784">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-784">A period</span></span> 
- <span data-ttu-id="aab42-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-785">Three digits</span></span> 
- <span data-ttu-id="aab42-786">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-786">A hyphen</span></span> 
- <span data-ttu-id="aab42-787">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-787">Two digits which are check digits</span></span>

<span data-ttu-id="aab42-788">纯</span><span class="sxs-lookup"><span data-stu-id="aab42-788">Unformatted:</span></span>
- <span data-ttu-id="aab42-789">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-790">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-790">Checksum</span></span>

<span data-ttu-id="aab42-791">是</span><span class="sxs-lookup"><span data-stu-id="aab42-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-792">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-792">Definition</span></span>

<span data-ttu-id="aab42-793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-794">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-795">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="aab42-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-796">The checksum passes.</span></span>

<span data-ttu-id="aab42-797">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-798">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-800">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="aab42-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="aab42-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="aab42-802">CPF</span><span class="sxs-lookup"><span data-stu-id="aab42-802">CPF</span></span>
- <span data-ttu-id="aab42-803">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-803">Identification</span></span>
- <span data-ttu-id="aab42-804">注册</span><span class="sxs-lookup"><span data-stu-id="aab42-804">Registration</span></span>
- <span data-ttu-id="aab42-805">营业</span><span class="sxs-lookup"><span data-stu-id="aab42-805">Revenue</span></span>
- <span data-ttu-id="aab42-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="aab42-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="aab42-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="aab42-807">Imposto</span></span> 
- <span data-ttu-id="aab42-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="aab42-808">Identificação</span></span> 
- <span data-ttu-id="aab42-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="aab42-809">Inscrição</span></span> 
- <span data-ttu-id="aab42-810">Receita</span><span class="sxs-lookup"><span data-stu-id="aab42-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="aab42-811">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="aab42-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-812">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-812">Format</span></span>

<span data-ttu-id="aab42-813">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="aab42-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-814">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-814">Pattern</span></span>
<span data-ttu-id="aab42-815">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="aab42-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="aab42-816">两个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-816">Two digits</span></span> 
- <span data-ttu-id="aab42-817">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-817">A period</span></span> 
- <span data-ttu-id="aab42-818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-818">Three digits</span></span> 
- <span data-ttu-id="aab42-819">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-819">A period</span></span> 
- <span data-ttu-id="aab42-820">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="aab42-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="aab42-821">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="aab42-821">A forward slash</span></span> 
- <span data-ttu-id="aab42-822">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="aab42-822">Four-digit branch number</span></span> 
- <span data-ttu-id="aab42-823">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-823">A hyphen</span></span> 
- <span data-ttu-id="aab42-824">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-825">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-825">Checksum</span></span>

<span data-ttu-id="aab42-826">是</span><span class="sxs-lookup"><span data-stu-id="aab42-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-827">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-827">Definition</span></span>

<span data-ttu-id="aab42-828">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-829">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-830">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="aab42-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-831">The checksum passes.</span></span>

<span data-ttu-id="aab42-832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-833">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-835">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="aab42-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="aab42-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="aab42-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="aab42-837">CNPJ</span></span> 
- <span data-ttu-id="aab42-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="aab42-838">CNPJ/MF</span></span> 
- <span data-ttu-id="aab42-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="aab42-839">CNPJ-MF</span></span> 
- <span data-ttu-id="aab42-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="aab42-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="aab42-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="aab42-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="aab42-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="aab42-842">Legal entity</span></span> 
- <span data-ttu-id="aab42-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="aab42-843">Legal entities</span></span> 
- <span data-ttu-id="aab42-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="aab42-844">Registration Status</span></span> 
- <span data-ttu-id="aab42-845">商业版</span><span class="sxs-lookup"><span data-stu-id="aab42-845">Business</span></span> 
- <span data-ttu-id="aab42-846">Company</span><span class="sxs-lookup"><span data-stu-id="aab42-846">Company</span></span>
- <span data-ttu-id="aab42-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="aab42-847">CNPJ</span></span> 
- <span data-ttu-id="aab42-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="aab42-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="aab42-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="aab42-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="aab42-850">CGC</span><span class="sxs-lookup"><span data-stu-id="aab42-850">CGC</span></span> 
- <span data-ttu-id="aab42-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="aab42-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="aab42-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="aab42-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="aab42-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="aab42-853">Situação cadastral</span></span> 
- <span data-ttu-id="aab42-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="aab42-854">Inscrição</span></span> 
- <span data-ttu-id="aab42-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="aab42-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="aab42-856">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="aab42-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-857">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-857">Format</span></span>

<span data-ttu-id="aab42-858">Registro Geral （旧格式）：9个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="aab42-859">Registro de Identidade （RIC）（新格式）：11个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-860">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-860">Pattern</span></span>

<span data-ttu-id="aab42-861">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="aab42-862">两个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-862">Two digits</span></span> 
- <span data-ttu-id="aab42-863">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-863">A period</span></span> 
- <span data-ttu-id="aab42-864">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-864">Three digits</span></span> 
- <span data-ttu-id="aab42-865">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-865">A period</span></span> 
- <span data-ttu-id="aab42-866">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-866">Three digits</span></span> 
- <span data-ttu-id="aab42-867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-867">A hyphen</span></span> 
- <span data-ttu-id="aab42-868">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-868">One digit which is a check digit</span></span>

<span data-ttu-id="aab42-869">Registro de Identidade （RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="aab42-870">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-870">10 digits</span></span> 
- <span data-ttu-id="aab42-871">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-871">A hyphen</span></span> 
- <span data-ttu-id="aab42-872">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-873">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-873">Checksum</span></span>

<span data-ttu-id="aab42-874">是</span><span class="sxs-lookup"><span data-stu-id="aab42-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-875">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-875">Definition</span></span>

<span data-ttu-id="aab42-876">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-877">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-878">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="aab42-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-879">The checksum passes.</span></span>

<span data-ttu-id="aab42-880">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-881">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-883">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="aab42-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="aab42-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="aab42-885">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG （此关键字区分大小写） RIC （此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="aab42-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-887">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-887">Format</span></span>

<span data-ttu-id="aab42-888">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-889">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-889">Pattern</span></span>

<span data-ttu-id="aab42-890">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="aab42-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="aab42-891">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="aab42-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="aab42-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-892">Five digits</span></span> 
- <span data-ttu-id="aab42-893">连字符</span><span class="sxs-lookup"><span data-stu-id="aab42-893">A hyphen</span></span> 
- <span data-ttu-id="aab42-894">三位数字或</span><span class="sxs-lookup"><span data-stu-id="aab42-894">Three digits OR</span></span>
- <span data-ttu-id="aab42-895">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="aab42-895">A zero "0"</span></span> 
- <span data-ttu-id="aab42-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-897">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-897">Checksum</span></span>

<span data-ttu-id="aab42-898">否</span><span class="sxs-lookup"><span data-stu-id="aab42-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-899">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-899">Definition</span></span>

<span data-ttu-id="aab42-900">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-901">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-902">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="aab42-903">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="aab42-904">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-905">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-906">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-907">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="aab42-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="aab42-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="aab42-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="aab42-909">canada savings bonds</span></span>
- <span data-ttu-id="aab42-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="aab42-910">canada revenue agency</span></span>
- <span data-ttu-id="aab42-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="aab42-911">canadian financial institution</span></span>
- <span data-ttu-id="aab42-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="aab42-912">direct deposit form</span></span>
- <span data-ttu-id="aab42-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="aab42-913">canadian citizen</span></span>
- <span data-ttu-id="aab42-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="aab42-914">legal representative</span></span>
- <span data-ttu-id="aab42-915">notary public</span><span class="sxs-lookup"><span data-stu-id="aab42-915">notary public</span></span>
- <span data-ttu-id="aab42-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="aab42-916">commissioner for oaths</span></span>
- <span data-ttu-id="aab42-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="aab42-917">child care benefit</span></span>
- <span data-ttu-id="aab42-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="aab42-918">universal child care</span></span>
- <span data-ttu-id="aab42-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="aab42-919">canada child tax benefit</span></span>
- <span data-ttu-id="aab42-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="aab42-920">income tax benefit</span></span>
- <span data-ttu-id="aab42-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="aab42-921">harmonized sales tax</span></span>
- <span data-ttu-id="aab42-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="aab42-922">social insurance number</span></span>
- <span data-ttu-id="aab42-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="aab42-923">income tax refund</span></span>
- <span data-ttu-id="aab42-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="aab42-924">child tax benefit</span></span>
- <span data-ttu-id="aab42-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="aab42-925">territorial payments</span></span>
- <span data-ttu-id="aab42-926">institution number</span><span class="sxs-lookup"><span data-stu-id="aab42-926">institution number</span></span>
- <span data-ttu-id="aab42-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="aab42-927">deposit request</span></span>
- <span data-ttu-id="aab42-928">banking information</span><span class="sxs-lookup"><span data-stu-id="aab42-928">banking information</span></span>
- <span data-ttu-id="aab42-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="aab42-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="aab42-930">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-931">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-931">Format</span></span>

<span data-ttu-id="aab42-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="aab42-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-933">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-933">Pattern</span></span>

<span data-ttu-id="aab42-934">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="aab42-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-935">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-935">Checksum</span></span>

<span data-ttu-id="aab42-936">否</span><span class="sxs-lookup"><span data-stu-id="aab42-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-937">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-937">Definition</span></span>

<span data-ttu-id="aab42-938">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-939">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-940">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="aab42-941">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-942">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="aab42-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="aab42-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="aab42-944">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="aab42-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="aab42-945">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="aab42-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="aab42-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="aab42-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="aab42-947">通讯</span><span class="sxs-lookup"><span data-stu-id="aab42-947">DL</span></span>
- <span data-ttu-id="aab42-948">DLS</span><span class="sxs-lookup"><span data-stu-id="aab42-948">DLS</span></span>
- <span data-ttu-id="aab42-949">采用</span><span class="sxs-lookup"><span data-stu-id="aab42-949">CDL</span></span>
- <span data-ttu-id="aab42-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="aab42-950">CDLS</span></span>
- <span data-ttu-id="aab42-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="aab42-951">DriverLic</span></span>
- <span data-ttu-id="aab42-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="aab42-952">DriverLics</span></span>
- <span data-ttu-id="aab42-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-953">DriverLicense</span></span>
- <span data-ttu-id="aab42-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-954">DriverLicenses</span></span>
- <span data-ttu-id="aab42-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-955">DriverLicence</span></span>
- <span data-ttu-id="aab42-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-956">DriverLicences</span></span>
- <span data-ttu-id="aab42-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-957">Driver Lic</span></span>
- <span data-ttu-id="aab42-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-958">Driver Lics</span></span>
- <span data-ttu-id="aab42-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="aab42-959">Driver License</span></span>
- <span data-ttu-id="aab42-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-960">Driver Licenses</span></span>
- <span data-ttu-id="aab42-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-961">Driver Licence</span></span>
- <span data-ttu-id="aab42-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-962">Driver Licences</span></span>
- <span data-ttu-id="aab42-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="aab42-963">DriversLic</span></span>
- <span data-ttu-id="aab42-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="aab42-964">DriversLics</span></span>
- <span data-ttu-id="aab42-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-965">DriversLicence</span></span>
- <span data-ttu-id="aab42-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-966">DriversLicences</span></span>
- <span data-ttu-id="aab42-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-967">DriversLicense</span></span>
- <span data-ttu-id="aab42-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-968">DriversLicenses</span></span>
- <span data-ttu-id="aab42-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-969">Drivers Lic</span></span>
- <span data-ttu-id="aab42-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-970">Drivers Lics</span></span>
- <span data-ttu-id="aab42-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="aab42-971">Drivers License</span></span>
- <span data-ttu-id="aab42-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-972">Drivers Licenses</span></span>
- <span data-ttu-id="aab42-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-973">Drivers Licence</span></span>
- <span data-ttu-id="aab42-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-974">Drivers Licences</span></span>
- <span data-ttu-id="aab42-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-975">Driver'Lic</span></span>
- <span data-ttu-id="aab42-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-976">Driver'Lics</span></span>
- <span data-ttu-id="aab42-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="aab42-977">Driver'License</span></span>
- <span data-ttu-id="aab42-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-978">Driver'Licenses</span></span>
- <span data-ttu-id="aab42-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-979">Driver'Licence</span></span>
- <span data-ttu-id="aab42-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-980">Driver'Licences</span></span>
- <span data-ttu-id="aab42-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-981">Driver' Lic</span></span>
- <span data-ttu-id="aab42-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-982">Driver' Lics</span></span>
- <span data-ttu-id="aab42-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="aab42-983">Driver' License</span></span>
- <span data-ttu-id="aab42-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-984">Driver' Licenses</span></span>
- <span data-ttu-id="aab42-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-985">Driver' Licence</span></span>
- <span data-ttu-id="aab42-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-986">Driver' Licences</span></span>
- <span data-ttu-id="aab42-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="aab42-987">Driver'sLic</span></span>
- <span data-ttu-id="aab42-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="aab42-988">Driver'sLics</span></span>
- <span data-ttu-id="aab42-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-989">Driver'sLicense</span></span>
- <span data-ttu-id="aab42-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-990">Driver'sLicenses</span></span>
- <span data-ttu-id="aab42-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="aab42-991">Driver'sLicence</span></span>
- <span data-ttu-id="aab42-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="aab42-992">Driver'sLicences</span></span>
- <span data-ttu-id="aab42-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-993">Driver's Lic</span></span>
- <span data-ttu-id="aab42-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-994">Driver's Lics</span></span>
- <span data-ttu-id="aab42-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="aab42-995">Driver's License</span></span>
- <span data-ttu-id="aab42-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-996">Driver's Licenses</span></span>
- <span data-ttu-id="aab42-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-997">Driver's Licence</span></span>
- <span data-ttu-id="aab42-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-998">Driver's Licences</span></span>
- <span data-ttu-id="aab42-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="aab42-999">Permis de Conduire</span></span>
- <span data-ttu-id="aab42-1000">id</span><span class="sxs-lookup"><span data-stu-id="aab42-1000">id</span></span>
- <span data-ttu-id="aab42-1001">ids</span><span class="sxs-lookup"><span data-stu-id="aab42-1001">ids</span></span>
- <span data-ttu-id="aab42-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="aab42-1002">idcard number</span></span>
- <span data-ttu-id="aab42-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1003">idcard numbers</span></span>
- <span data-ttu-id="aab42-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="aab42-1004">idcard #</span></span>
- <span data-ttu-id="aab42-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="aab42-1005">idcard #s</span></span>
- <span data-ttu-id="aab42-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="aab42-1006">idcard card</span></span>
- <span data-ttu-id="aab42-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1007">idcard cards</span></span>
- <span data-ttu-id="aab42-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1008">idcard</span></span>
- <span data-ttu-id="aab42-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-1009">identification number</span></span>
- <span data-ttu-id="aab42-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1010">identification numbers</span></span>
- <span data-ttu-id="aab42-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="aab42-1011">identification #</span></span>
- <span data-ttu-id="aab42-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="aab42-1012">identification #s</span></span>
- <span data-ttu-id="aab42-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="aab42-1013">identification card</span></span>
- <span data-ttu-id="aab42-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1014">identification cards</span></span>
- <span data-ttu-id="aab42-1015">id</span><span class="sxs-lookup"><span data-stu-id="aab42-1015">identification</span></span> 
- <span data-ttu-id="aab42-1016">通讯#</span><span class="sxs-lookup"><span data-stu-id="aab42-1016">DL#</span></span>
- <span data-ttu-id="aab42-1017">DLS#</span><span class="sxs-lookup"><span data-stu-id="aab42-1017">DLS#</span></span> 
- <span data-ttu-id="aab42-1018">采用#</span><span class="sxs-lookup"><span data-stu-id="aab42-1018">CDL#</span></span> 
- <span data-ttu-id="aab42-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="aab42-1019">CDLS#</span></span> 
- <span data-ttu-id="aab42-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1020">DriverLic#</span></span> 
- <span data-ttu-id="aab42-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1021">DriverLics#</span></span> 
- <span data-ttu-id="aab42-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-1022">DriverLicense#</span></span> 
- <span data-ttu-id="aab42-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="aab42-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1024">DriverLicence#</span></span> 
- <span data-ttu-id="aab42-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1025">DriverLicences#</span></span> 
- <span data-ttu-id="aab42-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1026">Driver Lic#</span></span>
- <span data-ttu-id="aab42-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1027">Driver Lics#</span></span> 
- <span data-ttu-id="aab42-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1028">Driver License#</span></span> 
- <span data-ttu-id="aab42-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="aab42-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1030">Driver License#</span></span> 
- <span data-ttu-id="aab42-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1031">Driver Licences#</span></span> 
- <span data-ttu-id="aab42-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1032">DriversLic#</span></span> 
- <span data-ttu-id="aab42-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1033">DriversLics#</span></span> 
- <span data-ttu-id="aab42-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-1034">DriversLicense#</span></span> 
- <span data-ttu-id="aab42-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="aab42-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1036">DriversLicence#</span></span> 
- <span data-ttu-id="aab42-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1037">DriversLicences#</span></span> 
- <span data-ttu-id="aab42-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="aab42-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="aab42-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1040">Drivers License#</span></span> 
- <span data-ttu-id="aab42-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="aab42-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="aab42-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="aab42-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="aab42-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="aab42-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1046">Driver'License#</span></span> 
- <span data-ttu-id="aab42-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="aab42-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="aab42-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="aab42-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="aab42-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="aab42-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1052">Driver' License#</span></span> 
- <span data-ttu-id="aab42-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="aab42-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="aab42-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="aab42-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="aab42-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="aab42-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="aab42-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="aab42-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="aab42-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="aab42-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="aab42-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="aab42-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="aab42-1064">Driver's License#</span></span> 
- <span data-ttu-id="aab42-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="aab42-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="aab42-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="aab42-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="aab42-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="aab42-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="aab42-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="aab42-1069">号#</span><span class="sxs-lookup"><span data-stu-id="aab42-1069">id#</span></span> 
- <span data-ttu-id="aab42-1070">id#</span><span class="sxs-lookup"><span data-stu-id="aab42-1070">ids#</span></span> 
- <span data-ttu-id="aab42-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="aab42-1071">idcard card#</span></span> 
- <span data-ttu-id="aab42-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="aab42-1072">idcard cards#</span></span> 
- <span data-ttu-id="aab42-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="aab42-1073">idcard#</span></span> 
- <span data-ttu-id="aab42-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="aab42-1074">identification card#</span></span> 
- <span data-ttu-id="aab42-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="aab42-1075">identification cards#</span></span> 
- <span data-ttu-id="aab42-1076">id#</span><span class="sxs-lookup"><span data-stu-id="aab42-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="aab42-1077">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="aab42-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1078">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1078">Format</span></span>

<span data-ttu-id="aab42-1079">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1080">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1080">Pattern</span></span>

<span data-ttu-id="aab42-1081">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1082">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1082">Checksum</span></span>

<span data-ttu-id="aab42-1083">否</span><span class="sxs-lookup"><span data-stu-id="aab42-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1084">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1084">Definition</span></span>

<span data-ttu-id="aab42-1085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1086">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1087">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1088">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="aab42-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="aab42-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="aab42-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="aab42-1090">personal health number</span></span>
- <span data-ttu-id="aab42-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="aab42-1091">patient information</span></span>
- <span data-ttu-id="aab42-1092">health services</span><span class="sxs-lookup"><span data-stu-id="aab42-1092">health services</span></span>
- <span data-ttu-id="aab42-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="aab42-1093">speciality services</span></span>
- <span data-ttu-id="aab42-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="aab42-1094">automobile accident</span></span>
- <span data-ttu-id="aab42-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="aab42-1095">patient hospital</span></span>
- <span data-ttu-id="aab42-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="aab42-1096">psychiatrist</span></span>
- <span data-ttu-id="aab42-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="aab42-1097">workers compensation</span></span>
- <span data-ttu-id="aab42-1098">障碍</span><span class="sxs-lookup"><span data-stu-id="aab42-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="aab42-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1100">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1100">Format</span></span>

<span data-ttu-id="aab42-1101">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1102">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1102">Pattern</span></span>

<span data-ttu-id="aab42-1103">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1104">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1104">Checksum</span></span>

<span data-ttu-id="aab42-1105">否</span><span class="sxs-lookup"><span data-stu-id="aab42-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1106">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1106">Definition</span></span>

<span data-ttu-id="aab42-1107">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1108">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1109">找到 Keyword_canada_passport_number 或 Keyword_passport 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1110">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="aab42-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="aab42-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="aab42-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="aab42-1112">canadian citizenship</span></span>
- <span data-ttu-id="aab42-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="aab42-1113">canadian passport</span></span>
- <span data-ttu-id="aab42-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="aab42-1114">passport application</span></span>
- <span data-ttu-id="aab42-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="aab42-1115">passport photos</span></span>
- <span data-ttu-id="aab42-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="aab42-1116">certified translator</span></span>
- <span data-ttu-id="aab42-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="aab42-1117">canadian citizens</span></span>
- <span data-ttu-id="aab42-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="aab42-1118">processing times</span></span>
- <span data-ttu-id="aab42-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="aab42-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="aab42-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-1120">Keyword_passport</span></span>

- <span data-ttu-id="aab42-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="aab42-1121">Passport Number</span></span>
- <span data-ttu-id="aab42-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="aab42-1122">Passport No</span></span>
- <span data-ttu-id="aab42-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-1123">Passport #</span></span>
- <span data-ttu-id="aab42-1124">登记卡#</span><span class="sxs-lookup"><span data-stu-id="aab42-1124">Passport#</span></span>
- <span data-ttu-id="aab42-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="aab42-1125">PassportID</span></span>
- <span data-ttu-id="aab42-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="aab42-1126">Passportno</span></span>
- <span data-ttu-id="aab42-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-1127">passportnumber</span></span>
- <span data-ttu-id="aab42-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-1128">パスポート</span></span>
- <span data-ttu-id="aab42-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-1129">パスポート番号</span></span>
- <span data-ttu-id="aab42-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-1130">パスポートのNum</span></span>
- <span data-ttu-id="aab42-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="aab42-1131">パスポート＃</span></span>
- <span data-ttu-id="aab42-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="aab42-1132">Numéro de passeport</span></span>
- <span data-ttu-id="aab42-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="aab42-1133">Passeport n °</span></span>
- <span data-ttu-id="aab42-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="aab42-1134">Passeport Non</span></span>
- <span data-ttu-id="aab42-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="aab42-1135">Passeport #</span></span>
- <span data-ttu-id="aab42-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="aab42-1136">Passeport#</span></span>
- <span data-ttu-id="aab42-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="aab42-1137">PasseportNon</span></span>
- <span data-ttu-id="aab42-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="aab42-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="aab42-1139">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="aab42-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1140">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1140">Format</span></span>

<span data-ttu-id="aab42-1141">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1142">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1142">Pattern</span></span>

<span data-ttu-id="aab42-1143">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1144">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1144">Checksum</span></span>

<span data-ttu-id="aab42-1145">否</span><span class="sxs-lookup"><span data-stu-id="aab42-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1146">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1146">Definition</span></span>

<span data-ttu-id="aab42-1147">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-1148">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="aab42-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1149">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="aab42-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="aab42-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="aab42-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="aab42-1151">social insurance number</span></span>
- <span data-ttu-id="aab42-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="aab42-1152">health information act</span></span>
- <span data-ttu-id="aab42-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="aab42-1153">income tax information</span></span>
- <span data-ttu-id="aab42-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="aab42-1154">manitoba health</span></span>
- <span data-ttu-id="aab42-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="aab42-1155">health registration</span></span>
- <span data-ttu-id="aab42-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="aab42-1156">prescription purchases</span></span>
- <span data-ttu-id="aab42-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="aab42-1157">benefit eligibility</span></span>
- <span data-ttu-id="aab42-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="aab42-1158">personal health</span></span>
- <span data-ttu-id="aab42-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="aab42-1159">power of attorney</span></span>
- <span data-ttu-id="aab42-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="aab42-1160">registration number</span></span>
- <span data-ttu-id="aab42-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="aab42-1161">personal health number</span></span>
- <span data-ttu-id="aab42-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="aab42-1162">practitioner referral</span></span>
- <span data-ttu-id="aab42-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="aab42-1163">wellness professional</span></span>
- <span data-ttu-id="aab42-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="aab42-1164">patient referral</span></span>
- <span data-ttu-id="aab42-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="aab42-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="aab42-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="aab42-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="aab42-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="aab42-1167">Nunavut</span></span>
- <span data-ttu-id="aab42-1168">省</span><span class="sxs-lookup"><span data-stu-id="aab42-1168">Quebec</span></span>
- <span data-ttu-id="aab42-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="aab42-1169">Northwest Territories</span></span>
- <span data-ttu-id="aab42-1170">省</span><span class="sxs-lookup"><span data-stu-id="aab42-1170">Ontario</span></span>
- <span data-ttu-id="aab42-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="aab42-1171">British Columbia</span></span>
- <span data-ttu-id="aab42-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="aab42-1172">Alberta</span></span>
- <span data-ttu-id="aab42-1173">彻</span><span class="sxs-lookup"><span data-stu-id="aab42-1173">Saskatchewan</span></span>
- <span data-ttu-id="aab42-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="aab42-1174">Manitoba</span></span>
- <span data-ttu-id="aab42-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="aab42-1175">Yukon</span></span>
- <span data-ttu-id="aab42-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="aab42-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="aab42-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="aab42-1177">New Brunswick</span></span>
- <span data-ttu-id="aab42-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="aab42-1178">Nova Scotia</span></span>
- <span data-ttu-id="aab42-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="aab42-1179">Prince Edward Island</span></span>
- <span data-ttu-id="aab42-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="aab42-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="aab42-1181">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1182">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1182">Format</span></span>

<span data-ttu-id="aab42-1183">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="aab42-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1184">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1184">Pattern</span></span>

<span data-ttu-id="aab42-1185">格式</span><span class="sxs-lookup"><span data-stu-id="aab42-1185">Formatted:</span></span>
- <span data-ttu-id="aab42-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1186">Three digits</span></span> 
- <span data-ttu-id="aab42-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="aab42-1187">A hyphen or space</span></span> 
- <span data-ttu-id="aab42-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1188">Three digits</span></span> 
- <span data-ttu-id="aab42-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="aab42-1189">A hyphen or space</span></span> 
- <span data-ttu-id="aab42-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1190">Three digits</span></span>

<span data-ttu-id="aab42-1191">未格式化：9个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1192">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1192">Checksum</span></span>

<span data-ttu-id="aab42-1193">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1194">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1194">Definition</span></span>

<span data-ttu-id="aab42-1195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1196">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1197">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="aab42-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="aab42-1198">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="aab42-1199">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="aab42-1200">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="aab42-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1201">The checksum passes.</span></span>

<span data-ttu-id="aab42-1202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1203">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1204">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="aab42-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1206">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="aab42-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="aab42-1207">Keyword_sin</span></span>

- <span data-ttu-id="aab42-1208">sin</span><span class="sxs-lookup"><span data-stu-id="aab42-1208">sin</span></span> 
- <span data-ttu-id="aab42-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="aab42-1209">social insurance</span></span> 
- <span data-ttu-id="aab42-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="aab42-1211">罪</span><span class="sxs-lookup"><span data-stu-id="aab42-1211">sins</span></span> 
- <span data-ttu-id="aab42-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="aab42-1212">ssn</span></span> 
- <span data-ttu-id="aab42-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="aab42-1213">ssns</span></span> 
- <span data-ttu-id="aab42-1214">social security</span><span class="sxs-lookup"><span data-stu-id="aab42-1214">social security</span></span> 
- <span data-ttu-id="aab42-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="aab42-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="aab42-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-1216">national identification number</span></span> 
- <span data-ttu-id="aab42-1217">national id</span><span class="sxs-lookup"><span data-stu-id="aab42-1217">national id</span></span> 
- <span data-ttu-id="aab42-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="aab42-1218">sin#</span></span> 
- <span data-ttu-id="aab42-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="aab42-1219">soc ins</span></span> 
- <span data-ttu-id="aab42-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="aab42-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="aab42-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="aab42-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="aab42-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="aab42-1222">driver's license</span></span> 
- <span data-ttu-id="aab42-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="aab42-1223">drivers license</span></span> 
- <span data-ttu-id="aab42-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="aab42-1224">driver's licence</span></span> 
- <span data-ttu-id="aab42-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="aab42-1225">drivers licence</span></span> 
- <span data-ttu-id="aab42-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="aab42-1226">DOB</span></span> 
- <span data-ttu-id="aab42-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="aab42-1227">Birthdate</span></span> 
- <span data-ttu-id="aab42-1228">一定</span><span class="sxs-lookup"><span data-stu-id="aab42-1228">Birthday</span></span> 
- <span data-ttu-id="aab42-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="aab42-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="aab42-1230">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1231">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1231">Format</span></span>

<span data-ttu-id="aab42-1232">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1233">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1233">Pattern</span></span>

<span data-ttu-id="aab42-1234">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="aab42-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="aab42-1235">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-1235">1-2 digits</span></span> 
- <span data-ttu-id="aab42-1236">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-1236">A period</span></span> 
- <span data-ttu-id="aab42-1237">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-1237">Three digits</span></span> 
- <span data-ttu-id="aab42-1238">一个点 </span><span class="sxs-lookup"><span data-stu-id="aab42-1238">A period</span></span> 
- <span data-ttu-id="aab42-1239">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-1239">Three digits</span></span> 
- <span data-ttu-id="aab42-1240">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="aab42-1240">A dash</span></span> 
- <span data-ttu-id="aab42-1241">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1242">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1242">Checksum</span></span>

<span data-ttu-id="aab42-1243">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1244">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1244">Definition</span></span>

<span data-ttu-id="aab42-1245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1246">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1247">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="aab42-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1248">The checksum passes.</span></span>

<span data-ttu-id="aab42-1249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1250">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1252">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="aab42-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="aab42-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="aab42-1254">National Identification Number</span></span> 
- <span data-ttu-id="aab42-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-1255">Identity card</span></span> 
- <span data-ttu-id="aab42-1256">ID</span><span class="sxs-lookup"><span data-stu-id="aab42-1256">ID</span></span> 
- <span data-ttu-id="aab42-1257">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-1257">Identification</span></span> 
- <span data-ttu-id="aab42-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="aab42-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="aab42-1259">以</span><span class="sxs-lookup"><span data-stu-id="aab42-1259">RUN</span></span> 
- <span data-ttu-id="aab42-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="aab42-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="aab42-1261">墨守成规</span><span class="sxs-lookup"><span data-stu-id="aab42-1261">RUT</span></span> 
- <span data-ttu-id="aab42-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="aab42-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="aab42-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="aab42-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="aab42-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="aab42-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="aab42-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="aab42-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="aab42-1266">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1267">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1267">Format</span></span>

<span data-ttu-id="aab42-1268">18 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1269">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1269">Pattern</span></span>

<span data-ttu-id="aab42-1270">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-1270">18 digits:</span></span>
- <span data-ttu-id="aab42-1271">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="aab42-1272">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="aab42-1273">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="aab42-1274">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1275">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1275">Checksum</span></span>

<span data-ttu-id="aab42-1276">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1277">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1277">Definition</span></span>

<span data-ttu-id="aab42-1278">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1279">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1280">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="aab42-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1281">The checksum passes.</span></span>

<span data-ttu-id="aab42-1282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1283">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1285">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="aab42-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="aab42-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="aab42-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="aab42-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="aab42-1288">台湾</span><span class="sxs-lookup"><span data-stu-id="aab42-1288">PRC</span></span> 
- <span data-ttu-id="aab42-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="aab42-1289">National Identification Card</span></span> 
- <span data-ttu-id="aab42-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="aab42-1290">身份证</span></span> 
- <span data-ttu-id="aab42-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="aab42-1291">居民 身份证</span></span> 
- <span data-ttu-id="aab42-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="aab42-1292">居民身份证</span></span> 
- <span data-ttu-id="aab42-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="aab42-1293">鉴定</span></span> 
- <span data-ttu-id="aab42-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-1294">身分證</span></span> 
- <span data-ttu-id="aab42-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-1295">居民 身份證</span></span>
- <span data-ttu-id="aab42-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="aab42-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="aab42-1297">信用卡号</span><span class="sxs-lookup"><span data-stu-id="aab42-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1298">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1298">Format</span></span>

<span data-ttu-id="aab42-1299">14到16个数字，可以是格式化或无格式（dddddddddddddddd），并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="aab42-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1300">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1300">Pattern</span></span>

<span data-ttu-id="aab42-1301">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="aab42-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1302">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1302">Checksum</span></span>

<span data-ttu-id="aab42-1303">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1304">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1304">Definition</span></span>

<span data-ttu-id="aab42-1305">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1306">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1307">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-1307">One of the following is true:</span></span>
    - <span data-ttu-id="aab42-1308">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="aab42-1309">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="aab42-1310">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="aab42-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1311">The checksum passes.</span></span>

<span data-ttu-id="aab42-1312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1313">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1315">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="aab42-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="aab42-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="aab42-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="aab42-1317">card verification</span></span>
- <span data-ttu-id="aab42-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-1318">card identification number</span></span>
- <span data-ttu-id="aab42-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="aab42-1319">cvn</span></span>
- <span data-ttu-id="aab42-1320">cid</span><span class="sxs-lookup"><span data-stu-id="aab42-1320">cid</span></span>
- <span data-ttu-id="aab42-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="aab42-1321">cvc2</span></span>
- <span data-ttu-id="aab42-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="aab42-1322">cvv2</span></span>
- <span data-ttu-id="aab42-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="aab42-1323">pin block</span></span>
- <span data-ttu-id="aab42-1324">security code</span><span class="sxs-lookup"><span data-stu-id="aab42-1324">security code</span></span>
- <span data-ttu-id="aab42-1325">security number</span><span class="sxs-lookup"><span data-stu-id="aab42-1325">security number</span></span>
- <span data-ttu-id="aab42-1326">security no</span><span class="sxs-lookup"><span data-stu-id="aab42-1326">security no</span></span>
- <span data-ttu-id="aab42-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="aab42-1327">issue number</span></span>
- <span data-ttu-id="aab42-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="aab42-1328">issue no</span></span>
- <span data-ttu-id="aab42-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="aab42-1329">cryptogramme</span></span>
- <span data-ttu-id="aab42-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="aab42-1330">numéro de sécurité</span></span>
- <span data-ttu-id="aab42-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="aab42-1331">numero de securite</span></span>
- <span data-ttu-id="aab42-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="aab42-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="aab42-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="aab42-1334">prüfziffer</span></span>
- <span data-ttu-id="aab42-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="aab42-1335">prufziffer</span></span>
- <span data-ttu-id="aab42-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="aab42-1336">sicherheits Kode</span></span>
- <span data-ttu-id="aab42-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="aab42-1337">sicherheitscode</span></span>
- <span data-ttu-id="aab42-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="aab42-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1339">verfalldatum</span></span>
- <span data-ttu-id="aab42-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="aab42-1340">codice di verifica</span></span>
- <span data-ttu-id="aab42-1341">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1341">cod.</span></span> <span data-ttu-id="aab42-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1342">sicurezza</span></span>
- <span data-ttu-id="aab42-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1343">cod sicurezza</span></span>
- <span data-ttu-id="aab42-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aab42-1344">n autorizzazione</span></span>
- <span data-ttu-id="aab42-1345">código</span><span class="sxs-lookup"><span data-stu-id="aab42-1345">código</span></span>
- <span data-ttu-id="aab42-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="aab42-1346">codigo</span></span>
- <span data-ttu-id="aab42-1347">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1347">cod.</span></span> <span data-ttu-id="aab42-1348">seg</span><span class="sxs-lookup"><span data-stu-id="aab42-1348">seg</span></span>
- <span data-ttu-id="aab42-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="aab42-1349">cod seg</span></span>
- <span data-ttu-id="aab42-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1350">código de segurança</span></span>
- <span data-ttu-id="aab42-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1351">codigo de seguranca</span></span>
- <span data-ttu-id="aab42-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1352">codigo de segurança</span></span>
- <span data-ttu-id="aab42-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1353">código de seguranca</span></span>
- <span data-ttu-id="aab42-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="aab42-1354">cód.</span></span> <span data-ttu-id="aab42-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1355">segurança</span></span>
- <span data-ttu-id="aab42-1356">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1356">cod.</span></span> <span data-ttu-id="aab42-1357">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="aab42-1357">seguranca cod.</span></span> <span data-ttu-id="aab42-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1358">segurança</span></span>
- <span data-ttu-id="aab42-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="aab42-1359">cód.</span></span> <span data-ttu-id="aab42-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1360">seguranca</span></span>
- <span data-ttu-id="aab42-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1361">cód segurança</span></span>
- <span data-ttu-id="aab42-1362">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="aab42-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1363">cód seguranca</span></span>
- <span data-ttu-id="aab42-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="aab42-1364">número de verificação</span></span>
- <span data-ttu-id="aab42-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="aab42-1365">numero de verificacao</span></span>
- <span data-ttu-id="aab42-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="aab42-1366">ablauf</span></span>
- <span data-ttu-id="aab42-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="aab42-1367">gültig bis</span></span>
- <span data-ttu-id="aab42-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="aab42-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="aab42-1369">gultig bis</span></span>
- <span data-ttu-id="aab42-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="aab42-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="aab42-1371">scadenza</span></span>
- <span data-ttu-id="aab42-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="aab42-1372">data scad</span></span>
- <span data-ttu-id="aab42-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="aab42-1373">fecha de expiracion</span></span>
- <span data-ttu-id="aab42-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="aab42-1374">fecha de venc</span></span>
- <span data-ttu-id="aab42-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="aab42-1375">vencimiento</span></span>
- <span data-ttu-id="aab42-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="aab42-1376">válido hasta</span></span>
- <span data-ttu-id="aab42-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="aab42-1377">valido hasta</span></span>
- <span data-ttu-id="aab42-1378">vto</span><span class="sxs-lookup"><span data-stu-id="aab42-1378">vto</span></span>
- <span data-ttu-id="aab42-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="aab42-1379">data de expiração</span></span>
- <span data-ttu-id="aab42-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="aab42-1380">data de expiracao</span></span>
- <span data-ttu-id="aab42-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="aab42-1381">data em que expira</span></span>
- <span data-ttu-id="aab42-1382">validade</span><span class="sxs-lookup"><span data-stu-id="aab42-1382">validade</span></span>
- <span data-ttu-id="aab42-1383">valor</span><span class="sxs-lookup"><span data-stu-id="aab42-1383">valor</span></span>
- <span data-ttu-id="aab42-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="aab42-1384">vencimento</span></span>
- <span data-ttu-id="aab42-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="aab42-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="aab42-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="aab42-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="aab42-1387">amex</span><span class="sxs-lookup"><span data-stu-id="aab42-1387">amex</span></span>
- <span data-ttu-id="aab42-1388">american express</span><span class="sxs-lookup"><span data-stu-id="aab42-1388">american express</span></span>
- <span data-ttu-id="aab42-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="aab42-1389">americanexpress</span></span>
- <span data-ttu-id="aab42-1390">反之</span><span class="sxs-lookup"><span data-stu-id="aab42-1390">Visa</span></span>
- <span data-ttu-id="aab42-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="aab42-1391">mastercard</span></span>
- <span data-ttu-id="aab42-1392">Master Card</span><span class="sxs-lookup"><span data-stu-id="aab42-1392">master card</span></span>
- <span data-ttu-id="aab42-1393">emc</span><span class="sxs-lookup"><span data-stu-id="aab42-1393">mc</span></span> 
- <span data-ttu-id="aab42-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="aab42-1394">mastercards</span></span>
- <span data-ttu-id="aab42-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1395">master cards</span></span>
- <span data-ttu-id="aab42-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="aab42-1396">diner's Club</span></span>
- <span data-ttu-id="aab42-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="aab42-1397">diners club</span></span>
- <span data-ttu-id="aab42-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="aab42-1398">dinersclub</span></span>
- <span data-ttu-id="aab42-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="aab42-1399">discover card</span></span>
- <span data-ttu-id="aab42-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="aab42-1400">discovercard</span></span>
- <span data-ttu-id="aab42-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1401">discover cards</span></span>
- <span data-ttu-id="aab42-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="aab42-1402">JCB</span></span>
- <span data-ttu-id="aab42-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="aab42-1403">japanese card bureau</span></span>
- <span data-ttu-id="aab42-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="aab42-1404">carte blanche</span></span>
- <span data-ttu-id="aab42-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="aab42-1405">carteblanche</span></span>
- <span data-ttu-id="aab42-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="aab42-1406">credit card</span></span>
- <span data-ttu-id="aab42-1407">收件人#</span><span class="sxs-lookup"><span data-stu-id="aab42-1407">cc#</span></span>
- <span data-ttu-id="aab42-1408">cc #：</span><span class="sxs-lookup"><span data-stu-id="aab42-1408">cc#:</span></span>
- <span data-ttu-id="aab42-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="aab42-1409">expiration date</span></span>
- <span data-ttu-id="aab42-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="aab42-1410">exp date</span></span>
- <span data-ttu-id="aab42-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="aab42-1411">expiry date</span></span>
- <span data-ttu-id="aab42-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="aab42-1412">date d’expiration</span></span>
- <span data-ttu-id="aab42-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="aab42-1413">date d'exp</span></span>
- <span data-ttu-id="aab42-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="aab42-1414">date expiration</span></span>
- <span data-ttu-id="aab42-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="aab42-1415">bank card</span></span>
- <span data-ttu-id="aab42-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1416">bankcard</span></span>
- <span data-ttu-id="aab42-1417">card number</span><span class="sxs-lookup"><span data-stu-id="aab42-1417">card number</span></span>
- <span data-ttu-id="aab42-1418">card num</span><span class="sxs-lookup"><span data-stu-id="aab42-1418">card num</span></span>
- <span data-ttu-id="aab42-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-1419">cardnumber</span></span>
- <span data-ttu-id="aab42-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1420">cardnumbers</span></span>
- <span data-ttu-id="aab42-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1421">card numbers</span></span>
- <span data-ttu-id="aab42-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1422">creditcard</span></span>
- <span data-ttu-id="aab42-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1423">credit cards</span></span>
- <span data-ttu-id="aab42-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1424">creditcards</span></span>
- <span data-ttu-id="aab42-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="aab42-1425">ccn</span></span>
- <span data-ttu-id="aab42-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="aab42-1426">card holder</span></span>
- <span data-ttu-id="aab42-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="aab42-1427">cardholder</span></span>
- <span data-ttu-id="aab42-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="aab42-1428">card holders</span></span>
- <span data-ttu-id="aab42-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="aab42-1429">cardholders</span></span>
- <span data-ttu-id="aab42-1430">check card</span><span class="sxs-lookup"><span data-stu-id="aab42-1430">check card</span></span>
- <span data-ttu-id="aab42-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1431">checkcard</span></span>
- <span data-ttu-id="aab42-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1432">check cards</span></span>
- <span data-ttu-id="aab42-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1433">checkcards</span></span>
- <span data-ttu-id="aab42-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="aab42-1434">debit card</span></span>
- <span data-ttu-id="aab42-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1435">debitcard</span></span>
- <span data-ttu-id="aab42-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1436">debit cards</span></span>
- <span data-ttu-id="aab42-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1437">debitcards</span></span>
- <span data-ttu-id="aab42-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="aab42-1438">atm card</span></span>
- <span data-ttu-id="aab42-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1439">atmcard</span></span>
- <span data-ttu-id="aab42-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1440">atm cards</span></span>
- <span data-ttu-id="aab42-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1441">atmcards</span></span>
- <span data-ttu-id="aab42-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="aab42-1442">enroute</span></span>
- <span data-ttu-id="aab42-1443">en route</span><span class="sxs-lookup"><span data-stu-id="aab42-1443">en route</span></span>
- <span data-ttu-id="aab42-1444">card type</span><span class="sxs-lookup"><span data-stu-id="aab42-1444">card type</span></span>
- <span data-ttu-id="aab42-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="aab42-1445">carte bancaire</span></span>
- <span data-ttu-id="aab42-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="aab42-1446">carte de crédit</span></span>
- <span data-ttu-id="aab42-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="aab42-1447">carte de credit</span></span>
- <span data-ttu-id="aab42-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1448">numéro de carte</span></span>
- <span data-ttu-id="aab42-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1449">numero de carte</span></span>
- <span data-ttu-id="aab42-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1450">nº de la carte</span></span>
- <span data-ttu-id="aab42-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1451">nº de carte</span></span>
- <span data-ttu-id="aab42-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="aab42-1452">kreditkarte</span></span>
- <span data-ttu-id="aab42-1453">karte</span><span class="sxs-lookup"><span data-stu-id="aab42-1453">karte</span></span>
- <span data-ttu-id="aab42-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="aab42-1454">karteninhaber</span></span>
- <span data-ttu-id="aab42-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="aab42-1455">karteninhabers</span></span>
- <span data-ttu-id="aab42-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="aab42-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="aab42-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="aab42-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="aab42-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="aab42-1458">kreditkartentyp</span></span>
- <span data-ttu-id="aab42-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="aab42-1459">eigentümername</span></span>
- <span data-ttu-id="aab42-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="aab42-1460">kartennr</span></span> 
- <span data-ttu-id="aab42-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1461">kartennummer</span></span>
- <span data-ttu-id="aab42-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1462">kreditkartennummer</span></span>
- <span data-ttu-id="aab42-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="aab42-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1464">carta di credito</span></span>
- <span data-ttu-id="aab42-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1465">carta credito</span></span>
- <span data-ttu-id="aab42-1466">carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1466">carta</span></span>
- <span data-ttu-id="aab42-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1467">n carta</span></span>
- <span data-ttu-id="aab42-1468">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="aab42-1468">nr.</span></span> <span data-ttu-id="aab42-1469">carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1469">carta</span></span>
- <span data-ttu-id="aab42-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1470">nr carta</span></span>
- <span data-ttu-id="aab42-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1471">numero carta</span></span>
- <span data-ttu-id="aab42-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1472">numero della carta</span></span>
- <span data-ttu-id="aab42-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1473">numero di carta</span></span>
- <span data-ttu-id="aab42-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1474">tarjeta credito</span></span>
- <span data-ttu-id="aab42-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1475">tarjeta de credito</span></span>
- <span data-ttu-id="aab42-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1476">tarjeta crédito</span></span>
- <span data-ttu-id="aab42-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="aab42-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="aab42-1478">tarjeta de atm</span></span>
- <span data-ttu-id="aab42-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="aab42-1479">tarjeta atm</span></span>
- <span data-ttu-id="aab42-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1480">tarjeta debito</span></span>
- <span data-ttu-id="aab42-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1481">tarjeta de debito</span></span>
- <span data-ttu-id="aab42-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1482">tarjeta débito</span></span>
- <span data-ttu-id="aab42-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1483">tarjeta de débito</span></span>
- <span data-ttu-id="aab42-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1484">nº de tarjeta</span></span>
- <span data-ttu-id="aab42-1485">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1485">no.</span></span> <span data-ttu-id="aab42-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1486">de tarjeta</span></span>
- <span data-ttu-id="aab42-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1487">no de tarjeta</span></span>
- <span data-ttu-id="aab42-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1488">numero de tarjeta</span></span>
- <span data-ttu-id="aab42-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1489">número de tarjeta</span></span>
- <span data-ttu-id="aab42-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="aab42-1490">tarjeta no</span></span>
- <span data-ttu-id="aab42-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="aab42-1491">tarjetahabiente</span></span>
- <span data-ttu-id="aab42-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1492">cartão de crédito</span></span>
- <span data-ttu-id="aab42-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1493">cartão de credito</span></span>
- <span data-ttu-id="aab42-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1494">cartao de crédito</span></span>
- <span data-ttu-id="aab42-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1495">cartao de credito</span></span>
- <span data-ttu-id="aab42-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1496">cartão de débito</span></span>
- <span data-ttu-id="aab42-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1497">cartao de débito</span></span>
- <span data-ttu-id="aab42-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1498">cartão de debito</span></span>
- <span data-ttu-id="aab42-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1499">cartao de debito</span></span>
- <span data-ttu-id="aab42-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="aab42-1500">débito automático</span></span>
- <span data-ttu-id="aab42-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="aab42-1501">debito automatico</span></span>
- <span data-ttu-id="aab42-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1502">número do cartão</span></span>
- <span data-ttu-id="aab42-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1503">numero do cartão</span></span> 
- <span data-ttu-id="aab42-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1504">número do cartao</span></span>
- <span data-ttu-id="aab42-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1505">numero do cartao</span></span>
- <span data-ttu-id="aab42-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1506">número de cartão</span></span>
- <span data-ttu-id="aab42-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1507">numero de cartão</span></span>
- <span data-ttu-id="aab42-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1508">número de cartao</span></span>
- <span data-ttu-id="aab42-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1509">numero de cartao</span></span>
- <span data-ttu-id="aab42-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1510">nº do cartão</span></span>
- <span data-ttu-id="aab42-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1511">nº do cartao</span></span>
- <span data-ttu-id="aab42-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="aab42-1512">nº.</span></span> <span data-ttu-id="aab42-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1513">do cartão</span></span>
- <span data-ttu-id="aab42-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1514">no do cartão</span></span>
- <span data-ttu-id="aab42-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1515">no do cartao</span></span>
- <span data-ttu-id="aab42-1516">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1516">no.</span></span> <span data-ttu-id="aab42-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1517">do cartão</span></span>
- <span data-ttu-id="aab42-1518">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1518">no.</span></span> <span data-ttu-id="aab42-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="aab42-1520">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1521">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1521">Format</span></span>

<span data-ttu-id="aab42-1522">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1523">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1523">Pattern</span></span>

<span data-ttu-id="aab42-1524">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1525">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1525">Checksum</span></span>

<span data-ttu-id="aab42-1526">否</span><span class="sxs-lookup"><span data-stu-id="aab42-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1527">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1527">Definition</span></span>

<span data-ttu-id="aab42-1528">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1529">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1530">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-1531">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="aab42-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="aab42-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-1533">Croatian identity card</span></span>
- <span data-ttu-id="aab42-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="aab42-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="aab42-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="aab42-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1536">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1536">Format</span></span>

<span data-ttu-id="aab42-1537">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1538">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1538">Pattern</span></span>

<span data-ttu-id="aab42-1539">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-1539">11 digits:</span></span>
- <span data-ttu-id="aab42-1540">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1540">10 digits</span></span> 
- <span data-ttu-id="aab42-1541">最后一个数字是用于国际数据交换目的的校验位，字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1542">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1542">Checksum</span></span>

<span data-ttu-id="aab42-1543">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1544">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1544">Definition</span></span>

<span data-ttu-id="aab42-1545">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1546">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1547">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="aab42-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1548">The checksum passes.</span></span>

<span data-ttu-id="aab42-1549">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1550">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1552">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="aab42-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="aab42-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="aab42-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="aab42-1554">Personal Identification Number</span></span>
- <span data-ttu-id="aab42-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="aab42-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="aab42-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="aab42-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="aab42-1557">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="aab42-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1558">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1558">Format</span></span>

<span data-ttu-id="aab42-1559">9个带可选正斜杠（旧格式）的数字，带可选正斜杠的10个数字（新的格式）</span><span class="sxs-lookup"><span data-stu-id="aab42-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1560">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1560">Pattern</span></span>

<span data-ttu-id="aab42-1561">9个数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="aab42-1562">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1562">Nine digits</span></span>

<span data-ttu-id="aab42-1563">或</span><span class="sxs-lookup"><span data-stu-id="aab42-1563">OR</span></span>

- <span data-ttu-id="aab42-1564">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="aab42-1565">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="aab42-1565">A forward slash</span></span>
- <span data-ttu-id="aab42-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1566">Three digits</span></span>

<span data-ttu-id="aab42-1567">10个数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-1567">10 digits (new format):</span></span>
- <span data-ttu-id="aab42-1568">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1568">10 digits</span></span>

<span data-ttu-id="aab42-1569">或</span><span class="sxs-lookup"><span data-stu-id="aab42-1569">OR</span></span>

- <span data-ttu-id="aab42-1570">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="aab42-1571">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="aab42-1571">A forward slash</span></span> 
- <span data-ttu-id="aab42-1572">四个数字，其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1573">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1573">Checksum</span></span>

<span data-ttu-id="aab42-1574">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1575">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1575">Definition</span></span>

<span data-ttu-id="aab42-1576">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-1577">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="aab42-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="aab42-1579">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1579">Keywords</span></span>

- <span data-ttu-id="aab42-1580">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="aab42-1580">czech personal identity number</span></span>
- <span data-ttu-id="aab42-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="aab42-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="aab42-1582">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1583">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1583">Format</span></span>

<span data-ttu-id="aab42-1584">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="aab42-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1585">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1585">Pattern</span></span>

<span data-ttu-id="aab42-1586">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-1586">10 digits:</span></span>
- <span data-ttu-id="aab42-1587">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="aab42-1588">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-1588">A hyphen</span></span> 
- <span data-ttu-id="aab42-1589">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1590">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1590">Checksum</span></span>

<span data-ttu-id="aab42-1591">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1592">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1592">Definition</span></span>

<span data-ttu-id="aab42-1593">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-1594">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="aab42-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-1596">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="aab42-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="aab42-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="aab42-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="aab42-1598">Personal Identification Number</span></span>
- <span data-ttu-id="aab42-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="aab42-1599">CPR</span></span>
- <span data-ttu-id="aab42-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="aab42-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="aab42-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="aab42-1602">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1603">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1603">Format</span></span>

<span data-ttu-id="aab42-1604">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1605">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1605">Pattern</span></span>

<span data-ttu-id="aab42-1606">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="aab42-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="aab42-1607">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="aab42-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="aab42-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="aab42-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="aab42-1609">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1610">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1610">Checksum</span></span>

<span data-ttu-id="aab42-1611">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1612">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1612">Definition</span></span>

<span data-ttu-id="aab42-1613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1614">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-1616">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1616">Keywords</span></span>

<span data-ttu-id="aab42-1617">无</span><span class="sxs-lookup"><span data-stu-id="aab42-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="aab42-1618">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="aab42-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1619">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1619">Format</span></span>

<span data-ttu-id="aab42-1620">16 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1621">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1621">Pattern</span></span>

<span data-ttu-id="aab42-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1623">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1623">Checksum</span></span>

<span data-ttu-id="aab42-1624">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1625">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1625">Definition</span></span>

<span data-ttu-id="aab42-1626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1627">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1628">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="aab42-1629">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="aab42-1630">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="aab42-1631">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="aab42-1632">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="aab42-1633">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="aab42-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1635">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="aab42-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="aab42-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="aab42-1637">account number</span><span class="sxs-lookup"><span data-stu-id="aab42-1637">account number</span></span> 
- <span data-ttu-id="aab42-1638">card number</span><span class="sxs-lookup"><span data-stu-id="aab42-1638">card number</span></span> 
- <span data-ttu-id="aab42-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="aab42-1639">card no.</span></span> 
- <span data-ttu-id="aab42-1640">security number</span><span class="sxs-lookup"><span data-stu-id="aab42-1640">security number</span></span> 
- <span data-ttu-id="aab42-1641">收件人#</span><span class="sxs-lookup"><span data-stu-id="aab42-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="aab42-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="aab42-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="aab42-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="aab42-1643">acct nbr</span></span> 
- <span data-ttu-id="aab42-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="aab42-1644">acct num</span></span> 
- <span data-ttu-id="aab42-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="aab42-1645">acct no</span></span> 
- <span data-ttu-id="aab42-1646">american express</span><span class="sxs-lookup"><span data-stu-id="aab42-1646">american express</span></span> 
- <span data-ttu-id="aab42-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="aab42-1647">americanexpress</span></span> 
- <span data-ttu-id="aab42-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="aab42-1648">americano espresso</span></span> 
- <span data-ttu-id="aab42-1649">amex</span><span class="sxs-lookup"><span data-stu-id="aab42-1649">amex</span></span> 
- <span data-ttu-id="aab42-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="aab42-1650">atm card</span></span> 
- <span data-ttu-id="aab42-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1651">atm cards</span></span> 
- <span data-ttu-id="aab42-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1652">atm kaart</span></span> 
- <span data-ttu-id="aab42-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1653">atmcard</span></span> 
- <span data-ttu-id="aab42-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1654">atmcards</span></span> 
- <span data-ttu-id="aab42-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1655">atmkaart</span></span> 
- <span data-ttu-id="aab42-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="aab42-1656">atmkaarten</span></span> 
- <span data-ttu-id="aab42-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="aab42-1657">bancontact</span></span> 
- <span data-ttu-id="aab42-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="aab42-1658">bank card</span></span> 
- <span data-ttu-id="aab42-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1659">bankkaart</span></span> 
- <span data-ttu-id="aab42-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="aab42-1660">card holder</span></span> 
- <span data-ttu-id="aab42-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="aab42-1661">card holders</span></span> 
- <span data-ttu-id="aab42-1662">card num</span><span class="sxs-lookup"><span data-stu-id="aab42-1662">card num</span></span> 
- <span data-ttu-id="aab42-1663">card number</span><span class="sxs-lookup"><span data-stu-id="aab42-1663">card number</span></span> 
- <span data-ttu-id="aab42-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1664">card numbers</span></span> 
- <span data-ttu-id="aab42-1665">card type</span><span class="sxs-lookup"><span data-stu-id="aab42-1665">card type</span></span> 
- <span data-ttu-id="aab42-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="aab42-1666">cardano numerico</span></span> 
- <span data-ttu-id="aab42-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="aab42-1667">cardholder</span></span> 
- <span data-ttu-id="aab42-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="aab42-1668">cardholders</span></span> 
- <span data-ttu-id="aab42-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-1669">cardnumber</span></span> 
- <span data-ttu-id="aab42-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="aab42-1670">cardnumbers</span></span> 
- <span data-ttu-id="aab42-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="aab42-1671">carta bianca</span></span> 
- <span data-ttu-id="aab42-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1672">carta credito</span></span> 
- <span data-ttu-id="aab42-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1673">carta di credito</span></span> 
- <span data-ttu-id="aab42-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1674">cartao de credito</span></span> 
- <span data-ttu-id="aab42-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1675">cartao de crédito</span></span> 
- <span data-ttu-id="aab42-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1676">cartao de debito</span></span> 
- <span data-ttu-id="aab42-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1677">cartao de débito</span></span> 
- <span data-ttu-id="aab42-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="aab42-1678">carte bancaire</span></span> 
- <span data-ttu-id="aab42-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="aab42-1679">carte blanche</span></span> 
- <span data-ttu-id="aab42-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="aab42-1680">carte bleue</span></span> 
- <span data-ttu-id="aab42-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="aab42-1681">carte de credit</span></span> 
- <span data-ttu-id="aab42-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="aab42-1682">carte de crédit</span></span> 
- <span data-ttu-id="aab42-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1683">carte di credito</span></span> 
- <span data-ttu-id="aab42-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="aab42-1684">carteblanche</span></span> 
- <span data-ttu-id="aab42-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1685">cartão de credito</span></span> 
- <span data-ttu-id="aab42-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="aab42-1686">cartão de crédito</span></span> 
- <span data-ttu-id="aab42-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1687">cartão de debito</span></span> 
- <span data-ttu-id="aab42-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="aab42-1688">cartão de débito</span></span> 
- <span data-ttu-id="aab42-1689">cb</span><span class="sxs-lookup"><span data-stu-id="aab42-1689">cb</span></span> 
- <span data-ttu-id="aab42-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="aab42-1690">ccn</span></span> 
- <span data-ttu-id="aab42-1691">check card</span><span class="sxs-lookup"><span data-stu-id="aab42-1691">check card</span></span> 
- <span data-ttu-id="aab42-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1692">check cards</span></span> 
- <span data-ttu-id="aab42-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1693">checkcard</span></span>
- <span data-ttu-id="aab42-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1694">checkcards</span></span> 
- <span data-ttu-id="aab42-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1695">chequekaart</span></span> 
- <span data-ttu-id="aab42-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="aab42-1696">cirrus</span></span> 
- <span data-ttu-id="aab42-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="aab42-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="aab42-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1698">controlekaart</span></span> 
- <span data-ttu-id="aab42-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="aab42-1699">controlekaarten</span></span> 
- <span data-ttu-id="aab42-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="aab42-1700">credit card</span></span> 
- <span data-ttu-id="aab42-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1701">credit cards</span></span> 
- <span data-ttu-id="aab42-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1702">creditcard</span></span> 
- <span data-ttu-id="aab42-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1703">creditcards</span></span> 
- <span data-ttu-id="aab42-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1704">debetkaart</span></span> 
- <span data-ttu-id="aab42-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="aab42-1705">debetkaarten</span></span> 
- <span data-ttu-id="aab42-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="aab42-1706">debit card</span></span> 
- <span data-ttu-id="aab42-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1707">debit cards</span></span> 
- <span data-ttu-id="aab42-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="aab42-1708">debitcard</span></span> 
- <span data-ttu-id="aab42-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="aab42-1709">debitcards</span></span> 
- <span data-ttu-id="aab42-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="aab42-1710">debito automatico</span></span> 
- <span data-ttu-id="aab42-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="aab42-1711">diners club</span></span> 
- <span data-ttu-id="aab42-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="aab42-1712">dinersclub</span></span> 
- <span data-ttu-id="aab42-1713">确定</span><span class="sxs-lookup"><span data-stu-id="aab42-1713">discover</span></span> 
- <span data-ttu-id="aab42-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="aab42-1714">discover card</span></span> 
- <span data-ttu-id="aab42-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1715">discover cards</span></span> 
- <span data-ttu-id="aab42-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="aab42-1716">discovercard</span></span> 
- <span data-ttu-id="aab42-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="aab42-1717">discovercards</span></span> 
- <span data-ttu-id="aab42-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="aab42-1718">débito automático</span></span>
- <span data-ttu-id="aab42-1719">edc</span><span class="sxs-lookup"><span data-stu-id="aab42-1719">edc</span></span> 
- <span data-ttu-id="aab42-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="aab42-1720">eigentümername</span></span> 
- <span data-ttu-id="aab42-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="aab42-1721">european debit card</span></span> 
- <span data-ttu-id="aab42-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1722">hoofdkaart</span></span> 
- <span data-ttu-id="aab42-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="aab42-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="aab42-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="aab42-1724">in viaggio</span></span> 
- <span data-ttu-id="aab42-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="aab42-1725">japanese card bureau</span></span> 
- <span data-ttu-id="aab42-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="aab42-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="aab42-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="aab42-1727">jcb</span></span> 
- <span data-ttu-id="aab42-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="aab42-1728">kaart</span></span> 
- <span data-ttu-id="aab42-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="aab42-1729">kaart num</span></span> 
- <span data-ttu-id="aab42-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="aab42-1730">kaartaantal</span></span> 
- <span data-ttu-id="aab42-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="aab42-1731">kaartaantallen</span></span> 
- <span data-ttu-id="aab42-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="aab42-1732">kaarthouder</span></span> 
- <span data-ttu-id="aab42-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="aab42-1733">kaarthouders</span></span> 
- <span data-ttu-id="aab42-1734">karte</span><span class="sxs-lookup"><span data-stu-id="aab42-1734">karte</span></span>  
- <span data-ttu-id="aab42-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="aab42-1735">karteninhaber</span></span> 
- <span data-ttu-id="aab42-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="aab42-1736">karteninhabers</span></span>
- <span data-ttu-id="aab42-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="aab42-1737">kartennr</span></span> 
- <span data-ttu-id="aab42-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1738">kartennummer</span></span> 
- <span data-ttu-id="aab42-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="aab42-1739">kreditkarte</span></span> 
- <span data-ttu-id="aab42-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="aab42-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="aab42-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="aab42-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="aab42-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="aab42-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="aab42-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="aab42-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="aab42-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="aab42-1745">maestro</span></span> 
- <span data-ttu-id="aab42-1746">Master Card</span><span class="sxs-lookup"><span data-stu-id="aab42-1746">master card</span></span> 
- <span data-ttu-id="aab42-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="aab42-1747">master cards</span></span> 
- <span data-ttu-id="aab42-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="aab42-1748">mastercard</span></span> 
- <span data-ttu-id="aab42-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="aab42-1749">mastercards</span></span> 
- <span data-ttu-id="aab42-1750">emc</span><span class="sxs-lookup"><span data-stu-id="aab42-1750">mc</span></span> 
- <span data-ttu-id="aab42-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="aab42-1751">mister cash</span></span> 
- <span data-ttu-id="aab42-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1752">n carta</span></span> 
- <span data-ttu-id="aab42-1753">carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1753">carta</span></span> 
- <span data-ttu-id="aab42-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1754">no de tarjeta</span></span> 
- <span data-ttu-id="aab42-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1755">no do cartao</span></span> 
- <span data-ttu-id="aab42-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1756">no do cartão</span></span> 
- <span data-ttu-id="aab42-1757">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1757">no.</span></span> <span data-ttu-id="aab42-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1758">de tarjeta</span></span> 
- <span data-ttu-id="aab42-1759">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1759">no.</span></span> <span data-ttu-id="aab42-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1760">do cartao</span></span> 
- <span data-ttu-id="aab42-1761">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1761">no.</span></span> <span data-ttu-id="aab42-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1762">do cartão</span></span> 
- <span data-ttu-id="aab42-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1763">nr carta</span></span> 
- <span data-ttu-id="aab42-1764">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="aab42-1764">nr.</span></span> <span data-ttu-id="aab42-1765">carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1765">carta</span></span> 
- <span data-ttu-id="aab42-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1766">numeri di scheda</span></span> 
- <span data-ttu-id="aab42-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1767">numero carta</span></span> 
- <span data-ttu-id="aab42-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1768">numero de cartao</span></span> 
- <span data-ttu-id="aab42-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1769">numero de carte</span></span> 
- <span data-ttu-id="aab42-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1770">numero de cartão</span></span> 
- <span data-ttu-id="aab42-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1771">numero de tarjeta</span></span>
- <span data-ttu-id="aab42-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1772">numero della carta</span></span> 
- <span data-ttu-id="aab42-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1773">numero di carta</span></span> 
- <span data-ttu-id="aab42-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1774">numero di scheda</span></span> 
- <span data-ttu-id="aab42-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1775">numero do cartao</span></span> 
- <span data-ttu-id="aab42-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1776">numero do cartão</span></span> 
- <span data-ttu-id="aab42-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1777">numéro de carte</span></span> 
- <span data-ttu-id="aab42-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="aab42-1778">nº carta</span></span> 
- <span data-ttu-id="aab42-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1779">nº de carte</span></span> 
- <span data-ttu-id="aab42-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="aab42-1780">nº de la carte</span></span> 
- <span data-ttu-id="aab42-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="aab42-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1782">nº do cartao</span></span> 
- <span data-ttu-id="aab42-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1783">nº do cartão</span></span> 
- <span data-ttu-id="aab42-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="aab42-1784">nº.</span></span> <span data-ttu-id="aab42-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1785">do cartão</span></span> 
- <span data-ttu-id="aab42-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1786">número de cartao</span></span> 
- <span data-ttu-id="aab42-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="aab42-1787">número de cartão</span></span> 
- <span data-ttu-id="aab42-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="aab42-1788">número de tarjeta</span></span> 
- <span data-ttu-id="aab42-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="aab42-1789">número do cartao</span></span> 
- <span data-ttu-id="aab42-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="aab42-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="aab42-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="aab42-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="aab42-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="aab42-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="aab42-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="aab42-1793">scheda della banca</span></span> 
- <span data-ttu-id="aab42-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="aab42-1794">scheda di controllo</span></span> 
- <span data-ttu-id="aab42-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1795">scheda di debito</span></span> 
- <span data-ttu-id="aab42-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="aab42-1796">scheda matrice</span></span> 
- <span data-ttu-id="aab42-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="aab42-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="aab42-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="aab42-1798">schede di controllo</span></span> 
- <span data-ttu-id="aab42-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1799">schede di debito</span></span> 
- <span data-ttu-id="aab42-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="aab42-1800">schede matrici</span></span> 
- <span data-ttu-id="aab42-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="aab42-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="aab42-1802">scoprono le schede</span></span> 
- <span data-ttu-id="aab42-1803">solo</span><span class="sxs-lookup"><span data-stu-id="aab42-1803">solo</span></span> 
- <span data-ttu-id="aab42-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1804">supporti di scheda</span></span> 
- <span data-ttu-id="aab42-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1805">supporto di scheda</span></span> 
- <span data-ttu-id="aab42-1806">器</span><span class="sxs-lookup"><span data-stu-id="aab42-1806">switch</span></span> 
- <span data-ttu-id="aab42-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="aab42-1807">tarjeta atm</span></span> 
- <span data-ttu-id="aab42-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1808">tarjeta credito</span></span> 
- <span data-ttu-id="aab42-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="aab42-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="aab42-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="aab42-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="aab42-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="aab42-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="aab42-1812">tarjeta debito</span></span> 
- <span data-ttu-id="aab42-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="aab42-1813">tarjeta no</span></span>
- <span data-ttu-id="aab42-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="aab42-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="aab42-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1815">tipo della scheda</span></span> 
- <span data-ttu-id="aab42-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="aab42-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="aab42-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1817">scheda</span></span> 
- <span data-ttu-id="aab42-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="aab42-1818">v pay</span></span> 
- <span data-ttu-id="aab42-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="aab42-1819">v-pay</span></span> 
- <span data-ttu-id="aab42-1820">反之</span><span class="sxs-lookup"><span data-stu-id="aab42-1820">visa</span></span> 
- <span data-ttu-id="aab42-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="aab42-1821">visa plus</span></span> 
- <span data-ttu-id="aab42-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="aab42-1822">visa electron</span></span> 
- <span data-ttu-id="aab42-1823">visto</span><span class="sxs-lookup"><span data-stu-id="aab42-1823">visto</span></span> 
- <span data-ttu-id="aab42-1824">visum</span><span class="sxs-lookup"><span data-stu-id="aab42-1824">visum</span></span> 
- <span data-ttu-id="aab42-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="aab42-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="aab42-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="aab42-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="aab42-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-1827">card identification number</span></span>
- <span data-ttu-id="aab42-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="aab42-1828">card verification</span></span> 
- <span data-ttu-id="aab42-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="aab42-1829">cardi la verifica</span></span> 
- <span data-ttu-id="aab42-1830">cid</span><span class="sxs-lookup"><span data-stu-id="aab42-1830">cid</span></span> 
- <span data-ttu-id="aab42-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="aab42-1831">cod seg</span></span> 
- <span data-ttu-id="aab42-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1832">cod seguranca</span></span> 
- <span data-ttu-id="aab42-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1833">cod segurança</span></span> 
- <span data-ttu-id="aab42-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1834">cod sicurezza</span></span> 
- <span data-ttu-id="aab42-1835">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1835">cod.</span></span> <span data-ttu-id="aab42-1836">seg</span><span class="sxs-lookup"><span data-stu-id="aab42-1836">seg</span></span> 
- <span data-ttu-id="aab42-1837">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1837">cod.</span></span> <span data-ttu-id="aab42-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1838">seguranca</span></span> 
- <span data-ttu-id="aab42-1839">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1839">cod.</span></span> <span data-ttu-id="aab42-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1840">segurança</span></span> 
- <span data-ttu-id="aab42-1841">货.</span><span class="sxs-lookup"><span data-stu-id="aab42-1841">cod.</span></span> <span data-ttu-id="aab42-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1842">sicurezza</span></span> 
- <span data-ttu-id="aab42-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="aab42-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="aab42-1844">codice di verifica</span></span> 
- <span data-ttu-id="aab42-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="aab42-1845">codigo</span></span> 
- <span data-ttu-id="aab42-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="aab42-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1847">codigo de segurança</span></span> 
- <span data-ttu-id="aab42-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="aab42-1848">crittogramma</span></span> 
- <span data-ttu-id="aab42-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="aab42-1849">cryptogram</span></span> 
- <span data-ttu-id="aab42-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="aab42-1850">cryptogramme</span></span> 
- <span data-ttu-id="aab42-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="aab42-1851">cv2</span></span> 
- <span data-ttu-id="aab42-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="aab42-1852">cvc</span></span> 
- <span data-ttu-id="aab42-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="aab42-1853">cvc2</span></span> 
- <span data-ttu-id="aab42-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="aab42-1854">cvn</span></span> 
- <span data-ttu-id="aab42-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="aab42-1855">cvv</span></span> 
- <span data-ttu-id="aab42-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="aab42-1856">cvv2</span></span> 
- <span data-ttu-id="aab42-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1857">cód seguranca</span></span> 
- <span data-ttu-id="aab42-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1858">cód segurança</span></span> 
- <span data-ttu-id="aab42-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="aab42-1859">cód.</span></span> <span data-ttu-id="aab42-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1860">seguranca</span></span> 
- <span data-ttu-id="aab42-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="aab42-1861">cód.</span></span> <span data-ttu-id="aab42-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1862">segurança</span></span> 
- <span data-ttu-id="aab42-1863">código</span><span class="sxs-lookup"><span data-stu-id="aab42-1863">código</span></span> 
- <span data-ttu-id="aab42-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="aab42-1864">código de seguranca</span></span> 
- <span data-ttu-id="aab42-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="aab42-1865">código de segurança</span></span> 
- <span data-ttu-id="aab42-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="aab42-1866">de kaart controle</span></span> 
- <span data-ttu-id="aab42-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="aab42-1867">geeft nr uit</span></span> 
- <span data-ttu-id="aab42-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="aab42-1868">issue no</span></span> 
- <span data-ttu-id="aab42-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="aab42-1869">issue number</span></span> 
- <span data-ttu-id="aab42-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="aab42-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="aab42-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="aab42-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="aab42-1873">kwestieaantal</span></span> 
- <span data-ttu-id="aab42-1874">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1874">no.</span></span> <span data-ttu-id="aab42-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="aab42-1875">dell'edizione</span></span> 
- <span data-ttu-id="aab42-1876">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-1876">no.</span></span> <span data-ttu-id="aab42-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1877">di sicurezza</span></span> 
- <span data-ttu-id="aab42-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="aab42-1878">numero de securite</span></span> 
- <span data-ttu-id="aab42-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="aab42-1879">numero de verificacao</span></span> 
- <span data-ttu-id="aab42-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="aab42-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="aab42-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="aab42-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="aab42-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="aab42-1882">scheda</span></span> 
- <span data-ttu-id="aab42-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="aab42-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="aab42-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="aab42-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="aab42-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="aab42-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="aab42-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aab42-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="aab42-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="aab42-1887">número de verificação</span></span> 
- <span data-ttu-id="aab42-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="aab42-1888">perno il blocco</span></span> 
- <span data-ttu-id="aab42-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="aab42-1889">pin block</span></span> 
- <span data-ttu-id="aab42-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="aab42-1890">prufziffer</span></span> 
- <span data-ttu-id="aab42-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="aab42-1891">prüfziffer</span></span> 
- <span data-ttu-id="aab42-1892">security code</span><span class="sxs-lookup"><span data-stu-id="aab42-1892">security code</span></span> 
- <span data-ttu-id="aab42-1893">security no</span><span class="sxs-lookup"><span data-stu-id="aab42-1893">security no</span></span> 
- <span data-ttu-id="aab42-1894">security number</span><span class="sxs-lookup"><span data-stu-id="aab42-1894">security number</span></span> 
- <span data-ttu-id="aab42-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="aab42-1895">sicherheits kode</span></span> 
- <span data-ttu-id="aab42-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="aab42-1896">sicherheitscode</span></span> 
- <span data-ttu-id="aab42-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="aab42-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="aab42-1898">speldblok</span></span> 
- <span data-ttu-id="aab42-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="aab42-1899">veiligheid nr</span></span> 
- <span data-ttu-id="aab42-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="aab42-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="aab42-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="aab42-1901">veiligheidscode</span></span> 
- <span data-ttu-id="aab42-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="aab42-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="aab42-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="aab42-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="aab42-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="aab42-1905">ablauf</span></span> 
- <span data-ttu-id="aab42-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="aab42-1906">data de expiracao</span></span> 
- <span data-ttu-id="aab42-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="aab42-1907">data de expiração</span></span> 
- <span data-ttu-id="aab42-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="aab42-1908">data del exp</span></span> 
- <span data-ttu-id="aab42-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="aab42-1909">data di exp</span></span> 
- <span data-ttu-id="aab42-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="aab42-1910">data di scadenza</span></span> 
- <span data-ttu-id="aab42-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="aab42-1911">data em que expira</span></span> 
- <span data-ttu-id="aab42-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="aab42-1912">data scad</span></span> 
- <span data-ttu-id="aab42-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="aab42-1913">data scadenza</span></span> 
- <span data-ttu-id="aab42-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="aab42-1914">date de validité</span></span> 
- <span data-ttu-id="aab42-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="aab42-1915">datum afloop</span></span> 
- <span data-ttu-id="aab42-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="aab42-1916">datum van exp</span></span> 
- <span data-ttu-id="aab42-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="aab42-1917">de afloop</span></span> 
- <span data-ttu-id="aab42-1918">espira</span><span class="sxs-lookup"><span data-stu-id="aab42-1918">espira</span></span> 
- <span data-ttu-id="aab42-1919">espira</span><span class="sxs-lookup"><span data-stu-id="aab42-1919">espira</span></span> 
- <span data-ttu-id="aab42-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="aab42-1920">exp date</span></span> 
- <span data-ttu-id="aab42-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="aab42-1921">exp datum</span></span> 
- <span data-ttu-id="aab42-1922">时间</span><span class="sxs-lookup"><span data-stu-id="aab42-1922">expiration</span></span> 
- <span data-ttu-id="aab42-1923">何时</span><span class="sxs-lookup"><span data-stu-id="aab42-1923">expire</span></span> 
- <span data-ttu-id="aab42-1924">不久</span><span class="sxs-lookup"><span data-stu-id="aab42-1924">expires</span></span> 
- <span data-ttu-id="aab42-1925">过期</span><span class="sxs-lookup"><span data-stu-id="aab42-1925">expiry</span></span> 
- <span data-ttu-id="aab42-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="aab42-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="aab42-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="aab42-1927">fecha de venc</span></span> 
- <span data-ttu-id="aab42-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="aab42-1928">gultig bis</span></span> 
- <span data-ttu-id="aab42-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="aab42-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="aab42-1930">gültig bis</span></span> 
- <span data-ttu-id="aab42-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="aab42-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="aab42-1932">la scadenza</span></span> 
- <span data-ttu-id="aab42-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="aab42-1933">scadenza</span></span> 
- <span data-ttu-id="aab42-1934">valable</span><span class="sxs-lookup"><span data-stu-id="aab42-1934">valable</span></span> 
- <span data-ttu-id="aab42-1935">validade</span><span class="sxs-lookup"><span data-stu-id="aab42-1935">validade</span></span> 
- <span data-ttu-id="aab42-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="aab42-1936">valido hasta</span></span> 
- <span data-ttu-id="aab42-1937">valor</span><span class="sxs-lookup"><span data-stu-id="aab42-1937">valor</span></span> 
- <span data-ttu-id="aab42-1938">venc</span><span class="sxs-lookup"><span data-stu-id="aab42-1938">venc</span></span> 
- <span data-ttu-id="aab42-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="aab42-1939">vencimento</span></span> 
- <span data-ttu-id="aab42-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="aab42-1940">vencimiento</span></span> 
- <span data-ttu-id="aab42-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="aab42-1941">verloopt</span></span> 
- <span data-ttu-id="aab42-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="aab42-1942">vervaldag</span></span> 
- <span data-ttu-id="aab42-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="aab42-1943">vervaldatum</span></span> 
- <span data-ttu-id="aab42-1944">vto</span><span class="sxs-lookup"><span data-stu-id="aab42-1944">vto</span></span> 
- <span data-ttu-id="aab42-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="aab42-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="aab42-1946">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1946">EU Driver's License Number</span></span>

<span data-ttu-id="aab42-1947">若要了解详细信息，请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="aab42-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="aab42-1948">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-1948">EU National Identification Number</span></span>

<span data-ttu-id="aab42-1949">若要了解详细信息，请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="aab42-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="aab42-1950">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1950">EU Passport Number</span></span>

<span data-ttu-id="aab42-1951">若要了解详细信息，请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="aab42-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="aab42-1952">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="aab42-1953">若要了解详细信息，请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="aab42-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="aab42-1954">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="aab42-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="aab42-1955">若要了解详细信息，请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="aab42-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="aab42-1956">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1957">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1957">Format</span></span>

<span data-ttu-id="aab42-1958">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1959">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1959">Pattern</span></span>

<span data-ttu-id="aab42-1960">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="aab42-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="aab42-1961">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="aab42-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="aab42-1962">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="aab42-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="aab42-1963">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="aab42-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="aab42-1964">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1965">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1965">Checksum</span></span>

<span data-ttu-id="aab42-1966">是</span><span class="sxs-lookup"><span data-stu-id="aab42-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1967">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1967">Definition</span></span>

<span data-ttu-id="aab42-1968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1969">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1970">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="aab42-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-1972">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1972">Keywords</span></span>

- <span data-ttu-id="aab42-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="aab42-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="aab42-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="aab42-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="aab42-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="aab42-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="aab42-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="aab42-1976">Personbeteckning</span></span>
- <span data-ttu-id="aab42-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="aab42-1978">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="aab42-1978">Finland Passport Number</span></span>

<span data-ttu-id="aab42-1979">设置九个字母和数字的组合的组合九个字母和数字的组合：两个字母（不区分大小写）七个数字校验和无定义 DLP 策略是75% 确信它检测到这种类型的敏感信息，如果在300个字符的邻近性：正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-1980">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="aab42-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="aab42-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="aab42-1982">Keyword_finland_passport_number Passport Passi 的关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="aab42-1983">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-1984">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-1984">Format</span></span>

<span data-ttu-id="aab42-1985">12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-1986">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-1986">Pattern</span></span>

<span data-ttu-id="aab42-1987">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="aab42-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-1988">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-1988">Checksum</span></span>

<span data-ttu-id="aab42-1989">否</span><span class="sxs-lookup"><span data-stu-id="aab42-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-1990">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-1990">Definition</span></span>

<span data-ttu-id="aab42-1991">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-1992">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-1993">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="aab42-1994">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="aab42-1995">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-1996">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="aab42-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="aab42-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="aab42-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="aab42-1998">drivers licence</span></span>
- <span data-ttu-id="aab42-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="aab42-1999">drivers license</span></span>
- <span data-ttu-id="aab42-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2000">driving licence</span></span>
- <span data-ttu-id="aab42-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="aab42-2001">driving license</span></span>
- <span data-ttu-id="aab42-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="aab42-2002">permis de conduire</span></span>
- <span data-ttu-id="aab42-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="aab42-2003">licence number</span></span>
- <span data-ttu-id="aab42-2004">license number</span><span class="sxs-lookup"><span data-stu-id="aab42-2004">license number</span></span>
- <span data-ttu-id="aab42-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-2005">licence numbers</span></span>
- <span data-ttu-id="aab42-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="aab42-2007">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="aab42-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2008">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2008">Format</span></span>

<span data-ttu-id="aab42-2009">12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2010">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2010">Pattern</span></span>

<span data-ttu-id="aab42-2011">12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2012">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2012">Checksum</span></span>

<span data-ttu-id="aab42-2013">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2014">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2014">Definition</span></span>

<span data-ttu-id="aab42-2015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2016">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2017">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2017">Keywords</span></span>

<span data-ttu-id="aab42-2018">无</span><span class="sxs-lookup"><span data-stu-id="aab42-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="aab42-2019">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2020">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2020">Format</span></span>

<span data-ttu-id="aab42-2021">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2022">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2022">Pattern</span></span>

<span data-ttu-id="aab42-2023">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="aab42-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="aab42-2024">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2024">Two digits</span></span> 
- <span data-ttu-id="aab42-2025">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2026">五位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2027">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2027">Checksum</span></span>

<span data-ttu-id="aab42-2028">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2029">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2029">Definition</span></span>

<span data-ttu-id="aab42-2030">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2031">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2032">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2033">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="aab42-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-2034">Keyword_passport</span></span>

- <span data-ttu-id="aab42-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2035">Passport Number</span></span>
- <span data-ttu-id="aab42-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="aab42-2036">Passport No</span></span>
- <span data-ttu-id="aab42-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-2037">Passport #</span></span>
- <span data-ttu-id="aab42-2038">登记卡#</span><span class="sxs-lookup"><span data-stu-id="aab42-2038">Passport#</span></span>
- <span data-ttu-id="aab42-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="aab42-2039">PassportID</span></span>
- <span data-ttu-id="aab42-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="aab42-2040">Passportno</span></span>
- <span data-ttu-id="aab42-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-2041">passportnumber</span></span>
- <span data-ttu-id="aab42-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-2042">パスポート</span></span>
- <span data-ttu-id="aab42-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2043">パスポート番号</span></span>
- <span data-ttu-id="aab42-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-2044">パスポートのNum</span></span>
- <span data-ttu-id="aab42-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2045">パスポート ＃</span></span> 
- <span data-ttu-id="aab42-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="aab42-2046">Numéro de passeport</span></span>
- <span data-ttu-id="aab42-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="aab42-2047">Passeport n °</span></span>
- <span data-ttu-id="aab42-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="aab42-2048">Passeport Non</span></span>
- <span data-ttu-id="aab42-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="aab42-2049">Passeport #</span></span>
- <span data-ttu-id="aab42-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="aab42-2050">Passeport#</span></span>
- <span data-ttu-id="aab42-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="aab42-2051">PasseportNon</span></span>
- <span data-ttu-id="aab42-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="aab42-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="aab42-2053">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="aab42-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2054">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2054">Format</span></span>

<span data-ttu-id="aab42-2055">15 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2056">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2056">Pattern</span></span>

<span data-ttu-id="aab42-2057">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="aab42-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="aab42-2058">13位数，后跟一个空格，后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="aab42-2059">或</span><span class="sxs-lookup"><span data-stu-id="aab42-2059">or</span></span>
- <span data-ttu-id="aab42-2060">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2061">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2061">Checksum</span></span>

<span data-ttu-id="aab42-2062">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2063">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2063">Definition</span></span>

<span data-ttu-id="aab42-2064">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2065">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2066">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="aab42-2067">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2067">The checksum passes.</span></span>

<span data-ttu-id="aab42-2068">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2069">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2070">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="aab42-2071">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2072">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="aab42-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="aab42-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="aab42-2074">insee</span><span class="sxs-lookup"><span data-stu-id="aab42-2074">insee</span></span>
- <span data-ttu-id="aab42-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-2075">securité sociale</span></span>
- <span data-ttu-id="aab42-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-2076">securite sociale</span></span>
- <span data-ttu-id="aab42-2077">national id</span><span class="sxs-lookup"><span data-stu-id="aab42-2077">national id</span></span>
- <span data-ttu-id="aab42-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="aab42-2078">national identification</span></span>
- <span data-ttu-id="aab42-2079">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="aab42-2079">numéro d'identité</span></span>
- <span data-ttu-id="aab42-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="aab42-2080">no d'identité</span></span>
- <span data-ttu-id="aab42-2081">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-2081">no.</span></span> <span data-ttu-id="aab42-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="aab42-2082">d'identité</span></span>
- <span data-ttu-id="aab42-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="aab42-2083">numero d'identite</span></span>
- <span data-ttu-id="aab42-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="aab42-2084">no d'identite</span></span>
- <span data-ttu-id="aab42-2085">不。</span><span class="sxs-lookup"><span data-stu-id="aab42-2085">no.</span></span> <span data-ttu-id="aab42-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="aab42-2086">d'identite</span></span>
- <span data-ttu-id="aab42-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="aab42-2087">social security number</span></span>
- <span data-ttu-id="aab42-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="aab42-2088">social security code</span></span>
- <span data-ttu-id="aab42-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="aab42-2089">social insurance number</span></span>
- <span data-ttu-id="aab42-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="aab42-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="aab42-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="aab42-2091">d'identité nationale</span></span>
- <span data-ttu-id="aab42-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="aab42-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="aab42-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="aab42-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="aab42-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="aab42-2095">numéro de sécu</span></span>
- <span data-ttu-id="aab42-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="aab42-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="aab42-2097">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2098">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2098">Format</span></span>

<span data-ttu-id="aab42-2099">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="aab42-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2100">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2100">Pattern</span></span>

<span data-ttu-id="aab42-2101">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="aab42-2102">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2102">A digit or letter</span></span> 
- <span data-ttu-id="aab42-2103">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2103">Two digits</span></span> 
- <span data-ttu-id="aab42-2104">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2104">Six digits or letters</span></span> 
- <span data-ttu-id="aab42-2105">一位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2105">A digit</span></span> 
- <span data-ttu-id="aab42-2106">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2107">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2107">Checksum</span></span>

<span data-ttu-id="aab42-2108">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2109">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2109">Definition</span></span>

<span data-ttu-id="aab42-2110">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2111">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2112">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="aab42-2113">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="aab42-2114">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="aab42-2115">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="aab42-2116">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2117">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="aab42-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="aab42-2119">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2119">Führerschein</span></span>
- <span data-ttu-id="aab42-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2120">Fuhrerschein</span></span>
- <span data-ttu-id="aab42-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2121">Fuehrerschein</span></span>
- <span data-ttu-id="aab42-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="aab42-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="aab42-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="aab42-2125">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2125">Führerschein-</span></span> 
- <span data-ttu-id="aab42-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="aab42-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="aab42-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="aab42-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="aab42-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="aab42-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="aab42-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="aab42-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="aab42-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="aab42-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="aab42-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="aab42-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="aab42-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="aab42-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="aab42-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="aab42-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="aab42-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="aab42-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="aab42-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="aab42-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="aab42-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="aab42-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="aab42-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="aab42-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="aab42-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="aab42-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="aab42-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="aab42-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="aab42-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="aab42-2152">通讯</span><span class="sxs-lookup"><span data-stu-id="aab42-2152">DL</span></span> 
- <span data-ttu-id="aab42-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="aab42-2153">DLS</span></span>
- <span data-ttu-id="aab42-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-2154">Driv Lic</span></span> 
- <span data-ttu-id="aab42-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="aab42-2155">Driv Licen</span></span> 
- <span data-ttu-id="aab42-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="aab42-2156">Driv License</span></span>
- <span data-ttu-id="aab42-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2157">Driv Licenses</span></span> 
- <span data-ttu-id="aab42-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2158">Driv Licence</span></span> 
- <span data-ttu-id="aab42-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-2159">Driv Licences</span></span> 
- <span data-ttu-id="aab42-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-2160">Driv Lic</span></span> 
- <span data-ttu-id="aab42-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="aab42-2161">Driver Licen</span></span> 
- <span data-ttu-id="aab42-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="aab42-2162">Driver License</span></span> 
- <span data-ttu-id="aab42-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2163">Driver Licenses</span></span> 
- <span data-ttu-id="aab42-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2164">Driver Licence</span></span> 
- <span data-ttu-id="aab42-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-2165">Driver Licences</span></span> 
- <span data-ttu-id="aab42-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-2166">Drivers Lic</span></span> 
- <span data-ttu-id="aab42-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="aab42-2167">Drivers Licen</span></span> 
- <span data-ttu-id="aab42-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="aab42-2168">Drivers License</span></span> 
- <span data-ttu-id="aab42-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="aab42-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2170">Drivers Licence</span></span> 
- <span data-ttu-id="aab42-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-2171">Drivers Licences</span></span> 
- <span data-ttu-id="aab42-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-2172">Driver's Lic</span></span> 
- <span data-ttu-id="aab42-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="aab42-2173">Driver's Licen</span></span> 
- <span data-ttu-id="aab42-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="aab42-2174">Driver's License</span></span> 
- <span data-ttu-id="aab42-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="aab42-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2176">Driver's Licence</span></span> 
- <span data-ttu-id="aab42-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-2177">Driver's Licences</span></span> 
- <span data-ttu-id="aab42-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-2178">Driving Lic</span></span> 
- <span data-ttu-id="aab42-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="aab42-2179">Driving Licen</span></span> 
- <span data-ttu-id="aab42-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="aab42-2180">Driving License</span></span> 
- <span data-ttu-id="aab42-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2181">Driving Licenses</span></span> 
- <span data-ttu-id="aab42-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2182">Driving Licence</span></span> 
- <span data-ttu-id="aab42-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="aab42-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="aab42-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="aab42-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="aab42-2185">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="aab42-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="aab42-2188">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2188">No-Führerschein</span></span> 
- <span data-ttu-id="aab42-2189">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2190">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="aab42-2191">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2191">N-Führerschein</span></span> 
- <span data-ttu-id="aab42-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="aab42-2194">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="aab42-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="aab42-2197">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2197">No-Führerschein</span></span> 
- <span data-ttu-id="aab42-2198">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2199">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="aab42-2200">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2200">N-Führerschein</span></span> 
- <span data-ttu-id="aab42-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="aab42-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="aab42-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="aab42-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="aab42-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="aab42-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="aab42-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="aab42-2205">ausstellungsort</span></span>
- <span data-ttu-id="aab42-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="aab42-2206">ausstellende behöde</span></span>
- <span data-ttu-id="aab42-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="aab42-2207">ausstellende behorde</span></span>
- <span data-ttu-id="aab42-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="aab42-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="aab42-2209">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2210">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2210">Format</span></span>

<span data-ttu-id="aab42-2211">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2212">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2212">Pattern</span></span>

<span data-ttu-id="aab42-2213">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="aab42-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="aab42-2214">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="aab42-2215">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2215">Three digits</span></span> 
- <span data-ttu-id="aab42-2216">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="aab42-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="aab42-2217">一位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2218">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2218">Checksum</span></span>

<span data-ttu-id="aab42-2219">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2220">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2220">Definition</span></span>

<span data-ttu-id="aab42-2221">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2222">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2223">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="aab42-2224">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2224">The checksum passes.</span></span>

<span data-ttu-id="aab42-2225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2226">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2227">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="aab42-2228">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2229">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="aab42-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="aab42-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="aab42-2231">reisepass</span></span>
- <span data-ttu-id="aab42-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="aab42-2232">reisepasse</span></span>
- <span data-ttu-id="aab42-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2233">reisepassnummer</span></span>
- <span data-ttu-id="aab42-2234">登记卡</span><span class="sxs-lookup"><span data-stu-id="aab42-2234">passport</span></span>
- <span data-ttu-id="aab42-2235">passports</span><span class="sxs-lookup"><span data-stu-id="aab42-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="aab42-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="aab42-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="aab42-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-2237">geburtsdatum</span></span>
- <span data-ttu-id="aab42-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="aab42-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="aab42-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="aab42-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="aab42-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="aab42-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="aab42-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="aab42-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="aab42-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="aab42-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="aab42-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="aab42-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="aab42-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="aab42-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="aab42-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="aab42-2246">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2247">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2247">Format</span></span>

<span data-ttu-id="aab42-2248">自2010年11月1日起：九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="aab42-2249">从1年4月1987至31年10月2010：10位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2250">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2250">Pattern</span></span>

<span data-ttu-id="aab42-2251">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="aab42-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="aab42-2252">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2253">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2253">Eight digits</span></span>

<span data-ttu-id="aab42-2254">介于1年4月1987至 31 10 月2010：</span><span class="sxs-lookup"><span data-stu-id="aab42-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="aab42-2255">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2256">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2256">Checksum</span></span>

<span data-ttu-id="aab42-2257">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2258">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2258">Definition</span></span>

<span data-ttu-id="aab42-2259">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2260">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2261">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2262">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="aab42-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="aab42-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="aab42-2264">Identity Card</span></span>
- <span data-ttu-id="aab42-2265">ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2265">ID</span></span>
- <span data-ttu-id="aab42-2266">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-2266">Identification</span></span>
- <span data-ttu-id="aab42-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="aab42-2267">Personalausweis</span></span>
- <span data-ttu-id="aab42-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="aab42-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="aab42-2269">Ausweis</span></span>
- <span data-ttu-id="aab42-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="aab42-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="aab42-2271">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="aab42-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2272">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2272">Format</span></span>

<span data-ttu-id="aab42-2273">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="aab42-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2274">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2274">Pattern</span></span>

<span data-ttu-id="aab42-2275">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="aab42-2276">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="aab42-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="aab42-2277">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="aab42-2277">A dash</span></span> 
- <span data-ttu-id="aab42-2278">六位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2278">Six digits</span></span>

<span data-ttu-id="aab42-2279">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="aab42-2280">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="aab42-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="aab42-2281">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="aab42-2281">A dash</span></span> 
- <span data-ttu-id="aab42-2282">六位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2283">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2283">Checksum</span></span>

<span data-ttu-id="aab42-2284">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2285">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2285">Definition</span></span>

<span data-ttu-id="aab42-2286">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2287">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2288">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2289">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="aab42-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="aab42-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="aab42-2291">Greek identity Card</span></span>
- <span data-ttu-id="aab42-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="aab42-2292">Tautotita</span></span>
- <span data-ttu-id="aab42-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="aab42-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="aab42-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="aab42-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="aab42-2295">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="aab42-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2296">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2296">Format</span></span>

<span data-ttu-id="aab42-2297">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="aab42-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2298">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2298">Pattern</span></span>

<span data-ttu-id="aab42-2299">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="aab42-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="aab42-2300">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2301">六个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2301">Six digits</span></span> 
- <span data-ttu-id="aab42-2302">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="aab42-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2303">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2303">Checksum</span></span>

<span data-ttu-id="aab42-2304">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2305">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2305">Definition</span></span>

<span data-ttu-id="aab42-2306">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2307">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2308">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="aab42-2309">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2309">The checksum passes.</span></span>

<span data-ttu-id="aab42-2310">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2311">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2312">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2313">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="aab42-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="aab42-2315">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="aab42-2315">hong kong identity card</span></span>
- <span data-ttu-id="aab42-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="aab42-2316">HKIDC</span></span>
- <span data-ttu-id="aab42-2317">id card</span><span class="sxs-lookup"><span data-stu-id="aab42-2317">id card</span></span>
- <span data-ttu-id="aab42-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-2318">identity card</span></span>
- <span data-ttu-id="aab42-2319">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="aab42-2319">hk identity card</span></span>
- <span data-ttu-id="aab42-2320">香港 id</span><span class="sxs-lookup"><span data-stu-id="aab42-2320">hong kong id</span></span>
- <span data-ttu-id="aab42-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2321">香港身份證</span></span>
- <span data-ttu-id="aab42-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="aab42-2323">證</span><span class="sxs-lookup"><span data-stu-id="aab42-2323">身份證</span></span>
- <span data-ttu-id="aab42-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2324">身份証</span></span>
- <span data-ttu-id="aab42-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2325">身分證</span></span>
- <span data-ttu-id="aab42-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2326">身分証</span></span>
- <span data-ttu-id="aab42-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2327">香港身份証</span></span>
- <span data-ttu-id="aab42-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2328">香港身分證</span></span>
- <span data-ttu-id="aab42-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2329">香港身分証</span></span>
- <span data-ttu-id="aab42-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2330">香港身份證</span></span>
- <span data-ttu-id="aab42-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2331">香港居民身份證</span></span>
- <span data-ttu-id="aab42-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2332">香港居民身份証</span></span>
- <span data-ttu-id="aab42-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2333">香港居民身分證</span></span>
- <span data-ttu-id="aab42-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2334">香港居民身分証</span></span>
- <span data-ttu-id="aab42-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="aab42-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="aab42-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="aab42-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="aab42-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="aab42-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="aab42-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="aab42-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="aab42-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="aab42-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="aab42-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="aab42-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="aab42-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="aab42-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="aab42-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="aab42-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="aab42-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="aab42-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="aab42-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="aab42-2351">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="aab42-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2352">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2352">Format</span></span>

<span data-ttu-id="aab42-2353">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2354">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2354">Pattern</span></span>

<span data-ttu-id="aab42-2355">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2355">10 letters or digits:</span></span>
- <span data-ttu-id="aab42-2356">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2357">四位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2357">Four digits</span></span> 
- <span data-ttu-id="aab42-2358">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2359">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2359">Checksum</span></span>

<span data-ttu-id="aab42-2360">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2361">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2361">Definition</span></span>

<span data-ttu-id="aab42-2362">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2363">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2364">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="aab42-2365">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2366">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="aab42-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="aab42-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="aab42-2369">蛋糕</span><span class="sxs-lookup"><span data-stu-id="aab42-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="aab42-2370">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2371">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2371">Format</span></span>

<span data-ttu-id="aab42-2372">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="aab42-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2373">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2373">Pattern</span></span>

<span data-ttu-id="aab42-2374">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2374">12 digits:</span></span>
- <span data-ttu-id="aab42-2375">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2375">Four digits</span></span> 
- <span data-ttu-id="aab42-2376">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="aab42-2376">An optional space or dash</span></span> 
- <span data-ttu-id="aab42-2377">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2377">Four digits</span></span> 
- <span data-ttu-id="aab42-2378">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="aab42-2378">An optional space or dash</span></span> 
- <span data-ttu-id="aab42-2379">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2380">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2380">Checksum</span></span>

<span data-ttu-id="aab42-2381">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2382">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2382">Definition</span></span>

<span data-ttu-id="aab42-2383">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-2384">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="aab42-2385">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2385">The checksum passes.</span></span>
<span data-ttu-id="aab42-2386">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-2387">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="aab42-2388">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="aab42-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="aab42-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="aab42-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="aab42-2390">Aadhar</span></span>
- <span data-ttu-id="aab42-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="aab42-2391">Aadhaar</span></span>
- <span data-ttu-id="aab42-2392">UID</span><span class="sxs-lookup"><span data-stu-id="aab42-2392">UID</span></span>
- <span data-ttu-id="aab42-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="aab42-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="aab42-2394">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="aab42-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2395">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2395">Format</span></span>

<span data-ttu-id="aab42-2396">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="aab42-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2397">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2397">Pattern</span></span>

<span data-ttu-id="aab42-2398">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2398">16 digits:</span></span>
- <span data-ttu-id="aab42-2399">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-2399">Two-digit province code</span></span> 
- <span data-ttu-id="aab42-2400">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2400">A period (optional)</span></span> 
- <span data-ttu-id="aab42-2401">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="aab42-2402">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="aab42-2403">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2403">A period (optional)</span></span> 
- <span data-ttu-id="aab42-2404">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="aab42-2405">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2405">A period (optional)</span></span> 
- <span data-ttu-id="aab42-2406">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2407">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2407">Checksum</span></span>

<span data-ttu-id="aab42-2408">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2409">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2409">Definition</span></span>

<span data-ttu-id="aab42-2410">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2411">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2412">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="aab42-2413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2414">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2415">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="aab42-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="aab42-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="aab42-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="aab42-2417">KTP</span></span>
- <span data-ttu-id="aab42-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="aab42-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="aab42-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="aab42-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="aab42-2420">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="aab42-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2421">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2421">Format</span></span>

<span data-ttu-id="aab42-2422">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="aab42-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2423">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2423">Pattern</span></span>

<span data-ttu-id="aab42-2424">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="aab42-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="aab42-2425">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="aab42-2425">Two-letter country code</span></span>
- <span data-ttu-id="aab42-2426">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="aab42-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="aab42-2427">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="aab42-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="aab42-2428">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2428">1-3 letters or digits</span></span>

<span data-ttu-id="aab42-p135">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="aab42-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="aab42-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="aab42-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2432">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2432">Checksum</span></span>

<span data-ttu-id="aab42-2433">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2434">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2434">Definition</span></span>

<span data-ttu-id="aab42-2435">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2436">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2437">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2438">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2438">Keywords</span></span>

<span data-ttu-id="aab42-2439">无</span><span class="sxs-lookup"><span data-stu-id="aab42-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="aab42-2440">IP 地址</span><span class="sxs-lookup"><span data-stu-id="aab42-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2441">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="aab42-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="aab42-2442">IPv4:</span></span>
<span data-ttu-id="aab42-2443">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="aab42-2444">Ipv4</span><span class="sxs-lookup"><span data-stu-id="aab42-2444">IPv6:</span></span>
<span data-ttu-id="aab42-2445"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2446">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2447">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2447">Checksum</span></span>

<span data-ttu-id="aab42-2448">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2449">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2449">Definition</span></span>

<span data-ttu-id="aab42-2450">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2451">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2452">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="aab42-2453">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2454">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2455">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="aab42-2456">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2457">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2458">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2459">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="aab42-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="aab42-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="aab42-2461">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="aab42-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="aab42-2462">ip address</span></span> 
- <span data-ttu-id="aab42-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="aab42-2463">ip addresses</span></span>
- <span data-ttu-id="aab42-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="aab42-2464">internet protocol</span></span>
- <span data-ttu-id="aab42-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="aab42-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="aab42-2466">国际分类的 Diseases （ICD-10 CM）</span><span class="sxs-lookup"><span data-stu-id="aab42-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2467">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2467">Format</span></span>

<span data-ttu-id="aab42-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="aab42-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2469">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2469">Pattern</span></span>

<span data-ttu-id="aab42-2470">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2471">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2471">Checksum</span></span>

<span data-ttu-id="aab42-2472">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2473">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2473">Definition</span></span>

<span data-ttu-id="aab42-2474">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2475">找到 Dictionary_icd_10_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="aab42-2476">找到 Dictionary_icd_10_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="aab42-2477">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2478">找到 Dictionary_icd_10_ 更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="aab42-2479">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2479">Keywords</span></span>

<span data-ttu-id="aab42-2480">Dictionary_icd_10_updated 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="aab42-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="aab42-2481">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="aab42-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="aab42-2482">Dictionary_icd_10_codes 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="aab42-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="aab42-2483">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="aab42-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="aab42-2484">国际分类的 Diseases （ICD-9-CM）</span><span class="sxs-lookup"><span data-stu-id="aab42-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2485">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2485">Format</span></span>

<span data-ttu-id="aab42-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="aab42-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2487">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2487">Pattern</span></span>

<span data-ttu-id="aab42-2488">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2489">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2489">Checksum</span></span>

<span data-ttu-id="aab42-2490">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2491">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2491">Definition</span></span>

<span data-ttu-id="aab42-2492">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2493">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="aab42-2494">找到 Dictionary_icd_9_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="aab42-2495">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2496">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2497">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2497">Keywords</span></span>

<span data-ttu-id="aab42-2498">Dictionary_icd_9_updated 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="aab42-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="aab42-2499">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="aab42-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="aab42-2500">Dictionary_icd_9_codes 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="aab42-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="aab42-2501">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="aab42-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="aab42-2502">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2503">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2503">Format</span></span>

<span data-ttu-id="aab42-2504">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="aab42-2505">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="aab42-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="aab42-2506">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="aab42-2507">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="aab42-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2508">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2508">Pattern</span></span>

<span data-ttu-id="aab42-2509">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="aab42-2510">七个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2510">Seven digits</span></span> 
- <span data-ttu-id="aab42-2511">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="aab42-2512">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="aab42-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="aab42-2513">七个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2513">Seven digits</span></span> 
- <span data-ttu-id="aab42-2514">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="aab42-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="aab42-2515">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2516">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2516">Checksum</span></span>

<span data-ttu-id="aab42-2517">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2518">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2518">Definition</span></span>

<span data-ttu-id="aab42-2519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2520">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2521">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-2521">One of the following is true:</span></span>
    - <span data-ttu-id="aab42-2522">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="aab42-2523">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="aab42-2524">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2524">The checksum passes.</span></span>

<span data-ttu-id="aab42-2525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2526">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2527">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2528">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="aab42-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="aab42-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="aab42-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="aab42-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2531">PPS Number</span></span> 
- <span data-ttu-id="aab42-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="aab42-2532">PPS Num</span></span> 
- <span data-ttu-id="aab42-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2533">PPS No.</span></span> 
- <span data-ttu-id="aab42-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="aab42-2534">PPS #</span></span> 
- <span data-ttu-id="aab42-2535">.PPS#</span><span class="sxs-lookup"><span data-stu-id="aab42-2535">PPS#</span></span> 
- <span data-ttu-id="aab42-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="aab42-2536">PPSN</span></span> 
- <span data-ttu-id="aab42-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="aab42-2537">Public Services Card</span></span> 
- <span data-ttu-id="aab42-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="aab42-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="aab42-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="aab42-2539">Uimh.</span></span> <span data-ttu-id="aab42-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="aab42-2540">PSP</span></span> 
- <span data-ttu-id="aab42-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="aab42-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="aab42-2542">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2543">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2543">Format</span></span>

<span data-ttu-id="aab42-2544">13 位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2545">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2545">Pattern</span></span>

<span data-ttu-id="aab42-2546">格式</span><span class="sxs-lookup"><span data-stu-id="aab42-2546">Formatted:</span></span>
- <span data-ttu-id="aab42-2547">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2547">Two digits</span></span> 
- <span data-ttu-id="aab42-2548">破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-2548">A dash</span></span> 
- <span data-ttu-id="aab42-2549">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2549">Three digits</span></span> 
- <span data-ttu-id="aab42-2550">破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-2550">A dash</span></span> 
- <span data-ttu-id="aab42-2551">八位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2551">Eight digits</span></span>

<span data-ttu-id="aab42-2552">纯</span><span class="sxs-lookup"><span data-stu-id="aab42-2552">Unformatted:</span></span>
- <span data-ttu-id="aab42-2553">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2554">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2554">Checksum</span></span>

<span data-ttu-id="aab42-2555">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2556">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2556">Definition</span></span>

<span data-ttu-id="aab42-2557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2558">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2559">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2560">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="aab42-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="aab42-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2562">Bank Account Number</span></span> 
- <span data-ttu-id="aab42-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="aab42-2563">Bank Account</span></span> 
- <span data-ttu-id="aab42-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2564">Account Number</span></span> 
- <span data-ttu-id="aab42-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="aab42-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="aab42-2566">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2567">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2567">Format</span></span>

<span data-ttu-id="aab42-2568">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2569">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2569">Pattern</span></span>

<span data-ttu-id="aab42-2570">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2571">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2571">Checksum</span></span>

<span data-ttu-id="aab42-2572">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2573">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2573">Definition</span></span>

<span data-ttu-id="aab42-2574">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2575">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2576">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="aab42-2577">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2578">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="aab42-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="aab42-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="aab42-2580">מספר זהות</span></span> 
- <span data-ttu-id="aab42-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="aab42-2582">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2583">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2583">Format</span></span>

<span data-ttu-id="aab42-2584">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="aab42-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2585">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2585">Pattern</span></span>

- <span data-ttu-id="aab42-2586">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="aab42-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="aab42-2587">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2588">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-2589">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="aab42-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="aab42-2590">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2591">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2591">Checksum</span></span>

<span data-ttu-id="aab42-2592">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2593">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2593">Definition</span></span>

<span data-ttu-id="aab42-2594">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2595">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2596">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2597">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="aab42-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="aab42-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="aab42-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="aab42-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="aab42-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="aab42-2601">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2602">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2602">Format</span></span>

<span data-ttu-id="aab42-2603">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2604">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2604">Pattern</span></span>

<span data-ttu-id="aab42-2605">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="aab42-2605">Bank account number:</span></span>
- <span data-ttu-id="aab42-2606">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2606">Seven or eight digits</span></span>
- <span data-ttu-id="aab42-2607">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="aab42-2607">Bank account branch code:</span></span>
- <span data-ttu-id="aab42-2608">四位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2608">Four digits</span></span> 
- <span data-ttu-id="aab42-2609">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="aab42-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="aab42-2610">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2610">Three digits</span></span>

<span data-ttu-id="aab42-2611">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2611">Checksum</span></span>

<span data-ttu-id="aab42-2612">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2613">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2613">Definition</span></span>

<span data-ttu-id="aab42-2614">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2615">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2616">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="aab42-2617">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-2617">One of the following is true:</span></span>
- <span data-ttu-id="aab42-2618">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2619">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="aab42-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2621">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2622">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2623">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="aab42-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="aab42-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="aab42-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2625">Checking Account Number</span></span> 
- <span data-ttu-id="aab42-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="aab42-2626">Checking Account</span></span> 
- <span data-ttu-id="aab42-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-2627">Checking Account #</span></span> 
- <span data-ttu-id="aab42-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="aab42-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-2629">Checking Acct #</span></span> 
- <span data-ttu-id="aab42-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="aab42-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2631">Checking Account No.</span></span> 
- <span data-ttu-id="aab42-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2632">Bank Account Number</span></span> 
- <span data-ttu-id="aab42-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="aab42-2633">Bank Account</span></span> 
- <span data-ttu-id="aab42-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-2634">Bank Account #</span></span> 
- <span data-ttu-id="aab42-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="aab42-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-2636">Bank Acct #</span></span> 
- <span data-ttu-id="aab42-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="aab42-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2638">Bank Account No.</span></span> 
- <span data-ttu-id="aab42-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2639">Savings Account Number</span></span> 
- <span data-ttu-id="aab42-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="aab42-2640">Savings Account</span></span> 
- <span data-ttu-id="aab42-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-2641">Savings Account #</span></span> 
- <span data-ttu-id="aab42-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="aab42-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-2643">Savings Acct #</span></span> 
- <span data-ttu-id="aab42-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="aab42-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2645">Savings Account No.</span></span> 
- <span data-ttu-id="aab42-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2646">Debit Account Number</span></span> 
- <span data-ttu-id="aab42-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="aab42-2647">Debit Account</span></span> 
- <span data-ttu-id="aab42-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-2648">Debit Account #</span></span> 
- <span data-ttu-id="aab42-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="aab42-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-2650">Debit Acct #</span></span> 
- <span data-ttu-id="aab42-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="aab42-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2652">Debit Account No.</span></span> 
- <span data-ttu-id="aab42-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="aab42-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="aab42-2654">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="aab42-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="aab42-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="aab42-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="aab42-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="aab42-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="aab42-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="aab42-2657">口座番号の確認</span></span> 
- <span data-ttu-id="aab42-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2658">銀行口座番号</span></span> 
- <span data-ttu-id="aab42-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="aab42-2659">銀行口座</span></span> 
- <span data-ttu-id="aab42-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2660">銀行口座＃</span></span> 
- <span data-ttu-id="aab42-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="aab42-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="aab42-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="aab42-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="aab42-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2664">銀行口座番号</span></span>
- <span data-ttu-id="aab42-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="aab42-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="aab42-2666">預金口座</span></span> 
- <span data-ttu-id="aab42-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="aab42-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="aab42-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="aab42-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="aab42-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="aab42-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="aab42-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="aab42-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2673">口座番号</span></span> 
- <span data-ttu-id="aab42-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2674">口座番号＃</span></span> 
- <span data-ttu-id="aab42-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="aab42-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="aab42-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="aab42-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="aab42-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="aab42-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="aab42-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="aab42-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="aab42-2681">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2682">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2682">Format</span></span>

<span data-ttu-id="aab42-2683">12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2684">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2684">Pattern</span></span>

<span data-ttu-id="aab42-2685">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2686">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2686">Checksum</span></span>

<span data-ttu-id="aab42-2687">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2688">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2688">Definition</span></span>

<span data-ttu-id="aab42-2689">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2690">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2691">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2692">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="aab42-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="aab42-2694">通讯#</span><span class="sxs-lookup"><span data-stu-id="aab42-2694">dl#</span></span> 
- <span data-ttu-id="aab42-2695">通讯</span><span class="sxs-lookup"><span data-stu-id="aab42-2695">DL＃</span></span> 
- <span data-ttu-id="aab42-2696">dls#</span><span class="sxs-lookup"><span data-stu-id="aab42-2696">dls#</span></span> 
- <span data-ttu-id="aab42-2697">DLS</span><span class="sxs-lookup"><span data-stu-id="aab42-2697">DLS＃</span></span> 
- <span data-ttu-id="aab42-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="aab42-2698">driver license</span></span> 
- <span data-ttu-id="aab42-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2699">driver licenses</span></span> 
- <span data-ttu-id="aab42-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="aab42-2700">drivers license</span></span> 
- <span data-ttu-id="aab42-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="aab42-2701">driver's license</span></span> 
- <span data-ttu-id="aab42-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2702">drivers licenses</span></span> 
- <span data-ttu-id="aab42-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-2703">driver's licenses</span></span> 
- <span data-ttu-id="aab42-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="aab42-2704">driving licence</span></span> 
- <span data-ttu-id="aab42-2705">.lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-2705">lic#</span></span> 
- <span data-ttu-id="aab42-2706">.LIC</span><span class="sxs-lookup"><span data-stu-id="aab42-2706">LIC＃</span></span> 
- <span data-ttu-id="aab42-2707">driver'lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-2707">lics#</span></span> 
- <span data-ttu-id="aab42-2708">state id</span><span class="sxs-lookup"><span data-stu-id="aab42-2708">state id</span></span> 
- <span data-ttu-id="aab42-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="aab42-2709">state identification</span></span> 
- <span data-ttu-id="aab42-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-2710">state identification number</span></span> 
- <span data-ttu-id="aab42-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2711">低所得国＃</span></span> 
- <span data-ttu-id="aab42-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="aab42-2712">免許証</span></span> 
- <span data-ttu-id="aab42-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2713">状態ID</span></span>
- <span data-ttu-id="aab42-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="aab42-2714">状態の識別</span></span> 
- <span data-ttu-id="aab42-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2715">状態の識別番号</span></span> 
- <span data-ttu-id="aab42-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="aab42-2716">運転免許</span></span> 
- <span data-ttu-id="aab42-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="aab42-2717">運転免許証</span></span> 
- <span data-ttu-id="aab42-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="aab42-2719">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2720">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2720">Format</span></span>

<span data-ttu-id="aab42-2721">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2722">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2722">Pattern</span></span>

<span data-ttu-id="aab42-2723">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2724">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2724">Checksum</span></span>

<span data-ttu-id="aab42-2725">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2726">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2726">Definition</span></span>

<span data-ttu-id="aab42-2727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2728">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2729">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2730">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="aab42-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="aab42-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-2732">パスポート</span></span> 
- <span data-ttu-id="aab42-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2733">パスポート番号</span></span> 
- <span data-ttu-id="aab42-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-2734">パスポートのNum</span></span> 
- <span data-ttu-id="aab42-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="aab42-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="aab42-2736">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2737">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2737">Format</span></span>

<span data-ttu-id="aab42-2738">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2739">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2739">Pattern</span></span>

<span data-ttu-id="aab42-2740">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2741">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2741">Checksum</span></span>

<span data-ttu-id="aab42-2742">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2743">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2743">Definition</span></span>

<span data-ttu-id="aab42-2744">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2745">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2746">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2747">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="aab42-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="aab42-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2749">Resident Registration Number</span></span>
- <span data-ttu-id="aab42-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2750">Resident Register Number</span></span> 
- <span data-ttu-id="aab42-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="aab42-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="aab42-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2753">Resident Register No.</span></span> 
- <span data-ttu-id="aab42-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="aab42-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="aab42-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="aab42-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="aab42-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="aab42-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="aab42-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="aab42-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="aab42-2760">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="aab42-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2761">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2761">Format</span></span>

<span data-ttu-id="aab42-2762">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2763">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2763">Pattern</span></span>

<span data-ttu-id="aab42-2764">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2764">7-12 digits:</span></span>
- <span data-ttu-id="aab42-2765">四位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2765">Four digits</span></span> 
- <span data-ttu-id="aab42-2766">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="aab42-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="aab42-2767">六位数字或</span><span class="sxs-lookup"><span data-stu-id="aab42-2767">Six digits OR</span></span>
- <span data-ttu-id="aab42-2768">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2769">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2769">Checksum</span></span>

<span data-ttu-id="aab42-2770">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2771">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2771">Definition</span></span>

<span data-ttu-id="aab42-2772">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2773">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2774">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="aab42-2775">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2776">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2777">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2778">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="aab42-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="aab42-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="aab42-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="aab42-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="aab42-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="aab42-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="aab42-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="aab42-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="aab42-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="aab42-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="aab42-2785">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="aab42-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2786">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2786">Format</span></span>

<span data-ttu-id="aab42-2787">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2788">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2788">Pattern</span></span>

<span data-ttu-id="aab42-2789">12个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2789">12 letters and digits:</span></span>
- <span data-ttu-id="aab42-2790">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="aab42-2791">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2791">Eight digits</span></span> 
- <span data-ttu-id="aab42-2792">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2793">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2793">Checksum</span></span>

<span data-ttu-id="aab42-2794">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2795">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2795">Definition</span></span>

<span data-ttu-id="aab42-2796">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2797">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2798">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2799">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="aab42-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="aab42-2801">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="aab42-2801">Residence card number</span></span>
- <span data-ttu-id="aab42-2802">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="aab42-2802">Residence card no</span></span>
- <span data-ttu-id="aab42-2803">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="aab42-2803">Residence card #</span></span>
- <span data-ttu-id="aab42-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="aab42-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="aab42-2805">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2806">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2806">Format</span></span>

<span data-ttu-id="aab42-2807">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="aab42-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2808">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2808">Pattern</span></span>

<span data-ttu-id="aab42-2809">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2809">12 digits:</span></span>
- <span data-ttu-id="aab42-2810">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="aab42-2811">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2811">A dash (optional)</span></span> 
- <span data-ttu-id="aab42-2812">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="aab42-2813">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2813">A dash (optional)</span></span> 
- <span data-ttu-id="aab42-2814">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2814">Three random digits</span></span> 
- <span data-ttu-id="aab42-2815">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="aab42-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2816">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2816">Checksum</span></span>

<span data-ttu-id="aab42-2817">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2818">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2818">Definition</span></span>

<span data-ttu-id="aab42-2819">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2820">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2821">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2822">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="aab42-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="aab42-2824">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="aab42-2824">digital application card</span></span>
- <span data-ttu-id="aab42-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="aab42-2825">i/c</span></span>
- <span data-ttu-id="aab42-2826">i/c 否</span><span class="sxs-lookup"><span data-stu-id="aab42-2826">i/c no</span></span>
- <span data-ttu-id="aab42-2827">ic</span><span class="sxs-lookup"><span data-stu-id="aab42-2827">ic</span></span>
- <span data-ttu-id="aab42-2828">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="aab42-2828">ic no</span></span>
- <span data-ttu-id="aab42-2829">id card</span><span class="sxs-lookup"><span data-stu-id="aab42-2829">id card</span></span>
- <span data-ttu-id="aab42-2830">标识卡</span><span class="sxs-lookup"><span data-stu-id="aab42-2830">identification Card</span></span>
- <span data-ttu-id="aab42-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-2831">identity card</span></span>
- <span data-ttu-id="aab42-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="aab42-2832">k/p</span></span>
- <span data-ttu-id="aab42-2833">k/p no</span><span class="sxs-lookup"><span data-stu-id="aab42-2833">k/p no</span></span>
- <span data-ttu-id="aab42-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="aab42-2834">kad akuan diri</span></span>
- <span data-ttu-id="aab42-2835">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="aab42-2836">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="aab42-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="aab42-2837">kp</span><span class="sxs-lookup"><span data-stu-id="aab42-2837">kp</span></span>
- <span data-ttu-id="aab42-2838">kp no</span><span class="sxs-lookup"><span data-stu-id="aab42-2838">kp no</span></span>
- <span data-ttu-id="aab42-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="aab42-2839">mykad</span></span>
- <span data-ttu-id="aab42-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="aab42-2840">mykas</span></span>
- <span data-ttu-id="aab42-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="aab42-2841">mykid</span></span>
- <span data-ttu-id="aab42-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="aab42-2842">mypr</span></span>
- <span data-ttu-id="aab42-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="aab42-2843">mytentera</span></span>
- <span data-ttu-id="aab42-2844">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="aab42-2844">malaysia identity card</span></span>
- <span data-ttu-id="aab42-2845">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="aab42-2845">malaysian identity card</span></span>
- <span data-ttu-id="aab42-2846">nric</span><span class="sxs-lookup"><span data-stu-id="aab42-2846">nric</span></span>
- <span data-ttu-id="aab42-2847">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="aab42-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="aab42-2848">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2849">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2849">Format</span></span>

<span data-ttu-id="aab42-2850">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="aab42-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2851">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2851">Pattern</span></span>

<span data-ttu-id="aab42-2852">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2852">8-9 digits:</span></span>
- <span data-ttu-id="aab42-2853">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2853">Three digits</span></span> 
- <span data-ttu-id="aab42-2854">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2854">A space (optional)</span></span> 
- <span data-ttu-id="aab42-2855">三个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2855">Three digits</span></span> 
- <span data-ttu-id="aab42-2856">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="aab42-2856">A space (optional)</span></span> 
- <span data-ttu-id="aab42-2857">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2858">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2858">Checksum</span></span>

<span data-ttu-id="aab42-2859">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2860">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2860">Definition</span></span>

<span data-ttu-id="aab42-2861">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2862">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2863">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="aab42-2864">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="aab42-2865">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2866">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="aab42-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="aab42-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="aab42-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="aab42-2868">Citizen service number</span></span> 
- <span data-ttu-id="aab42-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="aab42-2869">BSN</span></span> 
- <span data-ttu-id="aab42-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="aab42-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2871">Sofinummer</span></span> 
- <span data-ttu-id="aab42-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="aab42-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="aab42-2874">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2875">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2875">Format</span></span>

<span data-ttu-id="aab42-2876">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2877">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2877">Pattern</span></span>

<span data-ttu-id="aab42-2878">三个字母（不区分大小写）一个空格（可选）四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2879">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2879">Checksum</span></span>

<span data-ttu-id="aab42-2880">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2881">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2881">Definition</span></span>

<span data-ttu-id="aab42-2882">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2883">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2884">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="aab42-2885">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2885">The checksum passes.</span></span>

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

<span data-ttu-id="aab42-2886">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2886">Keywords</span></span>

<span data-ttu-id="aab42-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="aab42-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="aab42-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="aab42-2888">NHI</span></span> 
- <span data-ttu-id="aab42-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="aab42-2889">New Zealand</span></span> 
- <span data-ttu-id="aab42-2890">运行状况</span><span class="sxs-lookup"><span data-stu-id="aab42-2890">Health</span></span> 
- <span data-ttu-id="aab42-2891">治疗</span><span class="sxs-lookup"><span data-stu-id="aab42-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="aab42-2892">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2893">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2893">Format</span></span>

<span data-ttu-id="aab42-2894">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2895">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2895">Pattern</span></span>

<span data-ttu-id="aab42-2896">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2896">11 digits:</span></span>
- <span data-ttu-id="aab42-2897">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="aab42-2898">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="aab42-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="aab42-2899">两个校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2900">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2900">Checksum</span></span>

<span data-ttu-id="aab42-2901">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2902">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2902">Definition</span></span>

<span data-ttu-id="aab42-2903">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2904">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2905">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="aab42-2906">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2906">The checksum passes.</span></span>
- <span data-ttu-id="aab42-2907">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2908">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2909">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2910">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="aab42-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="aab42-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-2912">Personal identification number</span></span>
- <span data-ttu-id="aab42-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="aab42-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="aab42-2914">ID Number</span></span>
- <span data-ttu-id="aab42-2915">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-2915">Identification</span></span>
- <span data-ttu-id="aab42-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2916">Personnummer</span></span>
- <span data-ttu-id="aab42-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="aab42-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="aab42-2918">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2919">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2919">Format</span></span>

<span data-ttu-id="aab42-2920">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="aab42-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2921">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2921">Pattern</span></span>

<span data-ttu-id="aab42-2922">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-2922">12 digits:</span></span>
- <span data-ttu-id="aab42-2923">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2923">Four digits</span></span> 
- <span data-ttu-id="aab42-2924">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-2924">A hyphen</span></span> 
- <span data-ttu-id="aab42-2925">七个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-2925">Seven digits</span></span> 
- <span data-ttu-id="aab42-2926">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-2926">A hyphen</span></span> 
- <span data-ttu-id="aab42-2927">一个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2928">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2928">Checksum</span></span>

<span data-ttu-id="aab42-2929">否</span><span class="sxs-lookup"><span data-stu-id="aab42-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2930">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2930">Definition</span></span>

<span data-ttu-id="aab42-2931">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2932">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2933">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2934">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="aab42-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="aab42-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="aab42-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="aab42-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="aab42-2937">UMID</span></span> 
- <span data-ttu-id="aab42-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="aab42-2938">Identity Card</span></span> 
- <span data-ttu-id="aab42-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="aab42-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="aab42-2940">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="aab42-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2941">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2941">Format</span></span>

<span data-ttu-id="aab42-2942">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2943">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2943">Pattern</span></span>

<span data-ttu-id="aab42-2944">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2945">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2945">Checksum</span></span>

<span data-ttu-id="aab42-2946">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2947">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2947">Definition</span></span>

<span data-ttu-id="aab42-2948">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="aab42-2949">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="aab42-2950">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2951">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="aab42-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="aab42-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="aab42-2953">Dowód osobisty</span></span>
- <span data-ttu-id="aab42-2954">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="aab42-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="aab42-2955">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="aab42-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="aab42-2956">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="aab42-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="aab42-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="aab42-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="aab42-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="aab42-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="aab42-2959">dow.</span><span class="sxs-lookup"><span data-stu-id="aab42-2959">dow.</span></span> <span data-ttu-id="aab42-2960">os.</span><span class="sxs-lookup"><span data-stu-id="aab42-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="aab42-2961">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="aab42-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2962">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2962">Format</span></span>

<span data-ttu-id="aab42-2963">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2964">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2964">Pattern</span></span>

<span data-ttu-id="aab42-2965">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2966">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2966">Checksum</span></span>

<span data-ttu-id="aab42-2967">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2968">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2968">Definition</span></span>

<span data-ttu-id="aab42-2969">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2970">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2971">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="aab42-2972">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-2973">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="aab42-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="aab42-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="aab42-2975">Nr PESEL</span></span>
- <span data-ttu-id="aab42-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="aab42-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="aab42-2977">波兰护照</span><span class="sxs-lookup"><span data-stu-id="aab42-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2978">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2978">Format</span></span>

<span data-ttu-id="aab42-2979">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2980">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2980">Pattern</span></span>

<span data-ttu-id="aab42-2981">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-2982">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-2982">Checksum</span></span>

<span data-ttu-id="aab42-2983">是</span><span class="sxs-lookup"><span data-stu-id="aab42-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-2984">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-2984">Definition</span></span>

<span data-ttu-id="aab42-2985">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-2986">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-2987">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="aab42-2988">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-2989">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="aab42-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="aab42-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="aab42-2991">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="aab42-2991">Numer paszportu</span></span>
- <span data-ttu-id="aab42-2992">Führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="aab42-2992">Nr.</span></span> <span data-ttu-id="aab42-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="aab42-2993">Paszportu</span></span>
- <span data-ttu-id="aab42-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="aab42-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="aab42-2995">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-2996">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-2996">Format</span></span>

<span data-ttu-id="aab42-2997">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-2998">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-2998">Pattern</span></span>

<span data-ttu-id="aab42-2999">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3000">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3000">Checksum</span></span>

<span data-ttu-id="aab42-3001">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3002">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3002">Definition</span></span>

<span data-ttu-id="aab42-3003">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3004">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3005">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3006">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="aab42-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="aab42-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="aab42-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="aab42-3008">Citizen Card</span></span>
- <span data-ttu-id="aab42-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="aab42-3009">National ID Card</span></span>
- <span data-ttu-id="aab42-3010">CC</span><span class="sxs-lookup"><span data-stu-id="aab42-3010">CC</span></span>
- <span data-ttu-id="aab42-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="aab42-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="aab42-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="aab42-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="aab42-3013">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3014">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3014">Format</span></span>

<span data-ttu-id="aab42-3015">10 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3016">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3016">Pattern</span></span>

<span data-ttu-id="aab42-3017">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3018">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3018">Checksum</span></span>

<span data-ttu-id="aab42-3019">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3020">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3020">Definition</span></span>

<span data-ttu-id="aab42-3021">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3022">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3023">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3024">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="aab42-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="aab42-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="aab42-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="aab42-3026">Identification Card</span></span> 
- <span data-ttu-id="aab42-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="aab42-3027">I card number</span></span> 
- <span data-ttu-id="aab42-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="aab42-3028">ID number</span></span> 
- <span data-ttu-id="aab42-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="aab42-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="aab42-3030">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="aab42-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3031">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3031">Format</span></span>

<span data-ttu-id="aab42-3032">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3033">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3033">Pattern</span></span>

- <span data-ttu-id="aab42-3034">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="aab42-3035">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-3036">七个数字 </span><span class="sxs-lookup"><span data-stu-id="aab42-3036">Seven digits</span></span> 
- <span data-ttu-id="aab42-3037">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3038">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3038">Checksum</span></span>

<span data-ttu-id="aab42-3039">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3040">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3040">Definition</span></span>

<span data-ttu-id="aab42-3041">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3042">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3043">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="aab42-3044">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3044">The checksum passes.</span></span>

<span data-ttu-id="aab42-3045">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3046">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3047">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3048">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="aab42-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="aab42-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="aab42-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="aab42-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="aab42-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3051">Identity Card Number</span></span> 
- <span data-ttu-id="aab42-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="aab42-3052">NRIC</span></span> 
- <span data-ttu-id="aab42-3053">IC</span><span class="sxs-lookup"><span data-stu-id="aab42-3053">IC</span></span> 
- <span data-ttu-id="aab42-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="aab42-3055">FIN</span><span class="sxs-lookup"><span data-stu-id="aab42-3055">FIN</span></span> 
- <span data-ttu-id="aab42-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="aab42-3056">身份证</span></span> 
- <span data-ttu-id="aab42-3057">證</span><span class="sxs-lookup"><span data-stu-id="aab42-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="aab42-3058">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="aab42-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3059">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3059">Format</span></span>

<span data-ttu-id="aab42-3060">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="aab42-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3061">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3061">Pattern</span></span>

<span data-ttu-id="aab42-3062">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3062">13 digits:</span></span>
- <span data-ttu-id="aab42-3063">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="aab42-3064">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3064">Four digits</span></span> 
- <span data-ttu-id="aab42-3065">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="aab42-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="aab42-3066">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="aab42-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="aab42-3067">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="aab42-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3068">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3068">Checksum</span></span>

<span data-ttu-id="aab42-3069">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3070">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3070">Definition</span></span>

<span data-ttu-id="aab42-3071">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3072">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3073">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="aab42-3074">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3075">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="aab42-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="aab42-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="aab42-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="aab42-3077">Identity card</span></span>
- <span data-ttu-id="aab42-3078">ID</span><span class="sxs-lookup"><span data-stu-id="aab42-3078">ID</span></span>
- <span data-ttu-id="aab42-3079">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="aab42-3080">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3081">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3081">Format</span></span>

<span data-ttu-id="aab42-3082">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="aab42-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3083">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3083">Pattern</span></span>

<span data-ttu-id="aab42-3084">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3084">13 digits:</span></span>
- <span data-ttu-id="aab42-3085">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="aab42-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="aab42-3086">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="aab42-3086">A hyphen</span></span> 
- <span data-ttu-id="aab42-3087">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="aab42-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="aab42-3088">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="aab42-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="aab42-3089">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="aab42-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="aab42-3090">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="aab42-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3091">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3091">Checksum</span></span>

<span data-ttu-id="aab42-3092">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3093">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3093">Definition</span></span>

<span data-ttu-id="aab42-3094">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3095">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3096">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="aab42-3097">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3097">The checksum passes.</span></span>

<span data-ttu-id="aab42-3098">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3099">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3100">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3101">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="aab42-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="aab42-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="aab42-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="aab42-3103">National ID card</span></span> 
- <span data-ttu-id="aab42-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="aab42-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="aab42-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="aab42-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="aab42-3106">RRN</span></span> 
- <span data-ttu-id="aab42-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="aab42-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="aab42-3108">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="aab42-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3109">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3109">Format</span></span>

<span data-ttu-id="aab42-3110">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3111">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3111">Pattern</span></span>

<span data-ttu-id="aab42-3112">11-12 位数：</span><span class="sxs-lookup"><span data-stu-id="aab42-3112">11-12 digits:</span></span>
- <span data-ttu-id="aab42-3113">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3113">Two digits</span></span> 
- <span data-ttu-id="aab42-3114">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="aab42-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="aab42-3115">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3115">7-8 digits</span></span> 
- <span data-ttu-id="aab42-3116">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="aab42-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="aab42-3117">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3118">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3118">Checksum</span></span>

<span data-ttu-id="aab42-3119">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3120">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3120">Definition</span></span>

<span data-ttu-id="aab42-3121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3122">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3123">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3124">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3124">Keywords</span></span>

<span data-ttu-id="aab42-3125">无</span><span class="sxs-lookup"><span data-stu-id="aab42-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="aab42-3126">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="aab42-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3127">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3127">Format</span></span>

<span data-ttu-id="aab42-3128">字符串 "User Id"、"User ID"、"uid" 或 "UserId"，后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="aab42-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3129">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3129">Pattern</span></span>

- <span data-ttu-id="aab42-3130">字符串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="aab42-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="aab42-3131">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="aab42-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="aab42-3132">字符串 "Password" 或 "pwd"，其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="aab42-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="aab42-3133">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-3133">An equal sign (=)</span></span>
- <span data-ttu-id="aab42-3134">任何不是美元符号（$）、百分比符号（%）、大于号（>）、符号（@）、引号（"）、分号（;)、左大括号（[）或左中括号（{）的字符</span><span class="sxs-lookup"><span data-stu-id="aab42-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="aab42-3135">7-128 个字符的任意组合，不是分号（;)、正斜杠（/）或引号（"）</span><span class="sxs-lookup"><span data-stu-id="aab42-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="aab42-3136">一个分号（;)或引号（"）</span><span class="sxs-lookup"><span data-stu-id="aab42-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3137">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3137">Checksum</span></span>

<span data-ttu-id="aab42-3138">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3139">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3139">Definition</span></span>

<span data-ttu-id="aab42-3140">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3141">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3142">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="aab42-3143">正则表达式**CEP_PasswordPlaceHolder 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3144">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3145">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="aab42-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="aab42-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="aab42-3147">部分密码</span><span class="sxs-lookup"><span data-stu-id="aab42-3147">some-password</span></span>
- <span data-ttu-id="aab42-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="aab42-3148">somepassword</span></span>
- <span data-ttu-id="aab42-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="aab42-3149">secretPassword</span></span>
- <span data-ttu-id="aab42-3150">采用</span><span class="sxs-lookup"><span data-stu-id="aab42-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="aab42-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="aab42-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="aab42-3152">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-3153">密码或密码后跟0-2 个空格、一个等号（=）、0-2 个空格和一个星号（\*）--或--</span><span class="sxs-lookup"><span data-stu-id="aab42-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="aab42-3154">密码或密码后跟：</span><span class="sxs-lookup"><span data-stu-id="aab42-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="aab42-3155">等号（=）</span><span class="sxs-lookup"><span data-stu-id="aab42-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="aab42-3156">小于号（<）</span><span class="sxs-lookup"><span data-stu-id="aab42-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="aab42-3157">1-200 个字符的任意组合，这些字符为大写或小写字母、数字、星号（\*）、连字符（-）、下划线（_）或空白字符</span><span class="sxs-lookup"><span data-stu-id="aab42-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="aab42-3158">大于号（>）</span><span class="sxs-lookup"><span data-stu-id="aab42-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="aab42-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="aab42-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="aab42-3160">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="aab42-3161">尚未</span><span class="sxs-lookup"><span data-stu-id="aab42-3161">contoso</span></span>
- <span data-ttu-id="aab42-3162">送交</span><span class="sxs-lookup"><span data-stu-id="aab42-3162">fabrikam</span></span>
- <span data-ttu-id="aab42-3163">罗斯</span><span class="sxs-lookup"><span data-stu-id="aab42-3163">northwind</span></span>
- <span data-ttu-id="aab42-3164">沙盒</span><span class="sxs-lookup"><span data-stu-id="aab42-3164">sandbox</span></span>
- <span data-ttu-id="aab42-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="aab42-3165">onebox</span></span>
- <span data-ttu-id="aab42-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="aab42-3166">localhost</span></span>
- <span data-ttu-id="aab42-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="aab42-3167">127.0.0.1</span></span>
- <span data-ttu-id="aab42-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="aab42-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-3169">com</span><span class="sxs-lookup"><span data-stu-id="aab42-3169">com</span></span>
- <span data-ttu-id="aab42-3170">s-int。</span><span class="sxs-lookup"><span data-stu-id="aab42-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="aab42-3171">netmeeting</span><span class="sxs-lookup"><span data-stu-id="aab42-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="aab42-3172">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3173">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3173">Format</span></span>

<span data-ttu-id="aab42-3174">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="aab42-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3175">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3175">Pattern</span></span>

<span data-ttu-id="aab42-3176">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="aab42-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="aab42-3177">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="aab42-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="aab42-3178">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="aab42-3179">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="aab42-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="aab42-3180">四个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3181">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3181">Checksum</span></span>

<span data-ttu-id="aab42-3182">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3183">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3183">Definition</span></span>

<span data-ttu-id="aab42-3184">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3185">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3186">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3187">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3187">Keywords</span></span>

<span data-ttu-id="aab42-3188">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="aab42-3189">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3190">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3190">Format</span></span>

<span data-ttu-id="aab42-3191">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3192">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3192">Pattern</span></span>

<span data-ttu-id="aab42-3193">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3194">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3194">Checksum</span></span>

<span data-ttu-id="aab42-3195">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3196">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3196">Definition</span></span>

<span data-ttu-id="aab42-3197">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3198">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3199">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-3199">One of the following is true:</span></span>
    - <span data-ttu-id="aab42-3200">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="aab42-3201">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3202">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="aab42-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="aab42-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="aab42-3204">visa requirements</span></span> 
- <span data-ttu-id="aab42-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="aab42-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="aab42-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="aab42-3206">Schengen visas</span></span> 
- <span data-ttu-id="aab42-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="aab42-3207">Schengen visa</span></span> 
- <span data-ttu-id="aab42-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="aab42-3208">Visa Processing</span></span> 
- <span data-ttu-id="aab42-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="aab42-3209">Visa Type</span></span> 
- <span data-ttu-id="aab42-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="aab42-3210">Single Entry</span></span> 
- <span data-ttu-id="aab42-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="aab42-3211">Multiple Entry</span></span> 
- <span data-ttu-id="aab42-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="aab42-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="aab42-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-3213">Keyword_passport</span></span>

- <span data-ttu-id="aab42-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3214">Passport Number</span></span> 
- <span data-ttu-id="aab42-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="aab42-3215">Passport No</span></span> 
- <span data-ttu-id="aab42-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-3216">Passport #</span></span> 
- <span data-ttu-id="aab42-3217">登记卡#</span><span class="sxs-lookup"><span data-stu-id="aab42-3217">Passport#</span></span> 
- <span data-ttu-id="aab42-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="aab42-3218">PassportID</span></span> 
- <span data-ttu-id="aab42-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="aab42-3219">Passportno</span></span> 
- <span data-ttu-id="aab42-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-3220">passportnumber</span></span> 
- <span data-ttu-id="aab42-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-3221">パスポート</span></span> 
- <span data-ttu-id="aab42-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-3222">パスポート番号</span></span> 
- <span data-ttu-id="aab42-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-3223">パスポートのNum</span></span> 
- <span data-ttu-id="aab42-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="aab42-3224">パスポート＃</span></span> 
- <span data-ttu-id="aab42-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="aab42-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="aab42-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="aab42-3226">Passeport n °</span></span> 
- <span data-ttu-id="aab42-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="aab42-3227">Passeport Non</span></span> 
- <span data-ttu-id="aab42-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="aab42-3228">Passeport #</span></span> 
- <span data-ttu-id="aab42-3229">Passeport#</span><span class="sxs-lookup"><span data-stu-id="aab42-3229">Passeport#</span></span> 
- <span data-ttu-id="aab42-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="aab42-3230">PasseportNon</span></span> 
- <span data-ttu-id="aab42-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="aab42-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="aab42-3232">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="aab42-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3233">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3233">Format</span></span>

<span data-ttu-id="aab42-3234">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3235">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3235">Pattern</span></span>

<span data-ttu-id="aab42-3236">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="aab42-3237">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-3238">可选空格</span><span class="sxs-lookup"><span data-stu-id="aab42-3238">An optional space</span></span> 
- <span data-ttu-id="aab42-3239">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="aab42-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="aab42-3240">可选空格</span><span class="sxs-lookup"><span data-stu-id="aab42-3240">An optional space</span></span> 
- <span data-ttu-id="aab42-3241">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="aab42-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3242">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3242">Checksum</span></span>

<span data-ttu-id="aab42-3243">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3244">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3244">Definition</span></span>

<span data-ttu-id="aab42-3245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3246">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3247">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3248">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="aab42-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="aab42-3249">Keyword_swift</span></span>

- <span data-ttu-id="aab42-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="aab42-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="aab42-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="aab42-3251">iso 9362</span></span> 
- <span data-ttu-id="aab42-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="aab42-3252">iso9362</span></span> 
- <span data-ttu-id="aab42-3253">反应\#</span><span class="sxs-lookup"><span data-stu-id="aab42-3253">swift\#</span></span> 
- <span data-ttu-id="aab42-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="aab42-3254">swiftcode</span></span> 
- <span data-ttu-id="aab42-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-3255">swiftnumber</span></span> 
- <span data-ttu-id="aab42-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="aab42-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="aab42-3257">swift code</span></span> 
- <span data-ttu-id="aab42-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="aab42-3258">swift number #</span></span> 
- <span data-ttu-id="aab42-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="aab42-3259">swift routing number</span></span> 
- <span data-ttu-id="aab42-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="aab42-3260">bic number</span></span> 
- <span data-ttu-id="aab42-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="aab42-3261">bic code</span></span> 
- <span data-ttu-id="aab42-3262">numéro\#</span><span class="sxs-lookup"><span data-stu-id="aab42-3262">bic \#</span></span> 
- <span data-ttu-id="aab42-3263">numéro\#</span><span class="sxs-lookup"><span data-stu-id="aab42-3263">bic\#</span></span> 
- <span data-ttu-id="aab42-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="aab42-3264">bank identifier code</span></span> 
- <span data-ttu-id="aab42-3265">標準化9362</span><span class="sxs-lookup"><span data-stu-id="aab42-3265">標準化9362</span></span> 
- <span data-ttu-id="aab42-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="aab42-3266">迅速＃</span></span> 
- <span data-ttu-id="aab42-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="aab42-3267">SWIFTコード</span></span> 
- <span data-ttu-id="aab42-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="aab42-3268">SWIFT番号</span></span> 
- <span data-ttu-id="aab42-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="aab42-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="aab42-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="aab42-3270">BIC番号</span></span> 
- <span data-ttu-id="aab42-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="aab42-3271">BICコード</span></span> 
- <span data-ttu-id="aab42-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="aab42-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="aab42-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="aab42-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="aab42-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="aab42-3274">rapide \#</span></span> 
- <span data-ttu-id="aab42-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="aab42-3275">code SWIFT</span></span> 
- <span data-ttu-id="aab42-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="aab42-3276">le numéro de swift</span></span> 
- <span data-ttu-id="aab42-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="aab42-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="aab42-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="aab42-3278">le numéro BIC</span></span> 
- <span data-ttu-id="aab42-3279">\#NUMÉRO</span><span class="sxs-lookup"><span data-stu-id="aab42-3279">\# BIC</span></span> 
- <span data-ttu-id="aab42-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="aab42-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="aab42-3281">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="aab42-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3282">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3282">Format</span></span>

<span data-ttu-id="aab42-3283">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3284">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3284">Pattern</span></span>

<span data-ttu-id="aab42-3285">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="aab42-3286">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="aab42-3287">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="aab42-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="aab42-3288">八位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3289">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3289">Checksum</span></span>

<span data-ttu-id="aab42-3290">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3291">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3291">Definition</span></span>

<span data-ttu-id="aab42-3292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3293">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3294">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="aab42-3295">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3296">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="aab42-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="aab42-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="aab42-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="aab42-3298">身份證字號</span></span> 
- <span data-ttu-id="aab42-3299">證</span><span class="sxs-lookup"><span data-stu-id="aab42-3299">身份證</span></span> 
- <span data-ttu-id="aab42-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="aab42-3300">身份證號碼</span></span> 
- <span data-ttu-id="aab42-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="aab42-3301">身份證號</span></span> 
- <span data-ttu-id="aab42-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="aab42-3302">身分證字號</span></span> 
- <span data-ttu-id="aab42-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="aab42-3303">身分證</span></span> 
- <span data-ttu-id="aab42-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="aab42-3304">身分證號碼</span></span> 
- <span data-ttu-id="aab42-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="aab42-3305">身份證號</span></span> 
- <span data-ttu-id="aab42-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="aab42-3306">身分證統一編號</span></span> 
- <span data-ttu-id="aab42-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="aab42-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="aab42-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="aab42-3308">簽名</span></span> 
- <span data-ttu-id="aab42-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="aab42-3309">蓋章</span></span> 
- <span data-ttu-id="aab42-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="aab42-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="aab42-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="aab42-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="aab42-3312">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3313">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3313">Format</span></span>

- <span data-ttu-id="aab42-3314">生物识别护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="aab42-3315">不带生物的护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3316">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3316">Pattern</span></span>
<span data-ttu-id="aab42-3317">生物识别护照号码：</span><span class="sxs-lookup"><span data-stu-id="aab42-3317">Biometric passport number:</span></span>
- <span data-ttu-id="aab42-3318">数字“3” </span><span class="sxs-lookup"><span data-stu-id="aab42-3318">The digit "3"</span></span> 
- <span data-ttu-id="aab42-3319">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3319">Eight digits</span></span>

<span data-ttu-id="aab42-3320">不带生物的护照号码：</span><span class="sxs-lookup"><span data-stu-id="aab42-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="aab42-3321">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3322">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3322">Checksum</span></span>

<span data-ttu-id="aab42-3323">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3324">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3324">Definition</span></span>

<span data-ttu-id="aab42-3325">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3326">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3327">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3328">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="aab42-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="aab42-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="aab42-3330">ROC passport number</span></span> 
- <span data-ttu-id="aab42-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="aab42-3331">Passport number</span></span> 
- <span data-ttu-id="aab42-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="aab42-3332">Passport no</span></span> 
- <span data-ttu-id="aab42-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="aab42-3333">Passport Num</span></span> 
- <span data-ttu-id="aab42-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-3334">Passport #</span></span> 
- <span data-ttu-id="aab42-3335">护照</span><span class="sxs-lookup"><span data-stu-id="aab42-3335">护照</span></span> 
- <span data-ttu-id="aab42-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="aab42-3336">中華民國護照</span></span> 
- <span data-ttu-id="aab42-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="aab42-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="aab42-3338">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3339">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3339">Format</span></span>

<span data-ttu-id="aab42-3340">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="aab42-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3341">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3341">Pattern</span></span>

<span data-ttu-id="aab42-3342">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3342">10 letters and digits:</span></span>
- <span data-ttu-id="aab42-3343">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="aab42-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="aab42-3344">八个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3345">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3345">Checksum</span></span>

<span data-ttu-id="aab42-3346">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3347">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3347">Definition</span></span>

<span data-ttu-id="aab42-3348">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3349">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3350">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3351">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="aab42-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="aab42-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="aab42-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="aab42-3353">Resident Certificate</span></span> 
- <span data-ttu-id="aab42-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="aab42-3354">Resident Cert</span></span> 
- <span data-ttu-id="aab42-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="aab42-3355">Resident Cert.</span></span> 
- <span data-ttu-id="aab42-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="aab42-3356">Identification card</span></span> 
- <span data-ttu-id="aab42-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="aab42-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="aab42-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="aab42-3358">ARC</span></span> 
- <span data-ttu-id="aab42-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="aab42-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="aab42-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="aab42-3360">TARC</span></span> 
- <span data-ttu-id="aab42-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="aab42-3361">居留證</span></span> 
- <span data-ttu-id="aab42-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="aab42-3362">外僑居留證</span></span> 
- <span data-ttu-id="aab42-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="aab42-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="aab42-3364">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="aab42-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3365">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3365">Format</span></span>

<span data-ttu-id="aab42-3366">13 位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3367">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3367">Pattern</span></span>

<span data-ttu-id="aab42-3368">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3368">13 digits:</span></span>
- <span data-ttu-id="aab42-3369">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="aab42-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="aab42-3370">12 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3371">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3371">Checksum</span></span>

<span data-ttu-id="aab42-3372">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3373">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3373">Definition</span></span>

<span data-ttu-id="aab42-3374">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3375">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3376">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="aab42-3377">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3378">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3379">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="aab42-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="aab42-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="aab42-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3381">ID Number</span></span>
- <span data-ttu-id="aab42-3382">标识号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3382">Identification Number</span></span>
- <span data-ttu-id="aab42-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="aab42-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="aab42-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="aab42-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="aab42-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="aab42-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="aab42-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="aab42-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="aab42-3387">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3388">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3388">Format</span></span>

<span data-ttu-id="aab42-3389">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3390">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3390">Pattern</span></span>

<span data-ttu-id="aab42-3391">11 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3392">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3392">Checksum</span></span>

<span data-ttu-id="aab42-3393">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3394">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3394">Definition</span></span>

<span data-ttu-id="aab42-3395">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3396">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3397">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="aab42-3398">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3399">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3400">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="aab42-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="aab42-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="aab42-3402">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="aab42-3402">TC Kimlik No</span></span>
- <span data-ttu-id="aab42-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="aab42-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="aab42-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="aab42-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="aab42-3405">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="aab42-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="aab42-p144">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3408">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3408">Format</span></span>

<span data-ttu-id="aab42-3409">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="aab42-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3410">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3410">Pattern</span></span>

<span data-ttu-id="aab42-3411">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3411">18 letters and digits:</span></span>
- <span data-ttu-id="aab42-3412">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="aab42-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="aab42-3413">一位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3413">One digit</span></span> 
- <span data-ttu-id="aab42-3414">MMDDY 的日期格式的五个数字（如果驱动程序是女，第七个字符增加50，即51到62而不是01到12）</span><span class="sxs-lookup"><span data-stu-id="aab42-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="aab42-3415">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="aab42-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="aab42-3416">五位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3417">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3417">Checksum</span></span>

<span data-ttu-id="aab42-3418">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3419">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3419">Definition</span></span>

<span data-ttu-id="aab42-3420">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3421">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3422">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="aab42-3423">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3424">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="aab42-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="aab42-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="aab42-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="aab42-3426">DVLA</span></span> 
- <span data-ttu-id="aab42-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="aab42-3427">light vans</span></span> 
- <span data-ttu-id="aab42-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="aab42-3428">quadbikes</span></span> 
- <span data-ttu-id="aab42-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="aab42-3429">motor cars</span></span> 
- <span data-ttu-id="aab42-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="aab42-3430">125cc</span></span> 
- <span data-ttu-id="aab42-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="aab42-3431">sidecar</span></span> 
- <span data-ttu-id="aab42-3432">tricycles</span><span class="sxs-lookup"><span data-stu-id="aab42-3432">tricycles</span></span> 
- <span data-ttu-id="aab42-3433">motorcycles</span><span class="sxs-lookup"><span data-stu-id="aab42-3433">motorcycles</span></span> 
- <span data-ttu-id="aab42-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="aab42-3434">photocard licence</span></span> 
- <span data-ttu-id="aab42-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="aab42-3435">learner drivers</span></span> 
- <span data-ttu-id="aab42-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="aab42-3436">licence holder</span></span> 
- <span data-ttu-id="aab42-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="aab42-3437">licence holders</span></span> 
- <span data-ttu-id="aab42-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="aab42-3438">driving licences</span></span> 
- <span data-ttu-id="aab42-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="aab42-3439">driving licence</span></span> 
- <span data-ttu-id="aab42-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="aab42-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="aab42-p145">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="aab42-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3443">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3443">Format</span></span>

<span data-ttu-id="aab42-3444">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3445">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3445">Pattern</span></span>

<span data-ttu-id="aab42-3446">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3447">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3447">Checksum</span></span>

<span data-ttu-id="aab42-3448">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3449">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3449">Definition</span></span>

<span data-ttu-id="aab42-3450">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3451">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3452">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3453">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="aab42-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="aab42-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="aab42-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="aab42-3455">council nomination</span></span> 
- <span data-ttu-id="aab42-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="aab42-3456">nomination form</span></span> 
- <span data-ttu-id="aab42-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="aab42-3457">electoral register</span></span> 
- <span data-ttu-id="aab42-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="aab42-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="aab42-p146">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="aab42-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3461">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3461">Format</span></span>

<span data-ttu-id="aab42-3462">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="aab42-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3463">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3463">Pattern</span></span>

<span data-ttu-id="aab42-3464">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="aab42-3464">10-17 digits:</span></span>
- <span data-ttu-id="aab42-3465">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="aab42-3466">一个空格</span><span class="sxs-lookup"><span data-stu-id="aab42-3466">A space</span></span> 
- <span data-ttu-id="aab42-3467">三位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3467">Three digits</span></span> 
- <span data-ttu-id="aab42-3468">一个空格</span><span class="sxs-lookup"><span data-stu-id="aab42-3468">A space</span></span> 
- <span data-ttu-id="aab42-3469">四位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3470">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3470">Checksum</span></span>

<span data-ttu-id="aab42-3471">是</span><span class="sxs-lookup"><span data-stu-id="aab42-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3472">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3472">Definition</span></span>

<span data-ttu-id="aab42-3473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3474">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3475">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-3475">One of the following is true:</span></span>
    - <span data-ttu-id="aab42-3476">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="aab42-3477">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="aab42-3478">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="aab42-3479">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="aab42-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3480">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="aab42-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="aab42-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="aab42-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="aab42-3482">national health service</span></span> 
- <span data-ttu-id="aab42-3483">nhs</span><span class="sxs-lookup"><span data-stu-id="aab42-3483">nhs</span></span> 
- <span data-ttu-id="aab42-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="aab42-3484">health services authority</span></span> 
- <span data-ttu-id="aab42-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="aab42-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="aab42-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="aab42-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="aab42-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="aab42-3487">patient id</span></span> 
- <span data-ttu-id="aab42-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="aab42-3488">patient identification</span></span> 
- <span data-ttu-id="aab42-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="aab42-3489">patient no</span></span> 
- <span data-ttu-id="aab42-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="aab42-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="aab42-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="aab42-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="aab42-3492">GP</span><span class="sxs-lookup"><span data-stu-id="aab42-3492">GP</span></span> 
- <span data-ttu-id="aab42-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="aab42-3493">DOB</span></span> 
- <span data-ttu-id="aab42-3494">D. B。</span><span class="sxs-lookup"><span data-stu-id="aab42-3494">D.O.B</span></span> 
- <span data-ttu-id="aab42-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="aab42-3495">Date of Birth</span></span> 
- <span data-ttu-id="aab42-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="aab42-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="aab42-p147">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="aab42-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3499">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3499">Format</span></span>

<span data-ttu-id="aab42-3500">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="aab42-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3501">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3501">Pattern</span></span>

<span data-ttu-id="aab42-3502">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="aab42-3502">Two possible patterns:</span></span>

- <span data-ttu-id="aab42-3503">两个字母（有效 NINOs 仅使用此前缀中的特定字符，此格式将对此进行验证; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="aab42-3504">六位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3504">Six digits</span></span>
- <span data-ttu-id="aab42-3505">"A"、"B"、"C" 或 "d" （与前缀一样，后缀中只允许有某些字符; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="aab42-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="aab42-3506">或</span><span class="sxs-lookup"><span data-stu-id="aab42-3506">OR</span></span>

- <span data-ttu-id="aab42-3507">两个字母</span><span class="sxs-lookup"><span data-stu-id="aab42-3507">Two letters</span></span>
- <span data-ttu-id="aab42-3508">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3508">A space or dash</span></span>
- <span data-ttu-id="aab42-3509">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3509">Two digits</span></span>
- <span data-ttu-id="aab42-3510">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3510">A space or dash</span></span>
- <span data-ttu-id="aab42-3511">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3511">Two digits</span></span>
- <span data-ttu-id="aab42-3512">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3512">A space or dash</span></span>
- <span data-ttu-id="aab42-3513">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3513">Two digits</span></span>
- <span data-ttu-id="aab42-3514">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3514">A space or dash</span></span>
- <span data-ttu-id="aab42-3515">要么是 "A"、"B"、"C"，要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="aab42-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3516">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3516">Checksum</span></span>

<span data-ttu-id="aab42-3517">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3518">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3518">Definition</span></span>

<span data-ttu-id="aab42-3519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3520">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3521">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="aab42-3522">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3523">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3524">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3525">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="aab42-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="aab42-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="aab42-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="aab42-3527">national insurance number</span></span> 
- <span data-ttu-id="aab42-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="aab42-3528">national insurance contributions</span></span> 
- <span data-ttu-id="aab42-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="aab42-3529">protection act</span></span> 
- <span data-ttu-id="aab42-3530">方面</span><span class="sxs-lookup"><span data-stu-id="aab42-3530">insurance</span></span> 
- <span data-ttu-id="aab42-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="aab42-3531">social security number</span></span> 
- <span data-ttu-id="aab42-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="aab42-3532">insurance application</span></span> 
- <span data-ttu-id="aab42-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="aab42-3533">medical application</span></span> 
- <span data-ttu-id="aab42-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="aab42-3534">social insurance</span></span> 
- <span data-ttu-id="aab42-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="aab42-3535">medical attention</span></span> 
- <span data-ttu-id="aab42-3536">social security</span><span class="sxs-lookup"><span data-stu-id="aab42-3536">social security</span></span> 
- <span data-ttu-id="aab42-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="aab42-3537">great britain</span></span> 
- <span data-ttu-id="aab42-3538">方面</span><span class="sxs-lookup"><span data-stu-id="aab42-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="aab42-p148">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="aab42-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3541">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3541">Format</span></span>

<span data-ttu-id="aab42-3542">九个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3543">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3543">Pattern</span></span>

<span data-ttu-id="aab42-3544">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3545">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3545">Checksum</span></span>

<span data-ttu-id="aab42-3546">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3547">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3547">Definition</span></span>

<span data-ttu-id="aab42-3548">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3549">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3550">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3551">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="aab42-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="aab42-3552">Keyword_passport</span></span>

- <span data-ttu-id="aab42-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3553">Passport Number</span></span> 
- <span data-ttu-id="aab42-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="aab42-3554">Passport No</span></span> 
- <span data-ttu-id="aab42-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="aab42-3555">Passport #</span></span> 
- <span data-ttu-id="aab42-3556">登记卡#</span><span class="sxs-lookup"><span data-stu-id="aab42-3556">Passport#</span></span> 
- <span data-ttu-id="aab42-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="aab42-3557">PassportID</span></span> 
- <span data-ttu-id="aab42-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="aab42-3558">Passportno</span></span> 
- <span data-ttu-id="aab42-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="aab42-3559">passportnumber</span></span> 
- <span data-ttu-id="aab42-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="aab42-3560">パスポート</span></span> 
- <span data-ttu-id="aab42-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aab42-3561">パスポート番号</span></span> 
- <span data-ttu-id="aab42-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="aab42-3562">パスポートのNum</span></span> 
- <span data-ttu-id="aab42-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="aab42-3563">パスポート＃</span></span> 
- <span data-ttu-id="aab42-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="aab42-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="aab42-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="aab42-3565">Passeport n °</span></span> 
- <span data-ttu-id="aab42-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="aab42-3566">Passeport Non</span></span> 
- <span data-ttu-id="aab42-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="aab42-3567">Passeport #</span></span> 
- <span data-ttu-id="aab42-3568">Passeport#</span><span class="sxs-lookup"><span data-stu-id="aab42-3568">Passeport#</span></span> 
- <span data-ttu-id="aab42-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="aab42-3569">PasseportNon</span></span> 
- <span data-ttu-id="aab42-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="aab42-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="aab42-3571">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="aab42-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3572">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3572">Format</span></span>

<span data-ttu-id="aab42-3573">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3574">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3574">Pattern</span></span>

<span data-ttu-id="aab42-3575">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3576">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3576">Checksum</span></span>

<span data-ttu-id="aab42-3577">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3578">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3578">Definition</span></span>

<span data-ttu-id="aab42-3579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3580">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3581">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aab42-3582">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="aab42-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="aab42-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="aab42-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3584">Checking Account Number</span></span> 
- <span data-ttu-id="aab42-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="aab42-3585">Checking Account</span></span> 
- <span data-ttu-id="aab42-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-3586">Checking Account #</span></span> 
- <span data-ttu-id="aab42-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="aab42-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-3588">Checking Acct #</span></span> 
- <span data-ttu-id="aab42-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="aab42-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3590">Checking Account No.</span></span> 
- <span data-ttu-id="aab42-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3591">Bank Account Number</span></span> 
- <span data-ttu-id="aab42-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-3592">Bank Account #</span></span> 
- <span data-ttu-id="aab42-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="aab42-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-3594">Bank Acct #</span></span> 
- <span data-ttu-id="aab42-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="aab42-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3596">Bank Account No.</span></span> 
- <span data-ttu-id="aab42-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3597">Savings Account Number</span></span> 
- <span data-ttu-id="aab42-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="aab42-3598">Savings Account.</span></span> 
- <span data-ttu-id="aab42-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-3599">Savings Account #</span></span> 
- <span data-ttu-id="aab42-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="aab42-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-3601">Savings Acct #</span></span> 
- <span data-ttu-id="aab42-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="aab42-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3603">Savings Account No.</span></span> 
- <span data-ttu-id="aab42-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3604">Debit Account Number</span></span> 
- <span data-ttu-id="aab42-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="aab42-3605">Debit Account</span></span> 
- <span data-ttu-id="aab42-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="aab42-3606">Debit Account #</span></span> 
- <span data-ttu-id="aab42-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="aab42-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="aab42-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="aab42-3608">Debit Acct #</span></span> 
- <span data-ttu-id="aab42-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="aab42-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="aab42-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="aab42-3611">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="aab42-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3612">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3612">Format</span></span>

<span data-ttu-id="aab42-3613">取决于州</span><span class="sxs-lookup"><span data-stu-id="aab42-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3614">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3614">Pattern</span></span>

<span data-ttu-id="aab42-3615">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="aab42-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="aab42-3616">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="aab42-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="aab42-3617">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="aab42-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3618">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3618">Checksum</span></span>

<span data-ttu-id="aab42-3619">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3620">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3620">Definition</span></span>

<span data-ttu-id="aab42-3621">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3622">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3623">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="aab42-3624">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="aab42-3625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3626">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3627">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="aab42-3628">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="aab42-3629">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3630">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="aab42-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="aab42-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="aab42-3632">通讯</span><span class="sxs-lookup"><span data-stu-id="aab42-3632">DL</span></span> 
- <span data-ttu-id="aab42-3633">DLS</span><span class="sxs-lookup"><span data-stu-id="aab42-3633">DLS</span></span> 
- <span data-ttu-id="aab42-3634">采用</span><span class="sxs-lookup"><span data-stu-id="aab42-3634">CDL</span></span> 
- <span data-ttu-id="aab42-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="aab42-3635">CDLS</span></span> 
- <span data-ttu-id="aab42-3636">ID</span><span class="sxs-lookup"><span data-stu-id="aab42-3636">ID</span></span> 
- <span data-ttu-id="aab42-3637">Id</span><span class="sxs-lookup"><span data-stu-id="aab42-3637">IDs</span></span> 
- <span data-ttu-id="aab42-3638">通讯#</span><span class="sxs-lookup"><span data-stu-id="aab42-3638">DL#</span></span> 
- <span data-ttu-id="aab42-3639">DLS#</span><span class="sxs-lookup"><span data-stu-id="aab42-3639">DLS#</span></span> 
- <span data-ttu-id="aab42-3640">采用#</span><span class="sxs-lookup"><span data-stu-id="aab42-3640">CDL#</span></span> 
- <span data-ttu-id="aab42-3641">CDLS#</span><span class="sxs-lookup"><span data-stu-id="aab42-3641">CDLS#</span></span> 
- <span data-ttu-id="aab42-3642">号#</span><span class="sxs-lookup"><span data-stu-id="aab42-3642">ID#</span></span>
- <span data-ttu-id="aab42-3643">Id#</span><span class="sxs-lookup"><span data-stu-id="aab42-3643">IDs#</span></span> 
- <span data-ttu-id="aab42-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="aab42-3644">ID number</span></span> 
- <span data-ttu-id="aab42-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-3645">ID numbers</span></span> 
- <span data-ttu-id="aab42-3646">.LIC</span><span class="sxs-lookup"><span data-stu-id="aab42-3646">LIC</span></span> 
- <span data-ttu-id="aab42-3647">.LIC#</span><span class="sxs-lookup"><span data-stu-id="aab42-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="aab42-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="aab42-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="aab42-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="aab42-3649">DriverLic</span></span> 
- <span data-ttu-id="aab42-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="aab42-3650">DriverLics</span></span> 
- <span data-ttu-id="aab42-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-3651">DriverLicense</span></span> 
- <span data-ttu-id="aab42-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3652">DriverLicenses</span></span> 
- <span data-ttu-id="aab42-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-3653">Driver Lic</span></span> 
- <span data-ttu-id="aab42-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-3654">Driver Lics</span></span> 
- <span data-ttu-id="aab42-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="aab42-3655">Driver License</span></span> 
- <span data-ttu-id="aab42-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3656">Driver Licenses</span></span> 
- <span data-ttu-id="aab42-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="aab42-3657">DriversLic</span></span> 
- <span data-ttu-id="aab42-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="aab42-3658">DriversLics</span></span> 
- <span data-ttu-id="aab42-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-3659">DriversLicense</span></span> 
- <span data-ttu-id="aab42-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3660">DriversLicenses</span></span> 
- <span data-ttu-id="aab42-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-3661">Drivers Lic</span></span> 
- <span data-ttu-id="aab42-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-3662">Drivers Lics</span></span> 
- <span data-ttu-id="aab42-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="aab42-3663">Drivers License</span></span> 
- <span data-ttu-id="aab42-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="aab42-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-3665">Driver'Lic</span></span> 
- <span data-ttu-id="aab42-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-3666">Driver'Lics</span></span> 
- <span data-ttu-id="aab42-3667">Driver'License</span><span class="sxs-lookup"><span data-stu-id="aab42-3667">Driver'License</span></span> 
- <span data-ttu-id="aab42-3668">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="aab42-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-3669">Driver' Lic</span></span> 
- <span data-ttu-id="aab42-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-3670">Driver' Lics</span></span> 
- <span data-ttu-id="aab42-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="aab42-3671">Driver' License</span></span> 
- <span data-ttu-id="aab42-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3672">Driver' Licenses</span></span>
- <span data-ttu-id="aab42-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="aab42-3673">Driver'sLic</span></span> 
- <span data-ttu-id="aab42-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="aab42-3674">Driver'sLics</span></span> 
- <span data-ttu-id="aab42-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="aab42-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="aab42-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="aab42-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="aab42-3677">Driver's Lic</span></span> 
- <span data-ttu-id="aab42-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="aab42-3678">Driver's Lics</span></span> 
- <span data-ttu-id="aab42-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="aab42-3679">Driver's License</span></span> 
- <span data-ttu-id="aab42-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="aab42-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="aab42-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="aab42-3681">identification number</span></span> 
- <span data-ttu-id="aab42-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="aab42-3682">identification numbers</span></span> 
- <span data-ttu-id="aab42-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="aab42-3683">identification #</span></span> 
- <span data-ttu-id="aab42-3684">id card</span><span class="sxs-lookup"><span data-stu-id="aab42-3684">id card</span></span> 
- <span data-ttu-id="aab42-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="aab42-3685">id cards</span></span> 
- <span data-ttu-id="aab42-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="aab42-3686">identification card</span></span> 
- <span data-ttu-id="aab42-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="aab42-3687">identification cards</span></span> 
- <span data-ttu-id="aab42-3688">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3688">DriverLic#</span></span> 
- <span data-ttu-id="aab42-3689">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3689">DriverLics#</span></span> 
- <span data-ttu-id="aab42-3690">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-3690">DriverLicense#</span></span> 
- <span data-ttu-id="aab42-3691">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="aab42-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3692">Driver Lic#</span></span> 
- <span data-ttu-id="aab42-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3693">Driver Lics#</span></span> 
- <span data-ttu-id="aab42-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="aab42-3694">Driver License#</span></span> 
- <span data-ttu-id="aab42-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="aab42-3696">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3696">DriversLic#</span></span> 
- <span data-ttu-id="aab42-3697">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3697">DriversLics#</span></span> 
- <span data-ttu-id="aab42-3698">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-3698">DriversLicense#</span></span> 
- <span data-ttu-id="aab42-3699">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="aab42-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="aab42-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="aab42-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="aab42-3702">Drivers License#</span></span> 
- <span data-ttu-id="aab42-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="aab42-3704">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="aab42-3705">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="aab42-3706">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="aab42-3706">Driver'License#</span></span> 
- <span data-ttu-id="aab42-3707">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="aab42-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="aab42-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="aab42-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="aab42-3710">Driver' License#</span></span> 
- <span data-ttu-id="aab42-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="aab42-3712">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="aab42-3713">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="aab42-3714">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="aab42-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="aab42-3715">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="aab42-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="aab42-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="aab42-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="aab42-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="aab42-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="aab42-3718">Driver's License#</span></span> 
- <span data-ttu-id="aab42-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="aab42-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="aab42-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="aab42-3720">id card#</span></span> 
- <span data-ttu-id="aab42-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="aab42-3721">id cards#</span></span> 
- <span data-ttu-id="aab42-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="aab42-3722">identification card#</span></span> 
- <span data-ttu-id="aab42-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="aab42-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="aab42-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="aab42-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="aab42-3725">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="aab42-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="aab42-3726">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="aab42-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="aab42-3727">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="aab42-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3728">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3728">Format</span></span>

<span data-ttu-id="aab42-3729">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="aab42-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3730">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3730">Pattern</span></span>

<span data-ttu-id="aab42-3731">格式</span><span class="sxs-lookup"><span data-stu-id="aab42-3731">Formatted:</span></span>
- <span data-ttu-id="aab42-3732">数字“9”</span><span class="sxs-lookup"><span data-stu-id="aab42-3732">The digit "9"</span></span> 
- <span data-ttu-id="aab42-3733">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3733">Two digits</span></span> 
- <span data-ttu-id="aab42-3734">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3734">A space or dash</span></span> 
- <span data-ttu-id="aab42-3735">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="aab42-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="aab42-3736">一位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3736">A digit</span></span> 
- <span data-ttu-id="aab42-3737">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="aab42-3737">A space, or dash</span></span> 
- <span data-ttu-id="aab42-3738">四位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3738">Four digits</span></span>

<span data-ttu-id="aab42-3739">纯</span><span class="sxs-lookup"><span data-stu-id="aab42-3739">Unformatted:</span></span>
- <span data-ttu-id="aab42-3740">数字“9”</span><span class="sxs-lookup"><span data-stu-id="aab42-3740">The digit "9"</span></span> 
- <span data-ttu-id="aab42-3741">两位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3741">Two digits</span></span> 
- <span data-ttu-id="aab42-3742">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="aab42-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="aab42-3743">五位数字</span><span class="sxs-lookup"><span data-stu-id="aab42-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3744">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3744">Checksum</span></span>

<span data-ttu-id="aab42-3745">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="aab42-3746">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3746">Definition</span></span>

<span data-ttu-id="aab42-3747">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3748">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3749">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="aab42-3750">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="aab42-3751">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="aab42-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="aab42-3752">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="aab42-3753">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="aab42-3754">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3755">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3756">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="aab42-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="aab42-3757">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="aab42-3758">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="aab42-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="aab42-3759">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="aab42-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="aab42-3760">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="aab42-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="aab42-3761">Keyword_itin</span></span>

- <span data-ttu-id="aab42-3762">报税</span><span class="sxs-lookup"><span data-stu-id="aab42-3762">taxpayer</span></span> 
- <span data-ttu-id="aab42-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="aab42-3763">tax id</span></span> 
- <span data-ttu-id="aab42-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="aab42-3764">tax identification</span></span> 
- <span data-ttu-id="aab42-3765">itin</span><span class="sxs-lookup"><span data-stu-id="aab42-3765">itin</span></span> 
- <span data-ttu-id="aab42-3766">ssn</span><span class="sxs-lookup"><span data-stu-id="aab42-3766">ssn</span></span> 
- <span data-ttu-id="aab42-3767">锡</span><span class="sxs-lookup"><span data-stu-id="aab42-3767">tin</span></span> 
- <span data-ttu-id="aab42-3768">social security</span><span class="sxs-lookup"><span data-stu-id="aab42-3768">social security</span></span> 
- <span data-ttu-id="aab42-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="aab42-3769">tax payer</span></span> 
- <span data-ttu-id="aab42-3770">itins</span><span class="sxs-lookup"><span data-stu-id="aab42-3770">itins</span></span> 
- <span data-ttu-id="aab42-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="aab42-3771">taxid</span></span> 
- <span data-ttu-id="aab42-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="aab42-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="aab42-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="aab42-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="aab42-3774">许可证</span><span class="sxs-lookup"><span data-stu-id="aab42-3774">License</span></span> 
- <span data-ttu-id="aab42-3775">通讯</span><span class="sxs-lookup"><span data-stu-id="aab42-3775">DL</span></span> 
- <span data-ttu-id="aab42-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="aab42-3776">DOB</span></span> 
- <span data-ttu-id="aab42-3777">出生日期</span><span class="sxs-lookup"><span data-stu-id="aab42-3777">Birthdate</span></span> 
- <span data-ttu-id="aab42-3778">一定</span><span class="sxs-lookup"><span data-stu-id="aab42-3778">Birthday</span></span> 
- <span data-ttu-id="aab42-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="aab42-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="aab42-3780">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="aab42-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="aab42-3781">Format</span><span class="sxs-lookup"><span data-stu-id="aab42-3781">Format</span></span>

<span data-ttu-id="aab42-3782">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="aab42-3783">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="aab42-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="aab42-3784">模式</span><span class="sxs-lookup"><span data-stu-id="aab42-3784">Pattern</span></span>

<span data-ttu-id="aab42-3785">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="aab42-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="aab42-3786">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="aab42-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="aab42-3787">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="aab42-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="aab42-3788">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="aab42-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="aab42-3789">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="aab42-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="aab42-3790">校验和</span><span class="sxs-lookup"><span data-stu-id="aab42-3790">Checksum</span></span>

<span data-ttu-id="aab42-3791">否</span><span class="sxs-lookup"><span data-stu-id="aab42-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="aab42-3792">定义</span><span class="sxs-lookup"><span data-stu-id="aab42-3792">Definition</span></span>

<span data-ttu-id="aab42-3793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3794">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3795">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="aab42-3796">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3797">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3798">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="aab42-3799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3800">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3801">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="aab42-3802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="aab42-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="aab42-3803">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="aab42-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="aab42-3804">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="aab42-3804">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="aab42-3805">关键字</span><span class="sxs-lookup"><span data-stu-id="aab42-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="aab42-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="aab42-3806">Keyword_ssn</span></span>

- <span data-ttu-id="aab42-3807">Social Security</span><span class="sxs-lookup"><span data-stu-id="aab42-3807">Social Security</span></span> 
- <span data-ttu-id="aab42-3808">Social Security#</span><span class="sxs-lookup"><span data-stu-id="aab42-3808">Social Security#</span></span> 
- <span data-ttu-id="aab42-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="aab42-3809">Soc Sec</span></span> 
- <span data-ttu-id="aab42-3810">SSN</span><span class="sxs-lookup"><span data-stu-id="aab42-3810">SSN</span></span> 
- <span data-ttu-id="aab42-3811">SSN</span><span class="sxs-lookup"><span data-stu-id="aab42-3811">SSNS</span></span> 
- <span data-ttu-id="aab42-3812">SSN#</span><span class="sxs-lookup"><span data-stu-id="aab42-3812">SSN#</span></span> 
- <span data-ttu-id="aab42-3813">SS#</span><span class="sxs-lookup"><span data-stu-id="aab42-3813">SS#</span></span> 
- <span data-ttu-id="aab42-3814">SSID</span><span class="sxs-lookup"><span data-stu-id="aab42-3814">SSID</span></span> 
   
