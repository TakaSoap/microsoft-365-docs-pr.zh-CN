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
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933076"
---
# <a name="learn-about-sensitive-information-types"></a>了解敏感信息类型

标识和分类组织控制下的敏感项目是信息保护规范 [的第一步](protect-information.md)。  Microsoft 365 提供了三种标识项目的方法，以便对项目进行分类：

- 用户手动
- 自动模式识别，如敏感信息类型
- [机器学习](classifier-learn-about.md)

敏感信息类型是基于模式的分类器。 它们检测敏感信息（如社会保险、信用卡或银行帐号）以标识敏感项目，请参阅敏感信息 [类型实体定义](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>敏感信息类型用于

- [数据丢失防护策略](data-loss-prevention-policies.md) 
- [敏感度标签](sensitivity-labels.md)
- [保留标签](retention.md)
- [通信合规性](communication-compliance.md)
- [自动标记策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>敏感信息类型的基本部分

每个敏感信息类型实体由以下字段定义：

- name：如何引用敏感信息类型
- description： describes what the sensitive information type is looking for
- 模式：模式定义敏感信息类型检测到的信息。 它由以下组件组成
    - 主元素 – 敏感信息类型要查找的主元素。 它可以 **是具有或** 不带校验和验证、关键字列表、关键字词典或函数的 **正则表达式**。 
    - 支持元素 – 充当支持证据的元素，有助于提高匹配可信度。 例如，与 SSN 号码邻近的关键字"SSN"。 它可以是包含或不带校验和验证、关键字列表、关键字词典的正则表达式。
    - 可信度 - 置信 (高、中、低) 反映与主要元素一起检测到的支持性证据量。 项目包含的支持性证据越高，匹配项包含的敏感信息的可信度越高。
    - 邻近度 – 主要元素和支持元素之间的字符数

![确证性证据和临近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

在此视频中了解有关可信度的更多信息


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>敏感信息类型示例


## <a name="argentina-national-identity-dni-number"></a>阿根廷国家/ (DNI) 号码

### <a name="format"></a>Format

八个数字，用点分隔

### <a name="pattern"></a>模式

八个数字：
- 两个数字
- a period
- 三个数字
- a period
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的邻近度内，DLP 策略具有中等可信度，即检测到这种类型的敏感信息：
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
- 标识国家身份证 
- DNI 
- NIC 国家/个人注册表 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>有关可信度的更多方面

在敏感信息类型实体定义中，可信度反映除了主要元素之外检测到多少支持证据。 项目包含的支持性证据越高，匹配项包含的敏感信息的可信度越高。 例如，高可信度的匹配项将包含与主要元素接近的更多支持证据，而置信度较低的匹配将几乎不包含接近度的支持性证据。 

高可信度返回最小的误报，但可能会导致漏报数更多。 低或中等可信度返回更多的误报，但漏报很少到零。

- **低可信度**：值 65，匹配的项将包含最小的漏报，但误报最多。  
- **中置** 信度 ：值 75，匹配项将包含误报和漏报的平均数量。  
- **高可信度**：值 85，匹配的项将包含最小的误报，但包含最多的漏报。  

你应该将高可信度模式与较低的计数（如 5 到 10）和低可信度模式（例如 20 个或多个）一起用于较高的计数。

## <a name="creating-custom-sensitive-information-types"></a>创建自定义敏感信息类型

若要在安全与合规中心内创建自定义敏感信息类型，可使用以下几种方法：

- **使用 UI** 可以使用安全与合规中心 UI 创建自定义敏感信息类型。 通过此方法，你可以使用正则表达式、关键字和关键字字典。 若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。

- **使用 EDM** 可以使用基于精确数据匹配 (EDM) 的分类创建自定义敏感信息类型。 通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。 请参阅[使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

- **使用 PowerShell** 可以使用 PowerShell 创建自定义敏感信息类型。 尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。 请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。



> [!NOTE]
> Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语

>此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

## <a name="for-further-information"></a>有关详细信息
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
- [在 PowerShell 中创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->