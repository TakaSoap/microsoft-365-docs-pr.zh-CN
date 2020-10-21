---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何为你的组织设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 609f6d929408dd15ff6f296dc405448140726c89
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644839"
---
# <a name="set-up-multi-factor-authentication"></a>设置多重身份验证
  
根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。

> [!IMPORTANT]
> 如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且你在登录时收到 MFA 的提示，则已经自动为你的订阅启用[安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。


## <a name="before-you-begin"></a>准备工作

- 只有全局管理员才能管理 MFA。 有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。
- 如果你启用了旧版每人 MFA，[关闭旧版对每个人进行MFA](#turn-off-legacy-per-person-mfa)。 
- 如果你在 Windows 设备上有 Office 2013 客户端，[启用 Office 2013 客户端的新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。
- 高级：如果你有使用 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。 有关详细信息，请参阅[具有 Azure 多重身份验证的高级方案和第三方 VPN 解决方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

## <a name="turn-security-defaults-on-or-off"></a>打开或关闭安全性默认值

对于大多数组织来说，安全性默认值提供很好的额外登录安全性级别。 有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果你的订阅是新的，则可能已自动为你启用安全性默认值。

可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。

1.  使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。
2.  在左侧导航栏中，选择“**显示所有**”，然后在 **管理中心**下，选择 “**Azure Active Directory**”。
3. 在 **Azure Active Directory 管理中心**里选择 “**Azure Active Directory** > **属性**”。
3.  在页面底部，选择“**管理安全性默认值**”。
4.  选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

如果你已在使用 [基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，则会在你使用安全性默认值之前，提示你将其关闭。

1.  转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2.  选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。
2.  转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4.  在页面底部，选择“**管理安全性默认值**”。
5.  选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

## <a name="use-conditional-access-policies"></a>使用条件访问策略

如果你的组织具有更精细的登录安全需求，条件访问策略可以为你提供更多控制。 "条件访问" 允许你在向用户授予对应用程序或服务的访问权限前，先创建和定义对登录事件作出反应并请求其他操作的策略。

> [!IMPORTANT]
> 在你启用条件访问策略前，请关闭“每人 MFA” 和安全性默认值。 

"条件访问" 适用于购买了 Azure AD 高级版 P1 的客户，或购买了包含此项许可证的客户，比如 Microsoft 365 商业高级版和 Microsoft 365 E3。 有关详细信息，请参阅 [创建条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

可通过 Azure AD 高级 P2 许可证或包含此项的许可证（例如 Microsoft 365 E5）来获得基于风险的条件访问。 有关详细信息，请参阅[基于风险的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。

有关 Azure AD P1 和 P2 的详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="turn-on-modern-authentication-for-your-organization"></a>为你的组织启用新式验证

对于大多数订阅来说，新式验证将自动被启用，但如果你在很久前购买了订阅，则可能不会。 必须先启用该功能，然后 MFA 才能使用 Office 应用适当地工作。

1. 在 Microsoft 365 管理中心里，在左侧导航栏中选择“**设置**” > “**组织设置**”。
1. 在“**服务**”选项卡上，选择 “**新式身份验证**”，然后在"**新式身份验证**"窗格中，确保选择 “**启用新式验证**”。 选择“**保存更改**”。

### <a name="turn-off-legacy-per-person-mfa"></a>关闭“旧版每人 MFA”

如果你以前已启用了“每人MFA”，则必须在启用安全性默认值之前将其关闭。

1. 在 Microsoft 365 管理中心里，在左侧导航栏中选择“**用户**” > “**活动用户**”。 
1. 在“**活动用户**”页面上，选择“**多重身份验证**”。
1. 在“多重身份验证”页面上，选择每个用户并将其多重身份验证状态设置为“**禁用**”。

## <a name="next-steps"></a>后续步骤
- [如何注册以获取更多验证方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [何为：多重身份验证](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [注册后如何登录](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何更改其他验证方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)





