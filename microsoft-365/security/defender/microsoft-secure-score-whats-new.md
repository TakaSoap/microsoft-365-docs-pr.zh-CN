---
title: Microsoft 安全分数中的新增功能
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数发生了哪些新更改。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， Microsoft 安全分数， microsoft 365 安全中心
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 5a868904a43e17952368e097c0b0e963252d5bed
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570359"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="c7c3d-104">Microsoft 安全分数中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c7c3d-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c7c3d-105">为了更好地代表 Microsoft 安全分数的安全状态，我们进行了一些更改。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="c7c3d-106">若要了解计划更改，请参阅 Microsoft 安全分数 [中即将提供哪些功能？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="c7c3d-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="c7c3d-107">Microsoft 安全分数位于 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>
    
## <a name="february-2021"></a><span data-ttu-id="c7c3d-108">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-108">February 2021</span></span>

### <a name="compatibility-with-graph-api"></a><span data-ttu-id="c7c3d-109">与 Graph API 的兼容性</span><span class="sxs-lookup"><span data-stu-id="c7c3d-109">Compatibility with Graph API</span></span>

<span data-ttu-id="c7c3d-110">通过 Graph API 提供的 Microsoft 安全分数建议的外观和权重与当前在 Microsoft 365 安全中心看到的建议相同。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-110">Microsoft Secure Score recommendations delivered via Graph API will look and be weighted the same as the recommendations you currently see in the Microsoft 365 security center.</span></span>

## <a name="january-2021"></a><span data-ttu-id="c7c3d-111">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-111">January 2021</span></span>

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a><span data-ttu-id="c7c3d-112">添加了针对 Microsoft Teams 的第一个安全建议</span><span class="sxs-lookup"><span data-stu-id="c7c3d-112">Added our first security recommendation for Microsoft Teams</span></span>

<span data-ttu-id="c7c3d-113">Microsoft Teams 客户将在安全分数中看到"限制匿名用户加入会议"作为新的改进操作。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-113">Microsoft Teams customers will see "Restrict anonymous users from joining meetings" as a new improvement action in Secure Score.</span></span>

## <a name="december-2020"></a><span data-ttu-id="c7c3d-114">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-114">December 2020</span></span>

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="c7c3d-115">为 Microsoft Defender for Endpoint 添加了六个与帐户相关的改进操作 (Microsoft Defender ATP) ：</span><span class="sxs-lookup"><span data-stu-id="c7c3d-115">Added six accounts-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="c7c3d-116">将"最小密码长度"设置为"14 个或多个字符"</span><span class="sxs-lookup"><span data-stu-id="c7c3d-116">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="c7c3d-117">将"强制密码历史记录"设置为"24 个或多个密码 (") "</span><span class="sxs-lookup"><span data-stu-id="c7c3d-117">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="c7c3d-118">将"最长密码使用时间"设置为"60 天或更少天，但不设置为 0"</span><span class="sxs-lookup"><span data-stu-id="c7c3d-118">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="c7c3d-119">将"最短密码使用时间"设置为"1 天或 (天) "</span><span class="sxs-lookup"><span data-stu-id="c7c3d-119">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="c7c3d-120">禁用内置管理员帐户</span><span class="sxs-lookup"><span data-stu-id="c7c3d-120">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="c7c3d-121">禁用内置来宾帐户</span><span class="sxs-lookup"><span data-stu-id="c7c3d-121">Disable the built-in Guest account</span></span>

