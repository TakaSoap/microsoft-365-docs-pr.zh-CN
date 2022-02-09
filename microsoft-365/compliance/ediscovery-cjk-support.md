---
title: CJK/Double Byte 对 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解Advanced eDiscovery语言Microsoft 365支持使用双字节字符集的 CJK (朝鲜语) 、日语和朝鲜语。
ms.openlocfilehash: 4c1871eb49754ba93d762989e3cff9c53950d2c6
ms.sourcegitcommit: 57211e8082a3429017ad33fe0e6bd9af203bb7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62487319"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK 语言支持Advanced eDiscovery

Advanced eDiscovery支持双字节字符集语言 (包括简体中文、繁体中文、日语和朝鲜语，在审阅集的以下高级方案中统称为 *CJK* 语言) ：

- 查询 [审阅集内的数据时](review-set-search.md)。

- 在审阅 [集内标记文档时](tagging-documents.md)。

- 当你 [使用近重复检测、](analyzing-data-in-review-set.md) 电子邮件线程和主题分析来分析审阅集内的情况数据时。

## <a name="frequently-asked-questions"></a>常见问题解答

**如何创建搜索以收集包含 CJK 字符的项目？**

在搜索关键字搜索中的内容时，[](building-search-queries.md#keyword-searches)可以将 CJK 字符用于关键字搜索、关键字查询和Advanced eDiscovery。 [](keyword-queries-and-search-conditions.md) 在核心电子数据展示和内容搜索中搜索内容时，也支持搜索 CJK 字符。

我们针对所有搜索运算符和搜索条件 [](keyword-queries-and-search-conditions.md#search-operators)（包括布尔 [](keyword-queries-and-search-conditions.md#search-conditions)运算符 **AND**、**OR**、**NOT** 和 NEAR）提供 CJK **支持**。

如果您确定内容位置或项目包含 CJK 字符，但搜索不会返回任何结果，请单击查询语言-国家/地区图标 ![内容搜索中的查询语言国家/地区图标。](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) 并选择相应的语言国家/地区区域性代码值进行搜索。 默认语言/区域是中性的。

**能否同时搜索多种语言？**

这取决于你的搜索方案。

- 在[查询评价集](review-set-search.md)内的数据时Advanced eDiscovery，可以搜索多种语言。

- 创建 [搜索以收集数据时](create-draft-collection.md)，请为所面向的每种语言创建单独的集合。 例如，如果要搜索同时包含中文和朝鲜语的文档，请为第一个集合选择"中文"，然后为第二个集合选择"朝鲜语"。

**我看不到查询语言-国家/地区图标来选择审阅集内查询的语言。如何在审阅集搜索中指定查询语言？**

对于审阅集查询，无需指定文档语言。 Advanced eDiscovery内容添加到审阅集时自动检测文档语言。 这有助于在审阅集内优化查询结果。

**能否在文件元数据中查看 [检测到的语言](view-documents-in-review-set.md#file-metadata)？**

否，在文件元数据中看不到检测到的语言。

**我能否在审阅集内按文档语言进行筛选**？

否，不能按审阅集内的文档语言进行筛选、排序或搜索。

**此 CJK 版本用于审阅集方案是否会影响我的任何现有搜索和审阅集？**

否，现有的搜索和审阅集不会更改。 无需对现有数据重新索引，英文文本的搜索结果将相同。

**如何将显示语言更改为中文、日语或朝鲜语？**

若要了解如何更改显示语言和时区，请参阅如何为用户设置语言和[Office 365](/office365/troubleshoot/access-management/set-language-and-region)。

## <a name="known-issues"></a>已知问题

- OCR 不支持图像文件的 CJK 字符

- CJK (批注视图中的电子邮件文件) *.eml 和 *.msg 文件。[](view-documents-in-review-set.md#annotate-view)

- CJK 语言不支持 [在](view-documents-in-review-set.md#text-view) 文本视图中突出显示搜索词。

- [用于分析数据](using-relevance.md)的相关性模块不支持 CJK 语言。

- [CJK](managing-holds.md#manage-non-custodial-holds) 语言不支持基于查询的保留。