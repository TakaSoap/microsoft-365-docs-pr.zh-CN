---
title: 在Microsoft 365 管理中心中管理电子邮件应用访问权限
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkEXCHANGE
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何选择用户可用于访问电子邮件、日历和联系人的移动应用。
ms.openlocfilehash: 5f5a96a0ac44757cfe168db87deb494019759c36
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780228"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>管理Microsoft 365 管理中心中的电子邮件应用访问权限

使用移动电子邮件访问设置来选择组织中的哪些移动应用可用于访问其工作或学校帐户以访问电子邮件、日历和联系人。
  
> [!IMPORTANT]
> 组织将有权访问此设置，除非使用Microsoft Intune或已在<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理中心</a>配置了移动设备管理设置。
  
## <a name="manage-email-app-options"></a>管理电子邮件应用选项

> [!IMPORTANT]
> 如果不使用此功能，则不会更改用户的体验。 他们将能够使用任何移动电子邮件应用从其移动设备访问其工作或学校帐户的电子邮件、日历和联系人。

1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务和&amp;加载项</a>页面。

2. 在 **“移动电子邮件访问选项** ”页上，选中复选框，然后选择组织中的用户在其设备上使用电子邮件应用的方式：
  
选择设置组织中的用户如何从其移动设备访问其工作或学校帐户的选项
  
- **仅Outlook** - 组织中的用户需要在其移动设备上使用适用于 Android 或 iOS 应用的Outlook或Outlook。

- **任何电子邮件应用** - 组织中的所有用户都将被提示使用Outlook，但他们可以选择使用任何电子邮件应用。

- **任何电子邮件应用** - 组织中的新用户或设备将提示使用Outlook一次，但他们可以选择使用任何电子邮件应用。

有关更多详细信息，请查看 [有关从移动设备访问电子邮件的选项](access-email-from-a-mobile-device.md)。
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>组织中已激活新用户或设备

一旦组织中的用户将其工作或学校电子邮件添加到第三方电子邮件应用或新设备，他们将 **代表你的组织** 收到来自 Microsoft 的电子邮件。 该电子邮件将让他们了解使用Outlook移动应用的好处，并提供指向下载位置的链接。 然后，用户可以选择是继续使用第三方应用，还是选择使用Outlook移动应用。 在用户首次收到此电子邮件后的 24 小时内，他们的设备将被隔离，电子邮件、日历和联系人数据将不会更新。 如果他们选择使用Outlook移动应用，则第三方应用将保持隔离状态，数据将仅与Outlook移动应用同步。 如果他们决定继续使用第三方应用，数据将立即开始同步。 如果在前 24 小时内未执行任何操作，则电子邮件将从其收件箱中删除，数据将自动从服务器开始同步。
  
## <a name="previously-configured-users-in-your-organization"></a>组织中以前配置的用户

如果决定向组织中的每个人推荐Outlook，除了上述新用户的体验外，以前将工作或学校电子邮件帐户连接到第三方应用的用户将在启用此设置后的 48 小时内 **代表组织** 收到 Microsoft 发来的电子邮件。 该电子邮件将让他们了解使用Outlook移动应用的好处，并提供指向下载位置的链接。 然后，用户可以选择是继续使用第三方应用，还是选择使用Outlook移动应用。 在用户首次收到此电子邮件后的 24 小时内，他们的设备将被隔离，电子邮件、日历和联系人数据将不会更新。 如果他们选择使用Outlook移动应用，则第三方应用将保持隔离状态，数据将仅与Outlook移动应用同步。 如果他们决定继续使用第三方应用，数据将立即开始同步。 如果在前 24 小时内未执行任何操作，则电子邮件将从其收件箱中删除，数据将自动从服务器开始同步。
