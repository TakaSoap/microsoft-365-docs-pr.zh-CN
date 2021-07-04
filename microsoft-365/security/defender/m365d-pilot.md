---
title: 运行试点Microsoft 365 Defender项目
description: 在生产中Microsoft 365 Defender试点项目，以有效确定项目的好处和Microsoft 365 Defender。
keywords: Microsoft 365 Defender试点、运行试点 Microsoft 365 Defender 项目、评估生产中的 Microsoft 365 Defender、Microsoft 365 Defender 试验项目、网络安全、高级永久性威胁、企业安全、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
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
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289951"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="e00d0-104">运行试点Microsoft 365 Defender项目</span><span class="sxs-lookup"><span data-stu-id="e00d0-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e00d0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e00d0-105">**Applies to:**</span></span>
- <span data-ttu-id="e00d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e00d0-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e00d0-107">本指南通过提供指针来帮助你运行试点项目，以确保你有一个结构良好的计划，指导你完成使用攻击模拟功能，最后结束试点，并提供关键方法，让你反映和记录结果。</span><span class="sxs-lookup"><span data-stu-id="e00d0-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![运行测试试点Microsoft 365 Defender阶段](../../media/pilotphases.png)


<span data-ttu-id="e00d0-109">运行试点有助于有效地确定采用Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="e00d0-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="e00d0-110">在生产Microsoft 365 Defender启用项目并启动用例之前，最好先规划确定要为试点项目完成的任务并设置成功条件。</span><span class="sxs-lookup"><span data-stu-id="e00d0-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="e00d0-111">如何使用此试点手册</span><span class="sxs-lookup"><span data-stu-id="e00d0-111">How to use this pilot playbook</span></span>

<span data-ttu-id="e00d0-112">本指南概述了Microsoft 365 Defender如何设置试点项目的指南和分步说明。</span><span class="sxs-lookup"><span data-stu-id="e00d0-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="e00d0-113">Microsoft 365 Defender是一个统一的攻破前和入侵后企业防御套件，在本机协调跨终结点、标识、电子邮件和应用程序的保护、检测、预防、调查和响应，以针对复杂的攻击提供集成保护。</span><span class="sxs-lookup"><span data-stu-id="e00d0-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="e00d0-114">它通过将以下功能组合并协调到单个安全解决方案中来这样做：</span><span class="sxs-lookup"><span data-stu-id="e00d0-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>

- <span data-ttu-id="e00d0-115">Microsoft Defender for Endpoint (终结点) </span><span class="sxs-lookup"><span data-stu-id="e00d0-115">Microsoft Defender for Endpoint (endpoints)</span></span>
- <span data-ttu-id="e00d0-116">Microsoft Defender for Office 365 (电子邮件) </span><span class="sxs-lookup"><span data-stu-id="e00d0-116">Microsoft Defender for Office 365 (email)</span></span>
- <span data-ttu-id="e00d0-117">Microsoft Defender 标识 (标识) </span><span class="sxs-lookup"><span data-stu-id="e00d0-117">Microsoft Defender for Identity (identity)</span></span>
- <span data-ttu-id="e00d0-118">Microsoft Cloud App Security (应用) </span><span class="sxs-lookup"><span data-stu-id="e00d0-118">Microsoft Cloud App Security (apps)</span></span>

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

<span data-ttu-id="e00d0-120">借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 接收的威胁信号汇集在一起，并确定威胁的完整范围和影响、威胁进入环境的方法、对环境的影响以及威胁当前对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="e00d0-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="e00d0-121">Microsoft 365 Defender采取自动操作来阻止或停止攻击和自修复受影响的邮箱、终结点和用户标识。</span><span class="sxs-lookup"><span data-stu-id="e00d0-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="e00d0-122">有关详细信息[，Microsoft 365 Defender](microsoft-365-defender.md)概述。</span><span class="sxs-lookup"><span data-stu-id="e00d0-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>

<span data-ttu-id="e00d0-123">下面的示例时间线因环境中具有正确的资源而异。</span><span class="sxs-lookup"><span data-stu-id="e00d0-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="e00d0-124">一些检测和工作流可能需要比其他检测和工作流更多的学习时间。</span><span class="sxs-lookup"><span data-stu-id="e00d0-124">Some detections and workflows might need more learning time than the others.</span></span>

