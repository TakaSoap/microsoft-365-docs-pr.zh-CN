---
title: 了解基于确切数据匹配的敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解基于数据匹配的精确敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f883d2509961ee07045949530f8fbb50629212f
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759758"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>了解基于确切数据匹配的敏感信息类型

[敏感信息类型](sensitive-information-type-learn-about.md) 用于帮助识别敏感项，以便防止它们无意中或不当共享，帮助在电子数据展示中查找相关数据，并将治理操作应用于特定类型的信息。 基于以下内容定义自定义敏感信息类型 (SIT) ：

- 模式
- 关键字证据，例如 *员工*、 *社会保障号码* 或 *ID*
- 字符近似特定模式的证据
- 可信度

但是，如果想要自定义敏感信息类型 (使用确切或几乎精确的数据值的 SIT) ，而不是基于泛型模式找到匹配项的信息类型，该怎么办？ 使用基于 EDM 的精确数据匹配 () 分类，可以创建一个自定义敏感信息类型，该类型旨在：

- 动态且轻松地刷新
- 更具可伸缩性
- 导致更少的误报
- 处理结构化敏感数据
- 更安全地处理敏感信息，而不是与任何人（包括 Microsoft）共享敏感信息
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

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT 中的不同内容

使用 EDM SIT 时，了解一些唯一的概念会很有帮助。  

### <a name="schema"></a>架构

架构是定义以下内容的 xml 文件：

- 架构的名称，后来称为 *DataStore*。 
- 敏感信息源表包含的字段名称。 架构字段名称与敏感信息源表列名称的映射为 1：1。
- 哪些字段可搜索。
- 任何搜索修改参数（称为 *可配置匹配*），例如忽略分隔符和搜索值中的大小写。

### <a name="sensitive-information-source-table"></a>敏感信息源表

敏感源表包含 EDM SIT 将查找的敏感信息值。 它由列和行组成。 列标题是字段名称，行是数据实例，每个单元格都包含该字段的该实例的值。

下面是敏感信息源表的简单示例。

|名字|姓氏|Date of Birth|
|---|---|---|
|以 赛 亚|兰格| 05-05-1960|
|安娜|鲍曼|11-24-1971|
|奥斯卡|病房|02-12-1998|

### <a name="rule-package"></a>规则包

每个 SIT 都有一个规则包。 使用 EDM SIT 中的规则包来定义：

- 匹配项，指定将作为要在精确查找中使用的主要元素的字段。 它可以是具有或不带校验和验证、关键字列表、关键字字典或函数的正则表达式。
- 分类，指定触发 EDM 查找的敏感类型匹配项。
- 支持元素是一些元素，当找到这些元素时，这些元素提供支持的证据有助于提高匹配的置信度。 例如，靠近 SSN 编号的关键字“SSN”。 它可以是具有或不带校验和验证、关键字列表、关键字字典的正则表达式。
- 置信度 (高、中、低) 反映检测到多少支持证据以及主要元素。 项目包含的支持证据越多，匹配项所包含的敏感信息的置信度就越高。 有关置信度级别的详细信息，请参阅 [敏感信息类型的基本部分](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) 。
邻近性 - 主要元素和支持元素之间的字符数

### <a name="you-supply-your-own-schema-and-data"></a>提供自己的架构和数据

[Microsoft 365附带了 200 多个具有](sensitive-information-type-entity-definitions.md)预定义架构、正则表达式模式、关键字和置信度级别的 SITS。 使用 EDM SIT，你负责定义架构以及标识敏感项的主要字段和辅助字段。 由于架构以及主要和辅助数据值高度敏感，因此你将通过包含随机生成的或自提供的[盐](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.)值的[哈希](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes)函数对其进行加密。 然后，这些哈希值将上传到服务，因此敏感数据永远不会处于打开状态。

### <a name="primary-and-secondary-support-elements"></a>主要和辅助支持元素

创建 EDM SIT 时，请在规则包中定义 *主元素* 字段。 主要字段是将搜索所有内容的元素，需要遵循定义的模式才能进行标识。 在扫描的项中找到主元素时，EDM 将查找不需要遵循模式的 *辅助* 元素或支持元素，以及它们与主元素的邻近性。 EDM 要求首先通过现有 SIT 发现主元素。 请参阅有关可用 SIT 的完整列表的 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md) 。 必须找到一个用于检测你希望 EDM SIT 检测的类的类。 例如，如果 EDM SIT 架构以美国社会保障号码为主要元素，则在创建 EDM 架构时，会将其与美国 [社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn) SIT 相关联。


## <a name="how-matching-works"></a>匹配的工作原理

EDM 通过将找到的内容与定义的敏感数据表进行比较来查找匹配项。 匹配测试是使用传统规则和模式的组合完成的，以确保匹配的数据是要查找和保护的数据的实际实例。 EDM 的核心是将文档和电子邮件中的字符串与提供的敏感数据表中的值进行比较，以通过比较单向加密哈希来确定内容中的值是否存在于表中。

> [!TIP]
> 一种常见做法是结合使用 EDM 敏感信息类型及其基于 DLP 规则的常规敏感信息类型，以及不同的阈值。 例如，可以使用 EDM 敏感信息类型来查找社会保障号码和其他数据，具有严格的要求和低容忍度，其中一个或多个匹配项将导致 DLP 警报，并使用常规敏感信息类型，例如，美国社会保障号码内置设置为较高的计数。  

## <a name="see-also"></a>另请参阅

- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
   
