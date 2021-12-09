---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何为你的组织设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: c99d856382f88d9938a124770179610d8a16a33c
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61373040"
---
# <a name="set-up-multifactor-authentication"></a>设置多重身份验证

多重身份验证意味着你和你的员工必须提供多种登录 Microsoft 365 的方式，它是保护业务的最简单方法之一。 根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。 

> [!IMPORTANT]
> 如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且你在登录时收到 MFA 的提示，则已经自动为你的订阅启用[安全性默认值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="watch-turn-on-multifactor-authentication"></a>观看：打开多重身份验证

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2MuO3?autoplay=false]

1. 转到 Microsoft 365 管理中心：<a href="https://admin.microsoft.com/ " target="_blank">https://admin.microsoft.com</a>。
1. 选择 **显示全部**，然后选择 **Azure Active Directory 管理中心**。
1. 选择 **Azure Active Directory**、**属性**、**管理安全默认值**。
1. 在“**启用安全默认设置**”下，选择“**是**”，然后选择“**保存**”。

## <a name="before-you-begin"></a>准备工作

- 只有全局管理员才能管理 MFA。 有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。
- 如果你启用了旧版每用户 MFA，请[关闭旧版每用户 MFA](#turn-off-legacy-per-user-mfa)。
- 如果你在 Windows 设备上有 Office 2013 客户端，[启用 Office 2013 客户端的新式验证](./enable-modern-authentication.md)。
- 高级：如果你有使用 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。 有关详细信息，请参阅[具有 Azure Active Directory 多重身份验证的高级方案和第三方 VPN 解决方案](/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

### <a name="turn-off-legacy-per-user-mfa"></a>关闭旧版每用户 MFA

如果你以前已启用了每用户 MFA，则必须在启用安全性默认值之前将其关闭。

1. 在 Microsoft 365 管理中心中，在左侧导航栏中选择“**用户**”\>“**活动用户**”。
1. 在“**活动用户**”页面上，选择“**多重身份验证**”。
1. 在“多重身份验证”页面上，选择每个用户并将其多重身份验证状态设置为“**禁用**”。

## <a name="turn-security-defaults-on-or-off"></a>打开或关闭安全性默认值

对于大多数组织来说，安全性默认值提供很好的额外登录安全性级别。 有关详细信息，请参阅[什么是安全性默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果你的订阅是新的，则可能已自动为你启用安全性默认值。

可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。

1. 使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。
2. 在左侧导航栏中，选择“**全部显示**”，然后在 **管理中心** 下，选择“**Azure Active Directory**”。
3. 在 **Azure Active Directory 管理中心** 中选择“**Azure Active Directory**”\>“**属性**”。
4. 在页面底部，选择“**管理安全性默认值**”。
5. 选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

如果你已在使用 [基准条件访问策略](/azure/active-directory/conditional-access/concept-baseline-protection)，则会在你使用安全性默认值之前，提示你将其关闭。

1. 转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2. 选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。
3. 转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4. 在页面底部，选择“**管理安全性默认值**”。
5. 选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

## <a name="use-conditional-access-policies"></a>使用条件访问策略

如果你的组织具有更精细的登录安全需求，条件访问策略可以为你提供更多控制。 “条件访问”允许你在向用户授予对应用程序或服务的访问权限前，先创建和定义对登录事件作出反应并请求其他操作的策略。

> [!IMPORTANT]
> 在你启用条件访问策略前，请关闭每用户 MFA 和安全性默认值。

条件访问适用于已购买 Azure AD Premium P1 的客户，或包含此功能的许可证（如 Microsoft 365 商业高级版 和 Microsoft 365 E3）。有关详细信息，请参阅 [创建条件访问策略](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

可通过 Azure AD 高级 P2 许可证或包含此项的许可证（例如 Microsoft 365 E5）来获得基于风险的条件访问。 有关详细信息，请参阅[基于风险的条件访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。

有关 Azure AD P1 和 P2 的详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="turn-on-modern-authentication-for-your-organization"></a>为你的组织启用新式验证

对于大多数订阅，新式验证会自动启用，但如果在 2017 年 8 月之前购买了订阅，可能需要启用新式验证才能使用多重身份验证等功能，以在 Outlook 等 Windows 客户端中正常工作。


1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中，在左侧导航栏中选择“**设置**”\>“**组织设置**”。
2. 在“**服务**”选项卡下，选择“**新式验证**”，然后在“**新式验证**”窗格中，确保已选择“**启用新式验证**”选项。选择“**保存更改**”。


## <a name="next-steps"></a>后续步骤

- [如何注册以获取更多验证方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [何为：多重身份验证](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [注册后如何登录](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何更改其他验证方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>相关内容


[打开多重身份验证](../../business-video/turn-on-mfa.md)（视频）

[打开手机的多重身份验证](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)（视频）