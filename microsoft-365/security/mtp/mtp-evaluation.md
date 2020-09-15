---
title: 评估 Microsoft 威胁防护
description: 设置你的 Microsoft 威胁防护试用实验室环境，以试用旨在保护设备、标识、数据和应用程序的联合威胁防护解决方案如何帮助贵组织
keywords: Microsoft 威胁防护试用版，试用 Microsoft 威胁防护，评估 Microsoft 威胁防护，Microsoft 威胁防护评估实验室，网络安全，高级持久威胁，企业安全性，设备，设备，标识，用户，数据，应用程序，事件，自动化调查和修正，高级搜寻
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
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649957"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="66feb-104">创建 Microsoft 威胁防护试用实验室环境</span><span class="sxs-lookup"><span data-stu-id="66feb-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="66feb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="66feb-105">**Applies to:**</span></span>
- <span data-ttu-id="66feb-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="66feb-107">创建此试用版环境的目的是演示 Microsoft 威胁防护在您的组织中可使用的检测、预防、调查和响应的全面、集成和智能功能。</span><span class="sxs-lookup"><span data-stu-id="66feb-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="66feb-108">本指南将指导你完成基于建议的部署路径启动 Microsoft 威胁防护评估的步骤。</span><span class="sxs-lookup"><span data-stu-id="66feb-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="66feb-109">目标是帮助您在实验室环境中设置集成 Microsoft 威胁防护服务，或在向组织中的安全解决方案决策制定者提供 (POC) 的概念证明。</span><span class="sxs-lookup"><span data-stu-id="66feb-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="66feb-110">当您完成攻击模拟、自动调查和响应并对结果感到满意时，您可以在您的组织中 Microsoft 技术销售专业人员或专家的帮助下，将其部署到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="66feb-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="66feb-111">本指南将帮助您：</span><span class="sxs-lookup"><span data-stu-id="66feb-111">This guide will help you:</span></span>
- <span data-ttu-id="66feb-112">设置实验室服务器和计算机</span><span class="sxs-lookup"><span data-stu-id="66feb-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="66feb-113">使用用户和组配置 Active Directory</span><span class="sxs-lookup"><span data-stu-id="66feb-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="66feb-114">设置和配置 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft 云应用安全性</span><span class="sxs-lookup"><span data-stu-id="66feb-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="66feb-115">为您的服务器和计算机设置本地策略</span><span class="sxs-lookup"><span data-stu-id="66feb-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="66feb-116">模拟威胁攻击以在 Microsoft 威胁防护中生成测试事件或警报</span><span class="sxs-lookup"><span data-stu-id="66feb-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="66feb-117">为获得最佳结果，请尽可能严格地遵循实验室设置说明。</span><span class="sxs-lookup"><span data-stu-id="66feb-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="66feb-118">部署阶段</span><span class="sxs-lookup"><span data-stu-id="66feb-118">Deployment phases</span></span>

