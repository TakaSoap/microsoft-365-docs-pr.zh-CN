---
title: 计划 Microsoft Defender 防病毒保护更新
description: 计划应下载保护更新的时间、时间和间隔
keywords: 更新， 安全基线， 计划更新
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689943"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="4ed37-104">管理何时应下载和应用保护更新的计划</span><span class="sxs-lookup"><span data-stu-id="4ed37-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4ed37-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4ed37-105">**Applies to:**</span></span>

- [<span data-ttu-id="4ed37-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ed37-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4ed37-107">Microsoft Defender 防病毒允许你确定何时应查找和下载更新。</span><span class="sxs-lookup"><span data-stu-id="4ed37-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="4ed37-108">可以按：为终结点计划更新：</span><span class="sxs-lookup"><span data-stu-id="4ed37-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="4ed37-109">指定一周中的哪些天检查保护更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="4ed37-110">指定检查保护更新的时间间隔</span><span class="sxs-lookup"><span data-stu-id="4ed37-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="4ed37-111">指定检查保护更新的时间</span><span class="sxs-lookup"><span data-stu-id="4ed37-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="4ed37-112">还可以随机化每个终结点检查和下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="4ed37-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="4ed37-113">有关详细信息 [，请参阅计划](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 扫描主题。</span><span class="sxs-lookup"><span data-stu-id="4ed37-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="4ed37-114">使用 Configuration Manager 计划保护更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="4ed37-115">在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  </span><span class="sxs-lookup"><span data-stu-id="4ed37-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="4ed37-116">转到" **安全智能更新"** 部分。</span><span class="sxs-lookup"><span data-stu-id="4ed37-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="4ed37-117">在特定时间检查和下载更新：</span><span class="sxs-lookup"><span data-stu-id="4ed37-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="4ed37-118">将 **"以特定间隔检查 Endpoint Protection 安全智能更新..."** 设置为 **0。**</span><span class="sxs-lookup"><span data-stu-id="4ed37-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="4ed37-119">将 **"每天检查 Endpoint Protection 安全智能更新..."** 设置为应检查更新的时间。</span><span class="sxs-lookup"><span data-stu-id="4ed37-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="4ed37-120">3</span><span class="sxs-lookup"><span data-stu-id="4ed37-120">3</span></span>
4. <span data-ttu-id="4ed37-121">若要持续检查并下载更新，请以特定间隔将"检查 Endpoint Protection 安全智能更新 **..."** 设置为更新之间应发生的小时数。</span><span class="sxs-lookup"><span data-stu-id="4ed37-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="4ed37-122">[像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="4ed37-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="4ed37-123">使用组策略计划保护更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ed37-124">默认情况下，Microsoft Defender 防病毒将在任何计划扫描时间前 15 分钟检查更新。</span><span class="sxs-lookup"><span data-stu-id="4ed37-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="4ed37-125">启用这些设置将覆盖该默认设置。</span><span class="sxs-lookup"><span data-stu-id="4ed37-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="4ed37-126">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="4ed37-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="4ed37-127">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="4ed37-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="4ed37-128">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="4ed37-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="4ed37-129">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名智能更新** 并配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="4ed37-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="4ed37-130">双击指定 **一周中的哪些天检查** 安全智能更新设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="4ed37-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4ed37-131">输入一周中的一天以检查更新。</span><span class="sxs-lookup"><span data-stu-id="4ed37-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="4ed37-132">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4ed37-132">Click **OK**.</span></span>
    2. <span data-ttu-id="4ed37-133">双击指定 **检查安全智能更新的** 间隔设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="4ed37-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4ed37-134">输入更新之间的小时数。</span><span class="sxs-lookup"><span data-stu-id="4ed37-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="4ed37-135">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4ed37-135">Click **OK**.</span></span>
    3. <span data-ttu-id="4ed37-136">双击指定 **检查安全智能更新** 的时间设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="4ed37-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4ed37-137">输入应检查更新的时间。</span><span class="sxs-lookup"><span data-stu-id="4ed37-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="4ed37-138">时间基于终结点的本地时间。</span><span class="sxs-lookup"><span data-stu-id="4ed37-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="4ed37-139">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4ed37-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="4ed37-140">使用 PowerShell cmdlet 计划保护更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="4ed37-141">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4ed37-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="4ed37-142">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)  配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="4ed37-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="4ed37-143">使用 Windows Management Instruction (WMI) 计划保护更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="4ed37-144">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="4ed37-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="4ed37-145">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="4ed37-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="4ed37-146">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="4ed37-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="4ed37-147">相关文章</span><span class="sxs-lookup"><span data-stu-id="4ed37-147">Related articles</span></span>

- [<span data-ttu-id="4ed37-148">部署 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="4ed37-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ed37-149">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="4ed37-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ed37-150">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ed37-151">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="4ed37-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ed37-152">使用虚拟机管理移动设备和虚拟机 (更新) </span><span class="sxs-lookup"><span data-stu-id="4ed37-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4ed37-153">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="4ed37-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)