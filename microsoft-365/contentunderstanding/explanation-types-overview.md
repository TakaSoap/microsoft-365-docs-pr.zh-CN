---
title: 说明类型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 深入了解 Microsoft SharePoint Syntex 中的说明类型
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321793"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="0a27e-103">说明类型简介</span><span class="sxs-lookup"><span data-stu-id="0a27e-103">Introduction to explanation types</span></span>

<span data-ttu-id="0a27e-104">说明用于帮助定义要标记的信息并在 Microsoft SharePoint Syntex 中的文档理解模型里进行提取。</span><span class="sxs-lookup"><span data-stu-id="0a27e-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="0a27e-105">创建说明时，需要选择说明类型。</span><span class="sxs-lookup"><span data-stu-id="0a27e-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="0a27e-106">本文将帮助你深入了解，以便更好地了解不同的说明类型以及它们的使用方式。</span><span class="sxs-lookup"><span data-stu-id="0a27e-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![说明类型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="0a27e-108">可使用以下说明类型：</span><span class="sxs-lookup"><span data-stu-id="0a27e-108">These explanation types are available:</span></span>

- <span data-ttu-id="0a27e-109">**短语列表**：可在文档中使用的单词、短语、数字或其他字符的列表，或是正在提取的信息。</span><span class="sxs-lookup"><span data-stu-id="0a27e-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="0a27e-110">例如，文本字符串“**咨询医生**”存在于你正在识别的所有“医疗转介”文档中。</span><span class="sxs-lookup"><span data-stu-id="0a27e-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="0a27e-111">**模式列表**：列出可用于识别所提取信息的模式的数字、字母或其他字符。</span><span class="sxs-lookup"><span data-stu-id="0a27e-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="0a27e-112">例如，你可以从正在识别的所有“医疗转介”文档中提取咨询医生的“**电话号码**”。</span><span class="sxs-lookup"><span data-stu-id="0a27e-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="0a27e-113">**邻近度**：描述两个说明之间有多接近。</span><span class="sxs-lookup"><span data-stu-id="0a27e-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="0a27e-114">例如，*街道号码*模式列表会先于*街道名称*短语列表出现，两者之间不设有令牌（你将在本文后面了解令牌）。</span><span class="sxs-lookup"><span data-stu-id="0a27e-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="0a27e-115">使用邻近度类型要求模型中至少有两个说明，否则将禁用该选项。</span><span class="sxs-lookup"><span data-stu-id="0a27e-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="0a27e-116">短语列表</span><span class="sxs-lookup"><span data-stu-id="0a27e-116">Phrase list</span></span>

