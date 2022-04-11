---
title: 了解敏感信息类型
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: 本文概述了敏感信息类型及其检测敏感信息（如社会保障、信用卡或银行帐号）如何识别敏感项目
ms.openlocfilehash: aef78c5ab3348b7a0b00a649f94fa5e50a99a397
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760308"
---
# <a name="learn-about-sensitive-information-types"></a>了解敏感信息类型

识别和分类组织控制下的敏感项目是[信息保护规则](./information-protection.md)中的第一步。  Microsoft 365提供了三种方法来标识项目，以便对它们进行分类：

- 由用户手动完成
- 自动化模式识别，如敏感信息类型
- [机器学习](classifier-learn-about.md)

SIT)  (敏感信息类型是基于模式的分类器。 他们检测到诸如社会保障、信用卡或银行帐号等敏感信息以识别敏感项目，请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md) ，了解所有 SIT 的完整列表。

Microsoft 提供大量预配置的 SIT，也可以创建自己的 SIT。

## <a name="sensitive-information-types-are-used-in"></a>敏感信息类型用于

- [数据丢失防护策略](dlp-learn-about-dlp.md)
- [敏感度标签](sensitivity-labels.md)
- [保留标签](retention.md)
- [内部风险管理](insider-risk-management.md)
- [通信合规性](communication-compliance.md)
- [自动标记策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Priva](/privacy/priva)

## <a name="categories-of-sensitive-information-types"></a>敏感信息类型的类别

### <a name="built-in-sensitive-information-types"></a>内置敏感信息类型

默认情况下，这些 SIT 由 Microsoft 创建，显示在合规性控制台中。 不能编辑这些 SIT，但可以将其用作模板并复制以创建自定义敏感信息类型。 请参阅所有 SIT 的完整列表的 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md) 。

### <a name="named-entity-sensitive-information-types"></a>命名实体敏感信息类型