## <a name="november-2020"></a><span data-ttu-id="c7c3d-122">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-122">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="c7c3d-123">删除了通过安全分数创建 ServiceNow 票证的能力</span><span class="sxs-lookup"><span data-stu-id="c7c3d-123">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="c7c3d-124">不再提供通过安全分数创建 ServiceNow 票证（通过> **ServiceNow）** 的能力。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-124">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="c7c3d-125">感谢你提供反馈，并继续支持我们确定下一步。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-125">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="c7c3d-126">为 Microsoft Defender 终结点中心添加了三个与服务相关的改进 (Microsoft Defender ATP) ：</span><span class="sxs-lookup"><span data-stu-id="c7c3d-126">Added three services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="c7c3d-127">修复 Windows 服务的未标出服务路径</span><span class="sxs-lookup"><span data-stu-id="c7c3d-127">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="c7c3d-128">将服务可执行路径更改为公用受保护位置</span><span class="sxs-lookup"><span data-stu-id="c7c3d-128">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="c7c3d-129">更改服务帐户以避免在 Windows 注册表中缓存密码</span><span class="sxs-lookup"><span data-stu-id="c7c3d-129">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="c7c3d-130">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-130">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c7c3d-131">删除与 Microsoft Defender for Endpoint 相关的改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-131">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="c7c3d-132">将 Microsoft Defender SmartScreen Windows 应用商店应用 Web 内容检查设置为警告</span><span class="sxs-lookup"><span data-stu-id="c7c3d-132">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="c7c3d-133">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="c7c3d-133">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="c7c3d-134">更新了 Azure Active Directory 的改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-134">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="c7c3d-135">启用策略以阻止旧身份验证</span><span class="sxs-lookup"><span data-stu-id="c7c3d-135">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score"></a><span data-ttu-id="c7c3d-136">与标识安全分数不兼容</span><span class="sxs-lookup"><span data-stu-id="c7c3d-136">Incompatibility with Identity Secure Score</span></span>

<span data-ttu-id="c7c3d-137">在 Microsoft 安全分数的最近版本中，发布了改进的评分模型。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-137">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="c7c3d-138">通过这些更改，可以更灵活和准确地查看安全状态。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-138">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="c7c3d-139">但是，这些更新使 Microsoft 安全分数暂时与标识安全分数不兼容。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-139">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score.</span></span>

<span data-ttu-id="c7c3d-140">Identity Secure Score 将采用新的评分模型。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-140">In time, Identity Secure Score will adopt the new scoring model.</span></span> <span data-ttu-id="c7c3d-141">在此之前，客户将看到 Microsoft 安全分数和标识安全分数报告的分数的差异。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-141">Until then, customers will see differences in the scores reported by Microsoft Secure Score and the Identity Secure Score.</span></span> <span data-ttu-id="c7c3d-142">对此引起的不便，我们感到抱歉，并致力于确保这些体验在未来更加兼容。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-142">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="c7c3d-143">更新后的改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-143">Updated improvement actions</span></span>

- <span data-ttu-id="c7c3d-144">添加了 Azure Active Directory 改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-144">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="c7c3d-145">添加了 Microsoft Defender for Identity 改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-145">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="c7c3d-146">支持 Microsoft Defender 终结点 [威胁&漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议</span><span class="sxs-lookup"><span data-stu-id="c7c3d-146">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="c7c3d-147">现在，TVM 提供的所有已发布安全建议都可用</span><span class="sxs-lookup"><span data-stu-id="c7c3d-147">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="c7c3d-148">更新的界面和功能</span><span class="sxs-lookup"><span data-stu-id="c7c3d-148">Updated interface and functionality</span></span>

* <span data-ttu-id="c7c3d-149">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="c7c3d-149">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="c7c3d-150">跟踪分数并衡量分数基准的新增方法</span><span class="sxs-lookup"><span data-stu-id="c7c3d-150">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="c7c3d-151">更好地跟踪和理解分数回归</span><span class="sxs-lookup"><span data-stu-id="c7c3d-151">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="c7c3d-152">筛选、标记、搜索和分组改进操作</span><span class="sxs-lookup"><span data-stu-id="c7c3d-152">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="c7c3d-153">使用分数预测和计划操作管理你的未来目标</span><span class="sxs-lookup"><span data-stu-id="c7c3d-153">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="c7c3d-154">等等！</span><span class="sxs-lookup"><span data-stu-id="c7c3d-154">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="c7c3d-155">欢迎提出宝贵意见</span><span class="sxs-lookup"><span data-stu-id="c7c3d-155">We want to hear from you</span></span>

<span data-ttu-id="c7c3d-156">如果有任何问题，请通过发布到安全、隐私和合规性社区 [&告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。</span><span class="sxs-lookup"><span data-stu-id="c7c3d-156">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="c7c3d-157">We're monitoring the community and will provide help.</span><span class="sxs-lookup"><span data-stu-id="c7c3d-157">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c7c3d-158">相关资源</span><span class="sxs-lookup"><span data-stu-id="c7c3d-158">Related resources</span></span>

- [<span data-ttu-id="c7c3d-159">评估安全状况</span><span class="sxs-lookup"><span data-stu-id="c7c3d-159">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="c7c3d-160">跟踪 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="c7c3d-160">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="c7c3d-161">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="c7c3d-161">What's coming</span></span>](microsoft-secure-score-whats-coming.md)