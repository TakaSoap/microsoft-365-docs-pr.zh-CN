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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 将管理员添加到高级电子数据展示事例中时，被视为部分索引的任何内容都会重新处理，以使其完全可搜索。
ms.openlocfilehash: 95e087884b65628565e596dc8ae9f33aadc4cd9f
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527552"
---
# <a name="advanced-indexing-of-custodian-data"></a>保管人数据的高级索引

将管理员添加到高级电子数据展示事例中时，被视为部分索引的任何内容都会重新处理，以使其完全可搜索。  此过程称为 "*高级索引*"。 可以对内容进行部分索引，其中包括图像存在、不受支持的文件类型或在遇到索引文件大小限制时的原因。

若要了解有关处理支持和部分索引项目的详细信息，请参阅：

- [高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md)

- [处理 Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)

- [由 Exchange 搜索编制索引的文件格式](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后，您可以了解重新处理的有效性。  在事例的 "**处理**" 选项卡上的 "高级索引结果" 视图中，图表列出了添加到*混合索引*中的项目数。  混合索引是高级电子数据展示用于存储重新处理的内容的位置。

此视图还包括需要修正的项目数，以及按文件类型显示的错误的另一个图形。 有关详细信息，请参阅：

- [修正处理数据时出现的错误](error-remediation.md)

- [单个项目错误更正](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>更新保管人的高级索引

将管理员添加到高级电子数据展示事例中时，将重新处理所有部分索引项目。 但是，随着时间的推移，可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。  如有必要，可以为特定的保管人更新索引。 有关详细信息，请参阅[在高级电子数据展示事例中管理保管人](manage-new-custodians.md#re-index-custodian-data)。 您还可以通过单击 "**处理**" 选项卡上的 "更新"**索引**来更新事例中所有保管人的索引。

> [!NOTE]
> 更新保管人索引是一个长时间运行的过程。 建议您在一种情况下每日更新索引不超过一次。
