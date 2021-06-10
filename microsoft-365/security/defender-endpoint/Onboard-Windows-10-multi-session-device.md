---
title: 在 Windows 虚拟桌面中载入 Windows 10 多会话设备
description: 阅读本文中有关在虚拟桌面Windows 10多会话设备载入Windows内容
keywords: Windows虚拟桌面， WVD， microsoft defender， 终结点， 载入
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 5bf9f856e93ae1424373a917490a264c04e07feb
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861175"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="223cd-104">在 Windows 虚拟桌面中载入 Windows 10 多会话设备</span><span class="sxs-lookup"><span data-stu-id="223cd-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="223cd-105">6 分钟阅读</span><span class="sxs-lookup"><span data-stu-id="223cd-105">6 minutes to read</span></span> 

<span data-ttu-id="223cd-106">应用于：</span><span class="sxs-lookup"><span data-stu-id="223cd-106">Applies to:</span></span> 
- <span data-ttu-id="223cd-107">Windows 10虚拟桌面 Windows WVD (上运行的多) </span><span class="sxs-lookup"><span data-stu-id="223cd-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="223cd-108">Microsoft Defender for Endpoint 支持监视 VDI Windows虚拟桌面会话。</span><span class="sxs-lookup"><span data-stu-id="223cd-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="223cd-109">根据组织的需求，你可能需要实现 VDI 或 Windows 虚拟桌面会话，以帮助你的员工从非托管设备、远程位置或类似方案访问公司数据和应用。</span><span class="sxs-lookup"><span data-stu-id="223cd-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="223cd-110">通过 Microsoft Defender for Endpoint，你可以监视这些虚拟机的异常活动。</span><span class="sxs-lookup"><span data-stu-id="223cd-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="223cd-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="223cd-111">Before you begin</span></span>
<span data-ttu-id="223cd-112">熟悉非永久性 [VDI 的注意事项](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="223cd-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="223cd-113">尽管[Windows](/azure/virtual-desktop/overview)桌面不提供非持久性选项，但它确实提供了使用黄金 Windows 映像的方法，该映像可用于预配新主机和重新部署计算机。</span><span class="sxs-lookup"><span data-stu-id="223cd-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="223cd-114">这会增加环境中的变化，从而影响在 Microsoft Defender 终结点门户中创建和维护的条目，从而可能降低安全分析师的可见性。</span><span class="sxs-lookup"><span data-stu-id="223cd-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="223cd-115">根据你选择的载入方法，设备可以在 Microsoft Defender for Endpoint 门户中显示为：</span><span class="sxs-lookup"><span data-stu-id="223cd-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="223cd-116">每个虚拟桌面的单个条目</span><span class="sxs-lookup"><span data-stu-id="223cd-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="223cd-117">每个虚拟桌面的多个条目</span><span class="sxs-lookup"><span data-stu-id="223cd-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="223cd-118">Microsoft 建议将虚拟Windows虚拟桌面作为每个虚拟桌面的单个条目载入。</span><span class="sxs-lookup"><span data-stu-id="223cd-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="223cd-119">这可确保 Microsoft Defender 终结点门户中的调查体验基于计算机名称在一台设备的上下文中。</span><span class="sxs-lookup"><span data-stu-id="223cd-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="223cd-120">经常删除和重新部署 WVD 主机的组织应强烈建议使用此方法，因为它会阻止在 Microsoft Defender for Endpoint 门户中创建同一台计算机的多个对象。</span><span class="sxs-lookup"><span data-stu-id="223cd-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="223cd-121">这可能会导致调查事件时混淆。</span><span class="sxs-lookup"><span data-stu-id="223cd-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="223cd-122">对于测试或非可变环境，你可以选择不同的选择。</span><span class="sxs-lookup"><span data-stu-id="223cd-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="223cd-123">Microsoft 建议将 Microsoft Defender for Endpoint 载入脚本添加到 WVD 黄金映像。</span><span class="sxs-lookup"><span data-stu-id="223cd-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="223cd-124">这样，你可以确保此载入脚本在首次启动时立即运行。</span><span class="sxs-lookup"><span data-stu-id="223cd-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="223cd-125">它作为启动脚本在首次启动时在从 WVD 黄金映像预配的所有 WVD 计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="223cd-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="223cd-126">但是，如果使用的库图像之一未经修改，则将脚本放在共享位置，然后从本地或域组策略调用它。</span><span class="sxs-lookup"><span data-stu-id="223cd-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="223cd-127">WVD 黄金映像上的 VDI 载入启动脚本的位置和配置会将其配置为在 WVD 启动时运行的启动脚本。</span><span class="sxs-lookup"><span data-stu-id="223cd-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="223cd-128">不建议载入实际的 WVD 黄金映像。</span><span class="sxs-lookup"><span data-stu-id="223cd-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="223cd-129">另一个注意事项是用于运行脚本的方法。</span><span class="sxs-lookup"><span data-stu-id="223cd-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="223cd-130">它应尽早在启动/预配过程中运行，以减少计算机可用于接收会话和设备载入到服务之间的时间。</span><span class="sxs-lookup"><span data-stu-id="223cd-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="223cd-131">在方案 1 & 2 中考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="223cd-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="223cd-132">应用场景</span><span class="sxs-lookup"><span data-stu-id="223cd-132">Scenarios</span></span>
<span data-ttu-id="223cd-133">有几种方法可以载入 WVD 主机：</span><span class="sxs-lookup"><span data-stu-id="223cd-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="223cd-134">在黄金映像中运行脚本 (在启动期间从共享) 运行脚本。</span><span class="sxs-lookup"><span data-stu-id="223cd-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="223cd-135">使用管理工具运行脚本。</span><span class="sxs-lookup"><span data-stu-id="223cd-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="223cd-136">*方案 1：使用本地组策略*</span><span class="sxs-lookup"><span data-stu-id="223cd-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="223cd-137">此方案要求将脚本放置在黄金映像中，并使用本地组策略在启动过程早期运行。</span><span class="sxs-lookup"><span data-stu-id="223cd-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="223cd-138">按照载入非 [永久性虚拟桌面基础结构 VDI 设备 中的说明操作](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="223cd-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="223cd-139">按照每个设备的单个条目的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="223cd-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="223cd-140">*方案 2：使用域组策略*</span><span class="sxs-lookup"><span data-stu-id="223cd-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="223cd-141">此方案使用位于中央的脚本并使用基于域的组策略运行它。</span><span class="sxs-lookup"><span data-stu-id="223cd-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="223cd-142">还可以将脚本放在黄金映像中，并使用相同的方式运行它。</span><span class="sxs-lookup"><span data-stu-id="223cd-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="223cd-143">**从 WindowsDefenderATPOnboardingPackage.zip 安全中心Windows Defender文件**</span><span class="sxs-lookup"><span data-stu-id="223cd-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="223cd-144">打开 VDI 配置包.zip文件 (WindowsDefenderATPOnboardingPackage.zip) </span><span class="sxs-lookup"><span data-stu-id="223cd-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="223cd-145">在"Microsoft Defender 安全中心窗格中，选择 **"设置**  >  **载入"。**</span><span class="sxs-lookup"><span data-stu-id="223cd-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="223cd-146">选择Windows 10操作系统。</span><span class="sxs-lookup"><span data-stu-id="223cd-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="223cd-147">在" **部署方法"** 字段中，选择"非永久性终结点的 VDI 载入脚本"。</span><span class="sxs-lookup"><span data-stu-id="223cd-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="223cd-148">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="223cd-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="223cd-149">将文件内容.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="223cd-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="223cd-150">你应该有一个名为 **OptionalParamsPolicy** 的文件夹以及 **WindowsDefenderATPOnboardingScript.cmd** 和 **Onboard-NonPersistentMachine.ps1**。</span><span class="sxs-lookup"><span data-stu-id="223cd-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="223cd-151">**当虚拟机启动时，使用组策略管理控制台运行脚本**</span><span class="sxs-lookup"><span data-stu-id="223cd-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="223cd-152">打开组策略管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**</span><span class="sxs-lookup"><span data-stu-id="223cd-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="223cd-153">在组策略管理编辑器中，转到计算机 **配置** \> **首选项** \> **控制面板设置**。</span><span class="sxs-lookup"><span data-stu-id="223cd-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="223cd-154">右键单击 **计划任务**，单击 **新建**，**然后单击立即任务** (至少Windows 7) 。</span><span class="sxs-lookup"><span data-stu-id="223cd-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="223cd-155">在打开的任务窗口中，转到常规 **选项卡** 。在" **安全选项"** 下 **，单击"更改用户或组"** 并键入 SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="223cd-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="223cd-156">单击 **"检查名称"，** 然后单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="223cd-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="223cd-157">NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="223cd-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="223cd-158">Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.</span><span class="sxs-lookup"><span data-stu-id="223cd-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="223cd-159">转到"操作 **"选项卡**，然后单击"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="223cd-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="223cd-160">确保在 **"操作"** 字段中选择了"启动程序"。</span><span class="sxs-lookup"><span data-stu-id="223cd-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="223cd-161">输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="223cd-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="223cd-162">然后选择" **确定"** 并关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="223cd-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="223cd-163">*方案 3：使用管理工具载入*</span><span class="sxs-lookup"><span data-stu-id="223cd-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="223cd-164">如果你计划使用管理工具管理计算机，可以使用 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="223cd-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="223cd-165">有关详细信息，请参阅使用配置[Windows 10载入设备](configure-endpoints-sccm.md)。</span><span class="sxs-lookup"><span data-stu-id="223cd-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="223cd-166">如果你计划使用攻击面[](attack-surface-reduction.md)减少规则，请注意，不应使用规则"阻止源自[PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)和 WMI 命令的进程创建"，因为该规则与通过 Microsoft Endpoint Configuration Manager 管理不兼容。</span><span class="sxs-lookup"><span data-stu-id="223cd-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="223cd-167">该规则阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="223cd-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="223cd-168">载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="223cd-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="223cd-169">有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="223cd-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="223cd-170">生成黄金映像时标记计算机</span><span class="sxs-lookup"><span data-stu-id="223cd-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="223cd-171">作为载入的一部分，你可能要考虑设置计算机标记，以在 Microsoft 安全中心更轻松地区分 WVD 计算机。</span><span class="sxs-lookup"><span data-stu-id="223cd-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="223cd-172">有关详细信息，请参阅通过 [设置注册表项值添加设备标记](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="223cd-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="223cd-173">其他建议的配置设置</span><span class="sxs-lookup"><span data-stu-id="223cd-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="223cd-174">生成黄金映像时，你可能还想要配置初始保护设置。</span><span class="sxs-lookup"><span data-stu-id="223cd-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="223cd-175">有关详细信息，请参阅其他 [推荐的配置设置](configure-endpoints-gp.md#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="223cd-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="223cd-176">此外，如果您使用的是 FSlogix 用户配置文件，我们建议您从始终打开的保护中排除以下文件：</span><span class="sxs-lookup"><span data-stu-id="223cd-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="223cd-177">**排除文件：**</span><span class="sxs-lookup"><span data-stu-id="223cd-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="223cd-178">**排除进程：**</span><span class="sxs-lookup"><span data-stu-id="223cd-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="223cd-179">许可要求</span><span class="sxs-lookup"><span data-stu-id="223cd-179">Licensing requirements</span></span> 

<span data-ttu-id="223cd-180">许可注意事项：使用 Windows 10 企业版 多会话时，根据你的要求，你可以选择让所有用户通过 Microsoft Defender 针对终结点 (（针对每个用户) 、Windows Enterprise E5、Microsoft 365 安全或 Microsoft 365 E5）获得许可，或者通过 Azure Defender 许可 VM。</span><span class="sxs-lookup"><span data-stu-id="223cd-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="223cd-181">有关 Microsoft Defender 终结点的许可要求，可位于： [许可要求](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="223cd-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

#### <a name="related-links"></a><span data-ttu-id="223cd-182">相关链接</span><span class="sxs-lookup"><span data-stu-id="223cd-182">Related Links</span></span>

[<span data-ttu-id="223cd-183">使用 PowerShell 添加 Microsoft Defender 排除项</span><span class="sxs-lookup"><span data-stu-id="223cd-183">Add exclusions for Microsoft Defender by using PowerShell</span></span>](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
