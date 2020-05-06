---
title: Microsoft 合规性管理器发行说明
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-mar2020
description: 查看发行说明，其中包含有关在 Microsoft 合规性管理器中的新功能和已知问题（要在即将推出的版本中解决）的信息。
ms.openlocfilehash: fb462939ef1b1bf0c6f7f4552359d50645b528f3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033702"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a><span data-ttu-id="7ffb5-103">Microsoft 合规性管理器（预览）发行说明</span><span class="sxs-lookup"><span data-stu-id="7ffb5-103">Microsoft Compliance Manager (preview) release notes</span></span>

<span data-ttu-id="7ffb5-104">合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-104">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="7ffb5-105">此页面包含有关当前版本的新功能、改进功能和已知问题的更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-105">This page contains updates on new features, improved functionality, and known issues with the current release.</span></span>

<span data-ttu-id="7ffb5-106">您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-106">You can use the [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="improved-template-creation-and-update-process"></a><span data-ttu-id="7ffb5-107">改进的模板创建和更新过程</span><span class="sxs-lookup"><span data-stu-id="7ffb5-107">Improved template creation and update process</span></span>

<span data-ttu-id="7ffb5-108">我们已经更新了导入、导出和修改用于评估的模板的过程。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-108">We've updated the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="7ffb5-109">全新的简化体验使您能够更轻松地将自己的评估引入工作流并将其更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-109">The new, simplified experience will make it easier for you to bring your own assessments into your workflow and keep them updated.</span></span>

### <a name="the-old-process"></a><span data-ttu-id="7ffb5-110">旧进程</span><span class="sxs-lookup"><span data-stu-id="7ffb5-110">The old process</span></span>

<span data-ttu-id="7ffb5-111">在合规性管理器中创建模板的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-111">There were two ways of creating a template in Compliance Manager.</span></span> <span data-ttu-id="7ffb5-112">您可以复制现有模板，或将模板数据从 Excel 电子表格导入到新模板中。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-112">You could copy an existing template, or import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="7ffb5-113">在 "**模板**" 页上，选择 " **+ 添加模板**" 以创建新模板，方法是输入名称，选择 "维度"，然后上传具有特定格式和架构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-113">From your **Templates** page, you'd select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="7ffb5-114">或者，您可以选中 "**从现有模板复制**" 框，选择要复制的模板，然后验证维度。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-114">Or you could check the **Copy from an existing template** box, select a template to copy, and verify dimensions.</span></span> <span data-ttu-id="7ffb5-115">设计自定义模板需要一个多步骤过程，该过程是在创建模板后选择 "**添加自定义控件**" 开始执行的。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-115">Design customization your template required a multi-step process that began by selecting **Add custom control** after creating your template.</span></span>

### <a name="the-new-process"></a><span data-ttu-id="7ffb5-116">新进程</span><span class="sxs-lookup"><span data-stu-id="7ffb5-116">The new process</span></span>

<span data-ttu-id="7ffb5-117">我们使您能够更轻松地创建新模板。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-117">We made it easier for you to create new templates.</span></span> <span data-ttu-id="7ffb5-118">在单步**扩展**过程中，可以将包含操作和控件的电子表格添加到现有的 Microsoft 模板中，以生成自己的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="7ffb5-119">在合规性管理器的 "**模板**" 页上，选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-119">At your **Templates** page in Compliance Manager, select **+ Add template**.</span></span> <span data-ttu-id="7ffb5-120">在 "**模板**" 浮出控件窗格中，选中 "**从全局模板创建扩展**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-120">On the **Template** flyout pane, select the **Create extension from global template** checkbox.</span></span> <span data-ttu-id="7ffb5-121">您可以使用比以前更复杂的新 Excel 格式添加自定义项。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-121">You can add customizations with a new Excel format that is less complex than the previous one.</span></span> <span data-ttu-id="7ffb5-122">此新进程将替换**现有模板中**的前一副本并**添加自定义控件**函数。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-122">This new process replaces the former **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="7ffb5-123">每次通过以下概述的版本控制过程更新最初的评估时，您的自定义评估将继承这些更新并保留您的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-123">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="7ffb5-124">此外，还可以更轻松地修改您自己的现有模板。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-124">It's also easier to modify your own existing templates.</span></span> <span data-ttu-id="7ffb5-125">您可以导出模板，在同一工作簿中进行更改，然后在保存编辑内容后将其导入。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-125">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="7ffb5-126">查看有关使用此新过程[创建模板](working-with-compliance-manager.md#templates)的详细说明。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-126">View detailed instructions on [creating templates](working-with-compliance-manager.md#templates) with this new process.</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="7ffb5-127">版本控制通知和控制</span><span class="sxs-lookup"><span data-stu-id="7ffb5-127">Versioning notice and control</span></span>

<span data-ttu-id="7ffb5-128">您的组织在2020年4月发布的合规性管理器中收到更新的评估，以帮助您与认证和法规更新保持一致。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-128">Your organization received updated assessments in the April 2020 release of Compliance Manager to help you align with certification and regulation updates.</span></span> <span data-ttu-id="7ffb5-129">向前发展，我们将为你提供一个清楚的方法，以便你了解并接受通过**版本控制警报**的所有未来更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-129">Moving forward, we'll provide a clear way for you to understand and accept all future updates through **versioning alerts**.</span></span>

