---
title: 验证 Windows 10 电脑上的应用保护设置
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何验证 Windows 10 设备中的 Microsoft 365 业务应用程序保护设置。
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865566"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="411e4-103">验证 Windows 10 Pc 上的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="411e4-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="411e4-104">请确认已设置 Windows 10 设备策略</span><span class="sxs-lookup"><span data-stu-id="411e4-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="411e4-p101">[设置设备策略](protection-settings-for-windows-10-pcs.md)后, 可能需要为要在用户的设备上生效的策略的几个小时。您可以确认策略通过在用户的设备上查看各种 Windows 设置屏幕发生效果。用户将无法修改其 Windows 10 设备上的 Windows Update 和 Windows Defender 防病毒设置，因为这些选项大量将为灰色。</span><span class="sxs-lookup"><span data-stu-id="411e4-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="411e4-108">转到**设置** \> **更新&amp;安全** \> **Windows Update** \> **重新启动选项**和确认灰显状态的所有设置。</span><span class="sxs-lookup"><span data-stu-id="411e4-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![重新启动的所有选项都灰色。](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="411e4-110">转到**设置** \> **更新&amp;安全** \> **Windows Update** \> **高级选项**和确认灰显状态的所有设置。</span><span class="sxs-lookup"><span data-stu-id="411e4-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![所有的灰色 Windows 高级更新选项。](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="411e4-112">转到**设置** \> **更新&amp;安全** \> **Windows Update** \> **高级选项** \> **如何提供更新的选择**。</span><span class="sxs-lookup"><span data-stu-id="411e4-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="411e4-113">确认您可以看到的 （以红色） 的消息，并且隐藏或管理您的组织，某些设置灰色显示的所有选项。</span><span class="sxs-lookup"><span data-stu-id="411e4-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![选择如何传送更新页指示隐藏或由组织管理设置。](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="411e4-115">要打开 Windows Defender 安全中心，请转到**设置** \> **更新&amp;安全** \> **Windows Defender** \>单击**打开 Windows Defender 安全中心** \> **病毒&amp;线程保护** \> **病毒&amp;威胁保护设置**。</span><span class="sxs-lookup"><span data-stu-id="411e4-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="411e4-116">验证灰显状态的所有选项。</span><span class="sxs-lookup"><span data-stu-id="411e4-116">Verify that all options are greyed out.</span></span> 
    
    ![以灰色突出显示的病毒和威胁保护设置。](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="411e4-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="411e4-118">Related Topics</span></span>

<span data-ttu-id="411e4-119">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）</span><span class="sxs-lookup"><span data-stu-id="411e4-119">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)</span></span>
  
[<span data-ttu-id="411e4-120">Microsoft 365 Business 入门</span><span class="sxs-lookup"><span data-stu-id="411e4-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="411e4-121">管理 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="411e4-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="411e4-122">设置 Windows 10 电脑的设备配置</span><span class="sxs-lookup"><span data-stu-id="411e4-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

