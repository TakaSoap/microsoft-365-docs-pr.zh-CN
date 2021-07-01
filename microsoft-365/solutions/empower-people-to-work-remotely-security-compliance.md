---
title: 步骤 3：为混合工作者部署安全性和合规性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 安全和合规性服务保护混合工作者的应用、数据和设备。
ms.openlocfilehash: 3de458f99ce1c83132d193cae523a49353b6956c
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229391"
---
# <a name="step-3-deploy-security-and-compliance-for-hybrid-workers"></a><span data-ttu-id="0c9dc-103">步骤 3：为混合工作者部署安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-103">Step 3: Deploy security and compliance for hybrid workers</span></span>

<span data-ttu-id="0c9dc-104">对于混合式工作者，他们中一些从未离开办公室或不常去，安全性和合规性是整个解决方案的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-104">For hybrid workers, some of whom never go into the office or who go infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="0c9dc-105">他们的所有通信都通过 Internet 进行，而不是局限于组织 Intranet。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span>

<span data-ttu-id="0c9dc-106">你和你的员工可以做一些事情来保持工作效率，同时降低网络安全风险并保持遵守内部策略和数据法规。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="0c9dc-107">远程工作需要以下安全性和合规性元素：</span><span class="sxs-lookup"><span data-stu-id="0c9dc-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="0c9dc-108">控制对混合工作者使用的生产力应用（如 Microsoft Teams）的访问</span><span class="sxs-lookup"><span data-stu-id="0c9dc-108">Controlled access to the productivity apps that hybrid workers use, such as Microsoft Teams</span></span>
- <span data-ttu-id="0c9dc-109">对远程工作者创建和使用的数据的受控访问和保护，例如聊天对话或共享文件</span><span class="sxs-lookup"><span data-stu-id="0c9dc-109">Controlled access to and protection of the data that hybrid workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="0c9dc-110">保护 Windows 10 设备免受恶意软件和其他类型的网络攻击</span><span class="sxs-lookup"><span data-stu-id="0c9dc-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="0c9dc-111">使用一致的敏感度和保护级别标签保护电子邮件、文件和站点</span><span class="sxs-lookup"><span data-stu-id="0c9dc-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="0c9dc-112">防止信息泄漏</span><span class="sxs-lookup"><span data-stu-id="0c9dc-112">Prevention of leaked information</span></span>
- <span data-ttu-id="0c9dc-113">遵守区域数据法规</span><span class="sxs-lookup"><span data-stu-id="0c9dc-113">Adherence to regional data regulations</span></span>

<span data-ttu-id="0c9dc-114">下面是为混合工作者提供安全和合规性服务的 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-114">Here are the features of Microsoft 365 that provide security and compliance services for hybrid workers.</span></span>

