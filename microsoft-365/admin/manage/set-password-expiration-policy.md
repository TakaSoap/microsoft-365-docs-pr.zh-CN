---
title: 为组织设置密码过期策略
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 了解如何在 Microsoft 365 管理中心为组织设置密码过期策略。
ms.openlocfilehash: 59e9f4e36843d7c5d977a49d42ae0a11e9a2db25
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362105"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>为组织设置密码过期策略

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

## <a name="before-you-begin"></a>准备工作

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md)

只有[全局管理员或密码管理员](../add-users/about-admin-roles.md)才能执行这些步骤。

如果你是用户，则你不没有将密码设置为永不过期的权限。 让你的工作单位或学校的技术支持人员代你执行本文中的步骤。

作为管理员，可让用户密码在特定天数后过期，或设置密码永不过期。

## <a name="set-password-expiration-policy"></a>设置密码过期策略

> [!Tip]
> 默认情况下，密码设置为在 90 天后过期。 当前研究强烈表明，强制实施的密码更改弊大于利。 它们会导致用户选择安全性更弱的密码、重复使用密码，或者以很容易被黑客猜出的方式更新旧密码。 如果将密码设为永不过期，则建议启用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。

如果希望用户密码在特定时段后过期，请按照以下步骤操作。
> [!IMPORTANT]
> 只有[全局管理员](../add-users/about-admin-roles.md)可执行这些步骤。
  
1. 在管理中心，转到“**设置**”\>“**组织设置**”。

2. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全和隐私</a>页面。
 只有全局管理员能看到“安全和隐私”选项。
  
3. 选择“**密码过期策略**”。
  
4. 如果不希望强制用户更改密码，请选择“**将用户密码设置为以下天数后过期**”旁边的复选框。
  
5. 输入密码过期频率。 请在 14 到 730 之间选择一个天数。
  
6. 在第二个框中键入通知用户其密码将过期的时间，然后选择“**保存**”。 选择从 1 到 30 的天数。

7. 用户的密码到期后会收到通知，通知会出现在其屏幕右下角。
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>密码到期功能重要事项须知

下面是自 2018 年 1 月起有关此功能运行原理的一些注意事项须知：
  
- 对于仅使用 Outlook 应用的用户，在其密码在缓存中过期之前，不会强制其重置 Microsoft 365 密码。这一到期时间有可能在实际到期日期数天后抵达。这一情况在管理级别尚无解决方法。

- 用户不会收到提示其密码将在 X 天后过期的电子邮件通知。是否需要此功能？ **[在此处投票！](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**

## <a name="prevent-last-password-from-being-used-again"></a>防止再次使用上一次使用过的密码

如果要防止用户重新使用旧密码，可通过在本地 Active Directory (AD) 中强制实施密码历史记录来实现。 请参阅[创建自定义密码策略](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)。

在 Azure AD 中，当用户更改密码后，不能再次使用上一个密码。 密码策略适用于直接在 Azure AD 中创建和管理的所有用户帐户。 无法修改此密码策略。 请参阅 [Azure AD 密码策略](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)。

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>将用户密码哈希从本地 Active Directory 同步到 Azure AD (Microsoft 365)

本文适用于为仅限云的用户 (Azure AD) 设置过期策略。 它不适用于使用密码哈希同步、直通身份验证或本地联合身份验证（如 ADFS）的混合标识用户。
  
要了解如何将用户密码哈希从本地 AD 同步到 Azure AD，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Azure Active Directory 中的密码策略和账户限制

可在 Azure Active Directory 中设置更多密码策略和限制。 有关详细信息，请参阅[ Azure Active Directory 中的密码策略和帐户限制](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy)。

## <a name="update-password-policy"></a>更新密码策略

Set-MsolPasswordPolicy cmdlet 会更新指定的域或租户的密码策略。 需要两个设置：第一个用于指示密码在必须更改之前的有效时长，第二个用于指示在用户收到第一封显示其密码即将过期的通知时将触发的密码过期日期之前的剩余天数。

若要了解如何更新特定域或租户的密码策略，请参阅 [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)。

## <a name="related-content"></a>相关内容

[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)

[重置密码](../add-users/reset-passwords.md)