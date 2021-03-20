---
title: 创建和编辑 AutoPilot 设备
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何使用 Microsoft 365 商业高级版中的 AutoPilot 上载设备。 你可以将配置文件分配给设备或一组设备。
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913390"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="6a5b2-104">创建和编辑 AutoPilot 设备</span><span class="sxs-lookup"><span data-stu-id="6a5b2-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="6a5b2-105">上传设备列表</span><span class="sxs-lookup"><span data-stu-id="6a5b2-105">Upload a list of devices</span></span>

<span data-ttu-id="6a5b2-106">可以使用分 [步](add-autopilot-devices-and-profile.md) 指南上传设备，但还可以在"设备"选项卡 **中上传** 设备。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="6a5b2-107">设备必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="6a5b2-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="6a5b2-108">Windows 10 版本 1703 或更高版本</span><span class="sxs-lookup"><span data-stu-id="6a5b2-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="6a5b2-109">尚未通过 Windows 全新体验的新设备</span><span class="sxs-lookup"><span data-stu-id="6a5b2-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="6a5b2-110">在 Microsoft 365 管理中心，选择 **设备** \> **AutoPilot**。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="6a5b2-111">在 **AutoPilot 页面上**，选择 **"设备**"选项卡 \> **"添加设备"。**</span><span class="sxs-lookup"><span data-stu-id="6a5b2-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="6a5b2-113">在添加 **设备面板** 上，浏览到你准备保存关闭的设备列表 [CSV](../admin/misc/device-list.md) \>  \> **文件**。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="6a5b2-114">你可以从硬件供应商获取此信息，或者可以使用 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 脚本生成 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="6a5b2-115">向单个设备或一组设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="6a5b2-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="6a5b2-116">在" **准备 Windows"** 页上，选择" **设备** "选项卡，然后选中一个或多个设备旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="6a5b2-117">在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="6a5b2-118">如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="6a5b2-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
