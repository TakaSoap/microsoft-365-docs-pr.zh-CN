---
title: 应用程序监控 & 报告-安全中心
description: 了解如何深入了解你的组织中的云应用使用情况。 包括不同类型的应用程序、风险级别和警报。
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcb7997c8c248c2b4e7d16902b6ebdd7756ccd0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846624"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="92a74-105">Microsoft 365 安全中心中的应用程序监控和报告</span><span class="sxs-lookup"><span data-stu-id="92a74-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92a74-106">这些报告可更深入地了解在您的组织中使用云应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="92a74-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="92a74-107">包括不同类型的应用程序、风险级别和警报。</span><span class="sxs-lookup"><span data-stu-id="92a74-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="92a74-108">监视有风险的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="92a74-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="92a74-109">**电子邮件保护** 显示有风险的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="92a74-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="92a74-110">你可以选择要在 Microsoft Defender 安全中心中进一步调查的帐户。</span><span class="sxs-lookup"><span data-stu-id="92a74-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![电子邮件保护卡](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="92a74-112">监视用户授予的应用程序权限</span><span class="sxs-lookup"><span data-stu-id="92a74-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="92a74-113">**云应用安全-OAuth 应用** 列出由用户授予权限的云应用安全发现的应用程序。</span><span class="sxs-lookup"><span data-stu-id="92a74-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="92a74-114">云应用安全性风险目录包含16000个以上使用超过70个风险因素评估的应用程序。</span><span class="sxs-lookup"><span data-stu-id="92a74-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="92a74-115">风险因素从一般信息（如应用程序发布者）开始。</span><span class="sxs-lookup"><span data-stu-id="92a74-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="92a74-116">然后，它将移动到安全措施和控件，例如，应用程序是否支持静态加密或提供用户活动的审核日志。</span><span class="sxs-lookup"><span data-stu-id="92a74-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![云应用安全 OAuth 应用程序卡片](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="92a74-118">监视云应用程序用户帐户</span><span class="sxs-lookup"><span data-stu-id="92a74-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="92a74-119">**适用于审阅的云应用帐户** 列表可能需要注意的帐户。</span><span class="sxs-lookup"><span data-stu-id="92a74-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![审阅卡片的云应用程序帐户](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="92a74-121">了解使用的是哪些云应用程序</span><span class="sxs-lookup"><span data-stu-id="92a74-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="92a74-122">**发现的云应用 (类别)** 显示您的组织中使用的应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="92a74-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="92a74-123">它链接到 Cloud App Security 中的云发现仪表板。</span><span class="sxs-lookup"><span data-stu-id="92a74-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="92a74-124">有关详细信息，请参阅 [快速入门：使用已发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="92a74-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![发现的云应用类别卡片](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="92a74-126">监视用户访问云应用程序的位置</span><span class="sxs-lookup"><span data-stu-id="92a74-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="92a74-127">**云应用活动位置** 显示用户在访问云应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="92a74-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![云应用活动位置卡片](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="92a74-129">监视基础架构工作负载的运行状况</span><span class="sxs-lookup"><span data-stu-id="92a74-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="92a74-130">**基础结构运行状况** 显示 Azure Defender 中的基础结构工作负荷的运行状况状态警报。</span><span class="sxs-lookup"><span data-stu-id="92a74-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender\*.</span></span>

<span data-ttu-id="92a74-131">Azure Defender \* 在本地和云工作负载中提供了统一的 Office 365 安全管理和 Defender。</span><span class="sxs-lookup"><span data-stu-id="92a74-131">Azure Defender\* provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="92a74-132">您可以从不同的源中收集、搜索和分析安全数据，包括防火墙和其他合作伙伴解决方案。</span><span class="sxs-lookup"><span data-stu-id="92a74-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="92a74-133">有关详细信息，请参阅 [Azure Defender \* 文档](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="92a74-133">For more information, see [Azure Defender\* Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基础结构运行状况卡片](../../media/infrastructure-health.png)
