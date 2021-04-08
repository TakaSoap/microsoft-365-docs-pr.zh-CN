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
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604401"
---
# <a name="introduction-to-explanation-types"></a>说明类型简介

说明用于帮助定义要标记的信息并在 Microsoft SharePoint Syntex 中的文档理解模型里进行提取。 创建说明时，需要选择说明类型。 本文将帮助你了解不同的说明类型以及它们的使用方式。 

![说明类型](../media/content-understanding/explanation-types.png) 
   
可使用以下说明类型：

- **短语列表**：可在文档中使用的单词、短语、数字或其他字符的列表，或是正在提取的信息。 例如，文本字符串“**咨询医生**”存在于你正在识别的所有“医疗转介”文档中。 或者来自正在识别的所有“医疗转介”文档中的咨询医生的“**电话号码**”。

- **邻近度**：描述两个说明之间的接近程度。 例如，*街道号码* 短语列表会先于 *街道名称* 短语列表出现，且两者之间不设有令牌（本文稍后部分将介绍令牌）。 使用邻近度类型要求模型中至少有两个说明，否则将禁用该选项。 
 
## <a name="phrase-list"></a>短语列表

短语列表说明类型通常用于通过模型识别和分类文档。 正如“*咨询医生*”标签示例中所述，它是所标识的文档中一致出现的单词、短语、数字或字符的字符串。

