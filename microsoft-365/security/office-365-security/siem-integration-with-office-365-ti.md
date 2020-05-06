---
title: SIEM 与高级威胁防护的集成
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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 office 365 高级威胁防护以及 Office 365 活动管理 API 中相关的威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035268"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="59d54-103">SIEM 与高级威胁防护的集成</span><span class="sxs-lookup"><span data-stu-id="59d54-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="59d54-104">如果您的组织使用的是安全事件和事件管理（SIEM）服务器，则可以将 Office 365 高级威胁防护与您的 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="59d54-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="59d54-105">SIEM 集成使您能够查看 SIEM 服务器报告中的 Office 365 高级保护检测到的恶意软件或网络钓鱼信息。</span><span class="sxs-lookup"><span data-stu-id="59d54-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="59d54-106">若要设置 SIEM 集成，请使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="59d54-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="59d54-107">Office 365 活动管理 API 检索来自组织的 Microsoft 365 for business 和 Azure Active Directory 活动日志的用户、管理员、系统和策略操作和事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="59d54-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="59d54-108">[Office 365 高级威胁防护架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)使用高级威胁防护功能，因此，如果您的组织具有 Office 365 高级威胁防护计划1或计划2或 Office 365 E5，您仍可以对您的 SIEM 服务器集成使用相同的 API。</span><span class="sxs-lookup"><span data-stu-id="59d54-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="59d54-109">作为我们最近更新的一部分，我们还在 office 365 管理活动 API 中的 Office 365 ATP 计划2中添加了来自自动调查和响应功能的事件。</span><span class="sxs-lookup"><span data-stu-id="59d54-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="59d54-110">除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，它还包含有关调查操作和实体的高级信息。</span><span class="sxs-lookup"><span data-stu-id="59d54-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="59d54-111">SIEM 服务器或其他类似系统应轮询**审核。常规**工作负荷以访问检测事件。</span><span class="sxs-lookup"><span data-stu-id="59d54-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="59d54-112">若要了解详细信息，请参阅[Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="59d54-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="59d54-113">此外， **AuditLogRecordType**的以下值与 OFFICE 365 ATP 事件相关：</span><span class="sxs-lookup"><span data-stu-id="59d54-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="59d54-114">枚举：AuditLogRecordType - 类型：Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="59d54-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="59d54-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="59d54-115">AuditLogRecordType</span></span>

|<span data-ttu-id="59d54-116">值</span><span class="sxs-lookup"><span data-stu-id="59d54-116">Value</span></span>|<span data-ttu-id="59d54-117">成员名称</span><span class="sxs-lookup"><span data-stu-id="59d54-117">Member name</span></span>|<span data-ttu-id="59d54-118">说明</span><span class="sxs-lookup"><span data-stu-id="59d54-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59d54-119">28</span><span class="sxs-lookup"><span data-stu-id="59d54-119">28</span></span>|<span data-ttu-id="59d54-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="59d54-120">ThreatIntelligence</span></span>|<span data-ttu-id="59d54-121">Exchange Online Protection 和 Office 365 高级威胁防护中的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="59d54-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="59d54-122">41</span><span class="sxs-lookup"><span data-stu-id="59d54-122">41</span></span>|<span data-ttu-id="59d54-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="59d54-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="59d54-124">ATP 安全链接从 Office 365 高级威胁防护的阻止时间和阻止覆盖事件。</span><span class="sxs-lookup"><span data-stu-id="59d54-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="59d54-125">47</span><span class="sxs-lookup"><span data-stu-id="59d54-125">47</span></span>|<span data-ttu-id="59d54-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="59d54-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="59d54-127">Office 365 高级威胁防护中的 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的网络钓鱼和恶意软件事件。</span><span class="sxs-lookup"><span data-stu-id="59d54-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="59d54-128">64</span><span class="sxs-lookup"><span data-stu-id="59d54-128">64</span></span>|<span data-ttu-id="59d54-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="59d54-129">AirInvestigation</span></span>|<span data-ttu-id="59d54-130">自动调查和响应事件，例如调查详细信息和 Office 365 高级威胁防护计划2中的相关项目。</span><span class="sxs-lookup"><span data-stu-id="59d54-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="59d54-131">您必须是全局管理员或已为安全 & 合规中心分配的安全管理员角色，才能设置与 Office 365 高级威胁防护的 SIEM 集成。</span><span class="sxs-lookup"><span data-stu-id="59d54-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="59d54-132">必须为你的 Microsoft 365 环境启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="59d54-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="59d54-133">若要获取有关此功能的帮助，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="59d54-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="59d54-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="59d54-134">Related topics</span></span>

[<span data-ttu-id="59d54-135">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="59d54-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="59d54-136">Office 365 中的自动化调查和响应（空气）</span><span class="sxs-lookup"><span data-stu-id="59d54-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="59d54-137">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="59d54-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="59d54-138">安全&amp;合规中心中的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="59d54-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="59d54-139">安全&amp;合规性中心中的权限</span><span class="sxs-lookup"><span data-stu-id="59d54-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
