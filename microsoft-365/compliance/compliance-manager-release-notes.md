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
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: 3fc16e92e912676d7aedc861ffe8306d68388c95
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635140"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="d2fdd-104">合规性管理器的发行说明（预览）</span><span class="sxs-lookup"><span data-stu-id="d2fdd-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="d2fdd-105">合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="d2fdd-106">您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的更新的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="d2fdd-107">合规性管理器中的新增功能（预览）</span><span class="sxs-lookup"><span data-stu-id="d2fdd-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="d2fdd-108">**基于角色的对合规性管理器的访问：** 已删除默认的**来宾访问**角色。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="d2fdd-109">为使用户能够访问合规性管理器，全局管理员必须为[每个用户分配一个权限](compliance-manager-overview.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="d2fdd-110">**更新的合规性分数**：合规性分数现在包括 Microsoft 管理的操作的分数。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="d2fdd-111">因此，你的分数将增加。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="d2fdd-112">**Actions 项：** 操作项现在是单个项目，并且许多包含来自 Microsoft 安全分数图形 API 的遥测集合。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="d2fdd-113">在可能的情况下，技术操作建议现在有指向 Office 365 服务中适用配置页面的链接。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="d2fdd-114">**租户管理：** 用于管理合规性管理器中的新数据元素的新界面（预览）：</span><span class="sxs-lookup"><span data-stu-id="d2fdd-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="d2fdd-115">**维：** 查看、添加和自定义模板、评估和操作项的元数据，以允许您为筛选器创建自定义透视。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="d2fdd-116">**所有者：** 为每个即席项目指定一个所有者。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="d2fdd-117">**客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并启用/禁用与安全得分集成的操作项的安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="d2fdd-118">合规性管理器中的已知问题（预览）</span><span class="sxs-lookup"><span data-stu-id="d2fdd-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="d2fdd-119">以下各节介绍了即将在即将发布的合规性管理器中解决的已知问题。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="d2fdd-120">合规性分数</span><span class="sxs-lookup"><span data-stu-id="d2fdd-120">Compliance Score</span></span>

- <span data-ttu-id="d2fdd-121">对于标记为**不在范围**内的措施项，分配给该措施项的分数不会从合规性分数计算中排除。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="d2fdd-122">标记为**不在范围内的**操作项不会增加合规性分数。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-122">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="d2fdd-123">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="d2fdd-123">Secure Score</span></span>

- <span data-ttu-id="d2fdd-124">安全分数结果不适用于某些 Microsoft 365 和 Office 365 订阅中的某些操作项。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-124">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="d2fdd-125">在这些情况下，**无法检测到**安全分数结果。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="d2fdd-126">有时，不完成相应策略和操作项目的安全分数结果。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="d2fdd-127">对于新租户，将自动打开所有操作的安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="d2fdd-128">全局管理员可以将 "安全分数连续更新" 开关设置为 "关闭"，这将关闭所有操作的更新。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="d2fdd-129">**注意**：当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-129">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="d2fdd-130">在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-130">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="d2fdd-131">在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-131">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="d2fdd-132">如果启用了安全分数更新，尽管操作的测试日期不会更新以反映监控情况，但这些操作将积极受到安全分数的监控。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-132">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="d2fdd-133">在创建新的评估时，分数将自动包含 Microsoft 托管的控制得分和安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-133">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="d2fdd-134">安全分数集成不支持的任何操作都可以手动实现。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-134">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="d2fdd-135">手动实现将考虑该操作的组的分数。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-135">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="d2fdd-136">Microsoft 托管控件</span><span class="sxs-lookup"><span data-stu-id="d2fdd-136">Microsoft-managed controls</span></span>

- <span data-ttu-id="d2fdd-137">Microsoft 托管控件的测试日期不会显示在 UI 中，即使在评估中也不会如此。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-137">The test date for Microsoft-managed controls isn't appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="d2fdd-138">若要查看测试日期信息，必须导出该评估。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-138">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="d2fdd-139">自定义</span><span class="sxs-lookup"><span data-stu-id="d2fdd-139">Customization</span></span>

- <span data-ttu-id="d2fdd-140">通过添加自定义控件，可以向现有控件系列添加新控件，但不允许您添加新的控件系列。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-140">Adding custom Controls enables adding a new control to an existing control family, but it doesn't allow you to add a new Control Family.</span></span>
- <span data-ttu-id="d2fdd-141">此版本不支持链接操作项，也不能向评估添加操作项或控件。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-141">This release doesn't support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="d2fdd-142">如果创建自定义操作，则不能对其进行编辑或将其删除。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-142">If you create a custom Action, you can't edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="d2fdd-143">控制系列未在评估中显示</span><span class="sxs-lookup"><span data-stu-id="d2fdd-143">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="d2fdd-144">导入模板时，基于该模板的所有评估都会反映属于该模板的所有控制系列。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-144">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="d2fdd-145">但是，如果向模板中添加新的控制系列，则任何现有评估都不会反映这些更改。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-145">But if you add new Control Families to the Template, any existing Assessments won't reflect the changes.</span></span> <span data-ttu-id="d2fdd-146">仅由更新后的模板创建的新评估将反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-146">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="d2fdd-147">模板</span><span class="sxs-lookup"><span data-stu-id="d2fdd-147">Templates</span></span>

- <span data-ttu-id="d2fdd-148">创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-148">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="d2fdd-149">存档的模板是可编辑的，不应是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-149">Archived templates are editable and they shouldn't be editable.</span></span>
- <span data-ttu-id="d2fdd-150">锁定的模板允许在不应进行评估时创建评估。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-150">Locked templates allow for Assessment creation when they shouldn't.</span></span> <span data-ttu-id="d2fdd-151">锁定模板旨在防止它用于创建评估。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-151">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="d2fdd-152">导出</span><span class="sxs-lookup"><span data-stu-id="d2fdd-152">Export</span></span>

- <span data-ttu-id="d2fdd-153">将模板状态设置为 "已**导入**" 或 "**待审批**" 时，模板导出到 JSON 失败。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-153">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="d2fdd-154">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="d2fdd-154">Supported browsers</span></span>

- <span data-ttu-id="d2fdd-155">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-155">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="d2fdd-156">在刷新浏览器之前，可能会出现更新数据未显示的实例。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-156">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="d2fdd-157">Microsoft Edge 的预览版本不受支持，但没有已知问题。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-157">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="d2fdd-158">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-158">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="d2fdd-159">会话超时</span><span class="sxs-lookup"><span data-stu-id="d2fdd-159">Session timeout</span></span>

- <span data-ttu-id="d2fdd-160">会话超时时，可能会出现 "发生错误" 错误。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-160">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="d2fdd-161">若要解决此问题，请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-161">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="d2fdd-162">语言支持</span><span class="sxs-lookup"><span data-stu-id="d2fdd-162">Language support</span></span>

- <span data-ttu-id="d2fdd-163">并非所有网页都支持所有语言。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-163">All languages aren't supported for all webpages.</span></span> <span data-ttu-id="d2fdd-164">如果本地语言不受支持，请在美国英语中查看。</span><span class="sxs-lookup"><span data-stu-id="d2fdd-164">If your local language is unsupported, view in US English.</span></span>