虽然这并不是强制要求，但如果要捕获的短语位于文档中的一致位置，则可以在“说明”上取得更好的成功。 例如，“*咨询医生*”标签可能一直位于文档中的第一段。 也可以使用 **[配置短语在文档中出现的位置](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** 高级设置来选择短语所在的特定区域，尤其是在短语可能出现在文档中多个位置的情况下。

如果标识标签时需要区分大小写，使用短语列表类型可以使你在说明中指定这种情况，只需通过选择“**仅完全匹配的大写**”复选框。

![区分大小写](../media/content-understanding/case-sensitivity.png) 

当创建以不同格式识别和提取信息（如日期、电话号码和信用卡号码）的说明时，短语类型尤其有用。 例如，可按多种不同的格式显示日期（1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1,2020 等等）。 通过在你尝试识别和提取的数据中捕获任何可能的变化，定义短语列表可以使你的说明变得更加高效。 

对于 **电话号码** 示例，你从模型识别的所有“医疗转介”文档中提取每个咨询医生的电话号码。 创建说明时，请键入电话号码在文档中可能显示的不同格式，以便能够捕捉可能的变化。 

![电话号码短语模式](../media/content-understanding/pattern-list.png)

在此示例中，在“**高级设置**” 中，选择“**0 - 9 中的任何数字**”复选框，以将短语列表中使用的每个“0”值识别为 0 到 9 中的任何数字。

![0 - 9 中的任何数字](../media/content-understanding/digit-identity.png)

同样，如果创建包含文本字符的短语列表，请选择“**a-z 中的任何字母**”复选框，以将短语列表中使用的每个“a”字符识别为“a”到“z”中的任何字符。

例如，如果创建“**日期**”短语列表，并且想要确保识别出某个日期格式（如 *Jan 1, 2020*），则需执行以下操作：
- 将 *aaa 0, 0000* 和 *aaa 00, 0000* 添加到短语列表中。
- 确保也选中了 **a-z 中的任何字母**。

![a-z 中的任何字母](../media/content-understanding/any-letter.png)

此外，如果在短语列表中有大写要求，可选择“**仅完全匹配大写**”复选框。 对于“日期”示例，如果需要月份的第一个字母大写，则需要执行以下操作：

- 将 *Aaa 0, 0000* 和 *Aaa 00, 0000* 添加到短语列表中。
- 确保也选中了“**仅完全匹配的大写**”。

![仅完全匹配的大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> 请使用 [说明库](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates)，以便使用常见短语列表的短语列表模板，如 *日期*、*电话号码*、*信用卡号码* 等等，而不是手动创建短语列表说明。

## <a name="proximity"></a>邻近度 

邻近度说明类型可帮助模型识别数据（通过定义另一份数据与其的接近程度）。 例如，在模型中，你已经定义了两个用于标记客户的“*街道地址编号*”和“*电话号码*”的说明。 

注意客户的电话号码始终出现在街道地址编号的前面。 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

使用邻近度说明来定义电话号码说明的距离，以便更好地识别文档中的街道地址编号。

![邻近度说明](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a>什么是令牌？

为使用邻近度说明类型，需理解令牌的含义，因为令牌数目是邻近度说明测量某个说明与另一个说明距离的方法。 令牌是字母和数字的连续跨度结构（不包含空格或标点）。 

下表显示了一些如何确定短语中令牌数目的示例。

|短语|令牌的数目|说明|
|--|--|--|
|`Dog`|1|单个单词，无标点符号或空格。|
|`RMT33W`|1|记录定位器的编号。 它可能包含数字和字母，但不包含标点符号。|
|`425-555-5555`|5|电话号码。 每个标点符号是一个令牌，因此 `425-555-5555` 是 5 个令牌：<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

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

![邻近度示例](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a>配置短语在文档中出现的位置

创建说明时，默认情况下会在整个文档中搜索要提取的短语。 但是，可以使用“**这些短语出现的位置**”高级设置来帮助隔离文档中出现短语的特定位置。 这适用于文档的其他位置可能出现短语的类似实例，而你希望确保选择正确短语的情况。 以我们的医疗转诊文档为例，文档的第一段中总是会提到 **转诊医生**。 在此示例中，使用**这些短语出现的位置设置，可以配置说明，以仅在文档开头或可能出现该短语的任何其他位置搜索此标签。

![“这些短语出现的位置”设置](../media/content-understanding/phrase-location.png)

可以为此设置选择以下选项：

- 文件中的任何位置：将在整个文档中搜索短语。

- 文件开头：从文档开头开始搜索短语。

   ![文件开头](../media/content-understanding/beginning-of-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 **结束位置** 值将更新以显示所选区域包含的令牌数。 请注意，可以更新“结束位置”值并调整所选区域。

   ![文件开头位置框](../media/content-understanding/beginning-box.png)

- 文件末尾：从文档末尾到短语位置搜索文档。

   ![文件末尾](../media/content-understanding/end-of-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 **开始位置** 值将更新以显示所选区域包含的令牌数。 请注意，可以更新“开始位置”值并调整所选区域。

   ![文件末尾位置框](../media/content-understanding/end-box.png)

- 自定义范围：在文档内的指定范围内搜索短语位置。

   ![自定义范围](../media/content-understanding/custom-file.png)

    在查看器中，可以手动调整选择框以包括出现短语的位置。 对于此设置，需要选择一个 **开始** 和 **结束** 位置。 这些值表示从文档开头开始的令牌数。 尽管可以手动输入这些值，但在查看器中手动调整选择框更容易。 
   
## <a name="use-explanation-templates"></a>使用说明模板

可手动添加各个短语列表值进行解释，但使用解释库中提供模板更为轻松。

例如，可以使用 *Date* 的短语列表模板来手动添加 *Date* 的所有变体，因为它已包含许多短语列表值：

![说明库](../media/content-understanding/explanation-template.png)
 
解释库包含常用的短语列表说明，包括：

- 日期：日历日期，所有格式。 包括文本和数字（例如，“2020 年 12 月 9 日”）。
- 日期（数值）：日历日期，所有格式。 包含数字（例如 1-11-2020）。
- 时间：12 和 24 小时格式。
- 数字：正数和负数（最多 2 位小数）。 
- 百分比：表示百分比的模式列表。 例如，1%、11%、100%、11.11% 等。
- 电话号码：常用的美国和国际格式。 例如，000 000 0000、000-000-0000、(000)000-0000、(000) 000-0000 等。
- 邮政编码：美国邮政编码格式。 例如，11111、11111-1111。
- 句首词：最多 9 个字符单词的常用模式。 
- 句尾：句子结尾的常用标点符号
- 信用卡：常用的信用卡卡号格式。 例如，1111-1111-1111-1111。 
- 社会安全号码：美国社会安全号码格式。 例如，111-11-1111。 
- 复选框：表示已填充复选框上变体的短语列表。 例如，_X_、_ _X_ 等。
- 货币：主要国际符号。 例如：$。 
- 电子邮件抄送：带有术语“CC：”的短语列表，通常位于邮件发送给的其他人员或组的姓名或电子邮件地址附近。
- 电子邮件日期：带有术语“发送于：”的短语列表，通常位于发送电子邮件日期附近。
- 电子邮件问候语：电子邮件的常见打开行。
- 电子邮件收件人：带有术语“收件人：”的短语列表，通常位于邮件发送到的人员或组的姓名或电子邮件地址附近。 
- 电子邮件发件人：带有术语“发件人：”的短语列表，通常位于发件人姓名或电子邮件地址附近。 
- 电子邮件主题：带有术语“主题：”的短语列表，通常位于电子邮件的主题附近。 

说明库还包含三种自动模板类型，用于处理示例文件中标记的数据：

- 标记后：示例文件中标签后发生的字词或字符。
- 标签之前：示例文件中标签前发生的字词或字符。
- 标签：示例文件前 10 个标签。

为提供自动模板工作方式的示例，以下示例文件中将使用"之前的标签"说明模板，帮助为模型提供更多信息，以获得更准确的匹配。

![示例文件](../media/content-understanding/before-label.png)

选择"标签之前"说明模板时，它将查找示例文件中标签前显示的第一组字词。 在示例中，第一个示例文件中标识的字词为"截至"。

![标签模板之前](../media/content-understanding/before-label-explanation.png)

可选择" **添加** 模板创建解释。  添加更多示例文件时，将在短语列表中标识并添加其他字词。

![添加标签](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a>若要使用说明库中的模板

1. 从模型的“**培训**”页面的“**说明**”部分中，选择“**新建**”，然后选择“**通过模板**”。

   ![添加前标签](../media/content-understanding/from-template.png)

2.  在“**说明模板**”页面上，选择要使用的说明，然后选择“**添加**”。

    ![选择模板](../media/content-understanding/phone-template.png)

3. 所选模板的信息显示在“**创建说明**”页面。 如果需要，可编辑解释名称，并从短语列表中添加或删除项目。  

    ![编辑模板](../media/content-understanding/phone-template-live.png)

4. 完成后，选择“**保存**”。