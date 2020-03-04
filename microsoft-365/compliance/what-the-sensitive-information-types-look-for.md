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
ms.openlocfilehash: 368ccef9e5213a7494140d2c305ddafe1e0c3f79
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409507"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="35c9f-104">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="35c9f-104">What the sensitive information types look for</span></span>

<span data-ttu-id="35c9f-105">Office 365 安全&amp;合规中心中的数据丢失防护（DLP）包括许多可供您在 DLP 策略中使用的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="35c9f-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="35c9f-106">本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="35c9f-107">敏感信息类型通过正则表达式或函数可以识别的模式定义。</span><span class="sxs-lookup"><span data-stu-id="35c9f-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="35c9f-108">此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="35c9f-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="35c9f-109">可信度和相似度也会在评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="35c9f-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="35c9f-110">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="35c9f-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-111">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-111">Format</span></span>

<span data-ttu-id="35c9f-112">9 个数字，可以是格式化模式，也可以是非格式化模式 </span><span class="sxs-lookup"><span data-stu-id="35c9f-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-113">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-113">Pattern</span></span>

<span data-ttu-id="35c9f-114">格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-114">Formatted:</span></span>
- <span data-ttu-id="35c9f-115">四个数字，以 0、 1、 2、 3、 6、 7 或 8 开头</span><span class="sxs-lookup"><span data-stu-id="35c9f-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="35c9f-116">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-116">A hyphen</span></span>
- <span data-ttu-id="35c9f-117">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-117">Four digits</span></span>
- <span data-ttu-id="35c9f-118">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-118">A hyphen</span></span>
- <span data-ttu-id="35c9f-119">一个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-119">A digit</span></span>

<span data-ttu-id="35c9f-120">无格式：9个连续的数字，以0、1、2、3、6、7或8开头</span><span class="sxs-lookup"><span data-stu-id="35c9f-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="35c9f-121">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-121">Checksum</span></span>

<span data-ttu-id="35c9f-122">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-123">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-123">Definition</span></span>

<span data-ttu-id="35c9f-124">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-125">函数 Func_aba_routing 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-126">找到 Keyword_ABA_Routing 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="35c9f-127">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="35c9f-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="35c9f-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="35c9f-129">aba</span><span class="sxs-lookup"><span data-stu-id="35c9f-129">aba</span></span>
- <span data-ttu-id="35c9f-130">aba #</span><span class="sxs-lookup"><span data-stu-id="35c9f-130">aba #</span></span>
- <span data-ttu-id="35c9f-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="35c9f-131">aba routing #</span></span>
- <span data-ttu-id="35c9f-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="35c9f-132">aba routing number</span></span>
- <span data-ttu-id="35c9f-133">aba#</span><span class="sxs-lookup"><span data-stu-id="35c9f-133">aba#</span></span>
- <span data-ttu-id="35c9f-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="35c9f-134">abarouting#</span></span>
- <span data-ttu-id="35c9f-135">aba number</span><span class="sxs-lookup"><span data-stu-id="35c9f-135">aba number</span></span>
- <span data-ttu-id="35c9f-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-136">abaroutingnumber</span></span>
- <span data-ttu-id="35c9f-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="35c9f-137">american bank association routing #</span></span>
- <span data-ttu-id="35c9f-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="35c9f-138">american bank association routing number</span></span>
- <span data-ttu-id="35c9f-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="35c9f-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="35c9f-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="35c9f-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="35c9f-141">bank routing number</span></span>
- <span data-ttu-id="35c9f-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="35c9f-142">bankrouting#</span></span>
- <span data-ttu-id="35c9f-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-143">bankroutingnumber</span></span>
- <span data-ttu-id="35c9f-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="35c9f-144">routing transit number</span></span>
- <span data-ttu-id="35c9f-145">RTN</span><span class="sxs-lookup"><span data-stu-id="35c9f-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="35c9f-146">阿根廷国家身份证 (DNI) 号</span><span class="sxs-lookup"><span data-stu-id="35c9f-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-147">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-147">Format</span></span>

<span data-ttu-id="35c9f-148">八个数字，用点分隔</span><span class="sxs-lookup"><span data-stu-id="35c9f-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-149">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-149">Pattern</span></span>

<span data-ttu-id="35c9f-150">八个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-150">Eight digits:</span></span>
- <span data-ttu-id="35c9f-151">两个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-151">Two digits</span></span>
- <span data-ttu-id="35c9f-152">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-152">A period</span></span>
- <span data-ttu-id="35c9f-153">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-153">Three digits</span></span>
- <span data-ttu-id="35c9f-154">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-154">A period</span></span>
- <span data-ttu-id="35c9f-155">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-156">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-156">Checksum</span></span>

<span data-ttu-id="35c9f-157">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-158">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-158">Definition</span></span>

<span data-ttu-id="35c9f-159">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-160">正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-161">找到 Keyword_argentina_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-162">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="35c9f-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="35c9f-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="35c9f-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="35c9f-165">标识</span><span class="sxs-lookup"><span data-stu-id="35c9f-165">Identity</span></span> 
- <span data-ttu-id="35c9f-166">标识国家/地区身份卡片</span><span class="sxs-lookup"><span data-stu-id="35c9f-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="35c9f-167">DNI</span><span class="sxs-lookup"><span data-stu-id="35c9f-167">DNI</span></span> 
- <span data-ttu-id="35c9f-168">个人的网络国家注册表</span><span class="sxs-lookup"><span data-stu-id="35c9f-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="35c9f-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="35c9f-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="35c9f-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="35c9f-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="35c9f-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="35c9f-171">Identidad</span></span> 
- <span data-ttu-id="35c9f-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="35c9f-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="35c9f-173">澳大利亚银行帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-174">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-174">Format</span></span>

<span data-ttu-id="35c9f-175">6-10 个数字，带或不带 BSB 号码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-176">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-176">Pattern</span></span>

<span data-ttu-id="35c9f-177">帐号为 6-10 个数字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="35c9f-178">澳大利亚银行州级分部编号：</span><span class="sxs-lookup"><span data-stu-id="35c9f-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="35c9f-179">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-179">Three digits</span></span> 
- <span data-ttu-id="35c9f-180">连字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-180">A hyphen</span></span> 
- <span data-ttu-id="35c9f-181">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-182">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-182">Checksum</span></span>

<span data-ttu-id="35c9f-183">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-184">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-184">Definition</span></span>

<span data-ttu-id="35c9f-185">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-186">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="35c9f-187">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="35c9f-188">正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="35c9f-189">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-190">正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="35c9f-191">找到 Keyword_australia_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-192">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="35c9f-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="35c9f-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="35c9f-194">swift bank code</span></span>
- <span data-ttu-id="35c9f-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="35c9f-195">correspondent bank</span></span>
- <span data-ttu-id="35c9f-196">base currency</span><span class="sxs-lookup"><span data-stu-id="35c9f-196">base currency</span></span>
- <span data-ttu-id="35c9f-197">usa account</span><span class="sxs-lookup"><span data-stu-id="35c9f-197">usa account</span></span>
- <span data-ttu-id="35c9f-198">holder address</span><span class="sxs-lookup"><span data-stu-id="35c9f-198">holder address</span></span>
- <span data-ttu-id="35c9f-199">bank address</span><span class="sxs-lookup"><span data-stu-id="35c9f-199">bank address</span></span>
- <span data-ttu-id="35c9f-200">information account</span><span class="sxs-lookup"><span data-stu-id="35c9f-200">information account</span></span>
- <span data-ttu-id="35c9f-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="35c9f-201">fund transfers</span></span>
- <span data-ttu-id="35c9f-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="35c9f-202">bank charges</span></span>
- <span data-ttu-id="35c9f-203">bank details</span><span class="sxs-lookup"><span data-stu-id="35c9f-203">bank details</span></span>
- <span data-ttu-id="35c9f-204">banking information</span><span class="sxs-lookup"><span data-stu-id="35c9f-204">banking information</span></span>
- <span data-ttu-id="35c9f-205">full names</span><span class="sxs-lookup"><span data-stu-id="35c9f-205">full names</span></span>
- <span data-ttu-id="35c9f-206">iaea</span><span class="sxs-lookup"><span data-stu-id="35c9f-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="35c9f-207">澳大利亚驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-208">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-208">Format</span></span>

<span data-ttu-id="35c9f-209">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-210">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-210">Pattern</span></span>

<span data-ttu-id="35c9f-211">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="35c9f-212">两位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-213">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-213">Two digits</span></span> 
- <span data-ttu-id="35c9f-214">五位数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="35c9f-215">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-215">OR</span></span>

- <span data-ttu-id="35c9f-216">1-2 个可选字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-217">4-9 位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-217">4-9 digits</span></span>

<span data-ttu-id="35c9f-218">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-218">OR</span></span>

- <span data-ttu-id="35c9f-219">九个数字或字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-220">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-220">Checksum</span></span>

<span data-ttu-id="35c9f-221">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-222">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-222">Definition</span></span>

<span data-ttu-id="35c9f-223">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-224">正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-225">找到 Keyword_australia_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="35c9f-226">未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-227">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="35c9f-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="35c9f-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="35c9f-229">international driving permits</span></span>
- <span data-ttu-id="35c9f-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="35c9f-230">australian automobile association</span></span>
- <span data-ttu-id="35c9f-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="35c9f-231">international driving permit</span></span>
- <span data-ttu-id="35c9f-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-232">DriverLicence</span></span>
- <span data-ttu-id="35c9f-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-233">DriverLicences</span></span>
- <span data-ttu-id="35c9f-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-234">Driver Lic</span></span>
- <span data-ttu-id="35c9f-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-235">Driver Licence</span></span>
- <span data-ttu-id="35c9f-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-236">Driver Licences</span></span>
- <span data-ttu-id="35c9f-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-237">DriversLic</span></span>
- <span data-ttu-id="35c9f-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-238">DriversLicence</span></span>
- <span data-ttu-id="35c9f-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-239">DriversLicences</span></span>
- <span data-ttu-id="35c9f-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-240">Drivers Lic</span></span>
- <span data-ttu-id="35c9f-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-241">Drivers Lics</span></span>
- <span data-ttu-id="35c9f-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-242">Drivers Licence</span></span>
- <span data-ttu-id="35c9f-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-243">Drivers Licences</span></span>
- <span data-ttu-id="35c9f-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-244">Driver'Lic</span></span>
- <span data-ttu-id="35c9f-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-245">Driver'Lics</span></span>
- <span data-ttu-id="35c9f-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-246">Driver'Licence</span></span>
- <span data-ttu-id="35c9f-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-247">Driver'Licences</span></span>
- <span data-ttu-id="35c9f-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-248">Driver' Lic</span></span>
- <span data-ttu-id="35c9f-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-249">Driver' Lics</span></span>
- <span data-ttu-id="35c9f-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-250">Driver' Licence</span></span>
- <span data-ttu-id="35c9f-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-251">Driver' Licences</span></span>
- <span data-ttu-id="35c9f-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-252">Driver'sLic</span></span>
- <span data-ttu-id="35c9f-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-253">Driver'sLics</span></span>
- <span data-ttu-id="35c9f-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-254">Driver'sLicence</span></span>
- <span data-ttu-id="35c9f-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-255">Driver'sLicences</span></span>
- <span data-ttu-id="35c9f-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-256">Driver's Lic</span></span>
- <span data-ttu-id="35c9f-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-257">Driver's Lics</span></span>
- <span data-ttu-id="35c9f-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-258">Driver's Licence</span></span>
- <span data-ttu-id="35c9f-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-259">Driver's Licences</span></span>
- <span data-ttu-id="35c9f-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-260">DriverLic#</span></span>
- <span data-ttu-id="35c9f-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-261">DriverLics#</span></span>
- <span data-ttu-id="35c9f-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-262">DriverLicence#</span></span>
- <span data-ttu-id="35c9f-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-263">DriverLicences#</span></span>
- <span data-ttu-id="35c9f-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-264">Driver Lic#</span></span>
- <span data-ttu-id="35c9f-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-265">Driver Lics#</span></span>
- <span data-ttu-id="35c9f-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-266">Driver Licence#</span></span>
- <span data-ttu-id="35c9f-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-267">Driver Licences#</span></span>
- <span data-ttu-id="35c9f-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-268">DriversLic#</span></span>
- <span data-ttu-id="35c9f-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-269">DriversLics#</span></span>
- <span data-ttu-id="35c9f-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-270">DriversLicence#</span></span>
- <span data-ttu-id="35c9f-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-271">DriversLicences#</span></span>
- <span data-ttu-id="35c9f-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-272">Drivers Lic#</span></span>
- <span data-ttu-id="35c9f-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-273">Drivers Lics#</span></span>
- <span data-ttu-id="35c9f-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-274">Drivers Licence#</span></span>
- <span data-ttu-id="35c9f-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-275">Drivers Licences#</span></span>
- <span data-ttu-id="35c9f-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-276">Driver'Lic#</span></span>
- <span data-ttu-id="35c9f-277">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-277">Driver'Lics#</span></span>
- <span data-ttu-id="35c9f-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-278">Driver'Licence#</span></span>
- <span data-ttu-id="35c9f-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-279">Driver'Licences#</span></span>
- <span data-ttu-id="35c9f-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-280">Driver' Lic#</span></span>
- <span data-ttu-id="35c9f-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-281">Driver' Lics#</span></span>
- <span data-ttu-id="35c9f-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-282">Driver' Licence#</span></span>
- <span data-ttu-id="35c9f-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-283">Driver' Licences#</span></span>
- <span data-ttu-id="35c9f-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-284">Driver'sLic#</span></span>
- <span data-ttu-id="35c9f-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-285">Driver'sLics#</span></span>
- <span data-ttu-id="35c9f-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-286">Driver'sLicence#</span></span>
- <span data-ttu-id="35c9f-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-287">Driver'sLicences#</span></span>
- <span data-ttu-id="35c9f-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-288">Driver's Lic#</span></span>
- <span data-ttu-id="35c9f-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-289">Driver's Lics#</span></span>
- <span data-ttu-id="35c9f-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-290">Driver's Licence#</span></span>
- <span data-ttu-id="35c9f-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="35c9f-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="35c9f-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="35c9f-293">aaa</span><span class="sxs-lookup"><span data-stu-id="35c9f-293">aaa</span></span>
- <span data-ttu-id="35c9f-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-294">DriverLicense</span></span>
- <span data-ttu-id="35c9f-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-295">DriverLicenses</span></span>
- <span data-ttu-id="35c9f-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="35c9f-296">Driver License</span></span>
- <span data-ttu-id="35c9f-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-297">Driver Licenses</span></span>
- <span data-ttu-id="35c9f-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-298">DriversLicense</span></span>
- <span data-ttu-id="35c9f-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-299">DriversLicenses</span></span>
- <span data-ttu-id="35c9f-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="35c9f-300">Drivers License</span></span>
- <span data-ttu-id="35c9f-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-301">Drivers Licenses</span></span>
- <span data-ttu-id="35c9f-302">Driver'License</span><span class="sxs-lookup"><span data-stu-id="35c9f-302">Driver'License</span></span>
- <span data-ttu-id="35c9f-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-303">Driver'Licenses</span></span>
- <span data-ttu-id="35c9f-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="35c9f-304">Driver' License</span></span>
- <span data-ttu-id="35c9f-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-305">Driver' Licenses</span></span>
- <span data-ttu-id="35c9f-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-306">Driver'sLicense</span></span>
- <span data-ttu-id="35c9f-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-307">Driver'sLicenses</span></span>
- <span data-ttu-id="35c9f-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="35c9f-308">Driver's License</span></span>
- <span data-ttu-id="35c9f-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-309">Driver's Licenses</span></span>
- <span data-ttu-id="35c9f-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-310">DriverLicense#</span></span>
- <span data-ttu-id="35c9f-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-311">DriverLicenses#</span></span>
- <span data-ttu-id="35c9f-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-312">Driver License#</span></span>
- <span data-ttu-id="35c9f-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-313">Driver Licenses#</span></span>
- <span data-ttu-id="35c9f-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-314">DriversLicense#</span></span>
- <span data-ttu-id="35c9f-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-315">DriversLicenses#</span></span>
- <span data-ttu-id="35c9f-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-316">Drivers License#</span></span>
- <span data-ttu-id="35c9f-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-317">Drivers Licenses#</span></span>
- <span data-ttu-id="35c9f-318">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-318">Driver'License#</span></span>
- <span data-ttu-id="35c9f-319">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-319">Driver'Licenses#</span></span>
- <span data-ttu-id="35c9f-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-320">Driver' License#</span></span>
- <span data-ttu-id="35c9f-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-321">Driver' Licenses#</span></span>
- <span data-ttu-id="35c9f-322">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-322">Driver'sLicense#</span></span>
- <span data-ttu-id="35c9f-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="35c9f-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-324">Driver's License#</span></span>
- <span data-ttu-id="35c9f-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="35c9f-326">澳大利亚医疗帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-327">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-327">Format</span></span>

<span data-ttu-id="35c9f-328">10-11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-329">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-329">Pattern</span></span>

<span data-ttu-id="35c9f-330">10-11 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-330">10-11 digits:</span></span>
- <span data-ttu-id="35c9f-331">第一个数字范围为 2-6</span><span class="sxs-lookup"><span data-stu-id="35c9f-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="35c9f-332">第九个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="35c9f-333">第十个数字是问题数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="35c9f-334">第十一个数字（可选）是个人号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-335">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-335">Checksum</span></span>

<span data-ttu-id="35c9f-336">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-337">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-337">Definition</span></span>

<span data-ttu-id="35c9f-338">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-339">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-340">找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="35c9f-341">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-341">The checksum passes.</span></span>

<span data-ttu-id="35c9f-342">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-343">函数 Func_australian_medical_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-344">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-345">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="35c9f-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="35c9f-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="35c9f-347">bank account details</span></span>
- <span data-ttu-id="35c9f-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="35c9f-348">medicare payments</span></span>
- <span data-ttu-id="35c9f-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="35c9f-349">mortgage account</span></span>
- <span data-ttu-id="35c9f-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="35c9f-350">bank payments</span></span>
- <span data-ttu-id="35c9f-351">information branch</span><span class="sxs-lookup"><span data-stu-id="35c9f-351">information branch</span></span>
- <span data-ttu-id="35c9f-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="35c9f-352">credit card loan</span></span>
- <span data-ttu-id="35c9f-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="35c9f-353">department of human services</span></span>
- <span data-ttu-id="35c9f-354">local service</span><span class="sxs-lookup"><span data-stu-id="35c9f-354">local service</span></span>
- <span data-ttu-id="35c9f-355">medicare</span><span class="sxs-lookup"><span data-stu-id="35c9f-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="35c9f-356">澳大利亚护照号</span><span class="sxs-lookup"><span data-stu-id="35c9f-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-357">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-357">Format</span></span>

<span data-ttu-id="35c9f-358">一个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-359">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-359">Pattern</span></span>

<span data-ttu-id="35c9f-360">一个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-361">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-361">Checksum</span></span>

<span data-ttu-id="35c9f-362">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-363">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-363">Definition</span></span>

<span data-ttu-id="35c9f-364">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-365">正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-366">找到 Keyword_passport 或 Keyword_australia_passport_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-367">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="35c9f-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-368">Keyword_passport</span></span>

- <span data-ttu-id="35c9f-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-369">Passport Number</span></span>
- <span data-ttu-id="35c9f-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="35c9f-370">Passport No</span></span>
- <span data-ttu-id="35c9f-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-371">Passport #</span></span>
- <span data-ttu-id="35c9f-372">登记卡#</span><span class="sxs-lookup"><span data-stu-id="35c9f-372">Passport#</span></span>
- <span data-ttu-id="35c9f-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="35c9f-373">PassportID</span></span>
- <span data-ttu-id="35c9f-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="35c9f-374">Passportno</span></span>
- <span data-ttu-id="35c9f-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-375">passportnumber</span></span>
- <span data-ttu-id="35c9f-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-376">パスポート</span></span>
- <span data-ttu-id="35c9f-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-377">パスポート番号</span></span>
- <span data-ttu-id="35c9f-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-378">パスポートのNum</span></span>
- <span data-ttu-id="35c9f-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-379">パスポート ＃</span></span> 
- <span data-ttu-id="35c9f-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="35c9f-380">Numéro de passeport</span></span>
- <span data-ttu-id="35c9f-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="35c9f-381">Passeport n °</span></span>
- <span data-ttu-id="35c9f-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="35c9f-382">Passeport Non</span></span>
- <span data-ttu-id="35c9f-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-383">Passeport #</span></span>
- <span data-ttu-id="35c9f-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="35c9f-384">Passeport#</span></span>
- <span data-ttu-id="35c9f-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="35c9f-385">PasseportNon</span></span>
- <span data-ttu-id="35c9f-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="35c9f-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="35c9f-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="35c9f-388">登记卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-388">passport</span></span>
- <span data-ttu-id="35c9f-389">passport details</span><span class="sxs-lookup"><span data-stu-id="35c9f-389">passport details</span></span>
- <span data-ttu-id="35c9f-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="35c9f-390">immigration and citizenship</span></span>
- <span data-ttu-id="35c9f-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="35c9f-391">commonwealth of australia</span></span>
- <span data-ttu-id="35c9f-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="35c9f-392">department of immigration</span></span>
- <span data-ttu-id="35c9f-393">residential address</span><span class="sxs-lookup"><span data-stu-id="35c9f-393">residential address</span></span>
- <span data-ttu-id="35c9f-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="35c9f-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="35c9f-395">反之</span><span class="sxs-lookup"><span data-stu-id="35c9f-395">visa</span></span>
- <span data-ttu-id="35c9f-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-396">national identity card</span></span>
- <span data-ttu-id="35c9f-397">passport number</span><span class="sxs-lookup"><span data-stu-id="35c9f-397">passport number</span></span>
- <span data-ttu-id="35c9f-398">travel document</span><span class="sxs-lookup"><span data-stu-id="35c9f-398">travel document</span></span>
- <span data-ttu-id="35c9f-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="35c9f-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="35c9f-400">澳大利亚税号</span><span class="sxs-lookup"><span data-stu-id="35c9f-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-401">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-401">Format</span></span>

<span data-ttu-id="35c9f-402">8-9 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-403">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-403">Pattern</span></span>

<span data-ttu-id="35c9f-404">通常 8-9 位数字，显示中包含空格，如下所示：</span><span class="sxs-lookup"><span data-stu-id="35c9f-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="35c9f-405">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-405">Three digits</span></span> 
- <span data-ttu-id="35c9f-406">可选空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-406">An optional space</span></span> 
- <span data-ttu-id="35c9f-407">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-407">Three digits</span></span> 
- <span data-ttu-id="35c9f-408">可选空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-408">An optional space</span></span> 
- <span data-ttu-id="35c9f-409">2-3 位数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-410">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-410">Checksum</span></span>

<span data-ttu-id="35c9f-411">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-412">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-412">Definition</span></span>

<span data-ttu-id="35c9f-413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-414">函数 Func_australian_tax_file_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-415">未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="35c9f-416">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-417">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="35c9f-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="35c9f-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="35c9f-419">australian business number</span></span>
- <span data-ttu-id="35c9f-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="35c9f-420">marginal tax rate</span></span>
- <span data-ttu-id="35c9f-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="35c9f-421">medicare levy</span></span>
- <span data-ttu-id="35c9f-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="35c9f-422">portfolio number</span></span>
- <span data-ttu-id="35c9f-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="35c9f-423">service veterans</span></span>
- <span data-ttu-id="35c9f-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="35c9f-424">withholding tax</span></span>
- <span data-ttu-id="35c9f-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="35c9f-425">individual tax return</span></span>
- <span data-ttu-id="35c9f-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="35c9f-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="35c9f-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="35c9f-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="35c9f-428">00000000</span><span class="sxs-lookup"><span data-stu-id="35c9f-428">00000000</span></span>
- <span data-ttu-id="35c9f-429">11111111</span><span class="sxs-lookup"><span data-stu-id="35c9f-429">11111111</span></span>
- <span data-ttu-id="35c9f-430">22222222</span><span class="sxs-lookup"><span data-stu-id="35c9f-430">22222222</span></span>
- <span data-ttu-id="35c9f-431">33333333</span><span class="sxs-lookup"><span data-stu-id="35c9f-431">33333333</span></span>
- <span data-ttu-id="35c9f-432">44444444</span><span class="sxs-lookup"><span data-stu-id="35c9f-432">44444444</span></span>
- <span data-ttu-id="35c9f-433">55555555</span><span class="sxs-lookup"><span data-stu-id="35c9f-433">55555555</span></span>
- <span data-ttu-id="35c9f-434">66666666</span><span class="sxs-lookup"><span data-stu-id="35c9f-434">66666666</span></span>
- <span data-ttu-id="35c9f-435">77777777</span><span class="sxs-lookup"><span data-stu-id="35c9f-435">77777777</span></span>
- <span data-ttu-id="35c9f-436">88888888</span><span class="sxs-lookup"><span data-stu-id="35c9f-436">88888888</span></span>
- <span data-ttu-id="35c9f-437">99999999</span><span class="sxs-lookup"><span data-stu-id="35c9f-437">99999999</span></span>
- <span data-ttu-id="35c9f-438">000000000</span><span class="sxs-lookup"><span data-stu-id="35c9f-438">000000000</span></span>
- <span data-ttu-id="35c9f-439">111111111</span><span class="sxs-lookup"><span data-stu-id="35c9f-439">111111111</span></span>
- <span data-ttu-id="35c9f-440">222222222</span><span class="sxs-lookup"><span data-stu-id="35c9f-440">222222222</span></span>
- <span data-ttu-id="35c9f-441">333333333</span><span class="sxs-lookup"><span data-stu-id="35c9f-441">333333333</span></span>
- <span data-ttu-id="35c9f-442">444444444</span><span class="sxs-lookup"><span data-stu-id="35c9f-442">444444444</span></span>
- <span data-ttu-id="35c9f-443">555555555</span><span class="sxs-lookup"><span data-stu-id="35c9f-443">555555555</span></span>
- <span data-ttu-id="35c9f-444">666666666</span><span class="sxs-lookup"><span data-stu-id="35c9f-444">666666666</span></span>
- <span data-ttu-id="35c9f-445">777777777</span><span class="sxs-lookup"><span data-stu-id="35c9f-445">777777777</span></span>
- <span data-ttu-id="35c9f-446">888888888</span><span class="sxs-lookup"><span data-stu-id="35c9f-446">888888888</span></span>
- <span data-ttu-id="35c9f-447">999999999</span><span class="sxs-lookup"><span data-stu-id="35c9f-447">999999999</span></span>
- <span data-ttu-id="35c9f-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="35c9f-448">0000000000</span></span>
- <span data-ttu-id="35c9f-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="35c9f-449">1111111111</span></span>
- <span data-ttu-id="35c9f-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="35c9f-450">2222222222</span></span>
- <span data-ttu-id="35c9f-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="35c9f-451">3333333333</span></span>
- <span data-ttu-id="35c9f-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="35c9f-452">4444444444</span></span>
- <span data-ttu-id="35c9f-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="35c9f-453">5555555555</span></span>
- <span data-ttu-id="35c9f-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="35c9f-454">6666666666</span></span>
- <span data-ttu-id="35c9f-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="35c9f-455">7777777777</span></span>
- <span data-ttu-id="35c9f-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="35c9f-456">8888888888</span></span>
- <span data-ttu-id="35c9f-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="35c9f-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="35c9f-458">Azure DocumentDB 身份验证密钥</span><span class="sxs-lookup"><span data-stu-id="35c9f-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-459">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-459">Format</span></span>

<span data-ttu-id="35c9f-460">字符串 "DocumentDb"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="35c9f-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-461">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-461">Pattern</span></span>

- <span data-ttu-id="35c9f-462">字符串 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="35c9f-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="35c9f-463">介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-464">大于号（>）、等号（=）、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="35c9f-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="35c9f-465">86字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-466">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-467">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-467">Checksum</span></span>

<span data-ttu-id="35c9f-468">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-469">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-469">Definition</span></span>

<span data-ttu-id="35c9f-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-471">正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-472">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-473">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-475">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-476">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-476">contoso</span></span>
- <span data-ttu-id="35c9f-477">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-477">fabrikam</span></span>
- <span data-ttu-id="35c9f-478">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-478">northwind</span></span>
- <span data-ttu-id="35c9f-479">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-479">sandbox</span></span>
- <span data-ttu-id="35c9f-480">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-480">onebox</span></span>
- <span data-ttu-id="35c9f-481">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-481">localhost</span></span>
- <span data-ttu-id="35c9f-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-482">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-484">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-484">com</span></span>
- <span data-ttu-id="35c9f-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-486">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="35c9f-487">Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串</span><span class="sxs-lookup"><span data-stu-id="35c9f-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-488">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-488">Format</span></span>

<span data-ttu-id="35c9f-489">字符串 "Server"、"server" 或 "data source"，后跟下面模式中所述的字符和字符串，包括字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-490">com "或" cloudapp "。</span><span class="sxs-lookup"><span data-stu-id="35c9f-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-491">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="35c9f-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-492">net "和字符串" Password "或" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="35c9f-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-493">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-493">Pattern</span></span>

