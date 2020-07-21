---
title: Microsoft 安全分数中的新增功能
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数发生了哪些新更改。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
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
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200104"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="c0680-104">Microsoft 安全分数中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c0680-104">What's new in Microsoft Secure Score</span></span>

<span data-ttu-id="c0680-105">若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。</span><span class="sxs-lookup"><span data-stu-id="c0680-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="c0680-106">若要了解计划的更改，请参阅[Microsoft Secure 评分中的内容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="c0680-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="june-2020"></a><span data-ttu-id="c0680-107">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="c0680-107">June 2020</span></span>

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c0680-108">Microsoft Defender 高级威胁防护的已删除改进操作</span><span class="sxs-lookup"><span data-stu-id="c0680-108">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="c0680-109">打开攻击面降低规则</span><span class="sxs-lookup"><span data-stu-id="c0680-109">Turn on Attack Surface Reduction rules</span></span>

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c0680-110">新增了 Microsoft Defender 高级威胁防护的改进措施</span><span class="sxs-lookup"><span data-stu-id="c0680-110">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="c0680-111">阻止 Adobe Reader 创建子流程</span><span class="sxs-lookup"><span data-stu-id="c0680-111">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="c0680-112">对勒索软件使用高级防护</span><span class="sxs-lookup"><span data-stu-id="c0680-112">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="c0680-113">阻止所有 Office 应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="c0680-113">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="c0680-114">阻止 Office 应用程序创建可执行内容</span><span class="sxs-lookup"><span data-stu-id="c0680-114">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="c0680-115">阻止 JavaScript 或 VBScript 启动下载的可执行内容</span><span class="sxs-lookup"><span data-stu-id="c0680-115">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="c0680-116">阻止执行可能模糊的脚本</span><span class="sxs-lookup"><span data-stu-id="c0680-116">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="c0680-117">阻止来自电子邮件客户端和 web 邮件的可执行内容</span><span class="sxs-lookup"><span data-stu-id="c0680-117">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="c0680-118">阻止 Office 通信应用程序创建子进程</span><span class="sxs-lookup"><span data-stu-id="c0680-118">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="c0680-119">阻止从 USB 运行的不受信任和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="c0680-119">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="c0680-120">通过 WMI 事件订阅阻止持久化</span><span class="sxs-lookup"><span data-stu-id="c0680-120">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="c0680-121">阻止 Office 应用程序将代码注入其他进程</span><span class="sxs-lookup"><span data-stu-id="c0680-121">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="c0680-122">阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件</span><span class="sxs-lookup"><span data-stu-id="c0680-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="c0680-123">阻止进程创建源自 PSExec 和 WMI 命令</span><span class="sxs-lookup"><span data-stu-id="c0680-123">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="c0680-124">阻止从 Windows 本地安全颁发机构子系统盗取凭据（lsass.exe）</span><span class="sxs-lookup"><span data-stu-id="c0680-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="c0680-125">阻止来自 Office 宏的 Win32 API 调用</span><span class="sxs-lookup"><span data-stu-id="c0680-125">Block Win32 API calls from Office macros</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="c0680-126">标识安全分数和图形 API 不兼容</span><span class="sxs-lookup"><span data-stu-id="c0680-126">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="c0680-127">在最近发布的 Microsoft 安全分数中，已发布了一个改进的计分模型。</span><span class="sxs-lookup"><span data-stu-id="c0680-127">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="c0680-128">通过这些更改，可以更灵活、准确地查看安全状况。</span><span class="sxs-lookup"><span data-stu-id="c0680-128">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="c0680-129">但是，这些更新已使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。</span><span class="sxs-lookup"><span data-stu-id="c0680-129">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="c0680-130">在时间中，标识安全分数和图形 API 将采用新的评分模型。</span><span class="sxs-lookup"><span data-stu-id="c0680-130">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="c0680-131">在此之前，客户将看到 Microsoft 安全分数、标识安全分数和图形 API 所报告的分数之间的差异。</span><span class="sxs-lookup"><span data-stu-id="c0680-131">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="c0680-132">对于此导致的不便，我们深表歉意，并在努力确保这些体验在将来更具兼容性。</span><span class="sxs-lookup"><span data-stu-id="c0680-132">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="c0680-133">更新的提高操作</span><span class="sxs-lookup"><span data-stu-id="c0680-133">Updated improvement actions</span></span>

- <span data-ttu-id="c0680-134">添加了 Azure Active Directory 改善操作</span><span class="sxs-lookup"><span data-stu-id="c0680-134">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="c0680-135">添加了 Azure 高级威胁防护改进操作</span><span class="sxs-lookup"><span data-stu-id="c0680-135">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="c0680-136">对 Microsoft Defender ATP 威胁的支持[& 漏洞管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)安全建议</span><span class="sxs-lookup"><span data-stu-id="c0680-136">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="c0680-137">TVM 提供的所有已发布的安全建议现已推出</span><span class="sxs-lookup"><span data-stu-id="c0680-137">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="c0680-138">更新的界面和功能</span><span class="sxs-lookup"><span data-stu-id="c0680-138">Updated interface and functionality</span></span>

* <span data-ttu-id="c0680-139">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="c0680-139">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="c0680-140">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="c0680-140">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="c0680-141">更好地跟踪和理解分数回归</span><span class="sxs-lookup"><span data-stu-id="c0680-141">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="c0680-142">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="c0680-142">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="c0680-143">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="c0680-143">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="c0680-144">更多！</span><span class="sxs-lookup"><span data-stu-id="c0680-144">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="c0680-145">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="c0680-145">We want to hear from you</span></span>

<span data-ttu-id="c0680-146">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="c0680-146">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="c0680-147">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="c0680-147">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c0680-148">相关资源</span><span class="sxs-lookup"><span data-stu-id="c0680-148">Related resources</span></span>

- [<span data-ttu-id="c0680-149">评估安全状况</span><span class="sxs-lookup"><span data-stu-id="c0680-149">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="c0680-150">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="c0680-150">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="c0680-151">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="c0680-151">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
