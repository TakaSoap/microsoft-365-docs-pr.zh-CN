---
title: 试点Microsoft Cloud App Security Microsoft 365 Defender、创建试点组、配置条件访问控制、试用功能、将安装程序作为测试的一Microsoft 365 Defender
description: 设置你的Microsoft 365 Defender试验实验室或试验环境，以测试并体验旨在保护设备、标识、数据和应用程序的安全解决方案。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
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
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457625"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="df2d3-103">试用Microsoft Cloud App Security Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df2d3-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="df2d3-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="df2d3-104">**Applies to:**</span></span>
- <span data-ttu-id="df2d3-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df2d3-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="df2d3-106">本文是设置环境评估环境的第 3 步（第 3 步，第[3](eval-defender-mcas-overview.md)步Microsoft Cloud App Security）。</span><span class="sxs-lookup"><span data-stu-id="df2d3-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="df2d3-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="df2d3-108">使用以下步骤为用户设置和配置Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="df2d3-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![试点计划Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="df2d3-110">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="df2d3-110">Step 1.</span></span> [<span data-ttu-id="df2d3-111">创建试点组 — 将试点部署的范围缩小到某些用户组</span><span class="sxs-lookup"><span data-stu-id="df2d3-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="df2d3-112">步骤 2.配置保护 — 条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="df2d3-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="df2d3-113">步骤 3.试用功能 - 演练用于保护环境的教程</span><span class="sxs-lookup"><span data-stu-id="df2d3-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="df2d3-114">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="df2d3-114">Step 1.</span></span> <span data-ttu-id="df2d3-115">创建试点组 — 将试点部署的范围缩小到某些用户组</span><span class="sxs-lookup"><span data-stu-id="df2d3-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="df2d3-116">Microsoft Cloud App Security允许您确定部署的范围。</span><span class="sxs-lookup"><span data-stu-id="df2d3-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="df2d3-117">通过作用域，可以选择要监视的应用或排除在监视之外的某些用户组。</span><span class="sxs-lookup"><span data-stu-id="df2d3-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="df2d3-118">可以包括或排除用户组。</span><span class="sxs-lookup"><span data-stu-id="df2d3-118">You can include or exclude user groups.</span></span> <span data-ttu-id="df2d3-119">若要确定试点部署的范围，请参阅 [作用域部署](/cloud-app-security/scoped-deployment)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="df2d3-120">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="df2d3-120">Step 2.</span></span> <span data-ttu-id="df2d3-121">配置保护 — 条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="df2d3-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="df2d3-122">可以配置的最强大保护之一是条件访问应用控制。</span><span class="sxs-lookup"><span data-stu-id="df2d3-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="df2d3-123">这需要与 Azure AD Azure Active Directory (集成) 。</span><span class="sxs-lookup"><span data-stu-id="df2d3-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="df2d3-124">它允许你将条件访问策略（包括相关策略 (如要求正常运行的设备) 已批准的云应用。</span><span class="sxs-lookup"><span data-stu-id="df2d3-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="df2d3-125">使用 Microsoft Cloud App Security管理 SaaS 应用的第一步是发现它们，然后将其添加到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="df2d3-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="df2d3-126">如果需要发现帮助，请参阅 [发现和管理网络中 SaaS 应用](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="df2d3-127">发现应用后， [将其添加到 Azure AD 租户](/azure/active-directory/manage-apps/add-application-portal)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="df2d3-128">可以通过执行以下操作开始管理这些操作：</span><span class="sxs-lookup"><span data-stu-id="df2d3-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="df2d3-129">首先，在 Azure AD 中，创建新的条件访问策略，并配置为"使用条件访问应用控制"。</span><span class="sxs-lookup"><span data-stu-id="df2d3-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="df2d3-130">这会将请求重定向到云应用安全。</span><span class="sxs-lookup"><span data-stu-id="df2d3-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="df2d3-131">你可以创建一个策略，并添加所有 SaaS 应用到此策略。</span><span class="sxs-lookup"><span data-stu-id="df2d3-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="df2d3-132">接下来，在云应用安全，创建会话策略。</span><span class="sxs-lookup"><span data-stu-id="df2d3-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="df2d3-133">为要应用的每个控件创建一个策略。</span><span class="sxs-lookup"><span data-stu-id="df2d3-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="df2d3-134">有关详细信息，包括受支持的应用和客户端，请参阅使用条件访问应用Microsoft Cloud App Security[保护应用](/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="df2d3-135">有关示例策略，请参阅[适用于 SaaS Microsoft Cloud App Security推荐策略](../office-365-security/mcas-saas-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="df2d3-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="df2d3-136">这些策略基于一组 [常见标识](../office-365-security/microsoft-365-policies-configurations.md) 和设备访问策略，这些策略建议作为所有客户的起点。</span><span class="sxs-lookup"><span data-stu-id="df2d3-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="df2d3-137">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="df2d3-137">Step 3.</span></span> <span data-ttu-id="df2d3-138">试用功能 - 演练用于保护环境的教程</span><span class="sxs-lookup"><span data-stu-id="df2d3-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="df2d3-139">本指南Microsoft Cloud App Security包括一系列教程，可帮助你发现风险和保护环境。</span><span class="sxs-lookup"><span data-stu-id="df2d3-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="df2d3-140">请尝试云应用安全教程：</span><span class="sxs-lookup"><span data-stu-id="df2d3-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="df2d3-141">检测可疑用户活动</span><span class="sxs-lookup"><span data-stu-id="df2d3-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="df2d3-142">调查有风险的用户</span><span class="sxs-lookup"><span data-stu-id="df2d3-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="df2d3-143">调查有风险的 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="df2d3-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="df2d3-144">发现和保护敏感信息</span><span class="sxs-lookup"><span data-stu-id="df2d3-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="df2d3-145">实时保护组织的任何应用</span><span class="sxs-lookup"><span data-stu-id="df2d3-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="df2d3-146">阻止下载敏感信息</span><span class="sxs-lookup"><span data-stu-id="df2d3-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="df2d3-147">使用管理员隔离保护文件</span><span class="sxs-lookup"><span data-stu-id="df2d3-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="df2d3-148">在有风险的操作时要求执行逐步身份验证</span><span class="sxs-lookup"><span data-stu-id="df2d3-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="df2d3-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="df2d3-149">Next steps</span></span>

[<span data-ttu-id="df2d3-150">在试点环境中使用Microsoft 365 Defender和响应</span><span class="sxs-lookup"><span data-stu-id="df2d3-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="df2d3-151">返回到评估结果[概述Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df2d3-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="df2d3-152">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df2d3-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>