- <span data-ttu-id="35c9f-494">字符串 "Server"、"server" 或 "data source"</span><span class="sxs-lookup"><span data-stu-id="35c9f-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="35c9f-495">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-496">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-496">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-497">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-498">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-499">字符串 "cloudapp"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-500">com "，" cloudapp。</span><span class="sxs-lookup"><span data-stu-id="35c9f-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-501">net "或" database。</span><span class="sxs-lookup"><span data-stu-id="35c9f-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-502">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-502">net"</span></span>
- <span data-ttu-id="35c9f-503">介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-504">字符串 "Password"、"password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="35c9f-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="35c9f-505">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-506">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-506">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-507">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-508">一个或多个不是分号（;)、引号（"）或撇号（'）的字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="35c9f-509">分号（;)、引号（"）或撇号（'）</span><span class="sxs-lookup"><span data-stu-id="35c9f-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-510">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-510">Checksum</span></span>

<span data-ttu-id="35c9f-511">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-512">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-512">Definition</span></span>

<span data-ttu-id="35c9f-513">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-514">正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-515">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-516">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-518">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-519">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-519">contoso</span></span>
- <span data-ttu-id="35c9f-520">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-520">fabrikam</span></span>
- <span data-ttu-id="35c9f-521">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-521">northwind</span></span>
- <span data-ttu-id="35c9f-522">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-522">sandbox</span></span>
- <span data-ttu-id="35c9f-523">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-523">onebox</span></span>
- <span data-ttu-id="35c9f-524">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-524">localhost</span></span>
- <span data-ttu-id="35c9f-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-525">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-527">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-527">com</span></span>
- <span data-ttu-id="35c9f-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-529">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="35c9f-530">Azure IoT 连接字符串</span><span class="sxs-lookup"><span data-stu-id="35c9f-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-531">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-531">Format</span></span>

<span data-ttu-id="35c9f-532">字符串 "HostName"，后跟下面模式中所示的字符和字符串，包括字符串 "azure 设备"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-533">net "和" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="35c9f-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-534">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-534">Pattern</span></span>

- <span data-ttu-id="35c9f-535">字符串 "HostName"</span><span class="sxs-lookup"><span data-stu-id="35c9f-535">The string "HostName"</span></span>
- <span data-ttu-id="35c9f-536">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-537">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-537">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-538">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-539">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-540">字符串 "azure 设备。</span><span class="sxs-lookup"><span data-stu-id="35c9f-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-541">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-541">net"</span></span>
- <span data-ttu-id="35c9f-542">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-543">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="35c9f-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="35c9f-544">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-545">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-545">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-546">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-547">43字母、数字、数字、正斜杠（/）或加号（+）的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-548">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-549">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-549">Checksum</span></span>

<span data-ttu-id="35c9f-550">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-551">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-551">Definition</span></span>

<span data-ttu-id="35c9f-552">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-553">正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-554">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-555">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-557">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-558">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-558">contoso</span></span>
- <span data-ttu-id="35c9f-559">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-559">fabrikam</span></span>
- <span data-ttu-id="35c9f-560">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-560">northwind</span></span>
- <span data-ttu-id="35c9f-561">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-561">sandbox</span></span>
- <span data-ttu-id="35c9f-562">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-562">onebox</span></span>
- <span data-ttu-id="35c9f-563">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-563">localhost</span></span>
- <span data-ttu-id="35c9f-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-564">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-566">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-566">com</span></span>
- <span data-ttu-id="35c9f-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-568">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="35c9f-569">Azure 发布设置密码</span><span class="sxs-lookup"><span data-stu-id="35c9f-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-570">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-570">Format</span></span>

<span data-ttu-id="35c9f-571">字符串 "userpwd ="，后跟一个字母数字字符串。</span><span class="sxs-lookup"><span data-stu-id="35c9f-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-572">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-572">Pattern</span></span>

- <span data-ttu-id="35c9f-573">字符串 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="35c9f-573">The string "userpwd="</span></span>
- <span data-ttu-id="35c9f-574">任何60小写字母或数字的组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="35c9f-575">一个引号（"）</span><span class="sxs-lookup"><span data-stu-id="35c9f-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-576">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-576">Checksum</span></span>

<span data-ttu-id="35c9f-577">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-578">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-578">Definition</span></span>

<span data-ttu-id="35c9f-579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-580">正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-581">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="35c9f-582">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-584">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-585">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-585">contoso</span></span>
- <span data-ttu-id="35c9f-586">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-586">fabrikam</span></span>
- <span data-ttu-id="35c9f-587">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-587">northwind</span></span>
- <span data-ttu-id="35c9f-588">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-588">sandbox</span></span>
- <span data-ttu-id="35c9f-589">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-589">onebox</span></span>
- <span data-ttu-id="35c9f-590">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-590">localhost</span></span>
- <span data-ttu-id="35c9f-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-591">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-593">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-593">com</span></span>
- <span data-ttu-id="35c9f-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-595">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="35c9f-596">Azure Redis 缓存连接字符串</span><span class="sxs-lookup"><span data-stu-id="35c9f-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-597">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-597">Format</span></span>

<span data-ttu-id="35c9f-598">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-599">net "，后跟下面的模式中所述的字符和字符串，包括字符串" password "或" pwd "。</span><span class="sxs-lookup"><span data-stu-id="35c9f-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-600">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-600">Pattern</span></span>

- <span data-ttu-id="35c9f-601">字符串 "redis"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-602">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-602">net"</span></span>
- <span data-ttu-id="35c9f-603">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-604">字符串 "password" 或 "pwd"</span><span class="sxs-lookup"><span data-stu-id="35c9f-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="35c9f-605">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-606">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-606">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-607">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-608">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="35c9f-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-609">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-610">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-610">Checksum</span></span>

<span data-ttu-id="35c9f-611">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-612">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-612">Definition</span></span>

<span data-ttu-id="35c9f-613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-614">正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="35c9f-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="35c9f-615">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-616">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-618">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-619">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-619">contoso</span></span>
- <span data-ttu-id="35c9f-620">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-620">fabrikam</span></span>
- <span data-ttu-id="35c9f-621">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-621">northwind</span></span>
- <span data-ttu-id="35c9f-622">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-622">sandbox</span></span>
- <span data-ttu-id="35c9f-623">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-623">onebox</span></span>
- <span data-ttu-id="35c9f-624">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-624">localhost</span></span>
- <span data-ttu-id="35c9f-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-625">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-627">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-627">com</span></span>
- <span data-ttu-id="35c9f-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-629">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="35c9f-630">Azure SA</span><span class="sxs-lookup"><span data-stu-id="35c9f-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-631">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-631">Format</span></span>

<span data-ttu-id="35c9f-632">字符串 "sig"，后跟下面模式中所示的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="35c9f-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-633">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-633">Pattern</span></span>

- <span data-ttu-id="35c9f-634">字符串 "sig"</span><span class="sxs-lookup"><span data-stu-id="35c9f-634">The string "sig"</span></span>
- <span data-ttu-id="35c9f-635">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-636">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-636">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-637">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-638">介于43-53 个字符和小写字母、数字或百分比符号（%）之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="35c9f-639">字符串 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="35c9f-639">The string "%3d"</span></span>
- <span data-ttu-id="35c9f-640">不是字母或大写字符、数字或百分号（%）的任何字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-641">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-641">Checksum</span></span>

<span data-ttu-id="35c9f-642">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-643">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-643">Definition</span></span>

<span data-ttu-id="35c9f-644">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-645">正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="35c9f-646">Azure 服务总线连接字符串</span><span class="sxs-lookup"><span data-stu-id="35c9f-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-647">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-647">Format</span></span>

<span data-ttu-id="35c9f-648">字符串 "终结点"，后跟下面模式中所示的字符和字符串，包括字符串 "</span><span class="sxs-lookup"><span data-stu-id="35c9f-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-649">net "和" SharedAccesKey "。</span><span class="sxs-lookup"><span data-stu-id="35c9f-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-650">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-650">Pattern</span></span>

- <span data-ttu-id="35c9f-651">字符串 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="35c9f-651">The string "EndPoint"</span></span>
- <span data-ttu-id="35c9f-652">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-653">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-653">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-654">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-655">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-656">字符串 "</span><span class="sxs-lookup"><span data-stu-id="35c9f-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-657">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-657">net"</span></span>
- <span data-ttu-id="35c9f-658">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-659">字符串 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="35c9f-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="35c9f-660">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-661">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-661">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-662">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-663">43个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="35c9f-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-664">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-665">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-665">Checksum</span></span>

<span data-ttu-id="35c9f-666">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-667">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-667">Definition</span></span>

<span data-ttu-id="35c9f-668">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-669">正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。</span><span class="sxs-lookup"><span data-stu-id="35c9f-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="35c9f-670">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-671">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-673">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-674">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-674">contoso</span></span>
- <span data-ttu-id="35c9f-675">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-675">fabrikam</span></span>
- <span data-ttu-id="35c9f-676">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-676">northwind</span></span>
- <span data-ttu-id="35c9f-677">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-677">sandbox</span></span>
- <span data-ttu-id="35c9f-678">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-678">onebox</span></span>
- <span data-ttu-id="35c9f-679">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-679">localhost</span></span>
- <span data-ttu-id="35c9f-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-680">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-682">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-682">com</span></span>
- <span data-ttu-id="35c9f-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-684">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="35c9f-685">Azure 存储帐户密钥</span><span class="sxs-lookup"><span data-stu-id="35c9f-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-686">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-686">Format</span></span>

<span data-ttu-id="35c9f-687">字符串 "DefaultEndpointsProtocol"，后跟下面模式中所述的字符和字符串，包括字符串 "AccountKey"。</span><span class="sxs-lookup"><span data-stu-id="35c9f-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-688">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-688">Pattern</span></span>

- <span data-ttu-id="35c9f-689">字符串 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="35c9f-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="35c9f-690">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-691">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-691">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-692">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-693">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-694">字符串 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="35c9f-694">The string "AccountKey"</span></span>
- <span data-ttu-id="35c9f-695">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-696">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-696">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-697">0-2 空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="35c9f-698">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="35c9f-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-699">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-700">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-700">Checksum</span></span>

<span data-ttu-id="35c9f-701">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-702">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-702">Definition</span></span>

<span data-ttu-id="35c9f-703">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-704">正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-705">正则表达式**CEP_AzureEmulatorStorageAccountFilter 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-706">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-707">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="35c9f-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="35c9f-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="35c9f-709">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="35c9f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-712">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-713">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-713">contoso</span></span>
- <span data-ttu-id="35c9f-714">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-714">fabrikam</span></span>
- <span data-ttu-id="35c9f-715">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-715">northwind</span></span>
- <span data-ttu-id="35c9f-716">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-716">sandbox</span></span>
- <span data-ttu-id="35c9f-717">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-717">onebox</span></span>
- <span data-ttu-id="35c9f-718">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-718">localhost</span></span>
- <span data-ttu-id="35c9f-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-719">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-721">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-721">com</span></span>
- <span data-ttu-id="35c9f-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-723">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="35c9f-724">Azure 存储帐户密钥（常规）</span><span class="sxs-lookup"><span data-stu-id="35c9f-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-725">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-725">Format</span></span>

<span data-ttu-id="35c9f-726">任何86位或大写字母、数字、正斜杠（/）或加号（+）的任意组合，前面或后面是下面模式中所述的字符。</span><span class="sxs-lookup"><span data-stu-id="35c9f-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-727">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-727">Pattern</span></span>

- <span data-ttu-id="35c9f-728">大于号（>）、撇号（'）、等号（=）、引号（"）或数字符号（#）的0-1</span><span class="sxs-lookup"><span data-stu-id="35c9f-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="35c9f-729">86个字符的任意组合，这些字符为小写字母、数字、斜杠（/）或加号（+）</span><span class="sxs-lookup"><span data-stu-id="35c9f-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="35c9f-730">两个等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="35c9f-731">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-731">Checksum</span></span>

<span data-ttu-id="35c9f-732">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-733">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-733">Definition</span></span>

<span data-ttu-id="35c9f-734">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-735">正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="35c9f-736">比利时国家号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-737">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-737">Format</span></span>

<span data-ttu-id="35c9f-738">11 个数字加分隔符</span><span class="sxs-lookup"><span data-stu-id="35c9f-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-739">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-739">Pattern</span></span>

<span data-ttu-id="35c9f-740">11 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="35c9f-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="35c9f-741">六个数字加两个点，采用格式  YY.MM.DD，代表出生日期  </span><span class="sxs-lookup"><span data-stu-id="35c9f-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="35c9f-742">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-742">A hyphen</span></span> 
- <span data-ttu-id="35c9f-743">三个连续的数字（男性用奇数，女性用偶数） </span><span class="sxs-lookup"><span data-stu-id="35c9f-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="35c9f-744">一个点</span><span class="sxs-lookup"><span data-stu-id="35c9f-744">A period</span></span> 
- <span data-ttu-id="35c9f-745">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-746">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-746">Checksum</span></span>

<span data-ttu-id="35c9f-747">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-748">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-748">Definition</span></span>

<span data-ttu-id="35c9f-749">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-750">函数 Func_belgium_national_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-751">找到 Keyword_belgium_national_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="35c9f-752">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-753">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="35c9f-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="35c9f-755">标识</span><span class="sxs-lookup"><span data-stu-id="35c9f-755">Identity</span></span>
- <span data-ttu-id="35c9f-756">注册</span><span class="sxs-lookup"><span data-stu-id="35c9f-756">Registration</span></span>
- <span data-ttu-id="35c9f-757">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-757">Identification</span></span> 
- <span data-ttu-id="35c9f-758">ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-758">ID</span></span> 
- <span data-ttu-id="35c9f-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-759">Identiteitskaart</span></span>
- <span data-ttu-id="35c9f-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-760">Registratie nummer</span></span> 
- <span data-ttu-id="35c9f-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-761">Identificatie nummer</span></span> 
- <span data-ttu-id="35c9f-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="35c9f-762">Identiteit</span></span>
- <span data-ttu-id="35c9f-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="35c9f-763">Registratie</span></span>
- <span data-ttu-id="35c9f-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="35c9f-764">Identificatie</span></span> 
- <span data-ttu-id="35c9f-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="35c9f-765">Carte d’identité</span></span> 
- <span data-ttu-id="35c9f-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="35c9f-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="35c9f-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="35c9f-767">numéro d'identification</span></span>
- <span data-ttu-id="35c9f-768">identité</span><span class="sxs-lookup"><span data-stu-id="35c9f-768">identité</span></span> 
- <span data-ttu-id="35c9f-769">inscription</span><span class="sxs-lookup"><span data-stu-id="35c9f-769">inscription</span></span> 
- <span data-ttu-id="35c9f-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="35c9f-770">Identifikation</span></span>
- <span data-ttu-id="35c9f-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="35c9f-771">Identifizierung</span></span>
- <span data-ttu-id="35c9f-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-772">Identifikationsnummer</span></span>
- <span data-ttu-id="35c9f-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="35c9f-773">Personalausweis</span></span>
- <span data-ttu-id="35c9f-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="35c9f-774">Registrierung</span></span>
- <span data-ttu-id="35c9f-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="35c9f-776">巴西 CPF 号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-777">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-777">Format</span></span>

<span data-ttu-id="35c9f-778">11 个数字（包括校验位），可以格式化，也可以非格式化</span><span class="sxs-lookup"><span data-stu-id="35c9f-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-779">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-779">Pattern</span></span>

<span data-ttu-id="35c9f-780">格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-780">Formatted:</span></span>
- <span data-ttu-id="35c9f-781">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-781">Three digits</span></span> 
- <span data-ttu-id="35c9f-782">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-782">A period</span></span> 
- <span data-ttu-id="35c9f-783">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-783">Three digits</span></span> 
- <span data-ttu-id="35c9f-784">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-784">A period</span></span> 
- <span data-ttu-id="35c9f-785">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-785">Three digits</span></span> 
- <span data-ttu-id="35c9f-786">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-786">A hyphen</span></span> 
- <span data-ttu-id="35c9f-787">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-787">Two digits which are check digits</span></span>

<span data-ttu-id="35c9f-788">纯</span><span class="sxs-lookup"><span data-stu-id="35c9f-788">Unformatted:</span></span>
- <span data-ttu-id="35c9f-789">11 个数字，其中最后两个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-790">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-790">Checksum</span></span>

<span data-ttu-id="35c9f-791">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-792">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-792">Definition</span></span>

<span data-ttu-id="35c9f-793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-794">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-795">找到 Keyword_brazil_cpf 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="35c9f-796">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-796">The checksum passes.</span></span>

<span data-ttu-id="35c9f-797">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-798">函数 Func_brazil_cpf 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-799">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-800">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="35c9f-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="35c9f-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="35c9f-802">CPF</span><span class="sxs-lookup"><span data-stu-id="35c9f-802">CPF</span></span>
- <span data-ttu-id="35c9f-803">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-803">Identification</span></span>
- <span data-ttu-id="35c9f-804">注册</span><span class="sxs-lookup"><span data-stu-id="35c9f-804">Registration</span></span>
- <span data-ttu-id="35c9f-805">营业</span><span class="sxs-lookup"><span data-stu-id="35c9f-805">Revenue</span></span>
- <span data-ttu-id="35c9f-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="35c9f-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="35c9f-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="35c9f-807">Imposto</span></span> 
- <span data-ttu-id="35c9f-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="35c9f-808">Identificação</span></span> 
- <span data-ttu-id="35c9f-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="35c9f-809">Inscrição</span></span> 
- <span data-ttu-id="35c9f-810">Receita</span><span class="sxs-lookup"><span data-stu-id="35c9f-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="35c9f-811">巴西法律实体编号 (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="35c9f-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-812">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-812">Format</span></span>

<span data-ttu-id="35c9f-813">14 个数字（包括注册号、分行号码和校验位），再加上分隔符</span><span class="sxs-lookup"><span data-stu-id="35c9f-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-814">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-814">Pattern</span></span>
<span data-ttu-id="35c9f-815">14 个数字，再加上分隔符：</span><span class="sxs-lookup"><span data-stu-id="35c9f-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="35c9f-816">两个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-816">Two digits</span></span> 
- <span data-ttu-id="35c9f-817">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-817">A period</span></span> 
- <span data-ttu-id="35c9f-818">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-818">Three digits</span></span> 
- <span data-ttu-id="35c9f-819">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-819">A period</span></span> 
- <span data-ttu-id="35c9f-820">三个数字（前 8 位数是注册号） </span><span class="sxs-lookup"><span data-stu-id="35c9f-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="35c9f-821">正斜杠 </span><span class="sxs-lookup"><span data-stu-id="35c9f-821">A forward slash</span></span> 
- <span data-ttu-id="35c9f-822">四位分行号码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-822">Four-digit branch number</span></span> 
- <span data-ttu-id="35c9f-823">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-823">A hyphen</span></span> 
- <span data-ttu-id="35c9f-824">两个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-825">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-825">Checksum</span></span>

<span data-ttu-id="35c9f-826">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-827">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-827">Definition</span></span>

<span data-ttu-id="35c9f-828">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-829">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-830">找到 Keyword_brazil_cnpj 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="35c9f-831">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-831">The checksum passes.</span></span>

<span data-ttu-id="35c9f-832">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-833">函数 Func_brazil_cnpj 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-834">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-835">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="35c9f-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="35c9f-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="35c9f-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="35c9f-837">CNPJ</span></span> 
- <span data-ttu-id="35c9f-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="35c9f-838">CNPJ/MF</span></span> 
- <span data-ttu-id="35c9f-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="35c9f-839">CNPJ-MF</span></span> 
- <span data-ttu-id="35c9f-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="35c9f-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="35c9f-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="35c9f-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="35c9f-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="35c9f-842">Legal entity</span></span> 
- <span data-ttu-id="35c9f-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="35c9f-843">Legal entities</span></span> 
- <span data-ttu-id="35c9f-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="35c9f-844">Registration Status</span></span> 
- <span data-ttu-id="35c9f-845">商业版</span><span class="sxs-lookup"><span data-stu-id="35c9f-845">Business</span></span> 
- <span data-ttu-id="35c9f-846">Company</span><span class="sxs-lookup"><span data-stu-id="35c9f-846">Company</span></span>
- <span data-ttu-id="35c9f-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="35c9f-847">CNPJ</span></span> 
- <span data-ttu-id="35c9f-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="35c9f-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="35c9f-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="35c9f-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="35c9f-850">CGC</span><span class="sxs-lookup"><span data-stu-id="35c9f-850">CGC</span></span> 
- <span data-ttu-id="35c9f-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="35c9f-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="35c9f-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="35c9f-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="35c9f-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="35c9f-853">Situação cadastral</span></span> 
- <span data-ttu-id="35c9f-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="35c9f-854">Inscrição</span></span> 
- <span data-ttu-id="35c9f-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="35c9f-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="35c9f-856">	巴西国家身份证 (RG)</span><span class="sxs-lookup"><span data-stu-id="35c9f-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-857">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-857">Format</span></span>

<span data-ttu-id="35c9f-858">Registro Geral （旧格式）：9个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="35c9f-859">Registro de Identidade （RIC）（新格式）：11个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-860">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-860">Pattern</span></span>

<span data-ttu-id="35c9f-861">Registro Geral（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="35c9f-862">两个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-862">Two digits</span></span> 
- <span data-ttu-id="35c9f-863">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-863">A period</span></span> 
- <span data-ttu-id="35c9f-864">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-864">Three digits</span></span> 
- <span data-ttu-id="35c9f-865">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-865">A period</span></span> 
- <span data-ttu-id="35c9f-866">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-866">Three digits</span></span> 
- <span data-ttu-id="35c9f-867">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-867">A hyphen</span></span> 
- <span data-ttu-id="35c9f-868">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-868">One digit which is a check digit</span></span>

<span data-ttu-id="35c9f-869">Registro de Identidade （RIC）（新格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="35c9f-870">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-870">10 digits</span></span> 
- <span data-ttu-id="35c9f-871">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-871">A hyphen</span></span> 
- <span data-ttu-id="35c9f-872">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-873">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-873">Checksum</span></span>

<span data-ttu-id="35c9f-874">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-875">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-875">Definition</span></span>

<span data-ttu-id="35c9f-876">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-877">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-878">找到 Keyword_brazil_rg 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="35c9f-879">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-879">The checksum passes.</span></span>

<span data-ttu-id="35c9f-880">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-881">函数 Func_brazil_rg 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-882">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-883">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="35c9f-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="35c9f-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="35c9f-885">Cédula de identidade identity 卡片国家 id número de rregistro registro de Iidentidade registro geral RG （此关键字区分大小写） RIC （此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="35c9f-886">加拿大银行帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-887">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-887">Format</span></span>

<span data-ttu-id="35c9f-888">七个或十二个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-889">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-889">Pattern</span></span>

<span data-ttu-id="35c9f-890">加拿大银行帐号是七个或十二个数字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="35c9f-891">加拿大银行帐户的银行代号是：</span><span class="sxs-lookup"><span data-stu-id="35c9f-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="35c9f-892">五位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-892">Five digits</span></span> 
- <span data-ttu-id="35c9f-893">连字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-893">A hyphen</span></span> 
- <span data-ttu-id="35c9f-894">三位数字或</span><span class="sxs-lookup"><span data-stu-id="35c9f-894">Three digits OR</span></span>
- <span data-ttu-id="35c9f-895">一个零“0” </span><span class="sxs-lookup"><span data-stu-id="35c9f-895">A zero "0"</span></span> 
- <span data-ttu-id="35c9f-896">八位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-897">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-897">Checksum</span></span>

<span data-ttu-id="35c9f-898">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-899">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-899">Definition</span></span>

<span data-ttu-id="35c9f-900">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-901">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-902">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="35c9f-903">正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="35c9f-904">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-905">正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-906">找到 Keyword_canada_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-907">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="35c9f-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="35c9f-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="35c9f-909">canada savings bonds</span></span>
- <span data-ttu-id="35c9f-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="35c9f-910">canada revenue agency</span></span>
- <span data-ttu-id="35c9f-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="35c9f-911">canadian financial institution</span></span>
- <span data-ttu-id="35c9f-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="35c9f-912">direct deposit form</span></span>
- <span data-ttu-id="35c9f-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="35c9f-913">canadian citizen</span></span>
- <span data-ttu-id="35c9f-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="35c9f-914">legal representative</span></span>
- <span data-ttu-id="35c9f-915">notary public</span><span class="sxs-lookup"><span data-stu-id="35c9f-915">notary public</span></span>
- <span data-ttu-id="35c9f-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="35c9f-916">commissioner for oaths</span></span>
- <span data-ttu-id="35c9f-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="35c9f-917">child care benefit</span></span>
- <span data-ttu-id="35c9f-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="35c9f-918">universal child care</span></span>
- <span data-ttu-id="35c9f-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="35c9f-919">canada child tax benefit</span></span>
- <span data-ttu-id="35c9f-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="35c9f-920">income tax benefit</span></span>
- <span data-ttu-id="35c9f-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="35c9f-921">harmonized sales tax</span></span>
- <span data-ttu-id="35c9f-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="35c9f-922">social insurance number</span></span>
- <span data-ttu-id="35c9f-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="35c9f-923">income tax refund</span></span>
- <span data-ttu-id="35c9f-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="35c9f-924">child tax benefit</span></span>
- <span data-ttu-id="35c9f-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="35c9f-925">territorial payments</span></span>
- <span data-ttu-id="35c9f-926">institution number</span><span class="sxs-lookup"><span data-stu-id="35c9f-926">institution number</span></span>
- <span data-ttu-id="35c9f-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="35c9f-927">deposit request</span></span>
- <span data-ttu-id="35c9f-928">banking information</span><span class="sxs-lookup"><span data-stu-id="35c9f-928">banking information</span></span>
- <span data-ttu-id="35c9f-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="35c9f-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="35c9f-930">加拿大驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-931">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-931">Format</span></span>

<span data-ttu-id="35c9f-932">因省而异</span><span class="sxs-lookup"><span data-stu-id="35c9f-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-933">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-933">Pattern</span></span>

<span data-ttu-id="35c9f-934">各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温</span><span class="sxs-lookup"><span data-stu-id="35c9f-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-935">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-935">Checksum</span></span>

<span data-ttu-id="35c9f-936">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-937">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-937">Definition</span></span>

