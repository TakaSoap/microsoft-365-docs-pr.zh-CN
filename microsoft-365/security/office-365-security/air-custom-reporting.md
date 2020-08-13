---
title: 将自定义报告解决方案与自动调查和响应结合使用
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
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
ms.collection: M365-security-compliance
description: 了解如何将自动调查和响应与自定义或第三方报告解决方案集成。
ms.openlocfilehash: cd7eb016ecd250eef56039e0135237c1caebadf8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656893"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="79c07-104">将管理活动 API 用于自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="79c07-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="79c07-105">使用[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)，可以获取[有关自动调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="79c07-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="79c07-106">但是，一些组织也使用自定义或第三方报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="79c07-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="79c07-107">如果您的组织想要使用此解决方案集成有关自动调查的信息，您可以使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="79c07-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="79c07-108">使用以下资源对此进行设置：</span><span class="sxs-lookup"><span data-stu-id="79c07-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="79c07-109">资源</span><span class="sxs-lookup"><span data-stu-id="79c07-109">Resource</span></span>|<span data-ttu-id="79c07-110">说明</span><span class="sxs-lookup"><span data-stu-id="79c07-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="79c07-111">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="79c07-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="79c07-112">Office 365 管理活动 API 提供了有关来自 Microsoft 365 和 Azure Active Directory 活动日志的各种用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="79c07-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="79c07-113">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="79c07-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="79c07-114">Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="79c07-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="79c07-115">请按照本文中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="79c07-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="79c07-116">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="79c07-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="79c07-117">您可以使用 Office 365 管理活动 API，从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="79c07-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="79c07-118">阅读本文以了解有关如何工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="79c07-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="79c07-119">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="79c07-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="79c07-120">获取[常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和[office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。</span><span class="sxs-lookup"><span data-stu-id="79c07-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="related-articles"></a><span data-ttu-id="79c07-121">相关文章</span><span class="sxs-lookup"><span data-stu-id="79c07-121">Related articles</span></span>

- [<span data-ttu-id="79c07-122">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="79c07-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="79c07-123">了解 Microsoft 威胁防护中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="79c07-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)