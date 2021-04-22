---
title: 总结试点 Microsoft 365 Defender 项目结果
description: 结束试点 Microsoft 365 Defender 项目，完成记分卡，分析报告结果，并决定如何继续。
keywords: Microsoft 365 Defender 试点，决定在试点 Microsoft 365 Defender 项目后下一步应执行哪些操作，评估生产中的 Microsoft 365 Defender 后应执行哪些操作，从 Microsoft 365 Defender 试点转换到部署、网络安全、高级永久性威胁、企业安全、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932865"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="65d82-104">结束和总结 Microsoft 365 Defender 试点</span><span class="sxs-lookup"><span data-stu-id="65d82-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65d82-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="65d82-105">**Applies to:**</span></span>
- <span data-ttu-id="65d82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65d82-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="65d82-107">[![规划](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="65d82-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="65d82-108">规划</span><span class="sxs-lookup"><span data-stu-id="65d82-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="65d82-109">[![准备](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="65d82-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="65d82-110">准备</span><span class="sxs-lookup"><span data-stu-id="65d82-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="65d82-111">[![模拟攻击](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="65d82-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="65d82-112">模拟攻击</span><span class="sxs-lookup"><span data-stu-id="65d82-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![结束和汇总](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="65d82-114">结束和汇总</span><span class="sxs-lookup"><span data-stu-id="65d82-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="65d82-115">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="65d82-115">*You are here!*</span></span>|


<span data-ttu-id="65d82-116">你目前处于结束和总结阶段。</span><span class="sxs-lookup"><span data-stu-id="65d82-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="65d82-117">你刚刚运行了仅内存的高级攻击模拟，该模拟在域控制器上远程执行代码。</span><span class="sxs-lookup"><span data-stu-id="65d82-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="65d82-118">你已了解 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 如何检测并创建有关恶意活动的警报。</span><span class="sxs-lookup"><span data-stu-id="65d82-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="65d82-119">你还了解如何将来自不同来源的警报以及其他上下文信息传递到 Microsoft 365 安全中心门户中的单个事件。</span><span class="sxs-lookup"><span data-stu-id="65d82-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="65d82-120">通过体验此类集成，SOC 分析师可以进行调查并进行必要的操作。</span><span class="sxs-lookup"><span data-stu-id="65d82-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="65d82-121">你还创建了一个高级搜寻查询，该查询将标识用户打开或保存附件并基于该查询创建检测的入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="65d82-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="65d82-122">在所有测试结束之后，你已到达该过程的结束。</span><span class="sxs-lookup"><span data-stu-id="65d82-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="65d82-123">最终输出应为：</span><span class="sxs-lookup"><span data-stu-id="65d82-123">The final output should be:</span></span>

- <span data-ttu-id="65d82-124">完成的记分卡</span><span class="sxs-lookup"><span data-stu-id="65d82-124">A completed scorecard</span></span>
- <span data-ttu-id="65d82-125">试点结果的详细报告</span><span class="sxs-lookup"><span data-stu-id="65d82-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="65d82-126">如何前进的决定</span><span class="sxs-lookup"><span data-stu-id="65d82-126">A decision on how to move forward</span></span>

<span data-ttu-id="65d82-127">将最终输出中的报告呈现给内部利益干系 (在 Microsoft 联系人和 Microsoft 联系人[](./prepare-m365d-eval.md)的准备阶段) 确定的报告。</span><span class="sxs-lookup"><span data-stu-id="65d82-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="65d82-128">这样做可确保任何反馈都可用于改进产品和文档。</span><span class="sxs-lookup"><span data-stu-id="65d82-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="65d82-129">我们希望您喜欢此模拟。</span><span class="sxs-lookup"><span data-stu-id="65d82-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="65d82-130">开始在组织中大规模实现你学到的知识，以充分使用集成的安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="65d82-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="65d82-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="65d82-131">Next step</span></span>
<span data-ttu-id="65d82-132">通过以下交互式指南详细了解 Microsoft 365 Defender 支柱：</span><span class="sxs-lookup"><span data-stu-id="65d82-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="65d82-133">使用 Microsoft Defender for Office 365 保护组织</span><span class="sxs-lookup"><span data-stu-id="65d82-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="65d82-134">了解如何通过 Microsoft Defender for Identity 检测可疑活动和潜在攻击</span><span class="sxs-lookup"><span data-stu-id="65d82-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="65d82-135">使用 Microsoft Cloud App Security 检测威胁和管理警报</span><span class="sxs-lookup"><span data-stu-id="65d82-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="65d82-136">使用 Microsoft Defender for Endpoint 调查和修正威胁</span><span class="sxs-lookup"><span data-stu-id="65d82-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)