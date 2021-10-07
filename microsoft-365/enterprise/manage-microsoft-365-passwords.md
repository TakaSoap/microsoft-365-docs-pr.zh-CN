---
title: 管理Microsoft 365用户帐户密码
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何管理Microsoft 365用户帐户密码。
ms.openlocfilehash: 6a0d4298f3d6c46ab067795bccf01123605ce1aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150734"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>管理Microsoft 365用户帐户密码

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以通过几种Microsoft 365管理用户帐户密码，具体取决于您的标识配置。 可以在 Microsoft 365 管理中心、Active Directory 域服务 (AD DS) 或 Azure Active Directory (Azure AD) 管理中心管理用户帐户。 [](/admin)

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>规划管理用户帐户密码的去向和方式

在哪里以及如何管理用户帐户取决于要用于用户帐户的标识Microsoft 365。 这两种模型是仅云模型和混合模型。
  
### <a name="cloud-only"></a>仅限云

在中管理用户帐户密码：

- [Microsoft 365 管理员中心](/admin)
- Azure AD 管理中心
    
### <a name="hybrid"></a>混合

使用混合标识，密码存储在 AD DS 中，因此必须使用本地 AD DS 工具管理用户帐户密码。 即使使用密码哈希同步 (PHS) （其中 Azure AD 在 AD DS 中存储已哈希版本的哈希版本）时，你和用户也必须在 AD DS 中管理其密码。

使用 [密码写回](#pw_writeback)，你的用户可以通过 Azure AD 更改其 AD DS 密码。

## <a name="prevent-bad-passwords"></a>防止密码错误

所有用户都应使用 [Microsoft 的密码指南](https://www.microsoft.com/research/publication/password-guidance)来创建用户帐户密码。

若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。 例如，你可以指定特定于贵组织的术语，例如：

- 品牌名称
- 产品名称
- 位置（例如公司总部）
- 特定于公司的内部条款
- 具有特定公司含义的缩写

你可以禁止云 [中和](/azure/active-directory/authentication/concept-password-ban-bad) 本地 [AD DS 中的错误密码](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)。

## <a name="simplify-user-sign-in"></a>简化用户登录

Azure AD 无缝单一 Sign-On (Azure AD 无缝 SSO) 可与 PHS 和 Pass-Through 身份验证 (PTA) 一起运行，以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码，在许多情况下，也无需键入其用户名。 这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。

将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。 请参阅[配置 Azure AD 无缝 SSO 说明](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>简化 AD DS 的密码更新

通过密码写回，你可以允许用户通过 Azure AD 重置其密码，然后复制到 AD DS。 用户无需访问其本地 AD DS 来更新其密码。 这非常适用于对本地网络没有远程访问连接的漫游或远程用户。

需要密码写回才可充分利用 Azure AD 标识保护功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。

有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

## <a name="simplify-password-resets"></a>简化密码重置

SSPR (自助服务密码重置) 用户可以重置或解锁其密码或帐户。 为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。 必须先启用 [密码写回](#pw_writeback) ，然后才能部署密码重置。

请参阅[推出密码重置说明](/azure/active-directory/authentication/howto-sspr-deployment)。