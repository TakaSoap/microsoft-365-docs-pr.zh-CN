---
title: 使用自动调查和响应的自定义报告解决方案
keywords: SIEM， API， AIR， autoIR， ATP， 自动调查， 集成， 自定义报告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解如何将自动调查和响应与自定义或第三方报告解决方案集成。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287133"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="13741-104">Microsoft Defender for Office 365 的自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="13741-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="13741-105">使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="13741-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="13741-106">但是，某些组织还使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="13741-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="13741-107">如果你的组织想要将有关自动调查的信息与[](office-365-air.md)此类解决方案集成，可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="13741-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="13741-108">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="13741-108">**Applies to**</span></span>
- [<span data-ttu-id="13741-109">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="13741-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="13741-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13741-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="13741-111">使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="13741-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="13741-112">但是，某些组织还使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="13741-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="13741-113">如果你的组织想要将有关自动调查的信息与此类解决方案集成，可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="13741-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="13741-114">资源</span><span class="sxs-lookup"><span data-stu-id="13741-114">Resource</span></span>|<span data-ttu-id="13741-115">说明</span><span class="sxs-lookup"><span data-stu-id="13741-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="13741-116">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="13741-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="13741-117">Office 365 管理活动 API 提供有关 Microsoft 365 和 Azure Active Directory 活动日志中的各种用户、管理员、系统和策略操作和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="13741-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="13741-118">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="13741-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="13741-119">Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="13741-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="13741-120">按照本文中的步骤设置此操作。</span><span class="sxs-lookup"><span data-stu-id="13741-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="13741-121">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="13741-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="13741-122">可以使用 Office 365 管理活动 API 从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="13741-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="13741-123">阅读本文可了解有关此工作原理的更多信息。</span><span class="sxs-lookup"><span data-stu-id="13741-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="13741-124">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="13741-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="13741-125">大致了解 [常见](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 架构和 [Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 以及威胁调查和响应架构，以了解通过 Office 365 管理活动 API 提供的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="13741-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="13741-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13741-126">See also</span></span>

- [<span data-ttu-id="13741-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="13741-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="13741-128">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="13741-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)
