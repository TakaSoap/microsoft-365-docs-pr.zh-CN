---
title: 使用 Microsoft 合规性管理器（预览）
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
- seo-marvel-apr2020
description: 了解如何使用合规性管理器跟踪、分配和验证与 Microsoft 产品相关的法规遵从性活动。
ms.openlocfilehash: fe7b04fe7687bc91e6f96fb2c3994a6536cec314
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817079"
---
# <a name="working-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="a9748-103">使用 Microsoft 合规性管理器（预览）</span><span class="sxs-lookup"><span data-stu-id="a9748-103">Working with Microsoft Compliance Manager (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9748-104">Microsoft 合规性管理器是一个仪表板和管理工具，提供了有关数据保护和合规性的摘要 stature 以及改进数据保护和合规性的建议。</span><span class="sxs-lookup"><span data-stu-id="a9748-104">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="a9748-105">合规性管理器中提供的客户操作是建议。</span><span class="sxs-lookup"><span data-stu-id="a9748-105">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="a9748-106">在实现之前，你的组织可以评估这些建议在其各自的法规环境中的有效性。</span><span class="sxs-lookup"><span data-stu-id="a9748-106">It is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="a9748-107">合规性管理器中提供的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="a9748-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="a9748-108">Access 合规性管理器</span><span class="sxs-lookup"><span data-stu-id="a9748-108">Access Compliance Manager</span></span>

<span data-ttu-id="a9748-109">可从 Microsoft 服务信任门户访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="a9748-109">Compliance Manager is accessible from the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="a9748-110">拥有 Microsoft 帐户或 Azure Active Directory 组织帐户的任何人都可以访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="a9748-110">Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>

1. <span data-ttu-id="a9748-111">转到 [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3)。</span><span class="sxs-lookup"><span data-stu-id="a9748-111">Go to [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3).</span></span>

2. <span data-ttu-id="a9748-112">使用 Microsoft 服务帐户（即 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）用户帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="a9748-112">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

> [!NOTE]
> <span data-ttu-id="a9748-113">在服务信任门户中，选择 "**合规性管理器**"，它是具有最新功能的预览版本。</span><span class="sxs-lookup"><span data-stu-id="a9748-113">In the Service Trust Portal, select **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="a9748-114">请勿选择**合规性管理器（经典）**，其中包含本文档未涵盖的早期版本功能。</span><span class="sxs-lookup"><span data-stu-id="a9748-114">Do not select **Compliance Manager (Classic)**, which contains early-release features not covered by this documentation.</span></span>

## <a name="administration"></a><span data-ttu-id="a9748-115">管理</span><span class="sxs-lookup"><span data-stu-id="a9748-115">Administration</span></span>

