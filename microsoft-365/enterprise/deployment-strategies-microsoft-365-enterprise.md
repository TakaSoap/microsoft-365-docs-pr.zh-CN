---
title: Microsoft 365 企业版底层基础结构部署策略
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解部署 Microsoft 365 企业版底层基础结构阶段的一些方法。
ms.openlocfilehash: 909526fb4938c8da142b4f667140f10dda660877
ms.sourcegitcommit: 6f94b7a272e33c492957336eae28f439e438c85b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "29993233"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="86fb6-103">Microsoft 365 企业版底层基础结构部署策略</span><span class="sxs-lookup"><span data-stu-id="86fb6-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="86fb6-p101">你可以通过多种方式部署 Microsoft 365 企业版[底层基础结构](deploy-foundation-infrastructure.md)的各个阶段，并向用户推出其功能、软件和服务。为了帮助你快速开始这项工作的项目管理（根据你的组织规模和现有基础结构，此工作可能十分庞大而复杂），请考虑以下部署策略：</span><span class="sxs-lookup"><span data-stu-id="86fb6-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="86fb6-106">串行部署</span><span class="sxs-lookup"><span data-stu-id="86fb6-106">Serial deployment</span></span>
- <span data-ttu-id="86fb6-107">并行部署与非重叠用户推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="86fb6-108">并行部署与重叠用户推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="86fb6-109">前端基础结构和端到端配置推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="86fb6-110">使用这些策略可以获得有关如何管理整个项目的思路，并更快实现 Microsoft 365 企业版带来的业务优势。</span><span class="sxs-lookup"><span data-stu-id="86fb6-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="86fb6-p102">本文做了一些假设和简化，目的是使用一致的方式描述部署策略。这些部署策略是概括性的，并不暗示任何特定的时间范围，也不表示适用于所有组织和情况。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="86fb6-113">典型企业组织的 IT 项目管理要素</span><span class="sxs-lookup"><span data-stu-id="86fb6-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="86fb6-p103">IT基础结构包括后端服务以及向最终用户推出新功能或改进功能功能或者安装的软件。IT 部门通常采用一种有条理的方式部署 IT 基础结构的元素。成功部署 IT 基础结构元素的一种方法应包括：</span><span class="sxs-lookup"><span data-stu-id="86fb6-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="86fb6-117">试点推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-117">A pilot rollout</span></span> 

  <span data-ttu-id="86fb6-118">此过程包括初始基础结构配置、向一组试点用户推出、测试以及对基础结构配置进行后续修改。</span><span class="sxs-lookup"><span data-stu-id="86fb6-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="86fb6-119">用户推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-119">A user rollout</span></span>

  <span data-ttu-id="86fb6-120">此过程包括根据区域、部门、组或其他类型的系统传播配置或软件向组织的其余人员推出。</span><span class="sxs-lookup"><span data-stu-id="86fb6-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="86fb6-121">试点推出与用户推出中的用户集不同。</span><span class="sxs-lookup"><span data-stu-id="86fb6-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="86fb6-122">本文使用以下图形来描述这些定义：</span><span class="sxs-lookup"><span data-stu-id="86fb6-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="86fb6-123">在用户推出图形中，阴影表示在整个组织内使用结构化或有条理的方法（如组、部门或区域）从 0% 到 100% 的百分比。</span><span class="sxs-lookup"><span data-stu-id="86fb6-123">The shading for the user rollout graphic indicates the rollout across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="86fb6-124">部署策略</span><span class="sxs-lookup"><span data-stu-id="86fb6-124">Deployment strategies</span></span>

<span data-ttu-id="86fb6-125">请考虑以下部署策略：</span><span class="sxs-lookup"><span data-stu-id="86fb6-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="86fb6-126">串行部署</span><span class="sxs-lookup"><span data-stu-id="86fb6-126">Serial deployment</span></span>
- <span data-ttu-id="86fb6-127">并行部署与非重叠用户推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="86fb6-128">并行部署与重叠用户推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="86fb6-129">前端基础结构和端到端配置推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="86fb6-130">串行部署</span><span class="sxs-lookup"><span data-stu-id="86fb6-130">Serial deployment</span></span>

