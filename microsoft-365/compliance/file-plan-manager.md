---
title: 使用文件计划在整个内容生命周期中管理保留标签
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
description: 文件计划为保留标签提供了高级管理功能。
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 422a76db5705e80c67803b798275e1faedd1d7aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906869"
---
# <a name="use-file-plan-to-manage-retention-labels"></a><span data-ttu-id="9de9e-103">使用文件计划管理保留标签</span><span class="sxs-lookup"><span data-stu-id="9de9e-103">Use file plan to manage retention labels</span></span>

><span data-ttu-id="9de9e-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="9de9e-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="9de9e-105">尽管可以从 Microsoft 365 合规性中心的“**信息管理**”创建和管理保留标签，但是“**记录管理**”中的文件计划具有其他管理功能：</span><span class="sxs-lookup"><span data-stu-id="9de9e-105">Although you can create and manage retention labels from **Information governance** in the Microsoft 365 compliance center, file plan from **Records management** has additional management capabilities:</span></span>

- <span data-ttu-id="9de9e-106">可以通过从电子表格中导入相关信息来批量创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="9de9e-106">You can bulk-create retention labels by importing the relevant information from a spreadsheet.</span></span>

- <span data-ttu-id="9de9e-107">可从现有保留标签中导出信息，以便进行分析和脱机协作，或者用于批量编辑。</span><span class="sxs-lookup"><span data-stu-id="9de9e-107">You can export the information from existing retention labels for analysis and offline collaboration, or for bulk-editing.</span></span>

- <span data-ttu-id="9de9e-108">显示有关保留标签的更多信息，以使可以更轻松地从一个视图查看和查看所有保留标签的设置。</span><span class="sxs-lookup"><span data-stu-id="9de9e-108">More information about the retention labels is displayed to make it easier to see into and across the settings of all your retention labels from one view.</span></span>

- <span data-ttu-id="9de9e-109">文件计划描述符支持每个标签的附加和可选信息。</span><span class="sxs-lookup"><span data-stu-id="9de9e-109">File plan descriptors support additional and optional information for each label.</span></span>

<span data-ttu-id="9de9e-110">文件计划可用于所有保留标签，即使未将内容标记为记录也是如此。</span><span class="sxs-lookup"><span data-stu-id="9de9e-110">File plan can be used for all retention labels, even if they don't mark content as a record.</span></span>

![文件计划页面](../media/compliance-file-plan.png)

<span data-ttu-id="9de9e-112">若要了解什么是保留标签以及如何使用它们，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="9de9e-112">For information about what retention labels are and how to use them, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="accessing-file-plan"></a><span data-ttu-id="9de9e-113">访问文件计划</span><span class="sxs-lookup"><span data-stu-id="9de9e-113">Accessing file plan</span></span>

<span data-ttu-id="9de9e-114">要访问文件计划，您必须具有以下管理员角色之一：</span><span class="sxs-lookup"><span data-stu-id="9de9e-114">To access file plan, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="9de9e-115">保留管理者</span><span class="sxs-lookup"><span data-stu-id="9de9e-115">Retention Manager</span></span>

- <span data-ttu-id="9de9e-116">仅拥有查看权限的保留管理者</span><span class="sxs-lookup"><span data-stu-id="9de9e-116">View-only Retention Manager</span></span>

<span data-ttu-id="9de9e-117">在 Microsoft 365 合规性中心中，转到“**解决方案**” > “**记录管理**” > “**文件计划**”。</span><span class="sxs-lookup"><span data-stu-id="9de9e-117">In the Microsoft 365 compliance center, go to **Solutions** > **Records management** > **File plan**.</span></span> 

<span data-ttu-id="9de9e-118">如果“**记录管理**”未显示在导航窗格中，请首先向下滚动并选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="9de9e-118">If **Records management** doesn't display in the navigation pane, first scroll down, and select **Show all**.</span></span>

