---
title: 内部风险管理审核日志
description: 了解 Microsoft 365 审核日志内部风险管理策略
keywords: Microsoft 365， 内部风险管理， 风险管理， 合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820267"
---
# <a name="insider-risk-management-audit-log"></a><span data-ttu-id="54367-104">内部风险管理审核日志</span><span class="sxs-lookup"><span data-stu-id="54367-104">Insider risk management audit log</span></span>

<span data-ttu-id="54367-105">利用内部风险管理审核日志，您可以及时了解对内部风险管理功能采取的操作。</span><span class="sxs-lookup"><span data-stu-id="54367-105">The insider risk management audit log enables you to stay informed on the actions that were taken on insider risk management features.</span></span> <span data-ttu-id="54367-106">此日志允许独立审阅分配给一个或多个内部风险管理角色组的用户所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="54367-106">This log allows independent review of the actions taken by users assigned to one or more insider risk management role groups.</span></span> <span data-ttu-id="54367-107">内部风险管理审核日志在组织中自动启用，并且无法禁用。</span><span class="sxs-lookup"><span data-stu-id="54367-107">The insider risk management audit log is automatically enabled in your organization and cannot be disabled.</span></span>

![内部风险管理审核日志](../media/insider-risk-audit-log.png)

<span data-ttu-id="54367-109">每当审核日志活动时，都会自动更新并立即更新活动，日志将活动信息保留 180 天 (大约六个月) 。</span><span class="sxs-lookup"><span data-stu-id="54367-109">The audit log is automatically and immediately updated whenever monitored activities occur and the log retains information about the activity for 180 days (about six months).</span></span> <span data-ttu-id="54367-110">180 天后，活动的数据将从日志中永久删除。</span><span class="sxs-lookup"><span data-stu-id="54367-110">After 180 days, the data for the activity is permanently deleted from the log.</span></span>

<span data-ttu-id="54367-111">活动监视中包含的区域包括：</span><span class="sxs-lookup"><span data-stu-id="54367-111">Areas included in activity monitoring include:</span></span>

- <span data-ttu-id="54367-112">策略</span><span class="sxs-lookup"><span data-stu-id="54367-112">Policies</span></span>
- <span data-ttu-id="54367-113">案例</span><span class="sxs-lookup"><span data-stu-id="54367-113">Cases</span></span>
- <span data-ttu-id="54367-114">警报</span><span class="sxs-lookup"><span data-stu-id="54367-114">Alerts</span></span>
- <span data-ttu-id="54367-115">设置</span><span class="sxs-lookup"><span data-stu-id="54367-115">Settings</span></span>
- <span data-ttu-id="54367-116">用户</span><span class="sxs-lookup"><span data-stu-id="54367-116">Users</span></span>
- <span data-ttu-id="54367-117">通知模板</span><span class="sxs-lookup"><span data-stu-id="54367-117">Notice templates</span></span>

<span data-ttu-id="54367-118">若要查看和导出数据，审核日志内部风险管理或内部风险管理审核 *员* 角色组。 </span><span class="sxs-lookup"><span data-stu-id="54367-118">To view and export data from the audit log, users must be assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups.</span></span> <span data-ttu-id="54367-119">若要详细了解内部风险管理角色组，请参阅内部风险管理入门步骤 [1：启用权限](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)。</span><span class="sxs-lookup"><span data-stu-id="54367-119">To learn more about insider risk management role groups, see [Getting started with insider risk management Step 1: Enabling permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).</span></span>

>[!NOTE]
><span data-ttu-id="54367-120">内部风险管理审核日志与 Microsoft 365 审核日志，它们是独立的审核系统，并捕获有关单独活动的信息。</span><span class="sxs-lookup"><span data-stu-id="54367-120">The insider risk management audit log isn't associated with the Microsoft 365 audit log, they are independent auditing systems and capture information on separate activities.</span></span> <span data-ttu-id="54367-121">禁用 Microsoft 365 审核不会影响内部风险管理中的活动审核。</span><span class="sxs-lookup"><span data-stu-id="54367-121">Disabling Microsoft 365 auditing doesn't impact activity auditing within insider risk management.</span></span>