<span data-ttu-id="86fb6-p104">通过串行部署，你可以完全推出一个阶段，使该阶段达到面向所有用户的 100% 部署完成度，然后再进入下一个阶段。可采用这种部署方式的一些原因如下：</span><span class="sxs-lookup"><span data-stu-id="86fb6-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="86fb6-133">风险缓解</span><span class="sxs-lookup"><span data-stu-id="86fb6-133">Risk mitigation</span></span>
- <span data-ttu-id="86fb6-134">资源分配限制</span><span class="sxs-lookup"><span data-stu-id="86fb6-134">Resourcing constraints</span></span>
- <span data-ttu-id="86fb6-135">IT 部门资金周期</span><span class="sxs-lookup"><span data-stu-id="86fb6-135">IT department funding cycles</span></span>
- <span data-ttu-id="86fb6-136">IT 技术依赖</span><span class="sxs-lookup"><span data-stu-id="86fb6-136">IT technology dependencies</span></span>
- <span data-ttu-id="86fb6-137">业务变更管理和最终用户阻力</span><span class="sxs-lookup"><span data-stu-id="86fb6-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="86fb6-138">以下甘特图显示了 Microsoft 365 企业版基础结构第 2-6 阶段的简化串行部署情况。</span><span class="sxs-lookup"><span data-stu-id="86fb6-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="86fb6-139">为了简化讨论和示意，假设每个阶段以及每个阶段中的部署细分段花费相同的时间量。</span><span class="sxs-lookup"><span data-stu-id="86fb6-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="86fb6-p105">第 1 阶段：Microsoft 365 企业版底层基础结构的网络是仅限于 IT 部门的阶段。用户可受益于与 Microsoft 云资源的优化连接，但不会强制用户实现此目标。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="86fb6-142">简化的试点用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="86fb6-p106">12 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p107">3 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p108">6 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p109">9 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p110">12 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-153">结果是在连续的试点推出之间保持 90 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="86fb6-154">简化的最终用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="86fb6-p111">1 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p112">4 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p113">7 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p114">10 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p115">下一年的 1 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-165">结果是在连续的用户推出之间保持 90 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="86fb6-166">此部署策略的缺点是完全部署 Microsoft 365 企业版底层基础结构可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="86fb6-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="86fb6-167">并行部署与非重叠用户推出（并行 1）</span><span class="sxs-lookup"><span data-stu-id="86fb6-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="86fb6-p116">对于此部署策略，你将在当前阶段的用户推出的最后一部分期间开始下一阶段的试点推出。以下是前一阶段的用户推出即将结束期间执行试点推出时的第 2-6 阶段的部署。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="86fb6-170">下面是并行和串行部署策略之间的简化比较。</span><span class="sxs-lookup"><span data-stu-id="86fb6-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="86fb6-p117">最终结果是，当前阶段的用户推出将在整个组织中完成，然后启动下一个阶段。不在试点推出中的用户不会同时处理多个阶段的推出，但试点推出与用户推出并行完成。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="86fb6-173">简化的试点用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="86fb6-p118">12 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p119">2 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p120">4 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p121">6 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p122">8 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-184">结果是在连续的试点推出之间保持 60 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="86fb6-185">简化的最终用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="86fb6-p123">1 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p124">3 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p125">5 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p126">7 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p127">9 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-196">结果是在连续的用户推出之间保持 60 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="86fb6-197">此部署策略的优势在于，可以花费更少的时间来完全部署 Microsoft 365 企业版底层基础结构，无需 IT 部门和用户同时处理多个推出。</span><span class="sxs-lookup"><span data-stu-id="86fb6-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="86fb6-198">并行部署与重叠用户推出（并行 2）</span><span class="sxs-lookup"><span data-stu-id="86fb6-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="86fb6-199">对于此部署策略：</span><span class="sxs-lookup"><span data-stu-id="86fb6-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="86fb6-200">在当前阶段的用户推出的最后一部分期间，你需要开始下一阶段的试点推出。</span><span class="sxs-lookup"><span data-stu-id="86fb6-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="86fb6-p128">在当前阶段的用户推出期间，你需要开始下一阶段的用户推出，确保用户不会同时处理多个阶段的推出。这里假设你通过区域、部门或其他单位以相同的方式推出底层基础结构的每个阶段。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="86fb6-203">下面是不同部署策略之间的简化比较。</span><span class="sxs-lookup"><span data-stu-id="86fb6-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="86fb6-204">最终结果是：</span><span class="sxs-lookup"><span data-stu-id="86fb6-204">The end result is that:</span></span>

