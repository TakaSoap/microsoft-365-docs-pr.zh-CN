---
title: Office 365 部署的多重身份验证计划
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Office 365 中的多重身份验证，以及对其进行设置时需要遵循的步骤。
ms.openlocfilehash: c3d5e83b951e4fd4a05cb18408ecb3d26e397cf9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252426"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Office 365 部署的多重身份验证计划

多重身份验证 (MFA) 是一种身份验证方法，要求使用多个验证方法，并向用户登录和交易添加第二层安全。该验证需要任意两个或多个以下验证方法来实现：
  
- 随机生成的密码
    
- 电话联络
    
- 智能卡（虚拟或物理） 
    
- 生物识别设备 
    
## <a name="multi-factor-authentication-in-office-365"></a>Office 365 中的多重身份验证

Office 365 使用多重身份验证来帮助提供额外的安全性，并通过 Microsoft 365 管理中心进行管理。 Office 365 提供以下 Azure 多重身份验证功能的子集作为订阅的一部分： 
  
- 能够启用和强制实施针对最终用户的多重身份验证
    
- 使用移动应用（联机和一次性密码 [OTP]）作为第二身份验证因素
    
- 使用电话联络作为第二身份验证因素
    
- 使用短消息服务 (SMS) 消息作为第二身份验证因素
    
- 用于非浏览器客户端的应用程序密码（例如，Microsoft Lync 2013 通信软件）
    
- 身份验证电话联络期间的默认 Microsoft 问候语
    
有关新增功能的完整列表，请参阅 [Azure 多重身份验证版本比较](https://go.microsoft.com/fwlink/?LinkId=506927)。通过购买 Azure 多重身份验证服务，可始终获得完整功能。 
  
获取的功能子集会有所不同，具体取决于是只进行 Office 365 的云部署，还是使用单一登录和 Active Directory 联合身份验证服务 (AD FS) 的混合设置。 
  
|**在哪里管理 Office 365 租户？**|**MFA 第二因素选项**|
|:-----|:-----|
|仅云  <br/> |Azure Active Directory MFA（文本或电话联络）  <br/> |
|本地托管的混合设置  <br/> | 如果在本地管理用户身份，有以下几种选择：  <br/>  物理或虚拟智能卡 (AD FS)  <br/> [Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 的模块）  <br/>  Azure AD MFA  <br/> |
   
  
下图演示更新的 Office 2013 设备应用（用于 Windows）如何使用户能够使用 MFA 登录。Office2013 设备应用通过使用 [Active Directory 身份验证库 (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) 支持多重身份验证。Azure AD 托管用户可登录的网页。标识提供程序可以是 Azure AD 或联合身份提供程序，如 AD FS。联合用户的身份验证执行以下步骤：
  
1. Azure AD 将用户重定向到由 Office 365 租户的记录的标识提供程序托管的登录网页。标识提供程序由用户登录名中指定的域来确定。
    
2. 用户在其设备的登录网页上进行登录。 
    
3. 如果用户成功登录，标识提供程序会将一个令牌返回到 Azure AD。
    
4. Azure AD 将 JSON Web 令牌 (JWT) 返回到 Office 设备应用，并通过结合使用 JWT 和 Office 365 对设备应用进行身份验证。 
    
下图对此进行了详细说明：
  
![Office 2013 设备应用的现代身份验证。](../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a>软件要求

要启用适用于 Office 2013 客户端的 MFA，必须根据是具有[基于即点即用的安装](#click-to-run-based-installations)内容还是[基于 MSI 的安装](#msi-based-installations)内容，来安装以下软件（下面列出的版本或更高版本）。
  
确定拥有的 Office 安装内容是基于即点即用的还是基于 MSI 的：
  
1. 启动 Outlook 2013。
    
2. 在 "**文件**" 菜单上，选择 " **Office 帐户**"。
    
3. 对于 Outlook 2013 即点即用安装，将显示" **更新选项**"项。对于基于 MSI 的安装，将不会显示" **更新选项**"项。 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a>基于即点即用的安装

对于基于即点即用的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请按照下面的步骤进行更新。
  
|**文件名**|**计算机上的安装路径**|**文件版本**|
|:-----|:-----|:-----|
|MSO.DLL.DLL  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI.DLL  <br/> |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook .exe  <br/> |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|ADAL.DLL  <br/> |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |变量  <br/> |
   
### <a name="msi-based-installations"></a>基于 MSI 的安装

对于基于 MSI 的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请使用"更新 KB 文章"列中的链接进行更新。
  
|**文件名**|**计算机上的安装路径**|**获取更新的位置**|**版本**|
|:-----|:-----|:-----|:-----|
|MSO.DLL.DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI.DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove  <br/> |C:\Program Files\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook .exe  <br/> |C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|ADAL.DLL  <br/> |C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore.exe  <br/> |C:\Program Files\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |不适用  <br/> |
   
## <a name="enable-mfa"></a>启用 MFA

要启用 MFA，必须完成以下操作：
  
1. 启用用于新式验证的客户端：
    
  - [在 Windows 设备上启用适用于 Office 2013 的新式验证](enable-modern-authentication.md) 。 
    
  - 使用第三方目录服务设置 Azure MFA。
    
    有关可接受此程序的特定标识提供程序的信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。 
    
2. [为 Office 365 设置多重身份验证](set-up-multi-factor-authentication.md)
    
3. 告知单个用户如何通过 MFA 进行登录：[通过 2 步验证登录 Office 365](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)。
    
> [!IMPORTANT]
> 如果已为用户启用 Azure AD MFA，并且这些用户拥有运行 Office 2013 但未启用新式验证的设备，则他们将需要在这些设备上使用应用密码。有关应用密码以及应在何时、何处和如何使用的详细信息，可访问此处进行了解：[用于 Azure 多重身份验证的应用密码](https://go.microsoft.com/fwlink/p/?LinkId=528178) 
  
## <a name="faq"></a>常见问题

[新式验证常见问题解答 wiki 文章](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 **已知问题：**
  
[Office 2013 和 Office 365 专业增强版新式验证：载入前注意事项](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Azure 多重身份验证疑难解答：**
  
请参阅 [Azure MFA 疑难解答](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。
  
[使用 AD FS 时，如何解决 Office 2013 新式验证的登录问题](https://support.microsoft.com/kb/3052203/)
  
 **如果备选 ID 不起作用：**
  
[如何使用 PowerShell 修复 UPN 重复](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[用于修复用户主体名称重复的脚本](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **客户端访问筛选：**
  
[Office 2013 和 Office 365 专业增强版新式验证和客户端访问筛选策略：载入前注意事项](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **哪些应用支持 MFA？**
  
|**Windows**|**Mac**|**iOS**|**Android 手机**|**Android 平板电脑**|
|:-----|:-----|:-----|:-----|:-----|
|此版本支持用于 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 和 Skype for Business 的新式验证。  <br/> |此版本支持用于 Word 2016 for Mac、Excel 2016 for Mac 和 PowerPoint 2016 for Mac 的新式验证。  <br/> |此版本支持用于 Word for iPad、Excel for iPad 和 PowerPoint for iPad 的新式验证。  <br/> |此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。  <br/> |此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。  <br/> |
|此版本支持用于 Outlook 2013 和 Outlook 2016 的新式验证。  <br/> |此版本支持用于 Outlook 2016 for Mac 的新式验证。  <br/> |此版本支持用于 Outlook for iPad 的新式验证。  <br/> |||
   

