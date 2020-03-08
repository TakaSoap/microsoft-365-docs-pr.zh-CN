---
title: 验证 Windows 10 电脑上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 在 Windows 10 设备上验证 Microsoft 365 商业应用保护设置，并验证用户不能将公司数据复制到个人文件或非托管应用。
ms.openlocfilehash: 5b798e0335188543fc308553f71085bcde8b7752
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560832"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>验证 Windows 10 电脑上的应用保护设置

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>确定用户不能将公司数据复制到企业设备上的个人文件中

[设置应用保护策略](protection-settings-for-windows-10-devices.md) 后，可能需要几个小时策略才会在用户的设备上生效。 如果启用了 "**阻止用户将公司数据复制到个人文件，并强制他们将公司拥有的工作文件保存到 OneDrive for** business**设置"，** 则可以在用户的设备连接到 Azure AD 并登录后对其进行检查。 
  
 **验证连接设置**
  
1. 按[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)所述，使用 Microsoft 365 商业版凭据登录并连接到 Azure AD 后，请转到" **Windows 设置**"\>" **帐户**"\>" **访问工作或学校帐户**"。选择" **连接到 \<租户名称\> Azure AD**"，然后选择" **信息**"。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. 在 "**管理者** \<租户名称\> " 页上，您可以看到包含**管理服务器地址**的**连接信息**，如下图中所示。 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **确认无法将公司数据粘贴到非托管应用中**
  
1. 打开由 Microsoft 365 商业版安装的 Outlook 2016。
    
2. 打开一封电子邮件，并复制其中的某些内容。
    
    打开记事本，并尝试将该内容粘贴到其中。
    
    你将收到一条错误，指出应用无法访问内容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    但是，可以将相同的内容粘贴到 Word 2016。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>验证用户不能将公司数据复制到个人设备上的个人文件中

 **验证连接设置**
  
1. 在以本地用户身份登录的 windows 10 个人设备上，转到 " **Windows 设置**"，然后单击或点击 "**帐户** \> **访问工作或学校**"。
    
2. 在" **访问工作或学校帐户**"下选择" **连接**"。
    
3. 在" **设置工作或学校帐户**"对话框\>" **登录**"中，输入 Microsoft 365 商业版凭据。
    
4. 在" **访问工作或学校帐户**"页面，选择" **工作或学校帐户**"，然后选择" **信息**"。
    
    ![单击或点击 "工作或学校帐户" 对话框上的 "信息"。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 在 "**访问工作或学校**" 页面上，您可以看到包含**管理服务器地址**的**连接信息**，如下图中所示，并在中包括 " *wip* " 和 " *mam* " 一词。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **确认无法将公司数据粘贴到非托管应用中**
  
1. 打开 Outlook 2016，并添加 Microsoft 365 商业版 帐户（如有必要），然后使用 Microsoft 365 商业版凭据进行登录。
    
2. 打开一封电子邮件，并复制其中的某些内容。
    
    打开记事本，并尝试将该内容粘贴到其中。
    
    您将收到一条错误，说明应用程序无法访问内容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    但是，可以将相同的内容粘贴到 Word 2016。
    

