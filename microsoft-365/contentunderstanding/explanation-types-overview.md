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
ms.localizationpriority: medium
description: 深入了解 Microsoft SharePoint Syntex 中的短语列表、正则表达式和接近度解释类型。
ms.openlocfilehash: 4f155b4a7e6aef9c12b97f56e414de9fcda88536
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152822"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 中的说明类型

说明用于帮助定义要标记的信息并在 Microsoft SharePoint Syntex 中的文档理解模型里进行提取。 创建说明时，需要选择说明类型。 本文将帮助你了解不同的说明类型以及它们的使用方式。

![常见说明窗格（显示三种说明类型）的屏幕截图。](../media/content-understanding/explanation-types.png)

可使用以下说明类型：

- [**短语列表**](#phrase-list)：可在文档中或正在提取的信息中使用的单词、短语、数字或其他字符列表。 例如，文本字符串 *咨询医生* 存在于你正在识别的所有医疗转介文档中。 或者来自正在识别的所有医疗转介文档中咨询医生的“*电话号码*”。

- [**正则表达式**](#regular-expression)：使用模式匹配表示法查找特定的字符模式。 例如，可以使用正则表达式在文档集中查找 *电子邮件地址* 的所有实例。

- [**邻近度**](#proximity)：描述两个说明之间的接近程度。 例如，*街道号码* 短语列表会先于 *街道名称* 短语列表出现，且两者之间不设有令牌（本文稍后部分将介绍令牌）。 使用邻近度类型要求模型中至少有两个说明，否则将禁用该选项。

## <a name="phrase-list"></a>短语列表

短语列表说明类型通常用于通过模型识别和分类文档。 正如“*咨询医生*”标签示例中所述，它是所标识的文档中一致出现的单词、短语、数字或字符的字符串。

虽然不是强制要求，但如果要捕获的短语位于文档中的一致位置，则可以在说明上取得更好的成功。 例如，“*咨询医生*”标签可能一致位于文档中的第一段。 也可以使用 **[配置短语在文档中出现的位置](explanation-types-overview.md#configure-where-phrases-occur-in-the-document)** 高级设置来选择短语所在的特定区域，尤其是在短语可能出现在文档中多个位置的情况下。

如果标识标签时需要区分大小写，使用短语列表类型可以使你在说明中指定这种情况，只需通过选择“**仅完全匹配的大写**”复选框。

![区分大小写。](../media/content-understanding/case-sensitivity.png)

当创建以不同格式识别和提取信息（如日期、电话号码和信用卡号码）的说明时，短语类型尤其有用。 例如，可按多种不同格式显示日期（1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1,2020）。 通过在尝试识别和提取的数据中捕获任何可能的变化，定义短语列表可以让说明变得更加高效。

对于 *电话号码* 示例，你从模型识别的所有医疗转介文档中提取每个咨询医生的电话号码。 创建说明时，请键入电话号码在文档中可能显示的不同格式，以便能够捕捉可能的变化。

![电话号码短语模式。](../media/content-understanding/pattern-list.png)

在此示例中，在“**高级设置**” 中，选择“**0 - 9 中的任何数字**”复选框，以将短语列表中使用的每个“0”值识别为 0 到 9 中的任何数字。

![0 - 9 中的任何数字。](../media/content-understanding/digit-identity.png)

同样，如果创建包含文本字符的短语列表，请选择“**a-z 中的任何字母**”复选框，以将短语列表中使用的每个“a”字符识别为“a”到“z”中的任何字符。

例如，如果创建“**日期**”短语列表，并且想要确保识别出某个日期格式（如 *Jan 1, 2020*），则需执行以下操作：

- 将 *aaa 0, 0000* 和 *aaa 00, 0000* 添加到短语列表中。
- 确保也选中了 **a-z 中的任何字母**。

![a-z 中的任何字母。](../media/content-understanding/any-letter.png)

如果在短语列表中有大写要求，可选择“**仅完全匹配大写**”复选框。 对于日期示例，如果要求月份的第一个字母大写，则需要执行以下操作：

- 将 *Aaa 0, 0000* 和 *Aaa 00, 0000* 添加到短语列表中。
- 确保也选中了“**仅完全匹配的大写**”。

![仅完全匹配的大写。](../media/content-understanding/exact-caps.png)

> [!NOTE]
> 请使用 [说明库](explanation-templates.md)，以使用常见短语列表的短语列表模板，如 *日期*、*电话号码*、*信用卡号码*，而不是手动创建短语列表说明。

## <a name="regular-expression"></a>正则表达式

通过正则表达式类型，可以创建在文档中帮助查找和识别某些文本字符串的模式。 可以使用正则表达式快速分析大量文本，以：

- 查找特定字符模式。
- 验证文本以确保其匹配预定义的模式（如电子邮件地址）。
- 提取、编辑、替换或删除文本字符串。

创建识别和提取不同格式信息（如电子邮件地址、银行账号或 URL）的说明时，短语类型尤其有用。 例如，电子邮件地址（如 megan@contoso.com）以某种格式（“megan”是前半部分，“com”是后半部分）显示。

适用于电子邮件地址的正则表达式为：**[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**。

此表达式包括五个部分，顺序如下：

1. 任何数量的以下字符：

   a. 从 a 到 z 的字母

   b. 从 0-9 的数字

   c. 句点、下划线、百分号或破折号

2. @ 符号

3. 任何数量的与电子邮件地址前半部分相同的字符

4. 一个句点

5. 两个到六个字母

要添加正则表达式说明类型，请：

1. 从“**创建说明**”面板中的“**说明类型**”下面，选择“**正则表达式**”。

   ![显示创建说明面板（已选择正则表达式）的屏幕截图。](../media/content-understanding/create-regular-expression.png)

2. 可以在“**正则表达式**”文本框中键入表达式，或者选择“**从模板中添加正则表达式**”。

   通过使用模板添加正则表达式时，模板自动向文本框添加名称和正则表达式。 例如，如果选择“**电子邮件地址**”模板，则将填充“**创建说明**”面板。

   ![显示创建说明面板（已应用电子邮件地址模板）的屏幕截图。](../media/content-understanding/create-regular-expression-email.png)

### <a name="limitations"></a>限制

下表显示了当前无法用于正则表达式模式的内联字符选项。

|选项  |状态  |当前功能  |
|---------|---------|---------|
|区分大小写 | 当前不受支持。 | 执行的所有匹配均不区分大小写。  |
|线条定位标记     | 当前不受支持。 | 无法指定出现匹配时字符串中的特定位置。   |

## <a name="proximity"></a>邻近度

邻近度说明类型可帮助模型识别数据（通过定义另一份数据与其的接近程度）。 例如，在模型中，假设已经定义了两个用于标记客户的“*街道地址编号*”和“*电话号码*”的说明。

注意客户的电话号码始终出现在街道地址编号的前面。

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

使用邻近度说明来定义电话号码说明的距离，以便更好地识别文档中的街道地址编号。

![邻近度说明。](../media/content-understanding/proximity.png)

> [!NOTE]
> 目前，正则表达式不能与邻近解释类型一起使用。

#### <a name="what-are-tokens"></a>什么是令牌？

要使用邻近度说明类型，需要了解什么是令牌。 令牌数目是邻近度说明测量某个说明与另一个说明距离的方法。 令牌是字母和数字的连续跨度结构（不包含空格或标点）。

下表显示了一些如何确定短语中令牌数目的示例。

|短语|令牌的数目|说明|
|--|--|--|
|`Dog`|1|单个单词，无标点符号或空格。|
|`RMT33W`|1|记录定位器编号。其中可能包含数字和字母，但不包含标点符号。|
|`425-555-5555`|5|电话号码。 每个标点符号是一个令牌，因此 `425-555-5555` 是 5 个令牌：<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>配置邻近度说明类型

针对示例，请配置邻近度设置，以定义从“*街道地址编号*”说明到“*电话号码*”说明的令牌数量的范围。 注意最小范围是“0”，因为电话号码和街道地址编号之间没有令牌。

但示例文档中的某些电话号码附加了 *(mobile)*。

Nestor Wilke<br>
111-111-1111 (mobile)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

*(mobile)* 中有三个令牌：

|短语|令牌计数|
|--|--|
|(|1|
|mobile|2|
|)|3|

配置邻近度设置，以便拥有 0 到 3 的范围。

![邻近度示例。](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a>配置短语在文档中出现的位置

创建说明时，默认情况下在整个文档中搜索尝试提取的短语。 但是，可以使用“**这些短语出现的位置**”高级设置来帮助隔离文档中出现短语的特定位置。 当文档的其他位置可能出现短语的类似实例，而你希望确保选择正确的一个时，此设置非常有用。

以我们的医疗转诊文档为例，文档的第一段中总是会提到 *转诊医生*。 通过“**这些短语出现的位置**”设置，在本示例中，你可以配置说明以仅在文档开头或可能出现该短语的任何其他位置搜索该短语。

![这些短语出现的位置设置。](../media/content-understanding/phrase-location.png)

可以为此设置选择以下选项：

- 文件中的任何位置：将在整个文档中搜索短语。

- 文件开头：从文档开头开始搜索短语。

   ![文件开头。](../media/content-understanding/beginning-of-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 **结束位置** 值将更新以显示所选区域包含的令牌数。 也可以更新“**结束位置**”值，以调整所选区域。

   ![文件开头位置框。](../media/content-understanding/beginning-box.png)

- 文件末尾：从文档末尾到短语位置搜索文档。

   ![文件末尾。](../media/content-understanding/end-of-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 **开始位置** 值将更新以显示所选区域包含的令牌数。 也可以更新开始位置值以调整所选区域。

   ![文件末尾位置框。](../media/content-understanding/end-box.png)

- 自定义范围：搜索文档的指定范围查找短语位置。

   ![自定义范围。](../media/content-understanding/custom-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 对于此设置，需要选择一个 **开始** 和 **结束** 位置。 这些值表示从文档开头开始的令牌数。 尽管可以手动输入这些值，但在查看器中手动调整选择框更加方便。

### <a name="see-also"></a>另请参阅

[在 SharePoint Syntex 中使用解释模板](explanation-templates.md)