<span data-ttu-id="66feb-119">创建 Microsoft 威胁防护试用实验室环境并部署它时有三个阶段：</span><span class="sxs-lookup"><span data-stu-id="66feb-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="66feb-120">阶段</span><span class="sxs-lookup"><span data-stu-id="66feb-120">Phase</span></span> | <span data-ttu-id="66feb-121">描述</span><span class="sxs-lookup"><span data-stu-id="66feb-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="66feb-122">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="66feb-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="66feb-123">第1阶段：准备</span><span class="sxs-lookup"><span data-stu-id="66feb-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="66feb-124">了解在试用实验室环境中部署 Microsoft 威胁防护时需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="66feb-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="66feb-125">-利益干系人和签署</span><span class="sxs-lookup"><span data-stu-id="66feb-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="66feb-126">-环境注意事项</span><span class="sxs-lookup"><span data-stu-id="66feb-126">- Environment considerations</span></span> <br><span data-ttu-id="66feb-127">-Access</span><span class="sxs-lookup"><span data-stu-id="66feb-127">- Access</span></span> <br><span data-ttu-id="66feb-128">-Azure Active Directory 安装程序</span><span class="sxs-lookup"><span data-stu-id="66feb-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="66feb-129">-配置顺序</span><span class="sxs-lookup"><span data-stu-id="66feb-129">- Configuration order</span></span>
|  <span data-ttu-id="66feb-130">![阶段2：安装程序](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="66feb-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="66feb-131">阶段2：安装程序</span><span class="sxs-lookup"><span data-stu-id="66feb-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="66feb-132">执行访问 Microsoft 365 安全中心的初始步骤，以设置 Microsoft 威胁防护试用实验室环境。</span><span class="sxs-lookup"><span data-stu-id="66feb-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="66feb-133">系统将指导您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66feb-133">You will be guided to:</span></span><br><br><span data-ttu-id="66feb-134">-注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="66feb-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="66feb-135">-配置域</span><span class="sxs-lookup"><span data-stu-id="66feb-135">- Configure domain</span></span><br><span data-ttu-id="66feb-136">-分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="66feb-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="66feb-137">-完成门户中的安装向导</span><span class="sxs-lookup"><span data-stu-id="66feb-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="66feb-138">![第3阶段： Configure & 板载](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="66feb-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="66feb-139">第3阶段： Configure & 板载</span><span class="sxs-lookup"><span data-stu-id="66feb-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="66feb-140">配置每个 Microsoft 威胁防护支柱和板载终结点。</span><span class="sxs-lookup"><span data-stu-id="66feb-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="66feb-141">系统将指导您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66feb-141">You will be guided to:</span></span><br><br><span data-ttu-id="66feb-142">-配置 Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="66feb-143">-配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="66feb-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="66feb-144">-配置 Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="66feb-145">-配置 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="66feb-146">在范围内</span><span class="sxs-lookup"><span data-stu-id="66feb-146">In scope</span></span>

<span data-ttu-id="66feb-147">本试用版实验室环境指南的范围如下：</span><span class="sxs-lookup"><span data-stu-id="66feb-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="66feb-148">设置 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="66feb-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="66feb-149">设置 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="66feb-150">注册 Microsoft 365 E5 试用版</span><span class="sxs-lookup"><span data-stu-id="66feb-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="66feb-151">配置域</span><span class="sxs-lookup"><span data-stu-id="66feb-151">Configure domain</span></span>
    -   <span data-ttu-id="66feb-152">分配 Microsoft 365 E5 许可证</span><span class="sxs-lookup"><span data-stu-id="66feb-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="66feb-153">完成门户中的设置向导</span><span class="sxs-lookup"><span data-stu-id="66feb-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="66feb-154">根据最佳实践配置所有 Microsoft 威胁防护支柱</span><span class="sxs-lookup"><span data-stu-id="66feb-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="66feb-155">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="66feb-156">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="66feb-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="66feb-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="66feb-158">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="66feb-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="66feb-159">超出范围</span><span class="sxs-lookup"><span data-stu-id="66feb-159">Out of scope</span></span>

<span data-ttu-id="66feb-160">以下内容超出了本部署指南的范围：</span><span class="sxs-lookup"><span data-stu-id="66feb-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="66feb-161">可能与 Microsoft Defender ATP 集成的第三方解决方案的配置</span><span class="sxs-lookup"><span data-stu-id="66feb-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="66feb-162">生产环境中的渗透测试</span><span class="sxs-lookup"><span data-stu-id="66feb-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="66feb-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="66feb-163">Next step</span></span>
<span data-ttu-id="66feb-164">![第1阶段：准备](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="66feb-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="66feb-165">[第1阶段：准备](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="66feb-165">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="66feb-166">准备 Microsoft 威胁防护评估实验室环境</span><span class="sxs-lookup"><span data-stu-id="66feb-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
