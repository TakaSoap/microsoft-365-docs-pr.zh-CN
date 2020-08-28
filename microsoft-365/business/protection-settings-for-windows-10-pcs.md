---
title: 编辑或创建 Windows 10 电脑的设备保护设置
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解 Microsoft 365 for business 中适用于 Windows 10 设备的安全设置。
ms.openlocfilehash: bd992113403c7134fb32bc6cced5bf216843241b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289147"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="a08a2-103">编辑或创建 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="a08a2-103">Edit or create device protection settings for Windows 10 PCs</span></span>

<span data-ttu-id="a08a2-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="a08a2-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a08a2-105">设置 "设置" 页面上的 "设置默认 Windows 保护设置" 后，可以添加适用于所有用户或一组用户的新的 "Windows 保护" 设置。</span><span class="sxs-lookup"><span data-stu-id="a08a2-105">After you have set set up default Windows protection settings on the Setup page, you can add new ones that apply to either all users, or a set of users.</span></span> <span data-ttu-id="a08a2-106">您还可以编辑已创建的任何文件。</span><span class="sxs-lookup"><span data-stu-id="a08a2-106">You can also edit any of the ones you have created.</span></span>

## <a name="create-protection-settings-for-windows-10-devices"></a><span data-ttu-id="a08a2-107">为 Windows 10 设备创建保护设置</span><span class="sxs-lookup"><span data-stu-id="a08a2-107">Create protection settings for Windows 10 devices</span></span>

<span data-ttu-id="a08a2-108">观看有关如何使用 Microsoft 365 商业高级版保护 Windows 10 设备的视频：</span><span class="sxs-lookup"><span data-stu-id="a08a2-108">View a video on how to secure Windows 10 devices with Microsoft 365 Business Premium:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="a08a2-109">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="a08a2-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="a08a2-110">在左侧导航中，选择 " **设备** \> **策略**" " \> **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a08a2-110">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="a08a2-111">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="a08a2-111">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="a08a2-112">在" **策略类型**"下，选择" **Windows 10 设备配置**"。</span><span class="sxs-lookup"><span data-stu-id="a08a2-112">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
5. <span data-ttu-id="a08a2-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="a08a2-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="a08a2-114">有关详细信息，请参阅 [可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="a08a2-114">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="a08a2-115">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="a08a2-115">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="a08a2-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="a08a2-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
7. <span data-ttu-id="a08a2-119">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="a08a2-119">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 

## <a name="edit-windows-10-protection-settings"></a><span data-ttu-id="a08a2-120">编辑 Windows 10 保护设置</span><span class="sxs-lookup"><span data-stu-id="a08a2-120">Edit Windows 10 protection settings</span></span>
 
1. <span data-ttu-id="a08a2-121">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="a08a2-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="a08a2-122">在左侧导航中，选择 " **设备** \> **策略** "。</span><span class="sxs-lookup"><span data-stu-id="a08a2-122">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="a08a2-123">选择现有的 Windows 设备策略，然后进行 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="a08a2-123">Choose an existing Windows device policy and then **Edit**.</span></span>
1. <span data-ttu-id="a08a2-124">选择要更改的设置旁边的 " **编辑** "，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a08a2-124">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="available-settings"></a><span data-ttu-id="a08a2-125">可用设置</span><span class="sxs-lookup"><span data-stu-id="a08a2-125">Available settings</span></span>

<span data-ttu-id="a08a2-126">所有设置均默认为" **开启**"状态。</span><span class="sxs-lookup"><span data-stu-id="a08a2-126">By default all settings are **On**.</span></span> <span data-ttu-id="a08a2-127">可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="a08a2-127">The following settings are available.</span></span>
  
<span data-ttu-id="a08a2-128">有关详细信息，请参阅 [Microsoft 365 Premium 中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a08a2-128">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a08a2-129">Setting</span><span class="sxs-lookup"><span data-stu-id="a08a2-129">Setting</span></span>  <br/> |<span data-ttu-id="a08a2-130">说明</span><span class="sxs-lookup"><span data-stu-id="a08a2-130">Description</span></span>  <br/> |
|<span data-ttu-id="a08a2-131">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="a08a2-131">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="a08a2-132">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="a08a2-132">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="a08a2-133">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="a08a2-133">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="a08a2-134">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="a08a2-134">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="a08a2-135">使用减少设备攻击面的规则</span><span class="sxs-lookup"><span data-stu-id="a08a2-135">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="a08a2-p105">启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以了解详细信息。  </span><span class="sxs-lookup"><span data-stu-id="a08a2-p105">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="a08a2-139">保护文件夹免受勒索软件等威胁</span><span class="sxs-lookup"><span data-stu-id="a08a2-139">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="a08a2-140">此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。</span><span class="sxs-lookup"><span data-stu-id="a08a2-140">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="a08a2-141">无法在受保护的文件夹中更改这些类型的应用。</span><span class="sxs-lookup"><span data-stu-id="a08a2-141">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="a08a2-142">仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="a08a2-142">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="a08a2-143">请参阅 [使用受控制文件夹的访问保护文件夹](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a08a2-143">See [Protect folders with Controlled folder access](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="a08a2-144">防止网络访问 Internet 上的潜在恶意内容</span><span class="sxs-lookup"><span data-stu-id="a08a2-144">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="a08a2-145">使用此设置可阻止出站用户与可承载网络钓鱼诈骗、入侵或其他恶意内容的低信誉 Internet 位置的连接。</span><span class="sxs-lookup"><span data-stu-id="a08a2-145">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="a08a2-146">仅当 Windows Defender 防病毒设置为 **打开**时，此设置才可用。</span><span class="sxs-lookup"><span data-stu-id="a08a2-146">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="a08a2-147">有关详细信息，请参阅 [保护网络](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="a08a2-147">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="a08a2-148">使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="a08a2-148">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="a08a2-149">Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。</span><span class="sxs-lookup"><span data-stu-id="a08a2-149">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="a08a2-150">有关详细信息，请参阅 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。</span><span class="sxs-lookup"><span data-stu-id="a08a2-150">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="a08a2-151">允许用户从 Microsoft Store 下载应用</span><span class="sxs-lookup"><span data-stu-id="a08a2-151">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="a08a2-p109">允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  </span><span class="sxs-lookup"><span data-stu-id="a08a2-p109">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="a08a2-154">允许用户访问 Cortana</span><span class="sxs-lookup"><span data-stu-id="a08a2-154">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="a08a2-155">Cortana 非常有用！</span><span class="sxs-lookup"><span data-stu-id="a08a2-155">Cortana can be very helpful!</span></span> <span data-ttu-id="a08a2-156">Cortana 可以为你打开或关闭设置、提供说明，并确保你的约会时间已过，因此，默认情况下将此设置保持为 **打开** 。</span><span class="sxs-lookup"><span data-stu-id="a08a2-156">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="a08a2-157">允许用户接收来自 Microsoft 的 Windows 提示和广告</span><span class="sxs-lookup"><span data-stu-id="a08a2-157">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="a08a2-158">Windows 提示非常方便，可在新功能发布时为用户提供指导。</span><span class="sxs-lookup"><span data-stu-id="a08a2-158">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="a08a2-159">让 Windows 10 设备自动保持最新状态</span><span class="sxs-lookup"><span data-stu-id="a08a2-159">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="a08a2-160">确保 Windows 10 设备会自动接收最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a08a2-160">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="a08a2-161">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="a08a2-161">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="a08a2-p111">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="a08a2-p111">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
