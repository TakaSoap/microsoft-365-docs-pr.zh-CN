---
title: 评估 Microsoft 365 Defender
description: 设置你的Microsoft 365 Defender试验实验室或试验环境，以试用并体验旨在保护组织中设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457711"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="ed28d-104">创建Microsoft 365 Defender试验实验室或试验环境</span><span class="sxs-lookup"><span data-stu-id="ed28d-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ed28d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ed28d-105">**Applies to:**</span></span>
- <span data-ttu-id="ed28d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="ed28d-107">本指南可帮助你通过用户和组设置实验室环境，然后指导你完成 Microsoft 365 Defender 中的功能配置，以便你可以模拟威胁攻击并获得有意义的试验结果。</span><span class="sxs-lookup"><span data-stu-id="ed28d-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="ed28d-108">创建此试验实验室或试验环境的目的是说明综合集成Microsoft 365 Defender功能。</span><span class="sxs-lookup"><span data-stu-id="ed28d-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="ed28d-109">体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。</span><span class="sxs-lookup"><span data-stu-id="ed28d-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="ed28d-110">将指导你完成这些步骤，以根据Microsoft 365 Defender部署路径开始评估。</span><span class="sxs-lookup"><span data-stu-id="ed28d-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="ed28d-111">目标是帮助您使用试用帐户在实验室环境中或在具有完整许可证的生产试验环境中设置安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="ed28d-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="ed28d-112">准备试验实验室或试验环境有助于向贵组织的决策者介绍安全操作用例。</span><span class="sxs-lookup"><span data-stu-id="ed28d-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="ed28d-113">运行完攻击模拟并满意结果后，可以在组织中使用 Microsoft 技术销售专业人员或专家，在组织中全面部署和运行攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="ed28d-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="ed28d-114">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="ed28d-114">This guide will help you:</span></span>
- <span data-ttu-id="ed28d-115">设置实验室服务器和计算机</span><span class="sxs-lookup"><span data-stu-id="ed28d-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="ed28d-116">使用用户和组配置 Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed28d-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="ed28d-117">设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ed28d-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ed28d-118">为服务器和计算机设置本地策略</span><span class="sxs-lookup"><span data-stu-id="ed28d-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="ed28d-119">模拟威胁攻击以在威胁中生成测试事件或Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="ed28d-120">为了获得最佳结果，请尽可能遵循实验室设置说明。</span><span class="sxs-lookup"><span data-stu-id="ed28d-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="ed28d-121">部署阶段</span><span class="sxs-lookup"><span data-stu-id="ed28d-121">Deployment phases</span></span>