![使用这些 Microsoft 365 服务保持安全和合规](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="0c9dc-116">安全性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-116">Security</span></span>

<span data-ttu-id="0c9dc-117">使用 Microsoft 365 的这些安全功能来保护应用程序和数据。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-117">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="0c9dc-118">功能或特性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-118">Capability or feature</span></span> | <span data-ttu-id="0c9dc-119">为什么需要它</span><span class="sxs-lookup"><span data-stu-id="0c9dc-119">Why I need it</span></span> | <span data-ttu-id="0c9dc-120">许可</span><span class="sxs-lookup"><span data-stu-id="0c9dc-120">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0c9dc-121">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0c9dc-121">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0c9dc-122">保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="0c9dc-p102">Microsoft Defender for Office 365 会收集并分析应用中信号，用于检测、调查和修正安全风险，并保护组织免受电子邮件、链接 （URL） 和协作工具造成恶意威胁。它还提供针对标准和严格安全性等同的租户配置评估和配置工具。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-p102">Microsoft Defender for Office 365 collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools. It also provides automated tenant configuration assessment and configuration tooling for standard and strict security postures.</span></span> | <span data-ttu-id="0c9dc-125">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-125">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-126">恶意软件防护</span><span class="sxs-lookup"><span data-stu-id="0c9dc-126">Malware protection</span></span> | <span data-ttu-id="0c9dc-127">‎Microsoft Defender 防病毒和 Device Guard 提供基于设备的恶意软件防护。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-127">‎Microsoft Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="0c9dc-p103">SharePoint‎ Online 会自动扫描上传文件中已知的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-p103">SharePoint‎ Online automatically scans file uploads for known malware. ‎</span></span><br><br> <span data-ttu-id="0c9dc-130">Exchange Online Protection‎ (‎EOP‎) 可保护云邮箱。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-130">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="0c9dc-131">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-131">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-132">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c9dc-132">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="0c9dc-133">保护你的组织的设备免受网络威胁和数据泄露，并检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-133">Protect your organization’s devices from cyber threats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="0c9dc-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-134">Microsoft 365 E5</span></span> |
| <span data-ttu-id="0c9dc-135">云应用安全</span><span class="sxs-lookup"><span data-stu-id="0c9dc-135">Cloud App Security</span></span> | <span data-ttu-id="0c9dc-136">保防您的基于云的服务（Microsoft 365 和其他 SaaS 应用）受到攻击。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-136">Protect your cloud-based services—both Microsoft 365 and other SaaS apps—from attack.</span></span> | <span data-ttu-id="0c9dc-137">Microsoft 365 E5 或单独的云应用安全许可证</span><span class="sxs-lookup"><span data-stu-id="0c9dc-137">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="0c9dc-138">Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="0c9dc-138">Azure AD Identity Protection</span></span>  | <span data-ttu-id="0c9dc-139">自动检测和修复基于标识的风险。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-139">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="0c9dc-140">创建基于风险的条件访问策略，以对有风险的登录要求多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-140">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="0c9dc-141">Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）</span><span class="sxs-lookup"><span data-stu-id="0c9dc-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

<span data-ttu-id="0c9dc-142">第一步是了解和使用 [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-142">You first step should be to learn about and use [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score).</span></span>

<span data-ttu-id="0c9dc-143">有关详细信息，请参阅[安全团队为支持在家办公需完成的 12 大任务](../security/top-security-tasks-for-remote-work.md)。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-143">See [Top 12 tasks for security teams to support working from home](../security/top-security-tasks-for-remote-work.md) for more information.</span></span>

<span data-ttu-id="0c9dc-144">有关 Microsoft 365 安全性的信息，请参阅 [Microsoft 365 安全文档](/microsoft-365/security)。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-144">For information about security across Microsoft 365, see [Microsoft 365 security documentation](/microsoft-365/security).</span></span>

## <a name="compliance"></a><span data-ttu-id="0c9dc-145">合规性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-145">Compliance</span></span>

<span data-ttu-id="0c9dc-146">使用 Microsoft 365 的这些合规性功能来遵守内部政策或法规要求。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-146">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="0c9dc-147">功能或特性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-147">Capability or feature</span></span> | <span data-ttu-id="0c9dc-148">为什么需要它</span><span class="sxs-lookup"><span data-stu-id="0c9dc-148">Why I need it</span></span> | <span data-ttu-id="0c9dc-149">许可</span><span class="sxs-lookup"><span data-stu-id="0c9dc-149">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0c9dc-150">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0c9dc-150">Sensitivity labels</span></span> | <span data-ttu-id="0c9dc-151">通过在电子邮件、文件或站点上放置具有不同保护级别的标签，可以在不影响用户工作效率和协作能力的情况下对组织的数据进行分类和保护。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-151">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="0c9dc-152">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-152">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-153">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0c9dc-153">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="0c9dc-154">在内部和外部检测、警告和阻止有风险的、无意或不适当的共享，例如包含个人信息的数据共享。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-154">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="0c9dc-155">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-155">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-156">条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="0c9dc-156">Conditional Access App Control</span></span> | <span data-ttu-id="0c9dc-157">防止敏感数据下载到用户的个人设备。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-157">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="0c9dc-158">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-158">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-159">数据保留标签和策略</span><span class="sxs-lookup"><span data-stu-id="0c9dc-159">Data retention labels and policies</span></span> | <span data-ttu-id="0c9dc-160">实施信息治理控制，例如将数据保留多长时间以及对客户个人数据存储的要求，以符合组织的政策或数据法规。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-160">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="0c9dc-161">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-161">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-162">Office 邮件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="0c9dc-162">Office message encryption (OME)</span></span> | <span data-ttu-id="0c9dc-163">在组织内部和外部的人员之间发送和接收加密的电子邮件，其中包含受监管的数据，例如客户的个人数据。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-163">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="0c9dc-164">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-165">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="0c9dc-165">Compliance Manager</span></span> | <span data-ttu-id="0c9dc-166">使用 Microsoft 服务信任门户中基于工作流的风险评估工具来管理与 Microsoft 云服务相关的法规合规性活动。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-166">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="0c9dc-167">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-167">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-168">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="0c9dc-168">Compliance Manager</span></span> | <span data-ttu-id="0c9dc-169">在 Microsoft 365 合规中心中查看当前合规配置和改进建议的总体分数。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-169">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="0c9dc-170">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="0c9dc-170">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="0c9dc-171">通信合规性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-171">Communication Compliance</span></span>  | <span data-ttu-id="0c9dc-172">对组织中的不当邮件进行检测、捕获和执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-172">Detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> | <span data-ttu-id="0c9dc-173">具有合规性或内部风险管理加载项的 Microsoft 365 E5 或 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="0c9dc-173">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
| <span data-ttu-id="0c9dc-174">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="0c9dc-174">Insider Risk Management</span></span> |  <span data-ttu-id="0c9dc-175">对组织中的恶意和意外风险进行检测、调查并采取相关措施。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-175">Detect, investigate, and act on malicious and inadvertent risks in your organization.</span></span> <span data-ttu-id="0c9dc-176">即使员工使用的是非托管设备，Microsoft 365 也可检测到这些类型的风险。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-176">Microsoft 365 can detect these kinds of risks even when a worker is using an unmanaged device.</span></span> | <span data-ttu-id="0c9dc-177">具有合规性或内部风险管理加载项的 Microsoft 365 E5 或 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="0c9dc-177">Microsoft 365 E5 or Microsoft 365 E3 with the Compliance or Insider Risk Management add-ons</span></span> |
||||

<span data-ttu-id="0c9dc-178">有关详细信息，请参阅 [Microsoft 365 合规中心入门快速任务](../compliance/compliance-quick-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-178">See [Quick tasks for getting started with Microsoft 365 compliance](../compliance/compliance-quick-tasks.md) for more information.</span></span>

## <a name="results-of-step-3"></a><span data-ttu-id="0c9dc-179">步骤 3 的结果</span><span class="sxs-lookup"><span data-stu-id="0c9dc-179">Results of Step 3</span></span>

<span data-ttu-id="0c9dc-180">对于混合工作者，已实现：</span><span class="sxs-lookup"><span data-stu-id="0c9dc-180">For your hybrid workers, you have implemented:</span></span>

- <span data-ttu-id="0c9dc-181">安全性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-181">Security</span></span>
  - <span data-ttu-id="0c9dc-182">控制对混合工作者用于通信和协作的应用和数据的访问</span><span class="sxs-lookup"><span data-stu-id="0c9dc-182">Controlled access to apps and data that hybrid workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="0c9dc-183">针对云服务数据、电子邮件和 Windows 10 设备的恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="0c9dc-183">Malware protection for cloud service data, email, and Windows 10 devices</span></span>
- <span data-ttu-id="0c9dc-184">合规性</span><span class="sxs-lookup"><span data-stu-id="0c9dc-184">Compliance</span></span>
  - <span data-ttu-id="0c9dc-185">一致的敏感度和保护级别标签</span><span class="sxs-lookup"><span data-stu-id="0c9dc-185">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="0c9dc-186">防止信息泄露的策略</span><span class="sxs-lookup"><span data-stu-id="0c9dc-186">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="0c9dc-187">遵守区域数据法规</span><span class="sxs-lookup"><span data-stu-id="0c9dc-187">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="0c9dc-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0c9dc-188">Next step</span></span>

<span data-ttu-id="0c9dc-189">[![步骤 4：管理设备、电脑和其他终结点](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="0c9dc-189">[![Step 4: Manage your devices, PCs, and other endpoints](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)</span></span>

<span data-ttu-id="0c9dc-190">继续执行[步骤 4](empower-people-to-work-remotely-manage-endpoints.md)，以管理你的设备、电脑和其他终结点。</span><span class="sxs-lookup"><span data-stu-id="0c9dc-190">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
