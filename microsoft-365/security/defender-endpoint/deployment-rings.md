---
title: 在圈中部署 Microsoft Defender for Endpoint
description: 了解如何在圈中部署 Microsoft Defender for Endpoint
keywords: 部署， 圈， 评估， 试点， 预览体验成员 - 快， 预览体验成员 - 慢， 设置， 载入， 阶段， 部署， 部署， 采用， 配置
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
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297198"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="f8d08-104">在圈中部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8d08-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8d08-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f8d08-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8d08-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8d08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8d08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8d08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f8d08-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="f8d08-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f8d08-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f8d08-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f8d08-110">可以使用基于圈的部署方法部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f8d08-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="f8d08-111">可以在以下方案中应用部署圈：</span><span class="sxs-lookup"><span data-stu-id="f8d08-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="f8d08-112">新部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="f8d08-113">现有部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="f8d08-114">新部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-114">New deployments</span></span>

![部署圈的图像](images/deployment-rings.png)


<span data-ttu-id="f8d08-116">基于圈的方法用于标识要载入的一组终结点，并验证是否满足特定条件，然后再继续将服务部署到更大的设备集。</span><span class="sxs-lookup"><span data-stu-id="f8d08-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="f8d08-117">你可以定义每个圈的退出条件，并确保它们满足，然后再移动到下一个圈。</span><span class="sxs-lookup"><span data-stu-id="f8d08-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="f8d08-118">采用基于圈的部署有助于减少推出服务时可能出现的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="f8d08-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="f8d08-119">通过先试用一定数量的设备，你可以识别潜在问题并减少可能出现的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="f8d08-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="f8d08-120">表 1 提供了您可能使用的部署圈的示例。</span><span class="sxs-lookup"><span data-stu-id="f8d08-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="f8d08-121">**表 1**</span><span class="sxs-lookup"><span data-stu-id="f8d08-121">**Table 1**</span></span>

