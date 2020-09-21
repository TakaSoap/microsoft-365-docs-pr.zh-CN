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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: bf080fddd7545c4397483c0eba7a010952922e7e
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956305"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="05d2c-104">运行你的试点 Microsoft 威胁防护项目</span><span class="sxs-lookup"><span data-stu-id="05d2c-104">Run your pilot Microsoft Threat Protection project</span></span> 

<span data-ttu-id="05d2c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="05d2c-105">**Applies to:**</span></span>
- <span data-ttu-id="05d2c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="05d2c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="05d2c-107">若要有效地确定 Microsoft 威胁防护 (MTP) 的优势和采用，可以运行试点项目。</span><span class="sxs-lookup"><span data-stu-id="05d2c-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="05d2c-108">在生产环境中启用 Microsoft 威胁防护并从定义的用例开始之前，最好先完成规划过程，以确定在此试点项目中必须完成的任务以及成功条件。</span><span class="sxs-lookup"><span data-stu-id="05d2c-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="05d2c-109">如何使用此试点操作手册</span><span class="sxs-lookup"><span data-stu-id="05d2c-109">How to use this pilot playbook</span></span>

<span data-ttu-id="05d2c-110">本指南概述了 Microsoft 威胁防护以及如何设置试点项目的分步指导。</span><span class="sxs-lookup"><span data-stu-id="05d2c-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![运行 Microsoft 威胁防护试点的各个阶段](../../media/pilotphases.png)

<span data-ttu-id="05d2c-112">下面的示例时间线因您的环境中的资源是否正确而异。</span><span class="sxs-lookup"><span data-stu-id="05d2c-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="05d2c-113">某些检测和工作流可能需要比其他更多的学习时间。</span><span class="sxs-lookup"><span data-stu-id="05d2c-113">Some detections and workflows might need more learning time than the others.</span></span>

![运行 Microsoft 威胁防护试点的示例时间线](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="05d2c-115">为获得最佳结果，请尽可能仔细地执行试点说明。</span><span class="sxs-lookup"><span data-stu-id="05d2c-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="05d2c-116">试点行动手册阶段</span><span class="sxs-lookup"><span data-stu-id="05d2c-116">Pilot playbook phases</span></span> 

<span data-ttu-id="05d2c-117">在运行 Microsoft 威胁防护试点中有四个阶段：</span><span class="sxs-lookup"><span data-stu-id="05d2c-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="05d2c-118">阶段</span><span class="sxs-lookup"><span data-stu-id="05d2c-118">Phase</span></span> | <span data-ttu-id="05d2c-119">说明</span><span class="sxs-lookup"><span data-stu-id="05d2c-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="05d2c-120">![规划](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="05d2c-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="05d2c-121">规划</span><span class="sxs-lookup"><span data-stu-id="05d2c-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="05d2c-122">了解在运行 Microsoft 威胁防护试点项目之前需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="05d2c-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="05d2c-123">-Scope</span><span class="sxs-lookup"><span data-stu-id="05d2c-123">- Scope</span></span> <br> <span data-ttu-id="05d2c-124">-用例</span><span class="sxs-lookup"><span data-stu-id="05d2c-124">- Use cases</span></span> <br><span data-ttu-id="05d2c-125">- 要求：</span><span class="sxs-lookup"><span data-stu-id="05d2c-125">- Requirements</span></span> <br><span data-ttu-id="05d2c-126">-测试计划</span><span class="sxs-lookup"><span data-stu-id="05d2c-126">- Test plan</span></span> <br> <span data-ttu-id="05d2c-127">-成功条件</span><span class="sxs-lookup"><span data-stu-id="05d2c-127">- Success criteria</span></span> <br> <span data-ttu-id="05d2c-128">记分卡</span><span class="sxs-lookup"><span data-stu-id="05d2c-128">- Scorecard</span></span> 
| <span data-ttu-id="05d2c-129">![过程](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="05d2c-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="05d2c-130">过程</span><span class="sxs-lookup"><span data-stu-id="05d2c-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="05d2c-131">访问 Microsoft 365 安全中心以设置你的 Microsoft 威胁防护试点环境。</span><span class="sxs-lookup"><span data-stu-id="05d2c-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="05d2c-132">系统将指导您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05d2c-132">You will be guided to:</span></span><br><br><span data-ttu-id="05d2c-133">-确定利益干系人并寻求你的试点的注销</span><span class="sxs-lookup"><span data-stu-id="05d2c-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="05d2c-134">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="05d2c-134">- Environment considerations</span></span> <br><span data-ttu-id="05d2c-135">-Access</span><span class="sxs-lookup"><span data-stu-id="05d2c-135">- Access</span></span> <br><span data-ttu-id="05d2c-136">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="05d2c-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="05d2c-137">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="05d2c-137">- Configuration order</span></span> <br> <span data-ttu-id="05d2c-138">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="05d2c-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="05d2c-139">-配置域</span><span class="sxs-lookup"><span data-stu-id="05d2c-139">- Configure domain</span></span> <br><span data-ttu-id="05d2c-140">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="05d2c-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="05d2c-141">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="05d2c-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="05d2c-142">![攻击模拟](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="05d2c-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="05d2c-143">攻击模拟</span><span class="sxs-lookup"><span data-stu-id="05d2c-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="05d2c-144">为模拟攻击，您将获得以下指导：</span><span class="sxs-lookup"><span data-stu-id="05d2c-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="05d2c-145">-验证测试环境要求</span><span class="sxs-lookup"><span data-stu-id="05d2c-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="05d2c-146">-运行模拟</span><span class="sxs-lookup"><span data-stu-id="05d2c-146">-  Run the simulation</span></span> <br><span data-ttu-id="05d2c-147">-调查事件</span><span class="sxs-lookup"><span data-stu-id="05d2c-147">- Investigate an incident</span></span> <br><span data-ttu-id="05d2c-148">-解决事件</span><span class="sxs-lookup"><span data-stu-id="05d2c-148">- resolve the incident</span></span> 
| <span data-ttu-id="05d2c-149">![结束和摘要](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="05d2c-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="05d2c-150">结束和摘要</span><span class="sxs-lookup"><span data-stu-id="05d2c-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="05d2c-151">当您到达进程的末尾时，您将被指引到：</span><span class="sxs-lookup"><span data-stu-id="05d2c-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="05d2c-152">-转到最终输出</span><span class="sxs-lookup"><span data-stu-id="05d2c-152">- Go through your final output</span></span><br><span data-ttu-id="05d2c-153">-向你的利益干系人提供你的输出</span><span class="sxs-lookup"><span data-stu-id="05d2c-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="05d2c-154">-提供反馈</span><span class="sxs-lookup"><span data-stu-id="05d2c-154">- Provide feedback</span></span> <br><span data-ttu-id="05d2c-155">-执行后续步骤</span><span class="sxs-lookup"><span data-stu-id="05d2c-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="05d2c-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="05d2c-156">Next step</span></span>
|<span data-ttu-id="05d2c-157">![规划阶段](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="05d2c-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="05d2c-158">规划阶段</span><span class="sxs-lookup"><span data-stu-id="05d2c-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="05d2c-159">规划 Microsoft 威胁防护试点项目</span><span class="sxs-lookup"><span data-stu-id="05d2c-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
