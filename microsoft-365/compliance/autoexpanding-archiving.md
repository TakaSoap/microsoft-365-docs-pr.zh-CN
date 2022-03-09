---
title: 了解自动扩展存档
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解为 Exchange Online 邮箱提供额外存档存储的自动扩展存档。
ms.openlocfilehash: 1b4b8d81868cc97fc8e8faf5b0dc449e4c07a868
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328857"
---
# <a name="learn-about-auto-expanding-archiving"></a>了解自动扩展存档

在 Office 365 中，存档邮箱为用户提供额外的邮箱存储空间。 在启用了用户的存档邮箱后，最多可获得 100 GB 的额外存储空间。 过去，当达到 100 GB 存储配额时，组织必须联系 Microsoft 为存档邮箱请求额外存储空间。 但现在不再如此。

Microsoft 365 中的存档功能（称为 *自动扩展存档*）在存档邮箱中提供高达 1.5 TB 的额外存储空间。 达到存档邮箱中的存储配额后，Microsoft 365 自动（并以增量方式）增加存档大小，直到存档邮箱达到 1.5 TB。

有关启用自动扩展存档的分步说明，请参阅 [启用自动扩展存档](enable-autoexpanding-archiving.md)。

> [!NOTE]
> 自动扩展存档还支持共享邮箱。要启用共享邮箱存档，需要 ExchangeOnline 计划 2 许可证或带有 Exchange Online 存档许可证的 Exchange Online 计划 1 许可证。

## <a name="how-auto-expanding-archiving-works"></a>自动扩展存档的工作原理

如前所述，启用用户的存档邮箱时将创建额外的邮箱存储空间。 启用自动扩展存档后，Microsoft 365 定期检查存档邮箱的大小。 当存档邮箱接近其存储限制时，Microsoft 365 自动为存档创建额外的存储空间。 如果用户用完此额外的存储空间，Microsoft 365 将向用户存档添加更多的存储空间。 此过程一直持续，直到用户的存档达到 1.5 TB 大小。 此过程自动发生，这意味着管理员无需请求额外的存档存储或管理自动扩展存档。

以下是该过程的快速概述。

