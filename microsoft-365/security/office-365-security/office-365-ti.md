---
title: 威胁调查和&功能 - Microsoft Defender for Office 365 计划 2
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft Defender for Office 365 计划中的威胁调查和响应功能。
ms.openlocfilehash: dc6a3dec096b6834d024cc4ff74a5b7600c33d45
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794228"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="9d6c7-103">威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="9d6c7-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9d6c7-104">[Microsoft Defender for Office 365](office-365-atp.md)中的威胁调查和响应功能可帮助安全分析员和管理员通过：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-104">Threat investigation and response capabilities in [Microsoft Defender for Office 365](office-365-atp.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="9d6c7-105">轻松识别、监视和了解网络攻击</span><span class="sxs-lookup"><span data-stu-id="9d6c7-105">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="9d6c7-106">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的威胁</span><span class="sxs-lookup"><span data-stu-id="9d6c7-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="9d6c7-107">提供见解和知识以帮助安全操作防止针对其组织的网络攻击</span><span class="sxs-lookup"><span data-stu-id="9d6c7-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="9d6c7-108">针对 [基于电子邮件的关键威胁在 Office 365](automated-investigation-response-office.md) 中采用自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="9d6c7-108">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="9d6c7-109">威胁调查和响应功能提供对安全与合规中心中提供的威胁和相关响应&见解。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="9d6c7-110">这些见解可帮助组织的安全团队保护用户免受电子邮件或基于文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-110">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="9d6c7-111">这些功能有助于监视信号和从多个源收集数据，例如用户活动、身份验证、电子邮件、遭到入侵的 PC 和安全事件。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-111">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="9d6c7-112">业务决策者和安全运营团队可以使用此信息来了解并响应针对组织的威胁，并保护知识产权。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-112">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="9d6c7-113">熟悉威胁调查和响应工具</span><span class="sxs-lookup"><span data-stu-id="9d6c7-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="9d6c7-114">威胁调查和响应功能作为一组工具和响应工作流&安全与合规中心内出现，其中包括：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-114">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="9d6c7-115">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="9d6c7-115">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="9d6c7-116">资源管理器</span><span class="sxs-lookup"><span data-stu-id="9d6c7-116">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="9d6c7-117">事件</span><span class="sxs-lookup"><span data-stu-id="9d6c7-117">Incidents</span></span>](#incidents)
- [<span data-ttu-id="9d6c7-118">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="9d6c7-118">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="9d6c7-119">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="9d6c7-119">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="9d6c7-120">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="9d6c7-120">Threat dashboard</span></span>

<span data-ttu-id="9d6c7-121">使用威胁仪表板 (也称为安全仪表板 [) ，](security-dashboard.md) 可快速查看已解决的威胁，并直观地向业务决策者报告 Microsoft 365 服务如何保护业务。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-121">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![威胁仪表板](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="9d6c7-123">若要查看和使用此仪表板，在安全与合规&，请转到 **威胁管理** \> **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-123">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="9d6c7-124">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="9d6c7-124">Threat Explorer</span></span>

<span data-ttu-id="9d6c7-125">使用 [威胁资源管理器 (](threat-explorer.md) 实时检测) 分析威胁、查看一段时间的攻击量，以及按威胁系列、攻击者基础结构等分析数据。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-125">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="9d6c7-126">威胁 (资源管理器也称为资源管理器) 是任何安全分析师调查工作流的起点。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-126">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![威胁资源管理器](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="9d6c7-128">若要查看和使用此报告，在安全与合规&，请转到 **威胁管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-128">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="9d6c7-129">事件</span><span class="sxs-lookup"><span data-stu-id="9d6c7-129">Incidents</span></span>

<span data-ttu-id="9d6c7-130">使用事件列表 (也称为调查) 查看正在进行中的安全事件列表。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-130">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="9d6c7-131">事件用于跟踪威胁（如可疑电子邮件）以及执行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-131">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![Office 365 中的当前威胁事件列表](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="9d6c7-133">若要查看组织的当前事件列表，在安全与合规&，转到"威胁管理审阅 \>  \> **事件"。**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-133">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![在安全&中心，选择"威胁管理 \> 审查"](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="9d6c7-135">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="9d6c7-135">Attack Simulator</span></span>

<span data-ttu-id="9d6c7-136">使用攻击模拟器在组织中设置和运行真实的网络攻击，在真正的网络攻击影响你的业务之前识别易受攻击的人。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-136">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="9d6c7-137">若要了解更多信息，请参阅 [Office 365 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-137">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="9d6c7-138">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="9d6c7-138">Automated investigation and response</span></span>

<span data-ttu-id="9d6c7-139">使用自动调查和响应 (AIR) 功能，以节省将内容、设备和组织中面临威胁的人关联在一起的时间和工作量。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-139">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="9d6c7-140">只要触发某些警报，或者当安全运营团队启动时，AIR 进程就可以开始。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-140">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="9d6c7-141">若要了解更多信息，请参阅 [Office 365 中的自动调查和响应](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-141">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="9d6c7-142">威胁智能小组件</span><span class="sxs-lookup"><span data-stu-id="9d6c7-142">Threat intelligence widgets</span></span>

<span data-ttu-id="9d6c7-143">作为 Microsoft Defender for Office 365 计划 2 产品/服务一部分，安全分析师可以查看有关已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-143">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="9d6c7-144">这可用于确定是否可以采取其他预防措施/步骤来保证用户安全。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-144">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![显示最近威胁相关信息的安全趋势](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="9d6c7-146">如何获取这些功能？</span><span class="sxs-lookup"><span data-stu-id="9d6c7-146">How do we get these capabilities?</span></span>

<span data-ttu-id="9d6c7-147">Microsoft 365 威胁调查和响应功能包含在 Microsoft Defender for Office 365 计划 2 中，该计划包含在企业版 E5 中或作为特定订阅的加载项。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-147">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="9d6c7-148">若要了解更多信息，请参阅[Defender for Office 365 计划 1 和计划 2。](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="9d6c7-148">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="9d6c7-149">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="9d6c7-149">Required roles and permissions</span></span>

<span data-ttu-id="9d6c7-150">Microsoft Defender for Office 365 使用基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-150">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="9d6c7-151">权限通过 Azure Active Directory、Microsoft 365 管理中心或安全与合规中心&角色分配。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-151">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="9d6c7-152">尽管某些角色（如安全管理员）可以在安全与合规中心&，但请考虑改为使用 Microsoft 365 管理中心或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-152">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="9d6c7-153">有关角色、角色组和权限的信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-153">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="9d6c7-154">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="9d6c7-154">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="9d6c7-155">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="9d6c7-155">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="9d6c7-156">活动</span><span class="sxs-lookup"><span data-stu-id="9d6c7-156">Activity</span></span>|<span data-ttu-id="9d6c7-157">角色和权限</span><span class="sxs-lookup"><span data-stu-id="9d6c7-157">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="9d6c7-158">使用威胁仪表板 (或新的[安全仪表板) ](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="9d6c7-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="9d6c7-159">查看最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="9d6c7-159">View information about recent or current threats</span></span>|<span data-ttu-id="9d6c7-160">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-160">One of the following:</span></span> <ul><li><span data-ttu-id="9d6c7-161">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-161">**Global Administrator**</span></span></li><li><span data-ttu-id="9d6c7-162">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-162">**Security Administrator**</span></span></li><li><span data-ttu-id="9d6c7-163">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-163">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="9d6c7-164">这些角色可以在 Azure Active Directory () <https://portal.azure.com> Microsoft 365 管理中心 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-164">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="9d6c7-165">使用 [威胁 (实时检测功能分析) ](threat-explorer.md) 威胁</span><span class="sxs-lookup"><span data-stu-id="9d6c7-165">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="9d6c7-166">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-166">One of the following:</span></span> <ul><li><span data-ttu-id="9d6c7-167">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-167">**Global Administrator**</span></span></li><li><span data-ttu-id="9d6c7-168">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-168">**Security Administrator**</span></span></li><li><span data-ttu-id="9d6c7-169">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-169">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="9d6c7-170">这些角色可以在 Azure Active Directory () <https://portal.azure.com> Microsoft 365 管理中心 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-170">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="9d6c7-171">查看事件 (也称为调查) </span><span class="sxs-lookup"><span data-stu-id="9d6c7-171">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="9d6c7-172">向事件添加电子邮件</span><span class="sxs-lookup"><span data-stu-id="9d6c7-172">Add email messages to an incident</span></span>|<span data-ttu-id="9d6c7-173">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-173">One of the following:</span></span> <ul><li><span data-ttu-id="9d6c7-174">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-174">**Global Administrator**</span></span></li><li><span data-ttu-id="9d6c7-175">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-175">**Security Administrator**</span></span></li><li><span data-ttu-id="9d6c7-176">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-176">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="9d6c7-177">这些角色可以在 Azure Active Directory () <https://portal.azure.com> Microsoft 365 管理中心 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-177">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="9d6c7-178">触发事件中的电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="9d6c7-178">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="9d6c7-179">查找并删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="9d6c7-179">Find and delete suspicious email messages</span></span>|<span data-ttu-id="9d6c7-180">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="9d6c7-180">One of the following:</span></span> <ul><li><span data-ttu-id="9d6c7-181">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="9d6c7-181">**Global Administrator**</span></span></li><li><span data-ttu-id="9d6c7-182">**安全管理员** 以及 **搜索和清除** 角色</span><span class="sxs-lookup"><span data-stu-id="9d6c7-182">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="9d6c7-183">全局 **管理员** 和安全管理员角色可以在 Azure Active Directory () 或 <https://portal.azure.com> Microsoft 365 管理中心 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-183">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="9d6c7-184">搜索 **和清除** 角色必须在安全与合规中心&分配 <https://protection.office.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-184">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="9d6c7-185">将 Microsoft Defender for Office 365 计划 2 与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="9d6c7-185">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="9d6c7-186">将 Microsoft Defender for Office 365 计划 2 与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="9d6c7-186">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="9d6c7-187">在 Azure Active  Directory **管理中心或** Microsoft 365 管理中心 () 分配全局管理员或安全 <https://portal.azure.com> <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-187">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="9d6c7-188">--- **加号** --- </span><span class="sxs-lookup"><span data-stu-id="9d6c7-188">--- **plus** --- </span></span><p> <span data-ttu-id="9d6c7-189">在 Microsoft [Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) 安全中心或 SIEM (等其他应用程序中分配的适当) 。</span><span class="sxs-lookup"><span data-stu-id="9d6c7-189">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="9d6c7-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9d6c7-190">Next steps</span></span>

- [<span data-ttu-id="9d6c7-191">了解威胁跟踪器 - 新增和值得注意的功能</span><span class="sxs-lookup"><span data-stu-id="9d6c7-191">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="9d6c7-192">查找并调查通过 Office 365 威胁调查和响应 (发送的恶意) </span><span class="sxs-lookup"><span data-stu-id="9d6c7-192">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="9d6c7-193">将 Office 365 威胁调查和响应与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="9d6c7-193">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-wdatp.md)

- [<span data-ttu-id="9d6c7-194">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="9d6c7-194">Learn about Attack Simulator</span></span>](attack-simulator.md)
