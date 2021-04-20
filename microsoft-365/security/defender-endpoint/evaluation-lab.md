---
title: Microsoft Defender for Endpoint 评估实验室
description: 了解适用于终结点的 Microsoft Defender 功能、运行攻击模拟，并了解它如何预防、检测和修正威胁。
keywords: 评估 mdatp， 评估， 实验室， 模拟， windows 10， windows server 2019， 评估实验室
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2382281fbb975daa18ec21aabaf5acf8d3fbfb2f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893433"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="6c74c-104">Microsoft Defender for Endpoint 评估实验室</span><span class="sxs-lookup"><span data-stu-id="6c74c-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c74c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c74c-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c74c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c74c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6c74c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c74c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c74c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6c74c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c74c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6c74c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="6c74c-110">执行全面安全产品评估可能是一个复杂的过程，要求在实际完成端到端攻击模拟之前进行繁琐的环境和设备配置。</span><span class="sxs-lookup"><span data-stu-id="6c74c-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="6c74c-111">增加复杂性是跟踪模拟活动、警报和结果在评估中的反映位置的难题。</span><span class="sxs-lookup"><span data-stu-id="6c74c-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="6c74c-112">Microsoft Defender for Endpoint 评估实验室旨在消除设备和环境配置的复杂性，以便你可以专注于评估平台的功能、运行模拟，并查看防护、检测和修正功能的操作。</span><span class="sxs-lookup"><span data-stu-id="6c74c-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="6c74c-113">借助简化的设置体验，你可以专注于运行自己的测试方案和预建模拟，以查看 Defender for Endpoint 的执行方式。</span><span class="sxs-lookup"><span data-stu-id="6c74c-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="6c74c-114">你可以完全访问该平台的强大功能，如自动调查、高级搜寻和威胁分析，从而可以测试 Defender for Endpoint 提供的全面保护堆栈。</span><span class="sxs-lookup"><span data-stu-id="6c74c-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="6c74c-115">你可以添加预配置了最新操作系统版本和正确安全组件的 Windows 10 或 Windows Server 2019 设备，并安装了 Office 2019 Standard。</span><span class="sxs-lookup"><span data-stu-id="6c74c-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="6c74c-116">还可以安装威胁模拟器。</span><span class="sxs-lookup"><span data-stu-id="6c74c-116">You can also install threat simulators.</span></span> <span data-ttu-id="6c74c-117">Defender for Endpoint 已与行业领先的威胁模拟平台合作，帮助你测试 Defender for Endpoint 功能，而无需离开门户。</span><span class="sxs-lookup"><span data-stu-id="6c74c-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="6c74c-118">安装首选模拟器，在评估实验室内运行方案，并立即查看平台的运行方式-所有这些操作都很方便，无需额外付费。</span><span class="sxs-lookup"><span data-stu-id="6c74c-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="6c74c-119">还可以方便地访问广泛的模拟数组，你可以从模拟目录访问和运行这些模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="6c74c-120">开始之前</span><span class="sxs-lookup"><span data-stu-id="6c74c-120">Before you begin</span></span>
<span data-ttu-id="6c74c-121">你将需要满足许可要求 [，或者具有](minimum-requirements.md#licensing-requirements) 对 Microsoft Defender for Endpoint 的试用访问权限，以访问评估实验室。</span><span class="sxs-lookup"><span data-stu-id="6c74c-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="6c74c-122">您必须具有 **"管理安全设置"** 权限才能：</span><span class="sxs-lookup"><span data-stu-id="6c74c-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="6c74c-123">创建实验室</span><span class="sxs-lookup"><span data-stu-id="6c74c-123">Create the lab</span></span>
- <span data-ttu-id="6c74c-124">创建设备</span><span class="sxs-lookup"><span data-stu-id="6c74c-124">Create devices</span></span>
- <span data-ttu-id="6c74c-125">重置密码</span><span class="sxs-lookup"><span data-stu-id="6c74c-125">Reset password</span></span>
- <span data-ttu-id="6c74c-126">创建模拟</span><span class="sxs-lookup"><span data-stu-id="6c74c-126">Create simulations</span></span> 
 
<span data-ttu-id="6c74c-127">如果启用了基于角色的访问控制 (RBAC) 并创建了至少一台计算机组，则用户必须具有访问所有计算机组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c74c-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="6c74c-128">有关详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="6c74c-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="6c74c-129">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6c74c-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c74c-130">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6c74c-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="6c74c-131">实验室入门</span><span class="sxs-lookup"><span data-stu-id="6c74c-131">Get started with the lab</span></span>
<span data-ttu-id="6c74c-132">可以从菜单访问实验室。</span><span class="sxs-lookup"><span data-stu-id="6c74c-132">You can access the lab from the menu.</span></span> <span data-ttu-id="6c74c-133">在导航菜单中，选择评估 **实验室中的>教程**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![菜单上的评估实验室的图像](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="6c74c-135">根据你选择的环境结构类型，设备将在激活后指定的小时数内可用。</span><span class="sxs-lookup"><span data-stu-id="6c74c-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="6c74c-136">每个环境都使用一组有限的测试设备进行预配。</span><span class="sxs-lookup"><span data-stu-id="6c74c-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="6c74c-137">当你已使用预配的设备时，不会提供新设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="6c74c-138">已删除的设备不会刷新可用的测试设备计数。</span><span class="sxs-lookup"><span data-stu-id="6c74c-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="6c74c-139">资源已用时，你无法再使用实验室。</span><span class="sxs-lookup"><span data-stu-id="6c74c-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="6c74c-140">它不会重置也不刷新。</span><span class="sxs-lookup"><span data-stu-id="6c74c-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="6c74c-141">建议谨慎使用资源。实验室资源有限。</span><span class="sxs-lookup"><span data-stu-id="6c74c-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="6c74c-142">它们不会重置，也不会刷新。</span><span class="sxs-lookup"><span data-stu-id="6c74c-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="6c74c-143">已有实验室？</span><span class="sxs-lookup"><span data-stu-id="6c74c-143">Already have a lab?</span></span> <span data-ttu-id="6c74c-144">请确保启用新的威胁模拟器并拥有活动设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="6c74c-145">设置评估实验室</span><span class="sxs-lookup"><span data-stu-id="6c74c-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="6c74c-146">在导航窗格中，选择"**评估和教程评估** 实验室  >  **"，** 然后选择"**设置实验室"。**</span><span class="sxs-lookup"><span data-stu-id="6c74c-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![评估实验室欢迎页面的图像](images/evaluation-lab-setup.png)

2. <span data-ttu-id="6c74c-148">根据你的评估需求，你可以选择设置一个在较长时间内具有较少设备的环境，或者选择在较短的一段时间设置更多设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="6c74c-149">选择首选实验室配置，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="6c74c-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![实验室配置选项的图像](images/lab-creation-page.png) 


3. <span data-ttu-id="6c74c-151"> (可选) 你可以选择在实验室中安装威胁模拟器。</span><span class="sxs-lookup"><span data-stu-id="6c74c-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![安装模拟器代理的图像](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="6c74c-153">首先需要接受并同意条款和信息共享声明。</span><span class="sxs-lookup"><span data-stu-id="6c74c-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="6c74c-154">选择你要使用的威胁模拟代理并输入详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c74c-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="6c74c-155">还可以选择稍后安装威胁模拟器。</span><span class="sxs-lookup"><span data-stu-id="6c74c-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="6c74c-156">如果你选择在实验室设置期间安装威胁模拟代理，你将享受在添加的设备上方便地安装这些代理的好处。</span><span class="sxs-lookup"><span data-stu-id="6c74c-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![摘要页的图像](images/lab-setup-summary.png)

5.  <span data-ttu-id="6c74c-158">查看摘要，然后选择"**设置实验室"。**</span><span class="sxs-lookup"><span data-stu-id="6c74c-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="6c74c-159">实验室设置过程完成后，可以添加设备并运行模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="6c74c-160">添加设备</span><span class="sxs-lookup"><span data-stu-id="6c74c-160">Add devices</span></span>
<span data-ttu-id="6c74c-161">当你将设备添加到你的环境时，Defender for Endpoint 会设置具有连接详细信息的配置良好的设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="6c74c-162">你可以添加 Windows 10 或 Windows Server 2019 设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="6c74c-163">设备将配置最新版本的操作系统和 Office 2019 Standard 以及其他应用（如 Java、Python 和 SysIntenals）。</span><span class="sxs-lookup"><span data-stu-id="6c74c-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="6c74c-164">实验室中需要更多的设备？</span><span class="sxs-lookup"><span data-stu-id="6c74c-164">Need more devices in your lab?</span></span> <span data-ttu-id="6c74c-165">提交支持票证，让 Defender for Endpoint 团队审阅你的请求。</span><span class="sxs-lookup"><span data-stu-id="6c74c-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="6c74c-166">如果你在实验室设置期间选择添加威胁模拟器，所有设备都将在添加的设备上安装威胁模拟器代理。</span><span class="sxs-lookup"><span data-stu-id="6c74c-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="6c74c-167">设备将自动载入到租户，同时推荐的 Windows 安全组件已打开，并且位于审核模式下，无需任何努力。</span><span class="sxs-lookup"><span data-stu-id="6c74c-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="6c74c-168">在测试设备中预配置以下安全组件：</span><span class="sxs-lookup"><span data-stu-id="6c74c-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="6c74c-169">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="6c74c-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="6c74c-170">首次看到时阻止</span><span class="sxs-lookup"><span data-stu-id="6c74c-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="6c74c-171">受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="6c74c-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="6c74c-172">漏洞保护</span><span class="sxs-lookup"><span data-stu-id="6c74c-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="6c74c-173">网络保护</span><span class="sxs-lookup"><span data-stu-id="6c74c-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="6c74c-174">可能不需要的应用程序检测</span><span class="sxs-lookup"><span data-stu-id="6c74c-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="6c74c-175">云端保护</span><span class="sxs-lookup"><span data-stu-id="6c74c-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="6c74c-176">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="6c74c-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="6c74c-177">Microsoft Defender 防病毒将 (审核模式) 。</span><span class="sxs-lookup"><span data-stu-id="6c74c-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="6c74c-178">如果 Microsoft Defender 防病毒阻止你运行你的模拟，可以通过 Windows 安全中心在设备上关闭实时保护。</span><span class="sxs-lookup"><span data-stu-id="6c74c-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="6c74c-179">有关详细信息，请参阅配置 [始终打开保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="6c74c-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="6c74c-180">自动调查设置将取决于租户设置。</span><span class="sxs-lookup"><span data-stu-id="6c74c-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="6c74c-181">默认情况下，它将配置为半自动化。</span><span class="sxs-lookup"><span data-stu-id="6c74c-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="6c74c-182">有关详细信息，请参阅 [自动调查概述](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="6c74c-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="6c74c-183">与测试设备的连接使用 RDP 完成。</span><span class="sxs-lookup"><span data-stu-id="6c74c-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="6c74c-184">请确保防火墙设置允许 RDP 连接。</span><span class="sxs-lookup"><span data-stu-id="6c74c-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="6c74c-185">从仪表板中，选择"**添加设备"。**</span><span class="sxs-lookup"><span data-stu-id="6c74c-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="6c74c-186">选择要添加的设备类型。</span><span class="sxs-lookup"><span data-stu-id="6c74c-186">Choose the type of device to add.</span></span> <span data-ttu-id="6c74c-187">你可以选择添加 Windows 10 或 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6c74c-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![包含设备选项的实验室设置的图像](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="6c74c-189">如果设备创建过程出现问题，你将收到通知，并且需要提交新请求。</span><span class="sxs-lookup"><span data-stu-id="6c74c-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="6c74c-190">如果设备创建失败，将不会计入允许的总体配额。</span><span class="sxs-lookup"><span data-stu-id="6c74c-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="6c74c-191">将显示连接详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c74c-191">The connection details are displayed.</span></span> <span data-ttu-id="6c74c-192">选择 **"** 复制"保存设备的密码。</span><span class="sxs-lookup"><span data-stu-id="6c74c-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="6c74c-193">密码只显示一次。</span><span class="sxs-lookup"><span data-stu-id="6c74c-193">The password is only displayed once.</span></span> <span data-ttu-id="6c74c-194">请务必保存它供以后使用。</span><span class="sxs-lookup"><span data-stu-id="6c74c-194">Be sure to save it for later use.</span></span>

    ![使用连接详细信息添加的设备的图像](images/add-machine-eval-lab.png)

4. <span data-ttu-id="6c74c-196">设备设置开始。</span><span class="sxs-lookup"><span data-stu-id="6c74c-196">Device set up begins.</span></span> <span data-ttu-id="6c74c-197">这最多可能需要 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="6c74c-198">通过选择"设备"选项卡，查看测试设备的状态、风险和曝光级别以及模拟器 **安装** 的状态。</span><span class="sxs-lookup"><span data-stu-id="6c74c-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    !["设备"选项卡图像](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="6c74c-200">在 **模拟器状态** 列中，你可以将鼠标悬停在信息图标上，了解代理的安装状态。</span><span class="sxs-lookup"><span data-stu-id="6c74c-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="6c74c-201">模拟攻击方案</span><span class="sxs-lookup"><span data-stu-id="6c74c-201">Simulate attack scenarios</span></span>
<span data-ttu-id="6c74c-202">通过连接到测试设备来运行自己的攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="6c74c-203">可以使用以下方法模拟攻击方案：</span><span class="sxs-lookup"><span data-stu-id="6c74c-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="6c74c-204">" [自己执行"攻击方案](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="6c74c-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="6c74c-205">威胁模拟器</span><span class="sxs-lookup"><span data-stu-id="6c74c-205">Threat simulators</span></span>

<span data-ttu-id="6c74c-206">您还可以使用 [高级搜寻](advanced-hunting-query-language.md) 来查询数据和 [威胁分析](threat-analytics.md) ，以查看有关新出现的威胁的报告。</span><span class="sxs-lookup"><span data-stu-id="6c74c-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="6c74c-207">自己动手攻击方案</span><span class="sxs-lookup"><span data-stu-id="6c74c-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="6c74c-208">如果你要查找预先模拟，可以使用我们的"自己执行" [攻击方案](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="6c74c-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="6c74c-209">这些脚本安全、有记录且易于使用。</span><span class="sxs-lookup"><span data-stu-id="6c74c-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="6c74c-210">这些方案将反映 Defender for Endpoint 功能，并演练调查体验。</span><span class="sxs-lookup"><span data-stu-id="6c74c-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="6c74c-211">与测试设备的连接使用 RDP 完成。</span><span class="sxs-lookup"><span data-stu-id="6c74c-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="6c74c-212">请确保防火墙设置允许 RDP 连接。</span><span class="sxs-lookup"><span data-stu-id="6c74c-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="6c74c-213">通过选择"连接"连接到你的设备并运行攻击 **模拟**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![测试设备的连接按钮的图像](images/test-machine-table.png)

2. <span data-ttu-id="6c74c-215">保存 RDP 文件，然后通过选择"连接 **"将其启动**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![远程桌面连接的图像](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="6c74c-217">如果在初始设置期间没有保存密码的副本，则可以通过从菜单中选择"重置密码：重置密码的图像"来 ![ 重置密码](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="6c74c-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="6c74c-218">设备会更改其状态为"正在执行密码重置"，然后你将在数分钟内看到新密码。</span><span class="sxs-lookup"><span data-stu-id="6c74c-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="6c74c-219">输入在设备创建步骤期间显示的密码。</span><span class="sxs-lookup"><span data-stu-id="6c74c-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![用于输入凭据的窗口的图像](images/enter-password.png)

4. <span data-ttu-id="6c74c-221">在设备上运行自己动手攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="6c74c-222">威胁模拟器方案</span><span class="sxs-lookup"><span data-stu-id="6c74c-222">Threat simulator scenarios</span></span>
<span data-ttu-id="6c74c-223">如果你在实验室设置期间选择安装任何受支持的威胁模拟器，可以在评估实验室设备上运行内置模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="6c74c-224">使用第三方平台运行威胁模拟是在实验室环境中评估 Microsoft Defender for Endpoint 功能的良好方法。</span><span class="sxs-lookup"><span data-stu-id="6c74c-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="6c74c-225">在运行模拟之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="6c74c-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="6c74c-226">必须将设备添加到评估实验室</span><span class="sxs-lookup"><span data-stu-id="6c74c-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="6c74c-227">威胁模拟器必须安装在评估实验室中</span><span class="sxs-lookup"><span data-stu-id="6c74c-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="6c74c-228">从门户中选择"**创建模拟"。**</span><span class="sxs-lookup"><span data-stu-id="6c74c-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="6c74c-229">选择威胁模拟器。</span><span class="sxs-lookup"><span data-stu-id="6c74c-229">Select a threat simulator.</span></span>

    ![威胁模拟器选择的图像](images/select-simulator.png)

3. <span data-ttu-id="6c74c-231">选择模拟或浏览模拟库以浏览可用的模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="6c74c-232">你可以从以下方法访问模拟库：</span><span class="sxs-lookup"><span data-stu-id="6c74c-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="6c74c-233">模拟概述 **磁贴或**</span><span class="sxs-lookup"><span data-stu-id="6c74c-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="6c74c-234">通过导航从导航窗格 **评估和教程**  >  **模拟&教程，** 然后选择 **模拟目录**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="6c74c-235">选择要运行模拟的设备。</span><span class="sxs-lookup"><span data-stu-id="6c74c-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="6c74c-236">选择 **创建模拟**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="6c74c-237">通过选择"模拟"选项卡查看 **模拟** 的进度。查看模拟状态、活动警报和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c74c-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![模拟选项卡的图像](images/simulations-tab.png)
    
<span data-ttu-id="6c74c-239">运行模拟后，我们鼓励你演练实验室进度栏，并探索 Microsoft Defender **for Endpoint 触发了自动调查和修正**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="6c74c-240">查看功能收集和分析的证据。</span><span class="sxs-lookup"><span data-stu-id="6c74c-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="6c74c-241">使用丰富的查询语言和原始遥测通过高级搜寻来搜寻攻击证据，并查看威胁分析中记录一些全球威胁。</span><span class="sxs-lookup"><span data-stu-id="6c74c-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="6c74c-242">模拟库</span><span class="sxs-lookup"><span data-stu-id="6c74c-242">Simulation gallery</span></span>
<span data-ttu-id="6c74c-243">Microsoft Defender for Endpoint 已与各种威胁模拟平台合作，让你可以方便地从门户内测试平台的功能。</span><span class="sxs-lookup"><span data-stu-id="6c74c-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="6c74c-244">通过从菜单访问模拟和教程模拟  >  **目录，查看** 所有可用的模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="6c74c-245">列出了受支持的第三方威胁模拟代理的列表，并且目录上提供了特定类型的模拟以及详细说明。</span><span class="sxs-lookup"><span data-stu-id="6c74c-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="6c74c-246">你可以方便地从目录运行任何可用的模拟。</span><span class="sxs-lookup"><span data-stu-id="6c74c-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![模拟目录的图像](images/simulations-catalog.png)

<span data-ttu-id="6c74c-248">每个模拟都附带对攻击方案的深入描述和参考，如使用的 MITRE 攻击技术和运行的高级搜寻查询示例。</span><span class="sxs-lookup"><span data-stu-id="6c74c-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="6c74c-249">**示例：** 
 ![模拟描述详细信息的图像1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="6c74c-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![模拟描述详细信息的图像2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="6c74c-251">评估报告</span><span class="sxs-lookup"><span data-stu-id="6c74c-251">Evaluation report</span></span>
<span data-ttu-id="6c74c-252">实验室报告汇总了在设备上进行的模拟的结果。</span><span class="sxs-lookup"><span data-stu-id="6c74c-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![评估报告的图像](images/eval-report.png)

<span data-ttu-id="6c74c-254">一目了然，你可以快速看到：</span><span class="sxs-lookup"><span data-stu-id="6c74c-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="6c74c-255">触发的事件</span><span class="sxs-lookup"><span data-stu-id="6c74c-255">Incidents that were triggered</span></span>
- <span data-ttu-id="6c74c-256">生成的警报</span><span class="sxs-lookup"><span data-stu-id="6c74c-256">Generated alerts</span></span>
- <span data-ttu-id="6c74c-257">关于曝光级别的评估</span><span class="sxs-lookup"><span data-stu-id="6c74c-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="6c74c-258">观察到的威胁类别</span><span class="sxs-lookup"><span data-stu-id="6c74c-258">Threat categories observed</span></span>
- <span data-ttu-id="6c74c-259">检测源</span><span class="sxs-lookup"><span data-stu-id="6c74c-259">Detection sources</span></span>
- <span data-ttu-id="6c74c-260">自动调查</span><span class="sxs-lookup"><span data-stu-id="6c74c-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="6c74c-261">提供反馈</span><span class="sxs-lookup"><span data-stu-id="6c74c-261">Provide feedback</span></span>
<span data-ttu-id="6c74c-262">你的反馈可帮助我们更好地保护你的环境免受高级攻击。</span><span class="sxs-lookup"><span data-stu-id="6c74c-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="6c74c-263">分享产品功能和评估结果的体验和印象。</span><span class="sxs-lookup"><span data-stu-id="6c74c-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="6c74c-264">通过选择"提供反馈"，告诉我们 **您的想法**。</span><span class="sxs-lookup"><span data-stu-id="6c74c-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![提供反馈的图像](images/send-us-feedback-eval-lab.png)