<span data-ttu-id="35c9f-938">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-939">函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-940">找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="35c9f-941">找到 Keyword_canada_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-942">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="35c9f-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="35c9f-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="35c9f-944">省/市/自治区的缩写，例如 AB</span><span class="sxs-lookup"><span data-stu-id="35c9f-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="35c9f-945">省名称，例如 Alberta</span><span class="sxs-lookup"><span data-stu-id="35c9f-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="35c9f-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="35c9f-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="35c9f-947">通讯</span><span class="sxs-lookup"><span data-stu-id="35c9f-947">DL</span></span>
- <span data-ttu-id="35c9f-948">DLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-948">DLS</span></span>
- <span data-ttu-id="35c9f-949">采用</span><span class="sxs-lookup"><span data-stu-id="35c9f-949">CDL</span></span>
- <span data-ttu-id="35c9f-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-950">CDLS</span></span>
- <span data-ttu-id="35c9f-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-951">DriverLic</span></span>
- <span data-ttu-id="35c9f-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-952">DriverLics</span></span>
- <span data-ttu-id="35c9f-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-953">DriverLicense</span></span>
- <span data-ttu-id="35c9f-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-954">DriverLicenses</span></span>
- <span data-ttu-id="35c9f-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-955">DriverLicence</span></span>
- <span data-ttu-id="35c9f-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-956">DriverLicences</span></span>
- <span data-ttu-id="35c9f-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-957">Driver Lic</span></span>
- <span data-ttu-id="35c9f-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-958">Driver Lics</span></span>
- <span data-ttu-id="35c9f-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="35c9f-959">Driver License</span></span>
- <span data-ttu-id="35c9f-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-960">Driver Licenses</span></span>
- <span data-ttu-id="35c9f-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-961">Driver Licence</span></span>
- <span data-ttu-id="35c9f-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-962">Driver Licences</span></span>
- <span data-ttu-id="35c9f-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-963">DriversLic</span></span>
- <span data-ttu-id="35c9f-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-964">DriversLics</span></span>
- <span data-ttu-id="35c9f-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-965">DriversLicence</span></span>
- <span data-ttu-id="35c9f-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-966">DriversLicences</span></span>
- <span data-ttu-id="35c9f-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-967">DriversLicense</span></span>
- <span data-ttu-id="35c9f-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-968">DriversLicenses</span></span>
- <span data-ttu-id="35c9f-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-969">Drivers Lic</span></span>
- <span data-ttu-id="35c9f-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-970">Drivers Lics</span></span>
- <span data-ttu-id="35c9f-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="35c9f-971">Drivers License</span></span>
- <span data-ttu-id="35c9f-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-972">Drivers Licenses</span></span>
- <span data-ttu-id="35c9f-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-973">Drivers Licence</span></span>
- <span data-ttu-id="35c9f-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-974">Drivers Licences</span></span>
- <span data-ttu-id="35c9f-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-975">Driver'Lic</span></span>
- <span data-ttu-id="35c9f-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-976">Driver'Lics</span></span>
- <span data-ttu-id="35c9f-977">Driver'License</span><span class="sxs-lookup"><span data-stu-id="35c9f-977">Driver'License</span></span>
- <span data-ttu-id="35c9f-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-978">Driver'Licenses</span></span>
- <span data-ttu-id="35c9f-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-979">Driver'Licence</span></span>
- <span data-ttu-id="35c9f-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-980">Driver'Licences</span></span>
- <span data-ttu-id="35c9f-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-981">Driver' Lic</span></span>
- <span data-ttu-id="35c9f-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-982">Driver' Lics</span></span>
- <span data-ttu-id="35c9f-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="35c9f-983">Driver' License</span></span>
- <span data-ttu-id="35c9f-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-984">Driver' Licenses</span></span>
- <span data-ttu-id="35c9f-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-985">Driver' Licence</span></span>
- <span data-ttu-id="35c9f-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-986">Driver' Licences</span></span>
- <span data-ttu-id="35c9f-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-987">Driver'sLic</span></span>
- <span data-ttu-id="35c9f-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-988">Driver'sLics</span></span>
- <span data-ttu-id="35c9f-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-989">Driver'sLicense</span></span>
- <span data-ttu-id="35c9f-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-990">Driver'sLicenses</span></span>
- <span data-ttu-id="35c9f-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="35c9f-991">Driver'sLicence</span></span>
- <span data-ttu-id="35c9f-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="35c9f-992">Driver'sLicences</span></span>
- <span data-ttu-id="35c9f-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-993">Driver's Lic</span></span>
- <span data-ttu-id="35c9f-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-994">Driver's Lics</span></span>
- <span data-ttu-id="35c9f-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="35c9f-995">Driver's License</span></span>
- <span data-ttu-id="35c9f-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-996">Driver's Licenses</span></span>
- <span data-ttu-id="35c9f-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-997">Driver's Licence</span></span>
- <span data-ttu-id="35c9f-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-998">Driver's Licences</span></span>
- <span data-ttu-id="35c9f-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="35c9f-999">Permis de Conduire</span></span>
- <span data-ttu-id="35c9f-1000">id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1000">id</span></span>
- <span data-ttu-id="35c9f-1001">ids</span><span class="sxs-lookup"><span data-stu-id="35c9f-1001">ids</span></span>
- <span data-ttu-id="35c9f-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1002">idcard number</span></span>
- <span data-ttu-id="35c9f-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1003">idcard numbers</span></span>
- <span data-ttu-id="35c9f-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="35c9f-1004">idcard #</span></span>
- <span data-ttu-id="35c9f-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="35c9f-1005">idcard #s</span></span>
- <span data-ttu-id="35c9f-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1006">idcard card</span></span>
- <span data-ttu-id="35c9f-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1007">idcard cards</span></span>
- <span data-ttu-id="35c9f-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1008">idcard</span></span>
- <span data-ttu-id="35c9f-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1009">identification number</span></span>
- <span data-ttu-id="35c9f-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1010">identification numbers</span></span>
- <span data-ttu-id="35c9f-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="35c9f-1011">identification #</span></span>
- <span data-ttu-id="35c9f-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="35c9f-1012">identification #s</span></span>
- <span data-ttu-id="35c9f-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1013">identification card</span></span>
- <span data-ttu-id="35c9f-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1014">identification cards</span></span>
- <span data-ttu-id="35c9f-1015">id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1015">identification</span></span> 
- <span data-ttu-id="35c9f-1016">通讯#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1016">DL#</span></span>
- <span data-ttu-id="35c9f-1017">DLS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1017">DLS#</span></span> 
- <span data-ttu-id="35c9f-1018">采用#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1018">CDL#</span></span> 
- <span data-ttu-id="35c9f-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1019">CDLS#</span></span> 
- <span data-ttu-id="35c9f-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1020">DriverLic#</span></span> 
- <span data-ttu-id="35c9f-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1021">DriverLics#</span></span> 
- <span data-ttu-id="35c9f-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1022">DriverLicense#</span></span> 
- <span data-ttu-id="35c9f-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="35c9f-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1024">DriverLicence#</span></span> 
- <span data-ttu-id="35c9f-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1025">DriverLicences#</span></span> 
- <span data-ttu-id="35c9f-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1026">Driver Lic#</span></span>
- <span data-ttu-id="35c9f-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1027">Driver Lics#</span></span> 
- <span data-ttu-id="35c9f-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1028">Driver License#</span></span> 
- <span data-ttu-id="35c9f-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="35c9f-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1030">Driver License#</span></span> 
- <span data-ttu-id="35c9f-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1031">Driver Licences#</span></span> 
- <span data-ttu-id="35c9f-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1032">DriversLic#</span></span> 
- <span data-ttu-id="35c9f-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1033">DriversLics#</span></span> 
- <span data-ttu-id="35c9f-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1034">DriversLicense#</span></span> 
- <span data-ttu-id="35c9f-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="35c9f-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1036">DriversLicence#</span></span> 
- <span data-ttu-id="35c9f-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1037">DriversLicences#</span></span> 
- <span data-ttu-id="35c9f-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="35c9f-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="35c9f-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1040">Drivers License#</span></span> 
- <span data-ttu-id="35c9f-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="35c9f-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="35c9f-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="35c9f-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="35c9f-1045">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="35c9f-1046">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1046">Driver'License#</span></span> 
- <span data-ttu-id="35c9f-1047">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="35c9f-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="35c9f-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="35c9f-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="35c9f-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="35c9f-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1052">Driver' License#</span></span> 
- <span data-ttu-id="35c9f-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="35c9f-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="35c9f-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="35c9f-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="35c9f-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="35c9f-1058">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="35c9f-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="35c9f-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="35c9f-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="35c9f-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="35c9f-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="35c9f-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1064">Driver's License#</span></span> 
- <span data-ttu-id="35c9f-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="35c9f-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="35c9f-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="35c9f-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="35c9f-1069">号#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1069">id#</span></span> 
- <span data-ttu-id="35c9f-1070">id#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1070">ids#</span></span> 
- <span data-ttu-id="35c9f-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1071">idcard card#</span></span> 
- <span data-ttu-id="35c9f-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1072">idcard cards#</span></span> 
- <span data-ttu-id="35c9f-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1073">idcard#</span></span> 
- <span data-ttu-id="35c9f-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1074">identification card#</span></span> 
- <span data-ttu-id="35c9f-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1075">identification cards#</span></span> 
- <span data-ttu-id="35c9f-1076">id#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="35c9f-1077">加拿大卫生服务号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1078">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1078">Format</span></span>

<span data-ttu-id="35c9f-1079">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1080">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1080">Pattern</span></span>

<span data-ttu-id="35c9f-1081">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1082">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1082">Checksum</span></span>

<span data-ttu-id="35c9f-1083">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1084">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1084">Definition</span></span>

<span data-ttu-id="35c9f-1085">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1086">正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1087">找到 Keyword_canada_health_service_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1088">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="35c9f-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="35c9f-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1090">personal health number</span></span>
- <span data-ttu-id="35c9f-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="35c9f-1091">patient information</span></span>
- <span data-ttu-id="35c9f-1092">health services</span><span class="sxs-lookup"><span data-stu-id="35c9f-1092">health services</span></span>
- <span data-ttu-id="35c9f-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="35c9f-1093">speciality services</span></span>
- <span data-ttu-id="35c9f-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="35c9f-1094">automobile accident</span></span>
- <span data-ttu-id="35c9f-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="35c9f-1095">patient hospital</span></span>
- <span data-ttu-id="35c9f-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="35c9f-1096">psychiatrist</span></span>
- <span data-ttu-id="35c9f-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="35c9f-1097">workers compensation</span></span>
- <span data-ttu-id="35c9f-1098">障碍</span><span class="sxs-lookup"><span data-stu-id="35c9f-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="35c9f-1099">加拿大护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1100">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1100">Format</span></span>

<span data-ttu-id="35c9f-1101">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1102">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1102">Pattern</span></span>

<span data-ttu-id="35c9f-1103">两个大写字母后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1104">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1104">Checksum</span></span>

<span data-ttu-id="35c9f-1105">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1106">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1106">Definition</span></span>

<span data-ttu-id="35c9f-1107">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1108">正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1109">找到 Keyword_canada_passport_number 或 Keyword_passport 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1110">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="35c9f-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="35c9f-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="35c9f-1112">canadian citizenship</span></span>
- <span data-ttu-id="35c9f-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-1113">canadian passport</span></span>
- <span data-ttu-id="35c9f-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="35c9f-1114">passport application</span></span>
- <span data-ttu-id="35c9f-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="35c9f-1115">passport photos</span></span>
- <span data-ttu-id="35c9f-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="35c9f-1116">certified translator</span></span>
- <span data-ttu-id="35c9f-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="35c9f-1117">canadian citizens</span></span>
- <span data-ttu-id="35c9f-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="35c9f-1118">processing times</span></span>
- <span data-ttu-id="35c9f-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="35c9f-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="35c9f-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-1120">Keyword_passport</span></span>

- <span data-ttu-id="35c9f-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1121">Passport Number</span></span>
- <span data-ttu-id="35c9f-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="35c9f-1122">Passport No</span></span>
- <span data-ttu-id="35c9f-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-1123">Passport #</span></span>
- <span data-ttu-id="35c9f-1124">登记卡#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1124">Passport#</span></span>
- <span data-ttu-id="35c9f-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="35c9f-1125">PassportID</span></span>
- <span data-ttu-id="35c9f-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="35c9f-1126">Passportno</span></span>
- <span data-ttu-id="35c9f-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1127">passportnumber</span></span>
- <span data-ttu-id="35c9f-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-1128">パスポート</span></span>
- <span data-ttu-id="35c9f-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1129">パスポート番号</span></span>
- <span data-ttu-id="35c9f-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1130">パスポートのNum</span></span>
- <span data-ttu-id="35c9f-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-1131">パスポート＃</span></span>
- <span data-ttu-id="35c9f-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="35c9f-1132">Numéro de passeport</span></span>
- <span data-ttu-id="35c9f-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="35c9f-1133">Passeport n °</span></span>
- <span data-ttu-id="35c9f-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="35c9f-1134">Passeport Non</span></span>
- <span data-ttu-id="35c9f-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-1135">Passeport #</span></span>
- <span data-ttu-id="35c9f-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1136">Passeport#</span></span>
- <span data-ttu-id="35c9f-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="35c9f-1137">PasseportNon</span></span>
- <span data-ttu-id="35c9f-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="35c9f-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="35c9f-1139">加拿大个人健康标识号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1140">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1140">Format</span></span>

<span data-ttu-id="35c9f-1141">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1142">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1142">Pattern</span></span>

<span data-ttu-id="35c9f-1143">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1144">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1144">Checksum</span></span>

<span data-ttu-id="35c9f-1145">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1146">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1146">Definition</span></span>

<span data-ttu-id="35c9f-1147">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_canada_phin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-1148">找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1149">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="35c9f-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="35c9f-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="35c9f-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1151">social insurance number</span></span>
- <span data-ttu-id="35c9f-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="35c9f-1152">health information act</span></span>
- <span data-ttu-id="35c9f-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="35c9f-1153">income tax information</span></span>
- <span data-ttu-id="35c9f-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="35c9f-1154">manitoba health</span></span>
- <span data-ttu-id="35c9f-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="35c9f-1155">health registration</span></span>
- <span data-ttu-id="35c9f-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="35c9f-1156">prescription purchases</span></span>
- <span data-ttu-id="35c9f-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="35c9f-1157">benefit eligibility</span></span>
- <span data-ttu-id="35c9f-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="35c9f-1158">personal health</span></span>
- <span data-ttu-id="35c9f-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="35c9f-1159">power of attorney</span></span>
- <span data-ttu-id="35c9f-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1160">registration number</span></span>
- <span data-ttu-id="35c9f-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1161">personal health number</span></span>
- <span data-ttu-id="35c9f-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="35c9f-1162">practitioner referral</span></span>
- <span data-ttu-id="35c9f-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="35c9f-1163">wellness professional</span></span>
- <span data-ttu-id="35c9f-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="35c9f-1164">patient referral</span></span>
- <span data-ttu-id="35c9f-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="35c9f-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="35c9f-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="35c9f-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="35c9f-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="35c9f-1167">Nunavut</span></span>
- <span data-ttu-id="35c9f-1168">省</span><span class="sxs-lookup"><span data-stu-id="35c9f-1168">Quebec</span></span>
- <span data-ttu-id="35c9f-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="35c9f-1169">Northwest Territories</span></span>
- <span data-ttu-id="35c9f-1170">省</span><span class="sxs-lookup"><span data-stu-id="35c9f-1170">Ontario</span></span>
- <span data-ttu-id="35c9f-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="35c9f-1171">British Columbia</span></span>
- <span data-ttu-id="35c9f-1172">Alberta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1172">Alberta</span></span>
- <span data-ttu-id="35c9f-1173">彻</span><span class="sxs-lookup"><span data-stu-id="35c9f-1173">Saskatchewan</span></span>
- <span data-ttu-id="35c9f-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="35c9f-1174">Manitoba</span></span>
- <span data-ttu-id="35c9f-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="35c9f-1175">Yukon</span></span>
- <span data-ttu-id="35c9f-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="35c9f-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="35c9f-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="35c9f-1177">New Brunswick</span></span>
- <span data-ttu-id="35c9f-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="35c9f-1178">Nova Scotia</span></span>
- <span data-ttu-id="35c9f-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="35c9f-1179">Prince Edward Island</span></span>
- <span data-ttu-id="35c9f-1180">加拿大</span><span class="sxs-lookup"><span data-stu-id="35c9f-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="35c9f-1181">加拿大社会保险号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1182">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1182">Format</span></span>

<span data-ttu-id="35c9f-1183">九个数字，包含可选连字符或空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1184">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1184">Pattern</span></span>

<span data-ttu-id="35c9f-1185">格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1185">Formatted:</span></span>
- <span data-ttu-id="35c9f-1186">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1186">Three digits</span></span> 
- <span data-ttu-id="35c9f-1187">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-1187">A hyphen or space</span></span> 
- <span data-ttu-id="35c9f-1188">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1188">Three digits</span></span> 
- <span data-ttu-id="35c9f-1189">连字符或空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-1189">A hyphen or space</span></span> 
- <span data-ttu-id="35c9f-1190">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1190">Three digits</span></span>

<span data-ttu-id="35c9f-1191">未格式化：9个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1192">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1192">Checksum</span></span>

<span data-ttu-id="35c9f-1193">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1194">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1194">Definition</span></span>

<span data-ttu-id="35c9f-1195">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1196">函数 Func_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1197">至少两个以下任意组合：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="35c9f-1198">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="35c9f-1199">找到 Keyword_sin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="35c9f-1200">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="35c9f-1201">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1201">The checksum passes.</span></span>

<span data-ttu-id="35c9f-1202">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1203">函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1204">找到 Keyword_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="35c9f-1205">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1206">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="35c9f-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="35c9f-1207">Keyword_sin</span></span>

- <span data-ttu-id="35c9f-1208">sin</span><span class="sxs-lookup"><span data-stu-id="35c9f-1208">sin</span></span> 
- <span data-ttu-id="35c9f-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="35c9f-1209">social insurance</span></span> 
- <span data-ttu-id="35c9f-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="35c9f-1211">罪</span><span class="sxs-lookup"><span data-stu-id="35c9f-1211">sins</span></span> 
- <span data-ttu-id="35c9f-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1212">ssn</span></span> 
- <span data-ttu-id="35c9f-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1213">ssns</span></span> 
- <span data-ttu-id="35c9f-1214">social security</span><span class="sxs-lookup"><span data-stu-id="35c9f-1214">social security</span></span> 
- <span data-ttu-id="35c9f-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="35c9f-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="35c9f-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1216">national identification number</span></span> 
- <span data-ttu-id="35c9f-1217">national id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1217">national id</span></span> 
- <span data-ttu-id="35c9f-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1218">sin#</span></span> 
- <span data-ttu-id="35c9f-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="35c9f-1219">soc ins</span></span> 
- <span data-ttu-id="35c9f-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="35c9f-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="35c9f-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="35c9f-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="35c9f-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="35c9f-1222">driver's license</span></span> 
- <span data-ttu-id="35c9f-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="35c9f-1223">drivers license</span></span> 
- <span data-ttu-id="35c9f-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-1224">driver's licence</span></span> 
- <span data-ttu-id="35c9f-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-1225">drivers licence</span></span> 
- <span data-ttu-id="35c9f-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="35c9f-1226">DOB</span></span> 
- <span data-ttu-id="35c9f-1227">出生日期</span><span class="sxs-lookup"><span data-stu-id="35c9f-1227">Birthdate</span></span> 
- <span data-ttu-id="35c9f-1228">一定</span><span class="sxs-lookup"><span data-stu-id="35c9f-1228">Birthday</span></span> 
- <span data-ttu-id="35c9f-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="35c9f-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="35c9f-1230">	智利身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1231">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1231">Format</span></span>

<span data-ttu-id="35c9f-1232">7-8 位数加上分隔符一个校验位或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1233">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1233">Pattern</span></span>

<span data-ttu-id="35c9f-1234">7-8 个数字加分隔符：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="35c9f-1235">1-2 个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1235">1-2 digits</span></span> 
- <span data-ttu-id="35c9f-1236">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1236">A period</span></span> 
- <span data-ttu-id="35c9f-1237">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1237">Three digits</span></span> 
- <span data-ttu-id="35c9f-1238">一个点 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1238">A period</span></span> 
- <span data-ttu-id="35c9f-1239">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1239">Three digits</span></span> 
- <span data-ttu-id="35c9f-1240">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1240">A dash</span></span> 
- <span data-ttu-id="35c9f-1241">一个数字或字母（不区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1242">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1242">Checksum</span></span>

<span data-ttu-id="35c9f-1243">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1244">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1244">Definition</span></span>

<span data-ttu-id="35c9f-1245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1246">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1247">找到 Keyword_chile_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="35c9f-1248">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1248">The checksum passes.</span></span>

<span data-ttu-id="35c9f-1249">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1250">函数 Func_chile_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1251">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1252">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="35c9f-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="35c9f-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1254">National Identification Number</span></span> 
- <span data-ttu-id="35c9f-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1255">Identity card</span></span> 
- <span data-ttu-id="35c9f-1256">ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-1256">ID</span></span> 
- <span data-ttu-id="35c9f-1257">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1257">Identification</span></span> 
- <span data-ttu-id="35c9f-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="35c9f-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="35c9f-1259">以</span><span class="sxs-lookup"><span data-stu-id="35c9f-1259">RUN</span></span> 
- <span data-ttu-id="35c9f-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="35c9f-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="35c9f-1261">墨守成规</span><span class="sxs-lookup"><span data-stu-id="35c9f-1261">RUT</span></span> 
- <span data-ttu-id="35c9f-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="35c9f-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="35c9f-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="35c9f-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="35c9f-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="35c9f-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="35c9f-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="35c9f-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="35c9f-1266">	中国居民身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1267">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1267">Format</span></span>

<span data-ttu-id="35c9f-1268">18 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1269">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1269">Pattern</span></span>

<span data-ttu-id="35c9f-1270">18 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1270">18 digits:</span></span>
- <span data-ttu-id="35c9f-1271">其中六个数字是地址代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="35c9f-1272">八个数字，采用  YYYYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-1273">三个数字，是顺序代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="35c9f-1274">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1275">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1275">Checksum</span></span>

<span data-ttu-id="35c9f-1276">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1277">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1277">Definition</span></span>

<span data-ttu-id="35c9f-1278">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1279">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1280">找到 Keyword_china_resident_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="35c9f-1281">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1281">The checksum passes.</span></span>

<span data-ttu-id="35c9f-1282">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1283">函数 Func_china_resident_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1284">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1285">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="35c9f-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="35c9f-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="35c9f-1288">台湾</span><span class="sxs-lookup"><span data-stu-id="35c9f-1288">PRC</span></span> 
- <span data-ttu-id="35c9f-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1289">National Identification Card</span></span> 
- <span data-ttu-id="35c9f-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="35c9f-1290">身份证</span></span> 
- <span data-ttu-id="35c9f-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="35c9f-1291">居民 身份证</span></span> 
- <span data-ttu-id="35c9f-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="35c9f-1292">居民身份证</span></span> 
- <span data-ttu-id="35c9f-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="35c9f-1293">鉴定</span></span> 
- <span data-ttu-id="35c9f-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-1294">身分證</span></span> 
- <span data-ttu-id="35c9f-1295">居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-1295">居民 身份證</span></span>
- <span data-ttu-id="35c9f-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="35c9f-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="35c9f-1297">信用卡号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1298">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1298">Format</span></span>

<span data-ttu-id="35c9f-1299">14到16个数字，可以是格式化或无格式（dddddddddddddddd），并且必须通过 Luhn 测试。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1300">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1300">Pattern</span></span>

<span data-ttu-id="35c9f-1301">非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1302">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1302">Checksum</span></span>

<span data-ttu-id="35c9f-1303">是，Luhn 校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1304">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1304">Definition</span></span>

<span data-ttu-id="35c9f-1305">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1306">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1307">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1307">One of the following is true:</span></span>
    - <span data-ttu-id="35c9f-1308">找到 Keyword_cc_verification 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="35c9f-1309">找到 Keyword_cc_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="35c9f-1310">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="35c9f-1311">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1311">The checksum passes.</span></span>

<span data-ttu-id="35c9f-1312">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1313">函数 Func_credit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1314">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1315">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="35c9f-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="35c9f-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="35c9f-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="35c9f-1317">card verification</span></span>
- <span data-ttu-id="35c9f-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1318">card identification number</span></span>
- <span data-ttu-id="35c9f-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1319">cvn</span></span>
- <span data-ttu-id="35c9f-1320">cid</span><span class="sxs-lookup"><span data-stu-id="35c9f-1320">cid</span></span>
- <span data-ttu-id="35c9f-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="35c9f-1321">cvc2</span></span>
- <span data-ttu-id="35c9f-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="35c9f-1322">cvv2</span></span>
- <span data-ttu-id="35c9f-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="35c9f-1323">pin block</span></span>
- <span data-ttu-id="35c9f-1324">security code</span><span class="sxs-lookup"><span data-stu-id="35c9f-1324">security code</span></span>
- <span data-ttu-id="35c9f-1325">security number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1325">security number</span></span>
- <span data-ttu-id="35c9f-1326">security no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1326">security no</span></span>
- <span data-ttu-id="35c9f-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1327">issue number</span></span>
- <span data-ttu-id="35c9f-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1328">issue no</span></span>
- <span data-ttu-id="35c9f-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="35c9f-1329">cryptogramme</span></span>
- <span data-ttu-id="35c9f-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="35c9f-1330">numéro de sécurité</span></span>
- <span data-ttu-id="35c9f-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="35c9f-1331">numero de securite</span></span>
- <span data-ttu-id="35c9f-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="35c9f-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="35c9f-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1334">prüfziffer</span></span>
- <span data-ttu-id="35c9f-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1335">prufziffer</span></span>
- <span data-ttu-id="35c9f-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="35c9f-1336">sicherheits Kode</span></span>
- <span data-ttu-id="35c9f-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="35c9f-1337">sicherheitscode</span></span>
- <span data-ttu-id="35c9f-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="35c9f-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1339">verfalldatum</span></span>
- <span data-ttu-id="35c9f-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="35c9f-1340">codice di verifica</span></span>
- <span data-ttu-id="35c9f-1341">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1341">cod.</span></span> <span data-ttu-id="35c9f-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1342">sicurezza</span></span>
- <span data-ttu-id="35c9f-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1343">cod sicurezza</span></span>
- <span data-ttu-id="35c9f-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="35c9f-1344">n autorizzazione</span></span>
- <span data-ttu-id="35c9f-1345">código</span><span class="sxs-lookup"><span data-stu-id="35c9f-1345">código</span></span>
- <span data-ttu-id="35c9f-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1346">codigo</span></span>
- <span data-ttu-id="35c9f-1347">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1347">cod.</span></span> <span data-ttu-id="35c9f-1348">seg</span><span class="sxs-lookup"><span data-stu-id="35c9f-1348">seg</span></span>
- <span data-ttu-id="35c9f-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="35c9f-1349">cod seg</span></span>
- <span data-ttu-id="35c9f-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1350">código de segurança</span></span>
- <span data-ttu-id="35c9f-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1351">codigo de seguranca</span></span>
- <span data-ttu-id="35c9f-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1352">codigo de segurança</span></span>
- <span data-ttu-id="35c9f-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1353">código de seguranca</span></span>
- <span data-ttu-id="35c9f-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1354">cód.</span></span> <span data-ttu-id="35c9f-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1355">segurança</span></span>
- <span data-ttu-id="35c9f-1356">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1356">cod.</span></span> <span data-ttu-id="35c9f-1357">seguranca 货到付款。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1357">seguranca cod.</span></span> <span data-ttu-id="35c9f-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1358">segurança</span></span>
- <span data-ttu-id="35c9f-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1359">cód.</span></span> <span data-ttu-id="35c9f-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1360">seguranca</span></span>
- <span data-ttu-id="35c9f-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1361">cód segurança</span></span>
- <span data-ttu-id="35c9f-1362">货到付款 seguranca 货到付款 segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="35c9f-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1363">cód seguranca</span></span>
- <span data-ttu-id="35c9f-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="35c9f-1364">número de verificação</span></span>
- <span data-ttu-id="35c9f-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1365">numero de verificacao</span></span>
- <span data-ttu-id="35c9f-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="35c9f-1366">ablauf</span></span>
- <span data-ttu-id="35c9f-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="35c9f-1367">gültig bis</span></span>
- <span data-ttu-id="35c9f-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="35c9f-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="35c9f-1369">gultig bis</span></span>
- <span data-ttu-id="35c9f-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="35c9f-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1371">scadenza</span></span>
- <span data-ttu-id="35c9f-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="35c9f-1372">data scad</span></span>
- <span data-ttu-id="35c9f-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="35c9f-1373">fecha de expiracion</span></span>
- <span data-ttu-id="35c9f-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1374">fecha de venc</span></span>
- <span data-ttu-id="35c9f-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="35c9f-1375">vencimiento</span></span>
- <span data-ttu-id="35c9f-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1376">válido hasta</span></span>
- <span data-ttu-id="35c9f-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1377">valido hasta</span></span>
- <span data-ttu-id="35c9f-1378">vto</span><span class="sxs-lookup"><span data-stu-id="35c9f-1378">vto</span></span>
- <span data-ttu-id="35c9f-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="35c9f-1379">data de expiração</span></span>
- <span data-ttu-id="35c9f-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1380">data de expiracao</span></span>
- <span data-ttu-id="35c9f-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="35c9f-1381">data em que expira</span></span>
- <span data-ttu-id="35c9f-1382">validade</span><span class="sxs-lookup"><span data-stu-id="35c9f-1382">validade</span></span>
- <span data-ttu-id="35c9f-1383">valor</span><span class="sxs-lookup"><span data-stu-id="35c9f-1383">valor</span></span>
- <span data-ttu-id="35c9f-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="35c9f-1384">vencimento</span></span>
- <span data-ttu-id="35c9f-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="35c9f-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="35c9f-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="35c9f-1387">amex</span><span class="sxs-lookup"><span data-stu-id="35c9f-1387">amex</span></span>
- <span data-ttu-id="35c9f-1388">american express</span><span class="sxs-lookup"><span data-stu-id="35c9f-1388">american express</span></span>
- <span data-ttu-id="35c9f-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="35c9f-1389">americanexpress</span></span>
- <span data-ttu-id="35c9f-1390">反之</span><span class="sxs-lookup"><span data-stu-id="35c9f-1390">Visa</span></span>
- <span data-ttu-id="35c9f-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1391">mastercard</span></span>
- <span data-ttu-id="35c9f-1392">Master Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1392">master card</span></span>
- <span data-ttu-id="35c9f-1393">emc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1393">mc</span></span> 
- <span data-ttu-id="35c9f-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1394">mastercards</span></span>
- <span data-ttu-id="35c9f-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1395">master cards</span></span>
- <span data-ttu-id="35c9f-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="35c9f-1396">diner's Club</span></span>
- <span data-ttu-id="35c9f-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="35c9f-1397">diners club</span></span>
- <span data-ttu-id="35c9f-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="35c9f-1398">dinersclub</span></span>
- <span data-ttu-id="35c9f-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1399">discover card</span></span>
- <span data-ttu-id="35c9f-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1400">discovercard</span></span>
- <span data-ttu-id="35c9f-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1401">discover cards</span></span>
- <span data-ttu-id="35c9f-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="35c9f-1402">JCB</span></span>
- <span data-ttu-id="35c9f-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="35c9f-1403">japanese card bureau</span></span>
- <span data-ttu-id="35c9f-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="35c9f-1404">carte blanche</span></span>
- <span data-ttu-id="35c9f-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="35c9f-1405">carteblanche</span></span>
- <span data-ttu-id="35c9f-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1406">credit card</span></span>
- <span data-ttu-id="35c9f-1407">收件人#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1407">cc#</span></span>
- <span data-ttu-id="35c9f-1408">cc #：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1408">cc#:</span></span>
- <span data-ttu-id="35c9f-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="35c9f-1409">expiration date</span></span>
- <span data-ttu-id="35c9f-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="35c9f-1410">exp date</span></span>
- <span data-ttu-id="35c9f-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="35c9f-1411">expiry date</span></span>
- <span data-ttu-id="35c9f-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="35c9f-1412">date d’expiration</span></span>
- <span data-ttu-id="35c9f-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1413">date d'exp</span></span>
- <span data-ttu-id="35c9f-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="35c9f-1414">date expiration</span></span>
- <span data-ttu-id="35c9f-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1415">bank card</span></span>
- <span data-ttu-id="35c9f-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1416">bankcard</span></span>
- <span data-ttu-id="35c9f-1417">card number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1417">card number</span></span>
- <span data-ttu-id="35c9f-1418">card num</span><span class="sxs-lookup"><span data-stu-id="35c9f-1418">card num</span></span>
- <span data-ttu-id="35c9f-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1419">cardnumber</span></span>
- <span data-ttu-id="35c9f-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1420">cardnumbers</span></span>
- <span data-ttu-id="35c9f-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1421">card numbers</span></span>
- <span data-ttu-id="35c9f-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1422">creditcard</span></span>
- <span data-ttu-id="35c9f-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1423">credit cards</span></span>
- <span data-ttu-id="35c9f-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1424">creditcards</span></span>
- <span data-ttu-id="35c9f-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1425">ccn</span></span>
- <span data-ttu-id="35c9f-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="35c9f-1426">card holder</span></span>
- <span data-ttu-id="35c9f-1427">持卡人</span><span class="sxs-lookup"><span data-stu-id="35c9f-1427">cardholder</span></span>
- <span data-ttu-id="35c9f-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="35c9f-1428">card holders</span></span>
- <span data-ttu-id="35c9f-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="35c9f-1429">cardholders</span></span>
- <span data-ttu-id="35c9f-1430">check card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1430">check card</span></span>
- <span data-ttu-id="35c9f-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1431">checkcard</span></span>
- <span data-ttu-id="35c9f-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1432">check cards</span></span>
- <span data-ttu-id="35c9f-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1433">checkcards</span></span>
- <span data-ttu-id="35c9f-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1434">debit card</span></span>
- <span data-ttu-id="35c9f-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1435">debitcard</span></span>
- <span data-ttu-id="35c9f-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1436">debit cards</span></span>
- <span data-ttu-id="35c9f-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1437">debitcards</span></span>
- <span data-ttu-id="35c9f-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1438">atm card</span></span>
- <span data-ttu-id="35c9f-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1439">atmcard</span></span>
- <span data-ttu-id="35c9f-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1440">atm cards</span></span>
- <span data-ttu-id="35c9f-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1441">atmcards</span></span>
- <span data-ttu-id="35c9f-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="35c9f-1442">enroute</span></span>
- <span data-ttu-id="35c9f-1443">en route</span><span class="sxs-lookup"><span data-stu-id="35c9f-1443">en route</span></span>
- <span data-ttu-id="35c9f-1444">card type</span><span class="sxs-lookup"><span data-stu-id="35c9f-1444">card type</span></span>
- <span data-ttu-id="35c9f-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="35c9f-1445">carte bancaire</span></span>
- <span data-ttu-id="35c9f-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="35c9f-1446">carte de crédit</span></span>
- <span data-ttu-id="35c9f-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="35c9f-1447">carte de credit</span></span>
- <span data-ttu-id="35c9f-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1448">numéro de carte</span></span>
- <span data-ttu-id="35c9f-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1449">numero de carte</span></span>
- <span data-ttu-id="35c9f-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1450">nº de la carte</span></span>
- <span data-ttu-id="35c9f-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1451">nº de carte</span></span>
- <span data-ttu-id="35c9f-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1452">kreditkarte</span></span>
- <span data-ttu-id="35c9f-1453">karte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1453">karte</span></span>
- <span data-ttu-id="35c9f-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1454">karteninhaber</span></span>
- <span data-ttu-id="35c9f-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1455">karteninhabers</span></span>
- <span data-ttu-id="35c9f-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="35c9f-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="35c9f-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="35c9f-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1458">kreditkartentyp</span></span>
- <span data-ttu-id="35c9f-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="35c9f-1459">eigentümername</span></span>
- <span data-ttu-id="35c9f-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="35c9f-1460">kartennr</span></span> 
- <span data-ttu-id="35c9f-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1461">kartennummer</span></span>
- <span data-ttu-id="35c9f-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1462">kreditkartennummer</span></span>
- <span data-ttu-id="35c9f-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="35c9f-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1464">carta di credito</span></span>
- <span data-ttu-id="35c9f-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1465">carta credito</span></span>
- <span data-ttu-id="35c9f-1466">carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1466">carta</span></span>
- <span data-ttu-id="35c9f-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1467">n carta</span></span>
- <span data-ttu-id="35c9f-1468">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1468">nr.</span></span> <span data-ttu-id="35c9f-1469">carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1469">carta</span></span>
- <span data-ttu-id="35c9f-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1470">nr carta</span></span>
- <span data-ttu-id="35c9f-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1471">numero carta</span></span>
- <span data-ttu-id="35c9f-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1472">numero della carta</span></span>
- <span data-ttu-id="35c9f-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1473">numero di carta</span></span>
- <span data-ttu-id="35c9f-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1474">tarjeta credito</span></span>
- <span data-ttu-id="35c9f-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1475">tarjeta de credito</span></span>
- <span data-ttu-id="35c9f-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1476">tarjeta crédito</span></span>
- <span data-ttu-id="35c9f-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="35c9f-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="35c9f-1478">tarjeta de atm</span></span>
- <span data-ttu-id="35c9f-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="35c9f-1479">tarjeta atm</span></span>
- <span data-ttu-id="35c9f-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1480">tarjeta debito</span></span>
- <span data-ttu-id="35c9f-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1481">tarjeta de debito</span></span>
- <span data-ttu-id="35c9f-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1482">tarjeta débito</span></span>
- <span data-ttu-id="35c9f-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1483">tarjeta de débito</span></span>
- <span data-ttu-id="35c9f-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1484">nº de tarjeta</span></span>
- <span data-ttu-id="35c9f-1485">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1485">no.</span></span> <span data-ttu-id="35c9f-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1486">de tarjeta</span></span>
- <span data-ttu-id="35c9f-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1487">no de tarjeta</span></span>
- <span data-ttu-id="35c9f-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1488">numero de tarjeta</span></span>
- <span data-ttu-id="35c9f-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1489">número de tarjeta</span></span>
- <span data-ttu-id="35c9f-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1490">tarjeta no</span></span>
- <span data-ttu-id="35c9f-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="35c9f-1491">tarjetahabiente</span></span>
- <span data-ttu-id="35c9f-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1492">cartão de crédito</span></span>
- <span data-ttu-id="35c9f-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1493">cartão de credito</span></span>
- <span data-ttu-id="35c9f-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1494">cartao de crédito</span></span>
- <span data-ttu-id="35c9f-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1495">cartao de credito</span></span>
- <span data-ttu-id="35c9f-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1496">cartão de débito</span></span>
- <span data-ttu-id="35c9f-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1497">cartao de débito</span></span>
- <span data-ttu-id="35c9f-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1498">cartão de debito</span></span>
- <span data-ttu-id="35c9f-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1499">cartao de debito</span></span>
- <span data-ttu-id="35c9f-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="35c9f-1500">débito automático</span></span>
- <span data-ttu-id="35c9f-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="35c9f-1501">debito automatico</span></span>
- <span data-ttu-id="35c9f-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1502">número do cartão</span></span>
- <span data-ttu-id="35c9f-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1503">numero do cartão</span></span> 
- <span data-ttu-id="35c9f-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1504">número do cartao</span></span>
- <span data-ttu-id="35c9f-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1505">numero do cartao</span></span>
- <span data-ttu-id="35c9f-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1506">número de cartão</span></span>
- <span data-ttu-id="35c9f-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1507">numero de cartão</span></span>
- <span data-ttu-id="35c9f-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1508">número de cartao</span></span>
- <span data-ttu-id="35c9f-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1509">numero de cartao</span></span>
- <span data-ttu-id="35c9f-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1510">nº do cartão</span></span>
- <span data-ttu-id="35c9f-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1511">nº do cartao</span></span>
- <span data-ttu-id="35c9f-1512">n º。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1512">nº.</span></span> <span data-ttu-id="35c9f-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1513">do cartão</span></span>
- <span data-ttu-id="35c9f-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1514">no do cartão</span></span>
- <span data-ttu-id="35c9f-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1515">no do cartao</span></span>
- <span data-ttu-id="35c9f-1516">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1516">no.</span></span> <span data-ttu-id="35c9f-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1517">do cartão</span></span>
- <span data-ttu-id="35c9f-1518">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1518">no.</span></span> <span data-ttu-id="35c9f-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="35c9f-1520">	克罗地亚身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1521">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1521">Format</span></span>

