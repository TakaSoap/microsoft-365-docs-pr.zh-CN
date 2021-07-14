---
title: 开始使用可见性和见解
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 开始使用可见性和见解。
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420030"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="72401-103">开始使用可见性和见解</span><span class="sxs-lookup"><span data-stu-id="72401-103">Get started with visibility and insights</span></span>

><span data-ttu-id="72401-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="72401-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="72401-105">首先从 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance) 上的应用治理仪表板开始。</span><span class="sxs-lookup"><span data-stu-id="72401-105">The first place to get started is the app governance dashboard at [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="72401-106">请注意，要查看应用治理数据，你的登录帐户必须具有[这些应用治理管理员角色](app-governance-get-started.md#administrator-roles)之一。</span><span class="sxs-lookup"><span data-stu-id="72401-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Microsoft 365 合规中心内的应用治理概述页面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="72401-108">你还可以从 **“Microsoft 365 管理中心”>“Microsoft 365 合规中心”>“应用治理”>“概述”** 页访问应用治理仪表板。</span><span class="sxs-lookup"><span data-stu-id="72401-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="72401-109">仪表板上提供的内容</span><span class="sxs-lookup"><span data-stu-id="72401-109">What’s available on the dashboard</span></span>

<span data-ttu-id="72401-110">仪表板包含租户中 Microsoft 365 应用生态系统组件的摘要：</span><span class="sxs-lookup"><span data-stu-id="72401-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="72401-111">**租户摘要**：关键应用和警报类别的计数。</span><span class="sxs-lookup"><span data-stu-id="72401-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="72401-112">**检测和策略警报**：租户中最近的活动警报</span><span class="sxs-lookup"><span data-stu-id="72401-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="72401-113">**数据和资源访问**：聚合应用 API 访问和租户中热门资源的总体使用情况。</span><span class="sxs-lookup"><span data-stu-id="72401-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="72401-114">将鼠标悬停在图表中的每个月份列上可以看到对应的值。</span><span class="sxs-lookup"><span data-stu-id="72401-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="72401-115">**改进应用保护和治理**：建议的操作，例如创建应用使用或权限策略。</span><span class="sxs-lookup"><span data-stu-id="72401-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="72401-116">**按类别排列的热门应用**：按以下类别排序的热门应用：</span><span class="sxs-lookup"><span data-stu-id="72401-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="72401-117">**所有类别**：对所有可用类别进行排序。</span><span class="sxs-lookup"><span data-stu-id="72401-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="72401-118">**高级特权**：高级权限是根据平台机器学习和信号在内部确定的类别。</span><span class="sxs-lookup"><span data-stu-id="72401-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="72401-119">**过度特权**：当应用治理收到的遥测数据表明向某个应用授予的权限在过去 90 天内未被使用时，该应用则处于过度特权状态。</span><span class="sxs-lookup"><span data-stu-id="72401-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="72401-120">应用治理必须至少运行 90 天才能确定是否有任何应用处于过度特权状态。</span><span class="sxs-lookup"><span data-stu-id="72401-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="72401-121">**未验证**：未获得[发布商认证](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)的应用被视为未验证。</span><span class="sxs-lookup"><span data-stu-id="72401-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="72401-122">**仅应用**：[应用程序权限](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)由无需登录用户即可运行的应用使用。</span><span class="sxs-lookup"><span data-stu-id="72401-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="72401-123">有权访问整个租户内的数据的应用可能具有更高的风险。</span><span class="sxs-lookup"><span data-stu-id="72401-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="72401-124">**新应用**：过去 7 天内注册的新 Microsoft 365 应用。</span><span class="sxs-lookup"><span data-stu-id="72401-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="72401-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="72401-125">Next step</span></span>

<span data-ttu-id="72401-126">[获取有关特定应用的详细见解](app-governance-visibility-insights-view-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="72401-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
