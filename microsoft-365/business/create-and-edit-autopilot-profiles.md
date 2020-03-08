---
title: 创建和编辑 AutoPilot 配置文件
f1.keywords:
- NOCSH
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 了解如何创建 AutoPilot 配置文件并将其应用到设备，以及编辑或删除配置文件或从设备中删除配置文件。
ms.openlocfilehash: 58c16b68c66dce7541a02ecd0d2466babe8cc338
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560712"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="0405c-103">创建和编辑 AutoPilot 配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="0405c-104">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-104">Create a profile</span></span>

<span data-ttu-id="0405c-105">配置文件适用于单个设备或一组设备，</span><span class="sxs-lookup"><span data-stu-id="0405c-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="0405c-106">在 Microsoft 365 Business 管理中心中，选择 "**设备** \> " **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="0405c-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="0405c-107">在 " **AutoPilot** " 页上，选择 "**配置文件**" 选项卡\> **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="0405c-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="0405c-108">在 "**创建配置文件**" 页上，输入可帮助您识别它的配置文件的名称，例如 "营销"。</span><span class="sxs-lookup"><span data-stu-id="0405c-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="0405c-109">打开所需的设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="0405c-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="0405c-110">有关 AutoPilot 配置文件设置的详细信息，请参阅[关于 AutoPilot 配置文件设置](autopilot-profile-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="0405c-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="0405c-112">对设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-112">Apply profile to a device</span></span>

<span data-ttu-id="0405c-113">创建配置文件后，可以将其应用到一个或一组设备。</span><span class="sxs-lookup"><span data-stu-id="0405c-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="0405c-114">您可以在分步[指南](add-autopilot-devices-and-profile.md)中选取现有配置文件，并将其应用于新设备，或替换某个设备或设备组的现有配置文件。</span><span class="sxs-lookup"><span data-stu-id="0405c-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="0405c-115">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="0405c-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0405c-116">选中设备名称旁边的复选框，然后在 "**设备**" 面板中，从 "**分配的配置文件**" 下拉列表\> **中**选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="0405c-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="0405c-118">编辑、删除或移除配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="0405c-p103">将配置文件分配给一个设备后，便可以更新该文件，即使已将该设备提供给一个用户。如果设备连接了 internet，系统会在设置过程中下载最新版本的配置文件。如果用户将其设备恢复为出厂默认设置，设备将再次下载配置文件的最新更新。</span><span class="sxs-lookup"><span data-stu-id="0405c-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="0405c-122">编辑配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-122">Edit a profile</span></span>

1. <span data-ttu-id="0405c-123">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="0405c-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0405c-124">选中设备名称旁边的复选框，然后在 "**配置文件**" 面板中，更新任何可用设置\> **保存**。</span><span class="sxs-lookup"><span data-stu-id="0405c-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="0405c-125">如果在用户将设备连接到 internet 之前执行此操作，配置文件会应用于设置过程。</span><span class="sxs-lookup"><span data-stu-id="0405c-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="0405c-126">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-126">Delete a profile</span></span>

1. <span data-ttu-id="0405c-127">在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="0405c-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="0405c-128">选中设备名称旁边的复选框，然后在 "**配置文件**" 面板中选择 "**删除配置文件** \> **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0405c-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="0405c-129">如果删除了配置文件，该文件会从之前分配到的一个或一组设备中移除。</span><span class="sxs-lookup"><span data-stu-id="0405c-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="0405c-130">移除配置文件</span><span class="sxs-lookup"><span data-stu-id="0405c-130">Remove a profile</span></span>

1. <span data-ttu-id="0405c-131">在" **准备 Windows**"页面上，选择" **设备**"选项卡。</span><span class="sxs-lookup"><span data-stu-id="0405c-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="0405c-132">选中设备名称旁边的复选框，然后在 "**设备**" 面板中，从 "分配的**配置文件**" \> **下拉列表中**选择 "**无**"。</span><span class="sxs-lookup"><span data-stu-id="0405c-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
