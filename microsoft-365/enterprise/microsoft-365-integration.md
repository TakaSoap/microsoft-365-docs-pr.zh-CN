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
description: 在本文中，我们将了解如何将 Microsoft 365 与您现有的目录服务和本地环境集成。
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384883"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 与本地环境的集成

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以将 Microsoft 365 与现有的本地 Active Directory 域服务集成 (AD DS) 以及 Exchange Server 的本地安装、Skype for Business Server 2015 或 SharePoint Server。
  
 - 在集成 AD DS 时，您可以同步和管理这两个环境的用户帐户。 您还可以 (PHS) 或单一登录 (SSO) 添加密码哈希同步，以便用户可以使用其本地凭据登录到这两个环境。
 - 当您与本地服务器产品集成时，将创建混合环境。 当您将用户或信息迁移到 Microsoft 365 时，混合环境可帮助您，也可以继续在本地使用某些用户或某些信息以及在云中使用一些信息。 有关混合环境的详细信息，请参阅 [混合云](../solutions/cloud-architecture-models.md#hybrid)。

您还可以在 Microsoft 365 管理中心中使用 Azure Active Directory (Azure AD) 顾问获取自定义设置指南 (您必须登录到 Microsoft 365) ：

- [Azure AD 安装指南](https://aka.ms/aadpguidance)
- [从你的组织的目录同步用户](https://aka.ms/aadconnectpwsync)
- [Active Directory 联合身份验证服务 (AD FS) 部署顾问](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>准备工作

在集成 Microsoft 365 和本地环境之前，还需要进行 [网络规划和性能调整](network-planning-and-performance.md)。 您还需要了解可用的 [标识模型](about-microsoft-365-identity.md)。 

有关可用于管理 Microsoft 365 用户帐户的工具列表，请参阅 [管理 microsoft 365 帐户](manage-microsoft-365-accounts.md) 。 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>将 Microsoft 365 与 AD DS 集成

如果您在 AD DS 中有现有的用户帐户，则不需要在 Microsoft 365 中重新创建所有这些帐户，并且在环境之间引入差异或错误的风险。 目录同步可帮助您在本地和联机环境中镜像这些帐户。 通过目录同步，用户不必记住每个环境的新信息，也不必创建或更新帐户两次。 你将需要为 [本地目录准备](prepare-for-directory-synchronization.md) 目录同步。
  
![使用目录同步将本地和联机用户帐户信息保持同步](../media/microsoft-365-integration/directory-synchronization.png)
  
如果您希望用户能够使用他们的本地凭据登录到 Microsoft 365，您还可以配置 SSO。 使用 SSO，Microsoft 365 配置为信任本地环境以进行用户身份验证。
  
![使用单一登录，在本地和联机环境中都可以使用相同的帐户。](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>使用或不使用密码哈希同步或不 (PTA 的传递身份验证的目录同步) 

用户使用其用户帐户登录到本地环境， (域 \ 用户名) 。 当他们转到 Microsoft 365 时，他们必须使用其工作或学校帐户 (user@domain.com) 重新登录。 这两个环境中的用户名相同。 当您添加 PHS 或 PTA 时，用户对这两个环境都具有相同的密码，但在登录到 Microsoft 365 时将不得不再次提供这些凭据。 使用 PHS 的目录同步是最常用的目录同步。

若要设置目录同步，请使用 Azure AD Connect。 有关说明，请参阅 [Set up directory 同步 For Microsoft 365](set-up-directory-synchronization.md) 和 [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537)。

了解有关 [准备将目录同步到 Microsoft 365 的](prepare-for-directory-synchronization.md)详细信息。

### <a name="directory-synchronization-with-sso"></a>使用 SSO 同步目录

用户使用其用户帐户登录到本地环境。 当他们转到 Microsoft 365 时，它们要么是自动登录，要么是使用它们在本地环境中使用的相同凭据登录 (域 \ 用户名) 。

若要设置 SSO，您还可以使用 Azure AD Connect。 有关说明，请参阅 [自定义安装的 AZURE AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430)。

有关详细信息，请参阅 [单一登录](https://go.microsoft.com/fwlink/p/?LinkId=698604)。

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect 替代了较早版本的身份集成工具，如 DirSync 和 Azure AD 同步。如果要从 Azure Active Directory 同步更新到 Azure AD Connect，请参阅 [升级说明](https://go.microsoft.com/fwlink/p/?LinkId=733240)。 

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)
