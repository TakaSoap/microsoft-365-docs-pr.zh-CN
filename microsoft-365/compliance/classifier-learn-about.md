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
description: Microsoft 365 trainable 分类器是一种工具，可通过提供要查看的正负样本来识别各种类型的内容。 在分类器经过培训之后，您确认其结果是准确的。 然后，使用它来搜索组织的内容，并对其进行分类以应用保留或敏感度标签，或将其包含在数据丢失防护 (DLP) 或保留策略中。
ms.openlocfilehash: d26e33efea09c2afb33c2b5e5ade264cb8bfaee6
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072941"
---
# <a name="learn-about-classifiers-preview"></a>了解 (预览的分类器) 

对内容进行分类和标记，以便可以对其进行保护和正确处理，这是信息保护训练科目的起始位置。 Microsoft 365 有三种对内容进行分类的方法。

## <a name="manually"></a>手动

此方法需要人为判断力和行动。 管理员既可以使用预先存在的标签和敏感信息类型，也可以创建它们自己的，然后发布它们。 用户和管理员会在遇到问题时将其应用于内容。 然后，您可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此类别的分类机制包括通过以下方式查找内容：

- 关键字或元数据值 (关键字查询语言) 。
- 使用以前确定的敏感信息模式，如社会安全性、信用卡或银行帐户号 [ (敏感信息类型实体定义) ](sensitive-information-type-entity-definitions.md)。
- 识别项目，因为它是模板 [ (文档 finger 打印) ](document-fingerprinting.md)的变体。
- 使用确切的字符串的状态 [ (精确的数据匹配) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

然后，可以自动应用敏感度和保留标签，以使内容可用于 [数据丢失防护 (DLP) ](data-loss-prevention-policies.md) 并 [自动应用保留标签的策略](apply-retention-labels-automatically.md)。

## <a name="classifiers"></a>符

此分类方法尤其适合于手动或自动模式匹配方法无法轻松识别的内容。 此分类方法详细介绍了如何培训分类器，以根据项目的具体内容（而不是项目 (模式匹配) 中的元素来标识项目。 分类器了解如何通过查看您感兴趣的内容的数百个示例来标识内容类型。 首先，我们对类别中明确的示例进行了介绍。 处理这些程序后，通过为匹配和不匹配的示例提供组合来对其进行测试。 然后，分类器将对任何给定项是否属于您要生成的类别进行预测。 然后，您可以确认其结果，并对真正的正值、真底片、误报和漏报进行排序，以帮助提高预测的准确性。 

发布分类器时，它会通过 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。 发布分类器后，您可以继续使用类似于初始培训过程的反馈流程对其进行训练。

### <a name="where-you-can-use-trainable-classifiers"></a>在哪里可以使用 trainable 分类程序
内置分类器和 trainable 分类器都可用作[具有灵敏度标签的 Office autolabeling](apply-sensitivity-label-automatically.md)的条件，并根据条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。 

敏感度标签可以将分类器用作条件，请参阅 [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> 分类器仅适用于未加密且为英语的项目。

## <a name="types-of-classifiers"></a>分类器的类型

- **预先培训的分类** 器-Microsoft 已创建并预先培训多个分类器，您可以开始使用而无需对其进行培训。 这些分类符的状态将显示为 `Ready to use` 。
- **自定义分类** 器-如果您的分类需求超出预先培训的分类器所涵盖的范围，则可以创建并培训自己的分类器。

### <a name="pre-trained-classifiers"></a>预先培训的分类器

Microsoft 365 附带了五个预先培训的分类器：

> [!CAUTION]
> 我们正在弃用 **冒犯性语言** 预培训分类器，因为它生成了大量误报。 请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。 我们建议您改用 **威胁** 、 **猥亵** 和 **骚扰** 预培训的分类器。

- **恢复** ：检测作为申请人个人、教育、专业资格、工作经验和其他个人身份信息的文本帐户的项目
- **源代码** ：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项
    - ActionScript
    - C
    - C#
    - C
    - Clojure
    - CoffeeScript
    - 转到
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - 编写
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - 命令行管理程序
    - 反应
    - Tex
    - Vim 脚本

> [!NOTE]
> 源代码经过培训，可在大部分文本是源代码时进行检测。 它不检测与纯文本交错的源代码文本。

- **骚扰** ：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、国家/地区、性别、色情方向、年龄、残疾
- **猥亵** 语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别
- **威胁** ：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对人员或属性造成物理伤害或损坏

这些项将显示在 **Microsoft 365 合规中心**  >  **数据分类 (preview)**  >  **Trainable 类元** 视图，其状态为 `Ready to use` 。

![分类器-预先培训的分类器](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。  此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。 虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。 您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。

### <a name="custom-classifiers"></a>自定义分类器

当预先培训的分类器不能满足您的需求时，您可以创建和培训自己的分类器。 创建你自己的工作有了显著的更多工作，但这些工作会更好地适应你的组织需求。

#### <a name="process-flow-for-creating-custom-classifiers"></a>创建自定义分类器的过程流

创建和发布在合规性解决方案（如保留策略和通信监督）中使用的分类器遵循此流程。 有关创建自定义 trainable 类元的更多详细信息，请参阅 [创建自定义分类器](classifier-get-started-with.md)。

![处理流自定义分类器](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>重新培训分类器

您可以通过向其提供有关其执行的分类准确性的反馈，帮助提高所有自定义分类器和一些预先培训的分类器的准确性。 这称为 "重新培训" 并遵循此工作流。

![分类器重新培训工作流](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](retention.md)
- [Data loss prevention (DLP)](data-loss-prevention-policies.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [文档指纹打印](document-fingerprinting.md)
- [精确数据匹配](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
