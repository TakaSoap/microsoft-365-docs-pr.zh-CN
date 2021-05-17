---
title: 启用受控文件夹访问
keywords: 受控文件夹访问权限， windows 10， windows defender， 勒索软件， 保护， 文件， 文件夹， 启用， 打开， 使用
description: 了解如何通过启用受控文件夹访问权限来保护重要文件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: ee87ac3bdfe88596a5f1625904af53499488f35f
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571004"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="ac06f-104">启用受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="ac06f-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ac06f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ac06f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac06f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac06f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ac06f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac06f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ac06f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ac06f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ac06f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ac06f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ac06f-110">[受控文件夹访问权限](controlled-folders.md) 可帮助你保护重要数据免受恶意应用和威胁（如勒索软件）的侵害。</span><span class="sxs-lookup"><span data-stu-id="ac06f-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="ac06f-111">受控文件夹访问权限包含在 Windows 10 Windows Server 2019 中。</span><span class="sxs-lookup"><span data-stu-id="ac06f-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="ac06f-112">可以使用以下任一方法启用受控文件夹访问权限：</span><span class="sxs-lookup"><span data-stu-id="ac06f-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="ac06f-113">Windows 安全中心应用</span><span class="sxs-lookup"><span data-stu-id="ac06f-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="ac06f-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ac06f-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="ac06f-115">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="ac06f-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="ac06f-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ac06f-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="ac06f-117">组策略</span><span class="sxs-lookup"><span data-stu-id="ac06f-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="ac06f-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac06f-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="ac06f-119">[审核](evaluate-controlled-folder-access.md) 模式允许你测试此功能在 (并查看) 事件，而不会影响设备的正常使用。</span><span class="sxs-lookup"><span data-stu-id="ac06f-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="ac06f-120">禁用本地管理员列表合并的组策略设置将覆盖受控文件夹访问权限设置。</span><span class="sxs-lookup"><span data-stu-id="ac06f-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="ac06f-121">它们还通过受控文件夹访问权限覆盖受保护的文件夹和允许的本地管理员设置的应用。</span><span class="sxs-lookup"><span data-stu-id="ac06f-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="ac06f-122">这些策略包括：</span><span class="sxs-lookup"><span data-stu-id="ac06f-122">These policies include:</span></span>

* <span data-ttu-id="ac06f-123">Microsoft Defender 防病毒 **配置列表的本地管理员合并行为**</span><span class="sxs-lookup"><span data-stu-id="ac06f-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="ac06f-124">System Center Endpoint Protection **允许用户添加排除和替代**</span><span class="sxs-lookup"><span data-stu-id="ac06f-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="ac06f-125">有关禁用本地列表合并的信息，请参阅阻止或 [允许用户在本地修改 Microsoft Defender AV 策略设置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)。</span><span class="sxs-lookup"><span data-stu-id="ac06f-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="ac06f-126">Windows 安全中心应用</span><span class="sxs-lookup"><span data-stu-id="ac06f-126">Windows Security app</span></span>

1. <span data-ttu-id="ac06f-127">在任务栏Windows 安全中心防护图标，打开应用。</span><span class="sxs-lookup"><span data-stu-id="ac06f-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="ac06f-128">还可以搜索 Defender 的"开始" **菜单**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="ac06f-129">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护图标) 然后选择勒索 **软件保护**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="ac06f-130">将受控文件夹访问权限 **的开关设置为\*\*\*\*开**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="ac06f-131">如果使用组策略、PowerShell 或 MDM CSP 配置受控文件夹访问权限，则设备重启后，Windows 安全中心应用中的状态将发生变化。</span><span class="sxs-lookup"><span data-stu-id="ac06f-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="ac06f-132">If the feature is set to **Audit mode** with any of those tools， the Windows 安全中心 app will show the state as **Off**.</span><span class="sxs-lookup"><span data-stu-id="ac06f-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="ac06f-133">如果要保护用户配置文件数据，我们建议用户配置文件应位于默认安装Windows驱动器上。</span><span class="sxs-lookup"><span data-stu-id="ac06f-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="ac06f-134">Intune</span><span class="sxs-lookup"><span data-stu-id="ac06f-134">Intune</span></span>

