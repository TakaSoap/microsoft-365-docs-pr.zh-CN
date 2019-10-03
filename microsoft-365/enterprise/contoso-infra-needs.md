---
title: Contoso 的 IT 基础结构和业务需求
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 本地 IT 基础设施的基本结构，以及 Microsoft 365 企业版如何满足其业务需求。
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369583"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="4fe85-103">Contoso 的 IT 基础结构和业务需求</span><span class="sxs-lookup"><span data-stu-id="4fe85-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="4fe85-104">**摘要：** 了解 Contoso 本地 IT 基础设施的基本结构，以及 Microsoft 365 企业版如何满足其业务需求。</span><span class="sxs-lookup"><span data-stu-id="4fe85-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="4fe85-105">Contoso 正在从本地集中式 IT 基础结构转换到一个合并了基于云的个人生产率工作负载和应用程序的包含云的 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="4fe85-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="4fe85-106">Contoso 的现有 IT 基础结构</span><span class="sxs-lookup"><span data-stu-id="4fe85-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="4fe85-107">Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="4fe85-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="4fe85-108">图 1 显示总部办事处及应用程序数据中心、DMZ 和 Internet。</span><span class="sxs-lookup"><span data-stu-id="4fe85-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contoso 的现有 IT 基础结构](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="4fe85-110">**图 1 Contoso 的现有 IT 基础结构**</span><span class="sxs-lookup"><span data-stu-id="4fe85-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="4fe85-111">本地应用程序数据中心主机：</span><span class="sxs-lookup"><span data-stu-id="4fe85-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="4fe85-112">使用 SQL Server 和其他 Linux 数据库的自定义业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="4fe85-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="4fe85-113">一组旧版 SharePoint server。</span><span class="sxs-lookup"><span data-stu-id="4fe85-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="4fe85-114">用于文件存储的组织级和工作组级服务器。</span><span class="sxs-lookup"><span data-stu-id="4fe85-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="4fe85-115">此外，每个区域中心办事处都支持一组服务器和一组类似的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4fe85-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="4fe85-116">这些服务器受区域 IT 部门的控制。</span><span class="sxs-lookup"><span data-stu-id="4fe85-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="4fe85-117">这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="4fe85-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="4fe85-118">在 Contoso 总部 DMZ 中，不同的服务器集提供不同的功能：</span><span class="sxs-lookup"><span data-stu-id="4fe85-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="4fe85-119">对 Contoso 公共网站的托管，客户可以在其中订购产品、部件、配件或服务。</span><span class="sxs-lookup"><span data-stu-id="4fe85-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="4fe85-120">对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="4fe85-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="4fe85-121">巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于虚拟专用网 (VPN) 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="4fe85-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="4fe85-122">Contoso 的业务需求</span><span class="sxs-lookup"><span data-stu-id="4fe85-122">Contoso's business needs</span></span>

<span data-ttu-id="4fe85-123">Contoso 的业务需求分为五个主要类别。</span><span class="sxs-lookup"><span data-stu-id="4fe85-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="4fe85-124">工作效率：</span><span class="sxs-lookup"><span data-stu-id="4fe85-124">Productivity:</span></span>

- <span data-ttu-id="4fe85-125">简化协作</span><span class="sxs-lookup"><span data-stu-id="4fe85-125">Make collaboration easier</span></span>

  <span data-ttu-id="4fe85-126">将电子邮件和基于文件共享的协作替换为在线模型，以允许对文档进行实时更改、简化在线会议并捕获会话线程。</span><span class="sxs-lookup"><span data-stu-id="4fe85-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="4fe85-127">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="4fe85-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="4fe85-128">由于许多员工在家办公或在办公点工作，将出现瓶颈的 VPN 解决方案替换为对 Contoso 数据和云资源的高性能访问。</span><span class="sxs-lookup"><span data-stu-id="4fe85-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="4fe85-129">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="4fe85-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="4fe85-130">利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。</span><span class="sxs-lookup"><span data-stu-id="4fe85-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="4fe85-131">安全性：</span><span class="sxs-lookup"><span data-stu-id="4fe85-131">Security:</span></span>

