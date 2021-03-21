---
title: 说明类型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 深入了解 Microsoft SharePoint Syntex 中的说明类型
ms.openlocfilehash: 5187b27438f25db1a2714f1fbc7b31db6d060ccc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928396"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="3b37c-103">说明类型简介</span><span class="sxs-lookup"><span data-stu-id="3b37c-103">Introduction to explanation types</span></span>

<span data-ttu-id="3b37c-104">说明用于帮助定义要标记的信息并在 Microsoft SharePoint Syntex 中的文档理解模型里进行提取。</span><span class="sxs-lookup"><span data-stu-id="3b37c-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="3b37c-105">创建说明时，需要选择说明类型。</span><span class="sxs-lookup"><span data-stu-id="3b37c-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="3b37c-106">本文将帮助你了解不同的说明类型以及它们的使用方式。</span><span class="sxs-lookup"><span data-stu-id="3b37c-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![说明类型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="3b37c-108">可使用以下说明类型：</span><span class="sxs-lookup"><span data-stu-id="3b37c-108">These explanation types are available:</span></span>

- <span data-ttu-id="3b37c-109">**短语列表**：可在文档中使用的单词、短语、数字或其他字符的列表，或是正在提取的信息。</span><span class="sxs-lookup"><span data-stu-id="3b37c-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="3b37c-110">例如，文本字符串“**咨询医生**”存在于你正在识别的所有“医疗转介”文档中。</span><span class="sxs-lookup"><span data-stu-id="3b37c-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="3b37c-111">**模式列表**：列出可用于识别所提取信息的模式的数字、字母或其他字符。</span><span class="sxs-lookup"><span data-stu-id="3b37c-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="3b37c-112">例如，你可以从正在识别的所有“医疗转介”文档中提取咨询医生的“**电话号码**”。</span><span class="sxs-lookup"><span data-stu-id="3b37c-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="3b37c-113">**邻近度**：描述两个说明之间有多接近。</span><span class="sxs-lookup"><span data-stu-id="3b37c-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="3b37c-114">例如，*街道号码* 模式列表会先于 *街道名称* 短语列表出现，两者之间不设有令牌（你将在本文后面了解令牌）。</span><span class="sxs-lookup"><span data-stu-id="3b37c-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="3b37c-115">使用邻近度类型要求模型中至少有两个说明，否则将禁用该选项。</span><span class="sxs-lookup"><span data-stu-id="3b37c-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="3b37c-116">短语列表</span><span class="sxs-lookup"><span data-stu-id="3b37c-116">Phrase list</span></span>

<span data-ttu-id="3b37c-117">短语列表说明类型通常用于通过模型识别和分类文档。</span><span class="sxs-lookup"><span data-stu-id="3b37c-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="3b37c-118">正如“*咨询医生*”标签示例中所述，它是所标识的文档中一致出现的单词、短语、数字或字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="3b37c-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="3b37c-119">虽然这并不是强制要求，但如果要捕获的短语位于文档中的一致位置，则可以在“说明”上取得更好的成功。</span><span class="sxs-lookup"><span data-stu-id="3b37c-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="3b37c-120">例如，“*咨询医生*”标签可能一直位于文档中的第一段。</span><span class="sxs-lookup"><span data-stu-id="3b37c-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="3b37c-121">如果标识标签时需要区分大小写，使用短语列表类型可以使你在说明中指定这种情况，只需通过选择“**仅完全匹配的大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="3b37c-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![区分大小写](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="3b37c-123">模式列表</span><span class="sxs-lookup"><span data-stu-id="3b37c-123">Pattern lists</span></span>

<span data-ttu-id="3b37c-124">当你创建一个从文档中标识和提取信息的说明时，阵列模式类型特别有用。</span><span class="sxs-lookup"><span data-stu-id="3b37c-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="3b37c-125">它通常以不同的格式显示，如日期、电话号码和信用卡号码。</span><span class="sxs-lookup"><span data-stu-id="3b37c-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="3b37c-126">例如，可按多种不同的格式显示日期（1/1/2020、1-1-2020、01/01/20、01/01/2020、2020 年 1 月 1 日等等）。</span><span class="sxs-lookup"><span data-stu-id="3b37c-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="3b37c-127">通过在你尝试标识和提取的数据中捕获任何可能的变体，定义模式列表使你的说明变得更加高效。</span><span class="sxs-lookup"><span data-stu-id="3b37c-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="3b37c-128">对于“**电话号码** ”示例，从模型识别的所有“医疗转介”文档中提取每个咨询医生的电话号码。</span><span class="sxs-lookup"><span data-stu-id="3b37c-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="3b37c-129">创建说明时，选择”模式列表”类型以便允许返回预期会返回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="3b37c-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![电话号码模式列表](../media/content-understanding/pattern-list.png)

