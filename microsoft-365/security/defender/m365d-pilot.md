---
title: 运行试点 Microsoft 365 Defender 项目
description: 在生产中运行试点 Microsoft 365 Defender 项目，以有效确定 Microsoft 365 Defender 的好处和采用。
keywords: Microsoft 威胁防护试点， 运行 Microsoft 威胁防护试点项目， 评估生产中的 Microsoft 威胁防护， Microsoft 威胁防护试点项目， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
ms.openlocfilehash: 1dd310d962cbce2b339cf09d5be6317c227d3f13
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056455"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="d2bc9-104">运行试点 Microsoft 365 Defender 项目</span><span class="sxs-lookup"><span data-stu-id="d2bc9-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d2bc9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d2bc9-105">**Applies to:**</span></span>
- <span data-ttu-id="d2bc9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2bc9-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="d2bc9-107">本指南通过提供指针来帮助你运行试点项目，以确保你有一个结构良好的计划，指导你完成使用攻击模拟功能，最后结束试点，并提供关键方法，让你反映和记录结果。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![运行 Microsoft 365 Defender 试点的阶段](../../media/pilotphases.png)


<span data-ttu-id="d2bc9-109">运行试点有助于有效地确定采用 Microsoft 365 Defender 的好处。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="d2bc9-110">在生产环境中启用 Microsoft 365 Defender 并启动用例之前，最好先计划确定为试点项目完成的任务并设置成功标准。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="d2bc9-111">如何使用此试点手册</span><span class="sxs-lookup"><span data-stu-id="d2bc9-111">How to use this pilot playbook</span></span>

<span data-ttu-id="d2bc9-112">本指南概述了 Microsoft 365 Defender 以及如何设置试点项目的分步说明。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="d2bc9-113">Microsoft 365 Defender 是一个统一的攻破前和入侵后企业防御套件，在本机协调跨终结点、标识、电子邮件和应用程序的保护、检测、预防、调查和响应，以提供针对复杂攻击的集成保护。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="d2bc9-114">它通过将以下功能组合并协调到单个安全解决方案中来这样做：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="d2bc9-115">Microsoft Defender for Endpoint， the new name for Microsoft Defender Advanced Threat Protection (endpoints) </span><span class="sxs-lookup"><span data-stu-id="d2bc9-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="d2bc9-116">Microsoft Defender for Office 365，Office 365 ATP 电子邮件 (的新) </span><span class="sxs-lookup"><span data-stu-id="d2bc9-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="d2bc9-117">Microsoft Defender for Identity，Azure ATP 的新名称 (标识) </span><span class="sxs-lookup"><span data-stu-id="d2bc9-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="d2bc9-118">Microsoft Cloud App Security (应用) </span><span class="sxs-lookup"><span data-stu-id="d2bc9-118">Microsoft Cloud App Security (apps)</span></span>

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

<span data-ttu-id="d2bc9-120">借助集成的 Microsoft 365 Defender 解决方案，安全专业人员可以将 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft Cloud App Security 接收的威胁信号汇集在一起，并确定威胁的完整范围和影响、威胁进入环境的方法、其影响以及威胁当前对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="d2bc9-121">Microsoft 365 Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="d2bc9-122">有关详细信息，请参阅 [Microsoft 365 Defender](microsoft-365-defender.md) 概述。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="d2bc9-123">下面的示例时间线因环境中具有正确的资源而异。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="d2bc9-124">一些检测和工作流可能需要比其他检测和工作流更多的学习时间。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-124">Some detections and workflows might need more learning time than the others.</span></span>

