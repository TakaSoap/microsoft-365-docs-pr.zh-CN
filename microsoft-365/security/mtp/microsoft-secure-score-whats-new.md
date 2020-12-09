---
title: Microsoft 安全分数中的新增功能
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数发生了哪些新更改。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: 4b25f701aca24563dc4f1a15f78a80e1e2064367
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604379"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="086d6-104">Microsoft 安全分数中的新增功能</span><span class="sxs-lookup"><span data-stu-id="086d6-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="086d6-105">若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。</span><span class="sxs-lookup"><span data-stu-id="086d6-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="086d6-106">若要了解计划的更改，请参阅 [Microsoft 安全分数中的内容？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="086d6-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="086d6-107">Microsoft 安全分数可在 https://security.microsoft.com/securescore [microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="086d6-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="086d6-108">2020年11月</span><span class="sxs-lookup"><span data-stu-id="086d6-108">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="086d6-109">删除了通过安全分数创建 ServiceNow 票证的能力</span><span class="sxs-lookup"><span data-stu-id="086d6-109">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="086d6-110">通过转到 **共享 > servicenow** 无法再提供通过安全得分创建 servicenow 票证的功能。</span><span class="sxs-lookup"><span data-stu-id="086d6-110">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="086d6-111">感谢你的反馈，并在我们确定后续步骤时继续提供支持。</span><span class="sxs-lookup"><span data-stu-id="086d6-111">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="086d6-112">为 microsoft defender 的终结点 (以前的 Microsoft Defender ATP) 添加了3个与服务相关的改进操作：</span><span class="sxs-lookup"><span data-stu-id="086d6-112">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="086d6-113">修复 Windows 服务的无引号服务路径</span><span class="sxs-lookup"><span data-stu-id="086d6-113">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="086d6-114">将服务可执行路径更改为常见的受保护位置</span><span class="sxs-lookup"><span data-stu-id="086d6-114">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="086d6-115">更改服务帐户以避免 windows 注册表中的缓存密码</span><span class="sxs-lookup"><span data-stu-id="086d6-115">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="086d6-116">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="086d6-116">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="086d6-117">删除与 Microsoft Defender for Endpoint 相关的改进操作</span><span class="sxs-lookup"><span data-stu-id="086d6-117">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="086d6-118">设置 Microsoft Defender SmartScreen Windows 应用商店应用程序 web 内容检查以警告</span><span class="sxs-lookup"><span data-stu-id="086d6-118">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="086d6-119">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="086d6-119">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="086d6-120">Azure Active Directory 的更新改进操作</span><span class="sxs-lookup"><span data-stu-id="086d6-120">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="086d6-121">启用策略以阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="086d6-121">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="086d6-122">标识安全分数和图形 API 不兼容</span><span class="sxs-lookup"><span data-stu-id="086d6-122">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="086d6-123">在最近发布的 Microsoft 安全分数中，已发布了一个改进的计分模型。</span><span class="sxs-lookup"><span data-stu-id="086d6-123">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="086d6-124">通过这些更改，可以更灵活、准确地查看安全状况。</span><span class="sxs-lookup"><span data-stu-id="086d6-124">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="086d6-125">但是，这些更新已使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。</span><span class="sxs-lookup"><span data-stu-id="086d6-125">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="086d6-126">在时间中，标识安全分数和图形 API 将采用新的评分模型。</span><span class="sxs-lookup"><span data-stu-id="086d6-126">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="086d6-127">在此之前，客户将看到 Microsoft 安全分数、标识安全分数和图形 API 所报告的分数之间的差异。</span><span class="sxs-lookup"><span data-stu-id="086d6-127">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="086d6-128">对于此导致的不便，我们深表歉意，并在努力确保这些体验在将来更具兼容性。</span><span class="sxs-lookup"><span data-stu-id="086d6-128">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="086d6-129">更新的提高操作</span><span class="sxs-lookup"><span data-stu-id="086d6-129">Updated improvement actions</span></span>

- <span data-ttu-id="086d6-130">添加了 Azure Active Directory 改善操作</span><span class="sxs-lookup"><span data-stu-id="086d6-130">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="086d6-131">添加了 Microsoft Defender for Identity 改进操作</span><span class="sxs-lookup"><span data-stu-id="086d6-131">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="086d6-132">对 Microsoft Defender for Endpoint 威胁的支持 [& 漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议</span><span class="sxs-lookup"><span data-stu-id="086d6-132">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="086d6-133">TVM 提供的所有已发布的安全建议现已推出</span><span class="sxs-lookup"><span data-stu-id="086d6-133">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="086d6-134">更新的界面和功能</span><span class="sxs-lookup"><span data-stu-id="086d6-134">Updated interface and functionality</span></span>

* <span data-ttu-id="086d6-135">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="086d6-135">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="086d6-136">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="086d6-136">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="086d6-137">更好地跟踪和理解分数回归</span><span class="sxs-lookup"><span data-stu-id="086d6-137">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="086d6-138">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="086d6-138">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="086d6-139">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="086d6-139">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="086d6-140">更多！</span><span class="sxs-lookup"><span data-stu-id="086d6-140">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="086d6-141">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="086d6-141">We want to hear from you</span></span>

<span data-ttu-id="086d6-142">如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="086d6-142">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="086d6-143">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="086d6-143">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="086d6-144">相关资源</span><span class="sxs-lookup"><span data-stu-id="086d6-144">Related resources</span></span>

- [<span data-ttu-id="086d6-145">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="086d6-145">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="086d6-146">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="086d6-146">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="086d6-147">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="086d6-147">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