<span data-ttu-id="0a27e-117">短语列表说明类型通常用于通过模型识别和分类文档。</span><span class="sxs-lookup"><span data-stu-id="0a27e-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="0a27e-118">正如“*咨询医生*”标签示例中所述，它是所标识的文档中一致出现的单词、短语、数字或字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="0a27e-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="0a27e-119">虽然这并不是要求，但如果要捕获的短语位于文档中的一致位置，则可以在“说明”上取得更好的成功。</span><span class="sxs-lookup"><span data-stu-id="0a27e-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="0a27e-120">例如，“*咨询医生*”标签可能一直位于文档中的第一段。</span><span class="sxs-lookup"><span data-stu-id="0a27e-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="0a27e-121">如果标识标签时需要区分大小写，使用短语列表类型可以使你在说明中指定这种情况，只需通过选择“**仅完全匹配的大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0a27e-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![区分大小写](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="0a27e-123">模式列表</span><span class="sxs-lookup"><span data-stu-id="0a27e-123">Pattern lists</span></span>

<span data-ttu-id="0a27e-124">当你创建一个从文档中标识和提取信息的说明时，阵列模式类型特别有用。</span><span class="sxs-lookup"><span data-stu-id="0a27e-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="0a27e-125">它通常以不同的格式显示，如日期、电话号码或信用卡号码。</span><span class="sxs-lookup"><span data-stu-id="0a27e-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="0a27e-126">例如，可按多种不同的格式显示日期（1/1/2020、1-1-2020、01/01/20、01/01/2020、2020 年 1 月 1 日等等）。</span><span class="sxs-lookup"><span data-stu-id="0a27e-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="0a27e-127">通过在你尝试标识和提取的数据中捕获任何可能的变体，定义模式列表使你的说明变得更加高效。</span><span class="sxs-lookup"><span data-stu-id="0a27e-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="0a27e-128">对于“**电话号码** ”示例，从模型识别的所有“医疗转介”文档中提取每个咨询医生的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0a27e-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="0a27e-129">创建说明时，选择”模式列表”类型以便允许返回预期会返回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="0a27e-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![电话号码模式列表](../media/content-understanding/pattern-list.png)

<span data-ttu-id="0a27e-131">在此示例中，选择“**0 - 9 中的任何数字**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0a27e-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="0a27e-132">选择此项可将模式列表中使用的每个 “0” 值识别为从 0 到 9 的任何数字。</span><span class="sxs-lookup"><span data-stu-id="0a27e-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0 - 9 中的任何数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="0a27e-134">同样，如果创建包含文本字符的模式列表，请选择“**a-z 中的任何字母**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0a27e-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="0a27e-135">选择此项可将模式列表中使用的每个 “a” 字符识别为从 “a” 到 “z” 的任何字符。</span><span class="sxs-lookup"><span data-stu-id="0a27e-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="0a27e-136">例如，如果创建“**日期**”模式列表，并且想确保识别出日期格式（如 *Jan 1, 2020*），则需执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a27e-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="0a27e-137">将 *aaa 0, 0000* 和 *aaa 00, 0000* 添加到模式列表中。</span><span class="sxs-lookup"><span data-stu-id="0a27e-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="0a27e-138">确保也选中了 **a-z 中的任何字母**。</span><span class="sxs-lookup"><span data-stu-id="0a27e-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![a-z 中的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="0a27e-140">此外，如果在模式列表中有大写要求，可选择“**仅完全匹配的大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="0a27e-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="0a27e-141">对于“日期”示例，如果需要将月份的第一个字母大写，则需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a27e-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="0a27e-142">将 *Aaa 0, 0000* 和 *Aaa 00, 0000* 添加到模式列表中。</span><span class="sxs-lookup"><span data-stu-id="0a27e-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="0a27e-143">确保也选中了“**仅完全匹配的大写**”。</span><span class="sxs-lookup"><span data-stu-id="0a27e-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![仅完全匹配的大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="0a27e-145">请使用[说明库]()，以便从常见模式列表中使用预制模式列表，如*日期*、*电话号码*、*信用卡号码*等等，而不是手动创建模式列表说明。</span><span class="sxs-lookup"><span data-stu-id="0a27e-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="0a27e-146">邻近度</span><span class="sxs-lookup"><span data-stu-id="0a27e-146">Proximity</span></span> 

<span data-ttu-id="0a27e-147">邻近度说明类型可帮助模型识别数据（通过定义另一份数据与其的接近程度）。</span><span class="sxs-lookup"><span data-stu-id="0a27e-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="0a27e-148">例如，在模型中，你已经定义了两个用于标记客户的“*街道地址编号*”和“*电话号码*”的说明。</span><span class="sxs-lookup"><span data-stu-id="0a27e-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="0a27e-149">此外，你还会注意到客户的电话号码始终出现在街道地址编号的前面。</span><span class="sxs-lookup"><span data-stu-id="0a27e-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="0a27e-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="0a27e-150">Alex Wilburn</span></span><br>
<span data-ttu-id="0a27e-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="0a27e-151">555-555-5555</span></span><br>
<span data-ttu-id="0a27e-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0a27e-152">One Microsoft Way</span></span><br>
<span data-ttu-id="0a27e-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0a27e-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0a27e-154">使用邻近度说明来定义电话号码说明的距离，以便更好地识别文档中的街道地址编号。</span><span class="sxs-lookup"><span data-stu-id="0a27e-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![邻近度说明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="0a27e-156">什么是令牌？</span><span class="sxs-lookup"><span data-stu-id="0a27e-156">What are tokens?</span></span>

<span data-ttu-id="0a27e-157">为使用邻近度说明类型，请理解令牌的含义，因为令牌数目是邻近度说明测量某个说明与另一个说明距离的方法。</span><span class="sxs-lookup"><span data-stu-id="0a27e-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="0a27e-158">令牌是字母和数字的连续跨度结构（不包含空格或标点）。</span><span class="sxs-lookup"><span data-stu-id="0a27e-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="0a27e-159">空格不是令牌。</span><span class="sxs-lookup"><span data-stu-id="0a27e-159">A space is NOT a token.</span></span> <span data-ttu-id="0a27e-160">每个标点字符都是一个令牌。</span><span class="sxs-lookup"><span data-stu-id="0a27e-160">Each punctuation character is a token.</span></span> <span data-ttu-id="0a27e-161">下表显示了一些如何确定短语中令牌数目的示例。</span><span class="sxs-lookup"><span data-stu-id="0a27e-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="0a27e-162">短语</span><span class="sxs-lookup"><span data-stu-id="0a27e-162">Phrase</span></span>|<span data-ttu-id="0a27e-163">令牌的数目</span><span class="sxs-lookup"><span data-stu-id="0a27e-163">Number of tokens</span></span>|<span data-ttu-id="0a27e-164">说明</span><span class="sxs-lookup"><span data-stu-id="0a27e-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="0a27e-165">1</span><span class="sxs-lookup"><span data-stu-id="0a27e-165">1</span></span>|<span data-ttu-id="0a27e-166">单个单词，无标点符号或空格。</span><span class="sxs-lookup"><span data-stu-id="0a27e-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="0a27e-167">1</span><span class="sxs-lookup"><span data-stu-id="0a27e-167">1</span></span>|<span data-ttu-id="0a27e-168">记录定位器的编号。</span><span class="sxs-lookup"><span data-stu-id="0a27e-168">A record locator number.</span></span> <span data-ttu-id="0a27e-169">它可能包含数字和字母，但不包含任何标点符号。</span><span class="sxs-lookup"><span data-stu-id="0a27e-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="0a27e-170">5</span><span class="sxs-lookup"><span data-stu-id="0a27e-170">5</span></span>|<span data-ttu-id="0a27e-171">电话号码。</span><span class="sxs-lookup"><span data-stu-id="0a27e-171">A phone number.</span></span> <span data-ttu-id="0a27e-172">每个标点符号是一个令牌，因此 `425-555-5555` 将是 5 个令牌：</span><span class="sxs-lookup"><span data-stu-id="0a27e-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="0a27e-173">7</span><span class="sxs-lookup"><span data-stu-id="0a27e-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="0a27e-174">配置邻近度说明类型</span><span class="sxs-lookup"><span data-stu-id="0a27e-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="0a27e-175">针对示例，请配置邻近度设置，以便我们可以定义从“*街道地址编号*说明”到“*电话号码*”说明的令牌数量的范围。</span><span class="sxs-lookup"><span data-stu-id="0a27e-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="0a27e-176">应看到最小范围是 “0”，因为电话号码和街道地址编号之间没有令牌。</span><span class="sxs-lookup"><span data-stu-id="0a27e-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="0a27e-177">但是，示例文档中的某些电话号码附加了 *(mobile)*。</span><span class="sxs-lookup"><span data-stu-id="0a27e-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="0a27e-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="0a27e-178">Nestor Wilke</span></span><br>
<span data-ttu-id="0a27e-179">111-111-1111 (mobile)</span><span class="sxs-lookup"><span data-stu-id="0a27e-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="0a27e-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="0a27e-180">One Microsoft Way</span></span><br>
<span data-ttu-id="0a27e-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="0a27e-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="0a27e-182">*(mobile)* 中有三个令牌：</span><span class="sxs-lookup"><span data-stu-id="0a27e-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="0a27e-183">短语</span><span class="sxs-lookup"><span data-stu-id="0a27e-183">Phrase</span></span>|<span data-ttu-id="0a27e-184">令牌计数</span><span class="sxs-lookup"><span data-stu-id="0a27e-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="0a27e-185">(</span><span class="sxs-lookup"><span data-stu-id="0a27e-185">(</span></span>|<span data-ttu-id="0a27e-186">1</span><span class="sxs-lookup"><span data-stu-id="0a27e-186">1</span></span>|
|<span data-ttu-id="0a27e-187">mobile</span><span class="sxs-lookup"><span data-stu-id="0a27e-187">mobile</span></span>|<span data-ttu-id="0a27e-188">2</span><span class="sxs-lookup"><span data-stu-id="0a27e-188">2</span></span>|
|<span data-ttu-id="0a27e-189">)</span><span class="sxs-lookup"><span data-stu-id="0a27e-189">)</span></span>|<span data-ttu-id="0a27e-190">3</span><span class="sxs-lookup"><span data-stu-id="0a27e-190">3</span></span>|

<span data-ttu-id="0a27e-191">配置邻近度设置，以便拥有 0 到 3 的范围。</span><span class="sxs-lookup"><span data-stu-id="0a27e-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![邻近度示例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="0a27e-193">使用说明模板</span><span class="sxs-lookup"><span data-stu-id="0a27e-193">Use explanation templates</span></span>

<span data-ttu-id="0a27e-194">虽然可以手动为说明添加各种模式列表值，但使用说明库中提供的预创建模板可能更容易。</span><span class="sxs-lookup"><span data-stu-id="0a27e-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="0a27e-195">例如，可使用已包含多种模式列表值的“*日期*”模式列表模板，而不用手动添加“*日期*”的所有变体：</span><span class="sxs-lookup"><span data-stu-id="0a27e-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![说明库](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="0a27e-197">说明库包含多种常用的模式列表说明，包括：</span><span class="sxs-lookup"><span data-stu-id="0a27e-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="0a27e-198">日期</span><span class="sxs-lookup"><span data-stu-id="0a27e-198">Date</span></span></br>
- <span data-ttu-id="0a27e-199">日期（数值）</span><span class="sxs-lookup"><span data-stu-id="0a27e-199">Date (numeric)</span></span></br>
- <span data-ttu-id="0a27e-200">时间</span><span class="sxs-lookup"><span data-stu-id="0a27e-200">Time</span></span></br>
- <span data-ttu-id="0a27e-201">号码</span><span class="sxs-lookup"><span data-stu-id="0a27e-201">Number</span></span></br>
- <span data-ttu-id="0a27e-202">电话号码</span><span class="sxs-lookup"><span data-stu-id="0a27e-202">Phone number</span></span></br>
- <span data-ttu-id="0a27e-203">邮政编码</span><span class="sxs-lookup"><span data-stu-id="0a27e-203">Zip code</span></span></br>
- <span data-ttu-id="0a27e-204">一句话的第一个词</span><span class="sxs-lookup"><span data-stu-id="0a27e-204">First word of sentence</span></span></br>
- <span data-ttu-id="0a27e-205">信用卡</span><span class="sxs-lookup"><span data-stu-id="0a27e-205">Credit card</span></span></br>
- <span data-ttu-id="0a27e-206">社会安全号码</span><span class="sxs-lookup"><span data-stu-id="0a27e-206">Social security number</span></span></br>

<span data-ttu-id="0a27e-207">请注意，说明库还包含短语列表说明的模板，包括：</span><span class="sxs-lookup"><span data-stu-id="0a27e-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="0a27e-208">句末</span><span class="sxs-lookup"><span data-stu-id="0a27e-208">End of sentence</span></span>
- <span data-ttu-id="0a27e-209">货币</span><span class="sxs-lookup"><span data-stu-id="0a27e-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="0a27e-210">若要使用说明库中的模板</span><span class="sxs-lookup"><span data-stu-id="0a27e-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="0a27e-211">从模型的“**培训**”页面的“**说明**”部分中，选择“**新建**”，然后选择“**通过模板**”。</span><span class="sxs-lookup"><span data-stu-id="0a27e-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![通过模板创建](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="0a27e-213">在“**说明模板**”页面上，选择要使用的说明，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0a27e-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![选择模板](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="0a27e-215">所选模板的信息将显示在“**创建说明**”页面。</span><span class="sxs-lookup"><span data-stu-id="0a27e-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="0a27e-216">如有必要，编辑说明名称，然后在模式列表中添加或删除项目。</span><span class="sxs-lookup"><span data-stu-id="0a27e-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![编辑模板](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="0a27e-218">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0a27e-218">When finished, select **Save**.</span></span>
