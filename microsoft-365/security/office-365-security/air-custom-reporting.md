---
title: 将自定义报告解决方案与自动调查和响应结合使用
keywords: SIEM、API、AIR、autoIR、ATP、自动调查、集成、自定义报告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解如何将自动调查和响应与自定义或第三方报告解决方案集成。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 9bc5de44700b7f1b7207f8fae002adcb55d32841
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446679"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="d2501-104">将管理活动 API 用于自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="d2501-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d2501-105">使用 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)，可以获取 [有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d2501-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="d2501-106">但是，一些组织也使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="d2501-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="d2501-107">如果您的组织想要使用此解决方案集成有关自动调查的信息，您可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="d2501-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="d2501-108">使用以下资源对此进行设置：</span><span class="sxs-lookup"><span data-stu-id="d2501-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="d2501-109">资源</span><span class="sxs-lookup"><span data-stu-id="d2501-109">Resource</span></span>|<span data-ttu-id="d2501-110">说明</span><span class="sxs-lookup"><span data-stu-id="d2501-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="d2501-111">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="d2501-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="d2501-112">Office 365 管理活动 API 提供了有关来自 Microsoft 365 和 Azure Active Directory 活动日志的各种用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="d2501-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="d2501-113">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="d2501-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="d2501-114">Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="d2501-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="d2501-115">请按照本文中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="d2501-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="d2501-116">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="d2501-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="d2501-117">您可以使用 Office 365 管理活动 API，从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="d2501-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="d2501-118">阅读本文以了解有关如何工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d2501-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="d2501-119">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="d2501-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="d2501-120">获取 [常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 和 [office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。</span><span class="sxs-lookup"><span data-stu-id="d2501-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="d2501-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2501-121">See also</span></span>

- [<span data-ttu-id="d2501-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="d2501-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="d2501-123">Microsoft 365 Defender 中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="d2501-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
