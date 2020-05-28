---
title: 在 Microsoft 365 管理中心中管理电子邮件应用程序访问
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
description: 了解如何选择用户可用于访问电子邮件、日历和联系人的移动应用程序。
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400048"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中管理电子邮件应用程序访问

使用移动电子邮件访问设置选择组织中的哪些移动应用人员可使用哪些移动应用来访问电子邮件、日历和联系人的工作或学校帐户。
  
> [!IMPORTANT]
> 你的组织将有权访问此设置，除非你使用的是 Microsoft Intune 或在 Exchange 管理中心中配置了移动设备管理设置。 
  
## <a name="manage-email-app-options"></a>管理电子邮件应用程序选项

> [!IMPORTANT]
>  如果不使用此功能，则不会对用户体验做出任何更改。 他们将能够使用任何移动电子邮件应用来访问其移动设备上的电子邮件、日历和联系人的工作或学校帐户。 
    
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务和加载项</a>页面。 

2. 在 "**移动电子邮件访问选项**" 页上，选中 "" 复选框，然后选择组织中的用户如何在其设备上使用电子邮件应用程序：
  
选择用于设置组织中的用户如何从其移动设备访问其工作或学校帐户的选项
  
- **仅限 outlook** -组织中的用户将需要在其移动设备上使用 Outlook for Android 或 Outlook for iOS 应用。 
    
- **任何电子邮件应用**程序-组织中的所有用户都将收到使用 Outlook 的提示，但他们可以选择使用任何电子邮件应用程序。 
    
- **任何电子邮件应用**程序-组织中的新用户或设备将收到一次使用 Outlook 的提示，但他们可以选择使用任何电子邮件应用程序。 
    
有关更多详细信息，请查看[从移动设备访问电子邮件的选项](access-email-from-a-mobile-device.md)。
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>在您的组织中激活了新用户或设备

一旦组织中的用户将他们的工作或学校电子邮件添加到第三方电子邮件应用或新设备，他们就会收到**Microsoft 代表你的组织**发送的电子邮件。 电子邮件将告知他们使用 Outlook 移动应用程序的好处，并提供下载位置的链接。 然后，你的用户可以选择是继续使用第三方应用还是选择使用 Outlook 移动应用。 在用户首次收到此电子邮件后的24小时内，其设备将处于隔离阶段，并且不会更新电子邮件、日历和联系人数据。 如果他们选择使用 Outlook 移动应用程序，则第三方应用程序将保持隔离，并且数据将仅与 Outlook 移动应用同步。 如果他们决定继续使用第三方应用程序，则数据将立即开始同步。 如果在前24小时内未执行任何操作，则会将电子邮件从其收件箱中删除，并且数据将从服务器自动开始同步。
  
## <a name="previously-configured-users-in-your-organization"></a>组织中以前配置的用户

如果你决定向组织中的所有人推荐 Outlook，除了上述针对新用户所述的体验之外，以前将其工作或学校电子邮件帐户连接到第三方应用的用户将在启用此设置的48小时内**代表你的组织收到 Microsoft 代表你的组织**发送的电子邮件。 电子邮件将告知他们使用 Outlook 移动应用程序的好处，并提供下载位置的链接。 然后，你的用户可以选择是继续使用第三方应用还是选择使用 Outlook 移动应用。 在用户首次收到此电子邮件后的24小时内，其设备将处于隔离阶段，并且不会更新电子邮件、日历和联系人数据。 如果他们选择使用 Outlook 移动应用程序，则第三方应用程序将保持隔离，并且数据将仅与 Outlook 移动应用同步。 如果他们决定继续使用第三方应用程序，则数据将立即开始同步。 如果在前24小时内未执行任何操作，则会将电子邮件从其收件箱中删除，并且数据将从服务器自动开始同步。 
  

