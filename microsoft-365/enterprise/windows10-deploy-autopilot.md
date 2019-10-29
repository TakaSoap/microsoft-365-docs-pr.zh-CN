---
title: 使用 Windows Autopilot 为新设备部署 Windows 10 企业版
description: 提供有关使用 Windows Autopilot 配置和部署 Windows 10 企业版的指南。
keywords: Microsoft 365，Microsoft 365 Enterprise，Microsoft 365 文档，Windows 10 企业版，部署，Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 0d85bc51ac3f224b396281ff4e8414541097ed22
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746538"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a><span data-ttu-id="82db8-104">步骤3：使用 Windows Autopilot 为新设备部署 Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="82db8-104">Step 3: Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>

<span data-ttu-id="82db8-105">*本文适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="82db8-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![阶段 3：Windows 10 企业版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="82db8-107">如果你有新的 Windows 10 电脑，则可以使用 Windows Autopilot 为你的组织自定义现成体验（OOBE），并部署具有已配置的应用程序和设置的新系统。</span><span class="sxs-lookup"><span data-stu-id="82db8-107">If you have new Windows 10 PCs, you can use Windows Autopilot to customize the out-of-box-experience (OOBE) for your organization and deploy a new system with apps and settings already configured.</span></span> <span data-ttu-id="82db8-108">没有要部署的映像，没有要注入的驱动程序，没有要管理的基础结构。</span><span class="sxs-lookup"><span data-stu-id="82db8-108">There are no images to deploy, no drivers to inject, and no infrastructure to manage.</span></span> <span data-ttu-id="82db8-109">用户可以独立完成部署过程，无需咨询其 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="82db8-109">Users can go through the deployment process independently, without the need consult their IT administrator.</span></span>

<span data-ttu-id="82db8-110">您可以设置和预配置新的 Windows 10 设备，让它们准备好使用 Windows Autopilot 进行高效使用。</span><span class="sxs-lookup"><span data-stu-id="82db8-110">You can set up and pre-configure new Windows 10 devices and get them ready for productive use using Windows Autopilot.</span></span> <span data-ttu-id="82db8-111">若要了解有关 Windows Autopilot 的详细信息（包括福利和 Windows Autopilot 方案），请参阅[Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)。</span><span class="sxs-lookup"><span data-stu-id="82db8-111">To learn more about Windows Autopilot, including benefits and Windows Autopilot scenarios, see [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot).</span></span> <span data-ttu-id="82db8-112">准备就绪后，请按照以下部件开始设置新设备。</span><span class="sxs-lookup"><span data-stu-id="82db8-112">When ready, follow these parts to start setting up new devices.</span></span>

## <a name="the-windows-autopilot-deployment-process-poster"></a><span data-ttu-id="82db8-113">Windows Autopilot 部署过程海报</span><span class="sxs-lookup"><span data-stu-id="82db8-113">The Windows Autopilot deployment process poster</span></span>

<span data-ttu-id="82db8-114">Windows Autopilot 海报是纵向模式（11x17）中的两页。</span><span class="sxs-lookup"><span data-stu-id="82db8-114">The Windows Autopilot poster is two pages in portrait mode (11x17).</span></span> <span data-ttu-id="82db8-115">单击下面的图像以在浏览器中查看 PDF。</span><span class="sxs-lookup"><span data-stu-id="82db8-115">Click the image below to view a PDF in your browser.</span></span> 