<span data-ttu-id="ed28d-122">创建测试实验室环境有三Microsoft 365 Defender阶段。</span><span class="sxs-lookup"><span data-stu-id="ed28d-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![部署阶段：准备、设置、载入](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="ed28d-124">阶段</span><span class="sxs-lookup"><span data-stu-id="ed28d-124">Phase</span></span> | <span data-ttu-id="ed28d-125">说明</span><span class="sxs-lookup"><span data-stu-id="ed28d-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="ed28d-126">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="ed28d-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="ed28d-127">了解在试验实验室或试验环境中部署Microsoft 365 Defender需要考虑哪些内容：</span><span class="sxs-lookup"><span data-stu-id="ed28d-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="ed28d-128">- 利益干系人与签署</span><span class="sxs-lookup"><span data-stu-id="ed28d-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="ed28d-129">- 环境注意事项</span><span class="sxs-lookup"><span data-stu-id="ed28d-129">- Environment considerations</span></span> <br><span data-ttu-id="ed28d-130">- Access</span><span class="sxs-lookup"><span data-stu-id="ed28d-130">- Access</span></span> <br><span data-ttu-id="ed28d-131">- Azure Active Directory安装程序</span><span class="sxs-lookup"><span data-stu-id="ed28d-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="ed28d-132">- 配置顺序</span><span class="sxs-lookup"><span data-stu-id="ed28d-132">- Configuration order</span></span>
|[<span data-ttu-id="ed28d-133">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="ed28d-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="ed28d-134">执行初始步骤以访问安全Microsoft 365中心，以设置Microsoft 365 Defender试验实验室或试验环境。</span><span class="sxs-lookup"><span data-stu-id="ed28d-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="ed28d-135">将指导你：</span><span class="sxs-lookup"><span data-stu-id="ed28d-135">You'll be guided to:</span></span><br><br><span data-ttu-id="ed28d-136">- 注册Microsoft 365 E5试用版</span><span class="sxs-lookup"><span data-stu-id="ed28d-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="ed28d-137">- 配置域</span><span class="sxs-lookup"><span data-stu-id="ed28d-137">- Configure domain</span></span><br><span data-ttu-id="ed28d-138">- 分配Microsoft 365 E5许可证</span><span class="sxs-lookup"><span data-stu-id="ed28d-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="ed28d-139">- 在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="ed28d-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="ed28d-140">阶段 3：配置&载入</span><span class="sxs-lookup"><span data-stu-id="ed28d-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="ed28d-141">配置每个Microsoft 365 Defender和板载终结点。</span><span class="sxs-lookup"><span data-stu-id="ed28d-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="ed28d-142">将指导你：</span><span class="sxs-lookup"><span data-stu-id="ed28d-142">You'll be guided to:</span></span><br><br><span data-ttu-id="ed28d-143">- 配置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ed28d-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="ed28d-144">- 配置Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ed28d-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="ed28d-145">- 为标识配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="ed28d-146">- 为终结点配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="ed28d-147">完成本指南后，你已标识所涉及的利益干系人以及所需的审批、具有正确的访问权限、注册试用、配置的域和每个 Microsoft 365 Defender 支柱，并且你的终结点将载入服务。</span><span class="sxs-lookup"><span data-stu-id="ed28d-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="ed28d-148">关键功能</span><span class="sxs-lookup"><span data-stu-id="ed28d-148">Key capabilities</span></span>

<span data-ttu-id="ed28d-149">尽管 Microsoft 365 Defender提供了许多功能，但此部署指南的主要目的是通过载入设备来引导你入门。</span><span class="sxs-lookup"><span data-stu-id="ed28d-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="ed28d-150">除了载入之外，本指南还让你开始使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="ed28d-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="ed28d-151">功能</span><span class="sxs-lookup"><span data-stu-id="ed28d-151">Capability</span></span> | <span data-ttu-id="ed28d-152">说明</span><span class="sxs-lookup"><span data-stu-id="ed28d-152">Description</span></span> 
:---|:---
<span data-ttu-id="ed28d-153">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ed28d-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ed28d-154">帮助保护你的整个Office 365免受当前威胁的威胁</span><span class="sxs-lookup"><span data-stu-id="ed28d-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="ed28d-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ed28d-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="ed28d-156">标识并检测对遭到入侵的身份和恶意内部操作的威胁。</span><span class="sxs-lookup"><span data-stu-id="ed28d-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="ed28d-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ed28d-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ed28d-158">提供丰富的可见性、控制数据传输，并检测云服务中的网络威胁。</span><span class="sxs-lookup"><span data-stu-id="ed28d-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="ed28d-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ed28d-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="ed28d-160">通过全面的终结点安全性来预防、检测和提供对高级威胁的响应功能。</span><span class="sxs-lookup"><span data-stu-id="ed28d-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="ed28d-161">在作用域内</span><span class="sxs-lookup"><span data-stu-id="ed28d-161">In scope</span></span>

<span data-ttu-id="ed28d-162">本指南包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="ed28d-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="ed28d-163">设置Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed28d-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="ed28d-164">设置Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="ed28d-165">注册Microsoft 365 E5试用版，或者如果你正在运行试点，请使用完整许可证</span><span class="sxs-lookup"><span data-stu-id="ed28d-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="ed28d-166">配置域</span><span class="sxs-lookup"><span data-stu-id="ed28d-166">Configure domain</span></span>
    -   <span data-ttu-id="ed28d-167">分配Microsoft 365 E5许可证</span><span class="sxs-lookup"><span data-stu-id="ed28d-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="ed28d-168">在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="ed28d-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="ed28d-169">根据Microsoft 365 Defender配置所有功能支柱</span><span class="sxs-lookup"><span data-stu-id="ed28d-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="ed28d-170">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ed28d-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="ed28d-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ed28d-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="ed28d-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ed28d-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="ed28d-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ed28d-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="ed28d-174">超出范围</span><span class="sxs-lookup"><span data-stu-id="ed28d-174">Out of scope</span></span>

<span data-ttu-id="ed28d-175">以下超出了此部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="ed28d-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="ed28d-176">可能与解决方案集成的第三方解决方案Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed28d-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="ed28d-177">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="ed28d-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="ed28d-178">下一步</span><span class="sxs-lookup"><span data-stu-id="ed28d-178">Next step</span></span>
<span data-ttu-id="ed28d-179">[阶段 1：准备](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="ed28d-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="ed28d-180">准备Microsoft 365 Defender试验实验室或试验环境</span><span class="sxs-lookup"><span data-stu-id="ed28d-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
