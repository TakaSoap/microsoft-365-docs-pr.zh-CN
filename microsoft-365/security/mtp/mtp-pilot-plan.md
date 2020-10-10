---
title: 规划你的试点 Microsoft 威胁防护项目
description: 使用利益干系人规划试点 Microsoft 威胁防护项目，以管理预期并确保成功的结果。
keywords: Microsoft 威胁防护试点，规划试点 Microsoft 威胁防护项目，评估 Microsoft 威胁防护在生产中，Microsoft 威胁防护试点项目，网络安全，高级持久威胁，企业安全性，设备，设备，标识，用户，数据，应用程序，事件，自动化调查和修正，高级搜寻
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: e62b4ec0ee6c9d05321accf269406e8127019f5b
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418105"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="8e6cb-104">规划你的试点 Microsoft 威胁防护项目</span><span class="sxs-lookup"><span data-stu-id="8e6cb-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8e6cb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8e6cb-105">**Applies to:**</span></span>
- <span data-ttu-id="8e6cb-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8e6cb-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="规划你的试点 Microsoft 威胁防护项目" />
      <br/><span data-ttu-id="8e6cb-108">计划</a></span><span class="sxs-lookup"><span data-stu-id="8e6cb-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="准备你的 Microsoft 威胁防护试用实验室或试点环境" />
      <br/><span data-ttu-id="8e6cb-110">准备</a></span><span class="sxs-lookup"><span data-stu-id="8e6cb-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="运行 Microsoft 威胁防护攻击模拟" />
     <br/><span data-ttu-id="8e6cb-112">模拟攻击</a></span><span class="sxs-lookup"><span data-stu-id="8e6cb-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="关闭并汇总你的 Microsoft 威胁防护试点" />
     <br/><span data-ttu-id="8e6cb-114">结束和汇总</a></span><span class="sxs-lookup"><span data-stu-id="8e6cb-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="8e6cb-115">你当前正在计划阶段。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="8e6cb-116">为确保您的试点项目成功，必须在开始时全面规划和获取利益干系人的批准。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="8e6cb-117">规划的元素包括标识范围、用例、要求和成功条件。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="8e6cb-118">本指南将指导你如何规划你的试点项目。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="8e6cb-119">为获得最佳结果，请尽可能仔细地执行试点说明。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="8e6cb-120">范围</span><span class="sxs-lookup"><span data-stu-id="8e6cb-120">Scope</span></span>

