---
title: Contoso IT 基础结构和业务需求
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 本地 IT 基础结构的基本结构，以及 Microsoft 365 for 企业如何满足公司的业务需求。
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637171"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="a39d2-103">Contoso IT 基础结构和业务需求</span><span class="sxs-lookup"><span data-stu-id="a39d2-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="a39d2-104">Contoso 正在从本地集中式 IT 基础结构转换到包含基于云的个人工作负载和应用程序的与云包含的安装程序。</span><span class="sxs-lookup"><span data-stu-id="a39d2-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="a39d2-105">现有 Contoso IT 基础结构</span><span class="sxs-lookup"><span data-stu-id="a39d2-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="a39d2-106">Contoso 通过将应用程序数据中心置于巴黎总部，来使用最集中的本地 IT 基础结构。</span><span class="sxs-lookup"><span data-stu-id="a39d2-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="a39d2-107">图1显示了具有应用程序数据中心、DMZ 和 internet 的总部办公室。</span><span class="sxs-lookup"><span data-stu-id="a39d2-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![现有 Contoso IT 基础结构](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="a39d2-109">**图1：现有 Contoso IT 基础结构**</span><span class="sxs-lookup"><span data-stu-id="a39d2-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="a39d2-110">本地应用程序数据中心主机：</span><span class="sxs-lookup"><span data-stu-id="a39d2-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="a39d2-111">使用 SQL Server 和其他 Linux 数据库的自定义业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="a39d2-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="a39d2-112">一组旧版 SharePoint server。</span><span class="sxs-lookup"><span data-stu-id="a39d2-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="a39d2-113">用于文件存储的组织级和工作组级服务器。</span><span class="sxs-lookup"><span data-stu-id="a39d2-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="a39d2-114">此外，每个区域中心办事处都支持一组服务器和一组类似的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a39d2-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="a39d2-115">这些服务器受区域 IT 部门的控制。</span><span class="sxs-lookup"><span data-stu-id="a39d2-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="a39d2-116">这些独立的多地理数据中心的应用程序和数据上的可搜索性仍然是一个挑战。</span><span class="sxs-lookup"><span data-stu-id="a39d2-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="a39d2-117">在 Contoso 总部 DMZ 中，不同的服务器集提供了：</span><span class="sxs-lookup"><span data-stu-id="a39d2-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="a39d2-118">Contoso 公共网站的托管，客户可以在其中订购产品、部件、用品和服务。</span><span class="sxs-lookup"><span data-stu-id="a39d2-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="a39d2-119">对 Contoso 合作伙伴 Extranet 的托管，用于合作伙伴的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="a39d2-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="a39d2-120">巴黎总部的工作人员对 Contoso Intranet 和 Web 代理基于虚拟专用网 (VPN) 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="a39d2-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="a39d2-121">Contoso 业务需求</span><span class="sxs-lookup"><span data-stu-id="a39d2-121">Contoso business needs</span></span>

<span data-ttu-id="a39d2-122">Contoso 业务需求分为五个主要类别：</span><span class="sxs-lookup"><span data-stu-id="a39d2-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="a39d2-123">**工作效率**</span><span class="sxs-lookup"><span data-stu-id="a39d2-123">**Productivity**</span></span>

- <span data-ttu-id="a39d2-124">简化协作</span><span class="sxs-lookup"><span data-stu-id="a39d2-124">Make collaboration easier</span></span>

  <span data-ttu-id="a39d2-125">将基于电子邮件和文件共享的协作替换为在线模型，允许对文档进行实时更改、更轻松地进行联机会议和捕获的对话线程。</span><span class="sxs-lookup"><span data-stu-id="a39d2-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="a39d2-126">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="a39d2-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="a39d2-127">由于许多员工在家工作或在现场工作，请将出现瓶颈的 VPN 解决方案替换为对 Contoso 数据和云中的资源的高性能访问。</span><span class="sxs-lookup"><span data-stu-id="a39d2-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="a39d2-128">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="a39d2-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="a39d2-129">利用最新的视觉学习和创意开发方法，包括墨迹书写和 3D 可视化。</span><span class="sxs-lookup"><span data-stu-id="a39d2-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="a39d2-130">**安全性**</span><span class="sxs-lookup"><span data-stu-id="a39d2-130">**Security**</span></span>

- <span data-ttu-id="a39d2-131">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="a39d2-131">Identity and access management</span></span>

  <span data-ttu-id="a39d2-132">强制实施身份验证和其他形式的身份验证，并保护用户和管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="a39d2-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="a39d2-133">威胁防护</span><span class="sxs-lookup"><span data-stu-id="a39d2-133">Threat protection</span></span>

  <span data-ttu-id="a39d2-134">防范外部安全威胁，包括电子邮件和基于操作系统的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="a39d2-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="a39d2-135">信息保护</span><span class="sxs-lookup"><span data-stu-id="a39d2-135">Information protection</span></span>

  <span data-ttu-id="a39d2-136">锁定对高价值数字资产（如客户数据、设计和制造规范以及员工信息）的访问并加密。</span><span class="sxs-lookup"><span data-stu-id="a39d2-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="a39d2-137">安全管理</span><span class="sxs-lookup"><span data-stu-id="a39d2-137">Security management</span></span>

  <span data-ttu-id="a39d2-138">监视安全状况并实时检测和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="a39d2-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="a39d2-139">**远程和移动访问及业务合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="a39d2-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="a39d2-140">提高远程和移动工作人员的安全性</span><span class="sxs-lookup"><span data-stu-id="a39d2-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="a39d2-141">实现会将自己的设备 (BYOD) 和公司拥有的设备管理，以确保安全访问、正确的应用程序行为和公司数据保护。</span><span class="sxs-lookup"><span data-stu-id="a39d2-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="a39d2-142">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="a39d2-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="a39d2-143">通过将通常访问的资源移动到云，降低维护和支持成本，并提高远程访问解决方案的性能。</span><span class="sxs-lookup"><span data-stu-id="a39d2-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="a39d2-144">为企业到 susiness (B2B) 交易提供更好的连接和更低的开销</span><span class="sxs-lookup"><span data-stu-id="a39d2-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="a39d2-145">使用使用联合身份验证的基于云的解决方案替换老化和昂贵的合作伙伴 extranet。</span><span class="sxs-lookup"><span data-stu-id="a39d2-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="a39d2-146">**合规性**</span><span class="sxs-lookup"><span data-stu-id="a39d2-146">**Compliance**</span></span>

- <span data-ttu-id="a39d2-147">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="a39d2-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="a39d2-148">确保遵守针对数据存储、加密、数据隐私和个人数据法规的行业和区域管理法规，如常规数据保护法规 (GDPR) 针对欧洲联合。</span><span class="sxs-lookup"><span data-stu-id="a39d2-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="a39d2-149">**管理**</span><span class="sxs-lookup"><span data-stu-id="a39d2-149">**Management**</span></span>

- <span data-ttu-id="a39d2-150">降低管理客户端电脑和设备上运行的软件的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="a39d2-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="a39d2-151">自动将更新安装到整个组织中的 Windows 操作系统和 Microsoft 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a39d2-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="a39d2-152">将 Contoso 业务需求映射到适用于企业的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a39d2-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="a39d2-153">Contoso IT 部门在部署前确定了以下业务需求映射到 Microsoft 365 E5 功能：</span><span class="sxs-lookup"><span data-stu-id="a39d2-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="a39d2-154">类别</span><span class="sxs-lookup"><span data-stu-id="a39d2-154">Category</span></span> | <span data-ttu-id="a39d2-155">业务需求</span><span class="sxs-lookup"><span data-stu-id="a39d2-155">Business need</span></span> | <span data-ttu-id="a39d2-156">适用于企业产品或功能的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a39d2-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="a39d2-157">工作效率</span><span class="sxs-lookup"><span data-stu-id="a39d2-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="a39d2-158">简化协作</span><span class="sxs-lookup"><span data-stu-id="a39d2-158">Make collaboration easier</span></span> | <span data-ttu-id="a39d2-159">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="a39d2-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="a39d2-160">提高远程和移动工作者的工作效率</span><span class="sxs-lookup"><span data-stu-id="a39d2-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="a39d2-161">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="a39d2-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a39d2-162">提高创造力和革新能力</span><span class="sxs-lookup"><span data-stu-id="a39d2-162">Increase creativity and innovation</span></span> | <span data-ttu-id="a39d2-163">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a39d2-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="a39d2-164">安全性</span><span class="sxs-lookup"><span data-stu-id="a39d2-164">Security</span></span> |  |  |
|  | <span data-ttu-id="a39d2-165">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="a39d2-165">Identity & access management</span></span> | <span data-ttu-id="a39d2-166">专用全局管理员帐户，使用 Azure 多重身份验证 (MFA) 和 Azure Active Directory 特权标识管理 (PIM) </span><span class="sxs-lookup"><span data-stu-id="a39d2-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="a39d2-167">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="a39d2-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="a39d2-168">条件访问</span><span class="sxs-lookup"><span data-stu-id="a39d2-168">Conditional Access</span></span> <BR> <span data-ttu-id="a39d2-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="a39d2-169">Windows Hello</span></span> <BR> <span data-ttu-id="a39d2-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="a39d2-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="a39d2-171">威胁防护</span><span class="sxs-lookup"><span data-stu-id="a39d2-171">Threat protection</span></span> | <span data-ttu-id="a39d2-172">高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="a39d2-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="a39d2-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="a39d2-173">Windows Defender</span></span> <BR> <span data-ttu-id="a39d2-174">高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="a39d2-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a39d2-175">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="a39d2-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a39d2-176">Microsoft 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="a39d2-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="a39d2-177">信息保护</span><span class="sxs-lookup"><span data-stu-id="a39d2-177">Information protection</span></span> | <span data-ttu-id="a39d2-178">Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="a39d2-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="a39d2-179">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a39d2-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="a39d2-180">Windows 信息保护 (WIP)</span><span class="sxs-lookup"><span data-stu-id="a39d2-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="a39d2-181">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="a39d2-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="a39d2-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a39d2-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a39d2-183">安全管理</span><span class="sxs-lookup"><span data-stu-id="a39d2-183">Security management</span></span> | <span data-ttu-id="a39d2-184">Azure 安全中心</span><span class="sxs-lookup"><span data-stu-id="a39d2-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="a39d2-185">Windows Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="a39d2-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="a39d2-186">远程和移动访问及业务合作伙伴</span><span class="sxs-lookup"><span data-stu-id="a39d2-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="a39d2-187">提高远程和移动工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="a39d2-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="a39d2-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a39d2-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a39d2-189">减少员工远程访问基础结构</span><span class="sxs-lookup"><span data-stu-id="a39d2-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="a39d2-190">Microsoft 365 工作负载和基于云的数据</span><span class="sxs-lookup"><span data-stu-id="a39d2-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a39d2-191">提高 B2B 交易的连接能力和更低的开销</span><span class="sxs-lookup"><span data-stu-id="a39d2-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="a39d2-192">联合身份验证和基于云的资源</span><span class="sxs-lookup"><span data-stu-id="a39d2-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="a39d2-193">合规性</span><span class="sxs-lookup"><span data-stu-id="a39d2-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="a39d2-194">遵守区域法规要求</span><span class="sxs-lookup"><span data-stu-id="a39d2-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="a39d2-195">Microsoft 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="a39d2-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="a39d2-196">管理</span><span class="sxs-lookup"><span data-stu-id="a39d2-196">Management</span></span> |  |  |
|  | <span data-ttu-id="a39d2-197">降低安装客户端更新的 IT 开销</span><span class="sxs-lookup"><span data-stu-id="a39d2-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="a39d2-198">部署圈</span><span class="sxs-lookup"><span data-stu-id="a39d2-198">Deployment rings</span></span> <BR> <span data-ttu-id="a39d2-199">Windows 10 企业版更新</span><span class="sxs-lookup"><span data-stu-id="a39d2-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="a39d2-200">Microsoft 365 企业应用版更新</span><span class="sxs-lookup"><span data-stu-id="a39d2-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="a39d2-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a39d2-201">Next step</span></span>

<span data-ttu-id="a39d2-202">[了解](contoso-networking.md) Contoso Corporation 本地网络，以及它是如何针对 Microsoft 365 基于云的资源的访问和延迟进行优化的。</span><span class="sxs-lookup"><span data-stu-id="a39d2-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="a39d2-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a39d2-203">See also</span></span>

[<span data-ttu-id="a39d2-204">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="a39d2-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a39d2-205">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="a39d2-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
