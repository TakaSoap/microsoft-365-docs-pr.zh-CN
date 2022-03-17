---
title: 为基于精确数据匹配的敏感信息类型导出源数据
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何导出基于准确数据匹配的敏感信息类型的源数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a1ee56708018ddfddf141499bf4cf5f9ee02449
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526258"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>为基于精确数据匹配的敏感信息类型导出源数据


敏感数据表是一个文本文件，其中包含值行，您将根据这些值对文档中的内容进行比较以标识敏感数据。 这些值可能是要检测的内容中的个人身份信息、产品记录或其他文本形式的敏感数据，并且对这些内容采取保护性操作。

以受支持的格式之一导出数据后，可以继续创建 EDM 架构。

## <a name="defining-your-edm-sensitive-type"></a>定义 EDM 敏感类型

定义 EDM 敏感类型时，最重要的决策之一是哪些字段将成为主要字段。 主要字段需要遵循可检测到的模式，并定义为 EDM 架构 (列) 可搜索字段。 辅助字段不需要遵循任何模式，因为它们会与与主要字段匹配的所有文本进行比较。

使用这些规则可帮助您决定应用作主字段的列：

- 如果必须基于是否存在与敏感数据表中的字段匹配的单个值来检测敏感数据，则无论该列周围是否存在任何其他敏感数据，则必须将列定义为 EDM 类型的主元素。 
- 如果在内容中必须检测到敏感数据表中不同字段的多个组合，请标识大多数此类组合常用的列，并指定这些列作为主要元素和其他字段的组合作为辅助元素。
- 如果要用作主字段的列未遵循可检测到的模式（如任何文本字符串）或遵循可检测到的模式（将在大部分文档或电子邮件中出现）的可检测模式，请尝试选择其他结构更好的列作为主要元素。

`full name``Social Security Number``account number``date of birth`例如，如果您有列 、、 和 ，即使第一个和最后一个名称是你要检测的不同数据组合通用的列，这些字符串不会遵循易于识别的模式，并且可能很难定义为敏感信息类型。 这是因为某些名称甚至不会以大写开头，它们可能由两个、三个或多个单词组成，甚至可能包含数字或其他非字母字符。 可以更轻松地标识出生日期，但由于每封电子邮件和大多数文档将包含至少一个日期，因此这也是一个不错的候选项。 社会保险号和帐号是用作主字段的良好候选项。

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>将敏感数据保存为 .csv、.tsv 或管道分隔格式

1. 确定要使用的敏感信息。 将数据导出到应用（如Microsoft Excel，将文件保存在文本文件中。 该文件可以保存在逗号分隔.csv (值中) .tsv (制表符分隔) 值，或用管道分隔 (|) 格式。 如果数据值可能包含逗号（如街道地址），则建议使用 .tsv 格式。
数据文件最多可包括以下内容：
   - 高达 1 亿行的敏感数据
   - 每个数据源最多 32 列（字段）
   - 最多 5 个列（字段）标记为可搜索

2. 构造数据或 .tsv .csv中的敏感数据，使第一行包含用于基于 EDM 的分类的字段的名称。 在你的文件中，你可能有字段名称，如"ssn"、"birthdate"、"firstname"、"lastname"。 列标题名称不能包含空格或下划线。 例如，本文中使用的示例 .csv 文件名为 *PatientRecords.csv*，其中包含 *PatientID*、*MRN*、*LastName*、*FirstName* 和 *SSN* 等列。

3. 注意敏感数据字段的格式。 特别是，内容中可能包含逗号的字段（例如，包含值"Seattle，WA"的街道地址）在解析时将解析为两个单独的字段（如果选择 .csv 格式）。 若要避免这种情况，请使用 .tsv 格式，或在敏感数据表中用双引号将包含值的逗号括起来。 如果逗号包含的值也包含空格，则需要创建与相应格式匹配的自定义 SIT。 例如，用于检测包含逗号和空格的多词字符串的 SIT。

## <a name="next-step"></a>后续步骤

- [为基于精确数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>另请参阅

- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
