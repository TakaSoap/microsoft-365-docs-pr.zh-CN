---
title: 查看体系结构要求和Microsoft Cloud App Security，通过了解 云应用安全 中的体系结构来规划Microsoft 365 Defender
description: Microsoft Cloud App Security技术图表介绍了 Microsoft 365 Defender 中的体系结构，这将帮助你构建试验环境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457609"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a><span data-ttu-id="eaa46-103">查看体系结构要求和解决方案的关键Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eaa46-103">Review architecture requirements and key concepts for Microsoft Cloud App Security</span></span>


<span data-ttu-id="eaa46-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eaa46-104">**Applies to:**</span></span>

- <span data-ttu-id="eaa46-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaa46-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="eaa46-106">本文是设置环境评估环境的第 1 步（第[3](eval-defender-mcas-overview.md)步）Microsoft Cloud App Security一Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="eaa46-106">This article is [Step 1 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security alongside Microsoft 365 Defender.</span></span> <span data-ttu-id="eaa46-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa46-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="eaa46-108">在启用Microsoft Cloud App Security，请确保您了解体系结构并满足要求。</span><span class="sxs-lookup"><span data-stu-id="eaa46-108">Before enabling Microsoft Cloud App Security, be sure you understand the architecture and can meet the requirements.</span></span> 

## <a name="understand-the-architecture"></a><span data-ttu-id="eaa46-109">了解体系结构</span><span class="sxs-lookup"><span data-stu-id="eaa46-109">Understand the architecture</span></span>

<span data-ttu-id="eaa46-110">Microsoft Cloud App Security CASB (云访问安全代理) 。</span><span class="sxs-lookup"><span data-stu-id="eaa46-110">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB).</span></span> <span data-ttu-id="eaa46-111">CASB 充当网关守卫，在企业用户和用户使用的云资源之间实时代理访问，无论用户位于何处，无论他们使用何种设备。</span><span class="sxs-lookup"><span data-stu-id="eaa46-111">CASBs act a gatekeeper to broker access in real time between your enterprise users and cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> <span data-ttu-id="eaa46-112">Microsoft Cloud App Security与 Microsoft 的管理功能（包括安全Microsoft 365 Defender）。</span><span class="sxs-lookup"><span data-stu-id="eaa46-112">Microsoft Cloud App Security natively integrates with Microsoft security capabilities, including Microsoft 365 Defender.</span></span> 

<span data-ttu-id="eaa46-113">如果没有云应用安全，组织使用的云应用将不受管理且不受保护，如上所示。</span><span class="sxs-lookup"><span data-stu-id="eaa46-113">Without Cloud App Security, cloud apps that are used by your organization are unmanaged and unprotected, as illustrated.</span></span>

![体系结构Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-architecture-a.png)

<span data-ttu-id="eaa46-115">在此图中：</span><span class="sxs-lookup"><span data-stu-id="eaa46-115">In the illustration:</span></span>
- <span data-ttu-id="eaa46-116">组织使用云应用不受监控且不受保护。</span><span class="sxs-lookup"><span data-stu-id="eaa46-116">The use of cloud apps by an organization is unmonitored and unprotected.</span></span> 
- <span data-ttu-id="eaa46-117">此使用超出在托管组织中实现的保护范围。</span><span class="sxs-lookup"><span data-stu-id="eaa46-117">This use falls outside the protections achieved within a managed organization.</span></span> 

#### <a name="discovering-cloud-apps"></a><span data-ttu-id="eaa46-118">发现云应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-118">Discovering cloud apps</span></span>

<span data-ttu-id="eaa46-119">管理云应用使用的第一步是发现组织使用哪些云应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-119">The first step to managing the use of cloud apps is to discover which cloud apps are used by your organization.</span></span> <span data-ttu-id="eaa46-120">下图说明了云发现如何与云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-120">This next diagram illustrates how cloud discovery works with Cloud App Security.</span></span>

![云Microsoft Cloud App Security体系结构 - 云发现](../../media/defender/m365-defender-mcas-architecture-b.png)

