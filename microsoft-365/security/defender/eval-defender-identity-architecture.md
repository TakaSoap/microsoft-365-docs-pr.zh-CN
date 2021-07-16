---
title: 查看 Microsoft Defender 标识的体系结构要求和技术框架、体系结构图、MDI
description: Microsoft Defender for Identity in Microsoft 365 Defender技术图表将帮助你在构建试用实验室或Microsoft 365环境之前了解 microsoft Defender 中的身份。
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
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457680"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a><span data-ttu-id="6d612-103">查看 Microsoft Defender for Identity 的体系结构要求和关键概念</span><span class="sxs-lookup"><span data-stu-id="6d612-103">Review architecture requirements and key concepts for Microsoft Defender for Identity</span></span>


<span data-ttu-id="6d612-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6d612-104">**Applies to:**</span></span>
- <span data-ttu-id="6d612-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d612-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="6d612-106">本文是设置 Microsoft Defender for Identity 评估环境过程中第 1 步（第 [3](eval-defender-identity-overview.md) 步）。</span><span class="sxs-lookup"><span data-stu-id="6d612-106">This article is [Step 1 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="6d612-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6d612-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="6d612-108">在启用 Microsoft Defender for Identity 之前，请确保你了解体系结构并满足要求。</span><span class="sxs-lookup"><span data-stu-id="6d612-108">Before enabling Microsoft Defender for Identity, be sure you understand the architecture and can meet the requirements.</span></span>

<span data-ttu-id="6d612-109">Microsoft Defender for Identity 使用机器学习和行为分析来识别跨本地网络的攻击，并检测并主动防止与云标识相关的用户登录风险。</span><span class="sxs-lookup"><span data-stu-id="6d612-109">Microsoft Defender for Identity uses machine learning and behavioral analytics to identify attacks across your on-premises network along with detecting and proactively preventing user sign-in risks associated with cloud identities.</span></span> <span data-ttu-id="6d612-110">有关详细信息，请参阅什么是 [Microsoft Defender for Identity？](/defender-for-identity/what-is)</span><span class="sxs-lookup"><span data-stu-id="6d612-110">For more information, see [What is Microsoft Defender for Identity?](/defender-for-identity/what-is)</span></span>

