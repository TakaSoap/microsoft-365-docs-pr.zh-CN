---
title: 试用 Microsoft Defender for Identity，设置配置基准、标准、指南，并学习有关检测和修正各种标识威胁的教程，如重新检测、凭据泄露、横向移动、域入侵和泄漏警报、执行用户、计算机、实体和横向移动路径调查。
description: 试用 Microsoft Defender for Identity、设置基准、学习有关重新实现、凭据泄露、横向移动、域入侵和泄漏警报等的教程。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457627"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="5fbe2-103">试用 Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5fbe2-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="5fbe2-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5fbe2-104">**Applies to:**</span></span>
- <span data-ttu-id="5fbe2-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fbe2-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="5fbe2-106">本文是设置 Microsoft Defender for Identity 评估环境过程中的第 3 步（第 [3](eval-defender-identity-overview.md) 步）。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="5fbe2-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="5fbe2-108">使用以下步骤为 Microsoft Defender 的标识设置和配置试点。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="5fbe2-109">请注意，建议不包括设置试点组。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="5fbe2-110">最佳做法是继续操作，在运行 Active Directory 域服务 (AD DS) 和 Active Directory 联合服务 (AD FS) 的所有服务器上安装传感器。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![将 Microsoft Defender for Identity 添加到 Defender 评估环境的步骤](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="5fbe2-112">下表介绍了图中的步骤。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="5fbe2-113">步骤 1：为标识环境配置基准建议</span><span class="sxs-lookup"><span data-stu-id="5fbe2-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="5fbe2-114">步骤 2：试用功能 - 演练用于识别和修正不同攻击类型的教程 </span><span class="sxs-lookup"><span data-stu-id="5fbe2-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="5fbe2-115">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="5fbe2-115">Step 1.</span></span> <span data-ttu-id="5fbe2-116">为标识环境配置基准建议</span><span class="sxs-lookup"><span data-stu-id="5fbe2-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="5fbe2-117">Microsoft 为使用 Microsoft 云服务的客户提供安全基准建议。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="5fbe2-118">[Azure 安全](/security/benchmark/azure/overview)基准 (ASB) 提供了说明性最佳做法和建议，以帮助提高 Azure 上的工作负载、数据和服务的安全性。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="5fbe2-119">这些基准建议包括 Microsoft Defender 标识 的 [Azure 安全基线](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="5fbe2-120">实施这些建议可能需要一些时间来计划和实现。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="5fbe2-121">虽然这将大大提高标识环境的安全性，但不应阻止你继续评估和实现 Microsoft Defender for Identity。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="5fbe2-122">此处提供了这些信息，以用于你的了解。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="5fbe2-123">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="5fbe2-123">Step 2.</span></span> <span data-ttu-id="5fbe2-124">试用功能 - 演练用于识别和修正不同攻击类型的教程</span><span class="sxs-lookup"><span data-stu-id="5fbe2-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="5fbe2-125">Microsoft Defender for Identity 文档包括一系列教程，这些教程演示了识别和修正各种攻击类型的过程。</span><span class="sxs-lookup"><span data-stu-id="5fbe2-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="5fbe2-126">试用 Defender for Identity 教程：</span><span class="sxs-lookup"><span data-stu-id="5fbe2-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="5fbe2-127">重新警报</span><span class="sxs-lookup"><span data-stu-id="5fbe2-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="5fbe2-128">凭据泄露警报</span><span class="sxs-lookup"><span data-stu-id="5fbe2-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="5fbe2-129">横向移动警报</span><span class="sxs-lookup"><span data-stu-id="5fbe2-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="5fbe2-130">域警报</span><span class="sxs-lookup"><span data-stu-id="5fbe2-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="5fbe2-131">Exfiltration 警报</span><span class="sxs-lookup"><span data-stu-id="5fbe2-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="5fbe2-132">调查用户</span><span class="sxs-lookup"><span data-stu-id="5fbe2-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="5fbe2-133">调查计算机</span><span class="sxs-lookup"><span data-stu-id="5fbe2-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="5fbe2-134">调查横向移动路径</span><span class="sxs-lookup"><span data-stu-id="5fbe2-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="5fbe2-135">调查实体</span><span class="sxs-lookup"><span data-stu-id="5fbe2-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="5fbe2-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5fbe2-136">Next steps</span></span>

[<span data-ttu-id="5fbe2-137">评估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fbe2-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="5fbe2-138">返回到评估 Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fbe2-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="5fbe2-139">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5fbe2-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>