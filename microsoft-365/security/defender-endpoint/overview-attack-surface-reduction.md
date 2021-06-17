---
title: 减少攻击面概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 的攻击面减少功能。
keywords: asr， 攻击面减少， Microsoft Defender for Endpoint， microsoft defender， 防病毒， av， windows defender
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
ms.date: 06/02/2021
ms.openlocfilehash: 6b3c88f23d3ceffbca588c80b05266d12147ca39
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985020"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="3fbfc-104">攻击面减少功能概述</span><span class="sxs-lookup"><span data-stu-id="3fbfc-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3fbfc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3fbfc-105">**Applies to:**</span></span>

- [<span data-ttu-id="3fbfc-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3fbfc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3fbfc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fbfc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3fbfc-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3fbfc-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="3fbfc-109">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="3fbfc-110">攻击面是组织易受网络威胁和攻击的所有位置。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-110">Attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="3fbfc-111">Defender for Endpoint 包括多项功能，可帮助减少攻击面。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="3fbfc-112">观看以下视频，详细了解攻击面减少。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-112">Watch the following video to learn more about attack surface reduction.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="3fbfc-113">了解有关攻击面减少更多信息的资源</span><span class="sxs-lookup"><span data-stu-id="3fbfc-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="3fbfc-114">如视频所述，Defender for Endpoint 包括多种攻击面减少功能。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="3fbfc-115">使用以下资源了解更多信息：</span><span class="sxs-lookup"><span data-stu-id="3fbfc-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="3fbfc-116">文章</span><span class="sxs-lookup"><span data-stu-id="3fbfc-116">Article</span></span> | <span data-ttu-id="3fbfc-117">说明</span><span class="sxs-lookup"><span data-stu-id="3fbfc-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="3fbfc-118">基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="3fbfc-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="3fbfc-119">在系统启动时和运行时保护和维护系统的完整性。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="3fbfc-120">通过本地和远程证明验证系统完整性。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="3fbfc-121">使用容器隔离Microsoft Edge帮助防范恶意网站。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-121">Use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="3fbfc-122">应用程序控制</span><span class="sxs-lookup"><span data-stu-id="3fbfc-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="3fbfc-123">使用应用程序控制，以便应用程序必须获得信任才能运行。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="3fbfc-124">受控文件夹访问</span><span class="sxs-lookup"><span data-stu-id="3fbfc-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="3fbfc-125">帮助防止恶意或可疑应用 (包括文件加密勒索软件恶意软件) 更改关键系统文件夹中的文件（ (要求Microsoft Defender 防病毒) </span><span class="sxs-lookup"><span data-stu-id="3fbfc-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3fbfc-126">网络保护</span><span class="sxs-lookup"><span data-stu-id="3fbfc-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="3fbfc-127">将保护扩展到组织设备上网络流量和连接。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="3fbfc-128"> (需要Microsoft Defender 防病毒) </span><span class="sxs-lookup"><span data-stu-id="3fbfc-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3fbfc-129">漏洞保护</span><span class="sxs-lookup"><span data-stu-id="3fbfc-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="3fbfc-130">帮助保护组织使用的操作系统和应用免遭攻击。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-130">Help protect the operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="3fbfc-131">Exploit Protection 还适用于第三方防病毒解决方案。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="3fbfc-132">攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="3fbfc-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="3fbfc-133">使用有助于停止恶意软件的智能规则，减少应用程序中的漏洞（攻击面）。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="3fbfc-134"> (需要Microsoft Defender 防病毒) 。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="3fbfc-135">设备控制</span><span class="sxs-lookup"><span data-stu-id="3fbfc-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="3fbfc-136">通过监视和控制组织中设备上使用的媒体（如可移动存储和 USB 驱动器）防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="3fbfc-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |
