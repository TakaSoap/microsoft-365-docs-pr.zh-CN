---
title: 预览电子数据展示搜索结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 预览 Microsoft 365 合规中心中内容搜索或核心电子数据展示搜索返回的结果示例。
ms.openlocfilehash: af0811d0c442d6f064fd336d4261d1f7b2337dc8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189341"
---
# <a name="preview-ediscovery-search-results"></a>预览电子数据展示搜索结果

运行内容搜索或与核心电子数据展示案例关联的搜索后，可以预览搜索返回的结果示例。 预览由搜索查询返回的项目可以帮助你确定搜索是否返回希望的结果，或者是否需要更改搜索查询并重新运行搜索。

预览由搜索返回的结果示例：

1. 在 Microsoft 365 合规中心，转到内容搜索页面或核心电子数据展示案例。

2. 选择搜索以显示飞出页面。

3. 在飞出页的底部，单击 **审阅示例**。

   ![单击弹出页面上的“审阅示例”来预览结果。](../media/PreviewSearchResults1.png)

   将显示一个包含搜索结果示例的页面。

4. 选择一个项以在阅读窗格中查看其内容。

   ![在阅读窗格中预览这些项目。](../media/PreviewSearchResults2.png)

   在上一个屏幕截图中，请注意，预览项目时，将突出显示搜索查询中的关键字。

## <a name="how-the-search-result-samples-are-selected"></a>如何选择搜索结果示例

最多有 1,000 个随机选择的项目可供预览。 除随机选择外，可供预览的项目还必须满足以下条件：

- 最多可预览单个内容位置（邮箱或网站）的 100 个项目。 这意味着，有可能只有不到 1,000 个项目可供预览。 例如，如果搜索 4 个邮箱，搜索返回 1,500 个估计项目，则只有 400 个可用于预览，因为每个邮箱只能预览 100 个项目。

- 对于邮箱项目，只有电子邮件信息可供预览。 无法预览任务、日历项目和联系人等项目。

- 对于网站项目，仅文档可供预览。 无法预览文件夹、列表或列表附件等项目。

## <a name="file-types-supported-when-previewing-search-results"></a>预览搜索结果时支持的文件类型

可以在预览窗格中预览受支持的文件类型。 如果文件类型不受支持，你需要将文件的副本下载到本地计算机（通过单击 **下载原始项目**）。 对于 .aspx Web 页面，尽管你可能没有访问该页面的权限，但该页面的 URL 将包括在内。 未编入索引的项目不提供预览。

以下是受支持的文件类型，可以在搜索结果窗格中对其进行预览。
  
- .txt、.html、.mhtml

- .eml

- .doc、.docx、.docm

- .pptm、.pptx

- .pdf

此外，还支持以下文件容器类型。 可以在预览窗格中查看容器中的文件列表。
  
- .zip

- .gzip