<span data-ttu-id="3b37c-131">在此示例中，选择“**0 - 9 中的任何数字**”复选框，以将模式列表中使用的“0”值识别为 0 到 9 中的任何数字。</span><span class="sxs-lookup"><span data-stu-id="3b37c-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0 - 9 中的任何数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="3b37c-133">同样，如果创建包含文本字符的模式列表，选择“**a-z 中的任何字母**”复选框，以将模式列表中使用的“a”字符识别为“a”到“z”中的任何字符。</span><span class="sxs-lookup"><span data-stu-id="3b37c-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="3b37c-134">例如，如果创建“**日期**”模式列表，并且想确保识别出日期格式（如 *Jan 1, 2020*），则需执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3b37c-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="3b37c-135">将 *aaa 0, 0000* 和 *aaa 00, 0000* 添加到模式列表中。</span><span class="sxs-lookup"><span data-stu-id="3b37c-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3b37c-136">确保也选中了 **a-z 中的任何字母**。</span><span class="sxs-lookup"><span data-stu-id="3b37c-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![a-z 中的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="3b37c-138">此外，如果在模式列表中有大写要求，可选择“**仅完全匹配的大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="3b37c-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="3b37c-139">对于“日期”示例，如果需要将月份的第一个字母大写，则需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3b37c-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="3b37c-140">将 *Aaa 0, 0000* 和 *Aaa 00, 0000* 添加到模式列表中。</span><span class="sxs-lookup"><span data-stu-id="3b37c-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3b37c-141">确保也选中了“**仅完全匹配的大写**”。</span><span class="sxs-lookup"><span data-stu-id="3b37c-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![仅完全匹配的大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="3b37c-143">请使用 [说明库](#use-explanation-templates)，以便从常见模式列表中使用模式列表模板，如 *日期*、*电话号码*、*信用卡号码* 等等，而不是手动创建模式列表说明。</span><span class="sxs-lookup"><span data-stu-id="3b37c-143">Instead of manually creating a pattern list explanation, use the [explanation library](#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="3b37c-144">邻近度</span><span class="sxs-lookup"><span data-stu-id="3b37c-144">Proximity</span></span> 

<span data-ttu-id="3b37c-145">邻近度说明类型可帮助模型识别数据（通过定义另一份数据与其的接近程度）。</span><span class="sxs-lookup"><span data-stu-id="3b37c-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="3b37c-146">例如，在模型中，你已经定义了两个用于标记客户的“*街道地址编号*”和“*电话号码*”的说明。</span><span class="sxs-lookup"><span data-stu-id="3b37c-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="3b37c-147">注意客户的电话号码始终出现在街道地址编号的前面。</span><span class="sxs-lookup"><span data-stu-id="3b37c-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="3b37c-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="3b37c-148">Alex Wilburn</span></span><br>
<span data-ttu-id="3b37c-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="3b37c-149">555-555-5555</span></span><br>
<span data-ttu-id="3b37c-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3b37c-150">One Microsoft Way</span></span><br>
<span data-ttu-id="3b37c-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3b37c-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3b37c-152">使用邻近度说明来定义电话号码说明的距离，以便更好地识别文档中的街道地址编号。</span><span class="sxs-lookup"><span data-stu-id="3b37c-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![邻近度说明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="3b37c-154">什么是令牌？</span><span class="sxs-lookup"><span data-stu-id="3b37c-154">What are tokens?</span></span>