- <span data-ttu-id="4fe85-132">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="4fe85-132">Identity and access management</span></span>

  <span data-ttu-id="4fe85-133">强制实施多重身份验证和其他形式的身份验证并保护用户和管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="4fe85-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="4fe85-134">威胁防护</span><span class="sxs-lookup"><span data-stu-id="4fe85-134">Threat protection</span></span>

  <span data-ttu-id="4fe85-135">防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="4fe85-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="4fe85-136">信息保护</span><span class="sxs-lookup"><span data-stu-id="4fe85-136">Information protection</span></span>

  <span data-ttu-id="4fe85-137">锁定对高价值数字资产（如客户数据、设计和制造规范以及员工信息）的访问并加密。</span><span class="sxs-lookup"><span data-stu-id="4fe85-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="4fe85-138">安全管理</span><span class="sxs-lookup"><span data-stu-id="4fe85-138">Security management</span></span>

  <span data-ttu-id="4fe85-139">监视安全状态并且能够实时检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="4fe85-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="4fe85-140">远程和移动访问及业务合作伙伴：</span><span class="sxs-lookup"><span data-stu-id="4fe85-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="4fe85-141">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="4fe85-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="4fe85-142">制定自带设备 (BYOD) 和公司拥有的设备管理以确保安全访问、正确的应用程序行为和公司数据保护。</span><span class="sxs-lookup"><span data-stu-id="4fe85-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="4fe85-143">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="4fe85-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="4fe85-144">通过将通常访问的资源移动到云来减少维护和支持成本，并提高远程访问解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="4fe85-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="4fe85-145">为企业对企业 (B2B) 交易提供更好的连接并减少开销</span><span class="sxs-lookup"><span data-stu-id="4fe85-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="4fe85-146">将不断老化且费用高昂的合作伙伴Extranet 替换为使用联合身份验证的基于云的解决方案。</span><span class="sxs-lookup"><span data-stu-id="4fe85-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="4fe85-147">合规性：</span><span class="sxs-lookup"><span data-stu-id="4fe85-147">Compliance:</span></span>

- <span data-ttu-id="4fe85-148">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="4fe85-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="4fe85-149">遵守并始终遵守针对数据存储、加密、数据隐私和个人数据的行业和区域法规，如欧盟一般数据保护条例 (GDPR)。</span><span class="sxs-lookup"><span data-stu-id="4fe85-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="4fe85-150">管理：</span><span class="sxs-lookup"><span data-stu-id="4fe85-150">Management:</span></span>

