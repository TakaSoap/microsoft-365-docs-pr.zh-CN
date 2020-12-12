---
title: 评估 Microsoft 365 Defender
description: 设置 Microsoft 365 Defender 试用实验室或试验环境，以试用并体验旨在保护组织中设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 威胁防护试用版， 试用 Microsoft 威胁防护， 评估 Microsoft 威胁防护， Microsoft 威胁防护评估实验室， Microsoft 威胁防护试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659627"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="7813c-104">创建 Microsoft 365 Defender 试用实验室或试验环境</span><span class="sxs-lookup"><span data-stu-id="7813c-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7813c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7813c-105">**Applies to:**</span></span>
- <span data-ttu-id="7813c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7813c-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="7813c-107">本指南可帮助你使用用户和组设置实验室环境，然后指导你完成 Microsoft 365 Defender 中的功能配置，以便你可以模拟威胁攻击并获取有意义的试验结果。</span><span class="sxs-lookup"><span data-stu-id="7813c-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="7813c-108">创建此试用实验室或试验环境的目的是说明全面和集成的 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="7813c-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="7813c-109">体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。</span><span class="sxs-lookup"><span data-stu-id="7813c-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="7813c-110">将指导你完成基于推荐的部署路径启动 Microsoft 365 Defender 评估的步骤。</span><span class="sxs-lookup"><span data-stu-id="7813c-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="7813c-111">目标是帮助你使用试用帐户在实验室环境中或在具有完整许可证的生产试验环境中设置安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="7813c-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="7813c-112">准备试验实验室或试验环境可以帮助您向贵组织的决策者呈现安全操作用例。</span><span class="sxs-lookup"><span data-stu-id="7813c-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="7813c-113">运行完攻击模拟并满意结果后，可以在组织中使用 Microsoft 技术销售专业人员或专家全面部署和操作它。</span><span class="sxs-lookup"><span data-stu-id="7813c-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="7813c-114">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="7813c-114">This guide will help you:</span></span>
- <span data-ttu-id="7813c-115">设置实验室服务器和计算机</span><span class="sxs-lookup"><span data-stu-id="7813c-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="7813c-116">使用用户和组配置 Active Directory</span><span class="sxs-lookup"><span data-stu-id="7813c-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="7813c-117">设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7813c-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="7813c-118">为服务器和计算机设置本地策略</span><span class="sxs-lookup"><span data-stu-id="7813c-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="7813c-119">模拟威胁攻击以在 Microsoft 365 Defender 中生成测试事件或警报</span><span class="sxs-lookup"><span data-stu-id="7813c-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="7813c-120">为获得最佳结果，请尽可能遵循实验室设置说明。</span><span class="sxs-lookup"><span data-stu-id="7813c-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="7813c-121">部署阶段</span><span class="sxs-lookup"><span data-stu-id="7813c-121">Deployment phases</span></span>