![运行测试试点Microsoft 365 Defender时间线](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> <span data-ttu-id="e00d0-126">为了获得最佳结果，请尽可能遵循试点说明。</span><span class="sxs-lookup"><span data-stu-id="e00d0-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>

### <a name="pilot-playbook-phases"></a><span data-ttu-id="e00d0-127">试点手册阶段</span><span class="sxs-lookup"><span data-stu-id="e00d0-127">Pilot playbook phases</span></span>

<span data-ttu-id="e00d0-128">运行测试试点有四Microsoft 365 Defender阶段：</span><span class="sxs-lookup"><span data-stu-id="e00d0-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="e00d0-129">阶段</span><span class="sxs-lookup"><span data-stu-id="e00d0-129">Phase</span></span> | <span data-ttu-id="e00d0-130">说明</span><span class="sxs-lookup"><span data-stu-id="e00d0-130">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="e00d0-131">规划</span><span class="sxs-lookup"><span data-stu-id="e00d0-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="e00d0-132">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="e00d0-132">~ 1 day</span></span>| <span data-ttu-id="e00d0-133">了解在运行试点项目之前需要考虑Microsoft 365 Defender哪些方面：</span><span class="sxs-lookup"><span data-stu-id="e00d0-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="e00d0-134">- 范围</span><span class="sxs-lookup"><span data-stu-id="e00d0-134">- Scope</span></span> <br> <span data-ttu-id="e00d0-135">- 用例</span><span class="sxs-lookup"><span data-stu-id="e00d0-135">- Use cases</span></span> <br><span data-ttu-id="e00d0-136">- 要求：</span><span class="sxs-lookup"><span data-stu-id="e00d0-136">- Requirements</span></span> <br><span data-ttu-id="e00d0-137">- 测试计划</span><span class="sxs-lookup"><span data-stu-id="e00d0-137">- Test plan</span></span> <br> <span data-ttu-id="e00d0-138">- 成功条件</span><span class="sxs-lookup"><span data-stu-id="e00d0-138">- Success criteria</span></span> <br> <span data-ttu-id="e00d0-139">- 记分卡</span><span class="sxs-lookup"><span data-stu-id="e00d0-139">- Scorecard</span></span> 
| [<span data-ttu-id="e00d0-140">准备</span><span class="sxs-lookup"><span data-stu-id="e00d0-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="e00d0-141">~2 天</span><span class="sxs-lookup"><span data-stu-id="e00d0-141">~2 days</span></span>|  <span data-ttu-id="e00d0-142">访问Microsoft 365安全中心，以设置Microsoft 365 Defender环境。</span><span class="sxs-lookup"><span data-stu-id="e00d0-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="e00d0-143">将指导你：</span><span class="sxs-lookup"><span data-stu-id="e00d0-143">You'll be guided to:</span></span><br><br><span data-ttu-id="e00d0-144">- 确定利益干系人并寻求试点签署</span><span class="sxs-lookup"><span data-stu-id="e00d0-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="e00d0-145">- 环境注意事项</span><span class="sxs-lookup"><span data-stu-id="e00d0-145">- Environment considerations</span></span> <br><span data-ttu-id="e00d0-146">- Access</span><span class="sxs-lookup"><span data-stu-id="e00d0-146">- Access</span></span> <br><span data-ttu-id="e00d0-147">- Azure Active Directory安装程序</span><span class="sxs-lookup"><span data-stu-id="e00d0-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e00d0-148">- 配置顺序</span><span class="sxs-lookup"><span data-stu-id="e00d0-148">- Configuration order</span></span> <br> <span data-ttu-id="e00d0-149">- 注册Microsoft 365 E5试用版</span><span class="sxs-lookup"><span data-stu-id="e00d0-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="e00d0-150">- 配置域</span><span class="sxs-lookup"><span data-stu-id="e00d0-150">- Configure domain</span></span> <br><span data-ttu-id="e00d0-151">- 分配Microsoft 365 E5许可证</span><span class="sxs-lookup"><span data-stu-id="e00d0-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="e00d0-152">- 在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="e00d0-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="e00d0-153">攻击模拟</span><span class="sxs-lookup"><span data-stu-id="e00d0-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="e00d0-154">~2 天</span><span class="sxs-lookup"><span data-stu-id="e00d0-154">~2 days</span></span>| <span data-ttu-id="e00d0-155">要模拟攻击，将指导你：</span><span class="sxs-lookup"><span data-stu-id="e00d0-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="e00d0-156">- 验证测试环境要求</span><span class="sxs-lookup"><span data-stu-id="e00d0-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="e00d0-157">- 运行模拟</span><span class="sxs-lookup"><span data-stu-id="e00d0-157">-  Run the simulation</span></span> <br><span data-ttu-id="e00d0-158">- 调查事件</span><span class="sxs-lookup"><span data-stu-id="e00d0-158">- Investigate an incident</span></span> <br><span data-ttu-id="e00d0-159">- 解决事件</span><span class="sxs-lookup"><span data-stu-id="e00d0-159">- resolve the incident</span></span> 
| [<span data-ttu-id="e00d0-160">结束和摘要</span><span class="sxs-lookup"><span data-stu-id="e00d0-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="e00d0-161">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="e00d0-161">~ 1 day</span></span>| <span data-ttu-id="e00d0-162">完成此过程后，将指导你：</span><span class="sxs-lookup"><span data-stu-id="e00d0-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="e00d0-163">- 完成最终输出</span><span class="sxs-lookup"><span data-stu-id="e00d0-163">- Go through your final output</span></span><br><span data-ttu-id="e00d0-164">- 将输出呈现给利益干系人</span><span class="sxs-lookup"><span data-stu-id="e00d0-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="e00d0-165">- 提供反馈</span><span class="sxs-lookup"><span data-stu-id="e00d0-165">- Provide feedback</span></span> <br><span data-ttu-id="e00d0-166">- 执行以下步骤</span><span class="sxs-lookup"><span data-stu-id="e00d0-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="e00d0-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e00d0-167">Next step</span></span>

|[<span data-ttu-id="e00d0-168">规划阶段</span><span class="sxs-lookup"><span data-stu-id="e00d0-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="e00d0-169">规划Microsoft 365 Defender试点项目</span><span class="sxs-lookup"><span data-stu-id="e00d0-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
