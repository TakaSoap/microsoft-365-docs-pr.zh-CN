---
title: Contoso 的 IT 基础结构和业务需求
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3cee0f3e6cd20b0d93038595cdab9270c8eb30aa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068380"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="f5b23-103">Contoso 的 IT 基础结构和业务需求</span><span class="sxs-lookup"><span data-stu-id="f5b23-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="f5b23-104">Contoso 正在从本地集中式 IT 基础结构转换到一个合并了基于云的个人生产率工作负载和应用程序的包含云的 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="f5b23-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="f5b23-105">Contoso 的现有 IT 基础结构</span><span class="sxs-lookup"><span data-stu-id="f5b23-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="f5b23-106">Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="f5b23-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="f5b23-107">图 1 显示总部办事处及应用程序数据中心、DMZ 和 Internet。</span><span class="sxs-lookup"><span data-stu-id="f5b23-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contoso 的现有 IT 基础结构](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="f5b23-109">**图 1 Contoso 的现有 IT 基础结构**</span><span class="sxs-lookup"><span data-stu-id="f5b23-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="f5b23-110">本地应用程序数据中心主机：</span><span class="sxs-lookup"><span data-stu-id="f5b23-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="f5b23-111">使用 SQL Server 和其他 Linux 数据库的自定义业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="f5b23-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="f5b23-112">一组旧版 SharePoint server。</span><span class="sxs-lookup"><span data-stu-id="f5b23-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="f5b23-113">用于文件存储的组织级和工作组级服务器。</span><span class="sxs-lookup"><span data-stu-id="f5b23-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="f5b23-114">此外，每个区域中心办事处都支持一组服务器和一组类似的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f5b23-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="f5b23-115">这些服务器受区域 IT 部门的控制。</span><span class="sxs-lookup"><span data-stu-id="f5b23-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="f5b23-116">这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="f5b23-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="f5b23-117">在 Contoso 总部 DMZ 中，不同的服务器集提供不同的功能：</span><span class="sxs-lookup"><span data-stu-id="f5b23-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="f5b23-118">对 Contoso 公共网站的托管，客户可以在其中订购产品、部件、配件或服务。</span><span class="sxs-lookup"><span data-stu-id="f5b23-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="f5b23-119">对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="f5b23-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="f5b23-120">巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于虚拟专用网 (VPN) 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="f5b23-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="f5b23-121">Contoso 的业务需求</span><span class="sxs-lookup"><span data-stu-id="f5b23-121">Contoso's business needs</span></span>

<span data-ttu-id="f5b23-122">Contoso 的业务需求分为五个主要类别。</span><span class="sxs-lookup"><span data-stu-id="f5b23-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="f5b23-123">工作效率：</span><span class="sxs-lookup"><span data-stu-id="f5b23-123">Productivity:</span></span>

- <span data-ttu-id="f5b23-124">简化协作</span><span class="sxs-lookup"><span data-stu-id="f5b23-124">Make collaboration easier</span></span>

  <span data-ttu-id="f5b23-125">将电子邮件和基于文件共享的协作替换为在线模型，以允许对文档进行实时更改、简化在线会议并捕获会话线程。</span><span class="sxs-lookup"><span data-stu-id="f5b23-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="f5b23-126">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="f5b23-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="f5b23-127">由于许多员工在家办公或在办公点工作，将出现瓶颈的 VPN 解决方案替换为对 Contoso 数据和云资源的高性能访问。</span><span class="sxs-lookup"><span data-stu-id="f5b23-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="f5b23-128">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="f5b23-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="f5b23-129">利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。</span><span class="sxs-lookup"><span data-stu-id="f5b23-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="f5b23-130">安全性：</span><span class="sxs-lookup"><span data-stu-id="f5b23-130">Security:</span></span>

- <span data-ttu-id="f5b23-131">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="f5b23-131">Identity and access management</span></span>

  <span data-ttu-id="f5b23-132">强制实施多重身份验证和其他形式的身份验证并保护用户和管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="f5b23-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="f5b23-133">威胁防护</span><span class="sxs-lookup"><span data-stu-id="f5b23-133">Threat protection</span></span>

  <span data-ttu-id="f5b23-134">防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="f5b23-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="f5b23-135">信息保护</span><span class="sxs-lookup"><span data-stu-id="f5b23-135">Information protection</span></span>

  <span data-ttu-id="f5b23-136">锁定对高价值数字资产（如客户数据、设计和制造规范以及员工信息）的访问并加密。</span><span class="sxs-lookup"><span data-stu-id="f5b23-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="f5b23-137">安全管理</span><span class="sxs-lookup"><span data-stu-id="f5b23-137">Security management</span></span>

  <span data-ttu-id="f5b23-138">监视安全状态并且能够实时检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="f5b23-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="f5b23-139">远程和移动访问及业务合作伙伴：</span><span class="sxs-lookup"><span data-stu-id="f5b23-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="f5b23-140">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="f5b23-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="f5b23-141">制定自带设备 (BYOD) 和公司拥有的设备管理以确保安全访问、正确的应用程序行为和公司数据保护。</span><span class="sxs-lookup"><span data-stu-id="f5b23-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="f5b23-142">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="f5b23-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="f5b23-143">通过将通常访问的资源移动到云来减少维护和支持成本，并提高远程访问解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="f5b23-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="f5b23-144">为企业对企业 (B2B) 交易提供更好的连接并减少开销</span><span class="sxs-lookup"><span data-stu-id="f5b23-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="f5b23-145">将不断老化且费用高昂的合作伙伴Extranet 替换为使用联合身份验证的基于云的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f5b23-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="f5b23-146">合规性：</span><span class="sxs-lookup"><span data-stu-id="f5b23-146">Compliance:</span></span>

- <span data-ttu-id="f5b23-147">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="f5b23-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="f5b23-148">遵守并始终遵守针对数据存储、加密、数据隐私和个人数据的行业和区域法规，如欧盟一般数据保护条例 (GDPR)。</span><span class="sxs-lookup"><span data-stu-id="f5b23-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="f5b23-149">管理：</span><span class="sxs-lookup"><span data-stu-id="f5b23-149">Management:</span></span>

- <span data-ttu-id="f5b23-150">减少管理客户端电脑和设备上运行的软件的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="f5b23-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="f5b23-151">在组织中自动安装 Windows 操作系统和 Microsoft Office 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="f5b23-151">Automate the installation of updates to the Windows operating system and Microsoft Office ProPlus across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="f5b23-152">将 Contoso 业务需求映射到 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="f5b23-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f5b23-153">Contoso 的 IT 部门会在部署之前，确定以下映射到 Microsoft 365 E5 功能的业务需求：</span><span class="sxs-lookup"><span data-stu-id="f5b23-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="f5b23-154">**类别**</span><span class="sxs-lookup"><span data-stu-id="f5b23-154">**Category**</span></span> | <span data-ttu-id="f5b23-155">**业务需要**</span><span class="sxs-lookup"><span data-stu-id="f5b23-155">**Business need**</span></span> | <span data-ttu-id="f5b23-156">**Microsoft 365 企业版的产品或功能**</span><span class="sxs-lookup"><span data-stu-id="f5b23-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="f5b23-157">工作效率</span><span class="sxs-lookup"><span data-stu-id="f5b23-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="f5b23-158">简化协作</span><span class="sxs-lookup"><span data-stu-id="f5b23-158">Make collaboration easier</span></span> | <span data-ttu-id="f5b23-159">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="f5b23-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="f5b23-160">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="f5b23-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="f5b23-161">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="f5b23-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="f5b23-162">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="f5b23-162">Increase creativity and innovation</span></span> | <span data-ttu-id="f5b23-163">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f5b23-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="f5b23-164">安全性</span><span class="sxs-lookup"><span data-stu-id="f5b23-164">Security</span></span> |  |  |
|  | <span data-ttu-id="f5b23-165">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="f5b23-165">Identity & access management</span></span> | <span data-ttu-id="f5b23-166">专用全局管理员帐户使用 Azure 多重身份验证 (MFA) 和 Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="f5b23-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="f5b23-167">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="f5b23-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="f5b23-168">条件访问</span><span class="sxs-lookup"><span data-stu-id="f5b23-168">Conditional Access</span></span> <BR> <span data-ttu-id="f5b23-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="f5b23-169">Windows Hello</span></span> <BR> <span data-ttu-id="f5b23-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="f5b23-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="f5b23-171">威胁防护</span><span class="sxs-lookup"><span data-stu-id="f5b23-171">Threat protection</span></span> | <span data-ttu-id="f5b23-172">高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="f5b23-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="f5b23-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="f5b23-173">Windows Defender</span></span> <BR> <span data-ttu-id="f5b23-174">高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f5b23-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="f5b23-175">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f5b23-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="f5b23-176">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="f5b23-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="f5b23-177">信息保护</span><span class="sxs-lookup"><span data-stu-id="f5b23-177">Information protection</span></span> | <span data-ttu-id="f5b23-178">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="f5b23-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="f5b23-179">Office 365 数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="f5b23-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="f5b23-180">Windows 信息保护 (WIP)</span><span class="sxs-lookup"><span data-stu-id="f5b23-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="f5b23-181">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="f5b23-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="f5b23-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f5b23-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="f5b23-183">安全管理</span><span class="sxs-lookup"><span data-stu-id="f5b23-183">Security management</span></span> | <span data-ttu-id="f5b23-184">Azure 安全中心</span><span class="sxs-lookup"><span data-stu-id="f5b23-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="f5b23-185">Windows Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="f5b23-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="f5b23-186">远程和移动访问及业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="f5b23-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="f5b23-187">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="f5b23-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="f5b23-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f5b23-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="f5b23-189">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="f5b23-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="f5b23-190">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="f5b23-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="f5b23-191">为 B2B 交易提供更好的连接并减少开销</span><span class="sxs-lookup"><span data-stu-id="f5b23-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="f5b23-192">联合身份验证和基于云的资源</span><span class="sxs-lookup"><span data-stu-id="f5b23-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="f5b23-193">合规性</span><span class="sxs-lookup"><span data-stu-id="f5b23-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="f5b23-194">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="f5b23-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="f5b23-195">Office 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="f5b23-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="f5b23-196">管理</span><span class="sxs-lookup"><span data-stu-id="f5b23-196">Management</span></span> |  |  |
|  | <span data-ttu-id="f5b23-197">减少安装客户端更新的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="f5b23-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="f5b23-198">部署圈</span><span class="sxs-lookup"><span data-stu-id="f5b23-198">Deployment rings</span></span> <BR> <span data-ttu-id="f5b23-199">Windows 10 企业版更新</span><span class="sxs-lookup"><span data-stu-id="f5b23-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="f5b23-200">Office 365 专业增强版更新</span><span class="sxs-lookup"><span data-stu-id="f5b23-200">Office 365 ProPlus updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="f5b23-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f5b23-201">Next step</span></span>

<span data-ttu-id="f5b23-202">[了解](contoso-networking.md) Contoso Corporation 本地网络，以及它是如何进行优化，以访问或延迟访问 Microsoft 365 基于云的资源。</span><span class="sxs-lookup"><span data-stu-id="f5b23-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5b23-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b23-203">See also</span></span>

[<span data-ttu-id="f5b23-204">部署指南</span><span class="sxs-lookup"><span data-stu-id="f5b23-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f5b23-205">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f5b23-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
