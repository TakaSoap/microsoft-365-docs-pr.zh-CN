---
title: 使用 Microsoft 合规性管理器（预览）
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
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使您能够跟踪、分配和验证与 Microsoft 产品相关的法规遵从性活动。
ms.openlocfilehash: 2bc7ccc4c6c236c0c730ac3fc651701d9a76bedf
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2020
ms.locfileid: "41022008"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="bcef3-104">使用 Microsoft 合规性管理器（预览）</span><span class="sxs-lookup"><span data-stu-id="bcef3-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcef3-105">Microsoft 合规性管理器是一个仪表板和管理工具，提供了有关数据保护和合规性的摘要 stature 以及改进数据保护和合规性的建议。</span><span class="sxs-lookup"><span data-stu-id="bcef3-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="bcef3-106">合规性管理器中提供的客户操作是建议;在实现之前，你的组织可以评估这些建议在其各自的法规环境中的有效性。</span><span class="sxs-lookup"><span data-stu-id="bcef3-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="bcef3-107">在合规性管理器中找到的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="bcef3-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="bcef3-108">Access 合规性管理器</span><span class="sxs-lookup"><span data-stu-id="bcef3-108">Access Compliance Manager</span></span>

<span data-ttu-id="bcef3-p103">合规性管理器是从服务信任门户进行访问。任何拥有 Microsoft 帐户或 Azure Active Directory 组织帐户的人，都可以访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="bcef3-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="bcef3-111">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="bcef3-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="bcef3-112">使用 Microsoft 服务帐户（即 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）用户帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="bcef3-112">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="bcef3-113">在服务信任门户中，我们建议选择**合规性管理器**，它是具有最新功能的预览版本。</span><span class="sxs-lookup"><span data-stu-id="bcef3-113">In the Service Trust Portal, we recommend selecting **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="bcef3-114">**合规性管理器（经典）** 将转到早期版本的合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="bcef3-114">**Compliance Manager (Classic)** takes you to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="bcef3-115">在显示非公开协议时，请阅读并选择 "**同意**"，然后显示合规性管理器仪表板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-115">When the Non-Disclosure Agreement is displayed, read it and select **Agree**, which then displays your Compliance Manager dashboard.</span></span>

<span data-ttu-id="bcef3-116">为实现入门，默认情况下，Office 365 的 ISO/IEC 27001:2103 评估会显示在您的组织中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-116">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="bcef3-117">管理</span><span class="sxs-lookup"><span data-stu-id="bcef3-117">Administration</span></span>

