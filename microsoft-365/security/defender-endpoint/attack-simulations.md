---
title: 通过模拟攻击体验 Microsoft Defender ATP
description: 运行提供的攻击方案模拟，以体验 Microsoft Defender ATP 如何检测、调查和响应泄露。
keywords: wdatp， 测试， 方案， 攻击， 模拟， 模拟， diy， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498305"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="28815-104">通过模拟攻击体验 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28815-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28815-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28815-105">**Applies to:**</span></span>
- [<span data-ttu-id="28815-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28815-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="28815-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28815-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="28815-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="28815-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28815-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28815-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="28815-110">了解 Microsoft Defender ATP 中的最新增强功能[：Defender for Endpoint 中的新增功能是什么？。](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="28815-110">Learn about the latest enhancements in Microsoft Defender ATP: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="28815-111">Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。</span><span class="sxs-lookup"><span data-stu-id="28815-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="28815-112">阅读 [：MITRE ATT 中的见解&基于 CK 的评估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="28815-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="28815-113">在将多个设备载入服务之前，你可能想要体验 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="28815-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="28815-114">为此，可以在一些测试设备上运行受控攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="28815-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="28815-115">运行模拟攻击后，你可以查看 Defender for Endpoint 如何显示恶意活动，并探索它如何启用有效的响应。</span><span class="sxs-lookup"><span data-stu-id="28815-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28815-116">准备工作</span><span class="sxs-lookup"><span data-stu-id="28815-116">Before you begin</span></span>

<span data-ttu-id="28815-117">若要运行任何提供的模拟，你至少需要一 [个已载入的设备](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="28815-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="28815-118">阅读每个攻击方案提供的演练文档。</span><span class="sxs-lookup"><span data-stu-id="28815-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="28815-119">每个文档都包括操作系统和应用程序要求，以及特定于攻击方案的详细说明。</span><span class="sxs-lookup"><span data-stu-id="28815-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="28815-120">运行模拟</span><span class="sxs-lookup"><span data-stu-id="28815-120">Run a simulation</span></span>

1. <span data-ttu-id="28815-121">在  >  **帮助模拟&** 教程中，选择要模拟的可用攻击方案：</span><span class="sxs-lookup"><span data-stu-id="28815-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="28815-122">**方案 1：文档丢弃后门** - 模拟传递社交工程的诱使文档。</span><span class="sxs-lookup"><span data-stu-id="28815-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="28815-123">文档启动一个专门设计的后门，该后门为攻击者提供控制。</span><span class="sxs-lookup"><span data-stu-id="28815-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="28815-124">**方案 2：** 无文件攻击中的 PowerShell 脚本 - 模拟依赖于 PowerShell 的无文件攻击，展示攻击面减少和设备学习检测恶意内存活动。</span><span class="sxs-lookup"><span data-stu-id="28815-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="28815-125">**方案 3：自动事件响应** - 触发自动调查，自动搜寻并修正泄露项目，从而扩展事件响应容量。</span><span class="sxs-lookup"><span data-stu-id="28815-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="28815-126">下载并阅读所选方案提供的相应演练文档。</span><span class="sxs-lookup"><span data-stu-id="28815-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="28815-127">下载模拟文件或复制模拟脚本，方法为导航到帮助模拟  >  **&教程**。</span><span class="sxs-lookup"><span data-stu-id="28815-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="28815-128">你可以选择在测试设备上下载文件或脚本，但这不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="28815-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="28815-129">根据演练文档中的指示，在测试设备上运行模拟文件或脚本。</span><span class="sxs-lookup"><span data-stu-id="28815-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="28815-130">模拟文件或脚本模拟攻击活动，但实际上是恶意的，不会损害或损害测试设备。</span><span class="sxs-lookup"><span data-stu-id="28815-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="28815-131">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="28815-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28815-132">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28815-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="28815-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="28815-133">Related topics</span></span>

- [<span data-ttu-id="28815-134">载入设备</span><span class="sxs-lookup"><span data-stu-id="28815-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="28815-135">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28815-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
