---
title: 配置和查看数据丢失防护策略警报
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
description: 了解如何定义和管理数据丢失防护策略的警报。
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750034"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a><span data-ttu-id="01f63-103">配置和查看数据丢失防护策略警报</span><span class="sxs-lookup"><span data-stu-id="01f63-103">Configure and view alerts for data loss prevention polices</span></span>

<span data-ttu-id="01f63-104">DLP 策略 (数据丢失) 采取保护措施，防止意外共享敏感项目。</span><span class="sxs-lookup"><span data-stu-id="01f63-104">Data loss prevention (DLP) polices can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="01f63-105">对敏感项目采取操作时，可以通过配置 DLP 警报来通知您。</span><span class="sxs-lookup"><span data-stu-id="01f63-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="01f63-106">本文演示如何定义 DLP 策略中链接到数据丢失防护的丰富警报 (DLP) 策略。</span><span class="sxs-lookup"><span data-stu-id="01f63-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="01f63-107">你将了解如何使用 Microsoft 365 合规中心中的新 DLP 警报管理仪表板查看 DLP 策略违反的[警报、](https://compliance.microsoft.com/)事件和关联元数据。</span><span class="sxs-lookup"><span data-stu-id="01f63-107">You'll see how to use the new DLP alert management dashboard in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<!-- LEFT OFF HERE-->

## <a name="features"></a><span data-ttu-id="01f63-108">功能</span><span class="sxs-lookup"><span data-stu-id="01f63-108">Features</span></span>

<span data-ttu-id="01f63-109">以下功能是以下功能的一部分：</span><span class="sxs-lookup"><span data-stu-id="01f63-109">The following features are part of this:</span></span>

-   <span data-ttu-id="01f63-110">**DLP 警报管理仪表板**：在 [](https://compliance.microsoft.com/)Microsoft 365 合规中心中，此仪表板显示对以下工作负载强制执行的 DLP 策略的警报：</span><span class="sxs-lookup"><span data-stu-id="01f63-110">**DLP alert management dashboard**: In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), this dashboard shows alerts for DLP policies that are enforced on the following workloads:</span></span>

    -   <span data-ttu-id="01f63-111">Exchange</span><span class="sxs-lookup"><span data-stu-id="01f63-111">Exchange</span></span>
    -   <span data-ttu-id="01f63-112">SharePoint</span><span class="sxs-lookup"><span data-stu-id="01f63-112">SharePoint</span></span>
    -   <span data-ttu-id="01f63-113">OneDrive</span><span class="sxs-lookup"><span data-stu-id="01f63-113">OneDrive</span></span>
    -   <span data-ttu-id="01f63-114">Teams</span><span class="sxs-lookup"><span data-stu-id="01f63-114">Teams</span></span>
    -   <span data-ttu-id="01f63-115">设备</span><span class="sxs-lookup"><span data-stu-id="01f63-115">Devices</span></span>
-   <span data-ttu-id="01f63-116">**高级警报配置选项**：这些选项是 DLP 策略创作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="01f63-116">**Advanced alert configuration options**: These options are part of the DLP policy authoring flow.</span></span> <span data-ttu-id="01f63-117">使用它们创建丰富的警报配置。</span><span class="sxs-lookup"><span data-stu-id="01f63-117">Use them to create rich alert configurations.</span></span> <span data-ttu-id="01f63-118">你可以根据事件数或泄露数据的大小创建单个事件警报或聚合警报。</span><span class="sxs-lookup"><span data-stu-id="01f63-118">You can create a single-event alert or an aggregated alert, based on the number of events or the size of the leaked data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="01f63-119">开始之前</span><span class="sxs-lookup"><span data-stu-id="01f63-119">Before you begin</span></span>

<span data-ttu-id="01f63-120">在开始之前，请确保你具有必要的先决条件：</span><span class="sxs-lookup"><span data-stu-id="01f63-120">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="01f63-121">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="01f63-121">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="01f63-122">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="01f63-122">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="01f63-123">角色</span><span class="sxs-lookup"><span data-stu-id="01f63-123">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="01f63-124">DLP 警报管理仪表板的许可</span><span class="sxs-lookup"><span data-stu-id="01f63-124">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="01f63-125">DLP 的所有符合条件的租户Office 365新的 DLP 警报管理仪表板。</span><span class="sxs-lookup"><span data-stu-id="01f63-125">All eligible tenants for Office 365 DLP can access the new DLP alert management dashboard.</span></span> <span data-ttu-id="01f63-126">若要开始，你应该有资格使用 Office 365 DLP Exchange Online SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="01f63-126">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="01f63-127">有关 DLP 的许可要求Office 365，请参阅哪些许可证为用户提供从服务中获益[的权利？。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="01f63-127">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="01f63-128">使用符合[使用 DLP](endpoint-dlp-learn-about.md)条件Teams终结点[DLP](dlp-microsoft-teams.md)的客户将在 DLP 警报管理仪表板中Teams终结点 DLP 策略警报和 DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="01f63-128">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="01f63-129">警报配置选项的许可</span><span class="sxs-lookup"><span data-stu-id="01f63-129">Licensing for alert configuration options</span></span>

-   <span data-ttu-id="01f63-130">**单事件警报** 配置：拥有 E1、F1 或 G1 订阅、E3 或 G3 订阅的组织只能在每次活动发生时触发警报时创建警报策略。</span><span class="sxs-lookup"><span data-stu-id="01f63-130">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>
-   <span data-ttu-id="01f63-131">**聚合警报配置**：若要基于阈值配置聚合警报策略，必须具有以下配置之一：</span><span class="sxs-lookup"><span data-stu-id="01f63-131">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must have either of the following configurations:</span></span>
    -   <span data-ttu-id="01f63-132">E5 或 G5 订阅</span><span class="sxs-lookup"><span data-stu-id="01f63-132">An E5 or G5 subscription</span></span>
    -   <span data-ttu-id="01f63-133">包含以下功能之一的 E1、F1 或 G1 订阅或 E3 或 G3 订阅：</span><span class="sxs-lookup"><span data-stu-id="01f63-133">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
        -   <span data-ttu-id="01f63-134">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="01f63-134">Office 365 Advanced Threat Protection Plan 2</span></span>
        -   <span data-ttu-id="01f63-135">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="01f63-135">Microsoft 365 E5 Compliance</span></span>
        -   <span data-ttu-id="01f63-136">Microsoft 365电子数据展示和审核加载项许可证</span><span class="sxs-lookup"><span data-stu-id="01f63-136">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="01f63-137">角色</span><span class="sxs-lookup"><span data-stu-id="01f63-137">Roles</span></span>

<span data-ttu-id="01f63-138">如果要查看 DLP 警报管理仪表板或编辑 DLP 策略中的警报配置选项，您必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="01f63-138">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

-   <span data-ttu-id="01f63-139">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="01f63-139">Compliance Administrator</span></span>
-   <span data-ttu-id="01f63-140">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="01f63-140">Compliance Data Administrator</span></span>
-   <span data-ttu-id="01f63-141">安全管理员</span><span class="sxs-lookup"><span data-stu-id="01f63-141">Security Administrator</span></span>
-   <span data-ttu-id="01f63-142">安全操作员</span><span class="sxs-lookup"><span data-stu-id="01f63-142">Security Operator</span></span>
-   <span data-ttu-id="01f63-143">安全读取者</span><span class="sxs-lookup"><span data-stu-id="01f63-143">Security Reader</span></span>

<span data-ttu-id="01f63-144">若要访问 DLP 警报管理仪表板，您需要管理警报角色和以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="01f63-144">To access the DLP alert management dashboard, you need the Manage alerts role and either of the following roles:</span></span>

-   <span data-ttu-id="01f63-145">DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="01f63-145">DLP Compliance Management</span></span>
-   <span data-ttu-id="01f63-146">View-Only DLP 合规性管理</span><span class="sxs-lookup"><span data-stu-id="01f63-146">View-Only DLP Compliance Management</span></span>

## <a name="alert-configuration-experience"></a><span data-ttu-id="01f63-147">警报配置体验</span><span class="sxs-lookup"><span data-stu-id="01f63-147">Alert configuration experience</span></span>

<span data-ttu-id="01f63-148">如果符合聚合警报配置选项的条件[](#licensing-for-alert-configuration-options)，则会看到 DLP 策略创作体验中的以下内联选项。</span><span class="sxs-lookup"><span data-stu-id="01f63-148">If you're eligible for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you see the following options inline in the DLP policy authoring experience.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

<span data-ttu-id="01f63-150">可以使用这些警报配置选项来配置一个设置，该设置定义 DLP 规则匹配在触发警报之前发生的时间。</span><span class="sxs-lookup"><span data-stu-id="01f63-150">You can use these alert configuration options to configure a setting that defines how often a DLP rule match can occur before an alert is triggered.</span></span> <span data-ttu-id="01f63-151">通过此配置，您可以设置一个策略，以在活动符合策略条件或超出特定阈值时（基于活动数或根据已过滤数据的量）生成警报。</span><span class="sxs-lookup"><span data-stu-id="01f63-151">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

<span data-ttu-id="01f63-152">如果符合单事件警报配置选项[](#licensing-for-alert-configuration-options)的条件，则会看到 DLP 策略创作体验中的以下警报配置选项。</span><span class="sxs-lookup"><span data-stu-id="01f63-152">If you're eligible for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you see the following alert configuration option in the DLP policy authoring experience.</span></span> <span data-ttu-id="01f63-153">使用此选项可创建每次因用户活动而发生 DLP 规则匹配时都会触发的警报。</span><span class="sxs-lookup"><span data-stu-id="01f63-153">Use this option to create an alert that's raised every time a DLP rule match happens because of a user activity.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="dlp-alert-management-dashboard"></a><span data-ttu-id="01f63-155">DLP 警报管理仪表板</span><span class="sxs-lookup"><span data-stu-id="01f63-155">DLP alert management dashboard</span></span>

<span data-ttu-id="01f63-156">使用 DLP 警报管理仪表板：</span><span class="sxs-lookup"><span data-stu-id="01f63-156">To work with the DLP alert management dashboard:</span></span>

1.  <span data-ttu-id="01f63-157">In the [Microsoft 365 compliance center，](https://www.compliance.microsoft.com)go to **Data Loss Prevention**.</span><span class="sxs-lookup"><span data-stu-id="01f63-157">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>

2.  <span data-ttu-id="01f63-158">选择" **警报"** 选项卡以查看 DLP 警报仪表板。</span><span class="sxs-lookup"><span data-stu-id="01f63-158">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>

    -   <span data-ttu-id="01f63-159">选择筛选器以优化警报列表。</span><span class="sxs-lookup"><span data-stu-id="01f63-159">Choose filters to refine the list of alerts.</span></span> <span data-ttu-id="01f63-160">选择 **"自定义** 列"列出您想要查看的属性。</span><span class="sxs-lookup"><span data-stu-id="01f63-160">Choose **Customize columns** to list the properties you want to see.</span></span> <span data-ttu-id="01f63-161">还可以选择在任何列中按升序或降序对警报进行排序。</span><span class="sxs-lookup"><span data-stu-id="01f63-161">You can also choose to sort the alerts in ascending or descending order in any column.</span></span>
    -   <span data-ttu-id="01f63-162">选择警报以查看详细信息：</span><span class="sxs-lookup"><span data-stu-id="01f63-162">Select an alert to see details:</span></span>

        :::image type="content" source="../media/alert-details.png" alt-text="显示 DLP 警报管理仪表板上的警报详细信息的屏幕截图。" border="false":::

1.  <span data-ttu-id="01f63-164">选择 **"事件"** 选项卡以查看与警报关联的所有事件。</span><span class="sxs-lookup"><span data-stu-id="01f63-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="01f63-165">可以选择特定事件以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="01f63-165">You can choose a particular event to view its details.</span></span>
    <span data-ttu-id="01f63-166">下表显示了一些事件详细信息。</span><span class="sxs-lookup"><span data-stu-id="01f63-166">The following table shows some of the event details.</span></span>
    
    | <span data-ttu-id="01f63-167">类别</span><span class="sxs-lookup"><span data-stu-id="01f63-167">Category</span></span>          | <span data-ttu-id="01f63-168">属性名</span><span class="sxs-lookup"><span data-stu-id="01f63-168">Property name</span></span>                 | <span data-ttu-id="01f63-169">说明</span><span class="sxs-lookup"><span data-stu-id="01f63-169">Description</span></span>                                                                | <span data-ttu-id="01f63-170">适用的事件类型</span><span class="sxs-lookup"><span data-stu-id="01f63-170">Applicable event types</span></span>                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |<span data-ttu-id="01f63-171">*事件详情*</span><span class="sxs-lookup"><span data-stu-id="01f63-171">*Event details*</span></span>||
    |      | <span data-ttu-id="01f63-172">Id</span><span class="sxs-lookup"><span data-stu-id="01f63-172">Id</span></span>                            | <span data-ttu-id="01f63-173">与事件关联的唯一 ID</span><span class="sxs-lookup"><span data-stu-id="01f63-173">Unique ID associated with the event</span></span>                                        | <span data-ttu-id="01f63-174">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-174">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-175">位置</span><span class="sxs-lookup"><span data-stu-id="01f63-175">Location</span></span>                      | <span data-ttu-id="01f63-176">检测到事件的工作负荷</span><span class="sxs-lookup"><span data-stu-id="01f63-176">Workload where the event was detected</span></span>                                      | <span data-ttu-id="01f63-177">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-177">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-178">活动时间</span><span class="sxs-lookup"><span data-stu-id="01f63-178">Time of activity</span></span>              | <span data-ttu-id="01f63-179">导致 DLP 冲突的用户活动时间</span><span class="sxs-lookup"><span data-stu-id="01f63-179">Time of the user activity that caused the DLP violation</span></span>                    | <span data-ttu-id="01f63-180">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-180">All events</span></span>                               |
    |<span data-ttu-id="01f63-181">*影响的实体*</span><span class="sxs-lookup"><span data-stu-id="01f63-181">*Impacted entities*</span></span>||
    |  | <span data-ttu-id="01f63-182">User</span><span class="sxs-lookup"><span data-stu-id="01f63-182">User</span></span>                          | <span data-ttu-id="01f63-183">导致 DLP 冲突的用户</span><span class="sxs-lookup"><span data-stu-id="01f63-183">User who caused the DLP violation</span></span>                                          | <span data-ttu-id="01f63-184">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-184">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-185">主机名称</span><span class="sxs-lookup"><span data-stu-id="01f63-185">Hostname</span></span>                      | <span data-ttu-id="01f63-186">检测到 DLP 违反情况的机器的主机名</span><span class="sxs-lookup"><span data-stu-id="01f63-186">Host name of the machine where the DLP violation was detected</span></span>              | <span data-ttu-id="01f63-187">设备事件</span><span class="sxs-lookup"><span data-stu-id="01f63-187">Devices events</span></span>                           |
    |                   | <span data-ttu-id="01f63-188">IP 地址</span><span class="sxs-lookup"><span data-stu-id="01f63-188">IP address</span></span>                    | <span data-ttu-id="01f63-189">计算机 IP 地址</span><span class="sxs-lookup"><span data-stu-id="01f63-189">IP address of the machine</span></span>                                                  | <span data-ttu-id="01f63-190">设备事件</span><span class="sxs-lookup"><span data-stu-id="01f63-190">Devices events</span></span>                           |
    |                   | <span data-ttu-id="01f63-191">文件路径</span><span class="sxs-lookup"><span data-stu-id="01f63-191">File path</span></span>                     | <span data-ttu-id="01f63-192">冲突所涉及的文件的绝对路径</span><span class="sxs-lookup"><span data-stu-id="01f63-192">Absolute path of the file involved in the violation</span></span>                        | <span data-ttu-id="01f63-193">SharePoint、OneDrive 和设备事件</span><span class="sxs-lookup"><span data-stu-id="01f63-193">SharePoint, OneDrive, and Devices events</span></span> |
    |                   | <span data-ttu-id="01f63-194">电子邮件收件人</span><span class="sxs-lookup"><span data-stu-id="01f63-194">Email recipients</span></span>              | <span data-ttu-id="01f63-195">违反 DLP 策略的电子邮件的收件人</span><span class="sxs-lookup"><span data-stu-id="01f63-195">Recipients of the email that violated the DLP policy</span></span>                       | <span data-ttu-id="01f63-196">Exchange事件</span><span class="sxs-lookup"><span data-stu-id="01f63-196">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="01f63-197">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="01f63-197">Email subject</span></span>                 | <span data-ttu-id="01f63-198">违反 DLP 策略的电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="01f63-198">Subject of the email that violated the DLP policy</span></span>                          | <span data-ttu-id="01f63-199">Exchange事件</span><span class="sxs-lookup"><span data-stu-id="01f63-199">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="01f63-200">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="01f63-200">Email attachments</span></span>             | <span data-ttu-id="01f63-201">电子邮件中违反 DLP 策略的附件的名称</span><span class="sxs-lookup"><span data-stu-id="01f63-201">Names of the attachments in the email that violated the DLP policy</span></span>         | <span data-ttu-id="01f63-202">Exchange事件</span><span class="sxs-lookup"><span data-stu-id="01f63-202">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="01f63-203">网站所有者</span><span class="sxs-lookup"><span data-stu-id="01f63-203">Site owner</span></span>                    | <span data-ttu-id="01f63-204">网站所有者的名称</span><span class="sxs-lookup"><span data-stu-id="01f63-204">Name of the site owner</span></span>                                                     | <span data-ttu-id="01f63-205">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-205">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="01f63-206">网站 URL</span><span class="sxs-lookup"><span data-stu-id="01f63-206">Site URL</span></span>                      | <span data-ttu-id="01f63-207">SharePoint 或 OneDrive 的完整 URL</span><span class="sxs-lookup"><span data-stu-id="01f63-207">Full URL of the SharePoint or OneDrive site</span></span>                                | <span data-ttu-id="01f63-208">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-208">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="01f63-209">已创建文件</span><span class="sxs-lookup"><span data-stu-id="01f63-209">File created</span></span>                  | <span data-ttu-id="01f63-210">文件创建时间</span><span class="sxs-lookup"><span data-stu-id="01f63-210">Time of file creation</span></span>                                                      | <span data-ttu-id="01f63-211">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-211">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="01f63-212">上次修改文件</span><span class="sxs-lookup"><span data-stu-id="01f63-212">File last modified</span></span>            | <span data-ttu-id="01f63-213">上次修改文件的时间</span><span class="sxs-lookup"><span data-stu-id="01f63-213">Time of the last modification of the file</span></span>                                  | <span data-ttu-id="01f63-214">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-214">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="01f63-215">文件大小</span><span class="sxs-lookup"><span data-stu-id="01f63-215">File size</span></span>                     | <span data-ttu-id="01f63-216">文件大小</span><span class="sxs-lookup"><span data-stu-id="01f63-216">Size of the file</span></span>                                                           | <span data-ttu-id="01f63-217">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-217">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="01f63-218">文件所有者</span><span class="sxs-lookup"><span data-stu-id="01f63-218">File owner</span></span>                    | <span data-ttu-id="01f63-219">文件的所有者</span><span class="sxs-lookup"><span data-stu-id="01f63-219">Owner of the file</span></span>                                                          | <span data-ttu-id="01f63-220">SharePoint事件OneDrive事件</span><span class="sxs-lookup"><span data-stu-id="01f63-220">SharePoint and OneDrive events</span></span>           |
    |<span data-ttu-id="01f63-221">*策略详细信息*</span><span class="sxs-lookup"><span data-stu-id="01f63-221">*Policy details*</span></span>||
    |     | <span data-ttu-id="01f63-222">匹配的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="01f63-222">DLP policy matched</span></span>            | <span data-ttu-id="01f63-223">匹配的 DLP 策略的名称</span><span class="sxs-lookup"><span data-stu-id="01f63-223">Name of the DLP policy that was matched</span></span>                                    | <span data-ttu-id="01f63-224">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-224">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-225">匹配的规则</span><span class="sxs-lookup"><span data-stu-id="01f63-225">Rule matched</span></span>                  | <span data-ttu-id="01f63-226">匹配的 DLP 策略中的 DLP 规则的名称</span><span class="sxs-lookup"><span data-stu-id="01f63-226">Name of the DLP rule in the DLP policy that was matched</span></span>                    | <span data-ttu-id="01f63-227">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-227">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-228">检测到敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="01f63-228">Sensitive info types detected</span></span> | <span data-ttu-id="01f63-229">作为 DLP 策略的一部分检测到的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="01f63-229">Sensitive information types that were detected as a part of the DLP policy</span></span> | <span data-ttu-id="01f63-230">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-230">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-231">Mailbox01 会使用新的数据库重新联机。</span><span class="sxs-lookup"><span data-stu-id="01f63-231">Actions taken</span></span>                 | <span data-ttu-id="01f63-232">作为匹配的 DLP 策略的一部分采取的操作</span><span class="sxs-lookup"><span data-stu-id="01f63-232">Actions taken as a part of the matched DLP policy</span></span>                          | <span data-ttu-id="01f63-233">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-233">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-234">用户过度控制策略</span><span class="sxs-lookup"><span data-stu-id="01f63-234">User overrode policy</span></span>          | <span data-ttu-id="01f63-235">用户是否通过策略提示过度控制策略</span><span class="sxs-lookup"><span data-stu-id="01f63-235">Whether the user overrode the policy through the policy tip</span></span>                | <span data-ttu-id="01f63-236">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-236">All events</span></span>                               |
    |                   | <span data-ttu-id="01f63-237">替代对齐文本</span><span class="sxs-lookup"><span data-stu-id="01f63-237">Override justification text</span></span>   | <span data-ttu-id="01f63-238">提供以替代策略提示的理由</span><span class="sxs-lookup"><span data-stu-id="01f63-238">Justification provided to override the policy tip</span></span>                          | <span data-ttu-id="01f63-239">所有事件</span><span class="sxs-lookup"><span data-stu-id="01f63-239">All events</span></span>                               |
    
1.  <span data-ttu-id="01f63-240">选择 **"敏感信息类型"** 选项卡以查看有关内容中检测到的敏感信息类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="01f63-240">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="01f63-241">详细信息包括可信度和计数。</span><span class="sxs-lookup"><span data-stu-id="01f63-241">Details include confidence and count.</span></span>

2.  <span data-ttu-id="01f63-242">调查警报后，选择"管理警报"以更改 **(、** 正在调查、已消除或已解决) 。 </span><span class="sxs-lookup"><span data-stu-id="01f63-242">After you investigate the alert, choose **Manage alert** to change the status (**Active**, **Investigating**, **Dismissed**, or **Resolved**).</span></span> <span data-ttu-id="01f63-243">您还可以添加注释并将警报分配给您的组织中的某人。</span><span class="sxs-lookup"><span data-stu-id="01f63-243">You can also add comments and assign the alert to someone in your organization.</span></span>

    -   <span data-ttu-id="01f63-244">若要查看工作流管理的历史记录，请选择"管理 **日志"。**</span><span class="sxs-lookup"><span data-stu-id="01f63-244">To see the history of workflow management, choose **Management log**.</span></span>
    -   <span data-ttu-id="01f63-245">对警报执行所需操作后，将警报的状态设置为"已解决 **"。**</span><span class="sxs-lookup"><span data-stu-id="01f63-245">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>