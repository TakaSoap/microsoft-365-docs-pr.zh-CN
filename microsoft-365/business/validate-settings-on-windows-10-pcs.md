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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证 Microsoft 365 商业版应用保护设置是否对用户的 Windows 10 设备生效。
ms.openlocfilehash: ff99b3a4fce49aebdb5c72f51e46678a7821e186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912406"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="62489-103">验证 Windows 10 PC 上的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="62489-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="62489-104">验证 Windows 10 设备策略是否设置</span><span class="sxs-lookup"><span data-stu-id="62489-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="62489-105">设置 [设备策略后](protection-settings-for-windows-10-pcs.md)，策略可能需要几个小时才能在用户的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="62489-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="62489-106">可以通过查看用户设备上的各个 Windows 设置屏幕来确认策略是否生效。</span><span class="sxs-lookup"><span data-stu-id="62489-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="62489-107">由于用户将无法修改 Windows 更新，Windows Defender Windows 10 设备上禁用防病毒设置，因此许多选项将灰显。</span><span class="sxs-lookup"><span data-stu-id="62489-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="62489-108">转到"**设置** \> **&amp; ""更新安全性** \> **""Windows** 更新 \> ""重启"选项，并确认所有设置都显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="62489-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![所有"重启"选项都灰显。](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="62489-110">转到设置 \> **更新 &amp; 安全性** \> **Windows 更新** \> **高级选项** 并确认所有设置都灰显。</span><span class="sxs-lookup"><span data-stu-id="62489-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows 高级更新选项全部灰显。](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="62489-112">转到设置 \> **更新 &amp; 安全性** \> **Windows 更新** \> **高级选项** \> **选择如何传递更新**。</span><span class="sxs-lookup"><span data-stu-id="62489-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="62489-113">确认你能看到红色 (显示) 某些设置被组织隐藏或管理，并且所有选项都显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="62489-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![选择更新的传递方式页面指示组织隐藏或管理设置。](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="62489-115">若要打开Windows Defender安全中心"，请转到"设置""更新Windows Defender"打开Windows Defender病毒线程保护 \> **&amp;** \>  \>  \> **&amp;** \> **病毒 &amp; 威胁防护设置"。**</span><span class="sxs-lookup"><span data-stu-id="62489-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="62489-116">验证所有选项是否灰显。</span><span class="sxs-lookup"><span data-stu-id="62489-116">Verify that all options are grayed out.</span></span> 
    
    ![病毒和威胁防护设置灰显。](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="62489-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="62489-118">Related Topics</span></span>

[<span data-ttu-id="62489-119">Microsoft 365 商业版文档和资源</span><span class="sxs-lookup"><span data-stu-id="62489-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="62489-120">Microsoft 365 商业版入门</span><span class="sxs-lookup"><span data-stu-id="62489-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="62489-121">管理 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="62489-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="62489-122">设置 Windows 10 电脑的设备配置</span><span class="sxs-lookup"><span data-stu-id="62489-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