- <span data-ttu-id="86fb6-205">试点推出从一个阶段进入到下一阶段，中间没有暂停。</span><span class="sxs-lookup"><span data-stu-id="86fb6-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="86fb6-206">在前一阶段的用户推出完成之前开始后一阶段的用户推出，但是不会有任何单个用户一次推出多个阶段。</span><span class="sxs-lookup"><span data-stu-id="86fb6-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="86fb6-207">简化的试点用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="86fb6-p129">12 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p130">1 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p131">2 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p132">3 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p133">4 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-218">结果是在连续的试点推出之间保持 30 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="86fb6-219">简化的最终用户体验示例：</span><span class="sxs-lookup"><span data-stu-id="86fb6-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="86fb6-p134">1 月，需要使用智能手机进行 MFA。（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="86fb6-p135">2 月，在 Windows 8.1 台式机上安装 Windows 10 企业版。（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-p136">3 月，安装 Office 365 专业增强版，取代 Office 2013。（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-p137">4 月，执行设备注册并实施应用和条件访问策略。（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-p138">5 月，安装 Azure 信息保护客户端，并接受关于如何将标签应用于文档的培训。（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="86fb6-230">结果是在连续的用户推出之间保持 30 天节奏。</span><span class="sxs-lookup"><span data-stu-id="86fb6-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="86fb6-p139">此部署策略的优势在于，可以花费更少的时间来完全部署 Microsoft 365 企业版底层基础结构，仍然无需各个用户同时处理多个推出。但是，用户不会在连续阶段之间休息。</span><span class="sxs-lookup"><span data-stu-id="86fb6-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="86fb6-233">前端基础结构和端到端配置推出</span><span class="sxs-lookup"><span data-stu-id="86fb6-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="86fb6-234">对于能够将第 2-6 阶段压缩到单个部署细分段的小型组织，部署结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="86fb6-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="86fb6-p140">IT 部门针对第 2-6 阶段配置基础结构，然后推出给试点用户以检查端到端功能。例如，试点用户同时获得所有以下功能：</span><span class="sxs-lookup"><span data-stu-id="86fb6-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="86fb6-237">MFA 和其他身份识别功能（身份识别）</span><span class="sxs-lookup"><span data-stu-id="86fb6-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="86fb6-238">Windows 设备上的 Windows 10 企业版（Windows 10 企业版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="86fb6-239">Office 套件的 Office 365 专业增强版（Office 365 专业增强版）</span><span class="sxs-lookup"><span data-stu-id="86fb6-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="86fb6-240">应用和条件访问策略（移动设备管理）</span><span class="sxs-lookup"><span data-stu-id="86fb6-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="86fb6-241">安装 Azure 信息保护客户端并接受关于如何将标签应用于文档的培训（信息保护）</span><span class="sxs-lookup"><span data-stu-id="86fb6-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="86fb6-242">一旦试点推出结束，用户推出便开始，在此过程中每个用户同时获得所有功能。</span><span class="sxs-lookup"><span data-stu-id="86fb6-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="86fb6-243">后续步骤</span><span class="sxs-lookup"><span data-stu-id="86fb6-243">Next step</span></span>

<span data-ttu-id="86fb6-244">开始部署 Microsoft 365 企业版和[底层基础结构](deploy-foundation-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="86fb6-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
