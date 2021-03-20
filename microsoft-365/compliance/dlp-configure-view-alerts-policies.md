---
title: 配置和查看 DLP 策略的警报（预览）
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
description: 了解如何定义和管理 DLP 策略的警报。
ms.openlocfilehash: 0594cee5208049aef16dee6fa03954faae2a1cdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917858"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a><span data-ttu-id="2a6c4-103">配置和查看 DLP 策略警报 (预览) </span><span class="sxs-lookup"><span data-stu-id="2a6c4-103">Configure and view alerts for DLP polices (preview)</span></span>

<span data-ttu-id="2a6c4-104">本文演示如何定义 DLP 策略中链接到数据丢失防护的丰富警报 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-104">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="2a6c4-105">你将了解如何使用 [Microsoft 365](https://compliance.microsoft.com/) 合规中心中的新 DLP 警报管理仪表板查看 DLP 策略违反的警报、事件和相关元数据。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-105">You'll see how to use the new DLP alert management dashboard in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

## <a name="features"></a><span data-ttu-id="2a6c4-106">功能</span><span class="sxs-lookup"><span data-stu-id="2a6c4-106">Features</span></span>

<span data-ttu-id="2a6c4-107">以下功能是此预览的一部分：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-107">The following features are part of this preview:</span></span>

