---
title: 在 Microsoft 365 中部署网络安全威胁保护
description: 了解如何在 Microsoft 365 E5 中部署威胁保护服务和 IT 网络安全功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 0736151f1ceacecb888c8a3eb3dd88183cc3a060
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662316"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a><span data-ttu-id="b238c-103">在 Microsoft 365 中部署威胁防护功能</span><span class="sxs-lookup"><span data-stu-id="b238c-103">Deploy threat protection capabilities across Microsoft 365</span></span>

<span data-ttu-id="b238c-104">[恶意软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)和复杂的 cyberattacks （如 [fileless 威胁](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)）是常见事件。</span><span class="sxs-lookup"><span data-stu-id="b238c-104">[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="b238c-105">企业需要使用有效的 IT 网络安全功能来保护自己及其客户。</span><span class="sxs-lookup"><span data-stu-id="b238c-105">Businesses need to protect themselves and their customers with effective IT network security capabilities.</span></span> <span data-ttu-id="b238c-106">此类攻击可能会导致贵组织的主要问题，包括从失去信任到财务 woes、业务威胁停机等。</span><span class="sxs-lookup"><span data-stu-id="b238c-106">Such attacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="b238c-107">防御威胁非常重要，但确定组织的时间、工作和资源的位置可能会有很大难度。</span><span class="sxs-lookup"><span data-stu-id="b238c-107">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="b238c-108">Microsoft 安全解决方案内置在我们的产品和服务中。</span><span class="sxs-lookup"><span data-stu-id="b238c-108">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="b238c-109">自动化和机器学习功能可降低安全团队的负载，以确保解决正确的项目。</span><span class="sxs-lookup"><span data-stu-id="b238c-109">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="b238c-110">Microsoft 网络安全解决方案的优势是基于我们在 [智能安全图形](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中每天处理的 trillions 信号。</span><span class="sxs-lookup"><span data-stu-id="b238c-110">And the strength of Microsoft network security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph).</span></span> <span data-ttu-id="b238c-111">Microsoft 365 安全解决方案包括 [Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)，这是一种解决方案，它将跨电子邮件、数据、设备和标识的信号汇集在一起，以在组织中绘制高级威胁的图片。</span><span class="sxs-lookup"><span data-stu-id="b238c-111">Microsoft 365 security solutions include [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>


<span data-ttu-id="b238c-112">观看此视频，了解部署过程的概述。</span><span class="sxs-lookup"><span data-stu-id="b238c-112">Watch this video for an overview of the deployment process.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

<span data-ttu-id="b238c-113">使用本文作为实施威胁防护解决方案的指南。</span><span class="sxs-lookup"><span data-stu-id="b238c-113">Use this article as a guide for implementing your threat protection solution.</span></span>

## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="b238c-114">Microsoft 365 E5 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="b238c-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 使你能够使用自适应内置智能来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="b238c-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="b238c-116">使用 Microsoft 365 E5 中的威胁防护功能，可以在内部部署和云环境中检测和调查高级威胁、受到危害的身份和恶意操作。</span><span class="sxs-lookup"><span data-stu-id="b238c-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="b238c-117">在 Microsoft 365 E5 中，默认情况下会集成威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="b238c-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="b238c-118">来自每个功能的信号将强度增加到检测和响应威胁的总体能力。</span><span class="sxs-lookup"><span data-stu-id="b238c-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="b238c-119">与运行非 Microsoft 产品相比，组合的一组功能为组织提供了最佳保护，尤其是多国组织。</span><span class="sxs-lookup"><span data-stu-id="b238c-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="b238c-120">下图描述了 Microsoft 365 E5 中的威胁防护服务和功能，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="b238c-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 威胁防护概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="b238c-122">一旦您部署任何高级威胁防护功能，您就可以打开 Microsoft 威胁防护，这会将信号和数据集中到一个位置。</span><span class="sxs-lookup"><span data-stu-id="b238c-122">As soon as you deploy any of the advanced threat protection capabilities, you can turn on Microsoft Threat Protection, which brings the signals and data together into one place.</span></span> 

![Microsoft 威胁防护仪表板的概念性图示](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="b238c-124">下图展示了用于部署这些单独功能的推荐途径。</span><span class="sxs-lookup"><span data-stu-id="b238c-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 威胁防护信号](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="b238c-126">解决方案/功能</span><span class="sxs-lookup"><span data-stu-id="b238c-126">Solution/capabilities</span></span>  |<span data-ttu-id="b238c-127">说明</span><span class="sxs-lookup"><span data-stu-id="b238c-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b238c-128">多重身份验证和条件访问</span><span class="sxs-lookup"><span data-stu-id="b238c-128">Multi-factor authentication and conditional access</span></span>     |<span data-ttu-id="b238c-129">针对泄露的标识和设备进行防护。</span><span class="sxs-lookup"><span data-stu-id="b238c-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="b238c-130">从这种保护开始，因为它是基础。</span><span class="sxs-lookup"><span data-stu-id="b238c-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="b238c-131">本指南中建议的配置包括作为先决条件的 Azure AD 标识保护。</span><span class="sxs-lookup"><span data-stu-id="b238c-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="b238c-132">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-132">Azure Advanced Threat Protection</span></span>     |  <span data-ttu-id="b238c-133">一种基于云的安全解决方案，利用本地 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕行为。</span><span class="sxs-lookup"><span data-stu-id="b238c-133">A cloud-based security solution that leverages your on-premises Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="b238c-134">重点关注 Azure 高级威胁防护下一步，因为它保护您的本地和云基础结构，没有任何依赖项或先决条件，并且可以提供直接的好处。</span><span class="sxs-lookup"><span data-stu-id="b238c-134">Focus on Azure Advanced Threat Protection next because it protects your on-prem and your cloud infrastructure, has no dependencies or prerequisites, and can provide immediate benefit.</span></span>       | 
|<span data-ttu-id="b238c-135">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-135">Office 365 Advanced Threat Protection</span></span>     | <span data-ttu-id="b238c-136">保护您的组织免受电子邮件、链接 (Url) 和协作工具带来的恶意威胁的侵扰。</span><span class="sxs-lookup"><span data-stu-id="b238c-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="b238c-137">针对恶意软件、网络钓鱼、欺骗和其他攻击类型的保护。</span><span class="sxs-lookup"><span data-stu-id="b238c-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="b238c-138">建议使用 "配置 Office 365 高级威胁防护"，因为 "更改控制"、"从委任系统迁移设置" 和其他注意事项可能需要更长时间才能部署。</span><span class="sxs-lookup"><span data-stu-id="b238c-138">Configuring Office 365 Advanced Threat Protection is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <br><br><span data-ttu-id="b238c-139">注意：请确保在 Exchange Online Protection)  (配置所有 Office 365 订阅中所包含的威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="b238c-139">Note: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="b238c-140">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-140">Microsoft Defender Advanced Threat Protection</span></span>    | <span data-ttu-id="b238c-141">一种 endpoint protection 平台，可帮助防止、检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="b238c-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="b238c-142">Microsoft Defender 高级威胁防护可能需要一段时间才能部署，但可以与其他功能并行进行配置。</span><span class="sxs-lookup"><span data-stu-id="b238c-142">Microsoft Defender Advanced Threat Protection can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="b238c-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b238c-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="b238c-144">用于发现、调查和治理的云访问安全代理。</span><span class="sxs-lookup"><span data-stu-id="b238c-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="b238c-145">你可以及早启用 Microsoft 云应用安全，以开始收集数据和见解。</span><span class="sxs-lookup"><span data-stu-id="b238c-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="b238c-146">在您的 SaaS 应用程序中实施信息和其他目标保护涉及规划，并可能需要更多时间。</span><span class="sxs-lookup"><span data-stu-id="b238c-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="b238c-147">具有多个安全团队的组织可以并行实施这些功能。</span><span class="sxs-lookup"><span data-stu-id="b238c-147">Organizations with multiple security teams can implement these capabilities in parallel.</span></span>

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="b238c-148">部署威胁防护解决方案</span><span class="sxs-lookup"><span data-stu-id="b238c-148">Deploy your threat protection solution</span></span>

<span data-ttu-id="b238c-149">若要确保贵组织能够获得最佳保护，请设置和部署安全解决方案以包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b238c-149">To make sure your organization has the best protection possible, set up and deploy your security solution to include the following steps:</span></span>

1. [<span data-ttu-id="b238c-150">设置多重身份验证和条件访问策略</span><span class="sxs-lookup"><span data-stu-id="b238c-150">Set up multi-factor authentication and conditional access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="b238c-151">配置 Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-151">Configure Azure Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [<span data-ttu-id="b238c-152">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-152">Turn on Microsoft Threat Protection</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [<span data-ttu-id="b238c-153">配置 Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-153">Configure Office 365 Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [<span data-ttu-id="b238c-154">配置 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b238c-154">Configure Microsoft Defender Advanced Threat Protection</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [<span data-ttu-id="b238c-155">配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="b238c-155">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="b238c-156">监视状态并采取操作</span><span class="sxs-lookup"><span data-stu-id="b238c-156">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="b238c-157">培训用户</span><span class="sxs-lookup"><span data-stu-id="b238c-157">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="b238c-158">您的威胁防护功能可以并行配置，因此，如果您有多个负责不同服务的网络安全团队，则可以同时配置组织的保护功能。</span><span class="sxs-lookup"><span data-stu-id="b238c-158">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span> <span data-ttu-id="b238c-159">下图说明了部署威胁防护功能的高级别过程。</span><span class="sxs-lookup"><span data-stu-id="b238c-159">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


