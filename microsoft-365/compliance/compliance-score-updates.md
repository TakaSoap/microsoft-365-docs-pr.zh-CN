---
title: Microsoft 合规性分数更新
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
description: 有关 Microsoft 合规性分数未来更新的详细信息（预览），M365 合规性中心中的一项功能，可帮助简化和自动化风险评估。
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857753"
---
# <a name="microsoft-compliance-score-preview-updates"></a><span data-ttu-id="45b1e-103">Microsoft 合规性分数（预览）更新</span><span class="sxs-lookup"><span data-stu-id="45b1e-103">Microsoft Compliance Score (Preview) updates</span></span>

 <span data-ttu-id="45b1e-104">本文提供有关[Microsoft 合规性分数](compliance-score.md)和[Microsoft 合规性管理器](compliance-manager-overview.md)未来更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="45b1e-104">This article provides details about future updates to [Microsoft Compliance Score](compliance-score.md) and [Microsoft Compliance Manager](compliance-manager-overview.md).</span></span> <span data-ttu-id="45b1e-105">了解有关其[关系](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="45b1e-105">Learn more about their [relationship](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="improved-template-creation-and-update-processes"></a><span data-ttu-id="45b1e-106">改进的模板创建和更新过程</span><span class="sxs-lookup"><span data-stu-id="45b1e-106">Improved template creation and update processes</span></span>

<span data-ttu-id="45b1e-107">我们正在简化导入、导出和修改用于评估的模板的过程。</span><span class="sxs-lookup"><span data-stu-id="45b1e-107">We're simplifying the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="45b1e-108">全新体验使你能够更轻松地将自己的评估引入到合规性分数，并使其保持更新。</span><span class="sxs-lookup"><span data-stu-id="45b1e-108">The new experience will make it easier for you to bring your own assessments into Compliance Score and keep them updated.</span></span>

### <a name="the-current-process"></a><span data-ttu-id="45b1e-109">当前进程</span><span class="sxs-lookup"><span data-stu-id="45b1e-109">The current process</span></span>

<span data-ttu-id="45b1e-110">有两种方法可以在合规性管理器中创建模板。</span><span class="sxs-lookup"><span data-stu-id="45b1e-110">There are two ways to create a template in Compliance Manager.</span></span> <span data-ttu-id="45b1e-111">您可以复制现有模板，也可以将模板数据从 Excel 电子表格导入到新模板中。</span><span class="sxs-lookup"><span data-stu-id="45b1e-111">You can copy an existing template, or you can import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="45b1e-112">从 "**模板**" 页中，选择 " **+ 添加模板**" 以创建新的模板，方法是输入名称，选择 "维度"，然后上传具有特定格式和架构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="45b1e-112">From your **Templates** page, you select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="45b1e-113">或者，您可以选中 "**从现有模板复制**" 框，选择要复制的模板并验证尺寸，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="45b1e-113">Or you can check the **Copy from an existing template** box, select a template to copy, and verify dimensions, as shown in the image below.</span></span> <span data-ttu-id="45b1e-114">自定义模板需要一个[多步骤过程](working-with-compliance-manager.md#templates)，该过程首先选择创建模板之后的 "**添加自定义控件**"。</span><span class="sxs-lookup"><span data-stu-id="45b1e-114">Customizing your template requires a [multi-step process](working-with-compliance-manager.md#templates) that begins by selecting **Add custom control** after creating your template.</span></span>

<span data-ttu-id="45b1e-115">![合规性分数-仪表板](../media/compliance-score-template-update-old.png "当前模板复制过程")</span><span class="sxs-lookup"><span data-stu-id="45b1e-115">![Compliance Score - dashboard](../media/compliance-score-template-update-old.png "Current template copy process")</span></span>

### <a name="whats-changing"></a><span data-ttu-id="45b1e-116">更改内容</span><span class="sxs-lookup"><span data-stu-id="45b1e-116">What's changing</span></span>

<span data-ttu-id="45b1e-117">我们正在让你更轻松地创建新模板。</span><span class="sxs-lookup"><span data-stu-id="45b1e-117">We're making it easier for you to create new templates.</span></span> <span data-ttu-id="45b1e-118">在单步**扩展**过程中，可以将包含操作和控件的电子表格添加到现有的 Microsoft 模板中，以生成自己的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="45b1e-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="45b1e-119">在 "**模板**" 浮出控件窗格中，选择 "**从共用模板创建扩展**" 复选框，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="45b1e-119">On the **Template** flyout pane, select the **Create extension from global template** checkbox, as shown in the image below.</span></span> <span data-ttu-id="45b1e-120">然后，您将使用一种新的 Excel 格式来添加自定义项，该格式不是当前的复杂格式。</span><span class="sxs-lookup"><span data-stu-id="45b1e-120">You'll then add customizations using a new Excel format that is less complex than the current one.</span></span> <span data-ttu-id="45b1e-121">此新进程将替换**现有模板中**的当前副本并**添加自定义控件**函数。</span><span class="sxs-lookup"><span data-stu-id="45b1e-121">This new process replaces the current **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="45b1e-122">每次通过以下概述的版本控制过程更新最初的评估时，您的自定义评估将继承这些更新并保留您的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="45b1e-122">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="45b1e-123">此外，我们还使您可以更轻松地修改您自己的现有模板。</span><span class="sxs-lookup"><span data-stu-id="45b1e-123">We're also making it easier to modify your own existing templates.</span></span> <span data-ttu-id="45b1e-124">您可以导出模板，在同一工作簿中进行更改，然后在保存编辑内容后将其导入。</span><span class="sxs-lookup"><span data-stu-id="45b1e-124">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="45b1e-125">![合规性分数-仪表板](../media/compliance-score-template-update-new.png "新模板创建过程")</span><span class="sxs-lookup"><span data-stu-id="45b1e-125">![Compliance Score - dashboard](../media/compliance-score-template-update-new.png "New template creation process")</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="45b1e-126">版本控制通知和控制</span><span class="sxs-lookup"><span data-stu-id="45b1e-126">Versioning notice and control</span></span>

<span data-ttu-id="45b1e-127">您的组织将在下一版本的合规性分数和合规性管理器中接收更新的评估，以帮助您与认证和法规更新保持一致。</span><span class="sxs-lookup"><span data-stu-id="45b1e-127">Your organization will receive updated assessments in the next release of Compliance Score and Compliance Manager to help you align with certification and regulation updates.</span></span>

<span data-ttu-id="45b1e-128">今后，只要有更新可用于评估模板或改进操作，警报图标都会通知您更新已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="45b1e-128">Going forward, whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="45b1e-129">当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。</span><span class="sxs-lookup"><span data-stu-id="45b1e-129">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="45b1e-130">下面是针对评估的版本控制警报的一个示例：</span><span class="sxs-lookup"><span data-stu-id="45b1e-130">Below is an example of the versioning alert for an assessment:</span></span>

<span data-ttu-id="45b1e-131">![合规性分数-版本控制警报](../media/compliance-score-assessment-version.png "评估版本更新警报")</span><span class="sxs-lookup"><span data-stu-id="45b1e-131">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="45b1e-132">选择警报图标可显示一个弹出窗格，其中介绍了更新并提示您接受：</span><span class="sxs-lookup"><span data-stu-id="45b1e-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="45b1e-133">![合规性分数-版本化飞出](../media/compliance-score-assessment-version-accept.png "评估更新确认窗格")</span><span class="sxs-lookup"><span data-stu-id="45b1e-133">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="45b1e-134">常见操作将同步组之间的状态</span><span class="sxs-lookup"><span data-stu-id="45b1e-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="45b1e-135">如果您的组织具有多个评估组，**技术**操作的行为（即影响整个组织的操作）将会发生变化。</span><span class="sxs-lookup"><span data-stu-id="45b1e-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) will change.</span></span> <span data-ttu-id="45b1e-136">跨组的任何重复操作将合并为一个单个操作。</span><span class="sxs-lookup"><span data-stu-id="45b1e-136">Any duplicate actions across groups will be combined into one single action.</span></span> <span data-ttu-id="45b1e-137">该单个操作将包含重复版本中所有已上载的笔记和证据。</span><span class="sxs-lookup"><span data-stu-id="45b1e-137">That single action will contain all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="45b1e-138">进行此更改后，技术操作将表现为属于同一组时的当前操作。</span><span class="sxs-lookup"><span data-stu-id="45b1e-138">With this change, technical actions will behave as they currently do when they belong to the same group.</span></span> <span data-ttu-id="45b1e-139">现在，在一个组或评估中对操作所做的任何更改都将反映在所有实例中。</span><span class="sxs-lookup"><span data-stu-id="45b1e-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="45b1e-140"> *\*实现状态*\*、*\*实现 Dat*\*、*\*测试状态*\*和*\*测试日期** 将反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="45b1e-140">The **Implementation Status**, **Implementation Dat**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="45b1e-141">语言支持</span><span class="sxs-lookup"><span data-stu-id="45b1e-141">Language support</span></span>

<span data-ttu-id="45b1e-142">由于英语：简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语，以下语言中现在还提供了合规性分数。</span><span class="sxs-lookup"><span data-stu-id="45b1e-142">Compliance Score will now be available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>