<span data-ttu-id="6d612-111">Defender for Identity 可保护本地 Active Directory 用户和/或已同步到 Azure AD Azure Active Directory (的用户) 。</span><span class="sxs-lookup"><span data-stu-id="6d612-111">Defender for Identity protects your on-premises Active Directory users and/or users synced to your Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="6d612-112">若要保护仅由 Azure AD 用户创建的环境，请参阅[Azure AD Identity Protection。](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="6d612-112">To protect an environment made up of only Azure AD users, see [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="6d612-113">了解体系结构</span><span class="sxs-lookup"><span data-stu-id="6d612-113">Understand the architecture</span></span>

<span data-ttu-id="6d612-114">下图说明了 Defender for Identity 的基准体系结构。</span><span class="sxs-lookup"><span data-stu-id="6d612-114">The following diagram illustrates the baseline architecture for Defender for Identity.</span></span> 

![Microsoft Defender for Identity 的体系结构](../../media/defender/m365-defender-identity-architecture.png)

<span data-ttu-id="6d612-116">在此图中：</span><span class="sxs-lookup"><span data-stu-id="6d612-116">In this illustration:</span></span>
- <span data-ttu-id="6d612-117">安装在 AD 域控制器上的传感器分析日志和网络流量，并将其发送到 Microsoft Defender for Identity 进行分析和报告。</span><span class="sxs-lookup"><span data-stu-id="6d612-117">Sensors installed on AD domain controllers parse logs and network traffic and send them to Microsoft Defender for Identity for analysis and reporting.</span></span>
-  <span data-ttu-id="6d612-118">当 Azure AD 配置为使用图示中的 (联合身份验证 (虚线时，传感器还可以分析 Active Directory 联合身份验证服务 (AD F) S) 。</span><span class="sxs-lookup"><span data-stu-id="6d612-118">Sensors can also parse Active Directory Federation Services (AD FS) when Azure AD is configured to use federated authentication (dotted line in illustration).</span></span> 
- <span data-ttu-id="6d612-119">Microsoft Defender for Identity 将信号共享到 Microsoft 365 Defender，以在 XDR (进行) 。</span><span class="sxs-lookup"><span data-stu-id="6d612-119">Microsoft Defender for Identity shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>


<span data-ttu-id="6d612-120">可以在以下服务器上直接安装 Defender for Identity 传感器：</span><span class="sxs-lookup"><span data-stu-id="6d612-120">Defender for Identity sensors can be directly installed on the following servers:</span></span>

- <span data-ttu-id="6d612-121">域控制器：传感器直接监视域控制器流量，无需专用服务器或端口镜像配置。</span><span class="sxs-lookup"><span data-stu-id="6d612-121">Domain controllers: The sensor directly monitors domain controller traffic, without the need for a dedicated server, or configuration of port mirroring.</span></span>
- <span data-ttu-id="6d612-122">AD FS：传感器直接监视网络流量和身份验证事件。</span><span class="sxs-lookup"><span data-stu-id="6d612-122">AD FS: The sensor directly monitors network traffic and authentication events.</span></span>

<span data-ttu-id="6d612-123">有关 Defender for Identity 的体系结构的深入探讨（包括与 云应用安全 集成，请参阅[Microsoft Defender for Identity architecture](/defender-for-identity/architecture)。</span><span class="sxs-lookup"><span data-stu-id="6d612-123">For a deeper look into the architecture of Defender for Identity, including integration with Cloud App Security, see [Microsoft Defender for Identity architecture](/defender-for-identity/architecture).</span></span>


## <a name="understand-key-concepts"></a><span data-ttu-id="6d612-124">了解关键概念</span><span class="sxs-lookup"><span data-stu-id="6d612-124">Understand key concepts</span></span>

<span data-ttu-id="6d612-125">下表确定了评估、配置和部署 Microsoft Defender for Identity 时必须了解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="6d612-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Identity.</span></span>


|<span data-ttu-id="6d612-126">概念</span><span class="sxs-lookup"><span data-stu-id="6d612-126">Concept</span></span>  |<span data-ttu-id="6d612-127">说明</span><span class="sxs-lookup"><span data-stu-id="6d612-127">Description</span></span> |<span data-ttu-id="6d612-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="6d612-128">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="6d612-129">受监视的活动</span><span class="sxs-lookup"><span data-stu-id="6d612-129">Monitored activities</span></span> | <span data-ttu-id="6d612-130">Defender for Identity 监视从组织内部生成的信号，以检测可疑或恶意活动，并帮助你确定每个潜在威胁的有效性，以便你可以有效地进行会审和响应。</span><span class="sxs-lookup"><span data-stu-id="6d612-130">Defender for Identity monitors signals generated from within your organization to detect suspicious or malicious activity and helps you determine the validity of each potential threat so that you can effectively triage and respond.</span></span>  |  [<span data-ttu-id="6d612-131">Microsoft Defender for Identity 受监视的活动</span><span class="sxs-lookup"><span data-stu-id="6d612-131">Microsoft Defender for Identity monitored activities</span></span>](/defender-for-identity/monitored-activities)       |
| <span data-ttu-id="6d612-132">安全警报</span><span class="sxs-lookup"><span data-stu-id="6d612-132">Security alerts</span></span>    | <span data-ttu-id="6d612-133">Defender for Identity 安全警报介绍了网络上传感器检测到的可疑活动，以及每个威胁中涉及的主角和计算机。</span><span class="sxs-lookup"><span data-stu-id="6d612-133">Defender for Identity security alerts explain the suspicious activities detected by sensors on your network along with the actors and computers involved in each threat.</span></span>   | [<span data-ttu-id="6d612-134">Microsoft Defender 标识安全警报</span><span class="sxs-lookup"><span data-stu-id="6d612-134">Microsoft Defender for Identity Security Alerts</span></span>](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| <span data-ttu-id="6d612-135">实体配置文件</span><span class="sxs-lookup"><span data-stu-id="6d612-135">Entity profiles</span></span>    | <span data-ttu-id="6d612-136">实体配置文件提供对用户、计算机、设备和资源及其访问历史记录的全面深入调查。</span><span class="sxs-lookup"><span data-stu-id="6d612-136">Entity profiles provide a comprehensive deep-dive investigation of users, computers, devices, and resources along with their access history.</span></span>   | [<span data-ttu-id="6d612-137">了解实体配置文件</span><span class="sxs-lookup"><span data-stu-id="6d612-137">Understanding entity profiles</span></span>](/defender-for-identity/entity-profiles)  |
| <span data-ttu-id="6d612-138">横向移动路径</span><span class="sxs-lookup"><span data-stu-id="6d612-138">Lateral movement paths</span></span>    | <span data-ttu-id="6d612-139">MDI 安全见解的一个关键组成部分是识别攻击者使用非敏感帐户在整个网络中获取对敏感帐户或计算机的访问权限的横向移动路径。</span><span class="sxs-lookup"><span data-stu-id="6d612-139">A key component of MDI security insights is identifying lateral movement paths in which an attacker uses non-sensitive accounts to gain access to sensitive accounts or machines throughout your network.</span></span>  | [<span data-ttu-id="6d612-140">Microsoft Defender 标识横向移动路径 (LMP) </span><span class="sxs-lookup"><span data-stu-id="6d612-140">Microsoft Defender for Identity Lateral Movement Paths (LMPs)</span></span>](/defender-for-identity/use-case-lateral-movement-path)  |
| <span data-ttu-id="6d612-141">网络名称解析</span><span class="sxs-lookup"><span data-stu-id="6d612-141">Network Name Resolution</span></span>    |  <span data-ttu-id="6d612-142">网络名称解析 (NNR) 是 MDI 功能的一个组件，可捕获基于网络流量、Windows 事件、ETW 等的活动，并将此原始数据与每个活动所涉及的相关计算机关联。</span><span class="sxs-lookup"><span data-stu-id="6d612-142">Network Name Resolution (NNR) is a component of MDI functionality which captures activities based on network traffic, Windows events, ETW, etc. and correlates this raw data to the relevant computers involved in each activity.</span></span>       | [<span data-ttu-id="6d612-143">什么是网络名称解析？</span><span class="sxs-lookup"><span data-stu-id="6d612-143">What is Network Name Resolution?</span></span>](/defender-for-identity/nnr-policy)      |
| <span data-ttu-id="6d612-144">报告</span><span class="sxs-lookup"><span data-stu-id="6d612-144">Reports</span></span>    | <span data-ttu-id="6d612-145">Defender for Identity 报告允许你计划或立即生成和下载提供系统和实体状态信息的报告。</span><span class="sxs-lookup"><span data-stu-id="6d612-145">Defender for Identity reports allow you to schedule or immediately generate and download reports that provide system and entity status information.</span></span>  <span data-ttu-id="6d612-146">可以创建有关环境中检测到的系统运行状况、安全警报和潜在横向移动路径的报告。</span><span class="sxs-lookup"><span data-stu-id="6d612-146">You can create reports about system health, security alerts, and potential lateral movement paths detected in your environment.</span></span>   | [<span data-ttu-id="6d612-147">Microsoft Defender 标识报告 </span><span class="sxs-lookup"><span data-stu-id="6d612-147">Microsoft Defender for Identity Reports </span></span>](/defender-for-identity/reports)       |
| <span data-ttu-id="6d612-148">角色组</span><span class="sxs-lookup"><span data-stu-id="6d612-148">Role groups</span></span>    | <span data-ttu-id="6d612-149">Defender for Identity 提供基于角色的组和委派访问权限，以根据组织的特定安全性和合规性需求（包括管理员、用户和查看者）保护数据。</span><span class="sxs-lookup"><span data-stu-id="6d612-149">Defender for Identity offers role-based groups and delegated access to safeguard data according to your organization's specific security and compliance needs which includes Administrators, Users and Viewers.</span></span>        |  [<span data-ttu-id="6d612-150">Microsoft Defender for Identity 角色组</span><span class="sxs-lookup"><span data-stu-id="6d612-150">Microsoft Defender for Identity role groups</span></span>](/defender-for-identity/role-groups)       |
| <span data-ttu-id="6d612-151">管理门户</span><span class="sxs-lookup"><span data-stu-id="6d612-151">Administrative portal</span></span>    |  <span data-ttu-id="6d612-152">除了安全Microsoft 365，Defender for Identity 门户 cab 还用于监视和响应可疑活动。</span><span class="sxs-lookup"><span data-stu-id="6d612-152">In addition to the Microsoft 365 Security Center, the Defender for Identity portal cab be used to monitor and respond to suspicious activity.</span></span>      | [<span data-ttu-id="6d612-153">使用 Microsoft Defender for Identity 门户</span><span class="sxs-lookup"><span data-stu-id="6d612-153">Working with the Microsoft Defender for Identity portal</span></span>](/defender-for-identity/workspace-portal)        |
| <span data-ttu-id="6d612-154">Microsoft Cloud App Security集成</span><span class="sxs-lookup"><span data-stu-id="6d612-154">Microsoft Cloud App Security integration</span></span>   | <span data-ttu-id="6d612-155">Microsoft Cloud App Security Microsoft Defender for Identity 集成，以跨混合环境（云应用和本地） (UEBA) 提供用户实体行为分析</span><span class="sxs-lookup"><span data-stu-id="6d612-155">Microsoft Cloud App Security integrates with Microsoft Defender for Identity to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises</span></span>   | <span data-ttu-id="6d612-156">Microsoft Defender for Identity 集成</span><span class="sxs-lookup"><span data-stu-id="6d612-156">Microsoft Defender for Identity integration</span></span>  |
| | | |


## <a name="review-prerequisites"></a><span data-ttu-id="6d612-157">查看先决条件</span><span class="sxs-lookup"><span data-stu-id="6d612-157">Review prerequisites</span></span>

<span data-ttu-id="6d612-158">Defender for Identity 需要进行一些先决条件工作，以确保本地标识和网络组件满足最低要求。</span><span class="sxs-lookup"><span data-stu-id="6d612-158">Defender for Identity requires some prerequisite work to ensure that your on-premises identity and networking components meet minimum requirements.</span></span> <span data-ttu-id="6d612-159">使用本文作为清单来确保你的环境准备就绪 [：Microsoft Defender for Identity 先决条件](/defender-for-identity/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="6d612-159">Use this article as a checklist to ensure your environment is ready: [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).</span></span>


## <a name="next-steps"></a><span data-ttu-id="6d612-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6d612-160">Next steps</span></span>

<span data-ttu-id="6d612-161">步骤 2/3： [启用评估环境 Defender for Identity](eval-defender-identity-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="6d612-161">Step 2 of 3: [Enable the evaluation environment Defender for Identity](eval-defender-identity-enable-eval.md)</span></span>

<span data-ttu-id="6d612-162">返回到评估 Microsoft [Defender 标识概述](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d612-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="6d612-163">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d612-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 