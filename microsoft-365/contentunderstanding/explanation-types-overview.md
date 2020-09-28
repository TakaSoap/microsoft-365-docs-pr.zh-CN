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
# <a name="introduction-to-explanation-types"></a>解释类型简介

使用说明可帮助定义要标记的信息，并在文档中提取 Microsoft SharePoint Syntex 的理解模型。 创建说明时，请务必选择 "说明类型"。 

本文可帮助您了解不同的说明类型及其使用方法。

   ![解释类型](../media/content-understanding/explanation-types.png) 
   
可以使用以下说明类型：

- **短语列表**：可以在要提取的文档中使用的单词、短语、数字或其他字符的列表。 例如，文本字符串指的 **医生** 位于您要标识的所有医学参考文档中。</br>

- "**模式" 列表**：列出数字、字母或其他字符的模式，您可以使用这些字符来标识要提取的信息。 例如，您可以从您要标识的所有医学参考文档中提取参考医生的 **电话号码** 。</br>

- **邻近度**：介绍了彼此之间的接近说明。 例如， *街道号码* 模式列表将在 " *街道名称* 短语" 列表中进行，在 (之间没有令牌，您将在本文后面的部分中了解令牌) 。 
 
## <a name="phrase-list"></a>短语列表

短语列表解释类型通常用于通过模型标识文档并对其进行分类。 如 " *推荐医生* 标签" 示例中所述，它是您要标识的文档中一致的单词、短语、数字或字符的字符串。

虽然不是要求，但如果您正在捕获的短语位于文档中的一致位置，则可以获得更好的成功说明。 例如，" *引用地址* " 标签可能始终位于文档的第一段。

如果在标识标签时需要区分大小写，则使用短语列表类型可以通过选中 " **唯一的完全大写** " 复选框，在您的说明中指定它。

   ![区分大小写](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>模式列表

当您创建用于标识和提取文档中的信息的说明时，模式列表类型尤其有用。 它通常以不同的格式显示，如日期、电话号码或信用卡号码。 例如，可以使用多种不同的格式显示日期， (1/1/2020、1-1-2020、01/01/20、01/01/2020、Jan 1、2020等 ) 。 通过在您尝试识别和提取的数据中捕获任何可能的变体，定义模式列表可以提高您的说明效率。 

对于 " **电话号码** " 示例，请从该模型标识的所有医学参考文档中提取每个引用地址的电话号码。 创建说明时，请选择 "模式" 列表类型以允许您可能会返回的不同格式。

   ![电话号码模式列表](../media/content-understanding/pattern-list.png)

对于此示例，请选中 " **0-9 中的任意数字** " 复选框。 如果选择此项，则会将模式列表中使用的每个 "0" 值识别为从0到9的任意数字。

   ![0-9 中的任何数字](../media/content-understanding/digit-identity.png)

同样，如果创建包含文本字符的模式列表，请从 a-z 复选框中选择 " **任意字母** "。 如果选择此项，则会将模式列表中使用的每个 "a" 字符识别为从 "a" 到 "z" 的任意字符。

例如，如果您创建了一个 **日期** 模式列表，并且您希望确保识别的日期格式（例如 *，2020年1月1日）* ，则需要执行以下操作：
- 将 *aaa 0、0000* 和 *aaa 00、0000* 添加到 "图案" 列表中。
- 请确保也选择 **了 a-z 中的任何字母** 。

   ![A-z 中的任何字母](../media/content-understanding/any-letter.png)

此外，如果在 "模式" 列表中有大小写要求，则可以选择 " **仅精确大写** " 复选框。 对于日期示例，如果需要将月份的第一个字母大写，则需要执行以下操作：

- 将 *Aaa 0、0000* 和 *Aaa 00、0000* 添加到 "图案" 列表中。
- 请确保只选择了 **精确的大写** 。

   ![仅精确大写](../media/content-understanding/exact-caps.png)

> [!NOTE]
> 不是手动创建模式列表说明，而是使用 [说明库]() 将预置的模式列表模板用于常见模式列表，如 *日期*、 *电话号码*、 *信用卡号*等。 

## <a name="proximity"></a>邻近度 

邻近度说明类型可帮助您的模型定义与另一条数据的接近程度的关系，从而识别数据。 例如，在您的模型中，定义了两个说明，用于标记客户 *街道地址编号* 和 *电话号码*。 

此外，还请注意，客户电话号码始终显示在街道地址号码之前。 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond，WA 98034<br>

使用邻近度说明来定义电话号码解释的距离，以便更好地标识文档中的街道地址号码。

   ![邻近性说明](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>什么是标记？

若要使用邻近性说明类型，请了解令牌的数目，因为标记的数目是近似说明如何测量从一个解释到另一个的距离。  

令牌是连续范围 (不) 字母和数字的空格或标点符号。 空格不是一个令牌。 每个标点字符都是一个令牌。 下表显示了如何确定短语中的标记数的一些示例。

|关键词|令牌数|说明|
|--|--|--|
|`Dog`|1 |一个不带标点符号或空格的单词。|
|`RMT33W`|1 |记录定位器编号。 它可能包含数字和字母，但不包含任何标点。|
|`425-555-5555`|5 |一个电话号码。 每个标点符号都是一个单独的令牌，因此  `425-555-5555` 是5个令牌：<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>配置邻近度说明类型

对于此示例，请配置邻近度设置，以便我们可以定义 *电话号码* 解释为 " *街道地址号码* " 说明中的令牌数量的范围。

您应该会看到，由于电话号码和街道地址号码之间没有令牌，因此最小范围为 "0"。

但是，示例文档中的一些电话号码追加 * (移动) *中。

Nestor Wilke<br>
111-111-1111 (移动) <br>
One Microsoft Way<br>
Redmond，WA 98034<br>

* (移动) *中有三个令牌：

|关键词|令牌计数|
|--|--|
|(|1 |
|流动|2 |
|)|3 |

将 "邻近度" 设置配置为介于0到3之间的范围。

   ![邻近感应示例](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>使用解释库

虽然您可以手动添加各种模式列表值以用于解释，但在解释库中使用提供给您的预先创建的模板要容易得多。

例如，不是手动添加 *日期*的所有变体，而是使用已包含多种模式列表值的 *日期*的模式列表模板：</br>

   ![解释库](../media/content-understanding/explanation-template.png)</br>
 
解释库包含许多常用的模式列表说明，包括：</br>

- Date</br>
- 日期 (数值) </br>
- Time</br>
- 数字</br>
- 电话号码</br>
- 邮政编码</br>
- 句子的第一个单词</br>
- 信用卡</br>
- 社会安全号码</br>

请注意，说明库也包含短语列表解释的模板，包括：
- 句末
- 货币

#### <a name="to-use-a-template-from-the-explanation-library"></a>使用解释库中的模板

1. 从模型**火车**页面的 "**说明**" 部分，选择 "**新建**"，然后选择 "**从模板**"。</br>

   ![从模板创建](../media/content-understanding/from-template.png)</br>

2.  在 " **说明模板** " 页上，选择要使用的说明，然后选择 " **添加**"。</br>

       ![选择模板](../media/content-understanding/phone-template.png)</br>

3. 您选择的模板信息将显示在 " **创建说明** " 页面上。 如果需要，请编辑说明名称，并在 "模式" 列表中添加或删除项目。 </br> 

   ![编辑模板](../media/content-understanding/phone-template-live.png)</br>

4. 完成后，选择 " **保存**"。
