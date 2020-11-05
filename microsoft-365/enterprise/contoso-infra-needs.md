---
title: Contoso IT 基础结构和业务需求
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 本地 IT 基础结构的基本结构，以及 Microsoft 365 for 企业如何满足公司的业务需求。
ms.openlocfilehash: b3b67429faccc5d22d49a2921fff4c8b3c3c062e
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920450"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="ad51d-103">Contoso IT 基础结构和业务需求</span><span class="sxs-lookup"><span data-stu-id="ad51d-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="ad51d-104">Contoso 正在从本地集中式 IT 基础结构转换到包含基于云的个人工作负载和应用程序的与云包含的安装程序。</span><span class="sxs-lookup"><span data-stu-id="ad51d-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="ad51d-105">现有 Contoso IT 基础结构</span><span class="sxs-lookup"><span data-stu-id="ad51d-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="ad51d-106">Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="ad51d-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="ad51d-107">下面是具有应用程序数据中心、DMZ 和 internet 的总部办公室。</span><span class="sxs-lookup"><span data-stu-id="ad51d-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![现有 Contoso IT 基础结构](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="ad51d-109">本地应用程序数据中心主机：</span><span class="sxs-lookup"><span data-stu-id="ad51d-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="ad51d-110">使用 SQL Server 和其他 Linux 数据库的自定义业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="ad51d-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="ad51d-111">一组旧版 SharePoint server。</span><span class="sxs-lookup"><span data-stu-id="ad51d-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="ad51d-112">用于文件存储的组织级和工作组级服务器。</span><span class="sxs-lookup"><span data-stu-id="ad51d-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="ad51d-113">此外，每个区域中心办事处都支持一组服务器和一组类似的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ad51d-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="ad51d-114">这些服务器受区域 IT 部门的控制。</span><span class="sxs-lookup"><span data-stu-id="ad51d-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="ad51d-115">这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="ad51d-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="ad51d-116">在 Contoso 总部 DMZ 中，不同的服务器集提供了：</span><span class="sxs-lookup"><span data-stu-id="ad51d-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="ad51d-117">Contoso 公共网站的托管，客户可以在其中订购产品、部件、用品和服务。</span><span class="sxs-lookup"><span data-stu-id="ad51d-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="ad51d-118">对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="ad51d-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="ad51d-119">巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于虚拟专用网 (VPN) 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="ad51d-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="ad51d-120">Contoso 业务需求</span><span class="sxs-lookup"><span data-stu-id="ad51d-120">Contoso business needs</span></span>

<span data-ttu-id="ad51d-121">Contoso 业务需求分为五个主要类别：</span><span class="sxs-lookup"><span data-stu-id="ad51d-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="ad51d-122">**工作效率**</span><span class="sxs-lookup"><span data-stu-id="ad51d-122">**Productivity**</span></span>

- <span data-ttu-id="ad51d-123">简化协作</span><span class="sxs-lookup"><span data-stu-id="ad51d-123">Make collaboration easier</span></span>

  <span data-ttu-id="ad51d-124">将基于电子邮件和文件共享的协作替换为在线模型，允许对文档进行实时更改、更轻松地进行联机会议和捕获的对话线程。</span><span class="sxs-lookup"><span data-stu-id="ad51d-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="ad51d-125">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="ad51d-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="ad51d-126">由于许多员工在家工作或在现场工作，请将出现瓶颈的 VPN 解决方案替换为对 Contoso 数据和云中的资源的高性能访问。</span><span class="sxs-lookup"><span data-stu-id="ad51d-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="ad51d-127">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="ad51d-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="ad51d-128">利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。</span><span class="sxs-lookup"><span data-stu-id="ad51d-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="ad51d-129">**安全性**</span><span class="sxs-lookup"><span data-stu-id="ad51d-129">**Security**</span></span>

- <span data-ttu-id="ad51d-130">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="ad51d-130">Identity and access management</span></span>

  <span data-ttu-id="ad51d-131">强制实施身份验证和其他形式的身份验证，并保护用户和管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="ad51d-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="ad51d-132">威胁防护</span><span class="sxs-lookup"><span data-stu-id="ad51d-132">Threat protection</span></span>

  <span data-ttu-id="ad51d-133">防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="ad51d-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="ad51d-134">信息保护</span><span class="sxs-lookup"><span data-stu-id="ad51d-134">Information protection</span></span>

  <span data-ttu-id="ad51d-135">锁定对高价值数字资产（如客户数据、设计和制造规范以及员工信息）的访问并加密。</span><span class="sxs-lookup"><span data-stu-id="ad51d-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="ad51d-136">安全管理</span><span class="sxs-lookup"><span data-stu-id="ad51d-136">Security management</span></span>

  <span data-ttu-id="ad51d-137">监视安全状况并实时检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="ad51d-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="ad51d-138">**远程和移动访问及业务合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="ad51d-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="ad51d-139">提高远程和移动工作人员的安全性</span><span class="sxs-lookup"><span data-stu-id="ad51d-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="ad51d-140">实现会将自己的设备 (BYOD) 和公司拥有的设备管理，以确保安全访问、正确的应用程序行为和公司数据保护。</span><span class="sxs-lookup"><span data-stu-id="ad51d-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="ad51d-141">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="ad51d-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="ad51d-142">通过将通常访问的资源移动到云，降低维护和支持成本，并提高远程访问解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="ad51d-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="ad51d-143">为企业到 susiness (B2B) 交易提供更好的连接和更低的开销</span><span class="sxs-lookup"><span data-stu-id="ad51d-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="ad51d-144">使用使用联合身份验证的基于云的解决方案替换老化和昂贵的合作伙伴 extranet。</span><span class="sxs-lookup"><span data-stu-id="ad51d-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="ad51d-145">**合规性**</span><span class="sxs-lookup"><span data-stu-id="ad51d-145">**Compliance**</span></span>

- <span data-ttu-id="ad51d-146">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="ad51d-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="ad51d-147">确保遵守针对数据存储、加密、数据隐私和个人数据法规的行业和区域管理法规，如常规数据保护法规 (GDPR) 针对欧洲联合。</span><span class="sxs-lookup"><span data-stu-id="ad51d-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="ad51d-148">**管理**</span><span class="sxs-lookup"><span data-stu-id="ad51d-148">**Management**</span></span>

- <span data-ttu-id="ad51d-149">降低管理客户端电脑和设备上运行的软件的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="ad51d-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="ad51d-150">自动将更新安装到整个组织中的 Windows 操作系统和 Microsoft 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ad51d-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="ad51d-151">将 Contoso 业务需求映射到适用于企业的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad51d-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="ad51d-152">Contoso IT 部门在部署前确定了以下业务需求映射到 Microsoft 365 E5 功能：</span><span class="sxs-lookup"><span data-stu-id="ad51d-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="ad51d-153">类别</span><span class="sxs-lookup"><span data-stu-id="ad51d-153">Category</span></span> | <span data-ttu-id="ad51d-154">业务需求</span><span class="sxs-lookup"><span data-stu-id="ad51d-154">Business need</span></span> | <span data-ttu-id="ad51d-155">适用于企业产品或功能的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad51d-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="ad51d-156">工作效率</span><span class="sxs-lookup"><span data-stu-id="ad51d-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="ad51d-157">简化协作</span><span class="sxs-lookup"><span data-stu-id="ad51d-157">Make collaboration easier</span></span> | <span data-ttu-id="ad51d-158">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="ad51d-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="ad51d-159">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="ad51d-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="ad51d-160">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="ad51d-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ad51d-161">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="ad51d-161">Increase creativity and innovation</span></span> | <span data-ttu-id="ad51d-162">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ad51d-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="ad51d-163">安全性</span><span class="sxs-lookup"><span data-stu-id="ad51d-163">Security</span></span> |  |  |
|  | <span data-ttu-id="ad51d-164">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="ad51d-164">Identity & access management</span></span> | <span data-ttu-id="ad51d-165">专用全局管理员帐户使用 Azure 多重身份验证 (MFA) 和 Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="ad51d-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="ad51d-166">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="ad51d-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="ad51d-167">条件访问</span><span class="sxs-lookup"><span data-stu-id="ad51d-167">Conditional Access</span></span> <BR> <span data-ttu-id="ad51d-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="ad51d-168">Windows Hello</span></span> <BR> <span data-ttu-id="ad51d-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="ad51d-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="ad51d-170">威胁防护</span><span class="sxs-lookup"><span data-stu-id="ad51d-170">Threat protection</span></span> | <span data-ttu-id="ad51d-171">高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="ad51d-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="ad51d-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ad51d-172">Windows Defender</span></span> <BR> <span data-ttu-id="ad51d-173">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ad51d-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="ad51d-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ad51d-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="ad51d-175">Microsoft 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="ad51d-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="ad51d-176">信息保护</span><span class="sxs-lookup"><span data-stu-id="ad51d-176">Information protection</span></span> | <span data-ttu-id="ad51d-177">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="ad51d-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="ad51d-178">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ad51d-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="ad51d-179">Windows 信息保护 (WIP)</span><span class="sxs-lookup"><span data-stu-id="ad51d-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="ad51d-180">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="ad51d-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="ad51d-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ad51d-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ad51d-182">安全管理</span><span class="sxs-lookup"><span data-stu-id="ad51d-182">Security management</span></span> | <span data-ttu-id="ad51d-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="ad51d-183">Azure Defender</span></span>  <BR> <span data-ttu-id="ad51d-184">Windows Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="ad51d-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="ad51d-185">远程和移动访问及业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ad51d-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="ad51d-186">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="ad51d-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="ad51d-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ad51d-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="ad51d-188">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="ad51d-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="ad51d-189">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="ad51d-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="ad51d-190">提高 B2B 交易的连接能力和更低的开销</span><span class="sxs-lookup"><span data-stu-id="ad51d-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="ad51d-191">联合身份验证和基于云的资源</span><span class="sxs-lookup"><span data-stu-id="ad51d-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="ad51d-192">合规性</span><span class="sxs-lookup"><span data-stu-id="ad51d-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="ad51d-193">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="ad51d-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="ad51d-194">Microsoft 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="ad51d-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="ad51d-195">管理</span><span class="sxs-lookup"><span data-stu-id="ad51d-195">Management</span></span> |  |  |
|  | <span data-ttu-id="ad51d-196">降低安装客户端更新的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="ad51d-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="ad51d-197">Windows 10 企业版更新</span><span class="sxs-lookup"><span data-stu-id="ad51d-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="ad51d-198">Microsoft 365 企业应用版更新</span><span class="sxs-lookup"><span data-stu-id="ad51d-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="ad51d-199">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ad51d-199">Next step</span></span>

<span data-ttu-id="ad51d-200">了解 Contoso Corporation [本地网络](contoso-networking.md) ，以及它是如何针对 Microsoft 365 基于云的资源的访问和延迟进行优化的。</span><span class="sxs-lookup"><span data-stu-id="ad51d-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad51d-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad51d-201">See also</span></span>

[<span data-ttu-id="ad51d-202">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="ad51d-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ad51d-203">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="ad51d-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
