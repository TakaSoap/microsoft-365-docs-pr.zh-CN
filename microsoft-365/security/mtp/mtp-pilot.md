---
title: 运行你的试点 Microsoft 威胁防护项目
description: 在生产中运行试点 Microsoft 威胁防护项目，以有效确定 Microsoft 威胁防护 (MTP) 的优势和采用情况。
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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477014"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="9e308-104">运行你的试点 Microsoft 威胁防护项目</span><span class="sxs-lookup"><span data-stu-id="9e308-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e308-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9e308-105">**Applies to:**</span></span>
- <span data-ttu-id="9e308-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9e308-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9e308-107">若要有效地确定 Microsoft 威胁防护 (MTP) 的优势和采用，可以运行试点项目。</span><span class="sxs-lookup"><span data-stu-id="9e308-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="9e308-108">在生产环境中启用 Microsoft 威胁防护并启动用例之前，最好先计划确定要为试点项目完成的任务并设置成功条件。</span><span class="sxs-lookup"><span data-stu-id="9e308-108">Before enabling Microsoft Threat Protection in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="9e308-109">如何使用此试点操作手册</span><span class="sxs-lookup"><span data-stu-id="9e308-109">How to use this pilot playbook</span></span>

<span data-ttu-id="9e308-110">本指南概述了 Microsoft 威胁防护以及有关如何设置试点项目的分步说明。</span><span class="sxs-lookup"><span data-stu-id="9e308-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="9e308-111">Microsoft 威胁防护是一种统一的前期和后入侵型企业防护套件，它通过终结点、标识、电子邮件和应用程序固有协调保护、检测、预防、调查和响应，以提供针对复杂攻击的集成保护。</span><span class="sxs-lookup"><span data-stu-id="9e308-111">Microsoft Threat Protection is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="9e308-112">它通过将以下功能组合并协调为一个安全解决方案来实现此操作：</span><span class="sxs-lookup"><span data-stu-id="9e308-112">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="9e308-113">Microsoft defender for Endpoint，Microsoft Defender 高级威胁防护的新名称 (终结点) </span><span class="sxs-lookup"><span data-stu-id="9e308-113">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="9e308-114">Microsoft Defender for Office 365，Office 365 ATP 的新名称 (电子邮件) </span><span class="sxs-lookup"><span data-stu-id="9e308-114">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="9e308-115">Microsoft Defender for Identity，Azure ATP 的新名称 (标识) </span><span class="sxs-lookup"><span data-stu-id="9e308-115">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="9e308-116">Microsoft 云应用安全 (应用程序) </span><span class="sxs-lookup"><span data-stu-id="9e308-116">Microsoft Cloud App Security (apps)</span></span>

![<span data-ttu-id="9e308-117">Image of_Microsoft 威胁防护解决方案，适用于用户、Azure 高级威胁防护、用于终结点的 Microsoft Defender 高级威胁防护、云应用、Microsoft 云应用安全性和数据（Office 365 高级威胁防护）</span><span class="sxs-lookup"><span data-stu-id="9e308-117">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp/m365pillars.png)