![文件计划页面](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a><span data-ttu-id="9de9e-120">浏览文件计划</span><span class="sxs-lookup"><span data-stu-id="9de9e-120">Navigating your file plan</span></span>

<span data-ttu-id="9de9e-121">如果已经从 Microsoft 365 合规性中心中的“**信息治理**”创建了保留标签，则这些标签会自动显示在文件计划中。</span><span class="sxs-lookup"><span data-stu-id="9de9e-121">If you've already created retention labels from **Information governance** in the Microsoft 365 compliance center, these labels automatically display in your file plan.</span></span> 

<span data-ttu-id="9de9e-122">同样，如果现在在文件计划中创建保留标签，则如果未将标签配置为将内容标记为记录，则也可以从 **信息治理** 中使用。</span><span class="sxs-lookup"><span data-stu-id="9de9e-122">Similarly, if you now create retention labels in file plan, they are also available from **Information governance** if the labels aren't configured to mark content as a record.</span></span>

<span data-ttu-id="9de9e-123">在“**文件计划**”页面上，将看到所有标签及其状态和设置、可选的文件计划描述符、用于分析或启用标签脱机审阅的导出选项，以及用于创建保留标签的导入选项。</span><span class="sxs-lookup"><span data-stu-id="9de9e-123">On the **File plan** page, you see all your labels with their status and settings, optional file plan descriptors, an export option to analyze or enable offline reviews of your labels, and an import option to create retention labels.</span></span> 

### <a name="label-settings-columns"></a><span data-ttu-id="9de9e-124">“标签设置”列</span><span class="sxs-lookup"><span data-stu-id="9de9e-124">Label settings columns</span></span>

<span data-ttu-id="9de9e-125">通过选择“**自定义列**”选项，可以显示或隐藏除标签“**名称**”之外的所有列。</span><span class="sxs-lookup"><span data-stu-id="9de9e-125">All columns except the label **Name** can be displayed or hidden by selecting the **Customize columns** option.</span></span> <span data-ttu-id="9de9e-126">但是默认情况下，前几列显示有关标签状态及其设置的信息：</span><span class="sxs-lookup"><span data-stu-id="9de9e-126">But by default, the first few columns display information about the label status and its settings:</span></span> 

- <span data-ttu-id="9de9e-127">**状态** 标识标签是包含在标签策略中还是自动应用策略中（**活动**）或不（**非活动**）。</span><span class="sxs-lookup"><span data-stu-id="9de9e-127">**Status** identifies whether the label is included in a label policy or auto-apply policy (**Active**) or not (**Inactive**).</span></span>

- <span data-ttu-id="9de9e-128">**基于** 标识保留期的方式或时间。</span><span class="sxs-lookup"><span data-stu-id="9de9e-128">**Based on** identifies how or when the retention period begins.</span></span> <span data-ttu-id="9de9e-129">有效值：</span><span class="sxs-lookup"><span data-stu-id="9de9e-129">Valid values:</span></span>
    - <span data-ttu-id="9de9e-130">事件</span><span class="sxs-lookup"><span data-stu-id="9de9e-130">Event</span></span>
    - <span data-ttu-id="9de9e-131">创建时间</span><span class="sxs-lookup"><span data-stu-id="9de9e-131">When created</span></span>
    - <span data-ttu-id="9de9e-132">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="9de9e-132">Last modified</span></span>
    - <span data-ttu-id="9de9e-133">标记时间</span><span class="sxs-lookup"><span data-stu-id="9de9e-133">When labeled</span></span>

- <span data-ttu-id="9de9e-134">**是记录** 标识在应用标签时是否将该项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="9de9e-134">**Is record** identifies if the item is marked as a record when the label is applied.</span></span> <span data-ttu-id="9de9e-135">有效值：</span><span class="sxs-lookup"><span data-stu-id="9de9e-135">Valid values:</span></span>
    - <span data-ttu-id="9de9e-136">否</span><span class="sxs-lookup"><span data-stu-id="9de9e-136">No</span></span>
    - <span data-ttu-id="9de9e-137">是</span><span class="sxs-lookup"><span data-stu-id="9de9e-137">Yes</span></span>
    - <span data-ttu-id="9de9e-138">是(法规)</span><span class="sxs-lookup"><span data-stu-id="9de9e-138">Yes(Regulatory)</span></span>

- <span data-ttu-id="9de9e-139">**保留期限** 标识保留期限。</span><span class="sxs-lookup"><span data-stu-id="9de9e-139">**Retention duration** identifies the retention period.</span></span> <span data-ttu-id="9de9e-140">有效值：</span><span class="sxs-lookup"><span data-stu-id="9de9e-140">Valid values:</span></span>
    - <span data-ttu-id="9de9e-141">天</span><span class="sxs-lookup"><span data-stu-id="9de9e-141">Days</span></span>
    - <span data-ttu-id="9de9e-142">月</span><span class="sxs-lookup"><span data-stu-id="9de9e-142">Months</span></span>
    - <span data-ttu-id="9de9e-143">年限</span><span class="sxs-lookup"><span data-stu-id="9de9e-143">Years</span></span>
    - <span data-ttu-id="9de9e-144">永久</span><span class="sxs-lookup"><span data-stu-id="9de9e-144">Forever</span></span>
    - <span data-ttu-id="9de9e-145">无</span><span class="sxs-lookup"><span data-stu-id="9de9e-145">None</span></span>

- <span data-ttu-id="9de9e-146">“**处置类型**”列指明在保留期到期时如何处置内容。</span><span class="sxs-lookup"><span data-stu-id="9de9e-146">**Disposition type** identifies what happens to the content at the end of the retention period.</span></span> <span data-ttu-id="9de9e-147">有效值：</span><span class="sxs-lookup"><span data-stu-id="9de9e-147">Valid values:</span></span>
    - <span data-ttu-id="9de9e-148">无操作</span><span class="sxs-lookup"><span data-stu-id="9de9e-148">No action</span></span>
    - <span data-ttu-id="9de9e-149">自动删除</span><span class="sxs-lookup"><span data-stu-id="9de9e-149">Auto-delete</span></span>
    - <span data-ttu-id="9de9e-150">需评审</span><span class="sxs-lookup"><span data-stu-id="9de9e-150">Review required</span></span>

### <a name="file-plan-descriptors-columns"></a><span data-ttu-id="9de9e-151">文件计划描述符列</span><span class="sxs-lookup"><span data-stu-id="9de9e-151">File plan descriptors columns</span></span>

<span data-ttu-id="9de9e-152">文件计划可将详细信息包含在保留标签中。</span><span class="sxs-lookup"><span data-stu-id="9de9e-152">File plan lets you include more information as part of your retention labels.</span></span> <span data-ttu-id="9de9e-153">这些文件计划描述符提供了更多选项，可用于改进要标记的内容的易管理性和组织性。</span><span class="sxs-lookup"><span data-stu-id="9de9e-153">These file plan descriptors provide more options to improve the manageability and organization of the content you need to label.</span></span>

<span data-ttu-id="9de9e-154">默认情况下，从“**引用 ID**”开始，接下来的几列将显示这些文件计划描述符，可在创建保留标签时指定，或编辑现有标签。</span><span class="sxs-lookup"><span data-stu-id="9de9e-154">By default, starting with **Reference ID**, the next few columns display these file plan descriptors that you can specify when you create a retention label, or edit an existing label.</span></span> 

<span data-ttu-id="9de9e-155">为了帮助你开始使用，以下文件计划描述符有一些现成的值：</span><span class="sxs-lookup"><span data-stu-id="9de9e-155">To get you started, there are some out-of-box values for the following file plan descriptors:</span></span> 
- <span data-ttu-id="9de9e-156">企业机能/部门</span><span class="sxs-lookup"><span data-stu-id="9de9e-156">Business function/department</span></span>
- <span data-ttu-id="9de9e-157">类别</span><span class="sxs-lookup"><span data-stu-id="9de9e-157">Category</span></span>
- <span data-ttu-id="9de9e-158">颁发机构类型</span><span class="sxs-lookup"><span data-stu-id="9de9e-158">Authority type</span></span>
- <span data-ttu-id="9de9e-159">预配/引文</span><span class="sxs-lookup"><span data-stu-id="9de9e-159">Provision/citation</span></span> 

<span data-ttu-id="9de9e-160">创建或编辑保留标签时的文件计划描述符示例：</span><span class="sxs-lookup"><span data-stu-id="9de9e-160">Example of file plan descriptors when you create or edit a retention label:</span></span>

![创建或编辑保留标签时的文件计划描述符](../media/file-plan-descriptors.png)

<span data-ttu-id="9de9e-162">文件计划描述符列示例视图：</span><span class="sxs-lookup"><span data-stu-id="9de9e-162">Example view of the file plan descriptors columns:</span></span>

![文件计划描述符列](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a><span data-ttu-id="9de9e-164">导出所有保留标签以分析或启用脱机评审</span><span class="sxs-lookup"><span data-stu-id="9de9e-164">Export all retention labels to analyze or enable offline reviews</span></span>

<span data-ttu-id="9de9e-165">在文件计划中，可以将所有保留标签的详细信息都导出到 .csv 文件中，有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。</span><span class="sxs-lookup"><span data-stu-id="9de9e-165">From your file plan, you can export the details of all retention labels into a .csv file to help you facilitate periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="9de9e-166">要导出所有保留标签：在“**文件计划**”页上，单击“**导出**”：</span><span class="sxs-lookup"><span data-stu-id="9de9e-166">To export all retention labels: On the **File plan** page, click **Export**:</span></span>

![文件计划导出选项](../media/compliance-file-plan-export-labels.png)

<span data-ttu-id="9de9e-168">将打开包含所有现有保留标签的 \*.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9de9e-168">A \*.csv file that contains all existing retention labels opens.</span></span> <span data-ttu-id="9de9e-169">例如：</span><span class="sxs-lookup"><span data-stu-id="9de9e-169">For example:</span></span>

![包含所有保留标签的 CSV 文件](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="9de9e-171">向文件计划导入保留标签</span><span class="sxs-lookup"><span data-stu-id="9de9e-171">Import retention labels into your file plan</span></span>

<span data-ttu-id="9de9e-172">在文件计划中可以批量导入新保留标签，并使用相同的方法来批量修改现有的保留标签。</span><span class="sxs-lookup"><span data-stu-id="9de9e-172">In file plan, you can bulk-import new retention labels, and use the same method to bulk-modify existing retention labels.</span></span>

<span data-ttu-id="9de9e-173">若要导入新的保留标签和修改现有保留标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9de9e-173">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="9de9e-174">在“**文件计划**”页面上，单击“**导入**”，以使用“**填写并导入文件计划**” 页面：</span><span class="sxs-lookup"><span data-stu-id="9de9e-174">On the **File plan** page, click **Import** to use the **Fill out and import your file plan** page:</span></span>

   ![文件计划导入选项](../media/compliance-file-plan-import-labels.png)

   ![空白文件计划模板下载选项](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="9de9e-177">下载空白模板以导入新的保留标签。</span><span class="sxs-lookup"><span data-stu-id="9de9e-177">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="9de9e-178">或者，你也可以从导出组织中的现有保留标签时导出的 .csv 文件开始。</span><span class="sxs-lookup"><span data-stu-id="9de9e-178">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![在 Excel 中打开空白文件计划模板](../media/file-plan-blank-template.png)

3. <span data-ttu-id="9de9e-180">使用以下描述属性的信息以及每个属性的有效值填写模板。</span><span class="sxs-lookup"><span data-stu-id="9de9e-180">Fill out the template, using the following information that describes the properties and valid values for each property.</span></span> <span data-ttu-id="9de9e-181">对于导入，某些值具有最大长度：</span><span class="sxs-lookup"><span data-stu-id="9de9e-181">For import, some values have a maximum length:</span></span>
    
    - <span data-ttu-id="9de9e-182">**LabelName**：最大长度为 64 个字符</span><span class="sxs-lookup"><span data-stu-id="9de9e-182">**LabelName**: Maximum length of 64 characters</span></span>
    - <span data-ttu-id="9de9e-183">**Comment** 和 **Notes**：最大程度为 1024 个字符</span><span class="sxs-lookup"><span data-stu-id="9de9e-183">**Comment** and **Notes**: Maximum length of 1024 characters</span></span>
    - <span data-ttu-id="9de9e-184">所有其他值：长度不受限制</span><span class="sxs-lookup"><span data-stu-id="9de9e-184">All other values: Unlimited length</span></span>
    <br/>
    
   |<span data-ttu-id="9de9e-185">属性</span><span class="sxs-lookup"><span data-stu-id="9de9e-185">Property</span></span>|<span data-ttu-id="9de9e-186">类型</span><span class="sxs-lookup"><span data-stu-id="9de9e-186">Type</span></span>|<span data-ttu-id="9de9e-187">有效值</span><span class="sxs-lookup"><span data-stu-id="9de9e-187">Valid values</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="9de9e-188">LabelName</span><span class="sxs-lookup"><span data-stu-id="9de9e-188">LabelName</span></span>|<span data-ttu-id="9de9e-189">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-189">String</span></span>|<span data-ttu-id="9de9e-190">此属性指定保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="9de9e-190">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="9de9e-191">评论</span><span class="sxs-lookup"><span data-stu-id="9de9e-191">Comment</span></span>|<span data-ttu-id="9de9e-192">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-192">String</span></span>|<span data-ttu-id="9de9e-193">使用此属性可以添加有关管理员的保留标签的说明。</span><span class="sxs-lookup"><span data-stu-id="9de9e-193">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="9de9e-194">此说明仅对在合规中心管理保留标签的管理员显示。</span><span class="sxs-lookup"><span data-stu-id="9de9e-194">This description appears only to admins who manage the retention label in the compliance center.</span></span>|
   |<span data-ttu-id="9de9e-195">注释</span><span class="sxs-lookup"><span data-stu-id="9de9e-195">Notes</span></span>|<span data-ttu-id="9de9e-196">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-196">String</span></span>|<span data-ttu-id="9de9e-197">使用此属性可以添加有关用户的保留标签的说明。</span><span class="sxs-lookup"><span data-stu-id="9de9e-197">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="9de9e-198">当用户将鼠标悬停在 Outlook、SharePoint 和 OneDrive 等应用的标签上时，将显示此说明。</span><span class="sxs-lookup"><span data-stu-id="9de9e-198">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="9de9e-199">如果将此属性保留为空白，则会显示默认说明，用于说明标签的保留设置。</span><span class="sxs-lookup"><span data-stu-id="9de9e-199">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="9de9e-200">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="9de9e-200">IsRecordLabel</span></span>|<span data-ttu-id="9de9e-201">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-201">String</span></span>|<span data-ttu-id="9de9e-202">此属性指定标签是否将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="9de9e-202">This property specifies whether the label marks the content as a record.</span></span> <span data-ttu-id="9de9e-203">有效值为：</span><span class="sxs-lookup"><span data-stu-id="9de9e-203">Valid values are:</span></span> </br><span data-ttu-id="9de9e-204">**TRUE**: 标签将该项目标记为记录和结果，因此此项目无法删除。</span><span class="sxs-lookup"><span data-stu-id="9de9e-204">**TRUE**: The label marks the item as a record and as a result, the item can't be deleted.</span></span> </br><span data-ttu-id="9de9e-205">**FALSE**: 标签不会将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="9de9e-205">**FALSE**: The label doesn't mark the content as a record.</span></span> <span data-ttu-id="9de9e-206">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-206">This is the default value.</span></span>|
   |<span data-ttu-id="9de9e-207">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="9de9e-207">RetentionAction</span></span>|<span data-ttu-id="9de9e-208">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-208">String</span></span>|<span data-ttu-id="9de9e-209">此属性指定在 RetentionDuration 属性指定的值到期后要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="9de9e-209">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="9de9e-210">有效值为：</span><span class="sxs-lookup"><span data-stu-id="9de9e-210">Valid values are:</span></span> </br><span data-ttu-id="9de9e-211">**Delete**：早于 RetentionDuration 属性指定的值的项目将被删除。</span><span class="sxs-lookup"><span data-stu-id="9de9e-211">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="9de9e-212">**Keep**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="9de9e-212">**Keep**: Retain items for the duration specified by the RetentionDuration property and then do nothing when the duration period expires.</span></span> </br><span data-ttu-id="9de9e-213">**KeepAndDelete**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="9de9e-213">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="9de9e-214">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="9de9e-214">RetentionDuration</span></span>|<span data-ttu-id="9de9e-215">String</span><span class="sxs-lookup"><span data-stu-id="9de9e-215">String</span></span>|<span data-ttu-id="9de9e-216">此属性指定内容保留的天数。</span><span class="sxs-lookup"><span data-stu-id="9de9e-216">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="9de9e-217">有效值为：</span><span class="sxs-lookup"><span data-stu-id="9de9e-217">Valid values are:</span></span> </br><span data-ttu-id="9de9e-218">**Unlimited**：项目将无限期保留。</span><span class="sxs-lookup"><span data-stu-id="9de9e-218">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="9de9e-219">\**_n_*_：正整数，例如 _\* 365\*\*。</span><span class="sxs-lookup"><span data-stu-id="9de9e-219">\**_n_*_: A positive integer; for example, _\* 365\*\*.</span></span> 
   |<span data-ttu-id="9de9e-220">RetentionType</span><span class="sxs-lookup"><span data-stu-id="9de9e-220">RetentionType</span></span>|<span data-ttu-id="9de9e-221">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-221">String</span></span>|<span data-ttu-id="9de9e-222">此属性指定保留期限是从内容创建日期、事件日期、标记的日期还是从上次修改日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="9de9e-222">This property specifies whether the retention duration is calculated from the content creation date, event date, when labeled date, or last modified date.</span></span> <span data-ttu-id="9de9e-223">有效值为：</span><span class="sxs-lookup"><span data-stu-id="9de9e-223">Valid values are:</span></span> </br><span data-ttu-id="9de9e-224">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9de9e-224">**CreationAgeInDays**</span></span></br><span data-ttu-id="9de9e-225">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9de9e-225">**EventAgeInDays**</span></span></br><span data-ttu-id="9de9e-226">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9de9e-226">**TaggedAgeInDays**</span></span></br><span data-ttu-id="9de9e-227">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9de9e-227">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="9de9e-228">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="9de9e-228">ReviewerEmail</span></span>|<span data-ttu-id="9de9e-229">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="9de9e-229">SmtpAddress</span></span>|<span data-ttu-id="9de9e-230">填充此属性后，在保留期到期时将触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="9de9e-230">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="9de9e-231">此属性指定 **KeepAndDelete** 保留操作的审阅者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9de9e-231">This property specifies the email address of a reviewer for the **KeepAndDelete** retention action.</span></span> <span data-ttu-id="9de9e-232">你可以包含单个用户、分发组或安全组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9de9e-232">You can include the email address of individual users, distribution groups, or security groups.</span></span> <span data-ttu-id="9de9e-233">可以指定多个电子邮件地址，中间用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="9de9e-233">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="9de9e-234">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="9de9e-234">ReferenceId</span></span>|<span data-ttu-id="9de9e-235">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-235">String</span></span>|<span data-ttu-id="9de9e-236">该属性指定在 **参考 ID** 文件计划描述符中显示的值，可将其用作组织的唯一值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-236">This property specifies the value that's displayed in the **Reference Id** file plan descriptor, which you can use as a unique value to your organization.</span></span>| 
   |<span data-ttu-id="9de9e-237">Departmentname</span><span class="sxs-lookup"><span data-stu-id="9de9e-237">DepartmentName</span></span>|<span data-ttu-id="9de9e-238">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-238">String</span></span>|<span data-ttu-id="9de9e-239">该属性指定在 **功能/部门** 文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-239">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="9de9e-240">类别</span><span class="sxs-lookup"><span data-stu-id="9de9e-240">Category</span></span>|<span data-ttu-id="9de9e-241">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-241">String</span></span>|<span data-ttu-id="9de9e-242">该属性指定在 **类别** 文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-242">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="9de9e-243">SubCategory</span><span class="sxs-lookup"><span data-stu-id="9de9e-243">SubCategory</span></span>|<span data-ttu-id="9de9e-244">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-244">String</span></span>|<span data-ttu-id="9de9e-245">该属性指定在 **子类别** 文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-245">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="9de9e-246">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="9de9e-246">AuthorityType</span></span>|<span data-ttu-id="9de9e-247">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-247">String</span></span>|<span data-ttu-id="9de9e-248">该属性指定在 **权限类型** 文件计划描述符中显示的值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-248">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="9de9e-249">CitationName</span><span class="sxs-lookup"><span data-stu-id="9de9e-249">CitationName</span></span>|<span data-ttu-id="9de9e-250">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-250">String</span></span>|<span data-ttu-id="9de9e-251">该属性指定在 **预配/引文** 文件计划描述符中显示的引文名称。</span><span class="sxs-lookup"><span data-stu-id="9de9e-251">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="9de9e-252">例如，“2002 年萨班斯-奥克斯利法案”。</span><span class="sxs-lookup"><span data-stu-id="9de9e-252">For example, "Sarbanes-Oxley Act of 2002".</span></span> |
   |<span data-ttu-id="9de9e-253">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="9de9e-253">CitationUrl</span></span>|<span data-ttu-id="9de9e-254">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-254">String</span></span>|<span data-ttu-id="9de9e-255">该属性指定在 **预配/引文** 文件计划描述符中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="9de9e-255">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="9de9e-256">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="9de9e-256">CitationJurisdiction</span></span>|<span data-ttu-id="9de9e-257">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-257">String</span></span>|<span data-ttu-id="9de9e-258">该属性指定在 **预配/引文** 文件计划描述符中显示的司法管辖区或机构。</span><span class="sxs-lookup"><span data-stu-id="9de9e-258">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="9de9e-259">例如，“美国证券交易委员会 (SEC)”。</span><span class="sxs-lookup"><span data-stu-id="9de9e-259">For example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="9de9e-260">Regulatory</span><span class="sxs-lookup"><span data-stu-id="9de9e-260">Regulatory</span></span>|<span data-ttu-id="9de9e-261">字符串</span><span class="sxs-lookup"><span data-stu-id="9de9e-261">String</span></span>|<span data-ttu-id="9de9e-262">保留为空白。</span><span class="sxs-lookup"><span data-stu-id="9de9e-262">Leave blank.</span></span> <span data-ttu-id="9de9e-263">此属性目前不可用。</span><span class="sxs-lookup"><span data-stu-id="9de9e-263">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="9de9e-264">EventType</span><span class="sxs-lookup"><span data-stu-id="9de9e-264">EventType</span></span>|<span data-ttu-id="9de9e-265">String</span><span class="sxs-lookup"><span data-stu-id="9de9e-265">String</span></span>|<span data-ttu-id="9de9e-266">此属性指定与标签关联的保留规则。</span><span class="sxs-lookup"><span data-stu-id="9de9e-266">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="9de9e-267">可以使用唯一标识该规则的任何值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-267">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="9de9e-268">例如：</span><span class="sxs-lookup"><span data-stu-id="9de9e-268">For example:</span></span></br><span data-ttu-id="9de9e-269">**名称**</span><span class="sxs-lookup"><span data-stu-id="9de9e-269">**Name**</span></span></br><span data-ttu-id="9de9e-270">**可分辨名称 (DN)**</span><span class="sxs-lookup"><span data-stu-id="9de9e-270">**Distinguished name (DN)**</span></span></br><span data-ttu-id="9de9e-271">**GUID**</span><span class="sxs-lookup"><span data-stu-id="9de9e-271">**GUID**</span></span> </br><span data-ttu-id="9de9e-272">可使用 [Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancerule) cmdlet 来查看可用的保留规则。</span><span class="sxs-lookup"><span data-stu-id="9de9e-272">You can use the [Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancerule) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="9de9e-273">请注意，因为 EventType 值是组织唯一的，如果从某个组织导出标签，则将该标签导入其他组织时，不能使用该组织中的 EventType 属性值。</span><span class="sxs-lookup"><span data-stu-id="9de9e-273">Note that because the EventType values are unique to an organization, if you export labels from one organization, you can't use the values for the EventType property from that organization to import labels into a different organization.</span></span>|
   |||

   <span data-ttu-id="9de9e-274">下面是包含有关保留标签的信息的模板示例。</span><span class="sxs-lookup"><span data-stu-id="9de9e-274">Here's an example of the template containing the information about retention labels.</span></span>

   ![填写了信息的文件计划模板](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="9de9e-276">在 **填写并导入文件计划** 页上的第 3 步，单击“**浏览文件**”以上传填好的模板。</span><span class="sxs-lookup"><span data-stu-id="9de9e-276">Under step 3 on the **Fill out and import your file plan** page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="9de9e-277">文件计划验证条目并显示导入统计信息。</span><span class="sxs-lookup"><span data-stu-id="9de9e-277">File plan validates the entries and displays the import statistics.</span></span>

   ![文件计划导入统计信息](../media/file-plan-import-statistics.png)

   <span data-ttu-id="9de9e-279">如果存在验证错误，文件计划导入将继续验证导入文件中的每一项，并在导入文件中显示引用行和行号的所有错误。</span><span class="sxs-lookup"><span data-stu-id="9de9e-279">If there's a validation error, file plan import continues to validate every entry in the import file and displays all errors  referencing the line and row numbers in the import file.</span></span> <span data-ttu-id="9de9e-280">复制显示的错误结果，以在返回导入文件时可以对其进行更正。</span><span class="sxs-lookup"><span data-stu-id="9de9e-280">Copy the displayed error results so you can correct them when you return to the import file.</span></span>

<span data-ttu-id="9de9e-281">导入完成后，现在可以将保留标签添加到新的保留标签策略中，或自动应用它们。</span><span class="sxs-lookup"><span data-stu-id="9de9e-281">When the import is complete, you can now add the retention labels to a new retention label policy, or auto-apply them.</span></span> <span data-ttu-id="9de9e-282">可以在“**文件计划**”页上执行以下操作，方法是选择 **+创建标签**，然后选择“**发布标签策略**”或“**自动应用标签**”。</span><span class="sxs-lookup"><span data-stu-id="9de9e-282">You can do this right from the **File plan** page by selecting the dropdown from **+ Create a label** and then **Policy to publish labels**, or **Policy to auto-apply a label**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9de9e-283">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9de9e-283">Next steps</span></span>

<span data-ttu-id="9de9e-284">若要详细了解如何创建和编辑保留标签及其策略，请参阅以下指南：</span><span class="sxs-lookup"><span data-stu-id="9de9e-284">For more information about creating and editing retention labels and their policies, see the following guidance:</span></span>
- [<span data-ttu-id="9de9e-285">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="9de9e-285">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="9de9e-286">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="9de9e-286">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)