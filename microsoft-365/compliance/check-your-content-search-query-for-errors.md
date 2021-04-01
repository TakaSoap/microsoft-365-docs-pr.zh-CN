---
title: 检查内容搜索查询中是否有错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 了解如何在运行搜索之前检测内容搜索的关键字查询中的错误和拼写错误。
ms.openlocfilehash: 939ac3d227f176a0b74138107ced5dd5b7142bcd
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488209"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="13573-103">检查内容搜索查询中是否有错误</span><span class="sxs-lookup"><span data-stu-id="13573-103">Check your Content Search query for errors</span></span>
  
<span data-ttu-id="13573-104">下面列出了我们检查的不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="13573-104">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="13573-105">不受支持的字符通常隐藏，并且通常会导致搜索错误或返回意外结果。</span><span class="sxs-lookup"><span data-stu-id="13573-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="13573-106">**智能引号** - 不支持智能单引号 (双引号) 也称作"花引号"。</span><span class="sxs-lookup"><span data-stu-id="13573-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="13573-107">只能在搜索查询中使用直双引号。</span><span class="sxs-lookup"><span data-stu-id="13573-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="13573-108">**非打印字符和控制** 字符 - 非打印字符和控制字符不代表书写符号，如字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="13573-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="13573-109">非打印字符和控制字符示例包括设置文本格式的字符或文本换行字符。</span><span class="sxs-lookup"><span data-stu-id="13573-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="13573-110">从左到 **右** 和从右到左标记 - 这些标记是控制字符，用于指示从左到右语言的文本方向 (如英语和西班牙语) 以及从右到左的语言 (如阿拉伯语和希伯来语) 。</span><span class="sxs-lookup"><span data-stu-id="13573-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="13573-111">**小写 Boolean 运算符** - 如果在搜索查询中使用布尔运算符（如 **AND** **、OR** 和 **NOT），** 则它必须是大写。</span><span class="sxs-lookup"><span data-stu-id="13573-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="13573-112">当我们检查查询拼写错误时，查询语法通常指示使用了布尔运算符，即使可能会使用小写运算符;例如，  `(WordA or WordB) and (WordC or WordD)` 。</span><span class="sxs-lookup"><span data-stu-id="13573-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="13573-113">如果查询的字符不受支持，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="13573-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="13573-114">如果在查询中发现不受支持的字符，则会显示一条警告消息，指出找到了不受支持的字符，并建议了替代方法。</span><span class="sxs-lookup"><span data-stu-id="13573-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="13573-115">然后，您可以选择保留原始查询或将其替换为建议的修改后的查询。</span><span class="sxs-lookup"><span data-stu-id="13573-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="13573-116">下面是在单击上一屏幕截图中检查搜索查询的拼写错误后显示的警告消息的示例。</span><span class="sxs-lookup"><span data-stu-id="13573-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="13573-117">请注意，原始查询使用了智能引号和小写 Boolean 运算符。</span><span class="sxs-lookup"><span data-stu-id="13573-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![将显示一条警告消息，并显示查询的建议修订](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="13573-119">如何防止搜索查询中不受支持的字符</span><span class="sxs-lookup"><span data-stu-id="13573-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="13573-120">从其他应用程序 (例如 Microsoft Word 或 Microsoft Excel)  (复制查询或部分查询并将其粘贴到内容搜索的查询页上的关键字框中时，通常会将不受支持的字符添加到查询中。</span><span class="sxs-lookup"><span data-stu-id="13573-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="13573-121">防止出现不受支持的字符的最佳方式是，在关键字框中仅键入查询。</span><span class="sxs-lookup"><span data-stu-id="13573-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="13573-122">也可以从 Word 或 Excel 复制查询，然后将其粘贴到纯文本编辑器（如 Microsoft 记事本）中。</span><span class="sxs-lookup"><span data-stu-id="13573-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="13573-123">保存文本文件，在"**编码"下拉列表中选择"ANSI"。** </span><span class="sxs-lookup"><span data-stu-id="13573-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="13573-124">这会删除所有格式和不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="13573-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="13573-125">然后，便可将文本文件中的查询复制并粘贴到关键字查询框中。</span><span class="sxs-lookup"><span data-stu-id="13573-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