## <a name="view-activity-in-the-insider-risk-audit-log"></a><span data-ttu-id="54367-122">查看内部风险中心审核日志</span><span class="sxs-lookup"><span data-stu-id="54367-122">View activity in the insider risk audit log</span></span>

<span data-ttu-id="54367-123">若要查看针对内部风险管理监视的功能活动，请导航到任何内部风险管理审核日志右上方区域中的"预览体验成员风险报告"链接。默认情况下，你将看到针对内部风险管理活动显示的以下信息：</span><span class="sxs-lookup"><span data-stu-id="54367-123">To view feature activity monitored for insider risk management, navigate to, and select the **Insider risk audit log** link in the top-right area of any insider risk management tab. By default, you'll see the following information displayed for insider risk management activities:</span></span>

- <span data-ttu-id="54367-124">**活动：** 用户在内部风险管理解决方案中执行的活动的说明。</span><span class="sxs-lookup"><span data-stu-id="54367-124">**Activity:** A description of the activity taken within the insider risk management solution by a user.</span></span>
- <span data-ttu-id="54367-125">**类别：** 执行活动的一个或多个区域。</span><span class="sxs-lookup"><span data-stu-id="54367-125">**Category:** The area or item where the activity was performed.</span></span> <span data-ttu-id="54367-126">例如， *执行策略更改* 活动时，你将看到"策略"类别。</span><span class="sxs-lookup"><span data-stu-id="54367-126">For example, you'll see *Policies* as the category when policy change activities were performed.</span></span>
- <span data-ttu-id="54367-127">**由：** 执行活动的用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="54367-127">**Activity performed by:** The user name of the user that performed the activity.</span></span>
- <span data-ttu-id="54367-128">**日期：** 执行活动的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="54367-128">**Date:** The date and time the activity was performed.</span></span> <span data-ttu-id="54367-129">日期和时间是组织的本地日期和时间。</span><span class="sxs-lookup"><span data-stu-id="54367-129">The date and time are the local date and time for your organization.</span></span>

<span data-ttu-id="54367-130">有关记录的活动的详细信息，请选择活动以显示活动详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="54367-130">For more information about a logged activity, select the activity to display the activity details pane.</span></span> <span data-ttu-id="54367-131">此窗格包含有关活动的其他信息。</span><span class="sxs-lookup"><span data-stu-id="54367-131">This pane includes additional information about the activity.</span></span>

## <a name="columns-and-filtering"></a><span data-ttu-id="54367-132">列和筛选</span><span class="sxs-lookup"><span data-stu-id="54367-132">Columns and filtering</span></span>

<span data-ttu-id="54367-133">为了便于审核员查看记录的活动，预览体验成员风险中心支持 **审核日志。**</span><span class="sxs-lookup"><span data-stu-id="54367-133">To make it easier for auditors to review logged activity, filtering is supported in the **Insider risk audit log**.</span></span> <span data-ttu-id="54367-134">对于基本筛选，队列列可以添加到视图中，以提供文件和邮件的不同透视。</span><span class="sxs-lookup"><span data-stu-id="54367-134">For basic filtering, queue columns are available to add to the view to provide different pivots on the files and messages.</span></span> <span data-ttu-id="54367-135">您可以按"类别 **"、"日期范围"和"** 由字段 **执行的活动"来筛选** 活动。</span><span class="sxs-lookup"><span data-stu-id="54367-135">You can filter activities by the **Category, Date range,** and **Activity performed by** fields.</span></span>

