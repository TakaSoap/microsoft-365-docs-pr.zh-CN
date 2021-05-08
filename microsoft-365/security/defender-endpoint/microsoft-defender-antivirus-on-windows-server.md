---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Windows Server 2016 和 Windows Server 2019 上启用和配置 Microsoft Defender 防病毒。
keywords: windows defender， 服务器， scep， system center endpoint protection， server 2016， current branch， server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269488"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="aac59-104">Windows Server 上的 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="aac59-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aac59-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aac59-105">**Applies to:**</span></span>

- [<span data-ttu-id="aac59-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aac59-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="aac59-107">Windows Server 的以下版本/版本上提供了 Microsoft Defender 防病毒：</span><span class="sxs-lookup"><span data-stu-id="aac59-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="aac59-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="aac59-108">Windows Server 2019</span></span>
- <span data-ttu-id="aac59-109">Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aac59-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="aac59-110">Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="aac59-110">Windows Server 2016.</span></span> 

<span data-ttu-id="aac59-111">在某些情况下，Microsoft Defender 防病毒称为 Endpoint *Protection*;但是，保护引擎是相同的。</span><span class="sxs-lookup"><span data-stu-id="aac59-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="aac59-112">尽管 [Windows 10](microsoft-defender-antivirus-in-windows-10.md)上的 Microsoft Defender 防病毒的功能、配置和管理基本相同，但 Windows Server 上有几个主要区别：</span><span class="sxs-lookup"><span data-stu-id="aac59-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="aac59-113">在 Windows Server [上，](configure-server-exclusions-microsoft-defender-antivirus.md) 根据定义的服务器角色应用自动排除项。</span><span class="sxs-lookup"><span data-stu-id="aac59-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="aac59-114">在 Windows Server 上，如果运行的是非 Microsoft 防病毒/反恶意软件解决方案，Microsoft Defender 防病毒不会自动进入被动模式或禁用模式。</span><span class="sxs-lookup"><span data-stu-id="aac59-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="aac59-115">但是，你可以手动将 Microsoft Defender 防病毒设置为被动或禁用模式。</span><span class="sxs-lookup"><span data-stu-id="aac59-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="aac59-116">在 Windows Server 上设置 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="aac59-117">在服务器平台上设置和运行 Microsoft Defender 防病毒的过程包括几个步骤：</span><span class="sxs-lookup"><span data-stu-id="aac59-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="aac59-118">[启用接口](#enable-the-user-interface-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="aac59-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="aac59-119">[安装 Microsoft Defender 防病毒](#install-microsoft-defender-antivirus-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="aac59-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="aac59-120">[验证 Microsoft Defender 防病毒是否正在运行](#verify-microsoft-defender-antivirus-is-running)。</span><span class="sxs-lookup"><span data-stu-id="aac59-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="aac59-121">[更新反恶意软件安全智能](#update-antimalware-security-intelligence)。</span><span class="sxs-lookup"><span data-stu-id="aac59-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="aac59-122"> (根据需要) [提交示例。](#submit-samples)</span><span class="sxs-lookup"><span data-stu-id="aac59-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="aac59-123"> (根据需要) [配置自动排除项](#configure-automatic-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="aac59-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="aac59-124"> (仅在必要) [将 Microsoft Defender 防病毒设置为被动模式](#need-to-set-microsoft-defender-antivirus-to-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="aac59-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="aac59-125">在 Windows Server 上启用用户界面</span><span class="sxs-lookup"><span data-stu-id="aac59-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="aac59-126">默认情况下，Microsoft Defender 防病毒已安装且在 Windows Server 上正常运行。</span><span class="sxs-lookup"><span data-stu-id="aac59-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="aac59-127">有时，用户界面会 (GUI) 安装，但不需要 GUI。</span><span class="sxs-lookup"><span data-stu-id="aac59-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="aac59-128">可以使用 PowerShell、组策略或其他方法来管理 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="aac59-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="aac59-129">如果服务器上未安装 GUI，并且要安装 GUI，则使用"添加角色 **和功能** "向导或 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac59-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="aac59-130">使用添加角色和功能向导打开 GUI</span><span class="sxs-lookup"><span data-stu-id="aac59-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="aac59-131">请参阅 [使用添加角色和功能向导](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)安装角色、角色服务和功能，并使用 **添加角色和功能向导**。</span><span class="sxs-lookup"><span data-stu-id="aac59-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="aac59-132">当您进入向导的 **"功能** "步骤时，在"Windows Defender **功能"** 下，选择 **"Windows Defender** GUI"选项。</span><span class="sxs-lookup"><span data-stu-id="aac59-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="aac59-133">在 Windows Server 2016 中，添加 **角色和功能向导** 如下所示：</span><span class="sxs-lookup"><span data-stu-id="aac59-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![添加显示选项 GUI 的角色Windows Defender向导](images/server-add-gui.png)

   <span data-ttu-id="aac59-135">在 Windows Server 2019 中，添加 **角色和功能向导** 类似。</span><span class="sxs-lookup"><span data-stu-id="aac59-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="aac59-136">使用 PowerShell 打开 GUI</span><span class="sxs-lookup"><span data-stu-id="aac59-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="aac59-137">以下 PowerShell cmdlet 将启用该接口：</span><span class="sxs-lookup"><span data-stu-id="aac59-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="aac59-138">在 Windows Server 上安装 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="aac59-139">如果你需要在 Windows Server 上安装或重新安装 Microsoft Defender 防病毒，可以使用添加角色 **和功能** 向导或 PowerShell 来这样做。</span><span class="sxs-lookup"><span data-stu-id="aac59-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="aac59-140">使用添加角色和功能向导安装 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="aac59-141">请参阅 [本文 ，并使用](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)添加 **角色和功能向导**。</span><span class="sxs-lookup"><span data-stu-id="aac59-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="aac59-142">当你进入向导的 **"功能"** 步骤时，选择"Microsoft Defender 防病毒"选项。</span><span class="sxs-lookup"><span data-stu-id="aac59-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="aac59-143">另外，选择 **"用于Windows Defender** GUI"选项。</span><span class="sxs-lookup"><span data-stu-id="aac59-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="aac59-144">使用 PowerShell 安装 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="aac59-145">若要使用 PowerShell 安装 Microsoft Defender 防病毒，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aac59-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="aac59-146">Microsoft Defender 防病毒中包含的反恶意软件引擎的事件消息可以在 [Microsoft Defender AV 事件找到](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="aac59-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="aac59-147">验证 Microsoft Defender 防病毒是否正在运行</span><span class="sxs-lookup"><span data-stu-id="aac59-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="aac59-148">安装 Microsoft Defender 防病毒后，下一步是验证其是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="aac59-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="aac59-149">在 Windows Server 终结点上，运行以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aac59-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="aac59-150">若要验证防火墙保护是否打开，请运行以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aac59-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="aac59-151">作为 PowerShell 的替代方法，可以使用命令提示符验证 Microsoft Defender 防病毒是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="aac59-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="aac59-152">为此，请从命令提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aac59-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="aac59-153">该命令 `sc query` 返回有关 Microsoft Defender 防病毒服务的信息。</span><span class="sxs-lookup"><span data-stu-id="aac59-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="aac59-154">当 Microsoft Defender 防病毒正在运行时， `STATE` 值将显示 `RUNNING` 。</span><span class="sxs-lookup"><span data-stu-id="aac59-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="aac59-155">更新反恶意软件安全智能</span><span class="sxs-lookup"><span data-stu-id="aac59-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="aac59-156">若要获取更新的反恶意软件安全智能，必须运行 Windows 更新服务。</span><span class="sxs-lookup"><span data-stu-id="aac59-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="aac59-157">如果使用更新管理服务，如 Windows Server Update Services (WSUS) ，请确保已针对你管理的计算机批准 Microsoft Defender 防病毒安全智能的更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="aac59-158">默认情况下，Windows 更新不会在 Windows Server 2019 或 Windows Server 2016 上自动下载和安装更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="aac59-159">可以使用以下方法之一更改此配置：</span><span class="sxs-lookup"><span data-stu-id="aac59-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="aac59-160">方法</span><span class="sxs-lookup"><span data-stu-id="aac59-160">Method</span></span>  |<span data-ttu-id="aac59-161">说明</span><span class="sxs-lookup"><span data-stu-id="aac59-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="aac59-162">**控制面板中的 Windows** 更新</span><span class="sxs-lookup"><span data-stu-id="aac59-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="aac59-163">- **自动安装更新** 会导致自动安装所有更新，Windows Defender安全智能更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="aac59-164">- **下载更新，但允许我** 选择是否安装它们Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="aac59-165">**组策略**</span><span class="sxs-lookup"><span data-stu-id="aac59-165">**Group Policy**</span></span>     | <span data-ttu-id="aac59-166">可以通过以下路径中的组策略中提供的设置来设置和管理 Windows **更新：管理模板\Windows 组件\Windows 更新\配置自动更新**</span><span class="sxs-lookup"><span data-stu-id="aac59-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="aac59-167">**AUOptions** 注册表项</span><span class="sxs-lookup"><span data-stu-id="aac59-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="aac59-168">以下两个值允许 Windows 更新自动下载和安装安全智能更新：</span><span class="sxs-lookup"><span data-stu-id="aac59-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="aac59-169">- **4**  - **自动安装更新**。</span><span class="sxs-lookup"><span data-stu-id="aac59-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="aac59-170">此值会导致自动安装所有更新，包括Windows Defender更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="aac59-171">- **3**  - **下载更新，但允许我选择是否安装它们**。</span><span class="sxs-lookup"><span data-stu-id="aac59-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="aac59-172">此值允许Windows Defender下载和安装安全智能更新，但不会自动安装其他更新。</span><span class="sxs-lookup"><span data-stu-id="aac59-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="aac59-173">为了确保对恶意软件的保护得到维护，我们建议您启用以下服务：</span><span class="sxs-lookup"><span data-stu-id="aac59-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="aac59-174">Windows 错误报告服务</span><span class="sxs-lookup"><span data-stu-id="aac59-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="aac59-175">Windows 更新服务</span><span class="sxs-lookup"><span data-stu-id="aac59-175">Windows Update service</span></span>

<span data-ttu-id="aac59-176">下表列出了 Microsoft Defender 防病毒的服务和从属服务。</span><span class="sxs-lookup"><span data-stu-id="aac59-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="aac59-177">服务名称</span><span class="sxs-lookup"><span data-stu-id="aac59-177">Service Name</span></span>|<span data-ttu-id="aac59-178">文件位置</span><span class="sxs-lookup"><span data-stu-id="aac59-178">File Location</span></span>|<span data-ttu-id="aac59-179">说明</span><span class="sxs-lookup"><span data-stu-id="aac59-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="aac59-180">Windows Defender Service (WinDefend) </span><span class="sxs-lookup"><span data-stu-id="aac59-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="aac59-181">这是需要一定时间运行的主要 Microsoft Defender 防病毒服务。</span><span class="sxs-lookup"><span data-stu-id="aac59-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="aac59-182">Windows 错误报告服务 (Wersvc) </span><span class="sxs-lookup"><span data-stu-id="aac59-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="aac59-183">此服务将错误报告发送回 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="aac59-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="aac59-184">Windows Defender MpsSvc (防火墙) </span><span class="sxs-lookup"><span data-stu-id="aac59-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="aac59-185">我们建议使防火墙Windows Defender启用。</span><span class="sxs-lookup"><span data-stu-id="aac59-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="aac59-186">Windows 更新 (Wuauserv) </span><span class="sxs-lookup"><span data-stu-id="aac59-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="aac59-187">需要 Windows 更新才能获取安全智能更新和反恶意软件引擎更新</span><span class="sxs-lookup"><span data-stu-id="aac59-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="aac59-188">提交示例</span><span class="sxs-lookup"><span data-stu-id="aac59-188">Submit samples</span></span>

<span data-ttu-id="aac59-189">示例提交允许 Microsoft 收集潜在恶意软件的示例。</span><span class="sxs-lookup"><span data-stu-id="aac59-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="aac59-190">为了帮助提供持续且最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。</span><span class="sxs-lookup"><span data-stu-id="aac59-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="aac59-191">我们收集程序可执行文件，例如.exe文件.dll文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="aac59-192">我们不会收集包含个人数据的文件，如 Microsoft Word 文档和 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="aac59-193">提交文件</span><span class="sxs-lookup"><span data-stu-id="aac59-193">Submit a file</span></span>

1. <span data-ttu-id="aac59-194">查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="aac59-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="aac59-195">访问 [示例提交门户 ，](https://www.microsoft.com/wdsi/filesubmission)并提交你的文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="aac59-196">启用自动提交示例</span><span class="sxs-lookup"><span data-stu-id="aac59-196">Enable automatic sample submission</span></span>

<span data-ttu-id="aac59-197">若要启用自动示例提交，请以管理员Windows PowerShell启动示例提交控制台，然后根据以下设置之一设置 **SubmitSamplesConsent** 值数据：</span><span class="sxs-lookup"><span data-stu-id="aac59-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="aac59-198">设置</span><span class="sxs-lookup"><span data-stu-id="aac59-198">Setting</span></span>  |<span data-ttu-id="aac59-199">说明</span><span class="sxs-lookup"><span data-stu-id="aac59-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="aac59-200">**0**  - **始终提示**</span><span class="sxs-lookup"><span data-stu-id="aac59-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="aac59-201">Microsoft Defender 防病毒服务会提示你确认提交所有必需文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="aac59-202">这是 Microsoft Defender 防病毒的默认设置，但不建议在没有 GUI 的情况下在 Windows Server 2016 或 2019 上安装。</span><span class="sxs-lookup"><span data-stu-id="aac59-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="aac59-203">**1**   - **自动发送安全示例**</span><span class="sxs-lookup"><span data-stu-id="aac59-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="aac59-204">Microsoft Defender 防病毒服务发送标记为"安全"的所有文件，并提示输入其余文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="aac59-205">**2**  - **从不发送**</span><span class="sxs-lookup"><span data-stu-id="aac59-205">**2** - **Never send**</span></span>      |<span data-ttu-id="aac59-206">Microsoft Defender 防病毒服务不提示也不发送任何文件。</span><span class="sxs-lookup"><span data-stu-id="aac59-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="aac59-207">**3**  - **自动发送所有示例**</span><span class="sxs-lookup"><span data-stu-id="aac59-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="aac59-208">Microsoft Defender 防病毒服务发送所有文件，而不提示确认。</span><span class="sxs-lookup"><span data-stu-id="aac59-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="aac59-209">配置自动排除项</span><span class="sxs-lookup"><span data-stu-id="aac59-209">Configure automatic exclusions</span></span>

<span data-ttu-id="aac59-210">为了帮助确保安全性和性能，某些排除项根据你在 Windows Server 2016 或 2019 上使用 Microsoft Defender 防病毒时安装的角色和功能自动添加。</span><span class="sxs-lookup"><span data-stu-id="aac59-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="aac59-211">请参阅 [在 Windows Server 上配置 Microsoft Defender 防病毒中的排除项](configure-server-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="aac59-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="aac59-212">需要将 Microsoft Defender 防病毒设置为被动模式？</span><span class="sxs-lookup"><span data-stu-id="aac59-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="aac59-213">如果你使用非 Microsoft 防病毒产品作为 Windows Server 上的主要防病毒解决方案，则必须将 Microsoft Defender 防病毒设置为被动模式或禁用模式。</span><span class="sxs-lookup"><span data-stu-id="aac59-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="aac59-214">在 Windows Server 版本 1803 或更高版本或 Windows Server 2019 上，可以将 Microsoft Defender 防病毒设置为被动模式。</span><span class="sxs-lookup"><span data-stu-id="aac59-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="aac59-215">在 Windows Server 2016 上，Microsoft Defender 防病毒与非 Microsoft 防病毒/反恶意软件产品一起不受支持。</span><span class="sxs-lookup"><span data-stu-id="aac59-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="aac59-216">在这些情况下，必须将 Microsoft Defender 防病毒设置为禁用模式。</span><span class="sxs-lookup"><span data-stu-id="aac59-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="aac59-217">使用 PowerShell 将 Microsoft Defender 防病毒设置为被动模式</span><span class="sxs-lookup"><span data-stu-id="aac59-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="aac59-218">如果你使用的是 Windows Server 版本 1803 或 Windows Server 2019，可以使用以下 PowerShell cmdlet 将 Microsoft Defender 防病毒设置为被动模式：</span><span class="sxs-lookup"><span data-stu-id="aac59-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="aac59-219">使用组策略将 Microsoft Defender 防病毒设置为被动模式</span><span class="sxs-lookup"><span data-stu-id="aac59-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="aac59-220">所需的过程</span><span class="sxs-lookup"><span data-stu-id="aac59-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="aac59-221">使用注册表项将 Microsoft Defender 防病毒设置为被动模式</span><span class="sxs-lookup"><span data-stu-id="aac59-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="aac59-222">如果你使用的是 Windows Server 版本 1803 或 Windows Server 2019，可以通过设置以下注册表项将 Microsoft Defender 防病毒设置为被动模式：</span><span class="sxs-lookup"><span data-stu-id="aac59-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="aac59-223">路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="aac59-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="aac59-224">名称：`ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="aac59-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="aac59-225">类型： `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="aac59-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="aac59-226">值：`1`</span><span class="sxs-lookup"><span data-stu-id="aac59-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="aac59-227">使用"删除角色和功能"向导禁用 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="aac59-228">请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，并使用 **删除角色和功能向导**。</span><span class="sxs-lookup"><span data-stu-id="aac59-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="aac59-229">当您进入向导的 **"功能**"步骤时，请清除"Windows Defender"选项。 </span><span class="sxs-lookup"><span data-stu-id="aac59-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="aac59-230">如果在 **"Windows Defender** 功能"部分下自行清除 **Windows Defender，** 系统将提示您删除"Windows Defender"**的界面选项 GUI。**</span><span class="sxs-lookup"><span data-stu-id="aac59-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="aac59-231">Microsoft Defender 防病毒在没有用户界面的情况下仍可以正常运行，但如果禁用核心防病毒功能，将无法 **Windows Defender** 用户界面。</span><span class="sxs-lookup"><span data-stu-id="aac59-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="aac59-232">使用 PowerShell 关闭 Microsoft Defender 防病毒用户界面</span><span class="sxs-lookup"><span data-stu-id="aac59-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="aac59-233">若要关闭 Microsoft Defender 防病毒 GUI，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aac59-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="aac59-234">是否正在使用 Windows Server 2016？</span><span class="sxs-lookup"><span data-stu-id="aac59-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="aac59-235">如果你使用的是 Windows Server 2016 以及 Microsoft 未提供或开发的第三方反恶意软件/防病毒产品，则需要禁用/卸载 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="aac59-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="aac59-236">无法卸载 Windows 安全应用，但可以使用以下说明禁用界面。</span><span class="sxs-lookup"><span data-stu-id="aac59-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="aac59-237">以下 PowerShell cmdlet 卸载 Windows Server 2016 上的 Microsoft Defender 防病毒：</span><span class="sxs-lookup"><span data-stu-id="aac59-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="aac59-238">若要在 Windows Server 2016 上禁用 Microsoft Defender 防病毒，请使用以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aac59-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="aac59-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aac59-239">See also</span></span>

- [<span data-ttu-id="aac59-240">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aac59-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="aac59-241">Microsoft Defender 防病毒兼容性</span><span class="sxs-lookup"><span data-stu-id="aac59-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
