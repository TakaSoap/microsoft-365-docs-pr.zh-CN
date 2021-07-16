---
title: 试用 Microsoft Defender for Endpoint，在评估中设置试点、测试功能
description: 了解如何运行 Microsoft Defender for Endpoint (MDE) 的试点，包括验证试点组和试用功能。
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
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457542"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a><span data-ttu-id="4853a-103">试用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4853a-103">Pilot Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4853a-104">本文将指导你运行 Microsoft Defender for Endpoint 试点的过程。</span><span class="sxs-lookup"><span data-stu-id="4853a-104">This article will guide you in the process of running a pilot for Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="4853a-105">使用以下步骤为 Microsoft Defender for Endpoint 设置和配置试点。</span><span class="sxs-lookup"><span data-stu-id="4853a-105">Use the following steps to setup and configure the pilot for Microsoft Defender for Endpoint.</span></span> 

![将 Microsoft Defender for Identity 添加到 Defender 评估环境的步骤](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- <span data-ttu-id="4853a-107">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="4853a-107">Step 1.</span></span> <span data-ttu-id="4853a-108">验证试点组</span><span class="sxs-lookup"><span data-stu-id="4853a-108">Verify pilot group</span></span>
- <span data-ttu-id="4853a-109">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="4853a-109">Step 2.</span></span> <span data-ttu-id="4853a-110">试用功能</span><span class="sxs-lookup"><span data-stu-id="4853a-110">Try out capabilities</span></span>

<span data-ttu-id="4853a-111">当你试用 Microsoft Defender for Endpoint 时，你可以选择先将一些设备载入服务，然后再载入整个组织。</span><span class="sxs-lookup"><span data-stu-id="4853a-111">When you pilot Microsoft Defender for Endpoint, you may choose to onboard a few devices to the service before onboarding your entire organization.</span></span>  

<span data-ttu-id="4853a-112">然后，你可以试用可用的功能，例如运行攻击模拟，了解 Defender for Endpoint 如何显示恶意活动，并让你进行有效的响应。</span><span class="sxs-lookup"><span data-stu-id="4853a-112">You can then try out capabilities that are available such as running attack simulations and seeing how Defender for Endpoint surfaces malicious activities and enables you to conduct an efficient response.</span></span> 

## <a name="step-1-verify-pilot-group"></a><span data-ttu-id="4853a-113">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="4853a-113">Step 1.</span></span> <span data-ttu-id="4853a-114">验证试点组</span><span class="sxs-lookup"><span data-stu-id="4853a-114">Verify pilot group</span></span>
<span data-ttu-id="4853a-115">完成"启用评估"部分概述的载入步骤后[](eval-defender-endpoint-enable-eval.md)，应大约在一小时后在设备清单列表中看到设备。</span><span class="sxs-lookup"><span data-stu-id="4853a-115">After completing the onboarding steps outlined in the [Enable evaluation](eval-defender-endpoint-enable-eval.md) section, you should see the devices in the Device inventory list approximately after an hour.</span></span> 

<span data-ttu-id="4853a-116">当你看到已载入的设备时，你可以继续尝试功能。</span><span class="sxs-lookup"><span data-stu-id="4853a-116">When you see your onboarded devices you can then proceed with trying out capabilities.</span></span> 

## <a name="step-2-try-out-capabilities"></a><span data-ttu-id="4853a-117">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="4853a-117">Step 2.</span></span> <span data-ttu-id="4853a-118">试用功能</span><span class="sxs-lookup"><span data-stu-id="4853a-118">Try out capabilities</span></span>
<span data-ttu-id="4853a-119">现在，你已完成载入某些设备并验证它们正在向服务报告，请通过尝试现成可用的强大功能来熟悉产品。</span><span class="sxs-lookup"><span data-stu-id="4853a-119">Now that you've completed onboarding some devices and verified that they are reporting to the service, familiarize yourself with the product by trying out the powerful capabilities that are available right out of the box.</span></span>

<span data-ttu-id="4853a-120">在试点期间，你可以轻松开始尝试一些功能以查看产品运行情况，而无需完成复杂的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="4853a-120">During the pilot, you can easily get started with trying out some of the features to see the product in action without going through complex configuration steps.</span></span>

<span data-ttu-id="4853a-121">让我们首先查看仪表板。</span><span class="sxs-lookup"><span data-stu-id="4853a-121">Let's start by checking out the dashboards.</span></span>

### <a name="view-the-device-inventory"></a><span data-ttu-id="4853a-122">查看设备清单</span><span class="sxs-lookup"><span data-stu-id="4853a-122">View the device inventory</span></span>
<span data-ttu-id="4853a-123">设备清单是你将看到网络中终结点、网络设备和 IoT 设备列表的地方。</span><span class="sxs-lookup"><span data-stu-id="4853a-123">The device inventory is where you'll see the list of endpoints, network devices, and IoT devices in your network.</span></span> <span data-ttu-id="4853a-124">它不仅为你提供了网络中设备的视图，还为你提供了有关这些设备的深入信息，例如域、风险级别、操作系统平台和其他详细信息，以便轻松识别风险最大的设备。</span><span class="sxs-lookup"><span data-stu-id="4853a-124">Not only does it provide you with a view of the devices in your network, but it also gives your in-depth information about them such as  domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="4853a-125">查看威胁和漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="4853a-125">View the Threat and vulnerability management dashboard</span></span> 
<span data-ttu-id="4853a-126">威胁漏洞管理可帮助你专注于对组织构成最紧急和最高风险的漏洞。</span><span class="sxs-lookup"><span data-stu-id="4853a-126">Threat and vulnerability management helps you focus on the weaknesses that pose the most urgent and the highest risk to the organization.</span></span> <span data-ttu-id="4853a-127">从仪表板中，获取组织曝光分数、设备的 Microsoft 安全分数、设备曝光分布、顶级安全建议、最易受攻击的软件、顶级修正活动和最公开设备数据等高级视图。</span><span class="sxs-lookup"><span data-stu-id="4853a-127">From the dashboard, get a high-level view of the organization exposure score, Microsoft Secure Score for Devices, device exposure distribution, top security recommendations, top vulnerable software, top remediation activities, and top exposed device data.</span></span> 

### <a name="run-a-simulation"></a><span data-ttu-id="4853a-128">运行模拟</span><span class="sxs-lookup"><span data-stu-id="4853a-128">Run a simulation</span></span>
<span data-ttu-id="4853a-129">Microsoft Defender for Endpoint 附带了 [可在](https://securitycenter.windows.com/tutorials) 试点设备上运行的"自己执行"攻击方案。</span><span class="sxs-lookup"><span data-stu-id="4853a-129">Microsoft Defender for Endpoint comes with ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials) that you can run on your pilot devices.</span></span>  <span data-ttu-id="4853a-130">每个文档都包括操作系统和应用程序要求，以及特定于攻击方案的详细说明。</span><span class="sxs-lookup"><span data-stu-id="4853a-130">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span> <span data-ttu-id="4853a-131">这些脚本安全、有记录且易于使用。</span><span class="sxs-lookup"><span data-stu-id="4853a-131">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="4853a-132">这些方案将反映 Defender for Endpoint 功能，并演练调查体验。</span><span class="sxs-lookup"><span data-stu-id="4853a-132">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

<span data-ttu-id="4853a-133">若要运行任何提供的模拟，你至少需要一 [个已载入的设备](../defender-endpoint/onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4853a-133">To run any of the provided simulations, you need at least [one onboarded device](../defender-endpoint/onboard-configure.md).</span></span>

1. <span data-ttu-id="4853a-134">在  >  **帮助模拟&** 教程中，选择要模拟的可用攻击方案：</span><span class="sxs-lookup"><span data-stu-id="4853a-134">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="4853a-135">**方案 1：文档丢弃后门** - 模拟传递社交工程的诱使文档。</span><span class="sxs-lookup"><span data-stu-id="4853a-135">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="4853a-136">文档启动一个专门设计的后门，该后门为攻击者提供控制。</span><span class="sxs-lookup"><span data-stu-id="4853a-136">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="4853a-137">**方案 2：** 无文件攻击中的 PowerShell 脚本 - 模拟依赖于 PowerShell 的无文件攻击，展示攻击面减少和设备学习检测恶意内存活动。</span><span class="sxs-lookup"><span data-stu-id="4853a-137">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="4853a-138">**方案 3：自动事件响应** - 触发自动调查，自动搜寻并修正泄露项目，从而扩展事件响应容量。</span><span class="sxs-lookup"><span data-stu-id="4853a-138">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="4853a-139">下载并阅读所选方案提供的相应演练文档。</span><span class="sxs-lookup"><span data-stu-id="4853a-139">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="4853a-140">下载模拟文件或复制模拟脚本，方法为导航到帮助模拟  >  **&教程**。</span><span class="sxs-lookup"><span data-stu-id="4853a-140">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="4853a-141">你可以选择在测试设备上下载文件或脚本，但这不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="4853a-141">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="4853a-142">根据演练文档中的指示，在测试设备上运行模拟文件或脚本。</span><span class="sxs-lookup"><span data-stu-id="4853a-142">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="4853a-143">模拟文件或脚本模拟攻击活动，但实际上是恶意的，不会损害或损害测试设备。</span><span class="sxs-lookup"><span data-stu-id="4853a-143">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4853a-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4853a-144">Next steps</span></span>
[<span data-ttu-id="4853a-145">评估Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4853a-145">Evaluate Microsoft Cloud App Security</span></span>](eval-defender-mcas-overview.md)

<span data-ttu-id="4853a-146">返回到评估 Microsoft [Defender for Endpoint 的概述](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4853a-146">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="4853a-147">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4853a-147">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>