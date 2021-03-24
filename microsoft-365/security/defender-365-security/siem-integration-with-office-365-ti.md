---
title: SIEM 与 Microsoft Defender for Office 365 集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与适用于 Office 365 的 Microsoft Defender 以及 Office 365 活动管理 API 中的相关威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055509"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="2aecd-103">SIEM 与 Microsoft Defender for Office 365 集成</span><span class="sxs-lookup"><span data-stu-id="2aecd-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2aecd-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2aecd-104">**Applies to**</span></span>
- [<span data-ttu-id="2aecd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2aecd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2aecd-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2aecd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2aecd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2aecd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2aecd-108">如果你的组织使用 SIEM (安全信息和事件) ，你可以将适用于 Office 365 的 Microsoft Defender 与 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="2aecd-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="2aecd-109">可以使用 Office [365](/office/office-365-management-api/office-365-management-activity-api-reference)活动管理 API 设置此集成。</span><span class="sxs-lookup"><span data-stu-id="2aecd-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="2aecd-110">SIEM 集成使你能够在 SIEM 服务器报告中查看信息，如 Microsoft Defender for Office 365 检测到的恶意软件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="2aecd-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="2aecd-111">若要查看 SIEM 与 Microsoft Defender for Office 365 集成的示例，请参阅技术社区 [博客：使用适用于 Office 365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)的 Defender 提高 SOC 的有效性和 O365 管理 API。</span><span class="sxs-lookup"><span data-stu-id="2aecd-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="2aecd-112">若要详细了解 Office 365 管理 API，请参阅 [Office 365 管理 API 概述](/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="2aecd-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="2aecd-113">SIEM 集成的工作原理</span><span class="sxs-lookup"><span data-stu-id="2aecd-113">How SIEM integration works</span></span>

<span data-ttu-id="2aecd-114">Office 365 活动管理 API 从组织的 Microsoft 365 和 Azure Active Directory 活动日志中检索有关用户、管理员、系统和策略操作和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="2aecd-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="2aecd-115">如果你的组织拥有 Microsoft Defender for Office 365 计划 1 或 2，或 Office 365 E5，可以使用 [Microsoft Defender for Office 365 架构](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="2aecd-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="2aecd-116">最近，来自 Microsoft Defender for Office [365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 计划 2 中的自动调查和响应功能的事件已添加到 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="2aecd-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="2aecd-117">除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，API 还包含有关调查操作和实体的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="2aecd-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="2aecd-118">SIEM 服务器或其他类似的系统轮询 **audit.general** 工作负载以访问检测事件。</span><span class="sxs-lookup"><span data-stu-id="2aecd-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="2aecd-119">若要了解更多信息，请参阅 [Office 365 管理 API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="2aecd-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="2aecd-120">枚举：AuditLogRecordType - 类型：Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="2aecd-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="2aecd-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="2aecd-121">AuditLogRecordType</span></span>

<span data-ttu-id="2aecd-122">下表汇总了与 Microsoft Defender for Office 365 事件相关的 **AuditLogRecordType** 值：</span><span class="sxs-lookup"><span data-stu-id="2aecd-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="2aecd-123">值</span><span class="sxs-lookup"><span data-stu-id="2aecd-123">Value</span></span>|<span data-ttu-id="2aecd-124">成员名称</span><span class="sxs-lookup"><span data-stu-id="2aecd-124">Member name</span></span>|<span data-ttu-id="2aecd-125">说明</span><span class="sxs-lookup"><span data-stu-id="2aecd-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="2aecd-126">28</span><span class="sxs-lookup"><span data-stu-id="2aecd-126">28</span></span>|<span data-ttu-id="2aecd-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="2aecd-127">ThreatIntelligence</span></span>|<span data-ttu-id="2aecd-128">Exchange Online Protection 和 Microsoft Defender for Office 365 中的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="2aecd-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2aecd-129">41</span><span class="sxs-lookup"><span data-stu-id="2aecd-129">41</span></span>|<span data-ttu-id="2aecd-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="2aecd-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="2aecd-131">来自 Microsoft Defender for Office 365 的安全链接阻止时间和阻止覆盖事件。</span><span class="sxs-lookup"><span data-stu-id="2aecd-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2aecd-132">47</span><span class="sxs-lookup"><span data-stu-id="2aecd-132">47</span></span>|<span data-ttu-id="2aecd-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="2aecd-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="2aecd-134">来自 Microsoft Defender for Office 365 的 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中文件的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="2aecd-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2aecd-135">64</span><span class="sxs-lookup"><span data-stu-id="2aecd-135">64</span></span>|<span data-ttu-id="2aecd-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="2aecd-136">AirInvestigation</span></span>|<span data-ttu-id="2aecd-137">来自 Microsoft Defender for Office 365 计划 2 的自动调查和响应事件，如调查详细信息和相关项目。</span><span class="sxs-lookup"><span data-stu-id="2aecd-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="2aecd-138">你必须是全局管理员或分配有安全与合规中心的安全&角色，才能设置 SIEM 与 Microsoft Defender for Office 365 的集成。</span><span class="sxs-lookup"><span data-stu-id="2aecd-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="2aecd-139">必须为 Microsoft 365 环境启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="2aecd-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="2aecd-140">若要获取有关此内容的帮助，请参阅打开 [审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="2aecd-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2aecd-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aecd-141">See also</span></span>

[<span data-ttu-id="2aecd-142">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="2aecd-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="2aecd-143">Office 365 中的 AIR (自动调查和) 响应</span><span class="sxs-lookup"><span data-stu-id="2aecd-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)