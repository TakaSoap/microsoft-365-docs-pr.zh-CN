---
title: 无限制存档概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展存档，为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029428"
---
# <a name="overview-of-unlimited-archiving"></a>无限制存档概述

在 Office 365 中，存档邮箱为用户提供了额外的邮箱存储空间。 启用用户的存档邮箱后，最多 100 GB 的额外存储空间可用。 过去，当达到 100 GB 存储配额时，组织必须联系 Microsoft 以请求为存档邮箱提供额外的存储空间。 情况不再如此。

Microsoft 365 中的无限制存档功能 (*自动* 扩展存档) 在存档邮箱中提供额外的存储空间。 当达到存档邮箱中的存储配额时，Microsoft 365 会自动增加存档的大小，这意味着用户不会用完邮箱存储空间，管理员也无需为存档邮箱请求额外存储空间。

有关启用自动扩展存档的分步说明，请参阅"[启用无限制存档"。](enable-unlimited-archiving.md)

> [!NOTE]
> 自动扩展存档还支持共享邮箱。 若要启用共享邮箱的存档，需要 Exchange Online 计划 2 许可证或具有 Exchange Online Archiving 许可证的 Exchange Online 计划 1 许可证。

## <a name="how-auto-expanding-archiving-works"></a>自动扩展存档的工作原理

如前所述，启用用户的存档邮箱时将创建额外的邮箱存储空间。 启用自动扩展存档后，Microsoft 365 会定期检查存档邮箱的大小。 当存档邮箱接近其存储限制时，Microsoft 365 会自动为存档创建额外的存储空间。 如果用户耗尽此额外存储空间，Microsoft 365 会向用户的存档中增加更多存储空间。 此过程会自动执行，这意味着管理员无需请求额外的存档存储或管理自动扩展存档。

以下是此过程的快速概述。

![自动扩展存档过程概述](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 为用户邮箱或共享邮箱启用存档。 将创建存储空间为 100 GB 的存档邮箱，存档邮箱的警告配额设置为 90 GB。

2. 管理员启用邮箱的自动扩展存档。 当存档邮箱 ("可恢复的项目"文件夹) 达到 90 GB 时，它将转换为自动扩展存档，并且 Microsoft 365 会向存档添加存储空间。 设置额外存储空间可能需要 30 天。

   > [!NOTE]
   > 如果邮箱处于保留状态或已分配给保留策略，则启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。 同样，存档警告配额增加到 100 GB。

3. 如有必要，Microsoft 365 会自动添加更多存储空间。

> [!IMPORTANT]
> 自动扩展存档仅支持用于单个用户 (或共享) 的邮箱，其增长速率不超过每天 1 GB。 用户的存档邮箱只供该用户使用。 不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱。 在用户的存档邮箱用于存储其他用户的存档数据或其他不当使用的情况下，Microsoft 保留拒绝无限制存档的权利。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>哪些内容会移到其他存档存储空间中？

若要高效地使用自动扩展存档存储，文件夹可能会移动。 Microsoft 365 确定在向存档中添加额外存储空间时移动的文件夹。 有时，当移动文件夹时，会自动创建一个或多个子文件夹，并且原始文件夹中的项目将分发到这些文件夹，以便于移动过程。 在 Outlook 中查看文件夹列表的存档部分时，这些子文件夹将显示在原始文件夹下。  Microsoft 365 用于命名这些子文件夹的命名约定是_yyyy (**\<folder name\> mmm dd， yyyyy** h_mm) 创建的，其中：

- **yyyy 是** 文件夹中收到邮件的年份。

- **mmm dd， yyyy h_m** is the date and time that the subfolder was created by Office 365， in UTC format， based on the user's time zone and regional settings in Outlook.

以下屏幕截图显示了将邮件移动到自动展开存档之前和之后的文件夹列表。

 **添加额外存储空间之前**

![预配自动扩展存档之前存档邮箱的文件夹列表](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **添加额外存储空间后**

![设置自动扩展存档后存档邮箱的文件夹列表](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如前所述，Microsoft 365 将项目移动到子文件夹 (，然后使用上述) 命名约定命名它们，以帮助将内容分发到辅助存档。 但是，将项目移动到子文件夹可能并不总是如此。 有时，可能会将整个文件夹移动到辅助存档。 在这种情况下，文件夹将保留其原始名称。  在 Outlook 的文件夹列表中，该文件夹已移动到辅助存档中，这一点并不明显。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>用于访问自动扩展存档中的项目的 Outlook 要求

若要访问存储在自动扩展存档中的邮件，用户必须使用以下 Outlook 客户端之一：

- Outlook 2016 或 Outlook 2019 for Windows

- Outlook 网页版

- Outlook 2016 或 Outlook 2019 for Mac

以下是使用 Outlook 或 Web 上的 Outlook 访问存储在自动扩展存档中的邮件时要考虑的一些情况。

- 可以访问存档邮箱中的任意文件夹，包括已移动到自动扩展存储区域的文件夹。

- Outlook 网页中提供了自动扩展存档搜索功能。 与联机存档类似，只有搜索当前文件夹本身，才能搜索已移动到其他存储区域的项目。 这意味着您必须选择文件夹列表中的存档文件夹，然后选择单个文件夹作为搜索范围。 同样，如果自动扩展存储区域中的文件夹包含子文件夹，则必须单独搜索每个子文件夹。
- "当前频道"和"预览版"中的 Outlook 桌面 (自动展开) 。 在此预览版中，当前邮箱范围可用，因此允许您搜索自动展开的存档。 有关此功能和其他 Microsoft 搜索支持功能的信息，请参阅 [Outlook for Windows](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)连接到 Exchange Online 如何使用 Microsoft 搜索。 

- 在自动展开的存档 (Outlook 和 Outlook 网页) 中的项目计数和读取/未读计数可能不准确。

- 可以删除指向自动扩展存储区的子文件夹中的项目，但无法删除文件夹本身。

- You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>自动扩展存档和其他合规性功能

本节介绍自动扩展存档与其他合规性和数据管理功能之间的功能。

- **电子数据展示：** 使用电子数据展示工具（如内容搜索或In-Place电子数据展示）时，也会搜索自动扩展存档中的其他存储区域。

- **保留：** 使用 Exchange Online 中的诉讼保留或安全与合规中心中的电子数据展示案例保留和保留策略等工具将邮箱置于保留状态时，自动扩展存档中的内容也会置于保留状态。

- **邮件记录管理 (MRM) ：** 如果使用 Exchange Online 中的 MRM 删除策略永久删除过期的邮箱项目，则位于自动扩展存档中的过期项目也将被删除。

- **导入服务：** 可以使用 Office 365 导入服务将 PST 文件导入用户的自动展开存档。 您最多可以将 100 GB 的数据从 PST 文件导入到用户的存档邮箱。

## <a name="more-information"></a>更多信息

有关自动扩展存档的更多技术详细信息，请参阅 [Microsoft 365：自动扩展存档常见问题解答](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。
