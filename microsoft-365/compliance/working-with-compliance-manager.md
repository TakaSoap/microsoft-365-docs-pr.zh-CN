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
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: d15899b994e4169c7362144623bc726f3825245d
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417581"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="ccb1d-104">使用 Microsoft 合规性管理器（预览）</span><span class="sxs-lookup"><span data-stu-id="ccb1d-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccb1d-105">Microsoft 合规性管理器是一个仪表板和管理工具，提供了有关数据保护和合规性的摘要 stature 以及改进数据保护和合规性的建议。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="ccb1d-106">合规性管理器中提供的客户操作是建议;在实现之前，你的组织可以评估这些建议在其各自的法规环境中的有效性。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="ccb1d-107">在合规性管理器中找到的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="ccb1d-108">Access 合规性管理器</span><span class="sxs-lookup"><span data-stu-id="ccb1d-108">Access Compliance Manager</span></span>

<span data-ttu-id="ccb1d-p103">合规性管理器是从服务信任门户进行访问。任何拥有 Microsoft 帐户或 Azure Active Directory 组织帐户的人，都可以访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="ccb1d-111">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="ccb1d-112">使用 Microsoft 服务帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-112">Sign in with your Microsoft service account.</span></span> <span data-ttu-id="ccb1d-113">这是你的 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-113">This is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="ccb1d-114">在服务信任门户中，选择 "**合规性管理器**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-114">In the Service Trust Portal, select **Compliance Manager**.</span></span> <span data-ttu-id="ccb1d-115">这是合规性管理器的预览版本。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-115">This is the preview version of Compliance Manager.</span></span> <span data-ttu-id="ccb1d-116">**合规性管理器（经典）** 是指向早期版本的合规性管理器的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-116">**Compliance Manager (Classic)** is the link to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="ccb1d-117">在显示非公开协议时，请阅读并选择 "**同意**继续"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-117">When the Non-Disclosure Agreement is displayed, read it, and select **Agree** to continue.</span></span> <span data-ttu-id="ccb1d-118">您必须同意一次，然后才会显示合规性管理器仪表板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-118">You must agree once, and then the Compliance Manager dashboard is displayed.</span></span>

<span data-ttu-id="ccb1d-119">为实现入门，默认情况下，Office 365 的 ISO/IEC 27001:2103 评估会显示在您的组织中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-119">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="ccb1d-120">管理</span><span class="sxs-lookup"><span data-stu-id="ccb1d-120">Administration</span></span>