<span data-ttu-id="7813c-122">创建 Microsoft 365 Defender 试用实验室环境有三个阶段。</span><span class="sxs-lookup"><span data-stu-id="7813c-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![部署阶段：准备、设置、载入](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="7813c-124">阶段</span><span class="sxs-lookup"><span data-stu-id="7813c-124">Phase</span></span> | <span data-ttu-id="7813c-125">说明</span><span class="sxs-lookup"><span data-stu-id="7813c-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="7813c-126">第 1 阶段：准备</span><span class="sxs-lookup"><span data-stu-id="7813c-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="7813c-127">了解在试用实验室或试验环境中部署 Microsoft 365 Defender 时需要考虑的问题：</span><span class="sxs-lookup"><span data-stu-id="7813c-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="7813c-128">- 利益干系人并注销</span><span class="sxs-lookup"><span data-stu-id="7813c-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="7813c-129">- 环境注意事项</span><span class="sxs-lookup"><span data-stu-id="7813c-129">- Environment considerations</span></span> <br><span data-ttu-id="7813c-130">- Access</span><span class="sxs-lookup"><span data-stu-id="7813c-130">- Access</span></span> <br><span data-ttu-id="7813c-131">- Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="7813c-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="7813c-132">- 配置顺序</span><span class="sxs-lookup"><span data-stu-id="7813c-132">- Configuration order</span></span>
|[<span data-ttu-id="7813c-133">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="7813c-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="7813c-134">执行初始步骤以访问 Microsoft 365 安全中心，以设置 Microsoft 365 Defender 试用实验室或试验环境。</span><span class="sxs-lookup"><span data-stu-id="7813c-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="7813c-135">将指导你：</span><span class="sxs-lookup"><span data-stu-id="7813c-135">You'll be guided to:</span></span><br><br><span data-ttu-id="7813c-136">- 注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="7813c-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="7813c-137">- 配置域</span><span class="sxs-lookup"><span data-stu-id="7813c-137">- Configure domain</span></span><br><span data-ttu-id="7813c-138">- 分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="7813c-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="7813c-139">- 在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="7813c-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="7813c-140">第 3 阶段：配置&载入</span><span class="sxs-lookup"><span data-stu-id="7813c-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="7813c-141">配置每个 Microsoft 365 Defender 支柱和载入终结点。</span><span class="sxs-lookup"><span data-stu-id="7813c-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="7813c-142">将指导你：</span><span class="sxs-lookup"><span data-stu-id="7813c-142">You'll be guided to:</span></span><br><br><span data-ttu-id="7813c-143">- 配置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7813c-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="7813c-144">- 配置 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7813c-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="7813c-145">- 为标识配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7813c-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="7813c-146">- 配置适用于终结点的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7813c-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="7813c-147">完成本指南后，你已确定所涉及的利益干系人以及所需的审批，拥有适当的访问权限，注册试用版、配置的域和每个 Microsoft 365 Defender 支柱，你的终结点将载入服务。</span><span class="sxs-lookup"><span data-stu-id="7813c-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="7813c-148">主要功能</span><span class="sxs-lookup"><span data-stu-id="7813c-148">Key capabilities</span></span>

<span data-ttu-id="7813c-149">虽然 Microsoft 365 Defender 提供了许多功能，但此部署指南的主要目的是通过载入设备入门。</span><span class="sxs-lookup"><span data-stu-id="7813c-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="7813c-150">除了载入之外，本指南还让你开始使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="7813c-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="7813c-151">功能</span><span class="sxs-lookup"><span data-stu-id="7813c-151">Capability</span></span> | <span data-ttu-id="7813c-152">说明</span><span class="sxs-lookup"><span data-stu-id="7813c-152">Description</span></span> 
:---|:---
<span data-ttu-id="7813c-153">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7813c-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7813c-154">帮助保护整个 Office 365 环境免受当前的威胁</span><span class="sxs-lookup"><span data-stu-id="7813c-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="7813c-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7813c-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="7813c-156">标识并检测对遭到入侵的身份和恶意内部操作的威胁。</span><span class="sxs-lookup"><span data-stu-id="7813c-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="7813c-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7813c-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="7813c-158">提供丰富的可见性、控制数据传输和跨云服务检测网络威胁。</span><span class="sxs-lookup"><span data-stu-id="7813c-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="7813c-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7813c-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="7813c-160">通过全面的终结点安全性，阻止、检测和提供对高级威胁的响应功能。</span><span class="sxs-lookup"><span data-stu-id="7813c-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="7813c-161">在作用域内</span><span class="sxs-lookup"><span data-stu-id="7813c-161">In scope</span></span>

<span data-ttu-id="7813c-162">本指南包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="7813c-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="7813c-163">设置 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7813c-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="7813c-164">设置 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7813c-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="7813c-165">注册 Microsoft 365 E5 试用版，或在运行试点时使用完整许可证</span><span class="sxs-lookup"><span data-stu-id="7813c-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="7813c-166">配置域</span><span class="sxs-lookup"><span data-stu-id="7813c-166">Configure domain</span></span>
    -   <span data-ttu-id="7813c-167">分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="7813c-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="7813c-168">在门户中完成安装向导</span><span class="sxs-lookup"><span data-stu-id="7813c-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="7813c-169">根据最佳做法配置所有 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="7813c-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="7813c-170">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7813c-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="7813c-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="7813c-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="7813c-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7813c-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="7813c-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7813c-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="7813c-174">超出范围</span><span class="sxs-lookup"><span data-stu-id="7813c-174">Out of scope</span></span>

<span data-ttu-id="7813c-175">以下超出了此部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="7813c-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="7813c-176">可能会与 Microsoft 365 Defender 集成的第三方解决方案的配置</span><span class="sxs-lookup"><span data-stu-id="7813c-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="7813c-177">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="7813c-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="7813c-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7813c-178">Next step</span></span>
<span data-ttu-id="7813c-179">[第 1 阶段：准备](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="7813c-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="7813c-180">准备 Microsoft 365 Defender 试用实验室或试验环境</span><span class="sxs-lookup"><span data-stu-id="7813c-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