<span data-ttu-id="35c9f-1522">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1523">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1523">Pattern</span></span>

<span data-ttu-id="35c9f-1524">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1525">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1525">Checksum</span></span>

<span data-ttu-id="35c9f-1526">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1527">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1527">Definition</span></span>

<span data-ttu-id="35c9f-1528">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1529">函数 Func_croatia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1530">找到 Keyword_croatia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-1531">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="35c9f-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="35c9f-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1533">Croatian identity card</span></span>
- <span data-ttu-id="35c9f-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="35c9f-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="35c9f-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1536">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1536">Format</span></span>

<span data-ttu-id="35c9f-1537">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1538">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1538">Pattern</span></span>

<span data-ttu-id="35c9f-1539">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1539">11 digits:</span></span>
- <span data-ttu-id="35c9f-1540">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1540">10 digits</span></span> 
- <span data-ttu-id="35c9f-1541">最后一个数字是用于国际数据交换目的的校验位，字母 HR 将加上11位数字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1542">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1542">Checksum</span></span>

<span data-ttu-id="35c9f-1543">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1544">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1544">Definition</span></span>

<span data-ttu-id="35c9f-1545">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1546">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1547">找到 Keyword_croatia_oib_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="35c9f-1548">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1548">The checksum passes.</span></span>

<span data-ttu-id="35c9f-1549">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1550">函数 Func_croatia_oib_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1551">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1552">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="35c9f-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="35c9f-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1554">Personal Identification Number</span></span>
- <span data-ttu-id="35c9f-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="35c9f-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="35c9f-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="35c9f-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="35c9f-1557">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1558">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1558">Format</span></span>

<span data-ttu-id="35c9f-1559">9个带可选正斜杠（旧格式）的数字，带可选正斜杠的10个数字（新的格式）</span><span class="sxs-lookup"><span data-stu-id="35c9f-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1560">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1560">Pattern</span></span>

<span data-ttu-id="35c9f-1561">9个数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="35c9f-1562">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1562">Nine digits</span></span>

<span data-ttu-id="35c9f-1563">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-1563">OR</span></span>

- <span data-ttu-id="35c9f-1564">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="35c9f-1565">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1565">A forward slash</span></span>
- <span data-ttu-id="35c9f-1566">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1566">Three digits</span></span>

<span data-ttu-id="35c9f-1567">10个数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1567">10 digits (new format):</span></span>
- <span data-ttu-id="35c9f-1568">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1568">10 digits</span></span>

<span data-ttu-id="35c9f-1569">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-1569">OR</span></span>

- <span data-ttu-id="35c9f-1570">代表出生日期的六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="35c9f-1571">一个正斜杠 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1571">A forward slash</span></span> 
- <span data-ttu-id="35c9f-1572">四个数字，其中最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1573">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1573">Checksum</span></span>

<span data-ttu-id="35c9f-1574">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1575">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1575">Definition</span></span>

<span data-ttu-id="35c9f-1576">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_czech_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-1577">找到 Keyword_czech_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="35c9f-1578">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="35c9f-1579">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1579">Keywords</span></span>

- <span data-ttu-id="35c9f-1580">捷克个人识别码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1580">czech personal identity number</span></span>
- <span data-ttu-id="35c9f-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="35c9f-1582">	丹麦个人身份号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1583">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1583">Format</span></span>

<span data-ttu-id="35c9f-1584">10 个数字，包含连字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1585">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1585">Pattern</span></span>

<span data-ttu-id="35c9f-1586">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1586">10 digits:</span></span>
- <span data-ttu-id="35c9f-1587">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-1588">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-1588">A hyphen</span></span> 
- <span data-ttu-id="35c9f-1589">四个数字，最后一位数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1590">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1590">Checksum</span></span>

<span data-ttu-id="35c9f-1591">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1592">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1592">Definition</span></span>

<span data-ttu-id="35c9f-1593">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：正则表达式 Regex_denmark_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-1594">找到 Keyword_denmark_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="35c9f-1595">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-1596">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="35c9f-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="35c9f-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1598">Personal Identification Number</span></span>
- <span data-ttu-id="35c9f-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="35c9f-1599">CPR</span></span>
- <span data-ttu-id="35c9f-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="35c9f-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="35c9f-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="35c9f-1602">药品管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1603">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1603">Format</span></span>

<span data-ttu-id="35c9f-1604">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1605">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1605">Pattern</span></span>

<span data-ttu-id="35c9f-1606">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="35c9f-1607">这一组可能的字母（不区分大小写）中的一个字母：abcdefghjklmnprstux，这是注册人代码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="35c9f-1608">一个字母（不区分大小写），这是注册人姓氏的第一个字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="35c9f-1609">七位数字，最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1610">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1610">Checksum</span></span>

<span data-ttu-id="35c9f-1611">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1612">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1612">Definition</span></span>

<span data-ttu-id="35c9f-1613">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1614">函数 Func_dea_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1615">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-1616">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1616">Keywords</span></span>

<span data-ttu-id="35c9f-1617">无</span><span class="sxs-lookup"><span data-stu-id="35c9f-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="35c9f-1618">欧盟借记卡号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1619">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1619">Format</span></span>

<span data-ttu-id="35c9f-1620">16 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1621">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1621">Pattern</span></span>

<span data-ttu-id="35c9f-1622">非常复杂且强大的模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1623">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1623">Checksum</span></span>

<span data-ttu-id="35c9f-1624">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1625">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1625">Definition</span></span>

<span data-ttu-id="35c9f-1626">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1627">函数 Func_eu_debit_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1628">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="35c9f-1629">找到 Keyword_eu_debit_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="35c9f-1630">找到 Keyword_card_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="35c9f-1631">找到 Keyword_card_security_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="35c9f-1632">找到 Keyword_card_expiration_terms_dict 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="35c9f-1633">函数 Func_expiration_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="35c9f-1634">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1635">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="35c9f-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="35c9f-1637">account number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1637">account number</span></span> 
- <span data-ttu-id="35c9f-1638">card number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1638">card number</span></span> 
- <span data-ttu-id="35c9f-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1639">card no.</span></span> 
- <span data-ttu-id="35c9f-1640">security number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1640">security number</span></span> 
- <span data-ttu-id="35c9f-1641">收件人#</span><span class="sxs-lookup"><span data-stu-id="35c9f-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="35c9f-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="35c9f-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="35c9f-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="35c9f-1643">acct nbr</span></span> 
- <span data-ttu-id="35c9f-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="35c9f-1644">acct num</span></span> 
- <span data-ttu-id="35c9f-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1645">acct no</span></span> 
- <span data-ttu-id="35c9f-1646">american express</span><span class="sxs-lookup"><span data-stu-id="35c9f-1646">american express</span></span> 
- <span data-ttu-id="35c9f-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="35c9f-1647">americanexpress</span></span> 
- <span data-ttu-id="35c9f-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="35c9f-1648">americano espresso</span></span> 
- <span data-ttu-id="35c9f-1649">amex</span><span class="sxs-lookup"><span data-stu-id="35c9f-1649">amex</span></span> 
- <span data-ttu-id="35c9f-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1650">atm card</span></span> 
- <span data-ttu-id="35c9f-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1651">atm cards</span></span> 
- <span data-ttu-id="35c9f-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1652">atm kaart</span></span> 
- <span data-ttu-id="35c9f-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1653">atmcard</span></span> 
- <span data-ttu-id="35c9f-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1654">atmcards</span></span> 
- <span data-ttu-id="35c9f-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1655">atmkaart</span></span> 
- <span data-ttu-id="35c9f-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="35c9f-1656">atmkaarten</span></span> 
- <span data-ttu-id="35c9f-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="35c9f-1657">bancontact</span></span> 
- <span data-ttu-id="35c9f-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1658">bank card</span></span> 
- <span data-ttu-id="35c9f-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1659">bankkaart</span></span> 
- <span data-ttu-id="35c9f-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="35c9f-1660">card holder</span></span> 
- <span data-ttu-id="35c9f-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="35c9f-1661">card holders</span></span> 
- <span data-ttu-id="35c9f-1662">card num</span><span class="sxs-lookup"><span data-stu-id="35c9f-1662">card num</span></span> 
- <span data-ttu-id="35c9f-1663">card number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1663">card number</span></span> 
- <span data-ttu-id="35c9f-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1664">card numbers</span></span> 
- <span data-ttu-id="35c9f-1665">card type</span><span class="sxs-lookup"><span data-stu-id="35c9f-1665">card type</span></span> 
- <span data-ttu-id="35c9f-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="35c9f-1666">cardano numerico</span></span> 
- <span data-ttu-id="35c9f-1667">持卡人</span><span class="sxs-lookup"><span data-stu-id="35c9f-1667">cardholder</span></span> 
- <span data-ttu-id="35c9f-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="35c9f-1668">cardholders</span></span> 
- <span data-ttu-id="35c9f-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1669">cardnumber</span></span> 
- <span data-ttu-id="35c9f-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1670">cardnumbers</span></span> 
- <span data-ttu-id="35c9f-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1671">carta bianca</span></span> 
- <span data-ttu-id="35c9f-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1672">carta credito</span></span> 
- <span data-ttu-id="35c9f-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1673">carta di credito</span></span> 
- <span data-ttu-id="35c9f-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1674">cartao de credito</span></span> 
- <span data-ttu-id="35c9f-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1675">cartao de crédito</span></span> 
- <span data-ttu-id="35c9f-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1676">cartao de debito</span></span> 
- <span data-ttu-id="35c9f-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1677">cartao de débito</span></span> 
- <span data-ttu-id="35c9f-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="35c9f-1678">carte bancaire</span></span> 
- <span data-ttu-id="35c9f-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="35c9f-1679">carte blanche</span></span> 
- <span data-ttu-id="35c9f-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="35c9f-1680">carte bleue</span></span> 
- <span data-ttu-id="35c9f-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="35c9f-1681">carte de credit</span></span> 
- <span data-ttu-id="35c9f-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="35c9f-1682">carte de crédit</span></span> 
- <span data-ttu-id="35c9f-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1683">carte di credito</span></span> 
- <span data-ttu-id="35c9f-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="35c9f-1684">carteblanche</span></span> 
- <span data-ttu-id="35c9f-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1685">cartão de credito</span></span> 
- <span data-ttu-id="35c9f-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1686">cartão de crédito</span></span> 
- <span data-ttu-id="35c9f-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1687">cartão de debito</span></span> 
- <span data-ttu-id="35c9f-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1688">cartão de débito</span></span> 
- <span data-ttu-id="35c9f-1689">cb</span><span class="sxs-lookup"><span data-stu-id="35c9f-1689">cb</span></span> 
- <span data-ttu-id="35c9f-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1690">ccn</span></span> 
- <span data-ttu-id="35c9f-1691">check card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1691">check card</span></span> 
- <span data-ttu-id="35c9f-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1692">check cards</span></span> 
- <span data-ttu-id="35c9f-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1693">checkcard</span></span>
- <span data-ttu-id="35c9f-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1694">checkcards</span></span> 
- <span data-ttu-id="35c9f-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1695">chequekaart</span></span> 
- <span data-ttu-id="35c9f-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="35c9f-1696">cirrus</span></span> 
- <span data-ttu-id="35c9f-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="35c9f-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="35c9f-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1698">controlekaart</span></span> 
- <span data-ttu-id="35c9f-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="35c9f-1699">controlekaarten</span></span> 
- <span data-ttu-id="35c9f-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1700">credit card</span></span> 
- <span data-ttu-id="35c9f-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1701">credit cards</span></span> 
- <span data-ttu-id="35c9f-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1702">creditcard</span></span> 
- <span data-ttu-id="35c9f-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1703">creditcards</span></span> 
- <span data-ttu-id="35c9f-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1704">debetkaart</span></span> 
- <span data-ttu-id="35c9f-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="35c9f-1705">debetkaarten</span></span> 
- <span data-ttu-id="35c9f-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1706">debit card</span></span> 
- <span data-ttu-id="35c9f-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1707">debit cards</span></span> 
- <span data-ttu-id="35c9f-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1708">debitcard</span></span> 
- <span data-ttu-id="35c9f-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1709">debitcards</span></span> 
- <span data-ttu-id="35c9f-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="35c9f-1710">debito automatico</span></span> 
- <span data-ttu-id="35c9f-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="35c9f-1711">diners club</span></span> 
- <span data-ttu-id="35c9f-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="35c9f-1712">dinersclub</span></span> 
- <span data-ttu-id="35c9f-1713">确定</span><span class="sxs-lookup"><span data-stu-id="35c9f-1713">discover</span></span> 
- <span data-ttu-id="35c9f-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1714">discover card</span></span> 
- <span data-ttu-id="35c9f-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1715">discover cards</span></span> 
- <span data-ttu-id="35c9f-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1716">discovercard</span></span> 
- <span data-ttu-id="35c9f-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1717">discovercards</span></span> 
- <span data-ttu-id="35c9f-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="35c9f-1718">débito automático</span></span>
- <span data-ttu-id="35c9f-1719">edc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1719">edc</span></span> 
- <span data-ttu-id="35c9f-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="35c9f-1720">eigentümername</span></span> 
- <span data-ttu-id="35c9f-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1721">european debit card</span></span> 
- <span data-ttu-id="35c9f-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1722">hoofdkaart</span></span> 
- <span data-ttu-id="35c9f-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="35c9f-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="35c9f-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="35c9f-1724">in viaggio</span></span> 
- <span data-ttu-id="35c9f-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="35c9f-1725">japanese card bureau</span></span> 
- <span data-ttu-id="35c9f-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="35c9f-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="35c9f-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="35c9f-1727">jcb</span></span> 
- <span data-ttu-id="35c9f-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="35c9f-1728">kaart</span></span> 
- <span data-ttu-id="35c9f-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="35c9f-1729">kaart num</span></span> 
- <span data-ttu-id="35c9f-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="35c9f-1730">kaartaantal</span></span> 
- <span data-ttu-id="35c9f-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="35c9f-1731">kaartaantallen</span></span> 
- <span data-ttu-id="35c9f-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="35c9f-1732">kaarthouder</span></span> 
- <span data-ttu-id="35c9f-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="35c9f-1733">kaarthouders</span></span> 
- <span data-ttu-id="35c9f-1734">karte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1734">karte</span></span>  
- <span data-ttu-id="35c9f-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1735">karteninhaber</span></span> 
- <span data-ttu-id="35c9f-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="35c9f-1736">karteninhabers</span></span>
- <span data-ttu-id="35c9f-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="35c9f-1737">kartennr</span></span> 
- <span data-ttu-id="35c9f-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1738">kartennummer</span></span> 
- <span data-ttu-id="35c9f-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1739">kreditkarte</span></span> 
- <span data-ttu-id="35c9f-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="35c9f-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="35c9f-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="35c9f-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="35c9f-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="35c9f-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="35c9f-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="35c9f-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="35c9f-1745">maestro</span></span> 
- <span data-ttu-id="35c9f-1746">Master Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-1746">master card</span></span> 
- <span data-ttu-id="35c9f-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1747">master cards</span></span> 
- <span data-ttu-id="35c9f-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="35c9f-1748">mastercard</span></span> 
- <span data-ttu-id="35c9f-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="35c9f-1749">mastercards</span></span> 
- <span data-ttu-id="35c9f-1750">emc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1750">mc</span></span> 
- <span data-ttu-id="35c9f-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="35c9f-1751">mister cash</span></span> 
- <span data-ttu-id="35c9f-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1752">n carta</span></span> 
- <span data-ttu-id="35c9f-1753">carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1753">carta</span></span> 
- <span data-ttu-id="35c9f-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1754">no de tarjeta</span></span> 
- <span data-ttu-id="35c9f-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1755">no do cartao</span></span> 
- <span data-ttu-id="35c9f-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1756">no do cartão</span></span> 
- <span data-ttu-id="35c9f-1757">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1757">no.</span></span> <span data-ttu-id="35c9f-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1758">de tarjeta</span></span> 
- <span data-ttu-id="35c9f-1759">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1759">no.</span></span> <span data-ttu-id="35c9f-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1760">do cartao</span></span> 
- <span data-ttu-id="35c9f-1761">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1761">no.</span></span> <span data-ttu-id="35c9f-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1762">do cartão</span></span> 
- <span data-ttu-id="35c9f-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1763">nr carta</span></span> 
- <span data-ttu-id="35c9f-1764">führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1764">nr.</span></span> <span data-ttu-id="35c9f-1765">carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1765">carta</span></span> 
- <span data-ttu-id="35c9f-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1766">numeri di scheda</span></span> 
- <span data-ttu-id="35c9f-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1767">numero carta</span></span> 
- <span data-ttu-id="35c9f-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1768">numero de cartao</span></span> 
- <span data-ttu-id="35c9f-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1769">numero de carte</span></span> 
- <span data-ttu-id="35c9f-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1770">numero de cartão</span></span> 
- <span data-ttu-id="35c9f-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1771">numero de tarjeta</span></span>
- <span data-ttu-id="35c9f-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1772">numero della carta</span></span> 
- <span data-ttu-id="35c9f-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1773">numero di carta</span></span> 
- <span data-ttu-id="35c9f-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1774">numero di scheda</span></span> 
- <span data-ttu-id="35c9f-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1775">numero do cartao</span></span> 
- <span data-ttu-id="35c9f-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1776">numero do cartão</span></span> 
- <span data-ttu-id="35c9f-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1777">numéro de carte</span></span> 
- <span data-ttu-id="35c9f-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1778">nº carta</span></span> 
- <span data-ttu-id="35c9f-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1779">nº de carte</span></span> 
- <span data-ttu-id="35c9f-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="35c9f-1780">nº de la carte</span></span> 
- <span data-ttu-id="35c9f-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="35c9f-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1782">nº do cartao</span></span> 
- <span data-ttu-id="35c9f-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1783">nº do cartão</span></span> 
- <span data-ttu-id="35c9f-1784">n º。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1784">nº.</span></span> <span data-ttu-id="35c9f-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1785">do cartão</span></span> 
- <span data-ttu-id="35c9f-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1786">número de cartao</span></span> 
- <span data-ttu-id="35c9f-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="35c9f-1787">número de cartão</span></span> 
- <span data-ttu-id="35c9f-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1788">número de tarjeta</span></span> 
- <span data-ttu-id="35c9f-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1789">número do cartao</span></span> 
- <span data-ttu-id="35c9f-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="35c9f-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="35c9f-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="35c9f-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="35c9f-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="35c9f-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="35c9f-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1793">scheda della banca</span></span> 
- <span data-ttu-id="35c9f-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1794">scheda di controllo</span></span> 
- <span data-ttu-id="35c9f-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1795">scheda di debito</span></span> 
- <span data-ttu-id="35c9f-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="35c9f-1796">scheda matrice</span></span> 
- <span data-ttu-id="35c9f-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="35c9f-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="35c9f-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1798">schede di controllo</span></span> 
- <span data-ttu-id="35c9f-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1799">schede di debito</span></span> 
- <span data-ttu-id="35c9f-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="35c9f-1800">schede matrici</span></span> 
- <span data-ttu-id="35c9f-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="35c9f-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="35c9f-1802">scoprono le schede</span></span> 
- <span data-ttu-id="35c9f-1803">solo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1803">solo</span></span> 
- <span data-ttu-id="35c9f-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1804">supporti di scheda</span></span> 
- <span data-ttu-id="35c9f-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1805">supporto di scheda</span></span> 
- <span data-ttu-id="35c9f-1806">器</span><span class="sxs-lookup"><span data-stu-id="35c9f-1806">switch</span></span> 
- <span data-ttu-id="35c9f-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="35c9f-1807">tarjeta atm</span></span> 
- <span data-ttu-id="35c9f-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1808">tarjeta credito</span></span> 
- <span data-ttu-id="35c9f-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="35c9f-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="35c9f-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="35c9f-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="35c9f-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="35c9f-1812">tarjeta debito</span></span> 
- <span data-ttu-id="35c9f-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1813">tarjeta no</span></span>
- <span data-ttu-id="35c9f-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="35c9f-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="35c9f-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1815">tipo della scheda</span></span> 
- <span data-ttu-id="35c9f-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="35c9f-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="35c9f-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1817">scheda</span></span> 
- <span data-ttu-id="35c9f-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="35c9f-1818">v pay</span></span> 
- <span data-ttu-id="35c9f-1819">v-支付</span><span class="sxs-lookup"><span data-stu-id="35c9f-1819">v-pay</span></span> 
- <span data-ttu-id="35c9f-1820">反之</span><span class="sxs-lookup"><span data-stu-id="35c9f-1820">visa</span></span> 
- <span data-ttu-id="35c9f-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="35c9f-1821">visa plus</span></span> 
- <span data-ttu-id="35c9f-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="35c9f-1822">visa electron</span></span> 
- <span data-ttu-id="35c9f-1823">visto</span><span class="sxs-lookup"><span data-stu-id="35c9f-1823">visto</span></span> 
- <span data-ttu-id="35c9f-1824">visum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1824">visum</span></span> 
- <span data-ttu-id="35c9f-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="35c9f-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="35c9f-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="35c9f-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="35c9f-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1827">card identification number</span></span>
- <span data-ttu-id="35c9f-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="35c9f-1828">card verification</span></span> 
- <span data-ttu-id="35c9f-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="35c9f-1829">cardi la verifica</span></span> 
- <span data-ttu-id="35c9f-1830">cid</span><span class="sxs-lookup"><span data-stu-id="35c9f-1830">cid</span></span> 
- <span data-ttu-id="35c9f-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="35c9f-1831">cod seg</span></span> 
- <span data-ttu-id="35c9f-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1832">cod seguranca</span></span> 
- <span data-ttu-id="35c9f-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1833">cod segurança</span></span> 
- <span data-ttu-id="35c9f-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1834">cod sicurezza</span></span> 
- <span data-ttu-id="35c9f-1835">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1835">cod.</span></span> <span data-ttu-id="35c9f-1836">seg</span><span class="sxs-lookup"><span data-stu-id="35c9f-1836">seg</span></span> 
- <span data-ttu-id="35c9f-1837">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1837">cod.</span></span> <span data-ttu-id="35c9f-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1838">seguranca</span></span> 
- <span data-ttu-id="35c9f-1839">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1839">cod.</span></span> <span data-ttu-id="35c9f-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1840">segurança</span></span> 
- <span data-ttu-id="35c9f-1841">货.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1841">cod.</span></span> <span data-ttu-id="35c9f-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1842">sicurezza</span></span> 
- <span data-ttu-id="35c9f-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="35c9f-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="35c9f-1844">codice di verifica</span></span> 
- <span data-ttu-id="35c9f-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="35c9f-1845">codigo</span></span> 
- <span data-ttu-id="35c9f-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="35c9f-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1847">codigo de segurança</span></span> 
- <span data-ttu-id="35c9f-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="35c9f-1848">crittogramma</span></span> 
- <span data-ttu-id="35c9f-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="35c9f-1849">cryptogram</span></span> 
- <span data-ttu-id="35c9f-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="35c9f-1850">cryptogramme</span></span> 
- <span data-ttu-id="35c9f-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="35c9f-1851">cv2</span></span> 
- <span data-ttu-id="35c9f-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1852">cvc</span></span> 
- <span data-ttu-id="35c9f-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="35c9f-1853">cvc2</span></span> 
- <span data-ttu-id="35c9f-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="35c9f-1854">cvn</span></span> 
- <span data-ttu-id="35c9f-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="35c9f-1855">cvv</span></span> 
- <span data-ttu-id="35c9f-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="35c9f-1856">cvv2</span></span> 
- <span data-ttu-id="35c9f-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1857">cód seguranca</span></span> 
- <span data-ttu-id="35c9f-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1858">cód segurança</span></span> 
- <span data-ttu-id="35c9f-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1859">cód.</span></span> <span data-ttu-id="35c9f-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1860">seguranca</span></span> 
- <span data-ttu-id="35c9f-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="35c9f-1861">cód.</span></span> <span data-ttu-id="35c9f-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1862">segurança</span></span> 
- <span data-ttu-id="35c9f-1863">código</span><span class="sxs-lookup"><span data-stu-id="35c9f-1863">código</span></span> 
- <span data-ttu-id="35c9f-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="35c9f-1864">código de seguranca</span></span> 
- <span data-ttu-id="35c9f-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="35c9f-1865">código de segurança</span></span> 
- <span data-ttu-id="35c9f-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="35c9f-1866">de kaart controle</span></span> 
- <span data-ttu-id="35c9f-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="35c9f-1867">geeft nr uit</span></span> 
- <span data-ttu-id="35c9f-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1868">issue no</span></span> 
- <span data-ttu-id="35c9f-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1869">issue number</span></span> 
- <span data-ttu-id="35c9f-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="35c9f-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="35c9f-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="35c9f-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="35c9f-1873">kwestieaantal</span></span> 
- <span data-ttu-id="35c9f-1874">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1874">no.</span></span> <span data-ttu-id="35c9f-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="35c9f-1875">dell'edizione</span></span> 
- <span data-ttu-id="35c9f-1876">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1876">no.</span></span> <span data-ttu-id="35c9f-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1877">di sicurezza</span></span> 
- <span data-ttu-id="35c9f-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="35c9f-1878">numero de securite</span></span> 
- <span data-ttu-id="35c9f-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1879">numero de verificacao</span></span> 
- <span data-ttu-id="35c9f-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="35c9f-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="35c9f-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="35c9f-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="35c9f-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="35c9f-1882">scheda</span></span> 
- <span data-ttu-id="35c9f-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="35c9f-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="35c9f-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="35c9f-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="35c9f-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="35c9f-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="35c9f-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="35c9f-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="35c9f-1887">número de verificação</span></span> 
- <span data-ttu-id="35c9f-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="35c9f-1888">perno il blocco</span></span> 
- <span data-ttu-id="35c9f-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="35c9f-1889">pin block</span></span> 
- <span data-ttu-id="35c9f-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1890">prufziffer</span></span> 
- <span data-ttu-id="35c9f-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1891">prüfziffer</span></span> 
- <span data-ttu-id="35c9f-1892">security code</span><span class="sxs-lookup"><span data-stu-id="35c9f-1892">security code</span></span> 
- <span data-ttu-id="35c9f-1893">security no</span><span class="sxs-lookup"><span data-stu-id="35c9f-1893">security no</span></span> 
- <span data-ttu-id="35c9f-1894">security number</span><span class="sxs-lookup"><span data-stu-id="35c9f-1894">security number</span></span> 
- <span data-ttu-id="35c9f-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="35c9f-1895">sicherheits kode</span></span> 
- <span data-ttu-id="35c9f-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="35c9f-1896">sicherheitscode</span></span> 
- <span data-ttu-id="35c9f-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="35c9f-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="35c9f-1898">speldblok</span></span> 
- <span data-ttu-id="35c9f-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-1899">veiligheid nr</span></span> 
- <span data-ttu-id="35c9f-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="35c9f-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="35c9f-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="35c9f-1901">veiligheidscode</span></span> 
- <span data-ttu-id="35c9f-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="35c9f-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="35c9f-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="35c9f-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="35c9f-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="35c9f-1905">ablauf</span></span> 
- <span data-ttu-id="35c9f-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="35c9f-1906">data de expiracao</span></span> 
- <span data-ttu-id="35c9f-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="35c9f-1907">data de expiração</span></span> 
- <span data-ttu-id="35c9f-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1908">data del exp</span></span> 
- <span data-ttu-id="35c9f-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1909">data di exp</span></span> 
- <span data-ttu-id="35c9f-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1910">data di scadenza</span></span> 
- <span data-ttu-id="35c9f-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="35c9f-1911">data em que expira</span></span> 
- <span data-ttu-id="35c9f-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="35c9f-1912">data scad</span></span> 
- <span data-ttu-id="35c9f-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1913">data scadenza</span></span> 
- <span data-ttu-id="35c9f-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="35c9f-1914">date de validité</span></span> 
- <span data-ttu-id="35c9f-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="35c9f-1915">datum afloop</span></span> 
- <span data-ttu-id="35c9f-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="35c9f-1916">datum van exp</span></span> 
- <span data-ttu-id="35c9f-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="35c9f-1917">de afloop</span></span> 
- <span data-ttu-id="35c9f-1918">espira</span><span class="sxs-lookup"><span data-stu-id="35c9f-1918">espira</span></span> 
- <span data-ttu-id="35c9f-1919">espira</span><span class="sxs-lookup"><span data-stu-id="35c9f-1919">espira</span></span> 
- <span data-ttu-id="35c9f-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="35c9f-1920">exp date</span></span> 
- <span data-ttu-id="35c9f-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1921">exp datum</span></span> 
- <span data-ttu-id="35c9f-1922">时间</span><span class="sxs-lookup"><span data-stu-id="35c9f-1922">expiration</span></span> 
- <span data-ttu-id="35c9f-1923">何时</span><span class="sxs-lookup"><span data-stu-id="35c9f-1923">expire</span></span> 
- <span data-ttu-id="35c9f-1924">不久</span><span class="sxs-lookup"><span data-stu-id="35c9f-1924">expires</span></span> 
- <span data-ttu-id="35c9f-1925">过期</span><span class="sxs-lookup"><span data-stu-id="35c9f-1925">expiry</span></span> 
- <span data-ttu-id="35c9f-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="35c9f-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="35c9f-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1927">fecha de venc</span></span> 
- <span data-ttu-id="35c9f-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="35c9f-1928">gultig bis</span></span> 
- <span data-ttu-id="35c9f-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="35c9f-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="35c9f-1930">gültig bis</span></span> 
- <span data-ttu-id="35c9f-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="35c9f-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1932">la scadenza</span></span> 
- <span data-ttu-id="35c9f-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="35c9f-1933">scadenza</span></span> 
- <span data-ttu-id="35c9f-1934">valable</span><span class="sxs-lookup"><span data-stu-id="35c9f-1934">valable</span></span> 
- <span data-ttu-id="35c9f-1935">validade</span><span class="sxs-lookup"><span data-stu-id="35c9f-1935">validade</span></span> 
- <span data-ttu-id="35c9f-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1936">valido hasta</span></span> 
- <span data-ttu-id="35c9f-1937">valor</span><span class="sxs-lookup"><span data-stu-id="35c9f-1937">valor</span></span> 
- <span data-ttu-id="35c9f-1938">venc</span><span class="sxs-lookup"><span data-stu-id="35c9f-1938">venc</span></span> 
- <span data-ttu-id="35c9f-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="35c9f-1939">vencimento</span></span> 
- <span data-ttu-id="35c9f-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="35c9f-1940">vencimiento</span></span> 
- <span data-ttu-id="35c9f-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="35c9f-1941">verloopt</span></span> 
- <span data-ttu-id="35c9f-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="35c9f-1942">vervaldag</span></span> 
- <span data-ttu-id="35c9f-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-1943">vervaldatum</span></span> 
- <span data-ttu-id="35c9f-1944">vto</span><span class="sxs-lookup"><span data-stu-id="35c9f-1944">vto</span></span> 
- <span data-ttu-id="35c9f-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="35c9f-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="35c9f-1946">欧盟驾驶执照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1946">EU Driver's License Number</span></span>

