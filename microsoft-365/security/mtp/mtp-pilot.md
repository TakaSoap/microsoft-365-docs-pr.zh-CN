---
title: 运行你的试点 Microsoft 365 Defender 项目
description: 在生产中运行试点 Microsoft 365 Defender 项目，以有效确定 Microsoft 365 Defender 的优势和采用情况。
keywords: Microsoft 威胁防护试点，运行试点 Microsoft 威胁防护项目，评估 Microsoft 威胁防护在生产中，Microsoft 威胁防护试点项目，网络安全，高级持久威胁，企业安全性，设备，设备，标识，用户，数据，应用程序，事件，自动化调查和修正，高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131219"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="b5656-104">运行你的试点 Microsoft 365 Defender 项目</span><span class="sxs-lookup"><span data-stu-id="b5656-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5656-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b5656-105">**Applies to:**</span></span>
- <span data-ttu-id="b5656-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5656-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b5656-107">若要有效地确定 Microsoft 365 Defender 的优势和采用情况，可以运行试点项目。</span><span class="sxs-lookup"><span data-stu-id="b5656-107">To effectively determine the benefit and adoption of Microsoft 365 Defender, you can run a pilot project.</span></span> <span data-ttu-id="b5656-108">在生产环境中启用 Microsoft 365 Defender 并启动用例之前，最好先计划确定要为试点项目完成的任务并设置成功条件。</span><span class="sxs-lookup"><span data-stu-id="b5656-108">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="b5656-109">如何使用此试点操作手册</span><span class="sxs-lookup"><span data-stu-id="b5656-109">How to use this pilot playbook</span></span>

