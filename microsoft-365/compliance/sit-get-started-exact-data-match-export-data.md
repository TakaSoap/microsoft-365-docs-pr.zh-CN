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
description: 了解如何导出源数据以获取基于确切数据匹配的敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 913870afeef443c5b346172099b0cd47db13e52e
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760682"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>为基于精确数据匹配的敏感信息类型导出源数据


敏感数据表是包含值行的文本文件，你将根据这些值比较文档中的内容来标识敏感数据。 这些值可能是要在内容中检测并采取保护措施的文本形式的个人可识别信息、产品记录或其他敏感数据。

以受支持格式之一导出数据后，可以继续创建 EDM 架构。

## <a name="defining-your-edm-sensitive-type"></a>定义 EDM 敏感类型

定义 EDM 敏感类型时，最关键的决策之一是哪些字段将是主字段。 主要字段需要遵循可检测模式，并将其定义为可搜索字段 (EDM 架构中) 列。 辅助字段不需要遵循任何模式，因为它们将与与主要字段的匹配项周围的所有文本进行比较。

使用以下规则可帮助你确定应用作主要字段的列：

- 如果必须基于在敏感数据表中存在与字段匹配的单个值来检测敏感数据，而不考虑其周围是否存在任何其他敏感数据，则必须将该列定义为 EDM 类型的主元素。 
- 如果必须在内容中检测到敏感数据表中不同字段的多个组合，请识别大多数此类组合共有的列，并将它们指定为主要元素，并将其他字段的组合指定为辅助元素。
- 如果要用作主字段的列不遵循可检测的模式，如任何文本字符串或遵循可检测模式，这些模式会出现在大量文档或电子邮件的某个位置，请尝试选择其他结构较好的列作为主要元素。

例如，如果你有列`full name`，`date of birth``account number`而且，即使名字和`Social Security Number`姓氏是要检测到的不同数据组合通用的列，此类字符串也不容易遵循可识别的模式，并且可能难以定义为敏感信息类型。 这是因为某些名称甚至可能不以大写开头，它们可能由两个、三个或更多个单词构成，甚至可能包含数字或其他非字母字符。 出生日期可以更容易识别，但由于每封电子邮件和大多数文档将包含至少一个日期，它也不是一个好的候选人。 社会保障号码和帐号是用作主要领域的好人选。

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>以.csv、.tsv 或管道分隔格式保存敏感数据

1. 确定要使用的敏感信息。 将数据导出到应用（如Microsoft Excel）并将文件保存在文本文件中。 该文件可以保存.csv (逗号分隔值) 、.tsv (选项卡分隔值) 或管道分隔 (|) 格式。 如果数据值可能包含逗号（如街道地址），建议使用 .tsv 格式。
数据文件最多可包括以下内容：
   - 高达 1 亿行的敏感数据
   - 每个数据源最多 32 列（字段）
   - 最多 5 个列（字段）标记为可搜索

2. 在.csv或 .tsv 文件中构建敏感数据，以便第一行包含用于基于 EDM 的分类的字段的名称。 在文件中，可能有字段名称，例如“ssn”、“birthdate”、“firstname”、“lastname”。 列标题名称不能包含空格或下划线。 例如，本文中使用的示例 .csv 文件名为 *PatientRecords.csv*，其中包含 *PatientID*、*MRN*、*LastName*、*FirstName* 和 *SSN* 等列。

3. 注意敏感数据字段的格式。 具体而言，在其内容中可能包含逗号的字段，例如，如果选择了.csv格式，则在分析时，包含值“Seattle，WA”的街道地址将被分析为两个单独的字段。 若要避免这种情况，请使用 .tsv 格式或用敏感数据表中的双引号括住包含值的逗号。 如果包含值的逗号也包含空格，则需要创建与相应格式匹配的自定义 SIT。 例如，使用逗号和空格检测多字字符串的 SIT。

## <a name="next-step"></a>后续步骤

- [为基于精确数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>另请参阅

- [基于精确数据匹配的敏感信息类型入门](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