<span data-ttu-id="a9748-116">只有全局管理员可以使用特定的管理功能，并且只有在使用全局管理员帐户登录时才可见。</span><span class="sxs-lookup"><span data-stu-id="a9748-116">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="a9748-117">全局管理员可以分配用户权限并打开自动安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-117">The global administrator can assign user permissions and turn on automatic Secure Score updates.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="a9748-118">向用户分配合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="a9748-118">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="a9748-119">一旦管理员将合规性管理器角色分配给其他用户，这些用户就可以在合规性管理器中查看数据，并执行角色所确定的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-119">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="a9748-120">管理员还可以通过向用户分配[Azure Active Directory （AZURE AD）中的全局读取器角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)，授予对合规性管理器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="a9748-120">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="a9748-121">每个合规性管理器角色都具有略有不同的权限。</span><span class="sxs-lookup"><span data-stu-id="a9748-121">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="a9748-122">您可以查看分配给每个角色的权限，查看哪些用户是哪些角色，以及通过服务信任门户在该角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-122">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="a9748-123">选择 "**管理**" 菜单项，然后选择 "要查看的**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-123">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理菜单：选择的设置](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="a9748-125">若要在合规性管理器角色中添加或删除用户，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-125">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="a9748-126">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a9748-126">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="a9748-127">使用 Azure Active Directory 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a9748-127">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="a9748-128">在 "服务信任门户" 顶部菜单栏上，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-128">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="a9748-129">在 "**选择角色**" 下拉列表中，选择要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="a9748-129">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="a9748-130">“**选择角色**”页上会列出已添加到每个角色的用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-130">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="a9748-131">若要将用户添加到此角色，请选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-131">To add users to this role, select **Add**.</span></span> <span data-ttu-id="a9748-132">在 "**添加用户**" 对话框中，选择 "用户" 字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-132">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="a9748-133">您可以在可用用户列表中滚动，也可以开始键入用户名，以根据您的搜索词筛选列表。</span><span class="sxs-lookup"><span data-stu-id="a9748-133">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="a9748-134">选择要将该帐户添加到使用该角色预配的 "**添加用户**" 列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-134">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="a9748-135">如果要同时添加多个用户，请开始键入用户名以筛选列表，然后选择要添加到列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-135">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="a9748-136">选择 "**保存**" 将所选角色设置给这些用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-136">Select **Save** to provision the selected role to these users.</span></span> 

    ![合规性管理器-添加用户](../media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="a9748-138">若要从此角色中删除用户，请选择 "用户"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-138">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合规性管理器-删除用户](../media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="a9748-140">控制自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="a9748-140">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="a9748-141">可以为所有操作自动启用安全分数更新，对所有操作关闭这些更新，或通过执行以下步骤设置单个操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-141">Secure Score updates can be turned on automatically for all actions, turned off for all actions, or set by individual action by following these steps.</span></span>

1. <span data-ttu-id="a9748-142">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a9748-142">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="a9748-143">在服务信任门户顶部菜单栏上的 "**更多**" 下，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-143">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="a9748-144">在 "**安全分数**" 选项卡中，选择相应的按钮以**打开所有操作**、为**所有操作**禁用或设置 "**每个操作"。**</span><span class="sxs-lookup"><span data-stu-id="a9748-144">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="a9748-145">如果选择 **"每个操作设置"，请**执行以下额外步骤，为单个操作打开安全得分更新：</span><span class="sxs-lookup"><span data-stu-id="a9748-145">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="a9748-146">从顶部菜单中选择 "**合规性管理器**" （注意：不要选择 "合规性管理器（经典）"）。</span><span class="sxs-lookup"><span data-stu-id="a9748-146">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="a9748-147">选择屏幕右上角的 "**租户管理**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-147">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="a9748-148">在 "**客户操作**" 窗格上，使用 "**受影响的操作**" 列下的省略号（**...**）查找预期操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-148">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="a9748-149">单击省略号，然后选择 "**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="a9748-149">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="a9748-150">将 "**安全分数连续更新**" 切换开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="a9748-150">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="a9748-151">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="a9748-151">Select **Save.**</span></span> <span data-ttu-id="a9748-152">现已为该操作启用安全分数连续监控。</span><span class="sxs-lookup"><span data-stu-id="a9748-152">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="a9748-153">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-153">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="a9748-154">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-154">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="a9748-155">组</span><span class="sxs-lookup"><span data-stu-id="a9748-155">Groups</span></span>

<span data-ttu-id="a9748-156">组是允许您组织评估的容器，并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。</span><span class="sxs-lookup"><span data-stu-id="a9748-156">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="a9748-157">您可以按符合您的方式对评估进行分组，如按年、标准、服务或组织的团队、部门或地理位置。</span><span class="sxs-lookup"><span data-stu-id="a9748-157">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="a9748-158">以下是两个组及其基础评估的示例：</span><span class="sxs-lookup"><span data-stu-id="a9748-158">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="a9748-159">**FFIEC 是评估2020**</span><span class="sxs-lookup"><span data-stu-id="a9748-159">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="a9748-160">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="a9748-160">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="a9748-161">Intune + FFIEC 为</span><span class="sxs-lookup"><span data-stu-id="a9748-161">Intune + FFIEC IS</span></span>
- <span data-ttu-id="a9748-162">**“数据安全和隐私”评估**</span><span class="sxs-lookup"><span data-stu-id="a9748-162">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="a9748-163">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="a9748-163">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="a9748-164">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="a9748-164">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="a9748-165">我们建议您在添加新评估*之前*为您的组织确定一个分组策略。</span><span class="sxs-lookup"><span data-stu-id="a9748-165">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span>

<span data-ttu-id="a9748-166">若要开始，请为您设置一个包含数据保护基准的**默认**组。</span><span class="sxs-lookup"><span data-stu-id="a9748-166">To get you started, a **Default** group is set up for you that contains the Data Protection Baseline.</span></span> <span data-ttu-id="a9748-167">此基准是一组包含常见行业法规和标准（[了解详细信息](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-167">This baseline is a set of controls that includes common industry regulations and standards ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="a9748-168">如何创建组</span><span class="sxs-lookup"><span data-stu-id="a9748-168">How to create a group</span></span>

<span data-ttu-id="a9748-169">不能将组创建为独立实体。</span><span class="sxs-lookup"><span data-stu-id="a9748-169">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="a9748-170">一个组必须始终包含至少一个评估，因此，若要创建一个组，必须首先创建一个评估以放置在该组中。</span><span class="sxs-lookup"><span data-stu-id="a9748-170">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span>

<span data-ttu-id="a9748-171">按照以下步骤创建组：</span><span class="sxs-lookup"><span data-stu-id="a9748-171">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="a9748-172">通过在仪表板顶部附近选择 " **+ 添加评估**" 来创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-172">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="a9748-173">从 "**评估**" 弹出窗口中，输入评估的标题，然后从下拉菜单中选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-173">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="a9748-174">在 "**请选择一个组或添加新组**" 中，选择 "**添加新组**"，然后在下面的字段中输入您的组名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-174">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="a9748-175">若要从现有组中复制信息，请切换**是否要从现有组中复制数据？** 切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="a9748-175">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="a9748-176">从下面的下拉菜单中选择要复制的组，并选中要在新组中将其传输到新评估中的任何字段的复选框。</span><span class="sxs-lookup"><span data-stu-id="a9748-176">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="a9748-177">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a9748-177">Select **Save**.</span></span> <span data-ttu-id="a9748-178">完成后，浮出控件窗格将关闭，您将在仪表板上看到您的新组。</span><span class="sxs-lookup"><span data-stu-id="a9748-178">When completed, the flyout pane closes and you'll see your new group on your dashboard.</span></span>

<span data-ttu-id="a9748-179">使用组时需要了解的内容：</span><span class="sxs-lookup"><span data-stu-id="a9748-179">What to know when working with groups:</span></span>
  
- <span data-ttu-id="a9748-180">组名（也称为*组 id*）在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a9748-180">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="a9748-181">组没有任何安全属性。</span><span class="sxs-lookup"><span data-stu-id="a9748-181">Groups do not have any security properties.</span></span> <span data-ttu-id="a9748-182">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="a9748-182">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="a9748-183">将评估添加到组后，不能更改分组。</span><span class="sxs-lookup"><span data-stu-id="a9748-183">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="a9748-184">您可以重命名评估组，这将更改与该组关联的所有评估的评估分组的名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-184">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="a9748-185">在同一组中的不同评估中的相关评估控件在完成后将自动更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-185">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="a9748-186">如果将新评估添加到现有组中，则会将该组中评估的常见信息复制到新评估中。</span><span class="sxs-lookup"><span data-stu-id="a9748-186">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="a9748-187">组可以包含对同一认证或法规的评估，但每个组只能包含针对特定产品认证对的一个评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-187">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="a9748-188">例如，组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-188">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="a9748-189">仅当一个组与同一个产品的对应证书或法规不同时，该组才可以包含对同一产品的多个评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-189">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="a9748-190">隐藏评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="a9748-190">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="a9748-191">其他相关评估的任何进一步更新不再在隐藏评估中反映出来。</span><span class="sxs-lookup"><span data-stu-id="a9748-191">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="a9748-192">（[了解如何隐藏评估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="a9748-192">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="a9748-193">无法删除组。</span><span class="sxs-lookup"><span data-stu-id="a9748-193">Groups cannot be deleted.</span></span>
- <span data-ttu-id="a9748-194">对显示在多个组中的措施项进行更改时，该更改将反映在该措施项的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="a9748-194">When a change is made to an Action Item that appears in multiple Groups, that change is reflected in all instances of that Action Item.</span></span>

## <a name="tenant-management-of-dimensions-owners--customer-actions"></a><span data-ttu-id="a9748-195">对维度、所有者、& 客户操作的租户管理</span><span class="sxs-lookup"><span data-stu-id="a9748-195">Tenant management of dimensions, owners, & customer actions</span></span>

<span data-ttu-id="a9748-196">**租户管理**界面使您能够管理以下组织范围的设置：</span><span class="sxs-lookup"><span data-stu-id="a9748-196">The **Tenant Management** interface enables you to manage these organization-wide settings:</span></span>

- <span data-ttu-id="a9748-197">**维：** 查看可用于为筛选器创建自定义透视的模板、评估和操作项的元数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-197">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="a9748-198">**所有者：** 填充可与操作关联的责任方列表。</span><span class="sxs-lookup"><span data-stu-id="a9748-198">**Owners:** Populate a list of responsible parties that can be associated with actions.</span></span>
- <span data-ttu-id="a9748-199">**客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并为与安全得分集成的操作启用/禁用安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="a9748-199">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="a9748-200">从屏幕右上角选择 "**租户管理**" 以打开管理界面，并使用以下步骤来管理**维度**、**所有者**和**客户操作**。</span><span class="sxs-lookup"><span data-stu-id="a9748-200">Select **Tenant Management** from the upper-right corner of your screen to open the management interface, and use the steps below to manage  **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="a9748-201">Dimensions</span><span class="sxs-lookup"><span data-stu-id="a9748-201">Dimensions</span></span>

<span data-ttu-id="a9748-202">维度是提供有关模板、评估或措施项的信息的元数据的集合。</span><span class="sxs-lookup"><span data-stu-id="a9748-202">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="a9748-203">维度使用键和值的概念，其中维度键表示属性，维度值表示属性的有效值。</span><span class="sxs-lookup"><span data-stu-id="a9748-203">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="a9748-204">例如，在合规性管理器中有三种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-204">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="a9748-205">它们由**操作目的**的维度键和**预防**、**侦探**和**纠正**的维度值定义。</span><span class="sxs-lookup"><span data-stu-id="a9748-205">They are defined by a Dimension Key of **Action Purpose** and Dimension Values of **Preventative**, **Detective**, and **Corrective**.</span></span>

### <a name="owners"></a><span data-ttu-id="a9748-206">Owners</span><span class="sxs-lookup"><span data-stu-id="a9748-206">Owners</span></span>

<span data-ttu-id="a9748-207">所有者用于标识负责每个控件的人员。</span><span class="sxs-lookup"><span data-stu-id="a9748-207">Owners are used to identify the person responsible for each control.</span></span> <span data-ttu-id="a9748-208">所有内置控件由 Microsoft、客户或这两者拥有。</span><span class="sxs-lookup"><span data-stu-id="a9748-208">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="a9748-209">您可以创建可用于在组织中指定更精确的职责的所有者的自定义值。</span><span class="sxs-lookup"><span data-stu-id="a9748-209">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="a9748-210">例如，可以创建代表组织中的特定组、团队或业务单位的所有者。</span><span class="sxs-lookup"><span data-stu-id="a9748-210">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="a9748-211">添加所有者</span><span class="sxs-lookup"><span data-stu-id="a9748-211">Add an Owner</span></span>

1. <span data-ttu-id="a9748-212">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-212">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a9748-213">选择 " **+ 添加所有者**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-213">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="a9748-214">提供所有者的名称和说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-214">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="a9748-215">说明显示在 "所有者" 列中。</span><span class="sxs-lookup"><span data-stu-id="a9748-215">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="a9748-216">编辑所有者</span><span class="sxs-lookup"><span data-stu-id="a9748-216">Edit an Owner</span></span>

<span data-ttu-id="a9748-217">您不能编辑所有者名称，但可以修改 "Owner" 列中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="a9748-217">You can't edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="a9748-218">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-218">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a9748-219">找到要编辑的所有者，选择其旁边的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-219">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="a9748-220">根据需要修改说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-220">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="a9748-221">删除所有者</span><span class="sxs-lookup"><span data-stu-id="a9748-221">Delete an Owner</span></span>

1. <span data-ttu-id="a9748-222">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-222">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a9748-223">找到要删除的所有者，选择其旁边的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-223">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="a9748-224">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-224">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="a9748-225">客户操作</span><span class="sxs-lookup"><span data-stu-id="a9748-225">Customer Actions</span></span>

<span data-ttu-id="a9748-226">"客户操作" 区域显示合规性管理器中所有模板和评估的所有客户操作（预览）。</span><span class="sxs-lookup"><span data-stu-id="a9748-226">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="a9748-227">![合规性管理器-添加用户](../media/compliance-manager-customer-actions.png "合规性管理器客户操作")</span><span class="sxs-lookup"><span data-stu-id="a9748-227">![Compliance Manager — add users](../media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="a9748-228">您可以一目了然地看到操作的标题、所有者、类别、强制和分数，并确定它是否与安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="a9748-228">At a glance, you can see an Action's title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="a9748-229">您可以展开操作并选择 "**读取更多**"，以读取操作说明并访问说明中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-229">You can expand an Action and select **Read More** to read the Action's description and access any links in the description.</span></span> <span data-ttu-id="a9748-230">您还可以使用此接口基于每个操作启用和禁用安全得分集成，并添加自定义操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-230">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="a9748-231">具有安全得分集成功能的操作旁边有一个省略号（...）（请注意，自定义操作旁边还有一个省略号）。</span><span class="sxs-lookup"><span data-stu-id="a9748-231">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="a9748-232">启用或禁用安全分数集成</span><span class="sxs-lookup"><span data-stu-id="a9748-232">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="a9748-233">选择要修改的操作的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-233">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="a9748-234">切换交换机以确保安全分数连续更新为 "开" 或 "关"，以通过安全分数启用或禁用连续监控。</span><span class="sxs-lookup"><span data-stu-id="a9748-234">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="a9748-235">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a9748-235">Select **Save**.</span></span>

<span data-ttu-id="a9748-236">当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。</span><span class="sxs-lookup"><span data-stu-id="a9748-236">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="a9748-237">在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。</span><span class="sxs-lookup"><span data-stu-id="a9748-237">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="a9748-238">在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。</span><span class="sxs-lookup"><span data-stu-id="a9748-238">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="a9748-239">安全分数集成不支持的任何操作都可以手动实现。</span><span class="sxs-lookup"><span data-stu-id="a9748-239">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="a9748-240">手动实现将考虑该操作的组的分数。</span><span class="sxs-lookup"><span data-stu-id="a9748-240">A manual implementation will factor into the score for that action's group.</span></span>

## <a name="assessments"></a><span data-ttu-id="a9748-241">评估</span><span class="sxs-lookup"><span data-stu-id="a9748-241">Assessments</span></span>

<span data-ttu-id="a9748-242">本节介绍如何查看和使用评估，包括如何添加新的评估、导出、复制现有评估中的信息，以及如何通过版本控制对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-242">This section explains how to view and work with your Assessments, including how to add new ones, export them, copy information from existing Assessments, and keep them updated through versioning.</span></span>

### <a name="view-an-assessment-and-action-details"></a><span data-ttu-id="a9748-243">查看评估和操作详细信息</span><span class="sxs-lookup"><span data-stu-id="a9748-243">View an Assessment and Action details</span></span>
  
<span data-ttu-id="a9748-244">在 "**评估**" 仪表板中，选择要打开的评估名称，并查看 "操作项" 和 "控件信息"。</span><span class="sxs-lookup"><span data-stu-id="a9748-244">In the **Assessments** dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="a9748-245">下面的示例展示了 Office 365 和 ISO 27001 的评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-245">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="a9748-246">第一个视图演示合规性管理器（预览版）中的新操作项视图。</span><span class="sxs-lookup"><span data-stu-id="a9748-246">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合规性管理器操作项目视图](../media/compliance-manager-action-items.png)

<span data-ttu-id="a9748-248">操作按字母顺序列出，并为每个操作分配一个分数和一个所有者。</span><span class="sxs-lookup"><span data-stu-id="a9748-248">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="a9748-249">选择 "**阅读更多**" 链接以阅读每个操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a9748-249">Select  the **Read More** link to read the details of each Action.</span></span>

![合规性管理器操作项目视图](../media/compliance-manager-actions-read-more.png)

<span data-ttu-id="a9748-251">选择 "**查看**" 链接以管理、分配、实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-251">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="a9748-252">下面是一个操作示例。</span><span class="sxs-lookup"><span data-stu-id="a9748-252">Below is an example Action.</span></span>

![合规性管理器操作视图](../media/compliance-manager-action.png)

<span data-ttu-id="a9748-254">使用以下字段来管理操作工作流：</span><span class="sxs-lookup"><span data-stu-id="a9748-254">Use the following fields to manage the Action workflow:</span></span>

- <span data-ttu-id="a9748-255">**为用户分配：** 选择此字段以选择或输入应为其分配此操作的用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-255">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="a9748-256">您可以在列表中滚动，或键入名称以查找它，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="a9748-256">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="a9748-257">**管理文档：** 您可以在 Office 文档、图像文件和屏幕截图、CSV 或 TXT 中的 PowerShell 输出以及 Pdf 中上载实现证据。</span><span class="sxs-lookup"><span data-stu-id="a9748-257">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="a9748-258">**实现状态：** 用于指示操作的当前实现状态。</span><span class="sxs-lookup"><span data-stu-id="a9748-258">**Implementation Status:** Used to indicate the Action's current implementation status.</span></span> <span data-ttu-id="a9748-259">可能的值尚未实现、实现、替代实施、规划且不在范围内。</span><span class="sxs-lookup"><span data-stu-id="a9748-259">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="a9748-260">**实施日期：** 执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="a9748-260">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="a9748-261">**测试结果：** 用于指示实现验证的结果。</span><span class="sxs-lookup"><span data-stu-id="a9748-261">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="a9748-262">可能的值未评估、传递、失败-低风险、失败-中等风险、失败-高风险以及不在范围内。</span><span class="sxs-lookup"><span data-stu-id="a9748-262">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="a9748-263">**测试日期：** 验证发生的日期。</span><span class="sxs-lookup"><span data-stu-id="a9748-263">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="a9748-264">**实现说明：** 输入您的组织的实现详细信息，以及您想要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="a9748-264">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="a9748-265">**测试计划：** 输入此操作的测试计划详细信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="a9748-265">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="a9748-266">**其他信息：** 输入有关此操作或在组织中实现此操作的方式的任何其他信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="a9748-266">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="a9748-267">在 "**控件信息**" 仪表板上，您可以在评估和模板级别查看控件的信息。</span><span class="sxs-lookup"><span data-stu-id="a9748-267">On the **Controls Info** dashboard, you can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="a9748-268">下面是用于评估的控件信息仪表板的一个示例。</span><span class="sxs-lookup"><span data-stu-id="a9748-268">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合规性管理器控制信息视图](../media/compliance-manager-controls-info.png)

<span data-ttu-id="a9748-270">对于评估，"控制信息" 仪表板将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="a9748-270">For Assessments, the Controls Info dashboard displays the following information:</span></span>

- <span data-ttu-id="a9748-271">一个**组**下拉列表，用于选择要查看的组（使用多个组时）。</span><span class="sxs-lookup"><span data-stu-id="a9748-271">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="a9748-272">一个**评估**下拉列表，用于选择要查看的评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-272">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="a9748-273">有关所选评估的元数据，包括：</span><span class="sxs-lookup"><span data-stu-id="a9748-273">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="a9748-274">**评估的控制措施**的进度指示器，其中显示了已评估的控制总数的控制次数。</span><span class="sxs-lookup"><span data-stu-id="a9748-274">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="a9748-275">评估的当前**合规性分数**，显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="a9748-275">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="a9748-276">有关评估中使用的**认证**和**产品**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a9748-276">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="a9748-277">评估的当前**状态**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="a9748-277">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="a9748-278">用于评估的**范围内的服务**的列表。</span><span class="sxs-lookup"><span data-stu-id="a9748-278">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="a9748-279">控件的详细信息，按控件系列分组，并提供指向客户操作和 Microsoft 实现详细信息的链接：</span><span class="sxs-lookup"><span data-stu-id="a9748-279">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="a9748-280">**您的操作**将显示您可以执行以满足部分或全部控件要求的客户操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-280">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control's requirements.</span></span> <span data-ttu-id="a9748-281">许多控件具有与之关联的多个操作，并且与控件关联的所有操作都显示在此处。</span><span class="sxs-lookup"><span data-stu-id="a9748-281">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="a9748-282">此处的操作与操作仪表板中列出的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="a9748-282">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="a9748-283">**Microsoft 操作**显示 microsoft 内部框架中应用于所选证书控制的控件列表。</span><span class="sxs-lookup"><span data-stu-id="a9748-283">**Microsoft Actions** displays the list of controls from Microsoft's internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="a9748-284">对于每个内部控件，选择 "已**实施**" 以查看 Microsoft 的实施和测试详细信息，以及测试结果和测试日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a9748-284">For each internal control, select **Implemented** to see Microsoft's implementation and test details, along with the test result and test date, as shown below.</span></span>

![合规性管理器 Microsoft 操作视图](../media/compliance-manager-microsoft-action.png)

### <a name="add-an-assessment"></a><span data-ttu-id="a9748-286">添加评估</span><span class="sxs-lookup"><span data-stu-id="a9748-286">Add an Assessment</span></span>
  
1. <span data-ttu-id="a9748-287">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-287">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="a9748-288">当边栏打开时，请输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="a9748-288">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="a9748-289">**标题（必需）：** 输入评估的标题</span><span class="sxs-lookup"><span data-stu-id="a9748-289">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="a9748-290">**请选择一个模板（必需）：** 选择标准或自定义模板</span><span class="sxs-lookup"><span data-stu-id="a9748-290">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="a9748-291">**请选择组或添加新组（必需）：** 选择现有组或选择添加新组，并提供唯一的组名称</span><span class="sxs-lookup"><span data-stu-id="a9748-291">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="a9748-292">**是否要复制现有组中的数据？（可选）：** 切换控件以启用组副本，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a9748-292">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="a9748-293">**选择一个组（可选）：** 如果已启用组副本，请选择要复制的组</span><span class="sxs-lookup"><span data-stu-id="a9748-293">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="a9748-294">**实现详细信息（可选）：** 选择以将实现详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="a9748-294">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="a9748-295">**测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="a9748-295">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="a9748-296">**文档（可选）：** 选择以将文档复制到新组</span><span class="sxs-lookup"><span data-stu-id="a9748-296">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="a9748-297">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-297">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="a9748-298">新评估显示在评估仪表板上，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="a9748-298">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="a9748-299">评估的标题。</span><span class="sxs-lookup"><span data-stu-id="a9748-299">The title of the Assessment.</span></span>
- <span data-ttu-id="a9748-300">评估的维度，包括认证、环境和应用于评估的产品。</span><span class="sxs-lookup"><span data-stu-id="a9748-300">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="a9748-301">创建日期的日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="a9748-301">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="a9748-302">评估分数显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="a9748-302">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="a9748-303">此分数自动包含来自 Microsoft 托管控件和安全得分的分数。</span><span class="sxs-lookup"><span data-stu-id="a9748-303">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="a9748-304">进度指示器，显示已评估的 Microsoft 托管控件和客户托管的控件的数量。</span><span class="sxs-lookup"><span data-stu-id="a9748-304">Progress indicators that show the number of assessed Microsoft-managed and customer-managed controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="a9748-305">从现有评估复制信息</span><span class="sxs-lookup"><span data-stu-id="a9748-305">Copying information from existing Assessments</span></span>

<span data-ttu-id="a9748-306">创建评估时，可以选择从现有组复制信息。</span><span class="sxs-lookup"><span data-stu-id="a9748-306">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="a9748-307">通过复制，您可以将输入到复制的评估中的信息应用于新评估中的相同控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-307">Copying allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="a9748-308">例如，如果您的组织中有与 FFIEC 相关的所有评估的组，则可以从现有评估中复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="a9748-308">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="a9748-309">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="a9748-309">Implementation Details</span></span>
- <span data-ttu-id="a9748-310">测试计划 & 其他信息</span><span class="sxs-lookup"><span data-stu-id="a9748-310">Test Plan & Additional Information</span></span>
- <span data-ttu-id="a9748-311">文档</span><span class="sxs-lookup"><span data-stu-id="a9748-311">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="a9748-312">将信息从现有评估复制到新评估</span><span class="sxs-lookup"><span data-stu-id="a9748-312">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="a9748-313">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-313">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="a9748-314">在 "**添加评估**" 窗口中，填写以下信息</span><span class="sxs-lookup"><span data-stu-id="a9748-314">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="a9748-315">**标题（必需）：** 输入评估的标题。</span><span class="sxs-lookup"><span data-stu-id="a9748-315">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="a9748-316">**请选择一个模板（必需）：** 选择标准或自定义模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-316">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="a9748-317">**请选择组或添加新组（必需）：** 选择 "**添加新组**" 并提供一个唯一的组名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-317">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="a9748-318">**是否要复制现有组中的数据？（可选）：** 将控件切换到 "打开" 以启用组副本，然后：-**选择一个组（可选）：** 如果已启用组副本，请从组中选择要复制的组。</span><span class="sxs-lookup"><span data-stu-id="a9748-318">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="a9748-319">- **实现详细信息（可选）：** 选择将实现详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="a9748-319">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="a9748-320">- **测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="a9748-320">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="a9748-321">- **文档（可选）：** 选择以将文档复制到新组。</span><span class="sxs-lookup"><span data-stu-id="a9748-321">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="a9748-322">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-322">Select **Save** to create the Assessment.</span></span>

### <a name="versioning-alerts-for-assessment-updates"></a><span data-ttu-id="a9748-323">评估更新的版本控制警报</span><span class="sxs-lookup"><span data-stu-id="a9748-323">Versioning alerts for Assessment updates</span></span>

<span data-ttu-id="a9748-324">如果有可供评估的更新，则会出现一个警报图标，通知您更新已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="a9748-324">When an update is available for an Assessment, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="a9748-325">当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。</span><span class="sxs-lookup"><span data-stu-id="a9748-325">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="a9748-326">下面是针对评估的版本控制警报的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a9748-326">Below is an example of the versioning alert for an Assessment:</span></span>

<span data-ttu-id="a9748-327">![合规性分数-版本控制警报](../media/compliance-score-assessment-version.png "评估版本更新警报")</span><span class="sxs-lookup"><span data-stu-id="a9748-327">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="a9748-328">选择警报图标可显示一个弹出窗格，其中介绍了更新并提示您接受：</span><span class="sxs-lookup"><span data-stu-id="a9748-328">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="a9748-329">![合规性分数-版本化飞出](../media/compliance-score-assessment-version-accept.png "评估更新确认窗格")</span><span class="sxs-lookup"><span data-stu-id="a9748-329">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

<span data-ttu-id="a9748-330">强烈建议您在收到更新通知时接受所有更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-330">We strongly recommend accepting all updates when you receive update notifications.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="a9748-331">导出评估</span><span class="sxs-lookup"><span data-stu-id="a9748-331">Export an Assessment</span></span>

<span data-ttu-id="a9748-332">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="a9748-332">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="a9748-333">报告是在创建报告的日期和时间的评估的快照。</span><span class="sxs-lookup"><span data-stu-id="a9748-333">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="a9748-334">该报告包含有关评估、控制实施状态、控制测试日期、测试结果的所有 Microsoft 和客户托管控件的详细信息，并提供了指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-334">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="a9748-335">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="a9748-335">Export an Assessment report</span></span>
  
1. <span data-ttu-id="a9748-336">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9748-336">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="a9748-337">在要导出的评估的下拉菜单中，选择 "**组**和**评估**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-337">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="a9748-338">选择 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9748-338">Select the **Export** button.</span></span>

<span data-ttu-id="a9748-339">在浏览器会话中，会将评估报告作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="a9748-339">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="a9748-340">Excel 文件的文件名称默认为评估的标题。</span><span class="sxs-lookup"><span data-stu-id="a9748-340">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="a9748-341">隐藏模板或评估</span><span class="sxs-lookup"><span data-stu-id="a9748-341">Hide a Template or an Assessment</span></span>

<span data-ttu-id="a9748-342">当您完成模板或评估且不再出于合规性目的而需要时，您可以将其从视图中隐藏。</span><span class="sxs-lookup"><span data-stu-id="a9748-342">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="a9748-343">如果模板或评估处于隐藏状态，则会将其从默认视图中删除，并且必须选中 "**包含隐藏**的" 复选框以显示它。</span><span class="sxs-lookup"><span data-stu-id="a9748-343">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="a9748-344">![合规性管理器隐藏的模板视图](../media/compliance-manager-hidden-template.png "合规性管理器隐藏模板")</span><span class="sxs-lookup"><span data-stu-id="a9748-344">![Compliance Manager Hidden Template View](../media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9748-345">隐藏的评估不会保留其到已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-345">Hidden Assessments don't retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="a9748-346">强烈建议您先导出评估，然后再将其隐藏，以保留指向报告中的证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-346">We highly recommended that you export an Assessment before hiding it to retain links to evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="a9748-347">隐藏模板</span><span class="sxs-lookup"><span data-stu-id="a9748-347">Hiding a Template</span></span>

1. <span data-ttu-id="a9748-348">打开 "**模板**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="a9748-348">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="a9748-349">找到要隐藏的模板，并在其所在行的省略号处，选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-349">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="a9748-350">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-350">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="a9748-351">隐藏评估</span><span class="sxs-lookup"><span data-stu-id="a9748-351">Hide an Assessment</span></span>

1. <span data-ttu-id="a9748-352">打开 "**评估**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="a9748-352">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="a9748-353">从下拉列表中选择包含您要隐藏的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="a9748-353">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="a9748-354">找到要隐藏的评估，然后在省略号上选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-354">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="a9748-355">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-355">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="a9748-356">查看隐藏评估</span><span class="sxs-lookup"><span data-stu-id="a9748-356">View hidden Assessments</span></span>
  
1. <span data-ttu-id="a9748-357">打开 "**评估**仪表板" 选项卡，然后选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a9748-357">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="a9748-358">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="a9748-358">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="a9748-359">取消隐藏评估</span><span class="sxs-lookup"><span data-stu-id="a9748-359">Unhide an Assessment</span></span>

1. <span data-ttu-id="a9748-360">在 "**评估**" 选项卡上，选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a9748-360">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="a9748-361">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="a9748-361">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="a9748-362">找到要取消隐藏的评估，然后在省略号上选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-362">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="a9748-363">当您看到确认消息时，请选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-363">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="a9748-364">控件和操作</span><span class="sxs-lookup"><span data-stu-id="a9748-364">Controls and Actions</span></span>

<span data-ttu-id="a9748-365">控件和操作是合规性管理器（预览版）中使用的主要数据透视。</span><span class="sxs-lookup"><span data-stu-id="a9748-365">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="a9748-366">在早期版本的合规性管理器中存在的控制轴已得到增强，可在相同的控制系列中显示 Microsoft 和 customer 控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-366">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="a9748-367">此 "合并" 视图使以每个控件为基础查看完整的共享职责模型变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="a9748-367">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="a9748-368">操作透视是合规性管理器（预览版）中的新操作，旨在提供 Microsoft 建议的所有操作的简化视图。</span><span class="sxs-lookup"><span data-stu-id="a9748-368">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="a9748-369">控件</span><span class="sxs-lookup"><span data-stu-id="a9748-369">Controls</span></span>

<span data-ttu-id="a9748-370">可以从 "控件信息" 仪表板查看控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-370">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="a9748-371">控件表示标准、认证、法规或框架中的要求。</span><span class="sxs-lookup"><span data-stu-id="a9748-371">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="a9748-372">若要跨多个标准、法规等满足这些要求，并将它们与操作相关联，则所有内容都被视为控制框架。</span><span class="sxs-lookup"><span data-stu-id="a9748-372">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="a9748-373">例如，像控制框架一样，法规（如 HIPAA）已按节细分，合规性管理器中的 HIPAA 控件使用与这些节相同的编号方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9748-373">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合规性管理器 Microsoft 控件详细信息](../media/compliance-manager-control-details.png)

<span data-ttu-id="a9748-375">有三种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="a9748-375">There are three types of controls:</span></span>

1. <span data-ttu-id="a9748-376">**Microsoft 托管控件：** 这些控件只是 microsoft 有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-376">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="a9748-377">它们显示在 "现成" 模板中，并已添加到 Microsoft 的合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="a9748-377">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="a9748-378">**客户管理的控件：** 这些控件只是客户有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-378">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="a9748-379">它们显示在 "现成" 模板中，并由客户添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="a9748-379">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="a9748-380">**共享管理控件：** 这些控件是在 Microsoft 和客户之间共享责任的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-380">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="a9748-381">这些模板显示在 "现成" 模板中，由 Microsoft 添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="a9748-381">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="a9748-382">客户还可以编辑或禁用 Microsoft 托管的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-382">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="a9748-383">Actions 项</span><span class="sxs-lookup"><span data-stu-id="a9748-383">Actions Items</span></span>

<span data-ttu-id="a9748-384">操作项目是实施标准或法规要求的建议任务，或者用于测试、验证和记录组织的实现要求的任务。</span><span class="sxs-lookup"><span data-stu-id="a9748-384">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="a9748-385">操作与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="a9748-385">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="a9748-386">每个控件都有一个或多个与之关联的操作，并且每个操作都可以与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="a9748-386">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="a9748-387">操作是合规性管理器（预览版）中核心工作流的一部分，因为它们是由组织分配、跟踪和验证的对象。</span><span class="sxs-lookup"><span data-stu-id="a9748-387">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="a9748-388">分配操作项</span><span class="sxs-lookup"><span data-stu-id="a9748-388">Assign Action Items</span></span>
  
1. <span data-ttu-id="a9748-389">在 "**操作项**" 仪表板上，选择包含要分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="a9748-389">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="a9748-390">在 "**评估**" 下拉列表中，选择要为其分配操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-390">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="a9748-391">找到要分配的操作，并在 "**所有者**" 列中选择要**查看**的链接、\* \* 已实现或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-391">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, \*\*Implemented, or **Test**.</span></span>
4. <span data-ttu-id="a9748-392">选择 "**分配用户**" 字段，将显示组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="a9748-392">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="a9748-393">滚动列表并选择 "用户" 或 "筛选列表" 以通过键入用户的名称来选择用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-393">Scroll the list and select user or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="a9748-394">在 "实施说明" 字段中，输入您希望向分配的用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="a9748-394">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="a9748-395">选择 "**保存**" 以分配操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-395">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="a9748-396">重新分配操作项</span><span class="sxs-lookup"><span data-stu-id="a9748-396">Reassign Action Items</span></span>

<span data-ttu-id="a9748-397">通过此函数，组织可以通过将操作重新分配给新用户，删除对用户帐户的任何活动的或未完成的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a9748-397">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="a9748-398">在 "**操作项**" 仪表板上，选择包含要重新分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="a9748-398">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="a9748-399">在 "**评估**" 下拉列表中，选择要重新分配其操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-399">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="a9748-400">找到要重新分配的操作，并在 "**所有者**" 列中选择要**查看**、**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-400">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="a9748-401">从 "**分配用户**" 字段中删除现有用户，然后从用户列表中选择其他用户，或通过键入用户名称来筛选列表以选择用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-401">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="a9748-402">在 "实施说明" 字段中，输入您希望向用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="a9748-402">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="a9748-403">选择 "**保存**" 以重新分配该操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-403">Select **Save** to reassign the Action.</span></span>

#### <a name="common-action-items-synch-status-across-groups"></a><span data-ttu-id="a9748-404">跨组的常见操作项同步状态</span><span class="sxs-lookup"><span data-stu-id="a9748-404">Common Action Items synch status across Groups</span></span>

<span data-ttu-id="a9748-405">如果您的组织具有多个评估组，则会有技术操作的行为（即，影响整个组织的操作）。</span><span class="sxs-lookup"><span data-stu-id="a9748-405">If your organization has multiple groups of assessments, there is a behavior of Technical actions (that is, actions affecting your entire organization).</span></span> <span data-ttu-id="a9748-406">所有组中的重复操作现在组合到一个单一操作中。</span><span class="sxs-lookup"><span data-stu-id="a9748-406">Any duplicate actions across groups are now combined into one single action.</span></span> <span data-ttu-id="a9748-407">该单个操作包含所有上载的笔记和来自以前的重复版本的证据。</span><span class="sxs-lookup"><span data-stu-id="a9748-407">That single action contains all uploaded notes and evidence from previously duplicate versions.</span></span> <span data-ttu-id="a9748-408">在一个组或评估中对操作所做的任何更改都将反映在该操作的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="a9748-408">Any change made to the action in one group or assessment will be reflected in all instances of that action.</span></span> <span data-ttu-id="a9748-409">"实现**状态**"、"**实施日期**"、"**测试状态**" 和 "**测试日期**" 字段反映了最新的更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-409">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** fields reflect the most recent updates.</span></span>

## <a name="templates"></a><span data-ttu-id="a9748-410">模板</span><span class="sxs-lookup"><span data-stu-id="a9748-410">Templates</span></span>

<span data-ttu-id="a9748-411">模板是合规性管理器（预览）中与产品和证书（例如，标准、法规、控制框架等）相关联的基本对象。</span><span class="sxs-lookup"><span data-stu-id="a9748-411">A Template is the base object in Compliance Manager (Preview) that is associated with a product and a certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="a9748-412">可以从 "**模板**" 仪表板中查看和添加模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-412">Templates can be viewed and added from the **Templates** dashboard.</span></span>

![合规性管理器 Microsoft 模板仪表板](../media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="a9748-414">仪表板将显示每个模板，以及与模板关联的证书和产品、创建模板的日期和上次修改的日期、客户和 Microsoft 托管控件的数量、模板的最大合规性分数以及模板的状态（例如，已批准、待定审批、导入）。</span><span class="sxs-lookup"><span data-stu-id="a9748-414">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

### <a name="create-a-template"></a><span data-ttu-id="a9748-415">创建模板</span><span class="sxs-lookup"><span data-stu-id="a9748-415">Create a Template</span></span>

<span data-ttu-id="a9748-416">有三种方法可以使用模板来创建评估：</span><span class="sxs-lookup"><span data-stu-id="a9748-416">There are three ways to work with Templates to create Assessments:</span></span>

1. <span data-ttu-id="a9748-417">使用 Microsoft 提供的预先配置的模板之一。</span><span class="sxs-lookup"><span data-stu-id="a9748-417">Use one of the pre-configured Templates provided by Microsoft.</span></span>
2. <span data-ttu-id="a9748-418">通过扩展过程自定义预先配置的模板以及您自己的操作和控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-418">Customize a pre-configured Template with your own actions and controls through the extension process.</span></span>
3. <span data-ttu-id="a9748-419">创建您自己的模板并将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="a9748-419">Create your own Template and import it into Compliance Manager.</span></span>

#### <a name="use-a-microsoft-pre-configured-template"></a><span data-ttu-id="a9748-420">使用 Microsoft 预先配置的模板</span><span class="sxs-lookup"><span data-stu-id="a9748-420">Use a Microsoft pre-configured Template</span></span>

<span data-ttu-id="a9748-421">预配置的模板在**模板**仪表板上可用。</span><span class="sxs-lookup"><span data-stu-id="a9748-421">The pre-configured templates are available on your **Templates** dashboard.</span></span> <span data-ttu-id="a9748-422">查看当前[模板列表](compliance-manager-overview.md#templates)，该列表会在每次有新模板时更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-422">View the current [list of templates](compliance-manager-overview.md#templates), which is updated each time a new template is available.</span></span>

#### <a name="customize-a-template-through-the-extension-process"></a><span data-ttu-id="a9748-423">通过扩展过程自定义模板</span><span class="sxs-lookup"><span data-stu-id="a9748-423">Customize a Template through the extension process</span></span>

1. <span data-ttu-id="a9748-424">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-424">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="a9748-425">在 "模板" 浮出控件窗格中，选中 "**从全局模板创建扩展**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a9748-425">On the Template flyout pane, select the **Create extension from global template** checkbox.</span></span>
3. <span data-ttu-id="a9748-426">从下拉式菜单中选择要扩展的模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-426">Select the template you want to extend from the drop-down menu.</span></span>
4. <span data-ttu-id="a9748-427">如果尚未在 Excel 中设置模板数据的格式，请选择浮出控件窗格中的链接以下载 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="a9748-427">If you have not already formatted your template data in Excel, select the link in the flyout pane to download an Excel file.</span></span> <span data-ttu-id="a9748-428">根据 "[导入模板数据](#import-template-data-with-excel)" 和下面的 Excel 说明填写电子表格，并将其保存到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="a9748-428">Fill out the spreadsheet according to the [Import Template data with Excel](#import-template-data-with-excel) instructions below and save it to your local drive.</span></span>
5. <span data-ttu-id="a9748-429">通过选择 "**浏览**" 来上载您的 Excel 文件，以导入自定义模板数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-429">Import your customized template data by selecting **Browse** to upload your Excel file.</span></span>
6. <span data-ttu-id="a9748-430">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-430">Select **Add to Dashboard**.</span></span> <span data-ttu-id="a9748-431">然后，你将看到添加到**模板**仪表板的新模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-431">You will then see your new template added to your **Templates** dashboard.</span></span>

#### <a name="create-your-own-template-and-import-it-into-compliance-manager"></a><span data-ttu-id="a9748-432">创建您自己的模板并将其导入到合规性管理器</span><span class="sxs-lookup"><span data-stu-id="a9748-432">Create your own Template and import it into Compliance Manager</span></span>

1. <span data-ttu-id="a9748-433">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-433">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="a9748-434">在 "模板" 浮出控件窗格中，选择 "**创建新模板**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-434">On the Template flyout pane, select **Create a new template**.</span></span>
3. <span data-ttu-id="a9748-435">通过选择 "**浏览**" 以上传包含数据的 Excel 文件（请参阅以下[Excel 中的导入模板数据](#import-template-data-with-excel)）导入模板数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-435">Import your template data by selecting **Browse** to upload your Excel file containing the data (see [Import Template data with Excel](#import-template-data-with-excel) below).</span></span>
4. <span data-ttu-id="a9748-436">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-436">Select **Add to Dashboard**.</span></span> <span data-ttu-id="a9748-437">然后，你将看到添加到**模板**仪表板的新模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-437">You will then see your new template added to your **Templates** dashboard.</span></span>

#### <a name="import-template-data-with-excel"></a><span data-ttu-id="a9748-438">使用 Excel 导入模板数据</span><span class="sxs-lookup"><span data-stu-id="a9748-438">Import Template data with Excel</span></span>

<span data-ttu-id="a9748-439">若要修改模板或创建自己的模板，您将使用[Excel 电子表格](https://go.microsoft.com/fwlink/?linkid=2124865)来捕获必要数据并将其上载到合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="a9748-439">To modify a template or create your own template, you'll use an [Excel spreadsheet](https://go.microsoft.com/fwlink/?linkid=2124865) to capture the necessary data and upload it to Compliance Manager.</span></span> <span data-ttu-id="a9748-440">此电子表格模板具有必须使用的特定格式和架构，或者不会将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="a9748-440">This spreadsheet template has a specific format and schema that must be used or it will not import into Compliance Manager.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9748-441">如果之前已在合规性管理器中创建或自定义模板，则**此过程已**作为2020年4月发布的合规性管理器（预览版）的一部分进行了更新。</span><span class="sxs-lookup"><span data-stu-id="a9748-441">If you've created or customized templates in Compliance Manager before, **this process has been updated** as part of the April 2020 release of Compliance Manager (Preview).</span></span> <span data-ttu-id="a9748-442">**请仔细查看此部分。**</span><span class="sxs-lookup"><span data-stu-id="a9748-442">**Please review this section carefully.**</span></span>

<span data-ttu-id="a9748-443">电子表格包含四个选项卡，其中三个选项卡是必需的：</span><span class="sxs-lookup"><span data-stu-id="a9748-443">The spreadsheet contains four tabs, three of which are required:</span></span>

1. <span data-ttu-id="a9748-444">模板（必需）</span><span class="sxs-lookup"><span data-stu-id="a9748-444">Template (required)</span></span>
2. <span data-ttu-id="a9748-445">ControlFamily （必需）</span><span class="sxs-lookup"><span data-stu-id="a9748-445">ControlFamily (required)</span></span>
3. <span data-ttu-id="a9748-446">操作（必需）</span><span class="sxs-lookup"><span data-stu-id="a9748-446">Actions (required)</span></span>
4. <span data-ttu-id="a9748-447">维度（可选）</span><span class="sxs-lookup"><span data-stu-id="a9748-447">Dimensions (optional)</span></span>

<span data-ttu-id="a9748-448">您的电子表格**必须按此顺序包含选项卡**，否则您的数据将无法成功导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="a9748-448">Your spreadsheet **must include the tabs in this order**, otherwise your data won't successfully import to a template.</span></span>

##### <a name="template-tab"></a><span data-ttu-id="a9748-449">模板选项卡</span><span class="sxs-lookup"><span data-stu-id="a9748-449">Template tab</span></span>

<span data-ttu-id="a9748-450">"**模板**" 选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="a9748-450">The **Template** tab is required.</span></span> <span data-ttu-id="a9748-451">此选项卡中的信息提供有关模板的元数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-451">The information in this tab provides metadata about the template.</span></span> <span data-ttu-id="a9748-452">有四个必需的列。</span><span class="sxs-lookup"><span data-stu-id="a9748-452">There are four required columns.</span></span> <span data-ttu-id="a9748-453">列必须保留在 Excel 工作表上的顺序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a9748-453">The columns must retain the order on the Excel sheet as listed below.</span></span> <span data-ttu-id="a9748-454">您可以在四列**之后**添加自己的列，以提供自己的维度。</span><span class="sxs-lookup"><span data-stu-id="a9748-454">You can add your own column **after** the four columns to provide your own dimensions.</span></span> <span data-ttu-id="a9748-455">如果执行此操作，请务必按照[下面的说明](#dimensions-tab)将其添加到 "**维度**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9748-455">If you do this, be sure to add them to the **Dimensions** tab using the [instructions below](#dimensions-tab).</span></span>

- <span data-ttu-id="a9748-456">**title**：这是模板的标题，它必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a9748-456">**title**: This is the title for your template, which must be unique.</span></span> <span data-ttu-id="a9748-457">它无法与合规性管理器中的其他模板共享名称，无论它是已创建的模板，还是由 Microsoft 提供的预先配置的模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-457">It can't share a name with another template you have in Compliance Manager, whether it's a template you already created, or a pre-configured template provided by Microsoft.</span></span>

- <span data-ttu-id="a9748-458">**产品**：这是必需的维度。</span><span class="sxs-lookup"><span data-stu-id="a9748-458">**product**: This is a required dimension.</span></span> <span data-ttu-id="a9748-459">列出与模板关联的产品。</span><span class="sxs-lookup"><span data-stu-id="a9748-459">List the product associated with the template.</span></span>

- <span data-ttu-id="a9748-460">**证书**：这是您要为模板使用的法规。</span><span class="sxs-lookup"><span data-stu-id="a9748-460">**certification**: This is the regulation you're using for the template.</span></span>

- <span data-ttu-id="a9748-461">**inScopeServices**：这些服务是此评估解决的产品中的服务（例如，如果您将 Office 365 列为产品，则 Microsoft 团队可能是一个范围内的服务）。</span><span class="sxs-lookup"><span data-stu-id="a9748-461">**inScopeServices**: These are the services within the product that this assessment addresses (for example, if you listed Office 365 as the product, Microsoft Teams could be an in-scope service).</span></span> <span data-ttu-id="a9748-462">您可以列出用两个分号分隔的多个服务。</span><span class="sxs-lookup"><span data-stu-id="a9748-462">You can list multiple services separated by two semi-colons.</span></span>

> [!NOTE]
> <span data-ttu-id="a9748-463">关于产品和证书：在导入 "**产品**" 和 "**证书**" 单元格中插入的数据无法在导入电子表格以创建或自定义模板之后进行编辑。</span><span class="sxs-lookup"><span data-stu-id="a9748-463">Regarding product and certification: The data you insert in the **product** and **certification** cells cannot be edited after you import the spreadsheet to create or customize a template.</span></span> <span data-ttu-id="a9748-464">此外，组不能包含具有相同的**产品/认证**组合的两个评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-464">Also, a group cannot contain two assessments that have the same **product/certification** combination.</span></span> <span data-ttu-id="a9748-465">您可以有多个模板具有相同的产品/认证组合。</span><span class="sxs-lookup"><span data-stu-id="a9748-465">You can have multiple templates that have the same product/certification combination.</span></span>

##### <a name="controlfamily-tab"></a><span data-ttu-id="a9748-466">ControlFamily 选项卡</span><span class="sxs-lookup"><span data-stu-id="a9748-466">ControlFamily tab</span></span>

<span data-ttu-id="a9748-467">**ControlFamily**选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="a9748-467">The **ControlFamily** tab is required.</span></span>  <span data-ttu-id="a9748-468">此选项卡中的必需列（必须遵循示例电子表格中提供的顺序）为：</span><span class="sxs-lookup"><span data-stu-id="a9748-468">The required columns in this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="a9748-469">**controlName**：这是来自证书、标准或法规的控件名称，通常是某种类型的 ID。</span><span class="sxs-lookup"><span data-stu-id="a9748-469">**controlName**: This is the control name from the certification, standard, or regulation, which is typically some type of ID.</span></span> <span data-ttu-id="a9748-470">控件名称在模板中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a9748-470">Control names must be unique within a template.</span></span> <span data-ttu-id="a9748-471">电子表格中不能有多个名称相同的控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-471">You can't have multiple controls with the same name in the spreadsheet.</span></span>

- <span data-ttu-id="a9748-472">**controlFamily**：为 controlFamily 提供一个单词或短语，用于标识广泛的控件分组。</span><span class="sxs-lookup"><span data-stu-id="a9748-472">**controlFamily**: Provide a word or phrase for the controlFamily, which identifies a broad grouping of controls.</span></span> <span data-ttu-id="a9748-473">ControlFamily 不一定是唯一的;它可以在电子表格中多次列出。</span><span class="sxs-lookup"><span data-stu-id="a9748-473">A controlFamily doesn't have to be unique; it can be listed more than once in a spreadsheet.</span></span> <span data-ttu-id="a9748-474">同一个 controlFamily 也可以在多个模板中列出，尽管它们彼此之间没有关系。</span><span class="sxs-lookup"><span data-stu-id="a9748-474">The same controlFamily can also be listed in multiple templates, though they have no relation to each other.</span></span> <span data-ttu-id="a9748-475">每个 controlFamily 必须至少映射到一个控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-475">Every controlFamily must be mapped to at least one control.</span></span>

- <span data-ttu-id="a9748-476">**controlTitle**：提供控件的标题。</span><span class="sxs-lookup"><span data-stu-id="a9748-476">**controlTitle**: Provide a title for the control.</span></span> <span data-ttu-id="a9748-477">尽管 controlName 是参考代码，但标题是一种通常会在法规中看到的 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="a9748-477">Whereas the controlName is a reference code, the title is a rich text format typically seen in the regulations.</span></span>

- <span data-ttu-id="a9748-478">**controlDescription**：提供控件的说明。</span><span class="sxs-lookup"><span data-stu-id="a9748-478">**controlDescription**: Provide a description of the control.</span></span>

- <span data-ttu-id="a9748-479">**controlActionTitle**：这是要与此控件相关的操作的标题。</span><span class="sxs-lookup"><span data-stu-id="a9748-479">**controlActionTitle**: This is the title of an action that you want to relate to this control.</span></span> <span data-ttu-id="a9748-480">您可以添加多个操作，方法是用两个分号隔开，中间没有空格。</span><span class="sxs-lookup"><span data-stu-id="a9748-480">You can add multiple actions by separating by two semi-colons with no space in between.</span></span> <span data-ttu-id="a9748-481">您列出的每个控件必须至少包含一个操作，并且该操作必须存在（这意味着您可以在同一电子表格的 "**操作**" 选项卡上列出您列出的操作、存在于其他模板中的操作或由 Microsoft 创建的操作）。</span><span class="sxs-lookup"><span data-stu-id="a9748-481">Every control you list must include at least one action, and the action must exist (which means you can list an action that you list on the **Actions** tab of the same spreadsheet, an action that exists in a different template, or an action created by Microsoft).</span></span> <span data-ttu-id="a9748-482">不同的控件可以引用相同的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-482">Different controls can reference the same action.</span></span>

##### <a name="actions-tab"></a><span data-ttu-id="a9748-483">操作选项卡</span><span class="sxs-lookup"><span data-stu-id="a9748-483">Actions tab</span></span>

<span data-ttu-id="a9748-484">"**操作**" 选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="a9748-484">The **Actions** tab is required.</span></span>  <span data-ttu-id="a9748-485">它指定您的组织的操作，而不是 Microsoft 的操作，这些操作在合规性管理器中已存在。</span><span class="sxs-lookup"><span data-stu-id="a9748-485">It designates actions of your organization and not the actions of Microsoft, which already exist in Compliance Manager.</span></span> <span data-ttu-id="a9748-486">此选项卡必需的列必须遵循示例电子表格中提供的顺序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9748-486">The required columns for this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="a9748-487">**actionTitle**：这是您的操作的标题，是必填字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-487">**actionTitle**: This is the title for your action and is a required field.</span></span> <span data-ttu-id="a9748-488">您提供的标题必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a9748-488">The title you provide must be unique.</span></span> <span data-ttu-id="a9748-489">**重要说明**：如果您引用您拥有的已存在的操作（如在另一个模板中），并且在后续列中修改了它的任何元素，则这些更改将传播到其他模板中的同一操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-489">**Important**: if you reference an action you own that already exists (such as in another template) and you modify any of its elements in the subsequent columns, those changes will propagate to the same action in other templates.</span></span>

- <span data-ttu-id="a9748-490">**implementationType**：在此必填字段中，列出以下三种实现类型之一：</span><span class="sxs-lookup"><span data-stu-id="a9748-490">**implementationType**: In this required field, list one of the three implementation types below:</span></span>
    - <span data-ttu-id="a9748-491">**操作**-由人员和进程实现以保护组织系统、资产、数据和人员的机密性、完整性和可用性（示例：安全意识和培训）</span><span class="sxs-lookup"><span data-stu-id="a9748-491">**Operational** - actions implemented by people and processes to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: security awareness and training)</span></span>
    - <span data-ttu-id="a9748-492">**技术**-通过使用信息系统的硬件、软件或固件组件中包含的技术和机制完成操作，以保护组织系统和数据的机密性、完整性和可用性（示例：多重身份验证）</span><span class="sxs-lookup"><span data-stu-id="a9748-492">**Technical** - actions completed through the use of technology and mechanisms contained in the hardware, software, or firmware components of the information system to protect the confidentiality, integrity, and availability of organizational systems and data (example: multi-factor authentication)</span></span>
    - <span data-ttu-id="a9748-493">**文档**-通过记录的策略和程序实现的操作：建立和定义保护组织系统、资产、数据和人员的机密性、完整性和可用性所需的控件（示例：信息安全策略）</span><span class="sxs-lookup"><span data-stu-id="a9748-493">**Documentation** - actions implemented through documented policies and procedures establishing and defining the controls required to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: an information security policy)</span></span>

- <span data-ttu-id="a9748-494">**actionScore**：在此必填字段中，为您的操作提供数值分数值。</span><span class="sxs-lookup"><span data-stu-id="a9748-494">**actionScore**: In this required field, provide a numeric score value for your action.</span></span> <span data-ttu-id="a9748-495">它必须是介于1到99之间的整数;它不能为0、null 或空。</span><span class="sxs-lookup"><span data-stu-id="a9748-495">It must be a whole number ranging from 1 to 99; it cannot be 0, null, or blank.</span></span> <span data-ttu-id="a9748-496">此数字越大，它在改进合规性状态方面的价值越大。</span><span class="sxs-lookup"><span data-stu-id="a9748-496">The higher the number, the greater its value toward improving your compliance posture.</span></span> <span data-ttu-id="a9748-497">有关指南，请参阅下文 Microsoft 如何对控件进行评分：</span><span class="sxs-lookup"><span data-stu-id="a9748-497">For guidance, see below how Microsoft scores its controls:</span></span>

<span data-ttu-id="a9748-498">![合规性管理器控制点值](../media/compliance-score-controls-scoring.png "合规性管理器控制点值")</span><span class="sxs-lookup"><span data-stu-id="a9748-498">![Compliance Manager controls point values](../media/compliance-score-controls-scoring.png "Compliance Manager controls point values")</span></span>

- <span data-ttu-id="a9748-499">**actionDescriptionTitle**：这是说明的标题，并且是必需的。</span><span class="sxs-lookup"><span data-stu-id="a9748-499">**actionDescriptionTitle**: This is the title of the description and is required.</span></span> <span data-ttu-id="a9748-500">此描述标题允许您在多个模板中执行相同的操作，并在每个模板中显示不同的说明。</span><span class="sxs-lookup"><span data-stu-id="a9748-500">This description title allows you to have the same action in multiple templates and surface a different description in each template.</span></span>  <span data-ttu-id="a9748-501">此字段可帮助您阐明说明所引用的模板。</span><span class="sxs-lookup"><span data-stu-id="a9748-501">This field helps you clarify what template the description is referencing.</span></span> <span data-ttu-id="a9748-502">在大多数情况下，您可以在此字段中放置正在创建的模板的名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-502">In most cases, you can put the name of the template you're creating in this field.</span></span>

- <span data-ttu-id="a9748-503">**actionDescription**：提供操作的说明。</span><span class="sxs-lookup"><span data-stu-id="a9748-503">**actionDescription**: Provide a description of the action.</span></span> <span data-ttu-id="a9748-504">您可以应用粗体文本和超链接等格式。</span><span class="sxs-lookup"><span data-stu-id="a9748-504">You can apply formatting such as bold text and hyperlinks.</span></span> <span data-ttu-id="a9748-505">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-505">This is required field.</span></span>

- <span data-ttu-id="a9748-506">**维度-操作目的**：这是可选字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-506">**dimension-Action Purpose**: This is an optional field.</span></span> <span data-ttu-id="a9748-507">如果包含，则标头必须包含 "dimension-" 前缀。</span><span class="sxs-lookup"><span data-stu-id="a9748-507">If you include it, the header must include the "dimension-" prefix.</span></span> <span data-ttu-id="a9748-508">此处包含的任何维度将用作[符合性分数中的筛选器](compliance-score-setup.md#filtering-your-dashboard-view)，并显示在[合规性分数的 "改进操作详细信息" 页](working-with-compliance-score.md#view-your-improvement-actions)上。</span><span class="sxs-lookup"><span data-stu-id="a9748-508">Any dimensions you include here will be used as [filters in Compliance Score](compliance-score-setup.md#filtering-your-dashboard-view) and appear on the [improvement actions details page in Compliance Score](working-with-compliance-score.md#view-your-improvement-actions).</span></span>

##### <a name="dimensions-tab"></a><span data-ttu-id="a9748-509">维度选项卡</span><span class="sxs-lookup"><span data-stu-id="a9748-509">Dimensions tab</span></span>

<span data-ttu-id="a9748-510">"**维度**" 选项卡是可选的。</span><span class="sxs-lookup"><span data-stu-id="a9748-510">The **Dimensions** tab is optional.</span></span> <span data-ttu-id="a9748-511">但是，如果在其他位置引用维度，并且在您已创建的模板中或在 Microsoft 模板中不存在该维度，则需要在此处指定它。</span><span class="sxs-lookup"><span data-stu-id="a9748-511">However, if you reference a dimension elsewhere, you need to specify it here if it does not exist in a template you've already created or in a Microsoft template.</span></span> <span data-ttu-id="a9748-512">下面列出了此选项卡的列：</span><span class="sxs-lookup"><span data-stu-id="a9748-512">The columns for this tab are listed below:</span></span>

- <span data-ttu-id="a9748-513">**dimensionKey**： list as "product"、"认证"、"操作目的"</span><span class="sxs-lookup"><span data-stu-id="a9748-513">**dimensionKey**: list as "product", "certifications," "action purpose"</span></span>
- <span data-ttu-id="a9748-514">**dimensionValue**：示例： Office 365、HIPPA、预防性、侦探</span><span class="sxs-lookup"><span data-stu-id="a9748-514">**dimensionValue**: examples: Office 365, HIPPA, Preventative, Detective</span></span>

<span data-ttu-id="a9748-515">您可以通过转到 "**租户管理**" 并选择 "**维度**" 选项卡来查看现有维度。此外，无论何时导出现有模板，导出的电子表格都将具有 "**尺寸**" 选项卡，其中列出了模板中使用的所有尺寸。</span><span class="sxs-lookup"><span data-stu-id="a9748-515">You can view your existing dimensions by going to **Tenant Management** and selecting the **Dimensions** tab. Also, anytime you export an existing template, the exported spreadsheet will have the **Dimensions** tab, which lists all the dimensions used in the template.</span></span>

### <a name="modify-an-existing-template"></a><span data-ttu-id="a9748-516">修改现有模板</span><span class="sxs-lookup"><span data-stu-id="a9748-516">Modify an existing Template</span></span>

<span data-ttu-id="a9748-517">若要使用上面所述的导入过程对创建或自定义的模板进行更改，请使用相同的过程将这些更改导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="a9748-517">To make changes to a Template you created or customized using the import process outlined above, you use the same process to import those changes into your Template.</span></span>

> [!NOTE]
> <span data-ttu-id="a9748-518">编辑模板组件时，有几个重要的因素需要注意，因此请仔细查看此部分。</span><span class="sxs-lookup"><span data-stu-id="a9748-518">There are several important factors to be aware of as you edit template components, so please review this section carefully.</span></span>

#### <a name="general-process-for-modifying-a-template"></a><span data-ttu-id="a9748-519">修改模板的常规过程</span><span class="sxs-lookup"><span data-stu-id="a9748-519">General process for modifying a Template</span></span>

<span data-ttu-id="a9748-520">若要对组织的现有模板之一进行更改，常规过程如下：</span><span class="sxs-lookup"><span data-stu-id="a9748-520">To make changes to one of your organization's existing templates, the general process is:</span></span>

1. <span data-ttu-id="a9748-521">从 "**模板**" 仪表板中，选择要修改的模板，该模板将调出显示 "**模板**" 选项卡的 "**控件信息**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="a9748-521">From your **Templates** dashboard, select the Template you want to modify, which brings up your **Controls Info** dashboard showing your **Template** tab.</span></span>
2. <span data-ttu-id="a9748-522">从此处选择 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="a9748-522">From here, select **Export**.</span></span> <span data-ttu-id="a9748-523">将下载包含所有模板数据的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="a9748-523">An Excel sheet with all your template data will download.</span></span>
3. <span data-ttu-id="a9748-524">若要编辑、添加或删除操作，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="a9748-524">To edit, add, or remove an action, see the sections below.</span></span>
4. <span data-ttu-id="a9748-525">完成对 Excel 文件所做的更改后，通过从仪表板中选择模板并选择 "**导入**"，将文件导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="a9748-525">When you're done making changes to your Excel file, import the file back into the template by selecting the template from your dashboard and selecting **Import**.</span></span> <span data-ttu-id="a9748-526">您的模板现在将包含所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a9748-526">Your template will now include the changes you made.</span></span>

#### <a name="to-edit-template-attributes"></a><span data-ttu-id="a9748-527">编辑模板属性</span><span class="sxs-lookup"><span data-stu-id="a9748-527">To edit Template attributes</span></span>

<span data-ttu-id="a9748-528">在 "**模板**" 选项卡上，您可以编辑 "**标题**" 列、" **inScopeServices** " 列以及您可能已添加的任何其他列中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="a9748-528">On the **Templates** tab, you can edit anything in the **title** column, the **inScopeServices** column, and in any other column you may have added.</span></span> <span data-ttu-id="a9748-529">但是，不能编辑 "**产品**" 或 "**认证**" 列中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="a9748-529">However, you can't edit anything in the **product** or **certification** columns.</span></span>

#### <a name="to-add-an-action-to-a-template"></a><span data-ttu-id="a9748-530">向模板添加操作</span><span class="sxs-lookup"><span data-stu-id="a9748-530">To add an action to a Template</span></span>

1. <span data-ttu-id="a9748-531">转到 "**操作**" 选项卡，并将您的信息添加到现有操作下方的第一个空行中的必填字段中。</span><span class="sxs-lookup"><span data-stu-id="a9748-531">Go to the **Actions** tab and add your information in the required fields in the first empty row underneath your existing actions.</span></span>
2. <span data-ttu-id="a9748-532">转到 " **ControlFamily** " 选项卡。查找包含操作所映射到的控件的行。</span><span class="sxs-lookup"><span data-stu-id="a9748-532">Go to your **ControlFamily** tab. Find the row containing the control your action maps to.</span></span> <span data-ttu-id="a9748-533">将您的新操作添加到该行中的 " **controlActionTitle** " 列（请记住，使用两个分号分隔此字段中的多个操作，中间没有空格）。</span><span class="sxs-lookup"><span data-stu-id="a9748-533">Add your new action to the **controlActionTitle** column in that row (remember to separate multiple actions in this field with two semi-colons, no space in between).</span></span>
3. <span data-ttu-id="a9748-534">将电子表格保存到本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="a9748-534">Save your spreadsheet to your local machine.</span></span>

#### <a name="to-edit-an-actions-information"></a><span data-ttu-id="a9748-535">编辑操作的信息</span><span class="sxs-lookup"><span data-stu-id="a9748-535">To edit an action's information</span></span>

<span data-ttu-id="a9748-536">您可以更改*除标题之外*的任何操作的信息。</span><span class="sxs-lookup"><span data-stu-id="a9748-536">You can change any action's information *except for its title*.</span></span> <span data-ttu-id="a9748-537">您可以编辑从 B 之前的列中的任何单元格，并将该文件重新导入到模板中时，该模板中的操作现在将包含更新后的数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-537">You can edit any cell from columns B onward, and when you import the file back into the template, the actions in that template will now contain the updated data.</span></span>

<span data-ttu-id="a9748-538">您无法编辑**actionTitle** （column A），因为如果您这样做，合规性管理器会将其视为一个新操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-538">You cannot edit the **actionTitle** (column A) because if you do, Compliance Manager considers this to be a new action.</span></span> <span data-ttu-id="a9748-539">如果要更改操作的名称，请参阅以下直接说明。</span><span class="sxs-lookup"><span data-stu-id="a9748-539">If you want to change an action's name, see the instructions immediately below.</span></span>

#### <a name="to-change-the-name-of-an-action"></a><span data-ttu-id="a9748-540">更改操作的名称</span><span class="sxs-lookup"><span data-stu-id="a9748-540">To change the name of an action</span></span>

<span data-ttu-id="a9748-541">如果要更改操作的名称，则必须在电子表格中显式指定要将现有名称替换为新名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-541">If you want to change the name of an action, you have to explicitly designate in the spreadsheet that you are replacing an existing name with a new name.</span></span> <span data-ttu-id="a9748-542">若要更改操作的名称，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a9748-542">To change an action's name, follow these steps:</span></span>

1. <span data-ttu-id="a9748-543">在电子表格的 "**操作**" 选项卡中，将一个新列添加到 a 列之后的电子表格中。</span><span class="sxs-lookup"><span data-stu-id="a9748-543">In the **Actions** tab of your spreadsheet, add a new column to the spreadsheet after column A.</span></span>
2. <span data-ttu-id="a9748-544">在此新列（现在是列 B）中，将其标头放在第1行： **oldActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="a9748-544">In this new column, which is now column B, put as its header in row 1: **oldActionTitle**.</span></span>
3. <span data-ttu-id="a9748-545">复制 A 列的内容并将其粘贴到 B 列中。这会将现有操作标题（即要更改的内容）放入 B 列中。</span><span class="sxs-lookup"><span data-stu-id="a9748-545">Copy the contents of column A and paste them into column B. This puts your existing action titles, which are what you want to change, into column B.</span></span>
4. <span data-ttu-id="a9748-546">在**actionTitle**列中，删除旧名称，并将其替换为您的操作的新名称。</span><span class="sxs-lookup"><span data-stu-id="a9748-546">In column A, **actionTitle**, delete the old name and replace it with the new name for your action.</span></span>

#### <a name="to-remove-an-action-from-a-template"></a><span data-ttu-id="a9748-547">从模板中删除操作</span><span class="sxs-lookup"><span data-stu-id="a9748-547">To remove an action from a Template</span></span>

<span data-ttu-id="a9748-548">从电子表格的某一行中删除操作**并不会**删除正在编辑的模板中的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-548">Deleting an action from a row in a spreadsheet **does not** remove the action from the template you're editing.</span></span> <span data-ttu-id="a9748-549">相反，请按照下面的过程操作，删除操作：</span><span class="sxs-lookup"><span data-stu-id="a9748-549">Instead, follow the process below to remove an action:</span></span>

1. <span data-ttu-id="a9748-550">在 "**操作**" 选项卡上，插入一个新列作为列 a，并在标题行中放置**操作**，该行号为1。</span><span class="sxs-lookup"><span data-stu-id="a9748-550">On the **Actions** tab, insert a new column as column A and put **Operation** in the header row, which is row number one.</span></span>
2. <span data-ttu-id="a9748-551">在要删除的操作所在的行上，将**Delete**放入该行的 A 列中。</span><span class="sxs-lookup"><span data-stu-id="a9748-551">On the row for the action you want to remove, put **Delete** in column A for that row.</span></span>
3. <span data-ttu-id="a9748-552">确保控件不会再引用此操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-552">Ensure that this action is no longer referenced by a control.</span></span> <span data-ttu-id="a9748-553">转到 " **ControlFamily** " 选项卡，在第 F 列中查找您的操作的标题，即**controlActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="a9748-553">Go to the **ControlFamily** tab and look for your action's title in column F, which is **controlActionTitle**.</span></span>
4. <span data-ttu-id="a9748-554">当您找到 " **controlActionTitle** " 列中列出的操作时，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="a9748-554">When you find your action listed in the **controlActionTitle** column, delete it.</span></span>
5. <span data-ttu-id="a9748-555">将电子表格保存到本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="a9748-555">Save your spreadsheet to your local machine.</span></span>

<span data-ttu-id="a9748-556">将电子表格导入回模板时，将从模板中删除您的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-556">When you import your spreadsheet back into the template, your action will be removed from the template.</span></span> <span data-ttu-id="a9748-557">从模板中移除操作并不会完全删除该操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-557">Removing an action from a template does not completely remove the action.</span></span> <span data-ttu-id="a9748-558">另一个模板仍可引用该操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-558">That action can still be referenced by another template.</span></span>

<span data-ttu-id="a9748-559">如果要删除控件引用的最后一个操作，则需要删除该控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-559">If you are removing the last action that a control references, then you need to remove the control.</span></span>

> [!NOTE]
> <span data-ttu-id="a9748-560">若要删除控件，请执行以下操作：按照上述步骤删除操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-560">To remove a control: Follow the same process for removing an action as outlined above.</span></span> <span data-ttu-id="a9748-561">在 " **ControlFamily** " 选项卡中，添加 "**操作**" 列并将 "**删除**" 放在要删除的控件旁边。</span><span class="sxs-lookup"><span data-stu-id="a9748-561">In the **ControlFamily** tab, add an **Operation** column and put **Delete** next to the control you want to remove.</span></span>

### <a name="updates-to-templates"></a><span data-ttu-id="a9748-562">模板的更新</span><span class="sxs-lookup"><span data-stu-id="a9748-562">Updates to Templates</span></span>

<span data-ttu-id="a9748-563">每次通过版本控制过程更新评估时，您的自定义评估将继承这些更新并保留您的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="a9748-563">Each time an Assessment is updated through the versioning process, your customized Assessment will inherit those updates and keep your custom controls.</span></span> <span data-ttu-id="a9748-564">[有关评估更新，请参阅版本控制警报](#versioning-alerts-for-assessment-updates)。</span><span class="sxs-lookup"><span data-stu-id="a9748-564">See [Versioning alerts for Assessment updates](#versioning-alerts-for-assessment-updates).</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="a9748-565">将模板导出到 JSON</span><span class="sxs-lookup"><span data-stu-id="a9748-565">Export a Template to JSON</span></span>

<span data-ttu-id="a9748-566">合规性管理器（预览版）支持将模板导出为 JavaScript 对象表示法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="a9748-566">Compliance Manager (Preview) supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="a9748-567">这使您可以与支持 JSON 的其他系统交换合规性管理器数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-567">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="a9748-568">报告</span><span class="sxs-lookup"><span data-stu-id="a9748-568">Reports</span></span>

<span data-ttu-id="a9748-569">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="a9748-569">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="a9748-570">报告是在导出的日期和时间进行评估的快照。</span><span class="sxs-lookup"><span data-stu-id="a9748-570">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="a9748-571">该报告包含 Microsoft 和客户托管的控件的详细信息，用于评估、控制实施状态、控制测试日期、测试结果以及指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="a9748-571">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="a9748-572">由于隐藏的评估不会保留指向已上载文档的链接，因此应先导出该评估，然后再将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="a9748-572">Because hidden Assessments don't retain links to uploaded documents, you should export the Assessment before you hide it.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="a9748-573">导出评估</span><span class="sxs-lookup"><span data-stu-id="a9748-573">Export an Assessment</span></span>

1. <span data-ttu-id="a9748-574">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9748-574">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="a9748-575">在下拉菜单中选择要导出的评估的组和评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-575">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="a9748-576">选择 "导出"。</span><span class="sxs-lookup"><span data-stu-id="a9748-576">Select Export.</span></span> <span data-ttu-id="a9748-577">将评估导出作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="a9748-577">The Assessment export is downloaded as an Excel file.</span></span>

<span data-ttu-id="a9748-578">![合规性管理器评估 Excel 报告](../media/compliance-manager-assessment-report.png "合规性管理器评估 Excel 报告")</span><span class="sxs-lookup"><span data-stu-id="a9748-578">![Compliance Manager Assessment Excel Report](../media/compliance-manager-assessment-report.png "Compliance Manager assessment Excel report")</span></span>

## <a name="permissions"></a><span data-ttu-id="a9748-579">权限</span><span class="sxs-lookup"><span data-stu-id="a9748-579">Permissions</span></span>

<span data-ttu-id="a9748-580">下表介绍了每个合规性管理器权限及其允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a9748-580">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="a9748-581">该表还指示分配了每个权限的角色。</span><span class="sxs-lookup"><span data-stu-id="a9748-581">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="a9748-582">**Azure AD 全局读取器**</span><span class="sxs-lookup"><span data-stu-id="a9748-582">**Azure AD Global Reader**</span></span>|<span data-ttu-id="a9748-583">**合规性管理器读者**</span><span class="sxs-lookup"><span data-stu-id="a9748-583">**Compliance Manager Reader**</span></span>|<span data-ttu-id="a9748-584">**合规性管理器参与者**</span><span class="sxs-lookup"><span data-stu-id="a9748-584">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="a9748-585">**合规性管理器评估员**</span><span class="sxs-lookup"><span data-stu-id="a9748-585">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="a9748-586">**合规性管理器管理员**</span><span class="sxs-lookup"><span data-stu-id="a9748-586">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="a9748-587">**门户管理员**</span><span class="sxs-lookup"><span data-stu-id="a9748-587">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9748-588">**读取数据：** 用户可以读取但不能编辑数据（模板数据和租户管理除外）。</span><span class="sxs-lookup"><span data-stu-id="a9748-588">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="a9748-589">X</span><span class="sxs-lookup"><span data-stu-id="a9748-589">X</span></span> | <span data-ttu-id="a9748-590">X</span><span class="sxs-lookup"><span data-stu-id="a9748-590">X</span></span> | <span data-ttu-id="a9748-591">X</span><span class="sxs-lookup"><span data-stu-id="a9748-591">X</span></span> | <span data-ttu-id="a9748-592">X</span><span class="sxs-lookup"><span data-stu-id="a9748-592">X</span></span> | <span data-ttu-id="a9748-593">X</span><span class="sxs-lookup"><span data-stu-id="a9748-593">X</span></span>  | <span data-ttu-id="a9748-594">X</span><span class="sxs-lookup"><span data-stu-id="a9748-594">X</span></span> |
|<span data-ttu-id="a9748-595">**编辑数据：** 除了 "测试结果" 和 "测试日期" 字段（"模板数据" 和 "租户管理" 除外）之外，用户可以编辑所有字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-595">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="a9748-596">X</span><span class="sxs-lookup"><span data-stu-id="a9748-596">X</span></span> | <span data-ttu-id="a9748-597">X</span><span class="sxs-lookup"><span data-stu-id="a9748-597">X</span></span>  | <span data-ttu-id="a9748-598">X</span><span class="sxs-lookup"><span data-stu-id="a9748-598">X</span></span> | <span data-ttu-id="a9748-599">X</span><span class="sxs-lookup"><span data-stu-id="a9748-599">X</span></span> |
|<span data-ttu-id="a9748-600">**编辑测试结果：** 用户可以编辑 "测试结果" 和 "测试日期" 字段。</span><span class="sxs-lookup"><span data-stu-id="a9748-600">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="a9748-601">X</span><span class="sxs-lookup"><span data-stu-id="a9748-601">X</span></span> | <span data-ttu-id="a9748-602">X</span><span class="sxs-lookup"><span data-stu-id="a9748-602">X</span></span> | <span data-ttu-id="a9748-603">X</span><span class="sxs-lookup"><span data-stu-id="a9748-603">X</span></span> |
|<span data-ttu-id="a9748-604">**管理评估：** 用户可以创建、存档和删除评估。</span><span class="sxs-lookup"><span data-stu-id="a9748-604">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="a9748-605">X</span><span class="sxs-lookup"><span data-stu-id="a9748-605">X</span></span> | <span data-ttu-id="a9748-606">X</span><span class="sxs-lookup"><span data-stu-id="a9748-606">X</span></span> |
|<span data-ttu-id="a9748-607">**管理主数据：** 用户可以查看、编辑和删除模板数据和租户管理数据。</span><span class="sxs-lookup"><span data-stu-id="a9748-607">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="a9748-608">X</span><span class="sxs-lookup"><span data-stu-id="a9748-608">X</span></span> | <span data-ttu-id="a9748-609">X</span><span class="sxs-lookup"><span data-stu-id="a9748-609">X</span></span> |
|<span data-ttu-id="a9748-610">**管理用户：** 用户可以将组织中的其他用户添加到 Reader、投稿人、评估员和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a9748-610">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="a9748-611">只有组织中具有全局管理员角色的用户才可以在门户管理员角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="a9748-611">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="a9748-612">X</span><span class="sxs-lookup"><span data-stu-id="a9748-612">X</span></span> |