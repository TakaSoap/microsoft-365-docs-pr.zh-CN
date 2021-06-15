---
title: 验证电脑的应用Windows 10设置
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证适用于Microsoft 365保护设置是否对用户的移动设备Windows 10生效。
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925251"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="c632f-103">验证电脑Windows 10保护设置</span><span class="sxs-lookup"><span data-stu-id="c632f-103">Validate device protection settings for Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="c632f-104">验证Windows 10策略是否设置</span><span class="sxs-lookup"><span data-stu-id="c632f-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="c632f-105">设置 [设备策略后](protection-settings-for-windows-10-pcs.md)，策略可能需要几个小时才能在用户的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="c632f-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="c632f-106">通过查看用户设备上的各个Windows 设置，可以确认策略是否生效。</span><span class="sxs-lookup"><span data-stu-id="c632f-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="c632f-107">由于用户无法修改 Windows 更新和Windows Defender 防病毒设备上Windows 10设置，因此许多选项将灰显。</span><span class="sxs-lookup"><span data-stu-id="c632f-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="c632f-108">Go to **设置** \> **Update &amp; security** \> **Windows Update** Restart \> **options** and confirm that all settings are grayed out.</span><span class="sxs-lookup"><span data-stu-id="c632f-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![所有"重启"选项都灰显。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="c632f-110">Go to **设置** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** and confirm that all settings are grayed out.</span><span class="sxs-lookup"><span data-stu-id="c632f-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows高级更新选项全部灰显。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="c632f-112">Go to **设置** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** Choose how \> **updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="c632f-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="c632f-113">确认你能看到红色 (显示) 某些设置被组织隐藏或管理，并且所有选项都显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="c632f-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![选择更新的传递方式页面指示组织隐藏或管理设置。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="c632f-115">若要打开Windows Defender安全中心，请转到设置更新安全中心Windows Defender打开Windows Defender病毒线程保护 \> **&amp;** \>  \>  \> **&amp;** \> **病毒 &amp; 威胁防护设置"。**</span><span class="sxs-lookup"><span data-stu-id="c632f-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="c632f-116">验证所有选项是否灰显。</span><span class="sxs-lookup"><span data-stu-id="c632f-116">Verify that all options are grayed out.</span></span> 
    
    ![病毒和威胁防护设置灰显。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="c632f-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="c632f-118">Related Topics</span></span>

[<span data-ttu-id="c632f-119">Microsoft 365文档和资源</span><span class="sxs-lookup"><span data-stu-id="c632f-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="c632f-120">企业Microsoft 365入门</span><span class="sxs-lookup"><span data-stu-id="c632f-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="c632f-121">管理Microsoft 365企业部署</span><span class="sxs-lookup"><span data-stu-id="c632f-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="c632f-122">设置 Windows 10 电脑的设备配置</span><span class="sxs-lookup"><span data-stu-id="c632f-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
