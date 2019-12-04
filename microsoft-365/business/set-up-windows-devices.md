---
title: 为 Microsoft 365 商业版用户设置 Windows 设备
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: '了解如何设置运行 Windows 10 Pro for Microsoft 365 商业用户的 Windows 设备。 '
ms.openlocfilehash: b377c1e69d117b893b256880cd3b9972e33345c7
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "39812870"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="35f7f-103">为 Microsoft 365 商业版用户设置 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="35f7f-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35f7f-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="35f7f-104">Prerequisites</span></span>

<span data-ttu-id="35f7f-p101">在为 Microsoft 365 商业版用户设置 Windows 设备之前，请确保所有 Windows 设备都运行 Windows 10 专业版 1703（创意者更新）。Windows 10 专业版是部署 Windows 10 商业版的先决条件，Windows 10 商业版是一组补充 Windows 10 专业版的云服务和设备管理功能，可实现 Microsoft 365 商业版的集中管理和安全控制。</span><span class="sxs-lookup"><span data-stu-id="35f7f-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="35f7f-107">如果 Windows 设备运行 Windows 7 专业版、Windows 8 专业版或 Windows 8.1 专业版，Microsoft 365 商业版订阅可授权进行 Windows 10 升级。</span><span class="sxs-lookup"><span data-stu-id="35f7f-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="35f7f-108">有关如何将 Windows 设备升级到 Windows 10 专业版创意者更新的详细信息，请按照本主题中的步骤操作：[将 Windows 设备升级到 Windows 专业版创意者更新](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="35f7f-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="35f7f-109">请参阅[验证设备是否已连接到 AZURE AD](#verify-the-device-is-connected-to-azure-ad) ，以验证您是否可以升级，或确保升级有效。</span><span class="sxs-lookup"><span data-stu-id="35f7f-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="35f7f-110">观看有关将 Windows 连接到 Microsoft 365 的简短视频。</span><span class="sxs-lookup"><span data-stu-id="35f7f-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="35f7f-111">如果你发现此视频有帮助，请查看[适用于 Microsoft 365 的完整培训系列和小型企业](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)版。</span><span class="sxs-lookup"><span data-stu-id="35f7f-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="35f7f-112">将 Windows 10 设备加入到组织的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="35f7f-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="35f7f-113">如果组织中的所有 Windows 设备都已升级到 Windows 10 Pro 创意者更新或已运行 Windows 10 Pro 创意者更新，则可以将这些设备加入到组织的 Azure Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="35f7f-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="35f7f-114">设备加入后，它们将自动升级到 Windows 10 商业版，这是 Microsoft 365 商业版订阅的一部分。</span><span class="sxs-lookup"><span data-stu-id="35f7f-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="35f7f-115">全新或新升级的 Windows 10 专业版设备</span><span class="sxs-lookup"><span data-stu-id="35f7f-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="35f7f-116">对于运行 Windows 10 专业版创意者更新的全新设备，或升级到 Windows 10 专业版创意者更新但尚未完成 Windows 10 设备设置的设备，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="35f7f-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="35f7f-117">完成 Windows 10 设备设置，直到显示" **设置方式**"页面。</span><span class="sxs-lookup"><span data-stu-id="35f7f-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="35f7f-119">在这里，选择" **针对组织进行设置**"，然后输入 Microsoft 365 商业版的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="35f7f-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="35f7f-120">完成 Windows 10 设备设置。</span><span class="sxs-lookup"><span data-stu-id="35f7f-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="35f7f-p103">完成后，用户将连接到组织的 Azure AD。请参阅[验证设备是否连接到 Azure AD](#verify-the-device-is-connected-to-azure-ad)确保完成操作。</span><span class="sxs-lookup"><span data-stu-id="35f7f-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="35f7f-123">已经设置并运行 Windows 10 专业版的设备</span><span class="sxs-lookup"><span data-stu-id="35f7f-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="35f7f-124">**将用户连接到 Azure AD：**</span><span class="sxs-lookup"><span data-stu-id="35f7f-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="35f7f-125">1.在用户运行 Windows 10 专业版 1703（创意者更新）的 Windows 电脑上（详见[先决条件](pre-requisites-for-data-protection.md)），单击 Windows 徽标，然后单击"设置"图标。</span><span class="sxs-lookup"><span data-stu-id="35f7f-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="35f7f-127">2.在" **设置**"中，转到" **帐户**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="35f7f-129">3.在" **你的信息**"页面上，单击" **访问工作或学校**"\>" **连接**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="35f7f-131">4.在" **设置工作或学校帐户**"对话框的" **备用操作**"下，选择" **将此设备加入 Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="35f7f-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="35f7f-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="35f7f-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="35f7f-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="35f7f-136">在 "**请确保这是你的组织**" 页上，验证信息是否正确，然后单击 "**加入**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="35f7f-p104">在" **设置完毕!**"页面上，单击" **完成**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="35f7f-140">如果已将文件上传到 OneDrive for Business，请将其同步回电脑。</span><span class="sxs-lookup"><span data-stu-id="35f7f-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="35f7f-141">如果您使用第三方工具来迁移配置文件和文件，也将其同步到新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="35f7f-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="35f7f-142">验证设备是否连接到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="35f7f-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="35f7f-p106">若要验证同步状态，请在" **设置**"中的" **访问工作或学校**"页面下，单击" **连接到**" _ \<organization name\> _区域以显示" **信息**"和" **断开连接**"按钮。单击" **信息**"，获取同步状态。</span><span class="sxs-lookup"><span data-stu-id="35f7f-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="35f7f-145">在同步状态页面上，单击"同步"，将最新的移动设备管理策略同步到电脑上。</span><span class="sxs-lookup"><span data-stu-id="35f7f-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="35f7f-146">若要开始使用 Microsoft 365 商业版帐户，请转到 Windows "**开始**" 按钮，右键单击您当前的帐户图片，然后**切换帐户**。</span><span class="sxs-lookup"><span data-stu-id="35f7f-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="35f7f-147">使用组织电子邮件和密码进行登录。</span><span class="sxs-lookup"><span data-stu-id="35f7f-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="35f7f-149">验证设备是否升级到 Windows 10 商业版</span><span class="sxs-lookup"><span data-stu-id="35f7f-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="35f7f-150">验证加入了 Azure AD 的 Windows 10 设备是否已升级到 Windows 10 商业版（Microsoft 365 商业版订阅的一部分）。</span><span class="sxs-lookup"><span data-stu-id="35f7f-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="35f7f-151">转到" **设置**"\>" **系统**"\>" **关于**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="35f7f-152">确认" **版本**"显示的是" **Windows 10 商业版**"。</span><span class="sxs-lookup"><span data-stu-id="35f7f-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="35f7f-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35f7f-154">Next steps</span></span>

<span data-ttu-id="35f7f-155">若要设置移动设备，请参阅[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。若要设置设备保护或应用保护策略，请参阅[管理 Microsoft 365 商业版](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="35f7f-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35f7f-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35f7f-156">See also</span></span>

[<span data-ttu-id="35f7f-157">Microsoft 365 商业培训视频</span><span class="sxs-lookup"><span data-stu-id="35f7f-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
