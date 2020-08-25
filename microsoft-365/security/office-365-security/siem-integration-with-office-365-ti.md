---
title: SIEM 与高级威胁防护集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 Office 365 活动管理 API 中的 Office 365 高级威胁防护和相关威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860685"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="e5483-103">SIEM 与高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="e5483-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="e5483-104">如果你的组织使用的是安全事件和事件管理 (SIEM) 服务器，则可将 Office 365 高级威胁防护 (Office 365 ATP) 与您的 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="e5483-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="e5483-105">可以使用 [Office 365 活动管理 API 设置此集成](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="e5483-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e5483-106">SIEM 集成可让你在 SIEM 服务器报告中查看信息，例如 Office 365 ATP 检测到的恶意软件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="e5483-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="e5483-107">若要查看 SIEM 与 Office 365 ATP 集成的示例，请参阅 [技术社区博客：通过 Office 365 ATP 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="e5483-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="e5483-108">有关 Office 365 管理 API 的详细信息，请参阅 [Office 365 管理 API 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="e5483-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="e5483-109">SIEM 集成的工作原理</span><span class="sxs-lookup"><span data-stu-id="e5483-109">How SIEM integration works</span></span>

<span data-ttu-id="e5483-110">Office 365 活动管理 API 从组织的 Microsoft 365 和 Azure Active Directory 活动日志中获取用户、管理员、系统和策略操作和事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e5483-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="e5483-111">如果你的组织有 Office 365 ATP 计划 1 或 2 或 Office 365 E5，则 [可以使用 Office 365 ATP 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="e5483-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="e5483-112">最近 [，Office 365 ATP](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 计划 2 中的自动调查和响应功能中的事件已添加到 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="e5483-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="e5483-113">除了包含有关核心调查详细信息的数据（如 ID、名称和状态），API 还包含有关调查操作和实体的高级信息。</span><span class="sxs-lookup"><span data-stu-id="e5483-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="e5483-114">SIEM 服务器或其他类似系统将轮询 **audit.general** 工作负载以访问检测事件。</span><span class="sxs-lookup"><span data-stu-id="e5483-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="e5483-115">若要了解详细信息，请参阅 [Office 365 管理 API 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="e5483-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 


## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="e5483-116">枚举：AuditLogRecordType - 类型：Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="e5483-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="e5483-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="e5483-117">AuditLogRecordType</span></span>

<span data-ttu-id="e5483-118">下表总结了与 Office 365 ATP 事件相关的 **AuditLogRecordType** 的值：</span><span class="sxs-lookup"><span data-stu-id="e5483-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="e5483-119">值</span><span class="sxs-lookup"><span data-stu-id="e5483-119">Value</span></span>|<span data-ttu-id="e5483-120">成员名称</span><span class="sxs-lookup"><span data-stu-id="e5483-120">Member name</span></span>|<span data-ttu-id="e5483-121">说明</span><span class="sxs-lookup"><span data-stu-id="e5483-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="e5483-122">28</span><span class="sxs-lookup"><span data-stu-id="e5483-122">28</span></span>|<span data-ttu-id="e5483-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="e5483-123">ThreatIntelligence</span></span>|<span data-ttu-id="e5483-124">Exchange Online Protection 和 Office 365 ATP 中的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="e5483-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="e5483-125">41</span><span class="sxs-lookup"><span data-stu-id="e5483-125">41</span></span>|<span data-ttu-id="e5483-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="e5483-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="e5483-127">ATP 安全链接时自动根据阻止和阻止覆盖 Office 365 ATP 中的事件。</span><span class="sxs-lookup"><span data-stu-id="e5483-127">ATP Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="e5483-128">47</span><span class="sxs-lookup"><span data-stu-id="e5483-128">47</span></span>|<span data-ttu-id="e5483-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="e5483-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="e5483-130">在 Office 365 ATP 中，SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的文件的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="e5483-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="e5483-131">64</span><span class="sxs-lookup"><span data-stu-id="e5483-131">64</span></span>|<span data-ttu-id="e5483-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="e5483-132">AirInvestigation</span></span>|<span data-ttu-id="e5483-133">自动调查和响应事件，例如调查详细信息和相关项目。可从 Office 365 ATP 计划 2 中进行自动调查和响应事件，例如调查详细信息和相关项目。</span><span class="sxs-lookup"><span data-stu-id="e5483-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="e5483-134">要设置与 Office 365 高级威胁防护的 SIEM 集成，你必须是全局管理员或已分配安全 & 合规中心的安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="e5483-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="e5483-135">必须为 Microsoft 365 环境启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="e5483-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="e5483-136">若要获取有关此问题的帮助 [，请参阅审核日志打开还是关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="e5483-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5483-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5483-137">See also</span></span>

[<span data-ttu-id="e5483-138">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="e5483-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="e5483-139">Office 365 中为 AIR (自动) 响应</span><span class="sxs-lookup"><span data-stu-id="e5483-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


