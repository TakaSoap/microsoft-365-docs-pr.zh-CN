---
title: 解释类型
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解有关 Microsoft SharePoint Syntex 中的解释类型的详细信息
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295738"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="1a484-103">解释类型简介</span><span class="sxs-lookup"><span data-stu-id="1a484-103">Introduction to explanation types</span></span>

<span data-ttu-id="1a484-104">使用说明可帮助定义要标记的信息，并在文档中提取 Microsoft SharePoint Syntex 的理解模型。</span><span class="sxs-lookup"><span data-stu-id="1a484-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="1a484-105">创建说明时，请务必选择 "说明类型"。</span><span class="sxs-lookup"><span data-stu-id="1a484-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="1a484-106">本文可帮助您了解不同的说明类型及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="1a484-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![解释类型](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="1a484-108">可以使用以下说明类型：</span><span class="sxs-lookup"><span data-stu-id="1a484-108">These explanation types are available:</span></span>

- <span data-ttu-id="1a484-109">**短语列表**：可以在要提取的文档中使用的单词、短语、数字或其他字符的列表。</span><span class="sxs-lookup"><span data-stu-id="1a484-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="1a484-110">例如，文本字符串指的 **医生** 位于您要标识的所有医学参考文档中。</span><span class="sxs-lookup"><span data-stu-id="1a484-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="1a484-111">"**模式" 列表**：列出数字、字母或其他字符的模式，您可以使用这些字符来标识要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="1a484-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="1a484-112">例如，您可以从您要标识的所有医学参考文档中提取参考医生的 **电话号码** 。</span><span class="sxs-lookup"><span data-stu-id="1a484-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="1a484-113">**邻近度**：介绍了彼此之间的接近说明。</span><span class="sxs-lookup"><span data-stu-id="1a484-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="1a484-114">例如， *街道号码* 模式列表将在 " *街道名称* 短语" 列表中进行，在 (之间没有令牌，您将在本文后面的部分中了解令牌) 。</span><span class="sxs-lookup"><span data-stu-id="1a484-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="1a484-115">短语列表</span><span class="sxs-lookup"><span data-stu-id="1a484-115">Phrase list</span></span>

<span data-ttu-id="1a484-116">短语列表解释类型通常用于通过模型标识文档并对其进行分类。</span><span class="sxs-lookup"><span data-stu-id="1a484-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="1a484-117">如 " *推荐医生* 标签" 示例中所述，它是您要标识的文档中一致的单词、短语、数字或字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="1a484-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="1a484-118">虽然不是要求，但如果您正在捕获的短语位于文档中的一致位置，则可以获得更好的成功说明。</span><span class="sxs-lookup"><span data-stu-id="1a484-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="1a484-119">例如，" *引用地址* " 标签可能始终位于文档的第一段。</span><span class="sxs-lookup"><span data-stu-id="1a484-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="1a484-120">如果在标识标签时需要区分大小写，则使用短语列表类型可以通过选中 " **唯一的完全大写** " 复选框，在您的说明中指定它。</span><span class="sxs-lookup"><span data-stu-id="1a484-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![区分大小写](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="1a484-122">模式列表</span><span class="sxs-lookup"><span data-stu-id="1a484-122">Pattern lists</span></span>

<span data-ttu-id="1a484-123">当您创建用于标识和提取文档中的信息的说明时，模式列表类型尤其有用。</span><span class="sxs-lookup"><span data-stu-id="1a484-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="1a484-124">它通常以不同的格式显示，如日期、电话号码或信用卡号码。</span><span class="sxs-lookup"><span data-stu-id="1a484-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="1a484-125">例如，可以使用多种不同的格式显示日期， (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020等 ) 。</span><span class="sxs-lookup"><span data-stu-id="1a484-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="1a484-126">通过在您尝试识别和提取的数据中捕获任何可能的变体，定义模式列表可以提高您的说明效率。</span><span class="sxs-lookup"><span data-stu-id="1a484-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="1a484-127">对于 " **电话号码** " 示例，请从该模型标识的所有医学参考文档中提取每个引用地址的电话号码。</span><span class="sxs-lookup"><span data-stu-id="1a484-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="1a484-128">创建说明时，请选择 "模式" 列表类型以允许您可能会返回的不同格式。</span><span class="sxs-lookup"><span data-stu-id="1a484-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![电话号码模式列表](../media/content-understanding/pattern-list.png)