<span data-ttu-id="b5656-110">本指南概述了 Microsoft 365 Defender 以及有关如何设置试点项目的分步说明。</span><span class="sxs-lookup"><span data-stu-id="b5656-110">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="b5656-111">Microsoft 365 Defender 是一个统一的前期和后入侵后企业防护套件，它在各个终结点、标识、电子邮件和应用程序中以本地方式协调保护、检测、预防、调查和响应，以提供针对复杂攻击的集成保护。</span><span class="sxs-lookup"><span data-stu-id="b5656-111">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="b5656-112">它通过将以下功能组合并协调为一个安全解决方案来实现此操作：</span><span class="sxs-lookup"><span data-stu-id="b5656-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="b5656-113">Microsoft defender for Endpoint，Microsoft Defender 高级威胁防护的新名称 (终结点) </span><span class="sxs-lookup"><span data-stu-id="b5656-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="b5656-114">Microsoft Defender for Office 365，Office 365 ATP 的新名称 (电子邮件) </span><span class="sxs-lookup"><span data-stu-id="b5656-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="b5656-115">Microsoft Defender for Identity，Azure ATP 的新名称 (标识) </span><span class="sxs-lookup"><span data-stu-id="b5656-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="b5656-116">Microsoft 云应用安全 (应用程序) </span><span class="sxs-lookup"><span data-stu-id="b5656-116">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender 解决方案，适用于用户、Microsoft Defender for a Endpoint for Microsoft Defender for Endpoint、云应用、Microsoft 云应用安全性和数据、Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="b5656-118">使用集成的 Microsoft 365 Defender 解决方案，安全专家可以将威胁信号与 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity 和 Microsoft 云应用安全接收结合在一起，并确定威胁的完整范围和影响、它如何进入环境、受影响的内容以及当前对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="b5656-118">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="b5656-119">Microsoft 365 Defender 执行自动操作以阻止或停止攻击和自我修复受影响的邮箱、终结点和用户身份。</span><span class="sxs-lookup"><span data-stu-id="b5656-119">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="b5656-120">有关详细信息，请参阅 [Microsoft 365 Defender 概述](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 。</span><span class="sxs-lookup"><span data-stu-id="b5656-120">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![运行 Microsoft 365 Defender 试点的阶段](../../media/pilotphases.png)

<span data-ttu-id="b5656-122">下面的示例时间线因您的环境中的资源是否正确而异。</span><span class="sxs-lookup"><span data-stu-id="b5656-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="b5656-123">某些检测和工作流可能需要比其他更多的学习时间。</span><span class="sxs-lookup"><span data-stu-id="b5656-123">Some detections and workflows might need more learning time than the others.</span></span>

![运行 Microsoft 365 Defender 试点的示例时间线](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="b5656-125">为获得最佳结果，请尽可能仔细地执行试点说明。</span><span class="sxs-lookup"><span data-stu-id="b5656-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="b5656-126">试点行动手册阶段</span><span class="sxs-lookup"><span data-stu-id="b5656-126">Pilot playbook phases</span></span> 

<span data-ttu-id="b5656-127">在运行 Microsoft 365 Defender 试点中有四个阶段：</span><span class="sxs-lookup"><span data-stu-id="b5656-127">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="b5656-128">阶段</span><span class="sxs-lookup"><span data-stu-id="b5656-128">Phase</span></span> | <span data-ttu-id="b5656-129">说明</span><span class="sxs-lookup"><span data-stu-id="b5656-129">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="b5656-130">规划</span><span class="sxs-lookup"><span data-stu-id="b5656-130">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="b5656-131">约1天</span><span class="sxs-lookup"><span data-stu-id="b5656-131">~ 1 day</span></span>| <span data-ttu-id="b5656-132">了解在运行 Microsoft 365 Defender 试点项目之前需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="b5656-132">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="b5656-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="b5656-133">- Scope</span></span> <br> <span data-ttu-id="b5656-134">-用例</span><span class="sxs-lookup"><span data-stu-id="b5656-134">- Use cases</span></span> <br><span data-ttu-id="b5656-135">- 要求：</span><span class="sxs-lookup"><span data-stu-id="b5656-135">- Requirements</span></span> <br><span data-ttu-id="b5656-136">-测试计划</span><span class="sxs-lookup"><span data-stu-id="b5656-136">- Test plan</span></span> <br> <span data-ttu-id="b5656-137">-成功条件</span><span class="sxs-lookup"><span data-stu-id="b5656-137">- Success criteria</span></span> <br> <span data-ttu-id="b5656-138">记分卡</span><span class="sxs-lookup"><span data-stu-id="b5656-138">- Scorecard</span></span> 
| [<span data-ttu-id="b5656-139">过程</span><span class="sxs-lookup"><span data-stu-id="b5656-139">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="b5656-140">约2天</span><span class="sxs-lookup"><span data-stu-id="b5656-140">~2 days</span></span>|  <span data-ttu-id="b5656-141">访问 Microsoft 365 安全中心以设置你的 Microsoft 365 Defender 试点环境。</span><span class="sxs-lookup"><span data-stu-id="b5656-141">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="b5656-142">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5656-142">You'll be guided to:</span></span><br><br><span data-ttu-id="b5656-143">-确定利益干系人并寻求你的试点的注销</span><span class="sxs-lookup"><span data-stu-id="b5656-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="b5656-144">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="b5656-144">- Environment considerations</span></span> <br><span data-ttu-id="b5656-145">-Access</span><span class="sxs-lookup"><span data-stu-id="b5656-145">- Access</span></span> <br><span data-ttu-id="b5656-146">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="b5656-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b5656-147">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="b5656-147">- Configuration order</span></span> <br> <span data-ttu-id="b5656-148">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="b5656-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="b5656-149">-配置域</span><span class="sxs-lookup"><span data-stu-id="b5656-149">- Configure domain</span></span> <br><span data-ttu-id="b5656-150">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="b5656-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="b5656-151">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="b5656-151">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="b5656-152">攻击模拟</span><span class="sxs-lookup"><span data-stu-id="b5656-152">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="b5656-153">约2天</span><span class="sxs-lookup"><span data-stu-id="b5656-153">~2 days</span></span>| <span data-ttu-id="b5656-154">为模拟攻击，您将获得以下指导：</span><span class="sxs-lookup"><span data-stu-id="b5656-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="b5656-155">-验证测试环境要求</span><span class="sxs-lookup"><span data-stu-id="b5656-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="b5656-156">-运行模拟</span><span class="sxs-lookup"><span data-stu-id="b5656-156">-  Run the simulation</span></span> <br><span data-ttu-id="b5656-157">-调查事件</span><span class="sxs-lookup"><span data-stu-id="b5656-157">- Investigate an incident</span></span> <br><span data-ttu-id="b5656-158">-解决事件</span><span class="sxs-lookup"><span data-stu-id="b5656-158">- resolve the incident</span></span> 
| [<span data-ttu-id="b5656-159">结束和摘要</span><span class="sxs-lookup"><span data-stu-id="b5656-159">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="b5656-160">约1天</span><span class="sxs-lookup"><span data-stu-id="b5656-160">~ 1 day</span></span>| <span data-ttu-id="b5656-161">当您到达进程的末尾时，您将被指引到：</span><span class="sxs-lookup"><span data-stu-id="b5656-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="b5656-162">-转到最终输出</span><span class="sxs-lookup"><span data-stu-id="b5656-162">- Go through your final output</span></span><br><span data-ttu-id="b5656-163">-向你的利益干系人提供你的输出</span><span class="sxs-lookup"><span data-stu-id="b5656-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="b5656-164">-提供反馈</span><span class="sxs-lookup"><span data-stu-id="b5656-164">- Provide feedback</span></span> <br><span data-ttu-id="b5656-165">-执行后续步骤</span><span class="sxs-lookup"><span data-stu-id="b5656-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="b5656-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b5656-166">Next step</span></span>
|[<span data-ttu-id="b5656-167">规划阶段</span><span class="sxs-lookup"><span data-stu-id="b5656-167">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="b5656-168">规划 Microsoft 365 Defender 试点项目</span><span class="sxs-lookup"><span data-stu-id="b5656-168">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