|<span data-ttu-id="f8d08-122">**部署圈**</span><span class="sxs-lookup"><span data-stu-id="f8d08-122">**Deployment ring**</span></span>|<span data-ttu-id="f8d08-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="f8d08-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="f8d08-124">Evaluate</span><span class="sxs-lookup"><span data-stu-id="f8d08-124">Evaluate</span></span> | <span data-ttu-id="f8d08-125">圈 1：标识 50 个系统用于试点测试</span><span class="sxs-lookup"><span data-stu-id="f8d08-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="f8d08-126">试点</span><span class="sxs-lookup"><span data-stu-id="f8d08-126">Pilot</span></span> | <span data-ttu-id="f8d08-127">圈 2：标识生产环境中的下 50-100 个终结点</span><span class="sxs-lookup"><span data-stu-id="f8d08-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="f8d08-128">完整部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-128">Full deployment</span></span> | <span data-ttu-id="f8d08-129">圈 3：以较大增量向其余环境推出服务</span><span class="sxs-lookup"><span data-stu-id="f8d08-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="f8d08-130">退出条件</span><span class="sxs-lookup"><span data-stu-id="f8d08-130">Exit criteria</span></span>
<span data-ttu-id="f8d08-131">这些圈的退出条件集示例包括：</span><span class="sxs-lookup"><span data-stu-id="f8d08-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="f8d08-132">设备显示在设备清单列表中</span><span class="sxs-lookup"><span data-stu-id="f8d08-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="f8d08-133">警报显示在仪表板中</span><span class="sxs-lookup"><span data-stu-id="f8d08-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="f8d08-134">运行检测测试</span><span class="sxs-lookup"><span data-stu-id="f8d08-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="f8d08-135">在设备上运行模拟攻击</span><span class="sxs-lookup"><span data-stu-id="f8d08-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="f8d08-136">Evaluate</span><span class="sxs-lookup"><span data-stu-id="f8d08-136">Evaluate</span></span>
<span data-ttu-id="f8d08-137">确定环境中要载入服务的少量测试计算机。</span><span class="sxs-lookup"><span data-stu-id="f8d08-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="f8d08-138">理想情况下，这些计算机将少于 50 个终结点。</span><span class="sxs-lookup"><span data-stu-id="f8d08-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="f8d08-139">试点</span><span class="sxs-lookup"><span data-stu-id="f8d08-139">Pilot</span></span>
<span data-ttu-id="f8d08-140">Microsoft Defender for Endpoint 支持可载入到服务的各种终结点。</span><span class="sxs-lookup"><span data-stu-id="f8d08-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="f8d08-141">在此圈中，确定要载入的几个设备，并基于定义的退出条件，决定继续下一个部署圈。</span><span class="sxs-lookup"><span data-stu-id="f8d08-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="f8d08-142">下表显示了受支持的终结点以及可用于将设备载入服务的相应工具。</span><span class="sxs-lookup"><span data-stu-id="f8d08-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="f8d08-143">终结点</span><span class="sxs-lookup"><span data-stu-id="f8d08-143">Endpoint</span></span>     | <span data-ttu-id="f8d08-144">部署工具</span><span class="sxs-lookup"><span data-stu-id="f8d08-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="f8d08-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="f8d08-145">**Windows**</span></span>  |  [<span data-ttu-id="f8d08-146">本地脚本 (最多 10 台设备) </span><span class="sxs-lookup"><span data-stu-id="f8d08-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="f8d08-147">注意：如果要在生产环境中部署 10 台以上设备，请改为使用组策略方法或下面列出的其他支持的工具。</span><span class="sxs-lookup"><span data-stu-id="f8d08-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="f8d08-148">组策略</span><span class="sxs-lookup"><span data-stu-id="f8d08-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="f8d08-149">Microsoft Endpoint Manager/移动设备管理器</span><span class="sxs-lookup"><span data-stu-id="f8d08-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="f8d08-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f8d08-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="f8d08-151">VDI 脚本</span><span class="sxs-lookup"><span data-stu-id="f8d08-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="f8d08-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="f8d08-152">**macOS**</span></span>    | [<span data-ttu-id="f8d08-153">本地脚本</span><span class="sxs-lookup"><span data-stu-id="f8d08-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="f8d08-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f8d08-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="f8d08-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="f8d08-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="f8d08-156">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="f8d08-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="f8d08-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="f8d08-157">**Linux Server**</span></span> | [<span data-ttu-id="f8d08-158">本地脚本</span><span class="sxs-lookup"><span data-stu-id="f8d08-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="f8d08-159">百分百</span><span class="sxs-lookup"><span data-stu-id="f8d08-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="f8d08-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="f8d08-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="f8d08-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="f8d08-161">**iOS**</span></span>      | [<span data-ttu-id="f8d08-162">基于应用</span><span class="sxs-lookup"><span data-stu-id="f8d08-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="f8d08-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="f8d08-163">**Android**</span></span>  | [<span data-ttu-id="f8d08-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="f8d08-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="f8d08-165">完整部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-165">Full deployment</span></span>
<span data-ttu-id="f8d08-166">在此阶段，可以使用规划 [部署材料来帮助](deployment-strategy.md) 你规划部署。</span><span class="sxs-lookup"><span data-stu-id="f8d08-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="f8d08-167">使用以下材料选择最适合贵组织的适用于终结点的 Microsoft Defender 体系结构。</span><span class="sxs-lookup"><span data-stu-id="f8d08-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="f8d08-168">**项目**</span><span class="sxs-lookup"><span data-stu-id="f8d08-168">**Item**</span></span>|<span data-ttu-id="f8d08-169">**说明**</span><span class="sxs-lookup"><span data-stu-id="f8d08-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8d08-170">[![Microsoft Defender for Endpoint 部署策略缩略图](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="f8d08-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="f8d08-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="f8d08-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="f8d08-172">体系结构资料有助于规划如下体系结构的部署：</span><span class="sxs-lookup"><span data-stu-id="f8d08-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="f8d08-173">云-本机</span><span class="sxs-lookup"><span data-stu-id="f8d08-173">Cloud-native</span></span> </li><li> <span data-ttu-id="f8d08-174">协同管理</span><span class="sxs-lookup"><span data-stu-id="f8d08-174">Co-management</span></span> </li><li> <span data-ttu-id="f8d08-175">本地</span><span class="sxs-lookup"><span data-stu-id="f8d08-175">On-premise</span></span></li><li><span data-ttu-id="f8d08-176">评估和本地载入</span><span class="sxs-lookup"><span data-stu-id="f8d08-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="f8d08-177">现有部署</span><span class="sxs-lookup"><span data-stu-id="f8d08-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="f8d08-178">Windows终结点</span><span class="sxs-lookup"><span data-stu-id="f8d08-178">Windows endpoints</span></span>
<span data-ttu-id="f8d08-179">对于 Windows 和/或 Windows 服务器，可以使用 SUVP) 安全更新验证计划选择多个计算机在修补 (之前提前测试 (**SVP) 。**</span><span class="sxs-lookup"><span data-stu-id="f8d08-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="f8d08-180">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f8d08-180">For more information, see:</span></span>
- [<span data-ttu-id="f8d08-181">什么是安全更新验证计划</span><span class="sxs-lookup"><span data-stu-id="f8d08-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="f8d08-182">软件更新验证计划与Microsoft 恶意软件防护中心 - TwC 交互式时间线第 4 部分</span><span class="sxs-lookup"><span data-stu-id="f8d08-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="f8d08-183">非Windows终结点</span><span class="sxs-lookup"><span data-stu-id="f8d08-183">Non-Windows endpoints</span></span>
<span data-ttu-id="f8d08-184">使用 macOS 和 Linux，可以使用几个系统，在 Beta 渠道中运行。</span><span class="sxs-lookup"><span data-stu-id="f8d08-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="f8d08-185">理想情况下，至少一个安全管理员和一个开发人员，以便你能够在生成之前找到兼容性、性能和可靠性问题，然后再进入当前频道。</span><span class="sxs-lookup"><span data-stu-id="f8d08-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="f8d08-186">通道的选择决定了提供给你的设备的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="f8d08-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="f8d08-187">Beta 版设备是接收更新和新功能的第一批设备，随后是预览版，最后是当前设备。</span><span class="sxs-lookup"><span data-stu-id="f8d08-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![预览体验成员圈的图像](images/insider-rings.png)

<span data-ttu-id="f8d08-189">为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用 Beta 或预览版。</span><span class="sxs-lookup"><span data-stu-id="f8d08-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="f8d08-190">在初始安装后切换通道需要重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="f8d08-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="f8d08-191">若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f8d08-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