<span data-ttu-id="35c9f-1947">若要了解详细信息，请参阅[EU 驱动程序的许可号敏感信息类型](eu-driver-s-license-number.md)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="35c9f-1948">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1948">EU National Identification Number</span></span>

<span data-ttu-id="35c9f-1949">若要了解详细信息，请参阅[EU 国家身份证号敏感信息类型](eu-national-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="35c9f-1950">EU 护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1950">EU Passport Number</span></span>

<span data-ttu-id="35c9f-1951">若要了解详细信息，请参阅[EU 护照号敏感信息类型](eu-passport-number.md)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="35c9f-1952">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="35c9f-1953">若要了解详细信息，请参阅[EU 社会保险号或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="35c9f-1954">EU 税标识号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="35c9f-1955">若要了解详细信息，请参阅[EU 纳税识别号敏感信息类型](eu-tax-identification-number.md)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="35c9f-1956">芬兰国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1957">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1957">Format</span></span>

<span data-ttu-id="35c9f-1958">六个数字加一个字符（表示一个世纪），加三个数字再加一个校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1959">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1959">Pattern</span></span>

<span data-ttu-id="35c9f-1960">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="35c9f-1961">采用 DDMMYY 格式的六位数字，表示出生日期</span><span class="sxs-lookup"><span data-stu-id="35c9f-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="35c9f-1962">世纪标记（“-”、“+”或“a”）</span><span class="sxs-lookup"><span data-stu-id="35c9f-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="35c9f-1963">三位个人标识号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="35c9f-1964">一个数字或字母（区分大小写），是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1965">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1965">Checksum</span></span>

<span data-ttu-id="35c9f-1966">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1967">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1967">Definition</span></span>

<span data-ttu-id="35c9f-1968">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1969">函数 Func_finnish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1970">找到 Keyword_finnish_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="35c9f-1971">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-1972">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1972">Keywords</span></span>

- <span data-ttu-id="35c9f-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="35c9f-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="35c9f-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="35c9f-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="35c9f-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="35c9f-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="35c9f-1976">Personbeteckning</span></span>
- <span data-ttu-id="35c9f-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="35c9f-1978">芬兰护照号</span><span class="sxs-lookup"><span data-stu-id="35c9f-1978">Finland Passport Number</span></span>

<span data-ttu-id="35c9f-1979">设置九个字母和数字的组合的组合九个字母和数字的组合：两个字母（不区分大小写）七个数字校验和无定义 DLP 策略是75% 确信它检测到这种类型的敏感信息，如果在300个字符的邻近性：正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-1980">找到 Keyword_finland_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="35c9f-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="35c9f-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="35c9f-1982">Keyword_finland_passport_number Passport Passi 的关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="35c9f-1983">法国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-1984">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-1984">Format</span></span>

<span data-ttu-id="35c9f-1985">12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-1986">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-1986">Pattern</span></span>

<span data-ttu-id="35c9f-1987">12 个数字，会对类似模式（如法国电话号码）进行验证</span><span class="sxs-lookup"><span data-stu-id="35c9f-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-1988">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-1988">Checksum</span></span>

<span data-ttu-id="35c9f-1989">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-1990">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-1990">Definition</span></span>

<span data-ttu-id="35c9f-1991">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-1992">函数 Func_french_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-1993">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="35c9f-1994">找到 Keyword_french_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="35c9f-1995">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-1996">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="35c9f-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="35c9f-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="35c9f-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-1998">drivers licence</span></span>
- <span data-ttu-id="35c9f-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="35c9f-1999">drivers license</span></span>
- <span data-ttu-id="35c9f-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2000">driving licence</span></span>
- <span data-ttu-id="35c9f-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="35c9f-2001">driving license</span></span>
- <span data-ttu-id="35c9f-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="35c9f-2002">permis de conduire</span></span>
- <span data-ttu-id="35c9f-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2003">licence number</span></span>
- <span data-ttu-id="35c9f-2004">license number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2004">license number</span></span>
- <span data-ttu-id="35c9f-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-2005">licence numbers</span></span>
- <span data-ttu-id="35c9f-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="35c9f-2007">法国国家/地区 ID 卡 (CNI)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2008">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2008">Format</span></span>

<span data-ttu-id="35c9f-2009">12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2010">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2010">Pattern</span></span>

<span data-ttu-id="35c9f-2011">12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2012">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2012">Checksum</span></span>

<span data-ttu-id="35c9f-2013">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2014">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2014">Definition</span></span>

<span data-ttu-id="35c9f-2015">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2016">正则表达式 Regex_france_cni 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2017">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2017">Keywords</span></span>

<span data-ttu-id="35c9f-2018">无</span><span class="sxs-lookup"><span data-stu-id="35c9f-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="35c9f-2019">法国护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2020">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2020">Format</span></span>

<span data-ttu-id="35c9f-2021">9 个数字和字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2022">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2022">Pattern</span></span>

<span data-ttu-id="35c9f-2023">九位数字和字母：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="35c9f-2024">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2024">Two digits</span></span> 
- <span data-ttu-id="35c9f-2025">两个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2026">五位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2027">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2027">Checksum</span></span>

<span data-ttu-id="35c9f-2028">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2029">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2029">Definition</span></span>

<span data-ttu-id="35c9f-2030">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2031">函数 Func_fr_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2032">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2033">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="35c9f-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-2034">Keyword_passport</span></span>

- <span data-ttu-id="35c9f-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2035">Passport Number</span></span>
- <span data-ttu-id="35c9f-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="35c9f-2036">Passport No</span></span>
- <span data-ttu-id="35c9f-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2037">Passport #</span></span>
- <span data-ttu-id="35c9f-2038">登记卡#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2038">Passport#</span></span>
- <span data-ttu-id="35c9f-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2039">PassportID</span></span>
- <span data-ttu-id="35c9f-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="35c9f-2040">Passportno</span></span>
- <span data-ttu-id="35c9f-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-2041">passportnumber</span></span>
- <span data-ttu-id="35c9f-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-2042">パスポート</span></span>
- <span data-ttu-id="35c9f-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2043">パスポート番号</span></span>
- <span data-ttu-id="35c9f-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-2044">パスポートのNum</span></span>
- <span data-ttu-id="35c9f-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2045">パスポート ＃</span></span> 
- <span data-ttu-id="35c9f-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="35c9f-2046">Numéro de passeport</span></span>
- <span data-ttu-id="35c9f-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="35c9f-2047">Passeport n °</span></span>
- <span data-ttu-id="35c9f-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="35c9f-2048">Passeport Non</span></span>
- <span data-ttu-id="35c9f-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2049">Passeport #</span></span>
- <span data-ttu-id="35c9f-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2050">Passeport#</span></span>
- <span data-ttu-id="35c9f-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="35c9f-2051">PasseportNon</span></span>
- <span data-ttu-id="35c9f-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="35c9f-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="35c9f-2053">法国社会保险号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2054">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2054">Format</span></span>

<span data-ttu-id="35c9f-2055">15 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2056">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2056">Pattern</span></span>

<span data-ttu-id="35c9f-2057">必须匹配两种模式之一：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="35c9f-2058">13位数，后跟一个空格，后跟两个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="35c9f-2059">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-2059">or</span></span>
- <span data-ttu-id="35c9f-2060">15 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2061">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2061">Checksum</span></span>

<span data-ttu-id="35c9f-2062">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2063">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2063">Definition</span></span>

<span data-ttu-id="35c9f-2064">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2065">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2066">找到 Keyword_fr_insee 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="35c9f-2067">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2067">The checksum passes.</span></span>

<span data-ttu-id="35c9f-2068">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2069">函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2070">未找到 Keyword_fr_insee 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="35c9f-2071">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2072">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="35c9f-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="35c9f-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="35c9f-2074">insee</span><span class="sxs-lookup"><span data-stu-id="35c9f-2074">insee</span></span>
- <span data-ttu-id="35c9f-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2075">securité sociale</span></span>
- <span data-ttu-id="35c9f-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2076">securite sociale</span></span>
- <span data-ttu-id="35c9f-2077">national id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2077">national id</span></span>
- <span data-ttu-id="35c9f-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="35c9f-2078">national identification</span></span>
- <span data-ttu-id="35c9f-2079">numéro d identité</span><span class="sxs-lookup"><span data-stu-id="35c9f-2079">numéro d'identité</span></span>
- <span data-ttu-id="35c9f-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="35c9f-2080">no d'identité</span></span>
- <span data-ttu-id="35c9f-2081">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2081">no.</span></span> <span data-ttu-id="35c9f-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="35c9f-2082">d'identité</span></span>
- <span data-ttu-id="35c9f-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="35c9f-2083">numero d'identite</span></span>
- <span data-ttu-id="35c9f-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="35c9f-2084">no d'identite</span></span>
- <span data-ttu-id="35c9f-2085">不。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2085">no.</span></span> <span data-ttu-id="35c9f-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="35c9f-2086">d'identite</span></span>
- <span data-ttu-id="35c9f-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2087">social security number</span></span>
- <span data-ttu-id="35c9f-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="35c9f-2088">social security code</span></span>
- <span data-ttu-id="35c9f-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2089">social insurance number</span></span>
- <span data-ttu-id="35c9f-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="35c9f-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2091">d'identité nationale</span></span>
- <span data-ttu-id="35c9f-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="35c9f-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="35c9f-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="35c9f-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="35c9f-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="35c9f-2095">numéro de sécu</span></span>
- <span data-ttu-id="35c9f-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="35c9f-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="35c9f-2097">德国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2098">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2098">Format</span></span>

<span data-ttu-id="35c9f-2099">11 个数字和字母组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2100">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2100">Pattern</span></span>

<span data-ttu-id="35c9f-2101">11 位数字和字母（不区分大小写）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="35c9f-2102">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2102">A digit or letter</span></span> 
- <span data-ttu-id="35c9f-2103">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2103">Two digits</span></span> 
- <span data-ttu-id="35c9f-2104">六位数字或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2104">Six digits or letters</span></span> 
- <span data-ttu-id="35c9f-2105">一位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2105">A digit</span></span> 
- <span data-ttu-id="35c9f-2106">一个数字或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2107">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2107">Checksum</span></span>

<span data-ttu-id="35c9f-2108">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2109">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2109">Definition</span></span>

<span data-ttu-id="35c9f-2110">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2111">函数 Func_german_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2112">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="35c9f-2113">找到 Keyword_german_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="35c9f-2114">找到 Keyword_german_drivers_license_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="35c9f-2115">找到 Keyword_german_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="35c9f-2116">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2117">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="35c9f-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="35c9f-2119">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2119">Führerschein</span></span>
- <span data-ttu-id="35c9f-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2120">Fuhrerschein</span></span>
- <span data-ttu-id="35c9f-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2121">Fuehrerschein</span></span>
- <span data-ttu-id="35c9f-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="35c9f-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="35c9f-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="35c9f-2125">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2125">Führerschein-</span></span> 
- <span data-ttu-id="35c9f-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="35c9f-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="35c9f-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="35c9f-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="35c9f-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="35c9f-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="35c9f-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="35c9f-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="35c9f-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="35c9f-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="35c9f-2134">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="35c9f-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="35c9f-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="35c9f-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="35c9f-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="35c9f-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="35c9f-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="35c9f-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="35c9f-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="35c9f-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="35c9f-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="35c9f-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="35c9f-2146">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="35c9f-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="35c9f-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="35c9f-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="35c9f-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="35c9f-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="35c9f-2152">通讯</span><span class="sxs-lookup"><span data-stu-id="35c9f-2152">DL</span></span> 
- <span data-ttu-id="35c9f-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-2153">DLS</span></span>
- <span data-ttu-id="35c9f-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2154">Driv Lic</span></span> 
- <span data-ttu-id="35c9f-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="35c9f-2155">Driv Licen</span></span> 
- <span data-ttu-id="35c9f-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="35c9f-2156">Driv License</span></span>
- <span data-ttu-id="35c9f-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2157">Driv Licenses</span></span> 
- <span data-ttu-id="35c9f-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2158">Driv Licence</span></span> 
- <span data-ttu-id="35c9f-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-2159">Driv Licences</span></span> 
- <span data-ttu-id="35c9f-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2160">Driv Lic</span></span> 
- <span data-ttu-id="35c9f-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="35c9f-2161">Driver Licen</span></span> 
- <span data-ttu-id="35c9f-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="35c9f-2162">Driver License</span></span> 
- <span data-ttu-id="35c9f-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2163">Driver Licenses</span></span> 
- <span data-ttu-id="35c9f-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2164">Driver Licence</span></span> 
- <span data-ttu-id="35c9f-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-2165">Driver Licences</span></span> 
- <span data-ttu-id="35c9f-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2166">Drivers Lic</span></span> 
- <span data-ttu-id="35c9f-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="35c9f-2167">Drivers Licen</span></span> 
- <span data-ttu-id="35c9f-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="35c9f-2168">Drivers License</span></span> 
- <span data-ttu-id="35c9f-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="35c9f-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2170">Drivers Licence</span></span> 
- <span data-ttu-id="35c9f-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-2171">Drivers Licences</span></span> 
- <span data-ttu-id="35c9f-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2172">Driver's Lic</span></span> 
- <span data-ttu-id="35c9f-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="35c9f-2173">Driver's Licen</span></span> 
- <span data-ttu-id="35c9f-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="35c9f-2174">Driver's License</span></span> 
- <span data-ttu-id="35c9f-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="35c9f-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2176">Driver's Licence</span></span> 
- <span data-ttu-id="35c9f-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-2177">Driver's Licences</span></span> 
- <span data-ttu-id="35c9f-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2178">Driving Lic</span></span> 
- <span data-ttu-id="35c9f-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="35c9f-2179">Driving Licen</span></span> 
- <span data-ttu-id="35c9f-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="35c9f-2180">Driving License</span></span> 
- <span data-ttu-id="35c9f-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2181">Driving Licenses</span></span> 
- <span data-ttu-id="35c9f-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2182">Driving Licence</span></span> 
- <span data-ttu-id="35c9f-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="35c9f-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="35c9f-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="35c9f-2185">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="35c9f-2188">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2188">No-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2189">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2190">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="35c9f-2191">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2191">N-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="35c9f-2194">Nr-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="35c9f-2197">Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2197">No-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2198">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2199">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="35c9f-2200">N-Führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2200">N-Führerschein</span></span> 
- <span data-ttu-id="35c9f-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="35c9f-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="35c9f-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="35c9f-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="35c9f-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="35c9f-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="35c9f-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="35c9f-2205">ausstellungsort</span></span>
- <span data-ttu-id="35c9f-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="35c9f-2206">ausstellende behöde</span></span>
- <span data-ttu-id="35c9f-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="35c9f-2207">ausstellende behorde</span></span>
- <span data-ttu-id="35c9f-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="35c9f-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="35c9f-2209">德国护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2210">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2210">Format</span></span>

<span data-ttu-id="35c9f-2211">10 个数字或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2212">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2212">Pattern</span></span>

<span data-ttu-id="35c9f-2213">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="35c9f-2214">第一个字符是这一组（C、F、G、H、J、K）中的数字或字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="35c9f-2215">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2215">Three digits</span></span> 
- <span data-ttu-id="35c9f-2216">五位数字或字母都来源于这一组（C、-H、J-N、P、R、T，V-Z）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="35c9f-2217">一位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2218">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2218">Checksum</span></span>

<span data-ttu-id="35c9f-2219">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2220">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2220">Definition</span></span>

<span data-ttu-id="35c9f-2221">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2222">函数 Func_german_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2223">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="35c9f-2224">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2224">The checksum passes.</span></span>

<span data-ttu-id="35c9f-2225">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2226">函数 Func_german_passport_data 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2227">找到以下任意五个关键字列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="35c9f-2228">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2229">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="35c9f-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="35c9f-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="35c9f-2231">reisepass</span></span>
- <span data-ttu-id="35c9f-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="35c9f-2232">reisepasse</span></span>
- <span data-ttu-id="35c9f-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2233">reisepassnummer</span></span>
- <span data-ttu-id="35c9f-2234">登记卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-2234">passport</span></span>
- <span data-ttu-id="35c9f-2235">passports</span><span class="sxs-lookup"><span data-stu-id="35c9f-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="35c9f-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="35c9f-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="35c9f-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-2237">geburtsdatum</span></span>
- <span data-ttu-id="35c9f-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="35c9f-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="35c9f-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="35c9f-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="35c9f-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="35c9f-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="35c9f-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="35c9f-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="35c9f-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="35c9f-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="35c9f-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="35c9f-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="35c9f-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="35c9f-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="35c9f-2246">德国身份证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2247">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2247">Format</span></span>

<span data-ttu-id="35c9f-2248">自2010年11月1日起：九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="35c9f-2249">从1年4月1987至31年10月2010：10位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2250">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2250">Pattern</span></span>

<span data-ttu-id="35c9f-2251">自 2010 年 11 月 1 日起：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="35c9f-2252">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2253">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2253">Eight digits</span></span>

<span data-ttu-id="35c9f-2254">介于1年4月1987至 31 10 月2010：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="35c9f-2255">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2256">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2256">Checksum</span></span>

<span data-ttu-id="35c9f-2257">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2258">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2258">Definition</span></span>

<span data-ttu-id="35c9f-2259">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2260">正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2261">找到 Keyword_germany_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2262">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="35c9f-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="35c9f-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2264">Identity Card</span></span>
- <span data-ttu-id="35c9f-2265">ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2265">ID</span></span>
- <span data-ttu-id="35c9f-2266">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2266">Identification</span></span>
- <span data-ttu-id="35c9f-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="35c9f-2267">Personalausweis</span></span>
- <span data-ttu-id="35c9f-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="35c9f-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="35c9f-2269">Ausweis</span></span>
- <span data-ttu-id="35c9f-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="35c9f-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="35c9f-2271">希腊国家 ID 卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2272">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2272">Format</span></span>

<span data-ttu-id="35c9f-2273">7-8 个字母和数字组合加一个短划线</span><span class="sxs-lookup"><span data-stu-id="35c9f-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2274">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2274">Pattern</span></span>

<span data-ttu-id="35c9f-2275">七个字母和数字（旧格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="35c9f-2276">一个字母（希腊字母表中的任一字母） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="35c9f-2277">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2277">A dash</span></span> 
- <span data-ttu-id="35c9f-2278">六位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2278">Six digits</span></span>

<span data-ttu-id="35c9f-2279">八个字母和数字（新格式）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="35c9f-2280">大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="35c9f-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="35c9f-2281">一个短划线 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2281">A dash</span></span> 
- <span data-ttu-id="35c9f-2282">六位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2283">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2283">Checksum</span></span>

<span data-ttu-id="35c9f-2284">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2285">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2285">Definition</span></span>

<span data-ttu-id="35c9f-2286">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2287">正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2288">找到 Keyword_greece_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2289">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="35c9f-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="35c9f-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2291">Greek identity Card</span></span>
- <span data-ttu-id="35c9f-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="35c9f-2292">Tautotita</span></span>
- <span data-ttu-id="35c9f-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="35c9f-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="35c9f-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="35c9f-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="35c9f-2295">香港身份证 (HKID) 号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2296">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2296">Format</span></span>

<span data-ttu-id="35c9f-2297">8-9 个字母和数字组合，最后一个字符两边可选择加括号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2298">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2298">Pattern</span></span>

<span data-ttu-id="35c9f-2299">8-9 个字母组合：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="35c9f-2300">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2301">六个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2301">Six digits</span></span> 
- <span data-ttu-id="35c9f-2302">最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2303">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2303">Checksum</span></span>

<span data-ttu-id="35c9f-2304">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2305">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2305">Definition</span></span>

<span data-ttu-id="35c9f-2306">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2307">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2308">找到 Keyword_hong_kong_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="35c9f-2309">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2309">The checksum passes.</span></span>

<span data-ttu-id="35c9f-2310">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2311">函数 Func_hong_kong_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2312">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2313">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="35c9f-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="35c9f-2315">中国香港恒等卡片</span><span class="sxs-lookup"><span data-stu-id="35c9f-2315">hong kong identity card</span></span>
- <span data-ttu-id="35c9f-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="35c9f-2316">HKIDC</span></span>
- <span data-ttu-id="35c9f-2317">id card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2317">id card</span></span>
- <span data-ttu-id="35c9f-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2318">identity card</span></span>
- <span data-ttu-id="35c9f-2319">hk identity 卡片</span><span class="sxs-lookup"><span data-stu-id="35c9f-2319">hk identity card</span></span>
- <span data-ttu-id="35c9f-2320">香港 id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2320">hong kong id</span></span>
- <span data-ttu-id="35c9f-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2321">香港身份證</span></span>
- <span data-ttu-id="35c9f-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="35c9f-2323">證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2323">身份證</span></span>
- <span data-ttu-id="35c9f-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2324">身份証</span></span>
- <span data-ttu-id="35c9f-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2325">身分證</span></span>
- <span data-ttu-id="35c9f-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2326">身分証</span></span>
- <span data-ttu-id="35c9f-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2327">香港身份証</span></span>
- <span data-ttu-id="35c9f-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2328">香港身分證</span></span>
- <span data-ttu-id="35c9f-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2329">香港身分証</span></span>
- <span data-ttu-id="35c9f-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2330">香港身份證</span></span>
- <span data-ttu-id="35c9f-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2331">香港居民身份證</span></span>
- <span data-ttu-id="35c9f-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2332">香港居民身份証</span></span>
- <span data-ttu-id="35c9f-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2333">香港居民身分證</span></span>
- <span data-ttu-id="35c9f-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2334">香港居民身分証</span></span>
- <span data-ttu-id="35c9f-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="35c9f-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="35c9f-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="35c9f-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="35c9f-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="35c9f-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="35c9f-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="35c9f-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="35c9f-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="35c9f-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="35c9f-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="35c9f-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="35c9f-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="35c9f-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="35c9f-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="35c9f-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="35c9f-2351">印度永久帐号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2352">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2352">Format</span></span>

<span data-ttu-id="35c9f-2353">10 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2354">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2354">Pattern</span></span>

<span data-ttu-id="35c9f-2355">10 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2355">10 letters or digits:</span></span>
- <span data-ttu-id="35c9f-2356">五个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2357">四位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2357">Four digits</span></span> 
- <span data-ttu-id="35c9f-2358">一个字母，是字母校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2359">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2359">Checksum</span></span>

<span data-ttu-id="35c9f-2360">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2361">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2361">Definition</span></span>

<span data-ttu-id="35c9f-2362">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2363">正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2364">找到 Keyword_india_permanent_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="35c9f-2365">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2366">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="35c9f-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="35c9f-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="35c9f-2369">蛋糕</span><span class="sxs-lookup"><span data-stu-id="35c9f-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="35c9f-2370">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2371">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2371">Format</span></span>

<span data-ttu-id="35c9f-2372">12 个数字（包含可选空格或短划线）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2373">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2373">Pattern</span></span>

<span data-ttu-id="35c9f-2374">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2374">12 digits:</span></span>
- <span data-ttu-id="35c9f-2375">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2375">Four digits</span></span> 
- <span data-ttu-id="35c9f-2376">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2376">An optional space or dash</span></span> 
- <span data-ttu-id="35c9f-2377">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2377">Four digits</span></span> 
- <span data-ttu-id="35c9f-2378">一个可选空格或短划线 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2378">An optional space or dash</span></span> 
- <span data-ttu-id="35c9f-2379">最后一个数字是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2380">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2380">Checksum</span></span>

<span data-ttu-id="35c9f-2381">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2382">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2382">Definition</span></span>

<span data-ttu-id="35c9f-2383">DLP 策略85% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-2384">找到 Keyword_india_aadhar 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="35c9f-2385">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2385">The checksum passes.</span></span>
<span data-ttu-id="35c9f-2386">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_india_aadhaar 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-2387">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="35c9f-2388">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="35c9f-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="35c9f-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="35c9f-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="35c9f-2390">Aadhar</span></span>
- <span data-ttu-id="35c9f-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="35c9f-2391">Aadhaar</span></span>
- <span data-ttu-id="35c9f-2392">UID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2392">UID</span></span>
- <span data-ttu-id="35c9f-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="35c9f-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="35c9f-2394">印度尼西亚身份证 (KTP) 号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2395">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2395">Format</span></span>

<span data-ttu-id="35c9f-2396">16 个数字（包含可选点）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2397">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2397">Pattern</span></span>

<span data-ttu-id="35c9f-2398">16 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2398">16 digits:</span></span>
- <span data-ttu-id="35c9f-2399">两位省代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2399">Two-digit province code</span></span> 
- <span data-ttu-id="35c9f-2400">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2400">A period (optional)</span></span> 
- <span data-ttu-id="35c9f-2401">两位摄政统治区或城市代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="35c9f-2402">两位住宅小区代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="35c9f-2403">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2403">A period (optional)</span></span> 
- <span data-ttu-id="35c9f-2404">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-2405">一个点（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2405">A period (optional)</span></span> 
- <span data-ttu-id="35c9f-2406">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2407">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2407">Checksum</span></span>

<span data-ttu-id="35c9f-2408">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2409">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2409">Definition</span></span>

<span data-ttu-id="35c9f-2410">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2411">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2412">找到 Keyword_indonesia_id_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="35c9f-2413">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2414">正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2415">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="35c9f-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="35c9f-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="35c9f-2417">KTP</span></span>
- <span data-ttu-id="35c9f-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="35c9f-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="35c9f-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="35c9f-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="35c9f-2420">国际银行帐号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2421">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2421">Format</span></span>

<span data-ttu-id="35c9f-2422">国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2423">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2423">Pattern</span></span>

<span data-ttu-id="35c9f-2424">模式必须包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="35c9f-2425">两个字母的国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2425">Two-letter country code</span></span>
- <span data-ttu-id="35c9f-2426">两个校验位（后跟一个可选空间） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="35c9f-2427">1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="35c9f-2428">1-3 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2428">1-3 letters or digits</span></span>

<span data-ttu-id="35c9f-p135">每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：</span><span class="sxs-lookup"><span data-stu-id="35c9f-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="35c9f-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="35c9f-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2432">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2432">Checksum</span></span>

<span data-ttu-id="35c9f-2433">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2434">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2434">Definition</span></span>

<span data-ttu-id="35c9f-2435">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2436">函数 Func_iban 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2437">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2438">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2438">Keywords</span></span>

<span data-ttu-id="35c9f-2439">无</span><span class="sxs-lookup"><span data-stu-id="35c9f-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="35c9f-2440">IP 地址</span><span class="sxs-lookup"><span data-stu-id="35c9f-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2441">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="35c9f-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="35c9f-2442">IPv4:</span></span>
<span data-ttu-id="35c9f-2443">解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="35c9f-2444">Ipv4</span><span class="sxs-lookup"><span data-stu-id="35c9f-2444">IPv6:</span></span>
<span data-ttu-id="35c9f-2445"> 解释格式化 IPv6 号码（包含冒号）的复杂模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2446">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2447">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2447">Checksum</span></span>

<span data-ttu-id="35c9f-2448">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2449">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2449">Definition</span></span>

<span data-ttu-id="35c9f-2450">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2451">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2452">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="35c9f-2453">对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2454">正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2455">找到 Keyword_ipaddress 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="35c9f-2456">对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2457">正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2458">未找到 Keyword_ipaddress 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2459">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="35c9f-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="35c9f-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="35c9f-2461">IP（此关键字区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="35c9f-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="35c9f-2462">ip address</span></span> 
- <span data-ttu-id="35c9f-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2463">ip addresses</span></span>
- <span data-ttu-id="35c9f-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="35c9f-2464">internet protocol</span></span>
- <span data-ttu-id="35c9f-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="35c9f-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="35c9f-2466">国际分类的 Diseases （ICD-10 CM）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2467">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2467">Format</span></span>

<span data-ttu-id="35c9f-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="35c9f-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2469">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2469">Pattern</span></span>

<span data-ttu-id="35c9f-2470">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2471">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2471">Checksum</span></span>

<span data-ttu-id="35c9f-2472">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2473">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2473">Definition</span></span>

<span data-ttu-id="35c9f-2474">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2475">找到 Dictionary_icd_10_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="35c9f-2476">找到 Dictionary_icd_10_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="35c9f-2477">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2478">找到 Dictionary_icd_10_ 更新的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="35c9f-2479">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2479">Keywords</span></span>

<span data-ttu-id="35c9f-2480">Dictionary_icd_10_updated 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="35c9f-2481">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="35c9f-2482">Dictionary_icd_10_codes 关键字词典中的任何术语，基于[国际分类 Diseases，第10次修订，临床修改（icd-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="35c9f-2483">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="35c9f-2484">国际分类的 Diseases （ICD-9-CM）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2485">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2485">Format</span></span>

<span data-ttu-id="35c9f-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="35c9f-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2487">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2487">Pattern</span></span>

<span data-ttu-id="35c9f-2488">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2489">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2489">Checksum</span></span>

<span data-ttu-id="35c9f-2490">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2491">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2491">Definition</span></span>

<span data-ttu-id="35c9f-2492">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2493">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="35c9f-2494">找到 Dictionary_icd_9_codes 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="35c9f-2495">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2496">找到 Dictionary_icd_9_updated 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2497">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2497">Keywords</span></span>

<span data-ttu-id="35c9f-2498">Dictionary_icd_9_updated 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="35c9f-2499">此类型仅查找术语，而不是保险代码。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="35c9f-2500">Dictionary_icd_9_codes 关键字词典中的任何术语，基于[国际分类的 Diseases，第九个修订，临床修改（icd-9 CM）](https://go.microsoft.com/fwlink/?linkid=852605)。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="35c9f-2501">此类型仅查找保险业代码，而不是说明。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="35c9f-2502">爱尔兰个人公共服务 (PPS) 号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2503">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2503">Format</span></span>

<span data-ttu-id="35c9f-2504">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="35c9f-2505">七位数字后跟 1-2  个字母 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="35c9f-2506">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="35c9f-2507">七位数字后跟两个字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2508">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2508">Pattern</span></span>

<span data-ttu-id="35c9f-2509">旧格式（到 31 Dec 2012）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="35c9f-2510">七个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2510">Seven digits</span></span> 
- <span data-ttu-id="35c9f-2511">1-2 个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="35c9f-2512">新格式（2013年1月1日和之后）：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="35c9f-2513">七个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2513">Seven digits</span></span> 
- <span data-ttu-id="35c9f-2514">一个字母（不区分大小写），是字母校验位 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="35c9f-2515">字母“A”或“H”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2516">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2516">Checksum</span></span>

<span data-ttu-id="35c9f-2517">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2518">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2518">Definition</span></span>

<span data-ttu-id="35c9f-2519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2520">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2521">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2521">One of the following is true:</span></span>
    - <span data-ttu-id="35c9f-2522">找到 Keyword_ireland_pps 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="35c9f-2523">函数 Func_eu_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="35c9f-2524">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2524">The checksum passes.</span></span>

<span data-ttu-id="35c9f-2525">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2526">函数 Func_ireland_pps 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2527">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2528">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="35c9f-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="35c9f-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="35c9f-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="35c9f-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2531">PPS Number</span></span> 
- <span data-ttu-id="35c9f-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="35c9f-2532">PPS Num</span></span> 
- <span data-ttu-id="35c9f-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2533">PPS No.</span></span> 
- <span data-ttu-id="35c9f-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2534">PPS #</span></span> 
- <span data-ttu-id="35c9f-2535">.PPS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2535">PPS#</span></span> 
- <span data-ttu-id="35c9f-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-2536">PPSN</span></span> 
- <span data-ttu-id="35c9f-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2537">Public Services Card</span></span> 
- <span data-ttu-id="35c9f-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="35c9f-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="35c9f-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2539">Uimh.</span></span> <span data-ttu-id="35c9f-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="35c9f-2540">PSP</span></span> 
- <span data-ttu-id="35c9f-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="35c9f-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="35c9f-2542">以色列银行帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2543">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2543">Format</span></span>

<span data-ttu-id="35c9f-2544">13 位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2545">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2545">Pattern</span></span>

<span data-ttu-id="35c9f-2546">格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2546">Formatted:</span></span>
- <span data-ttu-id="35c9f-2547">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2547">Two digits</span></span> 
- <span data-ttu-id="35c9f-2548">破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2548">A dash</span></span> 
- <span data-ttu-id="35c9f-2549">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2549">Three digits</span></span> 
- <span data-ttu-id="35c9f-2550">破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2550">A dash</span></span> 
- <span data-ttu-id="35c9f-2551">八位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2551">Eight digits</span></span>

<span data-ttu-id="35c9f-2552">纯</span><span class="sxs-lookup"><span data-stu-id="35c9f-2552">Unformatted:</span></span>
- <span data-ttu-id="35c9f-2553">	13 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2554">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2554">Checksum</span></span>

<span data-ttu-id="35c9f-2555">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2556">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2556">Definition</span></span>

<span data-ttu-id="35c9f-2557">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2558">正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2559">找到 Keyword_israel_bank_account_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2560">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="35c9f-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="35c9f-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2562">Bank Account Number</span></span> 
- <span data-ttu-id="35c9f-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2563">Bank Account</span></span> 
- <span data-ttu-id="35c9f-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2564">Account Number</span></span> 
- <span data-ttu-id="35c9f-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="35c9f-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="35c9f-2566">以色列国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2567">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2567">Format</span></span>

<span data-ttu-id="35c9f-2568">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2569">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2569">Pattern</span></span>

<span data-ttu-id="35c9f-2570">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2571">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2571">Checksum</span></span>

<span data-ttu-id="35c9f-2572">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2573">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2573">Definition</span></span>

<span data-ttu-id="35c9f-2574">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2575">函数 Func_israeli_national_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2576">找到 Keyword_Israel_National_ID 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="35c9f-2577">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2578">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="35c9f-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="35c9f-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="35c9f-2580">מספר זהות</span></span> 
- <span data-ttu-id="35c9f-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="35c9f-2582">意大利驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2583">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2583">Format</span></span>

<span data-ttu-id="35c9f-2584">10 个字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2585">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2585">Pattern</span></span>

- <span data-ttu-id="35c9f-2586">10 个字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="35c9f-2587">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2588">字母“A”或者“V”（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-2589">七个字母（不区分大小写）、数字或下划线字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="35c9f-2590">一个字母（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2591">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2591">Checksum</span></span>

<span data-ttu-id="35c9f-2592">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2593">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2593">Definition</span></span>

<span data-ttu-id="35c9f-2594">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2595">正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2596">找到 Keyword_italy_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2597">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="35c9f-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="35c9f-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="35c9f-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="35c9f-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="35c9f-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="35c9f-2601">日本银行帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2602">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2602">Format</span></span>

<span data-ttu-id="35c9f-2603">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2604">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2604">Pattern</span></span>

<span data-ttu-id="35c9f-2605">银行帐号：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2605">Bank account number:</span></span>
- <span data-ttu-id="35c9f-2606">七个或八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2606">Seven or eight digits</span></span>
- <span data-ttu-id="35c9f-2607">银行帐户分支代码：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2607">Bank account branch code:</span></span>
- <span data-ttu-id="35c9f-2608">四位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2608">Four digits</span></span> 
- <span data-ttu-id="35c9f-2609">空格或破折号（可选）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="35c9f-2610">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2610">Three digits</span></span>

<span data-ttu-id="35c9f-2611">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2611">Checksum</span></span>

<span data-ttu-id="35c9f-2612">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2613">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2613">Definition</span></span>

<span data-ttu-id="35c9f-2614">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2615">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2616">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="35c9f-2617">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2617">One of the following is true:</span></span>
- <span data-ttu-id="35c9f-2618">函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2619">找到 Keyword_jp_bank_branch_code 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="35c9f-2620">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2621">函数 Func_jp_bank_account 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2622">找到 Keyword_jp_bank_account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2623">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="35c9f-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="35c9f-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2625">Checking Account Number</span></span> 
- <span data-ttu-id="35c9f-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2626">Checking Account</span></span> 
- <span data-ttu-id="35c9f-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2627">Checking Account #</span></span> 
- <span data-ttu-id="35c9f-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="35c9f-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2629">Checking Acct #</span></span> 
- <span data-ttu-id="35c9f-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="35c9f-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2631">Checking Account No.</span></span> 
- <span data-ttu-id="35c9f-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2632">Bank Account Number</span></span> 
- <span data-ttu-id="35c9f-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2633">Bank Account</span></span> 
- <span data-ttu-id="35c9f-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2634">Bank Account #</span></span> 
- <span data-ttu-id="35c9f-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="35c9f-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2636">Bank Acct #</span></span> 
- <span data-ttu-id="35c9f-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="35c9f-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2638">Bank Account No.</span></span> 
- <span data-ttu-id="35c9f-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2639">Savings Account Number</span></span> 
- <span data-ttu-id="35c9f-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2640">Savings Account</span></span> 
- <span data-ttu-id="35c9f-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2641">Savings Account #</span></span> 
- <span data-ttu-id="35c9f-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="35c9f-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2643">Savings Acct #</span></span> 
- <span data-ttu-id="35c9f-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="35c9f-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2645">Savings Account No.</span></span> 
- <span data-ttu-id="35c9f-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2646">Debit Account Number</span></span> 
- <span data-ttu-id="35c9f-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-2647">Debit Account</span></span> 
- <span data-ttu-id="35c9f-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2648">Debit Account #</span></span> 
- <span data-ttu-id="35c9f-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="35c9f-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-2650">Debit Acct #</span></span> 
- <span data-ttu-id="35c9f-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="35c9f-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2652">Debit Account No.</span></span> 
- <span data-ttu-id="35c9f-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="35c9f-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="35c9f-2654">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="35c9f-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="35c9f-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="35c9f-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="35c9f-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="35c9f-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="35c9f-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="35c9f-2657">口座番号の確認</span></span> 
- <span data-ttu-id="35c9f-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2658">銀行口座番号</span></span> 
- <span data-ttu-id="35c9f-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="35c9f-2659">銀行口座</span></span> 
- <span data-ttu-id="35c9f-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2660">銀行口座＃</span></span> 
- <span data-ttu-id="35c9f-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="35c9f-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="35c9f-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="35c9f-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="35c9f-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2664">銀行口座番号</span></span>
- <span data-ttu-id="35c9f-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="35c9f-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="35c9f-2666">預金口座</span></span> 
- <span data-ttu-id="35c9f-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="35c9f-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="35c9f-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="35c9f-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="35c9f-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="35c9f-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="35c9f-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="35c9f-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2673">口座番号</span></span> 
- <span data-ttu-id="35c9f-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2674">口座番号＃</span></span> 
- <span data-ttu-id="35c9f-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="35c9f-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="35c9f-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="35c9f-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="35c9f-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="35c9f-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="35c9f-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="35c9f-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="35c9f-2681">日本驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2682">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2682">Format</span></span>

<span data-ttu-id="35c9f-2683">12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2684">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2684">Pattern</span></span>

<span data-ttu-id="35c9f-2685">12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2686">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2686">Checksum</span></span>

<span data-ttu-id="35c9f-2687">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2688">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2688">Definition</span></span>

<span data-ttu-id="35c9f-2689">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2690">函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2691">找到 Keyword_jp_drivers_license_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2692">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="35c9f-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="35c9f-2694">通讯#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2694">dl#</span></span> 
- <span data-ttu-id="35c9f-2695">通讯</span><span class="sxs-lookup"><span data-stu-id="35c9f-2695">DL＃</span></span> 
- <span data-ttu-id="35c9f-2696">dls#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2696">dls#</span></span> 
- <span data-ttu-id="35c9f-2697">DLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-2697">DLS＃</span></span> 
- <span data-ttu-id="35c9f-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="35c9f-2698">driver license</span></span> 
- <span data-ttu-id="35c9f-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2699">driver licenses</span></span> 
- <span data-ttu-id="35c9f-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="35c9f-2700">drivers license</span></span> 
- <span data-ttu-id="35c9f-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="35c9f-2701">driver's license</span></span> 
- <span data-ttu-id="35c9f-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2702">drivers licenses</span></span> 
- <span data-ttu-id="35c9f-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-2703">driver's licenses</span></span> 
- <span data-ttu-id="35c9f-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-2704">driving licence</span></span> 
- <span data-ttu-id="35c9f-2705">.lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2705">lic#</span></span> 
- <span data-ttu-id="35c9f-2706">.LIC</span><span class="sxs-lookup"><span data-stu-id="35c9f-2706">LIC＃</span></span> 
- <span data-ttu-id="35c9f-2707">driver'lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2707">lics#</span></span> 
- <span data-ttu-id="35c9f-2708">state id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2708">state id</span></span> 
- <span data-ttu-id="35c9f-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="35c9f-2709">state identification</span></span> 
- <span data-ttu-id="35c9f-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2710">state identification number</span></span> 
- <span data-ttu-id="35c9f-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2711">低所得国＃</span></span> 
- <span data-ttu-id="35c9f-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2712">免許証</span></span> 
- <span data-ttu-id="35c9f-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2713">状態ID</span></span>
- <span data-ttu-id="35c9f-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="35c9f-2714">状態の識別</span></span> 
- <span data-ttu-id="35c9f-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2715">状態の識別番号</span></span> 
- <span data-ttu-id="35c9f-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="35c9f-2716">運転免許</span></span> 
- <span data-ttu-id="35c9f-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="35c9f-2717">運転免許証</span></span> 
- <span data-ttu-id="35c9f-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="35c9f-2719">日本护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2720">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2720">Format</span></span>

<span data-ttu-id="35c9f-2721">两个字母后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2722">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2722">Pattern</span></span>

<span data-ttu-id="35c9f-2723">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2724">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2724">Checksum</span></span>

<span data-ttu-id="35c9f-2725">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2726">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2726">Definition</span></span>

<span data-ttu-id="35c9f-2727">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2728">函数 Func_jp_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2729">找到 Keyword_jp_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2730">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="35c9f-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="35c9f-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-2732">パスポート</span></span> 
- <span data-ttu-id="35c9f-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2733">パスポート番号</span></span> 
- <span data-ttu-id="35c9f-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-2734">パスポートのNum</span></span> 
- <span data-ttu-id="35c9f-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="35c9f-2736">日本居民登记号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2737">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2737">Format</span></span>

<span data-ttu-id="35c9f-2738">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2739">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2739">Pattern</span></span>

<span data-ttu-id="35c9f-2740">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2741">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2741">Checksum</span></span>

<span data-ttu-id="35c9f-2742">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2743">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2743">Definition</span></span>

<span data-ttu-id="35c9f-2744">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2745">函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2746">找到 Keyword_jp_resident_registration_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2747">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="35c9f-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="35c9f-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2749">Resident Registration Number</span></span>
- <span data-ttu-id="35c9f-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2750">Resident Register Number</span></span> 
- <span data-ttu-id="35c9f-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="35c9f-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="35c9f-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2753">Resident Register No.</span></span> 
- <span data-ttu-id="35c9f-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="35c9f-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="35c9f-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="35c9f-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="35c9f-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="35c9f-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="35c9f-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="35c9f-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="35c9f-2760">日本社会保险号码 (SIN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2761">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2761">Format</span></span>

<span data-ttu-id="35c9f-2762">7-12 个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2763">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2763">Pattern</span></span>

<span data-ttu-id="35c9f-2764">7-12 位数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2764">7-12 digits:</span></span>
- <span data-ttu-id="35c9f-2765">四位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2765">Four digits</span></span> 
- <span data-ttu-id="35c9f-2766">一个连字符（可选）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="35c9f-2767">六位数字或</span><span class="sxs-lookup"><span data-stu-id="35c9f-2767">Six digits OR</span></span>
- <span data-ttu-id="35c9f-2768">7-12 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2769">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2769">Checksum</span></span>

<span data-ttu-id="35c9f-2770">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2771">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2771">Definition</span></span>

<span data-ttu-id="35c9f-2772">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2773">函数 Func_jp_sin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2774">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="35c9f-2775">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2776">函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2777">找到 Keyword_jp_sin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2778">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="35c9f-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="35c9f-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="35c9f-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="35c9f-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="35c9f-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="35c9f-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="35c9f-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="35c9f-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="35c9f-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="35c9f-2785">日本住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2786">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2786">Format</span></span>

<span data-ttu-id="35c9f-2787">12个字母和数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2788">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2788">Pattern</span></span>

<span data-ttu-id="35c9f-2789">12个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2789">12 letters and digits:</span></span>
- <span data-ttu-id="35c9f-2790">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="35c9f-2791">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2791">Eight digits</span></span> 
- <span data-ttu-id="35c9f-2792">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2793">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2793">Checksum</span></span>

<span data-ttu-id="35c9f-2794">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2795">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2795">Definition</span></span>

<span data-ttu-id="35c9f-2796">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2797">正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2798">找到 Keyword_jp_residence_card_number 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2799">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="35c9f-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="35c9f-2801">住宅电话卡号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2801">Residence card number</span></span>
- <span data-ttu-id="35c9f-2802">住宅卡编号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2802">Residence card no</span></span>
- <span data-ttu-id="35c9f-2803">住宅卡片#</span><span class="sxs-lookup"><span data-stu-id="35c9f-2803">Residence card #</span></span>
- <span data-ttu-id="35c9f-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="35c9f-2805">马拉西亚身份证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2806">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2806">Format</span></span>

<span data-ttu-id="35c9f-2807">12 个数字（包含可选连字符）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2808">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2808">Pattern</span></span>

<span data-ttu-id="35c9f-2809">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2809">12 digits:</span></span>
- <span data-ttu-id="35c9f-2810">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-2811">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2811">A dash (optional)</span></span> 
- <span data-ttu-id="35c9f-2812">两个字母的出生地代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="35c9f-2813">一个短划线（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2813">A dash (optional)</span></span> 
- <span data-ttu-id="35c9f-2814">三个随机数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2814">Three random digits</span></span> 
- <span data-ttu-id="35c9f-2815">一位性别代码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2816">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2816">Checksum</span></span>

<span data-ttu-id="35c9f-2817">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2818">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2818">Definition</span></span>

<span data-ttu-id="35c9f-2819">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2820">正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2821">找到 Keyword_malaysia_id_card_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2822">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="35c9f-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="35c9f-2824">数字应用程序卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-2824">digital application card</span></span>
- <span data-ttu-id="35c9f-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="35c9f-2825">i/c</span></span>
- <span data-ttu-id="35c9f-2826">i/c 否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2826">i/c no</span></span>
- <span data-ttu-id="35c9f-2827">ic</span><span class="sxs-lookup"><span data-stu-id="35c9f-2827">ic</span></span>
- <span data-ttu-id="35c9f-2828">内部公司编号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2828">ic no</span></span>
- <span data-ttu-id="35c9f-2829">id card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2829">id card</span></span>
- <span data-ttu-id="35c9f-2830">标识卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-2830">identification Card</span></span>
- <span data-ttu-id="35c9f-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2831">identity card</span></span>
- <span data-ttu-id="35c9f-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="35c9f-2832">k/p</span></span>
- <span data-ttu-id="35c9f-2833">k/p no</span><span class="sxs-lookup"><span data-stu-id="35c9f-2833">k/p no</span></span>
- <span data-ttu-id="35c9f-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="35c9f-2834">kad akuan diri</span></span>
- <span data-ttu-id="35c9f-2835">kad aplikasi 数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="35c9f-2836">kad pengenalan 马来西亚</span><span class="sxs-lookup"><span data-stu-id="35c9f-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="35c9f-2837">kp</span><span class="sxs-lookup"><span data-stu-id="35c9f-2837">kp</span></span>
- <span data-ttu-id="35c9f-2838">kp no</span><span class="sxs-lookup"><span data-stu-id="35c9f-2838">kp no</span></span>
- <span data-ttu-id="35c9f-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="35c9f-2839">mykad</span></span>
- <span data-ttu-id="35c9f-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="35c9f-2840">mykas</span></span>
- <span data-ttu-id="35c9f-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="35c9f-2841">mykid</span></span>
- <span data-ttu-id="35c9f-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="35c9f-2842">mypr</span></span>
- <span data-ttu-id="35c9f-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="35c9f-2843">mytentera</span></span>
- <span data-ttu-id="35c9f-2844">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="35c9f-2844">malaysia identity card</span></span>
- <span data-ttu-id="35c9f-2845">马来西亚身份卡片</span><span class="sxs-lookup"><span data-stu-id="35c9f-2845">malaysian identity card</span></span>
- <span data-ttu-id="35c9f-2846">nric</span><span class="sxs-lookup"><span data-stu-id="35c9f-2846">nric</span></span>
- <span data-ttu-id="35c9f-2847">个人标识卡</span><span class="sxs-lookup"><span data-stu-id="35c9f-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="35c9f-2848">荷兰公民服务 (BSN) 号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2849">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2849">Format</span></span>

<span data-ttu-id="35c9f-2850">8-9 个数字（包含可选空格）</span><span class="sxs-lookup"><span data-stu-id="35c9f-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2851">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2851">Pattern</span></span>

<span data-ttu-id="35c9f-2852">8-9 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2852">8-9 digits:</span></span>
- <span data-ttu-id="35c9f-2853">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2853">Three digits</span></span> 
- <span data-ttu-id="35c9f-2854">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2854">A space (optional)</span></span> 
- <span data-ttu-id="35c9f-2855">三个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2855">Three digits</span></span> 
- <span data-ttu-id="35c9f-2856">一个空格（可选） </span><span class="sxs-lookup"><span data-stu-id="35c9f-2856">A space (optional)</span></span> 
- <span data-ttu-id="35c9f-2857">2-3 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2858">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2858">Checksum</span></span>

<span data-ttu-id="35c9f-2859">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2860">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2860">Definition</span></span>

<span data-ttu-id="35c9f-2861">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2862">函数 Func_netherlands_bsn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2863">找到 Keyword_netherlands_bsn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="35c9f-2864">函数 Func_eu_date2 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="35c9f-2865">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2866">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="35c9f-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="35c9f-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="35c9f-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2868">Citizen service number</span></span> 
- <span data-ttu-id="35c9f-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-2869">BSN</span></span> 
- <span data-ttu-id="35c9f-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="35c9f-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2871">Sofinummer</span></span> 
- <span data-ttu-id="35c9f-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="35c9f-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="35c9f-2874">新西兰卫生部号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2875">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2875">Format</span></span>

<span data-ttu-id="35c9f-2876">三个字母、一个空格（可选）以及四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2877">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2877">Pattern</span></span>

<span data-ttu-id="35c9f-2878">三个字母（不区分大小写）一个空格（可选）四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2879">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2879">Checksum</span></span>

<span data-ttu-id="35c9f-2880">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2881">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2881">Definition</span></span>

<span data-ttu-id="35c9f-2882">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2883">函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2884">找到 Keyword_nz_terms 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="35c9f-2885">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2885">The checksum passes.</span></span>

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

<span data-ttu-id="35c9f-2886">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2886">Keywords</span></span>

<span data-ttu-id="35c9f-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="35c9f-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="35c9f-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="35c9f-2888">NHI</span></span> 
- <span data-ttu-id="35c9f-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="35c9f-2889">New Zealand</span></span> 
- <span data-ttu-id="35c9f-2890">运行状况</span><span class="sxs-lookup"><span data-stu-id="35c9f-2890">Health</span></span> 
- <span data-ttu-id="35c9f-2891">治疗</span><span class="sxs-lookup"><span data-stu-id="35c9f-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="35c9f-2892">挪威身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2893">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2893">Format</span></span>

<span data-ttu-id="35c9f-2894">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2895">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2895">Pattern</span></span>

<span data-ttu-id="35c9f-2896">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2896">11 digits:</span></span>
- <span data-ttu-id="35c9f-2897">六个数字，采用  DDMMYY 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-2898">三位个人号码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="35c9f-2899">两个校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2900">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2900">Checksum</span></span>

<span data-ttu-id="35c9f-2901">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2902">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2902">Definition</span></span>

<span data-ttu-id="35c9f-2903">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2904">函数 Func_norway_id_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2905">找到 Keyword_norway_id_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="35c9f-2906">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2906">The checksum passes.</span></span>
- <span data-ttu-id="35c9f-2907">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2908">函数 Func_norway_id_numbe 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2909">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2910">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="35c9f-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="35c9f-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2912">Personal identification number</span></span>
- <span data-ttu-id="35c9f-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="35c9f-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2914">ID Number</span></span>
- <span data-ttu-id="35c9f-2915">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2915">Identification</span></span>
- <span data-ttu-id="35c9f-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2916">Personnummer</span></span>
- <span data-ttu-id="35c9f-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="35c9f-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="35c9f-2918">菲律宾统一多用途身份证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2919">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2919">Format</span></span>

<span data-ttu-id="35c9f-2920">12 个数字，通过连字符分隔 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2921">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2921">Pattern</span></span>

<span data-ttu-id="35c9f-2922">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2922">12 digits:</span></span>
- <span data-ttu-id="35c9f-2923">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2923">Four digits</span></span> 
- <span data-ttu-id="35c9f-2924">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2924">A hyphen</span></span> 
- <span data-ttu-id="35c9f-2925">七个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2925">Seven digits</span></span> 
- <span data-ttu-id="35c9f-2926">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-2926">A hyphen</span></span> 
- <span data-ttu-id="35c9f-2927">一个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2928">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2928">Checksum</span></span>

<span data-ttu-id="35c9f-2929">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2930">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2930">Definition</span></span>

<span data-ttu-id="35c9f-2931">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2932">正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2933">找到 Keyword_philippines_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2934">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="35c9f-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="35c9f-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="35c9f-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2937">UMID</span></span> 
- <span data-ttu-id="35c9f-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-2938">Identity Card</span></span> 
- <span data-ttu-id="35c9f-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="35c9f-2940">波兰身份证</span><span class="sxs-lookup"><span data-stu-id="35c9f-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2941">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2941">Format</span></span>

<span data-ttu-id="35c9f-2942">三个字母和六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2943">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2943">Pattern</span></span>

<span data-ttu-id="35c9f-2944">三个字母（不区分大小写）后跟六个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2945">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2945">Checksum</span></span>

<span data-ttu-id="35c9f-2946">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2947">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2947">Definition</span></span>

<span data-ttu-id="35c9f-2948">DLP 策略75% 确信在300个字符的邻近度内检测到此类型的敏感信息：函数 Func_polish_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="35c9f-2949">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="35c9f-2950">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2951">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="35c9f-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="35c9f-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="35c9f-2953">Dowód osobisty</span></span>
- <span data-ttu-id="35c9f-2954">器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="35c9f-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="35c9f-2955">Nazwa i 器 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="35c9f-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="35c9f-2956">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="35c9f-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="35c9f-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="35c9f-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="35c9f-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="35c9f-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="35c9f-2959">dow.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2959">dow.</span></span> <span data-ttu-id="35c9f-2960">os.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="35c9f-2961">波兰国家/地区 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="35c9f-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2962">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2962">Format</span></span>

<span data-ttu-id="35c9f-2963">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2964">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2964">Pattern</span></span>

<span data-ttu-id="35c9f-2965">11 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2966">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2966">Checksum</span></span>

<span data-ttu-id="35c9f-2967">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2968">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2968">Definition</span></span>

<span data-ttu-id="35c9f-2969">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2970">函数 Func_pesel_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2971">找到 Keyword_pesel_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="35c9f-2972">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-2973">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="35c9f-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="35c9f-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="35c9f-2975">Nr PESEL</span></span>
- <span data-ttu-id="35c9f-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="35c9f-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="35c9f-2977">波兰护照</span><span class="sxs-lookup"><span data-stu-id="35c9f-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2978">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2978">Format</span></span>

<span data-ttu-id="35c9f-2979">两个字母和七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2980">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2980">Pattern</span></span>

<span data-ttu-id="35c9f-2981">两个字母（不区分大小写）后跟七个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-2982">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-2982">Checksum</span></span>

<span data-ttu-id="35c9f-2983">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-2984">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-2984">Definition</span></span>

<span data-ttu-id="35c9f-2985">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-2986">函数 Func_polish_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-2987">找到 Keyword_polish_national_id_passport_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="35c9f-2988">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-2989">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="35c9f-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="35c9f-2991">器 paszportu</span><span class="sxs-lookup"><span data-stu-id="35c9f-2991">Numer paszportu</span></span>
- <span data-ttu-id="35c9f-2992">Führerschein-nr.</span><span class="sxs-lookup"><span data-stu-id="35c9f-2992">Nr.</span></span> <span data-ttu-id="35c9f-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="35c9f-2993">Paszportu</span></span>
- <span data-ttu-id="35c9f-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="35c9f-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="35c9f-2995">葡萄牙公民身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-2996">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-2996">Format</span></span>

<span data-ttu-id="35c9f-2997">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-2998">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-2998">Pattern</span></span>

<span data-ttu-id="35c9f-2999">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3000">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3000">Checksum</span></span>

<span data-ttu-id="35c9f-3001">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3002">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3002">Definition</span></span>

<span data-ttu-id="35c9f-3003">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3004">正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3005">找到 Keyword_portugal_citizen_card 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3006">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="35c9f-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="35c9f-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3008">Citizen Card</span></span>
- <span data-ttu-id="35c9f-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3009">National ID Card</span></span>
- <span data-ttu-id="35c9f-3010">CC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3010">CC</span></span>
- <span data-ttu-id="35c9f-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="35c9f-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="35c9f-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="35c9f-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="35c9f-3013">沙特阿拉伯国家 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3014">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3014">Format</span></span>

<span data-ttu-id="35c9f-3015">10 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3016">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3016">Pattern</span></span>

<span data-ttu-id="35c9f-3017">10 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3018">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3018">Checksum</span></span>

<span data-ttu-id="35c9f-3019">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3020">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3020">Definition</span></span>

<span data-ttu-id="35c9f-3021">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3022">正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3023">找到 Keyword_saudi_arabia_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3024">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="35c9f-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="35c9f-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3026">Identification Card</span></span> 
- <span data-ttu-id="35c9f-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3027">I card number</span></span> 
- <span data-ttu-id="35c9f-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3028">ID number</span></span> 
- <span data-ttu-id="35c9f-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="35c9f-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="35c9f-3030">新加坡国家登记身份证 (NRIC) 号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3031">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3031">Format</span></span>

<span data-ttu-id="35c9f-3032">九个字母和数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3033">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3033">Pattern</span></span>

- <span data-ttu-id="35c9f-3034">九个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="35c9f-3035">字母“F”、“G”、“S”或“T”（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-3036">七个数字 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3036">Seven digits</span></span> 
- <span data-ttu-id="35c9f-3037">一个字母校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3038">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3038">Checksum</span></span>

<span data-ttu-id="35c9f-3039">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3040">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3040">Definition</span></span>

<span data-ttu-id="35c9f-3041">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3042">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3043">找到 Keyword_singapore_nric 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="35c9f-3044">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3044">The checksum passes.</span></span>

<span data-ttu-id="35c9f-3045">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3046">正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3047">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3048">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="35c9f-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="35c9f-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="35c9f-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="35c9f-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3051">Identity Card Number</span></span> 
- <span data-ttu-id="35c9f-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3052">NRIC</span></span> 
- <span data-ttu-id="35c9f-3053">IC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3053">IC</span></span> 
- <span data-ttu-id="35c9f-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="35c9f-3055">FIN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3055">FIN</span></span> 
- <span data-ttu-id="35c9f-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="35c9f-3056">身份证</span></span> 
- <span data-ttu-id="35c9f-3057">證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="35c9f-3058">南非身份证号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3059">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3059">Format</span></span>

<span data-ttu-id="35c9f-3060">13 个数字（可能包含空格）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3061">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3061">Pattern</span></span>

<span data-ttu-id="35c9f-3062">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3062">13 digits:</span></span>
- <span data-ttu-id="35c9f-3063">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-3064">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3064">Four digits</span></span> 
- <span data-ttu-id="35c9f-3065">一位公民指示码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="35c9f-3066">数字“8”或“9” </span><span class="sxs-lookup"><span data-stu-id="35c9f-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="35c9f-3067">一个数字，是校验位</span><span class="sxs-lookup"><span data-stu-id="35c9f-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3068">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3068">Checksum</span></span>

<span data-ttu-id="35c9f-3069">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3070">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3070">Definition</span></span>

<span data-ttu-id="35c9f-3071">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3072">函数 Func_south_africa_identification_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3073">找到 Keyword_south_africa_identification_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="35c9f-3074">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3075">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="35c9f-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="35c9f-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3077">Identity card</span></span>
- <span data-ttu-id="35c9f-3078">ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3078">ID</span></span>
- <span data-ttu-id="35c9f-3079">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="35c9f-3080">韩国居民注册号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3081">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3081">Format</span></span>

<span data-ttu-id="35c9f-3082">13 个数字（包含连字符）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3083">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3083">Pattern</span></span>

<span data-ttu-id="35c9f-3084">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3084">13 digits:</span></span>
- <span data-ttu-id="35c9f-3085">六个数字，采用  YYMMDD 格式，代表出生日期 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="35c9f-3086">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3086">A hyphen</span></span> 
- <span data-ttu-id="35c9f-3087">一个数字，由世纪和性别 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="35c9f-3088">四位数字的出生地区代码 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="35c9f-3089">一个数字，用于区分前面数字均相同的人 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="35c9f-3090">一个校验位。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3091">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3091">Checksum</span></span>

<span data-ttu-id="35c9f-3092">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3093">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3093">Definition</span></span>

<span data-ttu-id="35c9f-3094">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3095">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3096">找到 Keyword_south_korea_resident_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="35c9f-3097">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3097">The checksum passes.</span></span>

<span data-ttu-id="35c9f-3098">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3099">函数 Func_south_korea_resident_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3100">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3101">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="35c9f-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="35c9f-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3103">National ID card</span></span> 
- <span data-ttu-id="35c9f-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="35c9f-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="35c9f-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="35c9f-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3106">RRN</span></span> 
- <span data-ttu-id="35c9f-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="35c9f-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="35c9f-3108">西班牙社会保险号码 (SSN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3109">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3109">Format</span></span>

<span data-ttu-id="35c9f-3110">11-12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3111">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3111">Pattern</span></span>

<span data-ttu-id="35c9f-3112">11-12 位数：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3112">11-12 digits:</span></span>
- <span data-ttu-id="35c9f-3113">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3113">Two digits</span></span> 
- <span data-ttu-id="35c9f-3114">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="35c9f-3115">7-8 位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3115">7-8 digits</span></span> 
- <span data-ttu-id="35c9f-3116">正斜杠（可选）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="35c9f-3117">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3118">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3118">Checksum</span></span>

<span data-ttu-id="35c9f-3119">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3120">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3120">Definition</span></span>

<span data-ttu-id="35c9f-3121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3122">函数 Func_spanish_social_security_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3123">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3124">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3124">Keywords</span></span>

<span data-ttu-id="35c9f-3125">无</span><span class="sxs-lookup"><span data-stu-id="35c9f-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="35c9f-3126">SQL Server 连接字符串</span><span class="sxs-lookup"><span data-stu-id="35c9f-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3127">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3127">Format</span></span>

<span data-ttu-id="35c9f-3128">字符串 "User Id"、"User ID"、"uid" 或 "UserId"，后跟下面模式中所述的字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3129">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3129">Pattern</span></span>

- <span data-ttu-id="35c9f-3130">字符串 "User Id"、"User ID"、"uid" 或 "UserId"</span><span class="sxs-lookup"><span data-stu-id="35c9f-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="35c9f-3131">介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="35c9f-3132">字符串 "Password" 或 "pwd"，其中 "pwd" 不以小写字母开头</span><span class="sxs-lookup"><span data-stu-id="35c9f-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="35c9f-3133">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3133">An equal sign (=)</span></span>
- <span data-ttu-id="35c9f-3134">任何不是美元符号（$）、百分比符号（%）、大于号（>）、符号（@）、引号（"）、分号（;)、左大括号（[）或左中括号（{）的字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="35c9f-3135">7-128 个字符的任意组合，不是分号（;)、正斜杠（/）或引号（"）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="35c9f-3136">一个分号（;)或引号（"）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3137">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3137">Checksum</span></span>

<span data-ttu-id="35c9f-3138">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3139">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3139">Definition</span></span>

<span data-ttu-id="35c9f-3140">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3141">正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3142">找**不**到 CEP_GlobalFilter 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="35c9f-3143">正则表达式**CEP_PasswordPlaceHolder 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3144">正则表达式**CEP_CommonExampleKeywords 不会找到与**该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3145">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="35c9f-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="35c9f-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="35c9f-3147">部分密码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3147">some-password</span></span>
- <span data-ttu-id="35c9f-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="35c9f-3148">somepassword</span></span>
- <span data-ttu-id="35c9f-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="35c9f-3149">secretPassword</span></span>
- <span data-ttu-id="35c9f-3150">采用</span><span class="sxs-lookup"><span data-stu-id="35c9f-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="35c9f-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="35c9f-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="35c9f-3152">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-3153">密码或密码后跟0-2 个空格、一个等号（=）、0-2 个空格和一个星号（\*）--或--</span><span class="sxs-lookup"><span data-stu-id="35c9f-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="35c9f-3154">密码或密码后跟：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="35c9f-3155">等号（=）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="35c9f-3156">小于号（<）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="35c9f-3157">1-200 个字符的任意组合，这些字符为大写或小写字母、数字、星号（\*）、连字符（-）、下划线（_）或空白字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="35c9f-3158">大于号（>）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="35c9f-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="35c9f-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="35c9f-3160">（请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="35c9f-3161">尚未</span><span class="sxs-lookup"><span data-stu-id="35c9f-3161">contoso</span></span>
- <span data-ttu-id="35c9f-3162">送交</span><span class="sxs-lookup"><span data-stu-id="35c9f-3162">fabrikam</span></span>
- <span data-ttu-id="35c9f-3163">罗斯</span><span class="sxs-lookup"><span data-stu-id="35c9f-3163">northwind</span></span>
- <span data-ttu-id="35c9f-3164">沙盒</span><span class="sxs-lookup"><span data-stu-id="35c9f-3164">sandbox</span></span>
- <span data-ttu-id="35c9f-3165">onebox</span><span class="sxs-lookup"><span data-stu-id="35c9f-3165">onebox</span></span>
- <span data-ttu-id="35c9f-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="35c9f-3166">localhost</span></span>
- <span data-ttu-id="35c9f-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="35c9f-3167">127.0.0.1</span></span>
- <span data-ttu-id="35c9f-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-3169">com</span><span class="sxs-lookup"><span data-stu-id="35c9f-3169">com</span></span>
- <span data-ttu-id="35c9f-3170">s-int。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="35c9f-3171">netmeeting</span><span class="sxs-lookup"><span data-stu-id="35c9f-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="35c9f-3172">瑞典国家 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3173">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3173">Format</span></span>

<span data-ttu-id="35c9f-3174">10 个或 12 个数字和一个可选分隔符</span><span class="sxs-lookup"><span data-stu-id="35c9f-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3175">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3175">Pattern</span></span>

<span data-ttu-id="35c9f-3176">10 或 12 位数字和可选的分隔符：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="35c9f-3177">2-4 位数字（可选）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="35c9f-3178">采用日期格式 YYMMDD 的六位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="35c9f-3179">“-”或“+”（可选）的分隔符，加</span><span class="sxs-lookup"><span data-stu-id="35c9f-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="35c9f-3180">四个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3181">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3181">Checksum</span></span>

<span data-ttu-id="35c9f-3182">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3183">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3183">Definition</span></span>

<span data-ttu-id="35c9f-3184">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3185">函数 Func_swedish_national_identifier 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3186">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3187">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3187">Keywords</span></span>

<span data-ttu-id="35c9f-3188">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="35c9f-3189">瑞典护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3190">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3190">Format</span></span>

<span data-ttu-id="35c9f-3191">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3192">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3192">Pattern</span></span>

<span data-ttu-id="35c9f-3193">八个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3194">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3194">Checksum</span></span>

<span data-ttu-id="35c9f-3195">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3196">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3196">Definition</span></span>

<span data-ttu-id="35c9f-3197">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3198">正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3199">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3199">One of the following is true:</span></span>
    - <span data-ttu-id="35c9f-3200">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="35c9f-3201">找到 Keyword_sweden_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3202">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="35c9f-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="35c9f-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="35c9f-3204">visa requirements</span></span> 
- <span data-ttu-id="35c9f-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="35c9f-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="35c9f-3206">Schengen visas</span></span> 
- <span data-ttu-id="35c9f-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="35c9f-3207">Schengen visa</span></span> 
- <span data-ttu-id="35c9f-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="35c9f-3208">Visa Processing</span></span> 
- <span data-ttu-id="35c9f-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="35c9f-3209">Visa Type</span></span> 
- <span data-ttu-id="35c9f-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="35c9f-3210">Single Entry</span></span> 
- <span data-ttu-id="35c9f-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="35c9f-3211">Multiple Entry</span></span> 
- <span data-ttu-id="35c9f-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="35c9f-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="35c9f-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3213">Keyword_passport</span></span>

- <span data-ttu-id="35c9f-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3214">Passport Number</span></span> 
- <span data-ttu-id="35c9f-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="35c9f-3215">Passport No</span></span> 
- <span data-ttu-id="35c9f-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3216">Passport #</span></span> 
- <span data-ttu-id="35c9f-3217">登记卡#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3217">Passport#</span></span> 
- <span data-ttu-id="35c9f-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3218">PassportID</span></span> 
- <span data-ttu-id="35c9f-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="35c9f-3219">Passportno</span></span> 
- <span data-ttu-id="35c9f-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-3220">passportnumber</span></span> 
- <span data-ttu-id="35c9f-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-3221">パスポート</span></span> 
- <span data-ttu-id="35c9f-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3222">パスポート番号</span></span> 
- <span data-ttu-id="35c9f-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-3223">パスポートのNum</span></span> 
- <span data-ttu-id="35c9f-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-3224">パスポート＃</span></span> 
- <span data-ttu-id="35c9f-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="35c9f-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="35c9f-3226">Passeport n °</span></span> 
- <span data-ttu-id="35c9f-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="35c9f-3227">Passeport Non</span></span> 
- <span data-ttu-id="35c9f-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3228">Passeport #</span></span> 
- <span data-ttu-id="35c9f-3229">Passeport#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3229">Passeport#</span></span> 
- <span data-ttu-id="35c9f-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="35c9f-3230">PasseportNon</span></span> 
- <span data-ttu-id="35c9f-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="35c9f-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="35c9f-3232">SWIFT 代码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3233">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3233">Format</span></span>

<span data-ttu-id="35c9f-3234">四个字母后跟 5-31 个字母或数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3235">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3235">Pattern</span></span>

<span data-ttu-id="35c9f-3236">四个字母后跟 5-31 个字母或数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="35c9f-3237">四个字母的银行代码（不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-3238">可选空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-3238">An optional space</span></span> 
- <span data-ttu-id="35c9f-3239">4-28 个字母或数字（基本银行账号 (BBAN)）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="35c9f-3240">可选空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-3240">An optional space</span></span> 
- <span data-ttu-id="35c9f-3241">1-3 个字母或数字（BBAN 的剩余内容）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3242">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3242">Checksum</span></span>

<span data-ttu-id="35c9f-3243">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3244">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3244">Definition</span></span>

<span data-ttu-id="35c9f-3245">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3246">正则表达式 Regex_swift 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3247">找到 Keyword_swift 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3248">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="35c9f-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="35c9f-3249">Keyword_swift</span></span>

- <span data-ttu-id="35c9f-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="35c9f-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="35c9f-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="35c9f-3251">iso 9362</span></span> 
- <span data-ttu-id="35c9f-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="35c9f-3252">iso9362</span></span> 
- <span data-ttu-id="35c9f-3253">反应\#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3253">swift\#</span></span> 
- <span data-ttu-id="35c9f-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="35c9f-3254">swiftcode</span></span> 
- <span data-ttu-id="35c9f-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-3255">swiftnumber</span></span> 
- <span data-ttu-id="35c9f-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="35c9f-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="35c9f-3257">swift code</span></span> 
- <span data-ttu-id="35c9f-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3258">swift number #</span></span> 
- <span data-ttu-id="35c9f-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3259">swift routing number</span></span> 
- <span data-ttu-id="35c9f-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3260">bic number</span></span> 
- <span data-ttu-id="35c9f-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="35c9f-3261">bic code</span></span> 
- <span data-ttu-id="35c9f-3262">numéro\#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3262">bic \#</span></span> 
- <span data-ttu-id="35c9f-3263">numéro\#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3263">bic\#</span></span> 
- <span data-ttu-id="35c9f-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="35c9f-3264">bank identifier code</span></span> 
- <span data-ttu-id="35c9f-3265">標準化9362</span><span class="sxs-lookup"><span data-stu-id="35c9f-3265">標準化9362</span></span> 
- <span data-ttu-id="35c9f-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-3266">迅速＃</span></span> 
- <span data-ttu-id="35c9f-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="35c9f-3267">SWIFTコード</span></span> 
- <span data-ttu-id="35c9f-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3268">SWIFT番号</span></span> 
- <span data-ttu-id="35c9f-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="35c9f-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3270">BIC番号</span></span> 
- <span data-ttu-id="35c9f-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="35c9f-3271">BICコード</span></span> 
- <span data-ttu-id="35c9f-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="35c9f-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="35c9f-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="35c9f-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="35c9f-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3274">rapide \#</span></span> 
- <span data-ttu-id="35c9f-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="35c9f-3275">code SWIFT</span></span> 
- <span data-ttu-id="35c9f-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="35c9f-3276">le numéro de swift</span></span> 
- <span data-ttu-id="35c9f-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="35c9f-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="35c9f-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3278">le numéro BIC</span></span> 
- <span data-ttu-id="35c9f-3279">\#NUMÉRO</span><span class="sxs-lookup"><span data-stu-id="35c9f-3279">\# BIC</span></span> 
- <span data-ttu-id="35c9f-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="35c9f-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="35c9f-3281">台湾国家/地区 ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3282">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3282">Format</span></span>

<span data-ttu-id="35c9f-3283">一个字母后跟九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3284">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3284">Pattern</span></span>

<span data-ttu-id="35c9f-3285">一个字母后跟 9 位数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="35c9f-3286">一个字母（英文，不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-3287">数字“1”或“2”</span><span class="sxs-lookup"><span data-stu-id="35c9f-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="35c9f-3288">八位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3289">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3289">Checksum</span></span>

<span data-ttu-id="35c9f-3290">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3291">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3291">Definition</span></span>

<span data-ttu-id="35c9f-3292">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3293">函数 Func_taiwanese_national_id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3294">找到 Keyword_taiwanese_national_id 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="35c9f-3295">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3296">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="35c9f-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="35c9f-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3298">身份證字號</span></span> 
- <span data-ttu-id="35c9f-3299">證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3299">身份證</span></span> 
- <span data-ttu-id="35c9f-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="35c9f-3300">身份證號碼</span></span> 
- <span data-ttu-id="35c9f-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3301">身份證號</span></span> 
- <span data-ttu-id="35c9f-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3302">身分證字號</span></span> 
- <span data-ttu-id="35c9f-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3303">身分證</span></span> 
- <span data-ttu-id="35c9f-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="35c9f-3304">身分證號碼</span></span> 
- <span data-ttu-id="35c9f-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3305">身份證號</span></span> 
- <span data-ttu-id="35c9f-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3306">身分證統一編號</span></span> 
- <span data-ttu-id="35c9f-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="35c9f-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="35c9f-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="35c9f-3308">簽名</span></span> 
- <span data-ttu-id="35c9f-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="35c9f-3309">蓋章</span></span> 
- <span data-ttu-id="35c9f-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="35c9f-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="35c9f-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="35c9f-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="35c9f-3312">	台湾护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3313">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3313">Format</span></span>

- <span data-ttu-id="35c9f-3314">生物识别护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="35c9f-3315">不带生物的护照号码：9个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3316">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3316">Pattern</span></span>
<span data-ttu-id="35c9f-3317">生物识别护照号码：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3317">Biometric passport number:</span></span>
- <span data-ttu-id="35c9f-3318">数字“3” </span><span class="sxs-lookup"><span data-stu-id="35c9f-3318">The digit "3"</span></span> 
- <span data-ttu-id="35c9f-3319">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3319">Eight digits</span></span>

<span data-ttu-id="35c9f-3320">不带生物的护照号码：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="35c9f-3321">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3322">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3322">Checksum</span></span>

<span data-ttu-id="35c9f-3323">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3324">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3324">Definition</span></span>

<span data-ttu-id="35c9f-3325">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3326">正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3327">找到 Keyword_taiwan_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3328">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="35c9f-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="35c9f-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3330">ROC passport number</span></span> 
- <span data-ttu-id="35c9f-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3331">Passport number</span></span> 
- <span data-ttu-id="35c9f-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="35c9f-3332">Passport no</span></span> 
- <span data-ttu-id="35c9f-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="35c9f-3333">Passport Num</span></span> 
- <span data-ttu-id="35c9f-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3334">Passport #</span></span> 
- <span data-ttu-id="35c9f-3335">护照</span><span class="sxs-lookup"><span data-stu-id="35c9f-3335">护照</span></span> 
- <span data-ttu-id="35c9f-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="35c9f-3336">中華民國護照</span></span> 
- <span data-ttu-id="35c9f-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="35c9f-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="35c9f-3338">台湾居民证 (ARC/TARC) 号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3339">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3339">Format</span></span>

<span data-ttu-id="35c9f-3340">10 letters and digits</span><span class="sxs-lookup"><span data-stu-id="35c9f-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3341">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3341">Pattern</span></span>

<span data-ttu-id="35c9f-3342">10 个字母和数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3342">10 letters and digits:</span></span>
- <span data-ttu-id="35c9f-3343">两个字母（不区分大小写） </span><span class="sxs-lookup"><span data-stu-id="35c9f-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="35c9f-3344">八个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3345">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3345">Checksum</span></span>

<span data-ttu-id="35c9f-3346">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3347">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3347">Definition</span></span>

<span data-ttu-id="35c9f-3348">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3349">正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3350">找到 Keyword_taiwan_resident_certificate 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3351">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="35c9f-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="35c9f-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="35c9f-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="35c9f-3353">Resident Certificate</span></span> 
- <span data-ttu-id="35c9f-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="35c9f-3354">Resident Cert</span></span> 
- <span data-ttu-id="35c9f-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3355">Resident Cert.</span></span> 
- <span data-ttu-id="35c9f-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3356">Identification card</span></span> 
- <span data-ttu-id="35c9f-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="35c9f-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="35c9f-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3358">ARC</span></span> 
- <span data-ttu-id="35c9f-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="35c9f-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="35c9f-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3360">TARC</span></span> 
- <span data-ttu-id="35c9f-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3361">居留證</span></span> 
- <span data-ttu-id="35c9f-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3362">外僑居留證</span></span> 
- <span data-ttu-id="35c9f-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="35c9f-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="35c9f-3364">泰语填充标识代码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3365">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3365">Format</span></span>

<span data-ttu-id="35c9f-3366">13 位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3367">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3367">Pattern</span></span>

<span data-ttu-id="35c9f-3368">13 个数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3368">13 digits:</span></span>
- <span data-ttu-id="35c9f-3369">第一个数字不是0或9</span><span class="sxs-lookup"><span data-stu-id="35c9f-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="35c9f-3370">12 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3371">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3371">Checksum</span></span>

<span data-ttu-id="35c9f-3372">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3373">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3373">Definition</span></span>

<span data-ttu-id="35c9f-3374">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3375">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3376">找到 Keyword_Thai_Citizen_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="35c9f-3377">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3378">函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3379">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="35c9f-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="35c9f-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3381">ID Number</span></span>
- <span data-ttu-id="35c9f-3382">标识号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3382">Identification Number</span></span>
- <span data-ttu-id="35c9f-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="35c9f-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="35c9f-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="35c9f-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="35c9f-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="35c9f-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="35c9f-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="35c9f-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="35c9f-3387">土耳其国家标识号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3388">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3388">Format</span></span>

<span data-ttu-id="35c9f-3389">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3390">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3390">Pattern</span></span>

<span data-ttu-id="35c9f-3391">11 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3392">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3392">Checksum</span></span>

<span data-ttu-id="35c9f-3393">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3394">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3394">Definition</span></span>

<span data-ttu-id="35c9f-3395">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3396">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3397">找到 Keyword_Turkish_National_Id 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="35c9f-3398">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3399">函数 Func_Turkish_National_Id 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3400">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="35c9f-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="35c9f-3402">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="35c9f-3402">TC Kimlik No</span></span>
- <span data-ttu-id="35c9f-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="35c9f-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="35c9f-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="35c9f-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="35c9f-3405">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="35c9f-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="35c9f-p144">英国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3408">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3408">Format</span></span>

<span data-ttu-id="35c9f-3409">特定格式的 18 个字母和数字组合</span><span class="sxs-lookup"><span data-stu-id="35c9f-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3410">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3410">Pattern</span></span>

<span data-ttu-id="35c9f-3411">18 个字母和数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3411">18 letters and digits:</span></span>
- <span data-ttu-id="35c9f-3412">用五个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="35c9f-3413">一位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3413">One digit</span></span> 
- <span data-ttu-id="35c9f-3414">MMDDY 的日期格式的五个数字（如果驱动程序是女，第七个字符增加50，即51到62而不是01到12）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="35c9f-3415">用两个字母（不区分大小写）或数字“9”来代替一个字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="35c9f-3416">五位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3417">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3417">Checksum</span></span>

<span data-ttu-id="35c9f-3418">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3419">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3419">Definition</span></span>

<span data-ttu-id="35c9f-3420">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3421">函数 Func_uk_drivers_license 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3422">找到 Keyword_uk_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="35c9f-3423">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3424">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="35c9f-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="35c9f-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="35c9f-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="35c9f-3426">DVLA</span></span> 
- <span data-ttu-id="35c9f-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="35c9f-3427">light vans</span></span> 
- <span data-ttu-id="35c9f-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="35c9f-3428">quadbikes</span></span> 
- <span data-ttu-id="35c9f-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="35c9f-3429">motor cars</span></span> 
- <span data-ttu-id="35c9f-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="35c9f-3430">125cc</span></span> 
- <span data-ttu-id="35c9f-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="35c9f-3431">sidecar</span></span> 
- <span data-ttu-id="35c9f-3432">tricycles</span><span class="sxs-lookup"><span data-stu-id="35c9f-3432">tricycles</span></span> 
- <span data-ttu-id="35c9f-3433">motorcycles</span><span class="sxs-lookup"><span data-stu-id="35c9f-3433">motorcycles</span></span> 
- <span data-ttu-id="35c9f-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-3434">photocard licence</span></span> 
- <span data-ttu-id="35c9f-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="35c9f-3435">learner drivers</span></span> 
- <span data-ttu-id="35c9f-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="35c9f-3436">licence holder</span></span> 
- <span data-ttu-id="35c9f-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="35c9f-3437">licence holders</span></span> 
- <span data-ttu-id="35c9f-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="35c9f-3438">driving licences</span></span> 
- <span data-ttu-id="35c9f-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="35c9f-3439">driving licence</span></span> 
- <span data-ttu-id="35c9f-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="35c9f-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="35c9f-p145">英国选民名册号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3443">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3443">Format</span></span>

<span data-ttu-id="35c9f-3444">两个字母后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3445">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3445">Pattern</span></span>

<span data-ttu-id="35c9f-3446">两个字母（不区分大小写）后跟 1-4 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3447">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3447">Checksum</span></span>

<span data-ttu-id="35c9f-3448">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3449">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3449">Definition</span></span>

<span data-ttu-id="35c9f-3450">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3451">正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3452">找到 Keyword_uk_electoral 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3453">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="35c9f-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="35c9f-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="35c9f-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="35c9f-3455">council nomination</span></span> 
- <span data-ttu-id="35c9f-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="35c9f-3456">nomination form</span></span> 
- <span data-ttu-id="35c9f-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="35c9f-3457">electoral register</span></span> 
- <span data-ttu-id="35c9f-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="35c9f-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="35c9f-p146">英国国家卫生服务号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3461">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3461">Format</span></span>

<span data-ttu-id="35c9f-3462">10-17 个数字，通过空格分隔 </span><span class="sxs-lookup"><span data-stu-id="35c9f-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3463">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3463">Pattern</span></span>

<span data-ttu-id="35c9f-3464">10-17 位数字：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3464">10-17 digits:</span></span>
- <span data-ttu-id="35c9f-3465">3 或 10 位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="35c9f-3466">一个空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-3466">A space</span></span> 
- <span data-ttu-id="35c9f-3467">三位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3467">Three digits</span></span> 
- <span data-ttu-id="35c9f-3468">一个空格</span><span class="sxs-lookup"><span data-stu-id="35c9f-3468">A space</span></span> 
- <span data-ttu-id="35c9f-3469">四位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3470">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3470">Checksum</span></span>

<span data-ttu-id="35c9f-3471">是</span><span class="sxs-lookup"><span data-stu-id="35c9f-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3472">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3472">Definition</span></span>

<span data-ttu-id="35c9f-3473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3474">函数 Func_uk_nhs_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3475">下列其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3475">One of the following is true:</span></span>
    - <span data-ttu-id="35c9f-3476">找到 Keyword_uk_nhs_number 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="35c9f-3477">找到 Keyword_uk_nhs_number1 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="35c9f-3478">找到 Keyword_uk_nhs_number_dob 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="35c9f-3479">校验和通过。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3480">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="35c9f-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="35c9f-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="35c9f-3482">national health service</span></span> 
- <span data-ttu-id="35c9f-3483">nhs</span><span class="sxs-lookup"><span data-stu-id="35c9f-3483">nhs</span></span> 
- <span data-ttu-id="35c9f-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="35c9f-3484">health services authority</span></span> 
- <span data-ttu-id="35c9f-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="35c9f-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="35c9f-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="35c9f-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="35c9f-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3487">patient id</span></span> 
- <span data-ttu-id="35c9f-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="35c9f-3488">patient identification</span></span> 
- <span data-ttu-id="35c9f-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="35c9f-3489">patient no</span></span> 
- <span data-ttu-id="35c9f-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="35c9f-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="35c9f-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="35c9f-3492">GP</span><span class="sxs-lookup"><span data-stu-id="35c9f-3492">GP</span></span> 
- <span data-ttu-id="35c9f-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="35c9f-3493">DOB</span></span> 
- <span data-ttu-id="35c9f-3494">D. B。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3494">D.O.B</span></span> 
- <span data-ttu-id="35c9f-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="35c9f-3495">Date of Birth</span></span> 
- <span data-ttu-id="35c9f-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="35c9f-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="35c9f-p147">英国国家保险号码 (NINO)</span><span class="sxs-lookup"><span data-stu-id="35c9f-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3499">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3499">Format</span></span>

<span data-ttu-id="35c9f-3500">由空格或短划线分隔的7个字符或9个字符</span><span class="sxs-lookup"><span data-stu-id="35c9f-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3501">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3501">Pattern</span></span>

<span data-ttu-id="35c9f-3502">两种可能的模式：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3502">Two possible patterns:</span></span>

- <span data-ttu-id="35c9f-3503">两个字母（有效 NINOs 仅使用此前缀中的特定字符，此格式将对此进行验证; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="35c9f-3504">六位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3504">Six digits</span></span>
- <span data-ttu-id="35c9f-3505">"A"、"B"、"C" 或 "d" （与前缀一样，后缀中只允许有某些字符; 不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="35c9f-3506">或</span><span class="sxs-lookup"><span data-stu-id="35c9f-3506">OR</span></span>

- <span data-ttu-id="35c9f-3507">两个字母</span><span class="sxs-lookup"><span data-stu-id="35c9f-3507">Two letters</span></span>
- <span data-ttu-id="35c9f-3508">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3508">A space or dash</span></span>
- <span data-ttu-id="35c9f-3509">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3509">Two digits</span></span>
- <span data-ttu-id="35c9f-3510">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3510">A space or dash</span></span>
- <span data-ttu-id="35c9f-3511">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3511">Two digits</span></span>
- <span data-ttu-id="35c9f-3512">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3512">A space or dash</span></span>
- <span data-ttu-id="35c9f-3513">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3513">Two digits</span></span>
- <span data-ttu-id="35c9f-3514">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3514">A space or dash</span></span>
- <span data-ttu-id="35c9f-3515">要么是 "A"、"B"、"C"，要么 ' d '</span><span class="sxs-lookup"><span data-stu-id="35c9f-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3516">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3516">Checksum</span></span>

<span data-ttu-id="35c9f-3517">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3518">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3518">Definition</span></span>

<span data-ttu-id="35c9f-3519">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3520">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3521">找到 Keyword_uk_nino 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="35c9f-3522">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3523">函数 Func_uk_nino 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3524">未找到 Keyword_uk_nino 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3525">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="35c9f-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="35c9f-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="35c9f-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3527">national insurance number</span></span> 
- <span data-ttu-id="35c9f-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="35c9f-3528">national insurance contributions</span></span> 
- <span data-ttu-id="35c9f-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="35c9f-3529">protection act</span></span> 
- <span data-ttu-id="35c9f-3530">方面</span><span class="sxs-lookup"><span data-stu-id="35c9f-3530">insurance</span></span> 
- <span data-ttu-id="35c9f-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3531">social security number</span></span> 
- <span data-ttu-id="35c9f-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="35c9f-3532">insurance application</span></span> 
- <span data-ttu-id="35c9f-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="35c9f-3533">medical application</span></span> 
- <span data-ttu-id="35c9f-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="35c9f-3534">social insurance</span></span> 
- <span data-ttu-id="35c9f-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="35c9f-3535">medical attention</span></span> 
- <span data-ttu-id="35c9f-3536">social security</span><span class="sxs-lookup"><span data-stu-id="35c9f-3536">social security</span></span> 
- <span data-ttu-id="35c9f-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="35c9f-3537">great britain</span></span> 
- <span data-ttu-id="35c9f-3538">方面</span><span class="sxs-lookup"><span data-stu-id="35c9f-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="35c9f-p148">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3541">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3541">Format</span></span>

<span data-ttu-id="35c9f-3542">九个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3543">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3543">Pattern</span></span>

<span data-ttu-id="35c9f-3544">九个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3545">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3545">Checksum</span></span>

<span data-ttu-id="35c9f-3546">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3547">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3547">Definition</span></span>

<span data-ttu-id="35c9f-3548">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3549">函数 Func_usa_uk_passport 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3550">找到 Keyword_passport 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3551">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="35c9f-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3552">Keyword_passport</span></span>

- <span data-ttu-id="35c9f-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3553">Passport Number</span></span> 
- <span data-ttu-id="35c9f-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="35c9f-3554">Passport No</span></span> 
- <span data-ttu-id="35c9f-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3555">Passport #</span></span> 
- <span data-ttu-id="35c9f-3556">登记卡#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3556">Passport#</span></span> 
- <span data-ttu-id="35c9f-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3557">PassportID</span></span> 
- <span data-ttu-id="35c9f-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="35c9f-3558">Passportno</span></span> 
- <span data-ttu-id="35c9f-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="35c9f-3559">passportnumber</span></span> 
- <span data-ttu-id="35c9f-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="35c9f-3560">パスポート</span></span> 
- <span data-ttu-id="35c9f-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3561">パスポート番号</span></span> 
- <span data-ttu-id="35c9f-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="35c9f-3562">パスポートのNum</span></span> 
- <span data-ttu-id="35c9f-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="35c9f-3563">パスポート＃</span></span> 
- <span data-ttu-id="35c9f-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="35c9f-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="35c9f-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="35c9f-3565">Passeport n °</span></span> 
- <span data-ttu-id="35c9f-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="35c9f-3566">Passeport Non</span></span> 
- <span data-ttu-id="35c9f-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3567">Passeport #</span></span> 
- <span data-ttu-id="35c9f-3568">Passeport#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3568">Passeport#</span></span> 
- <span data-ttu-id="35c9f-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="35c9f-3569">PasseportNon</span></span> 
- <span data-ttu-id="35c9f-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="35c9f-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="35c9f-3571">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3572">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3572">Format</span></span>

<span data-ttu-id="35c9f-3573">8-17 个数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3574">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3574">Pattern</span></span>

<span data-ttu-id="35c9f-3575">8-17 个连续的数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3576">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3576">Checksum</span></span>

<span data-ttu-id="35c9f-3577">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3578">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3578">Definition</span></span>

<span data-ttu-id="35c9f-3579">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3580">正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3581">找到 Keyword_usa_Bank_Account 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3582">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="35c9f-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="35c9f-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3584">Checking Account Number</span></span> 
- <span data-ttu-id="35c9f-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-3585">Checking Account</span></span> 
- <span data-ttu-id="35c9f-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3586">Checking Account #</span></span> 
- <span data-ttu-id="35c9f-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="35c9f-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3588">Checking Acct #</span></span> 
- <span data-ttu-id="35c9f-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="35c9f-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3590">Checking Account No.</span></span> 
- <span data-ttu-id="35c9f-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3591">Bank Account Number</span></span> 
- <span data-ttu-id="35c9f-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3592">Bank Account #</span></span> 
- <span data-ttu-id="35c9f-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="35c9f-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3594">Bank Acct #</span></span> 
- <span data-ttu-id="35c9f-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="35c9f-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3596">Bank Account No.</span></span> 
- <span data-ttu-id="35c9f-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3597">Savings Account Number</span></span> 
- <span data-ttu-id="35c9f-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3598">Savings Account.</span></span> 
- <span data-ttu-id="35c9f-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3599">Savings Account #</span></span> 
- <span data-ttu-id="35c9f-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="35c9f-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3601">Savings Acct #</span></span> 
- <span data-ttu-id="35c9f-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="35c9f-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3603">Savings Account No.</span></span> 
- <span data-ttu-id="35c9f-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3604">Debit Account Number</span></span> 
- <span data-ttu-id="35c9f-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="35c9f-3605">Debit Account</span></span> 
- <span data-ttu-id="35c9f-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3606">Debit Account #</span></span> 
- <span data-ttu-id="35c9f-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="35c9f-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3608">Debit Acct #</span></span> 
- <span data-ttu-id="35c9f-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="35c9f-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="35c9f-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="35c9f-3611">美国驾驶证号码</span><span class="sxs-lookup"><span data-stu-id="35c9f-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3612">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3612">Format</span></span>

<span data-ttu-id="35c9f-3613">取决于州</span><span class="sxs-lookup"><span data-stu-id="35c9f-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3614">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3614">Pattern</span></span>

<span data-ttu-id="35c9f-3615">取决于州 — 例如，纽约：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="35c9f-3616">与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="35c9f-3617">诸如 dddddddd 的 9 个数字将不匹配。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3618">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3618">Checksum</span></span>

<span data-ttu-id="35c9f-3619">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3620">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3620">Definition</span></span>

<span data-ttu-id="35c9f-3621">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3622">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3623">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="35c9f-3624">找到 Keyword_us_drivers_license 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="35c9f-3625">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3626">函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3627">找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="35c9f-3628">找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="35c9f-3629">未找到 Keyword_us_drivers_license 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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
```

### <a name="keywords"></a><span data-ttu-id="35c9f-3630">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="35c9f-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="35c9f-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="35c9f-3632">通讯</span><span class="sxs-lookup"><span data-stu-id="35c9f-3632">DL</span></span> 
- <span data-ttu-id="35c9f-3633">DLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-3633">DLS</span></span> 
- <span data-ttu-id="35c9f-3634">采用</span><span class="sxs-lookup"><span data-stu-id="35c9f-3634">CDL</span></span> 
- <span data-ttu-id="35c9f-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="35c9f-3635">CDLS</span></span> 
- <span data-ttu-id="35c9f-3636">ID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3636">ID</span></span> 
- <span data-ttu-id="35c9f-3637">Id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3637">IDs</span></span> 
- <span data-ttu-id="35c9f-3638">通讯#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3638">DL#</span></span> 
- <span data-ttu-id="35c9f-3639">DLS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3639">DLS#</span></span> 
- <span data-ttu-id="35c9f-3640">采用#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3640">CDL#</span></span> 
- <span data-ttu-id="35c9f-3641">CDLS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3641">CDLS#</span></span> 
- <span data-ttu-id="35c9f-3642">号#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3642">ID#</span></span>
- <span data-ttu-id="35c9f-3643">Id#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3643">IDs#</span></span> 
- <span data-ttu-id="35c9f-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3644">ID number</span></span> 
- <span data-ttu-id="35c9f-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-3645">ID numbers</span></span> 
- <span data-ttu-id="35c9f-3646">.LIC</span><span class="sxs-lookup"><span data-stu-id="35c9f-3646">LIC</span></span> 
- <span data-ttu-id="35c9f-3647">.LIC#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="35c9f-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="35c9f-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="35c9f-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3649">DriverLic</span></span> 
- <span data-ttu-id="35c9f-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3650">DriverLics</span></span> 
- <span data-ttu-id="35c9f-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-3651">DriverLicense</span></span> 
- <span data-ttu-id="35c9f-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3652">DriverLicenses</span></span> 
- <span data-ttu-id="35c9f-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3653">Driver Lic</span></span> 
- <span data-ttu-id="35c9f-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3654">Driver Lics</span></span> 
- <span data-ttu-id="35c9f-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="35c9f-3655">Driver License</span></span> 
- <span data-ttu-id="35c9f-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3656">Driver Licenses</span></span> 
- <span data-ttu-id="35c9f-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3657">DriversLic</span></span> 
- <span data-ttu-id="35c9f-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3658">DriversLics</span></span> 
- <span data-ttu-id="35c9f-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-3659">DriversLicense</span></span> 
- <span data-ttu-id="35c9f-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3660">DriversLicenses</span></span> 
- <span data-ttu-id="35c9f-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3661">Drivers Lic</span></span> 
- <span data-ttu-id="35c9f-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3662">Drivers Lics</span></span> 
- <span data-ttu-id="35c9f-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="35c9f-3663">Drivers License</span></span> 
- <span data-ttu-id="35c9f-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="35c9f-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3665">Driver'Lic</span></span> 
- <span data-ttu-id="35c9f-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3666">Driver'Lics</span></span> 
- <span data-ttu-id="35c9f-3667">Driver'License</span><span class="sxs-lookup"><span data-stu-id="35c9f-3667">Driver'License</span></span> 
- <span data-ttu-id="35c9f-3668">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="35c9f-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3669">Driver' Lic</span></span> 
- <span data-ttu-id="35c9f-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3670">Driver' Lics</span></span> 
- <span data-ttu-id="35c9f-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="35c9f-3671">Driver' License</span></span> 
- <span data-ttu-id="35c9f-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3672">Driver' Licenses</span></span>
- <span data-ttu-id="35c9f-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3673">Driver'sLic</span></span> 
- <span data-ttu-id="35c9f-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3674">Driver'sLics</span></span> 
- <span data-ttu-id="35c9f-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="35c9f-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="35c9f-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="35c9f-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="35c9f-3677">Driver's Lic</span></span> 
- <span data-ttu-id="35c9f-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="35c9f-3678">Driver's Lics</span></span> 
- <span data-ttu-id="35c9f-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="35c9f-3679">Driver's License</span></span> 
- <span data-ttu-id="35c9f-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="35c9f-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="35c9f-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="35c9f-3681">identification number</span></span> 
- <span data-ttu-id="35c9f-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="35c9f-3682">identification numbers</span></span> 
- <span data-ttu-id="35c9f-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="35c9f-3683">identification #</span></span> 
- <span data-ttu-id="35c9f-3684">id card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3684">id card</span></span> 
- <span data-ttu-id="35c9f-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-3685">id cards</span></span> 
- <span data-ttu-id="35c9f-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="35c9f-3686">identification card</span></span> 
- <span data-ttu-id="35c9f-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="35c9f-3687">identification cards</span></span> 
- <span data-ttu-id="35c9f-3688">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3688">DriverLic#</span></span> 
- <span data-ttu-id="35c9f-3689">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3689">DriverLics#</span></span> 
- <span data-ttu-id="35c9f-3690">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3690">DriverLicense#</span></span> 
- <span data-ttu-id="35c9f-3691">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="35c9f-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3692">Driver Lic#</span></span> 
- <span data-ttu-id="35c9f-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3693">Driver Lics#</span></span> 
- <span data-ttu-id="35c9f-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3694">Driver License#</span></span> 
- <span data-ttu-id="35c9f-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="35c9f-3696">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3696">DriversLic#</span></span> 
- <span data-ttu-id="35c9f-3697">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3697">DriversLics#</span></span> 
- <span data-ttu-id="35c9f-3698">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3698">DriversLicense#</span></span> 
- <span data-ttu-id="35c9f-3699">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="35c9f-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="35c9f-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="35c9f-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3702">Drivers License#</span></span> 
- <span data-ttu-id="35c9f-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="35c9f-3704">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="35c9f-3705">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="35c9f-3706">Driver'License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3706">Driver'License#</span></span> 
- <span data-ttu-id="35c9f-3707">Driver'Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="35c9f-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="35c9f-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="35c9f-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3710">Driver' License#</span></span> 
- <span data-ttu-id="35c9f-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="35c9f-3712">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="35c9f-3713">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="35c9f-3714">Driver'sLicense#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="35c9f-3715">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="35c9f-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="35c9f-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="35c9f-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3718">Driver's License#</span></span> 
- <span data-ttu-id="35c9f-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="35c9f-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3720">id card#</span></span> 
- <span data-ttu-id="35c9f-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3721">id cards#</span></span> 
- <span data-ttu-id="35c9f-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3722">identification card#</span></span> 
- <span data-ttu-id="35c9f-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="35c9f-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="35c9f-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="35c9f-3725">州缩写（例如，“NY”）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="35c9f-3726">州名称（例如，“New York”）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="35c9f-3727">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3728">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3728">Format</span></span>

<span data-ttu-id="35c9f-3729">九个数字，以“9”开头，“7”或“8”作为第四个数字，可以采用空格或短划线格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3730">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3730">Pattern</span></span>

<span data-ttu-id="35c9f-3731">格式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3731">Formatted:</span></span>
- <span data-ttu-id="35c9f-3732">数字“9”</span><span class="sxs-lookup"><span data-stu-id="35c9f-3732">The digit "9"</span></span> 
- <span data-ttu-id="35c9f-3733">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3733">Two digits</span></span> 
- <span data-ttu-id="35c9f-3734">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3734">A space or dash</span></span> 
- <span data-ttu-id="35c9f-3735">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="35c9f-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="35c9f-3736">一位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3736">A digit</span></span> 
- <span data-ttu-id="35c9f-3737">一个空格或破折号</span><span class="sxs-lookup"><span data-stu-id="35c9f-3737">A space, or dash</span></span> 
- <span data-ttu-id="35c9f-3738">四位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3738">Four digits</span></span>

<span data-ttu-id="35c9f-3739">纯</span><span class="sxs-lookup"><span data-stu-id="35c9f-3739">Unformatted:</span></span>
- <span data-ttu-id="35c9f-3740">数字“9”</span><span class="sxs-lookup"><span data-stu-id="35c9f-3740">The digit "9"</span></span> 
- <span data-ttu-id="35c9f-3741">两位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3741">Two digits</span></span> 
- <span data-ttu-id="35c9f-3742">“7”或“8”</span><span class="sxs-lookup"><span data-stu-id="35c9f-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="35c9f-3743">五位数字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3744">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3744">Checksum</span></span>

<span data-ttu-id="35c9f-3745">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="35c9f-3746">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3746">Definition</span></span>

<span data-ttu-id="35c9f-3747">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3748">函数 Func_formatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3749">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="35c9f-3750">找到 Keyword_itin 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="35c9f-3751">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="35c9f-3752">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="35c9f-3753">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="35c9f-3754">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3755">函数 Func_unformatted_itin 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3756">下列至少其中一项为真：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="35c9f-3757">找到 Keyword_itin_collaborative 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="35c9f-3758">函数 Func_us_address 找到正确日期格式的地址。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="35c9f-3759">函数 Func_us_date 找到正确日期格式的日期。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="35c9f-3760">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="35c9f-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="35c9f-3761">Keyword_itin</span></span>

- <span data-ttu-id="35c9f-3762">报税</span><span class="sxs-lookup"><span data-stu-id="35c9f-3762">taxpayer</span></span> 
- <span data-ttu-id="35c9f-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="35c9f-3763">tax id</span></span> 
- <span data-ttu-id="35c9f-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="35c9f-3764">tax identification</span></span> 
- <span data-ttu-id="35c9f-3765">itin</span><span class="sxs-lookup"><span data-stu-id="35c9f-3765">itin</span></span> 
- <span data-ttu-id="35c9f-3766">ssn</span><span class="sxs-lookup"><span data-stu-id="35c9f-3766">ssn</span></span> 
- <span data-ttu-id="35c9f-3767">锡</span><span class="sxs-lookup"><span data-stu-id="35c9f-3767">tin</span></span> 
- <span data-ttu-id="35c9f-3768">social security</span><span class="sxs-lookup"><span data-stu-id="35c9f-3768">social security</span></span> 
- <span data-ttu-id="35c9f-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="35c9f-3769">tax payer</span></span> 
- <span data-ttu-id="35c9f-3770">itins</span><span class="sxs-lookup"><span data-stu-id="35c9f-3770">itins</span></span> 
- <span data-ttu-id="35c9f-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="35c9f-3771">taxid</span></span> 
- <span data-ttu-id="35c9f-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="35c9f-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="35c9f-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="35c9f-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="35c9f-3774">许可证</span><span class="sxs-lookup"><span data-stu-id="35c9f-3774">License</span></span> 
- <span data-ttu-id="35c9f-3775">通讯</span><span class="sxs-lookup"><span data-stu-id="35c9f-3775">DL</span></span> 
- <span data-ttu-id="35c9f-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="35c9f-3776">DOB</span></span> 
- <span data-ttu-id="35c9f-3777">出生日期</span><span class="sxs-lookup"><span data-stu-id="35c9f-3777">Birthdate</span></span> 
- <span data-ttu-id="35c9f-3778">一定</span><span class="sxs-lookup"><span data-stu-id="35c9f-3778">Birthday</span></span> 
- <span data-ttu-id="35c9f-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="35c9f-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="35c9f-3780">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="35c9f-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="35c9f-3781">Format</span><span class="sxs-lookup"><span data-stu-id="35c9f-3781">Format</span></span>

<span data-ttu-id="35c9f-3782">9 个数字，可以是格式化模式，也可以是非格式化模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="35c9f-3783">如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="35c9f-3784">模式</span><span class="sxs-lookup"><span data-stu-id="35c9f-3784">Pattern</span></span>

<span data-ttu-id="35c9f-3785">四种不同模式中的 SSN 的四种函数外观：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="35c9f-3786">Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）</span><span class="sxs-lookup"><span data-stu-id="35c9f-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="35c9f-3787">Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="35c9f-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="35c9f-3788">Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="35c9f-3789">Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="35c9f-3790">校验和</span><span class="sxs-lookup"><span data-stu-id="35c9f-3790">Checksum</span></span>

<span data-ttu-id="35c9f-3791">否</span><span class="sxs-lookup"><span data-stu-id="35c9f-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="35c9f-3792">定义</span><span class="sxs-lookup"><span data-stu-id="35c9f-3792">Definition</span></span>

<span data-ttu-id="35c9f-3793">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3794">函数 Func_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3795">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3795">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="35c9f-3796">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3797">函数 Func_unformatted_ssn 查找与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3797">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3798">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3798">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="35c9f-3799">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3799">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3800">函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3800">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3801">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3801">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="35c9f-3802">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="35c9f-3802">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="35c9f-3803">函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3803">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="35c9f-3804">找到 Keyword_ssn 中的一个关键字。</span><span class="sxs-lookup"><span data-stu-id="35c9f-3804">A keyword from Keyword_ssn is found.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="35c9f-3805">关键字</span><span class="sxs-lookup"><span data-stu-id="35c9f-3805">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="35c9f-3806">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="35c9f-3806">Keyword_ssn</span></span>

- <span data-ttu-id="35c9f-3807">Social Security</span><span class="sxs-lookup"><span data-stu-id="35c9f-3807">Social Security</span></span> 
- <span data-ttu-id="35c9f-3808">Social Security#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3808">Social Security#</span></span> 
- <span data-ttu-id="35c9f-3809">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="35c9f-3809">Soc Sec</span></span> 
- <span data-ttu-id="35c9f-3810">SSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3810">SSN</span></span> 
- <span data-ttu-id="35c9f-3811">SSN</span><span class="sxs-lookup"><span data-stu-id="35c9f-3811">SSNS</span></span> 
- <span data-ttu-id="35c9f-3812">SSN#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3812">SSN#</span></span> 
- <span data-ttu-id="35c9f-3813">SS#</span><span class="sxs-lookup"><span data-stu-id="35c9f-3813">SS#</span></span> 
- <span data-ttu-id="35c9f-3814">SSID</span><span class="sxs-lookup"><span data-stu-id="35c9f-3814">SSID</span></span> 
   
