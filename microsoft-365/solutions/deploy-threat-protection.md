---
title: 跨 Microsoft 365 部署威胁防护功能
description: 了解如何跨 Microsoft 365 E5 部署威胁防护服务和安全性功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a2d758ca4628e4cd5f73e77d0d86946e350163c5
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424073"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="aa078-103">跨 Microsoft 365 部署威胁防护功能</span><span class="sxs-lookup"><span data-stu-id="aa078-103">Deploy threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="aa078-104">[恶意软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)和复杂的网络攻击（如无文件威胁）[](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)是常见事件。</span><span class="sxs-lookup"><span data-stu-id="aa078-104">[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="aa078-105">企业需要使用有效的 IT 安全性功能来保护自己及其客户。</span><span class="sxs-lookup"><span data-stu-id="aa078-105">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="aa078-106">网络攻击可能会给组织带来严重问题，包括失去信任、财务问题、业务损失停机时间等。</span><span class="sxs-lookup"><span data-stu-id="aa078-106">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="aa078-107">防范威胁非常重要，但确定组织的时间、精力和资源重点在哪些方面可能非常困难。</span><span class="sxs-lookup"><span data-stu-id="aa078-107">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="aa078-108">Microsoft 安全解决方案内置在我们的产品和服务中。</span><span class="sxs-lookup"><span data-stu-id="aa078-108">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="aa078-109">自动化和机器学习功能可减少安全团队的负载，以确保解决正确的项目。</span><span class="sxs-lookup"><span data-stu-id="aa078-109">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="aa078-110">Microsoft 安全解决方案的强大功能基于我们每天在 Intelligent Security Graph 中处理数万 [万个信号](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)。</span><span class="sxs-lookup"><span data-stu-id="aa078-110">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph).</span></span> <span data-ttu-id="aa078-111">Microsoft 365 安全解决方案包括 [Microsoft 365 Defender，](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)这是一种将电子邮件、数据、设备和标识中的信号汇集在一起的解决方案，可绘制针对组织的高级威胁的图片。</span><span class="sxs-lookup"><span data-stu-id="aa078-111">Microsoft 365 security solutions include [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>


<span data-ttu-id="aa078-112">观看此视频以简要了解部署流程。</span><span class="sxs-lookup"><span data-stu-id="aa078-112">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

>[!Note]
><span data-ttu-id="aa078-113">此视频使用以前的威胁防护产品和功能名称，但概念是相同的。</span><span class="sxs-lookup"><span data-stu-id="aa078-113">This video uses the previous names of threat protection products and features, but the concepts are the same.</span></span> <span data-ttu-id="aa078-114">此视频的更新正在进行中。</span><span class="sxs-lookup"><span data-stu-id="aa078-114">An update to this video is in progress.</span></span>
>

<span data-ttu-id="aa078-115">使用本文作为实施威胁防护解决方案的指南。</span><span class="sxs-lookup"><span data-stu-id="aa078-115">Use this article as a guide for implementing your threat protection solution.</span></span>

## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="aa078-116">Microsoft 365 E5 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="aa078-116">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="aa078-117">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 使你能够使用自适应内置智能保护组织。</span><span class="sxs-lookup"><span data-stu-id="aa078-117">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="aa078-118">借助 Microsoft 365 E5 中的威胁防护功能，可以检测和调查内部部署和云环境中的高级威胁、遭到入侵的标识和恶意操作。</span><span class="sxs-lookup"><span data-stu-id="aa078-118">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="aa078-119">在 Microsoft 365 E5 中，默认情况下集成了威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="aa078-119">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="aa078-120">来自每个功能的信号增强检测和响应威胁的整体能力。</span><span class="sxs-lookup"><span data-stu-id="aa078-120">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="aa078-121">与运行非 Microsoft 产品相比，组合的功能集为组织（尤其是国家/地区组织）提供最佳保护。</span><span class="sxs-lookup"><span data-stu-id="aa078-121">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="aa078-122">下图描述了本文中描述的 Microsoft 365 E5 中的威胁防护服务和功能。</span><span class="sxs-lookup"><span data-stu-id="aa078-122">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender 概述](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="aa078-124">一旦部署任何 Defender for Office 365 功能，就可以打开 Microsoft 365 Defender，这将信号和数据汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="aa078-124">As soon as you deploy any of the Defender for Office 365 capabilities, you can turn on Microsoft 365 Defender, which brings the signals and data together into one place.</span></span> 

