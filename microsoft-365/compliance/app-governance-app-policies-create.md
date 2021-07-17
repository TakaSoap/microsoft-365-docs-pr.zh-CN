---
title: 创建应用策略
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
description: 创建应用策略。
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438056"
---
# <a name="create-app-policies"></a><span data-ttu-id="5b602-103">创建应用策略</span><span class="sxs-lookup"><span data-stu-id="5b602-103">Create app policies</span></span>

><span data-ttu-id="5b602-104">*[Microsoft 365 安全与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="5b602-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5b602-105">除了一组用于检测异常应用行为和生成警报的内置功能外，Microsoft 应用治理中的应用策略也可以帮助你:</span><span class="sxs-lookup"><span data-stu-id="5b602-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="5b602-106">指定应用治理可以提醒应用行为以进行自动或手动修正的条件。</span><span class="sxs-lookup"><span data-stu-id="5b602-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="5b602-107">为组织实施应用合规性策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="5b602-108">可以根据提供的可自定义模板创建应用策略，也可以创建自己的自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="5b602-109">要创建新的应用策略，请转到“**Microsoft 365 合规中心”>“应用治理”>“概述”页面>“策略**”:</span><span class="sxs-lookup"><span data-stu-id="5b602-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="5b602-110">要使用专为应用使用设计的模板新建应用策略，请选择 **创建应用使用策略** 下的“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="5b602-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="5b602-111">要使用专为应用权限设计的模板新建应用策略，请选择 **创建应用权限策略** 下的 **创建策略**。</span><span class="sxs-lookup"><span data-stu-id="5b602-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="5b602-112">要新建应用认证的应用策略或创建自定义策略，请选择 **新建**。</span><span class="sxs-lookup"><span data-stu-id="5b602-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="5b602-113">应用策略模板</span><span class="sxs-lookup"><span data-stu-id="5b602-113">App policy templates</span></span>

<span data-ttu-id="5b602-114">要基于应用策略模板新建应用策略，请在 **选择应用策略模板页面** 中选择应用模板类别，选择模板名称，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="5b602-115">应用治理有三种应用策略模板。</span><span class="sxs-lookup"><span data-stu-id="5b602-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="5b602-116">应用用户和数据访问</span><span class="sxs-lookup"><span data-stu-id="5b602-116">App users and data access</span></span>

<span data-ttu-id="5b602-117">应用治理包含这些用于生成应用使用警报的模板。</span><span class="sxs-lookup"><span data-stu-id="5b602-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="5b602-118">模板名称</span><span class="sxs-lookup"><span data-stu-id="5b602-118">Template name</span></span> | <span data-ttu-id="5b602-119">说明</span><span class="sxs-lookup"><span data-stu-id="5b602-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5b602-120">具有大量数据访问的新应用</span><span class="sxs-lookup"><span data-stu-id="5b602-120">New app with a high volume of data access</span></span> | <span data-ttu-id="5b602-121">突出显示具有大量数据访问的最近注册应用，以确保这些数据模式符合预期。</span><span class="sxs-lookup"><span data-stu-id="5b602-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="5b602-122">默认情况下，此策略将标记所有在过去 7 天内注册的、且在此期间数据访问量超过 1 GB 的应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="5b602-123">可以使用更多条件和操作自定义此策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="5b602-124">应用权限</span><span class="sxs-lookup"><span data-stu-id="5b602-124">App Permissions</span></span>

<span data-ttu-id="5b602-125">应用治理包含这些用于生成应用权限警报的模板。</span><span class="sxs-lookup"><span data-stu-id="5b602-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="5b602-126">模板名称</span><span class="sxs-lookup"><span data-stu-id="5b602-126">Template name</span></span> | <span data-ttu-id="5b602-127">说明</span><span class="sxs-lookup"><span data-stu-id="5b602-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5b602-128">特权过多的应用</span><span class="sxs-lookup"><span data-stu-id="5b602-128">Overprivileged apps</span></span> | <span data-ttu-id="5b602-129">突出显示授予的权限超过那些应用使用的权限的应用，以确定可能减少权限的机会。</span><span class="sxs-lookup"><span data-stu-id="5b602-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="5b602-130">默认情况下，如果 90 天内未使用，此策略将标记所有标记为“特权过多”的应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="5b602-131">可以使用更多条件和操作自定义此时间段过滤器。</span><span class="sxs-lookup"><span data-stu-id="5b602-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="5b602-132">具有高特权权限的新应用</span><span class="sxs-lookup"><span data-stu-id="5b602-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="5b602-133">突出显示所有具有高特权权限的新应用，以确定可能需要进一步调查的潜在高占用空间应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="5b602-134">默认情况下，此策略将标记所有在过去 7 天内注册的、具有高范围权限的应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="5b602-135">应用认证</span><span class="sxs-lookup"><span data-stu-id="5b602-135">App certification</span></span>

<span data-ttu-id="5b602-136">应用治理包含这些用于生成应用认证警报的模板。</span><span class="sxs-lookup"><span data-stu-id="5b602-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="5b602-137">模板名称</span><span class="sxs-lookup"><span data-stu-id="5b602-137">Template name</span></span> | <span data-ttu-id="5b602-138">说明</span><span class="sxs-lookup"><span data-stu-id="5b602-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5b602-139">未经认证的新应用</span><span class="sxs-lookup"><span data-stu-id="5b602-139">New uncertified app</span></span> | <span data-ttu-id="5b602-140">突出显示尚未通过应用认证流程的新应用，以确保其在租户中符合预期。</span><span class="sxs-lookup"><span data-stu-id="5b602-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="5b602-141">默认情况下，此策略将标记所有在过去 7 天内注册且未经认证的应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="5b602-142">自定义应用策略</span><span class="sxs-lookup"><span data-stu-id="5b602-142">Custom app policies</span></span>

<span data-ttu-id="5b602-143">当需要执行某个内置模板尚未完成的操作时，请使用自定义应用策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="5b602-144">要新建自定义应用策略，请先在 **策略** 页面中选择 **新建**。</span><span class="sxs-lookup"><span data-stu-id="5b602-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="5b602-145">在 **选择应用策略模板页面**，选择 **自定义** 类别、**自定义策略** 模板，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="5b602-146">在 **名称和说明** 页面，配置以下内容:</span><span class="sxs-lookup"><span data-stu-id="5b602-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="5b602-147">策略名称</span><span class="sxs-lookup"><span data-stu-id="5b602-147">Policy Name</span></span>

- <span data-ttu-id="5b602-148">策略说明</span><span class="sxs-lookup"><span data-stu-id="5b602-148">Policy Description</span></span>

- <span data-ttu-id="5b602-149">选择策略严重性，设置此策略生成的警报的严重性。</span><span class="sxs-lookup"><span data-stu-id="5b602-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="5b602-150">High</span><span class="sxs-lookup"><span data-stu-id="5b602-150">High</span></span>
  - <span data-ttu-id="5b602-151">Medium</span><span class="sxs-lookup"><span data-stu-id="5b602-151">Medium</span></span>
  - <span data-ttu-id="5b602-152">低</span><span class="sxs-lookup"><span data-stu-id="5b602-152">Low</span></span>

<span data-ttu-id="5b602-153">在 **选择策略设置和条件** 页面，对于 **选择此策略适用的应用**，选择:</span><span class="sxs-lookup"><span data-stu-id="5b602-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="5b602-154">所有应用</span><span class="sxs-lookup"><span data-stu-id="5b602-154">All Apps</span></span>
- <span data-ttu-id="5b602-155">选择特定应用</span><span class="sxs-lookup"><span data-stu-id="5b602-155">Choose specific apps</span></span>

  <span data-ttu-id="5b602-156">允许选择一个或多个应用的窗格。</span><span class="sxs-lookup"><span data-stu-id="5b602-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="5b602-157">选择 **添加**。</span><span class="sxs-lookup"><span data-stu-id="5b602-157">Select **Add**.</span></span>

<span data-ttu-id="5b602-158">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-158">Select **Next**.</span></span>

<span data-ttu-id="5b602-159">在 **选择策略设置和条件** 页面，选择 **设置策略的新条件**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="5b602-160">**创建规则** 窗格允许选择新规则的条件。</span><span class="sxs-lookup"><span data-stu-id="5b602-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="5b602-161">选择 **添加条件** 并从条件列表中进行选择，然后指定条件的值。</span><span class="sxs-lookup"><span data-stu-id="5b602-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="5b602-162">可以添加多个条件。</span><span class="sxs-lookup"><span data-stu-id="5b602-162">You can add multiple conditions.</span></span>

<span data-ttu-id="5b602-163">以下是自定义应用策略的可用条件。</span><span class="sxs-lookup"><span data-stu-id="5b602-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="5b602-164">条件</span><span class="sxs-lookup"><span data-stu-id="5b602-164">Condition</span></span> | <span data-ttu-id="5b602-165">接受的条件值</span><span class="sxs-lookup"><span data-stu-id="5b602-165">Condition values accepted</span></span> | <span data-ttu-id="5b602-166">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b602-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="5b602-167">应用注册年龄</span><span class="sxs-lookup"><span data-stu-id="5b602-167">App registration age</span></span> | <span data-ttu-id="5b602-168">过去 X 天内</span><span class="sxs-lookup"><span data-stu-id="5b602-168">Within last X days</span></span> |  |
| <span data-ttu-id="5b602-169">应用认证</span><span class="sxs-lookup"><span data-stu-id="5b602-169">App certification</span></span> | <span data-ttu-id="5b602-170">基本合规性、MCAS 合规性或 N/A</span><span class="sxs-lookup"><span data-stu-id="5b602-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="5b602-171">Microsoft 365 认证</span><span class="sxs-lookup"><span data-stu-id="5b602-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="5b602-172">发布者验证</span><span class="sxs-lookup"><span data-stu-id="5b602-172">Publisher verification</span></span> | <span data-ttu-id="5b602-173">是或否</span><span class="sxs-lookup"><span data-stu-id="5b602-173">Yes or No</span></span> | [<span data-ttu-id="5b602-174">发布者验证</span><span class="sxs-lookup"><span data-stu-id="5b602-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="5b602-175">应用程序权限</span><span class="sxs-lookup"><span data-stu-id="5b602-175">Application Permission</span></span> | <span data-ttu-id="5b602-176">从列表中选择一个或多个 API 权限</span><span class="sxs-lookup"><span data-stu-id="5b602-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="5b602-177">Microsoft Graph 权限参考</span><span class="sxs-lookup"><span data-stu-id="5b602-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="5b602-178">委托的权限</span><span class="sxs-lookup"><span data-stu-id="5b602-178">Delegated Permission</span></span> | <span data-ttu-id="5b602-179">从列表中选择一个或多个 API 权限</span><span class="sxs-lookup"><span data-stu-id="5b602-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="5b602-180">Microsoft Graph 权限参考</span><span class="sxs-lookup"><span data-stu-id="5b602-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="5b602-181">高权限</span><span class="sxs-lookup"><span data-stu-id="5b602-181">High privilege</span></span> | <span data-ttu-id="5b602-182">是或否</span><span class="sxs-lookup"><span data-stu-id="5b602-182">Yes or No</span></span> | <span data-ttu-id="5b602-183">这是基于 MCAS 使用的相同逻辑的内部指定。</span><span class="sxs-lookup"><span data-stu-id="5b602-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="5b602-184">特权过多的应用</span><span class="sxs-lookup"><span data-stu-id="5b602-184">Overprivileged app</span></span> | <span data-ttu-id="5b602-185">是或否</span><span class="sxs-lookup"><span data-stu-id="5b602-185">Yes or No</span></span> | <span data-ttu-id="5b602-186">授予的权限超过那些应用使用的权限的应用。</span><span class="sxs-lookup"><span data-stu-id="5b602-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="5b602-187">应用数据访问</span><span class="sxs-lookup"><span data-stu-id="5b602-187">App data access</span></span> | <span data-ttu-id="5b602-188">每小时数据访问量超过 X GB</span><span class="sxs-lookup"><span data-stu-id="5b602-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="5b602-189">应用数据访问趋势</span><span class="sxs-lookup"><span data-stu-id="5b602-189">App data access trend</span></span> | <span data-ttu-id="5b602-190">过去 7 天内数据使用量增加 X%</span><span class="sxs-lookup"><span data-stu-id="5b602-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="5b602-191">应用 API 访问</span><span class="sxs-lookup"><span data-stu-id="5b602-191">App API Access</span></span> | <span data-ttu-id="5b602-192">每小时 API 调用数超过 X</span><span class="sxs-lookup"><span data-stu-id="5b602-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="5b602-193">应用 API 访问趋势</span><span class="sxs-lookup"><span data-stu-id="5b602-193">App API Access trend</span></span> | <span data-ttu-id="5b602-194">过去 7 天内 API 调用数增加 X%</span><span class="sxs-lookup"><span data-stu-id="5b602-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="5b602-195">同意的用户</span><span class="sxs-lookup"><span data-stu-id="5b602-195">Users consented</span></span> | <span data-ttu-id="5b602-196">同意的用户(超过或不足)X</span><span class="sxs-lookup"><span data-stu-id="5b602-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="5b602-197">同意的优先用户</span><span class="sxs-lookup"><span data-stu-id="5b602-197">Priority user consented</span></span> | <span data-ttu-id="5b602-198">是或否</span><span class="sxs-lookup"><span data-stu-id="5b602-198">Yes or No</span></span> | <span data-ttu-id="5b602-199">具有 [优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 的用户。</span><span class="sxs-lookup"><span data-stu-id="5b602-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="5b602-200">应用同意者</span><span class="sxs-lookup"><span data-stu-id="5b602-200">App consented by</span></span> | <span data-ttu-id="5b602-201">从列表中选择用户</span><span class="sxs-lookup"><span data-stu-id="5b602-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="5b602-202">正在同意的用户角色</span><span class="sxs-lookup"><span data-stu-id="5b602-202">Consenting user’s role</span></span> | <span data-ttu-id="5b602-203">选择一个或多个: Teams 管理员、目录读取者、安全信息读取者、合规性管理员、安全管理员、帮助台管理员、SharePoint 管理员、Exchange 管理员、全局读取者、全局管理员、合规性数据管理员、用户管理员、服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="5b602-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="5b602-204">允许多个选择。</span><span class="sxs-lookup"><span data-stu-id="5b602-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="5b602-205">此列表中应提供具有已分配成员的 Azure AD 角色。</span><span class="sxs-lookup"><span data-stu-id="5b602-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="5b602-206">已访问的工作负载</span><span class="sxs-lookup"><span data-stu-id="5b602-206">Workload accessed</span></span> | <span data-ttu-id="5b602-207">OneDrive 和/或 SharePoint 和/或 Exchange</span><span class="sxs-lookup"><span data-stu-id="5b602-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="5b602-208">允许多个选择。</span><span class="sxs-lookup"><span data-stu-id="5b602-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="5b602-209">错误率</span><span class="sxs-lookup"><span data-stu-id="5b602-209">Error rate</span></span> | <span data-ttu-id="5b602-210">在过去 7 天内，错误率大于 X%，其中 X 为管理员定义的值</span><span class="sxs-lookup"><span data-stu-id="5b602-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="5b602-211">必须满足所有指定的条件才可应用此应用策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="5b602-212">指定条件后，选择 **保存**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="5b602-213">在 **定义策略操作** 页面，如果你希望应用治理在生成基于此策略的警报时禁用应用，请选择 **禁用应用**，然后选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="5b602-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="5b602-214">在 **定义策略状态** 页面，选择以下其中一个选项:</span><span class="sxs-lookup"><span data-stu-id="5b602-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="5b602-215">**审核模式**: 评估策略但不执行配置的操作。</span><span class="sxs-lookup"><span data-stu-id="5b602-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="5b602-216">审核模式策略在策略列表中显示为 **审核** 状态。</span><span class="sxs-lookup"><span data-stu-id="5b602-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="5b602-217">**活动**: 评估策略并执行配置的操作。</span><span class="sxs-lookup"><span data-stu-id="5b602-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="5b602-218">**非活动**: 不评估策略且不执行配置的操作。</span><span class="sxs-lookup"><span data-stu-id="5b602-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="5b602-219">测试并监视新的应用策略</span><span class="sxs-lookup"><span data-stu-id="5b602-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="5b602-220">现在，应用策略已经创建，你应在 **策略** 页面中进行监视，以确保在测试期间其注册的活动警报数和警报总数符合预期。</span><span class="sxs-lookup"><span data-stu-id="5b602-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![Microsoft 365 合规中心中的 MAPG 策略摘要页面，其中突出显示了某项策略](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="5b602-222">如果警报数为预期之外的低值，请编辑应用策略的设置，以确保在设置其状态之前进行正确配置。</span><span class="sxs-lookup"><span data-stu-id="5b602-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="5b602-223">以下是新建策略、测试策略并使其处于活动状态的流程的示例:</span><span class="sxs-lookup"><span data-stu-id="5b602-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="5b602-224">新建策略，将严重性、应用、条件以及操作设置为初始值，并将状态设置为 **审核模式**。</span><span class="sxs-lookup"><span data-stu-id="5b602-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="5b602-225">检查预期行为，例如生成的警报。</span><span class="sxs-lookup"><span data-stu-id="5b602-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="5b602-226">如果行为不符合预期，请根据需要编辑策略应用、条件以及操作设置，并返回步骤 2。</span><span class="sxs-lookup"><span data-stu-id="5b602-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="5b602-227">如果行为符合预期，请编辑策略并将其状态更改为 **活动**。</span><span class="sxs-lookup"><span data-stu-id="5b602-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![创建应用策略工作流](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="5b602-229">下一步</span><span class="sxs-lookup"><span data-stu-id="5b602-229">Next step</span></span>

[<span data-ttu-id="5b602-230">管理应用策略。</span><span class="sxs-lookup"><span data-stu-id="5b602-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