- <span data-ttu-id="4fe85-151">减少管理客户端电脑和设备上运行的软件的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="4fe85-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="4fe85-152">在组织中自动安装 Windows 操作系统和 Microsoft Office 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="4fe85-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="4fe85-153">将 Contoso 业务需求映射到 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="4fe85-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4fe85-154">Contoso 的 IT 部门会在部署之前，确定以下映射到 Microsoft 365 企业版 E5 功能的业务需求：</span><span class="sxs-lookup"><span data-stu-id="4fe85-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="4fe85-155">**类别**</span><span class="sxs-lookup"><span data-stu-id="4fe85-155">**Category**</span></span> | <span data-ttu-id="4fe85-156">**业务需要**</span><span class="sxs-lookup"><span data-stu-id="4fe85-156">**Business need**</span></span> | <span data-ttu-id="4fe85-157">**Microsoft 365 企业版的产品或功能**</span><span class="sxs-lookup"><span data-stu-id="4fe85-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="4fe85-158">工作效率</span><span class="sxs-lookup"><span data-stu-id="4fe85-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="4fe85-159">简化协作</span><span class="sxs-lookup"><span data-stu-id="4fe85-159">Make collaboration easier</span></span> | <span data-ttu-id="4fe85-160">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4fe85-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="4fe85-161">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="4fe85-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="4fe85-162">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="4fe85-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="4fe85-163">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="4fe85-163">Increase creativity and innovation</span></span> | <span data-ttu-id="4fe85-164">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4fe85-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="4fe85-165">安全性</span><span class="sxs-lookup"><span data-stu-id="4fe85-165">Security</span></span> |  |  |
|  | <span data-ttu-id="4fe85-166">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="4fe85-166">Identity & access management</span></span> | <span data-ttu-id="4fe85-167">专用全局管理员帐户使用 Azure 多重身份验证 (MFA) 和 Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="4fe85-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="4fe85-168">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="4fe85-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="4fe85-169">条件访问</span><span class="sxs-lookup"><span data-stu-id="4fe85-169">Conditional access</span></span> <BR> <span data-ttu-id="4fe85-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="4fe85-170">Windows Hello</span></span> <BR> <span data-ttu-id="4fe85-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="4fe85-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="4fe85-172">威胁防护</span><span class="sxs-lookup"><span data-stu-id="4fe85-172">Threat protection</span></span> | <span data-ttu-id="4fe85-173">高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="4fe85-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="4fe85-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="4fe85-174">Windows Defender</span></span> <BR> <span data-ttu-id="4fe85-175">高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="4fe85-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="4fe85-176">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="4fe85-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="4fe85-177">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="4fe85-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="4fe85-178">信息保护</span><span class="sxs-lookup"><span data-stu-id="4fe85-178">Information protection</span></span> | <span data-ttu-id="4fe85-179">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="4fe85-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="4fe85-180">Office 365 数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="4fe85-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="4fe85-181">Windows 信息保护 (WIP)</span><span class="sxs-lookup"><span data-stu-id="4fe85-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="4fe85-182">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="4fe85-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="4fe85-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4fe85-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="4fe85-184">安全管理</span><span class="sxs-lookup"><span data-stu-id="4fe85-184">Security management</span></span> | <span data-ttu-id="4fe85-185">Azure 安全中心</span><span class="sxs-lookup"><span data-stu-id="4fe85-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="4fe85-186">Windows Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="4fe85-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="4fe85-187">远程和移动访问及业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="4fe85-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="4fe85-188">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="4fe85-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="4fe85-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4fe85-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="4fe85-190">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="4fe85-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="4fe85-191">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="4fe85-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="4fe85-192">为 B2B 交易提供更好的连接并减少开销</span><span class="sxs-lookup"><span data-stu-id="4fe85-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="4fe85-193">联合身份验证和基于云的资源</span><span class="sxs-lookup"><span data-stu-id="4fe85-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="4fe85-194">合规性</span><span class="sxs-lookup"><span data-stu-id="4fe85-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="4fe85-195">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="4fe85-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="4fe85-196">Office 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="4fe85-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="4fe85-197">管理</span><span class="sxs-lookup"><span data-stu-id="4fe85-197">Management</span></span> |  |  |
|  | <span data-ttu-id="4fe85-198">减少安装客户端更新的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="4fe85-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="4fe85-199">部署圈</span><span class="sxs-lookup"><span data-stu-id="4fe85-199">Deployment rings</span></span> <BR> <span data-ttu-id="4fe85-200">Windows 10 企业版更新</span><span class="sxs-lookup"><span data-stu-id="4fe85-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="4fe85-201">Office 365 专业增强版更新</span><span class="sxs-lookup"><span data-stu-id="4fe85-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="4fe85-202">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4fe85-202">Next step</span></span>

<span data-ttu-id="4fe85-203">[了解](contoso-networking.md) Contoso Corporation 本地网络，以及它是如何进行优化，以访问或延迟访问 Microsoft 365 基于云的资源。</span><span class="sxs-lookup"><span data-stu-id="4fe85-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fe85-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fe85-204">See also</span></span>

[<span data-ttu-id="4fe85-205">部署指南</span><span class="sxs-lookup"><span data-stu-id="4fe85-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4fe85-206">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="4fe85-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
