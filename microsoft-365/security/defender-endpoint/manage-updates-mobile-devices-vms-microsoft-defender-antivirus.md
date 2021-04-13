---
title: 定义 Microsoft Defender 防病毒如何更新移动设备
description: 使用 Microsoft Defender 防病毒保护更新管理移动设备（如笔记本电脑）的更新方式。
keywords: 更新， 保护， 计划更新， 电池， 移动设备， 笔记本电脑， 笔记本， 选择加入， Microsoft 更新， wsus， 替代
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689934"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="b1e6f-104">管理移动设备和虚拟机更新 (VM) </span><span class="sxs-lookup"><span data-stu-id="b1e6f-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b1e6f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b1e6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="b1e6f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1e6f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b1e6f-107">移动设备和 VM 可能需要进行更多配置，以确保性能不会受更新影响。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="b1e6f-108">有两个设置对这些设备有用：</span><span class="sxs-lookup"><span data-stu-id="b1e6f-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="b1e6f-109">选择在没有 WSUS 连接的情况下在移动计算机上加入 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="b1e6f-110">使用电池电源运行时阻止安全智能更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="b1e6f-111">以下文章在这些情况下可能也很有用：</span><span class="sxs-lookup"><span data-stu-id="b1e6f-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="b1e6f-112">配置计划扫描和跟进扫描</span><span class="sxs-lookup"><span data-stu-id="b1e6f-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b1e6f-113">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b1e6f-114">虚拟桌面基础结构中的 Microsoft Defender 防病毒部署指南 (VDI) 环境</span><span class="sxs-lookup"><span data-stu-id="b1e6f-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="b1e6f-115">选择在没有 WSUS 连接的情况下在移动计算机上加入 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="b1e6f-116">当运行 Microsoft Defender 防病毒的移动设备未连接到企业网络或没有 WSUS 连接时，可以使用 Microsoft 更新使这些设备的安全智能保持最新。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="b1e6f-117">这意味着，即使将 WSUS 设置为覆盖 Microsoft 更新 (Microsoft 更新) 保护更新也可以传递到设备。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="b1e6f-118">可以通过以下方法之一选择在移动设备上使用 Microsoft 更新：</span><span class="sxs-lookup"><span data-stu-id="b1e6f-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="b1e6f-119">使用组策略更改设置。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="b1e6f-120">使用 VBScript 创建脚本，然后在网络的每台计算机中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="b1e6f-121">通过"设置"菜单手动选择加入网络 **的每** 台计算机。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="b1e6f-122">使用组策略选择加入 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="b1e6f-123">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="b1e6f-124">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b1e6f-125">选择 **"策略\*\*\*\*"，然后选择"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="b1e6f-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b1e6f-126">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名更新**。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="b1e6f-127">将 **"允许安全智能更新从 Microsoft 更新"设置为\*\*\*\*"已启用"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b1e6f-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="b1e6f-128">使用 VBScript 选择加入 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="b1e6f-129">使用 MSDN 文章选择加入 [Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 中的说明创建 VBScript。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="b1e6f-130">运行在网络的每台计算机中创建的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="b1e6f-131">手动选择加入 Microsoft 更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="b1e6f-132">在 **"更新\*\*\*\*"&** 要选择加入的计算机的"更新和安全设置"中打开 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="b1e6f-133">选择 **"高级选项** "。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="b1e6f-134">选中"更新 Windows **时为我提供其他 Microsoft** 产品的更新"复选框。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="b1e6f-135">使用电池电源运行时阻止安全智能更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="b1e6f-136">你可以将 Microsoft Defender 防病毒配置为仅在电脑连接到有线电源时下载保护更新。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="b1e6f-137">使用组策略阻止使用电池电源进行安全智能更新</span><span class="sxs-lookup"><span data-stu-id="b1e6f-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="b1e6f-138">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，选择要配置的组策略对象，然后打开它进行编辑。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="b1e6f-139">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="b1e6f-140">选择 **"策略\*\*\*\*"，然后选择"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="b1e6f-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="b1e6f-141">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名更新**，然后将使用电池电源运行时允许安全智能更新设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="b1e6f-142">然后，选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-142">Then select **OK**.</span></span> 

<span data-ttu-id="b1e6f-143">此操作可防止在电脑使用电池电源时下载保护更新。</span><span class="sxs-lookup"><span data-stu-id="b1e6f-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b1e6f-144">相关文章</span><span class="sxs-lookup"><span data-stu-id="b1e6f-144">Related articles</span></span>

- [<span data-ttu-id="b1e6f-145">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="b1e6f-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b1e6f-146">在 Windows 10 中更新和管理 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="b1e6f-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)