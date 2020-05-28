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
description: 了解如何使用 Microsoft 365 商业高级版中的 AutoPilot 上传设备。 您可以将配置文件分配给一个或一组设备。
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400986"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="c1a66-104">创建和编辑 AutoPilot 设备</span><span class="sxs-lookup"><span data-stu-id="c1a66-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="c1a66-105">上传设备列表</span><span class="sxs-lookup"><span data-stu-id="c1a66-105">Upload a list of devices</span></span>

<span data-ttu-id="c1a66-106">您可以使用分步[指南](add-autopilot-devices-and-profile.md)上载设备，但也可以在 "**设备**" 选项卡中上传设备。</span><span class="sxs-lookup"><span data-stu-id="c1a66-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="c1a66-107">设备必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="c1a66-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="c1a66-108">Windows 10 版本1703或更高版本</span><span class="sxs-lookup"><span data-stu-id="c1a66-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="c1a66-109">尚未通过 Windows 开箱即用体验的新设备</span><span class="sxs-lookup"><span data-stu-id="c1a66-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="c1a66-110">在 Microsoft 365 管理中心，选择 "**设备** \> **AutoPilot**"。</span><span class="sxs-lookup"><span data-stu-id="c1a66-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="c1a66-111">在 " **AutoPilot** " 页上，选择 "**设备**" 选项卡 " \> **添加设备**"。</span><span class="sxs-lookup"><span data-stu-id="c1a66-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="c1a66-113">在 "**添加设备**" 面板上，浏览到已准备好保存的[设备列表 CSV 文件](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) \> **Save** \> **Close**。</span><span class="sxs-lookup"><span data-stu-id="c1a66-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="c1a66-114">您可以从您的硬件供应商处获取此信息，也可以使用[G-et-windowsautopilotinfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)生成 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="c1a66-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="c1a66-115">向单个设备或一组设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="c1a66-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="c1a66-116">在 "**准备 Windows** " 页面上，选择 "**设备**" 选项卡，然后选中一个或多个设备旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="c1a66-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="c1a66-117">在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="c1a66-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="c1a66-118">如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="c1a66-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
