---
title: 减少攻击面概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 的攻击面减少功能。
keywords: asr， 攻击面减少， microsoft defender atp， microsoft defender for endpoint， microsoft defender， 防病毒， av， windows defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dbc794338442f9ed54a7227e702de1039b5ea71c
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861739"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="c6ce0-104">减少攻击面概述</span><span class="sxs-lookup"><span data-stu-id="c6ce0-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6ce0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c6ce0-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6ce0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c6ce0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6ce0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6ce0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6ce0-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c6ce0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c6ce0-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="c6ce0-110">通过最大程度地减少组织易受网络威胁和攻击的位置，帮助减少攻击面。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="c6ce0-111">使用以下资源为贵组织的设备和应用程序配置保护。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="c6ce0-112">文章</span><span class="sxs-lookup"><span data-stu-id="c6ce0-112">Article</span></span> | <span data-ttu-id="c6ce0-113">说明</span><span class="sxs-lookup"><span data-stu-id="c6ce0-113">Description</span></span>
-|-
[<span data-ttu-id="c6ce0-114">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="c6ce0-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="c6ce0-115">使用有助于停止恶意软件的智能规则，减少应用程序中的漏洞（攻击面）。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="c6ce0-116"> (需要 Microsoft Defender 防病毒) 。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="c6ce0-117">基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="c6ce0-117">Hardware-based isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="c6ce0-118">在系统启动时和运行时保护和维护系统的完整性。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="c6ce0-119">通过本地和远程证明验证系统完整性。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="c6ce0-120">此外，使用 Microsoft Edge 的容器隔离来帮助防范恶意网站。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="c6ce0-121">应用程序控制</span><span class="sxs-lookup"><span data-stu-id="c6ce0-121">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control.md) | <span data-ttu-id="c6ce0-122">使用应用程序控制，以便应用程序必须获得信任才能运行。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="c6ce0-123">漏洞保护</span><span class="sxs-lookup"><span data-stu-id="c6ce0-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="c6ce0-124">帮助保护组织使用的操作系统和应用免遭攻击。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="c6ce0-125">Exploit Protection 还适用于第三方防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="c6ce0-126">网络保护</span><span class="sxs-lookup"><span data-stu-id="c6ce0-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="c6ce0-127">将保护扩展到组织设备上网络流量和连接。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="c6ce0-128"> (需要 Microsoft Defender 防病毒) </span><span class="sxs-lookup"><span data-stu-id="c6ce0-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="c6ce0-129">Web 保护功能</span><span class="sxs-lookup"><span data-stu-id="c6ce0-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="c6ce0-130">保护设备免受 Web 威胁，并帮助您控制不需要的内容。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="c6ce0-131">受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="c6ce0-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="c6ce0-132">帮助防止恶意或可疑应用 (包括文件加密勒索软件恶意软件) 需要 Microsoft Defender 防病毒程序更改关键系统 (中的) </span><span class="sxs-lookup"><span data-stu-id="c6ce0-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="c6ce0-133">网络防火墙</span><span class="sxs-lookup"><span data-stu-id="c6ce0-133">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security.md) | <span data-ttu-id="c6ce0-134">通过双向网络流量筛选，防止未经授权的流量流入或流出组织设备。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="c6ce0-135">关于减少攻击面的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c6ce0-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="c6ce0-136">有关攻击面减少规则、许可等的常见问题。</span><span class="sxs-lookup"><span data-stu-id="c6ce0-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
