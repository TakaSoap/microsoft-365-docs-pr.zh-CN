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
description: 了解 Contoso 本地 IT 基础结构的基本结构，以及企业内部部署基础结构如何满足Microsoft 365业务需求。
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558402"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="1d62c-103">Contoso IT 基础结构和业务需求</span><span class="sxs-lookup"><span data-stu-id="1d62c-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="1d62c-104">Contoso 正在从本地集中式 IT 基础结构过渡到包含云的安装程序，该设置包含基于云的个人工作效率工作负载和应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d62c-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="1d62c-105">现有 Contoso IT 基础结构</span><span class="sxs-lookup"><span data-stu-id="1d62c-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="1d62c-106">Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="1d62c-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="1d62c-107">下面是总部办事处，具有应用程序数据中心、DMZ 和 Internet。</span><span class="sxs-lookup"><span data-stu-id="1d62c-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![现有 Contoso IT 基础结构](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="1d62c-109">本地应用程序数据中心主机：</span><span class="sxs-lookup"><span data-stu-id="1d62c-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="1d62c-110">使用数据库和其他 Linux 数据库SQL Server业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d62c-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="1d62c-111">一组旧版 SharePoint server。</span><span class="sxs-lookup"><span data-stu-id="1d62c-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="1d62c-112">用于文件存储的组织级和工作组级服务器。</span><span class="sxs-lookup"><span data-stu-id="1d62c-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="1d62c-113">此外，每个区域中心办事处都支持一组服务器和一组类似的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d62c-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="1d62c-114">这些服务器受区域 IT 部门的控制。</span><span class="sxs-lookup"><span data-stu-id="1d62c-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="1d62c-115">这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="1d62c-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="1d62c-116">在 Contoso 总部 DMZ 中，不同的服务器集提供：</span><span class="sxs-lookup"><span data-stu-id="1d62c-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="1d62c-117">托管 Contoso 公共网站，客户可以从该网站订购产品、部件、供应品和服务。</span><span class="sxs-lookup"><span data-stu-id="1d62c-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="1d62c-118">对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="1d62c-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="1d62c-119">巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于虚拟专用网 (VPN) 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="1d62c-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="1d62c-120">Contoso 业务需求</span><span class="sxs-lookup"><span data-stu-id="1d62c-120">Contoso business needs</span></span>

<span data-ttu-id="1d62c-121">Contoso 业务需求分为五个主要类别：</span><span class="sxs-lookup"><span data-stu-id="1d62c-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="1d62c-122">**工作效率**</span><span class="sxs-lookup"><span data-stu-id="1d62c-122">**Productivity**</span></span>

- <span data-ttu-id="1d62c-123">简化协作</span><span class="sxs-lookup"><span data-stu-id="1d62c-123">Make collaboration easier</span></span>

  <span data-ttu-id="1d62c-124">将基于电子邮件和文件共享的协作替换为允许实时更改文档、简化联机会议和捕获的对话线程的联机模型。</span><span class="sxs-lookup"><span data-stu-id="1d62c-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="1d62c-125">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="1d62c-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="1d62c-126">由于许多员工在家工作或现场工作，因此请将瓶颈的 VPN 解决方案替换为对云中 Contoso 数据和资源的性能访问。</span><span class="sxs-lookup"><span data-stu-id="1d62c-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="1d62c-127">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="1d62c-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="1d62c-128">利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。</span><span class="sxs-lookup"><span data-stu-id="1d62c-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="1d62c-129">**安全性**</span><span class="sxs-lookup"><span data-stu-id="1d62c-129">**Security**</span></span>

- <span data-ttu-id="1d62c-130">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="1d62c-130">Identity and access management</span></span>

  <span data-ttu-id="1d62c-131">强制执行多重身份验证和其他形式的身份验证，并保护用户和管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="1d62c-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="1d62c-132">威胁防护</span><span class="sxs-lookup"><span data-stu-id="1d62c-132">Threat protection</span></span>

  <span data-ttu-id="1d62c-133">防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="1d62c-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="1d62c-134">信息保护</span><span class="sxs-lookup"><span data-stu-id="1d62c-134">Information protection</span></span>

  <span data-ttu-id="1d62c-135">锁定对高价值数字资产（如客户数据、设计和制造规范以及员工信息）的访问并加密。</span><span class="sxs-lookup"><span data-stu-id="1d62c-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="1d62c-136">安全管理</span><span class="sxs-lookup"><span data-stu-id="1d62c-136">Security management</span></span>

  <span data-ttu-id="1d62c-137">监视安全状况，并实时检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="1d62c-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="1d62c-138">**远程和移动访问及业务合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="1d62c-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="1d62c-139">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="1d62c-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="1d62c-140">实施自带设备 (BYOD) 和公司拥有的设备管理，以确保安全访问、正确的应用程序行为和公司数据保护。</span><span class="sxs-lookup"><span data-stu-id="1d62c-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="1d62c-141">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="1d62c-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="1d62c-142">通过将经常访问的资源移动到云中，减少维护和支持成本并提高远程访问解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="1d62c-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="1d62c-143">为 B2B 业务和 B2B (提供更好的连接并降低) 开销</span><span class="sxs-lookup"><span data-stu-id="1d62c-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="1d62c-144">使用使用联合身份验证的基于云的解决方案替换旧合作伙伴 Extranet 和昂贵的合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="1d62c-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="1d62c-145">**合规性**</span><span class="sxs-lookup"><span data-stu-id="1d62c-145">**Compliance**</span></span>

