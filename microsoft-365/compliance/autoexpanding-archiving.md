---
title: 自动扩展存档概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展存档，它为邮箱提供额外的存档Exchange Online存储。
ms.openlocfilehash: e3c203b7c29732d09adedf6282880f7e2805d428
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155078"
---
# <a name="overview-of-auto-expanding-archiving"></a>自动扩展存档概述

在Office 365，存档邮箱为用户提供了额外的邮箱存储空间。 启用用户的存档邮箱后，最多 100 GB 的额外存储空间可用。 过去，当达到 100 GB 存储配额时，组织必须联系 Microsoft 以请求为存档邮箱提供额外的存储空间。 这不再如此。

存档邮箱中的Microsoft 365 (功能称为自动扩展) 存档邮箱中最多提供 1.5 TB 的额外存储空间。 当达到存档邮箱中的存储配额时，Microsoft 365自动 (增量) 增加存档大小，直到存档邮箱达到 1.5 TB。

有关启用自动扩展存档的分步说明，请参阅启用 [自动扩展存档](enable-autoexpanding-archiving.md)。

> [!NOTE]
> 自动扩展存档还支持共享邮箱。 若要为共享邮箱启用存档，需要Exchange Online计划 2 许可证Exchange Online计划 1 Exchange Online Archiving许可证。

## <a name="how-auto-expanding-archiving-works"></a>自动扩展存档的工作原理

如前所述，启用用户的存档邮箱时将创建额外的邮箱存储空间。 启用自动扩展存档后，Microsoft 365定期检查存档邮箱的大小。 当存档邮箱接近其存储限制时，Microsoft 365自动为存档创建额外的存储空间。 如果用户耗尽此额外存储空间，Microsoft 365向用户的存档中增加更多存储空间。 此过程将继续，直到用户的存档大小达到 1.5 TB。 此过程将自动执行，这意味着管理员无需请求额外的存档存储或管理自动扩展存档。

以下是此过程的快速概述。

![自动扩展存档过程的概述。](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 为用户邮箱或共享邮箱启用存档。 创建存储空间为 100 GB 的存档邮箱，存档邮箱的警告配额设置为 90 GB。

2. 管理员为邮箱启用自动扩展存档。 当存档邮箱 (包括"可恢复的项目"文件夹) 达到 90 GB 时，它将转换为自动扩展存档，Microsoft 365 会将存储空间添加到存档中，直到达到最大大小 1.5 TB。 预配额外存储空间可能需要 30 天。

   > [!NOTE]
   > 如果邮箱处于保留状态或分配到保留策略，则当启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。 同样，存档警告配额增加到 100 GB。

3. Microsoft 365时自动增加更多存储空间。

> [!IMPORTANT]
> 自动扩展存档仅支持用于单个用户的邮箱 (或共享邮箱) 增长速率不会超过每天 1 GB。 用户的存档邮箱只供该用户使用。 不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱。 Microsoft 保留拒绝在用户的存档邮箱用于存储其他用户的存档数据的情况下或其他不恰当的使用情况下进行其他存档的权利。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>将哪些内容移动到其他存档存储空间？

若要充分利用自动扩展存档存储，文件夹可能会移动。 Microsoft 365在向存档添加额外存储空间时移动哪些文件夹。 有时，移动文件夹时，会自动创建一个或多个子文件夹，同时将原始文件夹中的项目分发到这些文件夹，以便于移动过程。 查看文件夹中的文件夹列表的存档Outlook，这些子文件夹将显示在原始文件夹下。 用于命名这些子Microsoft 365的命名约定是_yyyy (**\<folder name\> mmm dd， yyyyy** h_mm) 创建的，其中：

- **yyyy** 是文件夹中收到邮件的年份。

- **mmm dd， yyyy h_m** is the date and time that the subfolder was created by Office 365， in UTC format， based on the user's time zone and regional settings in Outlook.

以下屏幕截图显示了将邮件移动到自动展开存档之前和之后的文件夹列表。

 **添加额外存储空间之前**

![预配自动扩展存档之前存档邮箱的文件夹列表。](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **添加额外存储空间后**

![设置自动扩展存档后存档邮箱的文件夹列表。](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如前所述，Microsoft 365将项目移动到子文件夹 (并按上述命名约定命名它们) 以帮助将内容分发到辅助存档。 但是，将项目移动到子文件夹可能并不总是如此。 有时，整个文件夹可能会移到辅助存档中。 在这种情况下，文件夹将保留其原始名称。  在文件夹列表中的文件夹列表中Outlook文件夹已移动到辅助存档。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook自动扩展存档中的项目的要求

若要访问存储在自动扩展存档中的邮件，用户必须使用以下客户端Outlook之一：

- Outlook 2016 2019 Outlook 2019 或 Windows

- Outlook 网页版

- Outlook 2016 2019 for Mac Outlook 或 Outlook for Mac

下面是使用自动展开存档Outlook Outlook 网页版存档中存储的邮件时要考虑的一些情况。

- 可以访问存档邮箱中的任意文件夹，包括已移动到自动扩展存储区域的文件夹。

- 如果存档邮箱具有至少一个自动扩展存储区域，则不能从存档邮箱或辅助存档中删除文件夹。 换句话说，在设置自动扩展的存储区域后，你无法删除存档中任何文件夹。

- 可以删除自动扩展存储区域中的项目。 但是，你无法使用"恢复已删除邮件"功能来恢复从自动展开的存储区域删除的项目。

- 搜索自动扩展存档在 OWA Outlook中 (可用) 。 与联机存档类似，可以搜索已移动到其他存储区域的项目。 在 OWA 中选择存档作为搜索范围时， (包括自动展开的存档及其) 及其对应的子文件夹。

- 自动展开的存档搜索在当前频道中的Outlook桌面 (预览) 。 在此预览版中，"当前邮箱"范围可用，因此允许您搜索自动展开的存档。 有关此功能和其他支持功能Microsoft 搜索，请参阅如何[Outlook Windows](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)用户Exchange Online利用Microsoft 搜索。 

- Outlook存档中的Outlook和读/未读 (计数Outlook Outlook 网页版) 扩展存档中的项目计数可能不准确。

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>自动扩展存档和其他合规性功能

本节介绍自动扩展存档与其他合规性和数据管理功能之间的功能。

- **电子数据展示：** 使用电子数据展示工具（如内容搜索或In-Place电子数据展示）时，还搜索自动扩展存档中的其他存储区域。

- **保留：** 使用 Exchange Online 中的诉讼保留或安全与合规中心中的电子数据展示案例保留和保留策略等工具将邮箱置于保留状态时，自动扩展存档中的内容也会置于保留状态。

- **邮件记录管理 (MRM) ：** 如果使用 EXCHANGE ONLINE中的 MRM 删除策略来永久删除过期的邮箱项目，则位于自动展开存档中的过期项目也将被删除。

- **导入服务：** 可以使用 Office 365 导入服务将 PST 文件导入到用户的自动展开存档。 您最多可以将 100 GB 的数据从 PST 文件导入用户的存档邮箱。

## <a name="more-information"></a>更多信息

有关自动扩展存档的更多技术详细信息，请参阅[Microsoft 365： Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。
