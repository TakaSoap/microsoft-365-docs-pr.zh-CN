---
title: 设置 Windows 10 电脑的设备保护设置
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
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解 Microsoft 365 for business 中提供的用于保护 Windows 10 设备的默认设置和其他设置。
ms.openlocfilehash: 9096fb6a8fc790d9a9432578cfd8623f9cb69c7a
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011559"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="b3b2f-103">设置 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="b3b2f-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="b3b2f-104">保护 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="b3b2f-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="b3b2f-105">观看有关如何使用 Microsoft 365 for business 保护 Windows 10 设备的视频：</span><span class="sxs-lookup"><span data-stu-id="b3b2f-105">View a video on how to secure Windows 10 devices with Microsoft 365 for business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="b3b2f-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="b3b2f-107">在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="b3b2f-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="b3b2f-109">在" **策略类型**"下，选择" **Windows 10 设备配置**"。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="b3b2f-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="b3b2f-111">有关详细信息，请参阅[可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-111">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="b3b2f-112">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="b3b2f-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="b3b2f-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="b3b2f-116">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="b3b2f-117">可用设置</span><span class="sxs-lookup"><span data-stu-id="b3b2f-117">Available settings</span></span>

<span data-ttu-id="b3b2f-118">所有设置均默认为" **开启**"状态。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-118">By default all settings are **On**.</span></span> <span data-ttu-id="b3b2f-119">可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="b3b2f-119">The following settings are available.</span></span>
  
<span data-ttu-id="b3b2f-120">有关详细信息，请参阅[Microsoft 365 Premium 中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-120">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b3b2f-121">设置</span><span class="sxs-lookup"><span data-stu-id="b3b2f-121">Setting</span></span>  <br/> |<span data-ttu-id="b3b2f-122">说明</span><span class="sxs-lookup"><span data-stu-id="b3b2f-122">Description</span></span>  <br/> |
|<span data-ttu-id="b3b2f-123">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="b3b2f-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="b3b2f-124">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-125">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="b3b2f-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="b3b2f-126">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-127">使用减少设备攻击面的规则</span><span class="sxs-lookup"><span data-stu-id="b3b2f-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="b3b2f-p104">启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以了解详细信息。  </span><span class="sxs-lookup"><span data-stu-id="b3b2f-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="b3b2f-131">保护文件夹免受勒索软件等威胁</span><span class="sxs-lookup"><span data-stu-id="b3b2f-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="b3b2f-132">此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-132">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="b3b2f-133">无法在受保护的文件夹中更改这些类型的应用。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-133">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="b3b2f-134">仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-134">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="b3b2f-135">请参阅[使用受控制文件夹的访问保护文件夹](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-135">See [Protect folders with Controlled folder access](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-136">防止网络访问 Internet 上的潜在恶意内容</span><span class="sxs-lookup"><span data-stu-id="b3b2f-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="b3b2f-137">使用此设置可阻止出站用户与可承载网络钓鱼诈骗、入侵或其他恶意内容的低信誉 Internet 位置的连接。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-137">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="b3b2f-138">仅当 Windows Defender 防病毒设置为**打开**时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-138">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="b3b2f-139">有关详细信息，请参阅[保护网络](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-139">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="b3b2f-140">使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="b3b2f-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="b3b2f-141">Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-141">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="b3b2f-142">有关详细信息，请参阅[BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-142">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="b3b2f-143">允许用户从 Microsoft Store 下载应用</span><span class="sxs-lookup"><span data-stu-id="b3b2f-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="b3b2f-p108">允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  </span><span class="sxs-lookup"><span data-stu-id="b3b2f-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="b3b2f-146">允许用户访问 Cortana</span><span class="sxs-lookup"><span data-stu-id="b3b2f-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="b3b2f-147">Cortana 非常有用！</span><span class="sxs-lookup"><span data-stu-id="b3b2f-147">Cortana can be very helpful!</span></span> <span data-ttu-id="b3b2f-148">Cortana 可以为你打开或关闭设置、提供说明，并确保你的约会时间已过，因此，默认情况下将此设置保持为**打开**。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-148">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-149">允许用户接收来自 Microsoft 的 Windows 提示和广告</span><span class="sxs-lookup"><span data-stu-id="b3b2f-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="b3b2f-150">Windows 提示非常方便，可在新功能发布时为用户提供指导。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-151">让 Windows 10 设备自动保持最新状态</span><span class="sxs-lookup"><span data-stu-id="b3b2f-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="b3b2f-152">确保 Windows 10 设备会自动接收最新的更新。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="b3b2f-153">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="b3b2f-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="b3b2f-p110">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="b3b2f-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
