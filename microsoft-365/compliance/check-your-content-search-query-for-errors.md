---
title: 检查内容搜索查询中是否有错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 了解如何在运行搜索之前检测关键字查询中的错误和打字错误。
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818091"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="e15a2-103">检查内容搜索查询中是否有错误</span><span class="sxs-lookup"><span data-stu-id="e15a2-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="e15a2-104">当您创建或编辑内容搜索时，可以使用 Microsoft 365 检查您对不受支持的字符和小写 Boolean 运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="e15a2-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="e15a2-105">如何操作？</span><span class="sxs-lookup"><span data-stu-id="e15a2-105">How?</span></span> <span data-ttu-id="e15a2-106">只需在内容搜索的 "查询" 页上单击 "**检查查询以查找打字错误**"。</span><span class="sxs-lookup"><span data-stu-id="e15a2-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![单击 "检查查询是否输入拼写" 以检查不受支持的字符的搜索查询](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="e15a2-108">下面列出了我们检查的不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="e15a2-109">不受支持的字符通常是隐藏的，它们通常会导致搜索错误或返回意外的结果。</span><span class="sxs-lookup"><span data-stu-id="e15a2-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="e15a2-110">**智能引号**-不支持智能化单引号和双引号（也称为 "弯引号"）。</span><span class="sxs-lookup"><span data-stu-id="e15a2-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="e15a2-111">只能在搜索查询中使用直双引号。</span><span class="sxs-lookup"><span data-stu-id="e15a2-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="e15a2-112">**非打印字符和控制字符**-非打印字符和控制字符不代表写入的符号，如字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="e15a2-113">非打印字符和控制字符示例包括设置文本格式的字符或文本换行字符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="e15a2-114">**从左到右和从右到左标记**-这些标记是用于指明从左到右语言（如英语和西班牙语）和从右到左语言（如阿拉伯语和希伯来语）的文字方向的控制字符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="e15a2-115">**小写布尔运算符**-如果在搜索查询中使用布尔运算符，例如**AND**、 **OR**和**NOT** ，则它必须为大写。</span><span class="sxs-lookup"><span data-stu-id="e15a2-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="e15a2-116">当我们检查输入拼写的查询时，查询语法通常会指示是否使用了布尔运算符，即使可能使用了小写运算符也是如此。例如， `(WordA or WordB) and (WordC or WordD)` 。</span><span class="sxs-lookup"><span data-stu-id="e15a2-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="e15a2-117">如果查询包含不受支持的字符，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e15a2-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="e15a2-118">如果在查询中找到不受支持的字符，则会显示一条警告消息，指出找到了不受支持的字符，并提出了替代方法。</span><span class="sxs-lookup"><span data-stu-id="e15a2-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="e15a2-119">然后，您可以选择保留原始查询或将其替换为建议的修订后的查询。</span><span class="sxs-lookup"><span data-stu-id="e15a2-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="e15a2-120">下面的示例展示了在上一屏幕截图中单击搜索查询的 "**检查查询是否录入**" 后显示的警告消息。</span><span class="sxs-lookup"><span data-stu-id="e15a2-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="e15a2-121">请注意，原始查询包含智能引号和小写布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![将显示一条警告消息，其中包含查询的建议修订](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="e15a2-123">如何在搜索查询中阻止不受支持的字符</span><span class="sxs-lookup"><span data-stu-id="e15a2-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="e15a2-124">当您从其他应用程序（如 Microsoft Word 或 Microsoft Excel）复制查询或查询的某些部分并将其粘贴到内容搜索的查询页面上的关键字框中时，通常会将不受支持的字符添加到查询中。</span><span class="sxs-lookup"><span data-stu-id="e15a2-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="e15a2-125">防止出现不受支持的字符的最佳方式是，在关键字框中仅键入查询。</span><span class="sxs-lookup"><span data-stu-id="e15a2-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="e15a2-126">或者，您可以从 Word 或 Excel 复制查询，然后将其粘贴到纯文本编辑器（如 Microsoft 记事本）中。</span><span class="sxs-lookup"><span data-stu-id="e15a2-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="e15a2-127">保存文本文件，并在 "**编码**" 下拉列表中选择 " **ANSI** "。</span><span class="sxs-lookup"><span data-stu-id="e15a2-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="e15a2-128">这会删除所有格式和不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="e15a2-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="e15a2-129">然后，便可将文本文件中的查询复制并粘贴到关键字查询框中。</span><span class="sxs-lookup"><span data-stu-id="e15a2-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
