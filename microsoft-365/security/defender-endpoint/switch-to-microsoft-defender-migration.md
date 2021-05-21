---
title: 将非 Microsoft 终结点保护切换到 Microsoft Defender for Endpoint
description: 转换到 Microsoft Defender for Endpoint。 阅读本文，了解概述。
keywords: 迁移， windows defender 高级终结点保护， 适用于终结点， edr
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
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2a2b78089486b432ebf9492de26396b2bb96f94d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593497"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="42dfe-105">将非 Microsoft 终结点保护切换到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42dfe-105">Make the switch from non-Microsoft endpoint protection to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="42dfe-106">如果你正在考虑从非 Microsoft 终结点保护切换到 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) ，你的位置正确。</span><span class="sxs-lookup"><span data-stu-id="42dfe-106">If you are thinking about switching from your non-Microsoft endpoint protection to [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint), you're in the right place.</span></span> <span data-ttu-id="42dfe-107">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="42dfe-107">Use this article as a guide.</span></span>

:::image type="content" source="images/nonms-mde-migration.png" alt-text="迁移到 Defender for Endpoint 的概述":::

<span data-ttu-id="42dfe-109">当你切换到 Defender for Endpoint 时，你首先在活动模式下运行非 Microsoft 解决方案，在被动模式下为终结点配置 Defender，载入到适用于终结点的 Defender，将 Defender for Endpoint 设置为活动模式，然后删除非 Microsoft 解决方案。</span><span class="sxs-lookup"><span data-stu-id="42dfe-109">When you make the switch to Defender for Endpoint, you begin with your non-Microsoft solution operating in active mode, configure Defender for Endpoint in passive mode, onboard to Defender for Endpoint, set Defender for Endpoint to active mode, and then remove the non-Microsoft solution.</span></span>

