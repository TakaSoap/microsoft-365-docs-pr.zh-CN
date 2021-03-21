---
title: 电子数据展示搜索结果中的重复数据删除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: 了解如何消除重复电子数据展示搜索结果，以便只导出电子邮件的一个副本。
ms.openlocfilehash: 859c1c41a9f6a530cdefce5220039fbc6ba1a14e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925668"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>电子数据展示搜索结果中的重复数据删除

本文介绍了电子数据展示搜索结果的重复数据展示的工作原理，并说明了重复数据消除算法的限制。
  
使用电子数据展示工具导出电子数据展示搜索结果时，可以选择取消复制导出的结果。 应用场景 启用重复数据删除 (默认情况下，不会启用重复数据删除) ，即使已在搜索的邮箱中找到了同一邮件的多个实例，也只会导出电子邮件的一个副本。 重复数据删除通过减少导出搜索结果后必须审阅和分析的项目数来帮助您节省时间。 但是，了解重复数据删除的工作原理很重要，并且请注意，算法存在一些限制，可能会导致在导出过程中将唯一项标记为重复项。
  
## <a name="how-duplicate-messages-are-identified"></a>如何标识重复邮件

电子数据展示工具使用以下电子邮件属性的组合来确定邮件是否是重复邮件：
  
- **InternetMessageId** - 此属性指定电子邮件的 Internet 邮件标识符，该标识符是引用特定邮件的特定版本的全局唯一标识符。 此 ID 由发送邮件的发件人的电子邮件客户端程序或主机电子邮件系统生成。 如果用户向多个收件人发送邮件，则每个邮件实例的 Internet 邮件 ID 都相同。 对原始邮件的后续修订将收到不同的邮件标识符。 

- **ConversationTopic** - 此属性指定邮件的对话线程的主题。 **ConversationTopic** 属性的值是描述对话的总体主题的字符串。 一个接收者包含初始消息和在回复初始邮件时发送的所有邮件。 同一对话中的邮件 **ConversationTopic** 属性的值相同。 此属性的值通常是生成对话的初始邮件的主题行。 

- **BodyTagInfo** - 这是一个内部 Exchange 存储属性。 通过检查邮件正文中的各种属性可计算此属性的值。 此属性用于标识邮件正文的差异。 

在电子数据展示导出过程中，将针对符合搜索条件的每封邮件比较这三个属性。 如果两条或多条 (邮件的这些属性相同) 则确定这些邮件是重复的，如果启用了重复数据删除，则只会导出邮件的一个副本。 导出的邮件称为"源项目"。 有关重复邮件的信息包含在 **Results.csvManifest.xml导出** 的搜索结果中包含的一些报告。 在Results.csv **文件中** ，通过"复制到项目"列中有一个值 **来标识重复** 邮件。 此列中的值与导出的邮件的 **"项目** 标识"列中的值匹配。 
  
下图显示了重复消息如何显示在Results.csvManifest.xml导出的搜索结果中的重复消息。  这些报告不包括之前描述的电子邮件属性，这些属性用于重复数据消除算法。 相反，报告包括由 Exchange 存储分配给项目的 Item **Identity** 属性。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv Excel (中查看的报表) 
  
![查看报告报告中有关重复Results.csv的信息](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml Excel (中查看的报表) 
  
![查看报告报告中有关重复Manifest.xml的信息](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
此外，导出报告中还包括来自重复邮件的其他属性。 这包括重复邮件所在的邮箱、该邮件是否已发送到通讯组，以及该邮件是抄送还是密件抄送给其他用户。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>重复数据消除算法的限制

重复数据删除算法存在一些已知的限制，这些限制可能会导致唯一项标记为重复项。 了解这些限制非常重要，以便您可以决定是否使用可选的重复数据消除功能。
  
有一种重复数据删除功能可能会错误地将邮件标识为重复邮件，而不是导出 (但仍在导出报告中将邮件作为) 。 这些是用户编辑但不发送的消息。 例如，假设用户在 Outlook 中选择一封邮件，复制邮件内容，然后将邮件粘贴到新邮件中。 然后，用户通过删除或添加附件或更改主题行或正文本身来更改其中一个副本。 如果这两条消息与电子数据展示搜索的查询匹配，那么在导出搜索结果时，如果启用了重复数据删除，则只会导出其中一条消息。 因此，即使原始邮件或复制的邮件已更改，也不会发送任何修改后的邮件，因此 **InternetMessageId、ConversationTopic** 和 **BodyTagInfo** 属性的值未更新。  但如前所述，导出报告中将列出这两条消息 
  
启用"写入时复制"页面保护功能时，还可以将唯一邮件标记为重复邮件，就像邮箱置于诉讼保留或保留In-Place一样。 "写入时复制"功能会复制原始邮件 (并保存到用户的"可恢复的项目"文件夹的"版本"文件夹中) 然后再保存对原始项目的修订。 在这种情况下，"可恢复邮件"文件夹中 (修订副本和原始邮件) 可能会被视为重复邮件，因此只会导出其中一封邮件。
  
> [!IMPORTANT]
> 如果重复数据删除算法的限制可能会影响搜索结果的质量，则导出项目时不应启用重复数据删除。 如果本节中所述的情况不太可能成为搜索结果中的一个因素，并且您希望减少最有可能重复的项目数，则应考虑启用重复数据删除。 
  
## <a name="more-information"></a>更多信息

- 使用下列电子数据展示工具之一导出搜索结果时，本文中的信息适用：

  - Office 365 合规中心内的内容搜索

  - Exchange Online 中的就地电子数据展示

  - SharePoint Online 中的电子数据展示中心

- 有关导出搜索结果的信息，请参阅：

  - [导出内容搜索](export-search-results.md)

  - [导出内容搜索报告](export-a-content-search-report.md)

  - [将In-Place电子数据展示搜索结果导出到 PST 文件](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [在电子数据展示中心导出内容和创建报表](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)