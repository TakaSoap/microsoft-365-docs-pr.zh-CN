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
description: 将保管人添加到高级电子数据展示案例时，会重新处理被视为部分索引的任何内容，使其完全可搜索。
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750753"
---
# <a name="advanced-indexing-of-custodian-data"></a>保管人数据的高级索引

将保管人添加到高级电子数据展示案例后，将重新处理被视为部分索引的任何内容，使其完全可搜索。  此过程称为 *高级索引*。 内容可能由于多种原因（包括存在图像、不支持的文件类型或遇到索引文件大小限制）而部分编制索引。

若要了解有关处理支持和部分索引项的更多信息，请参阅：

- [高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md)

- [处理 Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)

- [由 Exchange 搜索编制索引的文件格式](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>查看高级索引结果

完成高级索引过程后，您可以了解重新处理的有效性。  在案例的"处理"选项卡上的"高级索引结果"视图中，图形列出了添加到混合索引 *中的项目数*。  混合索引是高级电子数据展示存储重新处理的内容的位置。

此视图还包括需要修正的项目数和按文件类型显示的另一个错误图。 有关详细信息，请参阅：

- [修正处理数据时出现的错误](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [单个项目错误更正](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>更新保管人的高级索引

将保管人添加到高级电子数据展示案例时，将重新处理所有部分索引项。 但是，随着时间的推移，可能会向用户的邮箱或 OneDrive 帐户添加更多的部分索引项目。  如有必要，可以更新特定保管人索引。 有关详细信息，请参阅 ["管理高级电子数据展示"案例中的保管人](manage-new-custodians.md#re-index-custodian-data)。 您还可以通过单击"处理"选项卡上的"更新索引"来更新情况下所有保管人 **索引**。

> [!NOTE]
> 更新保管人索引是一个长时间运行的过程。 建议您在一种情况下每天更新索引不要超过一次。