<span data-ttu-id="54367-136">若要为活动队列添加或删除列标题，请使用 **"** 自定义列"控件并从列选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="54367-136">To add or remove column headings for the activity queue, use the **Customize columns** control and select from the column options.</span></span> <span data-ttu-id="54367-137">这些列映射到预览体验成员风险计划支持的审核日志本文稍后将列出。</span><span class="sxs-lookup"><span data-stu-id="54367-137">These columns map to common conditions supported in the **Insider risk audit log** and are listed later in this article.</span></span>

## <a name="audit-log-export"></a><span data-ttu-id="54367-138">审核日志导出</span><span class="sxs-lookup"><span data-stu-id="54367-138">Audit log export</span></span>

<span data-ttu-id="54367-139">分配给内部风险管理或内部风险管理审核员角色组的用户可以通过选择"预览体验成员风险 审核日志"页上的"导出"，将 审核日志 中所有活动导出到 .csv (逗号分隔值) **文件中。**</span><span class="sxs-lookup"><span data-stu-id="54367-139">Users assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups can export all activity in the audit log to a .csv (comma-separated values) file by selecting **Export** on the **Insider risk audit log** page.</span></span> <span data-ttu-id="54367-140">根据活动的不同，活动某些字段可能不适用于活动，这些字段将在导出的文件中显示为空白。</span><span class="sxs-lookup"><span data-stu-id="54367-140">Depending on the activity, some fields for an activity may not be applicable to the activity and these fields will appear as blank in the exported file.</span></span>

<span data-ttu-id="54367-141">该文件包含以下字段的活动信息：</span><span class="sxs-lookup"><span data-stu-id="54367-141">The file contains activity information for the following fields:</span></span>