<span data-ttu-id="1a484-130">对于此示例，请选中 " **0-9 中的任意数字** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="1a484-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="1a484-131">如果选择此项，则会将模式列表中使用的每个 "0" 值识别为从0到9的任意数字。</span><span class="sxs-lookup"><span data-stu-id="1a484-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0-9 中的任何数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="1a484-133">同样，如果创建包含文本字符的模式列表，请从 a-z 复选框中选择 " **任意字母** "。</span><span class="sxs-lookup"><span data-stu-id="1a484-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="1a484-134">如果选择此项，则会将模式列表中使用的每个 "a" 字符识别为从 "a" 到 "z" 的任意字符。</span><span class="sxs-lookup"><span data-stu-id="1a484-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="1a484-135">例如，如果您创建了一个 **日期** 模式列表，并且您希望确保识别的日期格式（例如 *，2020年1月1日）* ，则需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a484-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="1a484-136">将 *aaa 0、0000* 和 *aaa 00、0000* 添加到 "图案" 列表中。</span><span class="sxs-lookup"><span data-stu-id="1a484-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1a484-137">请确保也选择 **了 a-z 中的任何字母** 。</span><span class="sxs-lookup"><span data-stu-id="1a484-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A-z 中的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="1a484-139">此外，如果在 "模式" 列表中有大小写要求，则可以选择 " **仅精确大写** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="1a484-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="1a484-140">对于日期示例，如果需要将月份的第一个字母大写，则需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a484-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="1a484-141">将 *Aaa 0、0000* 和 *Aaa 00、0000* 添加到 "图案" 列表中。</span><span class="sxs-lookup"><span data-stu-id="1a484-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1a484-142">请确保只选择了 **精确的大写** 。</span><span class="sxs-lookup"><span data-stu-id="1a484-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![仅精确大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="1a484-144">不是手动创建模式列表说明，而是使用 [说明库]() 将预置的模式列表模板用于常见模式列表，如 *日期*、 *电话号码*、 *信用卡号*等。</span><span class="sxs-lookup"><span data-stu-id="1a484-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="1a484-145">邻近度</span><span class="sxs-lookup"><span data-stu-id="1a484-145">Proximity</span></span> 

<span data-ttu-id="1a484-146">邻近度说明类型可帮助您的模型定义与另一条数据的接近程度的关系，从而识别数据。</span><span class="sxs-lookup"><span data-stu-id="1a484-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="1a484-147">例如，在您的模型中，定义了两个说明，用于标记客户 *街道地址编号* 和 *电话号码*。</span><span class="sxs-lookup"><span data-stu-id="1a484-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="1a484-148">此外，还请注意，客户电话号码始终显示在街道地址号码之前。</span><span class="sxs-lookup"><span data-stu-id="1a484-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="1a484-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="1a484-149">Alex Wilburn</span></span><br>
<span data-ttu-id="1a484-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="1a484-150">555-555-5555</span></span><br>
<span data-ttu-id="1a484-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1a484-151">One Microsoft Way</span></span><br>
<span data-ttu-id="1a484-152">Redmond，WA 98034</span><span class="sxs-lookup"><span data-stu-id="1a484-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1a484-153">使用邻近度说明来定义电话号码解释的距离，以便更好地标识文档中的街道地址号码。</span><span class="sxs-lookup"><span data-stu-id="1a484-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![邻近性说明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="1a484-155">什么是标记？</span><span class="sxs-lookup"><span data-stu-id="1a484-155">What are tokens?</span></span>

