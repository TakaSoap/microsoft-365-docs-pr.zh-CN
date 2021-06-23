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
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083700"
---
# <a name="threat-investigation-and-response"></a><span data-ttu-id="6a00e-103">威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="6a00e-103">Threat investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6a00e-104">**应用于**</span><span class="sxs-lookup"><span data-stu-id="6a00e-104">**Applies To**</span></span>
- [<span data-ttu-id="6a00e-105">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a00e-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="6a00e-106">[Microsoft Defender](defender-for-office-365.md) for Office 365威胁调查和响应功能可帮助安全分析员和管理员通过执行Microsoft 365来保护其组织的业务数据：</span><span class="sxs-lookup"><span data-stu-id="6a00e-106">Threat investigation and response capabilities in [Microsoft Defender for Office 365](defender-for-office-365.md) help security analysts and administrators protect their organization's Microsoft 365 for business users by:</span></span>

- <span data-ttu-id="6a00e-107">轻松识别、监视和了解网络攻击</span><span class="sxs-lookup"><span data-stu-id="6a00e-107">Making it easy to identify, monitor, and understand cyberattacks</span></span>
- <span data-ttu-id="6a00e-108">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a00e-108">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
- <span data-ttu-id="6a00e-109">提供见解和知识以帮助安全操作防止针对其组织的网络攻击</span><span class="sxs-lookup"><span data-stu-id="6a00e-109">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>
- <span data-ttu-id="6a00e-110">针对[基于电子邮件的关键威胁Office 365](automated-investigation-response-office.md)自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="6a00e-110">Employing [automated investigation and response in Office 365](automated-investigation-response-office.md) for critical email-based threats</span></span>

<span data-ttu-id="6a00e-111">威胁调查和响应功能提供威胁和可用响应门户中相关响应Microsoft 365 Defender见解。</span><span class="sxs-lookup"><span data-stu-id="6a00e-111">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6a00e-112">这些见解可帮助组织的安全团队保护用户免受基于电子邮件或文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="6a00e-112">These insights can help your organization's security team protect users from email- or file-based attacks.</span></span> <span data-ttu-id="6a00e-113">这些功能有助于监视信号并收集来自多个源的数据，例如用户活动、身份验证、电子邮件、被入侵电脑和安全事件。</span><span class="sxs-lookup"><span data-stu-id="6a00e-113">The capabilities help monitor signals and gather data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="6a00e-114">业务决策者和安全运营团队可以使用此信息来了解并响应对组织的威胁，并保护知识产权。</span><span class="sxs-lookup"><span data-stu-id="6a00e-114">Business decision makers and your security operations team can use this information to understand and respond to threats against your organization and protect your intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="6a00e-115">熟悉威胁调查和响应工具</span><span class="sxs-lookup"><span data-stu-id="6a00e-115">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="6a00e-116">威胁调查和响应功能作为一组Microsoft 365 Defender和响应工作流（包括以下内容）在 Microsoft 365 Defender 门户中显示：</span><span class="sxs-lookup"><span data-stu-id="6a00e-116">Threat investigation and response capabilities surface in the Microsoft 365 Defender portal, as a set of tools and response workflows, including the following:</span></span>

- [<span data-ttu-id="6a00e-117">资源管理器</span><span class="sxs-lookup"><span data-stu-id="6a00e-117">Explorer</span></span>](#explorer)
- [<span data-ttu-id="6a00e-118">事件</span><span class="sxs-lookup"><span data-stu-id="6a00e-118">Incidents</span></span>](#incidents)
- [<span data-ttu-id="6a00e-119">攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="6a00e-119">Attack simulation training</span></span>](attack-simulation-training.md)
- [<span data-ttu-id="6a00e-120">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="6a00e-120">Automated investigation and response</span></span>](automated-investigation-response-office.md)

### <a name="explorer"></a><span data-ttu-id="6a00e-121">资源管理器</span><span class="sxs-lookup"><span data-stu-id="6a00e-121">Explorer</span></span>

<span data-ttu-id="6a00e-122">使用 [资源管理器 (](threat-explorer.md) 实时检测功能) 威胁、查看一段时间的攻击量，以及按威胁系列、攻击者基础结构等分析数据。</span><span class="sxs-lookup"><span data-stu-id="6a00e-122">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="6a00e-123">资源管理器 (也称为威胁资源管理器) 是任何安全分析师调查工作流的起点。</span><span class="sxs-lookup"><span data-stu-id="6a00e-123">Explorer (also referred to as Threat Explorer) is the starting place for any security analyst's investigation workflow.</span></span>

![威胁资源管理器](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

<span data-ttu-id="6a00e-125">若要查看和使用此报告，在 Microsoft 365 Defender 门户中，转到电子邮件&**协作**  >  **资源管理器。**</span><span class="sxs-lookup"><span data-stu-id="6a00e-125">To view and use this report, in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Explorer**.</span></span>

### <a name="incidents"></a><span data-ttu-id="6a00e-126">事件</span><span class="sxs-lookup"><span data-stu-id="6a00e-126">Incidents</span></span>

<span data-ttu-id="6a00e-127">使用事件列表 (也称为调查) 查看正在飞行安全事件的列表。</span><span class="sxs-lookup"><span data-stu-id="6a00e-127">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="6a00e-128">事件用于跟踪威胁（如可疑电子邮件）以及执行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="6a00e-128">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>

![当前威胁事件列表Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

<span data-ttu-id="6a00e-130">若要查看组织的当前事件列表，在 Microsoft 365 Defender 门户中，转到"事件&**事件**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="6a00e-130">To view the list of current incidents for your organization, in the Microsoft 365 Defender portal, go to **Incidents & alerts** > **Incidents**.</span></span>

![在安全与&中心，选择"威胁管理 \> 审阅"](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a><span data-ttu-id="6a00e-132">攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="6a00e-132">Attack simulation training</span></span>

<span data-ttu-id="6a00e-133">使用攻击模拟培训在组织中设置和运行真实的网络攻击，并识别在真实网络攻击影响你的业务之前易受攻击的人。</span><span class="sxs-lookup"><span data-stu-id="6a00e-133">Use Attack simulation training to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="6a00e-134">若要了解更多信息，请参阅 [模拟网络钓鱼攻击](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="6a00e-134">To learn more, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

<span data-ttu-id="6a00e-135">若要查看并使用 Microsoft 365 Defender 门户中的此功能，请转到电子邮件&**协作**  >  **攻击模拟培训**。</span><span class="sxs-lookup"><span data-stu-id="6a00e-135">To view and use this feature in the Microsoft 365 Defender portal, go to **Email & collaboration** > **Attack simulation training**.</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="6a00e-136">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="6a00e-136">Automated investigation and response</span></span>

<span data-ttu-id="6a00e-137">使用自动调查和响应 (AIR) 功能，节省将内容、设备和组织中面临威胁的人相关的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="6a00e-137">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="6a00e-138">只要触发某些警报，或者由安全运营团队启动，AIR 进程就可以开始。</span><span class="sxs-lookup"><span data-stu-id="6a00e-138">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="6a00e-139">若要了解更多信息，请参阅 Office 365 中的[自动调查和Office 365。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="6a00e-139">To learn more, see [automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

## <a name="threat-intelligence-widgets"></a><span data-ttu-id="6a00e-140">威胁智能小组件</span><span class="sxs-lookup"><span data-stu-id="6a00e-140">Threat intelligence widgets</span></span>

<span data-ttu-id="6a00e-141">作为 Microsoft Defender for Office 365计划 2 产品/服务一部分，安全分析师可以审阅有关已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6a00e-141">As part of the Microsoft Defender for Office 365 Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="6a00e-142">这可用于确定是否可以采取其他预防措施/步骤来保证用户安全。</span><span class="sxs-lookup"><span data-stu-id="6a00e-142">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>

![显示有关最近威胁的信息的安全趋势](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="6a00e-144">我们如何获取这些功能？</span><span class="sxs-lookup"><span data-stu-id="6a00e-144">How do we get these capabilities?</span></span>

<span data-ttu-id="6a00e-145">Microsoft 365威胁调查和响应功能包含在 Microsoft Defender for Office 365 计划 2 中，该计划包含在 Enterprise E5 中或作为特定订阅的加载项。</span><span class="sxs-lookup"><span data-stu-id="6a00e-145">Microsoft 365 threat investigation and response capabilities are included in Microsoft Defender for Office 365 Plan 2, which is included in Enterprise E5 or as an add-on to certain subscriptions.</span></span> <span data-ttu-id="6a00e-146">若要了解更多信息，请参阅[Defender for Office 365 Plan 1 和 Plan 2。](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="6a00e-146">To learn more, see [Defender for Office 365 Plan 1 and Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="required-roles-and-permissions"></a><span data-ttu-id="6a00e-147">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="6a00e-147">Required roles and permissions</span></span>

<span data-ttu-id="6a00e-148">Microsoft Defender for Office 365使用基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="6a00e-148">Microsoft Defender for Office 365 uses role-based access control.</span></span> <span data-ttu-id="6a00e-149">权限通过 Azure Active Directory、Microsoft 365 管理中心 或 Microsoft 365 Defender 门户中的特定角色分配。</span><span class="sxs-lookup"><span data-stu-id="6a00e-149">Permissions are assigned through certain roles in Azure Active Directory, the Microsoft 365 admin center, or the Microsoft 365 Defender portal.</span></span>

> [!TIP]
> <span data-ttu-id="6a00e-150">尽管某些角色（如安全管理员）可以在 Microsoft 365 Defender 门户中分配，但请考虑使用 Microsoft 365 管理中心 或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6a00e-150">Although some roles, such as Security Administrator, can be assigned in the Microsoft 365 Defender portal, consider using either the Microsoft 365 admin center or Azure Active Directory instead.</span></span> <span data-ttu-id="6a00e-151">有关角色、角色组和权限的信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="6a00e-151">For information about roles, role groups, and permissions, see the following resources:</span></span>
>
> - [<span data-ttu-id="6a00e-152">Microsoft 365 Defender 门户中的权限</span><span class="sxs-lookup"><span data-stu-id="6a00e-152">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
> - [<span data-ttu-id="6a00e-153">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="6a00e-153">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|<span data-ttu-id="6a00e-154">活动</span><span class="sxs-lookup"><span data-stu-id="6a00e-154">Activity</span></span>|<span data-ttu-id="6a00e-155">角色和权限</span><span class="sxs-lookup"><span data-stu-id="6a00e-155">Roles and permissions</span></span>|
|---|---|
|<span data-ttu-id="6a00e-156">使用威胁&漏洞管理仪表板 (或新的[安全仪表板) ](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="6a00e-156">Use the Threat & Vulnerability Management dashboard (or the new [Security dashboard](security-dashboard.md))</span></span> <p> <span data-ttu-id="6a00e-157">查看有关最近威胁或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="6a00e-157">View information about recent or current threats</span></span>|<span data-ttu-id="6a00e-158">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="6a00e-158">One of the following:</span></span> <ul><li><span data-ttu-id="6a00e-159">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-159">**Global Administrator**</span></span></li><li><span data-ttu-id="6a00e-160">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-160">**Security Administrator**</span></span></li><li><span data-ttu-id="6a00e-161">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="6a00e-161">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="6a00e-162">这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或 <https://admin.microsoft.com> Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-162">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="6a00e-163">使用 [资源管理器 (实时检测功能) ](threat-explorer.md) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="6a00e-163">Use [Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>|<span data-ttu-id="6a00e-164">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="6a00e-164">One of the following:</span></span> <ul><li><span data-ttu-id="6a00e-165">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-165">**Global Administrator**</span></span></li><li><span data-ttu-id="6a00e-166">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-166">**Security Administrator**</span></span></li><li><span data-ttu-id="6a00e-167">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="6a00e-167">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="6a00e-168">这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或 <https://admin.microsoft.com> Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-168">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="6a00e-169">查看事件 (也称为调查) </span><span class="sxs-lookup"><span data-stu-id="6a00e-169">View Incidents (also referred to as Investigations)</span></span> <p> <span data-ttu-id="6a00e-170">向事件添加电子邮件</span><span class="sxs-lookup"><span data-stu-id="6a00e-170">Add email messages to an incident</span></span>|<span data-ttu-id="6a00e-171">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="6a00e-171">One of the following:</span></span> <ul><li><span data-ttu-id="6a00e-172">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-172">**Global Administrator**</span></span></li><li><span data-ttu-id="6a00e-173">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-173">**Security Administrator**</span></span></li><li><span data-ttu-id="6a00e-174">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="6a00e-174">**Security Reader**</span></span></li></ul> <p> <span data-ttu-id="6a00e-175">这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或 <https://admin.microsoft.com> Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-175">These roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span>|
|<span data-ttu-id="6a00e-176">在事件中触发电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="6a00e-176">Trigger email actions in an incident</span></span> <p> <span data-ttu-id="6a00e-177">查找并删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="6a00e-177">Find and delete suspicious email messages</span></span>|<span data-ttu-id="6a00e-178">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="6a00e-178">One of the following:</span></span> <ul><li><span data-ttu-id="6a00e-179">**全局管理员**</span><span class="sxs-lookup"><span data-stu-id="6a00e-179">**Global Administrator**</span></span></li><li><span data-ttu-id="6a00e-180">**安全管理员** 以及 **搜索和清除** 角色</span><span class="sxs-lookup"><span data-stu-id="6a00e-180">**Security Administrator** plus the **Search and Purge** role</span></span></li></ul> <p> <span data-ttu-id="6a00e-181">全局 **管理员\*\*\*\*和安全管理员** 角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或 <https://admin.microsoft.com> Microsoft 365 管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-181">The **Global Administrator** and **Security Administrator** roles can be assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="6a00e-182">搜索 **和清除** 角色必须在 Microsoft 36  Defender 门户 & 电子邮件和协作角色中 <https://security.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-182">The **Search and Purge** role must be assigned in the **Email & collaboration roles** in the Microsoft 36 Defender portal (<https://security.microsoft.com>).</span></span>|
|<span data-ttu-id="6a00e-183">将 Microsoft Defender for Office 365 计划 2 与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="6a00e-183">Integrate Microsoft Defender for Office 365 Plan 2 with Microsoft Defender for Endpoint</span></span> <p> <span data-ttu-id="6a00e-184">将 Microsoft Defender for Office 365 计划 2 与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="6a00e-184">Integrate Microsoft Defender for Office 365 Plan 2 with a SIEM server</span></span>|<span data-ttu-id="6a00e-185">全局 **管理员或** 安全管理员角色在 Azure Active Directory () 或 Microsoft 365 管理中心 (<https://portal.azure.com> <https://admin.microsoft.com>) 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-185">Either the **Global Administrator** or the **Security Administrator** role assigned in either Azure Active Directory (<https://portal.azure.com>) or the Microsoft 365 admin center (<https://admin.microsoft.com>).</span></span> <p> <span data-ttu-id="6a00e-186">--- **加号** --- </span><span class="sxs-lookup"><span data-stu-id="6a00e-186">--- **plus** --- </span></span><p> <span data-ttu-id="6a00e-187">在其他应用程序（如 (或 SIEM Microsoft Defender 安全中心）[](/windows/security/threat-protection/microsoft-defender-atp/user-roles)中分配的适当) 。</span><span class="sxs-lookup"><span data-stu-id="6a00e-187">An appropriate role assigned in additional applications (such as [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/user-roles) or your SIEM server).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="6a00e-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a00e-188">Next steps</span></span>

- [<span data-ttu-id="6a00e-189">了解威胁跟踪器 - 新增和值得注意的功能</span><span class="sxs-lookup"><span data-stu-id="6a00e-189">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
- [<span data-ttu-id="6a00e-190">查找并调查通过威胁调查和响应 (Office 365传递的恶意) </span><span class="sxs-lookup"><span data-stu-id="6a00e-190">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="6a00e-191">将Office 365威胁调查和响应与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="6a00e-191">Integrate Office 365 Threat Investigation and Response with Microsoft Defender for Endpoint</span></span>](integrate-office-365-ti-with-mde.md)
- [<span data-ttu-id="6a00e-192">模拟网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="6a00e-192">Simulate a phishing attack</span></span>](attack-simulation-training.md)
