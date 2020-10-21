---
title: 针对高级电子数据展示的 CJK/双字节支持
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft 365 中的高级电子数据展示如何支持中文、日语和朝鲜语 (CJK) 语言，这些语言使用双字节字符集。
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626930"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>适用于高级电子数据展示的 CJK 语言支持

高级电子数据展示支持双字节字符集语言 (这些语言包括简体中文、繁体中文、日语和朝鲜语，在审阅集中统称为以下高级方案的 *CJK* 语言) ：

- [查询评审集中的数据](review-set-search.md)时。

- 在 [审阅集中标记文档](tagging-documents.md)时。

- 通过使用接近重复检测、电子邮件线程和主题分析来 [分析评审集合中的事例数据](analyzing-data-in-review-set.md) 时。

## <a name="frequently-asked-questions"></a>常见问题解答

**如何创建搜索以收集包含 CJK 字符的项目？**

在高级电子数据展示中搜索内容时，可以使用 CJK 字符进行 [关键字搜索](building-search-queries.md#keyword-searches)、 [关键字查询和搜索条件](keyword-queries-and-search-conditions.md) 。 搜索核心电子数据展示和内容搜索中的内容时，也支持搜索 CJK 字符。

我们为所有 [搜索运算符](keyword-queries-and-search-conditions.md#search-operators) 和 [搜索条件](keyword-queries-and-search-conditions.md#search-conditions)（包括布尔运算符 **and**、 **OR**、 **NOT**和 **NEAR**）提供 CJK 支持。

如果你确信内容位置或项目包含 CJK 字符，但搜索不返回任何结果，请单击 "查询语言-国家/地区" 图标 ![查询语言-内容搜索中的国家/地区图标](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) 并为搜索选择对应的语言国家区域性代码值。 默认语言/区域是中性的。

**是否可以一次搜索多个语言？**

这取决于您的搜索方案。

- 当您在高级电子数据展示中 [查询审阅集中的数据](review-set-search.md) 时，您可以搜索多种语言。

- [创建用于收集数据的搜索](create-search-to-collect-data.md)时，请为目标的每种语言创建单独的搜索。 例如，如果要搜索同时包含中文和朝鲜语的文档，请选择 "中文" 作为第一个查询，然后选择 "朝鲜语" 作为第二个查询。

**我看不到查询语言-国家/地区图标在审阅集中选择查询的语言。如何在审阅集搜索中指定查询语言？**

对于审阅集查询，无需指定文档语言。 将内容添加到审阅集时，高级电子数据展示将自动检测文档语言。 这有助于优化评审集中的查询结果。

**是否可以查看 [文件元数据](view-documents-in-review-set.md#file-metadata)中检测到的语言？**

否，在文件元数据中看不到检测到的语言。

**能否按文档语言在审阅集中进行筛选**？

否，不能在审阅集中对文档语言进行筛选、排序或搜索。

**此 CJK 发布的检查集方案是否会影响我现有的搜索和审阅集？**

否，现有搜索和审阅集都不会更改。 您无需对现有数据重新编制索引，英语文本的搜索结果也将相同。

**如何将我的显示语言更改为中文、日语或朝鲜语？**

有关如何更改显示语言和时区的信息，请参阅 [如何设置 Office 365 的语言和区域设置](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)。

## <a name="known-issues"></a>已知问题

- OCR 不支持从图像文件中 CJK 字符

- CJK 语言不支持电子邮件文件 (例如，* .eml 和 * .msg) 中的 [批注视图](view-documents-in-review-set.md#annotate-view) 。

- CJK 语言不支持 [文本视图](view-documents-in-review-set.md#text-view) 中的搜索词突出显示。

- 用于分析数据的 [相关性模块](using-relevance.md) 不支持 CJK 语言。

- CJK 语言不支持[基于查询的保留](managing-holds.md#manage-non-custodial-holds)。 
