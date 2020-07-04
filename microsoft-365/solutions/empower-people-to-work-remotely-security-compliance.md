---
title: 步骤 3：为远程工作者部署安全与合规
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 使用 Microsoft 365 安全和合规性服务为远程工作者保护你的应用、数据和设备。
ms.openlocfilehash: f1c6f509477b4f4523951a64e6b4298753a1519d
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005991"
---
# <a name="step-3-deploy-security-and-compliance-for-remote-workers"></a><span data-ttu-id="0d1d5-103">步骤 3：为远程工作者部署安全与合规</span><span class="sxs-lookup"><span data-stu-id="0d1d5-103">Step 3: Deploy security and compliance for remote workers</span></span>

<span data-ttu-id="0d1d5-104">对于远程工作者来说，他们中的一些人永远不会上班或很少上班，安全性和合规性是整个解决方案的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-104">For remote workers, some of whom never come into the office or very infrequently, security and compliance are an important part of the overall solution.</span></span> <span data-ttu-id="0d1d5-105">他们的所有通信都通过 Internet 进行，而不是局限于组织 Intranet。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-105">All of their communications occur over the Internet instead of being confined to an organizational intranet.</span></span> 

<span data-ttu-id="0d1d5-106">你和你的员工可以做一些事情来保持工作效率，同时降低网络安全风险并保持遵守内部策略和数据法规。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-106">There are things you and your workers can do to remain productive while decreasing cybersecurity risk and maintaining compliance with your internal policies and data regulations.</span></span>

<span data-ttu-id="0d1d5-107">远程工作需要以下安全性和合规性元素：</span><span class="sxs-lookup"><span data-stu-id="0d1d5-107">Remote work needs these elements of security and compliance:</span></span>

- <span data-ttu-id="0d1d5-108">对远程工作者使用的生产力应用（例如 Microsoft Teams）的受控访问</span><span class="sxs-lookup"><span data-stu-id="0d1d5-108">Controlled access to the productivity apps that remote workers use, such as Microsoft Teams</span></span> 
- <span data-ttu-id="0d1d5-109">对远程工作者创建和使用的数据的受控访问和保护，例如聊天对话或共享文件</span><span class="sxs-lookup"><span data-stu-id="0d1d5-109">Controlled access to and protection of the data that remote workers create and use, such as chat conversations or shared files</span></span>
- <span data-ttu-id="0d1d5-110">保护 Windows 10 设备免受恶意软件和其他类型的网络攻击</span><span class="sxs-lookup"><span data-stu-id="0d1d5-110">Protection of Windows 10 devices from malware and other types of cyberattacks</span></span>
- <span data-ttu-id="0d1d5-111">使用一致的敏感度和保护级别标签保护电子邮件、文件和站点</span><span class="sxs-lookup"><span data-stu-id="0d1d5-111">Protection of email, files, and site with consistent labeling for levels of sensitivity and protection</span></span>
- <span data-ttu-id="0d1d5-112">防止信息泄漏</span><span class="sxs-lookup"><span data-stu-id="0d1d5-112">Prevention of leaked information</span></span>
- <span data-ttu-id="0d1d5-113">遵守区域数据法规</span><span class="sxs-lookup"><span data-stu-id="0d1d5-113">Adherence to regional data regulations</span></span>

