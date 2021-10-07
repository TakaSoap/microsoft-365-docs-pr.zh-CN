---
title: 会话的会话Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: 了解如何使用会话超时在客户端应用中平衡安全性和Microsoft 365访问。
ms.openlocfilehash: f5b7c87cabfd6f80061c2795568cd53955caa10f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213261"
---
# <a name="session-timeouts-for-microsoft-365"></a>会话的会话Microsoft 365

会话生存期是身份验证的重要部分，Microsoft 365是平衡安全性和提示用户提供凭据次数的重要组件。

## <a name="session-times-for-microsoft-365-services"></a>服务会话Microsoft 365时间

当用户在任何 Web 应用或Microsoft 365中进行身份验证时，将建立会话。 在会话期间，用户无需重新进行身份验证。 当用户处于非活动状态、关闭浏览器或选项卡时，或者其身份验证令牌由于其他原因（例如重置其密码时）过期时，会话可能会过期。 Microsoft 365服务具有不同的会话超时，以对应于每个服务的典型使用。

下表列出了所有服务Microsoft 365生存期：

| Microsoft 365 服务 | 会话超时 |
|:-----|:-----|
|Microsoft 365 管理中心  <br/> |系统要求你每 8 小时提供一次管理中心的凭据。  <br/> |
|SharePoint Online  <br/> |5 天不活动，只要用户选择"保持 **我登录"。** 如果用户在上一次登录SharePoint 24 小时或数小时后再次访问联机版，超时值将重置为 5 天。  <br/> |
|Outlook Web App  <br/> |6 小时。  <br/> 可以使用 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet 中的 _ActivityBasedAuthenticationTimeoutInterval_ 参数更改此值。  <br/> |
|Azure Active Directory  <br/>  (在启用了新式Office Microsoft 365的 Windows 客户端中)   <br/> | 新式验证使用访问令牌和刷新令牌向用户授予对使用 Microsoft 365 资源Azure Active Directory。 访问令牌是成功进行身份验证后提供的 JSON Web 令牌，有效期为 1 小时。 还提供了生存期较长的刷新令牌。 当访问令牌过期时，Office客户端使用有效的刷新令牌获取新的访问令牌。 如果用户的初始身份验证仍然有效，则此交换成功。  <br/>  刷新令牌的有效期为 90 天，如果连续使用，则有效期为吊销前。  <br/>  刷新令牌可能会因多个事件而失效，例如：  <br/>  自颁发刷新令牌以来，用户密码已更改。  <br/>  管理员可以应用条件访问策略，以限制对用户尝试访问的资源的访问。  <br/> |
|SharePoint和OneDrive Android、iOS 和 Windows 10  <br/> |访问令牌的默认生存期为 1 小时。 刷新令牌的默认最大非活动时间为 90 天。  <br/> [详细了解令牌以及如何配置令牌生存期](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> 若要撤销刷新令牌，可以重置用户Microsoft 365密码  <br/> |
|Yammer Microsoft 365 Sign-In  <br/> |浏览器的生存期。 如果用户关闭浏览器，并Yammer新浏览器中访问Yammer，用户会使用 Microsoft 365。 如果用户使用缓存 Cookie 的第三方浏览器，他们可能需要在重新打开浏览器时重新进行身份验证。  <br/> > [!NOTE]> 这仅适用于使用 Microsoft 365 Sign-In for Yammer 的网络。           |