- <span data-ttu-id="54367-142">**由：** 修改项目值的用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="54367-142">**Activity performed by:** The user name of the user modifying an item value.</span></span> <span data-ttu-id="54367-143">此处列出的用户被分配到以下一个或多个角色内部风险管理角色组 *：Insider Risk Management、Insider* Risk *Management Admins、Insider* *Risk Management Analysts、Insider* *Risk Management访问人员*。 [](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)</span><span class="sxs-lookup"><span data-stu-id="54367-143">Users listed here were assigned to one or more of the following role [insider risk management role groups](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management): *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*.</span></span> <span data-ttu-id="54367-144">每个角色组具有不同的权限级别来管理内部风险功能。</span><span class="sxs-lookup"><span data-stu-id="54367-144">Each role group has different permission levels for managing insider risk features.</span></span>
- <span data-ttu-id="54367-145">**活动：** 对项目执行的活动。</span><span class="sxs-lookup"><span data-stu-id="54367-145">**Activity:** The activity taken on an item.</span></span> <span data-ttu-id="54367-146">值为 *Viewed、Deleted、Added、Edited policy、Case、User、Alert 和* *Settings。*</span><span class="sxs-lookup"><span data-stu-id="54367-146">Values are *Viewed, Deleted, Added, Edited policy, Case, User, Alert,* and *Settings.*</span></span>
- <span data-ttu-id="54367-147">**添加**：在活动期间添加的对象，如用户、文件类型或域。</span><span class="sxs-lookup"><span data-stu-id="54367-147">**Added**: Objects that were added during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="54367-148">**警报量**：内部风险管理设置中定义的警报量级别。</span><span class="sxs-lookup"><span data-stu-id="54367-148">**Alert volume**: The level of alert volume defined in insider risk management settings.</span></span>
- <span data-ttu-id="54367-149">**金额**：当前选定的策略自定义指示器金额。</span><span class="sxs-lookup"><span data-stu-id="54367-149">**Amount**: The currently selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="54367-150">**资产 ID：** 执行活动的优先级物理资产的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="54367-150">**Asset ID**: The asset ID of the priority physical asset the activity was performed on.</span></span>
- <span data-ttu-id="54367-151">**类别：** 修改的项目的类别。</span><span class="sxs-lookup"><span data-stu-id="54367-151">**Category:** The category of the item modified.</span></span> <span data-ttu-id="54367-152">值为 *Policies、Cases、Users、Alerts、Settings 和* *Notice 模板。*</span><span class="sxs-lookup"><span data-stu-id="54367-152">Values are *Policies, Cases, Users, Alerts, Settings,* and *Notice templates.*</span></span>
- <span data-ttu-id="54367-153">**日期：** 日期和时间，在组织的本地日期和时间中列出。</span><span class="sxs-lookup"><span data-stu-id="54367-153">**Date:** Date and time, listed in your organization's local date and time.</span></span>
- <span data-ttu-id="54367-154">**说明**：用户为要处理的对象（如策略 (优先级用户组）输入的说明) 。</span><span class="sxs-lookup"><span data-stu-id="54367-154">**Description**: The description input by the user for the object being acted on (such as a policy or a priority user group).</span></span>
- <span data-ttu-id="54367-155">**DLP 策略**：已选择 (DLP) 策略，以触发包含在内部风险管理策略中。</span><span class="sxs-lookup"><span data-stu-id="54367-155">**DLP policy**: The data loss prevention (DLP) policy selected to trigger inclusion in an insider risk management policy.</span></span>
- <span data-ttu-id="54367-156">**指示器**：在内部风险设置内对活动执行的指示器 (例如添加或删除指示器) 。</span><span class="sxs-lookup"><span data-stu-id="54367-156">**Indicator**: The indicator in the within insider risk settings that the activity was performed on (such as adding or removing an indicator).</span></span>
- <span data-ttu-id="54367-157">**通知模板**：执行活动的通知模板。</span><span class="sxs-lookup"><span data-stu-id="54367-157">**Notice template**: The notice template the activity was performed on.</span></span>
- <span data-ttu-id="54367-158">**天数：** 在内部风险设置中定义的策略激活窗口。</span><span class="sxs-lookup"><span data-stu-id="54367-158">**Number of days**: The policy activation window defined in insider risk settings.</span></span>
- <span data-ttu-id="54367-159">**文件数**：在内部风险管理设置中定义的文件数量限制。</span><span class="sxs-lookup"><span data-stu-id="54367-159">**Number of files**: The file volume limit defined in insider risk management settings.</span></span>
- <span data-ttu-id="54367-160">**策略模板**：指示器所操作的策略模板属于该模板。</span><span class="sxs-lookup"><span data-stu-id="54367-160">**Policy template**: The policy template that the indicators acted on belongs to.</span></span>
- <span data-ttu-id="54367-161">**以前的金额**：以前选择的自定义指标策略金额。</span><span class="sxs-lookup"><span data-stu-id="54367-161">**Previous amount**: The previously selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="54367-162">**优先级用户组**：执行活动的优先级用户组。</span><span class="sxs-lookup"><span data-stu-id="54367-162">**Priority user group**: The priority user group the activity was performed on.</span></span>
- <span data-ttu-id="54367-163">**已删除**：活动期间删除的对象，如用户、文件类型或域。</span><span class="sxs-lookup"><span data-stu-id="54367-163">**Removed**: Objects that were removed during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="54367-164">**发件人**：活动执行通知模板的发件人字段。</span><span class="sxs-lookup"><span data-stu-id="54367-164">**Sender**: The sender field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="54367-165">**目标策略**：在用户上执行活动 (例如向用户添加用户或删除用户) 。</span><span class="sxs-lookup"><span data-stu-id="54367-165">**Target policy**: The policy the activity was performed on (such as adding a user to or removing a user from).</span></span>
- <span data-ttu-id="54367-166">**模板邮件正文**：执行活动的通知模板的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="54367-166">**Template message body**: The message body of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="54367-167">**模板主题**：执行活动的通知模板的主题字段。</span><span class="sxs-lookup"><span data-stu-id="54367-167">**Template subject**: The subject field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="54367-168">**用户：** 执行活动的用户。</span><span class="sxs-lookup"><span data-stu-id="54367-168">**User:** User the activity was performed on.</span></span>