<span data-ttu-id="eaa46-122">在此图中，有两种方法可用于监视网络流量和发现组织使用的云应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-122">In this illustration, there are two methods that can be used to monitor network traffic and discover cloud apps that are being used by your organization.</span></span>
- <span data-ttu-id="eaa46-123">A.</span><span class="sxs-lookup"><span data-stu-id="eaa46-123">A.</span></span> <span data-ttu-id="eaa46-124">云应用发现与 Microsoft Defender for Endpoint 本地集成。</span><span class="sxs-lookup"><span data-stu-id="eaa46-124">Cloud App Discovery integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="eaa46-125">Defender for Endpoint 报告从 IT 托管的设备访问的云Windows 10服务。</span><span class="sxs-lookup"><span data-stu-id="eaa46-125">Defender for Endpoint reports cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 
- <span data-ttu-id="eaa46-126">B.</span><span class="sxs-lookup"><span data-stu-id="eaa46-126">B.</span></span> <span data-ttu-id="eaa46-127">为了覆盖连接到网络的所有设备，云应用安全日志收集器安装在防火墙和其他代理上，以从终结点收集数据。</span><span class="sxs-lookup"><span data-stu-id="eaa46-127">For coverage on all devices connected to a network, the Cloud App Security log collector is installed on firewalls and other proxies to collect data from endpoints.</span></span> <span data-ttu-id="eaa46-128">此数据将发送到云应用安全进行分析。</span><span class="sxs-lookup"><span data-stu-id="eaa46-128">This data is sent to Cloud App Security for analysis.</span></span>

#### <a name="managing-cloud-apps"></a><span data-ttu-id="eaa46-129">管理云应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-129">Managing cloud apps</span></span>

<span data-ttu-id="eaa46-130">在发现云应用并分析组织如何使用这些应用的行为后，你可以开始管理你选择的云应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-130">After you discover cloud apps and analyze the behavior of how these are used by your organization, you can begin managing cloud apps that you choose.</span></span> 

![云Microsoft Cloud App Security - 管理云应用](../../media/defender/m365-defender-mcas-architecture-c.png)

<span data-ttu-id="eaa46-132">在此图中：</span><span class="sxs-lookup"><span data-stu-id="eaa46-132">In this illustration:</span></span>
- <span data-ttu-id="eaa46-133">某些应用已批准使用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-133">Some apps are sanctioned for use.</span></span> <span data-ttu-id="eaa46-134">这是开始管理应用的一种简单方法。</span><span class="sxs-lookup"><span data-stu-id="eaa46-134">This is a simple way of beginning to manage apps.</span></span>
- <span data-ttu-id="eaa46-135">通过将应用与应用连接器连接，你可以实现更高的可见性和控制。</span><span class="sxs-lookup"><span data-stu-id="eaa46-135">You can enable greater visibility and control by connecting apps with app connectors.</span></span> <span data-ttu-id="eaa46-136">应用连接器使用应用提供程序的 API。</span><span class="sxs-lookup"><span data-stu-id="eaa46-136">App connectors use the APIs of app providers.</span></span>


#### <a name="applying-session-controls-to-cloud-apps"></a><span data-ttu-id="eaa46-137">将会话控件应用到云应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-137">Applying session controls to cloud apps</span></span>

<span data-ttu-id="eaa46-138">Microsoft Cloud App Security充当反向代理，提供对批准的云应用的代理访问。</span><span class="sxs-lookup"><span data-stu-id="eaa46-138">Microsoft Cloud App Security serves as a reverse proxy, providing proxy access to sanctioned cloud apps.</span></span> <span data-ttu-id="eaa46-139">这允许云应用安全应用您配置的会话控件。</span><span class="sxs-lookup"><span data-stu-id="eaa46-139">This allows Cloud App Security to apply session controls that you configure.</span></span> 

![客户端Microsoft Cloud App Security - 代理访问会话控制](../../media/defender/m365-defender-mcas-architecture-d.png)

<span data-ttu-id="eaa46-141">在此图中：</span><span class="sxs-lookup"><span data-stu-id="eaa46-141">In this illustration:</span></span>
- <span data-ttu-id="eaa46-142">组织中用户和设备对批准的云应用的访问权限通过 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-142">Access to sanctioned cloud apps from users and devices in your organization is routed through Cloud App Security.</span></span>
- <span data-ttu-id="eaa46-143">此代理访问允许应用会话控件。</span><span class="sxs-lookup"><span data-stu-id="eaa46-143">This proxy access allows session controls to be applied.</span></span>
- <span data-ttu-id="eaa46-144">未批准或明确未批准的云应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="eaa46-144">Cloud apps that you have not sanctioned or explicitly unsanctioned are not affected.</span></span>

