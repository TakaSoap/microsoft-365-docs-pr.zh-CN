---
title: 使用 Microsoft 合规性分数
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
description: 了解如何使用 Microsoft 合规性分数中的工作流工具来帮助管理组织的合规性。
ms.openlocfilehash: 046a370fe1294220ee4ee6150311df5f51905674
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601189"
---
# <a name="working-with-microsoft-compliance-score-preview"></a><span data-ttu-id="54dc1-103">使用 Microsoft 合规性分数（预览）</span><span class="sxs-lookup"><span data-stu-id="54dc1-103">Working with Microsoft Compliance Score (Preview)</span></span>

## <a name="managing-your-workflow-with-improvement-actions"></a><span data-ttu-id="54dc1-104">使用改进操作管理工作流</span><span class="sxs-lookup"><span data-stu-id="54dc1-104">Managing your workflow with improvement actions</span></span>

<span data-ttu-id="54dc1-105">使用合规性分数中的提高操作将集中管理合规性工作流。</span><span class="sxs-lookup"><span data-stu-id="54dc1-105">Using improvement actions in Compliance Score centralizes your compliance workflows.</span></span> <span data-ttu-id="54dc1-106">改进操作建议建议的操作与数据保护规章和标准一致，并提供详细的实施指南。</span><span class="sxs-lookup"><span data-stu-id="54dc1-106">Improvement actions suggest recommended actions to align with data protection regulations and standards, and provide detailed implementation guidance.</span></span> <span data-ttu-id="54dc1-107">您可以将其分配给用户，以执行必要的实现和测试工作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-107">You can assign them to users to perform the necessary implementation and testing work.</span></span> <span data-ttu-id="54dc1-108">您还可以存储文档和注释，并在改进操作本身中直接记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="54dc1-108">You can also store documentation and notes, and record status updates right in the improvement action itself.</span></span>

## <a name="view-your-improvement-actions"></a><span data-ttu-id="54dc1-109">查看改进操作</span><span class="sxs-lookup"><span data-stu-id="54dc1-109">View your improvement actions</span></span>

<span data-ttu-id="54dc1-110">合规性分数仪表板显示了你的**关键改进操作**，其中包含最重要的问题的最多可用点。</span><span class="sxs-lookup"><span data-stu-id="54dc1-110">The Compliance Score dashboard shows your **key improvement actions**—the ones with the most available points which address the most important issues.</span></span>

<span data-ttu-id="54dc1-111">若要查看所有改进操作，请选择仪表板上的 "**改进操作**" 选项卡，或在仪表板上选择 "查看关键改进操作的列表" 下的 "**所有改进操作**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-111">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard, or select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span> <span data-ttu-id="54dc1-112">这将转到 "**改进操作**" 页面，您可以在其中查看组织的所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-112">This brings you to the the **Improvement actions** page, where you can see all of your organization’s improvement actions.</span></span>

