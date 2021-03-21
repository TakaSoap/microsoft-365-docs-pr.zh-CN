---
title: Microsoft 365 与本地环境的集成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: 本文将了解如何将 Microsoft 365 与现有目录服务和本地环境集成。
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923962"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 与本地环境的集成

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

可以将 Microsoft 365 与现有本地 Active Directory 域服务 (AD DS) 以及 Exchange Server、Skype for Business Server 2015 或 SharePoint Server 本地安装集成。
  
 - 集成 AD DS 时，可以同步和管理两种环境的用户帐户。 您还可以将密码哈希同步 (PHS) 或单一登录 (SSO) 以便用户可以使用其本地凭据登录到这两个环境。
 - 与本地服务器产品集成时，将创建混合环境。 在将用户或信息迁移到 Microsoft 365 时，混合环境会有所帮助，或者你可以继续拥有一些用户或本地的一些信息，还有一些信息位于云中。 有关混合环境详细信息，请参阅 [混合云](../solutions/cloud-architecture-models.md#hybrid)。

还可以将 Azure Active Directory (Azure AD) 顾问用于 Microsoft 365 管理中心中的自定义设置指南 (你必须登录到 Microsoft 365) ：

- [Azure AD 设置指南](https://aka.ms/aadpguidance)
- [从组织目录中同步用户](https://aka.ms/aadconnectpwsync)
- [Active Directory 联合身份验证服务 (AD FS) 顾问](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>开始之前

在集成 Microsoft 365 和本地环境之前，还需要执行 [网络规划和性能调整](network-planning-and-performance.md)。 你还需要了解可用的 [标识模型](about-microsoft-365-identity.md)。 

有关 [可用于管理 Microsoft 365](manage-microsoft-365-accounts.md) 用户帐户的工具列表，请参阅管理 Microsoft 365 帐户。 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>将 Microsoft 365 与 AD DS 集成

如果 AD DS 中已有用户帐户，则不希望在 Microsoft 365 中重新创建所有这些帐户，并且存在在环境之间引入差异或错误的风险。 目录同步可帮助你在内部部署和联机环境之间镜像这些帐户。 使用目录同步，用户不必记住每个环境的新信息，也不必创建或更新帐户两次。 您需要准备 [本地目录进行](prepare-for-directory-synchronization.md) 目录同步。
  
![使用目录同步使本地和联机用户帐户信息保持同步](../media/microsoft-365-integration/directory-synchronization.png)
  
如果希望用户能够使用其本地凭据登录 Microsoft 365，还可以配置 SSO。 借助 SSO，Microsoft 365 配置为信任本地环境进行用户身份验证。
  
![使用单一登录，可在本地和联机环境中使用同一帐户](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>包含或不带密码哈希同步的目录同步或 PTA (传递) 

用户使用其用户帐户登录本地环境， (域\用户名) 。 当他们转到 Microsoft 365 时，必须使用工作或学校帐户或帐户 (user@domain.com) 。 用户名在这两种环境中是相同的。 添加 PHS 或 PTA 时，用户在这两种环境中具有相同的密码，但登录 Microsoft 365 时必须再次提供这些凭据。 与 PHS 的目录同步是最常用的目录同步。

若要设置目录同步，请使用 Azure AD Connect。 有关说明，请参阅使用快速设置设置 [Microsoft 365](set-up-directory-synchronization.md) 和 [Azure AD Connect 的目录同步](/azure/active-directory/hybrid/how-to-connect-install-express)。

详细了解如何 [准备与 Microsoft 365 进行目录同步](prepare-for-directory-synchronization.md)。

### <a name="directory-synchronization-with-sso"></a>与 SSO 的目录同步

用户使用其用户帐户登录到其本地环境。 当他们转到 Microsoft 365 时，他们要么自动登录，要么使用用于本地环境的相同凭据登录 (域\用户名) 。

若要设置 SSO，你还使用 Azure AD Connect。 有关说明，请参阅 [Azure AD Connect 的自定义安装](/azure/active-directory/hybrid/how-to-connect-install-custom)。

有关详细信息，请参阅 [单一登录](/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect 取代了较早版本的标识集成工具，如 DirSync 和 Azure AD Sync。如果要从 Azure Active Directory 同步更新到 Azure AD Connect，请参阅 [升级说明](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started)。 

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)