![Microsoft 365 Defender 仪表板的概念图示](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="aa078-126">下图描述了部署这些单个功能的建议路径。</span><span class="sxs-lookup"><span data-stu-id="aa078-126">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 威胁防护信号](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="aa078-128">解决方案/功能</span><span class="sxs-lookup"><span data-stu-id="aa078-128">Solution/capabilities</span></span>  |<span data-ttu-id="aa078-129">说明</span><span class="sxs-lookup"><span data-stu-id="aa078-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="aa078-130">多重身份验证和条件访问</span><span class="sxs-lookup"><span data-stu-id="aa078-130">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="aa078-131">防止标识和设备遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="aa078-131">Protect against compromised identities and devices.</span></span> <span data-ttu-id="aa078-132">从此保护开始，因为它具有基础性。</span><span class="sxs-lookup"><span data-stu-id="aa078-132">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="aa078-133">本指南中建议的配置包括 Azure AD Identity Protection 作为先决条件。</span><span class="sxs-lookup"><span data-stu-id="aa078-133">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="aa078-134">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="aa078-134">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="aa078-135">基于云的安全解决方案，利用本地 Active Directory 域服务 (AD DS) 信号识别、检测和调查针对组织的高级威胁、泄露的身份和恶意内部操作。</span><span class="sxs-lookup"><span data-stu-id="aa078-135">A cloud-based security solution that leverages your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="aa078-136">接下来关注 Microsoft Defender for Identity，因为它可保护本地和云基础结构，没有依赖关系或先决条件，并且可提供即时安全优势。</span><span class="sxs-lookup"><span data-stu-id="aa078-136">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="aa078-137">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="aa078-137">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="aa078-138">保护组织免受电子邮件、链接和 (URL) 和协作工具造成的恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="aa078-138">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="aa078-139">恶意软件、网络钓鱼、欺骗和其他攻击类型的保护。</span><span class="sxs-lookup"><span data-stu-id="aa078-139">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="aa078-140">下一步建议为 Office 365 配置 Microsoft Defender，因为更改控制、从现有系统迁移设置和其他注意事项可能需要更长时间才能部署。</span><span class="sxs-lookup"><span data-stu-id="aa078-140">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <br><br><span data-ttu-id="aa078-141">注意：确保配置 Exchange Online Protection 应用程序的所有 Office 365 订阅 (威胁) 。</span><span class="sxs-lookup"><span data-stu-id="aa078-141">Note: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="aa078-142">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa078-142">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="aa078-143">有助于预防、检测、调查和响应高级威胁的终结点保护平台。</span><span class="sxs-lookup"><span data-stu-id="aa078-143">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="aa078-144">Defender for Endpoint 可能需要一些时间进行部署，但配置可以与其他功能并行完成。</span><span class="sxs-lookup"><span data-stu-id="aa078-144">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="aa078-145">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="aa078-145">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="aa078-146">用于发现、调查和治理的云访问安全代理。</span><span class="sxs-lookup"><span data-stu-id="aa078-146">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="aa078-147">你可以提前启用 Microsoft Cloud App Security，以便开始收集数据和见解。</span><span class="sxs-lookup"><span data-stu-id="aa078-147">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="aa078-148">在 SaaS 应用中实现信息和其他定向保护涉及规划，并且可能需要更多时间。</span><span class="sxs-lookup"><span data-stu-id="aa078-148">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="aa078-149">具有多个安全团队的组织可以并行实现这些功能。</span><span class="sxs-lookup"><span data-stu-id="aa078-149">Organizations with multiple security teams can implement these capabilities in parallel.</span></span>

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="aa078-150">部署威胁防护解决方案</span><span class="sxs-lookup"><span data-stu-id="aa078-150">Deploy your threat protection solution</span></span>

<span data-ttu-id="aa078-151">若要确保组织具有尽可能最佳的保护，请设置和部署安全解决方案，以包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="aa078-151">To make sure your organization has the best protection possible, set up and deploy your security solution to include the following steps:</span></span>

1. [<span data-ttu-id="aa078-152">设置多重身份验证和条件访问策略</span><span class="sxs-lookup"><span data-stu-id="aa078-152">Set up multi-factor authentication and Conditional Access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="aa078-153">配置 Microsoft Defender 的标识</span><span class="sxs-lookup"><span data-stu-id="aa078-153">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="aa078-154">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa078-154">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="aa078-155">为 Office 365 配置 Defender</span><span class="sxs-lookup"><span data-stu-id="aa078-155">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="aa078-156">配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa078-156">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="aa078-157">配置 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="aa078-157">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="aa078-158">监视状态并采取措施</span><span class="sxs-lookup"><span data-stu-id="aa078-158">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="aa078-159">培训用户</span><span class="sxs-lookup"><span data-stu-id="aa078-159">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="aa078-160">可以并行配置威胁防护功能，因此，如果有多个网络安全团队负责不同的服务，他们可以同时配置组织的保护功能。</span><span class="sxs-lookup"><span data-stu-id="aa078-160">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span> <span data-ttu-id="aa078-161">下图说明了部署威胁防护功能高级流程。</span><span class="sxs-lookup"><span data-stu-id="aa078-161">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威胁防护功能的过程](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png) 