<span data-ttu-id="9e308-118">借助集成的 Microsoft 威胁防护解决方案，安全专家可以结合使用 Microsoft Defender 高级威胁防护、Office 365 ATP、Azure ATP 和 Microsoft 云应用安全接收的威胁，并确定威胁的完整范围和影响、它如何进入环境、受影响的内容以及当前对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="9e308-118">With the integrated Microsoft Threat Protection solution, security professionals can stitch together the threat signals that Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="9e308-119">Microsoft 威胁防护采用自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户身份。</span><span class="sxs-lookup"><span data-stu-id="9e308-119">Microsoft Threat Protection takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="9e308-120">有关详细信息，请参阅 [Microsoft 威胁防护概述](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 。</span><span class="sxs-lookup"><span data-stu-id="9e308-120">See the [Microsoft Threat Protection overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>

![运行 Microsoft 威胁防护试点的各个阶段](../../media/pilotphases.png)

<span data-ttu-id="9e308-122">下面的示例时间线因您的环境中的资源是否正确而异。</span><span class="sxs-lookup"><span data-stu-id="9e308-122">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="9e308-123">某些检测和工作流可能需要比其他更多的学习时间。</span><span class="sxs-lookup"><span data-stu-id="9e308-123">Some detections and workflows might need more learning time than the others.</span></span>

![运行 Microsoft 威胁防护试点的示例时间线](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="9e308-125">为获得最佳结果，请尽可能仔细地执行试点说明。</span><span class="sxs-lookup"><span data-stu-id="9e308-125">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="9e308-126">试点行动手册阶段</span><span class="sxs-lookup"><span data-stu-id="9e308-126">Pilot playbook phases</span></span> 

<span data-ttu-id="9e308-127">在运行 Microsoft 威胁防护试点中有四个阶段：</span><span class="sxs-lookup"><span data-stu-id="9e308-127">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="9e308-128">阶段</span><span class="sxs-lookup"><span data-stu-id="9e308-128">Phase</span></span> | <span data-ttu-id="9e308-129">说明</span><span class="sxs-lookup"><span data-stu-id="9e308-129">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="9e308-130">![规划](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="9e308-130">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="9e308-131">规划</span><span class="sxs-lookup"><span data-stu-id="9e308-131">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="9e308-132">了解在运行 Microsoft 威胁防护试点项目之前需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="9e308-132">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="9e308-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="9e308-133">- Scope</span></span> <br> <span data-ttu-id="9e308-134">-用例</span><span class="sxs-lookup"><span data-stu-id="9e308-134">- Use cases</span></span> <br><span data-ttu-id="9e308-135">- 要求：</span><span class="sxs-lookup"><span data-stu-id="9e308-135">- Requirements</span></span> <br><span data-ttu-id="9e308-136">-测试计划</span><span class="sxs-lookup"><span data-stu-id="9e308-136">- Test plan</span></span> <br> <span data-ttu-id="9e308-137">-成功条件</span><span class="sxs-lookup"><span data-stu-id="9e308-137">- Success criteria</span></span> <br> <span data-ttu-id="9e308-138">记分卡</span><span class="sxs-lookup"><span data-stu-id="9e308-138">- Scorecard</span></span> 
| <span data-ttu-id="9e308-139">![过程](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="9e308-139">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="9e308-140">过程</span><span class="sxs-lookup"><span data-stu-id="9e308-140">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="9e308-141">访问 Microsoft 365 安全中心以设置你的 Microsoft 威胁防护试点环境。</span><span class="sxs-lookup"><span data-stu-id="9e308-141">Access Microsoft 365 Security Center to set up your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="9e308-142">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e308-142">You'll be guided to:</span></span><br><br><span data-ttu-id="9e308-143">-确定利益干系人并寻求你的试点的注销</span><span class="sxs-lookup"><span data-stu-id="9e308-143">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="9e308-144">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="9e308-144">- Environment considerations</span></span> <br><span data-ttu-id="9e308-145">-Access</span><span class="sxs-lookup"><span data-stu-id="9e308-145">- Access</span></span> <br><span data-ttu-id="9e308-146">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="9e308-146">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="9e308-147">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="9e308-147">- Configuration order</span></span> <br> <span data-ttu-id="9e308-148">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="9e308-148">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="9e308-149">-配置域</span><span class="sxs-lookup"><span data-stu-id="9e308-149">- Configure domain</span></span> <br><span data-ttu-id="9e308-150">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="9e308-150">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="9e308-151">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="9e308-151">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="9e308-152">![攻击模拟](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="9e308-152">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="9e308-153">攻击模拟</span><span class="sxs-lookup"><span data-stu-id="9e308-153">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="9e308-154">为模拟攻击，您将获得以下指导：</span><span class="sxs-lookup"><span data-stu-id="9e308-154">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="9e308-155">-验证测试环境要求</span><span class="sxs-lookup"><span data-stu-id="9e308-155">- Verify the test environment requirements</span></span> <br><span data-ttu-id="9e308-156">-运行模拟</span><span class="sxs-lookup"><span data-stu-id="9e308-156">-  Run the simulation</span></span> <br><span data-ttu-id="9e308-157">-调查事件</span><span class="sxs-lookup"><span data-stu-id="9e308-157">- Investigate an incident</span></span> <br><span data-ttu-id="9e308-158">-解决事件</span><span class="sxs-lookup"><span data-stu-id="9e308-158">- resolve the incident</span></span> 
| <span data-ttu-id="9e308-159">![结束和摘要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="9e308-159">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="9e308-160">结束和摘要</span><span class="sxs-lookup"><span data-stu-id="9e308-160">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="9e308-161">当您到达进程的末尾时，您将被指引到：</span><span class="sxs-lookup"><span data-stu-id="9e308-161">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="9e308-162">-转到最终输出</span><span class="sxs-lookup"><span data-stu-id="9e308-162">- Go through your final output</span></span><br><span data-ttu-id="9e308-163">-向你的利益干系人提供你的输出</span><span class="sxs-lookup"><span data-stu-id="9e308-163">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="9e308-164">-提供反馈</span><span class="sxs-lookup"><span data-stu-id="9e308-164">- Provide feedback</span></span> <br><span data-ttu-id="9e308-165">-执行后续步骤</span><span class="sxs-lookup"><span data-stu-id="9e308-165">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="9e308-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9e308-166">Next step</span></span>
|<span data-ttu-id="9e308-167">![规划阶段](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="9e308-167">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="9e308-168">规划阶段</span><span class="sxs-lookup"><span data-stu-id="9e308-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="9e308-169">规划 Microsoft 威胁防护试点项目</span><span class="sxs-lookup"><span data-stu-id="9e308-169">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