<span data-ttu-id="54dc1-113">如果您的操作列表很长，则筛选视图可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="54dc1-113">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="54dc1-114">若要执行此操作，请选择 "操作" 列表右上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-114">To do this, select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="54dc1-115">当 "**筛选器**" 浮出控件窗格出现时，根据法规和标准、解决方案和组选择所需的条件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-115">When the **Filters** flyout pane appears, then select your desired criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="54dc1-116">您还可以通过选择右上角的 "**组**" 来自定义视图，然后从下拉菜单中选择按组、解决方案、类别、操作类型或状态进行查看。</span><span class="sxs-lookup"><span data-stu-id="54dc1-116">You can also customize your view by selecting **Group** in the upper-right corner and, from the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="54dc1-117">此页面的默认视图不显示测试状态为 "已**通过**" 的提高操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-117">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="54dc1-118">若要查看已通过测试的操作，请选中 "**筛选器**浮出控件" 窗格中的 "**传递**" 框。</span><span class="sxs-lookup"><span data-stu-id="54dc1-118">To view actions that have passed testing, check the **Passed** box in the **Filters** flyout pane.</span></span> <span data-ttu-id="54dc1-119">仅具有已**通过**的测试状态与得分接近的操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-119">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="54dc1-120">"改进操作" 页显示每个改进操作的以下数据点：</span><span class="sxs-lookup"><span data-stu-id="54dc1-120">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="54dc1-121">**得分影响**：完成操作时，整体得分将增加的点数</span><span class="sxs-lookup"><span data-stu-id="54dc1-121">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="54dc1-122">**法规**：与操作相关的法规或标准</span><span class="sxs-lookup"><span data-stu-id="54dc1-122">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="54dc1-123">**组**：为其分配操作的组</span><span class="sxs-lookup"><span data-stu-id="54dc1-123">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="54dc1-124">**解决方案**：可在其中执行操作的解决方案</span><span class="sxs-lookup"><span data-stu-id="54dc1-124">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="54dc1-125">**评估**：评估（它会对控制以满足特定合规性目标进行组织），操作驻留在其中</span><span class="sxs-lookup"><span data-stu-id="54dc1-125">**Assessments**: the assessment  (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="54dc1-126">**类别**：相关的数据保护类别（即，保护信息、管理设备等）</span><span class="sxs-lookup"><span data-stu-id="54dc1-126">**Categories**: the related data protection category (i.e., protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="54dc1-127">**测试状态**：</span><span class="sxs-lookup"><span data-stu-id="54dc1-127">**Test status**:</span></span>
    - <span data-ttu-id="54dc1-128">**无**-未记录状态更新</span><span class="sxs-lookup"><span data-stu-id="54dc1-128">**None** - no status update recorded</span></span>
    - <span data-ttu-id="54dc1-129">**未评估**-测试尚未启动</span><span class="sxs-lookup"><span data-stu-id="54dc1-129">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="54dc1-130">**不在范围**内-已从合规性分数计算中排除，并且不会增加你的成绩</span><span class="sxs-lookup"><span data-stu-id="54dc1-130">**Not in scope** - is excluded from Compliance Score calculation and does not increase your score</span></span>
    - <span data-ttu-id="54dc1-131">**部分测试**-测试尚未完成</span><span class="sxs-lookup"><span data-stu-id="54dc1-131">**Partially tested** - testing is not yet complete</span></span>
    - <span data-ttu-id="54dc1-132">**失败的高风险**-实施测试失败，并且适用的标准不符合标准的风险较高</span><span class="sxs-lookup"><span data-stu-id="54dc1-132">**Failed high risk** - testing of implementation has failed, and the risk of non-compliance with the applicable standard is high</span></span>
    - <span data-ttu-id="54dc1-133">已成功测试已**通过**的实施</span><span class="sxs-lookup"><span data-stu-id="54dc1-133">**Passed** - implementation successfully tested</span></span>
- <span data-ttu-id="54dc1-134">积分：显示可获得的最大**积分。**</span><span class="sxs-lookup"><span data-stu-id="54dc1-134">**Pointed achieved**: shows points achieved out of the maximum that could be earned</span></span>

### <a name="improvement-actions-details"></a><span data-ttu-id="54dc1-135">改进操作详细信息</span><span class="sxs-lookup"><span data-stu-id="54dc1-135">Improvement actions details</span></span>

<span data-ttu-id="54dc1-136">每个改进操作都有详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="54dc1-136">Each improvement action has a details page.</span></span> <span data-ttu-id="54dc1-137">此页面包含详细的实现说明，说明了如何采取建议的操作来解决 "**概览**" 标题下列出的相关标准和法规要求。</span><span class="sxs-lookup"><span data-stu-id="54dc1-137">This page contains detailed implementation instructions, which explain how to take the recommended actions to address the related standards and regulatory requirements listed under the **At a glance** header.</span></span>

<span data-ttu-id="54dc1-138">[！注释] [！注释] [！注释] [！注释] [！注释] 可以启动推荐操作或将工作分配给其他用户、更新状态以及附加注释和文档。</span><span class="sxs-lookup"><span data-stu-id="54dc1-138">The details page is where you can launch the recommended action or assign the work to another user, update status, and attach notes and documentation.</span></span>

<span data-ttu-id="54dc1-139">若要查看改进操作的详细信息页面，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54dc1-139">To view an improvement action's details page:</span></span>

1. <span data-ttu-id="54dc1-140">转到 "改进操作" 页面。</span><span class="sxs-lookup"><span data-stu-id="54dc1-140">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="54dc1-141">单击或点击预期的 "改进" 操作的行中的任意位置，这将打开其详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="54dc1-141">Click or tap anywhere in the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="54dc1-142">通过选择屏幕右上角的向上或向下箭头，可以轻松查看列表中的下一个或上一个 "改进" 操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-142">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="54dc1-143">如果您在 "改进操作" 页面上筛选了列表，则向上或向下移动将转到该筛选列表中的下一项。</span><span class="sxs-lookup"><span data-stu-id="54dc1-143">If you filtered your list on the improvement actions page, moving up or down will take you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="54dc1-144">分配提高操作</span><span class="sxs-lookup"><span data-stu-id="54dc1-144">Assign improvement actions</span></span>

<span data-ttu-id="54dc1-145">若要开始实施改进操作，您可以自己执行工作，也可以将其分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="54dc1-145">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="54dc1-146">分配的人员可以是：</span><span class="sxs-lookup"><span data-stu-id="54dc1-146">The assigned person could be:</span></span>

- <span data-ttu-id="54dc1-147">业务策略所有者</span><span class="sxs-lookup"><span data-stu-id="54dc1-147">A business policy owner</span></span>
- <span data-ttu-id="54dc1-148">IT 实现者</span><span class="sxs-lookup"><span data-stu-id="54dc1-148">An IT implementer</span></span>
- <span data-ttu-id="54dc1-149">另一个负责执行任务的员工</span><span class="sxs-lookup"><span data-stu-id="54dc1-149">Another employee with responsibility to perform the task</span></span> 

<span data-ttu-id="54dc1-150">一旦确定了正确的人员，请确保他们在合规性分数（合规性管理员、合规性数据管理员、安全管理员或全局管理员）中保留了足够的[角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)以执行此工作，然后执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="54dc1-150">Once the proper person is identified, be sure they hold a sufficient [role](compliance-score-setup.md#set-user-permissions-and-assign-roles) in Compliance Score (compliance administrator, compliance data administrator, security administrator, or global administrator) to perform the work, then take the following steps:</span></span> 

1. <span data-ttu-id="54dc1-151">从 "改进操作详细信息" 页中，选择屏幕左上角旁边的 "**编辑状态**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-151">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span> 

2. <span data-ttu-id="54dc1-152">在 "编辑状态" 浮出控件窗格中，在 "**分配对象**" 框中单击或点击，这将填充 "**建议的人员**" 用户列表。</span><span class="sxs-lookup"><span data-stu-id="54dc1-152">In the edit status flyout pane, click or tap in the **Assigned to** box, which populates a **Suggested people** list of users.</span></span> <span data-ttu-id="54dc1-153">您可以从列表中选择用户，也可以键入要向其分配该操作的人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="54dc1-153">You can select the user from the list, or type the email address of the person to whom you want to assign the action.</span></span>

3. <span data-ttu-id="54dc1-154">选择 "**保存并关闭**" 以完成工作分配。</span><span class="sxs-lookup"><span data-stu-id="54dc1-154">Select **Save and close** to complete the assignment.</span></span> <span data-ttu-id="54dc1-155">分配的用户将收到已向其分配改进操作的电子邮件，然后他们可以从其仪表板中打开 "改进" 操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-155">The assigned user will receive an email that the improvement action has been assigned to them, and they can then open the improvement action from their dashboard.</span></span>

<span data-ttu-id="54dc1-156">然后，分配的用户可以执行实施说明中所述的建议操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-156">The assigned user can then perform the recommended actions outlined in the implementation instructions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="54dc1-157">执行工作和存储文档</span><span class="sxs-lookup"><span data-stu-id="54dc1-157">Perform work and store documentation</span></span>

<span data-ttu-id="54dc1-158">执行实施工作时，您可以将文件和注释直接上载到 "**备注和文档**" 部分中的 "改进" 操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-158">When you perform implementation work, you can upload files and notes directly to the improvement action in the **Notes and documentation** section.</span></span> <span data-ttu-id="54dc1-159">这提供了一个安全、集中的存储库，可帮助您演示控制的满意度，以满足合规性标准和法规要求。</span><span class="sxs-lookup"><span data-stu-id="54dc1-159">This provides a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="54dc1-160">任何具有只读访问权限的用户都可以读取此部分中的内容。</span><span class="sxs-lookup"><span data-stu-id="54dc1-160">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="54dc1-161">上载、下载或删除字段，或输入或编辑备注的功能仅限于具有编辑权限的角色。</span><span class="sxs-lookup"><span data-stu-id="54dc1-161">The ability to upload, download, or delete fields, or to enter or edit notes, is restricted to roles with editing rights.</span></span>

<span data-ttu-id="54dc1-162">"**备注和文档**" 部分中的字段包括：</span><span class="sxs-lookup"><span data-stu-id="54dc1-162">Fields in the **Notes and documentation** section include:</span></span>

<span data-ttu-id="54dc1-163">**上载的文档**</span><span class="sxs-lookup"><span data-stu-id="54dc1-163">**Uploaded documents**</span></span>

- <span data-ttu-id="54dc1-164">选择 "**管理文档**" 以上传任何相关文件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-164">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="54dc1-165">当 "管理文档" 浮出控件窗格打开时，选择 "**添加文档**"，然后从系统中选择文件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-165">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="54dc1-166">接受的文件类型：</span><span class="sxs-lookup"><span data-stu-id="54dc1-166">Accepted file types:</span></span> 
  - <span data-ttu-id="54dc1-167">文档（.doc、.xls、.ppt、.txt、.pdf）</span><span class="sxs-lookup"><span data-stu-id="54dc1-167">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
  - <span data-ttu-id="54dc1-168">图像（.jpg、.png）</span><span class="sxs-lookup"><span data-stu-id="54dc1-168">Images (.jpg, .png)</span></span>
  - <span data-ttu-id="54dc1-169">视频（mkv）</span><span class="sxs-lookup"><span data-stu-id="54dc1-169">Video (.mkv)</span></span>
  - <span data-ttu-id="54dc1-170">压缩文件（.zip、rar）</span><span class="sxs-lookup"><span data-stu-id="54dc1-170">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="54dc1-171">在您的文件在窗格中进行解析后，选择 "**关闭"，** 这将自动保存文件附件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-171">Once your file resolves in the pane, select **Close,** which automatically saves the file attachment.</span></span> <span data-ttu-id="54dc1-172">然后，您将看到 "已**上载文档**" 下方列出的文件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-172">You will then see the file listed underneath **Uploaded documents.**</span></span> 
- <span data-ttu-id="54dc1-173">若要下载或删除文档，请从文档列表下选择 "**管理文档**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-173">To download or delete the document, select **Manage documents** from  underneath the list of documents.</span></span> <span data-ttu-id="54dc1-174">在浮出控件窗格中，单击或点击文档行以突出显示它，然后选择 "**下载**" 或 "**删除"。**</span><span class="sxs-lookup"><span data-stu-id="54dc1-174">On the flyout pane, click or tap on the document row to highlight it, then select **Download** or **Delete.**</span></span>

<span data-ttu-id="54dc1-175">**实现、测试和其他说明**</span><span class="sxs-lookup"><span data-stu-id="54dc1-175">**Implementation, Test, and Additional notes**</span></span>

- <span data-ttu-id="54dc1-176">若要添加这三个字段中任一字段的注释，请选择 "**编辑实现说明**" 下面任何 "thse" 字段。</span><span class="sxs-lookup"><span data-stu-id="54dc1-176">To add notes in any of these three fields, select **Edit implementation notes** underneath any of thse fields.</span></span>
- <span data-ttu-id="54dc1-177">当浮出控件窗格打开时，在文本字段中输入备注，然后选择 "**保存并关闭**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-177">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="54dc1-178">若要编辑便笺，请选择 "**编辑实现说明**"，进行编辑，然后选择 "**保存并关闭**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-178">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="54dc1-179">"备注" 字段中没有字符限制。</span><span class="sxs-lookup"><span data-stu-id="54dc1-179">There is no character limit in the notes fields.</span></span> <span data-ttu-id="54dc1-180">建议保留备注摘要，以便可以从 "改进操作详细信息" 页轻松查看和编辑它们。</span><span class="sxs-lookup"><span data-stu-id="54dc1-180">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="54dc1-181">更改改进操作状态</span><span class="sxs-lookup"><span data-stu-id="54dc1-181">Change improvement action status</span></span>

<span data-ttu-id="54dc1-182">您可以为每个改进操作记录实现状态和日期以及测试状态和日期。</span><span class="sxs-lookup"><span data-stu-id="54dc1-182">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="54dc1-183">以下是可用的字段和状态选项：</span><span class="sxs-lookup"><span data-stu-id="54dc1-183">Below are the available fields and status options:</span></span>

- <span data-ttu-id="54dc1-184">**实现状态**：从以下状态选项中选择：</span><span class="sxs-lookup"><span data-stu-id="54dc1-184">**Implementation status**: select from these status options:</span></span>
    - <span data-ttu-id="54dc1-185">**未实现**-操作尚未实现</span><span class="sxs-lookup"><span data-stu-id="54dc1-185">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="54dc1-186">已**实现**-操作已实现</span><span class="sxs-lookup"><span data-stu-id="54dc1-186">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="54dc1-187">**替代实现**-如果你使用其他第三方工具或执行 Microsoft 建议中未包含的其他操作，请选择此选项</span><span class="sxs-lookup"><span data-stu-id="54dc1-187">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="54dc1-188">**计划**的操作计划实施</span><span class="sxs-lookup"><span data-stu-id="54dc1-188">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="54dc1-189">**不在范围内**-与您的组织不相关的操作的选项;选择此状态会将操作从计分中排除;取消选中它将在记分中包含操作</span><span class="sxs-lookup"><span data-stu-id="54dc1-189">**Not in scope** - an option for actions not relevant to your organization; selecting this status excludes the action from scoring; unselecting it will include the action in scoring</span></span>
- <span data-ttu-id="54dc1-190">**实现日期**：实现状态设置为 "已**实现**" 或 "**替代实现**" 时的可用字段;在 "日历" 弹出窗口中切换以选择日期</span><span class="sxs-lookup"><span data-stu-id="54dc1-190">**Implementation date**: available field when implementation status is set to **Implemented** or **Alternative implementation**; toggle through the calendar pop-up to select the date</span></span>
- <span data-ttu-id="54dc1-191">**测试状态**：从以下选项中选择：</span><span class="sxs-lookup"><span data-stu-id="54dc1-191">**Test status**: select from these options:</span></span>
    - <span data-ttu-id="54dc1-192">**未评估**-测试尚未启动</span><span class="sxs-lookup"><span data-stu-id="54dc1-192">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="54dc1-193">已成功测试已**通过**的实施</span><span class="sxs-lookup"><span data-stu-id="54dc1-193">**Passed**- implementation successfully tested</span></span>
    - <span data-ttu-id="54dc1-194">**失败的低风险**-测试失败，低风险</span><span class="sxs-lookup"><span data-stu-id="54dc1-194">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="54dc1-195">**失败中等风险**-测试失败，中等风险</span><span class="sxs-lookup"><span data-stu-id="54dc1-195">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="54dc1-196">**失败的高风险**-测试失败，高风险</span><span class="sxs-lookup"><span data-stu-id="54dc1-196">**Failed high risk** - testing failed, high risk</span></span>
- <span data-ttu-id="54dc1-197">**测试日期**：在 "日历" 弹出窗口中切换以选择日期</span><span class="sxs-lookup"><span data-stu-id="54dc1-197">**Test date**: toggle through the calendar pop-up to select the date</span></span>

> [!NOTE]
> <span data-ttu-id="54dc1-198">任何具有编辑权限的用户都可以编辑 "实施" 和 "测试状态" 字段，而不只是**分配**给用户的。</span><span class="sxs-lookup"><span data-stu-id="54dc1-198">Implementation and test status fields can be edited by any user with editing permissions, not just the **Assigned to** user.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="54dc1-199">将 "改进" 操作分配给评估员以完成</span><span class="sxs-lookup"><span data-stu-id="54dc1-199">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="54dc1-200">完成工作并上传证据后，下一步是设置实现状态和日期，并将 "改进" 操作分配给评估员进行验证。</span><span class="sxs-lookup"><span data-stu-id="54dc1-200">After you complete the work and upload evidence, the next step is to set the implementation status and date, and assign the improvement action to an assessor for validation.</span></span>

<span data-ttu-id="54dc1-201">评估员的类型包括：</span><span class="sxs-lookup"><span data-stu-id="54dc1-201">Types of assessors include:</span></span>

- <span data-ttu-id="54dc1-202">在组织中对控件进行验证的内部评估员</span><span class="sxs-lookup"><span data-stu-id="54dc1-202">Internal assessors who perform validation of controls within your organization</span></span>
- <span data-ttu-id="54dc1-203">外部评估员检查、验证和认证合规性（如审核 Microsoft 云服务的第三方独立组织）</span><span class="sxs-lookup"><span data-stu-id="54dc1-203">External assessors who examine, verify, and certify compliance—such as third-party independent organizations that audit Microsoft cloud services</span></span>

<span data-ttu-id="54dc1-204">评估员验证工作并检查文档，并选择相应的测试状态。</span><span class="sxs-lookup"><span data-stu-id="54dc1-204">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="54dc1-205">**如果测试状态为 "已传递"**：该操作已完成，并且**积分**显示了已达到的可能积分，并在总体合规性分数中计入数量。</span><span class="sxs-lookup"><span data-stu-id="54dc1-205">**If the test status is "Passed"**: the action is complete, and the **points achieved** shows the full number of possible points achieved and counted toward your overall compliance score.</span></span>

<span data-ttu-id="54dc1-206">**如果测试状态为 "失败" 的任何级别**：该操作不符合要求，并且评估员可以将其分配给适当的用户进行其他工作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-206">**If the test status is any degree of "Failed"**: the action does not meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="solutions-page"></a><span data-ttu-id="54dc1-207">解决方案页</span><span class="sxs-lookup"><span data-stu-id="54dc1-207">Solutions page</span></span>

<span data-ttu-id="54dc1-208">"**解决方案" 页面**是继续执行改进操作以增加成绩的另一个起点。</span><span class="sxs-lookup"><span data-stu-id="54dc1-208">The **Solutions page** is another starting point for working on improvement actions to increase your score.</span></span> 

<span data-ttu-id="54dc1-209">若要转到 "解决方案" 页，请选择仪表板上的 "**解决方案**" 选项卡，或选择 "查看下面的**所有解决方案**，**这些解决方案将影响您**的仪表板的右上部分中的分数。</span><span class="sxs-lookup"><span data-stu-id="54dc1-209">To get to your solutions page, select the **Solutions** tab on your dashboard, or select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

<span data-ttu-id="54dc1-210">"解决方案" 页显示按解决方案组织的挣和潜在点的份额。</span><span class="sxs-lookup"><span data-stu-id="54dc1-210">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="54dc1-211">查看此视图中的剩余点和改进操作可帮助您了解哪些解决方案需要更直接关注。</span><span class="sxs-lookup"><span data-stu-id="54dc1-211">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="54dc1-212">筛选解决方案视图</span><span class="sxs-lookup"><span data-stu-id="54dc1-212">Filtering your solutions view</span></span>

<span data-ttu-id="54dc1-213">筛选你查看的解决方案：</span><span class="sxs-lookup"><span data-stu-id="54dc1-213">To filter you view of solutions:</span></span> 

1. <span data-ttu-id="54dc1-214">选择评估列表左上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-214">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="54dc1-215">在飞出的 "**筛选器**" 窗格中，在所需条件（标准和规章、解决方案、操作类型、合规性管理器组、类别）旁边进行检查。</span><span class="sxs-lookup"><span data-stu-id="54dc1-215">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="54dc1-216">选择 "**应用**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="54dc1-216">Select the **Apply** button.</span></span> <span data-ttu-id="54dc1-217">筛选窗格将关闭，您将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="54dc1-217">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="54dc1-218">您还可以通过从评估列表上方的**组**下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="54dc1-218">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solutions-page"></a><span data-ttu-id="54dc1-219">从 "解决方案" 页采取操作</span><span class="sxs-lookup"><span data-stu-id="54dc1-219">Taking actions from the solutions page</span></span>

<span data-ttu-id="54dc1-220">"解决方案" 页显示已连接到 "改进操作" 的组织解决方案。</span><span class="sxs-lookup"><span data-stu-id="54dc1-220">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="54dc1-221">该表列出了每个解决方案对总体成绩的贡献、在该解决方案中实现的分数提升点，以及在该解决方案中分组的其余改进操作的数量，该解决方案可增加成绩。</span><span class="sxs-lookup"><span data-stu-id="54dc1-221">The table lists each solution's contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span> 

<span data-ttu-id="54dc1-222">可以通过以下两种方法从该屏幕执行操作：</span><span class="sxs-lookup"><span data-stu-id="54dc1-222">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="54dc1-223">在预期解决方案的行上，在 "**剩余操作**" 列下，单击或点击超链接的数字。</span><span class="sxs-lookup"><span data-stu-id="54dc1-223">On the row of your intended solution, under the **Remaining actions** column, click or tap on the hyperlinked number.</span></span> <span data-ttu-id="54dc1-224">这将转到 "改进操作" 屏幕的筛选视图，显示该解决方案的未经测试的改进操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-224">This takes you to a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="54dc1-225">在预期解决方案的行中的 "**打开解决方案**" 列下，选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-225">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="54dc1-226">这将转到 Microsoft 365 和 Office 365 安全性和合规性中心中的解决方案或位置，您可以采取建议的措施。</span><span class="sxs-lookup"><span data-stu-id="54dc1-226">This takes you to the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="54dc1-227">评估页</span><span class="sxs-lookup"><span data-stu-id="54dc1-227">Assessments page</span></span>

<span data-ttu-id="54dc1-228">"评估" 页面列出了您选择的针对您的组织进行跟踪的评估。</span><span class="sxs-lookup"><span data-stu-id="54dc1-228">The assessments page lists the assessments you select to track for your organization.</span></span> <span data-ttu-id="54dc1-229">您的合规性分数分母由所有跟踪的评估决定。</span><span class="sxs-lookup"><span data-stu-id="54dc1-229">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="54dc1-230">您添加的评定越多，您在改进操作页面上看到的改进操作越多，分数分母越高。</span><span class="sxs-lookup"><span data-stu-id="54dc1-230">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="54dc1-231">若要转到 "评估" 页面，请选择仪表板上的 "**评估**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="54dc1-231">To get to your assessments page, select the **Assessments** tab on your dashboard.</span></span>

<span data-ttu-id="54dc1-232">在此页面上，您可以快速查看有关每个评估的重要信息：</span><span class="sxs-lookup"><span data-stu-id="54dc1-232">On this page you can quickly view important information about each assessment:</span></span>

- <span data-ttu-id="54dc1-233">**状态**：评估中所有改进操作的完成状态将作为以下之一列出：</span><span class="sxs-lookup"><span data-stu-id="54dc1-233">**Status**: the status toward completion of all the improvement actions in the assessment will be listed as either:</span></span>
    - <span data-ttu-id="54dc1-234">**不符合**：评估中的改进操作尚未实施和测试成功;工作尚未开始</span><span class="sxs-lookup"><span data-stu-id="54dc1-234">**Non-compliant**: the improvement actions in the assessment have not been implemented and successfully tested; work has not yet begun</span></span>
    - <span data-ttu-id="54dc1-235">**正在进行**：工作在实施或测试改进操作过程中正在进行。例如，这可能意味着已为工作分配评估中的改进操作，正在实施和测试的过程中</span><span class="sxs-lookup"><span data-stu-id="54dc1-235">**In progress**: work is underway in implementing or testing the improvement actions; this could mean, for example, that an improvement action in the assessment has been assigned for work, is in the process of being implemented and tested</span></span>
- <span data-ttu-id="54dc1-236">**评估进度**：评估最终完成工作所占的百分比，由成功测试的控件数衡量。</span><span class="sxs-lookup"><span data-stu-id="54dc1-236">**Assessment progress**: the percentage of the work done towards final completion of the assessment, as measured by the number of controls successfully tested.</span></span>
- <span data-ttu-id="54dc1-237">**客户管理的操作**：为满足客户托管的控制措施而完成的操作的数量</span><span class="sxs-lookup"><span data-stu-id="54dc1-237">**Customer-managed actions**: the number of completed actions to satisfy implementation of  your customer-managed controls</span></span>
- <span data-ttu-id="54dc1-238">**Microsoft 管理的操作**：满足 microsoft 托管控件的实现的已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="54dc1-238">**Microsoft-managed actions**: the number of completed actions to satisfy implementation of Microsoft-managed controls</span></span>
- <span data-ttu-id="54dc1-239">**评估组**：你创建的组的名称，评估驻留在此</span><span class="sxs-lookup"><span data-stu-id="54dc1-239">**Assessment group**: name of the group you created, in which the assessment resides</span></span>
- <span data-ttu-id="54dc1-240">**相关服务**：关联的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="54dc1-240">**Related services**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="54dc1-241">**相关管理法规**：评估要满足的法规标准、策略或法律</span><span class="sxs-lookup"><span data-stu-id="54dc1-241">**Related regulations**: the regulatory standard, policy, or law which the assessment seeks to satisfy</span></span>

### <a name="default-assessments"></a><span data-ttu-id="54dc1-242">默认评估</span><span class="sxs-lookup"><span data-stu-id="54dc1-242">Default assessments</span></span>

<span data-ttu-id="54dc1-243">默认情况下，您将在 "评估" 页上看到 "Microsoft 365 数据保护基准评估"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-243">By default, you will see the Microsoft 365 data protection baseline assessment on the assessments page.</span></span> <span data-ttu-id="54dc1-244">合规性分数还提供了几个开箱即用评估（[查看完整列表](compliance-score.md#templates)）。</span><span class="sxs-lookup"><span data-stu-id="54dc1-244">Compliance Score also provides several out-of-box assessments ([view the full list](compliance-score.md#templates)).</span></span> <span data-ttu-id="54dc1-245">如果要添加更多评估以涵盖其他法规和标准，可以在合规性管理器中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-245">If you want to add more assessments to cover additional regulations and standards, you can do this in Compliance Manager.</span></span>

### <a name="managing-assessments"></a><span data-ttu-id="54dc1-246">管理评估</span><span class="sxs-lookup"><span data-stu-id="54dc1-246">Managing assessments</span></span>

<span data-ttu-id="54dc1-247">在公共预览过程中，用于查看、创建、导出和存档评估的功能将保留在合规性管理器工具中。</span><span class="sxs-lookup"><span data-stu-id="54dc1-247">During public preview, functionality for viewing, creating, exporting, and archiving assessments remains in the Compliance Manager tool.</span></span> 

<span data-ttu-id="54dc1-248">若要管理评估，请选择 "评估" 列表顶部的 **"管理合规性管理器" 中的 "管理评估**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-248">To manage your assessments, select **Manage Assessments in Compliance Manager** at the top of the assessments list.</span></span>

<span data-ttu-id="54dc1-249">"评估" 列表顶部的另一个链接（**合规性管理器中的 "microsoft 操作**"）将转到合规性管理器中的页面，其中显示了有助于满足合规性分数的 Microsoft 控件。</span><span class="sxs-lookup"><span data-stu-id="54dc1-249">The other link at the top of the assessments list, **Microsoft actions in Compliance Manager**, takes you to the page in Compliance Manager showing Microsoft controls that contribute to your compliance score.</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="54dc1-250">筛选评估视图</span><span class="sxs-lookup"><span data-stu-id="54dc1-250">Filtering your assessments view</span></span>

<span data-ttu-id="54dc1-251">筛选评估的视图：</span><span class="sxs-lookup"><span data-stu-id="54dc1-251">To filter you view of assessments:</span></span>

1. <span data-ttu-id="54dc1-252">选择评估列表左上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-252">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="54dc1-253">在飞出的 "**筛选器**" 窗格中，在所需条件（标准和规章，合规性管理器组）旁边进行检查。</span><span class="sxs-lookup"><span data-stu-id="54dc1-253">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, Compliance Manager group).</span></span>
3. <span data-ttu-id="54dc1-254">选择 "**应用**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="54dc1-254">Select the **Apply** button.</span></span> <span data-ttu-id="54dc1-255">筛选窗格将关闭，您将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="54dc1-255">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="54dc1-256">您还可以通过从评估列表上方的**组**下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="54dc1-256">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="managing-improvement-actions-within-an-assessment"></a><span data-ttu-id="54dc1-257">管理评估中的改进措施</span><span class="sxs-lookup"><span data-stu-id="54dc1-257">Managing improvement actions within an assessment</span></span>

<span data-ttu-id="54dc1-258">从 "**客户管理的操作**" 列下的 "评估" 列表中，选择预期评估的行上的链接文本。</span><span class="sxs-lookup"><span data-stu-id="54dc1-258">From the assessment list, under the **Customer-managed actions** column, select the linked text on the row of the intended assessment.</span></span> <span data-ttu-id="54dc1-259">这将为您显示 "改进操作" 页面的筛选视图，其中显示了该评估中的操作。</span><span class="sxs-lookup"><span data-stu-id="54dc1-259">This takes you a filtered view of the improvement actions page showing the actions within that assessment.</span></span>

## <a name="reporting"></a><span data-ttu-id="54dc1-260">Reporting</span><span class="sxs-lookup"><span data-stu-id="54dc1-260">Reporting</span></span>

<span data-ttu-id="54dc1-261">您可以在合规性分数中导出所有改进操作的报告。</span><span class="sxs-lookup"><span data-stu-id="54dc1-261">You can export a report of all your improvement actions in Compliance Score.</span></span> <span data-ttu-id="54dc1-262">从 "**改进操作**" 页中，选择屏幕左上角的 "**导出**"，在操作列表之上。</span><span class="sxs-lookup"><span data-stu-id="54dc1-262">From the **Improvement actions** page, select **Export** in the upper-left corner of your screen, above your list of actions.</span></span> <span data-ttu-id="54dc1-263">这将生成一个包含所有改进操作的 Excel 工作表和 "**改进操作**" 页面上显示的筛选器类别，可以在其中查看并保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="54dc1-263">This will produce an Excel worksheet with all your improvement actions and the filter categories shown on the **Improvement actions** page, which you can view and save to your local machine.</span></span>

<span data-ttu-id="54dc1-264">您还可以从合规性管理器导出报告。</span><span class="sxs-lookup"><span data-stu-id="54dc1-264">You can also export a report from Compliance Manager.</span></span> <span data-ttu-id="54dc1-265">在合规性管理器中，转到 "**控件信息**" 选项卡，然后选择屏幕右上部分的 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="54dc1-265">In Compliance Manager, go to the **Controls Info** tab and select **Export** in the upper-right section of the screen.</span></span> <span data-ttu-id="54dc1-266">这将生成可查看和保存的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="54dc1-266">This produces an Excel worksheet you can view and save.</span></span>