默认情况下，命名实体 SIT 也会显示在合规性控制台中。 它们检测人员姓名、身体地址以及医疗条款和条件。 无法编辑或复制它们。 有关详细信息，请参阅 [ (预览) 了解命名实体 ](named-entities-learn.md#learn-about-named-entities-preview) 。 命名实体 SIT 有两种类型：

**未捆绑**

这些命名实体 SIT 具有更窄的焦点，例如单个国家/地区或单个术语类。 如果需要具有较窄检测范围的 DLP 策略，请使用这些策略。 请参阅 [命名实体 SIT 的示例](named-entities-learn.md#examples-of-named-entity-sits)。

**捆绑**

捆绑的命名实体 SIT 检测类中所有可能的匹配项，例如所有物理地址。 在 DLP 策略中将它们用作用于检测敏感项的广泛条件。 请参阅 [命名实体 SIT 的示例](named-entities-learn.md#examples-of-named-entity-sits)。

### <a name="custom-sensitive-information-types"></a>自定义敏感信息类型

如果预配置的敏感信息类型不能满足你的需求，可以创建你完全定义的自定义敏感信息类型，也可以复制其中一个内置信息类型并对其进行修改。 有关详细信息，请参阅： [在合规中心创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md) 。

### <a name="exact-data-match-sensitive-information-types"></a>精确数据与敏感信息类型匹配

所有基于 EDM 的 SIT 都是从头开始创建的。 可以使用它们来检测具有在敏感信息数据库中定义的确切值的项。 有关详细信息，请参阅， [了解基于数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) 。

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>敏感信息类型的基本部分

每个敏感信息类型实体都由以下字段定义：

- 名称：如何引用敏感信息类型
- 说明：描述敏感信息类型要查找的内容
- 模式：模式定义敏感信息类型检测到的内容。 它由以下组件组成。
  - 主元素 – 敏感信息类型要查找的主要元素。 它可以是具有或不带校验和验证、**关键字列表**、**关键字字典** 或 **函** 数的 **正则表达** 式。
  - 支持元素 - 作为支持证据的元素，有助于提高匹配的信心。 例如，靠近 SSN 编号的关键字“SSN”。 它可以是具有或不带校验和验证、关键字列表、关键字字典的正则表达式。
  - 置信度 - 置信度级别 (高、中、低) 反映检测到多少支持证据以及主要元素。 项目包含的支持证据越多，匹配项所包含的敏感信息的置信度就越高。
  - 邻近 - 主要元素和支持元素之间的字符数。

![佐证证据和邻近窗口的关系图。](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

在此简短视频中详细了解置信度。

 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]

### <a name="example-sensitive-information-type"></a>敏感信息类型的示例

#### <a name="argentina-national-identity-dni-number"></a>阿根廷国家标识 (DNI) 编号

### <a name="format"></a>格式

八个数字，用点分隔

### <a name="pattern"></a>模式

八个数字：

- 两位数
- 一个句点
- 三位数
- 一个句点
- 三位数

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

如果 DLP 策略接近 300 个字符，则会检测到此类敏感信息：

- 正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。
- 找到 Keyword_argentina_national_id 中的一个关键字。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number
- 标识
- 标识国家标识卡
- DNI
- NIC 国家人员注册表
- Documento Nacional de Identidad
- Registro Nacional de las Personas
- Identidad
- Identificación

### <a name="more-on-confidence-levels"></a>有关置信度级别的详细信息

在敏感信息类型实体定义中， **置信度反映了** 除了主元素之外检测到的支持证据量。 项目包含的支持证据越多，匹配项所包含的敏感信息的置信度就越高。 例如，具有高置信度匹配项将包含与主要元素非常接近的更多支持证据，而置信度较低的匹配项在接近时几乎不包含任何支持证据。

高置信度返回最少的误报，但可能会导致更多的误报。 低置信度或中等置信度级别返回更多的误报，但误报数很少到零。

- **低置信度**：匹配项将包含最少的误报，但误报最多。 低置信度返回所有低、中、高置信度匹配项。 低置信度值为 65。
- **中等置信** 度：匹配项将包含平均误报和误报量。 中等置信度返回所有中等和高置信度匹配项。 中等置信度值为 75。
- **高置信度**：匹配的项目将包含最少的误报，但最假的负数。 高置信度仅返回高置信度匹配项，值为 85。

你应该使用高置信度模式与低计数，比如5到10，低置信度模式与较高的计数，说20或更多。

> [!NOTE]
> 如果现有策略或自定义敏感信息类型 (使用基于数字的置信度级别定义的 SIT)  (也称为准确性) ，则它们将自动映射到三个离散置信度级别：安全性 @ 合规中心 UI 中的低置信度、中等置信度和高置信度。
>
> - 具有最低准确度或自定义 SIT 模式且置信度级别在 76 到 100 之间的所有策略都将映射到高置信度。
> - 具有最低准确度或自定义 SIT 模式且置信度级别介于 66 和 75 之间的所有策略都将映射到中等置信度。
> - 具有最低准确性或自定义 SIT 模式（置信度低于或等于 65）的所有策略都将映射到低置信度。

## <a name="creating-custom-sensitive-information-types"></a>创建自定义敏感信息类型

你可以从多个选项中进行选择，以便在合规中心创建自定义敏感信息类型。

- **使用 UI** - 可以使用合规中心 UI 设置自定义敏感信息类型。 通过此方法，你可以使用正则表达式、关键字和关键字字典。 若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。

- **使用 EDM** - 可以使用基于 EDM 的精确数据匹配 (基于 EDM 的分类) 设置自定义敏感信息类型。 通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。 请参阅 [了解基于数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)。

- **使用 PowerShell** - 可以使用 PowerShell 设置自定义敏感信息类型。 尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。 请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。

> [!NOTE]
> 改进的置信度可在数据丢失防护中立即用于Microsoft 365服务、Microsoft 365服务Microsoft 信息保护、通信合规性、信息治理和记录管理。
> Microsoft 365 信息保护现在支持双字节字符集语言：
>
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
> 此支持适用于敏感信息类型。 有关详细信息，请参阅 [对双字节字符集发行说明的信息保护支持](mip-dbcs-relnotes.md) 。

> [!TIP]
> 若要检测含有中文/日文字符和单字节字符的模式，或检测含有中文/日文和英文的模式，则需要定义两个变体的关键词或词组。
>
> - 例如，若要检测像“机密的文件”这样的关键词，则要使用该关键词的两个变体; 一个是在日语和英语文本之间有空格，另一个是在日语和英语文本之间没有空格。 因此，在 SIT 中要添加的关键词应该是“机密的 文档”和“机密的文档”。 同样，若要检测短语 "東京オリンピック2020"，则应该使用两个变体;“東京オリンピック 2020”和“東京オリンピック2020”。
>
> 除了中文/日语/双字节字符，如果关键字/短语列表中还包含非中文/日语单词， (仅) 英语，则应创建两个字典/关键字列表。 一个针对包含中文/日语/双字节字符的关键字，另一个针对仅含英语的关键字。
>
> - 例如，如果要创建包含三个短语“高度机密”、“機密钥が高い”和“机密文档”的关键字词典/列表，则应创建两个关键字列表。
>     1. Highly confidential
>     2. “機密性が高い”、“机密的document”和“机密的 document”
>
> 当使用双字节连字符或双字节句号创建 regex 时，请确保像在 regex 中转义连字符或句号一样转义这两个字符。以下是供参考的示例 regex：
>
> `(?<!\d)([4][0-9]{3}[\-?\-\t]*[0-9]{4}`
>
> 建议在关键字列表中使用字符串匹配而不是字词匹配。

## <a name="for-further-information"></a>有关详细信息

- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
- [在 PowerShell 中创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)

若要了解如何使用敏感信息类型来遵守数据隐私法规，请参阅[使用Microsoft 365 (aka.ms/m365dataprivacy) 为数据隐私法规部署信息保护](../solutions/information-protection-deploy.md)。

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
