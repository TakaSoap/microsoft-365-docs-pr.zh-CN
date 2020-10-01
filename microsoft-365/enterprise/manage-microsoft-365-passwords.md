---
title: 管理 Microsoft 365 用户帐户密码
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
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
description: 了解如何管理 Microsoft 365 用户帐户密码。
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328484"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>管理 Microsoft 365 用户帐户密码

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

您可以通过几种不同的方式管理 Microsoft 365 用户帐户密码，具体取决于您的身份配置。 可以在 [Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)中管理用户帐户，在 Active Directory 域服务 (AD DS 中) ，或在 Azure Active Directory (azure AD) 管理中心中进行管理。

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>规划管理用户帐户密码的位置和方式

如何管理用户帐户的位置和方式取决于要用于 Microsoft 365 的标识模型。 这两种模型是仅云和混合模式。
  
### <a name="cloud-only"></a>仅限云

可以在中管理用户帐户密码：

- [Microsoft 365 管理员中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Azure AD 管理中心
    
### <a name="hybrid"></a>混合

使用混合标识，密码存储在 AD DS 中，因此您必须使用内部部署 AD DS 工具来管理用户帐户密码。 即使使用密码哈希同步 (PHS) （其中 Azure AD 在 AD DS 中存储已哈希版本的哈希版本），您和用户必须在 AD DS 中管理其密码。

通过 [密码写回](#pw_writeback)，你的用户可以通过 Azure AD 更改其 AD DS 密码。

## <a name="prevent-bad-passwords"></a>防止密码错误

所有用户都应使用 [Microsoft 的密码指南](https://www.microsoft.com/research/publication/password-guidance)来创建用户帐户密码。

若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。 例如，你可以指定特定于贵组织的术语，例如：

- 品牌名称
- 产品名称
- 位置（例如公司总部）
- 特定于公司的内部条款
- 具有特定公司含义的缩写

您可以 [在云中](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 和 [本地 AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)中禁止错误密码。

## <a name="simplify-user-sign-in"></a>简化用户登录

Azure AD 无缝单一登录 (Azure AD 无缝 SSO) 与 PHS 和传递身份验证 (PTA) 配合使用，以允许您的用户登录使用 Azure AD 用户帐户的服务，而无需键入其密码，在许多情况下，他们的用户名。 这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。

将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。 请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>简化对 AD DS 的密码更新

使用密码写回，可以允许用户通过 Azure AD 重置其密码，然后将其复制到 AD DS。 用户无需访问本地 AD DS 即可更新其密码。 这非常适用于对本地网络没有远程访问连接的漫游或远程用户。

需要密码写回才可充分利用 Azure AD 标识保护功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。

有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

## <a name="simplify-password-resets"></a>简化密码重置

自助服务密码重置 (SSPR) 允许用户重置或解锁其密码或帐户。 为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。 必须先启用 [密码写回](#pw_writeback) ，然后才能部署密码重置。

请参阅[推出密码重置说明](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