![自动扩展存档过程概述。](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. 为用户邮箱或共享邮箱启用存档。创建存储空间为 100 GB 的存档邮箱，并将存档邮箱的警告配额设置为 90 GB。

2. 管理员为邮箱启用自动扩展存档。 当存档邮箱（包括可恢复项目文件夹）达到 90 GB 时，将转换为自动扩展存档，并且 Microsoft 365 将向该存档添加存储空间，直到其达到最大大小 1.5 TB。 设置额外的存储空间最多可能需要 30 天。

   > [!NOTE]
   > 如果邮箱处于保留状态或以分配给保留策略，则在启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。同样，存档警告配额将增加到 100 GB。

3. 必要时，Microsoft 365 将自动添加更多存储空间。

> [!IMPORTANT]
> 只有用于单个用户（或共享邮箱）的邮箱才支持自动扩展存档，并且增长率不超过每天 1 GB。 用户的存档邮箱只供该用户使用。 不允许使用邮件日志、传输规则或自动转发规则将邮件复制到存档邮箱。 在用户存档邮箱用于存储其他用户的存档数据或存在其他不当使用的实例中，Microsoft 保留拒绝额外存档的权利。

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>哪些内容会移动到额外存档存储空间？

要高效使用自动扩展存档存储，可能会移动文件夹。 在向存档添加额外存储时，Microsoft 365 决定移动哪些文件夹。 有时，在移动文件夹时，会自动创建一个或多个子文件夹，并将原始文件夹中的项分发到这些文件夹，以方便移动过程。 在 Outlook 中查看文件夹列表的存档部分时，这些子文件夹显示在原始文件夹下。 Microsoft 365 用于命名这些子文件夹的命名约定是 <a begin="1" **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**，其中：

- **yyyy** 是收到文件夹中邮件的年份。

- **mmm dd，yyyy h_m** 是 Office 365 根据用户在 Outlook 中的时区和区域设置以 UTC 格式创建子文件夹的日期和时间。

以下屏幕截图显示了邮件移动到自动扩展存档之前和之后的文件夹列表。

 **添加额外存储之前**

![设置自动扩展存档之前存档邮箱的文件夹列表。](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **添加额外存储之后**

![设置自动扩展存档后存档邮箱的文件夹列表。](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> 如前所述，Microsoft 365 将项移动到子文件夹（并使用上述命名约定命名它们为其命名），以帮助将内容分发到辅助存档。 但是，将项目移动到子文件夹可能并非总是如此。 有时可能将整个文件夹移动到辅助存档。 在这种情况下，文件夹将保留其原始名称。  在 Outlook 中的文件夹列表中，文件夹已移动到辅助存档这一现象并不明显。

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook 对于访问自动扩展存档中项目的要求

要访问存储在自动扩展存档中的邮件，用户必须使用以下 Outlook 客户端之一：

- Outlook 2016 或 Outlook 2019 for Windows

- Outlook 网页版

- Outlook 2016 或 Outlook 2019 for Mac

下面是使用 Outlook 或 Outlook 网页版访问自动扩展存档中存储的邮件时要考虑的一些事项。

- 可以访问存档邮箱中的任何文件夹，包括移动到自动扩展存储区域的文件夹。

- 如果存档邮箱具有至少一个自动扩展存储区域，则无法从存档邮箱或辅助存档中删除文件夹。 换言之，在设置自动扩展存储区域后，将无法删除存档中的任何文件夹。

- 可以删除自动扩展存储区域中的项。但在为邮箱启用自动扩展存档后，无法使用“恢复已删除项目”功能来恢复项目。

- Outlook 网页版 (OWA) 中提供了搜索自动扩展存档。 与联机存档类似，可以搜索已移动到额外存储区域的项目。 在 OWA 中选择存档作为搜索范围时，将搜索所有存档（包括自动扩展存档）及其相应的子文件夹。 请注意，在仅限云存档情况下（主邮箱仍在本地），自动扩展存档功能不支持搜索。

- Outlook for Windows 中的每月企业频道提供自动扩展存档搜索。 通过此更新，当前邮箱范围可用，因此可以搜索自动扩展存档。 请注意，在仅限云存档情况下（主邮箱仍在本地），自动扩展存档功能不支持搜索。 有关此功能和其他 Microsoft 搜索支持功能的详细信息，请参阅 [连接到 Exchange Online 的 Outlook for Windows 如何利用 Microsoft 搜索](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)。 

- 在自动扩展存档中，Outlook 中的项目计数和已读/未读计数（在 Outlook 和 Outlook 网页版中）可能并不准确。

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>自动扩展存档和其他合规性功能

本部分介绍自动扩展存档与其他合规性和数据治理功能之间的功能。

- **电子数据展示：** 使用电子数据展示工具（如内容搜索或就地电子数据展示）时，还会搜索自动扩展存档中的额外存储区域。

- **保留：** 当使用诸如 Exchange Online 中诉讼保留或电子数据展示案例保留和安全与合规中心中的保留策略等工具将邮箱置于保留状态时，位于自动扩展存档中的内容也会置于保留状态。

- **邮件记录管理 (MRM)：** 如果使用 Exchange Online 中的 MRM 删除策略来永久删除过期的邮箱项目，也将删除自动扩展存档中的过期项目。

- **导入服务：** 可以使用 Office 365 导入服务将 PST 文件导入到用户的自动扩展存档。 最多可以将 100 GB 的数据从 PST 文件导入到用户的存档邮箱。

## <a name="next-steps"></a>后续步骤

有关自动扩展存档的更多技术详细信息，请参阅 [Microsoft 365：自动扩展存档常见问题解答](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。

如果已准备好启用自动扩展存档，请参阅 [启用自动扩展存档](enable-autoexpanding-archiving.md)。
