---
title: 适用于 Office 2013 和 Office 2016 客户端应用的新式验证工作原理
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: 了解 Microsoft 365 新式验证功能如何针对 Office 2013 和 2016 客户端应用以不同方式工作。
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921662"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>新式验证如何适用于 Office 2013、Office 2016 和 Office 2019 客户端应用

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

阅读本文，了解 Office 2013、Office 2016 和 Office 2019 客户端应用如何使用基于 Exchange Online、SharePoint Online 和 Skype for Business Online 的 Microsoft 365 租户上的身份验证配置的现代身份验证功能。

> [!NOTE]
> 旧版客户端应用（如 Office 2010 和 Office for Mac 2011）不支持新式验证，只能用于基本身份验证。

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Microsoft 365 服务新式验证的可用性

对于 Microsoft 365 服务，新式验证的默认状态为：
  
- 默认情况下 **为** Exchange Online 打开。 请参阅 [在 Exchange Online 中启用或禁用](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) 新式验证以将其关闭或打开。 
    
- 默认情况下 **为** SharePoint Online 启用。 
    
- 默认情况下 **，Skype** for Business Online 已打开。 请参阅 [启用 Skype for Business Online 进行新式验证 ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)以将其关闭或打开。

> [!NOTE]
> 对于在 2017 年 8 月 1 日 **之前** 创建的租户，将为 Exchange Online 和 Skype for Business Online 默认 **关闭** 新式验证。
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Office 客户端应用的登录行为

默认情况下，Office 2013 客户端应用支持旧式身份验证。 旧版意味着它们支持 Microsoft Online 登录助手或基本身份验证。 为了使这些客户端使用新式验证功能，Windows 客户端必须设置注册表项。 有关说明，请参阅 [在 Windows 设备上为 Office 2013 启用新式验证](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)。

若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。必须在每台要启用新式验证的设备上设置注册表项：
  
|**注册表项**|**类型**|**值** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
阅读 [如何将新式验证 (ADAL) Skype for Business，](./hybrid-modern-auth-overview.md) 了解它如何与 Skype for Business 一起运行。 
  
默认情况下，Office 2016 和 Office 2019 客户端支持新式验证，客户端无需任何操作来使用这些新流。 但是，要使用旧版身份验证，需要显式操作。
  
单击下面的链接，查看 Office 2013、Office 2016 和 Office 2019 客户端身份验证如何与 Microsoft 365 服务一起运行，具体取决于是否启用新式验证。
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

下表介绍了 Office 2013、Office 2016 和 Office 2019 客户端应用在连接 Exchange Online 时（带或不带新式验证）的身份验证行为。
  
|Office 客户端应用程序版本****|注册表项存在？****|新式验证打开？****|为租户启用新式验证的身份验证行为 (默认) ****|为租户关闭新式验证的身份验证行为****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |不 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |是  <br/> |在 Outlook 2013、2016 或 2019 上强制使用新式验证。 <br/> [更多信息](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|在 Outlook 客户端中强制使用新式验证。<br/> |
|Office 2019  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |
|Office 2019  <br/> |是，EnableADAL=0  <br/> |否  <br/> |基本身份验证  <br/> |基本身份验证  <br/> |
|Office 2016  <br/> |不 <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |是  <br/> |在 2013、2016 或 2019 上强制使用新式验证。 <br/> [更多信息](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|在 Outlook 客户端中强制使用新式验证。<br/> |
|Office 2016  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |
|Office 2016  <br/> |是，EnableADAL=0  <br/> |否  <br/> |基本身份验证  <br/> |基本身份验证  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |基本身份验证  <br/> |基本身份验证  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用基本身份验证。 未启用租户时，服务器将拒绝新式验证。  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

下表介绍了 Office 2013、Office 2016 和 Office 2019 客户端应用程序在连接 SharePoint Online 时（带或不带新式验证）的身份验证行为。
  
|Office 客户端应用程序版本****|注册表项存在？****|新式验证打开？****|为租户启用新式验证的身份验证行为 (默认) ****|为租户关闭新式验证的身份验证行为****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |仅新式验证。  <br/> |连接失败。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |仅新式验证。  <br/> |连接失败。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2016  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |仅新式验证。  <br/> |连接失败。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |仅新式验证。  <br/> |连接失败。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |仅新式验证。  <br/> |连接失败。  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

下表介绍了 Office 2013、Office 2016 和 Office 2019 客户端应用在连接 Skype for Business Online 时（带或不带新式验证）的身份验证行为。
  
|Office 客户端应用程序版本****|注册表项存在？****|新式验证打开？****|为租户启用新式验证的身份验证行为****|为租户禁用新式验证的身份验证行为 (默认) ****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |
|Office 2019  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2016  <br/> |否，或 EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |
|Office 2016  <br/> |是，EnableADAL = 0  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2013  <br/> |否  <br/> |否  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
|Office 2013  <br/> |是，EnableADAL = 1  <br/> |是  <br/> |首先尝试新式验证。 如果服务器拒绝新式验证连接，则使用 Microsoft Online 登录助手。 未启用 Skype for Business Online 租户时，服务器拒绝新式验证。  <br/> |仅适用于 Microsoft Online 登录助手。  <br/> |
   
## <a name="see-also"></a>另请参阅

[在 Windows 设备上启用适用于 Office 2013 的新式验证](../admin/security-and-compliance/enable-modern-authentication.md)

[适用于 Microsoft 365 的 Multi-Factor Authentication](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[使用多重身份验证登录到 Microsoft 365](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 企业版概述](microsoft-365-overview.md)