<span data-ttu-id="7ffb5-130">只要有更新可用于评估模板或改进操作，警报图标都会通知您更新已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-130">Whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="7ffb5-131">当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-131">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="7ffb5-132">选择警报图标可显示一个弹出窗格，该窗口说明更新并提示您接受。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept.</span></span> <span data-ttu-id="7ffb5-133">了解有关[接受评估更新](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-133">Learn more about [accepting updates to assessments](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="7ffb5-134">常见操作将同步组之间的状态</span><span class="sxs-lookup"><span data-stu-id="7ffb5-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="7ffb5-135">如果您的组织具有多个评估组，**技术**操作（即影响整个组织的操作）的行为已发生更改。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) has changed.</span></span> <span data-ttu-id="7ffb5-136">跨组的任何重复操作都已合并到一个单一操作中。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-136">Any duplicate actions across groups have been combined into one single action.</span></span> <span data-ttu-id="7ffb5-137">该单个操作包含所有已上载的笔记和来自重复版本的证据。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-137">That single action contains all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="7ffb5-138">进行此更改后，技术操作现在的行为与它们属于同一组时的行为相同。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-138">With this change, technical actions will now behave as they did when they belonged to the same group.</span></span> <span data-ttu-id="7ffb5-139">现在，在一个组或评估中对操作所做的任何更改都将反映在所有实例中。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="7ffb5-140">**实现状态**、**实现日期**、**测试状态**和**测试日期**将反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-140">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="7ffb5-141">语言支持</span><span class="sxs-lookup"><span data-stu-id="7ffb5-141">Language support</span></span>

<span data-ttu-id="7ffb5-142">合规性管理器现已提供以下语言版本，除了英语：简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-142">Compliance Manager is now available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="7ffb5-143">合规性管理器中的已知问题（预览）</span><span class="sxs-lookup"><span data-stu-id="7ffb5-143">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="7ffb5-144">以下部分介绍了当前版本的合规性管理器中的已知问题。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-144">The following section covers known issues in the current release of Compliance Manager.</span></span>

### <a name="dimension-values"></a><span data-ttu-id="7ffb5-145">维度值</span><span class="sxs-lookup"><span data-stu-id="7ffb5-145">Dimension values</span></span>

<span data-ttu-id="7ffb5-146">由于数据迁移在2020年4月的版本中，一些组织可能会在其评估和模板中看到**产品**或**证书**值 "custom"。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-146">As a result of data migration during the April 2020 release, some organizations may see a **Product** or **Certification** value of "custom" in their assessments and templates.</span></span> <span data-ttu-id="7ffb5-147">如果 "**产品**" 或 "**证书**" 字段为空，则会自动插入此值，并且不会对数据工作流产生影响。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-147">This value was inserted automatically if the **Product** or **Certification** fields were blank, and there won't be an effect on data workflows.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="7ffb5-148">合规性分数</span><span class="sxs-lookup"><span data-stu-id="7ffb5-148">Compliance Score</span></span>

- <span data-ttu-id="7ffb5-149">对于标记为**不在范围**内的措施项，分配给该措施项的分数不会从合规性分数计算中排除。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-149">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="7ffb5-150">标记为**不在范围内的**操作项不会增加合规性分数。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-150">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="7ffb5-151">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="7ffb5-151">Secure Score</span></span>

- <span data-ttu-id="7ffb5-152">安全分数结果不适用于某些 Microsoft 365 和 Office 365 订阅中的某些操作项。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-152">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="7ffb5-153">在这些情况下，**无法检测到**安全分数结果。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-153">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="7ffb5-154">有时，不完成相应策略和操作项目的安全分数结果。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-154">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="7ffb5-155">对于新租户，将自动打开所有操作的安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-155">For new tenants, Secure Score updates for all actions are automatically turned on.</span></span> <span data-ttu-id="7ffb5-156">全局管理员可以将 "安全分数连续更新" 开关设置为 "关闭"，这将关闭所有操作的更新。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-156">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="7ffb5-157">**注意**：当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-157">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="7ffb5-158">在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-158">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="7ffb5-159">在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-159">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="7ffb5-160">如果启用了安全分数更新，尽管操作的测试日期不会更新以反映监控情况，但这些操作将积极受到安全分数的监控。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-160">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action's test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="7ffb5-161">在创建新的评估时，分数将自动包含 Microsoft 托管的控制得分和安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-161">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="7ffb5-162">安全分数集成不支持的任何操作都可以手动实现。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-162">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="7ffb5-163">手动实现将考虑该操作的组的分数。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-163">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="export"></a><span data-ttu-id="7ffb5-164">导出</span><span class="sxs-lookup"><span data-stu-id="7ffb5-164">Export</span></span>

- <span data-ttu-id="7ffb5-165">将模板状态设置为 "已**导入**" 或 "**待审批**" 时，模板导出到 JSON 失败。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-165">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="7ffb5-166">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="7ffb5-166">Supported browsers</span></span>

- <span data-ttu-id="7ffb5-167">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-167">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="7ffb5-168">在刷新浏览器之前，可能会出现更新数据未显示的实例。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-168">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="7ffb5-169">Microsoft Edge 的预览版本不受支持，但没有已知问题。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-169">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="7ffb5-170">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-170">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="7ffb5-171">会话超时</span><span class="sxs-lookup"><span data-stu-id="7ffb5-171">Session timeout</span></span>

- <span data-ttu-id="7ffb5-172">会话超时时，可能会出现 "发生错误" 错误。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-172">When a session times out, a "Something went wrong" error may appear.</span></span> <span data-ttu-id="7ffb5-173">若要解决此问题，请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="7ffb5-173">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