<span data-ttu-id="ccb1d-121">只有全局管理员可以使用特定的管理功能，并且只有在使用全局管理员帐户登录时才可见。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-121">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="ccb1d-122">一旦管理员将合规性管理器角色分配给其他用户，这些用户就可以在合规性管理器中查看数据，并执行角色所确定的操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-122">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="ccb1d-123">管理员还可以通过向用户分配[Azure Active Directory （AZURE AD）中的全局读取器角色](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)，授予对合规性管理器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-123">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="ccb1d-124">向用户分配合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="ccb1d-124">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="ccb1d-125">每个合规性管理器角色都具有略有不同的权限。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-125">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="ccb1d-126">您可以查看分配给每个角色的权限，查看哪些用户是哪些角色，以及通过服务信任门户在该角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-126">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="ccb1d-127">选择 "**管理**" 菜单项，然后选择 "要查看的**设置**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-127">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理菜单：选择的设置](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="ccb1d-129">若要在合规性管理器角色中添加或删除用户，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-129">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="ccb1d-130">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-130">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="ccb1d-131">使用 Azure Active Directory 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-131">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="ccb1d-132">在 "服务信任门户" 顶部菜单栏上，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-132">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="ccb1d-133">在 "**选择角色**" 下拉列表中，选择要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-133">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="ccb1d-134">在 "**选择角色**" 页上列出了添加到每个角色的用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-134">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="ccb1d-135">若要将用户添加到此角色，请选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-135">To add users to this role, select **Add**.</span></span> <span data-ttu-id="ccb1d-136">在 "**添加用户**" 对话框中，选择 "用户" 字段。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-136">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="ccb1d-137">您可以在可用用户列表中滚动，也可以开始键入用户名，以根据您的搜索词筛选列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-137">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="ccb1d-138">选择要将该帐户添加到使用该角色预配的 "**添加用户**" 列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-138">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="ccb1d-139">如果要同时添加多个用户，请开始键入用户名以筛选列表，然后选择要添加到列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-139">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="ccb1d-140">选择 "**保存**" 将所选角色设置给这些用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-140">Select **Save** to provision the selected role to these users.</span></span> 

    ![合规性管理器-添加用户](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="ccb1d-142">若要从此角色中删除用户，请选择 "用户"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-142">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合规性管理器-删除用户](media/compliance-manager-delete-users.png)

## <a name="groups"></a><span data-ttu-id="ccb1d-144">组</span><span class="sxs-lookup"><span data-stu-id="ccb1d-144">Groups</span></span>

<span data-ttu-id="ccb1d-145">组允许您以逻辑方式组织评估，并在评估之间共享公共信息和工作流任务，这些评估与客户托管的控件相同或相关。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-145">Groups allow you to logically organize Assessments and that share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="ccb1d-146">您可以按组织中的年、标准、服务、团队、部门或机构对评估进行分组，以帮助最大限度地减少客户管理的操作：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-146">You can group Assessments by year, standard, service, team, division, or agencies within your organization to help minimize customer-managed Actions:</span></span>
  
- <span data-ttu-id="ccb1d-147">**FFIEC 是评估2019**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-147">**FFIEC IS Assessments 2019**</span></span>
  - <span data-ttu-id="ccb1d-148">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="ccb1d-148">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="ccb1d-149">Intune + FFIEC 为</span><span class="sxs-lookup"><span data-stu-id="ccb1d-149">Intune + FFIEC IS</span></span>
- <span data-ttu-id="ccb1d-150">**“数据安全和隐私”评估**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-150">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="ccb1d-151">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="ccb1d-151">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="ccb1d-152">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="ccb1d-152">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="ccb1d-153">当您创建新的评估时，您必须为评估创建一个新组，或将评估分配给现有组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-153">When you create a new Assessment, you must create a new group for the Assessment or assign the Assessment to an existing group.</span></span> <span data-ttu-id="ccb1d-154">不能将组创建为独立的实体。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-154">Groups cannot be created as stand-alone entities.</span></span> <span data-ttu-id="ccb1d-155">建议您在添加新评估*之前*为您的组织确定一个分组策略。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-155">It's recommended that you determine a grouping strategy for your organization *before* adding new assessments.</span></span> <span data-ttu-id="ccb1d-156">默认情况下，在初始评估中可使用名为 "默认组" 的组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-156">By default, a Group named "Default Group" is available for your initial Assessments.</span></span> <span data-ttu-id="ccb1d-157">组没有任何安全属性。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-157">Groups do not have any security properties.</span></span> <span data-ttu-id="ccb1d-158">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-158">All permissions are associated with Assessments.</span></span>

<span data-ttu-id="ccb1d-159">使用组时，请记住：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-159">When you work with groups, remember:</span></span>
  
- <span data-ttu-id="ccb1d-160">在同一组中的不同评估中的相关评估控件在完成后将自动更新。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-160">Related assessment controls in different assessments within the same Group automatically update when completed.</span></span>
- <span data-ttu-id="ccb1d-161">当您创建新的评估时，新组可以复制现有组中的信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-161">New groups can copy information from an existing group when you create a new Assessment.</span></span> <span data-ttu-id="ccb1d-162">从进行复制的组中的客户托管控件的 "实现详细信息" 和 "测试计划和管理响应" 字段中添加的任何信息都将复制到 "新建" 中的 "客户托管" 控件中的相同（或相关）。因素.</span><span class="sxs-lookup"><span data-stu-id="ccb1d-162">Any information added to the Implementation Details and Test Plan and Management Response fields of customer-managed controls from Assessments in the group that you're copying from are copied to the same (or related) customer-managed controls in the new Assessment.</span></span> <span data-ttu-id="ccb1d-163">如果要将新评估添加到现有组中，则会将该组中评估的常见信息复制到新评估中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-163">If you're adding a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="ccb1d-164">组名（也称为*组 id*）在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-164">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="ccb1d-165">组可以包含对同一认证/法规的评估，但每个组只能包含针对特定云服务/证书对的一个评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-165">Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair.</span></span> <span data-ttu-id="ccb1d-166">例如，组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-166">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="ccb1d-167">仅当一个组与同一个云服务的对应证书/法规不同时，该组才能包含对同一个云服务的多个评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-167">A group can contain multiple Assessments for the same cloud service only if the corresponding certification/regulation for each one is different.</span></span>
- <span data-ttu-id="ccb1d-168">在将评估添加到评估组后，不能更改此分组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-168">Once an assessment has been added to an assessment group, the grouping cannot be changed.</span></span> <span data-ttu-id="ccb1d-169">您可以重命名评估组，这将更改与该组关联的所有评估的评估分组的名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-169">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span> <span data-ttu-id="ccb1d-170">您可以创建评估和新的评估组，并从现有评估中复制信息，这样可有效地在不同的评估组中创建该评估的重复项。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-170">You can create an assessment and a new assessment group and copy information from an existing assessment, which effectively creates a duplicate of that assessment in a different assessment group.</span></span>
- <span data-ttu-id="ccb1d-171">存档评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-171">Archiving an assessment breaks the relationship between that assessment and the group.</span></span> <span data-ttu-id="ccb1d-172">任何进一步的相关评估更新将不再反映在存档评估中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-172">Any further updates to other related assessments are no longer reflected in the archived assessment.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="ccb1d-173">租户管理</span><span class="sxs-lookup"><span data-stu-id="ccb1d-173">Tenant Management</span></span>

<span data-ttu-id="ccb1d-174">合规性管理器（预览版）包括用于管理名为**租户管理**的新数据元素的新接口。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-174">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="ccb1d-175">此接口使您能够管理租户范围内的设置：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-175">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="ccb1d-176">**维：** 查看可用于为筛选器创建自定义透视的模板、评估和操作项的元数据。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-176">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="ccb1d-177">**所有者：** 为每个即席项目指定一个所有者。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-177">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="ccb1d-178">**客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并为与安全得分集成的操作启用/禁用安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-178">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="ccb1d-179">选择 "**租户管理**" 以打开管理界面，并使用以下步骤来管理**维度**、**所有者**和**客户操作**。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-179">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="ccb1d-180">Dimensions</span><span class="sxs-lookup"><span data-stu-id="ccb1d-180">Dimensions</span></span>

<span data-ttu-id="ccb1d-181">维度是提供有关模板、评估或措施项的信息的元数据的集合。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-181">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="ccb1d-182">维度使用键和值的概念，其中维度键表示属性，维度值表示属性的有效值。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-182">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="ccb1d-183">例如，在合规性管理器中有三种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-183">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="ccb1d-184">它们由**操作类型**的维度键和**文档**、**运营**和**技术**的维度值定义。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-184">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="ccb1d-185">您可以编辑或删除现有维度。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-185">You can edit or delete existing Dimensions.</span></span>

### <a name="owners"></a><span data-ttu-id="ccb1d-186">Owners</span><span class="sxs-lookup"><span data-stu-id="ccb1d-186">Owners</span></span>

<span data-ttu-id="ccb1d-187">所有者用于标识每个控件的负责方。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-187">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="ccb1d-188">所有内置控件由 Microsoft、客户或这两者拥有。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-188">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="ccb1d-189">您可以创建可用于在组织中指定更精确的职责的所有者的自定义值。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-189">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="ccb1d-190">例如，可以创建代表组织中的特定组、团队或业务单位的所有者。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-190">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="ccb1d-191">添加所有者</span><span class="sxs-lookup"><span data-stu-id="ccb1d-191">Add an Owner</span></span>

1. <span data-ttu-id="ccb1d-192">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-192">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="ccb1d-193">选择 " **+ 添加所有者**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-193">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="ccb1d-194">提供所有者的名称和说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-194">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="ccb1d-195">说明显示在 "所有者" 列中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-195">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="ccb1d-196">编辑所有者</span><span class="sxs-lookup"><span data-stu-id="ccb1d-196">Edit an Owner</span></span>

<span data-ttu-id="ccb1d-197">您不能编辑所有者名称，但可以修改 "Owner" 列中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-197">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="ccb1d-198">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-198">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="ccb1d-199">找到要编辑的所有者，选择其旁边的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-199">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="ccb1d-200">根据需要修改说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-200">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="ccb1d-201">删除所有者</span><span class="sxs-lookup"><span data-stu-id="ccb1d-201">Delete an Owner</span></span>

1. <span data-ttu-id="ccb1d-202">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-202">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="ccb1d-203">找到要删除的所有者，选择其旁边的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-203">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="ccb1d-204">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-204">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="ccb1d-205">客户操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-205">Customer Actions</span></span>

<span data-ttu-id="ccb1d-206">"客户操作" 区域显示合规性管理器中所有模板和评估的所有客户操作（预览）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-206">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

![合规性管理器-添加用户](media/compliance-manager-customer-actions.png)

<span data-ttu-id="ccb1d-208">一览，您可以查看操作的标题、所有者、类别、强制和分数，并确定它是否与安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-208">At-a-glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="ccb1d-209">您可以展开操作并选择 "**读取更多**"，以读取操作说明并访问说明中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-209">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="ccb1d-210">您还可以使用此接口基于每个操作启用和禁用安全得分集成，并添加自定义操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-210">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="ccb1d-211">具有安全得分集成功能的操作旁边有一个省略号（...）（请注意，自定义操作旁边还有一个省略号）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-211">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="ccb1d-212">启用或禁用安全分数集成</span><span class="sxs-lookup"><span data-stu-id="ccb1d-212">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="ccb1d-213">选择要修改的操作的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-213">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="ccb1d-214">切换交换机以确保安全分数连续更新为 "开" 或 "关"，以通过安全分数启用或禁用连续监控。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-214">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="ccb1d-215">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-215">Select **Save**.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="ccb1d-216">添加客户操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-216">Add a customer action</span></span>

1. <span data-ttu-id="ccb1d-217">选择 " **+ 添加客户操作**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-217">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="ccb1d-218">在 "**标题**" 字段中为操作提供唯一的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-218">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="ccb1d-219">在 "**最大合规性分数**" 字段中提供操作的合规性分数（可以是1-99 中的任何数字）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-219">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="ccb1d-220">使用 "**操作类型**" 下拉列表来指定要添加的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-220">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="ccb1d-221">如果操作类型不存在，则可以通过将值添加到 "操作类型" 维度键来添加它。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-221">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="ccb1d-222">使用 "**维度**" 下拉列表可指定或添加操作的维度键和值。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-222">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="ccb1d-223">使用 "**所有者**" 下拉列表指定操作的所有者。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-223">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="ccb1d-224">选择**+** 以添加操作的说明和说明标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-224">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="ccb1d-225">选择**X**以关闭说明边栏。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-225">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="ccb1d-226">选择 "**保存**" 以保存客户操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-226">Select **Save** to save the Customer Action.</span></span>

#### <a name="edit-a-customer-action"></a><span data-ttu-id="ccb1d-227">编辑客户操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-227">Edit a customer action</span></span>

1. <span data-ttu-id="ccb1d-228">选择要修改的操作的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-228">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="ccb1d-229">根据需要编辑操作，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-229">Edit the Action as desired, and select **Save**.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="ccb1d-230">删除客户操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-230">Delete a customer action</span></span>

1. <span data-ttu-id="ccb1d-231">选择要修改的操作的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-231">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="ccb1d-232">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-232">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="ccb1d-233">评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-233">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="ccb1d-234">添加评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-234">Add an Assessment</span></span>
  
1. <span data-ttu-id="ccb1d-235">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-235">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="ccb1d-236">当边栏打开时，请输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-236">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="ccb1d-237">**标题（必需）：** 输入评估的标题</span><span class="sxs-lookup"><span data-stu-id="ccb1d-237">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="ccb1d-238">**请选择一个模板（必需）：** 选择标准或自定义模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-238">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="ccb1d-239">**请选择组或添加新组（必需）：** 选择现有组或选择添加新组，并提供唯一的组名称</span><span class="sxs-lookup"><span data-stu-id="ccb1d-239">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="ccb1d-240">**是否要复制现有组中的数据？（可选）：** 切换控件以启用组副本，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-240">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="ccb1d-241">**选择一个组（可选）：** 如果已启用组副本，请选择要复制的组</span><span class="sxs-lookup"><span data-stu-id="ccb1d-241">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="ccb1d-242">**实现详细信息（可选）：** 选择以将实现详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="ccb1d-242">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="ccb1d-243">**测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="ccb1d-243">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="ccb1d-244">**文档（可选）：** 选择以将文档复制到新组</span><span class="sxs-lookup"><span data-stu-id="ccb1d-244">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="ccb1d-245">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-245">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="ccb1d-246">新评估显示在评估仪表板上，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-246">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="ccb1d-247">评估的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-247">The title of the Assessment.</span></span>
- <span data-ttu-id="ccb1d-248">评估的维度，包括认证、环境和应用于评估的产品。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-248">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="ccb1d-249">创建日期的日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-249">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="ccb1d-250">评估分数显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-250">The Assessment Score shown as a percentage.</span></span>
- <span data-ttu-id="ccb1d-251">进度指示器，显示已评估的 Microsoft 托管和客户 manged 控件的数量。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-251">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="ccb1d-252">从现有评估复制信息</span><span class="sxs-lookup"><span data-stu-id="ccb1d-252">Copying information from existing Assessments</span></span>

<span data-ttu-id="ccb1d-253">创建评估时，可以选择从现有组复制信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-253">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="ccb1d-254">这使您可以将输入到复制的评估中的信息应用于新评估中的相同控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-254">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="ccb1d-255">例如，如果您的组织中有与 FFIEC 相关的所有评估的组，则可以从现有评估中复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-255">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="ccb1d-256">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="ccb1d-256">Implementation Details</span></span>
- <span data-ttu-id="ccb1d-257">测试计划 & 其他信息</span><span class="sxs-lookup"><span data-stu-id="ccb1d-257">Test Plan & Additional Information</span></span>
- <span data-ttu-id="ccb1d-258">文档</span><span class="sxs-lookup"><span data-stu-id="ccb1d-258">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="ccb1d-259">将信息从现有评估复制到新评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-259">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="ccb1d-260">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-260">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="ccb1d-261">在 "**添加评估**" 窗口中，填写以下信息</span><span class="sxs-lookup"><span data-stu-id="ccb1d-261">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="ccb1d-262">**标题（必需）：** 输入评估的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-262">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="ccb1d-263">**请选择一个模板（必需）：** 选择标准或自定义模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-263">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="ccb1d-264">**请选择组或添加新组（必需）：** 选择 "**添加新组**" 并提供一个唯一的组名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-264">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="ccb1d-265">**是否要复制现有组中的数据？（可选）：** 将控件切换到 "打开" 以启用组副本，然后：-**选择一个组（可选）：** 如果已启用组副本，请从组中选择要复制的组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-265">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="ccb1d-266">- **实现详细信息（可选）：** 选择将实现详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-266">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="ccb1d-267">- **测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-267">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="ccb1d-268">- **文档（可选）：** 选择以将文档复制到新组。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-268">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="ccb1d-269">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-269">Select **Save** to create the Assessment.</span></span>

### <a name="viewing-assessments"></a><span data-ttu-id="ccb1d-270">查看评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-270">Viewing Assessments</span></span>

#### <a name="view-an-assessment"></a><span data-ttu-id="ccb1d-271">查看评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-271">View an Assessment</span></span>
  
1. <span data-ttu-id="ccb1d-272">在 "评估" 仪表板中，选择要打开的评估名称，并查看 "操作项" 和 "控件信息"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-272">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="ccb1d-273">下面的示例展示了 Office 365 和 ISO 27001 的评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-273">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="ccb1d-274">第一个视图演示合规性管理器（预览版）中的新操作项视图。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-274">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合规性管理器操作项目视图](media/compliance-manager-action-items.png)

<span data-ttu-id="ccb1d-276">操作按字母顺序列出，并为每个操作分配一个分数和一个所有者。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-276">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="ccb1d-277">选择 "**阅读更多**" 链接以阅读每个操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-277">Select  the **Read More** link to read the details of each Action.</span></span> 

![合规性管理器操作项目视图](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="ccb1d-279">选择 "**查看**" 链接以管理、分配、实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-279">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="ccb1d-280">下面是一个操作示例。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-280">Below is an example Action.</span></span>

![合规性管理器操作视图](media/compliance-manager-action.png)

<span data-ttu-id="ccb1d-282">在早期版本的合规性管理器中，实现要求的工作流是在控件级别执行的。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-282">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="ccb1d-283">合规性监察官会将控件分配给某人以实现该控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-283">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="ccb1d-284">这有两个缺点：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-284">There were two drawbacks to this:</span></span>

- <span data-ttu-id="ccb1d-285">控件通常具有与它们相关联的多个操作，并且分配了控件的用户可能不是完成实现该控件所需的所有操作的正确人员</span><span class="sxs-lookup"><span data-stu-id="ccb1d-285">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="ccb1d-286">将单独的任务组合到单个操作中阻止了用于在合规性管理器（预览版）中自动记录租户配置更改的信号和遥测的收集。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-286">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="ccb1d-287">在合规性管理器（预览）中，工作流过程已从控制级别移至操作级别。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-287">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="ccb1d-288">检查操作时，可使用以下字段来管理操作工作流：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-288">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="ccb1d-289">**为用户分配：** 选择此字段以选择或输入应为其分配此操作的用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-289">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="ccb1d-290">您可以在列表中滚动，或键入名称以查找它，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-290">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="ccb1d-291">**管理文档：** 您可以在 Office 文档、图像文件和屏幕截图、CSV 或 TXT 中的 PowerShell 输出以及 Pdf 中上载实现证据。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-291">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="ccb1d-292">**实现状态：** 用于指示操作的当前实现状态。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-292">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="ccb1d-293">可能的值尚未实现、实现、替代实施、规划且不在范围内。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-293">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="ccb1d-294">**实施日期：** 执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-294">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="ccb1d-295">**测试结果：** 用于指示实现验证的结果。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-295">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="ccb1d-296">可能的值未评估、传递、失败-低风险、失败-中等风险、失败-高风险以及不在范围内。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-296">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="ccb1d-297">**测试日期：** 验证发生的日期。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-297">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="ccb1d-298">**实现说明：** 输入您的组织的实现详细信息，以及您想要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-298">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="ccb1d-299">**测试计划：** 输入此操作的测试计划详细信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-299">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="ccb1d-300">**其他信息：** 输入有关此操作或在组织中实现此操作的方式的任何其他信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-300">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="ccb1d-301">合规性管理器（预览版）还包括在早期版本中找到的基于控件的数据透视。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-301">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="ccb1d-302">选择 "**控件信息**" 仪表板以查看它。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-302">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="ccb1d-303">您可以在评估和模板级别查看控件的信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-303">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="ccb1d-304">下面是用于评估的控件信息仪表板的一个示例。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-304">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合规性管理器控制信息视图](media/compliance-manager-controls-info.png)

<span data-ttu-id="ccb1d-306">对于评估，"控件信息" 仪表板将显示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-306">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="ccb1d-307">一个**组**下拉列表，用于选择要查看的组（使用多个组时）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-307">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="ccb1d-308">一个**评估**下拉列表，用于选择要查看的评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-308">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="ccb1d-309">有关所选评估的元数据，包括：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-309">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="ccb1d-310">**评估的控制措施**的进度指示器，其中显示了已评估的控制总数的控制次数。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-310">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="ccb1d-311">评估的当前**合规性分数**，显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-311">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="ccb1d-312">有关评估中使用的**认证**和**产品**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-312">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="ccb1d-313">评估的当前**状态**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-313">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="ccb1d-314">用于评估的**范围内的服务**的列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-314">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="ccb1d-315">控件的详细信息，按控件系列分组，并提供指向客户操作和 Microsoft 实现详细信息的链接：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-315">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="ccb1d-316">**您的操作**将显示您可以执行以满足部分或全部控件要求的客户操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-316">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="ccb1d-317">许多控件具有与之关联的多个操作，并且与控件关联的所有操作都显示在此处。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-317">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="ccb1d-318">此处的操作与操作仪表板中列出的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-318">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="ccb1d-319">**Microsoft 操作**显示 microsoft 内部框架中应用于所选证书控制的控件列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-319">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="ccb1d-320">对于每个内部控件，选择 "已**实施**" 以查看 Microsoft 的实施和测试详细信息，以及测试结果和测试日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-320">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![合规性管理器 Microsoft 操作视图](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="ccb1d-322">导出评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-322">Export an Assessment</span></span>

<span data-ttu-id="ccb1d-323">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-323">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="ccb1d-324">报告是在创建报告的日期和时间的评估的快照。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-324">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="ccb1d-325">该报告包含有关评估、控制实施状态、控制测试日期、测试结果的所有 Microsoft 和客户托管控件的详细信息，并提供了指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-325">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="ccb1d-326">应在存档评估之前导出评估报告，因为存档的评估不会保留指向已上载文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-326">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="ccb1d-327">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="ccb1d-327">Export an Assessment report</span></span>
  
1. <span data-ttu-id="ccb1d-328">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-328">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="ccb1d-329">在要导出的评估的下拉菜单中，选择 "**组**和**评估**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-329">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="ccb1d-330">选择 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-330">Select the **Export** button.</span></span>

<span data-ttu-id="ccb1d-331">在浏览器会话中，会将评估报告作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-331">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="ccb1d-332">Excel 文件的文件名称默认为评估的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-332">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="archive-a-template-or-an-assessment"></a><span data-ttu-id="ccb1d-333">存档模板或评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-333">Archive a Template or an Assessment</span></span>

<span data-ttu-id="ccb1d-334">如果你完成了模板或评估，并且不再出于合规性目的而需要它，则可以对其进行存档。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-334">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can archive it.</span></span> <span data-ttu-id="ccb1d-335">当存档一个模板或评估时，它将从默认视图中删除，您必须选中 "显示已存档" 复选框以显示它。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-335">When a Template or Assessment is archived, it is removed from the default view, and you must check the Show Archived checkbox to display it.</span></span>

![合规性管理器 Microsoft 操作视图](media/compliance-manager-archive-assessment-view.png)
  
> [!IMPORTANT]
> <span data-ttu-id="ccb1d-337">存档的评估不会保留其到上传的证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-337">Archived Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="ccb1d-338">强烈建议您在存档前导出评估，以保留指向报告中的证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-338">It is highly recommended that you export the Assessment before archiving to retain links to the evidence documents in the report.</span></span>
  
#### <a name="archive-a-template"></a><span data-ttu-id="ccb1d-339">存档模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-339">Archive a Template</span></span>

1. <span data-ttu-id="ccb1d-340">打开 "**模板**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-340">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="ccb1d-341">找到要存档的模板，然后选择 "存档" 图标。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-341">Locate the Template you want to archive and select the archive icon.</span></span>
3. <span data-ttu-id="ccb1d-342">当您看到确认消息时，请选择 "**存档**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-342">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="archive-an-assessment"></a><span data-ttu-id="ccb1d-343">存档评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-343">Archive an Assessment</span></span>

1. <span data-ttu-id="ccb1d-344">打开 "**评估**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-344">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="ccb1d-345">从下拉列表中选择包含您要存档的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-345">Select the **Group** from the dropdown that contains the Assessment you want to archive.</span></span>
3. <span data-ttu-id="ccb1d-346">找到要存档的评估，然后选择 "存档" 图标。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-346">Locate the Assessment you want to archive and select the archive icon.</span></span>
4. <span data-ttu-id="ccb1d-347">当您看到确认消息时，请选择 "**存档**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-347">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="view-archived-assessments"></a><span data-ttu-id="ccb1d-348">查看存档的评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-348">View archived Assessments</span></span>
  
1. <span data-ttu-id="ccb1d-349">打开 "**评估**仪表板" 选项卡并选中 "**显示已存档**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-349">Open the **Assessments** dashboard tab and check the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="ccb1d-350">存档的评估显示在 "**存档评估**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-350">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="ccb1d-351">选择评估名称以打开并查看评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-351">Select the Assessment name to open and view the Assessment.</span></span>

#### <a name="activate-an-archived-assessment"></a><span data-ttu-id="ccb1d-352">激活存档评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-352">Activate an archived Assessment</span></span>

1. <span data-ttu-id="ccb1d-353">在 "**评估**" 选项卡上，选中 "**显示已存档**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-353">On the **Assessments** tab and select the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="ccb1d-354">存档的评估显示在 "**存档评估**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-354">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="ccb1d-355">找到要激活的评估，然后选择激活图标。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-355">Locate the Assessment you want to activate and select the activate icon.</span></span>
4. <span data-ttu-id="ccb1d-356">当您看到确认消息时，请选择 "**激活**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-356">When you see the confirmation message, select **Activate**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="ccb1d-357">控件和操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-357">Controls and Actions</span></span>

<span data-ttu-id="ccb1d-358">控件和操作是合规性管理器（预览版）中使用的主要数据透视。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-358">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="ccb1d-359">在早期版本的合规性管理器中存在的控制轴已得到增强，可在相同的控制系列中显示 Microsoft 和 customer 控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-359">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="ccb1d-360">此 "合并" 视图使以每个控件为基础查看完整的共享职责模型变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-360">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="ccb1d-361">操作透视是合规性管理器（预览版）中的新操作，旨在提供 Microsoft 建议的所有操作的简化视图。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-361">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="ccb1d-362">控件</span><span class="sxs-lookup"><span data-stu-id="ccb1d-362">Controls</span></span>

<span data-ttu-id="ccb1d-363">可以从 "控件信息" 仪表板查看控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-363">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="ccb1d-364">控件表示标准、认证、法规或框架中的要求。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-364">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="ccb1d-365">若要跨多个标准、法规等满足这些要求，并将它们与操作相关联，则所有内容都被视为控制框架。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-365">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="ccb1d-366">例如，像控制框架一样，法规（如 HIPAA）已按节细分，合规性管理器中的 HIPAA 控件使用与这些节相同的编号方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-366">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合规性管理器 Microsoft 控件详细信息](media/compliance-manager-control-details.png)

<span data-ttu-id="ccb1d-368">有三种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-368">There are three types of controls:</span></span>

1. <span data-ttu-id="ccb1d-369">**Microsoft 托管控件：** 这些控件只是 microsoft 有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-369">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="ccb1d-370">它们显示在 "现成" 模板中，并已添加到 Microsoft 的合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-370">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="ccb1d-371">**客户管理的控件：** 这些控件只是客户有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-371">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="ccb1d-372">它们显示在 "现成" 模板中，并由客户添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-372">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="ccb1d-373">**共享管理控件：** 这些控件是在 Microsoft 和客户之间共享责任的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-373">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="ccb1d-374">这些模板显示在 "现成" 模板中，由 Microsoft 添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-374">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="ccb1d-375">客户还可以编辑或禁用 Microsoft 托管的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-375">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="ccb1d-376">Actions 项</span><span class="sxs-lookup"><span data-stu-id="ccb1d-376">Actions Items</span></span>

<span data-ttu-id="ccb1d-377">操作项目是实施标准或法规要求的建议任务，或者用于测试、验证和记录组织的实现要求的任务。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-377">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="ccb1d-378">操作与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-378">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="ccb1d-379">每个控件都有一个或多个与之关联的操作，并且每个操作都可以与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-379">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="ccb1d-380">操作是合规性管理器（预览版）中核心工作流的一部分，因为它们是由组织分配、跟踪和验证的对象。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-380">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="ccb1d-381">分配操作项</span><span class="sxs-lookup"><span data-stu-id="ccb1d-381">Assign Action Items</span></span>
  
1. <span data-ttu-id="ccb1d-382">在 "**操作项**" 仪表板上，选择包含要分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-382">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="ccb1d-383">在 "**评估**" 下拉列表中，选择要为其分配操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-383">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="ccb1d-384">找到要分配的操作，并在 "**所有者**" 列中选择要**查看**、已**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-384">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="ccb1d-385">选择 "**分配用户**" 字段，将显示组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-385">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="ccb1d-386">滚动列表并选择 "用户" 或 "筛选列表" 以通过键入用户的名称来选择用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-386">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="ccb1d-387">在 "实施说明" 字段中，输入您希望向分配的用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-387">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="ccb1d-388">选择 "**保存**" 以分配操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-388">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="ccb1d-389">重新分配操作项</span><span class="sxs-lookup"><span data-stu-id="ccb1d-389">Reassign Action Items</span></span>

<span data-ttu-id="ccb1d-390">通过此函数，组织可以通过将操作重新分配给新用户，删除对用户帐户的任何活动的或未完成的依赖项。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-390">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="ccb1d-391">在 "**操作项**" 仪表板上，选择包含要重新分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-391">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="ccb1d-392">在 "**评估**" 下拉列表中，选择要重新分配其操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-392">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="ccb1d-393">找到要重新分配的操作，并在 "**所有者**" 列中选择要**查看**、**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-393">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="ccb1d-394">从 "**分配用户**" 字段中删除现有用户，然后从用户列表中选择其他用户，或通过键入用户名称来筛选列表以选择用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-394">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="ccb1d-395">在 "实施说明" 字段中，输入您希望向用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-395">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="ccb1d-396">选择 "**保存**" 以重新分配该操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-396">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="ccb1d-397">模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-397">Templates</span></span>

<span data-ttu-id="ccb1d-398">模板是合规性管理器（预览）中与产品和证书（例如，标准、法规、控制框架等）相关联的基本对象。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-398">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="ccb1d-399">可以从 "模板" 仪表板中查看和添加模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-399">Templates can be viewed and added from the Templates dashboard.</span></span>

![合规性管理器 Microsoft 模板仪表板](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="ccb1d-401">仪表板将显示每个模板以及与模板关联的证书和产品、创建模板的日期和上次修改的日期、客户和 Microsoft 托管控件的数量以及最大符合性分数模板，以及模板的状态（例如，"已批准"、"待定审批"、"已导入"）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-401">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="ccb1d-402">内置模板都具有与之关联的内置评估，但您可以根据内置模板创建其他评估，也可以导入自己的模板，并根据这些模板创建自定义评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-402">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="ccb1d-403">创建模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-403">Create a Template</span></span>

<span data-ttu-id="ccb1d-404">您可以通过复制现有模板或导入自定义模板来创建模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-404">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="ccb1d-405">存在必须用于模板数据的特定格式和架构，或者不会将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-405">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="ccb1d-406">可以从此处下载具有正确架构和示例数据的文件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-406">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="ccb1d-407">每个自定义模板应位于一个单独的 Excel 工作簿（.xls 或 .xlsx 格式）中，其中包含五个选项卡：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-407">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="ccb1d-408">模板-评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-408">Template-Assessment</span></span>
2. <span data-ttu-id="ccb1d-409">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="ccb1d-409">ControlFamily</span></span>
3. <span data-ttu-id="ccb1d-410">操作</span><span class="sxs-lookup"><span data-stu-id="ccb1d-410">Actions</span></span>
4. <span data-ttu-id="ccb1d-411">Ownership</span><span class="sxs-lookup"><span data-stu-id="ccb1d-411">Ownership</span></span>
5. <span data-ttu-id="ccb1d-412">Dimensions</span><span class="sxs-lookup"><span data-stu-id="ccb1d-412">Dimensions</span></span>

<span data-ttu-id="ccb1d-413">下面详细说明了每个选项卡中使用的架构。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-413">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="ccb1d-414">模板-"评估" 选项卡</span><span class="sxs-lookup"><span data-stu-id="ccb1d-414">Template-Assessment tab</span></span>

<span data-ttu-id="ccb1d-415">此选项卡包含一个列：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-415">This tab has a single column:</span></span>

- <span data-ttu-id="ccb1d-416">**inScopeServices**：模板的范围内的产品或服务的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-416">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="ccb1d-417">ControlFamily 选项卡</span><span class="sxs-lookup"><span data-stu-id="ccb1d-417">ControlFamily tab</span></span>

<span data-ttu-id="ccb1d-418">此选项卡包含的列定义映射到 "操作" 选项卡上列出的操作的控件，并包含控件名称、系列、标题和说明等详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-418">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="ccb1d-419">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-419">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="ccb1d-420">**controlName：** 来自证书/标准/法规等的控制名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-420">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="ccb1d-421">**controlFamily：** 根据认证/标准、法规等控制家人。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-421">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="ccb1d-422">**controlTitle：** 控制证书/标准/法规等的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-422">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="ccb1d-423">**controlDescription：** 来自认证/标准/法规等的控制说明。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-423">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="ccb1d-424">**controlVersion：** 可选的控制版本信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-424">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="ccb1d-425">示例：对于 NIST 800-53，当前值为修订版4，因此 controlVersion 为4。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-425">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="ccb1d-426">对于 CSA CCM，它是3.0.1。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-426">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="ccb1d-427">**isDisabled：** 使用 TRUE 或 FALSE 可指示控件是否已被禁用。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-427">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="ccb1d-428">**controlType：** 使用 "抄送" 以指示这些控件是客户托管的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-428">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="ccb1d-429">**controlComplianceScore：** 分配给控件的所有操作分数的总和。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-429">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="ccb1d-430">**controlActionTitle：** 此控件的所有 actionTitles 的双分号分隔的列表，如 "操作" 选项卡上所列。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-430">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="ccb1d-431">操作选项卡</span><span class="sxs-lookup"><span data-stu-id="ccb1d-431">Actions tab</span></span>

<span data-ttu-id="ccb1d-432">此选项卡包含定义各个操作的列，并且包含操作标题、所有权和维度等详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-432">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="ccb1d-433">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-433">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="ccb1d-434">**actionTitle：** 操作的标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-434">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="ccb1d-435">每个标题都必须是唯一的，我们建议使用 Pascal 大小写。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-435">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="ccb1d-436">**actionRelatedODVs：** 以分号分隔的 actionTitles 列表，它们是 actionTitle 列中列出的子元素的父项。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-436">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="ccb1d-437">在父/子关系中，父项代表高水位线。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-437">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="ccb1d-438">因此，如果完成父操作，还将完成所有子操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-438">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="ccb1d-439">例如，如果您具有类似的要求，但具有不同的标准定义值（如密码长度），其中一个标准/法规至少需要15个字符，而另一个标准/要求至少需要12个或10个。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-439">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="ccb1d-440">15是此示例中的父级，如果至少配置15个字符，则还应满足在其他评估中建议的12个或10个字符的操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-440">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccb1d-441">ActionRelatedODVs 列是架构的必需列;但是，功能（相关操作）在合规性管理器（预览）中不可用。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-441">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="ccb1d-442">计划在更高版本中添加它。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-442">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="ccb1d-443">**actionDimensionValues：** 使用以下格式的 "维" 选项卡中的适用维度的两个以分号分隔的列表：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-443">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="ccb1d-444">例如：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-444">For example:</span></span>

    ```
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="ccb1d-445">自定义模板中使用的所有维度都必须在导入文件的 "维度" 选项卡上列出，即使它们已列在 "维度" 仪表板上也是如此。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-445">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="ccb1d-446">**actionScore：** 每个操作的数字值，表示该操作的分数。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-446">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="ccb1d-447">我们建议遵循内置评估使用的记分模型，这取决于每个操作的用途和实施。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-447">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="ccb1d-448">**actionOwnership：** 以分号分隔的所有者列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-448">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="ccb1d-449">所有列出的所有者都必须包含在 "所有权" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-449">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="ccb1d-450">**actionDescription：** 每个操作的文本，必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-450">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="ccb1d-451">此字段支持 Markdown 语言，如下所述。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-451">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="ccb1d-452">所有权选项卡</span><span class="sxs-lookup"><span data-stu-id="ccb1d-452">Ownership tab</span></span>

<span data-ttu-id="ccb1d-453">此选项卡包含用于定义每个操作的所有者的列。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-453">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="ccb1d-454">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-454">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="ccb1d-455">**ownershipName：** 所有者/责任方的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-455">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="ccb1d-456">**ownershipDescription：** 所有者/责任方的说明。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-456">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="ccb1d-457">维度选项卡</span><span class="sxs-lookup"><span data-stu-id="ccb1d-457">Dimensions tab</span></span>

<span data-ttu-id="ccb1d-458">此选项卡包含定义可与操作相关联的维度的列。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-458">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="ccb1d-459">此选项卡的列必须按下面列出的顺序在 Excel 中进行排序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-459">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="ccb1d-460">**dimensionKey：** 用于维度的键的列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-460">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="ccb1d-461">例如，产品、认证等。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-461">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="ccb1d-462">**dimensionValue：** 每个维度键的唯一值。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-462">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="ccb1d-463">例如，Office 365、Intune、Azure、自定义产品等。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-463">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="ccb1d-464">**allowMultiSelect：** 使用 TRUE 或 FALSE 可指示可以为单个维度键选择多个维度值。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-464">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="ccb1d-465">在 "说明" 字段中使用 Markdown 语言</span><span class="sxs-lookup"><span data-stu-id="ccb1d-465">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="ccb1d-466">模板和评估支持对某些文本元素和格式使用 Markdown 语言。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-466">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="ccb1d-467">在合规性管理器中使用的 Markdown 语言有三个格式元素：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-467">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="ccb1d-468">项目符号和编号列表</span><span class="sxs-lookup"><span data-stu-id="ccb1d-468">Bullets and Numbered lists</span></span>
- <span data-ttu-id="ccb1d-469">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="ccb1d-469">Hyperlinks</span></span>
- <span data-ttu-id="ccb1d-470">粗体</span><span class="sxs-lookup"><span data-stu-id="ccb1d-470">Boldface</span></span>

<span data-ttu-id="ccb1d-471">项目符号表示为星号而不是 Word 或 Excel 项目符号。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-471">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="ccb1d-472">例如：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-472">For example:</span></span>

```
* Item A
* Item B
* Item C
```

<span data-ttu-id="ccb1d-473">数字表示为数字，但在缩进（每个级别三个空格）和仅用于所有子级别的数字（例如，不带字母）之间使用空格。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-473">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="ccb1d-474">例如：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-474">For example:</span></span>
   1. <span data-ttu-id="ccb1d-475">Item A</span><span class="sxs-lookup"><span data-stu-id="ccb1d-475">Item A</span></span>
   2. <span data-ttu-id="ccb1d-476">项目 B</span><span class="sxs-lookup"><span data-stu-id="ccb1d-476">Item B</span></span>
      1. <span data-ttu-id="ccb1d-477">子项目 A</span><span class="sxs-lookup"><span data-stu-id="ccb1d-477">Sub-item A</span></span>
      2. <span data-ttu-id="ccb1d-478">子项目 B</span><span class="sxs-lookup"><span data-stu-id="ccb1d-478">Sub-item B</span></span>
   3. <span data-ttu-id="ccb1d-479">项目 C</span><span class="sxs-lookup"><span data-stu-id="ccb1d-479">Item C</span></span>
   4. <span data-ttu-id="ccb1d-480">项目 D</span><span class="sxs-lookup"><span data-stu-id="ccb1d-480">Item D</span></span>
      1. <span data-ttu-id="ccb1d-481">子项目 A</span><span class="sxs-lookup"><span data-stu-id="ccb1d-481">Sub-item A</span></span>
      2. <span data-ttu-id="ccb1d-482">子项目 B</span><span class="sxs-lookup"><span data-stu-id="ccb1d-482">Sub-item B</span></span>
   5. <span data-ttu-id="ccb1d-483">Item E</span><span class="sxs-lookup"><span data-stu-id="ccb1d-483">Item E</span></span>

<span data-ttu-id="ccb1d-484">通过在超链接文本周围加上括号并将超链接本身放在右方括号旁边的括号中来构造超链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-484">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="ccb1d-485">例如：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-485">For example:</span></span>

```
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="ccb1d-486">此文本呈现如下：单击[此处](https://www.microsoft.com)转到 Microsoft 主页。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-486">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>
<span data-ttu-id="ccb1d-487">如上面的示例中所示，合规性管理器不呈现带下划线的 Url。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-487">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="ccb1d-488">粗体文本只是文本的每一侧都加粗的两个星号。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-488">Boldface text is just two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="ccb1d-489">例如：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-489">For example:</span></span>

```
**This text will render in bold**
```
<span data-ttu-id="ccb1d-490">**此文本以粗体呈现**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-490">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="ccb1d-491">创建模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-491">Create a Template</span></span>

<span data-ttu-id="ccb1d-492">您可以通过复制现有模板或从 Excel 导入模板数据来创建模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-492">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="ccb1d-493">从 Excel 导入数据时，模板需要两个不同的合规性管理器管理员发布数据（一个发布，另一个用于审批）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-493">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="ccb1d-494">通过复制现有模板创建模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-494">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="ccb1d-495">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-495">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="ccb1d-496">在 "**输入模板名称**" 字段中，为模板提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-496">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="ccb1d-497">选中 "**从现有模板复制**" 复选框，然后从下拉列表中选择要复制的模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-497">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="ccb1d-498">（可选）添加任何其他维度。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-498">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="ccb1d-499">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-499">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="ccb1d-500">通过导入数据创建模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-500">Create a Template by importing data</span></span>

1. <span data-ttu-id="ccb1d-501">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-501">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="ccb1d-502">在 "**输入模板名称**" 字段中，为模板提供一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-502">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="ccb1d-503">从可用列表中选择至少一个维度。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-503">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="ccb1d-504">选择 "**浏览**" 导航到导入文件的位置，选择该文件，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-504">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="ccb1d-505">将验证导入文件，并指示检测到的控件和控件系列的数量。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-505">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="ccb1d-506">如果有错误，则会向包含错误详细信息的导入文件的修改版本提供链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-506">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="ccb1d-507">必须先解决所有错误，然后才会导入数据。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-507">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="ccb1d-508">数据通过验证后，选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-508">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="ccb1d-509">导入的模板将显示在 "**模板**" 仪表板上，其状态为 "已**导入**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-509">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="ccb1d-510">选择省略号（...），然后选择 "**发布**" 以发布模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-510">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="ccb1d-511">当出现确认消息时，请选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-511">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="ccb1d-512">模板状态将更改为 "**待审批**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-512">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="ccb1d-513">另一个具有合规性管理器管理员角色的用户必须批准模板仪表板中的模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-513">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="ccb1d-514">他们必须选择省略号（...），然后选择 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-514">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="ccb1d-515">当出现确认消息时，选择 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-515">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="ccb1d-516">现在即可使用该模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-516">The Template is now ready for use.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="ccb1d-517">自定义模板</span><span class="sxs-lookup"><span data-stu-id="ccb1d-517">Customize a Template</span></span>

<span data-ttu-id="ccb1d-518">可以通过其他自定义控件自定义模板。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-518">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="ccb1d-519">所有自定义控件都被视为客户托管的控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-519">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="ccb1d-520">向模板中添加自定义控件</span><span class="sxs-lookup"><span data-stu-id="ccb1d-520">Add a custom control to a Template</span></span>

1. <span data-ttu-id="ccb1d-521">打开要修改的**模板**。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-521">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="ccb1d-522">选择 " **+ 添加**自定义控件"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-522">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="ccb1d-523">从下拉列表中选择一个**控制族**，或输入一个新的控制族（如果不存在）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-523">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="ccb1d-524">为 "**控件 ID** " 字段中的控件提供一个唯一的名称或 ID。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-524">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="ccb1d-525">在 "**标题**" 字段中提供控件标题。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-525">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="ccb1d-526">提供 "**说明**" 字段中控件的要求和其他信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-526">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="ccb1d-527">选择 "**分配客户**操作"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-527">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="ccb1d-528">找到要分配给控件的操作：</span><span class="sxs-lookup"><span data-stu-id="ccb1d-528">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="ccb1d-529">使用 "**按维度筛选**" 以使用分配给操作的维度来查找和列出它们。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-529">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="ccb1d-530">使用 "**按所有者筛选**" 以使用分配给操作的所有者来查找和列出它们。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-530">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="ccb1d-531">从下拉列表中选择**操作类型**以按类型列出操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-531">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="ccb1d-532">输入要查找的操作的标题并将其列出。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-532">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="ccb1d-533">使用步骤8中的条件，将显示**匹配操作**的列表。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-533">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="ccb1d-534">选择要分配给控件的第一个操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-534">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="ccb1d-535">将显示操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-535">The details of the Action appear.</span></span> <span data-ttu-id="ccb1d-536">选择要使用的**说明**，然后选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-536">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="ccb1d-537">对每个要分配的其他操作重复步骤9和10。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-537">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="ccb1d-538">选择所有适用的操作后，选择 "**分配**"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-538">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="ccb1d-539">选择 "**保存**" 以保存新控件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-539">Select **Save** to save the new control.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="ccb1d-540">将模板导出到 JSON</span><span class="sxs-lookup"><span data-stu-id="ccb1d-540">Export a Template to JSON</span></span>

<span data-ttu-id="ccb1d-541">合规性管理器（预览版）还支持将模板导出为 JavaScript 对象表示法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-541">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="ccb1d-542">这使您可以与支持 JSON 的其他系统交换合规性管理器数据。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-542">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="ccb1d-543">报告</span><span class="sxs-lookup"><span data-stu-id="ccb1d-543">Reports</span></span>

<span data-ttu-id="ccb1d-544">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-544">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="ccb1d-545">报告是在导出的日期和时间进行评估的快照。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-545">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="ccb1d-546">该报告包含 Microsoft 和客户托管的控件的详细信息，用于评估、控制实施状态、控制测试日期、测试结果以及指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-546">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="ccb1d-547">应在存档评估之前将其导出，因为存档的评估不会保留指向已上载文档的链接。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-547">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="ccb1d-548">导出评估</span><span class="sxs-lookup"><span data-stu-id="ccb1d-548">Export an Assessment</span></span>

1. <span data-ttu-id="ccb1d-549">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-549">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="ccb1d-550">在下拉菜单中选择要导出的评估的组和评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-550">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="ccb1d-551">选择 "导出"。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-551">Select Export.</span></span> <span data-ttu-id="ccb1d-552">将评估导出作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-552">The Assessment export is downloaded as an Excel file.</span></span>

![合规性管理器评估 Excel 报告](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="ccb1d-554">权限</span><span class="sxs-lookup"><span data-stu-id="ccb1d-554">Permissions</span></span>

<span data-ttu-id="ccb1d-555">下表介绍了每个合规性管理器权限及其允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-555">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="ccb1d-556">该表还指示分配了每个权限的角色。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-556">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="ccb1d-557">**Azure AD 全局读取器**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-557">**Azure AD Global Reader**</span></span>|<span data-ttu-id="ccb1d-558">**合规性管理器读者**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-558">**Compliance Manager Reader**</span></span>|<span data-ttu-id="ccb1d-559">**合规性管理器参与者**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-559">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="ccb1d-560">**合规性管理器评估员**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-560">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="ccb1d-561">**合规性管理器管理员**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-561">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="ccb1d-562">**门户管理员**</span><span class="sxs-lookup"><span data-stu-id="ccb1d-562">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ccb1d-563">**读取数据：** 用户可以读取但不能编辑数据（模板数据和租户管理除外）。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-563">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="ccb1d-564">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-564">X</span></span> | <span data-ttu-id="ccb1d-565">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-565">X</span></span> | <span data-ttu-id="ccb1d-566">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-566">X</span></span> | <span data-ttu-id="ccb1d-567">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-567">X</span></span> | <span data-ttu-id="ccb1d-568">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-568">X</span></span>  | <span data-ttu-id="ccb1d-569">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-569">X</span></span>  |<span data-ttu-id="ccb1d-570">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-570">X</span></span> |
|<span data-ttu-id="ccb1d-571">**编辑数据：** 除了 "测试结果" 和 "测试日期" 字段（"模板数据" 和 "租户管理" 除外）之外，用户可以编辑所有字段。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-571">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="ccb1d-572">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-572">X</span></span> | <span data-ttu-id="ccb1d-573">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-573">X</span></span>  | <span data-ttu-id="ccb1d-574">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-574">X</span></span> | <span data-ttu-id="ccb1d-575">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-575">X</span></span> |
|<span data-ttu-id="ccb1d-576">**编辑测试结果：** 用户可以编辑 "测试结果" 和 "测试日期" 字段。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-576">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="ccb1d-577">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-577">X</span></span> | <span data-ttu-id="ccb1d-578">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-578">X</span></span> | <span data-ttu-id="ccb1d-579">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-579">X</span></span> |
|<span data-ttu-id="ccb1d-580">**管理评估：** 用户可以创建、存档和删除评估。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-580">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="ccb1d-581">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-581">X</span></span> | <span data-ttu-id="ccb1d-582">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-582">X</span></span> |
|<span data-ttu-id="ccb1d-583">**管理主数据：** 用户可以查看、编辑和删除模板数据和租户管理数据。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-583">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="ccb1d-584">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-584">X</span></span> | <span data-ttu-id="ccb1d-585">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-585">X</span></span> |
|<span data-ttu-id="ccb1d-586">**管理用户：** 用户可以将组织中的其他用户添加到 Reader、投稿人、评估员和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-586">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="ccb1d-587">只有组织中具有全局管理员角色的用户才可以在门户管理员角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="ccb1d-587">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="ccb1d-588">X</span><span class="sxs-lookup"><span data-stu-id="ccb1d-588">X</span></span> |
