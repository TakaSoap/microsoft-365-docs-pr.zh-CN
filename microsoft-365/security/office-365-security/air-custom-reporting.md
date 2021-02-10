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
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175807"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="95fe4-104">适用于 Office 365 的 Microsoft Defender 的自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="95fe4-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95fe4-105">使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="95fe4-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="95fe4-106">但是，某些组织还使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="95fe4-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="95fe4-107">如果你的组织希望将有关自动调查的信息与[](office-365-air.md)此类解决方案集成，可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="95fe4-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="95fe4-108">**适用于**</span><span class="sxs-lookup"><span data-stu-id="95fe4-108">**Applies to**</span></span>
- [<span data-ttu-id="95fe4-109">Microsoft Defender for Office 365 计划 2</span><span class="sxs-lookup"><span data-stu-id="95fe4-109">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="95fe4-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95fe4-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="95fe4-111">使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="95fe4-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="95fe4-112">但是，某些组织还使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="95fe4-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="95fe4-113">如果你的组织希望将有关自动调查的信息与此类解决方案集成，可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="95fe4-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="95fe4-114">资源</span><span class="sxs-lookup"><span data-stu-id="95fe4-114">Resource</span></span>|<span data-ttu-id="95fe4-115">说明</span><span class="sxs-lookup"><span data-stu-id="95fe4-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="95fe4-116">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="95fe4-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="95fe4-117">Office 365 管理活动 API 提供有关 Microsoft 365 和 Azure Active Directory 活动日志中的各种用户、管理员、系统和策略操作和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="95fe4-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="95fe4-118">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="95fe4-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="95fe4-119">Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="95fe4-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="95fe4-120">按照本文中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="95fe4-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="95fe4-121">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="95fe4-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="95fe4-122">可以使用 Office 365 管理活动 API 从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="95fe4-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="95fe4-123">阅读本文可了解有关此工作原理的更多信息。</span><span class="sxs-lookup"><span data-stu-id="95fe4-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="95fe4-124">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="95fe4-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="95fe4-125">大致了解 [常见](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 架构和适用于 Office [365 的 Defender](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 以及威胁调查和响应架构，以了解通过 Office 365 管理活动 API 提供的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="95fe4-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="95fe4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95fe4-126">See also</span></span>

- [<span data-ttu-id="95fe4-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="95fe4-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="95fe4-128">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="95fe4-128">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
