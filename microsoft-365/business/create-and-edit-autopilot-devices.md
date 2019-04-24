---
title: 创建和编辑 AutoPilot 设备
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何使用 Microsoft 365 商业版中的 AutoPilot 上传设备。 您可以将配置文件分配给一个或一组设备。
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277015"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="01d3f-104">创建和编辑 AutoPilot 设备</span><span class="sxs-lookup"><span data-stu-id="01d3f-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="01d3f-105">上传设备列表</span><span class="sxs-lookup"><span data-stu-id="01d3f-105">Upload a list of devices</span></span>

<span data-ttu-id="01d3f-106">可以使用[分步指南](add-autopilot-devices-and-profile.md)上传设备，还可通过" **设备**"选项卡上传设备。</span><span class="sxs-lookup"><span data-stu-id="01d3f-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="01d3f-107">设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="01d3f-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="01d3f-108">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="01d3f-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="01d3f-109">未获得过 Windows 现成体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="01d3f-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="01d3f-110">在 Microsoft 365 Business 管理中心中, 选择 "**设备** \> " **AutoPilot** \> "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="01d3f-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot** \> **Add**.</span></span>
  
2. <span data-ttu-id="01d3f-111">在" **准备 Windows**"页面上，选择" **设备**"选项卡 \>" **添加设备**"。</span><span class="sxs-lookup"><span data-stu-id="01d3f-111">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="01d3f-113">在 "**添加设备**" 面板上, 浏览到已准备好\*\*\*\* \> \*\*\*\* \>保存的[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。</span><span class="sxs-lookup"><span data-stu-id="01d3f-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="01d3f-114">可从硬件供应商获取此信息，也可以使用将生成 csv 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。</span><span class="sxs-lookup"><span data-stu-id="01d3f-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="01d3f-115">向单个设备或一组设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="01d3f-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="01d3f-116">在" **准备 Windows**"页面上，选择" **设备**"选项卡，并勾选一个或多个设备旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="01d3f-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="01d3f-117">在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="01d3f-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="01d3f-118">如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="01d3f-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
