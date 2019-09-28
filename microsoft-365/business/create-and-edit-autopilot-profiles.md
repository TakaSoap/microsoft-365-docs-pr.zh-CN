---
title: 创建和编辑 AutoPilot 配置文件
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '了解如何创建、编辑、删除或删除 AutoPilot 配置文件。 '
ms.openlocfilehash: 8fae8af5e7aa7b866745d0b34a4fe11862de6e9d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287767"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="9f5eb-103">创建和编辑 AutoPilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="9f5eb-104">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-104">Create a profile</span></span>

<span data-ttu-id="9f5eb-105">配置文件适用于单个设备或一组设备，</span><span class="sxs-lookup"><span data-stu-id="9f5eb-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="9f5eb-106">在 Microsoft 365 Business 管理中心中，选择 "**设备** \> " **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="9f5eb-107">在 " **AutoPilot** " 页上，选择 "**配置文件**" 选项卡\> **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="9f5eb-108">在" **创建配置文件**"页面上，输入可帮助识别配置文件的文件名称，例如"市场营销"，启用所需设置（请参阅[关于"AutoPilot 配置文件"设置](autopilot-profile-settings.md)获取详细信息），并选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="9f5eb-110">对设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-110">Apply profile to a device</span></span>

<span data-ttu-id="9f5eb-p101">创建配置文件之后，可将其应用到一个或一组设备。可以选择[分步指南](add-autopilot-devices-and-profile.md)中的现有配置文件，然后将其应用于新设备，或可替换某个设备或一组设备的现有配置文件。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="9f5eb-113">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="9f5eb-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="9f5eb-116">编辑、删除或移除配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="9f5eb-p102">将配置文件分配给一个设备后，便可以更新该文件，即使已将该设备提供给一个用户。如果设备连接了 internet，系统会在设置过程中下载最新版本的配置文件。如果用户将其设备恢复为出厂默认设置，设备将再次下载配置文件的最新更新。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="9f5eb-120">编辑配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-120">Edit a profile</span></span>

1. <span data-ttu-id="9f5eb-121">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="9f5eb-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="9f5eb-123">如果在用户将设备连接到 internet 之前执行此操作，配置文件会应用于设置过程。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="9f5eb-124">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-124">Delete a profile</span></span>

1. <span data-ttu-id="9f5eb-125">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="9f5eb-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="9f5eb-127">如果删除了配置文件，该文件会从之前分配到的一个或一组设备中移除。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="9f5eb-128">移除配置文件</span><span class="sxs-lookup"><span data-stu-id="9f5eb-128">Remove a profile</span></span>

1. <span data-ttu-id="9f5eb-129">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="9f5eb-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="9f5eb-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