![运行 Microsoft 365 Defender 试点的示例时间线](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="d2bc9-126">为了获得最佳结果，请尽可能遵循试点说明。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="d2bc9-127">试点手册阶段</span><span class="sxs-lookup"><span data-stu-id="d2bc9-127">Pilot playbook phases</span></span> 

<span data-ttu-id="d2bc9-128">运行 Microsoft 365 Defender 试点有四个阶段：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="d2bc9-129">阶段</span><span class="sxs-lookup"><span data-stu-id="d2bc9-129">Phase</span></span> | <span data-ttu-id="d2bc9-130">说明</span><span class="sxs-lookup"><span data-stu-id="d2bc9-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="d2bc9-131">规划</span><span class="sxs-lookup"><span data-stu-id="d2bc9-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="d2bc9-132">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="d2bc9-132">~ 1 day</span></span>| <span data-ttu-id="d2bc9-133">了解在运行 Microsoft 365 Defender 试点项目之前需要考虑的问题：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="d2bc9-134">- 范围</span><span class="sxs-lookup"><span data-stu-id="d2bc9-134">- Scope</span></span> <br> <span data-ttu-id="d2bc9-135">- 用例</span><span class="sxs-lookup"><span data-stu-id="d2bc9-135">- Use cases</span></span> <br><span data-ttu-id="d2bc9-136">- 要求：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-136">- Requirements</span></span> <br><span data-ttu-id="d2bc9-137">- 测试计划</span><span class="sxs-lookup"><span data-stu-id="d2bc9-137">- Test plan</span></span> <br> <span data-ttu-id="d2bc9-138">- 成功条件</span><span class="sxs-lookup"><span data-stu-id="d2bc9-138">- Success criteria</span></span> <br> <span data-ttu-id="d2bc9-139">- 记分卡</span><span class="sxs-lookup"><span data-stu-id="d2bc9-139">- Scorecard</span></span> 
| [<span data-ttu-id="d2bc9-140">准备</span><span class="sxs-lookup"><span data-stu-id="d2bc9-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="d2bc9-141">~2 天</span><span class="sxs-lookup"><span data-stu-id="d2bc9-141">~2 days</span></span>|  <span data-ttu-id="d2bc9-142">访问 Microsoft 365 安全中心以设置 Microsoft 365 Defender 试点环境。</span><span class="sxs-lookup"><span data-stu-id="d2bc9-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="d2bc9-143">将指导你：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-143">You'll be guided to:</span></span><br><br><span data-ttu-id="d2bc9-144">- 确定利益干系人并寻求试点签署</span><span class="sxs-lookup"><span data-stu-id="d2bc9-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="d2bc9-145">- 环境注意事项</span><span class="sxs-lookup"><span data-stu-id="d2bc9-145">- Environment considerations</span></span> <br><span data-ttu-id="d2bc9-146">- Access</span><span class="sxs-lookup"><span data-stu-id="d2bc9-146">- Access</span></span> <br><span data-ttu-id="d2bc9-147">- Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="d2bc9-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="d2bc9-148">- 配置顺序</span><span class="sxs-lookup"><span data-stu-id="d2bc9-148">- Configuration order</span></span> <br> <span data-ttu-id="d2bc9-149">- 注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="d2bc9-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="d2bc9-150">- 配置域</span><span class="sxs-lookup"><span data-stu-id="d2bc9-150">- Configure domain</span></span> <br><span data-ttu-id="d2bc9-151">- 分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="d2bc9-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="d2bc9-152">- 在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="d2bc9-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="d2bc9-153">攻击模拟</span><span class="sxs-lookup"><span data-stu-id="d2bc9-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="d2bc9-154">~2 天</span><span class="sxs-lookup"><span data-stu-id="d2bc9-154">~2 days</span></span>| <span data-ttu-id="d2bc9-155">要模拟攻击，将指导你：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="d2bc9-156">- 验证测试环境要求</span><span class="sxs-lookup"><span data-stu-id="d2bc9-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="d2bc9-157">- 运行模拟</span><span class="sxs-lookup"><span data-stu-id="d2bc9-157">-  Run the simulation</span></span> <br><span data-ttu-id="d2bc9-158">- 调查事件</span><span class="sxs-lookup"><span data-stu-id="d2bc9-158">- Investigate an incident</span></span> <br><span data-ttu-id="d2bc9-159">- 解决事件</span><span class="sxs-lookup"><span data-stu-id="d2bc9-159">- resolve the incident</span></span> 
| [<span data-ttu-id="d2bc9-160">结束和摘要</span><span class="sxs-lookup"><span data-stu-id="d2bc9-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="d2bc9-161">~ 1 天</span><span class="sxs-lookup"><span data-stu-id="d2bc9-161">~ 1 day</span></span>| <span data-ttu-id="d2bc9-162">完成此过程后，将指导你：</span><span class="sxs-lookup"><span data-stu-id="d2bc9-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="d2bc9-163">- 完成最终输出</span><span class="sxs-lookup"><span data-stu-id="d2bc9-163">- Go through your final output</span></span><br><span data-ttu-id="d2bc9-164">- 将输出呈现给利益干系人</span><span class="sxs-lookup"><span data-stu-id="d2bc9-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="d2bc9-165">- 提供反馈</span><span class="sxs-lookup"><span data-stu-id="d2bc9-165">- Provide feedback</span></span> <br><span data-ttu-id="d2bc9-166">- 执行以下步骤</span><span class="sxs-lookup"><span data-stu-id="d2bc9-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="d2bc9-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d2bc9-167">Next step</span></span>
|[<span data-ttu-id="d2bc9-168">规划阶段</span><span class="sxs-lookup"><span data-stu-id="d2bc9-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="d2bc9-169">规划 Microsoft 365 Defender 试点项目</span><span class="sxs-lookup"><span data-stu-id="d2bc9-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
