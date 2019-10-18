---
title: 设置 Windows 10 电脑的设备保护设置
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
description: 了解 Microsoft 365 商业版中提供的默认设置和其他设置，以保护 Windows 10 设备。
ms.openlocfilehash: ab306e3d5a6011a0e7d537c98ecca6ef49ff82d9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575750"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="ea7d8-103">设置 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="ea7d8-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="ea7d8-104">保护 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="ea7d8-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="ea7d8-105">查看有关如何使用 Microsoft 365 商业版保护 Windows 10 设备的视频：</span><span class="sxs-lookup"><span data-stu-id="ea7d8-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="ea7d8-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="ea7d8-107">在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="ea7d8-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="ea7d8-109">在" **策略类型**"下，选择" **Windows 10 设备配置**"。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="ea7d8-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span><span class="sxs-lookup"><span data-stu-id="ea7d8-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="ea7d8-112">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="ea7d8-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="ea7d8-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="ea7d8-116">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="ea7d8-117">可用设置</span><span class="sxs-lookup"><span data-stu-id="ea7d8-117">Available settings</span></span>

<span data-ttu-id="ea7d8-p103">所有设置均默认为" **开启**"状态。可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="ea7d8-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="ea7d8-120">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ea7d8-121">Setting</span><span class="sxs-lookup"><span data-stu-id="ea7d8-121">Setting</span></span>  <br/> |<span data-ttu-id="ea7d8-122">说明</span><span class="sxs-lookup"><span data-stu-id="ea7d8-122">Description</span></span>  <br/> |
|<span data-ttu-id="ea7d8-123">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="ea7d8-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="ea7d8-124">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="ea7d8-125">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="ea7d8-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="ea7d8-126">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="ea7d8-127">使用减少设备攻击面的规则</span><span class="sxs-lookup"><span data-stu-id="ea7d8-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="ea7d8-p104">启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](https://go.microsoft.com/fwlink/?linkid=870417)以了解详细信息。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="ea7d8-131">保护文件夹免受勒索软件等威胁</span><span class="sxs-lookup"><span data-stu-id="ea7d8-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="ea7d8-p105">此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。无法在受保护的文件夹中更改这些类型的应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。有关详细信息，请参阅[使用受控文件夹访问保护文件夹](https://go.microsoft.com/fwlink/?linkid=870418)。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="ea7d8-136">防止网络访问 Internet 上的潜在恶意内容</span><span class="sxs-lookup"><span data-stu-id="ea7d8-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="ea7d8-p106">使用此设置可阻止出站用户连接到可能承载网络钓鱼诈骗、漏洞利用或其他恶意内容的低信誉 Internet 位置。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。有关详细信息，请参阅[保护网络](https://go.microsoft.com/fwlink/?linkid=870419)。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="ea7d8-140">使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="ea7d8-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="ea7d8-p107">Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。有关详细信息，请参阅 [Bitlocker 常见问题解答](https://go.microsoft.com/fwlink/?linkid=871000)。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="ea7d8-143">允许用户从 Microsoft Store 下载应用</span><span class="sxs-lookup"><span data-stu-id="ea7d8-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="ea7d8-p108">允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="ea7d8-146">允许用户访问 Cortana</span><span class="sxs-lookup"><span data-stu-id="ea7d8-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="ea7d8-p109">Cortana 非常有用！该功能可为你打开/关闭设置、发出指令并确保你按时赴约，因此此设置默认保留为" **开**"。  </span><span class="sxs-lookup"><span data-stu-id="ea7d8-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="ea7d8-149">允许用户接收来自 Microsoft 的 Windows 提示和广告</span><span class="sxs-lookup"><span data-stu-id="ea7d8-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="ea7d8-150">Windows 提示非常方便，可在新功能发布时为用户提供指导。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="ea7d8-151">让 Windows 10 设备自动保持最新状态</span><span class="sxs-lookup"><span data-stu-id="ea7d8-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="ea7d8-152">确保 Windows 10 设备会自动接收最新的更新。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="ea7d8-153">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="ea7d8-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="ea7d8-p110">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="ea7d8-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

