---
title: 启用受控文件夹访问
keywords: 受控文件夹访问权限， windows 10， windows defender， 勒索软件， 保护， 文件， 文件夹， 启用， 打开， 使用
description: 了解如何通过启用受控文件夹访问权限来保护重要文件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924679"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="45abb-104">启用受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="45abb-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45abb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="45abb-105">**Applies to:**</span></span>
- [<span data-ttu-id="45abb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="45abb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="45abb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45abb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="45abb-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="45abb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45abb-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="45abb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="45abb-110">[受控文件夹访问权限](controlled-folders.md) 可帮助你保护重要数据免受恶意应用和威胁（如勒索软件）的侵害。</span><span class="sxs-lookup"><span data-stu-id="45abb-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="45abb-111">受控文件夹访问权限包含在 Windows 10 Windows Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="45abb-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="45abb-112">可以使用以下任一方法启用受控文件夹访问权限：</span><span class="sxs-lookup"><span data-stu-id="45abb-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="45abb-113">Windows 安全中心应用</span><span class="sxs-lookup"><span data-stu-id="45abb-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="45abb-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="45abb-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="45abb-115">移动设备管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="45abb-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="45abb-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="45abb-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="45abb-117">组策略</span><span class="sxs-lookup"><span data-stu-id="45abb-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="45abb-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="45abb-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="45abb-119">[审核](evaluate-controlled-folder-access.md) 模式允许你测试此功能在 (并查看) 事件，而不会影响设备的正常使用。</span><span class="sxs-lookup"><span data-stu-id="45abb-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="45abb-120">禁用本地管理员列表合并的组策略设置将覆盖受控文件夹访问权限设置。</span><span class="sxs-lookup"><span data-stu-id="45abb-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="45abb-121">它们还通过受控文件夹访问权限覆盖受保护的文件夹和允许的本地管理员设置的应用。</span><span class="sxs-lookup"><span data-stu-id="45abb-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="45abb-122">这些策略包括：</span><span class="sxs-lookup"><span data-stu-id="45abb-122">These policies include:</span></span>

* <span data-ttu-id="45abb-123">Microsoft Defender 防病毒 **配置列表的本地管理员合并行为**</span><span class="sxs-lookup"><span data-stu-id="45abb-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="45abb-124">System Center Endpoint Protection **允许用户添加排除和替代**</span><span class="sxs-lookup"><span data-stu-id="45abb-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="45abb-125">有关禁用本地列表合并的信息，请参阅阻止或 [允许用户在本地修改 Microsoft Defender AV 策略设置](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="45abb-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="45abb-126">Windows 安全中心应用</span><span class="sxs-lookup"><span data-stu-id="45abb-126">Windows Security app</span></span>

1. <span data-ttu-id="45abb-127">在任务栏Windows 安全中心防护图标，打开应用。</span><span class="sxs-lookup"><span data-stu-id="45abb-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="45abb-128">还可以搜索 Defender 的"开始" **菜单**。</span><span class="sxs-lookup"><span data-stu-id="45abb-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="45abb-129">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护图标) 然后选择勒索 **软件保护**。</span><span class="sxs-lookup"><span data-stu-id="45abb-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="45abb-130">将受控文件夹访问权限 **的开关设置为\*\*\*\*开**。</span><span class="sxs-lookup"><span data-stu-id="45abb-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="45abb-131">如果使用组策略、PowerShell 或 MDM CSP 配置受控文件夹访问权限，则设备重启后，Windows 安全中心应用中的状态将发生变化。</span><span class="sxs-lookup"><span data-stu-id="45abb-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="45abb-132">If the feature is set to **Audit mode** with any of those tools， the Windows 安全中心 app will show the state as **Off**.</span><span class="sxs-lookup"><span data-stu-id="45abb-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="45abb-133">如果要保护用户配置文件数据，我们建议用户配置文件应位于默认安装Windows驱动器上。</span><span class="sxs-lookup"><span data-stu-id="45abb-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="45abb-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="45abb-134">Endpoint Manager</span></span>

1. <span data-ttu-id="45abb-135">登录到 [安全Endpoint Manager并](https://endpoint.microsoft.com)打开 **终结点安全**。</span><span class="sxs-lookup"><span data-stu-id="45abb-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="45abb-136">转到攻击 **面减少**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="45abb-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="45abb-137">选择 **平台**，选择 **Windows 10** 和更高版本，然后选择配置文件 **攻击面减少规则**  >  **创建**。</span><span class="sxs-lookup"><span data-stu-id="45abb-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="45abb-138">命名策略并添加说明。</span><span class="sxs-lookup"><span data-stu-id="45abb-138">Name the policy and add a description.</span></span> <span data-ttu-id="45abb-139">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="45abb-139">Select **Next**.</span></span>

5.  <span data-ttu-id="45abb-140">向下滚动到底部，选择"**启用文件夹** 保护"下拉列表，然后选择"启用 **"。**</span><span class="sxs-lookup"><span data-stu-id="45abb-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="45abb-141">**选择"需要保护的其他文件夹的列表"，** 并添加需要保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="45abb-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="45abb-142">选择 **有权访问受保护文件夹的应用列表** ，并添加有权访问受保护文件夹的应用。</span><span class="sxs-lookup"><span data-stu-id="45abb-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="45abb-143">选择 **"从攻击面减少** 规则中排除文件和路径"，并添加需要从攻击面减少规则中排除的文件和路径。</span><span class="sxs-lookup"><span data-stu-id="45abb-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="45abb-144">选择配置文件 **分配**，分配到所有用户 **&所有设备，\*\*\*\*然后选择保存。**</span><span class="sxs-lookup"><span data-stu-id="45abb-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="45abb-145">选择 **"下一** 步"保存每个打开的边栏选项卡，然后选择"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="45abb-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="45abb-146">应用程序支持通配符，但文件夹不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="45abb-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="45abb-147">子文件夹不受保护。</span><span class="sxs-lookup"><span data-stu-id="45abb-147">Subfolders are not protected.</span></span> <span data-ttu-id="45abb-148">允许的应用将继续触发事件，直到它们重新启动。</span><span class="sxs-lookup"><span data-stu-id="45abb-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="45abb-149">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="45abb-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="45abb-150">使用 [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。</span><span class="sxs-lookup"><span data-stu-id="45abb-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="45abb-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="45abb-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="45abb-152">In Microsoft Endpoint Configuration Manager， go to **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="45abb-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="45abb-153">选择 **"主页**  >  **创建攻击防护策略"。**</span><span class="sxs-lookup"><span data-stu-id="45abb-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="45abb-154">输入名称和说明，选择受控 **文件夹访问权限**，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="45abb-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="45abb-155">选择是阻止更改还是审核更改、允许其他应用或添加其他文件夹，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="45abb-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="45abb-156">应用程序支持 Wilcard，但文件夹不支持。</span><span class="sxs-lookup"><span data-stu-id="45abb-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="45abb-157">子文件夹不受保护。</span><span class="sxs-lookup"><span data-stu-id="45abb-157">Subfolders are not protected.</span></span> <span data-ttu-id="45abb-158">允许的应用将继续触发事件，直到它们重新启动。</span><span class="sxs-lookup"><span data-stu-id="45abb-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="45abb-159">查看设置，然后选择" **下一** 步"以创建策略。</span><span class="sxs-lookup"><span data-stu-id="45abb-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="45abb-160">创建策略后 **，关闭**。</span><span class="sxs-lookup"><span data-stu-id="45abb-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="45abb-161">组策略</span><span class="sxs-lookup"><span data-stu-id="45abb-161">Group Policy</span></span>

1. <span data-ttu-id="45abb-162">在组策略管理设备上，打开组 [策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="45abb-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="45abb-163">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="45abb-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="45abb-164">展开树以 **Windows攻击> Microsoft Defender 防病毒 > Windows Defender受控>访问权限的组件**。</span><span class="sxs-lookup"><span data-stu-id="45abb-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="45abb-165">双击配置受控文件夹 **访问权限** 设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="45abb-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="45abb-166">在选项部分中，必须指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="45abb-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="45abb-167">**启用** - 不允许恶意和可疑应用对受保护文件夹中的文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="45abb-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="45abb-168">将在事件日志中提供Windows通知。</span><span class="sxs-lookup"><span data-stu-id="45abb-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="45abb-169">**禁用 (默认)** - 受控文件夹访问权限功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="45abb-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="45abb-170">所有应用都可以对受保护的文件夹中的文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="45abb-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="45abb-171">**审核模式** - 如果恶意或可疑应用尝试更改受保护文件夹中的文件，将允许更改。</span><span class="sxs-lookup"><span data-stu-id="45abb-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="45abb-172">但是，它将记录在事件Windows日志中，您可以在其中评估对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="45abb-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="45abb-173">**仅阻止磁盘修改**- 不受信任的应用尝试写入磁盘扇区将记录在Windows日志中。</span><span class="sxs-lookup"><span data-stu-id="45abb-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="45abb-174">可以在 Microsoft > Operational **> Windows > Windows Defender >** Id 1123 的应用程序>日志中找到这些日志。</span><span class="sxs-lookup"><span data-stu-id="45abb-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="45abb-175">**仅** 审核磁盘修改 - 仅在应用程序和服务日志Microsoft Windows Windows Defender Operational ID  >    >    >    >    >  **1124**) 下的 Windows (事件日志中记录写入受保护磁盘扇区的尝试。</span><span class="sxs-lookup"><span data-stu-id="45abb-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="45abb-176">不会记录修改或删除受保护文件夹中的文件的尝试。</span><span class="sxs-lookup"><span data-stu-id="45abb-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![在下拉列表中选中的组策略选项"启用"和"审核模式"的屏幕截图](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="45abb-178">若要完全启用受控文件夹访问权限，必须将组策略选项设置为 **已启用**，然后选择选项下拉菜单中的阻止。</span><span class="sxs-lookup"><span data-stu-id="45abb-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="45abb-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="45abb-179">PowerShell</span></span>

1. <span data-ttu-id="45abb-180">在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="45abb-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="45abb-181">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="45abb-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="45abb-182">可以通过指定 （而不是 ）在审核模式下 `AuditMode` 启用该功能 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="45abb-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="45abb-183">用于 `Disabled` 关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="45abb-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="45abb-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45abb-184">See also</span></span>

* [<span data-ttu-id="45abb-185">使用受控文件夹访问权限保护重要文件夹</span><span class="sxs-lookup"><span data-stu-id="45abb-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="45abb-186">自定义受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="45abb-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="45abb-187">评估 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="45abb-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