<span data-ttu-id="1a484-156">若要使用邻近性说明类型，请了解令牌的数目，因为标记的数目是近似说明如何测量从一个解释到另一个的距离。</span><span class="sxs-lookup"><span data-stu-id="1a484-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="1a484-157">令牌是连续范围 (不) 字母和数字的空格或标点符号。</span><span class="sxs-lookup"><span data-stu-id="1a484-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="1a484-158">空格不是一个令牌。</span><span class="sxs-lookup"><span data-stu-id="1a484-158">A space is NOT a token.</span></span> <span data-ttu-id="1a484-159">每个标点字符都是一个令牌。</span><span class="sxs-lookup"><span data-stu-id="1a484-159">Each punctuation character is a token.</span></span> <span data-ttu-id="1a484-160">下表显示了如何确定短语中的标记数的一些示例。</span><span class="sxs-lookup"><span data-stu-id="1a484-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="1a484-161">关键词</span><span class="sxs-lookup"><span data-stu-id="1a484-161">Phrase</span></span>|<span data-ttu-id="1a484-162">令牌数</span><span class="sxs-lookup"><span data-stu-id="1a484-162">Number of tokens</span></span>|<span data-ttu-id="1a484-163">说明</span><span class="sxs-lookup"><span data-stu-id="1a484-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="1a484-164">1 </span><span class="sxs-lookup"><span data-stu-id="1a484-164">1</span></span>|<span data-ttu-id="1a484-165">一个不带标点符号或空格的单词。</span><span class="sxs-lookup"><span data-stu-id="1a484-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="1a484-166">1 </span><span class="sxs-lookup"><span data-stu-id="1a484-166">1</span></span>|<span data-ttu-id="1a484-167">记录定位器编号。</span><span class="sxs-lookup"><span data-stu-id="1a484-167">A record locator number.</span></span> <span data-ttu-id="1a484-168">它可能包含数字和字母，但不包含任何标点。</span><span class="sxs-lookup"><span data-stu-id="1a484-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="1a484-169">5 </span><span class="sxs-lookup"><span data-stu-id="1a484-169">5</span></span>|<span data-ttu-id="1a484-170">一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="1a484-170">A phone number.</span></span> <span data-ttu-id="1a484-171">每个标点符号都是一个单独的令牌，因此  `425-555-5555` 是5个令牌：</span><span class="sxs-lookup"><span data-stu-id="1a484-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="1a484-172">7 </span><span class="sxs-lookup"><span data-stu-id="1a484-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="1a484-173">配置邻近度说明类型</span><span class="sxs-lookup"><span data-stu-id="1a484-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="1a484-174">对于此示例，请配置邻近度设置，以便我们可以定义 *电话号码* 解释为 " *街道地址号码* " 说明中的令牌数量的范围。</span><span class="sxs-lookup"><span data-stu-id="1a484-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="1a484-175">您应该会看到，由于电话号码和街道地址号码之间没有令牌，因此最小范围为 "0"。</span><span class="sxs-lookup"><span data-stu-id="1a484-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="1a484-176">但是，示例文档中的一些电话号码追加 \* (移动) \*中。</span><span class="sxs-lookup"><span data-stu-id="1a484-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="1a484-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="1a484-177">Nestor Wilke</span></span><br>
<span data-ttu-id="1a484-178">111-111-1111 (移动) </span><span class="sxs-lookup"><span data-stu-id="1a484-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="1a484-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1a484-179">One Microsoft Way</span></span><br>
<span data-ttu-id="1a484-180">Redmond，WA 98034</span><span class="sxs-lookup"><span data-stu-id="1a484-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1a484-181">\* (移动) \*中有三个令牌：</span><span class="sxs-lookup"><span data-stu-id="1a484-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="1a484-182">关键词</span><span class="sxs-lookup"><span data-stu-id="1a484-182">Phrase</span></span>|<span data-ttu-id="1a484-183">令牌计数</span><span class="sxs-lookup"><span data-stu-id="1a484-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="1a484-184">(</span><span class="sxs-lookup"><span data-stu-id="1a484-184">(</span></span>|<span data-ttu-id="1a484-185">1 </span><span class="sxs-lookup"><span data-stu-id="1a484-185">1</span></span>|
|<span data-ttu-id="1a484-186">流动</span><span class="sxs-lookup"><span data-stu-id="1a484-186">mobile</span></span>|<span data-ttu-id="1a484-187">2 </span><span class="sxs-lookup"><span data-stu-id="1a484-187">2</span></span>|
|<span data-ttu-id="1a484-188">)</span><span class="sxs-lookup"><span data-stu-id="1a484-188">)</span></span>|<span data-ttu-id="1a484-189">3 </span><span class="sxs-lookup"><span data-stu-id="1a484-189">3</span></span>|

