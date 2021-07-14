---
title: 了解可见性见解
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
description: 了解可见性和见解。
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420028"
---
# <a name="learn-about-visibility-and-insights"></a><span data-ttu-id="3f7f8-103">了解可见性见解</span><span class="sxs-lookup"><span data-stu-id="3f7f8-103">Learn about visibility and insights</span></span>

><span data-ttu-id="3f7f8-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="3f7f8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3f7f8-105">通过 Microsoft 应用治理，你可以快速获得关于 Microsoft 365 应用程序生态系统的可见性以及有意义的见解。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-105">With Microsoft app governance, you can quickly gain visibility and meaningful insights on your Microsoft 365 application ecosystem.</span></span> <span data-ttu-id="3f7f8-106">从应用治理仪表板开始，该仪表板提供租户中需要管理员注意的警报和应用的高级别摘要。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-106">You start from the app governance dashboard that provides a high-level summary of the alerts and apps in your tenant that require administrator attention.</span></span>

<span data-ttu-id="3f7f8-107">通过应用治理可见性和见解，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="3f7f8-107">With app governance visibility and insights, you can see:</span></span>

- <span data-ttu-id="3f7f8-108">通过 Microsoft Graph API 访问 Microsoft 365 数据，并且已启用 OAuth 的应用列表。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-108">A list of the OAuth-enabled apps that access Microsoft 365 data via Microsoft Graph APIs.</span></span>
- <span data-ttu-id="3f7f8-109">有关应用活动的丰富视图，以便你可以对它们做出反应或响应。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-109">A rich view on app activities so that you can react or respond to them.</span></span>

>[!Note]
><span data-ttu-id="3f7f8-110">应用治理中不会显示未授予 Microsoft 365 资源访问权限的仅 Azure 应用。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-110">Azure-only apps that are not granted permissions to access Microsoft 365 resources are not displayed in app governance.</span></span>
>

<span data-ttu-id="3f7f8-111">有关获得可见性和见解所需的管理员角色的概述，请参阅[管理员角色](app-governance-get-started.md#administrator-roles)。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-111">See [administrator roles](app-governance-get-started.md#administrator-roles) for an overview of required administrator roles for visibility and insights.</span></span>

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

<span data-ttu-id="3f7f8-112">通过应用治理，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="3f7f8-112">With app governance, you can see:</span></span>

- <span data-ttu-id="3f7f8-113">列出所有见解的仪表板。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-113">A dashboard of all insights.</span></span>
- <span data-ttu-id="3f7f8-114">具有工作负载和用户级别见解的单一及所有应用访问的数据。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-114">Data accessed by single and all apps with workload and user level insights.</span></span>
- <span data-ttu-id="3f7f8-115">应用信息和元数据，例如权限、注册日期和认证。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-115">App information and metadata, such as permissions, registration date, and certification.</span></span>
- <span data-ttu-id="3f7f8-116">发布者信息和元数据，例如名称和验证状态。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-116">Publisher information and metadata, such as name and verification status.</span></span>
- <span data-ttu-id="3f7f8-117">整个租户中对热门资源（电子邮件和文件）的使用情况。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-117">Usage of top resources (emails and files) across the tenant.</span></span>
- <span data-ttu-id="3f7f8-118">有关以下内容的见解：</span><span class="sxs-lookup"><span data-stu-id="3f7f8-118">Insights on:</span></span>

  - <span data-ttu-id="3f7f8-119">高级特权应用。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-119">High-privileged apps.</span></span>
  - <span data-ttu-id="3f7f8-120">过度特权应用。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-120">Overprivileged apps.</span></span>
  - <span data-ttu-id="3f7f8-121">高使用率的应用。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-121">High-usage apps.</span></span>
  - <span data-ttu-id="3f7f8-122">特定应用可以访问其数据的前几位同意用户。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-122">Top consented users whose data a specific app can access.</span></span>
  - <span data-ttu-id="3f7f8-123">拥有特定应用可以访问的数据的优先帐户。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-123">Priority accounts who have data that a specific app can access.</span></span>

- <span data-ttu-id="3f7f8-124">访问应用的用户的累积视图。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-124">A cumulative view of users accessing apps.</span></span>
- <span data-ttu-id="3f7f8-125">警报见解。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-125">Alerts insights.</span></span>
- <span data-ttu-id="3f7f8-126">策略列表见解。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-126">Policy list insights.</span></span>
<span data-ttu-id="3f7f8-127"><!--></span><span class="sxs-lookup"><span data-stu-id="3f7f8-127"><!--></span></span>
- <span data-ttu-id="3f7f8-128">在应用治理门户中的 MCAS 中创建的策略。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-128">Policies created in MCAS in the app governance portal.</span></span>
-->
- <span data-ttu-id="3f7f8-129">针对 MCAS 中生成的 OAuth 应用的警报（位于应用治理门户中）。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-129">Alerts for OAuth apps generated in MCAS, in the app governance portal.</span></span>

<span data-ttu-id="3f7f8-130">还可以：</span><span class="sxs-lookup"><span data-stu-id="3f7f8-130">You can also:</span></span>

- <span data-ttu-id="3f7f8-131">深入探索单个应用（应用页面）及其所有相关见解。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-131">Drill down to a single app (app page) with all its associated insights.</span></span>
- <span data-ttu-id="3f7f8-132">深入探索数据排名靠前的用户以及单个应用中的优先帐户。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-132">Drill-down into top users by data, and priority accounts within a single app.</span></span>

## <a name="next-step"></a><span data-ttu-id="3f7f8-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3f7f8-133">Next step</span></span>

[<span data-ttu-id="3f7f8-134">开始使用应用程序见解。</span><span class="sxs-lookup"><span data-stu-id="3f7f8-134">Get started with application insights.</span></span>](app-governance-visibility-insights-get-started.md)
