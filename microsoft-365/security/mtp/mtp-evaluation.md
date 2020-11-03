---
title: 评估 Microsoft 365 Defender
description: 设置 Microsoft 365 Defender 试用版实验室或试点环境，以试用并体验用于保护组织中的设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 威胁防护试用版，试用 Microsoft 威胁防护，评估 Microsoft 威胁防护，Microsoft 威胁防护评估实验室，Microsoft 威胁防护试验，网络安全，高级持久威胁，企业安全性，设备，设备，身份，用户，数据，应用程序，事件，自动调查和修正，高级搜寻
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
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846480"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="6735c-104">创建 Microsoft 365 Defender 试用版实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="6735c-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6735c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6735c-105">**Applies to:**</span></span>
- <span data-ttu-id="6735c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6735c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6735c-107">创建此试用版实验室或试点环境的目的是为了说明全面且集成的 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="6735c-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="6735c-108">体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。</span><span class="sxs-lookup"><span data-stu-id="6735c-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="6735c-109">本指南将指导您完成基于建议的部署路径启动 Microsoft 365 Defender 评估的步骤。</span><span class="sxs-lookup"><span data-stu-id="6735c-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6735c-110">目标是帮助您在实验室环境中使用试用帐户设置安全解决方案，或使用完整许可证在生产的试点环境中设置安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="6735c-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="6735c-111">准备试用版实验室或试点环境可帮助您在组织中向决策者提供安全操作用例。</span><span class="sxs-lookup"><span data-stu-id="6735c-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="6735c-112">当您完成攻击模拟并对结果感到满意时，您可以在组织中使用 Microsoft 技术销售专业人员或专家的帮助，在组织中完全部署和 operationalize 它。</span><span class="sxs-lookup"><span data-stu-id="6735c-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6735c-113">本指南将帮助您：</span><span class="sxs-lookup"><span data-stu-id="6735c-113">This guide will help you:</span></span>
- <span data-ttu-id="6735c-114">设置实验室服务器和计算机</span><span class="sxs-lookup"><span data-stu-id="6735c-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="6735c-115">使用用户和组配置 Active Directory</span><span class="sxs-lookup"><span data-stu-id="6735c-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6735c-116">设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft 云应用安全性</span><span class="sxs-lookup"><span data-stu-id="6735c-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6735c-117">为您的服务器和计算机设置本地策略</span><span class="sxs-lookup"><span data-stu-id="6735c-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="6735c-118">在 Microsoft 365 Defender 中模拟威胁攻击以生成测试事件或警报</span><span class="sxs-lookup"><span data-stu-id="6735c-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="6735c-119">为获得最佳结果，请尽可能严格地遵循实验室设置说明。</span><span class="sxs-lookup"><span data-stu-id="6735c-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6735c-120">部署阶段</span><span class="sxs-lookup"><span data-stu-id="6735c-120">Deployment phases</span></span>

<span data-ttu-id="6735c-121">创建 Microsoft 365 Defender 试用版环境并部署它时有三个阶段：</span><span class="sxs-lookup"><span data-stu-id="6735c-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="6735c-122">阶段</span><span class="sxs-lookup"><span data-stu-id="6735c-122">Phase</span></span> | <span data-ttu-id="6735c-123">说明</span><span class="sxs-lookup"><span data-stu-id="6735c-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="6735c-124">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6735c-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="6735c-125">第1阶段：准备</span><span class="sxs-lookup"><span data-stu-id="6735c-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="6735c-126">了解在试用实验室或试点环境中部署 Microsoft 365 Defender 时需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="6735c-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="6735c-127">-利益干系人和签署</span><span class="sxs-lookup"><span data-stu-id="6735c-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6735c-128">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="6735c-128">- Environment considerations</span></span> <br><span data-ttu-id="6735c-129">-Access</span><span class="sxs-lookup"><span data-stu-id="6735c-129">- Access</span></span> <br><span data-ttu-id="6735c-130">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="6735c-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6735c-131">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="6735c-131">- Configuration order</span></span>
|  <span data-ttu-id="6735c-132">![阶段2：安装程序](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="6735c-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="6735c-133">阶段2：安装程序</span><span class="sxs-lookup"><span data-stu-id="6735c-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="6735c-134">执行访问 Microsoft 365 安全中心的初始步骤，以设置你的 Microsoft 365 Defender 试用版实验室或试点环境。</span><span class="sxs-lookup"><span data-stu-id="6735c-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="6735c-135">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6735c-135">You'll be guided to:</span></span><br><br><span data-ttu-id="6735c-136">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="6735c-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6735c-137">-配置域</span><span class="sxs-lookup"><span data-stu-id="6735c-137">- Configure domain</span></span><br><span data-ttu-id="6735c-138">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="6735c-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6735c-139">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="6735c-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="6735c-140">![第3阶段： Configure & 板载](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="6735c-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="6735c-141">第3阶段： Configure & 板载</span><span class="sxs-lookup"><span data-stu-id="6735c-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="6735c-142">配置每个 Microsoft 365 Defender 支柱和板载终结点。</span><span class="sxs-lookup"><span data-stu-id="6735c-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="6735c-143">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6735c-143">You'll be guided to:</span></span><br><br><span data-ttu-id="6735c-144">-配置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="6735c-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="6735c-145">-配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="6735c-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6735c-146">-将 Microsoft Defender 配置为标识</span><span class="sxs-lookup"><span data-stu-id="6735c-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="6735c-147">-为终结点配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6735c-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="6735c-148">在范围内</span><span class="sxs-lookup"><span data-stu-id="6735c-148">In scope</span></span>

<span data-ttu-id="6735c-149">本指南的作用域中包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="6735c-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="6735c-150">设置 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6735c-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6735c-151">设置 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6735c-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="6735c-152">注册 Microsoft 365 E5 试用版，如果你正在运行试点，请使用你的完整许可证</span><span class="sxs-lookup"><span data-stu-id="6735c-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="6735c-153">配置域</span><span class="sxs-lookup"><span data-stu-id="6735c-153">Configure domain</span></span>
    -   <span data-ttu-id="6735c-154">分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="6735c-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6735c-155">完成门户中的设置向导</span><span class="sxs-lookup"><span data-stu-id="6735c-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6735c-156">根据最佳实践配置所有 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="6735c-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="6735c-157">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="6735c-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="6735c-158">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6735c-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="6735c-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6735c-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6735c-160">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6735c-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6735c-161">超出范围</span><span class="sxs-lookup"><span data-stu-id="6735c-161">Out of scope</span></span>

<span data-ttu-id="6735c-162">以下内容超出了本部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="6735c-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6735c-163">可能与 Microsoft 365 Defender 集成的第三方解决方案的配置</span><span class="sxs-lookup"><span data-stu-id="6735c-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="6735c-164">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="6735c-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6735c-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6735c-165">Next step</span></span>
<span data-ttu-id="6735c-166">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6735c-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="6735c-167">[第1阶段：准备](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="6735c-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="6735c-168">准备 Microsoft 365 Defender 试用版实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="6735c-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
