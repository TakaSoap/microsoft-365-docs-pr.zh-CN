---
title: Microsoft 365 中的应用治理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 实施 Microsoft 应用治理功能来治理你的应用。
ms.openlocfilehash: bc8c739132de52abb69c15479cd851462e9f6ce7
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420038"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="f7e44-103">Microsoft Cloud App Security（预览版）的应用治理加载项</span><span class="sxs-lookup"><span data-stu-id="f7e44-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="f7e44-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f7e44-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f7e44-105">网络攻击通过各种日益复杂的方式来利用你部署在本地和云基础设施中的应用，为特权提升、横向移动和数据泄露奠定基础。</span><span class="sxs-lookup"><span data-stu-id="f7e44-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="f7e44-106">若要了解潜在风险并阻止这些类型的攻击，你需要清楚了解组织的应用合规状况，以快速识别应用何时表现出异常行为，并在这些行为对你的环境、数据和用户构成风险时做出响应。</span><span class="sxs-lookup"><span data-stu-id="f7e44-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="f7e44-107">Microsoft Cloud App Security 的应用治理加载项功能是一项安全和策略管理功能，专为通过 Microsoft Graph API 访问 Microsoft 365 数据，且已启用 OAuth 的应用而设计。</span><span class="sxs-lookup"><span data-stu-id="f7e44-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="f7e44-108">应用治理通过可操作的见解和自动化的策略警报和操作，对这些应用及其用户如何访问、使用和共享存储在 Microsoft 365 中的敏感数据提供全面的可见性、修复和治理。</span><span class="sxs-lookup"><span data-stu-id="f7e44-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="f7e44-109">应用治理为你提供全面的：</span><span class="sxs-lookup"><span data-stu-id="f7e44-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="f7e44-110">**见解**：在单个仪表板上查看租户中 Microsoft 365 平台的所有第三方应用的视图。</span><span class="sxs-lookup"><span data-stu-id="f7e44-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="f7e44-111">你可以查看所有应用的状态和警报活动，并对它们做出反应或响应。</span><span class="sxs-lookup"><span data-stu-id="f7e44-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="f7e44-112">**治理**：为应用和用户模式及行为创建主动或被动策略，防止用户使用不合规或恶意的应用，并限制有风险的应用访问你的数据。</span><span class="sxs-lookup"><span data-stu-id="f7e44-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="f7e44-113">**检测**：在应用活动出现异常以及使用不合规、恶意或有风险的应用时收到警报和通知。</span><span class="sxs-lookup"><span data-stu-id="f7e44-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="f7e44-114">**修复**：除了自动修复功能外，还可以及时使用修复控件来响应异常应用活动检测。</span><span class="sxs-lookup"><span data-stu-id="f7e44-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="f7e44-115">应用治理是一种基于平台的解决方案，是 Microsoft 365 应用生态系统不可或缺的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7e44-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="f7e44-116">应用治理可监督和管理在 Azure Active Directory (Azure AD) 中注册、通过 Microsoft Graph API 访问数据，并且已启用 OAuth 的应用。</span><span class="sxs-lookup"><span data-stu-id="f7e44-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="f7e44-117">应用治理为你提供应用行为控件，以帮助增强 IT 基础设施的安全性和合规性状况。</span><span class="sxs-lookup"><span data-stu-id="f7e44-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="f7e44-118">应用治理概览</span><span class="sxs-lookup"><span data-stu-id="f7e44-118">A first glimpse at app governance</span></span>

<span data-ttu-id="f7e44-119">要查看应用治理仪表板，请转到 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance)。</span><span class="sxs-lookup"><span data-stu-id="f7e44-119">To see the app governance dashboard, go to [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="f7e44-120">请注意，若要查看应用治理数据，你的登录帐户必须具有其中一个[管理员角色](app-governance-get-started.md#administrator-roles)。</span><span class="sxs-lookup"><span data-stu-id="f7e44-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="f7e44-121">应用治理与 Azure AD 和 Microsoft Cloud App Security 的集成</span><span class="sxs-lookup"><span data-stu-id="f7e44-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="f7e44-122">应用治理、Azure AD 和 Microsoft Cloud App Security 收集并提供不同的数据集：</span><span class="sxs-lookup"><span data-stu-id="f7e44-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="f7e44-123">应用治理提供有关 API 级别应用活动的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="f7e44-124">Azure AD 提供基础应用元数据和有关登录应用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="f7e44-125">Microsoft Cloud App Security 提供应用风险信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="f7e44-126">通过跨应用治理、Azure AD 和 Microsoft Cloud App Security 共享信息，你可以在一个门户中显示聚合信息，并轻松链接到另一个门户以获取更多信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-126">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information.</span></span> <span data-ttu-id="f7e44-127">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="f7e44-127">Here are some examples:</span></span>

- <span data-ttu-id="f7e44-128">应用治理中的应用登录信息：</span><span class="sxs-lookup"><span data-stu-id="f7e44-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="f7e44-129">从应用治理门户，你可以查看每个应用的聚合登录活动，并链接回 Azure Active Directory 管理中心以获取登录事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="f7e44-130">Microsoft Cloud App Security 门户中的 API 使用信息：</span><span class="sxs-lookup"><span data-stu-id="f7e44-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="f7e44-131">从 Microsoft Cloud App Security 门户，你可以查看 API 使用级别和聚合数据传输，并链接到应用治理门户以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7e44-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="f7e44-132">以下是该集成的摘要。</span><span class="sxs-lookup"><span data-stu-id="f7e44-132">Here's a summary of the integration.</span></span>

![应用治理与 Azure AD 和 Microsoft Cloud App Security 的集成](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="f7e44-134">此外，应用治理会将其警报作为信号发送到 Microsoft Cloud App Security 和 Microsoft 365 Defender，并且会接收来自 Microsoft Cloud App Security 的警报，以便对基于应用的安全事件进行更详细的分析。</span><span class="sxs-lookup"><span data-stu-id="f7e44-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a><span data-ttu-id="f7e44-135">使用应用治理</span><span class="sxs-lookup"><span data-stu-id="f7e44-135">Using app governance</span></span>

<span data-ttu-id="f7e44-136">使用应用治理可防止租户及其数据受到潜在恶意或不良行为应用的影响，这属于以下三个核心功能范畴：</span><span class="sxs-lookup"><span data-stu-id="f7e44-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="f7e44-137">功能</span><span class="sxs-lookup"><span data-stu-id="f7e44-137">Capability</span></span> | <span data-ttu-id="f7e44-138">说明</span><span class="sxs-lookup"><span data-stu-id="f7e44-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="f7e44-139">应用可见性和见解</span><span class="sxs-lookup"><span data-stu-id="f7e44-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="f7e44-140">全方位了解租户中 Microsoft 365 应用的流量和活动。</span><span class="sxs-lookup"><span data-stu-id="f7e44-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="f7e44-141">用于强化治理的应用策略</span><span class="sxs-lookup"><span data-stu-id="f7e44-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="f7e44-142">创建主动或被动应用策略，这将允许你对 Microsoft 3635 应用实施治理。</span><span class="sxs-lookup"><span data-stu-id="f7e44-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="f7e44-143">检测和修正</span><span class="sxs-lookup"><span data-stu-id="f7e44-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="f7e44-144">根据平台检测警报或策略生成的检测警报，监控你的应用是否存在异常应用行为，并根据应用策略设置自动或手动进行修正。</span><span class="sxs-lookup"><span data-stu-id="f7e44-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
