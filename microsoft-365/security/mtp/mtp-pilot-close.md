---
title: 概述你的试点 Microsoft 威胁防护项目结果
description: 通过完成您的记分卡、分析报告结果和决定如何继续进行，来结束试点 Microsoft 威胁防护项目。
keywords: Microsoft 威胁 Protection 试点，决定在试点 Microsoft 威胁防护项目后如何执行下一步操作，评估 Microsoft 威胁防护在生产环境中，从 Microsoft 威胁防护试点转换为部署、网络安全、高级持久威胁、企业安全性、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
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
ms.openlocfilehash: 1a7b87432ce1eb16c29f462fb4865bfa5c5e2201
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418093"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="5054a-104">关闭并汇总你的 Microsoft 威胁防护试点</span><span class="sxs-lookup"><span data-stu-id="5054a-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5054a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5054a-105">**Applies to:**</span></span>
- <span data-ttu-id="5054a-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5054a-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="规划你的试点 Microsoft 威胁防护项目" />
      <br/><span data-ttu-id="5054a-108">制定 </a></span><span class="sxs-lookup"><span data-stu-id="5054a-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="准备你的 Microsoft 威胁防护试用实验室或试点环境" />
      <br/><span data-ttu-id="5054a-110">份 </a></span><span class="sxs-lookup"><span data-stu-id="5054a-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="运行 Microsoft 威胁防护攻击模拟" />
      <br/><span data-ttu-id="5054a-112">模拟攻击 </a></span><span class="sxs-lookup"><span data-stu-id="5054a-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="关闭并汇总你的 Microsoft 威胁防护试点" />
      <br/><span data-ttu-id="5054a-114">结束和汇总 </a></span><span class="sxs-lookup"><span data-stu-id="5054a-114">Close and summarize </a></span></span><br>
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

<span data-ttu-id="5054a-115">你当前处于结束和汇总阶段。</span><span class="sxs-lookup"><span data-stu-id="5054a-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="5054a-116">您刚刚运行了仅在域控制器上远程执行了代码的高级内存攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="5054a-116">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="5054a-117">你已了解 Microsoft Defender ATP 和 Azure ATP 如何检测和创建有关 stealthy 恶意活动的警报。</span><span class="sxs-lookup"><span data-stu-id="5054a-117">You’ve seen how Microsoft Defender ATP and Azure ATP detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="5054a-118">您还了解了不同源中的警报如何与其他上下文信息一起传递到 Microsoft 365 安全中心门户中的单个事件。</span><span class="sxs-lookup"><span data-stu-id="5054a-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="5054a-119">如果遇到此类集成，SOC 分析师可以调查并采取必要的措施。</span><span class="sxs-lookup"><span data-stu-id="5054a-119">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="5054a-120">你还创建了一个高级的搜寻查询，该查询将标识入站电子邮件，用户在该查询中打开或保存了附件并根据该查询创建了检测。</span><span class="sxs-lookup"><span data-stu-id="5054a-120">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="5054a-121">在所有测试结束后，你已到达进程的末尾。</span><span class="sxs-lookup"><span data-stu-id="5054a-121">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="5054a-122">最终输出应为：</span><span class="sxs-lookup"><span data-stu-id="5054a-122">The final output should be:</span></span>

- <span data-ttu-id="5054a-123">已完成的记分卡</span><span class="sxs-lookup"><span data-stu-id="5054a-123">A completed scorecard</span></span>
- <span data-ttu-id="5054a-124">有关试点结果的详细报告</span><span class="sxs-lookup"><span data-stu-id="5054a-124">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="5054a-125">有关如何向前移动的决策</span><span class="sxs-lookup"><span data-stu-id="5054a-125">A decision on how to move forward</span></span>

<span data-ttu-id="5054a-126">显示最终输出中的报告内部利益干系人 (在 [准备](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 阶段) 和 Microsoft 联系人中确定。</span><span class="sxs-lookup"><span data-stu-id="5054a-126">Present the reports from your final output both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="5054a-127">这样的努力可确保任何反馈都可用于改进产品和文档。</span><span class="sxs-lookup"><span data-stu-id="5054a-127">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="5054a-128">我们希望你喜欢此模拟。</span><span class="sxs-lookup"><span data-stu-id="5054a-128">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="5054a-129">开始实施您在组织中的更大范围内学习的内容，以充分利用集成安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="5054a-129">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="5054a-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5054a-130">Next step</span></span>
<span data-ttu-id="5054a-131">通过以下交互式指南详细了解 Microsoft 威胁防护支柱：</span><span class="sxs-lookup"><span data-stu-id="5054a-131">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="5054a-132">使用 Microsoft Defender for Office 365 保护你的组织</span><span class="sxs-lookup"><span data-stu-id="5054a-132">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="5054a-133">使用 Microsoft Defender for Identity 检测可疑活动和潜在攻击</span><span class="sxs-lookup"><span data-stu-id="5054a-133">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="5054a-134">检测威胁并使用 Microsoft 云应用安全管理警报</span><span class="sxs-lookup"><span data-stu-id="5054a-134">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="5054a-135">调查和修正与 Microsoft Defender for Endpoint 的威胁</span><span class="sxs-lookup"><span data-stu-id="5054a-135">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
