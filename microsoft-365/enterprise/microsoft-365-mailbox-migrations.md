---
title: Microsoft 365 邮箱迁移
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文包含有关 Microsoft 365 邮箱迁移的简要摘要以及用于迁移的 cmdlet 的列表。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546794"
---
# <a name="microsoft-365-mailbox-migrations"></a>Microsoft 365 邮箱迁移

通过基于 Exchange 的混合部署，客户可以选择将本地 Exchange 邮箱移动到 [Exchange online](https://docs.microsoft.com/Exchange/exchange-online) 组织，或将 exchange Online 邮箱移动到 [exchange 内部部署](https://docs.microsoft.com/Exchange/exchange-server) 组织。 在内部部署组织和 Exchange Online 组织之间移动邮箱时使用迁移批处理。

客户可以使用以下 cmdlet 查看有关邮箱迁移的统计信息和其他信息：

- [Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics)：提供用户邮箱的默认统计信息，其中包括状态、邮箱大小、存档邮箱大小和完成百分比。
- [Get 邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
)：提供组织中的邮箱对象和属性的摘要列表。
- "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/get-recipient)：" 提供现有的已启用邮件的对象（如邮箱、邮件用户、联系人和通讯组）的列表。
- [New-moverequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest)：提供正在进行的邮箱迁移的详细状态。
- [Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser)：提供有关邮箱移动和迁移用户的信息。
- [New-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch)：提供有关当前迁移批处理的状态信息。
- [Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics)：提供有关特定用户的迁移状态的详细信息。
- [Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)：提供有关邮箱的信息，如大小、邮件数以及上次访问时间。

有关 cmdlet 的详细信息，请参阅 [Exchange Online 中的移动和迁移 cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)。
