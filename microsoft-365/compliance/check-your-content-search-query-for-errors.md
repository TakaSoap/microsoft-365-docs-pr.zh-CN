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
description: 了解如何在运行搜索之前检测内容搜索的关键字查询中的错误和拼写错误。
ms.openlocfilehash: 296f30f5332165017f5c7ccebc35c0663041718d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470442"
---
# <a name="check-your-content-search-query-for-errors"></a>检查内容搜索查询中是否有错误
  
下面列出了我们检查的不受支持的字符。 不受支持的字符通常隐藏，并且通常会导致搜索错误或返回意外结果。
  
- **智能引号** - 不支持智能单引号 (双引号) 也称作"花引号"。 只能在搜索查询中使用直双引号。 

- **非打印字符和控制** 字符 - 非打印字符和控制字符不代表书写符号，如字母数字字符。 非打印字符和控制字符示例包括设置文本格式的字符或文本换行字符。 

- 从左到 **右** 和从右到左标记 - 这些标记是控制字符，用于指示从左到右语言的文本方向 (如英语和西班牙语) 以及从右到左的语言 (如阿拉伯语和希伯来语) 。

- **小写 Boolean 运算符** - 如果在搜索查询中使用布尔运算符（如 **AND** **、OR** 和 **NOT），** 则它必须是大写。 当我们检查查询拼写错误时，查询语法通常指示使用了布尔运算符，即使可能会使用小写运算符;例如，  `(WordA or WordB) and (WordC or WordD)` 。

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查询的字符不受支持，会发生什么情况？

如果在查询中发现不受支持的字符，则会显示一条警告消息，指出找到了不受支持的字符，并建议了替代方法。 然后，您可以选择保留原始查询或将其替换为建议的修改后的查询。

下面是在单击上一屏幕截图中检查搜索查询的拼写错误后显示的警告消息的示例。 请注意，原始查询使用了智能引号和小写 Boolean 运算符。
  
![将显示一条警告消息，并显示查询的建议修订](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何防止搜索查询中不受支持的字符

从其他应用程序 (例如 Microsoft Word 或 Microsoft Excel)  (复制查询或部分查询并将其粘贴到内容搜索的查询页上的关键字框中时，通常会将不受支持的字符添加到查询中。 防止出现不受支持的字符的最佳方式是，在关键字框中仅键入查询。 也可以从 Word 或 Excel 复制查询，然后将其粘贴到纯文本编辑器（如 Microsoft 记事本）中。 保存文本文件，在"**编码"下拉列表中选择"ANSI"。**  这会删除所有格式和不受支持的字符。 然后，便可将文本文件中的查询复制并粘贴到关键字查询框中。 