<span data-ttu-id="eaa46-145">会话控件允许你将参数应用于组织如何使用云应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-145">Session controls allow you to apply parameters to how cloud apps are used by your organization.</span></span> <span data-ttu-id="eaa46-146">例如，如果组织使用的是 Salesforce，可以配置仅允许托管设备访问 Salesforce 中组织数据的会话策略。</span><span class="sxs-lookup"><span data-stu-id="eaa46-146">For example, if your organization is using Salesforce, you can configure a session policy that allows only managed devices to access your organization's data in Salesforce.</span></span> <span data-ttu-id="eaa46-147">一个更简单的示例可能是将策略配置为监视来自非托管设备的流量，以便可以在应用更严格的策略之前分析此流量的风险。</span><span class="sxs-lookup"><span data-stu-id="eaa46-147">A simpler example could be configuring a policy to monitor traffic from unmanaged devices so you can analyze the risk of this traffic before applying stricter policies.</span></span>

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a><span data-ttu-id="eaa46-148">与 Azure AD 与条件访问应用控制集成</span><span class="sxs-lookup"><span data-stu-id="eaa46-148">Integrating with Azure AD with Conditional Access App Control</span></span>

<span data-ttu-id="eaa46-149">你可能已经将 SaaS 应用添加到 Azure AD 租户以强制执行多重身份验证和其他条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="eaa46-149">You might already have SaaS apps added to your Azure AD tenant to enforce multi-factor authentication and other conditional access policies.</span></span> <span data-ttu-id="eaa46-150">Microsoft Cloud App Security Azure AD 进行本机集成。</span><span class="sxs-lookup"><span data-stu-id="eaa46-150">Microsoft Cloud App Security natively integrates with Azure AD.</span></span> <span data-ttu-id="eaa46-151">你只需在 Azure AD 中配置一个策略，以使用 Azure AD 中的条件访问应用云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-151">All you have to do is configure a policy in Azure AD to use Conditional Access App Control in Cloud App Security.</span></span> <span data-ttu-id="eaa46-152">这将通过作为代理云应用安全这些托管 SaaS 应用的网络流量，这云应用安全监视此流量并应用会话控件。</span><span class="sxs-lookup"><span data-stu-id="eaa46-152">This routes network traffic for these managed SaaS apps through Cloud App Security as a proxy, which allows Cloud App Security to monitor this traffic and to apply session controls.</span></span> 

![适用于 Microsoft Cloud App Security 的体系结构 - SaaS 应用](../../media/defender/m365-defender-mcas-architecture-e.png)

<span data-ttu-id="eaa46-154">在此图中：</span><span class="sxs-lookup"><span data-stu-id="eaa46-154">In this illustration:</span></span>
- <span data-ttu-id="eaa46-155">SaaS 应用与 Azure AD 租户集成。</span><span class="sxs-lookup"><span data-stu-id="eaa46-155">SaaS apps are integrated with the Azure AD tenant.</span></span> <span data-ttu-id="eaa46-156">这允许 Azure AD 强制执行条件访问策略，包括多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="eaa46-156">This allows Azure AD to enforce conditional access policies, including multi-factor authentication.</span></span>
- <span data-ttu-id="eaa46-157">策略将添加到 Azure Active Directory，以将 SaaS 应用的流量云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-157">A policy is added to Azure Active Directory to direct traffic for SaaS apps to Cloud App Security.</span></span> <span data-ttu-id="eaa46-158">策略指定要应用此策略的 SaaS 应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-158">The policy specifies which SaaS apps to apply this policy to.</span></span> <span data-ttu-id="eaa46-159">因此，在 Azure AD 强制执行适用于这些 SaaS 应用的任何条件访问策略后，Azure AD 将 (代理) 会话流量云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-159">Consequently, after Azure AD enforces any conditional access policies that apply to these SaaS apps, Azure AD then directs (proxies) the session traffic through Cloud App Security.</span></span>
- <span data-ttu-id="eaa46-160">云应用安全监视此流量，并应用管理员配置的任何会话控制策略。</span><span class="sxs-lookup"><span data-stu-id="eaa46-160">Cloud App Security monitors this traffic and applies any session control policies that have been configured by administrators.</span></span> 

