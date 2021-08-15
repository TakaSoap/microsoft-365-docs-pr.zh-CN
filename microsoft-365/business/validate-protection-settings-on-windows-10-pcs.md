---
title: 验证 Windows 10 电脑上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 验证Microsoft 365 商业高级版设备上是否Windows 10应用保护设置，并验证用户无法将公司数据复制到个人文件或非托管应用。
ms.openlocfilehash: ab084ded5ef052a7b85839f0debb96eb1bc5bdf332230293613396825c7263f0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53861688"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>验证 Windows 10 电脑上的应用保护设置

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>确定用户不能将公司数据复制到企业设备上的个人文件中

[设置应用保护策略](protection-settings-for-windows-10-devices.md) 后，可能需要几个小时策略才会在用户的设备上生效。 如果你为公司拥有的设备打开"阻止用户将公司数据复制到个人文件并强制他们将工作文件保存到 **OneDrive for Business"** 设置，可以在用户连接到 Azure AD 并登录后在用户设备上检查此设置。 
  
 **验证连接设置**
  
1. 使用 Microsoft 365 商业高级版 凭据登录并连接到 Azure AD（如为 Microsoft 365 商业高级版 用户设置 Windows 设备中所述 [）](set-up-windows-devices.md)后，请转到 Windows 设置 \> **Accounts** \> **Access work or school**。 选择 **"连接到 \<tenant name\> Azure AD"，** 然后选择"信息 **"。**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. On the **Managed by** \<tenant name\> page， you can see the Connection **info** that includes a Management **Server Address** like the one shown in the following figure. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **验证您是否无法将公司数据粘贴到非托管应用程序中**
  
1. 打开Outlook 2016安装的应用程序Microsoft 365 商业高级版。
    
2. 打开一封电子邮件，并复制其中的某些内容。
    
    打开记事本，并尝试将该内容粘贴到其中。
    
    你将收到一条错误，指出应用无法访问内容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    但是，可以将相同的内容粘贴到 Word 2016。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>验证用户不能将公司数据复制到个人设备上的个人文件中

 **验证连接设置**
  
1. 在Windows 10本地用户登录的个人设备上，转到"Windows 设置"，然后单击 **或点击"** 帐户""访问工作或学校 \> **"。**
    
2. 在" **访问工作或学校帐户**"下选择" **连接**"。
    
3. Enter your Microsoft 365 商业高级版 credential into the **Set up a work or school account dialog** Sign \> **in**.
    
4. 在" **访问工作或学校帐户**"页面，选择" **工作或学校帐户**"，然后选择" **信息**"。
    
    ![单击或点击工作或学校帐户对话框中的信息。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. 在 **"访问工作或** 学校"页上，你可以看到包含管理服务器地址的连接信息，如下图所示，并包括单词 *wip* 和 *mam。* 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **验证您是否无法将公司数据粘贴到非托管应用程序中**
  
1. 打开Outlook 2016并根据需要添加 Microsoft 365 商业高级版 帐户，然后使用你的 Microsoft 365 商业高级版 凭据登录。
    
2. 打开一封电子邮件，并复制其中的某些内容。
    
    打开记事本，并尝试将该内容粘贴到其中。
    
    你将收到一条错误，指出应用无法访问内容。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    但是，可以将相同的内容粘贴到 Word 2016。
    