1. <span data-ttu-id="ac06f-135">登录到 Azure 门户 [并打开](https://portal.azure.com) Intune。</span><span class="sxs-lookup"><span data-stu-id="ac06f-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="ac06f-136">转到设备 **配置文件**  >  **创建**  >  **配置文件**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="ac06f-137">命名配置文件，选择 **"Windows 10及更高版本"和**"**终结点保护"。**</span><span class="sxs-lookup"><span data-stu-id="ac06f-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="ac06f-138">![创建终结点保护配置文件](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="ac06f-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="ac06f-139">转到配置 **Windows Defender**  >  **攻击防护**  >  **受控文件夹访问权限**  >  **启用**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="ac06f-140">键入每个有权访问受保护文件夹的应用程序的路径，以及需要保护的其他任何文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="ac06f-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="ac06f-141">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="ac06f-141">Select **Add**.</span></span><br/> <span data-ttu-id="ac06f-142">![在 Intune 中启用受控文件夹访问权限](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="ac06f-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="ac06f-143">应用程序支持 Wilcard，但文件夹不支持。</span><span class="sxs-lookup"><span data-stu-id="ac06f-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="ac06f-144">子文件夹不受保护。</span><span class="sxs-lookup"><span data-stu-id="ac06f-144">Subfolders are not protected.</span></span> <span data-ttu-id="ac06f-145">允许的应用将继续触发事件，直到它们重新启动。</span><span class="sxs-lookup"><span data-stu-id="ac06f-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="ac06f-146">选择 **确定** 以保存每个打开的边栏选项卡和 **创建**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="ac06f-147">选择配置文件 **分配**、分配给所有用户 **&所有设备"** 和"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="ac06f-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="ac06f-148">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="ac06f-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="ac06f-149">使用 [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。</span><span class="sxs-lookup"><span data-stu-id="ac06f-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ac06f-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ac06f-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="ac06f-151">In Microsoft Endpoint Configuration Manager， go to **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="ac06f-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="ac06f-152">选择 **"主页**  >  **创建攻击防护策略"。**</span><span class="sxs-lookup"><span data-stu-id="ac06f-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="ac06f-153">输入名称和说明，选择受控 **文件夹访问权限**，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="ac06f-154">选择是阻止更改还是审核更改、允许其他应用或添加其他文件夹，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="ac06f-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ac06f-155">应用程序支持 Wilcard，但文件夹不支持。</span><span class="sxs-lookup"><span data-stu-id="ac06f-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="ac06f-156">子文件夹不受保护。</span><span class="sxs-lookup"><span data-stu-id="ac06f-156">Subfolders are not protected.</span></span> <span data-ttu-id="ac06f-157">允许的应用将继续触发事件，直到它们重新启动。</span><span class="sxs-lookup"><span data-stu-id="ac06f-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="ac06f-158">查看设置，然后选择" **下一** 步"以创建策略。</span><span class="sxs-lookup"><span data-stu-id="ac06f-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="ac06f-159">创建策略后 **，关闭**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="ac06f-160">组策略</span><span class="sxs-lookup"><span data-stu-id="ac06f-160">Group Policy</span></span>

1. <span data-ttu-id="ac06f-161">在组策略管理设备上，打开组 [策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="ac06f-162">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="ac06f-163">展开树以 **Windows攻击> Microsoft Defender 防病毒 > Windows Defender受控>访问权限的组件**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="ac06f-164">双击配置受控文件夹 **访问权限** 设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="ac06f-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="ac06f-165">在选项部分中，必须指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ac06f-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="ac06f-166">**启用** - 不允许恶意和可疑应用对受保护文件夹中的文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="ac06f-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="ac06f-167">将在事件日志中提供Windows通知。</span><span class="sxs-lookup"><span data-stu-id="ac06f-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="ac06f-168">**禁用 (默认)** - 受控文件夹访问权限功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ac06f-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="ac06f-169">所有应用都可以对受保护的文件夹中的文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="ac06f-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="ac06f-170">**审核模式** - 如果恶意或可疑应用尝试更改受保护文件夹中的文件，将允许更改。</span><span class="sxs-lookup"><span data-stu-id="ac06f-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="ac06f-171">但是，它将记录在事件Windows日志中，您可以在其中评估对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="ac06f-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="ac06f-172">**仅阻止磁盘修改**- 不受信任的应用尝试写入磁盘扇区将记录在Windows日志中。</span><span class="sxs-lookup"><span data-stu-id="ac06f-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="ac06f-173">可以在 Microsoft > Operational **> Windows > Windows Defender >** Id 1123 的应用程序>日志中找到这些日志。</span><span class="sxs-lookup"><span data-stu-id="ac06f-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="ac06f-174">**仅** 审核磁盘修改 - 仅在应用程序和服务日志Microsoft Windows Windows Defender Operational ID  >    >    >    >    >  **1124**) 下的 Windows (事件日志中记录写入受保护磁盘扇区的尝试。</span><span class="sxs-lookup"><span data-stu-id="ac06f-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="ac06f-175">不会记录修改或删除受保护文件夹中的文件的尝试。</span><span class="sxs-lookup"><span data-stu-id="ac06f-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![在下拉列表中选中的组策略选项"启用"和"审核模式"的屏幕截图](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="ac06f-177">若要完全启用受控文件夹访问权限，必须将组策略选项设置为 **已启用**，然后选择选项下拉菜单中的阻止。</span><span class="sxs-lookup"><span data-stu-id="ac06f-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="ac06f-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac06f-178">PowerShell</span></span>

1. <span data-ttu-id="ac06f-179">在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="ac06f-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="ac06f-180">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ac06f-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="ac06f-181">可以通过指定 （而不是 ）在审核模式下 `AuditMode` 启用该功能 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="ac06f-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="ac06f-182">用于 `Disabled` 关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="ac06f-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac06f-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac06f-183">See also</span></span>

* [<span data-ttu-id="ac06f-184">使用受控文件夹访问权限保护重要文件夹</span><span class="sxs-lookup"><span data-stu-id="ac06f-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="ac06f-185">自定义受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="ac06f-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="ac06f-186">评估 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac06f-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
