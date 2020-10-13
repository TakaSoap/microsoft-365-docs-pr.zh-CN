---
title: 解决共享邮箱问题
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您在使用共享邮箱时遇到问题，请尝试这些解决方案。
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445503"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>解决共享邮箱问题

如果您在创建或使用共享邮箱时看到错误消息，请尝试这些可能的解决方案。 

## <a name="error-when-creating-shared-mailboxes"></a>创建共享邮箱时出错
<a name="bkmk_Fix"> </a>

如果您看到错误消息，则 **代理地址 "smtp： <共享邮箱名称 \> " 已由代理地址或 "" LegacyExchangeDN 使用 \<name> 。请选择其他代理地址**，这表示你尝试为共享邮箱提供一个已在使用中的名称。 例如，假设希望共享邮箱命名为 info@domain1 和 info@domain2。 可通过 2 种方法执行此操作：

  - 使用 Windows PowerShell。 有关说明，请参阅以下博客文章： [在不同的域中创建具有相同别名的共享邮箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 将第二个共享邮箱命名为不同于开头的内容，以避免出现此错误。 然后在管理中心内，将共享邮箱重命名为您想要的。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>有关使用共享邮箱时不具有发送权限的错误

如果您创建了一个共享邮箱，然后尝试从该邮箱发送邮件，则可能会出现以下情况：

**无法发送此邮件。您没有代表指定用户发送邮件的权限。**

当 Microsoft 365 遇到复制延迟问题时，将出现此消息。 当您的新共享邮箱的信息 (或添加的用户) 在我们的所有数据中心之间进行复制时，它会在一小时后消失。 请等待一小时，然后再尝试发送一封邮件。

## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)


    

