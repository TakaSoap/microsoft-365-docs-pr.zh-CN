---
title: 测试 Microsoft Defender for Endpoint 功能在审核模式下如何工作
description: 审核模式可帮助你查看 Microsoft Defender for Endpoint 在启用后如何保护你的设备。
keywords: 攻击防护， 审核， 审核， 模式， 已启用， 禁用， 测试， 演示， 评估， 实验室
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: c2ff6eac3254e855d4858edc218ae5df034352e4
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925647"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="711ed-104">在 Microsoft Defender for Endpoint 中测试攻击面减少</span><span class="sxs-lookup"><span data-stu-id="711ed-104">Test attack surface reduction in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="711ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="711ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="711ed-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="711ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="711ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="711ed-108">如果你是组织安全团队的一员，你可以配置攻击面减少功能以在审核模式下运行，以查看这些功能在组织中如何工作。</span><span class="sxs-lookup"><span data-stu-id="711ed-108">If you're part of your organization's security team, you can configure attack surface reduction capabilities to run in audit mode to see how they'll work in your organization.</span></span> <span data-ttu-id="711ed-109">特别是，可以在审核模式下启用攻击面减少规则、Exploit Protection、网络保护和受控文件夹访问权限。</span><span class="sxs-lookup"><span data-stu-id="711ed-109">In particular, you can enable attack surface reduction rules, exploit protection, network protection, and controlled folder access in audit mode.</span></span> <span data-ttu-id="711ed-110">通过审核模式，你可以查看启用该功能后将发生的情况记录。</span><span class="sxs-lookup"><span data-stu-id="711ed-110">Audit mode lets you see a record of what *would* have happened if you had enabled the feature.</span></span>

<span data-ttu-id="711ed-111">在测试这些功能在组织中工作的方式时，可能需要启用审核模式。</span><span class="sxs-lookup"><span data-stu-id="711ed-111">You may want to enable audit mode when testing how the features will work in your organization.</span></span> <span data-ttu-id="711ed-112">这将帮助确保你的业务线应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="711ed-112">This will help make sure your line-of-business apps aren't affected.</span></span> <span data-ttu-id="711ed-113">还可以了解在一定时段内发生的可疑文件修改尝试次数。</span><span class="sxs-lookup"><span data-stu-id="711ed-113">You can also get an idea of how many suspicious file modification attempts occur over a certain period of time.</span></span>

<span data-ttu-id="711ed-114">这些功能不会阻止或阻止应用、脚本或文件被修改。</span><span class="sxs-lookup"><span data-stu-id="711ed-114">The features won't block or prevent apps, scripts, or files from being modified.</span></span> <span data-ttu-id="711ed-115">但是，Windows事件日志将记录事件，就像功能完全启用一样。</span><span class="sxs-lookup"><span data-stu-id="711ed-115">However, the Windows Event Log will record events as if the features were fully enabled.</span></span> <span data-ttu-id="711ed-116">使用审核模式，你可以查看事件日志，以查看如果启用该功能，将有什么影响。</span><span class="sxs-lookup"><span data-stu-id="711ed-116">With audit mode, you can review the event log to see what impact the feature would have had if it was enabled.</span></span>

<span data-ttu-id="711ed-117">若要查找审核的条目，请转到应用程序和服务Microsoft Windows  >    >  **Windows Defender**  >    >  **操作**。</span><span class="sxs-lookup"><span data-stu-id="711ed-117">To find the audited entries, go to **Applications and Services** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

<span data-ttu-id="711ed-118">可以使用 Defender for Endpoint 获取每个事件的更多详细信息，尤其是调查攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="711ed-118">You can use Defender for Endpoint to get greater details for each event, especially for investigating attack surface reduction rules.</span></span> <span data-ttu-id="711ed-119">使用 Defender for Endpoint 控制台，你可以调查作为警报时间线和调查方案的 [一部分的问题](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="711ed-119">Using the Defender for Endpoint console lets you [investigate issues as part of the alert timeline and investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="711ed-120">可以使用组策略、PowerShell 和配置服务提供程序 (启用) 模式。</span><span class="sxs-lookup"><span data-stu-id="711ed-120">You can use Group Policy, PowerShell, and configuration service providers (CSPs) to enable audit mode.</span></span>

> [!TIP]
> <span data-ttu-id="711ed-121">您还可以访问 Testground Windows Defender[网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)确认这些功能是否正常工作并查看它们如何工作。</span><span class="sxs-lookup"><span data-stu-id="711ed-121">You can also visit the Windows Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

| <span data-ttu-id="711ed-122">审核选项</span><span class="sxs-lookup"><span data-stu-id="711ed-122">Audit options</span></span> | <span data-ttu-id="711ed-123">如何启用审核模式</span><span class="sxs-lookup"><span data-stu-id="711ed-123">How to enable audit mode</span></span> | <span data-ttu-id="711ed-124">如何查看事件</span><span class="sxs-lookup"><span data-stu-id="711ed-124">How to view events</span></span> |
|---------|---------|---------|
| <span data-ttu-id="711ed-125">审核适用于所有事件</span><span class="sxs-lookup"><span data-stu-id="711ed-125">Audit applies to all events</span></span> | [<span data-ttu-id="711ed-126">启用受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="711ed-126">Enable controlled folder access</span></span>](enable-controlled-folders.md) | [<span data-ttu-id="711ed-127">受控文件夹访问事件</span><span class="sxs-lookup"><span data-stu-id="711ed-127">Controlled folder access events</span></span>](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| <span data-ttu-id="711ed-128">审核适用于单个规则</span><span class="sxs-lookup"><span data-stu-id="711ed-128">Audit applies to individual rules</span></span> | [<span data-ttu-id="711ed-129">启用攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="711ed-129">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md) | [<span data-ttu-id="711ed-130">攻击面减少规则事件</span><span class="sxs-lookup"><span data-stu-id="711ed-130">Attack surface reduction rule events</span></span>](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| <span data-ttu-id="711ed-131">审核适用于所有事件</span><span class="sxs-lookup"><span data-stu-id="711ed-131">Audit applies to all events</span></span> | [<span data-ttu-id="711ed-132">启用网络保护</span><span class="sxs-lookup"><span data-stu-id="711ed-132">Enable network protection</span></span>](enable-network-protection.md) | [<span data-ttu-id="711ed-133">网络保护事件</span><span class="sxs-lookup"><span data-stu-id="711ed-133">Network protection events</span></span>](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| <span data-ttu-id="711ed-134">审核适用于单个缓解</span><span class="sxs-lookup"><span data-stu-id="711ed-134">Audit applies to individual mitigations</span></span> | [<span data-ttu-id="711ed-135">启用漏洞保护</span><span class="sxs-lookup"><span data-stu-id="711ed-135">Enable exploit protection</span></span>](enable-exploit-protection.md) | [<span data-ttu-id="711ed-136">Exploit Protection 事件</span><span class="sxs-lookup"><span data-stu-id="711ed-136">Exploit protection events</span></span>](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)