<span data-ttu-id="bcef3-118">只有全局管理员可以使用特定的管理功能，并且只有在使用全局管理员帐户登录时才可见。</span><span class="sxs-lookup"><span data-stu-id="bcef3-118">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="bcef3-119">全局管理员可以分配用户权限，并且可以为所有操作启用自动安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="bcef3-119">The global administrator can assign user permissions, and can turn on automatic Secure Score updates for all actions.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="bcef3-120">向用户分配合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="bcef3-120">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="bcef3-121">一旦管理员将合规性管理器角色分配给其他用户，这些用户就可以在合规性管理器中查看数据，并执行角色所确定的操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-121">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="bcef3-122">管理员还可以通过向用户分配[Azure Active Directory （AZURE AD）中的全局读取器角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)，授予对合规性管理器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="bcef3-122">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="bcef3-123">每个合规性管理器角色都具有略有不同的权限。</span><span class="sxs-lookup"><span data-stu-id="bcef3-123">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="bcef3-124">您可以查看分配给每个角色的权限，查看哪些用户是哪些角色，以及通过服务信任门户在该角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-124">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="bcef3-125">选择 "**管理**" 菜单项，然后选择 "要查看的**设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-125">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理菜单：选择的设置](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="bcef3-127">若要在合规性管理器角色中添加或删除用户，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-127">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="bcef3-128">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bcef3-128">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="bcef3-129">使用 Azure Active Directory 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bcef3-129">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="bcef3-130">在 "服务信任门户" 顶部菜单栏上，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-130">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="bcef3-131">在 "**选择角色**" 下拉列表中，选择要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="bcef3-131">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="bcef3-132">“**选择角色**”页上会列出已添加到每个角色的用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-132">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="bcef3-133">若要将用户添加到此角色，请选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-133">To add users to this role, select **Add**.</span></span> <span data-ttu-id="bcef3-134">在 "**添加用户**" 对话框中，选择 "用户" 字段。</span><span class="sxs-lookup"><span data-stu-id="bcef3-134">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="bcef3-135">您可以在可用用户列表中滚动，也可以开始键入用户名，以根据您的搜索词筛选列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-135">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="bcef3-136">选择要将该帐户添加到使用该角色预配的 "**添加用户**" 列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-136">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="bcef3-137">如果要同时添加多个用户，请开始键入用户名以筛选列表，然后选择要添加到列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-137">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="bcef3-138">选择 "**保存**" 将所选角色设置给这些用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-138">Select **Save** to provision the selected role to these users.</span></span> 

    ![合规性管理器-添加用户](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="bcef3-140">若要从此角色中删除用户，请选择 "用户"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-140">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合规性管理器-删除用户](media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="bcef3-142">控制自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="bcef3-142">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="bcef3-143">可以为所有操作自动启用安全分数更新，可以为所有操作关闭这些更新，也可以通过单个操作进行设置。</span><span class="sxs-lookup"><span data-stu-id="bcef3-143">Secure Score updates can be turned on automatically for all actions, can be turned off for all actions, or can be set by individual action.</span></span>

1. <span data-ttu-id="bcef3-144">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bcef3-144">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="bcef3-145">在 "服务信任门户" 顶部菜单栏上，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-145">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="bcef3-146">在 "**安全分数**" 选项卡中，选择所选设置对应的相应按钮。</span><span class="sxs-lookup"><span data-stu-id="bcef3-146">In the **Secure Score** tab, select the appropriate button for your chosen setting.</span></span>

<span data-ttu-id="bcef3-147">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="bcef3-147">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="bcef3-148">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-148">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="bcef3-149">组</span><span class="sxs-lookup"><span data-stu-id="bcef3-149">Groups</span></span>

<span data-ttu-id="bcef3-150">组是允许您组织评估的容器，并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。</span><span class="sxs-lookup"><span data-stu-id="bcef3-150">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="bcef3-151">您可以按符合您的方式对评估进行分组，如按年、标准、服务或组织的团队、部门或地理位置。</span><span class="sxs-lookup"><span data-stu-id="bcef3-151">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="bcef3-152">以下是两个组及其基础评估的示例：</span><span class="sxs-lookup"><span data-stu-id="bcef3-152">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="bcef3-153">**FFIEC 是评估2020**</span><span class="sxs-lookup"><span data-stu-id="bcef3-153">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="bcef3-154">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="bcef3-154">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="bcef3-155">Intune + FFIEC 为</span><span class="sxs-lookup"><span data-stu-id="bcef3-155">Intune + FFIEC IS</span></span>
- <span data-ttu-id="bcef3-156">**“数据安全和隐私”评估**</span><span class="sxs-lookup"><span data-stu-id="bcef3-156">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="bcef3-157">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="bcef3-157">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="bcef3-158">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="bcef3-158">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="bcef3-159">我们建议您在添加新评估*之前*为您的组织确定一个分组策略。</span><span class="sxs-lookup"><span data-stu-id="bcef3-159">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span> <span data-ttu-id="bcef3-160">默认情况下，在初始评估中可使用名为 "默认组" 的组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-160">By default, a group named "Default Group" is available for your initial Assessments.</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="bcef3-161">如何创建组</span><span class="sxs-lookup"><span data-stu-id="bcef3-161">How to create a group</span></span>

<span data-ttu-id="bcef3-162">不能将组创建为独立实体。</span><span class="sxs-lookup"><span data-stu-id="bcef3-162">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="bcef3-163">一个组必须始终包含至少一个评估，因此，若要创建一个组，必须首先创建一个评估以放置在该组中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-163">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span> <span data-ttu-id="bcef3-164">按照以下步骤创建组：</span><span class="sxs-lookup"><span data-stu-id="bcef3-164">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="bcef3-165">通过在仪表板顶部附近选择 " **+ 添加评估**" 来创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-165">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="bcef3-166">从 "**评估**" 弹出窗口中，输入评估的标题，然后从下拉菜单中选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-166">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="bcef3-167">在 "**请选择一个组或添加新组**" 中，选择 "**添加新组**"，然后在下面的字段中输入您的组名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-167">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="bcef3-168">若要从现有组中复制信息，请切换**是否要从现有组中复制数据？** 切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="bcef3-168">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="bcef3-169">从下面的下拉菜单中选择要复制的组，并选中要在新组中将其传输到新评估中的任何字段的复选框。</span><span class="sxs-lookup"><span data-stu-id="bcef3-169">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="bcef3-170">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bcef3-170">Select **Save**.</span></span> <span data-ttu-id="bcef3-171">完成后，浮出控件窗格将关闭，新组会自动显示在仪表板上。</span><span class="sxs-lookup"><span data-stu-id="bcef3-171">When completed, the flyout pane closes and your new group automatically displays on your dashboard.</span></span>

<span data-ttu-id="bcef3-172">使用组时需要了解的内容：</span><span class="sxs-lookup"><span data-stu-id="bcef3-172">What to know when working with groups:</span></span>
  
- <span data-ttu-id="bcef3-173">组名（也称为*组 id*）在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bcef3-173">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="bcef3-174">组没有任何安全属性。</span><span class="sxs-lookup"><span data-stu-id="bcef3-174">Groups do not have any security properties.</span></span> <span data-ttu-id="bcef3-175">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="bcef3-175">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="bcef3-176">将评估添加到组后，不能更改分组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-176">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="bcef3-177">您可以重命名评估组，这将更改与该组关联的所有评估的评估分组的名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-177">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="bcef3-178">在同一组中的不同评估中的相关评估控件在完成后将自动更新。</span><span class="sxs-lookup"><span data-stu-id="bcef3-178">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="bcef3-179">如果将新评估添加到现有组中，则会将该组中评估的常见信息复制到新评估中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-179">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="bcef3-180">组可以包含对同一认证或法规的评估，但每个组只能包含针对特定产品认证对的一个评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-180">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="bcef3-181">例如，组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-181">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="bcef3-182">仅当一个组与同一个产品的对应证书或法规不同时，该组才可以包含对同一产品的多个评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-182">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="bcef3-183">隐藏评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="bcef3-183">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="bcef3-184">其他相关评估的任何进一步更新不再在隐藏评估中反映出来。</span><span class="sxs-lookup"><span data-stu-id="bcef3-184">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="bcef3-185">（[了解如何隐藏评估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="bcef3-185">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="bcef3-186">无法删除组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-186">Groups cannot be deleted.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="bcef3-187">租户管理</span><span class="sxs-lookup"><span data-stu-id="bcef3-187">Tenant Management</span></span>

<span data-ttu-id="bcef3-188">合规性管理器（预览版）包括用于管理名为**租户管理**的新数据元素的新接口。</span><span class="sxs-lookup"><span data-stu-id="bcef3-188">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="bcef3-189">此接口使您能够管理租户范围内的设置：</span><span class="sxs-lookup"><span data-stu-id="bcef3-189">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="bcef3-190">**维：** 查看可用于为筛选器创建自定义透视的模板、评估和操作项的元数据。</span><span class="sxs-lookup"><span data-stu-id="bcef3-190">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="bcef3-191">**所有者：** 为每个即席项目指定一个所有者。</span><span class="sxs-lookup"><span data-stu-id="bcef3-191">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="bcef3-192">**客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并为与安全得分集成的操作启用/禁用安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="bcef3-192">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="bcef3-193">选择 "**租户管理**" 以打开管理界面，并使用以下步骤来管理**维度**、**所有者**和**客户操作**。</span><span class="sxs-lookup"><span data-stu-id="bcef3-193">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="bcef3-194">Dimensions</span><span class="sxs-lookup"><span data-stu-id="bcef3-194">Dimensions</span></span>

<span data-ttu-id="bcef3-195">维度是提供有关模板、评估或措施项的信息的元数据的集合。</span><span class="sxs-lookup"><span data-stu-id="bcef3-195">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="bcef3-196">维度使用键和值的概念，其中维度键表示属性，维度值表示属性的有效值。</span><span class="sxs-lookup"><span data-stu-id="bcef3-196">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="bcef3-197">例如，在合规性管理器中有三种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-197">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="bcef3-198">它们由**操作类型**的维度键和**文档**、**运营**和**技术**的维度值定义。</span><span class="sxs-lookup"><span data-stu-id="bcef3-198">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="bcef3-199">您可以编辑或删除现有维度。</span><span class="sxs-lookup"><span data-stu-id="bcef3-199">You can edit or delete existing Dimensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcef3-200">您可以添加新的维度，也可以将其分配给已导入的模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-200">You can add new dimensions, and they can be assigned to Templates that you have already imported.</span></span> <span data-ttu-id="bcef3-201">您还可以将新的维度添加到任何新创建的模板中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-201">You can also add new dimensions to any new Templates you create.</span></span>

### <a name="owners"></a><span data-ttu-id="bcef3-202">所有者</span><span class="sxs-lookup"><span data-stu-id="bcef3-202">Owners</span></span>

<span data-ttu-id="bcef3-203">所有者用于标识每个控件的负责方。</span><span class="sxs-lookup"><span data-stu-id="bcef3-203">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="bcef3-204">所有内置控件由 Microsoft、客户或这两者拥有。</span><span class="sxs-lookup"><span data-stu-id="bcef3-204">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="bcef3-205">您可以创建可用于在组织中指定更精确的职责的所有者的自定义值。</span><span class="sxs-lookup"><span data-stu-id="bcef3-205">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="bcef3-206">例如，可以创建代表组织中的特定组、团队或业务单位的所有者。</span><span class="sxs-lookup"><span data-stu-id="bcef3-206">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="bcef3-207">添加所有者</span><span class="sxs-lookup"><span data-stu-id="bcef3-207">Add an Owner</span></span>

1. <span data-ttu-id="bcef3-208">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-208">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bcef3-209">选择 " **+ 添加所有者**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-209">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="bcef3-210">提供所有者的名称和说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-210">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="bcef3-211">说明显示在 "所有者" 列中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-211">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="bcef3-212">编辑所有者</span><span class="sxs-lookup"><span data-stu-id="bcef3-212">Edit an Owner</span></span>

<span data-ttu-id="bcef3-213">您不能编辑所有者名称，但可以修改 "Owner" 列中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="bcef3-213">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="bcef3-214">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-214">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bcef3-215">找到要编辑的所有者，选择其旁边的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-215">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="bcef3-216">根据需要修改说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-216">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="bcef3-217">删除所有者</span><span class="sxs-lookup"><span data-stu-id="bcef3-217">Delete an Owner</span></span>

1. <span data-ttu-id="bcef3-218">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-218">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="bcef3-219">找到要删除的所有者，选择其旁边的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-219">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="bcef3-220">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-220">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="bcef3-221">客户操作</span><span class="sxs-lookup"><span data-stu-id="bcef3-221">Customer Actions</span></span>

<span data-ttu-id="bcef3-222">"客户操作" 区域显示合规性管理器中所有模板和评估的所有客户操作（预览）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-222">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="bcef3-223">![合规性管理器-添加用户](media/compliance-manager-customer-actions.png "合规性管理器客户操作")</span><span class="sxs-lookup"><span data-stu-id="bcef3-223">![Compliance Manager — add users](media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="bcef3-224">您可以一目了然地看到操作的标题、所有者、类别、强制和分数，并确定它是否与安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="bcef3-224">At a glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="bcef3-225">您可以展开操作并选择 "**读取更多**"，以读取操作说明并访问说明中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-225">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="bcef3-226">您还可以使用此接口基于每个操作启用和禁用安全得分集成，并添加自定义操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-226">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="bcef3-227">具有安全得分集成功能的操作旁边有一个省略号（...）（请注意，自定义操作旁边还有一个省略号）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-227">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="bcef3-228">启用或禁用安全分数集成</span><span class="sxs-lookup"><span data-stu-id="bcef3-228">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="bcef3-229">选择要修改的操作的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-229">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="bcef3-230">切换交换机以确保安全分数连续更新为 "开" 或 "关"，以通过安全分数启用或禁用连续监控。</span><span class="sxs-lookup"><span data-stu-id="bcef3-230">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="bcef3-231">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bcef3-231">Select **Save**.</span></span>

<span data-ttu-id="bcef3-232">当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-232">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="bcef3-233">在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。</span><span class="sxs-lookup"><span data-stu-id="bcef3-233">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="bcef3-234">在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。</span><span class="sxs-lookup"><span data-stu-id="bcef3-234">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="bcef3-235">安全分数集成不支持的任何操作都可以手动实现。</span><span class="sxs-lookup"><span data-stu-id="bcef3-235">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="bcef3-236">手动实现将考虑该操作的组的分数。</span><span class="sxs-lookup"><span data-stu-id="bcef3-236">A manual implementation will factor into the score for that action's group.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="bcef3-237">添加客户操作</span><span class="sxs-lookup"><span data-stu-id="bcef3-237">Add a customer action</span></span>

1. <span data-ttu-id="bcef3-238">选择 " **+ 添加客户操作**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-238">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="bcef3-239">在 "**标题**" 字段中为操作提供唯一的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-239">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="bcef3-240">在 "**最大合规性分数**" 字段中提供操作的合规性分数（可以是1-99 中的任何数字）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-240">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="bcef3-241">使用 "**操作类型**" 下拉列表来指定要添加的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="bcef3-241">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="bcef3-242">如果操作类型不存在，则可以通过将值添加到 "操作类型" 维度键来添加它。</span><span class="sxs-lookup"><span data-stu-id="bcef3-242">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="bcef3-243">使用 "**维度**" 下拉列表可指定或添加操作的维度键和值。</span><span class="sxs-lookup"><span data-stu-id="bcef3-243">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="bcef3-244">使用 "**所有者**" 下拉列表指定操作的所有者。</span><span class="sxs-lookup"><span data-stu-id="bcef3-244">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="bcef3-245">选择**+** 以添加操作的说明和说明标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-245">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="bcef3-246">选择**X**以关闭说明边栏。</span><span class="sxs-lookup"><span data-stu-id="bcef3-246">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="bcef3-247">选择 "**保存**" 以保存客户操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-247">Select **Save** to save the Customer Action.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="bcef3-248">删除客户操作</span><span class="sxs-lookup"><span data-stu-id="bcef3-248">Delete a customer action</span></span>

1. <span data-ttu-id="bcef3-249">选择要修改的操作的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-249">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="bcef3-250">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-250">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="bcef3-251">评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-251">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="bcef3-252">添加评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-252">Add an Assessment</span></span>
  
1. <span data-ttu-id="bcef3-253">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-253">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="bcef3-254">当边栏打开时，请输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="bcef3-254">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="bcef3-255">**标题（必需）：** 输入评估的标题</span><span class="sxs-lookup"><span data-stu-id="bcef3-255">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="bcef3-256">**请选择一个模板（必需）：** 选择标准或自定义模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-256">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="bcef3-257">**请选择组或添加新组（必需）：** 选择现有组或选择添加新组，并提供唯一的组名称</span><span class="sxs-lookup"><span data-stu-id="bcef3-257">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="bcef3-258">**是否要复制现有组中的数据？（可选）：** 切换控件以启用组副本，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bcef3-258">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="bcef3-259">**选择一个组（可选）：** 如果已启用组副本，请选择要复制的组</span><span class="sxs-lookup"><span data-stu-id="bcef3-259">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="bcef3-260">**实现详细信息（可选）：** 选择以将实现详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="bcef3-260">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="bcef3-261">**测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="bcef3-261">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="bcef3-262">**文档（可选）：** 选择以将文档复制到新组</span><span class="sxs-lookup"><span data-stu-id="bcef3-262">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="bcef3-263">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-263">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="bcef3-264">新评估显示在评估仪表板上，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="bcef3-264">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="bcef3-265">评估的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-265">The title of the Assessment.</span></span>
- <span data-ttu-id="bcef3-266">评估的维度，包括认证、环境和应用于评估的产品。</span><span class="sxs-lookup"><span data-stu-id="bcef3-266">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="bcef3-267">创建日期的日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="bcef3-267">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="bcef3-268">评估分数显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="bcef3-268">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="bcef3-269">此分数自动包含来自 Microsoft 托管控件和安全得分的分数。</span><span class="sxs-lookup"><span data-stu-id="bcef3-269">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="bcef3-270">进度指示器，显示已评估的 Microsoft 托管和客户 manged 控件的数量。</span><span class="sxs-lookup"><span data-stu-id="bcef3-270">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="bcef3-271">从现有评估复制信息</span><span class="sxs-lookup"><span data-stu-id="bcef3-271">Copying information from existing Assessments</span></span>

<span data-ttu-id="bcef3-272">创建评估时，可以选择从现有组复制信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-272">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="bcef3-273">这使您可以将输入到复制的评估中的信息应用于新评估中的相同控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-273">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="bcef3-274">例如，如果您的组织中有与 FFIEC 相关的所有评估的组，则可以从现有评估中复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="bcef3-274">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="bcef3-275">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="bcef3-275">Implementation Details</span></span>
- <span data-ttu-id="bcef3-276">测试计划 & 其他信息</span><span class="sxs-lookup"><span data-stu-id="bcef3-276">Test Plan & Additional Information</span></span>
- <span data-ttu-id="bcef3-277">文档</span><span class="sxs-lookup"><span data-stu-id="bcef3-277">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="bcef3-278">将信息从现有评估复制到新评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-278">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="bcef3-279">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-279">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="bcef3-280">在 "**添加评估**" 窗口中，填写以下信息</span><span class="sxs-lookup"><span data-stu-id="bcef3-280">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="bcef3-281">**标题（必需）：** 输入评估的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-281">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="bcef3-282">**请选择一个模板（必需）：** 选择标准或自定义模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-282">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="bcef3-283">**请选择组或添加新组（必需）：** 选择 "**添加新组**" 并提供一个唯一的组名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-283">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="bcef3-284">**是否要复制现有组中的数据？（可选）：** 将控件切换到 "打开" 以启用组副本，然后：-**选择一个组（可选）：** 如果已启用组副本，请从组中选择要复制的组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-284">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="bcef3-285">- **实现详细信息（可选）：** 选择将实现详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-285">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="bcef3-286">- **测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-286">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="bcef3-287">- **文档（可选）：** 选择以将文档复制到新组。</span><span class="sxs-lookup"><span data-stu-id="bcef3-287">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="bcef3-288">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-288">Select **Save** to create the Assessment.</span></span>

### <a name="view-an-assessment"></a><span data-ttu-id="bcef3-289">查看评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-289">View an Assessment</span></span>
  
1. <span data-ttu-id="bcef3-290">在 "评估" 仪表板中，选择要打开的评估名称，并查看 "操作项" 和 "控件信息"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-290">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="bcef3-291">下面的示例展示了 Office 365 和 ISO 27001 的评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-291">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="bcef3-292">第一个视图演示合规性管理器（预览版）中的新操作项视图。</span><span class="sxs-lookup"><span data-stu-id="bcef3-292">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合规性管理器操作项目视图](media/compliance-manager-action-items.png)

<span data-ttu-id="bcef3-294">操作按字母顺序列出，并为每个操作分配一个分数和一个所有者。</span><span class="sxs-lookup"><span data-stu-id="bcef3-294">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="bcef3-295">选择 "**阅读更多**" 链接以阅读每个操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-295">Select  the **Read More** link to read the details of each Action.</span></span> 

![合规性管理器操作项目视图](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="bcef3-297">选择 "**查看**" 链接以管理、分配、实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-297">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="bcef3-298">下面是一个操作示例。</span><span class="sxs-lookup"><span data-stu-id="bcef3-298">Below is an example Action.</span></span>

![合规性管理器操作视图](media/compliance-manager-action.png)

<span data-ttu-id="bcef3-300">在早期版本的合规性管理器中，实现要求的工作流是在控件级别执行的。</span><span class="sxs-lookup"><span data-stu-id="bcef3-300">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="bcef3-301">合规性监察官会将控件分配给某人以实现该控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-301">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="bcef3-302">这有两个缺点：</span><span class="sxs-lookup"><span data-stu-id="bcef3-302">There were two drawbacks to this:</span></span>

- <span data-ttu-id="bcef3-303">控件通常具有与它们相关联的多个操作，并且分配了控件的用户可能不是完成实现该控件所需的所有操作的正确人员</span><span class="sxs-lookup"><span data-stu-id="bcef3-303">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="bcef3-304">将单独的任务组合到单个操作中阻止了用于在合规性管理器（预览版）中自动记录租户配置更改的信号和遥测的收集。</span><span class="sxs-lookup"><span data-stu-id="bcef3-304">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="bcef3-305">在合规性管理器（预览）中，工作流过程已从控制级别移至操作级别。</span><span class="sxs-lookup"><span data-stu-id="bcef3-305">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="bcef3-306">检查操作时，可使用以下字段来管理操作工作流：</span><span class="sxs-lookup"><span data-stu-id="bcef3-306">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="bcef3-307">**为用户分配：** 选择此字段以选择或输入应为其分配此操作的用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-307">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="bcef3-308">您可以在列表中滚动，或键入名称以查找它，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="bcef3-308">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="bcef3-309">**管理文档：** 您可以在 Office 文档、图像文件和屏幕截图、CSV 或 TXT 中的 PowerShell 输出以及 Pdf 中上载实现证据。</span><span class="sxs-lookup"><span data-stu-id="bcef3-309">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="bcef3-310">**实现状态：** 用于指示操作的当前实现状态。</span><span class="sxs-lookup"><span data-stu-id="bcef3-310">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="bcef3-311">可能的值尚未实现、实现、替代实施、规划且不在范围内。</span><span class="sxs-lookup"><span data-stu-id="bcef3-311">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="bcef3-312">**实施日期：** 执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="bcef3-312">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="bcef3-313">**测试结果：** 用于指示实现验证的结果。</span><span class="sxs-lookup"><span data-stu-id="bcef3-313">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="bcef3-314">可能的值未评估、传递、失败-低风险、失败-中等风险、失败-高风险以及不在范围内。</span><span class="sxs-lookup"><span data-stu-id="bcef3-314">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="bcef3-315">**测试日期：** 验证发生的日期。</span><span class="sxs-lookup"><span data-stu-id="bcef3-315">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="bcef3-316">**实现说明：** 输入您的组织的实现详细信息，以及您想要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="bcef3-316">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="bcef3-317">**测试计划：** 输入此操作的测试计划详细信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="bcef3-317">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="bcef3-318">**其他信息：** 输入有关此操作或在组织中实现此操作的方式的任何其他信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="bcef3-318">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="bcef3-319">合规性管理器（预览版）还包括在早期版本中找到的基于控件的数据透视。</span><span class="sxs-lookup"><span data-stu-id="bcef3-319">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="bcef3-320">选择 "**控件信息**" 仪表板以查看它。</span><span class="sxs-lookup"><span data-stu-id="bcef3-320">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="bcef3-321">您可以在评估和模板级别查看控件的信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-321">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="bcef3-322">下面是用于评估的控件信息仪表板的一个示例。</span><span class="sxs-lookup"><span data-stu-id="bcef3-322">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合规性管理器控制信息视图](media/compliance-manager-controls-info.png)

<span data-ttu-id="bcef3-324">对于评估，"控件信息" 仪表板将显示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-324">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="bcef3-325">一个**组**下拉列表，用于选择要查看的组（使用多个组时）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-325">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="bcef3-326">一个**评估**下拉列表，用于选择要查看的评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-326">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="bcef3-327">有关所选评估的元数据，包括：</span><span class="sxs-lookup"><span data-stu-id="bcef3-327">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="bcef3-328">**评估的控制措施**的进度指示器，其中显示了已评估的控制总数的控制次数。</span><span class="sxs-lookup"><span data-stu-id="bcef3-328">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="bcef3-329">评估的当前**合规性分数**，显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="bcef3-329">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="bcef3-330">有关评估中使用的**认证**和**产品**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-330">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="bcef3-331">评估的当前**状态**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="bcef3-331">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="bcef3-332">用于评估的**范围内的服务**的列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-332">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="bcef3-333">控件的详细信息，按控件系列分组，并提供指向客户操作和 Microsoft 实现详细信息的链接：</span><span class="sxs-lookup"><span data-stu-id="bcef3-333">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="bcef3-334">**您的操作**将显示您可以执行以满足部分或全部控件要求的客户操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-334">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="bcef3-335">许多控件具有与之关联的多个操作，并且与控件关联的所有操作都显示在此处。</span><span class="sxs-lookup"><span data-stu-id="bcef3-335">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="bcef3-336">此处的操作与操作仪表板中列出的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="bcef3-336">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="bcef3-337">**Microsoft 操作**显示 microsoft 内部框架中应用于所选证书控制的控件列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-337">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="bcef3-338">对于每个内部控件，选择 "已**实施**" 以查看 Microsoft 的实施和测试详细信息，以及测试结果和测试日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="bcef3-338">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![合规性管理器 Microsoft 操作视图](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="bcef3-340">导出评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-340">Export an Assessment</span></span>

<span data-ttu-id="bcef3-341">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-341">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="bcef3-342">报告是在创建报告的日期和时间的评估的快照。</span><span class="sxs-lookup"><span data-stu-id="bcef3-342">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="bcef3-343">该报告包含有关评估、控制实施状态、控制测试日期、测试结果的所有 Microsoft 和客户托管控件的详细信息，并提供了指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-343">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="bcef3-344">应在存档评估之前导出评估报告，因为存档的评估不会保留指向已上载文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-344">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="bcef3-345">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="bcef3-345">Export an Assessment report</span></span>
  
1. <span data-ttu-id="bcef3-346">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcef3-346">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="bcef3-347">在要导出的评估的下拉菜单中，选择 "**组**和**评估**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-347">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="bcef3-348">选择 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bcef3-348">Select the **Export** button.</span></span>

<span data-ttu-id="bcef3-349">在浏览器会话中，会将评估报告作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="bcef3-349">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="bcef3-350">Excel 文件的文件名称默认为评估的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-350">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="bcef3-351">隐藏模板或评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-351">Hide a Template or an Assessment</span></span>

<span data-ttu-id="bcef3-352">当您完成模板或评估且不再出于合规性目的而需要时，您可以将其从视图中隐藏。</span><span class="sxs-lookup"><span data-stu-id="bcef3-352">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="bcef3-353">如果模板或评估处于隐藏状态，则会将其从默认视图中删除，并且必须选中 "**包含隐藏**的" 复选框以显示它。</span><span class="sxs-lookup"><span data-stu-id="bcef3-353">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="bcef3-354">![合规性管理器隐藏的模板视图](media/compliance-manager-hidden-template.png "合规性管理器隐藏模板")</span><span class="sxs-lookup"><span data-stu-id="bcef3-354">![Compliance Manager Hidden Template View](media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcef3-355">隐藏的评估不会保留其到已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-355">Hidden Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="bcef3-356">强烈建议您先导出评估，然后再将其隐藏，以保留指向报告中的证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-356">It is highly recommended that you export the Assessment before hiding it to retain links to the evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="bcef3-357">隐藏模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-357">Hiding a Template</span></span>

1. <span data-ttu-id="bcef3-358">打开 "**模板**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-358">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="bcef3-359">找到要隐藏的模板，并在其所在行的省略号处，选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-359">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="bcef3-360">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-360">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="bcef3-361">隐藏评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-361">Hide an Assessment</span></span>

1. <span data-ttu-id="bcef3-362">打开 "**评估**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-362">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="bcef3-363">从下拉列表中选择包含您要隐藏的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="bcef3-363">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="bcef3-364">找到要隐藏的评估，然后在省略号上选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-364">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="bcef3-365">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-365">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="bcef3-366">查看隐藏评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-366">View hidden Assessments</span></span>
  
1. <span data-ttu-id="bcef3-367">打开 "**评估**仪表板" 选项卡，然后选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcef3-367">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="bcef3-368">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-368">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="bcef3-369">取消隐藏评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-369">Unhide an Assessment</span></span>

1. <span data-ttu-id="bcef3-370">在 "**评估**" 选项卡上，选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcef3-370">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="bcef3-371">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-371">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="bcef3-372">找到要取消隐藏的评估，然后在省略号上选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-372">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="bcef3-373">当您看到确认消息时，请选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-373">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="bcef3-374">控件和操作</span><span class="sxs-lookup"><span data-stu-id="bcef3-374">Controls and Actions</span></span>

<span data-ttu-id="bcef3-375">控件和操作是合规性管理器（预览版）中使用的主要数据透视。</span><span class="sxs-lookup"><span data-stu-id="bcef3-375">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="bcef3-376">在早期版本的合规性管理器中存在的控制轴已得到增强，可在相同的控制系列中显示 Microsoft 和 customer 控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-376">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="bcef3-377">此 "合并" 视图使以每个控件为基础查看完整的共享职责模型变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="bcef3-377">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="bcef3-378">操作透视是合规性管理器（预览版）中的新操作，旨在提供 Microsoft 建议的所有操作的简化视图。</span><span class="sxs-lookup"><span data-stu-id="bcef3-378">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="bcef3-379">控件</span><span class="sxs-lookup"><span data-stu-id="bcef3-379">Controls</span></span>

<span data-ttu-id="bcef3-380">可以从 "控件信息" 仪表板查看控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-380">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="bcef3-381">控件表示标准、认证、法规或框架中的要求。</span><span class="sxs-lookup"><span data-stu-id="bcef3-381">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="bcef3-382">若要跨多个标准、法规等满足这些要求，并将它们与操作相关联，则所有内容都被视为控制框架。</span><span class="sxs-lookup"><span data-stu-id="bcef3-382">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="bcef3-383">例如，像控制框架一样，法规（如 HIPAA）已按节细分，合规性管理器中的 HIPAA 控件使用与这些节相同的编号方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-383">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合规性管理器 Microsoft 控件详细信息](media/compliance-manager-control-details.png)

<span data-ttu-id="bcef3-385">有三种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="bcef3-385">There are three types of controls:</span></span>

1. <span data-ttu-id="bcef3-386">**Microsoft 托管控件：** 这些控件只是 microsoft 有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-386">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="bcef3-387">它们显示在 "现成" 模板中，并已添加到 Microsoft 的合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-387">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="bcef3-388">**客户管理的控件：** 这些控件只是客户有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-388">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="bcef3-389">它们显示在 "现成" 模板中，并由客户添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-389">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="bcef3-390">**共享管理控件：** 这些控件是在 Microsoft 和客户之间共享责任的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-390">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="bcef3-391">这些模板显示在 "现成" 模板中，由 Microsoft 添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-391">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="bcef3-392">客户还可以编辑或禁用 Microsoft 托管的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-392">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="bcef3-393">Actions 项</span><span class="sxs-lookup"><span data-stu-id="bcef3-393">Actions Items</span></span>

<span data-ttu-id="bcef3-394">操作项目是实施标准或法规要求的建议任务，或者用于测试、验证和记录组织的实现要求的任务。</span><span class="sxs-lookup"><span data-stu-id="bcef3-394">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="bcef3-395">操作与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="bcef3-395">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="bcef3-396">每个控件都有一个或多个与之关联的操作，并且每个操作都可以与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="bcef3-396">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="bcef3-397">操作是合规性管理器（预览版）中核心工作流的一部分，因为它们是由组织分配、跟踪和验证的对象。</span><span class="sxs-lookup"><span data-stu-id="bcef3-397">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="bcef3-398">分配操作项</span><span class="sxs-lookup"><span data-stu-id="bcef3-398">Assign Action Items</span></span>
  
1. <span data-ttu-id="bcef3-399">在 "**操作项**" 仪表板上，选择包含要分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="bcef3-399">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="bcef3-400">在 "**评估**" 下拉列表中，选择要为其分配操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-400">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="bcef3-401">找到要分配的操作，并在 "**所有者**" 列中选择要**查看**、已**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-401">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="bcef3-402">选择 "**分配用户**" 字段，将显示组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-402">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="bcef3-403">滚动列表并选择 "用户" 或 "筛选列表" 以通过键入用户的名称来选择用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-403">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="bcef3-404">在 "实施说明" 字段中，输入您希望向分配的用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="bcef3-404">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="bcef3-405">选择 "**保存**" 以分配操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-405">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="bcef3-406">重新分配操作项</span><span class="sxs-lookup"><span data-stu-id="bcef3-406">Reassign Action Items</span></span>

<span data-ttu-id="bcef3-407">通过此函数，组织可以通过将操作重新分配给新用户，删除对用户帐户的任何活动的或未完成的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bcef3-407">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="bcef3-408">在 "**操作项**" 仪表板上，选择包含要重新分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="bcef3-408">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="bcef3-409">在 "**评估**" 下拉列表中，选择要重新分配其操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-409">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="bcef3-410">找到要重新分配的操作，并在 "**所有者**" 列中选择要**查看**、**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-410">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="bcef3-411">从 "**分配用户**" 字段中删除现有用户，然后从用户列表中选择其他用户，或通过键入用户名称来筛选列表以选择用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-411">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="bcef3-412">在 "实施说明" 字段中，输入您希望向用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="bcef3-412">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="bcef3-413">选择 "**保存**" 以重新分配该操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-413">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="bcef3-414">模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-414">Templates</span></span>

<span data-ttu-id="bcef3-415">模板是合规性管理器（预览）中与产品和证书（例如，标准、法规、控制框架等）相关联的基本对象。</span><span class="sxs-lookup"><span data-stu-id="bcef3-415">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="bcef3-416">可以从 "模板" 仪表板中查看和添加模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-416">Templates can be viewed and added from the Templates dashboard.</span></span>

![合规性管理器 Microsoft 模板仪表板](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="bcef3-418">仪表板将显示每个模板以及与模板关联的证书和产品、创建模板的日期和上次修改的日期、客户和 Microsoft 托管控件的数量以及最大符合性分数模板，以及模板的状态（例如，"已批准"、"待定审批"、"已导入"）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-418">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="bcef3-419">内置模板都具有与之关联的内置评估，但您可以根据内置模板创建其他评估，也可以导入自己的模板，并根据这些模板创建自定义评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-419">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="bcef3-420">创建模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-420">Create a Template</span></span>

<span data-ttu-id="bcef3-421">您可以通过复制现有模板或导入自定义模板来创建模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-421">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="bcef3-422">存在必须用于模板数据的特定格式和架构，或者不会将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-422">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="bcef3-423">可以从此处下载具有正确架构和示例数据的文件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-423">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="bcef3-424">每个自定义模板应位于一个单独的 Excel 工作簿（.xls 或 .xlsx 格式）中，其中包含五个选项卡：</span><span class="sxs-lookup"><span data-stu-id="bcef3-424">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="bcef3-425">模板-评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-425">Template-Assessment</span></span>
2. <span data-ttu-id="bcef3-426">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="bcef3-426">ControlFamily</span></span>
3. <span data-ttu-id="bcef3-427">操作</span><span class="sxs-lookup"><span data-stu-id="bcef3-427">Actions</span></span>
4. <span data-ttu-id="bcef3-428">Ownership</span><span class="sxs-lookup"><span data-stu-id="bcef3-428">Ownership</span></span>
5. <span data-ttu-id="bcef3-429">Dimensions</span><span class="sxs-lookup"><span data-stu-id="bcef3-429">Dimensions</span></span>

<span data-ttu-id="bcef3-430">下面详细说明了每个选项卡中使用的架构。</span><span class="sxs-lookup"><span data-stu-id="bcef3-430">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="bcef3-431">模板-"评估" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcef3-431">Template-Assessment tab</span></span>

<span data-ttu-id="bcef3-432">此选项卡包含一个列：</span><span class="sxs-lookup"><span data-stu-id="bcef3-432">This tab has a single column:</span></span>

- <span data-ttu-id="bcef3-433">**inScopeServices**：模板的范围内的产品或服务的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-433">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="bcef3-434">ControlFamily 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcef3-434">ControlFamily tab</span></span>

<span data-ttu-id="bcef3-435">此选项卡包含的列定义映射到 "操作" 选项卡上列出的操作的控件，并包含控件名称、系列、标题和说明等详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-435">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="bcef3-436">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-436">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="bcef3-437">**controlName：** 来自证书/标准/法规等的控制名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-437">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="bcef3-438">**controlFamily：** 根据认证/标准、法规等控制家人。</span><span class="sxs-lookup"><span data-stu-id="bcef3-438">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="bcef3-439">**controlTitle：** 控制证书/标准/法规等的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-439">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="bcef3-440">**controlDescription：** 来自认证/标准/法规等的控制说明。</span><span class="sxs-lookup"><span data-stu-id="bcef3-440">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="bcef3-441">**controlVersion：** 可选的控制版本信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-441">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="bcef3-442">示例：对于 NIST 800-53，当前值为修订版4，因此 controlVersion 为4。</span><span class="sxs-lookup"><span data-stu-id="bcef3-442">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="bcef3-443">对于 CSA CCM，它是3.0.1。</span><span class="sxs-lookup"><span data-stu-id="bcef3-443">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="bcef3-444">**isDisabled：** 使用 TRUE 或 FALSE 可指示控件是否已被禁用。</span><span class="sxs-lookup"><span data-stu-id="bcef3-444">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="bcef3-445">**controlType：** 使用 "抄送" 以指示这些控件是客户托管的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-445">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="bcef3-446">**controlComplianceScore：** 分配给控件的所有操作分数的总和。</span><span class="sxs-lookup"><span data-stu-id="bcef3-446">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="bcef3-447">**controlActionTitle：** 此控件的所有 actionTitles 的双分号分隔的列表，如 "操作" 选项卡上所列。</span><span class="sxs-lookup"><span data-stu-id="bcef3-447">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="bcef3-448">操作选项卡</span><span class="sxs-lookup"><span data-stu-id="bcef3-448">Actions tab</span></span>

<span data-ttu-id="bcef3-449">此选项卡包含定义各个操作的列，并且包含操作标题、所有权和维度等详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-449">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="bcef3-450">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-450">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="bcef3-451">**actionTitle：** 操作的标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-451">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="bcef3-452">每个标题都必须是唯一的，我们建议使用 Pascal 大小写。</span><span class="sxs-lookup"><span data-stu-id="bcef3-452">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="bcef3-453">**actionRelatedODVs：** 以分号分隔的 actionTitles 列表，它们是 actionTitle 列中列出的子元素的父项。</span><span class="sxs-lookup"><span data-stu-id="bcef3-453">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="bcef3-454">在父/子关系中，父项代表高水位线。</span><span class="sxs-lookup"><span data-stu-id="bcef3-454">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="bcef3-455">因此，如果完成父操作，还将完成所有子操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-455">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="bcef3-456">例如，如果您具有类似的要求，但具有不同的标准定义值（如密码长度），其中一个标准/法规至少需要15个字符，而另一个标准/要求至少需要12个或10个。</span><span class="sxs-lookup"><span data-stu-id="bcef3-456">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="bcef3-457">15是此示例中的父级，如果至少配置15个字符，则还应满足在其他评估中建议的12个或10个字符的操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-457">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcef3-458">ActionRelatedODVs 列是架构的必需列;但是，功能（相关操作）在合规性管理器（预览）中不可用。</span><span class="sxs-lookup"><span data-stu-id="bcef3-458">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="bcef3-459">计划在更高版本中添加它。</span><span class="sxs-lookup"><span data-stu-id="bcef3-459">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="bcef3-460">**actionDimensionValues：** 使用以下格式的 "维" 选项卡中的适用维度的两个以分号分隔的列表：</span><span class="sxs-lookup"><span data-stu-id="bcef3-460">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```Markdown
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="bcef3-461">例如：</span><span class="sxs-lookup"><span data-stu-id="bcef3-461">For example:</span></span>

    ```Markdown
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="bcef3-462">自定义模板中使用的所有维度都必须在导入文件的 "维度" 选项卡上列出，即使它们已列在 "维度" 仪表板上也是如此。</span><span class="sxs-lookup"><span data-stu-id="bcef3-462">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="bcef3-463">**actionScore：** 每个操作的数字值，表示该操作的分数。</span><span class="sxs-lookup"><span data-stu-id="bcef3-463">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="bcef3-464">我们建议遵循内置评估使用的记分模型，这取决于每个操作的用途和实施。</span><span class="sxs-lookup"><span data-stu-id="bcef3-464">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="bcef3-465">**actionOwnership：** 以分号分隔的所有者列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-465">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="bcef3-466">所有列出的所有者都必须包含在 "所有权" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="bcef3-466">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="bcef3-467">**actionDescription：** 每个操作的文本，必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bcef3-467">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="bcef3-468">此字段支持 Markdown 语言，如下所述。</span><span class="sxs-lookup"><span data-stu-id="bcef3-468">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="bcef3-469">所有权选项卡</span><span class="sxs-lookup"><span data-stu-id="bcef3-469">Ownership tab</span></span>

<span data-ttu-id="bcef3-470">此选项卡包含用于定义每个操作的所有者的列。</span><span class="sxs-lookup"><span data-stu-id="bcef3-470">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="bcef3-471">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-471">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="bcef3-472">**ownershipName：** 所有者/责任方的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-472">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="bcef3-473">**ownershipDescription：** 所有者/责任方的说明。</span><span class="sxs-lookup"><span data-stu-id="bcef3-473">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="bcef3-474">维度选项卡</span><span class="sxs-lookup"><span data-stu-id="bcef3-474">Dimensions tab</span></span>

<span data-ttu-id="bcef3-475">此选项卡包含定义可与操作相关联的维度的列。</span><span class="sxs-lookup"><span data-stu-id="bcef3-475">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="bcef3-476">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcef3-476">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="bcef3-477">**dimensionKey：** 用于维度的键的列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-477">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="bcef3-478">例如，产品、认证等。</span><span class="sxs-lookup"><span data-stu-id="bcef3-478">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="bcef3-479">**dimensionValue：** 每个维度键的唯一值。</span><span class="sxs-lookup"><span data-stu-id="bcef3-479">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="bcef3-480">例如，Office 365、Intune、Azure、自定义产品等。</span><span class="sxs-lookup"><span data-stu-id="bcef3-480">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="bcef3-481">**allowMultiSelect：** 使用 TRUE 或 FALSE 可指示可以为单个维度键选择多个维度值。</span><span class="sxs-lookup"><span data-stu-id="bcef3-481">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="bcef3-482">在 "说明" 字段中使用 Markdown 语言</span><span class="sxs-lookup"><span data-stu-id="bcef3-482">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="bcef3-483">模板和评估支持对某些文本元素和格式使用 Markdown 语言。</span><span class="sxs-lookup"><span data-stu-id="bcef3-483">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="bcef3-484">在合规性管理器中使用的 Markdown 语言有三个格式元素：</span><span class="sxs-lookup"><span data-stu-id="bcef3-484">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="bcef3-485">项目符号和编号列表</span><span class="sxs-lookup"><span data-stu-id="bcef3-485">Bullets and Numbered lists</span></span>
- <span data-ttu-id="bcef3-486">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="bcef3-486">Hyperlinks</span></span>
- <span data-ttu-id="bcef3-487">粗体</span><span class="sxs-lookup"><span data-stu-id="bcef3-487">Boldface</span></span>

<span data-ttu-id="bcef3-488">项目符号表示为星号而不是 Word 或 Excel 项目符号。</span><span class="sxs-lookup"><span data-stu-id="bcef3-488">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="bcef3-489">例如：</span><span class="sxs-lookup"><span data-stu-id="bcef3-489">For example:</span></span>

```Markdown
* Item A
* Item B
* Item C
```

<span data-ttu-id="bcef3-490">数字表示为数字，但在缩进（每个级别三个空格）和仅用于所有子级别的数字（例如，不带字母）之间使用空格。</span><span class="sxs-lookup"><span data-stu-id="bcef3-490">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="bcef3-491">例如：</span><span class="sxs-lookup"><span data-stu-id="bcef3-491">For example:</span></span>
   1. <span data-ttu-id="bcef3-492">Item A</span><span class="sxs-lookup"><span data-stu-id="bcef3-492">Item A</span></span>
   2. <span data-ttu-id="bcef3-493">项目 B</span><span class="sxs-lookup"><span data-stu-id="bcef3-493">Item B</span></span>
      1. <span data-ttu-id="bcef3-494">子项目 A</span><span class="sxs-lookup"><span data-stu-id="bcef3-494">Sub-item A</span></span>
      2. <span data-ttu-id="bcef3-495">子项目 B</span><span class="sxs-lookup"><span data-stu-id="bcef3-495">Sub-item B</span></span>
   3. <span data-ttu-id="bcef3-496">项目 C</span><span class="sxs-lookup"><span data-stu-id="bcef3-496">Item C</span></span>
   4. <span data-ttu-id="bcef3-497">项目 D</span><span class="sxs-lookup"><span data-stu-id="bcef3-497">Item D</span></span>
      1. <span data-ttu-id="bcef3-498">子项目 A</span><span class="sxs-lookup"><span data-stu-id="bcef3-498">Sub-item A</span></span>
      2. <span data-ttu-id="bcef3-499">子项目 B</span><span class="sxs-lookup"><span data-stu-id="bcef3-499">Sub-item B</span></span>
   5. <span data-ttu-id="bcef3-500">Item E</span><span class="sxs-lookup"><span data-stu-id="bcef3-500">Item E</span></span>

<span data-ttu-id="bcef3-501">通过在超链接文本周围加上括号并将超链接本身放在右方括号旁边的括号中来构造超链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-501">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="bcef3-502">例如：</span><span class="sxs-lookup"><span data-stu-id="bcef3-502">For example:</span></span>

```Markdown
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="bcef3-503">此文本呈现如下：单击[此处](https://www.microsoft.com)转到 Microsoft 主页。</span><span class="sxs-lookup"><span data-stu-id="bcef3-503">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>

<span data-ttu-id="bcef3-504">如上面的示例中所示，合规性管理器不呈现带下划线的 Url。</span><span class="sxs-lookup"><span data-stu-id="bcef3-504">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="bcef3-505">粗体文本是文本的每一侧加粗的两个星号。</span><span class="sxs-lookup"><span data-stu-id="bcef3-505">Boldface text is two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="bcef3-506">例如：</span><span class="sxs-lookup"><span data-stu-id="bcef3-506">For example:</span></span>

```Markdown
**This text will render in bold**
```
<span data-ttu-id="bcef3-507">**此文本以粗体呈现**</span><span class="sxs-lookup"><span data-stu-id="bcef3-507">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="bcef3-508">创建模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-508">Create a Template</span></span>

<span data-ttu-id="bcef3-509">您可以通过复制现有模板或从 Excel 导入模板数据来创建模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-509">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="bcef3-510">从 Excel 导入数据时，模板需要两个不同的合规性管理器管理员发布数据（一个发布，另一个用于审批）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-510">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="bcef3-511">通过复制现有模板创建模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-511">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="bcef3-512">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-512">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="bcef3-513">在 "**输入模板名称**" 字段中，为模板提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-513">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="bcef3-514">选中 "**从现有模板复制**" 复选框，然后从下拉列表中选择要复制的模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-514">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="bcef3-515">（可选）添加任何其他维度。</span><span class="sxs-lookup"><span data-stu-id="bcef3-515">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="bcef3-516">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-516">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="bcef3-517">通过导入数据创建模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-517">Create a Template by importing data</span></span>

1. <span data-ttu-id="bcef3-518">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-518">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="bcef3-519">在 "**输入模板名称**" 字段中，为模板提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="bcef3-519">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="bcef3-520">从可用列表中选择至少一个维度。</span><span class="sxs-lookup"><span data-stu-id="bcef3-520">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="bcef3-521">选择 "**浏览**" 导航到导入文件的位置，选择该文件，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-521">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="bcef3-522">将验证导入文件，并指示检测到的控件和控件系列的数量。</span><span class="sxs-lookup"><span data-stu-id="bcef3-522">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="bcef3-523">如果有错误，则会向包含错误详细信息的导入文件的修改版本提供链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-523">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="bcef3-524">必须先解决所有错误，然后才会导入数据。</span><span class="sxs-lookup"><span data-stu-id="bcef3-524">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="bcef3-525">数据通过验证后，选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-525">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="bcef3-526">导入的模板将显示在 "**模板**" 仪表板上，其状态为 "已**导入**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-526">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="bcef3-527">选择省略号（...），然后选择 "**发布**" 以发布模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-527">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="bcef3-528">当出现确认消息时，请选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-528">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="bcef3-529">模板状态将更改为 "**待审批**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-529">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="bcef3-530">另一个具有合规性管理器管理员角色的用户必须批准模板仪表板中的模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-530">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="bcef3-531">他们必须选择省略号（...），然后选择 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-531">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="bcef3-532">当出现确认消息时，选择 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-532">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="bcef3-533">现在即可使用该模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-533">The Template is now ready for use.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcef3-534">创建模板时，您必须包括**产品**和**证书**的维度，以确保您的模板在合规性分数中显示。</span><span class="sxs-lookup"><span data-stu-id="bcef3-534">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="bcef3-535">自定义模板</span><span class="sxs-lookup"><span data-stu-id="bcef3-535">Customize a Template</span></span>

<span data-ttu-id="bcef3-536">可以通过其他自定义控件自定义模板。</span><span class="sxs-lookup"><span data-stu-id="bcef3-536">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="bcef3-537">所有自定义控件都被视为客户托管的控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-537">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="bcef3-538">向模板中添加自定义控件</span><span class="sxs-lookup"><span data-stu-id="bcef3-538">Add a custom control to a Template</span></span>

1. <span data-ttu-id="bcef3-539">打开要修改的**模板**。</span><span class="sxs-lookup"><span data-stu-id="bcef3-539">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="bcef3-540">选择 " **+ 添加**自定义控件"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-540">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="bcef3-541">从下拉列表中选择一个**控制族**，或输入一个新的控制族（如果不存在）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-541">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="bcef3-542">为 "**控件 ID** " 字段中的控件提供一个唯一的名称或 ID。</span><span class="sxs-lookup"><span data-stu-id="bcef3-542">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="bcef3-543">在 "**标题**" 字段中提供控件标题。</span><span class="sxs-lookup"><span data-stu-id="bcef3-543">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="bcef3-544">提供 "**说明**" 字段中控件的要求和其他信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-544">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="bcef3-545">选择 "**分配客户**操作"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-545">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="bcef3-546">找到要分配给控件的操作：</span><span class="sxs-lookup"><span data-stu-id="bcef3-546">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="bcef3-547">使用 "**按维度筛选**" 以使用分配给操作的维度来查找和列出它们。</span><span class="sxs-lookup"><span data-stu-id="bcef3-547">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="bcef3-548">使用 "**按所有者筛选**" 以使用分配给操作的所有者来查找和列出它们。</span><span class="sxs-lookup"><span data-stu-id="bcef3-548">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="bcef3-549">从下拉列表中选择**操作类型**以按类型列出操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-549">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="bcef3-550">输入要查找的操作的标题并将其列出。</span><span class="sxs-lookup"><span data-stu-id="bcef3-550">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="bcef3-551">使用步骤8中的条件，将显示**匹配操作**的列表。</span><span class="sxs-lookup"><span data-stu-id="bcef3-551">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="bcef3-552">选择要分配给控件的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-552">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="bcef3-553">将显示操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcef3-553">The details of the Action appear.</span></span> <span data-ttu-id="bcef3-554">选择要使用的**说明**，然后选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-554">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="bcef3-555">对每个要分配的其他操作重复步骤9和10。</span><span class="sxs-lookup"><span data-stu-id="bcef3-555">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="bcef3-556">选择所有适用的操作后，选择 "**分配**"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-556">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="bcef3-557">选择 "**保存**" 以保存新控件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-557">Select **Save** to save the new control.</span></span>

> [!NOTE]
> <span data-ttu-id="bcef3-558">对模板所做的任何更改不会反映在现有评估中。</span><span class="sxs-lookup"><span data-stu-id="bcef3-558">Any changes made to a template will not be reflected in existing assessments.</span></span> <span data-ttu-id="bcef3-559">必须首先执行模板更新，然后再将其应用于新的评估，以便能够看到所做的更改。</span><span class="sxs-lookup"><span data-stu-id="bcef3-559">Template updates must be made first, and then applied to a new assessment, in order for the changes to be seen.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="bcef3-560">将模板导出到 JSON</span><span class="sxs-lookup"><span data-stu-id="bcef3-560">Export a Template to JSON</span></span>

<span data-ttu-id="bcef3-561">合规性管理器（预览版）还支持将模板导出为 JavaScript 对象表示法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="bcef3-561">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="bcef3-562">这使您可以与支持 JSON 的其他系统交换合规性管理器数据。</span><span class="sxs-lookup"><span data-stu-id="bcef3-562">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="bcef3-563">报告</span><span class="sxs-lookup"><span data-stu-id="bcef3-563">Reports</span></span>

<span data-ttu-id="bcef3-564">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="bcef3-564">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="bcef3-565">报告是在导出的日期和时间进行评估的快照。</span><span class="sxs-lookup"><span data-stu-id="bcef3-565">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="bcef3-566">该报告包含 Microsoft 和客户托管的控件的详细信息，用于评估、控制实施状态、控制测试日期、测试结果以及指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-566">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="bcef3-567">应在存档评估之前将其导出，因为存档的评估不会保留指向已上载文档的链接。</span><span class="sxs-lookup"><span data-stu-id="bcef3-567">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="bcef3-568">导出评估</span><span class="sxs-lookup"><span data-stu-id="bcef3-568">Export an Assessment</span></span>

1. <span data-ttu-id="bcef3-569">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcef3-569">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="bcef3-570">在下拉菜单中选择要导出的评估的组和评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-570">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="bcef3-571">选择 "导出"。</span><span class="sxs-lookup"><span data-stu-id="bcef3-571">Select Export.</span></span> <span data-ttu-id="bcef3-572">将评估导出作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="bcef3-572">The Assessment export is downloaded as an Excel file.</span></span>

![合规性管理器评估 Excel 报告](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="bcef3-574">Permissions</span><span class="sxs-lookup"><span data-stu-id="bcef3-574">Permissions</span></span>

<span data-ttu-id="bcef3-575">下表介绍了每个合规性管理器权限及其允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bcef3-575">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="bcef3-576">该表还指示分配了每个权限的角色。</span><span class="sxs-lookup"><span data-stu-id="bcef3-576">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="bcef3-577">**Azure AD 全局读取器**</span><span class="sxs-lookup"><span data-stu-id="bcef3-577">**Azure AD Global Reader**</span></span>|<span data-ttu-id="bcef3-578">**合规性管理器读者**</span><span class="sxs-lookup"><span data-stu-id="bcef3-578">**Compliance Manager Reader**</span></span>|<span data-ttu-id="bcef3-579">**合规性管理器参与者**</span><span class="sxs-lookup"><span data-stu-id="bcef3-579">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="bcef3-580">**合规性管理器评估员**</span><span class="sxs-lookup"><span data-stu-id="bcef3-580">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="bcef3-581">**合规性管理器管理员**</span><span class="sxs-lookup"><span data-stu-id="bcef3-581">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="bcef3-582">**门户管理员**</span><span class="sxs-lookup"><span data-stu-id="bcef3-582">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bcef3-583">**读取数据：** 用户可以读取但不能编辑数据（模板数据和租户管理除外）。</span><span class="sxs-lookup"><span data-stu-id="bcef3-583">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="bcef3-584">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-584">X</span></span> | <span data-ttu-id="bcef3-585">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-585">X</span></span> | <span data-ttu-id="bcef3-586">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-586">X</span></span> | <span data-ttu-id="bcef3-587">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-587">X</span></span> | <span data-ttu-id="bcef3-588">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-588">X</span></span>  | <span data-ttu-id="bcef3-589">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-589">X</span></span> |
|<span data-ttu-id="bcef3-590">**编辑数据：** 除了 "测试结果" 和 "测试日期" 字段（"模板数据" 和 "租户管理" 除外）之外，用户可以编辑所有字段。</span><span class="sxs-lookup"><span data-stu-id="bcef3-590">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="bcef3-591">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-591">X</span></span> | <span data-ttu-id="bcef3-592">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-592">X</span></span>  | <span data-ttu-id="bcef3-593">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-593">X</span></span> | <span data-ttu-id="bcef3-594">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-594">X</span></span> |
|<span data-ttu-id="bcef3-595">**编辑测试结果：** 用户可以编辑 "测试结果" 和 "测试日期" 字段。</span><span class="sxs-lookup"><span data-stu-id="bcef3-595">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="bcef3-596">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-596">X</span></span> | <span data-ttu-id="bcef3-597">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-597">X</span></span> | <span data-ttu-id="bcef3-598">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-598">X</span></span> |
|<span data-ttu-id="bcef3-599">**管理评估：** 用户可以创建、存档和删除评估。</span><span class="sxs-lookup"><span data-stu-id="bcef3-599">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="bcef3-600">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-600">X</span></span> | <span data-ttu-id="bcef3-601">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-601">X</span></span> |
|<span data-ttu-id="bcef3-602">**管理主数据：** 用户可以查看、编辑和删除模板数据和租户管理数据。</span><span class="sxs-lookup"><span data-stu-id="bcef3-602">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="bcef3-603">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-603">X</span></span> | <span data-ttu-id="bcef3-604">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-604">X</span></span> |
|<span data-ttu-id="bcef3-605">**管理用户：** 用户可以将组织中的其他用户添加到 Reader、投稿人、评估员和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="bcef3-605">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="bcef3-606">只有组织中具有全局管理员角色的用户才可以在门户管理员角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="bcef3-606">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="bcef3-607">X</span><span class="sxs-lookup"><span data-stu-id="bcef3-607">X</span></span> |
