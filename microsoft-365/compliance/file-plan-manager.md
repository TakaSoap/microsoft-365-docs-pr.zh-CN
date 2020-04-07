---
title: 文件计划管理器概述
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 文件计划管理器提供了对保留标签和保留标签策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。
ms.openlocfilehash: c4b1ddfaf3191a282a67917c2b2d257712a10802
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151457"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="768f9-103">文件计划管理器概述</span><span class="sxs-lookup"><span data-stu-id="768f9-103">Overview of file plan manager</span></span>

><span data-ttu-id="768f9-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="768f9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="768f9-105">文件计划管理器提供了对保留标签和保留标签策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。</span><span class="sxs-lookup"><span data-stu-id="768f9-105">File plan manager provides advanced management capabilities for retention labels, retention label policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span> 

<span data-ttu-id="768f9-106">若要访问安全与合规中心中的文件计划管理器，请转到“**记录管理**” > “**文件计划**”。</span><span class="sxs-lookup"><span data-stu-id="768f9-106">To access file plan manager in the security and compliance center, go to **Records management** > **File plan**.</span></span>

![文件计划页面](../media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="768f9-108">访问文件计划管理器</span><span class="sxs-lookup"><span data-stu-id="768f9-108">Accessing file plan manager</span></span>

<span data-ttu-id="768f9-109">要访问文件计划管理器，您必须具有以下管理员角色之一：</span><span class="sxs-lookup"><span data-stu-id="768f9-109">To access file plan manager, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="768f9-110">保留管理者</span><span class="sxs-lookup"><span data-stu-id="768f9-110">Retention Manager</span></span>

- <span data-ttu-id="768f9-111">仅拥有查看权限的保留管理者</span><span class="sxs-lookup"><span data-stu-id="768f9-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="768f9-112">默认保留标签和标签策略</span><span class="sxs-lookup"><span data-stu-id="768f9-112">Default retention labels and label policy</span></span>

<span data-ttu-id="768f9-113">如果“安全与合规中心”没有保留标签，则第一次在左侧导航栏中选择**文件计划**时，将创建名为**默认数据治理发布策略**的标签策略。</span><span class="sxs-lookup"><span data-stu-id="768f9-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="768f9-114">此标签策略包含三个保留标签：</span><span class="sxs-lookup"><span data-stu-id="768f9-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="768f9-115">**操作过程**</span><span class="sxs-lookup"><span data-stu-id="768f9-115">**Operational procedure**</span></span>
- <span data-ttu-id="768f9-116">**业务常规**</span><span class="sxs-lookup"><span data-stu-id="768f9-116">**Business general**</span></span>
- <span data-ttu-id="768f9-117">**合同协议**</span><span class="sxs-lookup"><span data-stu-id="768f9-117">**Contract agreement**</span></span>

<span data-ttu-id="768f9-118">这些保留标签仅为保留内容，而非为删除内容而配置。</span><span class="sxs-lookup"><span data-stu-id="768f9-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="768f9-119">此标签策略将发布到整个公司，可以禁用或删除。</span><span class="sxs-lookup"><span data-stu-id="768f9-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="768f9-120">可以通过查看保留策略的**创建的保留策略**和**创建的保留配置**活动的审核日志来判断谁打开了文件计划管理器并启动了首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="768f9-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="768f9-121">因客户反馈，我们已删除创建上述默认保留标签和保留标签策略的功能。</span><span class="sxs-lookup"><span data-stu-id="768f9-121">Due to customer feedback, we have removed this feature that creates the default retention labels and retention label policy mentioned above.</span></span> <span data-ttu-id="768f9-122">如果你在 2019 年 4 月 11 日之前打开文件计划管理器，则将只能看到这些保留标签和保留标签策略。</span><span class="sxs-lookup"><span data-stu-id="768f9-122">You will only see these retention labels and retention label policy if you opened file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="768f9-123">浏览文件计划</span><span class="sxs-lookup"><span data-stu-id="768f9-123">Navigating your file plan</span></span>

<span data-ttu-id="768f9-124">使用文件计划管理器，可以更轻松地在一个视图中查看所有保留标签和保留策略的设置。</span><span class="sxs-lookup"><span data-stu-id="768f9-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="768f9-125">请注意，文件计划中包含在文件计划内外创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="768f9-126">文件计划“**标签**”选项卡提供了以下附加信息和功能：</span><span class="sxs-lookup"><span data-stu-id="768f9-126">On the file plan **Labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="768f9-127">“标签设置”列</span><span class="sxs-lookup"><span data-stu-id="768f9-127">Label settings columns</span></span>

- <span data-ttu-id="768f9-p103">“依据”\*\*\*\* 列指明将启动保留期的触发器类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="768f9-130">事件</span><span class="sxs-lookup"><span data-stu-id="768f9-130">Event</span></span>
    - <span data-ttu-id="768f9-131">创建时间</span><span class="sxs-lookup"><span data-stu-id="768f9-131">When created</span></span>
    - <span data-ttu-id="768f9-132">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="768f9-132">When last modified</span></span>
    - <span data-ttu-id="768f9-133">标记时间</span><span class="sxs-lookup"><span data-stu-id="768f9-133">When labeled</span></span>
- <span data-ttu-id="768f9-p104">“记录”\*\*\*\* 列指明项是否在标签应用时成为已声明记录。有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="768f9-136">否</span><span class="sxs-lookup"><span data-stu-id="768f9-136">No</span></span>
    - <span data-ttu-id="768f9-137">是</span><span class="sxs-lookup"><span data-stu-id="768f9-137">Yes</span></span>
    - <span data-ttu-id="768f9-138">是(法规)</span><span class="sxs-lookup"><span data-stu-id="768f9-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="768f9-p105">“保留”\*\*\*\* 列指明保留类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="768f9-141">保留</span><span class="sxs-lookup"><span data-stu-id="768f9-141">Keep</span></span>
    - <span data-ttu-id="768f9-142">保留和删除</span><span class="sxs-lookup"><span data-stu-id="768f9-142">Keep and delete</span></span>
    - <span data-ttu-id="768f9-143">删除</span><span class="sxs-lookup"><span data-stu-id="768f9-143">Delete</span></span>
- <span data-ttu-id="768f9-p106">“处置”\*\*\*\* 列指明在保留期到期时如何处置内容。有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="768f9-146">Null</span><span class="sxs-lookup"><span data-stu-id="768f9-146">null</span></span>
    - <span data-ttu-id="768f9-147">无操作</span><span class="sxs-lookup"><span data-stu-id="768f9-147">No action</span></span>
    - <span data-ttu-id="768f9-148">自动删除</span><span class="sxs-lookup"><span data-stu-id="768f9-148">Auto-delete</span></span>
    - <span data-ttu-id="768f9-149">需要评审(亦称为“处置评审”)</span><span class="sxs-lookup"><span data-stu-id="768f9-149">Review required (aka Disposition review)</span></span>

![文件计划中的“标签设置”](../media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="768f9-151">保留标签文件计划描述符列</span><span class="sxs-lookup"><span data-stu-id="768f9-151">Retention label file plan descriptors columns</span></span>

<span data-ttu-id="768f9-152">现在可以在保留标签的配置中添加更多信息。</span><span class="sxs-lookup"><span data-stu-id="768f9-152">You can now include more information in the configuration of your retention labels.</span></span> <span data-ttu-id="768f9-153">将文件计划描述符插入保留标签，可提升文件计划的可管理性和条理性。</span><span class="sxs-lookup"><span data-stu-id="768f9-153">Inserting file plan descriptors into retention  labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="768f9-154">为了便于用户上手，文件计划管理器提供了一些现成值：“功能/部门”、“类别”、“权限类型”和“预配/引文”。</span><span class="sxs-lookup"><span data-stu-id="768f9-154">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation.</span></span> <span data-ttu-id="768f9-155">可以在创建或编辑保留标签时，添加新的文件计划描述符值。</span><span class="sxs-lookup"><span data-stu-id="768f9-155">You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="768f9-156">你也可以在将保留标签导入文件计划时指定文件计划描述符。</span><span class="sxs-lookup"><span data-stu-id="768f9-156">You can also specify file plan descriptors when importing retention labels into your file plan.</span></span> 

<span data-ttu-id="768f9-157">下图展示了创建或编辑保留标签时有关文件计划描述符的步骤。</span><span class="sxs-lookup"><span data-stu-id="768f9-157">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![文件计划描述符](../media/file-plan-descriptors.png)

<span data-ttu-id="768f9-159">下图展示了文件计划管理器的“**标签**”选项卡上的文件计划描述符列。</span><span class="sxs-lookup"><span data-stu-id="768f9-159">Here's a view of the file plan descriptors columns on the **Labels** tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="768f9-161">导出所有现有保留标签以分析和/或执行离线评审</span><span class="sxs-lookup"><span data-stu-id="768f9-161">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="768f9-162">在文件计划管理器中，可以将所有保留标签的详细信息都导出到 .csv 文件中，这样做有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。</span><span class="sxs-lookup"><span data-stu-id="768f9-162">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="768f9-163">若要导出所有保留标签，请在“**文件计划**”页面上，依次选择“**文件计划操作**”\>“**导出标签**”。</span><span class="sxs-lookup"><span data-stu-id="768f9-163">To export all retention labels: On the **File plan** page, **File plan actions** \> **Export labels**.</span></span>

![文件计划导出选项](../media/file-plan-export-labels-option.png)

<span data-ttu-id="768f9-165">此时，包含所有现有保留标签的 \*.csv 文件打开。</span><span class="sxs-lookup"><span data-stu-id="768f9-165">A \*.csv file containing all existing retention labels will open.</span></span>

![包含所有保留标签的 CSV 文件](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="768f9-167">向文件计划导入保留标签</span><span class="sxs-lookup"><span data-stu-id="768f9-167">Import retention labels into your file plan</span></span>

<span data-ttu-id="768f9-168">在文件计划管理器中，可以批量导入新保留标签，并能修改现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-168">In the File plan manager, you can bulk import new retention labels and modify existing retention labels.</span></span>

<span data-ttu-id="768f9-169">若要导入新的保留标签和修改现有保留标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="768f9-169">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="768f9-170">在“**文件计划**”页面上，转到“**文件计划操作**” > “**导入标签**”。</span><span class="sxs-lookup"><span data-stu-id="768f9-170">On the **File plan** page, go to **File plan actions** > **Import labels**.</span></span>

   ![文件计划导入选项](../media/file-plan-import-labels-option.png)

   ![空白文件计划模板下载选项](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="768f9-173">下载空白模板以导入新的保留标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-173">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="768f9-174">或者，你也可以从导出组织中的现有保留标签时导出的 .csv 文件开始。</span><span class="sxs-lookup"><span data-stu-id="768f9-174">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![在 Excel 中打开的空白文件计划模板](../media/file-plan-blank-template.png)

3. <span data-ttu-id="768f9-176">填写模板。</span><span class="sxs-lookup"><span data-stu-id="768f9-176">Fill-out the template.</span></span> <span data-ttu-id="768f9-177">下文介绍了文件计划模板中每个属性的属性和有效值。</span><span class="sxs-lookup"><span data-stu-id="768f9-177">The following describes the properties and valid values for each property in the file plan template.</span></span><br/>

   |<span data-ttu-id="768f9-178">**Property**</span><span class="sxs-lookup"><span data-stu-id="768f9-178">**Property**</span></span>|<span data-ttu-id="768f9-179">**类型**</span><span class="sxs-lookup"><span data-stu-id="768f9-179">**Type**</span></span>|<span data-ttu-id="768f9-180">**有效值**</span><span class="sxs-lookup"><span data-stu-id="768f9-180">**Valid values**</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="768f9-181">LabelName</span><span class="sxs-lookup"><span data-stu-id="768f9-181">LabelName</span></span>|<span data-ttu-id="768f9-182">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-182">String</span></span>|<span data-ttu-id="768f9-183">此属性指定保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="768f9-183">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="768f9-184">评论</span><span class="sxs-lookup"><span data-stu-id="768f9-184">Comment</span></span>|<span data-ttu-id="768f9-185">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-185">String</span></span>|<span data-ttu-id="768f9-186">使用此属性可以添加有关管理员的保留标签的说明。</span><span class="sxs-lookup"><span data-stu-id="768f9-186">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="768f9-187">此说明仅对在安全与合规中心管理标签的管理员显示。</span><span class="sxs-lookup"><span data-stu-id="768f9-187">This description appears only to admins who manage the label in the security and compliance center.</span></span>|
   |<span data-ttu-id="768f9-188">备注</span><span class="sxs-lookup"><span data-stu-id="768f9-188">Notes</span></span>|<span data-ttu-id="768f9-189">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-189">String</span></span>|<span data-ttu-id="768f9-190">使用此属性可以添加有关用户的保留标签的说明。</span><span class="sxs-lookup"><span data-stu-id="768f9-190">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="768f9-191">当用户将鼠标悬停在 Outlook、SharePoint 和 OneDrive 等应用的标签上时，将显示此说明。</span><span class="sxs-lookup"><span data-stu-id="768f9-191">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="768f9-192">如果将此属性保留为空白，则会显示默认说明，用于说明标签的保留设置。</span><span class="sxs-lookup"><span data-stu-id="768f9-192">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="768f9-193">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="768f9-193">IsRecordLabel</span></span>|<span data-ttu-id="768f9-194">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-194">String</span></span>|<span data-ttu-id="768f9-195">此属性指定标签是否为记录标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-195">This property specifies whether the label is a record label.</span></span> <span data-ttu-id="768f9-196">带有记录标签的项目声明为记录。</span><span class="sxs-lookup"><span data-stu-id="768f9-196">Items tagged with a record label are declared as records.</span></span> <span data-ttu-id="768f9-197">有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-197">Valid values are:</span></span></br><span data-ttu-id="768f9-198">**TRUE**：标签是记录标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-198">**TRUE**: The label is a record label.</span></span> <span data-ttu-id="768f9-199">请注意，无法删除声明为记录的项目。</span><span class="sxs-lookup"><span data-stu-id="768f9-199">Note that items that are declared as a record can't be deleted.</span></span> </br><span data-ttu-id="768f9-200">**FALSE**：标签不是记录标签。</span><span class="sxs-lookup"><span data-stu-id="768f9-200">**FALSE**: The label isn't a record label.</span></span> <span data-ttu-id="768f9-201">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="768f9-201">This is the default value.</span></span>|
   |<span data-ttu-id="768f9-202">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="768f9-202">RetentionAction</span></span>|<span data-ttu-id="768f9-203">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-203">String</span></span>|<span data-ttu-id="768f9-204">此属性指定在 RetentionDuration 属性指定的值到期后要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="768f9-204">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="768f9-205">有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-205">Valid values are:</span></span></br><span data-ttu-id="768f9-206">**Delete**：早于 RetentionDuration 属性指定的值的项目将被删除。</span><span class="sxs-lookup"><span data-stu-id="768f9-206">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="768f9-207">**Keep**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="768f9-207">**Keep**: Retain items for the duration specified by the RetentionDuration property and then doing nothing when the duration period expires.</span></span> </br><span data-ttu-id="768f9-208">**KeepAndDelete**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="768f9-208">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="768f9-209">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="768f9-209">RetentionDuration</span></span>|<span data-ttu-id="768f9-210">String</span><span class="sxs-lookup"><span data-stu-id="768f9-210">String</span></span>|<span data-ttu-id="768f9-211">此属性指定内容保留的天数。</span><span class="sxs-lookup"><span data-stu-id="768f9-211">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="768f9-212">有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-212">Valid values are:</span></span></br><span data-ttu-id="768f9-213">**Unlimited**：项目将无限期保留。</span><span class="sxs-lookup"><span data-stu-id="768f9-213">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="768f9-214">***n***：正整数，例如 **365**。</span><span class="sxs-lookup"><span data-stu-id="768f9-214">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="768f9-215">RetentionType</span><span class="sxs-lookup"><span data-stu-id="768f9-215">RetentionType</span></span>|<span data-ttu-id="768f9-216">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-216">String</span></span>|<span data-ttu-id="768f9-217">此属性指定保留期限是从内容创建日期、事件日期、标记的日期还是从上次修改日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="768f9-217">This property specifies whether the retention duration is calculated from the content creation date, event date, labeled (tagged) date, or last modified date.</span></span> <span data-ttu-id="768f9-218">有效值为：</span><span class="sxs-lookup"><span data-stu-id="768f9-218">Valid values are:</span></span></br><span data-ttu-id="768f9-219">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="768f9-219">**CreationAgeInDays**</span></span></br><span data-ttu-id="768f9-220">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="768f9-220">**EventAgeInDays**</span></span></br><span data-ttu-id="768f9-221">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="768f9-221">**TaggedAgeInDays**</span></span></br><span data-ttu-id="768f9-222">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="768f9-222">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="768f9-223">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="768f9-223">ReviewerEmail</span></span>|<span data-ttu-id="768f9-224">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="768f9-224">SmtpAddress</span></span>|<span data-ttu-id="768f9-225">填充此属性后，在保留期到期时将触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="768f9-225">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="768f9-226">此属性指定 **Delete** 和 **KeepAndDelete** 保留操作的审阅者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="768f9-226">This property specifies the email address of a reviewer for **Delete** and **KeepAndDelete** retention actions.</span></span> <span data-ttu-id="768f9-227">你可以包含单个用户、分发或安全组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="768f9-227">You can include the email address of individual users, distribution, or security groups.</span></span> <span data-ttu-id="768f9-228">可以指定多个电子邮件地址，中间用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="768f9-228">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="768f9-229">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="768f9-229">ReferenceId</span></span>|<span data-ttu-id="768f9-230">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-230">String</span></span>|<span data-ttu-id="768f9-231">该属性指定在 **参考 ID** 文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="768f9-231">This property specifies the value that's displayed in the **Reference Id** file plan descriptor.</span></span>| 
   |<span data-ttu-id="768f9-232">Departmentname</span><span class="sxs-lookup"><span data-stu-id="768f9-232">DepartmentName</span></span>|<span data-ttu-id="768f9-233">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-233">String</span></span>|<span data-ttu-id="768f9-234">该属性指定在**功能/部门**文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="768f9-234">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="768f9-235">类别</span><span class="sxs-lookup"><span data-stu-id="768f9-235">Category</span></span>|<span data-ttu-id="768f9-236">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-236">String</span></span>|<span data-ttu-id="768f9-237">该属性指定在**类别**文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="768f9-237">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="768f9-238">SubCategory</span><span class="sxs-lookup"><span data-stu-id="768f9-238">SubCategory</span></span>|<span data-ttu-id="768f9-239">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-239">String</span></span>|<span data-ttu-id="768f9-240">该属性指定在**子类别**文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="768f9-240">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="768f9-241">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="768f9-241">AuthorityType</span></span>|<span data-ttu-id="768f9-242">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-242">String</span></span>|<span data-ttu-id="768f9-243">该属性指定在**权限类型**文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="768f9-243">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="768f9-244">CitationName</span><span class="sxs-lookup"><span data-stu-id="768f9-244">CitationName</span></span>|<span data-ttu-id="768f9-245">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-245">String</span></span>|<span data-ttu-id="768f9-246">该属性指定在**预配/引文**文件计划描述符中显示的引文名称；例如“2002 年萨班斯-奥克斯利法案”。</span><span class="sxs-lookup"><span data-stu-id="768f9-246">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor; for example "Sarbanes-Oxley Act or 2002".</span></span> |
   |<span data-ttu-id="768f9-247">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="768f9-247">CitationUrl</span></span>|<span data-ttu-id="768f9-248">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-248">String</span></span>|<span data-ttu-id="768f9-249">该属性指定在**预配/引文**文件计划描述符中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="768f9-249">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="768f9-250">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="768f9-250">CitationJurisdiction</span></span>|<span data-ttu-id="768f9-251">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-251">String</span></span>|<span data-ttu-id="768f9-252">该属性指定在**预配/引文**文件计划描述符中显示的管辖权地或机构；例如“美国证券交易委员会 (SEC)”。</span><span class="sxs-lookup"><span data-stu-id="768f9-252">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor; for example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="768f9-253">Regulatory</span><span class="sxs-lookup"><span data-stu-id="768f9-253">Regulatory</span></span>|<span data-ttu-id="768f9-254">字符串</span><span class="sxs-lookup"><span data-stu-id="768f9-254">String</span></span>|<span data-ttu-id="768f9-255">保留为空白。</span><span class="sxs-lookup"><span data-stu-id="768f9-255">Leave blank.</span></span> <span data-ttu-id="768f9-256">此属性目前不可用。</span><span class="sxs-lookup"><span data-stu-id="768f9-256">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="768f9-257">EventType</span><span class="sxs-lookup"><span data-stu-id="768f9-257">EventType</span></span>|<span data-ttu-id="768f9-258">String</span><span class="sxs-lookup"><span data-stu-id="768f9-258">String</span></span>|<span data-ttu-id="768f9-259">此属性指定与标签关联的保留规则。</span><span class="sxs-lookup"><span data-stu-id="768f9-259">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="768f9-260">可以使用唯一标识该规则的任何值。</span><span class="sxs-lookup"><span data-stu-id="768f9-260">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="768f9-261">例如：</span><span class="sxs-lookup"><span data-stu-id="768f9-261">For example:</span></span></br><span data-ttu-id="768f9-262">**名称**</span><span class="sxs-lookup"><span data-stu-id="768f9-262">**Name**</span></span></br><span data-ttu-id="768f9-263">**可分辨名称 (DN)**</span><span class="sxs-lookup"><span data-stu-id="768f9-263">**Distinguished name (DN)**</span></span></br><span data-ttu-id="768f9-264">**GUID**</span><span class="sxs-lookup"><span data-stu-id="768f9-264">**GUID**</span></span> </br><span data-ttu-id="768f9-265">可使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet 来查看可用的保留规则。</span><span class="sxs-lookup"><span data-stu-id="768f9-265">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="768f9-266">请注意，如果从某个 Office 365 组织导出标签，则将该标签导入其他 Office 365 组织时，不能使用该组织中的 EventType 属性值。</span><span class="sxs-lookup"><span data-stu-id="768f9-266">Note that if you export labels from one Office 365 organization, you can't use the values for the EventType  property from that organization when importing labels to a different Office 365 organization.</span></span> <span data-ttu-id="768f9-267">这是因为 EventType 值对于组织是唯一的。</span><span class="sxs-lookup"><span data-stu-id="768f9-267">That because the EventType values are unique to an organization.</span></span> |
   |||

   <span data-ttu-id="768f9-268">下面是包含有关保留标签的信息的模板示例。</span><span class="sxs-lookup"><span data-stu-id="768f9-268">Here's an example the template containing the information about retention labels.</span></span>

   ![填写了信息的文件计划模板](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="768f9-270">在“导入文件计划向导”页面的“步骤 3”下，单击“**浏览文件**”以上传已填写的模板。</span><span class="sxs-lookup"><span data-stu-id="768f9-270">Under step 3 on the import file plan wizard page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="768f9-271">文件计划管理器会验证条目，并显示导入统计信息。</span><span class="sxs-lookup"><span data-stu-id="768f9-271">File plan manager will validate the entries and display the import statistics.</span></span>

   ![文件计划导入统计信息](../media/file-plan-import-statistics.png)

   <span data-ttu-id="768f9-273">如果出现验证错误，文件计划导入将继续验证导入文件中的每个条目，并显示导入文件中引用行/行编号的所有错误，复制显示的错误结果，以便能够轻松返回导入文件并更正错误。</span><span class="sxs-lookup"><span data-stu-id="768f9-273">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easily return to the import file and correct the errors.</span></span>

5. <span data-ttu-id="768f9-274">导入完成后，返回到文件计划管理器，以将新保留标签与新的或现有的保留标签策略相关联。</span><span class="sxs-lookup"><span data-stu-id="768f9-274">When the import is complete, return to file plan manager to associate the new retention labels to new or existing retention label policies.</span></span>

   ![“发布标签”选项](../media/file-plan-publish-labels-option.png)
