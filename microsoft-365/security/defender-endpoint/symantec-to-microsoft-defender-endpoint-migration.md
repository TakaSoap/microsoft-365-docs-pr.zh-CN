---
title: 从 Symantec 迁移到 Microsoft Defender for Endpoint
description: 大致了解如何从 Symantec 切换到 Microsoft Defender for Endpoint
keywords: migration， Microsoft Defender for Endpoint， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 62a916fcf89432a512ada1b85002cce401e4dd23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530894"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="ee504-104">从 Symantec 迁移到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee504-104">Migrate from Symantec to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="ee504-105">如果你计划从 Symantec Endpoint Protection (Symantec) 切换到适用于 Endpoint (的[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)) ，你的位置正确。</span><span class="sxs-lookup"><span data-stu-id="ee504-105">If you are planning to switch from Symantec Endpoint Protection (Symantec) to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Microsoft Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="ee504-106">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="ee504-106">Use this article as a guide.</span></span>

<span data-ttu-id="ee504-107">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ee504-107">**Applies to:**</span></span>
- [<span data-ttu-id="ee504-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee504-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee504-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee504-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="从 Symantec 迁移到 Defender for Endpoint 的概述":::

<span data-ttu-id="ee504-111">当你从 Symantec 切换到适用于终结点的 Defender 时，你将从主动模式下的 Symantec 解决方案开始，在被动模式下配置适用于终结点的 Defender，载入到适用于终结点的 Defender，然后将适用于终结点的 Defender 设置为活动模式并删除 Symantec。</span><span class="sxs-lookup"><span data-stu-id="ee504-111">When you make the switch from Symantec to Defender for Endpoint, you begin with your Symantec solution in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, and then set Defender for Endpoint to active mode and remove Symantec.</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="ee504-112">迁移过程</span><span class="sxs-lookup"><span data-stu-id="ee504-112">The migration process</span></span>

<span data-ttu-id="ee504-113">从 Symantec 切换到 Microsoft Defender for Endpoint 时，将按照一个可以分为三个阶段的过程操作，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="ee504-113">When you switch from Symantec to Microsoft Defender for Endpoint, you follow a process that can be divided into three phases, as described in the following table:</span></span>

![迁移阶段 - 准备、设置、载入](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="ee504-115">阶段</span><span class="sxs-lookup"><span data-stu-id="ee504-115">Phase</span></span> |<span data-ttu-id="ee504-116">说明</span><span class="sxs-lookup"><span data-stu-id="ee504-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="ee504-117">准备迁移</span><span class="sxs-lookup"><span data-stu-id="ee504-117">Prepare for your migration</span></span>](symantec-to-microsoft-defender-atp-prepare.md) |<span data-ttu-id="ee504-118">在 **"准备**"阶段，更新组织设备、获取 Microsoft Defender for Endpoint、规划角色和权限，并授予对 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="ee504-118">During the **Prepare** phase, you update your organization's devices, get Microsoft Defender for Endpoint, plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ee504-119">还可以配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Defender 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ee504-119">You also configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="ee504-120">设置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee504-120">Set up Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-setup.md) |<span data-ttu-id="ee504-121">在 **设置阶段**，启用Microsoft Defender 防病毒并设置为被动模式。</span><span class="sxs-lookup"><span data-stu-id="ee504-121">During the **Setup** phase, you enable Microsoft Defender Antivirus and set it to passive mode.</span></span> <span data-ttu-id="ee504-122">还可以为 & 和 Symantec Microsoft Defender 防病毒配置设置Endpoint Protection。</span><span class="sxs-lookup"><span data-stu-id="ee504-122">You also configure settings & exclusions for Microsoft Defender Antivirus and Symantec Endpoint Protection.</span></span> <span data-ttu-id="ee504-123">然后，创建设备组、集合和组织单位。</span><span class="sxs-lookup"><span data-stu-id="ee504-123">Then, you create your device groups, collections, and organizational units.</span></span> <span data-ttu-id="ee504-124">最后，配置反恶意软件策略和实时保护设置。</span><span class="sxs-lookup"><span data-stu-id="ee504-124">Finally, you configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="ee504-125">载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ee504-125">Onboard to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-onboard.md) |<span data-ttu-id="ee504-126">在载入 **阶段，** 将设备载入到 Microsoft Defender for Endpoint，确认 Microsfot Defender 防病毒正在被动模式下运行，并验证终结点是否正在与 Defender for Endpoint 通信。</span><span class="sxs-lookup"><span data-stu-id="ee504-126">During the **Onboard** phase, you onboard your devices to Microsoft Defender for Endpoint, confirm that Microsfot Defender Antivirus is running in passive mode, and verify that your endpoints are communicating with Defender for Endpoint.</span></span> <span data-ttu-id="ee504-127">然后，卸载 Symantec 并确保 Defender for Endpoint 正常工作。</span><span class="sxs-lookup"><span data-stu-id="ee504-127">Then, you uninstall Symantec and make sure that Defender for Endpoint is working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ee504-128">Microsoft Defender for Endpoint 中包含哪些内容？</span><span class="sxs-lookup"><span data-stu-id="ee504-128">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="ee504-129">在此迁移指南中，我们重点介绍下[](microsoft-defender-antivirus-in-windows-10.md)一代保护和终结点检测和[](overview-endpoint-detection-response.md)响应功能，作为迁移到 Microsoft Defender for Endpoint 的起点。</span><span class="sxs-lookup"><span data-stu-id="ee504-129">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ee504-130">但是，Microsoft Defender for Endpoint 包括的不仅仅是防病毒和终结点保护。</span><span class="sxs-lookup"><span data-stu-id="ee504-130">However, Microsoft Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="ee504-131">Microsoft Defender for Endpoint 是一个统一的平台，可用于预防性保护、入侵后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="ee504-131">Microsoft Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="ee504-132">下表总结了 Microsoft Defender for Endpoint 中的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="ee504-132">The following table summarizes features and capabilities in Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="ee504-133">功能</span><span class="sxs-lookup"><span data-stu-id="ee504-133">Feature/Capability</span></span> | <span data-ttu-id="ee504-134">说明</span><span class="sxs-lookup"><span data-stu-id="ee504-134">Description</span></span> |
|---|---|
| [<span data-ttu-id="ee504-135">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="ee504-135">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="ee504-136">威胁& 漏洞管理功能有助于识别、评估和修正跨终结点（如 (设备）中的) 。</span><span class="sxs-lookup"><span data-stu-id="ee504-136">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="ee504-137">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="ee504-137">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="ee504-138">攻击面减少规则有助于保护组织的设备和应用程序免受网络威胁和攻击。</span><span class="sxs-lookup"><span data-stu-id="ee504-138">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="ee504-139">下一代保护</span><span class="sxs-lookup"><span data-stu-id="ee504-139">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="ee504-140">下一代保护包括Microsoft Defender 防病毒帮助阻止威胁和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="ee504-140">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="ee504-141">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="ee504-141">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="ee504-142">终结点检测和响应功能可检测、调查和响应入侵尝试和主动泄露。</span><span class="sxs-lookup"><span data-stu-id="ee504-142">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="ee504-143">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="ee504-143">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="ee504-144">高级搜寻功能使安全运营团队能够找到已知或潜在威胁的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="ee504-144">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="ee504-145">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="ee504-145">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="ee504-146">行为阻止和包含功能有助于根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。</span><span class="sxs-lookup"><span data-stu-id="ee504-146">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="ee504-147">自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="ee504-147">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="ee504-148">自动调查和响应功能可检查警报，并立即采取修正措施来解决违规问题。</span><span class="sxs-lookup"><span data-stu-id="ee504-148">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="ee504-149">[威胁搜寻服务](microsoft-threat-experts.md) (Microsoft 威胁专家) </span><span class="sxs-lookup"><span data-stu-id="ee504-149">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="ee504-150">威胁搜寻服务为安全运营团队提供专家级别的监视和分析，并帮助确保不会错过关键威胁。</span><span class="sxs-lookup"><span data-stu-id="ee504-150">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="ee504-151">**想要了解更多信息？请参阅 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="ee504-151">**Want to learn more? See [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="ee504-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ee504-152">Next step</span></span>

- <span data-ttu-id="ee504-153">继续为 [迁移做准备](symantec-to-microsoft-defender-atp-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="ee504-153">Proceed to [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).</span></span>
