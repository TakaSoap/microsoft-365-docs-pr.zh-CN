---
title: 了解基于精确数据匹配的敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解基于准确数据匹配的敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 552d86e4c460ee0195ec83d88965592298a17d90
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914744"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>了解基于精确数据匹配的敏感信息类型

[](sensitive-information-type-learn-about.md)敏感信息类型用于帮助标识敏感项目，以便防止意外或不当共享它们，帮助在电子数据展示中查找敏感数据，以及将管理操作应用于某些类型的信息。 您根据以下信息在 SIT (自定义) 类型：

- 模式
- 关键字证据，*如员工**、社会保险号* 或 *ID*
- 字符近似特定模式的证据
- 可信度

但是，如果需要使用使用精确或接近精确数据值的 (SIT) ，而不是基于通用模式找到匹配项的自定义敏感信息类型，应该如何呢？ 使用精确数据 (EDM) 基于分类，你可以创建自定义敏感信息类型，该类型旨在：

- 动态且轻松地刷新
- 更具可伸缩性
- 导致更少的误报
- 处理结构化敏感数据
- 更安全地处理敏感信息，而不是与任何人（包括 Microsoft）共享它
- 与多种 Microsoft 云服务一起使用

![基于 EDM 的分类。](../media/EDMClassification.png)

基于 EDM 的分类允许你创建自定义敏感信息类型，它们将引用敏感信息数据库中的精确值。 数据库可以每天刷新一次，最多可包含 1 亿行数据。 因此，当员工、患者或客户往来并且记录发生更改时，你的自定义敏感信息类型仍将保持最新并且适用。 你还可以将基于 EDM 的分类与策略一起使用，例如[数据丢失防护策略](dlp-learn-about-dlp.md)或[Microsoft Cloud App Security 文件策略](/cloud-app-security/data-protection-policies)。

> [!NOTE]
> Microsoft 365 信息保护支持双字节字符集语言，用于:
>
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
> 此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT 中的不同

使用 EDM STS 时，了解它们特有的一些概念会很有帮助。  

### <a name="schema"></a>架构

架构是一个定义以下项的 xml 文件：

- 架构的名称，稍后称为 *DataStore*。 
- 敏感信息源表包含的字段名称。 架构字段名称与敏感信息源表列名称的映射为 1：1。
- 哪些字段可搜索。
- 任何修改参数（称为 *可配置匹配*）的搜索，如忽略搜索值中的分隔符和大小写。

### <a name="sensitive-information-source-table"></a>敏感信息源表

包含 EDM SIT 将查找的敏感信息值的敏感源表。 它由列和 roes 组成。 列标题是字段名称，行是数据的实例，每个单元格包含该字段的实例的值。

下面是敏感信息源表的简单示例。

|名字  |姓氏  |Date of Birth  |
|---------|---------|---------|
|Isa一   |Langer  | 05-05-1960 |
|分析   |Bowman         |11-24-1971 |
|Oscar   |省/市/区         |02-12-1998 |


### <a name="rule-package"></a>规则包

每个 SIT 都有一个规则包。 使用 EDM SIT 中的规则包定义：

- Matches，它指定将在完全查找中使用的主元素的字段。 它可以是包含或不带校验和验证、关键字列表、关键字词典或函数的正则表达式。
- Classification，用于指定触发 EDM 查找的敏感类型匹配。
- 支持元素，这些元素在找到时可提供支持证据以帮助提高匹配可信度。 例如，与 SSN 号码接近的关键字"SSN"。 它可以是包含或不带校验和验证、关键字列表、关键字词典的正则表达式。
- 高 (、中、低) 可信度反映与主要元素一起检测到的支持性证据量。 项目包含的支持性证据越充分，匹配项包含所查找敏感信息的置信度越高。 有关可信度 [详细信息，请参阅敏感信息类型](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) 的基本部分。
邻近度 – 主要元素和支持元素之间的字符数

### <a name="you-supply-your-own-schema-and-data"></a>提供你自己的架构和数据

[Microsoft 365 200 多个具有](sensitive-information-type-entity-definitions.md)预定义架构、正则表达式模式、关键字和可信度的 SITS。 使用 EDM SI，你负责定义用于标识敏感项的架构以及主要和辅助字段。 由于架构和主要和辅助数据值高度敏感，因此你将通过包含随机生成的或自提供的 salt[](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes)值的哈希函数[加密它们。](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) 然后，这些哈希值将上载到服务，因此你的敏感数据永远不会打开。

### <a name="primary-and-secondary-support-elements"></a>主要和辅助支持元素

创建 EDM SIT 时，在规则 *包中* 定义主元素字段。 主要字段是搜索所有内容的元素，这些元素需要遵循定义的模式才能进行标识。 在扫描的项中发现主元素后，EDM 将查找不需要遵循模式且与主要元素接近的辅助或支持元素。 EDM 要求首先可以通过现有 SIT 发现主元素。 请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md) ，了解可用 SIT 的完整列表。 你必须找到其中一个检测 EDM SIT 要检测的类的类。 例如，如果您的 EDM SIT 架构将美国社会保险号作为主元素，则当您创建 EDM 架构时，会将 EDM 架构与美国社会保险号 [ (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) SIT 关联。


## <a name="how-matching-works"></a>匹配的工作原理

EDM 通过将找到的内容与定义的敏感数据表进行比较来查找匹配项。 匹配测试是使用传统规则和模式的组合进行的，以确保匹配的数据是你想要查找和保护的实际数据实例。 EDM 的核心是，通过比较单向加密哈希，将文档中的字符串和电子邮件中的字符串与提供的敏感数据表中的值进行比较，以找出内容中的值是否存在于表中。

> [!TIP]
> 一种常见做法是结合使用 EDM 敏感信息类型和它们基于 DLP 规则的常规敏感信息类型，并使用不同的阈值。 例如，您可以使用 EDM 敏感信息类型来查找社会保险号和其他数据，具有严格的要求和低容限，其中一个或多个匹配将导致 DLP 警报，并使用常规敏感信息类型，如美国社会保险号内置位置用于较高的计数。  

## <a name="see-also"></a>另请参阅

- [开始使用基于精确数据匹配的敏感信息类型](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
   