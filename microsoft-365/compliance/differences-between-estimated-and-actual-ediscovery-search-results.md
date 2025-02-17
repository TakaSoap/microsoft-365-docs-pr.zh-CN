---
title: 估计和实际电子数据展示搜索结果之间的差异
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: 了解为什么使用电子数据展示工具在Office 365中运行的搜索中估计和实际搜索结果可能有所不同。
ms.openlocfilehash: 5ec234ed698e621a629aecf7adf34fb675b29034
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783834"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>估计和实际电子数据展示搜索结果之间的差异

本文适用于可以使用以下Microsoft 365电子数据展示工具之一运行的搜索： 

- 内容搜索
- 核心电子数据展示

运行电子数据展示搜索时，所使用的工具将返回 (项数及其总大小) 与搜索条件匹配的估计值。 例如，在Microsoft 365 合规中心中运行搜索时，估计的搜索结果将显示在所选搜索的浮出控件页上。
  
![搜索浮出控件页上显示的结果估计。](../media/EstimatedSearchResults1.png)
  
在将结果导出到本地计算机和随搜索结果一起下载的导出摘要报表中时，对电子数据展示导出工具中显示的总大小和项数的估计值相同。
  
**电子数据展示导出工具中的估计结果**

![电子数据展示导出工具中的估计结果。](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**导出摘要报表中的估计结果**

![导出摘要报表中包含估计的搜索结果。](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
但是，正如你在导出摘要报表的上一个屏幕截图中注意到的那样，下载的实际搜索结果的大小和数量不同于估计的搜索结果的大小和数量。
  
![估计和下载的搜索结果之间的差异。](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
下面是造成这些差异的一些原因：
  
- **结果的估计方式**。 搜索结果的估计只是，估计值 (，而不是满足搜索查询条件的项的实际计数) 。 若要编译Exchange项的估计值，请使用电子数据展示工具从Exchange数据库请求满足搜索条件的消息 ID 列表。 但是，导出搜索结果时，将重新运行搜索，并从Exchange数据库中检索实际消息。 因此，这些差异可能会因项目估计数和实际项数的确定而产生。

- **在估算和导出搜索结果的时间之间发生的更改**。 导出搜索结果时，将重新启动搜索，以收集搜索索引中满足搜索条件的最新项。 在收集估计的搜索结果和导出搜索结果的时间之间，可能会创建、发送或接收符合搜索条件的其他项目。 此外，估计搜索结果时搜索索引中的项可能不再存在，因为它们在导出搜索结果之前已从内容位置清除。 缓解此问题的一种方法是为电子数据展示搜索指定日期范围。 另一种方法是保留内容位置，以便保留和清除项目。

   可导致的其他问题包括估计和导出的搜索结果之间的差异：

  - 使用日期查询时项目增加。 这通常由以下两个事项导致：

  - 在SharePoint中保留版本控制。 如果文档从保留的网站中删除并启用文档版本控制，将保留所删除文档的所有版本。

  - 日历项。 接受和拒绝消息，定期会议将自动继续在后台创建具有旧日期的新项目。

  - 使用保留时，可能会在用户的主要邮箱和存档邮箱中保留同一项。 当用户手动将项目移动到其存档时，可能会发生这种情况。

  - 尽管这种情况很少见，但在应用保留时，内置日历项的维护 (用户无法编辑，但包含在许多搜索结果中) 可能会不时删除。 定期删除日历项将导致导出的项减少。

- **未表达的项**。 未进行搜索的项目可能会导致估计的搜索结果与实际搜索结果之间的差异。 导出搜索结果时，可以包括未执行的项。 如果在导出搜索结果时包含未执行的项，则可能会导出更多项。 这将导致估计和导出的搜索结果之间的差异。

    使用内容搜索工具时，可以选择在导出搜索结果时包含未执行的项。 在浮出页上列出了搜索返回的未表达项数以及其他估计的搜索结果。 任何未表达的项目也将包含在估计搜索结果的总大小中。 导出搜索结果时，可以选择包括或不包含未执行的项。 如何配置这些选项可能会导致已下载的估计搜索结果与实际搜索结果之间的差异。

- **导出包含所有内容位置的内容搜索的结果**。 如果从中导出结果的搜索是搜索组织中的所有内容位置，则将仅导出包含与搜索条件匹配的项的内容位置中的未执行项。 In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. 但是，所有内容位置的未表达式项 (即使不包含与搜索查询) 匹配的项目也会包含在估计的搜索结果中。

    或者，如果从包含的特定内容位置导出结果的搜索，则将从搜索中指定的所有内容位置导出搜索条件) 未排除 (的未执行项。 在这种情况下，已导出的未表达项的估计数目和未导出的项数应相同。

    之所以不从组织中的每一个位置导出未导出的项目，是因为这可能会增加导出错误的可能性，并增加导出和下载搜索结果所需的时间。

- **搜索估算中未包含SharePoint和OneDrive中的未表达项**。 估计的搜索结果中不包括来自SharePoint网站和OneDrive for Business帐户的未执行项。 这是因为SharePoint索引不包含未表达项的数据。 搜索估算中仅包含邮箱中的未表达式项目。 但是，如果在导出搜索结果时包含未表达的项目，则包括SharePoint和OneDrive中的未表达项，这将增加实际导出的项目数。 这将导致估计的结果 (不包含SharePoint和OneDrive网站) 中未表达的项目与下载的实际项目之间的差异。 有关仅从包含与搜索条件匹配的项目的内容位置导出未表达式项的规则仍适用于这种情况。

- **SharePoint和OneDrive中的文档版本**。 搜索SharePoint网站和OneDrive帐户时，文档的多个版本不包括在估计的搜索结果计数中。 但是，在导出搜索结果时，可以选择包括所有文档版本。 如果在导出搜索结果时包含文档版本，则将增加导出项的实际 (数和总大小) 。

- **SharePoint文件夹**。 如果SharePoint中的文件夹与搜索查询匹配，例如按日期搜索，则搜索估算将包括那些具有上次修改日期范围的文件夹的计数 (但不包括这些文件夹中的项) 。 导出搜索结果时，将导出文件夹中的项，但不会导出实际文件夹。 结果是导出的项数将大于估计的搜索结果数。 如果文件夹为空，则导出的实际搜索结果数将减少一项，因为实际文件夹未导出。

   > [!NOTE]
   > 运行基于查询的搜索时，可以通过向查询添加以下条件来排除SharePoint文件夹： `NOT(ContentType:folder)`

- **SharePoint列表**。 如果SharePoint列表的名称与搜索查询匹配，则搜索估算将包含列表中所有项的计数。 导出搜索结果时，列表 (和列表项) 将导出为单个 CSV 文件。 这将减少实际导出的项数。 如果列表包含附件，则附件将作为单独的文档导出，这也会增加导出的项数。

   > [!NOTE]
   > 运行基于查询的搜索时，可以通过向查询添加以下条件来排除SharePoint列表： `NOT(ContentType:list)`

- **原始文件格式与导出的文件格式**。 对于Exchange项，搜索结果的估计大小是使用原始Exchange消息大小计算的。 但是，电子邮件在 PST 文件中导出，或者作为单个邮件导出 (格式为 EML 文件) 。 这两个导出选项使用的文件格式与原始Exchange消息不同，这会导致导出的文件总大小不同于估计的文件大小。

- **在导出过程中取消重复Exchange项**。 对于Exchange项，取消重复会减少导出的项数。 在导出搜索结果时，可以选择取消重复搜索结果。 对于Exchange邮件，这意味着仅导出邮件的单个实例，即使该邮件可能在多个邮箱中找到。 估计的搜索结果包括消息的每个实例。 因此，如果在导出搜索结果时选择“去重复”选项，则导出的项的实际数量可能远远低于估计的项目数。

搜索结果报告 (Results.csv 文件) 包含每个重复邮件的条目，并标识存在重复邮件的源邮箱。 这有助于识别包含重复邮件的所有邮箱。

> [!NOTE]
> 如果在导出搜索结果或仅下载报表时未选择已 **加密或未识别格式选项的 Include 项** ，则会下载索引错误报告，但它们没有任何条目。 这并不意味着没有任何索引错误。 它只是意味着未表达的项目未包含在导出中。
