---
title: 为Windows用户设置Microsoft 365 商业高级版设备
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 为Windows用户设置Windows 10 专业版运行Microsoft 365 商业高级版，从而实现集中式管理和安全控制。
ms.openlocfilehash: 46357074752e1715fdcdcd8be841e53f85475ddf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191285"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>为Windows用户设置Microsoft 365 商业高级版设备

## <a name="before-you-begin"></a>准备工作

在你可以为 Microsoft 365 商业高级版 用户设置 Windows 设备之前，请确保所有 Windows 设备都运行 Windows 10 专业版 版本 1703 (创意者更新) 。 Windows 10 专业版是部署 Windows 10 商业版 的先决条件，这是一组云服务和设备管理功能，可补充 Windows 10 专业版 并启用 Microsoft 365 商业高级版 的集中管理和安全控制。
  
如果你有Windows运行 Windows 7 Pro、Windows 8 专业版 或 Windows 8.1 专业版 的设备，Microsoft 365 商业高级版 订阅将授权你进行 Windows 10 升级。
  
有关如何将 Windows 设备升级到 Windows 10 专业版创意者更新的详细信息，请按照本主题中的步骤操作：[将 Windows 设备升级到 Windows 专业版创意者更新](../../business-video/upgrade.md)。
  
请参阅 [验证设备是否连接到 Azure AD](#verify-the-device-is-connected-to-azure-ad) 以验证是否具有升级，或确保升级有效。

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a>观看：连接电脑Microsoft 365企业

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>将 Windows 10 设备加入到组织的 Azure AD

当Windows设备已升级到 Windows 10 专业版 创意者更新或已在运行 Windows 10 专业版 创意者更新时，你可以将这些设备加入到组织的 Azure Active Directory。 设备加入后，将自动升级到 Windows 10 商业版，这是你的 Microsoft 365 商业高级版 订阅的一部分。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>全新或新升级的 Windows 10 专业版设备

对于运行 Windows 10 专业版创意者更新的全新设备，或升级到 Windows 10 专业版创意者更新但尚未完成 Windows 10 设备设置的设备，请按照以下步骤操作。
  
1. 完成 Windows 10 设备设置，直到显示" **设置方式**"页面。 
    
    ![在"如何设置"页上，选择"为组织设置"。](../../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. 在这里，**选择"为组织设置"，** 然后输入你的用户名和密码进行Microsoft 365 商业高级版。 
    
3. 完成 Windows 10 设备设置。
    
   完成后，用户将连接到组织的 Azure AD。请参阅[验证设备是否连接到 Azure AD](#verify-the-device-is-connected-to-azure-ad)确保完成操作。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>已经设置并运行 Windows 10 专业版的设备

 **将用户连接到 Azure AD：**
  
1. 1.在用户运行 Windows 10 专业版 1703（创意者更新）的 Windows 电脑上（详见[先决条件](../security-and-compliance/pre-requisites-for-data-protection.md)），单击 Windows 徽标，然后单击"设置"图标。
  
   ![在""开始"菜单中，单击"Windows 设置图标"。](../../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. 2.在" **设置**"中，转到" **帐户**"。
  
   ![在Windows 设置中，转到"帐户"。](../../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. 3.在" **你的信息**"页面上，单击" **访问工作或学校**"\>" **连接**"。
  
   ![在连接工作或学校"下选择"管理"。](../../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. 4.在" **设置工作或学校帐户**"对话框的" **备用操作**"下，选择" **将此设备加入 Azure Active Directory**"。
  
   ![单击"加入此设备"以Azure Active Directory。](../../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![在让我们登录页面上输入你的工作或学校电子邮件。](../../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. 在 **"确保这是您的组织"页上**，验证信息是否正确，然后选择"加入 **"。**
  
   在 **"你已全部设置"上！** page， chosse **Done**.
  
   ![在"确保这是您的组织"屏幕上，选择"加入"。](../../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
如果已将文件上传到 OneDrive for Business，请将其同步回电脑。 如果使用第三方工具迁移配置文件和文件，则还要将其同步到新配置文件。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>验证设备是否连接到 Azure AD

若要验证同步状态，请在"访问工作或学校"页面上设置，选择 **"连接到** _  "区域以公开按钮"信息"和"断开连接 \<organization name\> **"。**  选择 **"** 信息"获取同步状态。 
  
在" **同步状态"** 页面上，选择 **"同步** "，获取电脑上的最新移动设备管理策略。
  
若要开始使用 Microsoft 365 商业高级版 帐户，请转到 **"Windows"** 按钮，右键单击当前帐户图片，然后 **切换帐户**。 使用组织电子邮件和密码进行登录。
  
![单击"信息"按钮以查看同步状态。](../../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>验证电脑是否升级到Windows 10 商业版

确认已加入 Azure AD Windows 10设备已升级到Windows 10 商业版订阅的一Microsoft 365 商业高级版部分。
  
1. 转到" **设置**"\>" **系统**"\>" **关于**"。
    
2. 确认" **版本**"显示的是" **Windows 10 商业版**"。
    
    ![Verify that Windows edition is Windows 10 Business.](../../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>后续步骤

若要设置移动设备，请参阅为 Microsoft 365 商业高级版 用户设置移动设备。[若要](set-up-mobile-devices.md)设置设备保护或应用保护策略，请参阅管理 Microsoft 365 [for business。](/admin/index.yml)
  
## <a name="related-content"></a>相关内容

[Microsoft 365 商业版培训视频](../../business-video/index.yml)(链接页面)
