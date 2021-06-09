---
title: 数据丢失防护警报仪表板入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 开始定义和管理数据丢失防护策略的警报。
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843862"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="a8b78-103">数据丢失防护警报仪表板入门</span><span class="sxs-lookup"><span data-stu-id="a8b78-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="a8b78-104">DLP 策略 (数据丢失) 采取保护措施，防止意外共享敏感项目。</span><span class="sxs-lookup"><span data-stu-id="a8b78-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="a8b78-105">对敏感项目采取操作时，可以通过配置 DLP 警报来通知您。</span><span class="sxs-lookup"><span data-stu-id="a8b78-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="a8b78-106">本文演示如何定义 DLP 策略中链接到数据丢失防护的丰富警报 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="a8b78-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="a8b78-107">你将了解如何在合规性中心内使用[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)警报管理Microsoft 365查看 DLP 策略违反的警报、[事件](https://compliance.microsoft.com/)和关联元数据。</span><span class="sxs-lookup"><span data-stu-id="a8b78-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="a8b78-108">如果您是 DLP 警报的新增用户，则应该查看了解数据丢失防护 [警报仪表板](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="a8b78-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a8b78-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="a8b78-109">Before you begin</span></span>

<span data-ttu-id="a8b78-110">在开始之前，请确保你具有必要的先决条件：</span><span class="sxs-lookup"><span data-stu-id="a8b78-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="a8b78-111">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="a8b78-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="a8b78-112">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="a8b78-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="a8b78-113">角色</span><span class="sxs-lookup"><span data-stu-id="a8b78-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="a8b78-114">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="a8b78-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="a8b78-115">DLP 的所有符合条件的租户Office 365 DLP 警报管理仪表板。</span><span class="sxs-lookup"><span data-stu-id="a8b78-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="a8b78-116">若要开始，你应该有资格使用 Office 365 DLP Exchange Online SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="a8b78-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="a8b78-117">有关 DLP 的许可要求Office 365，请参阅哪些许可证为用户提供从服务中获益[的权利？。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="a8b78-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="a8b78-118">使用符合[使用 DLP](endpoint-dlp-learn-about.md)条件Teams终结点[DLP](dlp-microsoft-teams.md)的客户将在 DLP 警报管理仪表板中Teams终结点 DLP 策略警报和 DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="a8b78-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="a8b78-119">内容 **预览** 功能仅适用于以下许可证：</span><span class="sxs-lookup"><span data-stu-id="a8b78-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="a8b78-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b78-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="a8b78-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a8b78-121">Office 365 (E5)</span></span>
- <span data-ttu-id="a8b78-122">高级合规性 (E5) 加载项</span><span class="sxs-lookup"><span data-stu-id="a8b78-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="a8b78-123">Microsoft 365 E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="a8b78-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="a8b78-124">Microsft 365 E5/A5 合规性</span><span class="sxs-lookup"><span data-stu-id="a8b78-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="a8b78-125">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="a8b78-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="a8b78-126">**单事件警报** 配置：拥有 E1、F1 或 G1 订阅、E3 或 G3 订阅的组织只能在每次活动发生时触发警报时创建警报策略。</span><span class="sxs-lookup"><span data-stu-id="a8b78-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="a8b78-127">**聚合警报配置**：若要根据阈值配置聚合警报策略，您必须以下许可配置之一：</span><span class="sxs-lookup"><span data-stu-id="a8b78-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="a8b78-128">E5 或 G5 订阅</span><span class="sxs-lookup"><span data-stu-id="a8b78-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="a8b78-129">包含以下功能之一的 E1、F1 或 G1 订阅或 E3 或 G3 订阅：</span><span class="sxs-lookup"><span data-stu-id="a8b78-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="a8b78-130">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="a8b78-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="a8b78-131">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="a8b78-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="a8b78-132">Microsoft 365电子数据展示和审核加载项许可证</span><span class="sxs-lookup"><span data-stu-id="a8b78-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="a8b78-133">角色</span><span class="sxs-lookup"><span data-stu-id="a8b78-133">Roles</span></span>


<span data-ttu-id="a8b78-134">如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="a8b78-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="a8b78-135">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="a8b78-135">Compliance Administrator</span></span>
- <span data-ttu-id="a8b78-136">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="a8b78-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="a8b78-137">安全管理员</span><span class="sxs-lookup"><span data-stu-id="a8b78-137">Security Administrator</span></span>
- <span data-ttu-id="a8b78-138">安全操作员</span><span class="sxs-lookup"><span data-stu-id="a8b78-138">Security Operator</span></span>
- <span data-ttu-id="a8b78-139">安全读取者</span><span class="sxs-lookup"><span data-stu-id="a8b78-139">Security Reader</span></span>

<span data-ttu-id="a8b78-140">若要访问 DLP 警报管理仪表板，您需要：</span><span class="sxs-lookup"><span data-stu-id="a8b78-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="a8b78-141">管理警报</span><span class="sxs-lookup"><span data-stu-id="a8b78-141">Manage alerts</span></span>

<span data-ttu-id="a8b78-142">以及以下两个角色之一：</span><span class="sxs-lookup"><span data-stu-id="a8b78-142">and either of these two roles:</span></span>

- <span data-ttu-id="a8b78-143">DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="a8b78-143">DLP Compliance Management</span></span>
- <span data-ttu-id="a8b78-144">View-Only DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="a8b78-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="a8b78-145">若要访问内容预览功能和匹配敏感内容和上下文功能，你必须是以下组的成员：</span><span class="sxs-lookup"><span data-stu-id="a8b78-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="a8b78-146">内容资源管理器内容查看器角色组</span><span class="sxs-lookup"><span data-stu-id="a8b78-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="a8b78-147">已预分配数据分类内容查看器角色。</span><span class="sxs-lookup"><span data-stu-id="a8b78-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="a8b78-148">DLP 警报配置</span><span class="sxs-lookup"><span data-stu-id="a8b78-148">DLP alert configuration</span></span>

<span data-ttu-id="a8b78-149">若要了解如何在 DLP 策略中配置警报，请参阅从数据丢失防护[开始。](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="a8b78-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="a8b78-150">聚合事件警报配置</span><span class="sxs-lookup"><span data-stu-id="a8b78-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="a8b78-151">如果您的组织已获得 [聚合警报配置](#licensing-for-alert-configuration-options)选项的许可，则当您创建或编辑 DLP 策略时，将看到这些选项。</span><span class="sxs-lookup"><span data-stu-id="a8b78-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

<span data-ttu-id="a8b78-153">通过此配置，您可以设置一个策略，以在活动符合策略条件或超出特定阈值时（基于活动数或根据已过滤数据的量）生成警报。</span><span class="sxs-lookup"><span data-stu-id="a8b78-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="a8b78-154">单个事件警报配置</span><span class="sxs-lookup"><span data-stu-id="a8b78-154">Single event alert configuration</span></span>

<span data-ttu-id="a8b78-155">如果您的组织已获得单事件 [警报](#licensing-for-alert-configuration-options)配置选项的许可，则当您创建或编辑 DLP 策略时，将看到这些选项。</span><span class="sxs-lookup"><span data-stu-id="a8b78-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="a8b78-156">使用此选项可创建每次发生 DLP 规则匹配时都会触发的警报。</span><span class="sxs-lookup"><span data-stu-id="a8b78-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="a8b78-158">调查 DLP 警报</span><span class="sxs-lookup"><span data-stu-id="a8b78-158">Investigate a DLP alert</span></span>

<span data-ttu-id="a8b78-159">使用 DLP 警报管理仪表板：</span><span class="sxs-lookup"><span data-stu-id="a8b78-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="a8b78-160">In the [Microsoft 365 compliance center，](https://www.compliance.microsoft.com)go to **Data Loss Prevention**.</span><span class="sxs-lookup"><span data-stu-id="a8b78-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="a8b78-161">选择" **警报"** 选项卡以查看 DLP 警报仪表板。</span><span class="sxs-lookup"><span data-stu-id="a8b78-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="a8b78-162">选择警报以查看详细信息：</span><span class="sxs-lookup"><span data-stu-id="a8b78-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="显示 DLP 警报管理仪表板上的警报详细信息的屏幕截图。" border="false":::

4. <span data-ttu-id="a8b78-164">选择 **"事件"** 选项卡以查看与警报关联的所有事件。</span><span class="sxs-lookup"><span data-stu-id="a8b78-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="a8b78-165">可以选择特定事件以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8b78-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="a8b78-166">有关一些可用事件详细信息的列表，请参阅了解数据丢失防护 [警报仪表板](dlp-alerts-dashboard-learn.md)。</span><span class="sxs-lookup"><span data-stu-id="a8b78-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="a8b78-167">选择 **"** 详细信息"打开 **警报** 的"概述"页。</span><span class="sxs-lookup"><span data-stu-id="a8b78-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="a8b78-168">概述页提供了摘要：</span><span class="sxs-lookup"><span data-stu-id="a8b78-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="a8b78-169">发生的情况</span><span class="sxs-lookup"><span data-stu-id="a8b78-169">of what happened</span></span>
    1. <span data-ttu-id="a8b78-170">谁执行了导致策略匹配的操作</span><span class="sxs-lookup"><span data-stu-id="a8b78-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="a8b78-171">有关匹配策略的信息等</span><span class="sxs-lookup"><span data-stu-id="a8b78-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="a8b78-172">选择 **"事件"** 选项卡以访问：</span><span class="sxs-lookup"><span data-stu-id="a8b78-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="a8b78-173">涉及的内容</span><span class="sxs-lookup"><span data-stu-id="a8b78-173">content involved</span></span>
    1. <span data-ttu-id="a8b78-174">匹配的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a8b78-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="a8b78-175">metadata</span><span class="sxs-lookup"><span data-stu-id="a8b78-175">metadata</span></span>

7. <span data-ttu-id="a8b78-176">选择 **"敏感信息类型"** 选项卡以查看有关内容中检测到的敏感信息类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8b78-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="a8b78-177">详细信息包括可信度、计数和与敏感信息类型匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="a8b78-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="a8b78-178">调查警报后，返回到"概述"选项卡，可在其中管理会审和管理警报处置并添加注释。</span><span class="sxs-lookup"><span data-stu-id="a8b78-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="a8b78-179">若要查看工作流管理的历史记录，请选择"管理 **日志"。**</span><span class="sxs-lookup"><span data-stu-id="a8b78-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="a8b78-180">对警报执行所需操作后，将警报的状态设置为"已解决 **"。**</span><span class="sxs-lookup"><span data-stu-id="a8b78-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8b78-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b78-181">See also</span></span>

- [<span data-ttu-id="a8b78-182">了解数据丢失防护警报和警报仪表板</span><span class="sxs-lookup"><span data-stu-id="a8b78-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="a8b78-183">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="a8b78-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)