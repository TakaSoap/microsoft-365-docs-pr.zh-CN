---
title: 保管人数据的高级索引
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 将保管人添加到Advanced eDiscovery案例时，任何被视为部分索引的内容将被重新处理，使其完全可搜索。
ms.openlocfilehash: 9209732925c87277755c89381791154bf9dbe953
ms.sourcegitcommit: 2e05865beeb2051fd9ece212a46179310b946a46
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2021
ms.locfileid: "61148898"
---
# <a name="advanced-indexing-of-custodian-data"></a>保管人数据的高级索引

将保管人添加到Advanced eDiscovery案例时，任何被视为部分索引或具有索引错误的内容都将被重新编制索引，使其完全可搜索。  此重新编制索引的过程称为 *"高级索引"。* 内容部分编制索引或出现索引错误有很多原因。 这包括图像文件或文件中是否存在图像、不支持的文件类型或文件大小索引限制。 For SharePoint files， Advanced indexing runs only on items are marked as partially indexed or that have indexing errors. 在Exchange中，包含图像附件的电子邮件不会标记为部分索引或带有索引错误。 这意味着，高级索引过程不会对这些文件重新编制索引。

若要详细了解处理支持和部分索引项，请参阅：

- [支持的文件类型Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [电子数据展示中的部分索引项](partially-indexed-items-in-content-search.md)

- [由 Exchange 搜索编制索引的文件格式](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后，您可以了解重新处理的有效性。  在案例的"处理"选项卡上的"高级索引结果"视图中，图形列出了添加到混合索引 *的项目数*。  混合索引是高级电子数据展示存储重新处理的内容的位置。

此视图还包括需要修正的项目数和按文件类型显示的另一个错误图表。 有关更多信息，请参阅：

- [修正处理数据时出现的错误](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [单个项目错误更正](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>更新保管人的高级索引

将保管人添加到一个Advanced eDiscovery案例时，将重新处理所有部分索引项。 但是，随着时间的推移，可能会将更多的部分索引项目添加到用户的邮箱或OneDrive帐户。  如有必要，可以更新特定保管人索引。 有关详细信息，请参阅管理案例[的保管人Advanced eDiscovery案例](manage-new-custodians.md#reindex-custodian-data)。 在一种情况下，您还可以通过单击"处理"选项卡上的 **"** 更新索引"来更新所有保管 **人** 索引。

> [!NOTE]
> 更新保管人索引是一个长时间运行的过程。 建议您在一种情况下每天更新索引不要超过一次。
