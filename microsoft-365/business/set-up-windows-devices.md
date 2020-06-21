---
title: 为 Microsoft 365 商业高级版用户设置 Windows 设备
f1.keywords:
- CSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 了解如何设置运行 Windows 10 Pro for Microsoft 365 商业高级版用户的 Windows 设备，从而实现集中管理和安全控制。
ms.openlocfilehash: 85ac3c964792a132d5699703e543289020e38f57
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785844"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>为 Microsoft 365 商业高级版用户设置 Windows 设备

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>为 Microsoft 365 商业高级用户设置 Windows 设备的先决条件

在为 Microsoft 365 商业高级版用户设置 Windows 设备之前，请确保所有 Windows 设备都运行的是 Windows 10 专业版，即版本1703（创意者更新）。 Windows 10 专业版是部署 Windows 10 商业版的先决条件，它是一组可补充 Windows 10 专业的云服务和设备管理功能，并能够实现 Microsoft 365 商业高级版的集中管理和安全控制。
  
如果你有运行 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 Pro 的 Windows 设备，Microsoft 365 商业高级版订阅将享有 Windows 10 升级。
  
有关如何将 Windows 设备升级到 Windows 10 专业版创意者更新的详细信息，请按照本主题中的步骤操作：[将 Windows 设备升级到 Windows 专业版创意者更新](upgrade-to-windows-pro-creators-update.md)。
  
请参阅[验证设备是否已连接到 AZURE AD](#verify-the-device-is-connected-to-azure-ad) ，以验证您是否可以升级，或确保升级有效。

观看有关将 Windows 连接到 Microsoft 365 的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>将 Windows 10 设备加入到组织的 Azure AD

如果组织中的所有 Windows 设备都已升级到 Windows 10 Pro 创意者更新或已运行 Windows 10 Pro 创意者更新，则可以将这些设备加入到组织的 Azure Active Directory 中。 设备加入后，它们将自动升级到 Windows 10 商业版，这是 Microsoft 365 商业高级版订阅的一部分。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>全新或新升级的 Windows 10 专业版设备

对于运行 Windows 10 专业版创意者更新的全新设备，或升级到 Windows 10 专业版创意者更新但尚未完成 Windows 10 设备设置的设备，请按照以下步骤操作。
  
1. 完成 Windows 10 设备设置，直到显示" **设置方式**"页面。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 在此处选择 "为**组织设置**"，然后输入 Microsoft 365 商业高级版的用户名和密码。 
    
3. 完成 Windows 10 设备设置。
    
   Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure. 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>已经设置并运行 Windows 10 专业版的设备

 **将用户连接到 Azure AD：**
  
1. 1.在用户运行 Windows 10 专业版 1703（创意者更新）的 Windows 电脑上（详见[先决条件](pre-requisites-for-data-protection.md)），单击 Windows 徽标，然后单击"设置"图标。
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. 2.在" **设置**"中，转到" **帐户**"。
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. 3.在" **你的信息**"页面上，单击" **访问工作或学校**"\>" **连接**"。
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. 4.在" **设置工作或学校帐户**"对话框的" **备用操作**"下，选择" **将此设备加入 Azure Active Directory**"。
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 在 "**请确保这是你的组织**" 页上，验证信息是否正确，然后单击 "**加入**"。
  
   On the **You're all set!** page, click **Done**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
如果已将文件上传到 OneDrive for Business，请将其同步回电脑。 如果您使用第三方工具来迁移配置文件和文件，也将其同步到新的配置文件。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>验证设备是否连接到 Azure AD

若要验证您的同步状态，请在 "**设置**" 中的 "**访问工作或学校**" 页上，单击 "**已连接到**_ \<organization name\> _" 区域以显示按钮**信息**并**断开连接**。 单击" **信息**"，获取同步状态。 
  
在同步状态页面上，单击"同步"，将最新的移动设备管理策略同步到电脑上。
  
若要开始使用 Microsoft 365 商业高级版帐户，请转到 Windows "**开始**" 按钮，右键单击您当前的帐户图片，然后**切换帐户**。 使用组织电子邮件和密码进行登录。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>验证设备是否升级到 Windows 10 商业版

验证您的 Azure AD 加入 Windows 10 设备是否已升级到 Windows 10 商业版，作为 Microsoft 365 商业高级版订阅的一部分。
  
1. 转到" **设置**"\>" **系统**"\>" **关于**"。
    
2. 确认" **版本**"显示的是" **Windows 10 商业版**"。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>后续步骤

若要设置移动设备，请参阅[设置适用于 Microsoft 365 商业高级用户的移动设备](set-up-mobile-devices.md)，若要设置设备保护或应用保护策略，请参阅[管理 Microsoft 365 for Business](manage.md)。
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>有关设置和使用 Microsoft 365 商业高级版的详细信息

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