<span data-ttu-id="1a484-190">将 "邻近度" 设置配置为介于0到3之间的范围。</span><span class="sxs-lookup"><span data-stu-id="1a484-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![邻近感应示例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="1a484-192">使用解释库</span><span class="sxs-lookup"><span data-stu-id="1a484-192">Use the explanation library</span></span>

<span data-ttu-id="1a484-193">虽然您可以手动添加各种模式列表值以用于解释，但在解释库中使用提供给您的预先创建的模板要容易得多。</span><span class="sxs-lookup"><span data-stu-id="1a484-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="1a484-194">例如，不是手动添加 *日期*的所有变体，而是使用已包含多种模式列表值的 *日期*的模式列表模板：</span><span class="sxs-lookup"><span data-stu-id="1a484-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![解释库](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="1a484-196">解释库包含许多常用的模式列表说明，包括：</span><span class="sxs-lookup"><span data-stu-id="1a484-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="1a484-197">Date</span><span class="sxs-lookup"><span data-stu-id="1a484-197">Date</span></span></br>
- <span data-ttu-id="1a484-198">日期 (数值) </span><span class="sxs-lookup"><span data-stu-id="1a484-198">Date (numeric)</span></span></br>
- <span data-ttu-id="1a484-199">Time</span><span class="sxs-lookup"><span data-stu-id="1a484-199">Time</span></span></br>
- <span data-ttu-id="1a484-200">数字</span><span class="sxs-lookup"><span data-stu-id="1a484-200">Number</span></span></br>
- <span data-ttu-id="1a484-201">电话号码</span><span class="sxs-lookup"><span data-stu-id="1a484-201">Phone number</span></span></br>
- <span data-ttu-id="1a484-202">邮政编码</span><span class="sxs-lookup"><span data-stu-id="1a484-202">Zip code</span></span></br>
- <span data-ttu-id="1a484-203">句子的第一个单词</span><span class="sxs-lookup"><span data-stu-id="1a484-203">First word of sentence</span></span></br>
- <span data-ttu-id="1a484-204">信用卡</span><span class="sxs-lookup"><span data-stu-id="1a484-204">Credit card</span></span></br>
- <span data-ttu-id="1a484-205">社会安全号码</span><span class="sxs-lookup"><span data-stu-id="1a484-205">Social security number</span></span></br>

<span data-ttu-id="1a484-206">请注意，说明库也包含短语列表解释的模板，包括：</span><span class="sxs-lookup"><span data-stu-id="1a484-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="1a484-207">句末</span><span class="sxs-lookup"><span data-stu-id="1a484-207">End of sentence</span></span>
- <span data-ttu-id="1a484-208">货币</span><span class="sxs-lookup"><span data-stu-id="1a484-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="1a484-209">使用解释库中的模板</span><span class="sxs-lookup"><span data-stu-id="1a484-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="1a484-210">从模型**火车**页面的 "**说明**" 部分，选择 "**新建**"，然后选择 "**从模板**"。</span><span class="sxs-lookup"><span data-stu-id="1a484-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![从模板创建](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="1a484-212">在 " **说明模板** " 页上，选择要使用的说明，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="1a484-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![选择模板](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="1a484-214">您选择的模板信息将显示在 " **创建说明** " 页面上。</span><span class="sxs-lookup"><span data-stu-id="1a484-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="1a484-215">如果需要，请编辑说明名称，并在 "模式" 列表中添加或删除项目。</span><span class="sxs-lookup"><span data-stu-id="1a484-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![编辑模板](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="1a484-217">完成后，选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1a484-217">When finished, select **Save**.</span></span>
