---
title: 在 Microsoft SharePoint Syntex 中使用解释模板
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
description: 了解更多关于如何在 Microsoft SharePoint Syntex 中使用和保存解释模板。
ms.openlocfilehash: 87d151a3dc0863b880515abb6ee59d3691d9e4c6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172235"
---
# <a name="use-explanation-templates-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中使用解释模板

可手动添加各个短语列表值进行解释，但使用解释库中提供模板更为轻松。

例如，可以使用 *日期* 的短语列表模板添加 *日期* 的所有变体，而不是通过手动添加，因为模板中已包含许多短语列表值：

![说明库。](../media/content-understanding/explanation-template.png)

说明库包含常用的 *短语列表* 说明，包括：

- 日期：日历日期，所有格式。 包括文本和数字（例如，“2020 年 12 月 9 日”）。
- 日期（数值）：日历日期，所有格式。 包含数字（例如 1-11-2020）。
- 时间: 12 小时和 24 小时格式。
- 数字：正数和负数（最多 2 位小数）。
- 百分比：表示百分比的模式列表。 例如，1%、11%、100% 或 11.11%。
- 电话号码：常用的美国和国际格式。 例如，000 000 0000、000-000-0000、(000)000-0000 或 (000) 000-0000。
- 邮政编码：美国邮政编码格式。 例如，11111、11111-1111。
- 句首词：最多 9 个字符单词的常用模式。
- 句尾：句子结尾的常用标点符号。
- 信用卡：常用的信用卡卡号格式。 例如，1111-1111-1111-1111。
- 社会安全号码：美国社会安全号码格式。例如，111-11-1111。
- 复选框: 表示已填充复选框上变体的短语列表。例如，_X_，_ _X_。
- 货币：主要国际符号。 例如：$。
- 电子邮件抄送：带有术语“CC：”的短语列表，通常位于邮件发送给的其他人员或组的姓名或电子邮件地址附近。
- 电子邮件日期：带有术语“发送于：”的短语列表，通常位于发送电子邮件日期附近。
- 电子邮件问候语：电子邮件的常见打开行。
- 电子邮件收件人：带有术语“收件人：”的短语列表，通常位于邮件发送到的人员或组的姓名或电子邮件地址附近。
- 电子邮件发件人：带有术语“发件人：”的短语列表，通常位于发件人姓名或电子邮件地址附近。
- 电子邮件主题：带有术语“主题：”的短语列表，通常位于电子邮件的主题附近。

说明库还包含常用的 *正则表达式* 说明，包括：

- 6 位到 17 位数字: 匹配任何长度为 6 到 17 位的数字。 美国银行账号适合此模式。
- 电子邮件地址：匹配常见类型的电子邮件地址，如 meganb@contoso.com。
- 美国纳税人 ID 编号：匹配以 9 开头的 3 位数字，后跟以 7 或 8 开头的 6 位数字
- Web 地址 (URL)：匹配以 http://或 https:// 开头的 web 地址格式。

此外，说明库还包含三种自动模板类型，用于处理示例文件中标记的数据：

- 标记后：示例文件中标签后发生的字词或字符。
- 标签之前：示例文件中标签前发生的字词或字符。
- 标签：示例文件前 10 个标签。

为提供自动模板工作方式的示例，以下示例文件中将使用“标签之前”说明模板，以帮助向模型提供更多信息，从而获得更准确的匹配。

![示例文件。](../media/content-understanding/before-label.png)

选择标签之前说明模板时，将查找示例文件中标签之前显示的第一组字词。 在示例中，第一个示例文件中标识的字词集为“截至”。

![在标签模板之前。](../media/content-understanding/before-label-explanation.png)

可选择" **添加** 模板创建解释。 添加更多示例文件时，将在短语列表中标识并添加其他字词。

![添加标签。](../media/content-understanding/before-label-add.png)

## <a name="use-a-template-from-the-explanation-library"></a>使用说明库中的模板

1. 在模型的 **“培训”** 页面的 **“说明”** 部分中，选择 **“新建”**，然后选择 **“来自模板”**。

   ![添加前标签。](../media/content-understanding/from-template.png)

2.  在“**说明模板**”页面上，选择要使用的说明，然后选择“**添加**”。

    ![选择模板。](../media/content-understanding/phone-template.png)

3. 所选模板的信息显示在“**创建说明**”页面。 如果需要，可编辑解释名称，并从短语列表中添加或删除项目。

    ![编辑模板。](../media/content-understanding/phone-template-live.png)

4. 完成后，选择“**保存**”。

## <a name="save-a-template-to-the-explanation-library"></a>保存模版到说明库

可以将说明另存为模板，使其在内容中心的解释库中可用，以便与其他模型一起使用。 该模板将包括说明的基本和高级设置，但说明短语在文档中显示位置的选项除外。

> [!NOTE]
> 只有短语列表和正则表达式的解释可以保存为模板。

1. 在模型 **“培训”** 页面的 **“说明”** 部分:

   a. 从说明列表中，选择要另存为模板的说明。

   b. 选择 **“保存为模板”**。

    ![“解释”部分的屏幕截图显示了“另存为”模板选项。](../media/content-understanding/explanation-save-as-template.png)

2. 在 **保存说明模板** 页面:

   a. 在 **名称** 部分中，根据需要重命名说明。

   b. 在 **描述** 部分中，添加说明让其他人了解如何使用说明。

   c. 选择“**保存**”。

    ![“保存说明模板”页面的屏幕截图。](../media/content-understanding/save-explanation-template.png)

### <a name="see-also"></a>另请参阅

[SharePoint Syntex 中的说明类型](explanation-types-overview.md)