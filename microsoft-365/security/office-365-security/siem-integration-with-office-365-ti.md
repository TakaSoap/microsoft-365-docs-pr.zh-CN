---
title: SIEM 与 Microsoft Defender for Office 365 的集成
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
description: 将组织的 SIEM 服务器与 Microsoft Defender for Office 365 以及 Office 365 活动管理 API 中相关的威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6253ed0133bf53bdbeca71bb595a850e25441311
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561691"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="0ded6-103">SIEM 与 Microsoft Defender for Office 365 的集成</span><span class="sxs-lookup"><span data-stu-id="0ded6-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0ded6-104">如果您的组织使用安全信息和事件管理 (SIEM) server，则可以将 Microsoft Defender for Office 365 与您的 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="0ded6-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="0ded6-105">您可以使用 [Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)设置这种集成。</span><span class="sxs-lookup"><span data-stu-id="0ded6-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="0ded6-106">通过 SIEM 集成，您可以查看 SIEM 服务器报告中的 Microsoft Defender for Office 365 检测到的恶意软件或网络钓鱼诈骗的信息。</span><span class="sxs-lookup"><span data-stu-id="0ded6-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="0ded6-107">若要查看与 Microsoft Defender for Office 365 的 SIEM 集成示例，请参阅 [技术社区博客：使用适用于 office 365 的 Defender 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="0ded6-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="0ded6-108">若要了解有关 Office 365 管理 Api 的详细信息，请参阅 [office 365 管理 api 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="0ded6-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="0ded6-109">SIEM 集成的工作原理</span><span class="sxs-lookup"><span data-stu-id="0ded6-109">How SIEM integration works</span></span>

<span data-ttu-id="0ded6-110">Office 365 活动管理 API 检索组织的 Microsoft 365 和 Azure Active Directory 活动日志中的用户、管理员、系统和策略操作以及事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0ded6-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="0ded6-111">如果你的组织具有 Microsoft Defender for Office 365 Plan 1 或2或 Office 365 E5，则可以使用 [Microsoft defender For office 365 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="0ded6-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="0ded6-112">最近， [Microsoft Defender For office 365 计划 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 中的自动调查和响应功能的事件已添加到 Office 365 管理活动 API 中。</span><span class="sxs-lookup"><span data-stu-id="0ded6-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="0ded6-113">除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，API 还包含有关调查操作和实体的高级信息。</span><span class="sxs-lookup"><span data-stu-id="0ded6-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="0ded6-114">SIEM 服务器或其他类似的系统会轮询 **审核。常规** 工作负荷以访问检测事件。</span><span class="sxs-lookup"><span data-stu-id="0ded6-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="0ded6-115">若要了解详细信息，请参阅 [Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="0ded6-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="0ded6-116">枚举：AuditLogRecordType - 类型：Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="0ded6-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="0ded6-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="0ded6-117">AuditLogRecordType</span></span>

<span data-ttu-id="0ded6-118">下表汇总了与 Microsoft Defender for Office 365 事件相关的 **AuditLogRecordType** 的值：</span><span class="sxs-lookup"><span data-stu-id="0ded6-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="0ded6-119">值</span><span class="sxs-lookup"><span data-stu-id="0ded6-119">Value</span></span>|<span data-ttu-id="0ded6-120">成员名称</span><span class="sxs-lookup"><span data-stu-id="0ded6-120">Member name</span></span>|<span data-ttu-id="0ded6-121">说明</span><span class="sxs-lookup"><span data-stu-id="0ded6-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="0ded6-122">28</span><span class="sxs-lookup"><span data-stu-id="0ded6-122">28</span></span>|<span data-ttu-id="0ded6-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="0ded6-123">ThreatIntelligence</span></span>|<span data-ttu-id="0ded6-124">来自 Exchange Online Protection 和 Microsoft Defender for Office 365 的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="0ded6-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="0ded6-125">41</span><span class="sxs-lookup"><span data-stu-id="0ded6-125">41</span></span>|<span data-ttu-id="0ded6-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="0ded6-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="0ded6-127">Microsoft Defender for Office 365 中的安全链接时间段和阻止替代事件。</span><span class="sxs-lookup"><span data-stu-id="0ded6-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="0ded6-128">47</span><span class="sxs-lookup"><span data-stu-id="0ded6-128">47</span></span>|<span data-ttu-id="0ded6-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="0ded6-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="0ded6-130">Microsoft Defender for Office 365 中的 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="0ded6-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="0ded6-131">64</span><span class="sxs-lookup"><span data-stu-id="0ded6-131">64</span></span>|<span data-ttu-id="0ded6-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="0ded6-132">AirInvestigation</span></span>|<span data-ttu-id="0ded6-133">来自 Microsoft Defender for Office 365 计划2的自动化调查和响应事件，如调查详细信息和相关项目。</span><span class="sxs-lookup"><span data-stu-id="0ded6-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="0ded6-134">您必须是全局管理员或将安全管理员角色分配给安全 & 合规性中心，才能设置 SIEM 与 Microsoft Defender for Office 365 的集成。</span><span class="sxs-lookup"><span data-stu-id="0ded6-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span><br/><span data-ttu-id="0ded6-135">必须为你的 Microsoft 365 环境启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="0ded6-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="0ded6-136">若要获取有关此功能的帮助，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0ded6-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ded6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ded6-137">See also</span></span>

[<span data-ttu-id="0ded6-138">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="0ded6-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="0ded6-139">Office 365 中的自动调查和响应 (空中) </span><span class="sxs-lookup"><span data-stu-id="0ded6-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