<span data-ttu-id="eaa46-161">你可能已使用尚未添加到 Azure AD 云应用安全发现和批准的云应用。</span><span class="sxs-lookup"><span data-stu-id="eaa46-161">You might have discovered and sanctioned cloud apps using Cloud App Security that have not been added to Azure AD.</span></span> <span data-ttu-id="eaa46-162">通过将这些云应用添加到 Azure AD 租户和条件访问规则的范围，可以利用条件访问应用控制。</span><span class="sxs-lookup"><span data-stu-id="eaa46-162">You can take advantage of Conditional Access App Control by adding these cloud apps to your Azure AD tenant and the scope of your conditional access rules.</span></span>

#### <a name="protecting-your-organization-from-hackers"></a><span data-ttu-id="eaa46-163">保护组织免受黑客攻击</span><span class="sxs-lookup"><span data-stu-id="eaa46-163">Protecting your organization from hackers</span></span>

<span data-ttu-id="eaa46-164">云应用安全本身提供强大的保护。</span><span class="sxs-lookup"><span data-stu-id="eaa46-164">Cloud App Security provides powerful protection on its own.</span></span> <span data-ttu-id="eaa46-165">但是，当与 Microsoft 365 Defender 的其他功能结合使用时，云应用安全向共享信号提供数据，这共同有助于阻止攻击。</span><span class="sxs-lookup"><span data-stu-id="eaa46-165">However, when combined with the other capabilities of Microsoft 365 Defender, Cloud App Security provides data into the shared signals which, together, helps stop attacks.</span></span>

<span data-ttu-id="eaa46-166">从概述到本试点评估和试点指南，值得Microsoft 365 Defender此图示。</span><span class="sxs-lookup"><span data-stu-id="eaa46-166">It's worth repeating this illustration from the overview to this Microsoft 365 Defender evaluation and pilot guide.</span></span> 

![如何Microsoft 365 Defender威胁链](../../media/defender/m365-defender-eval-threat-chain.png)

<span data-ttu-id="eaa46-168">专注于此图的右侧，Microsoft Cloud App Security异常行为，如无法旅行、凭据访问和异常下载、文件共享或邮件转发活动，并报告给安全团队。</span><span class="sxs-lookup"><span data-stu-id="eaa46-168">Focusing on the right side of this illustration, Microsoft Cloud App Security notices anomalous behavior like impossible-travel, credential access, and unusual download, file share, or mail forwarding activity and reports these to the security team.</span></span> <span data-ttu-id="eaa46-169">因此，云应用安全有助于防止黑客横向移动和敏感数据的窃取。</span><span class="sxs-lookup"><span data-stu-id="eaa46-169">Consequently, Cloud App Security helps prevent lateral movement by hackers and exfiltration of sensitive data.</span></span> <span data-ttu-id="eaa46-170">Microsoft 356 Defender 将来自所有组件的信号关联在一起，以提供完整的攻击情景。</span><span class="sxs-lookup"><span data-stu-id="eaa46-170">Microsoft 356 Defender correlates the signals from all the components to provide the full attack story.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="eaa46-171">了解关键概念</span><span class="sxs-lookup"><span data-stu-id="eaa46-171">Understand key concepts</span></span>

<span data-ttu-id="eaa46-172">下表确定了在评估、配置和部署Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="eaa46-172">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Cloud App Security.</span></span>


