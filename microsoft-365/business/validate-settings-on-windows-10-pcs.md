---
title: 验证 Windows 10 电脑上的应用保护设置
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证 Microsoft 365 商业应用保护设置是否在用户的 Windows 10 设备上生效。
ms.openlocfilehash: 1b661b41a8042e81f653463cbd32fc6bf6428b53
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "42549949"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="2423e-103">验证 Windows 10 电脑上的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="2423e-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="2423e-104">验证是否已设置 Windows 10 设备策略</span><span class="sxs-lookup"><span data-stu-id="2423e-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="2423e-105">[设置设备策略](protection-settings-for-windows-10-pcs.md)后，可能需要几个小时才能使策略在用户的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="2423e-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="2423e-106">您可以通过查看用户设备上的各种 Windows 设置屏幕来确认这些策略是否生效。</span><span class="sxs-lookup"><span data-stu-id="2423e-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="2423e-107">由于用户无法修改其 Windows 10 设备上的 Windows Update 和 Windows Defender 防病毒设置，因此许多选项将灰显。</span><span class="sxs-lookup"><span data-stu-id="2423e-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="2423e-108">转到 "**设置** \> " " \*\* &amp;更新安全\*\* \*\*\*\* \> \> Windows 更新**重新启动选项**"，并确认所有设置均显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="2423e-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![所有重新启动选项都将灰显。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="2423e-110">转到 "**设置** \> " "**更新&amp;安全** \*\*\*\* \> \> Windows 更新**高级选项**"，并确认所有设置均显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="2423e-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows 高级更新选项全部显示为灰色。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="2423e-112">转到**设置** \> **更新&amp;安全** \> **Windows 更新** \> **高级选项** \> **选择如何传递更新**。</span><span class="sxs-lookup"><span data-stu-id="2423e-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="2423e-113">确认您可以看到某些设置已被组织隐藏或管理的邮件（红色），所有选项都将灰显。</span><span class="sxs-lookup"><span data-stu-id="2423e-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![选择如何传递更新页面指示你的组织隐藏或管理的设置。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="2423e-115">若要打开 windows defender 安全中心，请转到**设置** \> **更新&amp;安全** \> \> **Windows defender**单击**打开 windows defender 安全中心** \> **病毒&amp;线程防护** \> \*\* &amp;病毒防护设置\*\*。</span><span class="sxs-lookup"><span data-stu-id="2423e-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="2423e-116">验证所有选项是否都显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="2423e-116">Verify that all options are grayed out.</span></span> 
    
    ![病毒和威胁防护设置显示为灰色。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="2423e-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="2423e-118">Related Topics</span></span>

<span data-ttu-id="2423e-119">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）</span><span class="sxs-lookup"><span data-stu-id="2423e-119">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)</span></span>
  
[<span data-ttu-id="2423e-120">Microsoft 365 Business 入门</span><span class="sxs-lookup"><span data-stu-id="2423e-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="2423e-121">管理 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="2423e-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="2423e-122">设置 Windows 10 电脑的设备配置</span><span class="sxs-lookup"><span data-stu-id="2423e-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