> [!TIP]
> - <span data-ttu-id="42dfe-110">如果你当前正在使用 McAfee Endpoint Security (McAfee) ，请参阅从 [McAfee 迁移到 Defender for Endpoint](mcafee-to-microsoft-defender-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="42dfe-110">If you're currently using McAfee Endpoint Security (McAfee), see [Migrate from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).</span></span>
> - <span data-ttu-id="42dfe-111">如果你当前正在使用 Symantec Endpoint Protection (Symantec) ，请参阅从[Symantec](symantec-to-microsoft-defender-endpoint-migration.md)迁移到 Defender for Endpoint 。</span><span class="sxs-lookup"><span data-stu-id="42dfe-111">If you're currently using Symantec Endpoint Protection (Symantec), see [Migrate from Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).</span></span>

## <a name="the-migration-process"></a><span data-ttu-id="42dfe-112">迁移过程</span><span class="sxs-lookup"><span data-stu-id="42dfe-112">The migration process</span></span>

<span data-ttu-id="42dfe-113">迁移到 Defender for Endpoint 的过程分为三个阶段，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="42dfe-113">The process of migrating to Defender for Endpoint can be divided into three phases, as described in the following table:</span></span>

![迁移阶段 - 准备、设置、载入](images/phase-diagrams/migration-phases.png)

|<span data-ttu-id="42dfe-115">阶段</span><span class="sxs-lookup"><span data-stu-id="42dfe-115">Phase</span></span> |<span data-ttu-id="42dfe-116">说明</span><span class="sxs-lookup"><span data-stu-id="42dfe-116">Description</span></span> |
|--|--|
|[<span data-ttu-id="42dfe-117">准备迁移</span><span class="sxs-lookup"><span data-stu-id="42dfe-117">Prepare for your migration</span></span>](switch-to-microsoft-defender-prepare.md) |<span data-ttu-id="42dfe-118">在 [" **准备"** 阶段](switch-to-microsoft-defender-prepare.md)：</span><span class="sxs-lookup"><span data-stu-id="42dfe-118">During [the **Prepare** phase](switch-to-microsoft-defender-prepare.md):</span></span> <p><span data-ttu-id="42dfe-119">1。更新组织的设备。</span><span class="sxs-lookup"><span data-stu-id="42dfe-119">1. Update your organization's devices.</span></span> <p><span data-ttu-id="42dfe-120">2. 获取适用于终结点的 Defender。</span><span class="sxs-lookup"><span data-stu-id="42dfe-120">2. Get Defender for Endpoint.</span></span> <p><span data-ttu-id="42dfe-121">3. 规划角色和权限，并授予对Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="42dfe-121">3. Plan your roles and permissions, and grant access to the Microsoft Defender Security Center.</span></span> <p><span data-ttu-id="42dfe-122">4. 配置设备代理和 Internet 设置，以启用组织设备与适用于终结点的 Defender 之间的通信。</span><span class="sxs-lookup"><span data-stu-id="42dfe-122">4. Configure your device proxy and internet settings to enable communication between your organization's devices and Defender for Endpoint.</span></span> |
|[<span data-ttu-id="42dfe-123">设置适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="42dfe-123">Set up Defender for Endpoint</span></span>](switch-to-microsoft-defender-setup.md) |<span data-ttu-id="42dfe-124">在 [设置 **阶段**：](switch-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="42dfe-124">During [the **Setup** phase](switch-to-microsoft-defender-setup.md):</span></span> <p><span data-ttu-id="42dfe-125">1. 启用/重新安装Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="42dfe-125">1. Enable/reinstall Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="42dfe-126">2. 为终结点配置 Defender。</span><span class="sxs-lookup"><span data-stu-id="42dfe-126">2. Configure Defender for Endpoint.</span></span> <p><span data-ttu-id="42dfe-127">3. 将 Defender for Endpoint 添加到现有解决方案的排除列表中。</span><span class="sxs-lookup"><span data-stu-id="42dfe-127">3. Add Defender for Endpoint to the exclusion list for your existing solution.</span></span> <p><span data-ttu-id="42dfe-128">4. 将现有解决方案添加到列表的排除Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="42dfe-128">4. Add your existing solution to the exclusion list for Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="42dfe-129">5. 设置设备组、集合和组织单位。</span><span class="sxs-lookup"><span data-stu-id="42dfe-129">5. Set up your device groups, collections, and organizational units.</span></span> <p><span data-ttu-id="42dfe-130">6. 配置反恶意软件策略和实时保护设置。</span><span class="sxs-lookup"><span data-stu-id="42dfe-130">6. Configure your antimalware policies and real-time protection settings.</span></span>|
|[<span data-ttu-id="42dfe-131">载入到适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="42dfe-131">Onboard to Defender for Endpoint</span></span>](switch-to-microsoft-defender-onboard.md) |<span data-ttu-id="42dfe-132">在 [载入 **阶段**](switch-to-microsoft-defender-onboard.md)：</span><span class="sxs-lookup"><span data-stu-id="42dfe-132">During [the **Onboard** phase](switch-to-microsoft-defender-onboard.md):</span></span> <p><span data-ttu-id="42dfe-133">1. 将设备载入到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="42dfe-133">1. Onboard your devices to Defender for Endpoint.</span></span> <p><span data-ttu-id="42dfe-134">2. 运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="42dfe-134">2. Run a detection test.</span></span> <p><span data-ttu-id="42dfe-135">3. 确认Microsoft Defender 防病毒被动模式下运行。</span><span class="sxs-lookup"><span data-stu-id="42dfe-135">3. Confirm that Microsoft Defender Antivirus is running in passive mode.</span></span> <p><span data-ttu-id="42dfe-136">4. 获取更新Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="42dfe-136">4. Get updates for Microsoft Defender Antivirus.</span></span> <p><span data-ttu-id="42dfe-137">5. 卸载现有的终结点保护解决方案。</span><span class="sxs-lookup"><span data-stu-id="42dfe-137">5. Uninstall your existing endpoint protection solution.</span></span> <p><span data-ttu-id="42dfe-138">6. 确保 Defender for Endpoint 正常工作。</span><span class="sxs-lookup"><span data-stu-id="42dfe-138">6. Make sure that Defender for Endpoint working correctly.</span></span> |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="42dfe-139">Microsoft Defender for Endpoint 中包含哪些内容？</span><span class="sxs-lookup"><span data-stu-id="42dfe-139">What's included in Microsoft Defender for Endpoint?</span></span>

<span data-ttu-id="42dfe-140">在此迁移指南中，我们重点介绍下[](microsoft-defender-antivirus-in-windows-10.md)一代保护和终结点检测和[](overview-endpoint-detection-response.md)响应功能，作为迁移到 Defender for Endpoint 的起点。</span><span class="sxs-lookup"><span data-stu-id="42dfe-140">In this migration guide, we focus on [next-generation protection](microsoft-defender-antivirus-in-windows-10.md) and [endpoint detection and response](overview-endpoint-detection-response.md) capabilities as a starting point for moving to Defender for Endpoint.</span></span> <span data-ttu-id="42dfe-141">但是，Defender for Endpoint 包括的不仅仅是防病毒和终结点保护。</span><span class="sxs-lookup"><span data-stu-id="42dfe-141">However, Defender for Endpoint includes much more than antivirus and endpoint protection.</span></span> <span data-ttu-id="42dfe-142">Defender for Endpoint 是一个统一的平台，用于预防性保护、攻破后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="42dfe-142">Defender for Endpoint is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="42dfe-143">下表总结了 Defender for Endpoint 中的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="42dfe-143">The following table summarizes features and capabilities in Defender for Endpoint.</span></span> 

| <span data-ttu-id="42dfe-144">功能</span><span class="sxs-lookup"><span data-stu-id="42dfe-144">Feature/Capability</span></span> | <span data-ttu-id="42dfe-145">说明</span><span class="sxs-lookup"><span data-stu-id="42dfe-145">Description</span></span> |
|---|---|
| [<span data-ttu-id="42dfe-146">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="42dfe-146">Threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md) | <span data-ttu-id="42dfe-147">威胁& 漏洞管理功能有助于识别、评估和修正跨终结点（如 (设备）中的) 。</span><span class="sxs-lookup"><span data-stu-id="42dfe-147">Threat & vulnerability management capabilities help identify, assess, and remediate weaknesses across your endpoints (such as devices).</span></span> |
| [<span data-ttu-id="42dfe-148">减少攻击面</span><span class="sxs-lookup"><span data-stu-id="42dfe-148">Attack surface reduction</span></span>](overview-attack-surface-reduction.md) | <span data-ttu-id="42dfe-149">攻击面减少规则有助于保护组织的设备和应用程序免受网络威胁和攻击。</span><span class="sxs-lookup"><span data-stu-id="42dfe-149">Attack surface reduction rules help protect your organization's devices and applications from cyberthreats and attacks.</span></span> |
| [<span data-ttu-id="42dfe-150">下一代保护</span><span class="sxs-lookup"><span data-stu-id="42dfe-150">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md) | <span data-ttu-id="42dfe-151">下一代保护包括Microsoft Defender 防病毒帮助阻止威胁和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="42dfe-151">Next-generation protection includes Microsoft Defender Antivirus to help block threats and malware.</span></span> |
| [<span data-ttu-id="42dfe-152">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="42dfe-152">Endpoint detection and response</span></span>](overview-endpoint-detection-response.md) | <span data-ttu-id="42dfe-153">终结点检测和响应功能可检测、调查和响应入侵尝试和主动泄露。</span><span class="sxs-lookup"><span data-stu-id="42dfe-153">Endpoint detection and response capabilities detect, investigate, and respond to intrusion attempts and active breaches.</span></span>  |
| [<span data-ttu-id="42dfe-154">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="42dfe-154">Advanced hunting</span></span>](advanced-hunting-overview.md) | <span data-ttu-id="42dfe-155">高级搜寻功能使安全运营团队能够找到已知或潜在威胁的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="42dfe-155">Advanced hunting capabilities enable your security operations team to locate indicators and entities of known or potential threats.</span></span> |
| [<span data-ttu-id="42dfe-156">行为阻止和控制</span><span class="sxs-lookup"><span data-stu-id="42dfe-156">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md) | <span data-ttu-id="42dfe-157">行为阻止和包含功能有助于根据威胁的行为和进程树识别和停止威胁，即使威胁已开始执行。</span><span class="sxs-lookup"><span data-stu-id="42dfe-157">Behavioral blocking and containment capabilities help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> |
| [<span data-ttu-id="42dfe-158">自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="42dfe-158">Automated investigation and remediation</span></span>](automated-investigations.md) | <span data-ttu-id="42dfe-159">自动调查和响应功能可检查警报，并立即采取修正措施来解决违规问题。</span><span class="sxs-lookup"><span data-stu-id="42dfe-159">Automated investigation and response capabilities examine alerts and take immediate remediation action to resolve breaches.</span></span> |
| <span data-ttu-id="42dfe-160">[威胁搜寻服务](microsoft-threat-experts.md) (Microsoft 威胁专家) </span><span class="sxs-lookup"><span data-stu-id="42dfe-160">[Threat hunting service](microsoft-threat-experts.md) (Microsoft Threat Experts)</span></span> | <span data-ttu-id="42dfe-161">威胁搜寻服务为安全运营团队提供专家级别的监视和分析，并帮助确保不会错过关键威胁。</span><span class="sxs-lookup"><span data-stu-id="42dfe-161">Threat hunting services provide security operations teams with expert level monitoring and analysis, and to help ensure that critical threats aren't missed.</span></span> |

<span data-ttu-id="42dfe-162">**想要了解更多信息？请参阅 [Defender for Endpoint](microsoft-defender-endpoint.md)。**</span><span class="sxs-lookup"><span data-stu-id="42dfe-162">**Want to learn more? See [Defender for Endpoint](microsoft-defender-endpoint.md).**</span></span>

## <a name="next-step"></a><span data-ttu-id="42dfe-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="42dfe-163">Next step</span></span>

- <span data-ttu-id="42dfe-164">继续为 [迁移做准备](switch-to-microsoft-defender-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="42dfe-164">Proceed to [Prepare for your migration](switch-to-microsoft-defender-prepare.md).</span></span>
