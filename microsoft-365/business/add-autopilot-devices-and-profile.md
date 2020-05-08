---
title: 使用分步指南添加 Autopilot 设备和配置文件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为你的企业设置新的 Windows 10 设备，以便其可供员工使用。
ms.openlocfilehash: de14012ebf9e7cdd22e41505f316ab665773c670
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165873"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="00eab-103">使用分步指南添加 Autopilot 设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="00eab-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="00eab-104">您可以使用 Windows AutoPilot 为你的企业设置**新**的 Windows 10 设备，以便在你将其提供给员工时可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="00eab-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="00eab-105">设备要求</span><span class="sxs-lookup"><span data-stu-id="00eab-105">Device requirements</span></span>

<span data-ttu-id="00eab-106">设备必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="00eab-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="00eab-107">Windows 10 版本1703或更高版本</span><span class="sxs-lookup"><span data-stu-id="00eab-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="00eab-108">尚未通过 Windows 开箱即用体验的新设备</span><span class="sxs-lookup"><span data-stu-id="00eab-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="00eab-109">使用设置指南创建设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="00eab-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="00eab-110">[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="00eab-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="00eab-111">如果尚未创建设备组或配置文件，最好的入门方式是使用分步指南。</span><span class="sxs-lookup"><span data-stu-id="00eab-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="00eab-112">您还可以[添加设备](create-and-edit-autopilot-devices.md)并[将配置文件分配](create-and-edit-autopilot-profiles.md)给它们，而无需使用指南。</span><span class="sxs-lookup"><span data-stu-id="00eab-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="00eab-113">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="00eab-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="00eab-114">在左侧导航窗格中，选择 "**设备** \> " " **AutoPilot**"。</span><span class="sxs-lookup"><span data-stu-id="00eab-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![在管理中心中，选择 "设备"，然后选择 "AutoPilot"。](../media/AutoPilot.png)
  
2. <span data-ttu-id="00eab-116">在 " **AutoPilot** " 页上，单击或点击 "**启动指南**"。</span><span class="sxs-lookup"><span data-stu-id="00eab-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="00eab-118">在 "**使用设备列表上载 .csv 文件**" 页上，浏览到已准备就绪的位置。CSV 文件，然后**打开** \> "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="00eab-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="00eab-119">该文件必须具有三个标头：</span><span class="sxs-lookup"><span data-stu-id="00eab-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="00eab-120">列 A：设备序列号</span><span class="sxs-lookup"><span data-stu-id="00eab-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="00eab-121">列 B：Windows 产品 ID</span><span class="sxs-lookup"><span data-stu-id="00eab-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="00eab-122">列 C：硬件哈希</span><span class="sxs-lookup"><span data-stu-id="00eab-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="00eab-123">您可以从您的硬件供应商处获取此信息，也可以使用[G-et-windowsautopilotinfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)生成 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="00eab-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="00eab-p103">有关详细信息，请参阅[设备列表 CSV 文件](https://docs.microsoft.com/microsoft-365/admin/misc/device-list)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。</span><span class="sxs-lookup"><span data-stu-id="00eab-p103">For more information, see [Device list CSV-file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="00eab-126">在 "**分配配置文件**" 页上，可以选择现有配置文件，也可以创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="00eab-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="00eab-127">如果尚未安装，系统会提示您创建一个。</span><span class="sxs-lookup"><span data-stu-id="00eab-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="00eab-128">配置文件是可应用到单个设备或一组设备的一系列设置。</span><span class="sxs-lookup"><span data-stu-id="00eab-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="00eab-129">默认功能是必需的，并会自动设置。</span><span class="sxs-lookup"><span data-stu-id="00eab-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="00eab-130">默认功能是：</span><span class="sxs-lookup"><span data-stu-id="00eab-130">The default features are:</span></span>
    
    - <span data-ttu-id="00eab-131">跳过 Cortana、OneDrive 和 OEM 注册。</span><span class="sxs-lookup"><span data-stu-id="00eab-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="00eab-132">使用公司品牌创建登录体验。</span><span class="sxs-lookup"><span data-stu-id="00eab-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="00eab-133">将设备连接到 Azure Active Directory 帐户，并自动注册以由 Microsoft 365 商业高级版管理。</span><span class="sxs-lookup"><span data-stu-id="00eab-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="00eab-134">有关详细信息，请参阅[关于 AutoPilot 配置文件设置](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="00eab-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="00eab-135">其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。</span><span class="sxs-lookup"><span data-stu-id="00eab-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="00eab-136">选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="00eab-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="00eab-137">**您已完成**指示您创建的配置文件（或选择的）将应用于您通过上载设备列表创建的设备组。</span><span class="sxs-lookup"><span data-stu-id="00eab-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="00eab-138">这些设置将在设备用户下次登录时生效。</span><span class="sxs-lookup"><span data-stu-id="00eab-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="00eab-139">选择\*\*\*\*“关闭”。</span><span class="sxs-lookup"><span data-stu-id="00eab-139">Choose **Close**.</span></span>
    
