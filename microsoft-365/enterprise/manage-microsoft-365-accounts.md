---
title: 管理 Microsoft 365 用户帐户
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
description: 了解如何管理 Microsoft 365 用户帐户。
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327755"
---
# <a name="manage-microsoft-365-user-accounts"></a>管理 Microsoft 365 用户帐户

您可以通过几种不同的方式管理 Microsoft 365 用户帐户，具体取决于您的配置。 你可以在 Active Directory 域服务 (AD DS) 中或在 Azure Active Directory (Azure AD) 管理门户中管理 [Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users/)、 [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、active directory 域服务中的用户帐户。 

一旦购买 Microsoft 365，Microsoft 365 管理中心和 PowerShell 便可用于管理帐户。 管理云身份时，组织中的每个人都有单独的用户帐户名和密码。 如果要与本地基础结构集成并将用户帐户与 Microsoft 365 同步，可以使用 Azure AD Connect 为单一登录 (SSO) 功能提供标识和密码的同步。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>规划将管理用户帐户的位置和方式

如何管理用户帐户的位置和方式取决于要用于 Microsoft 365 的标识模型。 这两个整体模型为仅云和混合模式。
  
### <a name="cloud-only"></a>仅限云

在 Microsoft 365 管理中心中创建和管理用户。 您还可以使用 PowerShell 或 Azure AD 管理中心。 
    
### <a name="hybrid"></a>混合

用户帐户与 AD DS 中的 Microsoft 365 同步，因此您必须使用内部部署 AD DS 工具来管理用户帐户。 
    
## <a name="managing-accounts"></a>管理帐户

在决定您的组织创建和管理帐户的方式时，请考虑以下要求：
  
- 目录同步软件需要安装在本地环境中的服务器上，以连接 Microsoft 365 和 AD DS 之间的标识。
    
- 任何目录同步选项（包括 SSO 选项）都要求 AD DS 属性满足标准。 [准备目录同步到 Microsoft 365](prepare-for-directory-synchronization.md)中描述了在目录中使用的属性和清除 (（如果有任何) 需要）的具体说明。 
    
- 规划如何创建 Microsoft 365 帐户。
    
下表列出了不同的帐户管理工具。
    
|工具|注释|
|:-----|:-----|
|Microsoft 365 管理中心  <br/> |[单独或批量添加用户](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  提供一个简单的 web 界面来添加和更改用户帐户。  <br/>  如果启用了目录同步，则无法用于更改用户 (位置和许可证分配可以设置) 。  <br/>  不能与 SSO 选项一起使用。  <br/> |
|Windows PowerShell  <br/> |[使用 Windows PowerShell 管理 Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  允许您使用 Windows PowerShell 脚本在批量用户中添加用户。  <br/>  可用于将位置和许可证分配给帐户，而不考虑帐户的创建方式。  <br/> |
|批量导入  <br/> |[同时添加多个用户](add-several-users-at-the-same-time.md) <br/>  允许您导入 CSV 文件以将一组用户添加到 Microsoft 365。  <br/>  不能与 SSO 选项一起使用。  <br/> |
|Azure AD  <br/> |你可以使用 Microsoft 365 订阅获取 Azure AD 的免费版本。 您可以为云用户执行自助密码重置等功能，并使用免费版本自定义登录和访问面板页。 若要获取增强的功能，您可以升级到基本版本、Azure AD 高级 P1 或 Azure AD Premium P2。 有关支持的功能的列表，请参阅 [AZURE AD 版本](https://go.microsoft.com/fwlink/p/?LinkId=698465) 。  <br/> |
|目录同步  <br/> |[将本地标识与 Azure AD 集成](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  对于使用或不使用密码同步进行目录同步，请将 [AZURE AD Connect 与 express 设置结合](https://go.microsoft.com/fwlink/p/?LinkID=698537)使用。  <br/>  对于多个林和 SSO 选项，请使用 [自定义安装的 AZURE AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430)。  <br/>  提供启用 SSO 所需的基础结构。  <br/>  对许多混合方案（如暂存迁移和混合 Exchange）是必需的  <br/>  从 AD DS 同步安全和启用邮件的组。  <br/> |
|||
   
- 无论您打算如何将用户帐户添加到 Microsoft 365，您都需要管理多个帐户功能，例如分配许可证、指定位置等。 可以从 Microsoft 365 管理中心对这些功能进行管理，也可以 [使用 PowerShell 创建用户帐户](https://go.microsoft.com/fwlink/p/?LinkId=717083)。
    
    如果选择通过管理中心添加和管理所有用户，您将指定位置，并在创建 Microsoft 365 帐户的同时分配许可证。 因此，不需要进行大量规划。
    
    > [!IMPORTANT]
    > 在 Microsoft 365 中创建帐户，而不向 SharePoint Online 分配许可证 (，例如) 意味着帐户所有者可以查看 Microsoft 365 中心，但不能访问公司订阅中的任何服务。 分配位置和许可证后，帐户将复制到您分配的服务或服务。 用户可以登录到其帐户并使用您分配给他们的服务。 
  
## <a name="see-also"></a>另请参阅

[Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
