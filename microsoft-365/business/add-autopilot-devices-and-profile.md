---
title: 使用分步指南添加 Autopilot 设备和配置文件
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为Windows 10设置新设备，以便员工可以使用这些设备。
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636098"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="3b9ee-103">使用分步指南添加 Autopilot 设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="3b9ee-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="3b9ee-104">可以使用 Windows AutoPilot 为Windows 10设置新的设备，以便当你将这些设备授予你的员工时，这些设备可供使用。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="3b9ee-105">设备要求</span><span class="sxs-lookup"><span data-stu-id="3b9ee-105">Device requirements</span></span>

<span data-ttu-id="3b9ee-106">设备必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="3b9ee-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="3b9ee-107">Windows 10版本 1703 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3b9ee-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="3b9ee-108">尚未体验全新体验Windows全新体验的新设备</span><span class="sxs-lookup"><span data-stu-id="3b9ee-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="3b9ee-109">使用设置指南创建设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="3b9ee-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="3b9ee-110">如果你尚未创建设备组或配置文件，则开始使用最佳方法就是使用分步指南。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="3b9ee-111">还可以添加[设备并](create-and-edit-autopilot-devices.md)[为其分配配置文件](create-and-edit-autopilot-profiles.md)，而无需使用指南。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="3b9ee-112">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="3b9ee-113">在左侧导航窗格中，选择 **设备** \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![在管理中心，选择"设备"，然后选择"AutoPilot"。](../media/AutoPilot.png)
  
2. <span data-ttu-id="3b9ee-115">在 **AutoPilot** 页面上，单击或点击"开始 **指南"。**</span><span class="sxs-lookup"><span data-stu-id="3b9ee-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="3b9ee-117">On the **Upload .csv file with list of devices** page， browse to a location where you have the prepared .CSV file， then **Open** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="3b9ee-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="3b9ee-118">文件必须具有三个标头：</span><span class="sxs-lookup"><span data-stu-id="3b9ee-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="3b9ee-119">列 A：设备序列号</span><span class="sxs-lookup"><span data-stu-id="3b9ee-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="3b9ee-120">列 B：Windows 产品 ID</span><span class="sxs-lookup"><span data-stu-id="3b9ee-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="3b9ee-121">列 C：硬件哈希</span><span class="sxs-lookup"><span data-stu-id="3b9ee-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="3b9ee-122">你可以从硬件供应商获取此信息，或者可以使用 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 脚本生成 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="3b9ee-p103">有关详细信息，请参阅 [设备列表 CSV 文件](../admin/misc/device-list.md)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3b9ee-125">此脚本使用 WMI 检索客户在 Autopilot 中注册设备Windows属性。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="3b9ee-126">请注意，生成的 CSV 文件不收集 Windows 产品 ID (PKID) 值是正常的，因为注册设备不需要这样做，并且输出 CSV 中的 PKID 为 NULL 完全正常。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="3b9ee-127">将仅填充序列号和硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="3b9ee-128">在 **"分配配置文件"** 页上，您可以选择现有配置文件或创建新配置文件。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="3b9ee-129">如果还没有，系统将提示你创建一个。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="3b9ee-130">配置文件是可应用到单个设备或一组设备的一系列设置。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="3b9ee-131">默认功能是必需的，并且会自动设置。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="3b9ee-132">默认功能是：</span><span class="sxs-lookup"><span data-stu-id="3b9ee-132">The default features are:</span></span>
    
    - <span data-ttu-id="3b9ee-133">跳过 Cortana、OneDrive和 OEM 注册。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="3b9ee-134">使用公司品牌创建登录体验。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="3b9ee-135">连接你的设备Azure Active Directory帐户，并自动注册它们，以由Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="3b9ee-136">有关详细信息，请参阅关于 [AutoPilot 配置文件设置](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="3b9ee-137">其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="3b9ee-138">选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="3b9ee-139">**你已完成指示** 你创建 (或选择) 的配置文件将应用到通过上传设备列表创建的设备组。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="3b9ee-140">设置将在设备用户下次登录时生效。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="3b9ee-141">选择“关闭”。</span><span class="sxs-lookup"><span data-stu-id="3b9ee-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="3b9ee-142">相关内容</span><span class="sxs-lookup"><span data-stu-id="3b9ee-142">Related content</span></span>

<span data-ttu-id="3b9ee-143">[有关 AutoPilot 配置文件设置 (](autopilot-profile-settings.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="3b9ee-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="3b9ee-144">[用于保护设备和应用数据的选项](../admin/devices/choose-device-security.md) (本文) </span><span class="sxs-lookup"><span data-stu-id="3b9ee-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
