---
title: 创建和编辑 AutoPilot 设备
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: 了解如何上载设备使用自动执行某些操作在 Microsoft 365 企业版。您可以分配给设备或一组设备的配置文件。
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865648"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="3a0e6-104">创建和编辑 AutoPilot 设备</span><span class="sxs-lookup"><span data-stu-id="3a0e6-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="3a0e6-105">上传设备列表</span><span class="sxs-lookup"><span data-stu-id="3a0e6-105">Upload a list of devices</span></span>

<span data-ttu-id="3a0e6-106">可以使用[分步指南](add-autopilot-devices-and-profile.md)上传设备，还可通过" **设备**"选项卡上传设备。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="3a0e6-107">设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="3a0e6-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="3a0e6-108">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="3a0e6-109">未获得过 Windows 现成体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="3a0e6-110">在 Microsoft 365 商业版 管理中心的" **设备操作**"卡上，选择" **使用 Autopilot 部署 Windows**"。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="3a0e6-112">在" **准备 Windows**"页面上，选择" **设备**"选项卡 \>" **添加设备**"。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="3a0e6-114">在**添加设备**面板中，浏览到[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)已经准备好\>**保存** \> **关闭**。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="3a0e6-115">可从硬件供应商获取此信息，也可以使用将生成 csv 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="3a0e6-116">向单个设备或一组设备应用配置文件</span><span class="sxs-lookup"><span data-stu-id="3a0e6-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="3a0e6-117">在" **准备 Windows**"页面上，选择" **设备**"选项卡，并勾选一个或多个设备旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="3a0e6-118">在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="3a0e6-119">如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="3a0e6-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
