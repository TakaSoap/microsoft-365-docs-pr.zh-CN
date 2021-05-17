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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d61da5a12882bef3ffee715bffb37ec96a18fd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203639"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="f0f69-103">威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="f0f69-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0f69-104">**应用于**</span><span class="sxs-lookup"><span data-stu-id="f0f69-104">**Applies To**</span></span>
- [<span data-ttu-id="f0f69-105">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f0f69-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="f0f69-106">[Microsoft Defender](defender-for-office-365.md) for Office 365威胁调查和响应功能可帮助安全分析员和管理员通过执行Microsoft 365来保护其组织的业务数据：</span><span class="sxs-lookup"><span data-stu-id="f0f69-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="f0f69-107">轻松识别、监视和了解网络攻击</span><span class="sxs-lookup"><span data-stu-id="f0f69-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="f0f69-108">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0f69-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="f0f69-109">提供见解和知识以帮助安全操作防止针对其组织的网络攻击</span><span class="sxs-lookup"><span data-stu-id="f0f69-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="f0f69-110">针对[基于电子邮件的关键威胁Office 365](automated-investigation-response-office.md)自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="f0f69-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="f0f69-111">威胁调查和响应功能可深入了解安全与合规中心内提供的威胁&响应操作。</span><span class="sxs-lookup"><span data-stu-id="f0f69-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Security & Compliance Center.</span></span> <span data-ttu-id="f0f69-112">这些见解可帮助组织的安全团队保护用户免受基于电子邮件或文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="f0f69-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="f0f69-113">这些功能有助于监视信号并收集来自多个源的数据，例如用户活动、身份验证、电子邮件、被入侵电脑和安全事件。</span><span class="sxs-lookup"><span data-stu-id="f0f69-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="f0f69-114">业务决策者和安全运营团队可以使用此信息来了解并响应对组织的威胁，并保护知识产权。</span><span class="sxs-lookup"><span data-stu-id="f0f69-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="f0f69-115">熟悉威胁调查和响应工具</span><span class="sxs-lookup"><span data-stu-id="f0f69-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="f0f69-116">威胁调查和响应功能以一组工具和响应工作流&安全与合规中心内出现，其中包括：</span><span class="sxs-lookup"><span data-stu-id="f0f69-116">Threat investigation and response capabilities surface in the Security & Compliance Center, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="f0f69-117">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="f0f69-117">Threat dashboard</span></span>](#threat-dashboard)
- [<span data-ttu-id="f0f69-118">资源管理器</span><span class="sxs-lookup"><span data-stu-id="f0f69-118">Explorer</span></span>](#threat-explorer)
- [<span data-ttu-id="f0f69-119">事件</span><span class="sxs-lookup"><span data-stu-id="f0f69-119">Incidents</span></span>](#incidents)
- [<span data-ttu-id="f0f69-120">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="f0f69-120">Attack Simulator</span></span>](#attack-simulator)
- [<span data-ttu-id="f0f69-121">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="f0f69-121">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a><span data-ttu-id="f0f69-122">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="f0f69-122">Threat dashboard</span></span>

<span data-ttu-id="f0f69-123">使用威胁 (也称为安全仪表板[) ，](security-dashboard.md)可快速查看已解决的威胁，并直观地向业务决策者报告 Microsoft 365 服务如何保护业务。</span><span class="sxs-lookup"><span data-stu-id="f0f69-123">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Microsoft 365 services are securing your business.</span></span>

![威胁仪表板](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

<span data-ttu-id="f0f69-125">若要查看和使用此仪表板，在安全与合规&，请转到威胁 **管理** \> **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="f0f69-125">To view and use this dashboard, in the Security & Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

### <a name="threat-explorer"></a><span data-ttu-id="f0f69-126">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="f0f69-126">Threat Explorer</span></span>

<span data-ttu-id="f0f69-127">使用 [威胁 (](threat-explorer.md) 和实时检测) 分析威胁、查看一段时间的攻击量，以及按威胁系列、攻击者基础结构等分析数据。</span><span class="sxs-lookup"><span data-stu-id="f0f69-127">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="f0f69-128">威胁 (也称为资源管理器) 资源管理器"是任何安全分析师调查工作流的起点。</span><span class="sxs-lookup"><span data-stu-id="f0f69-128">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![威胁资源管理器](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="f0f69-130">若要查看和使用此报告，在安全与合规&，请转到威胁 **管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f0f69-130">To view and use this report, in the Security & Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="f0f69-131">事件</span><span class="sxs-lookup"><span data-stu-id="f0f69-131">Incidents</span></span>

<span data-ttu-id="f0f69-132">使用事件列表 (也称为调查) 查看正在飞行安全事件的列表。</span><span class="sxs-lookup"><span data-stu-id="f0f69-132">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="f0f69-133">事件用于跟踪威胁（如可疑电子邮件）以及执行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="f0f69-133">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![当前威胁事件列表Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="f0f69-135">若要查看组织的当前事件列表，在安全与合规&，转到"威胁管理 \> **""审阅** \> **事件"。**</span><span class="sxs-lookup"><span data-stu-id="f0f69-135">To view the list of current incidents for your organization, in the Security & Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>

![在安全与&中心，选择"威胁管理 \> 审阅"](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="f0f69-137">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="f0f69-137">Attack Simulator</span></span>

<span data-ttu-id="f0f69-138">使用攻击模拟器在组织中设置和运行真实的网络攻击，并识别在真实网络攻击影响你的业务之前易受攻击的人。</span><span class="sxs-lookup"><span data-stu-id="f0f69-138">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="f0f69-139">若要了解更多信息，请参阅攻击[模拟器Office 365。](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="f0f69-139">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="f0f69-140">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="f0f69-140">Automated investigation and response</span></span>

<span data-ttu-id="f0f69-141">使用自动调查和响应 (AIR) 功能，节省将内容、设备和组织中面临威胁的人相关的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="f0f69-141">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="f0f69-142">只要触发某些警报，或者由安全运营团队启动，AIR 进程就可以开始。</span><span class="sxs-lookup"><span data-stu-id="f0f69-142">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="f0f69-143">若要了解更多信息，请参阅 Office 365 中的[自动调查和Office 365。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="f0f69-143">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="f0f69-144">威胁智能小组件</span><span class="sxs-lookup"><span data-stu-id="f0f69-144">Threat intelligence widgets</span></span>

<span data-ttu-id="f0f69-145">作为 Microsoft Defender for Office 365计划 2 产品/服务一部分，安全分析师可以审阅有关已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0f69-145">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="f0f69-146">这可用于确定是否可以采取其他预防措施/步骤来保证用户安全。</span><span class="sxs-lookup"><span data-stu-id="f0f69-146">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![显示有关最近威胁的信息的安全趋势](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="f0f69-148">我们如何获取这些功能？</span><span class="sxs-lookup"><span data-stu-id="f0f69-148">How do we get these capabilities?</span></span>

<span data-ttu-id="f0f69-149">Microsoft 365威胁调查和响应功能包含在 Microsoft Defender for Office 365 计划 2 中，该计划包含在 Enterprise E5 中或作为特定订阅的加载项。</span><span class="sxs-lookup"><span data-stu-id="f0f69-149">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="f0f69-150">若要了解更多信息，请参阅[Defender for Office 365 Plan 1 和 Plan 2。](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="f0f69-150">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="f0f69-151">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="f0f69-151">Required roles and permissions</span></span>

<span data-ttu-id="f0f69-152">Microsoft Defender for Office 365使用基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="f0f69-152">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="f0f69-153">权限通过安全中心、Azure Active Directory管理Microsoft 365安全中心&分配。</span><span class="sxs-lookup"><span data-stu-id="f0f69-153">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Security & Compliance Center.</span></span>

> [!TIP]
> <span data-ttu-id="f0f69-154">尽管可以在安全与合规中心分配某些角色（如安全&管理员），但请考虑改为使用 Microsoft 365 管理中心Azure Active Directory角色。</span><span class="sxs-lookup"><span data-stu-id="f0f69-154">Although some roles, such as Security Administrator, can be assigned in the Security & Compliance Center, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="f0f69-155">有关角色、角色组和权限的信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="f0f69-155">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="f0f69-156">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="f0f69-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
>
> - [<span data-ttu-id="f0f69-157">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="f0f69-157">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|<span data-ttu-id="f0f69-158">活动</span><span class="sxs-lookup"><span data-stu-id="f0f69-158">Activity</span></span>|<span data-ttu-id="f0f69-159">角色和权限</span><span class="sxs-lookup"><span data-stu-id="f0f69-159">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="f0f69-160">使用威胁仪表板 (或新的 [安全仪表板](security-dashboard.md)) </span><span class="sxs-lookup"><span data-stu-id="f0f69-160">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="f0f69-161">查看有关最近威胁或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="f0f69-161">View information about recent or current threats</span></span>|<span data-ttu-id="f0f69-162">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f0f69-162">One of the following:</span></span> <ul><li><span data-ttu-id="f0f69-163">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-163">**Global Administrator**</span></span></li><li><span data-ttu-id="f0f69-164">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-164">**Security Administrator**</span></span></li><li><span data-ttu-id="f0f69-165">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="f0f69-165">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="f0f69-166">可以在管理中心或管理中心Azure Active Directory () 分配Microsoft 365 <https://portal.azure.com> 角色 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-166">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="f0f69-167">使用 [威胁 (和实时检测 ](threat-explorer.md)) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="f0f69-167">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="f0f69-168">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f0f69-168">One of the following:</span></span> <ul><li><span data-ttu-id="f0f69-169">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-169">**Global Administrator**</span></span></li><li><span data-ttu-id="f0f69-170">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-170">**Security Administrator**</span></span></li><li><span data-ttu-id="f0f69-171">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="f0f69-171">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="f0f69-172">可以在管理中心或管理中心Azure Active Directory () 分配Microsoft 365 <https://portal.azure.com> 角色 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-172">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="f0f69-173">查看事件 (也称为调查) </span><span class="sxs-lookup"><span data-stu-id="f0f69-173">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="f0f69-174">向事件添加电子邮件</span><span class="sxs-lookup"><span data-stu-id="f0f69-174">Add email messages to an incident</span></span>|<span data-ttu-id="f0f69-175">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f0f69-175">One of the following:</span></span> <ul><li><span data-ttu-id="f0f69-176">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-176">**Global Administrator**</span></span></li><li><span data-ttu-id="f0f69-177">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-177">**Security Administrator**</span></span></li><li><span data-ttu-id="f0f69-178">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="f0f69-178">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="f0f69-179">可以在管理中心或管理中心Azure Active Directory () 分配Microsoft 365 <https://portal.azure.com> 角色 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-179">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="f0f69-180">在事件中触发电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="f0f69-180">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="f0f69-181">查找并删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="f0f69-181">Find and delete suspicious email messages</span></span>|<span data-ttu-id="f0f69-182">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f0f69-182">One of the following:</span></span> <ul><li><span data-ttu-id="f0f69-183">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="f0f69-183">**Global Administrator**</span></span></li><li><span data-ttu-id="f0f69-184">**安全管理员** 以及 **搜索和清除** 角色</span><span class="sxs-lookup"><span data-stu-id="f0f69-184">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="f0f69-185">全局 **管理员\*\*\*\*和安全管理员** 角色可以在管理中心Azure Active Directory () Microsoft 365 <https://portal.azure.com> 分配 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-185">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="f0f69-186">搜索 **和清除** 角色必须在安全与合规中心&分配 <https://protection.office.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-186">The **Search and Purge** role must be assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span>|
|<span data-ttu-id="f0f69-187">将 Microsoft Defender for Office 365 计划 2 与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="f0f69-187">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span>  <p> <span data-ttu-id="f0f69-188">将 Microsoft Defender for Office 365 计划 2 与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="f0f69-188">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="f0f69-189">全局 **管理员或** 安全管理员角色在 Azure Active Directory () 或 Microsoft 365 <https://portal.azure.com> 管理中心 <https://admin.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-189">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="f0f69-190">--- **加号** --- </span><span class="sxs-lookup"><span data-stu-id="f0f69-190">--- **plus** --- </span></span><p> <span data-ttu-id="f0f69-191">在其他应用程序（如 (或 SIEM Microsoft Defender 安全中心）[](/windows/security/threat-protection/microsoft-defender-atp/user-roles)中分配的适当) 。</span><span class="sxs-lookup"><span data-stu-id="f0f69-191">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="f0f69-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f0f69-192">Next steps</span></span>

- [<span data-ttu-id="f0f69-193">了解威胁跟踪器 - 新增和值得注意的功能</span><span class="sxs-lookup"><span data-stu-id="f0f69-193">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="f0f69-194">查找并调查通过威胁调查和响应 (Office 365传递的恶意) </span><span class="sxs-lookup"><span data-stu-id="f0f69-194">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="f0f69-195">将Office 365威胁调查和响应与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="f0f69-195">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)

- [<span data-ttu-id="f0f69-196">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="f0f69-196">Learn about Attack Simulator</span></span>](attack-simulator.md)