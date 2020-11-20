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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373991"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="f9d12-104">Microsoft 安全分数中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f9d12-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f9d12-105">若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。</span><span class="sxs-lookup"><span data-stu-id="f9d12-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="f9d12-106">若要了解计划的更改，请参阅 [Microsoft Secure 评分中的内容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d12-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="f9d12-107">Microsoft 安全分数可在 https://security.microsoft.com/securescore [microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="f9d12-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="f9d12-108">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="f9d12-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="f9d12-109">为 microsoft defender 的终结点 (以前的 Microsoft Defender ATP) 添加了3个与服务相关的改进操作：</span><span class="sxs-lookup"><span data-stu-id="f9d12-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="f9d12-110">修复 Windows 服务的无引号服务路径</span><span class="sxs-lookup"><span data-stu-id="f9d12-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="f9d12-111">将服务可执行路径更改为常见的受保护位置</span><span class="sxs-lookup"><span data-stu-id="f9d12-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="f9d12-112">更改服务帐户以避免 windows 注册表中的缓存密码</span><span class="sxs-lookup"><span data-stu-id="f9d12-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="f9d12-113">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="f9d12-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f9d12-114">删除与 Microsoft Defender for Endpoint 相关的改进操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="f9d12-115">设置 Microsoft Defender SmartScreen Windows 应用商店应用程序 web 内容检查以警告</span><span class="sxs-lookup"><span data-stu-id="f9d12-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="f9d12-116">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="f9d12-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="f9d12-117">Azure Active Directory 的更新改进操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="f9d12-118">启用策略以阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="f9d12-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="f9d12-119">标识安全分数和图形 API 不兼容</span><span class="sxs-lookup"><span data-stu-id="f9d12-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="f9d12-120">在最近发布的 Microsoft 安全分数中，已发布了一个改进的计分模型。</span><span class="sxs-lookup"><span data-stu-id="f9d12-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="f9d12-121">通过这些更改，可以更灵活、准确地查看安全状况。</span><span class="sxs-lookup"><span data-stu-id="f9d12-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="f9d12-122">但是，这些更新已使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。</span><span class="sxs-lookup"><span data-stu-id="f9d12-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="f9d12-123">在时间中，标识安全分数和图形 API 将采用新的评分模型。</span><span class="sxs-lookup"><span data-stu-id="f9d12-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="f9d12-124">在此之前，客户将看到 Microsoft 安全分数、标识安全分数和图形 API 所报告的分数之间的差异。</span><span class="sxs-lookup"><span data-stu-id="f9d12-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="f9d12-125">对于此导致的不便，我们深表歉意，并在努力确保这些体验在将来更具兼容性。</span><span class="sxs-lookup"><span data-stu-id="f9d12-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="f9d12-126">更新的提高操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-126">Updated improvement actions</span></span>

- <span data-ttu-id="f9d12-127">添加了 Azure Active Directory 改善操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="f9d12-128">添加了 Microsoft Defender for Identity 改进操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="f9d12-129">对 Microsoft Defender for Endpoint 威胁的支持 [& 漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议</span><span class="sxs-lookup"><span data-stu-id="f9d12-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="f9d12-130">TVM 提供的所有已发布的安全建议现已推出</span><span class="sxs-lookup"><span data-stu-id="f9d12-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="f9d12-131">更新的界面和功能</span><span class="sxs-lookup"><span data-stu-id="f9d12-131">Updated interface and functionality</span></span>

* <span data-ttu-id="f9d12-132">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="f9d12-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="f9d12-133">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="f9d12-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="f9d12-134">更好地跟踪和理解分数回归</span><span class="sxs-lookup"><span data-stu-id="f9d12-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="f9d12-135">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="f9d12-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="f9d12-136">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="f9d12-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="f9d12-137">更多！</span><span class="sxs-lookup"><span data-stu-id="f9d12-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="f9d12-138">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="f9d12-138">We want to hear from you</span></span>

<span data-ttu-id="f9d12-139">如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="f9d12-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="f9d12-140">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="f9d12-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="f9d12-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="f9d12-141">Related resources</span></span>

- [<span data-ttu-id="f9d12-142">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="f9d12-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="f9d12-143">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="f9d12-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="f9d12-144">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="f9d12-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
