---
title: 评估 Microsoft 威胁防护
description: 设置您的 Microsoft 威胁防护试用实验室或试点环境，以试用旨在保护设备、标识、数据和应用程序的联合威胁防护解决方案如何帮助您的组织
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62852dfe75794d5d0e33453f978967fff40813e1
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816933"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="276b8-104">创建 Microsoft 威胁防护试用实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="276b8-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

<span data-ttu-id="276b8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="276b8-105">**Applies to:**</span></span>
- <span data-ttu-id="276b8-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="276b8-107">创建此试用版实验室或试点环境的目的是说明 Microsoft 威胁防护在您的组织中可使用的检测、预防、调查和响应的全面、集成和智能功能。</span><span class="sxs-lookup"><span data-stu-id="276b8-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="276b8-108">本指南将指导你完成基于建议的部署路径启动 Microsoft 威胁防护评估的步骤。</span><span class="sxs-lookup"><span data-stu-id="276b8-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="276b8-109">目标是帮助您在实验室环境中使用试用帐户或在使用完整许可证时在生产中的试点环境中设置集成 Microsoft 威胁防护服务。</span><span class="sxs-lookup"><span data-stu-id="276b8-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="276b8-110">在为组织中的安全解决方案决策者提供安全操作使用案例时，这些结果将非常有用。</span><span class="sxs-lookup"><span data-stu-id="276b8-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="276b8-111">当您完成攻击模拟并对结果感到满意时，您可以在组织中使用 Microsoft 技术销售专家或专家的帮助，在组织中完全部署和 operationalize 它。</span><span class="sxs-lookup"><span data-stu-id="276b8-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="276b8-112">本指南将帮助您：</span><span class="sxs-lookup"><span data-stu-id="276b8-112">This guide will help you:</span></span>
- <span data-ttu-id="276b8-113">设置实验室服务器和计算机</span><span class="sxs-lookup"><span data-stu-id="276b8-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="276b8-114">使用用户和组配置 Active Directory</span><span class="sxs-lookup"><span data-stu-id="276b8-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="276b8-115">设置和配置 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft 云应用安全性</span><span class="sxs-lookup"><span data-stu-id="276b8-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="276b8-116">为您的服务器和计算机设置本地策略</span><span class="sxs-lookup"><span data-stu-id="276b8-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="276b8-117">模拟威胁攻击以在 Microsoft 威胁防护中生成测试事件或警报</span><span class="sxs-lookup"><span data-stu-id="276b8-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="276b8-118">为获得最佳结果，请尽可能严格地遵循实验室设置说明。</span><span class="sxs-lookup"><span data-stu-id="276b8-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="276b8-119">部署阶段</span><span class="sxs-lookup"><span data-stu-id="276b8-119">Deployment phases</span></span>

<span data-ttu-id="276b8-120">创建 Microsoft 威胁防护试用实验室环境并部署它时有三个阶段：</span><span class="sxs-lookup"><span data-stu-id="276b8-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="276b8-121">阶段</span><span class="sxs-lookup"><span data-stu-id="276b8-121">Phase</span></span> | <span data-ttu-id="276b8-122">说明</span><span class="sxs-lookup"><span data-stu-id="276b8-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="276b8-123">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="276b8-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="276b8-124">第1阶段：准备</span><span class="sxs-lookup"><span data-stu-id="276b8-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="276b8-125">了解在试用实验室或试点环境中部署 Microsoft 威胁防护时需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="276b8-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="276b8-126">-利益干系人和签署</span><span class="sxs-lookup"><span data-stu-id="276b8-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="276b8-127">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="276b8-127">- Environment considerations</span></span> <br><span data-ttu-id="276b8-128">-Access</span><span class="sxs-lookup"><span data-stu-id="276b8-128">- Access</span></span> <br><span data-ttu-id="276b8-129">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="276b8-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="276b8-130">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="276b8-130">- Configuration order</span></span>
|  <span data-ttu-id="276b8-131">![阶段2：安装程序](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="276b8-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="276b8-132">阶段2：安装程序</span><span class="sxs-lookup"><span data-stu-id="276b8-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="276b8-133">执行访问 Microsoft 365 安全中心的初始步骤，以设置你的 Microsoft 威胁防护试用实验室或试点环境。</span><span class="sxs-lookup"><span data-stu-id="276b8-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="276b8-134">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="276b8-134">You'll be guided to:</span></span><br><br><span data-ttu-id="276b8-135">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="276b8-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="276b8-136">-配置域</span><span class="sxs-lookup"><span data-stu-id="276b8-136">- Configure domain</span></span><br><span data-ttu-id="276b8-137">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="276b8-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="276b8-138">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="276b8-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="276b8-139">![第3阶段： Configure & 板载](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="276b8-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="276b8-140">第3阶段： Configure & 板载</span><span class="sxs-lookup"><span data-stu-id="276b8-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="276b8-141">配置每个 Microsoft 威胁防护支柱和板载终结点。</span><span class="sxs-lookup"><span data-stu-id="276b8-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="276b8-142">你将指导你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="276b8-142">You'll be guided to:</span></span><br><br><span data-ttu-id="276b8-143">-配置 Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="276b8-144">-配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="276b8-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="276b8-145">-配置 Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="276b8-146">-配置 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="276b8-147">在范围内</span><span class="sxs-lookup"><span data-stu-id="276b8-147">In scope</span></span>

<span data-ttu-id="276b8-148">本指南的作用域中包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="276b8-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="276b8-149">设置 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="276b8-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="276b8-150">设置 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="276b8-151">注册 Microsoft 365 E5 试用版，如果你正在运行试点，请使用你的完整许可证</span><span class="sxs-lookup"><span data-stu-id="276b8-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="276b8-152">配置域</span><span class="sxs-lookup"><span data-stu-id="276b8-152">Configure domain</span></span>
    -   <span data-ttu-id="276b8-153">分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="276b8-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="276b8-154">完成门户中的设置向导</span><span class="sxs-lookup"><span data-stu-id="276b8-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="276b8-155">根据最佳实践配置所有 Microsoft 威胁防护支柱</span><span class="sxs-lookup"><span data-stu-id="276b8-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="276b8-156">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="276b8-157">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="276b8-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="276b8-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="276b8-159">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="276b8-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="276b8-160">超出范围</span><span class="sxs-lookup"><span data-stu-id="276b8-160">Out of scope</span></span>

<span data-ttu-id="276b8-161">以下内容超出了本部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="276b8-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="276b8-162">可能与 Microsoft 威胁防护集成的第三方解决方案的配置</span><span class="sxs-lookup"><span data-stu-id="276b8-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="276b8-163">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="276b8-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="276b8-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="276b8-164">Next step</span></span>
<span data-ttu-id="276b8-165">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="276b8-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="276b8-166">[第1阶段：准备](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="276b8-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="276b8-167">准备你的 Microsoft 威胁防护试用实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="276b8-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
