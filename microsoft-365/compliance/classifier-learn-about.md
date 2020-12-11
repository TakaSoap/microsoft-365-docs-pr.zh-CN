---
title: 了解可训练的分类器（预览版）
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
description: Microsoft 365 可训练分类器是一种工具，可用于通过提供要查看的正面和负面示例来识别各种类型的内容。 对分类器进行训练后，可确认其结果准确无误。 然后，使用它搜索组织的内容，并进行分类以应用保留标签或敏感度标签，或将其包括在 DLP 策略或保留策略的数据丢失防护 (DLP) 中。
ms.openlocfilehash: 77ebefe338f393a916f0a6844b42b16e3d011d49
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620158"
---
# <a name="learn-about-classifiers-preview"></a>了解分类器 (预览) 

对内容进行分类和标记以便可以保护和正确处理内容是信息保护规范的起点。 Microsoft 365 有三种对内容进行分类的方法。

## <a name="manually"></a>手动

此方法需要人为的判断和操作。 管理员可以使用预先存在的标签和敏感信息类型，也可以创建自己的标签和敏感信息类型，然后发布它们。 用户和管理员在遇到内容时将其应用于内容。 然后，您可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此类别的分类机制包括通过以下方法查找内容：

- 关键字或元数据值 (关键字查询语言) 。
- 使用以前标识的敏感信息模式，如社会保险、信用卡或银行帐号 ([ 敏感信息类型实体 ](sensitive-information-type-entity-definitions.md)定义) 。
- 识别项目，因为它是模板上的变体， ([文档手指) 。 ](document-fingerprinting.md)
- 使用精确字符串的存在 ([数据完全匹配) 。 ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

然后，可以自动应用敏感度和保留标签，使内容可用于数据丢失防护 ([DLP) ](data-loss-prevention-policies.md) 和自动应用保留标签 [策略](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>分类器

此分类方法特别适用于无法通过手动或自动模式匹配方法轻松识别的内容。 这种分类方法更与训练分类器以根据项目是什么来标识项目有关，而不是由与项目模式匹配 (元素) 。 分类器通过查看数百个对分类感兴趣的内容示例来了解如何标识内容类型。 首先，请馈送该类别中绝对属于该类别的示例。 处理这些示例后，通过混合提供匹配和非匹配示例来测试它。 然后，分类器将预测任何给定项目是否属于你正在构建的类别中。 然后确认其结果，对真正、真负、误报和漏报进行排序，以帮助提高其预测的准确性。 

发布分类器时，分类器对 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容分类。 发布分类器后，可以继续使用与初始培训过程类似的反馈流程对分类器进行培训。

### <a name="where-you-can-use-trainable-classifiers"></a>在哪里可以使用可训练分类器
内置分类器以及可训练分类器均作为使用敏感度标签[进行 Office](apply-sensitivity-label-automatically.md)自动标记的条件，根据条件和通信合规性自动应用[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)保留[标签策略](communication-compliance.md)。 

敏感度标签可以使用分类器作为条件，请参阅自动将敏感度 [标签应用于内容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分类器仅适用于未加密且为英语的项目。

## <a name="types-of-classifiers"></a>分类器的类型

- **预先训练的分类器** - Microsoft 已创建并预先训练许多分类器，无需培训即可开始使用。 这些分类器的状态将显示为 `Ready to use` 。
- **自定义分类** 器 - 如果你的分类需求超出预先训练的分类器涵盖范围，可以创建并训练自己的分类器。

### <a name="pre-trained-classifiers"></a>经过预先训练的分类器

Microsoft 365 附带五个预先训练的分类器：

> [!CAUTION]
> 我们弃用冒犯性语言预先训练的分类器，因为它一直产生大量误报。 请勿使用它，如果当前正在使用它，则应该将业务流程从其中移开。 我们建议改为使用 **威胁**、**亵** 亵和骚扰预先训练的分类器。

- **简历**：检测是简历个人、教育、专业资格、工作体验和其他个人识别信息的文本帐户的项目
- **源代码：** 检测包含用 GitHub 上前 25 种使用的计算机编程语言编写的一组说明和语句的项目
    - ActionScript
    - C
    - C#
    - C++
    - 一个
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
> 源代码经过训练，可检测大部分文本是源代码时。 它不会检测与纯文本交错的源代码文本。

- **冒犯**：根据以下特征检测与针对一个或多个个人的攻击行为相关的特定冒犯性语言文本项：种族、种族、宗教、国家/地区、性别、性取向、年龄、残障
- **冒犯性**：检测特定类别的冒犯性语言文本项，这些文本项包含使大多数用户都为难的表达式
- **威胁**：检测与威胁相关的特定类别的冒犯性语言文本项，以实施暴力或对人员或属性进行物理损害或损害

它们显示在 **Microsoft 365** 合规中心数据  >  **分类 (预览**)  >  **可** 训练分类器视图中的状态 `Ready to use` 为 。

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、冒犯、冒犯和威胁分类器仅适用于可搜索文本，并不详尽或完整。  此外，语言和文化标准会不断改变，鉴于这些希望，Microsoft 保留自行更新这些分类器的权利。 虽然分类器可帮助组织监视使用的攻击性语言和其他语言，但分类器不会解决此类语言的后果，也不旨在提供组织监视或响应此类语言使用的唯一方式。 贵组织（而非 Microsoft 或其子公司）仍负责与监视、强制执行、阻止、删除和保留由预先训练的分类器标识的任何内容相关的所有决策。

### <a name="custom-classifiers"></a>自定义分类器

当预先训练的分类器不能满足你的需求时，你可以创建并训练你自己的分类器。 创建自己的任务涉及的工作明显更多，但它们可以更好地根据组织需求进行定制。 

例如，你可以为：
 
- 法律文档 - 例如律师客户特权、结束集、工作声明
- 战略业务文档 - 如新闻稿、合并和收购、交易、业务或市场营销计划、知识产权、专利、设计文档
- 定价信息 - 如发票、报价、工作订单、采购文档 
- 财务信息 - 例如组织投资、季度或年度结果    

#### <a name="process-flow-for-creating-custom-classifiers"></a>创建自定义分类器的流程

创建和发布分类器以用于合规性解决方案（如保留策略和通信监督）遵循此流程。 有关创建自定义可训练分类器的详细信息，请参阅["创建自定义分类器"。](classifier-get-started-with.md)

![进程流自定义分类器](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新分类器

通过提供有关自定义分类器及其所执行分类的准确性的反馈，可帮助提高所有自定义分类器以及一些经过预先训练的分类器的准确性。 这称为重新培训并遵循此工作流。

![分类器重新分类工作流](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](retention.md)
- [数据丢失防护 (DLP)](data-loss-prevention-policies.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [文档手指打印](document-fingerprinting.md)
- [精确数据匹配](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
