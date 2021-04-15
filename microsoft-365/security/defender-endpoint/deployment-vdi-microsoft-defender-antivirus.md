---
title: Microsoft Defender 防病毒虚拟桌面基础结构部署指南
description: 了解如何在虚拟桌面环境中部署 Microsoft Defender 防病毒，以在保护和性能之间实现最佳平衡。
keywords: vdi， hyper-v， vm， 虚拟机， windows defender， 防病毒， av， 虚拟桌面， rds， 远程桌面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: fed66586dc0607989e407ecd790d2af8c40e2939
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765727"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="0ae15-104">虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南</span><span class="sxs-lookup"><span data-stu-id="0ae15-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0ae15-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0ae15-105">**Applies to:**</span></span>

- [<span data-ttu-id="0ae15-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ae15-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0ae15-107">除了标准本地配置或硬件配置之外，还可以在远程桌面 (RDS) 或虚拟桌面基础结构 (VDI) 使用 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="0ae15-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="0ae15-108">有关 [Microsoft 远程桌面](/azure/virtual-desktop) 服务和 VDI 支持的更多详细信息，请参阅 Windows 虚拟桌面文档。</span><span class="sxs-lookup"><span data-stu-id="0ae15-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="0ae15-109">有关基于 Azure 的虚拟机，请参阅[在 Azure Defender 中安装 Endpoint Protection。](/azure/security-center/security-center-install-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="0ae15-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="0ae15-110">由于能够轻松地将更新部署到在 VDIs 中运行的 VM，我们缩短了本指南，侧重于如何快速轻松地获取计算机更新。</span><span class="sxs-lookup"><span data-stu-id="0ae15-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="0ae15-111">你不再需要定期创建和密封黄金映像，因为更新会扩展到主机服务器上其组件位，然后在虚拟机打开时直接下载到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="0ae15-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="0ae15-112">本指南介绍如何配置 VM 以实现最佳保护和性能，包括如何：</span><span class="sxs-lookup"><span data-stu-id="0ae15-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="0ae15-113">为安全智能更新设置专用的 VDI 文件共享</span><span class="sxs-lookup"><span data-stu-id="0ae15-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="0ae15-114">随机化计划扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="0ae15-115">使用快速扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="0ae15-116">阻止通知</span><span class="sxs-lookup"><span data-stu-id="0ae15-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="0ae15-117">禁止每次更新后执行扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="0ae15-118">扫描过期的计算机或已脱机一段时间的计算机</span><span class="sxs-lookup"><span data-stu-id="0ae15-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="0ae15-119">应用排除项</span><span class="sxs-lookup"><span data-stu-id="0ae15-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="0ae15-120">还可以下载虚拟桌面基础结构上的白皮书 [Microsoft Defender 防病毒](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)，该白皮书将查看新的共享安全智能更新功能，以及性能测试和有关如何在你自己的 VDI 上测试防病毒性能的指导。</span><span class="sxs-lookup"><span data-stu-id="0ae15-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ae15-121">尽管 VDI 可以托管在 Windows Server 2012 或 Windows Server 2016 上，但由于保护技术和功能在早期版本的 Windows 中不可用，虚拟机 (VM) 至少应运行 Windows 10 1607。</span><span class="sxs-lookup"><span data-stu-id="0ae15-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="0ae15-122">Microsoft Defender AV 在 Windows 10 Insider Preview 版本 18323 版本 18323 (及更高版本中的虚拟机上的操作方式有一些性能和) 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="0ae15-123">如果你需要使用 Insider Preview 版本，我们将在本指南中确定;如果未指定，则获得最佳保护和性能的最低必需版本为 Windows 10 1607。</span><span class="sxs-lookup"><span data-stu-id="0ae15-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="0ae15-124">设置专用的 VDI 文件共享</span><span class="sxs-lookup"><span data-stu-id="0ae15-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="0ae15-125">在 Windows 10 版本 1903 中，我们引入了共享安全智能功能，该功能将下载的安全智能更新的解包卸载到主机上，从而节省各个计算机上以前的 CPU、磁盘和内存资源。</span><span class="sxs-lookup"><span data-stu-id="0ae15-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="0ae15-126">此功能已被备份，现在适用于 Windows 10 版本 1703 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="0ae15-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="0ae15-127">可以使用组策略或 PowerShell 设置此功能。</span><span class="sxs-lookup"><span data-stu-id="0ae15-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="0ae15-128">使用组策略启用共享安全智能功能：</span><span class="sxs-lookup"><span data-stu-id="0ae15-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="0ae15-129">在组策略管理计算机上，打开组策略管理控制台，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="0ae15-130">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0ae15-131">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="0ae15-132">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="0ae15-133">双击定义 **VDI 客户端的安全智能** 位置，然后将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="0ae15-134">将自动显示一个字段。</span><span class="sxs-lookup"><span data-stu-id="0ae15-134">A field automatically appears.</span></span>

6. <span data-ttu-id="0ae15-135">输入 `\\<sharedlocation\>\wdav-update` (此值的帮助，请参阅下载[并解压缩) 。](#download-and-unpackage-the-latest-updates)</span><span class="sxs-lookup"><span data-stu-id="0ae15-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="0ae15-136">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-136">Click **OK**.</span></span>

8. <span data-ttu-id="0ae15-137">将 GPO 部署到要测试的 VM。</span><span class="sxs-lookup"><span data-stu-id="0ae15-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="0ae15-138">使用 PowerShell 启用共享安全智能功能</span><span class="sxs-lookup"><span data-stu-id="0ae15-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="0ae15-139">使用以下 cmdlet 启用该功能。</span><span class="sxs-lookup"><span data-stu-id="0ae15-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="0ae15-140">然后，你需要按通常将基于 PowerShell 的配置策略推送到 VM 中那样进行推送：</span><span class="sxs-lookup"><span data-stu-id="0ae15-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="0ae15-141">请参阅 [下载和解包部分](#download-and-unpackage-the-latest-updates) ，了解 \<shared location\> 将是什么。</span><span class="sxs-lookup"><span data-stu-id="0ae15-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="0ae15-142">下载最新更新并解压缩</span><span class="sxs-lookup"><span data-stu-id="0ae15-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="0ae15-143">现在，你可以开始下载和安装新更新。</span><span class="sxs-lookup"><span data-stu-id="0ae15-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="0ae15-144">我们在下面创建了一个示例 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="0ae15-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="0ae15-145">此脚本是下载新更新并使它们为 VM 做好准备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="0ae15-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="0ae15-146">然后，你应该使用计划任务 (将脚本设置为在特定时间在管理计算机上运行，或者如果你熟悉在 Azure、Intune 或 SCCM 中使用 PowerShell 脚本，则还可以使用这些脚本) 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="0ae15-147">你可以将计划任务设置为每天运行一次，以便只要下载包并解压缩，VM 就会收到新更新。</span><span class="sxs-lookup"><span data-stu-id="0ae15-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="0ae15-148">我们建议从每天一次开始，但应尝试增加或降低频率以了解影响。</span><span class="sxs-lookup"><span data-stu-id="0ae15-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="0ae15-149">安全智能包通常每三到四小时发布一次。</span><span class="sxs-lookup"><span data-stu-id="0ae15-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="0ae15-150">建议不要设置小于 4 小时的频率，因为这会增加管理计算机上网络开销，而没有任何好处。</span><span class="sxs-lookup"><span data-stu-id="0ae15-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="0ae15-151">设置计划任务以运行 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="0ae15-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="0ae15-152">在管理计算机上，打开"开始"菜单并键入 **"任务计划程序"。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="0ae15-153">打开它，然后选择 **创建任务...**</span><span class="sxs-lookup"><span data-stu-id="0ae15-153">Open it and select **Create task…**</span></span> <span data-ttu-id="0ae15-154">位于侧面板上。</span><span class="sxs-lookup"><span data-stu-id="0ae15-154">on the side panel.</span></span>

2. <span data-ttu-id="0ae15-155">输入名称作为 **安全智能解压缩。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="0ae15-156">转到"触发器 **"** 选项卡。选择 **"新建..."。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="0ae15-157"> > **每天**，然后选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="0ae15-158">转到" **操作"** 选项卡。选择 **"新建..."。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="0ae15-159">在"程序/脚本 **"字段中输入** **PowerShell。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="0ae15-160">在 `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` "添加 **参数"字段中** 输入。</span><span class="sxs-lookup"><span data-stu-id="0ae15-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="0ae15-161">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-161">Select **OK**.</span></span>

4. <span data-ttu-id="0ae15-162">如果需要，可以选择配置其他设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="0ae15-163">选择 **"** 确定"保存计划任务。</span><span class="sxs-lookup"><span data-stu-id="0ae15-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="0ae15-164">可以通过右键单击任务并单击"运行"来手动启动 **更新**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="0ae15-165">手动下载并解压缩</span><span class="sxs-lookup"><span data-stu-id="0ae15-165">Download and unpackage manually</span></span>

<span data-ttu-id="0ae15-166">如果您希望手动执行所有操作，下面是复制脚本行为要执行哪些操作：</span><span class="sxs-lookup"><span data-stu-id="0ae15-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="0ae15-167">在系统根目录上新建一个文件夹 `wdav_update` ，以存储智能更新，例如，创建文件夹 `c:\wdav_update` 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="0ae15-168">使用 GUID 名称 *wdav_update文件夹* 下创建子文件夹，例如 `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="0ae15-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="0ae15-169">下面是一个示例： `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="0ae15-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ae15-170">在脚本中，我们设置它，以便 GUID 的最后 12 个数字是下载文件时的年、月、日以及时间，以便每次创建一个新文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ae15-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="0ae15-171">您可以更改此设置，以便每次将文件下载到同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ae15-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="0ae15-172">将安全智能包从 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  下载到 GUID 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ae15-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="0ae15-173">该文件应命名为 `mpam-fe.exe` 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="0ae15-174">打开 cmd 提示符窗口并导航到您创建的 GUID 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ae15-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="0ae15-175">使用 **/X** 提取命令提取文件，例如 `mpam-fe.exe /X` 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ae15-176">每当使用提取的更新包创建一个新的 GUID 文件夹，或者每当使用新的已提取包更新现有文件夹时，VM 都会选取更新的包。</span><span class="sxs-lookup"><span data-stu-id="0ae15-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="0ae15-177">随机化计划扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-177">Randomize scheduled scans</span></span>

<span data-ttu-id="0ae15-178">除了实时保护和扫描之外，计划的 [扫描也运行](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae15-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="0ae15-179">扫描本身的开始时间仍基于计划扫描策略 (**ScheduleDay、ScheduleTime** 和 **ScheduleQuickScanTime**) 。 </span><span class="sxs-lookup"><span data-stu-id="0ae15-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="0ae15-180">随机化将导致 Microsoft Defender 防病毒从为计划扫描设置的时间起，在 4 小时时段内在每台计算机中启动扫描。</span><span class="sxs-lookup"><span data-stu-id="0ae15-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="0ae15-181">有关 [可用于计划](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 扫描的其他配置选项，请参阅计划扫描。</span><span class="sxs-lookup"><span data-stu-id="0ae15-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="0ae15-182">使用快速扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-182">Use quick scans</span></span>

<span data-ttu-id="0ae15-183">可以指定在计划扫描期间应执行的扫描类型。</span><span class="sxs-lookup"><span data-stu-id="0ae15-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="0ae15-184">快速扫描是首选方法，因为它们旨在查找恶意软件需要驻留的所有位置以处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0ae15-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="0ae15-185">以下过程介绍如何使用组策略设置快速扫描。</span><span class="sxs-lookup"><span data-stu-id="0ae15-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="0ae15-186">在组策略编辑器中，转到管理 **模板**  >  **Windows 组件** Microsoft Defender  >  **防病毒**  >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="0ae15-187">选择 **"指定要用于计划扫描** 的扫描类型"，然后编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="0ae15-188">将策略设置为 **"已启用"，** 然后在"选项"**下**，选择 **"快速扫描"。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="0ae15-189">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-189">Select **OK**.</span></span> 

5. <span data-ttu-id="0ae15-190">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="0ae15-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="0ae15-191">阻止通知</span><span class="sxs-lookup"><span data-stu-id="0ae15-191">Prevent notifications</span></span>

<span data-ttu-id="0ae15-192">有时，Microsoft Defender 防病毒通知可能会发送到多个会话或跨多个会话保留。</span><span class="sxs-lookup"><span data-stu-id="0ae15-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="0ae15-193">为了尽可能减小此问题，你可以锁定 Microsoft Defender 防病毒用户界面。</span><span class="sxs-lookup"><span data-stu-id="0ae15-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="0ae15-194">以下过程介绍如何使用组策略禁止通知。</span><span class="sxs-lookup"><span data-stu-id="0ae15-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="0ae15-195">在组策略编辑器中，转到 **Windows 组件**  >  **Microsoft Defender 防病毒**  >  **客户端接口**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="0ae15-196">选择 **"取消所有通知** "，然后编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="0ae15-197">将策略设置为 **"已启用"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ae15-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="0ae15-198">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="0ae15-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="0ae15-199">当扫描完成或采取修正操作时，禁止通知可防止来自 Microsoft Defender 防病毒的通知显示在 Windows 10 上的操作中心中。</span><span class="sxs-lookup"><span data-stu-id="0ae15-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="0ae15-200">但是，安全运营团队将在 Microsoft Defender 安全中心中查看扫描 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="0ae15-201">若要在 Windows 10 上打开操作中心，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0ae15-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="0ae15-202">在任务栏的右侧，选择操作中心图标。</span><span class="sxs-lookup"><span data-stu-id="0ae15-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="0ae15-203">按 Windows 徽标键按钮 + A。</span><span class="sxs-lookup"><span data-stu-id="0ae15-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="0ae15-204">在触摸屏设备上，从屏幕的右边缘轻扫。</span><span class="sxs-lookup"><span data-stu-id="0ae15-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="0ae15-205">更新后禁用扫描</span><span class="sxs-lookup"><span data-stu-id="0ae15-205">Disable scans after an update</span></span>

<span data-ttu-id="0ae15-206">在更新后禁用扫描将阻止扫描在收到更新后发生。</span><span class="sxs-lookup"><span data-stu-id="0ae15-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="0ae15-207">如果还运行了快速扫描，可以在创建基本映像时应用此设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="0ae15-208">这样，你可以阻止新更新的 VM 再次执行扫描 (，因为当你创建基本映像映像库时已经) 。</span><span class="sxs-lookup"><span data-stu-id="0ae15-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ae15-209">在更新后运行扫描有助于确保 VM 受最新安全智能更新的保护。</span><span class="sxs-lookup"><span data-stu-id="0ae15-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="0ae15-210">禁用此选项将降低 VM 的保护级别，并且应仅在首次创建或部署基本映像时使用。</span><span class="sxs-lookup"><span data-stu-id="0ae15-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="0ae15-211">在组策略编辑器中，转到 **Windows 组件**  >  **Microsoft Defender 防病毒**  >  **安全智能更新**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="0ae15-212">选择 **"在安全智能更新后启用扫描"，** 然后编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="0ae15-213">将策略设置为 **Disabled**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="0ae15-214">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-214">Select **OK**.</span></span>

5. <span data-ttu-id="0ae15-215">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="0ae15-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="0ae15-216">此策略阻止扫描在更新后立即运行。</span><span class="sxs-lookup"><span data-stu-id="0ae15-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="0ae15-217">扫描已脱机的 VM</span><span class="sxs-lookup"><span data-stu-id="0ae15-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="0ae15-218">在组策略编辑器中，转到 **Windows 组件** Microsoft  >  **Defender 防病毒**  >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="0ae15-219">选择 **"打开捕获快速扫描"，** 然后编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="0ae15-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="0ae15-220">将策略设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="0ae15-221">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-221">Select **OK**.</span></span>

5. <span data-ttu-id="0ae15-222">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="0ae15-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="0ae15-223">如果 VM 错过两个或多个连续的计划扫描，此策略将强制进行扫描。</span><span class="sxs-lookup"><span data-stu-id="0ae15-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="0ae15-224">启用无头 UI 模式</span><span class="sxs-lookup"><span data-stu-id="0ae15-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="0ae15-225">在组策略编辑器中，转到 **Windows 组件**  >  **Microsoft Defender 防病毒**  >  **客户端接口**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="0ae15-226">选择 **启用无头 UI 模式** 并编辑策略。</span><span class="sxs-lookup"><span data-stu-id="0ae15-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="0ae15-227">将策略设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="0ae15-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="0ae15-228">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0ae15-228">Click **OK**.</span></span>

5. <span data-ttu-id="0ae15-229">像通常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="0ae15-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="0ae15-230">此策略对组织中最终用户隐藏整个 Microsoft Defender 防病毒用户界面。</span><span class="sxs-lookup"><span data-stu-id="0ae15-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="0ae15-231">排除项</span><span class="sxs-lookup"><span data-stu-id="0ae15-231">Exclusions</span></span>

<span data-ttu-id="0ae15-232">可以添加、删除或自定义排除项，以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="0ae15-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="0ae15-233">有关详细信息，请参阅在 [Windows Server 上配置 Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae15-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ae15-234">其他资源</span><span class="sxs-lookup"><span data-stu-id="0ae15-234">Additional resources</span></span>

- [<span data-ttu-id="0ae15-235">技术社区博客：为非永久性 VDI 计算机配置 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="0ae15-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="0ae15-236">远程桌面服务和 VDI 上的 TechNet 论坛</span><span class="sxs-lookup"><span data-stu-id="0ae15-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="0ae15-237">SignatureDownloadCustomTask PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="0ae15-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)