<span data-ttu-id="3b37c-155">为使用邻近度说明类型，需理解令牌的含义，因为令牌数目是邻近度说明测量某个说明与另一个说明距离的方法。</span><span class="sxs-lookup"><span data-stu-id="3b37c-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="3b37c-156">令牌是字母和数字的连续跨度结构（不包含空格或标点）。</span><span class="sxs-lookup"><span data-stu-id="3b37c-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="3b37c-157">下表显示了一些如何确定短语中令牌数目的示例。</span><span class="sxs-lookup"><span data-stu-id="3b37c-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="3b37c-158">短语</span><span class="sxs-lookup"><span data-stu-id="3b37c-158">Phrase</span></span>|<span data-ttu-id="3b37c-159">令牌的数目</span><span class="sxs-lookup"><span data-stu-id="3b37c-159">Number of tokens</span></span>|<span data-ttu-id="3b37c-160">说明</span><span class="sxs-lookup"><span data-stu-id="3b37c-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="3b37c-161">1</span><span class="sxs-lookup"><span data-stu-id="3b37c-161">1</span></span>|<span data-ttu-id="3b37c-162">单个单词，无标点符号或空格。</span><span class="sxs-lookup"><span data-stu-id="3b37c-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="3b37c-163">1</span><span class="sxs-lookup"><span data-stu-id="3b37c-163">1</span></span>|<span data-ttu-id="3b37c-164">记录定位器的编号。</span><span class="sxs-lookup"><span data-stu-id="3b37c-164">A record locator number.</span></span> <span data-ttu-id="3b37c-165">它可能包含数字和字母，但不包含标点符号。</span><span class="sxs-lookup"><span data-stu-id="3b37c-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="3b37c-166">5</span><span class="sxs-lookup"><span data-stu-id="3b37c-166">5</span></span>|<span data-ttu-id="3b37c-167">电话号码。</span><span class="sxs-lookup"><span data-stu-id="3b37c-167">A phone number.</span></span> <span data-ttu-id="3b37c-168">每个标点符号是一个令牌，因此 `425-555-5555` 是 5 个令牌：</span><span class="sxs-lookup"><span data-stu-id="3b37c-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="3b37c-169">7</span><span class="sxs-lookup"><span data-stu-id="3b37c-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="3b37c-170">配置邻近度说明类型</span><span class="sxs-lookup"><span data-stu-id="3b37c-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="3b37c-171">针对示例，请配置邻近度设置，以定义从“*街道地址编号*”说明到“*电话号码*”说明的令牌数量的范围。</span><span class="sxs-lookup"><span data-stu-id="3b37c-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="3b37c-172">注意最小范围是“0”，因为电话号码和街道地址编号之间没有令牌。</span><span class="sxs-lookup"><span data-stu-id="3b37c-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="3b37c-173">但示例文档中的某些电话号码附加了 *(mobile)*。</span><span class="sxs-lookup"><span data-stu-id="3b37c-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="3b37c-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="3b37c-174">Nestor Wilke</span></span><br>
<span data-ttu-id="3b37c-175">111-111-1111 (mobile)</span><span class="sxs-lookup"><span data-stu-id="3b37c-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="3b37c-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3b37c-176">One Microsoft Way</span></span><br>
<span data-ttu-id="3b37c-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3b37c-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3b37c-178">*(mobile)* 中有三个令牌：</span><span class="sxs-lookup"><span data-stu-id="3b37c-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="3b37c-179">短语</span><span class="sxs-lookup"><span data-stu-id="3b37c-179">Phrase</span></span>|<span data-ttu-id="3b37c-180">令牌计数</span><span class="sxs-lookup"><span data-stu-id="3b37c-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="3b37c-181">(</span><span class="sxs-lookup"><span data-stu-id="3b37c-181">(</span></span>|<span data-ttu-id="3b37c-182">1</span><span class="sxs-lookup"><span data-stu-id="3b37c-182">1</span></span>|
|<span data-ttu-id="3b37c-183">mobile</span><span class="sxs-lookup"><span data-stu-id="3b37c-183">mobile</span></span>|<span data-ttu-id="3b37c-184">2</span><span class="sxs-lookup"><span data-stu-id="3b37c-184">2</span></span>|
|<span data-ttu-id="3b37c-185">)</span><span class="sxs-lookup"><span data-stu-id="3b37c-185">)</span></span>|<span data-ttu-id="3b37c-186">3</span><span class="sxs-lookup"><span data-stu-id="3b37c-186">3</span></span>|

