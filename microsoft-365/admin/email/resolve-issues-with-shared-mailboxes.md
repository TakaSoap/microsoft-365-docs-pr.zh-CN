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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果遇到共享邮箱问题，请尝试这些解决方案。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926482"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>解决共享邮箱问题

如果在创建和使用共享邮箱时看到错误消息，请尝试这些可能的解决方案。 

## <a name="error-when-creating-shared-mailboxes"></a>创建共享邮箱时出错
<a name="bkmk_Fix"> </a>

如果看到错误消息，代理地址 **"smtp：<shared mailbox name"已被代理地址或" "的 \> LegacyExchangeDN \<name> 使用。请选择其他代理地址**，这意味着你要尝试为共享邮箱指定一个已在使用的名称。 例如，假设希望共享邮箱命名为 info@domain1 和 info@domain2。 可以通过两种方式来执行此操作：

  - 使用 Windows PowerShell。 有关说明，请参阅此博客文章 [：在不同域中创建同名别名的共享邮箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - 将第二个共享邮箱的名称从一开始不同，以绕开错误。 然后在管理中心中，将共享邮箱重命名为您希望它的名称。

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>使用共享邮箱时没有发送权限的错误

如果您创建了共享邮箱，然后尝试从该邮箱发送邮件，您可能会收到以下消息：

**无法发送此消息。您没有代表指定用户发送邮件的权限。**

当用户遇到Microsoft 365延迟问题时，将出现此消息。 在一小时左右的时间，当有关新共享邮箱或已添加 (用户邮箱的信息) 我们的所有数据中心进行复制时，该邮箱应该会消失。 等待一小时，然后再次尝试发送邮件。

## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)


    