<span data-ttu-id="82db8-116">[![使用 Autopilot 海报部署 Windows 10](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=bfzlEl8SrShCQyj8E2QUf6LJfxlKre6ortODE4qHjrc%3D&st=2019-10-24T22%3A18%3A33Z&se=2019-10-25T22%3A28%3A33Z&sp=r)</span><span class="sxs-lookup"><span data-stu-id="82db8-116">[![Deploy Windows 10 with Autopilot poster](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=bfzlEl8SrShCQyj8E2QUf6LJfxlKre6ortODE4qHjrc%3D&st=2019-10-24T22%3A18%3A33Z&se=2019-10-25T22%3A28%3A33Z&sp=r)</span></span>

<span data-ttu-id="82db8-117">您还可以下载[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf)或[Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx)格式的此海报。</span><span class="sxs-lookup"><span data-stu-id="82db8-117">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) format.</span></span>

## <a name="part-1-start-windows-autopilot-deployment"></a><span data-ttu-id="82db8-118">第1部分：启动 Windows Autopilot 部署</span><span class="sxs-lookup"><span data-stu-id="82db8-118">Part 1: Start Windows Autopilot deployment</span></span>
<span data-ttu-id="82db8-119">请参阅[Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)to：</span><span class="sxs-lookup"><span data-stu-id="82db8-119">See [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) to:</span></span>

1. <span data-ttu-id="82db8-120">了解并完成 Windows Autopilot 部署的先决条件。</span><span class="sxs-lookup"><span data-stu-id="82db8-120">Learn about and complete the prerequisites for Windows Autopilot deployment.</span></span> <span data-ttu-id="82db8-121">先决条件包括：</span><span class="sxs-lookup"><span data-stu-id="82db8-121">The prerequisites include:</span></span>
    - <span data-ttu-id="82db8-122">**设备注册和 OOBE 自定义**</span><span class="sxs-lookup"><span data-stu-id="82db8-122">**Device registration and OOBE customization**</span></span>

        <span data-ttu-id="82db8-123">若要注册设备，您需要获取其硬件 ID 并进行注册。</span><span class="sxs-lookup"><span data-stu-id="82db8-123">To register devices, you need to acquire their hardware ID and register it.</span></span> <span data-ttu-id="82db8-124">我们正在与各种硬件供应商合作，让他们为你提供所需的信息，或代表你上传。</span><span class="sxs-lookup"><span data-stu-id="82db8-124">We are actively working with various hardware vendors to enable them to provide the required information to you, or upload it on your behalf.</span></span> <span data-ttu-id="82db8-125">您还可以选择使用生成包含设备的硬件 ID 的 .csv 文件的 PowerShell 脚本来捕获此信息。</span><span class="sxs-lookup"><span data-stu-id="82db8-125">You also have the option to capture this information by yourself using a PowerShell script that generates a .csv file with the device's hardware ID.</span></span>

        <span data-ttu-id="82db8-126">注册设备后，可以配置 OOBE 自定义选项，包括跳过隐私设置和 EULA。</span><span class="sxs-lookup"><span data-stu-id="82db8-126">Once devices are registered, there are OOBE customization options that you can configure including skipping privacy settings and EULA.</span></span>

    - <span data-ttu-id="82db8-127">**针对 OOBE 的公司品牌塑造**</span><span class="sxs-lookup"><span data-stu-id="82db8-127">**Company branding for OOBE**</span></span>

        <span data-ttu-id="82db8-128">这使您可以在设备 OOBE 期间添加品牌显示。</span><span class="sxs-lookup"><span data-stu-id="82db8-128">This allows you to add branding to appear during device OOBE.</span></span>

    - <span data-ttu-id="82db8-129">**Microsoft Intune 中的 MDM 自动注册**</span><span class="sxs-lookup"><span data-stu-id="82db8-129">**MDM auto-enrollment in Microsoft Intune**</span></span>
        
        <span data-ttu-id="82db8-130">在将设备连接到 Azure AD 时，自动注册允许用户在 Intune 中为设备管理注册其 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="82db8-130">Automatic enrollment lets users enroll their Windows 10 devices in Intune for device management when they connect their devices to Azure AD.</span></span> <span data-ttu-id="82db8-131">若要注册，用户需要将其工作帐户添加到其个人拥有的设备，或将公司拥有的设备加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="82db8-131">To enroll, users add their work account to their personally-owned devices or join corporate-owned devices to Azure AD.</span></span> <span data-ttu-id="82db8-132">在后台，还会为该设备注册使用 Intune 进行管理。</span><span class="sxs-lookup"><span data-stu-id="82db8-132">In the background, the device is also enrolled for management with Intune.</span></span>

    - <span data-ttu-id="82db8-133">**Windows Autopilot 所使用的云服务的网络连接**</span><span class="sxs-lookup"><span data-stu-id="82db8-133">**Network connectivity to cloud services used by Windows Autopilot**</span></span>

        <span data-ttu-id="82db8-134">Windows Autopilot 部署程序使用大量云服务将设备恢复到生产状态，并且必须可从注册为 Windows Autopilot 设备的设备访问这些服务。</span><span class="sxs-lookup"><span data-stu-id="82db8-134">The Windows Autopilot Deployment Program uses a number of cloud services to get your devices to a productive state and these services must be accessible from devices registered as Windows Autopilot devices.</span></span> 

    - <span data-ttu-id="82db8-135">**设备必须已预安装 Windows 10 版本 1703 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="82db8-135">**Devices must be pre-installed with Windows 10, version 1703 or later**</span></span>

2. <span data-ttu-id="82db8-136">了解并为您的组织选择 Windows Autopilot 部署计划。</span><span class="sxs-lookup"><span data-stu-id="82db8-136">Learn about and select the Windows Autopilot Deployment Program for your organization.</span></span> <span data-ttu-id="82db8-137">您可以从以下部署程序中进行选择：</span><span class="sxs-lookup"><span data-stu-id="82db8-137">You can select from these deployment programs:</span></span>
    - <span data-ttu-id="82db8-138">**适用于企业的 Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="82db8-138">**Microsoft Store for Business**</span></span>
    - <span data-ttu-id="82db8-139">**Microsoft Intune**</span><span class="sxs-lookup"><span data-stu-id="82db8-139">**Microsoft Intune**</span></span>
    - <span data-ttu-id="82db8-140">**合作伙伴中心**</span><span class="sxs-lookup"><span data-stu-id="82db8-140">**Partner Center**</span></span>

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a><span data-ttu-id="82db8-141">第2部分：为 Microsoft 365 设置 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="82db8-141">Part 2: Set up a Windows 10 device for Microsoft 365</span></span>
<span data-ttu-id="82db8-142">在为 Microsoft 365 用户设置 Windows 设备之前，请确保所有 Windows 设备运行的是 Windows 10、版本1703（创意者更新）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="82db8-142">Before you can set up Windows devices for Microsoft 365 users, make sure all the Windows devices are running Windows 10, version 1703 (Creators Update) or later.</span></span>

<span data-ttu-id="82db8-143">在组织中的所有 Windows 设备都已升级到 Windows 10 创意者更新或已在运行 Windows 10 创意者更新之后，您可以将这些设备加入到组织的 Azure Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="82db8-143">After all Windows devices in your organization have either been upgraded to Windows 10 Creators Update or are already running Windows 10 Creators Update, you can join these devices to your organization’s Azure Active Directory.</span></span>

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a><span data-ttu-id="82db8-144">设置全新的或新升级的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="82db8-144">Set up a brand new or newly-upgraded Windows 10 device</span></span>
<span data-ttu-id="82db8-145">按照以下步骤操作，在运行 Windows 10 创意者更新（或更高版本）的全新设备上或在升级到 Windows 10 创意者更新（或更高版本）但尚未通过全新安装程序更新的设备上使用 Windows 10 OOBE 设置设备。</span><span class="sxs-lookup"><span data-stu-id="82db8-145">Follow these steps to set up a device using the Windows 10 OOBE on a brand new device running Windows 10 Creators Update (or later) or on a device that was upgrade to Windows 10 Creators Update (or later) but has not gone through out-of-box setup.</span></span>

1. <span data-ttu-id="82db8-146">如果没有配置无线网络，请确保通过有线或以太网连接将设备连接到 internet。</span><span class="sxs-lookup"><span data-stu-id="82db8-146">If you don't have a wireless network configured, make sure you connect the device to the internet through a wired or Ethernet connection.</span></span>
2. <span data-ttu-id="82db8-147">请浏览 Windows 设备设置体验。</span><span class="sxs-lookup"><span data-stu-id="82db8-147">Go through the Windows device setup experience.</span></span> <span data-ttu-id="82db8-148">在新的或重置设备上，安装程序体验将以 "开始" 的 "地区" 开头 **。此权限正确吗？** 闪屏.</span><span class="sxs-lookup"><span data-stu-id="82db8-148">On a new or reset device, the setup experience starts with the **Let's start with region. Is this right?** screen.</span></span>
3. <span data-ttu-id="82db8-149">完成 Windows 10 设备设置，直到显示" **设置方式**"页面。</span><span class="sxs-lookup"><span data-stu-id="82db8-149">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> <span data-ttu-id="82db8-150">在此处，为组织选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-150">Here, select **Set up for an organization**.</span></span>
4. <span data-ttu-id="82db8-151">使用 Microsoft 365 用户的帐户和密码登录。</span><span class="sxs-lookup"><span data-stu-id="82db8-151">Sign in using the Microsoft 365 user's account and password.</span></span> <span data-ttu-id="82db8-152">根据用户密码设置的不同，可能会提示您更新密码。</span><span class="sxs-lookup"><span data-stu-id="82db8-152">Depending on the user password setting, you may be prompted to update the password.</span></span> 
5. <span data-ttu-id="82db8-153">完成 Windows 10 设备设置。</span><span class="sxs-lookup"><span data-stu-id="82db8-153">Finish Windows 10 device setup.</span></span>

<span data-ttu-id="82db8-154">完成后，设备将连接到您的组织的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="82db8-154">After you’re done, the device will be connected to your organization’s Azure AD.</span></span>

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a><span data-ttu-id="82db8-155">设置已完成的设备的开箱即用安装程序</span><span class="sxs-lookup"><span data-stu-id="82db8-155">Set up a device that has already completed out-of-box setup</span></span>
<span data-ttu-id="82db8-156">如果你的设备具有 Windows 10 创意者更新（或更高版本），并且已通过 "开箱即用" 安装程序，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="82db8-156">If your device has Windows 10 Creators Update (or later) and has already gone through the out-of-box setup, follow these steps.</span></span>

1. <span data-ttu-id="82db8-157">在运行 Windows 10 版本1703（创意者更新）的用户的 Windows 电脑上，选择**Windows**徽标，然后选择 "**设置**" 图标。</span><span class="sxs-lookup"><span data-stu-id="82db8-157">On your user's Windows PC that is running Windows 10, version 1703 (Creators Update), select the **Windows** logo, and then select the **Settings** icon.</span></span>
2. <span data-ttu-id="82db8-158">2.在" **设置**"中，转到" **帐户**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-158">In **Settings**, go to **Accounts**.</span></span>
3. <span data-ttu-id="82db8-159">在 "**你的信息**" 页上，选择 "**访问工作或学校** > **连接**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-159">On the **Your info** page, select **Access work or school** > **Connect**.</span></span>
4. <span data-ttu-id="82db8-160">在 "**设置工作或学校帐户**" 对话框中的 "**替代操作**" 下，选择 "将**此设备加入 Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-160">On the **Set up a work or school account** dialog, under **Alternate actions**, select **Join this device to Azure Active Directory**.</span></span>
5. <span data-ttu-id="82db8-161">在 "**让你登录**" 页面上，输入你的工作或学校帐户，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-161">On the **Let's get you signed in** page, enter your work or school account, and select **Next**.</span></span>
6. <span data-ttu-id="82db8-162">在 "**输入密码**" 页面上，输入您的密码，然后选择 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-162">On the **Enter password** page, enter your password, and select **Sign in**.</span></span>
7. <span data-ttu-id="82db8-163">在 "**确保这是你的组织**" 页上，验证信息是否正确，然后选择 "**加入**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-163">On the **Make sure this is your organization** page, verify that the information is correct, and select **Join**.</span></span>
8. <span data-ttu-id="82db8-164">在 "**全是" 设置！**</span><span class="sxs-lookup"><span data-stu-id="82db8-164">On the **You're all set!**</span></span> <span data-ttu-id="82db8-165">页面上，选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-165">page, select **Done**.</span></span>

<span data-ttu-id="82db8-166">完成后，用户将连接到您的组织的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="82db8-166">After you're done, the user will be connected to your organization's Azure AD.</span></span>

### <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="82db8-167">验证设备是否连接到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="82db8-167">Verify the device is connected to Azure AD</span></span>
<span data-ttu-id="82db8-168">按照以下步骤操作，以使用 Azure AD 验证设备的同步状态，然后开始在设备上使用 Microsoft 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="82db8-168">Follow these steps to verify the device’s sync status with Azure AD, and then start using your Microsoft 365 account on the device.</span></span> 

1. <span data-ttu-id="82db8-169">打开 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="82db8-169">Open **Settings**.</span></span>
2. <span data-ttu-id="82db8-170">在 "**访问工作或学校**" 页面上，选择 "**已连接到<organization name> \*\* " 区域以显示按钮**信息**并**断开连接\*\*。</span><span class="sxs-lookup"><span data-stu-id="82db8-170">On the **Access work or school** page, select the **Connected to <organization name>** area to expose the buttons **Info** and **Disconnect**.</span></span>
3. <span data-ttu-id="82db8-171">选择 "**信息**" 以获取你的同步状态。</span><span class="sxs-lookup"><span data-stu-id="82db8-171">Select **Info** to get your synchronization status.</span></span>
4. <span data-ttu-id="82db8-172">在 "**同步状态**" 页上，选择 "**同步**" 以获取电脑上的最新移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="82db8-172">On the **Sync status** page, select **Sync** to get the latest mobile device management policies onto the PC.</span></span>
5. <span data-ttu-id="82db8-173">若要开始使用 Microsoft 365 帐户，请转到 Windows "**开始**" 按钮，右键单击您当前的帐户图片，然后选择 "**切换**帐户"。</span><span class="sxs-lookup"><span data-stu-id="82db8-173">To start using the Microsoft 365 account, go to the Windows **Start** button, right-click your current account picture and then select **Switch** account.</span></span>
6. <span data-ttu-id="82db8-174">使用组织电子邮件和密码进行登录。</span><span class="sxs-lookup"><span data-stu-id="82db8-174">Sign in by using your organization email and password.</span></span>

<span data-ttu-id="82db8-175">如果在企业环境中使用 Windows 10 时遇到问题，可以参阅[主要 Microsoft 支持解决方案，了解最常见的问题](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。</span><span class="sxs-lookup"><span data-stu-id="82db8-175">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions).</span></span> <span data-ttu-id="82db8-176">这些资源包括知识库文章、更新和库文章。</span><span class="sxs-lookup"><span data-stu-id="82db8-176">These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="82db8-177">作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step3)。</span><span class="sxs-lookup"><span data-stu-id="82db8-177">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="82db8-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82db8-178">Next step</span></span>

|||
|:-------|:-----|
|![第 4 步](./media/stepnumbers/Step4.png)| [<span data-ttu-id="82db8-180">监视设备运行状况和合规性</span><span class="sxs-lookup"><span data-stu-id="82db8-180">Monitor device health and compliance</span></span>](windows10-enable-windows-analytics.md) |
