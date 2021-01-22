---
title: 应用监视&报告 - 安全中心
description: 了解如何在组织中深入了解云应用使用。 包括不同类型的应用、其风险级别和警报。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 应用
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930518"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="927a0-105">Microsoft 365 安全中心中的应用监视和报告</span><span class="sxs-lookup"><span data-stu-id="927a0-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="927a0-106">这些报告提供有关云应用在组织中如何使用的更多见解。</span><span class="sxs-lookup"><span data-stu-id="927a0-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="927a0-107">包括不同类型的应用、其风险级别和警报。</span><span class="sxs-lookup"><span data-stu-id="927a0-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="927a0-108">监视有风险的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="927a0-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="927a0-109">**电子邮件保护** 显示处于风险之中的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="927a0-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="927a0-110">可以选择在 Microsoft Defender 安全中心中进一步调查的帐户。</span><span class="sxs-lookup"><span data-stu-id="927a0-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![电子邮件保护卡](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="927a0-112">监视用户授予的应用权限</span><span class="sxs-lookup"><span data-stu-id="927a0-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="927a0-113">**Cloud App Security - OAuth 应用** 列出云应用安全发现的应用，这些应用已由用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="927a0-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="927a0-114">Cloud App Security 的风险目录包括超过 16，000 个应用，这些应用使用 70 多种风险因素进行评估。</span><span class="sxs-lookup"><span data-stu-id="927a0-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="927a0-115">风险因素从常规信息（如应用发布者）开始。</span><span class="sxs-lookup"><span data-stu-id="927a0-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="927a0-116">然后，它移至安全措施和控件，例如应用是支持静态加密还是提供审核日志活动。</span><span class="sxs-lookup"><span data-stu-id="927a0-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth 应用卡](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="927a0-118">监视云应用用户帐户</span><span class="sxs-lookup"><span data-stu-id="927a0-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="927a0-119">**用于查看的云应用帐户** 列出了可能需要关注的帐户。</span><span class="sxs-lookup"><span data-stu-id="927a0-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![用于查看卡片的云应用帐户](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="927a0-121">了解使用哪些云应用</span><span class="sxs-lookup"><span data-stu-id="927a0-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="927a0-122">**发现的云 (类别)** 显示组织中使用的应用类型。</span><span class="sxs-lookup"><span data-stu-id="927a0-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="927a0-123">它链接到 Cloud App Security 中的云发现仪表板。</span><span class="sxs-lookup"><span data-stu-id="927a0-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="927a0-124">有关详细信息，请参阅快速 [入门：使用发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="927a0-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![发现的云应用类别卡片](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="927a0-126">监视用户访问云应用的地方</span><span class="sxs-lookup"><span data-stu-id="927a0-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="927a0-127">**云应用活动位置** 显示用户访问云应用的位置。</span><span class="sxs-lookup"><span data-stu-id="927a0-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![云应用活动位置卡](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="927a0-129">监视基础结构工作负荷的运行状况</span><span class="sxs-lookup"><span data-stu-id="927a0-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="927a0-130">**基础结构运行状况** 显示 Azure Defender 中基础结构工作负荷的运行状况警报。</span><span class="sxs-lookup"><span data-stu-id="927a0-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="927a0-131">Azure Defender 跨本地和云工作负载为 Office 365 提供统一的安全管理和 Defender。</span><span class="sxs-lookup"><span data-stu-id="927a0-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="927a0-132">你可以收集、搜索和分析不同来源的安全数据，包括防火墙和其他合作伙伴解决方案。</span><span class="sxs-lookup"><span data-stu-id="927a0-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="927a0-133">有关详细信息，请参阅 [Azure Defender 文档](https://docs.microsoft.com/azure/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="927a0-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![基础结构运行状况卡](../../media/infrastructure-health.png)
