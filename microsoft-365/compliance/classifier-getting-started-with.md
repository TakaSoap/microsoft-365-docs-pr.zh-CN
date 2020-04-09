---
title: 可训练分类器入门（预览）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 trainable 分类器是一种工具，可通过提供要查看的正负样本来识别各种类型的内容。 在分类器经过培训之后，您确认其结果是准确的。 然后，使用它搜索组织的内容，并对其进行分类以应用保留或敏感度标签，或将其包含在数据丢失防护（DLP）或保留策略中。
ms.openlocfilehash: 4d11fcf4e1437641cb73510d341d299ce3695938
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193520"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>可训练分类器入门（预览）

对内容进行分类和标记，以便可以对其进行保护和正确处理，这是信息保护训练科目的起始位置。 Microsoft 365 有三种对内容进行分类的方法。

## <a name="manually"></a>手动

此方法需要人为判断力和行动。 管理员既可以使用预先存在的标签和敏感信息类型，也可以创建它们自己的，然后发布它们。 用户和管理员会在遇到问题时将其应用于内容。 然后，您可以保护内容并管理其处置。

## <a name="automated-pattern-matching"></a>自动模式匹配

此类别的分类机制包括通过以下方式查找内容：

- 关键字或元数据值（关键字查询语言）
- 使用以前确定的敏感信息模式，如社会安全性、信用卡或银行帐户号码[（敏感信息类型）](what-the-sensitive-information-types-look-for.md)
- 识别项目，因为它是模板的变体[（文档指纹打印）](document-fingerprinting.md)
- 使用确切的字符串[（精确数据匹配）](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)的状态。

然后，可以自动应用敏感度和保留标签，以使内容可用于[数据丢失防护（DLP）](data-loss-prevention-policies.md)和[保留策略](retention-policies.md)。

## <a name="trainable-classifiers"></a>Trainable 类元

此分类方法尤其适合于手动或自动模式匹配方法无法轻松识别的内容。 此分类方法详细介绍了如何培训分类器，以根据项目的具体内容（而不是项目中的元素）来标识项目（模式匹配）。 分类器了解如何通过查看您感兴趣的内容的数百个示例来标识内容类型。 首先，我们对类别中明确的示例进行了介绍。 处理这些程序后，通过为匹配和不匹配的示例提供组合来对其进行测试。 然后，分类器将对任何给定项是否属于您要生成的类别进行预测。 然后，确认其结果，并对误报、负、误报和漏报进行排序，以帮助提高预测的准确性。 在发布训练有素的分类器时，它会通过 SharePoint Online、Exchange 和 OneDrive 等位置中的项目进行排序，并对内容进行分类。

> [!IMPORTANT]
> 内置分类器和 trainable 分类器都可用作基于条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)的条件。 敏感度标签只能将内置分类器用作条件，请参阅[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)。

> [!IMPORTANT]
> Trainable 类元仅适用于未加密且为英语的项目。

### <a name="licensing-requirements"></a>许可要求

Trainable 分类器是 Microsoft 365 E5 或 E5 合规性功能。 您必须拥有其中一种订阅才能使用它们。

## <a name="types-of-classifiers"></a>分类器的类型

有内置的分类器和 trainable 分类器。 将 trainable 类元获取为可发布的状态需要进行一次投资培训。 为了帮助您开始使用分类器，Microsoft 365 附带了几个内置的分类符。

> [!NOTE]
> 在分类和标记工作流中使用任何内置分类器之前，应根据您认为符合该类别的组织内容示例对其进行测试，以验证其分类预测是否符合您的预期。

### <a name="understanding-built-in-classifiers"></a>了解内置分类器

Microsoft 365 附带了五个建议的内置分类器：

> [!CAUTION]
> 我们正在弃用采用**冒犯性语言**的内置分类器，因为它生成了大量误报。 请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。 我们建议改为使用**威胁**、**猥亵**和**骚扰**内置分类符。

- **恢复**：检测作为申请人个人、教育、专业资格、工作经验以及其他个人标识信息的文本帐户的项目。
- **源代码**：检测包含一组由 GitHub 上的前25个使用的计算机编程语言编写的指令和语句的项。

|语言名称|||||
|---------|---------|---------|---------|---------|
|ActionScript|C        |C#       |C     |Clojure  |
|CoffeeScript|CSS     |转到       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|编写     |PHP      |Python   |R        |Ruby     |
|Scala    |命令行管理程序    |反应    |Tex      |Vim 脚本|


- **骚扰**：根据以下特性，检测与针对一个或多个用户的攻击性行为相关的冒犯性语言文本项的特定类别：种族、ethnicity、宗教、民族、性别、色情方向、年龄、残疾。
- **猥亵**语言：检测包含 embarrass 大多数人的表达式的冒犯性语言文本项的特定类别。
- **威胁**：检测与威胁相关的攻击性语言文本项的特定类别，以提交暴力或对个人或属性造成物理伤害或损坏。

这些显示在**Microsoft 365 合规中心** > **数据分类（预览版）** > **Trainable 类元**视图中，状态为`Ready to use`。

![分类器-可供使用的类元](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> 请注意，冒犯性语言、骚扰、猥亵和威胁分类器仅适用于可搜索文本不详尽或完整。  此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时更新这些分类器的权利。 虽然分类程序可以帮助组织监视攻击性和其他使用的语言，但分类程序不会解决此类语言的后果，也不能提供组织的唯一方法来监视或响应此类语言的使用。 您的组织（而不是 Microsoft 或其子公司）仍负责与监控、强制执行、阻止、删除和保留预先培训的分类器所标识的任何内容相关的所有决策。

#### <a name="process-flow-for-using-built-in-classifiers"></a>使用内置分类器的过程流

内置的类元不需要接受培训，但您需要确认他们能够在合规性解决方案中使用它们之前确定所需的内容类型。 测试预先培训的类元将遵循此流程。

![处理预先培训的分类器的过程流](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>了解 trainable 类元

当内置分类器不能满足您的需求时，您可以创建和培训自己的分类器。 创建你自己的工作有了显著的更多工作，但这些工作会更好地适应你的组织需求。 有关如何使用预先培训的分类器的详细信息，请参阅[Using a 内置分类器](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> 只有创建 trainable 分类器的用户才可以培训和查看该分类器所做的预测。

#### <a name="process-flow-for-creating-trainable-classifiers"></a>创建 trainable 类元的过程流

创建和发布在合规性解决方案（如保留策略和通信监督）中使用的 trainable 分类程序遵循此流程。 有关创建 trainable 类元的更多详细信息，请参阅[创建 trainable 分类器](classifier-creating-a-trainable-classifier.md)。

![process flow trainable 类元](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>另请参阅

- [保留标签](labels.md)
- [保留策略](retention-policies.md)
- [数据丢失防护（DLP）](data-loss-prevention-policies.md)
- [敏感度标签](sensitivity-labels.md)
- [敏感信息类型](what-the-sensitive-information-types-look-for.md)
- [文档指纹打印](document-fingerprinting.md)
- [精确数据匹配](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