-   <span data-ttu-id="2a6c4-108">**DLP 警报管理仪表板**：在 [Microsoft 365](https://compliance.microsoft.com/)合规中心中，此仪表板显示对以下工作负载强制执行的 DLP 策略的警报：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-108">**DLP alert management dashboard**: In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), this dashboard shows alerts for DLP policies that are enforced on the following workloads:</span></span>

    -   <span data-ttu-id="2a6c4-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="2a6c4-109">Exchange</span></span>
    -   <span data-ttu-id="2a6c4-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2a6c4-110">SharePoint</span></span>
    -   <span data-ttu-id="2a6c4-111">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2a6c4-111">OneDrive</span></span>
    -   <span data-ttu-id="2a6c4-112">Teams</span><span class="sxs-lookup"><span data-stu-id="2a6c4-112">Teams</span></span>
    -   <span data-ttu-id="2a6c4-113">设备</span><span class="sxs-lookup"><span data-stu-id="2a6c4-113">Devices</span></span>
-   <span data-ttu-id="2a6c4-114">**高级警报配置选项**：这些选项是 DLP 策略创作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-114">**Advanced alert configuration options**: These options are part of the DLP policy authoring flow.</span></span> <span data-ttu-id="2a6c4-115">使用它们创建丰富的警报配置。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-115">Use them to create rich alert configurations.</span></span> <span data-ttu-id="2a6c4-116">你可以根据事件数或泄露数据的大小创建单个事件警报或聚合警报。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-116">You can create a single-event alert or an aggregated alert, based on the number of events or the size of the leaked data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2a6c4-117">开始之前</span><span class="sxs-lookup"><span data-stu-id="2a6c4-117">Before you begin</span></span>

<span data-ttu-id="2a6c4-118">在开始之前，请确保你具有必要的先决条件：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-118">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="2a6c4-119">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="2a6c4-119">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="2a6c4-120">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="2a6c4-120">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="2a6c4-121">角色</span><span class="sxs-lookup"><span data-stu-id="2a6c4-121">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="2a6c4-122">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="2a6c4-122">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="2a6c4-123">Office 365 DLP 的所有符合条件的租户都可以访问新的 DLP 警报管理仪表板。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-123">All eligible tenants for Office 365 DLP can access the new DLP alert management dashboard.</span></span> <span data-ttu-id="2a6c4-124">To get started， you should be eligible for Office 365 DLP for Exchange Online， SharePoint Online， and OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="2a6c4-124">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="2a6c4-125">有关 Office 365 DLP 的许可要求详细信息，请参阅哪些许可证为用户提供从服务中获益[的权利？。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="2a6c4-125">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="2a6c4-126">参与 Endpoint [DLP](./endpoint-dlp-learn-about.md?view=o365-worldwide) 公共预览版或符合 [Teams DLP](./dlp-microsoft-teams.md?view=o365-worldwide) 条件的客户将在 DLP 警报管理仪表板中查看其终结点 DLP 策略警报和 Teams DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-126">Customers who participate in the [Endpoint DLP](./endpoint-dlp-learn-about.md?view=o365-worldwide) public preview or who are eligible for [Teams DLP](./dlp-microsoft-teams.md?view=o365-worldwide) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="2a6c4-127">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="2a6c4-127">Licensing for alert configuration options</span></span>

-   <span data-ttu-id="2a6c4-128">**单事件警报** 配置：拥有 E1、F1 或 G1 订阅、E3 或 G3 订阅的组织只能在每次活动发生时触发警报时创建警报策略。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-128">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>
-   <span data-ttu-id="2a6c4-129">**聚合警报配置**：若要基于阈值配置聚合警报策略，必须具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-129">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must have either of the following configurations:</span></span>
    -   <span data-ttu-id="2a6c4-130">E5 或 G5 订阅</span><span class="sxs-lookup"><span data-stu-id="2a6c4-130">An E5 or G5 subscription</span></span>
    -   <span data-ttu-id="2a6c4-131">包含以下功能之一的 E1、F1 或 G1 订阅或 E3 或 G3 订阅：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-131">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
        -   <span data-ttu-id="2a6c4-132">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="2a6c4-132">Office 365 Advanced Threat Protection Plan 2</span></span>
        -   <span data-ttu-id="2a6c4-133">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="2a6c4-133">Microsoft 365 E5 Compliance</span></span>
        -   <span data-ttu-id="2a6c4-134">Microsoft 365 电子数据展示和审核加载项许可证</span><span class="sxs-lookup"><span data-stu-id="2a6c4-134">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="2a6c4-135">角色</span><span class="sxs-lookup"><span data-stu-id="2a6c4-135">Roles</span></span>

<span data-ttu-id="2a6c4-136">如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-136">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

-   <span data-ttu-id="2a6c4-137">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="2a6c4-137">Compliance Administrator</span></span>
-   <span data-ttu-id="2a6c4-138">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="2a6c4-138">Compliance Data Administrator</span></span>
-   <span data-ttu-id="2a6c4-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="2a6c4-139">Security Administrator</span></span>
-   <span data-ttu-id="2a6c4-140">安全操作员</span><span class="sxs-lookup"><span data-stu-id="2a6c4-140">Security Operator</span></span>
-   <span data-ttu-id="2a6c4-141">安全读取者</span><span class="sxs-lookup"><span data-stu-id="2a6c4-141">Security Reader</span></span>

<span data-ttu-id="2a6c4-142">若要访问 DLP 警报管理仪表板，您需要管理警报角色和以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-142">To access the DLP alert management dashboard, you need the Manage alerts role and either of the following roles:</span></span>

-   <span data-ttu-id="2a6c4-143">DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="2a6c4-143">DLP Compliance Management</span></span>
-   <span data-ttu-id="2a6c4-144">View-Only DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="2a6c4-144">View-Only DLP Compliance Management</span></span>

## <a name="alert-configuration-experience"></a><span data-ttu-id="2a6c4-145">警报配置体验</span><span class="sxs-lookup"><span data-stu-id="2a6c4-145">Alert configuration experience</span></span>

<span data-ttu-id="2a6c4-146">如果符合聚合警报配置选项的条件[](#licensing-for-alert-configuration-options)，则会看到 DLP 策略创作体验中的以下内联选项。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-146">If you're eligible for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you see the following options inline in the DLP policy authoring experience.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

<span data-ttu-id="2a6c4-148">可以使用这些警报配置选项来配置一个设置，该设置定义 DLP 规则匹配在触发警报之前发生的时间。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-148">You can use these alert configuration options to configure a setting that defines how often a DLP rule match can occur before an alert is triggered.</span></span> <span data-ttu-id="2a6c4-149">通过此配置，您可以设置一个策略，以在活动符合策略条件或超出特定阈值时（基于活动数或根据已过滤数据的量）生成警报。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-149">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

<span data-ttu-id="2a6c4-150">如果符合单事件警报配置选项[](#licensing-for-alert-configuration-options)的条件，则会看到 DLP 策略创作体验中的以下警报配置选项。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-150">If you're eligible for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you see the following alert configuration option in the DLP policy authoring experience.</span></span> <span data-ttu-id="2a6c4-151">使用此选项可创建每次因用户活动而发生 DLP 规则匹配时都会触发的警报。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-151">Use this option to create an alert that's raised every time a DLP rule match happens because of a user activity.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="dlp-alert-management-dashboard"></a><span data-ttu-id="2a6c4-153">DLP 警报管理仪表板</span><span class="sxs-lookup"><span data-stu-id="2a6c4-153">DLP alert management dashboard</span></span>

<span data-ttu-id="2a6c4-154">使用 DLP 警报管理仪表板：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-154">To work with the DLP alert management dashboard:</span></span>

1.  <span data-ttu-id="2a6c4-155">在 [Microsoft 365 合规中心](https://www.compliance.microsoft.com)，转到 **数据丢失防护**。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-155">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>

2.  <span data-ttu-id="2a6c4-156">选择" **警报"** 选项卡以查看 DLP 警报仪表板。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-156">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>

    -   <span data-ttu-id="2a6c4-157">选择筛选器以优化警报列表。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-157">Choose filters to refine the list of alerts.</span></span> <span data-ttu-id="2a6c4-158">选择 **"自定义** 列"列出您想要查看的属性。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-158">Choose **Customize columns** to list the properties you want to see.</span></span> <span data-ttu-id="2a6c4-159">还可以选择在任何列中按升序或降序对警报进行排序。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-159">You can also choose to sort the alerts in ascending or descending order in any column.</span></span>
    -   <span data-ttu-id="2a6c4-160">选择警报以查看详细信息：</span><span class="sxs-lookup"><span data-stu-id="2a6c4-160">Select an alert to see details:</span></span>

        :::image type="content" source="../media/alert-details.png" alt-text="显示 DLP 警报管理仪表板上的警报详细信息的屏幕截图。" border="false":::

1.  <span data-ttu-id="2a6c4-162">选择 **"事件"** 选项卡以查看与警报关联的所有事件。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-162">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="2a6c4-163">可以选择特定事件以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-163">You can choose a particular event to view its details.</span></span>
    <span data-ttu-id="2a6c4-164">下表显示了一些事件详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-164">The following table shows some of the event details.</span></span>
    
    | <span data-ttu-id="2a6c4-165">类别</span><span class="sxs-lookup"><span data-stu-id="2a6c4-165">Category</span></span>          | <span data-ttu-id="2a6c4-166">属性名</span><span class="sxs-lookup"><span data-stu-id="2a6c4-166">Property name</span></span>                 | <span data-ttu-id="2a6c4-167">说明</span><span class="sxs-lookup"><span data-stu-id="2a6c4-167">Description</span></span>                                                                | <span data-ttu-id="2a6c4-168">适用的事件类型</span><span class="sxs-lookup"><span data-stu-id="2a6c4-168">Applicable event types</span></span>                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |<span data-ttu-id="2a6c4-169">*事件详情*</span><span class="sxs-lookup"><span data-stu-id="2a6c4-169">*Event details*</span></span>||
    |      | <span data-ttu-id="2a6c4-170">Id</span><span class="sxs-lookup"><span data-stu-id="2a6c4-170">Id</span></span>                            | <span data-ttu-id="2a6c4-171">与事件关联的唯一 ID</span><span class="sxs-lookup"><span data-stu-id="2a6c4-171">Unique ID associated with the event</span></span>                                        | <span data-ttu-id="2a6c4-172">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-172">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-173">位置</span><span class="sxs-lookup"><span data-stu-id="2a6c4-173">Location</span></span>                      | <span data-ttu-id="2a6c4-174">检测到事件的工作负荷</span><span class="sxs-lookup"><span data-stu-id="2a6c4-174">Workload where the event was detected</span></span>                                      | <span data-ttu-id="2a6c4-175">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-175">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-176">活动时间</span><span class="sxs-lookup"><span data-stu-id="2a6c4-176">Time of activity</span></span>              | <span data-ttu-id="2a6c4-177">导致 DLP 冲突的用户活动时间</span><span class="sxs-lookup"><span data-stu-id="2a6c4-177">Time of the user activity that caused the DLP violation</span></span>                    | <span data-ttu-id="2a6c4-178">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-178">All events</span></span>                               |
    |<span data-ttu-id="2a6c4-179">*影响的实体*</span><span class="sxs-lookup"><span data-stu-id="2a6c4-179">*Impacted entities*</span></span>||
    |  | <span data-ttu-id="2a6c4-180">User</span><span class="sxs-lookup"><span data-stu-id="2a6c4-180">User</span></span>                          | <span data-ttu-id="2a6c4-181">导致 DLP 冲突的用户</span><span class="sxs-lookup"><span data-stu-id="2a6c4-181">User who caused the DLP violation</span></span>                                          | <span data-ttu-id="2a6c4-182">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-182">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-183">主机名称</span><span class="sxs-lookup"><span data-stu-id="2a6c4-183">Hostname</span></span>                      | <span data-ttu-id="2a6c4-184">检测到 DLP 违反情况的机器的主机名</span><span class="sxs-lookup"><span data-stu-id="2a6c4-184">Host name of the machine where the DLP violation was detected</span></span>              | <span data-ttu-id="2a6c4-185">设备事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-185">Devices events</span></span>                           |
    |                   | <span data-ttu-id="2a6c4-186">IP 地址</span><span class="sxs-lookup"><span data-stu-id="2a6c4-186">IP address</span></span>                    | <span data-ttu-id="2a6c4-187">计算机 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2a6c4-187">IP address of the machine</span></span>                                                  | <span data-ttu-id="2a6c4-188">设备事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-188">Devices events</span></span>                           |
    |                   | <span data-ttu-id="2a6c4-189">文件路径</span><span class="sxs-lookup"><span data-stu-id="2a6c4-189">File path</span></span>                     | <span data-ttu-id="2a6c4-190">冲突所涉及的文件的绝对路径</span><span class="sxs-lookup"><span data-stu-id="2a6c4-190">Absolute path of the file involved in the violation</span></span>                        | <span data-ttu-id="2a6c4-191">SharePoint、OneDrive 和设备事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-191">SharePoint, OneDrive, and Devices events</span></span> |
    |                   | <span data-ttu-id="2a6c4-192">电子邮件收件人</span><span class="sxs-lookup"><span data-stu-id="2a6c4-192">Email recipients</span></span>              | <span data-ttu-id="2a6c4-193">违反 DLP 策略的电子邮件的收件人</span><span class="sxs-lookup"><span data-stu-id="2a6c4-193">Recipients of the email that violated the DLP policy</span></span>                       | <span data-ttu-id="2a6c4-194">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-194">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="2a6c4-195">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="2a6c4-195">Email subject</span></span>                 | <span data-ttu-id="2a6c4-196">违反 DLP 策略的电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="2a6c4-196">Subject of the email that violated the DLP policy</span></span>                          | <span data-ttu-id="2a6c4-197">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-197">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="2a6c4-198">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-198">Email attachments</span></span>             | <span data-ttu-id="2a6c4-199">电子邮件中违反 DLP 策略的附件的名称</span><span class="sxs-lookup"><span data-stu-id="2a6c4-199">Names of the attachments in the email that violated the DLP policy</span></span>         | <span data-ttu-id="2a6c4-200">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-200">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="2a6c4-201">网站所有者</span><span class="sxs-lookup"><span data-stu-id="2a6c4-201">Site owner</span></span>                    | <span data-ttu-id="2a6c4-202">网站所有者的名称</span><span class="sxs-lookup"><span data-stu-id="2a6c4-202">Name of the site owner</span></span>                                                     | <span data-ttu-id="2a6c4-203">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-203">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="2a6c4-204">网站 URL</span><span class="sxs-lookup"><span data-stu-id="2a6c4-204">Site URL</span></span>                      | <span data-ttu-id="2a6c4-205">SharePoint 或 OneDrive 网站的完整 URL</span><span class="sxs-lookup"><span data-stu-id="2a6c4-205">Full URL of the SharePoint or OneDrive site</span></span>                                | <span data-ttu-id="2a6c4-206">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-206">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="2a6c4-207">已创建文件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-207">File created</span></span>                  | <span data-ttu-id="2a6c4-208">文件创建时间</span><span class="sxs-lookup"><span data-stu-id="2a6c4-208">Time of file creation</span></span>                                                      | <span data-ttu-id="2a6c4-209">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-209">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="2a6c4-210">上次修改文件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-210">File last modified</span></span>            | <span data-ttu-id="2a6c4-211">上次修改文件的时间</span><span class="sxs-lookup"><span data-stu-id="2a6c4-211">Time of the last modification of the file</span></span>                                  | <span data-ttu-id="2a6c4-212">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-212">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="2a6c4-213">文件大小</span><span class="sxs-lookup"><span data-stu-id="2a6c4-213">File size</span></span>                     | <span data-ttu-id="2a6c4-214">文件大小</span><span class="sxs-lookup"><span data-stu-id="2a6c4-214">Size of the file</span></span>                                                           | <span data-ttu-id="2a6c4-215">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-215">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="2a6c4-216">文件所有者</span><span class="sxs-lookup"><span data-stu-id="2a6c4-216">File owner</span></span>                    | <span data-ttu-id="2a6c4-217">文件的所有者</span><span class="sxs-lookup"><span data-stu-id="2a6c4-217">Owner of the file</span></span>                                                          | <span data-ttu-id="2a6c4-218">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-218">SharePoint and OneDrive events</span></span>           |
    |<span data-ttu-id="2a6c4-219">*策略详细信息*</span><span class="sxs-lookup"><span data-stu-id="2a6c4-219">*Policy details*</span></span>||
    |     | <span data-ttu-id="2a6c4-220">匹配的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="2a6c4-220">DLP policy matched</span></span>            | <span data-ttu-id="2a6c4-221">匹配的 DLP 策略的名称</span><span class="sxs-lookup"><span data-stu-id="2a6c4-221">Name of the DLP policy that was matched</span></span>                                    | <span data-ttu-id="2a6c4-222">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-222">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-223">匹配的规则</span><span class="sxs-lookup"><span data-stu-id="2a6c4-223">Rule matched</span></span>                  | <span data-ttu-id="2a6c4-224">匹配的 DLP 策略中的 DLP 规则的名称</span><span class="sxs-lookup"><span data-stu-id="2a6c4-224">Name of the DLP rule in the DLP policy that was matched</span></span>                    | <span data-ttu-id="2a6c4-225">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-225">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-226">检测到敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2a6c4-226">Sensitive info types detected</span></span> | <span data-ttu-id="2a6c4-227">作为 DLP 策略的一部分检测到的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2a6c4-227">Sensitive information types that were detected as a part of the DLP policy</span></span> | <span data-ttu-id="2a6c4-228">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-228">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-229">Mailbox01 会使用新的数据库重新联机。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-229">Actions taken</span></span>                 | <span data-ttu-id="2a6c4-230">作为匹配的 DLP 策略的一部分采取的操作</span><span class="sxs-lookup"><span data-stu-id="2a6c4-230">Actions taken as a part of the matched DLP policy</span></span>                          | <span data-ttu-id="2a6c4-231">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-231">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-232">用户过度控制策略</span><span class="sxs-lookup"><span data-stu-id="2a6c4-232">User overrode policy</span></span>          | <span data-ttu-id="2a6c4-233">用户是否通过策略提示过度控制策略</span><span class="sxs-lookup"><span data-stu-id="2a6c4-233">Whether the user overrode the policy through the policy tip</span></span>                | <span data-ttu-id="2a6c4-234">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-234">All events</span></span>                               |
    |                   | <span data-ttu-id="2a6c4-235">替代对齐文本</span><span class="sxs-lookup"><span data-stu-id="2a6c4-235">Override justification text</span></span>   | <span data-ttu-id="2a6c4-236">提供以替代策略提示的理由</span><span class="sxs-lookup"><span data-stu-id="2a6c4-236">Justification provided to override the policy tip</span></span>                          | <span data-ttu-id="2a6c4-237">所有事件</span><span class="sxs-lookup"><span data-stu-id="2a6c4-237">All events</span></span>                               |
    
1.  <span data-ttu-id="2a6c4-238">选择 **"敏感信息类型"** 选项卡以查看有关内容中检测到的敏感信息类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-238">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="2a6c4-239">详细信息包括可信度和计数。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-239">Details include confidence and count.</span></span>

2.  <span data-ttu-id="2a6c4-240">调查警报后，选择"管理警报"以更改 **(、** 正在调查、已消除或已解决) 。 </span><span class="sxs-lookup"><span data-stu-id="2a6c4-240">After you investigate the alert, choose **Manage alert** to change the status (**Active**, **Investigating**, **Dismissed**, or **Resolved**).</span></span> <span data-ttu-id="2a6c4-241">您还可以添加注释并将警报分配给您的组织中的某人。</span><span class="sxs-lookup"><span data-stu-id="2a6c4-241">You can also add comments and assign the alert to someone in your organization.</span></span>

    -   <span data-ttu-id="2a6c4-242">若要查看工作流管理的历史记录，请选择"管理 **日志"。**</span><span class="sxs-lookup"><span data-stu-id="2a6c4-242">To see the history of workflow management, choose **Management log**.</span></span>
    -   <span data-ttu-id="2a6c4-243">对警报执行所需操作后，将警报的状态设置为"已解决 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a6c4-243">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>