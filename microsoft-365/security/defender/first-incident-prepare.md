---
title: 为第一个事件准备安全状态
description: 为 Microsoft 365 Defender 中的第一个事件设置租户Microsoft 365状态。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4fc124bf8787d5880d78a4f5208bd66329da07a0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539031"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="40855-104">为第一个事件准备安全状态</span><span class="sxs-lookup"><span data-stu-id="40855-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="40855-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="40855-105">**Applies to:**</span></span>
- <span data-ttu-id="40855-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40855-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="40855-107">准备事件处理涉及为组织网络设置来自不同类型的安全事件的充分保护。</span><span class="sxs-lookup"><span data-stu-id="40855-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="40855-108">为降低安全事件的风险，美国国家标准和技术协会 (NIST) 推荐了几种安全做法，包括风险评估、强化主机安全、安全配置网络以及预防恶意软件。</span><span class="sxs-lookup"><span data-stu-id="40855-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="40855-109">Microsoft 365Defender 可帮助解决事件防护的几个方面：</span><span class="sxs-lookup"><span data-stu-id="40855-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="40855-110">实现零 [信任](https://docs.microsoft.com/security/zero-trust/) 框架</span><span class="sxs-lookup"><span data-stu-id="40855-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="40855-111">使用 Microsoft 安全分数分配分数来确定 [安全状态](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="40855-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="40855-112">通过威胁和漏洞管理中的漏洞评估 [防止威胁](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="40855-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="40855-113">了解最新的安全威胁，以便你可以为它们做好准备</span><span class="sxs-lookup"><span data-stu-id="40855-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="40855-114">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="40855-114">Step 1.</span></span> <span data-ttu-id="40855-115">实现零信任</span><span class="sxs-lookup"><span data-stu-id="40855-115">Implement Zero Trust</span></span>

<span data-ttu-id="40855-116">[零](https://docs.microsoft.com/security/zero-trust/) 信任是一种集成的安全理念和端到端策略，它考虑任何现代环境的复杂性质，包括移动工作人员以及用户、设备、应用程序和数据，无论他们位于何处。</span><span class="sxs-lookup"><span data-stu-id="40855-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="40855-117">通过提供单一窗格以一致的方式管理所有检测，Microsoft 365 Defender 可以使安全运营团队更轻松地实施零信任指导原则。 [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust)</span><span class="sxs-lookup"><span data-stu-id="40855-117">By providing a single pane of glass to manage all detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="40855-118">Microsoft 365 Defender 的组件可以显示违反为建立零信任条件访问策略而实施的规则，通过将来自 Microsoft Defender for Endpoint (MDE) 或其他移动安全供应商的数据集成为设备合规性策略和基于设备的条件访问策略实现的信息源。</span><span class="sxs-lookup"><span data-stu-id="40855-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="40855-119">设备风险直接影响该设备的用户可访问的资源。</span><span class="sxs-lookup"><span data-stu-id="40855-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="40855-120">基于特定条件拒绝访问资源是零信任的主要主题，Microsoft 365 Defender 提供确定信任级别条件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="40855-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="40855-121">例如，Microsoft 365 Defender 可以通过"威胁和漏洞管理"页提供设备的软件版本级别，而条件访问策略限制具有过时或易受攻击的版本的设备。</span><span class="sxs-lookup"><span data-stu-id="40855-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="40855-122">自动化是实施和维护零信任环境的重要部分，同时还减少了可能导致发生 IR 事件或 IR 事件 (警报) 数量。</span><span class="sxs-lookup"><span data-stu-id="40855-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="40855-123">Microsoft 365 Defender 的组件可以自动化，例如修正操作[ (称为](m365d-autoir.md)Microsoft 365 安全中心) 中的事件调查、通知操作，甚至是创建支持票证（如[在 ServiceNow](https://microsoft.service-now.com/sp/)中）。</span><span class="sxs-lookup"><span data-stu-id="40855-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="40855-124">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="40855-124">Step 2.</span></span> <span data-ttu-id="40855-125">确定组织的安全状态</span><span class="sxs-lookup"><span data-stu-id="40855-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="40855-126">接下来，组织可以使用 Microsoft 365 Defender 中的[Microsoft](microsoft-secure-score.md)安全分数来确定你当前的安全状况，并考虑如何改进它的建议。</span><span class="sxs-lookup"><span data-stu-id="40855-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="40855-127">分数越高，组织采取的安全建议和改进措施就越高。</span><span class="sxs-lookup"><span data-stu-id="40855-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="40855-128">安全分数建议可以跨不同的产品进行，并允许组织进一步提升分数。</span><span class="sxs-lookup"><span data-stu-id="40855-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 安全中心中的 Microsoft 安全分数示例":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="40855-130">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="40855-130">Step 3.</span></span> <span data-ttu-id="40855-131">评估组织的漏洞暴露</span><span class="sxs-lookup"><span data-stu-id="40855-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="40855-132">预防事件有助于简化安全操作工作，以重点关注进行中的关键和重要的安全事件。</span><span class="sxs-lookup"><span data-stu-id="40855-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="40855-133">软件漏洞通常是攻击的可阻止入口点，可能导致数据盗窃、数据丢失或业务运营中断。</span><span class="sxs-lookup"><span data-stu-id="40855-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="40855-134">如果没有攻击在进行中，则安全操作必须努力在组织中实现并保持可接受的漏洞暴露级别。 [](../defender-endpoint/tvm-exposure-score.md)</span><span class="sxs-lookup"><span data-stu-id="40855-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="40855-135">若要检查软件修补进度，请访问 Defender [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) for Endpoint 中的"威胁和漏洞管理"页，可通过"更多资源"选项卡从 Microsoft 365 Defender **访问** 该页面。</span><span class="sxs-lookup"><span data-stu-id="40855-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 安全中心中的威胁和漏洞页面示例"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="40855-137">4. 了解新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="40855-137">4. Understand emerging threats</span></span>

<span data-ttu-id="40855-138">在[安全中心](threat-analytics.md)Microsoft 365威胁分析，及时获得最新的安全威胁环境。</span><span class="sxs-lookup"><span data-stu-id="40855-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="40855-139">专家 Microsoft 安全研究人员创建报告，详细说明最新的网络威胁，以便你了解它们可能会Microsoft 365订阅、设备和用户。</span><span class="sxs-lookup"><span data-stu-id="40855-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="40855-140">这些报告可能包括：</span><span class="sxs-lookup"><span data-stu-id="40855-140">These reports can include:</span></span>

- <span data-ttu-id="40855-141">活动威胁参与者及其活动</span><span class="sxs-lookup"><span data-stu-id="40855-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="40855-142">热门和新的攻击技术</span><span class="sxs-lookup"><span data-stu-id="40855-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="40855-143">关键漏洞</span><span class="sxs-lookup"><span data-stu-id="40855-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="40855-144">常见的攻击面</span><span class="sxs-lookup"><span data-stu-id="40855-144">Common attack surfaces</span></span>
- <span data-ttu-id="40855-145">流行恶意软件</span><span class="sxs-lookup"><span data-stu-id="40855-145">Prevalent malware</span></span>

<span data-ttu-id="40855-146">威胁分析还会查看你的配置和警报，以确定你面临的风险以及是否有适用于报告的活动警报。</span><span class="sxs-lookup"><span data-stu-id="40855-146">Threat analytics also looks at your configuration and alerts to determine how at-risk you are and if there are active alerts applicable to a report.</span></span>

<span data-ttu-id="40855-147">你可以实施新兴威胁的建议，以强化安全状况并最大限度地减少攻击面区域。</span><span class="sxs-lookup"><span data-stu-id="40855-147">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="40855-148">安排时间，定期查看安全中心中Microsoft 365分析[](threat-analytics.md)"部分。</span><span class="sxs-lookup"><span data-stu-id="40855-148">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="40855-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="40855-149">Next step</span></span>

<span data-ttu-id="40855-150">[![步骤 1：了解如何对事件分类和分析](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="40855-150">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="40855-151">了解如何 [对事件进行会审和分析](first-incident-analyze.md)。</span><span class="sxs-lookup"><span data-stu-id="40855-151">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40855-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40855-152">See also</span></span>

- [<span data-ttu-id="40855-153">事件概述</span><span class="sxs-lookup"><span data-stu-id="40855-153">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="40855-154">调查事件</span><span class="sxs-lookup"><span data-stu-id="40855-154">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="40855-155">管理事件</span><span class="sxs-lookup"><span data-stu-id="40855-155">Manage incidents</span></span>](manage-incidents.md)