![使用这些 Microsoft 365 服务保持安全和合规](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a><span data-ttu-id="0d1d5-115">安全性</span><span class="sxs-lookup"><span data-stu-id="0d1d5-115">Security</span></span>

<span data-ttu-id="0d1d5-116">使用 Microsoft 365 的这些安全功能来保护应用程序和数据。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-116">Protect your applications and data with these security features of Microsoft 365.</span></span>

| <span data-ttu-id="0d1d5-117">功能或特性</span><span class="sxs-lookup"><span data-stu-id="0d1d5-117">Capability or feature</span></span> | <span data-ttu-id="0d1d5-118">说明</span><span class="sxs-lookup"><span data-stu-id="0d1d5-118">Description</span></span> | <span data-ttu-id="0d1d5-119">许可</span><span class="sxs-lookup"><span data-stu-id="0d1d5-119">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0d1d5-120">Office 高级威胁防护 (ATP)</span><span class="sxs-lookup"><span data-stu-id="0d1d5-120">Office Advanced Threat Protection (ATP)</span></span> | <span data-ttu-id="0d1d5-121">保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-121">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> <br><br> <span data-ttu-id="0d1d5-122">Office ATP 会从你的应用收集和分析信号，以检测、调查和补救安全风险，并保护你的组织免受电子邮件、链接 (URL) 和协作工具带来的恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-122">Office ATP collects and analyzes signals from your apps for detection, investigation, and remediation of security risks and safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> | <span data-ttu-id="0d1d5-123">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-123">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="0d1d5-124">恶意软件防护</span><span class="sxs-lookup"><span data-stu-id="0d1d5-124">Malware protection</span></span> | <span data-ttu-id="0d1d5-125">‎Windows Defender 防病毒和 Device Guard 提供基于设备的恶意软件防护。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-125">‎Windows Defender Antivirus and Device Guard provides device-based malware protection.</span></span> <br><br> <span data-ttu-id="0d1d5-126">SharePoint‎ Online 会自动扫描上传文件中已知的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-126">SharePoint‎ Online automatically scans file uploads for known malware.</span></span> <span data-ttu-id="0d1d5-127">‎</span><span class="sxs-lookup"><span data-stu-id="0d1d5-127">‎</span></span><br><br> <span data-ttu-id="0d1d5-128">Exchange Online Protection‎ (‎EOP‎) 可保护云邮箱。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-128">Exchange Online Protection‎ (‎EOP‎) secures cloud mailboxes.</span></span> | <span data-ttu-id="0d1d5-129">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-130">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="0d1d5-130">Microsoft Defender ATP</span></span> | <span data-ttu-id="0d1d5-131">保护你的组织的设备免受网络威胁和数据泄露，并检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-131">Protect your organization’s devices from cyberthreats and data breaches and detect, investigate, and respond to advanced threats.</span></span> | <span data-ttu-id="0d1d5-132">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-132">Microsoft 365 E5</span></span> |
| <span data-ttu-id="0d1d5-133">云应用安全</span><span class="sxs-lookup"><span data-stu-id="0d1d5-133">Cloud App Security</span></span> | <span data-ttu-id="0d1d5-134">保护基于云的服务（Microsoft 365 和其他 SaaS 应用）免受攻击。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-134">Protect your cloud-based services—both Microsoft 365 and other SaaS apps— from attack.</span></span> | <span data-ttu-id="0d1d5-135">Microsoft 365 E5 或单独的云应用安全许可证</span><span class="sxs-lookup"><span data-stu-id="0d1d5-135">Microsoft 365 E5 or individual Cloud App Security licenses</span></span> |
| <span data-ttu-id="0d1d5-136">Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="0d1d5-136">Azure AD Identity Protection</span></span>  | <span data-ttu-id="0d1d5-137">自动检测和修复基于标识的风险。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-137">Automate detection and remediation of identity-based risks.</span></span> <br><br><span data-ttu-id="0d1d5-138">创建基于风险的条件访问策略，以对有风险的登录要求多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-138">Create risk-based Conditional Access policies to require multi-factor authentication (MFA) for risky sign-ins.</span></span> | <span data-ttu-id="0d1d5-139">Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）</span><span class="sxs-lookup"><span data-stu-id="0d1d5-139">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
||||

## <a name="compliance"></a><span data-ttu-id="0d1d5-140">合规性</span><span class="sxs-lookup"><span data-stu-id="0d1d5-140">Compliance</span></span>

<span data-ttu-id="0d1d5-141">使用 Microsoft 365 的这些合规性功能来遵守内部政策或法规要求。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-141">Comply with internal policies or regulatory requirements with these compliance features of Microsoft 365.</span></span>

| <span data-ttu-id="0d1d5-142">功能或特性</span><span class="sxs-lookup"><span data-stu-id="0d1d5-142">Capability or feature</span></span> | <span data-ttu-id="0d1d5-143">说明</span><span class="sxs-lookup"><span data-stu-id="0d1d5-143">Description</span></span> | <span data-ttu-id="0d1d5-144">许可</span><span class="sxs-lookup"><span data-stu-id="0d1d5-144">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0d1d5-145">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0d1d5-145">Sensitivity labels</span></span> | <span data-ttu-id="0d1d5-146">通过在电子邮件、文件或站点上放置具有不同保护级别的标签，可以在不影响用户工作效率和协作能力的情况下对组织的数据进行分类和保护。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-146">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="0d1d5-147">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-147">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-148">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="0d1d5-148">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="0d1d5-149">在内部和外部检测、警告和阻止有风险的、无意或不适当的共享，例如包含个人信息的数据共享。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-149">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="0d1d5-150">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-150">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="0d1d5-151">条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="0d1d5-151">Conditional Access App Control</span></span> | <span data-ttu-id="0d1d5-152">防止敏感数据下载到用户的个人设备。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-152">Prevent sensitive data from being downloaded to users' personal devices.</span></span> | <span data-ttu-id="0d1d5-153">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-153">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-154">数据保留标签和策略</span><span class="sxs-lookup"><span data-stu-id="0d1d5-154">Data retention labels and policies</span></span> | <span data-ttu-id="0d1d5-155">实施信息治理控制，例如将数据保留多长时间以及对客户个人数据存储的要求，以符合组织的政策或数据法规。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-155">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="0d1d5-156">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-156">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-157">电子邮件加密</span><span class="sxs-lookup"><span data-stu-id="0d1d5-157">Email encryption</span></span> | <span data-ttu-id="0d1d5-158">在组织内部和外部的人员之间发送和接收加密的电子邮件，其中包含受监管的数据，例如客户的个人数据。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-158">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="0d1d5-159">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-159">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-160">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="0d1d5-160">Compliance Manager</span></span> | <span data-ttu-id="0d1d5-161">使用 Microsoft 服务信任门户中基于工作流的风险评估工具来管理与 Microsoft 云服务相关的法规合规性活动。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-161">Manage regulatory compliance activities related to Microsoft cloud services with this workflow-based risk assessment tool in the Microsoft Service Trust Portal.</span></span> | <span data-ttu-id="0d1d5-162">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-162">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="0d1d5-163">合规性分数（预览版）</span><span class="sxs-lookup"><span data-stu-id="0d1d5-163">Compliance Score (preview)</span></span> | <span data-ttu-id="0d1d5-164">在 Microsoft 365 合规中心中查看当前合规配置和改进建议的总体分数。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-164">See an overall score of your current compliance configuration and recommendations for improving it in the Microsoft 365 Compliance Center.</span></span> | <span data-ttu-id="0d1d5-165">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="0d1d5-165">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="results-of-step-3"></a><span data-ttu-id="0d1d5-166">步骤 3 的结果</span><span class="sxs-lookup"><span data-stu-id="0d1d5-166">Results of Step 3</span></span>

<span data-ttu-id="0d1d5-167">对于你的远程工作者，你已实施：</span><span class="sxs-lookup"><span data-stu-id="0d1d5-167">For your remote workers, you have implemented:</span></span>

- <span data-ttu-id="0d1d5-168">安全性：</span><span class="sxs-lookup"><span data-stu-id="0d1d5-168">Security:</span></span>
  - <span data-ttu-id="0d1d5-169">对远程工作者用于通信和协作的应用和数据的受控访问</span><span class="sxs-lookup"><span data-stu-id="0d1d5-169">Controlled access to apps and data that remote workers use to communicate and collaborate</span></span>
  - <span data-ttu-id="0d1d5-170">针对云服务数据、电子邮件和 Windows 10 设备的恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="0d1d5-170">Malware protection for cloud service data, email, and Windows 10 devices</span></span> 
- <span data-ttu-id="0d1d5-171">合规性：</span><span class="sxs-lookup"><span data-stu-id="0d1d5-171">Compliance:</span></span>
  - <span data-ttu-id="0d1d5-172">一致的敏感度和保护级别标签</span><span class="sxs-lookup"><span data-stu-id="0d1d5-172">Consistent labeling for levels of sensitivity and protection</span></span>
  - <span data-ttu-id="0d1d5-173">防止信息泄露的策略</span><span class="sxs-lookup"><span data-stu-id="0d1d5-173">Policies to prevention information leakage</span></span>
  - <span data-ttu-id="0d1d5-174">遵守区域数据法规</span><span class="sxs-lookup"><span data-stu-id="0d1d5-174">Adherence to regional data regulations</span></span>

## <a name="next-step"></a><span data-ttu-id="0d1d5-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0d1d5-175">Next step</span></span>

<span data-ttu-id="0d1d5-176">继续执行[步骤 4](empower-people-to-work-remotely-manage-endpoints.md)，以管理你的设备、电脑和其他终结点。</span><span class="sxs-lookup"><span data-stu-id="0d1d5-176">Continue with [Step 4](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
