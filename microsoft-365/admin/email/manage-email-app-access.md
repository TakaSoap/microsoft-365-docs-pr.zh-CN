---
title: 在应用中管理电子邮件Microsoft 365 管理中心
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何选择用户可用于访问电子邮件、日历和联系人的移动应用。
ms.openlocfilehash: d38730df158758ceb310ba25f45f222d7893afe2d0aefc601a17663e85787552
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53825975"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>管理电子邮件应用中的电子邮件Microsoft 365 管理中心

使用移动电子邮件访问设置选择贵组织人员可用于访问其工作或学校帐户以访问电子邮件、日历和联系人的移动应用。
  
> [!IMPORTANT]
> 你的组织将有权访问此设置，除非你使用 Microsoft Intune或在管理中心中配置了移动设备Exchange设置。 
  
## <a name="manage-email-app-options"></a>管理电子邮件应用选项

> [!IMPORTANT]
>  如果不使用此功能，用户体验不会发生变化。 他们将可以使用任何移动电子邮件应用访问其工作或学校帐户的电子邮件、日历和移动设备中的联系人。 
    
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务和加载项</a>页面。 

2. 在 **"移动电子邮件访问选项** "页上，选中此复选框，然后选择组织中用户如何在其设备上使用电子邮件应用：
  
选择用于设置组织中用户如何从移动设备访问工作或学校帐户的选项
  
- **Outlook -** 你的组织的用户需要使用适用于 Android Outlook 或 Outlook for iOS 应用的移动设备。 
    
- **任何电子邮件** 应用 - 系统将提示您组织的所有用户使用Outlook，但他们可以选择使用任意电子邮件应用。 
    
- **任何电子邮件** 应用 - 将提示你组织中新用户或设备使用Outlook，但他们可以选择使用任意电子邮件应用。 
    
有关详细信息，请查看 [用于从移动设备访问电子邮件的选项](access-email-from-a-mobile-device.md)。
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>在组织中激活新用户或设备

只要贵组织的用户将工作或学校电子邮件添加到第三方电子邮件应用或新设备，他们就会代表你的组织收到 **来自 Microsoft 的电子邮件**。 电子邮件将让他们了解使用 Outlook 移动应用的好处，并提供指向下载位置的链接。 然后，用户可以选择是继续使用第三方应用，还是选择使用Outlook应用。 在用户首次收到此电子邮件后的 24 小时内，他们的设备将隔离，并且不会更新电子邮件、日历和联系人数据。 如果用户选择使用Outlook应用，则第三方应用将保持隔离状态，并且数据将仅与Outlook同步。 如果他们决定继续使用第三方应用，数据将立即开始同步。 如果在前 24 小时内未采取任何操作，电子邮件将从收件箱中删除，并且数据将自动从服务器开始同步。
  
## <a name="previously-configured-users-in-your-organization"></a>组织中以前配置的用户

如果你决定向组织中的每个人推荐 Outlook，除了上述新用户的体验之外，之前将工作或学校电子邮件帐户连接到第三方应用的用户将在启用此设置的 48 小时内代表你的组织收到 **来自 Microsoft** 的电子邮件。 电子邮件将让他们了解使用 Outlook 移动应用的好处，并提供指向下载位置的链接。 然后，用户可以选择是继续使用第三方应用，还是选择使用Outlook应用。 在用户首次收到此电子邮件后的 24 小时内，他们的设备将隔离，并且不会更新电子邮件、日历和联系人数据。 如果用户选择使用Outlook应用，则第三方应用将保持隔离状态，并且数据将仅与Outlook同步。 如果他们决定继续使用第三方应用，数据将立即开始同步。 如果在前 24 小时内未采取任何操作，电子邮件将从收件箱中删除，并且数据将自动从服务器开始同步。 
  