<span data-ttu-id="3b37c-187">配置邻近度设置，以便拥有 0 到 3 的范围。</span><span class="sxs-lookup"><span data-stu-id="3b37c-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![邻近度示例](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="3b37c-189">配置短语在文档中出现的位置</span><span class="sxs-lookup"><span data-stu-id="3b37c-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="3b37c-190">创建说明时，默认情况下会在整个文档中搜索要提取的短语。</span><span class="sxs-lookup"><span data-stu-id="3b37c-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="3b37c-191">但是，可以使用“<b>这些短语出现的位置</b>”高级设置来帮助隔离文档中出现短语的特定位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="3b37c-192">这适用于文档的其他位置可能出现短语的类似实例，而你希望确保选择正确短语的情况。</span><span class="sxs-lookup"><span data-stu-id="3b37c-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="3b37c-193">以我们的医疗转诊文档为例，文档的第一段中总是会提到 **转诊医生**。</span><span class="sxs-lookup"><span data-stu-id="3b37c-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="3b37c-194">通过“<b>这些短语出现的位置</b>”设置，在本示例中，你可以配置说明以仅在文档开头或可能出现该短语的任何其他位置搜索该短语。</span><span class="sxs-lookup"><span data-stu-id="3b37c-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![“这些短语出现的位置”设置](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="3b37c-196">可以为此设置选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="3b37c-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="3b37c-197">文件中的任何位置：将在整个文档中搜索短语。</span><span class="sxs-lookup"><span data-stu-id="3b37c-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="3b37c-198">文件开头：从文档开头开始搜索短语。</span><span class="sxs-lookup"><span data-stu-id="3b37c-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="3b37c-199">![文件开头](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="3b37c-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="3b37c-200">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="3b37c-201"><b>结束位置</b>值将更新以显示所选区域包含的令牌数。</span><span class="sxs-lookup"><span data-stu-id="3b37c-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="3b37c-202">请注意，可以更新“结束位置”值并调整所选区域。</span><span class="sxs-lookup"><span data-stu-id="3b37c-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="3b37c-203">![文件开头位置框](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="3b37c-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="3b37c-204">文件末尾：从文档末尾开始搜索短语。</span><span class="sxs-lookup"><span data-stu-id="3b37c-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="3b37c-205">![文件末尾](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="3b37c-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="3b37c-206">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="3b37c-207"><b>开始位置</b>值将更新以显示所选区域包含的令牌数。</span><span class="sxs-lookup"><span data-stu-id="3b37c-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="3b37c-208">请注意，可以更新“开始位置”值并调整所选区域。</span><span class="sxs-lookup"><span data-stu-id="3b37c-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="3b37c-209">![文件末尾位置框](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="3b37c-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="3b37c-210">自定义范围：在文档内的指定范围内搜索短语位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="3b37c-211">![自定义范围](../media/content-understanding/custom-file.png)</span><span class="sxs-lookup"><span data-stu-id="3b37c-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="3b37c-212">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="3b37c-213">对于此设置，需要选择一个<b>开始</b>和<b>结束</b>位置。</span><span class="sxs-lookup"><span data-stu-id="3b37c-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="3b37c-214">这些值表示从文档开头开始的令牌数。</span><span class="sxs-lookup"><span data-stu-id="3b37c-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="3b37c-215">尽管可以手动输入这些值，但在查看器中手动调整选择框更容易。</span><span class="sxs-lookup"><span data-stu-id="3b37c-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="3b37c-216">使用说明模板</span><span class="sxs-lookup"><span data-stu-id="3b37c-216">Use explanation templates</span></span>

<span data-ttu-id="3b37c-217">可手动添加各个短语列表值进行解释，但使用解释库中提供模板更为轻松。</span><span class="sxs-lookup"><span data-stu-id="3b37c-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="3b37c-218">例如，可以使用 *Date* 的短语列表模板来手动添加 *Date* 的所有变体，因为它已包含许多短语列表值：</span><span class="sxs-lookup"><span data-stu-id="3b37c-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![说明库](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="3b37c-220">解释库包含常用的短语列表说明，包括：</span><span class="sxs-lookup"><span data-stu-id="3b37c-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="3b37c-221">日期</span><span class="sxs-lookup"><span data-stu-id="3b37c-221">Date</span></span></br>
- <span data-ttu-id="3b37c-222">日期（数值）</span><span class="sxs-lookup"><span data-stu-id="3b37c-222">Date (numeric)</span></span></br>
- <span data-ttu-id="3b37c-223">时间</span><span class="sxs-lookup"><span data-stu-id="3b37c-223">Time</span></span></br>
- <span data-ttu-id="3b37c-224">号码</span><span class="sxs-lookup"><span data-stu-id="3b37c-224">Number</span></span></br>
- <span data-ttu-id="3b37c-225">百分比</span><span class="sxs-lookup"><span data-stu-id="3b37c-225">Percentage</span></span></br>
- <span data-ttu-id="3b37c-226">电话号码</span><span class="sxs-lookup"><span data-stu-id="3b37c-226">Phone number</span></span></br>
- <span data-ttu-id="3b37c-227">邮政编码</span><span class="sxs-lookup"><span data-stu-id="3b37c-227">Zip code</span></span></br>
- <span data-ttu-id="3b37c-228">一句话的第一个词</span><span class="sxs-lookup"><span data-stu-id="3b37c-228">First word of sentence</span></span></br>
- <span data-ttu-id="3b37c-229">句末</span><span class="sxs-lookup"><span data-stu-id="3b37c-229">End of sentence</span></span></br>
- <span data-ttu-id="3b37c-230">信用卡</span><span class="sxs-lookup"><span data-stu-id="3b37c-230">Credit card</span></span></br>
- <span data-ttu-id="3b37c-231">社会安全号码</span><span class="sxs-lookup"><span data-stu-id="3b37c-231">Social security number</span></span></br>
- <span data-ttu-id="3b37c-232">复选框</span><span class="sxs-lookup"><span data-stu-id="3b37c-232">Checkbox</span></span></br>
- <span data-ttu-id="3b37c-233">货币</span><span class="sxs-lookup"><span data-stu-id="3b37c-233">Currency</span></span></br>
- <span data-ttu-id="3b37c-234">电子邮件抄送</span><span class="sxs-lookup"><span data-stu-id="3b37c-234">Email CC</span></span></br>
- <span data-ttu-id="3b37c-235">电子邮件日期</span><span class="sxs-lookup"><span data-stu-id="3b37c-235">Email date</span></span></br>
- <span data-ttu-id="3b37c-236">电子邮件问候语</span><span class="sxs-lookup"><span data-stu-id="3b37c-236">Email greeting</span></span></br>
- <span data-ttu-id="3b37c-237">向电子邮件收件人发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="3b37c-237">Email recipient</span></span></br>
- <span data-ttu-id="3b37c-238">电子邮件发件人</span><span class="sxs-lookup"><span data-stu-id="3b37c-238">Email sender</span></span></br>
- <span data-ttu-id="3b37c-239">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="3b37c-239">Email subject</span></span></br>

<span data-ttu-id="3b37c-240">说明库还包含三种自动模板类型，用于处理示例文件中标记的数据：</span><span class="sxs-lookup"><span data-stu-id="3b37c-240">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="3b37c-241">标记后：示例文件中标签后发生的字词或字符。</span><span class="sxs-lookup"><span data-stu-id="3b37c-241">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="3b37c-242">标签之前：示例文件中标签前发生的字词或字符。</span><span class="sxs-lookup"><span data-stu-id="3b37c-242">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="3b37c-243">标签：示例文件前 10 个标签。</span><span class="sxs-lookup"><span data-stu-id="3b37c-243">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="3b37c-244">为提供自动模板工作方式的示例，以下示例文件中将使用"之前的标签"说明模板，帮助为模型提供更多信息，以获得更准确的匹配。</span><span class="sxs-lookup"><span data-stu-id="3b37c-244">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![示例文件](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="3b37c-246">选择"标签之前"说明模板时，它将查找示例文件中标签前显示的第一组字词。</span><span class="sxs-lookup"><span data-stu-id="3b37c-246">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="3b37c-247">在示例中，第一个示例文件中标识的字词为"截至"。</span><span class="sxs-lookup"><span data-stu-id="3b37c-247">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![标签模板之前](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="3b37c-249">可选择" <b>添加</b> 模板创建解释。</span><span class="sxs-lookup"><span data-stu-id="3b37c-249">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="3b37c-250">添加更多示例文件时，将在短语列表中标识并添加其他字词。</span><span class="sxs-lookup"><span data-stu-id="3b37c-250">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![添加标签](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="3b37c-252">若要使用说明库中的模板</span><span class="sxs-lookup"><span data-stu-id="3b37c-252">To use a template from the explanation library</span></span>

1. <span data-ttu-id="3b37c-253">从模型的“**培训**”页面的“**说明**”部分中，选择“**新建**”，然后选择“**通过模板**”。</span><span class="sxs-lookup"><span data-stu-id="3b37c-253">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![添加前标签](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="3b37c-255">在“**说明模板**”页面上，选择要使用的说明，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3b37c-255">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![选择模板](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="3b37c-257">所选模板的信息显示在“**创建说明**”页面。</span><span class="sxs-lookup"><span data-stu-id="3b37c-257">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="3b37c-258">如果需要，可编辑解释名称，并从短语列表中添加或删除项目。</span><span class="sxs-lookup"><span data-stu-id="3b37c-258">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![编辑模板](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="3b37c-260">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3b37c-260">When finished, select **Save**.</span></span>