---
title: Microsoft SharePoint Syntex 中的说明类型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex 中的说明类型。
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706547"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="5f4e4-103">Microsoft SharePoint Syntex 中的说明类型</span><span class="sxs-lookup"><span data-stu-id="5f4e4-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="5f4e4-104">说明用于帮助定义要标记的信息并在 Microsoft SharePoint Syntex 中的文档理解模型里进行提取。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="5f4e4-105">创建说明时，需要选择说明类型。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="5f4e4-106">本文将帮助你了解不同的说明类型以及它们的使用方式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-106">This article helps you understand the different explanation types and how they're used.</span></span>

![常见说明窗格（显示三种说明类型）的屏幕截图。](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="5f4e4-108">可使用以下说明类型：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-108">These explanation types are available:</span></span>

- <span data-ttu-id="5f4e4-109">[**短语列表**](#phrase-list)：可在文档中或正在提取的信息中使用的单词、短语、数字或其他字符列表。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="5f4e4-110">例如，文本字符串 *咨询医生* 存在于你正在识别的所有医疗转介文档中。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="5f4e4-111">或者来自正在识别的所有医疗转介文档中咨询医生的“*电话号码*”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="5f4e4-112">[**正则表达式**](#regular-expression)：使用模式匹配表示法查找特定的字符模式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="5f4e4-113">例如，可以使用正则表达式在文档集中查找 *电子邮件地址* 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="5f4e4-114">[**邻近度**](#proximity)：描述两个说明之间的接近程度。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="5f4e4-115">例如，*街道号码* 短语列表会先于 *街道名称* 短语列表出现，且两者之间不设有令牌（本文稍后部分将介绍令牌）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="5f4e4-116">使用邻近度类型要求模型中至少有两个说明，否则将禁用该选项。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="5f4e4-117">短语列表</span><span class="sxs-lookup"><span data-stu-id="5f4e4-117">Phrase list</span></span>

<span data-ttu-id="5f4e4-118">短语列表说明类型通常用于通过模型识别和分类文档。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="5f4e4-119">正如“*咨询医生*”标签示例中所述，它是所标识的文档中一致出现的单词、短语、数字或字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="5f4e4-120">虽然不是强制要求，但如果要捕获的短语位于文档中的一致位置，则可以在说明上取得更好的成功。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="5f4e4-121">例如，“*咨询医生*”标签可能一致位于文档中的第一段。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="5f4e4-122">也可以使用 **[配置短语在文档中出现的位置](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** 高级设置来选择短语所在的特定区域，尤其是在短语可能出现在文档中多个位置的情况下。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="5f4e4-123">如果标识标签时需要区分大小写，使用短语列表类型可以使你在说明中指定这种情况，只需通过选择“**仅完全匹配的大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![区分大小写](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="5f4e4-125">当创建以不同格式识别和提取信息（如日期、电话号码和信用卡号码）的说明时，短语类型尤其有用。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="5f4e4-126">例如，可按多种不同格式显示日期（1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1,2020）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="5f4e4-127">通过在尝试识别和提取的数据中捕获任何可能的变化，定义短语列表可以让说明变得更加高效。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="5f4e4-128">对于 *电话号码* 示例，你从模型识别的所有医疗转介文档中提取每个咨询医生的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="5f4e4-129">创建说明时，请键入电话号码在文档中可能显示的不同格式，以便能够捕捉可能的变化。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![电话号码短语模式](../media/content-understanding/pattern-list.png)

<span data-ttu-id="5f4e4-131">在此示例中，在“**高级设置**” 中，选择“**0 - 9 中的任何数字**”复选框，以将短语列表中使用的每个“0”值识别为 0 到 9 中的任何数字。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![0 - 9 中的任何数字](../media/content-understanding/digit-identity.png)

<span data-ttu-id="5f4e4-133">同样，如果创建包含文本字符的短语列表，请选择“**a-z 中的任何字母**”复选框，以将短语列表中使用的每个“a”字符识别为“a”到“z”中的任何字符。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="5f4e4-134">例如，如果创建“**日期**”短语列表，并且想要确保识别出某个日期格式（如 *Jan 1, 2020*），则需执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="5f4e4-135">将 *aaa 0, 0000* 和 *aaa 00, 0000* 添加到短语列表中。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="5f4e4-136">确保也选中了 **a-z 中的任何字母**。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![a-z 中的任何字母](../media/content-understanding/any-letter.png)

<span data-ttu-id="5f4e4-138">如果在短语列表中有大写要求，可选择“**仅完全匹配大写**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="5f4e4-139">对于日期示例，如果要求月份的第一个字母大写，则需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="5f4e4-140">将 *Aaa 0, 0000* 和 *Aaa 00, 0000* 添加到短语列表中。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="5f4e4-141">确保也选中了“**仅完全匹配的大写**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![仅完全匹配的大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="5f4e4-143">请使用 [说明库](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates)，以使用常见短语列表的短语列表模板，如 *日期*、*电话号码*、*信用卡号码*，而不是手动创建短语列表说明。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="5f4e4-144">正则表达式</span><span class="sxs-lookup"><span data-stu-id="5f4e4-144">Regular expression</span></span>

<span data-ttu-id="5f4e4-145">通过正则表达式类型，可以创建在文档中帮助查找和识别某些文本字符串的模式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="5f4e4-146">可以使用正则表达式快速分析大量文本，以：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="5f4e4-147">查找特定字符模式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-147">Find specific character patterns.</span></span>
- <span data-ttu-id="5f4e4-148">验证文本以确保其匹配预定义的模式（如电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="5f4e4-149">提取、编辑、替换或删除文本字符串。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="5f4e4-150">创建识别和提取不同格式信息（如电子邮件地址、银行账号或 URL）的说明时，短语类型尤其有用。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="5f4e4-151">例如，电子邮件地址（如 megan@contoso.com）以某种格式（“megan”是前半部分，“com”是后半部分）显示。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="5f4e4-152">适用于电子邮件地址的正则表达式为：**[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="5f4e4-153">此表达式包括五个部分，顺序如下：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="5f4e4-154">任何数量的以下字符：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="5f4e4-155">a.</span><span class="sxs-lookup"><span data-stu-id="5f4e4-155">a.</span></span> <span data-ttu-id="5f4e4-156">从 a 到 z 的字母</span><span class="sxs-lookup"><span data-stu-id="5f4e4-156">Letters from a to z</span></span>

   <span data-ttu-id="5f4e4-157">b.</span><span class="sxs-lookup"><span data-stu-id="5f4e4-157">b.</span></span> <span data-ttu-id="5f4e4-158">从 0-9 的数字</span><span class="sxs-lookup"><span data-stu-id="5f4e4-158">Numbers from 0-9</span></span>

   <span data-ttu-id="5f4e4-159">c.</span><span class="sxs-lookup"><span data-stu-id="5f4e4-159">c.</span></span> <span data-ttu-id="5f4e4-160">句点、下划线、百分号或破折号</span><span class="sxs-lookup"><span data-stu-id="5f4e4-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="5f4e4-161">@ 符号</span><span class="sxs-lookup"><span data-stu-id="5f4e4-161">The @ symbol</span></span>

3. <span data-ttu-id="5f4e4-162">任何数量的与电子邮件地址前半部分相同的字符</span><span class="sxs-lookup"><span data-stu-id="5f4e4-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="5f4e4-163">一个句点</span><span class="sxs-lookup"><span data-stu-id="5f4e4-163">A period</span></span>

5. <span data-ttu-id="5f4e4-164">两个到六个字母</span><span class="sxs-lookup"><span data-stu-id="5f4e4-164">Two to six letters</span></span>

<span data-ttu-id="5f4e4-165">要添加正则表达式说明类型，请：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="5f4e4-166">从“**创建说明**”面板中的“**说明类型**”下面，选择“**正则表达式**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![显示创建说明面板（已选择正则表达式）的屏幕截图。](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="5f4e4-168">可以在“**正则表达式**”文本框中键入表达式，或者选择“**从模板中添加正则表达式**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="5f4e4-169">通过使用模板添加正则表达式时，模板自动向文本框添加名称和正则表达式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="5f4e4-170">例如，如果选择“**电子邮件地址**”模板，则将填充“**创建说明**”面板。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![显示创建说明面板（已应用电子邮件地址模板）的屏幕截图。](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="5f4e4-172">邻近度</span><span class="sxs-lookup"><span data-stu-id="5f4e4-172">Proximity</span></span> 

<span data-ttu-id="5f4e4-173">邻近度说明类型可帮助模型识别数据（通过定义另一份数据与其的接近程度）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="5f4e4-174">例如，在模型中，假设已经定义了两个用于标记客户的“*街道地址编号*”和“*电话号码*”的说明。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="5f4e4-175">注意客户的电话号码始终出现在街道地址编号的前面。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="5f4e4-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="5f4e4-176">Alex Wilburn</span></span><br>
<span data-ttu-id="5f4e4-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="5f4e4-177">555-555-5555</span></span><br>
<span data-ttu-id="5f4e4-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="5f4e4-178">One Microsoft Way</span></span><br>
<span data-ttu-id="5f4e4-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="5f4e4-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="5f4e4-180">使用邻近度说明来定义电话号码说明的距离，以便更好地识别文档中的街道地址编号。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![邻近度说明](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="5f4e4-182">什么是令牌？</span><span class="sxs-lookup"><span data-stu-id="5f4e4-182">What are tokens?</span></span>

<span data-ttu-id="5f4e4-183">要使用邻近度说明类型，需要了解什么是令牌。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="5f4e4-184">令牌数目是邻近度说明测量某个说明与另一个说明距离的方法。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="5f4e4-185">令牌是字母和数字的连续跨度结构（不包含空格或标点）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="5f4e4-186">下表显示了一些如何确定短语中令牌数目的示例。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="5f4e4-187">短语</span><span class="sxs-lookup"><span data-stu-id="5f4e4-187">Phrase</span></span>|<span data-ttu-id="5f4e4-188">令牌的数目</span><span class="sxs-lookup"><span data-stu-id="5f4e4-188">Number of tokens</span></span>|<span data-ttu-id="5f4e4-189">说明</span><span class="sxs-lookup"><span data-stu-id="5f4e4-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="5f4e4-190">1</span><span class="sxs-lookup"><span data-stu-id="5f4e4-190">1</span></span>|<span data-ttu-id="5f4e4-191">单个单词，无标点符号或空格。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="5f4e4-192">1</span><span class="sxs-lookup"><span data-stu-id="5f4e4-192">1</span></span>|<span data-ttu-id="5f4e4-193">记录定位器的编号。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-193">A record locator number.</span></span> <span data-ttu-id="5f4e4-194">它可能包含数字和字母，但不包含标点符号。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="5f4e4-195">5</span><span class="sxs-lookup"><span data-stu-id="5f4e4-195">5</span></span>|<span data-ttu-id="5f4e4-196">电话号码。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-196">A phone number.</span></span> <span data-ttu-id="5f4e4-197">每个标点符号是一个令牌，因此 `425-555-5555` 是 5 个令牌：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="5f4e4-198">7</span><span class="sxs-lookup"><span data-stu-id="5f4e4-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="5f4e4-199">配置邻近度说明类型</span><span class="sxs-lookup"><span data-stu-id="5f4e4-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="5f4e4-200">针对示例，请配置邻近度设置，以定义从“*街道地址编号*”说明到“*电话号码*”说明的令牌数量的范围。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="5f4e4-201">注意最小范围是“0”，因为电话号码和街道地址编号之间没有令牌。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="5f4e4-202">但示例文档中的某些电话号码附加了 *(mobile)*。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="5f4e4-203">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="5f4e4-203">Nestor Wilke</span></span><br>
<span data-ttu-id="5f4e4-204">111-111-1111 (mobile)</span><span class="sxs-lookup"><span data-stu-id="5f4e4-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="5f4e4-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="5f4e4-205">One Microsoft Way</span></span><br>
<span data-ttu-id="5f4e4-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="5f4e4-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="5f4e4-207">*(mobile)* 中有三个令牌：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="5f4e4-208">短语</span><span class="sxs-lookup"><span data-stu-id="5f4e4-208">Phrase</span></span>|<span data-ttu-id="5f4e4-209">令牌计数</span><span class="sxs-lookup"><span data-stu-id="5f4e4-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="5f4e4-210">(</span><span class="sxs-lookup"><span data-stu-id="5f4e4-210">(</span></span>|<span data-ttu-id="5f4e4-211">1</span><span class="sxs-lookup"><span data-stu-id="5f4e4-211">1</span></span>|
|<span data-ttu-id="5f4e4-212">mobile</span><span class="sxs-lookup"><span data-stu-id="5f4e4-212">mobile</span></span>|<span data-ttu-id="5f4e4-213">2</span><span class="sxs-lookup"><span data-stu-id="5f4e4-213">2</span></span>|
|<span data-ttu-id="5f4e4-214">)</span><span class="sxs-lookup"><span data-stu-id="5f4e4-214">)</span></span>|<span data-ttu-id="5f4e4-215">3</span><span class="sxs-lookup"><span data-stu-id="5f4e4-215">3</span></span>|

<span data-ttu-id="5f4e4-216">配置邻近度设置，以便拥有 0 到 3 的范围。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![邻近度示例](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="5f4e4-218">配置短语在文档中出现的位置</span><span class="sxs-lookup"><span data-stu-id="5f4e4-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="5f4e4-219">创建说明时，默认情况下在整个文档中搜索尝试提取的短语。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="5f4e4-220">但是，可以使用“**这些短语出现的位置**”高级设置来帮助隔离文档中出现短语的特定位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="5f4e4-221">当文档的其他位置可能出现短语的类似实例，而你希望确保选择正确的一个时，此设置非常有用。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="5f4e4-222">以我们的医疗转诊文档为例，文档的第一段中总是会提到 *转诊医生*。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="5f4e4-223">通过“**这些短语出现的位置**”设置，在本示例中，你可以配置说明以仅在文档开头或可能出现该短语的任何其他位置搜索该短语。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![“这些短语出现的位置”设置](../media/content-understanding/phrase-location.png)

<span data-ttu-id="5f4e4-225">可以为此设置选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="5f4e4-226">文件中的任何位置：将在整个文档中搜索短语。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="5f4e4-227">文件开头：从文档开头开始搜索短语。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![文件开头](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="5f4e4-229">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="5f4e4-230">**结束位置** 值将更新以显示所选区域包含的令牌数。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="5f4e4-231">也可以更新“**结束位置**”值，以调整所选区域。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![文件开头位置框](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="5f4e4-233">文件末尾：从文档末尾到短语位置搜索文档。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![文件末尾](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="5f4e4-235">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="5f4e4-236">**开始位置** 值将更新以显示所选区域包含的令牌数。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="5f4e4-237">也可以更新开始位置值以调整所选区域。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![文件末尾位置框](../media/content-understanding/end-box.png)

- <span data-ttu-id="5f4e4-239">自定义范围：搜索文档的指定范围查找短语位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![自定义范围](../media/content-understanding/custom-file.png)

    <span data-ttu-id="5f4e4-241">在查看器中，可以手动调整选择框以包括出现短语的位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="5f4e4-242">对于此设置，需要选择一个 **开始** 和 **结束** 位置。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="5f4e4-243">这些值表示从文档开头开始的令牌数。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="5f4e4-244">尽管可以手动输入这些值，但在查看器中手动调整选择框更加方便。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="5f4e4-245">使用说明模板</span><span class="sxs-lookup"><span data-stu-id="5f4e4-245">Use explanation templates</span></span>

<span data-ttu-id="5f4e4-246">可手动添加各个短语列表值进行解释，但使用解释库中提供模板更为轻松。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="5f4e4-247">例如，可以使用 *日期* 的短语列表模板添加 *日期* 的所有变体，而不是通过手动添加，因为模板中已包含许多短语列表值：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![说明库](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="5f4e4-249&quot;>说明库包含常用的 *短语列表* 说明，包括：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5f4e4-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;5f4e4-250&quot;>日期：日历日期，所有格式。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5f4e4-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;5f4e4-251&quot;>包括文本和数字（例如，“2020 年 12 月 9 日”）。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;5f4e4-251&quot;>Includes text and numbers (for example, &quot;Dec 9, 2020").</span></span>
- <span data-ttu-id="5f4e4-252">日期（数值）：日历日期，所有格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="5f4e4-253">包含数字（例如 1-11-2020）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="5f4e4-254">时间：12 和 24 小时格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="5f4e4-255">数字：正数和负数（最多 2 位小数）。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="5f4e4-256">百分比：表示百分比的模式列表。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="5f4e4-257">例如，1%、11%、100% 或 11.11%。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="5f4e4-258">电话号码：常用的美国和国际格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="5f4e4-259">例如，000 000 0000、000-000-0000、(000)000-0000 或 (000) 000-0000。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="5f4e4-260">邮政编码：美国邮政编码格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="5f4e4-261">例如，11111、11111-1111。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="5f4e4-262">句首词：最多 9 个字符单词的常用模式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="5f4e4-263">句尾：句子结尾的常用标点符号。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="5f4e4-264">信用卡：常用的信用卡卡号格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="5f4e4-265">例如，1111-1111-1111-1111。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="5f4e4-p132">社会安全号码：美国社会安全号码格式。例如，111-11-1111。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="5f4e4-268">复选框：表示已填充复选框上变体的短语列表。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="5f4e4-269">例如，_X_、_ _X_。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="5f4e4-270">货币：主要国际符号。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-270">Currency: Major international symbols.</span></span> <span data-ttu-id="5f4e4-271">例如：$。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-271">For example, $.</span></span> 
- <span data-ttu-id="5f4e4-272">电子邮件抄送：带有术语“CC：”的短语列表，通常位于邮件发送给的其他人员或组的姓名或电子邮件地址附近。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="5f4e4-273">电子邮件日期：带有术语“发送于：”的短语列表，通常位于发送电子邮件日期附近。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="5f4e4-274">电子邮件问候语：电子邮件的常见打开行。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="5f4e4-275">电子邮件收件人：带有术语“收件人：”的短语列表，通常位于邮件发送到的人员或组的姓名或电子邮件地址附近。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="5f4e4-276">电子邮件发件人：带有术语“发件人：”的短语列表，通常位于发件人姓名或电子邮件地址附近。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="5f4e4-277">电子邮件主题：带有术语“主题：”的短语列表，通常位于电子邮件的主题附近。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="5f4e4-278">说明库还包含常用的 *正则表达式* 说明，包括：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="5f4e4-279">6 到 17 位数字：匹配任何长度为 6 到 17 位的数字。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="5f4e4-280">美国银行账号适合此模式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="5f4e4-281">电子邮件地址：匹配常见类型的电子邮件地址，如 meganb@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="5f4e4-282">美国纳税人 ID 编号：匹配以 9 开头的 3 位数字，后跟以 7 或 8 开头的 6 位数字</span><span class="sxs-lookup"><span data-stu-id="5f4e4-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="5f4e4-283">Web 地址 (URL)：匹配以 http://或 https:// 开头的 web 地址格式。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="5f4e4-284">此外，说明库还包含三种自动模板类型，用于处理示例文件中标记的数据：</span><span class="sxs-lookup"><span data-stu-id="5f4e4-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="5f4e4-285">标记后：示例文件中标签后发生的字词或字符。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="5f4e4-286">标签之前：示例文件中标签前发生的字词或字符。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="5f4e4-287">标签：示例文件前 10 个标签。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="5f4e4-288">为提供自动模板工作方式的示例，以下示例文件中将使用“标签之前”说明模板，以帮助向模型提供更多信息，从而获得更准确的匹配。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![示例文件](../media/content-understanding/before-label.png)

<span data-ttu-id="5f4e4-290">选择标签之前说明模板时，将查找示例文件中标签之前显示的第一组字词。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="5f4e4-291">在示例中，第一个示例文件中标识的字词为"截至"。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![标签模板之前](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="5f4e4-293">可选择" **添加** 模板创建解释。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="5f4e4-294">添加更多示例文件时，将在短语列表中标识并添加其他字词。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![添加标签](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="5f4e4-296">若要使用说明库中的模板</span><span class="sxs-lookup"><span data-stu-id="5f4e4-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="5f4e4-297">从模型的“**培训**”页面的“**说明**”部分中，选择“**新建**”，然后选择“**通过模板**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![添加前标签](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="5f4e4-299">在“**说明模板**”页面上，选择要使用的说明，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![选择模板](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="5f4e4-301">所选模板的信息显示在“**创建说明**”页面。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="5f4e4-302">如果需要，可编辑解释名称，并从短语列表中添加或删除项目。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![编辑模板](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="5f4e4-304">完成后，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-304">When finished, select **Save**.</span></span>