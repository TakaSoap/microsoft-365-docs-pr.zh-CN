---
title: Office 365 中的 office 365 威胁调查和响应功能高级威胁防护计划2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: 了解 Office 365 中的威胁智能功能。高级威胁防护可帮助您研究组织的威胁、响应恶意软件、网络钓鱼和 Office 365 已代表您检测到的其他攻击，并搜索威胁指示器.
ms.openlocfilehash: 2f95054d35edee7db419bc665b520b2b48dda447
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598749"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="aa0fd-103">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="aa0fd-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="aa0fd-104">Office 365 中的威胁调查和响应功能[高级威胁防护](office-365-atp.md)帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
- <span data-ttu-id="aa0fd-105">轻松识别、监控和理解 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="aa0fd-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="aa0fd-106">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 团队中的威胁</span><span class="sxs-lookup"><span data-stu-id="aa0fd-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="aa0fd-107">提供有关帮助安全操作的见解和知识，以防止针对组织的 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="aa0fd-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="aa0fd-108">[在 Office 365 中采用自动调查和响应](automated-investigation-response-office.md)，以实现基于电子邮件的关键威胁</span><span class="sxs-lookup"><span data-stu-id="aa0fd-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>
    
<span data-ttu-id="aa0fd-109">威胁调查和响应功能提供了对 Office 365 安全&amp;合规中心中提供的威胁和相关响应操作的见解。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="aa0fd-110">这些见解可帮助您的组织的安全团队保护 Office 365 用户免受电子邮件或基于文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-110">These insights can help your organization's security team protect Office 365 users from email- or file-based attacks.</span></span> <span data-ttu-id="aa0fd-111">这些功能可帮助监视信号并收集来自多个源（如用户活动、身份验证、电子邮件、受损电脑和安全事件）的数据。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="aa0fd-112">业务决策者和安全操作团队可以使用此信息来了解和响应针对组织的威胁，并保护您的知识产权。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="aa0fd-113">了解威胁调查和响应工具</span><span class="sxs-lookup"><span data-stu-id="aa0fd-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="aa0fd-114">安全&amp;合规中心中的威胁调查和响应功能，作为一组工具和响应工作流，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-114">Threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the following:</span></span>
- [<span data-ttu-id="aa0fd-115">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="aa0fd-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="aa0fd-116">Explorer</span><span class="sxs-lookup"><span data-stu-id="aa0fd-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="aa0fd-117">事件</span><span class="sxs-lookup"><span data-stu-id="aa0fd-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="aa0fd-118">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="aa0fd-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="aa0fd-119">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="aa0fd-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="aa0fd-120">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="aa0fd-120">Threat dashboard</span></span>

<span data-ttu-id="aa0fd-121">使用 "威胁" 仪表板（也称为 "安全"[仪表板](security-dashboard.md)）快速查看已解决的威胁，并以直观方式向业务决策者报告 Office 365 服务如何保护您的业务。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威胁仪表板](../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="aa0fd-123">若要查看和使用此仪表板，请在 Office &amp; 365 安全合规中心中，转到 "**威胁管理** \> "**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-123">To view and use this dashboard, in the Office 365 Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="aa0fd-124">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="aa0fd-124">Threat Explorer</span></span>

<span data-ttu-id="aa0fd-125">使用[威胁浏览器（和实时检测）](threat-explorer.md)来分析威胁，查看一段时间内的攻击量，并根据威胁系列、攻击者基础结构等对数据进行分析。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="aa0fd-126">威胁资源管理器（也称为浏览器）是任何安全分析员的调查工作流的起始位置。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![威胁资源管理器](../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="aa0fd-128">若要查看和使用此报告，请在 Office 365 &amp;安全合规性中心中，转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-128">To view and use this report, in the Office 365 Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="aa0fd-129">事件</span><span class="sxs-lookup"><span data-stu-id="aa0fd-129">Incidents</span></span>

<span data-ttu-id="aa0fd-130">使用 "事件" 列表（也称为 "调查"）查看飞行安全事件的列表。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="aa0fd-131">事件用于跟踪可疑电子邮件等威胁，并进行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 中的当前威胁事件列表](../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="aa0fd-133">若要查看您的组织的当前事件列表，请在安全&amp;合规性中心中，转到 "**威胁管理** \> **审核** \> **事件**"。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-133">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![在 "安全&amp;合规性中心" 中， \>选择 "威胁管理审核"](../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="aa0fd-135">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="aa0fd-135">Attack Simulator</span></span>

<span data-ttu-id="aa0fd-136">使用攻击模拟器在您的组织中设置和运行真实的 cyberattacks，并在真正的 cyberattack 影响您的企业之前识别易受攻击的人员。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="aa0fd-137">若要了解详细信息，请参阅[Office 365 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="aa0fd-138">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="aa0fd-138">Automated investigation and response</span></span>

<span data-ttu-id="aa0fd-139">使用自动调查和响应（空气）功能来节省与内容、设备和人员相关的时间和精力，以防止组织中的威胁带来风险。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="aa0fd-140">只要触发了某些警报，或安全操作团队启动时，AIR 进程就可以开始。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="aa0fd-141">若要了解详细信息，请参阅[Office 365 中的自动化调查和响应](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span> 
  
## <a name="threat-intelligence-widgets"></a><span data-ttu-id="aa0fd-142">威胁智能小部件</span><span class="sxs-lookup"><span data-stu-id="aa0fd-142">Threat intelligence widgets</span></span>

<span data-ttu-id="aa0fd-143">作为 Office 365 高级威胁防护计划2产品的一部分，安全分析员可以查看已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-143">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="aa0fd-144">这有助于确定是否存在可采取的更多预防措施/步骤，以确保用户安全。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![显示有关最近威胁的信息的安全趋势](../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="aa0fd-146">如何获取这些功能？</span><span class="sxs-lookup"><span data-stu-id="aa0fd-146">How do we get these capabilities?</span></span>

<span data-ttu-id="aa0fd-147">Office 365 中包含 office 365 高级威胁防护计划2，其中包括在企业版 E5 中，或作为特定订阅的加载项。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-147">Office 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="aa0fd-148">若要了解详细信息，请参阅[Office 365 ATP 计划1和计划 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-148">To learn more, see [Office 365 ATP Plan 1 and Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="aa0fd-149">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="aa0fd-149">Required roles and permissions</span></span>

<span data-ttu-id="aa0fd-150">Office 365 高级威胁防护使用基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-150">Office 365 Advanced Threat Protection uses role-based access control.</span></span> <span data-ttu-id="aa0fd-151">可以通过 Azure Active Directory、Microsoft 365 管理中心或 Office 365 安全性 & 合规性中心中的某些角色来分配权限。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Office 365 Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="aa0fd-152">尽管某些角色（例如安全管理员）可以在 Office 365 安全 & 合规性中心中分配，但请考虑改用 Microsoft 365 管理中心或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-152">Although some roles, such as Security Administrator, can be assigned in the Office 365 Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="aa0fd-153">有关角色、角色组和权限的信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
> - [<span data-ttu-id="aa0fd-154">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="aa0fd-154">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
> - [<span data-ttu-id="aa0fd-155">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="aa0fd-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)


|<span data-ttu-id="aa0fd-156">活动</span><span class="sxs-lookup"><span data-stu-id="aa0fd-156">Activity</span></span> |<span data-ttu-id="aa0fd-157">角色和权限</span><span class="sxs-lookup"><span data-stu-id="aa0fd-157">Roles and permissions</span></span> |  
|:-----|:-----|
|<span data-ttu-id="aa0fd-158">使用威胁仪表板（或新[安全仪表板](security-dashboard.md)）</span><span class="sxs-lookup"><span data-stu-id="aa0fd-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <br/><span data-ttu-id="aa0fd-159">查看有关最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="aa0fd-159">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="aa0fd-160">下列一种含义：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-160">One of the following:</span></span> <br/><span data-ttu-id="aa0fd-161">- **Office 365 全局管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-161">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="aa0fd-162">- **安全管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-162">- **Security Administrator**</span></span> <br/><span data-ttu-id="aa0fd-163">- **安全读者**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-163">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="aa0fd-164">可以在任何 Azure Active Directory （[https://portal.azure.com](https://portal.azure.com)）或 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)）中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-164">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span> |
|<span data-ttu-id="aa0fd-165">使用[威胁浏览器（和实时检测）](threat-explorer.md)分析威胁</span><span class="sxs-lookup"><span data-stu-id="aa0fd-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="aa0fd-166">下列一种含义：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-166">One of the following:</span></span> <br/><span data-ttu-id="aa0fd-167">- **Office 365 全局管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-167">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="aa0fd-168">- **安全管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-168">- **Security Administrator**</span></span> <br/><span data-ttu-id="aa0fd-169">- **安全读者**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-169">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="aa0fd-170">可以在任何 Azure Active Directory （[https://portal.azure.com](https://portal.azure.com)）或 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)）中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-170">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span> |
|<span data-ttu-id="aa0fd-171">查看事件（也称为调查）</span><span class="sxs-lookup"><span data-stu-id="aa0fd-171">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="aa0fd-172">将电子邮件添加到事件</span><span class="sxs-lookup"><span data-stu-id="aa0fd-172">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="aa0fd-173">下列一种含义：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-173">One of the following:</span></span> <br/><span data-ttu-id="aa0fd-174">- **Office 365 全局管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-174">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="aa0fd-175">- **安全管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-175">- **Security Administrator**</span></span> <br/><span data-ttu-id="aa0fd-176">- **安全读者**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-176">- **Security Reader**</span></span> <br/> <br/><span data-ttu-id="aa0fd-177">可以在任何 Azure Active Directory （[https://portal.azure.com](https://portal.azure.com)）或 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)）中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-177">These roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span>  |
|<span data-ttu-id="aa0fd-178">触发事件中的电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="aa0fd-178">Trigger email actions in an incident</span></span> <br/> <br/> <span data-ttu-id="aa0fd-179">查找和删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="aa0fd-179">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="aa0fd-180">下列一种含义：</span><span class="sxs-lookup"><span data-stu-id="aa0fd-180">One of the following:</span></span> <br/><span data-ttu-id="aa0fd-181">- **Office 365 全局管理员**</span><span class="sxs-lookup"><span data-stu-id="aa0fd-181">- **Office 365 Global Administrator**</span></span>  <br/> <span data-ttu-id="aa0fd-182">- **安全管理员**和**搜索和清除**角色</span><span class="sxs-lookup"><span data-stu-id="aa0fd-182">- **Security Administrator** plus the **Search and Purge** role</span></span><br/><br/><span data-ttu-id="aa0fd-183">**全局管理员**和**安全管理员**角色可以在 Azure Active Directory （[https://portal.azure.com](https://portal.azure.com)）或 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)）中进行分配。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span> <br/><br/><span data-ttu-id="aa0fd-184">必须在 Office 365 安全 & 合规中心（[https://protection.office.com](https://protection.office.com)）中分配**搜索和清除**角色。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-184">The **Search and Purge** role must be assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> |
|<span data-ttu-id="aa0fd-185">将 Office 365 高级威胁防护计划2与 Microsoft Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="aa0fd-185">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender Advanced Threat Protection</span></span>  <br/><br/> <span data-ttu-id="aa0fd-186">将 Office 365 高级威胁防护计划2与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="aa0fd-186">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="aa0fd-187">在任何 Azure Active[https://portal.azure.com](https://portal.azure.com)Directory （）或 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)）中分配的**Office 365 全局管理员**或**安全管理员**角色。</span><span class="sxs-lookup"><span data-stu-id="aa0fd-187">Either the **Office 365 Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span><br/><span data-ttu-id="aa0fd-188">--- **外** ---</span><span class="sxs-lookup"><span data-stu-id="aa0fd-188">--- **plus** ---</span></span><br/><span data-ttu-id="aa0fd-189">在其他应用程序（如[Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)或 SIEM server）中分配的相应角色</span><span class="sxs-lookup"><span data-stu-id="aa0fd-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server)</span></span>  |
   
    
## <a name="next-steps"></a><span data-ttu-id="aa0fd-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="aa0fd-190">Next steps</span></span>

- [<span data-ttu-id="aa0fd-191">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="aa0fd-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="aa0fd-192">查找并调查已传递的恶意电子邮件（Office 365 威胁调查和响应）</span><span class="sxs-lookup"><span data-stu-id="aa0fd-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="aa0fd-193">集成 Office 365 威胁调查和响应与 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="aa0fd-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="aa0fd-194">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="aa0fd-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

