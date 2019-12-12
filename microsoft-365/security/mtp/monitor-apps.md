---
title: Microsoft 365 安全中心中的应用程序监控和报告
description: 介绍如何能够深入了解组织中的云应用程序使用情况
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 8688088508f57fca1ba62dd41c28cd204df5c05e
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910257"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="4e9cb-104">Microsoft 365 安全中心中的应用程序监控和报告</span><span class="sxs-lookup"><span data-stu-id="4e9cb-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="4e9cb-105">这些报告可更深入地了解如何在组织中使用云应用程序，包括哪些类型的应用、风险级别和警报。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="4e9cb-106">监视电子邮件帐户的风险</span><span class="sxs-lookup"><span data-stu-id="4e9cb-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="4e9cb-107">**电子邮件保护**显示有风险的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="4e9cb-108">您可以单击某个帐户以在 Microsoft Defender 安全中心中进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![电子邮件保护卡](../images/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="4e9cb-110">监视用户授予的应用程序权限</span><span class="sxs-lookup"><span data-stu-id="4e9cb-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="4e9cb-111">**云应用安全-OAuth 应用**列出由用户授予权限的云应用安全发现的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="4e9cb-112">云应用安全性风险目录包含16000个以上使用超过70个风险因素评估的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="4e9cb-113">风险因素从一般信息（如应用程序发布者）开始，到安全措施和控件，例如应用程序是否支持在 rest 上进行加密或提供用户活动的审核日志。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![云应用安全 OAuth 应用程序卡片](../images/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="4e9cb-115">监视云应用程序用户帐户</span><span class="sxs-lookup"><span data-stu-id="4e9cb-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="4e9cb-116">**适用于审阅的云应用帐户**列表可能需要注意的帐户。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![审阅卡片的云应用程序帐户](../images/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="4e9cb-118">了解使用的是哪些云应用程序</span><span class="sxs-lookup"><span data-stu-id="4e9cb-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="4e9cb-119">已**发现的云应用程序（类别）** 显示在您的组织中使用的是哪些类型的应用程序，以及云发现仪表板在云应用安全中的链接。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="4e9cb-120">有关详细信息，请参阅[快速入门：使用已发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![发现的云应用类别卡片](../images/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="4e9cb-122">监视用户访问云应用程序的位置</span><span class="sxs-lookup"><span data-stu-id="4e9cb-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="4e9cb-123">**云应用活动位置**显示用户在访问云应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![云应用活动位置卡片](../images/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="4e9cb-125">监视基础架构工作负载的运行状况</span><span class="sxs-lookup"><span data-stu-id="4e9cb-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="4e9cb-126">**基础结构运行状况**在 Azure 安全中心中显示基础结构工作负荷的运行状况状态警报。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="4e9cb-127">Azure 安全中心在内部部署和云工作负载中提供统一的安全管理和高级威胁保护。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="4e9cb-128">您可以从各种源（包括防火墙和其他合作伙伴解决方案）收集、搜索和分析安全数据。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="4e9cb-129">有关详细信息，请参阅[Azure 安全中心文档](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="4e9cb-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基础结构运行状况卡片](../images/infrastructure-health.png)
