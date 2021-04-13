---
title: 将 Microsoft Defender AV 保护更新应用到过期终结点
description: 定义何时以及如何对一段时间未更新的终结点应用更新。
keywords: 更新， 保护， 过期， 过时， 旧， 跟进
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3f56c18b66a27adfb1384f5c3f5e6c06034247d4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689945"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="74d29-104">管理 Microsoft Defender 防病毒更新并扫描过期的终结点</span><span class="sxs-lookup"><span data-stu-id="74d29-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="74d29-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74d29-105">**Applies to:**</span></span>

- [<span data-ttu-id="74d29-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="74d29-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="74d29-107">Microsoft Defender 防病毒允许你定义终结点在需要更新和扫描自身之前可以避免更新的所需时间或可以错过的扫描次数。</span><span class="sxs-lookup"><span data-stu-id="74d29-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="74d29-108">在设备不经常连接到公司或外部网络或者不每天使用的设备的环境中，这尤其有用。</span><span class="sxs-lookup"><span data-stu-id="74d29-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="74d29-109">例如，使用特定电脑的员工休息三天，在此期间不登录到其电脑。</span><span class="sxs-lookup"><span data-stu-id="74d29-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="74d29-110">当用户返回工作并登录到其电脑时，Microsoft Defender 防病毒将立即检查并下载最新的保护更新，并运行扫描。</span><span class="sxs-lookup"><span data-stu-id="74d29-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="74d29-111">为一段时间未更新的终结点设置跟进保护更新</span><span class="sxs-lookup"><span data-stu-id="74d29-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="74d29-112">如果 Microsoft Defender 防病毒在指定的时段内未下载保护更新，你可以将它设置为在下次登录时自动检查并下载最新更新。</span><span class="sxs-lookup"><span data-stu-id="74d29-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="74d29-113">如果你已全局禁用启动时的自动更新 [下载，这将非常有用](manage-event-based-updates-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="74d29-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="74d29-114">使用 Configuration Manager 配置跟进保护更新</span><span class="sxs-lookup"><span data-stu-id="74d29-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="74d29-115">在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  </span><span class="sxs-lookup"><span data-stu-id="74d29-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="74d29-116">转到" **安全智能更新"** 部分并配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="74d29-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="74d29-117">将 **"如果客户端计算机在连续计划更新** 两次以上时处于脱机状态，则强制进行安全智能更新"设置为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="74d29-118">对于  **"如果配置管理器用作** 安全智能更新的源..."，请指定配置管理器提供的保护更新应视为过期的小时数。</span><span class="sxs-lookup"><span data-stu-id="74d29-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="74d29-119">这将基于定义的回退源顺序，导致使用下一 [个更新位置](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)。</span><span class="sxs-lookup"><span data-stu-id="74d29-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="74d29-120">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-120">Click **OK**.</span></span>

4.  <span data-ttu-id="74d29-121">[像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="74d29-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="74d29-122">使用组策略启用和配置跟进更新功能</span><span class="sxs-lookup"><span data-stu-id="74d29-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="74d29-123">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="74d29-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="74d29-124">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="74d29-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="74d29-125">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="74d29-126">将树展开到 **Microsoft Defender 防病毒>签名> Windows 组件**。</span><span class="sxs-lookup"><span data-stu-id="74d29-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="74d29-127">双击定义需要更新安全智能的天数设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="74d29-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="74d29-128">输入希望 Microsoft Defender AV 检查并下载最新保护更新的天数。</span><span class="sxs-lookup"><span data-stu-id="74d29-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="74d29-129">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="74d29-130">使用 PowerShell cmdlet 配置跟进保护更新</span><span class="sxs-lookup"><span data-stu-id="74d29-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="74d29-131">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="74d29-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="74d29-132">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)  配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="74d29-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="74d29-133">使用 Windows Management Instruction (WMI) 配置跟进保护更新</span><span class="sxs-lookup"><span data-stu-id="74d29-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="74d29-134">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="74d29-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="74d29-135">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="74d29-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="74d29-136">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="74d29-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="74d29-137">设置保护报告为过期前的天数</span><span class="sxs-lookup"><span data-stu-id="74d29-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="74d29-138">还可以指定 Microsoft Defender 防病毒保护被视为旧或过期的天数。</span><span class="sxs-lookup"><span data-stu-id="74d29-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="74d29-139">指定天数后，客户端将自行报告为过期，并向电脑用户显示错误。</span><span class="sxs-lookup"><span data-stu-id="74d29-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="74d29-140">还可能导致 Microsoft Defender 防病毒尝试基于定义的回退源顺序 [ (](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order) 下载其他源) 的更新，例如将 WSUS 或 Microsoft Update 设置为第一个源后将 MMPC 用作辅助源时。</span><span class="sxs-lookup"><span data-stu-id="74d29-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="74d29-141">使用组策略指定保护被视为过期前的天数</span><span class="sxs-lookup"><span data-stu-id="74d29-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="74d29-142">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="74d29-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="74d29-143">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="74d29-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="74d29-144">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="74d29-145">将树展开到 Microsoft Defender 防病毒 **>签名> Windows** 组件，并配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="74d29-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="74d29-146">双击定义 **间谍软件定义** 被视为过期的天数，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="74d29-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="74d29-147">输入希望 Microsoft Defender AV 考虑间谍软件安全智能过期的天数。</span><span class="sxs-lookup"><span data-stu-id="74d29-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="74d29-148">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="74d29-149">双击"**定义病毒定义** 被视为过期的天数"，将选项设置为"**已启用"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="74d29-150">输入您希望 Microsoft Defender AV 考虑病毒安全智能过期的天数。</span><span class="sxs-lookup"><span data-stu-id="74d29-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="74d29-151">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="74d29-152">为一段时间未扫描的终结点设置跟进扫描</span><span class="sxs-lookup"><span data-stu-id="74d29-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="74d29-153">你可以设置在 Microsoft Defender 防病毒强制扫描之前可能错过的连续计划扫描的数量。</span><span class="sxs-lookup"><span data-stu-id="74d29-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="74d29-154">启用此功能的过程为：</span><span class="sxs-lookup"><span data-stu-id="74d29-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="74d29-155">设置至少一个计划扫描 (请参阅计划 [扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主题) 。</span><span class="sxs-lookup"><span data-stu-id="74d29-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="74d29-156">启用跟进扫描功能。</span><span class="sxs-lookup"><span data-stu-id="74d29-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="74d29-157">定义在进行跟进扫描之前可以跳过的扫描数。</span><span class="sxs-lookup"><span data-stu-id="74d29-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="74d29-158">可以针对完整扫描和快速扫描启用此功能。</span><span class="sxs-lookup"><span data-stu-id="74d29-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="74d29-159">使用组策略启用和配置跟进扫描功能</span><span class="sxs-lookup"><span data-stu-id="74d29-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="74d29-160">确保已设置至少一个计划扫描。</span><span class="sxs-lookup"><span data-stu-id="74d29-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="74d29-161">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="74d29-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="74d29-162">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="74d29-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="74d29-163">单击 **"策略\*\*\*\*"，然后单击"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="74d29-164">将树展开到 **Windows 组件> Microsoft Defender 防病毒>扫描并** 配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="74d29-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="74d29-165">如果已设置计划快速扫描，请双击"启用捕获快速扫描"设置，将该选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="74d29-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="74d29-166">如果已设置计划的完全扫描，请双击打开跟进 **完全扫描** 设置，将该选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="74d29-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="74d29-167">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-167">Click **OK**.</span></span>
    3. <span data-ttu-id="74d29-168">双击定义 **强制进行** 跟进扫描的天数设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="74d29-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="74d29-169">输入在用户下次登录到电脑时自动运行扫描之前可能错过的扫描数。</span><span class="sxs-lookup"><span data-stu-id="74d29-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="74d29-170">运行的扫描类型由指定要用于计划扫描的扫描类型确定 (请参阅计划扫描主题) 。 [](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="74d29-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="74d29-171">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="74d29-172">组策略设置标题是指天数。</span><span class="sxs-lookup"><span data-stu-id="74d29-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="74d29-173">但是，该设置应用于在运行 (扫描) 之前扫描次数。</span><span class="sxs-lookup"><span data-stu-id="74d29-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="74d29-174">使用 PowerShell cmdlet 配置跟进扫描</span><span class="sxs-lookup"><span data-stu-id="74d29-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="74d29-175">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="74d29-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="74d29-176">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)  管理 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="74d29-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="74d29-177">使用 Windows Management Instruction (WMI) 配置跟进扫描</span><span class="sxs-lookup"><span data-stu-id="74d29-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="74d29-178">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="74d29-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="74d29-179">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="74d29-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="74d29-180">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="74d29-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="74d29-181">使用 Configuration Manager 配置跟进扫描</span><span class="sxs-lookup"><span data-stu-id="74d29-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="74d29-182">在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  </span><span class="sxs-lookup"><span data-stu-id="74d29-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="74d29-183">转到计划 **扫描** 部分，如果客户端计算机脱机，则强制扫描所选扫描类型 **...** 到 **是**。</span><span class="sxs-lookup"><span data-stu-id="74d29-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="74d29-184">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74d29-184">Click **OK**.</span></span>

4.  <span data-ttu-id="74d29-185">[像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="74d29-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="74d29-186">相关文章</span><span class="sxs-lookup"><span data-stu-id="74d29-186">Related articles</span></span>

- [<span data-ttu-id="74d29-187">部署 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="74d29-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74d29-188">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="74d29-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74d29-189">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="74d29-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74d29-190">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="74d29-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74d29-191">使用虚拟机管理移动设备和虚拟机 (更新) </span><span class="sxs-lookup"><span data-stu-id="74d29-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="74d29-192">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="74d29-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)