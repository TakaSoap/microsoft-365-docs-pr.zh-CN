---
title: DLP 自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 获取有关数据丢失防护 (DLP) 的自定义敏感信息类型的概述，如主要模式、字符接近度和可信度级别。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817961"
---
# <a name="custom-sensitive-information-types"></a>自定义敏感信息类型

Microsoft 365 包括许多你可直接在组织中使用的内置敏感信息类型，包括用于[数据丢失保护](data-loss-prevention-policies.md) (DLP) 或 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)。 内置敏感信息类型可以根据正则表达式 (regex) 或函数定义的模式，帮助标识和保护信用卡号、银行账号、护照号等。 若要了解详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。

但是，如果需要标识和保护使用组织特定格式的不同敏感信息类型，如员工 ID 或项目号，那该怎么办？ 为此，你可以创建自定义敏感信息类型。

自定义敏感信息类型的基本组成部分是：

- **主要模式**：员工 ID 号、项目编号等。这通常是由正则表达式 (RegEx) 标识，但也可以是关键字列表。

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![确证性证据和临近度窗口的关系图](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![“实例计数”和“匹配准确度”选项](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>创建自定义敏感信息类型

若要在安全与合规中心内创建自定义敏感信息类型，可使用以下几种方法：

- **使用 EDM**（新方法！）可以使用基于精确数据匹配 (EDM) 的分类创建自定义敏感信息类型。 通过此方法，你可以使用可定期刷新的安全数据库创建动态敏感信息类型。 请参阅[使用基于精确数据匹配的分类创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)。

- **使用 PowerShell** 可以使用 PowerShell 创建自定义敏感信息类型。 尽管此方法比使用 UI 更复杂，但你可以拥有更多的配置选项。 请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。

- **使用 UI** 可以使用安全与合规中心 UI 创建自定义敏感信息类型。 通过此方法，你可以使用正则表达式、关键字和关键字字典。 若要了解详细信息，请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。