<span data-ttu-id="8e6cb-121">试验的范围将根据您的环境和可接受的测试方法确定测试的范围。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="8e6cb-122">下面是一些需要考虑的示例范围：</span><span class="sxs-lookup"><span data-stu-id="8e6cb-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="8e6cb-123">包含终结点、服务器和域控制器的开发或测试环境。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="8e6cb-124">使用 Microsoft 365、Azure、Active Directory 服务、终结点和服务器的生产环境</span><span class="sxs-lookup"><span data-stu-id="8e6cb-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="8e6cb-125">如果你还没有完全许可证，可以获取试用版许可证来 [评估 Microsoft 威胁防护](https://aka.ms/mtp-trial-lab) –规划、准备、设置、配置和运行你的试点项目。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="8e6cb-126">你的利益干系人将在帮助促进从开始到完成的过程中发挥重要作用。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="8e6cb-127">要评估的操作系统的类型还应根据组织的构成进行定义。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="8e6cb-128">这可能包括以下内容： [Mac 终结点](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、 [Linux 服务器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、 [windows 10 终结点](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、 [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="8e6cb-129">用例</span><span class="sxs-lookup"><span data-stu-id="8e6cb-129">Use cases</span></span>

<span data-ttu-id="8e6cb-130">用例表示要测试的工具应由其预期用户使用的声明。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="8e6cb-131">可以从特定角色（如 SOC 分析师）的角度来制定用户情景。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="8e6cb-132">例如：</span><span class="sxs-lookup"><span data-stu-id="8e6cb-132">For example:</span></span>
- <span data-ttu-id="8e6cb-133">作为 SOC 分析师，我需要在网络中的设备、用户和邮箱之间查看、关联、评估和管理警报和事件。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="8e6cb-134">[事件管理]</span><span class="sxs-lookup"><span data-stu-id="8e6cb-134">[Incident management]</span></span>
- <span data-ttu-id="8e6cb-135">作为 SOC 分析师，我必须具有工具和过程来自动调查网络中的恶意事件并对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="8e6cb-136">[自动红外线]</span><span class="sxs-lookup"><span data-stu-id="8e6cb-136">[Auto IR]</span></span>
- <span data-ttu-id="8e6cb-137">作为 SOC 分析师，我必须从我的环境中搜索数据，以找出已知的和潜在的威胁以及可疑的活动。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="8e6cb-138">[高级搜寻]</span><span class="sxs-lookup"><span data-stu-id="8e6cb-138">[Advanced Hunting]</span></span>

<span data-ttu-id="8e6cb-139">请记住，应在定义的作用域的参数中创建这些用例。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="8e6cb-140">例如，如果测试范围不包括 Microsoft 云应用安全性等工具的评估，则不应创建依赖此数据源的用例。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e6cb-141">要求</span><span class="sxs-lookup"><span data-stu-id="8e6cb-141">Requirements</span></span>

<span data-ttu-id="8e6cb-142">在用例列表中，您可以开始创建要求。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="8e6cb-143">要求包含工具必须具备的功能才能满足用例。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="8e6cb-144">这些要求可以分解为多个类别，如配置和维护、支持集成以及特定于功能的要求（如搜寻能力和构建自定义警报的能力）。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="8e6cb-145">测试计划</span><span class="sxs-lookup"><span data-stu-id="8e6cb-145">Test plan</span></span>

<span data-ttu-id="8e6cb-146">根据要求的不同，可能适合测试的不同方法。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="8e6cb-147">例如，如果要求是评估自动修正的 efficacy，则测试计划需要包括生成在 Microsoft 威胁防护中将触发自动修正操作的行为 () s 的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="8e6cb-148">如果要求是检测特定行为或攻击，则测试可能会涉及更多步骤。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="8e6cb-149">这样一点是制定一个适当的计划，以准确地针对您的要求进行测试。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="8e6cb-150">成功条件</span><span class="sxs-lookup"><span data-stu-id="8e6cb-150">Success criteria</span></span>

<span data-ttu-id="8e6cb-151">成功条件最终将设置为针对要测试的内容进行度量的条形图。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="8e6cb-152">无论您是要测试 Microsoft 威胁防护 (还是针对其他工具或其本身的任何其他技术) ，都必须有一些可量化的条件来确定该工具提供的值。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="8e6cb-153">根据范围、要求和测试计划，成功条件将确定如何对测试进行评分。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="8e6cb-154">根据你的需要，此过程应不只是通过或失败，更多的加权计分。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="8e6cb-155">例如，若要成功，工具可能需要在您确定的某些关键区域中得分超过80%。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="8e6cb-156">记分卡</span><span class="sxs-lookup"><span data-stu-id="8e6cb-156">Scorecard</span></span>

<span data-ttu-id="8e6cb-157">将计划的所有元素组合在一起的一种方法就是创建记分卡。</span><span class="sxs-lookup"><span data-stu-id="8e6cb-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="8e6cb-158">请参阅下面的示例记分卡：</span><span class="sxs-lookup"><span data-stu-id="8e6cb-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="8e6cb-159">用例</span><span class="sxs-lookup"><span data-stu-id="8e6cb-159">Use case</span></span> | <span data-ttu-id="8e6cb-160">要求</span><span class="sxs-lookup"><span data-stu-id="8e6cb-160">Requirements</span></span> | <span data-ttu-id="8e6cb-161">配置要求</span><span class="sxs-lookup"><span data-stu-id="8e6cb-161">Configuration requirements</span></span> | <span data-ttu-id="8e6cb-162">测试计划</span><span class="sxs-lookup"><span data-stu-id="8e6cb-162">Test plan</span></span> | <span data-ttu-id="8e6cb-163">预期结果</span><span class="sxs-lookup"><span data-stu-id="8e6cb-163">Expected outcome</span></span> | <span data-ttu-id="8e6cb-164">测试状态</span><span class="sxs-lookup"><span data-stu-id="8e6cb-164">Test status</span></span> | <span data-ttu-id="8e6cb-165">得分</span><span class="sxs-lookup"><span data-stu-id="8e6cb-165">Score</span></span> | <span data-ttu-id="8e6cb-166">注释</span><span class="sxs-lookup"><span data-stu-id="8e6cb-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="8e6cb-167">事件管理</span><span class="sxs-lookup"><span data-stu-id="8e6cb-167">Incident management</span></span>|<span data-ttu-id="8e6cb-168">-Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8e6cb-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="8e6cb-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-169">- Azure ATP</span></span> </br></br><span data-ttu-id="8e6cb-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="8e6cb-171">-Microsoft 云应用安全 (可选) </span><span class="sxs-lookup"><span data-stu-id="8e6cb-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="8e6cb-172">有关详细信息，请参阅准备、设置和配置的[先决条件](https://aka.ms/mtp-trial-lab)</span><span class="sxs-lookup"><span data-stu-id="8e6cb-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="8e6cb-173">模拟攻击</span><span class="sxs-lookup"><span data-stu-id="8e6cb-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="8e6cb-174">调查事件</span><span class="sxs-lookup"><span data-stu-id="8e6cb-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="8e6cb-175">调查人员可以了解事件的范围和影响并管理事件</span><span class="sxs-lookup"><span data-stu-id="8e6cb-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="8e6cb-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="8e6cb-176">AutoIR</span></span>|<span data-ttu-id="8e6cb-177">-Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8e6cb-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="8e6cb-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-178">- Azure ATP</span></span> </br></br><span data-ttu-id="8e6cb-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="8e6cb-180">有关详细信息，请参阅准备、设置和配置的[先决条件](https://aka.ms/mtp-trial-lab)</span><span class="sxs-lookup"><span data-stu-id="8e6cb-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="8e6cb-181">启用 AutoIR</span><span class="sxs-lookup"><span data-stu-id="8e6cb-181">Enable AutoIR</span></span>  |[<span data-ttu-id="8e6cb-182">模拟攻击</span><span class="sxs-lookup"><span data-stu-id="8e6cb-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="8e6cb-183">自动调查</span><span class="sxs-lookup"><span data-stu-id="8e6cb-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="8e6cb-184">Microsoft 威胁防护会自动修正警报和事件</span><span class="sxs-lookup"><span data-stu-id="8e6cb-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="8e6cb-185">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="8e6cb-185">Advanced hunting</span></span>|<span data-ttu-id="8e6cb-186">-Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8e6cb-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="8e6cb-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="8e6cb-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8e6cb-188">- Office 365 ATP</span></span>   |<span data-ttu-id="8e6cb-189">有关详细信息，请参阅准备、设置和配置的[先决条件](https://aka.ms/mtp-trial-lab)</span><span class="sxs-lookup"><span data-stu-id="8e6cb-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="8e6cb-190">高级搜寻方案</span><span class="sxs-lookup"><span data-stu-id="8e6cb-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="8e6cb-191">调查人员可以通过高级搜索、旋转受影响的实体和创建自定义检测来查找数据</span><span class="sxs-lookup"><span data-stu-id="8e6cb-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="8e6cb-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8e6cb-192">Next step</span></span>
|<span data-ttu-id="8e6cb-193">![准备阶段](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="8e6cb-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="8e6cb-194">准备阶段</span><span class="sxs-lookup"><span data-stu-id="8e6cb-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="8e6cb-195">准备你的 Microsoft 威胁防护试点环境</span><span class="sxs-lookup"><span data-stu-id="8e6cb-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