|<span data-ttu-id="eaa46-173">概念</span><span class="sxs-lookup"><span data-stu-id="eaa46-173">Concept</span></span>  |<span data-ttu-id="eaa46-174">说明</span><span class="sxs-lookup"><span data-stu-id="eaa46-174">Description</span></span> |<span data-ttu-id="eaa46-175">详细信息</span><span class="sxs-lookup"><span data-stu-id="eaa46-175">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="eaa46-176">云应用安全仪表板</span><span class="sxs-lookup"><span data-stu-id="eaa46-176">Cloud App Security Dashboard</span></span> | <span data-ttu-id="eaa46-177">概述了有关组织的最重要的信息，并提供了深入调查的链接。</span><span class="sxs-lookup"><span data-stu-id="eaa46-177">Presents an overview of the most important information about your organization and gives links to deeper investigation.</span></span>        | [<span data-ttu-id="eaa46-178">使用仪表板 </span><span class="sxs-lookup"><span data-stu-id="eaa46-178">Working with the dashboard </span></span>](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| <span data-ttu-id="eaa46-179">条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="eaa46-179">Conditional Access App Control</span></span>    | <span data-ttu-id="eaa46-180">与 Identity Provider 和 IdP (反向代理体系结构) Azure AD 条件访问策略，并选择性地强制执行会话控制。</span><span class="sxs-lookup"><span data-stu-id="eaa46-180">Reverse proxy architecture that integrates with your Identity Provider (IdP) to give Azure AD conditional access policies and selectively enforce session controls.</span></span>        |  [<span data-ttu-id="eaa46-181">使用条件访问Microsoft Cloud App Security控制保护应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-181">Protect apps with Microsoft Cloud App Security Conditional Access App Control</span></span>](/cloud-app-security/proxy-intro-aad)       |
|  <span data-ttu-id="eaa46-182">云应用程序目录</span><span class="sxs-lookup"><span data-stu-id="eaa46-182">Cloud App Catalog</span></span>   | <span data-ttu-id="eaa46-183">通过云应用目录，你可以全面了解超过 16，000 个云应用的 Microsoft 目录，这些应用根据 80 多个风险因素进行排名和评分。</span><span class="sxs-lookup"><span data-stu-id="eaa46-183">The Cloud App Catalog gives you a full picture against Microsoft catalog of over 16,000 cloud apps that are ranked and scored based on more than 80 risk factors.</span></span>    |  [<span data-ttu-id="eaa46-184">使用应用风险评分</span><span class="sxs-lookup"><span data-stu-id="eaa46-184">Working with App risk scores</span></span>](/cloud-app-security/risk-score)       |
| <span data-ttu-id="eaa46-185">云发现仪表板</span><span class="sxs-lookup"><span data-stu-id="eaa46-185">Cloud Discovery Dashboard</span></span>    | <span data-ttu-id="eaa46-186">云发现可分析流量日志，旨在进一步深入了解云应用在组织中如何使用，并给出警报和风险级别。</span><span class="sxs-lookup"><span data-stu-id="eaa46-186">Cloud Discovery analyzes your traffic logs and is designed to give more insight into how cloud apps are being used in your organization as well as give alerts and risk levels.</span></span>     |  [<span data-ttu-id="eaa46-187">使用发现的应用   </span><span class="sxs-lookup"><span data-stu-id="eaa46-187">Working with discovered apps   </span></span>](/cloud-app-security/discovered-apps)    |
|<span data-ttu-id="eaa46-188">连接的应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-188">Connected Apps</span></span> |<span data-ttu-id="eaa46-189">云应用安全使用云到云集成、API 连接器以及利用条件应用访问控制实时访问和会话控件的连接应用提供端到端保护。</span><span class="sxs-lookup"><span data-stu-id="eaa46-189">Cloud App Security provides end-to-end protection for connected apps using Cloud-to-Cloud integration, API connectors, and real-time access and session controls leveraging our Conditional App Access Controls.</span></span> |[<span data-ttu-id="eaa46-190">保护已连接的应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-190">Protecting connected apps</span></span>](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a><span data-ttu-id="eaa46-191">查看体系结构要求</span><span class="sxs-lookup"><span data-stu-id="eaa46-191">Review architecture requirements</span></span>

### <a name="discovering-cloud-apps"></a><span data-ttu-id="eaa46-192">发现云应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-192">Discovering cloud apps</span></span>

<span data-ttu-id="eaa46-193">若要发现环境中使用的云应用，你可以执行以下一项或两项操作：</span><span class="sxs-lookup"><span data-stu-id="eaa46-193">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="eaa46-194">与 Microsoft Defender for Endpoint 集成，快速启动并运行云发现。</span><span class="sxs-lookup"><span data-stu-id="eaa46-194">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="eaa46-195">通过此本机集成，你可以立即开始在 Windows 10 设备上、网络上和网络上收集云流量上的数据。</span><span class="sxs-lookup"><span data-stu-id="eaa46-195">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="eaa46-196">若要发现连接到网络的所有设备访问的所有云应用，云应用安全防火墙和其他代理上部署安全日志收集器。</span><span class="sxs-lookup"><span data-stu-id="eaa46-196">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="eaa46-197">这将从终结点收集数据，并将其发送到云应用安全进行分析。</span><span class="sxs-lookup"><span data-stu-id="eaa46-197">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="eaa46-198">云应用安全与一些第三方代理进行本机集成，以使用更多功能。</span><span class="sxs-lookup"><span data-stu-id="eaa46-198">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="eaa46-199">这些选项包含在步骤 [2 中。启用评估环境](eval-defender-mcas-enable-eval.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa46-199">These options are included in [Step 2. Enable the evaluation environment](eval-defender-mcas-enable-eval.md).</span></span> 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a><span data-ttu-id="eaa46-200">将 Azure AD 条件访问策略应用于云应用</span><span class="sxs-lookup"><span data-stu-id="eaa46-200">Applying Azure AD Conditional Access policies to cloud apps</span></span>

<span data-ttu-id="eaa46-201">条件访问应用 (将条件访问策略应用于云应用) Azure AD 集成。</span><span class="sxs-lookup"><span data-stu-id="eaa46-201">Conditional Access App Control (the ability to apply Conditional Access policies to cloud apps) requires integration with Azure AD.</span></span> <span data-ttu-id="eaa46-202">这不是开始使用 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="eaa46-202">This isn't a requirement for getting started with Cloud App Security.</span></span> <span data-ttu-id="eaa46-203">我们鼓励你在试点阶段（步骤[3）中试用此步骤。试点Microsoft Cloud App Security](eval-defender-mcas-pilot.md)。</span><span class="sxs-lookup"><span data-stu-id="eaa46-203">It is a step we encourage you to try out during the pilot phase — [Step 3. Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="eaa46-204">SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="eaa46-204">SIEM integration</span></span>

<span data-ttu-id="eaa46-205">你可以将Microsoft Cloud App Security SIEM 服务器或 Azure Sentinel 集成，以集中监视已连接应用中的警报和活动。</span><span class="sxs-lookup"><span data-stu-id="eaa46-205">You can integrate Microsoft Cloud App Security with your generic SIEM server or with Azure Sentinel to enable centralized monitoring of alerts and activities from connected apps.</span></span> 

<span data-ttu-id="eaa46-206">此外，Azure Sentinel Microsoft Cloud App Security连接器，以便与 Azure Sentinel 进行更深入的集成。</span><span class="sxs-lookup"><span data-stu-id="eaa46-206">Additionally, Azure Sentinel includes a Microsoft Cloud App Security connector to provide deeper integration with Azure Sentinel.</span></span> <span data-ttu-id="eaa46-207">这样，你不仅能够了解云应用，还可以获得复杂的分析，以识别和防御网络威胁，并控制数据传输方式。</span><span class="sxs-lookup"><span data-stu-id="eaa46-207">This enables you to not only gain visibility into your cloud apps but to also get sophisticated analytics to identify and combat cyberthreats and to control how your data travels.</span></span>

- [<span data-ttu-id="eaa46-208">通用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="eaa46-208">Generic SIEM integration</span></span>](/cloud-app-security/siem)
- [<span data-ttu-id="eaa46-209">将警报和云发现日志从 MCAS 流式传输至 Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="eaa46-209">Stream alerts and Cloud Discovery logs from MCAS into Azure Sentinel</span></span>](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a><span data-ttu-id="eaa46-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eaa46-210">Next steps</span></span>

<span data-ttu-id="eaa46-211">步骤 2/3：[为用户启用Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="eaa46-211">Step 2 of 3: [Enable the evaluation environment for Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)</span></span>

<span data-ttu-id="eaa46-212">返回到评估结果[概述Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eaa46-212">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="eaa46-213">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eaa46-213">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>