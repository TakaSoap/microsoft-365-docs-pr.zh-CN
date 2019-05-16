---
title: 使用分步指南添加 Autopilot 设备和配置文件
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为你的企业设置新的 Windows 10 设备。
ms.openlocfilehash: 9a70978156fb26ac3aad08f1758b7ee125067d38
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072142"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="e36f6-103">使用分步指南添加 Autopilot 设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="e36f6-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="e36f6-104">您可以使用 Windows AutoPilot 为你的企业设置**新**的 Windows 10 设备, 以便在你将其提供给员工时随时准备就绪以供生产使用。</span><span class="sxs-lookup"><span data-stu-id="e36f6-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="e36f6-105">设备要求</span><span class="sxs-lookup"><span data-stu-id="e36f6-105">Device requirements</span></span>

<span data-ttu-id="e36f6-106">设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="e36f6-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="e36f6-107">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e36f6-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="e36f6-108">未获得过 Windows 现成体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="e36f6-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="e36f6-109">使用设置指南创建设备和配置文件</span><span class="sxs-lookup"><span data-stu-id="e36f6-109">Use the setup guide to create devices and profiles</span></span>

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

<span data-ttu-id="e36f6-111">如果尚未创建设备组或配置文件，最好首先使用分步指南，但也可在不使用指南的情况下，[添加设备](create-and-edit-autopilot-devices.md)和[分配配置文件](create-and-edit-autopilot-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e36f6-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="e36f6-112">转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="e36f6-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e36f6-113">在左侧导航中, 选择 "**设备** \> **AutoPilot**"。</span><span class="sxs-lookup"><span data-stu-id="e36f6-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![在管理中心选择 "设备", 然后选择 "AutoPilot"。](media/AutoPilot.png)
  
2. <span data-ttu-id="e36f6-115">在 " **AutoPilot** " 页上, 单击或点击 "**启动指南**"。</span><span class="sxs-lookup"><span data-stu-id="e36f6-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="e36f6-p101">在" **上传设备列表 .csv 文件**"页面，浏览到已准备好的 .CSV 文件所在位置，然后单击" **打开**"\>" **下一步**"。该文件应具有三个页眉：</span><span class="sxs-lookup"><span data-stu-id="e36f6-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="e36f6-119">列 A：设备序列号</span><span class="sxs-lookup"><span data-stu-id="e36f6-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="e36f6-120">列 B：Windows 产品 ID</span><span class="sxs-lookup"><span data-stu-id="e36f6-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="e36f6-121">列 C：硬件哈希</span><span class="sxs-lookup"><span data-stu-id="e36f6-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="e36f6-122">可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。</span><span class="sxs-lookup"><span data-stu-id="e36f6-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="e36f6-p102">有关详细信息，请参阅[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。</span><span class="sxs-lookup"><span data-stu-id="e36f6-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="e36f6-p103">在" **分配配置文件**"页面上，可选择现有配置文件或新建配置文件。如果没有配置文件，系统会提示新建配置文件。</span><span class="sxs-lookup"><span data-stu-id="e36f6-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="e36f6-127">配置文件是可应用到单个设备或一组设备的一系列设置。</span><span class="sxs-lookup"><span data-stu-id="e36f6-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="e36f6-p104">默认功能是必需的且会自动设置。默认功能是：</span><span class="sxs-lookup"><span data-stu-id="e36f6-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="e36f6-130">跳过 Cortana、OneDrive 和 OEM 注册。</span><span class="sxs-lookup"><span data-stu-id="e36f6-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="e36f6-131">使用公司品牌创建登录体验。</span><span class="sxs-lookup"><span data-stu-id="e36f6-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="e36f6-132">你的设备将连接到 Azure Active Directory 帐户，并自动注册以便由 Microsoft 365 商业版 托管。</span><span class="sxs-lookup"><span data-stu-id="e36f6-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="e36f6-133">有关详细信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="e36f6-133">For more information, see</span></span>
    
    <span data-ttu-id="e36f6-134">[关于 AutoPilot 配置文件设置](autopilot-profile-settings.md) 。</span><span class="sxs-lookup"><span data-stu-id="e36f6-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="e36f6-135">其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。</span><span class="sxs-lookup"><span data-stu-id="e36f6-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="e36f6-136">选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e36f6-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="e36f6-p105">" **完成**"页面指示创建（或选择）的配置文件会应用到通过上传设备列表创建的设备组。这些设置将在设备用户下次登录时生效。选择" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e36f6-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    