---
title: 了解可训练的分类器
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 可Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的正面和负面示例来识别各种类型的内容。 对分类器进行培训后，您确认其结果准确无误。 然后，使用它搜索组织的内容，并进行分类以应用保留或敏感度标签，或将其包括在 DLP 策略或保留策略 (数据丢失) 中。
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114048"
---
# <a name="learn-about-trainable-classifiers"></a>了解可训练的分类器

对内容进行分类和标记，以便可以保护和正确处理内容是信息保护规范的起点。 Microsoft 365三种方法对内容进行分类。

## <a name="manually"></a>手动

此方法需要人为判断和操作。 管理员可以使用预先存在的标签和敏感信息类型，也可以创建自己的标签和敏感信息类型，然后发布它们。 用户和管理员在遇到内容时将其应用于内容。 然后，您可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此分类机制类别包括按以下方法查找内容：

- 关键字或元数据值 (关键字查询语言) 。
- 使用之前标识的敏感信息模式，如社会保险、信用卡或银行帐户 ([敏感信息类型实体定义) 。 ](sensitive-information-type-entity-definitions.md)
- 识别项，因为它是模板上的变体 ([文档手指) 。 ](document-fingerprinting.md)
- 使用存在确切字符串 ([数据完全匹配) 。 ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

然后，可以自动应用敏感度和保留标签，使内容可供在了解数据丢失防护策略[](dlp-learn-about-dlp.md)和自动应用保留) 策略中[使用](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分类器

此分类方法特别适用于无法通过手动或自动模式匹配方法轻松标识的内容。 这种分类方法更多的是训练一个分类器，以根据项目是什么来识别项目，而不是通过项目中的元素（模式匹配）。 分类器通过查看对分类感兴趣的内容的数百个示例来了解如何识别内容类型。 首先馈送该类别中肯定属于该类别的示例。 处理这些示例后，通过提供匹配和非匹配示例的组合来测试它。 然后，分类器将预测任何给定项目是否属于你正在构建的类别。 然后确认其结果，对真正的正数、负数、误报和漏报进行排序，以帮助提高预测的准确性。 

发布分类器时，分类器会按 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。 发布分类器后，可以继续使用与初始培训过程类似的反馈流程对分类器进行培训。

### <a name="where-you-can-use-trainable-classifiers"></a>在哪里可以使用可训练分类器
内置分类器和可训练分类器都作为一个条件，Office敏感度标签[](apply-sensitivity-label-automatically.md)自动标记，根据条件和通信合规性自动应用保留[标签策略](communication-compliance.md)。 [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) 

敏感度标签可以使用分类器作为条件，请参阅自动将 [敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分类器仅适用于未加密且使用英语的项目。

## <a name="types-of-classifiers"></a>分类器的类型

- **预先训练的分类** 器 - Microsoft 已创建大量分类器，并对这些分类器进行预先训练，无需培训即可开始使用这些分类器。 这些分类器将显示为 状态 `Ready to use` 。
- **自定义分类** 器 - 如果你的分类需求超出了预先训练的分类器涵盖范围，可以创建并训练自己的分类器。

### <a name="pre-trained-classifiers"></a>预先训练的分类器

Microsoft 365五个预先训练的分类器：

> [!CAUTION]
> 我们弃用冒犯性 **语言** 预先训练的分类器，因为它一直产生大量误报。 请勿使用，如果当前正在使用，应将业务流程从其中移开。 我们建议改为使用 **威胁**、**亵亵和****骚扰** 预先训练的分类器。

- **简历**：检测是收信人个人、教育、专业资格、工作体验和其他个人识别信息的文本帐户的项目
- **源代码 ：** 检测包含一组使用前 25 种使用计算机编程语言编写的指令和语句GitHub
    - ActionScript
    - C
    - C#
    - C++
    - 一些
    - CoffeeScript
    - 转到
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - 命令行管理程序
    - Swift
    - Tex
    - Vim 脚本

> [!NOTE]
> 源代码经过训练，可检测大量文本何时是源代码。 它不会检测与纯文本交错的源代码文本。

- **冒犯**：根据以下特征检测与针对一个或多个个人的冒犯行为相关的特定冒犯性语言文本项类别：种族、国家/地区、性别、性取向、年龄、残障
- **冒犯性**：检测特定类别的冒犯性语言文本项，这些文本项包含使大多数用户感同的表达式
- **威胁**：检测与威胁相关的特定类别的冒犯性语言文本项，以实施暴力或对人员或属性进行物理损害或损害

这些记录Microsoft 365数据  >  **分类**  >  **可训练分类** 器视图，状态为 `Ready to use` 。

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、冒犯性、亵亵和威胁分类器仅适用于可搜索文本，并不详尽或完整。  此外，语言和文化标准会不断改变，并且鉴于这些创新，Microsoft 保留自行决定更新这些分类器的权利。 虽然分类器可帮助组织监视使用的攻击性语言和其他语言，但分类器不会解决此类语言的后果，也不用于提供组织监视或响应此类语言使用的唯一方式。 贵组织（而不是 Microsoft 或其子公司）仍负责与监视、强制执行、阻止、删除和保留由预先训练的分类器标识的任何内容相关的所有决策。

### <a name="custom-classifiers"></a>自定义分类器

如果预先训练的分类器无法满足您的需求，您可以创建并训练自己的分类器。 创建自己的工作涉及明显更多工作，但它们可以更好地根据组织需求进行定制。 

例如，你可以为：
 
- 法律文档 - 例如律师客户特权、结束集、工作说明
- 战略业务文档 - 如新闻稿、合并和收购、交易、业务或市场营销计划、知识产权、专利、设计文档
- 定价信息 - 如发票、报价、工作订单、采购文档 
- 财务信息 - 如组织投资、季度或年度结果    

#### <a name="process-flow-for-creating-custom-classifiers"></a>创建自定义分类器的过程流

创建和发布分类器以用于合规性解决方案（如保留策略和通信监督）遵循此流程。 有关创建自定义可训练分类器的详细信息，请参阅 [创建自定义分类器](classifier-get-started-with.md)。

![进程流自定义分类器](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新分类器

通过提供有关自定义分类器及其所执行分类的准确性的反馈，可以帮助提高所有自定义分类器以及一些预先训练的分类器的准确性。 这称为重新培训并遵循此工作流。

![分类器重新分类工作流](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](retention.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [文档手指打印](document-fingerprinting.md)
- [精确数据匹配](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
