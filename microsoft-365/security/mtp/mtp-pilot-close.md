---
title: 概述你的试点 Microsoft 365 Defender 项目结果
description: 通过完成您的记分卡、分析报告结果和决定如何向前移动，来结束试点 Microsoft 365 Defender 项目。
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
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130913"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="bdf48-104">关闭并汇总你的 Microsoft 365 Defender 试点</span><span class="sxs-lookup"><span data-stu-id="bdf48-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bdf48-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bdf48-105">**Applies to:**</span></span>
- <span data-ttu-id="bdf48-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdf48-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="bdf48-107">[![规划](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="bdf48-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="bdf48-108">规划</span><span class="sxs-lookup"><span data-stu-id="bdf48-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="bdf48-109">[![准备](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="bdf48-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="bdf48-110">过程</span><span class="sxs-lookup"><span data-stu-id="bdf48-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="bdf48-111">[![模拟攻击](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="bdf48-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="bdf48-112">模拟攻击</span><span class="sxs-lookup"><span data-stu-id="bdf48-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![结束和汇总](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="bdf48-114">结束和汇总</span><span class="sxs-lookup"><span data-stu-id="bdf48-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="bdf48-115">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="bdf48-115">*You are here!*</span></span>|


<span data-ttu-id="bdf48-116">你当前处于结束和汇总阶段。</span><span class="sxs-lookup"><span data-stu-id="bdf48-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="bdf48-117">您刚刚运行了仅在域控制器上远程执行了代码的高级内存攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="bdf48-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="bdf48-118">你已了解 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 检测和创建有关 stealthy 恶意活动的警报的方式。</span><span class="sxs-lookup"><span data-stu-id="bdf48-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="bdf48-119">您还了解了不同源中的警报如何与其他上下文信息一起传递到 Microsoft 365 安全中心门户中的单个事件。</span><span class="sxs-lookup"><span data-stu-id="bdf48-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="bdf48-120">如果遇到此类集成，SOC 分析师可以调查并采取必要的措施。</span><span class="sxs-lookup"><span data-stu-id="bdf48-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="bdf48-121">你还创建了一个高级的搜寻查询，该查询将标识入站电子邮件，用户在该查询中打开或保存了附件并根据该查询创建了检测。</span><span class="sxs-lookup"><span data-stu-id="bdf48-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="bdf48-122">在所有测试结束后，你已到达进程的末尾。</span><span class="sxs-lookup"><span data-stu-id="bdf48-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="bdf48-123">最终输出应为：</span><span class="sxs-lookup"><span data-stu-id="bdf48-123">The final output should be:</span></span>

- <span data-ttu-id="bdf48-124">已完成的记分卡</span><span class="sxs-lookup"><span data-stu-id="bdf48-124">A completed scorecard</span></span>
- <span data-ttu-id="bdf48-125">有关试点结果的详细报告</span><span class="sxs-lookup"><span data-stu-id="bdf48-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="bdf48-126">有关如何向前移动的决策</span><span class="sxs-lookup"><span data-stu-id="bdf48-126">A decision on how to move forward</span></span>

<span data-ttu-id="bdf48-127">将最终输出中的报告呈现给内部利益干系人， (在 [准备](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 阶段) 和 Microsoft 联系人中确定。</span><span class="sxs-lookup"><span data-stu-id="bdf48-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="bdf48-128">这样的努力可确保任何反馈都可用于改进产品和文档。</span><span class="sxs-lookup"><span data-stu-id="bdf48-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="bdf48-129">我们希望你喜欢此模拟。</span><span class="sxs-lookup"><span data-stu-id="bdf48-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="bdf48-130">开始实施您在组织中的更大范围内学习的内容，以充分利用集成安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdf48-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="bdf48-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bdf48-131">Next step</span></span>
<span data-ttu-id="bdf48-132">通过以下交互指南了解有关 Microsoft 365 Defender 支柱的详细信息：</span><span class="sxs-lookup"><span data-stu-id="bdf48-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="bdf48-133">使用 Microsoft Defender for Office 365 保护你的组织</span><span class="sxs-lookup"><span data-stu-id="bdf48-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="bdf48-134">了解如何通过 Microsoft Defender for Identity 检测可疑活动和潜在攻击</span><span class="sxs-lookup"><span data-stu-id="bdf48-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="bdf48-135">检测威胁并使用 Microsoft 云应用安全管理警报</span><span class="sxs-lookup"><span data-stu-id="bdf48-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="bdf48-136">调查和修正与 Microsoft Defender for Endpoint 的威胁</span><span class="sxs-lookup"><span data-stu-id="bdf48-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
