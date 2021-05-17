---
title: 创建和编辑 AutoPilot 配置文件
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 了解如何创建 AutoPilot 配置文件，并应用到设备，以及编辑或删除配置文件或者从设备中删除配置文件。
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580246"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="4b43e-103">创建和编辑 AutoPilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="4b43e-104">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-104">Create a profile</span></span>

<span data-ttu-id="4b43e-105">配置文件适用于单个设备或一组设备，</span><span class="sxs-lookup"><span data-stu-id="4b43e-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="4b43e-106">In the Microsoft 365 admin center， choose **Devices** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="4b43e-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="4b43e-107">在 **AutoPilot 页面上** ，选择 **配置文件** 选项卡 \> **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="4b43e-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="4b43e-108">在 **"创建配置文件** "页上，输入可帮助您标识该配置文件的名称，例如 Marketing。</span><span class="sxs-lookup"><span data-stu-id="4b43e-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="4b43e-109">打开您想要的设置，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b43e-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="4b43e-110">有关 AutoPilot 配置文件设置详细信息，请参阅关于 [AutoPilot 配置文件设置](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="4b43e-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="4b43e-112">对设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-112">Apply profile to a device</span></span>

<span data-ttu-id="4b43e-113">创建配置文件后，你可以将配置文件应用于设备或一组设备。</span><span class="sxs-lookup"><span data-stu-id="4b43e-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="4b43e-114">可以在分步指南中选取现有配置文件[](add-autopilot-devices-and-profile.md)并将其应用到新设备，或者替换设备或设备组的现有配置文件。</span><span class="sxs-lookup"><span data-stu-id="4b43e-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="4b43e-115">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b43e-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4b43e-116">选中设备名称旁边的复选框，在"设备"面板中，从"分配配置文件"下拉列表"保存"中选择 \> **配置文件**。</span><span class="sxs-lookup"><span data-stu-id="4b43e-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="4b43e-118">编辑、删除或移除配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="4b43e-p103">将配置文件分配给一个设备后，便可以更新该文件，即使已将该设备提供给一个用户。如果设备连接了 internet，系统会在设置过程中下载最新版本的配置文件。如果用户将其设备恢复为出厂默认设置，设备将再次下载配置文件的最新更新。</span><span class="sxs-lookup"><span data-stu-id="4b43e-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="4b43e-122">编辑配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-122">Edit a profile</span></span>

1. <span data-ttu-id="4b43e-123">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b43e-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4b43e-124">选中设备名称旁边的复选框，在配置文件面板中更新任何可用的设置保存 \> 。</span><span class="sxs-lookup"><span data-stu-id="4b43e-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="4b43e-125">如果在用户将设备连接到 internet 之前执行此操作，配置文件会应用于设置过程。</span><span class="sxs-lookup"><span data-stu-id="4b43e-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="4b43e-126">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-126">Delete a profile</span></span>

1. <span data-ttu-id="4b43e-127">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b43e-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="4b43e-128">选中设备名称旁边的复选框，在"配置文件"面板 **中，选择**"删除配置文件""**保存** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="4b43e-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="4b43e-129">如果删除了配置文件，该文件会从之前分配到的一个或一组设备中移除。</span><span class="sxs-lookup"><span data-stu-id="4b43e-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="4b43e-130">移除配置文件</span><span class="sxs-lookup"><span data-stu-id="4b43e-130">Remove a profile</span></span>

1. <span data-ttu-id="4b43e-131">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b43e-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="4b43e-132">选中设备名称旁边的复选框，在"设备"面板中，从"已分配配置文件"下拉列表"保存"中选择"无 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="4b43e-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
