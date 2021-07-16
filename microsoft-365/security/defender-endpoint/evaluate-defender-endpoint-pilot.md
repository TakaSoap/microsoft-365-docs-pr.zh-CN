---
title: 通过模拟攻击体验 Microsoft Defender (MDE) 体验
description: 试用你的Microsoft 365 Defender试验实验室或试验环境。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457648"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="90ca8-104">通过模拟攻击体验 Microsoft Defender (MDE) 体验</span><span class="sxs-lookup"><span data-stu-id="90ca8-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="90ca8-105">了解适用于终结点的 Microsoft Defender 中的最新增强功能[：Defender for Endpoint 中的新增功能是什么？。](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="90ca8-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="90ca8-106">Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。</span><span class="sxs-lookup"><span data-stu-id="90ca8-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="90ca8-107">阅读[：Insights MITRE ATT&基于 CK 的评估。](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="90ca8-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="90ca8-108">在将多个设备载入服务之前，你可能想要体验 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="90ca8-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="90ca8-109">为此，可以在一些测试设备上运行受控攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="90ca8-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="90ca8-110">运行模拟攻击后，你可以查看 Defender for Endpoint 如何显示恶意活动，并探索它如何启用有效的响应。</span><span class="sxs-lookup"><span data-stu-id="90ca8-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="90ca8-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="90ca8-111">Before you begin</span></span>

<span data-ttu-id="90ca8-112">若要运行任何提供的模拟，你至少需要一 [个已载入的设备](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="90ca8-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="90ca8-113">阅读每个攻击方案提供的演练文档。</span><span class="sxs-lookup"><span data-stu-id="90ca8-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="90ca8-114">每个文档都包括操作系统和应用程序要求，以及特定于攻击方案的详细说明。</span><span class="sxs-lookup"><span data-stu-id="90ca8-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="90ca8-115">运行模拟</span><span class="sxs-lookup"><span data-stu-id="90ca8-115">Run a simulation</span></span>

1. <span data-ttu-id="90ca8-116">在  >  **帮助模拟&** 教程中，选择要模拟的可用攻击方案：</span><span class="sxs-lookup"><span data-stu-id="90ca8-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="90ca8-117">**方案 1：文档丢弃后门** - 模拟传递社交工程的诱使文档。</span><span class="sxs-lookup"><span data-stu-id="90ca8-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="90ca8-118">文档启动一个专门设计的后门，该后门为攻击者提供控制。</span><span class="sxs-lookup"><span data-stu-id="90ca8-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="90ca8-119">**方案 2：** 无文件攻击中的 PowerShell 脚本 - 模拟依赖于 PowerShell 的无文件攻击，展示攻击面减少和设备学习检测恶意内存活动。</span><span class="sxs-lookup"><span data-stu-id="90ca8-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="90ca8-120">**方案 3：自动事件响应** - 触发自动调查，自动搜寻并修正泄露项目，从而扩展事件响应容量。</span><span class="sxs-lookup"><span data-stu-id="90ca8-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="90ca8-121">下载并阅读所选方案提供的相应演练文档。</span><span class="sxs-lookup"><span data-stu-id="90ca8-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="90ca8-122">下载模拟文件或复制模拟脚本，方法为导航到帮助模拟  >  **&教程**。</span><span class="sxs-lookup"><span data-stu-id="90ca8-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="90ca8-123">你可以选择在测试设备上下载文件或脚本，但这不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="90ca8-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="90ca8-124">根据演练文档中的指示，在测试设备上运行模拟文件或脚本。</span><span class="sxs-lookup"><span data-stu-id="90ca8-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="90ca8-125">模拟文件或脚本模拟攻击活动，但实际上是恶意的，不会损害或损害测试设备。</span><span class="sxs-lookup"><span data-stu-id="90ca8-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="90ca8-126">备用主题文本</span><span class="sxs-lookup"><span data-stu-id="90ca8-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="90ca8-127">模拟攻击方案</span><span class="sxs-lookup"><span data-stu-id="90ca8-127">Simulate attack scenarios</span></span>

<span data-ttu-id="90ca8-128">通过连接到测试设备来运行自己的攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="90ca8-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="90ca8-129">可以使用以下方法模拟攻击方案：</span><span class="sxs-lookup"><span data-stu-id="90ca8-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="90ca8-130">" [自己执行"攻击方案](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="90ca8-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="90ca8-131">威胁模拟器</span><span class="sxs-lookup"><span data-stu-id="90ca8-131">Threat simulators</span></span>

<span data-ttu-id="90ca8-132">您还可以使用 [高级搜寻](advanced-hunting-overview.md) 来查询数据和 [威胁分析](threat-analytics.md) ，以查看有关新出现的威胁的报告。</span><span class="sxs-lookup"><span data-stu-id="90ca8-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="90ca8-133">自己动手攻击方案</span><span class="sxs-lookup"><span data-stu-id="90ca8-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="90ca8-134">如果你要查找预先模拟，可以使用我们的"自己执行" [攻击方案](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="90ca8-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="90ca8-135">这些脚本安全、有记录且易于使用。</span><span class="sxs-lookup"><span data-stu-id="90ca8-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="90ca8-136">这些方案将反映 Defender for Endpoint 功能，并演练调查体验。</span><span class="sxs-lookup"><span data-stu-id="90ca8-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="90ca8-137">与测试设备的连接使用 RDP 完成。</span><span class="sxs-lookup"><span data-stu-id="90ca8-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="90ca8-138">请确保防火墙设置允许 RDP 连接。</span><span class="sxs-lookup"><span data-stu-id="90ca8-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="90ca8-139">连接你的设备，通过选择""选项运行攻击 **连接。**</span><span class="sxs-lookup"><span data-stu-id="90ca8-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![测试设备的连接按钮的图像](images/test-machine-table.png)

2. <span data-ttu-id="90ca8-141">保存 RDP 文件，然后通过选择 **"连接"启动它**。</span><span class="sxs-lookup"><span data-stu-id="90ca8-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![远程桌面连接的图像](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="90ca8-143">如果在初始设置期间没有保存密码的副本，则可以通过从菜单中选择"重置密码：重置密码的图像"来 ![ 重置密码](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="90ca8-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="90ca8-144">设备会更改其状态为"正在执行密码重置"，然后你将在数分钟内看到新密码。</span><span class="sxs-lookup"><span data-stu-id="90ca8-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="90ca8-145">输入在设备创建步骤期间显示的密码。</span><span class="sxs-lookup"><span data-stu-id="90ca8-145">Enter the password that was displayed during the device creation step.</span></span>

   ![用于输入凭据的窗口的图像](images/enter-password.png)

4. <span data-ttu-id="90ca8-147">在设备上运行自己动手攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="90ca8-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="90ca8-148">威胁模拟器方案</span><span class="sxs-lookup"><span data-stu-id="90ca8-148">Threat simulator scenarios</span></span>

<span data-ttu-id="90ca8-149">如果你在实验室设置期间选择安装任何受支持的威胁模拟器，可以在评估实验室设备上运行内置模拟。</span><span class="sxs-lookup"><span data-stu-id="90ca8-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="90ca8-150">使用第三方平台运行威胁模拟是在实验室环境中评估 Microsoft Defender for Endpoint 功能的良好方法。</span><span class="sxs-lookup"><span data-stu-id="90ca8-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="90ca8-151">在运行模拟之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="90ca8-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="90ca8-152">必须将设备添加到评估实验室</span><span class="sxs-lookup"><span data-stu-id="90ca8-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="90ca8-153">威胁模拟器必须安装在评估实验室中</span><span class="sxs-lookup"><span data-stu-id="90ca8-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="90ca8-154">从门户中选择"**创建模拟"。**</span><span class="sxs-lookup"><span data-stu-id="90ca8-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="90ca8-155">选择威胁模拟器。</span><span class="sxs-lookup"><span data-stu-id="90ca8-155">Select a threat simulator.</span></span>

    ![威胁模拟器选择的图像](images/select-simulator.png)

3. <span data-ttu-id="90ca8-157">选择模拟或浏览模拟库以浏览可用的模拟。</span><span class="sxs-lookup"><span data-stu-id="90ca8-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="90ca8-158">你可以从以下方法访问模拟库：</span><span class="sxs-lookup"><span data-stu-id="90ca8-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="90ca8-159">模拟概述 **磁贴或**</span><span class="sxs-lookup"><span data-stu-id="90ca8-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="90ca8-160">通过导航从导航窗格 **评估和教程**  >  **模拟&教程，** 然后选择 **模拟目录**。</span><span class="sxs-lookup"><span data-stu-id="90ca8-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="90ca8-161">选择要运行模拟的设备。</span><span class="sxs-lookup"><span data-stu-id="90ca8-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="90ca8-162">选择 **创建模拟**。</span><span class="sxs-lookup"><span data-stu-id="90ca8-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="90ca8-163">通过选择"模拟"选项卡查看 **模拟** 的进度。查看模拟状态、活动警报和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="90ca8-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="90ca8-164">![模拟选项卡的图像](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="90ca8-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="90ca8-165">运行模拟后，我们鼓励你演练实验室进度栏，并探索 Microsoft Defender **for Endpoint 触发了自动调查和修正**。</span><span class="sxs-lookup"><span data-stu-id="90ca8-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="90ca8-166">查看功能收集和分析的证据。</span><span class="sxs-lookup"><span data-stu-id="90ca8-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="90ca8-167">使用丰富的查询语言和原始遥测通过高级搜寻来搜寻攻击证据，并查看威胁分析中记录一些全球威胁。</span><span class="sxs-lookup"><span data-stu-id="90ca8-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
