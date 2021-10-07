---
title: 管理Microsoft 365用户帐户
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
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何管理Microsoft 365用户帐户。
ms.openlocfilehash: 7f75c74984ce58a8b403f01948075b185047f260
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150770"
---
# <a name="manage-microsoft-365-user-accounts"></a>管理Microsoft 365用户帐户

可以通过几种Microsoft 365管理用户帐户，具体取决于您的配置。 可以在[](/admin)[Microsoft 365 管理中心、PowerShell、Active](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Directory 域服务 (AD DS) 或 Azure Active Directory (Azure AD) 管理门户中管理用户帐户。 

一旦购买Microsoft 365，Microsoft 365 管理中心 PowerShell 可用于<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>管理帐户。 管理云标识时，组织中的每个人都具有单独的用户帐户名称和密码。 如果你想要与本地基础结构集成，并将用户帐户与 Microsoft 365 同步，可以使用 Azure AD 连接 为单一登录 (SSO) 功能提供标识和密码同步。
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>规划用户帐户管理位置和方式

在哪里以及如何管理用户帐户取决于要用于用户帐户的标识Microsoft 365。 这两种整体模型是仅云模型和混合模型。
  
### <a name="cloud-only"></a>仅限云

您可以在"管理"中<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a> 您还可以使用 PowerShell 或 Azure AD 管理中心。 
    
### <a name="hybrid"></a>混合

用户帐户与来自 AD DS Microsoft 365同步，因此必须使用本地 AD DS 工具管理用户帐户。 
    
## <a name="managing-accounts"></a>管理帐户

在确定组织创建和管理帐户的方式时，请考虑以下要求：
  
- 目录同步软件需要安装在本地环境的服务器上，以连接 Microsoft 365 和 AD DS 之间的标识。
    
- 任何目录同步选项（包括 SSO 选项）都要求 AD DS 属性符合标准。 准备目录同步到 Microsoft 365 中介绍了目录中使用的属性以及 (（如果需要任何) ）的[Microsoft 365。](prepare-for-directory-synchronization.md) 
    
- 规划如何创建帐户Microsoft 365帐户。
    
下表列出了不同的帐户管理工具。
    
|工具|备注|
|:-----|:-----|
|Microsoft 365 管理中心  <br/> |[单独或批量添加用户](../admin/add-users/add-users.md) <br/>  提供用于添加和更改用户帐户的简单 Web 界面。  <br/>  如果启用了目录同步，则不能用于更改用户 (且可以将许可证分配设置为) 。  <br/>  不能与 SSO 选项一同使用。  <br/> |
|Windows PowerShell  <br/> |[使用Microsoft 365管理Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  允许您使用自定义脚本批量添加Windows PowerShell用户。  <br/>  可用于向帐户分配位置和许可证，而不考虑帐户的创建方式。  <br/> |
|批量导入  <br/> |[同时添加多个用户](add-several-users-at-the-same-time.md) <br/>  允许您导入 CSV 文件以将一组用户添加到Microsoft 365。  <br/>  不能与 SSO 选项一同使用。  <br/> |
|Azure AD  <br/> |通过订阅获取免费版本的 Azure AD Microsoft 365订阅。 你可以执行一些功能，如为云用户重置自助服务密码，以及使用免费版本自定义登录和访问面板页面。 若要获得增强功能，可以升级到基本版本、Azure AD Premium P1或Azure AD Premium P2。 有关 [支持的功能列表，请参阅 Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) 版本。  <br/> |
|目录同步  <br/> |[将本地标识与 Azure AD 集成](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  对于具有或不使用密码同步的目录同步，请使用[Azure AD 连接快速设置](/azure/active-directory/hybrid/how-to-connect-install-express)。  <br/>  对于多个林和 SSO 选项，请使用[Azure AD](/azure/active-directory/hybrid/how-to-connect-install-custom)自定义连接。  <br/>  提供启用 SSO 所需的基础结构。  <br/>  在许多混合方案（如分步迁移和混合部署）中Exchange  <br/>  从 AD DS 同步安全和启用邮件的组。  <br/> |
|||
   
- 无论打算如何向用户添加用户帐户Microsoft 365，都需要管理多个帐户功能，例如分配许可证、指定位置等。 这些功能可以从管理组长期Microsoft 365 管理中心或者您也可以使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>[PowerShell 创建用户帐户](./create-user-accounts-with-microsoft-365-powershell.md)。
    
    如果选择通过管理中心添加和管理所有用户，则指定位置并分配许可证，同时创建Microsoft 365帐户。 因此，不需要进行太多规划。
    
    > [!IMPORTANT]
    > 在 Microsoft 365 中创建帐户，而不向 SharePoint Online 分配许可证 (，例如) 意味着帐户所有者可以查看 Microsoft 365 中心，但不能访问公司订阅内的任何服务。 分配位置和许可证后，该帐户将复制到你分配的一个或多个服务。 用户可以登录到其帐户并使用你分配给他们的服务。 
  
## <a name="see-also"></a>另请参阅

[Microsoft 365 管理中心](/admin)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)