- <span data-ttu-id="1d62c-146">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="1d62c-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="1d62c-147">确保遵守有关数据存储、加密、数据隐私和个人数据法规的行业和区域法规，如欧盟一般数据保护条例 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="1d62c-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="1d62c-148">**管理**</span><span class="sxs-lookup"><span data-stu-id="1d62c-148">**Management**</span></span>

- <span data-ttu-id="1d62c-149">减少在客户端电脑和设备上运行的管理软件的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="1d62c-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="1d62c-150">自动安装整个组织中Windows操作系统Microsoft 365 企业应用版更新。</span><span class="sxs-lookup"><span data-stu-id="1d62c-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="1d62c-151">映射 Contoso 业务需求以Microsoft 365企业版</span><span class="sxs-lookup"><span data-stu-id="1d62c-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="1d62c-152">Contoso IT 部门在部署之前确定了以下Microsoft 365 E5功能所需的映射：</span><span class="sxs-lookup"><span data-stu-id="1d62c-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="1d62c-153">类别</span><span class="sxs-lookup"><span data-stu-id="1d62c-153">Category</span></span> | <span data-ttu-id="1d62c-154">业务需求</span><span class="sxs-lookup"><span data-stu-id="1d62c-154">Business need</span></span> | <span data-ttu-id="1d62c-155">Microsoft 365企业产品或功能</span><span class="sxs-lookup"><span data-stu-id="1d62c-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="1d62c-156">工作效率</span><span class="sxs-lookup"><span data-stu-id="1d62c-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="1d62c-157">简化协作</span><span class="sxs-lookup"><span data-stu-id="1d62c-157">Make collaboration easier</span></span> | <span data-ttu-id="1d62c-158">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="1d62c-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="1d62c-159">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="1d62c-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="1d62c-160">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="1d62c-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="1d62c-161">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="1d62c-161">Increase creativity and innovation</span></span> | <span data-ttu-id="1d62c-162">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1d62c-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="1d62c-163">安全性</span><span class="sxs-lookup"><span data-stu-id="1d62c-163">Security</span></span> |  |  |
|  | <span data-ttu-id="1d62c-164">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="1d62c-164">Identity & access management</span></span> | <span data-ttu-id="1d62c-165">使用 Azure AD 多重身份验证的专用全局管理员帐户 (MFA) Azure AD Privileged Identity Management (PIM) </span><span class="sxs-lookup"><span data-stu-id="1d62c-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="1d62c-166">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="1d62c-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="1d62c-167">条件访问</span><span class="sxs-lookup"><span data-stu-id="1d62c-167">Conditional Access</span></span> <BR> <span data-ttu-id="1d62c-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="1d62c-168">Windows Hello</span></span> <BR> <span data-ttu-id="1d62c-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="1d62c-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="1d62c-170">威胁防护</span><span class="sxs-lookup"><span data-stu-id="1d62c-170">Threat protection</span></span> | <span data-ttu-id="1d62c-171">高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="1d62c-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="1d62c-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1d62c-172">Windows Defender</span></span> <BR> <span data-ttu-id="1d62c-173">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1d62c-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="1d62c-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1d62c-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="1d62c-175">Microsoft 365威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="1d62c-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="1d62c-176">信息保护</span><span class="sxs-lookup"><span data-stu-id="1d62c-176">Information protection</span></span> | <span data-ttu-id="1d62c-177">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="1d62c-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="1d62c-178">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="1d62c-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="1d62c-179">Windows 信息保护 (WIP)</span><span class="sxs-lookup"><span data-stu-id="1d62c-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="1d62c-180">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="1d62c-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="1d62c-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1d62c-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="1d62c-182">安全管理</span><span class="sxs-lookup"><span data-stu-id="1d62c-182">Security management</span></span> | <span data-ttu-id="1d62c-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="1d62c-183">Azure Defender</span></span>  <BR> <span data-ttu-id="1d62c-184">Windows Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="1d62c-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="1d62c-185">远程和移动访问及业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="1d62c-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="1d62c-186">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="1d62c-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="1d62c-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1d62c-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="1d62c-188">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="1d62c-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="1d62c-189">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="1d62c-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="1d62c-190">改进连接并降低 B2B 事务的开销</span><span class="sxs-lookup"><span data-stu-id="1d62c-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="1d62c-191">联合身份验证和基于云的资源</span><span class="sxs-lookup"><span data-stu-id="1d62c-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="1d62c-192">合规性</span><span class="sxs-lookup"><span data-stu-id="1d62c-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="1d62c-193">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="1d62c-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="1d62c-194">GDPR 功能在Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d62c-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="1d62c-195">管理</span><span class="sxs-lookup"><span data-stu-id="1d62c-195">Management</span></span> |  |  |
|  | <span data-ttu-id="1d62c-196">减少安装客户端更新的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="1d62c-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="1d62c-197">Windows 10 企业版更新</span><span class="sxs-lookup"><span data-stu-id="1d62c-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="1d62c-198">Microsoft 365 企业应用版更新</span><span class="sxs-lookup"><span data-stu-id="1d62c-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="1d62c-199">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d62c-199">Next step</span></span>

<span data-ttu-id="1d62c-200">了解 Contoso [Corporation](contoso-networking.md)本地网络，以及如何针对访问和延迟优化网络以Microsoft 365基于云的资源。</span><span class="sxs-lookup"><span data-stu-id="1d62c-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d62c-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d62c-201">See also</span></span>

[<span data-ttu-id="1d62c-202">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="1d62c-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1d62c-203">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="1d62c-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
