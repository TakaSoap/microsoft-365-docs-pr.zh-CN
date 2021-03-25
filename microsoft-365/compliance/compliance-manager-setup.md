---
title: Microsoft 合规性管理器入门
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 设置 Microsoft 合规性管理器用户权限和角色，并配置操作自动化测试。 管理用户历史记录并筛选仪表板视图。
ms.openlocfilehash: 3b32ac5a82bbc726c5bf61859266e0561ca7f53c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199215"
---
# <a name="get-started-with-compliance-manager"></a><span data-ttu-id="7f553-104">合规性管理器入门</span><span class="sxs-lookup"><span data-stu-id="7f553-104">Get started with Compliance Manager</span></span>

<span data-ttu-id="7f553-105">**本文内容：** 本文可帮助你设置合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="7f553-105">**In this article:** This article helps you set up Compliance Manager.</span></span> <span data-ttu-id="7f553-106">了解如何访问 **合规性** 管理器 **、设置角色和权限** 以及配置 **改进操作自动测试**。</span><span class="sxs-lookup"><span data-stu-id="7f553-106">Learn how to **access** Compliance Manager, **set roles and permissions**, and configure **automatic testing of improvement actions**.</span></span> <span data-ttu-id="7f553-107">演练 **合规性管理器仪表板** 并了解主要页面：改进行动页、解决方案页、评估页和评估模板页。</span><span class="sxs-lookup"><span data-stu-id="7f553-107">Walk through **your Compliance Manager dashboard** and understand the main pages: the improvement actions page, the solutions page, the assessments page, and the assessment templates page.</span></span>

## <a name="who-can-access-compliance-manager"></a><span data-ttu-id="7f553-108">谁可以访问合规性管理器</span><span class="sxs-lookup"><span data-stu-id="7f553-108">Who can access Compliance Manager</span></span>

<span data-ttu-id="7f553-109">合规性管理器适用于具有 Office 365 和 Microsoft 365 许可证的组织，以及美国政府社区云 (GCC) 中等和 GCC 高客户。</span><span class="sxs-lookup"><span data-stu-id="7f553-109">Compliance Manager is available to organizations with Office 365 and Microsoft 365 licenses, and to US Government Community Cloud (GCC) Moderate and GCC High customers.</span></span> <span data-ttu-id="7f553-110">评估可用性和管理功能取决于您的许可协议。</span><span class="sxs-lookup"><span data-stu-id="7f553-110">Assessment availability and management capabilities depend on your licensing agreement.</span></span>  <span data-ttu-id="7f553-111">[查看服务说明详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="7f553-111">[View service description details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7f553-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="7f553-112">Before you begin</span></span>

<span data-ttu-id="7f553-113">组织的 Microsoft 365 全局管理员可能是第一个访问合规性管理器的用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-113">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Manager.</span></span> <span data-ttu-id="7f553-114">我们建议全局管理员登录并设置用户权限，如第一次访问合规性管理器时所述。</span><span class="sxs-lookup"><span data-stu-id="7f553-114">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Manager for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="7f553-115">登录</span><span class="sxs-lookup"><span data-stu-id="7f553-115">Sign in</span></span>

1. <span data-ttu-id="7f553-116">转到 [Microsoft 365](https://compliance.microsoft.com/) 合规中心 **，然后使用** Microsoft 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="7f553-116">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global administrator account.</span></span>
2. <span data-ttu-id="7f553-117">选择 **左侧导航** 窗格中的"合规性管理器"。</span><span class="sxs-lookup"><span data-stu-id="7f553-117">Select **Compliance Manager** on the left navigation pane.</span></span> <span data-ttu-id="7f553-118">你将到达合规性管理器 [仪表板](#understand-the-compliance-manager-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="7f553-118">You'll arrive at your [Compliance Manager dashboard](#understand-the-compliance-manager-dashboard).</span></span>

<span data-ttu-id="7f553-119">访问合规性管理器的直接链接是 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) 。</span><span class="sxs-lookup"><span data-stu-id="7f553-119">The direct link to access Compliance Manager is [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="7f553-120">设置用户权限和分配角色</span><span class="sxs-lookup"><span data-stu-id="7f553-120">Set user permissions and assign roles</span></span>

<span data-ttu-id="7f553-121">合规性管理器使用基于角色的访问控制 (RBAC) 权限模型。</span><span class="sxs-lookup"><span data-stu-id="7f553-121">Compliance Manager uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="7f553-122">只有分配了角色的用户才能访问合规性管理器，并且每个用户允许的操作受角色 [类型限制](#role-types)。</span><span class="sxs-lookup"><span data-stu-id="7f553-122">Only users who are assigned a role may access Compliance Manager, and the actions allowed by each user are restricted by [role type](#role-types).</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="7f553-123">在何处设置权限</span><span class="sxs-lookup"><span data-stu-id="7f553-123">Where to set permissions</span></span>

<span data-ttu-id="7f553-124">拥有组织的全局管理员角色的人可以设置合规性管理器的用户权限。</span><span class="sxs-lookup"><span data-stu-id="7f553-124">The person holding the global admin role for your organization can set user permissions for Compliance Manager.</span></span> <span data-ttu-id="7f553-125">权限可以在 Office 365 安全与合规中心& Azure AD (Azure Active Directory) 。</span><span class="sxs-lookup"><span data-stu-id="7f553-125">Permissions can be set in the Office 365 Security & Compliance center as well as in Azure Active Directory (Azure AD).</span></span>

> [!NOTE]
> <span data-ttu-id="7f553-126">美国政府社区组织 (GCC) 客户只能在 Azure AD 中为合规性管理器设置用户权限和角色。</span><span class="sxs-lookup"><span data-stu-id="7f553-126">Customers in US Government Community (GCC) High environments can only set user permissions and roles for Compliance Manager in Azure AD.</span></span> <span data-ttu-id="7f553-127">有关 Azure AD 说明和角色类型定义，请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="7f553-127">See below for Azure AD instructions and role type definitions.</span></span>

<span data-ttu-id="7f553-128">若要在 Office 365 安全与合规中心中设置权限&分配角色，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7f553-128">To set permissions and assign roles in the Office 365 Security & Compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="7f553-129">转到 [Office 365 安全与&中心，](https://protection.office.com/) 然后选择左侧导航 **上的权限** 。</span><span class="sxs-lookup"><span data-stu-id="7f553-129">Go to the [Office 365 Security & Compliance Center](https://protection.office.com/) and select **Permissions** on the left navigation.</span></span>

2. <span data-ttu-id="7f553-130">查找要添加一个或多个用户的角色组，并选中组名称左侧的框。</span><span class="sxs-lookup"><span data-stu-id="7f553-130">Find the role group to which you want to add one or more users, and check the box to the left of the group name.</span></span> <span data-ttu-id="7f553-131"> (请参阅 [下面的角色和相关函数列表](#role-types)。</span><span class="sxs-lookup"><span data-stu-id="7f553-131">(See the [list of roles and related functions below](#role-types).</span></span> <span data-ttu-id="7f553-132">角色组名称模仿角色名称。) </span><span class="sxs-lookup"><span data-stu-id="7f553-132">The role group names mimic the role name.)</span></span>

3. <span data-ttu-id="7f553-133">在该组的飞出窗格中，选择"成员 **"** 标题下的 **"编辑** "。</span><span class="sxs-lookup"><span data-stu-id="7f553-133">On the flyout pane for that group, select **Edit** under the **Members** header.</span></span>

4. <span data-ttu-id="7f553-134">选择 **"选择成员"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-134">Select **Choose members**.</span></span> <span data-ttu-id="7f553-135">将显示另一个弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="7f553-135">Another flyout window will appear.</span></span>

5. <span data-ttu-id="7f553-136">选择 **+ 添加** 以选择要添加到组的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-136">Select **+ Add** to choose one or more users to add to the group.</span></span>

6. <span data-ttu-id="7f553-137">选中要添加的名称旁边的复选框，然后选择底部的 **"添加** "按钮。</span><span class="sxs-lookup"><span data-stu-id="7f553-137">Select the checkbox next to the names you want to add, then select the **Add** button at the bottom.</span></span>

7. <span data-ttu-id="7f553-138">分配完用户后，选择"完成"，然后选择"**保存**"，然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-138">When you’re done assigning users, select **Done**, then select **Save**, then **Close**.</span></span>

##### <a name="more-about-the-office-365-security--compliance-center"></a><span data-ttu-id="7f553-139">有关 Office 365 安全与&中心</span><span class="sxs-lookup"><span data-stu-id="7f553-139">More about the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="7f553-140">详细了解 Office [365 安全](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)与合规中心&权限。</span><span class="sxs-lookup"><span data-stu-id="7f553-140">Learn more about [permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="7f553-141">如果您无法访问 Office 365 安全与合规中心，或者您需要访问 Microsoft 服务信任门户中的经典版本的合规性管理器，则服务信任门户中的管理员设置提供了另一种分配角色 (查看说明[) 。](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)</span><span class="sxs-lookup"><span data-stu-id="7f553-141">If you don't have access to the Office 365 Security and Compliance Center, or if you need to access the classic version of Compliance Manager in the Microsoft Service Trust Portal,  the Admin settings in the Service Trust Portal provides another way to assign roles ([view instructions](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)).</span></span> <span data-ttu-id="7f553-142">请注意，此类角色的功能更加有限。</span><span class="sxs-lookup"><span data-stu-id="7f553-142">Be aware that such roles are more limited in their functionality.</span></span>

##### <a name="more-about-azure-ad"></a><span data-ttu-id="7f553-143">有关 Azure AD 的更多信息</span><span class="sxs-lookup"><span data-stu-id="7f553-143">More about Azure AD</span></span>

<span data-ttu-id="7f553-144">若要在 Azure AD 中分配角色和设置权限，请参阅使用 Azure Active Directory 向用户分配管理员 [和非管理员角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="7f553-144">To assign roles and set permissions in Azure AD, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

<span data-ttu-id="7f553-145">具有 Azure AD 标识的用户没有 Office 365 或 Microsoft 365 订阅，将无法访问 Microsoft 365 合规中心中的合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="7f553-145">Users with Azure AD identities who don't have Office 365 or Microsoft 365 subscriptions won't be able to access Compliance Manager in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7f553-146">若要在访问合规性管理器方面寻求帮助 [，请联系](mailto:cmresearch@microsoft.com)cmresearch@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="7f553-146">To seek assistance in accessing Compliance Manager, contact [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).</span></span>

### <a name="role-types"></a><span data-ttu-id="7f553-147">角色类型</span><span class="sxs-lookup"><span data-stu-id="7f553-147">Role types</span></span>

<span data-ttu-id="7f553-148">下表显示了合规性管理器中每个角色允许的功能。</span><span class="sxs-lookup"><span data-stu-id="7f553-148">The table below shows the functions allowed by each role in Compliance Manager.</span></span> <span data-ttu-id="7f553-149">该表还显示每个 [Azure AD 角色如何](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 映射到合规性管理器角色。</span><span class="sxs-lookup"><span data-stu-id="7f553-149">The table also shows how each [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to Compliance Manager roles.</span></span> <span data-ttu-id="7f553-150">用户至少需要合规性管理器读者角色或 Azure AD 全局读者角色，以访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="7f553-150">Users will need at least the Compliance Manager reader role, or Azure AD global reader role, to access Compliance Manager.</span></span>


| <span data-ttu-id="7f553-151">用户可以：</span><span class="sxs-lookup"><span data-stu-id="7f553-151">User can:</span></span> | <span data-ttu-id="7f553-152">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="7f553-152">Compliance Manager role</span></span> | <span data-ttu-id="7f553-153">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="7f553-153">Azure AD role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="7f553-154">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="7f553-154">**Read but not edit data**</span></span>| <span data-ttu-id="7f553-155">合规性管理器读者</span><span class="sxs-lookup"><span data-stu-id="7f553-155">Compliance Manager Reader</span></span>  | <span data-ttu-id="7f553-156">Azure AD 全局读者、安全读者</span><span class="sxs-lookup"><span data-stu-id="7f553-156">Azure AD Global reader, Security reader</span></span> | 
| <span data-ttu-id="7f553-157">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="7f553-157">**Edit data**</span></span>| <span data-ttu-id="7f553-158">合规性管理器贡献</span><span class="sxs-lookup"><span data-stu-id="7f553-158">Compliance Manager Contribution</span></span> | <span data-ttu-id="7f553-159">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="7f553-159">Compliance Administrator</span></span> | 
| <span data-ttu-id="7f553-160">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="7f553-160">**Edit test results**</span></span>| <span data-ttu-id="7f553-161">合规性管理器评估</span><span class="sxs-lookup"><span data-stu-id="7f553-161">Compliance Manager Assessment</span></span> | <span data-ttu-id="7f553-162">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="7f553-162">Compliance Administrator</span></span> | 
| <span data-ttu-id="7f553-163">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="7f553-163">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="7f553-164">合规性管理器管理</span><span class="sxs-lookup"><span data-stu-id="7f553-164">Compliance Manager Administration</span></span> | <span data-ttu-id="7f553-165">合规性管理员、合规性数据管理员、安全管理员</span><span class="sxs-lookup"><span data-stu-id="7f553-165">Compliance Administrator, Compliance Data Administrator, Security Administrator</span></span>  | 
| <span data-ttu-id="7f553-166">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="7f553-166">**Assign users**</span></span>| <span data-ttu-id="7f553-167">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f553-167">Global Administrator</span></span> | <span data-ttu-id="7f553-168">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f553-168">Global Administrator</span></span> | 

## <a name="settings-for-automated-testing-and-user-history"></a><span data-ttu-id="7f553-169">自动测试和用户历史记录的设置</span><span class="sxs-lookup"><span data-stu-id="7f553-169">Settings for automated testing and user history</span></span>

<span data-ttu-id="7f553-170">Microsoft 365 合规中心中的合规性管理器设置允许你启用和禁用改进操作自动测试。</span><span class="sxs-lookup"><span data-stu-id="7f553-170">The Compliance Manager settings in the Microsoft 365 compliance center allow you to enable and disable automatic testing of improvement actions.</span></span> <span data-ttu-id="7f553-171">这些设置还允许您管理与改进操作关联的用户数据，包括将改进操作重新分配给其他用户的能力。</span><span class="sxs-lookup"><span data-stu-id="7f553-171">The settings also allow you to manage the data of users associated to improvement actions, including the ability to reassign improvement actions to a different user.</span></span>  <span data-ttu-id="7f553-172">只有具有全局管理员或合规性管理器管理员角色的人才能访问合规性管理器设置。</span><span class="sxs-lookup"><span data-stu-id="7f553-172">Only people with a global administrator or Compliance Manager Administrator role can access the Compliance Manager settings.</span></span>

> [!NOTE]
> <span data-ttu-id="7f553-173">GCC 高环境中的客户无法使用自动测试功能，因为安全分数在这些环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="7f553-173">The automated testing feature is not available to customers in GCC High environments because Secure Score isn't available in these environments.</span></span> <span data-ttu-id="7f553-174">GCC 高客户需要手动实施和测试其改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-174">GCC High customers will need to manually implement and test their improvement actions.</span></span>

### <a name="set-up-automated-testing"></a><span data-ttu-id="7f553-175">设置自动测试</span><span class="sxs-lookup"><span data-stu-id="7f553-175">Set up automated testing</span></span>

<span data-ttu-id="7f553-176">合规性管理器中的一些改进操作也受 [Microsoft 安全](../security/defender/microsoft-secure-score.md)分数 监视。</span><span class="sxs-lookup"><span data-stu-id="7f553-176">Some improvement actions in Compliance Manager are also monitored by [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="7f553-177">可以设置对共同监视的操作的自动测试，这意味着在安全分数中对操作进行测试和更新时，这些结果会与合规性管理器中的相同操作同步，并计入合规性分数。</span><span class="sxs-lookup"><span data-stu-id="7f553-177">You can set up automated testing of actions that are jointly monitored, which means that when an action is tested and updated in Secure Score, those results synch with the same actions in Compliance Manager and count toward your compliance score.</span></span>

<span data-ttu-id="7f553-178">默认情况下，对使用合规性管理器的组织启用自动测试。</span><span class="sxs-lookup"><span data-stu-id="7f553-178">Automatic testing is turned on by default for organizations new to Compliance Manager.</span></span> <span data-ttu-id="7f553-179">首次部署 Microsoft 365 或 Office 365 时，安全分数需要大约 7 天的时间，以完全收集数据，并纳入合规性分数中。</span><span class="sxs-lookup"><span data-stu-id="7f553-179">When you first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your compliance score.</span></span>  <span data-ttu-id="7f553-180">启用自动测试后，不会更新该操作的测试日期，但其测试状态将更新。</span><span class="sxs-lookup"><span data-stu-id="7f553-180">When automated testing is turned on, the action’s test date won’t be updated, but its test status will update.</span></span> <span data-ttu-id="7f553-181">创建新评估后，分数将自动包含 Microsoft 控制分数和安全分数集成。</span><span class="sxs-lookup"><span data-stu-id="7f553-181">When new assessments are created, scores automatically include Microsoft control scores and Secure Score integration.</span></span>

<span data-ttu-id="7f553-182">组织的全局管理员可以随时更改自动测试的设置。</span><span class="sxs-lookup"><span data-stu-id="7f553-182">The global administrator for your organization can change the settings for automated testing at any time.</span></span> <span data-ttu-id="7f553-183">您可以关闭常见改进操作自动化测试，或为单个操作启用它。</span><span class="sxs-lookup"><span data-stu-id="7f553-183">You can turn off automated testing for common improvement actions, or turn it on for individual actions.</span></span> <span data-ttu-id="7f553-184">按照下面的说明更改自动测试设置。</span><span class="sxs-lookup"><span data-stu-id="7f553-184">Follow the instructions below to change your automated testing settings.</span></span>

#### <a name="to-manage-your-automated-testing-settings"></a><span data-ttu-id="7f553-185">若要管理自动测试设置：</span><span class="sxs-lookup"><span data-stu-id="7f553-185">To manage your automated testing settings:</span></span>

1. <span data-ttu-id="7f553-186">从 Microsoft 365 合规中心中的任意位置选择[左侧导航上的"设置"。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f553-186">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7f553-187">在设置页上，选择合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="7f553-187">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="7f553-188">从 **左侧导航栏中** 选择"自动测试"。</span><span class="sxs-lookup"><span data-stu-id="7f553-188">Select **Automated testing** from the left navigation.</span></span>

4. <span data-ttu-id="7f553-189">选择适用的按钮以针对所有改进操作启用自动测试，针对所有操作将其关闭，或按单个操作打开。</span><span class="sxs-lookup"><span data-stu-id="7f553-189">Select the applicable button to turn on automatic testing for all improvement actions, turn it off for all actions, or turn on by individual action.</span></span>

5. <span data-ttu-id="7f553-190">如果您选择" **启用每个改进操作"，** 则列表将显示可供选择的所有可用改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-190">If you select **Turn on per improvement action**, a list will show all the available improvement actions to choose from.</span></span>  <span data-ttu-id="7f553-191">选中要自动测试的任何操作旁边的框。</span><span class="sxs-lookup"><span data-stu-id="7f553-191">Check the box next to any action you want automatically tested.</span></span>

6. <span data-ttu-id="7f553-192">选择 **"保存** "以保存设置。</span><span class="sxs-lookup"><span data-stu-id="7f553-192">Select **Save** to save your settings.</span></span> <span data-ttu-id="7f553-193">You'll receive a confirmation message at the top of your screen that your selection was saved.</span><span class="sxs-lookup"><span data-stu-id="7f553-193">You’ll receive a confirmation message at the top of your screen that your selection was saved.</span></span> <span data-ttu-id="7f553-194">如果收到失败通知，请重试。</span><span class="sxs-lookup"><span data-stu-id="7f553-194">If you receive a failure notice, try again.</span></span>

<span data-ttu-id="7f553-195">**注意：** 只有全局管理员可以打开或关闭所有操作自动更新。</span><span class="sxs-lookup"><span data-stu-id="7f553-195">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="7f553-196">合规性管理器管理员可以为单个操作（而不是全局性的所有操作）启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="7f553-196">The Compliance Manager Administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="manage-user-history"></a><span data-ttu-id="7f553-197">管理用户历史记录</span><span class="sxs-lookup"><span data-stu-id="7f553-197">Manage user history</span></span>

<span data-ttu-id="7f553-198">管理 **用户历史记录** 设置可帮助您快速识别哪些用户已使用合规性管理器中的改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-198">The **Manage user history** settings help you quickly identify which users have worked with improvement actions in Compliance Manager.</span></span> <span data-ttu-id="7f553-199">与改进操作关联的可识别用户数据包括完成的任何实施和测试工作、他们上载的文档以及他们输入的任何注释。</span><span class="sxs-lookup"><span data-stu-id="7f553-199">The identifiable user data associated with improvement actions includes any implementation and testing work done, documents they uploaded, and any notes they entered.</span></span> <span data-ttu-id="7f553-200">了解和检索此类数据对于组织自己的合规性需求可能是必需的。</span><span class="sxs-lookup"><span data-stu-id="7f553-200">Understanding and retrieving this type of data may be necessary for your organization’s own compliance needs.</span></span>

<span data-ttu-id="7f553-201">用户历史记录设置还允许您将一个用户的所有改进操作重新分配给另一个用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-201">The user history settings also allow you to reassign all improvement actions from one user to another.</span></span>

<span data-ttu-id="7f553-202">**若要查找用户历史记录设置，请执行以下操作：**</span><span class="sxs-lookup"><span data-stu-id="7f553-202">**To find the user history settings:**</span></span>

1. <span data-ttu-id="7f553-203">从 Microsoft 365 合规中心中的任意位置选择[左侧导航上的"设置"。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f553-203">Select Settings on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7f553-204">在设置页上，选择合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="7f553-204">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="7f553-205">从 **左侧导航栏中选择** "管理用户历史记录"。</span><span class="sxs-lookup"><span data-stu-id="7f553-205">Select **Manage user history** from the left navigation.</span></span>

<span data-ttu-id="7f553-206">" **管理用户历史记录** "页按电子邮件地址显示分配给改进操作的所有用户的列表。</span><span class="sxs-lookup"><span data-stu-id="7f553-206">The **manage user history** page shows a list of all users by email address who are assigned to an improvement action.</span></span> <span data-ttu-id="7f553-207">通过 **键入** 特定用户的电子邮件地址，使用"搜索"按钮快速查找该用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-207">Use the **Search** button to quickly find a specific user by typing in their email address.</span></span>

<span data-ttu-id="7f553-208">在每个用户的电子邮件地址右侧，"选择"下拉菜单提供导出报告、重新分配改进操作或删除历史记录的选项。</span><span class="sxs-lookup"><span data-stu-id="7f553-208">To the right of each user’s email address, the **Select** drop-down menu provides options to  export a report, reassign improvement actions, or delete history.</span></span> <span data-ttu-id="7f553-209">有关每个选项的详细信息，请参阅下面的每个部分。</span><span class="sxs-lookup"><span data-stu-id="7f553-209">See each section below for details about each option.</span></span>

#### <a name="export-a-report-of-user-history-data"></a><span data-ttu-id="7f553-210">导出用户历史记录数据报告</span><span class="sxs-lookup"><span data-stu-id="7f553-210">Export a report of user history data</span></span>

<span data-ttu-id="7f553-211">可以导出包含当前分配给用户的改进操作列表的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="7f553-211">You can export an Excel file containing a list of improvement actions currently assigned to a user.</span></span>  <span data-ttu-id="7f553-212">该报告还列出了该用户上载的任何证据文件。</span><span class="sxs-lookup"><span data-stu-id="7f553-212">The report also lists any evidence files uploaded by that user.</span></span> <span data-ttu-id="7f553-213">此信息可帮助您重新分配开放改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-213">This information can help you reassign open improvement actions.</span></span>

<span data-ttu-id="7f553-214">该报告反映自创建日期起改进操作的状态。</span><span class="sxs-lookup"><span data-stu-id="7f553-214">The report reflects the improvement action’s status as of its creation date.</span></span> <span data-ttu-id="7f553-215">这不是之前对状态或工作分配的所有更改的历史报告， (从改进操作页面[导出) 。](compliance-manager-improvement-actions.md#export-a-report)</span><span class="sxs-lookup"><span data-stu-id="7f553-215">It’s not a historical report of all previous changes to its status or assignment (learn how to [export a report from your improvement actions page](compliance-manager-improvement-actions.md#export-a-report)).</span></span>

<span data-ttu-id="7f553-216">**按照以下步骤按用户导出报告：**</span><span class="sxs-lookup"><span data-stu-id="7f553-216">**Follow the steps below to export a report by user:**</span></span>

1. <span data-ttu-id="7f553-217">从 Microsoft 365 合规中心中的任意位置选择[左侧导航上的"设置"。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f553-217">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7f553-218">在设置页上，选择合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="7f553-218">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="7f553-219">从 **左侧导航中选择** "管理用户历史记录"。</span><span class="sxs-lookup"><span data-stu-id="7f553-219">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="7f553-220">通过搜索列表电子邮件地址，或选择"搜索"并输入用户的电子邮件地址来查找目标用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-220">Find your intended user by searching the list email addresses, or by selecting **Search** and entering the user’s email address.</span></span>

5. <span data-ttu-id="7f553-221">从"**选择"** 下拉菜单中，选择"导出 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-221">From the **Select** drop-down menu, choose **Export report**.</span></span>

6. <span data-ttu-id="7f553-222">生成报表的 Excel 文件后，可以将其打开并保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7f553-222">Once the Excel file of your report is generated, you can open it and save it to your local machine.</span></span>

#### <a name="reassign-improvement-actions-to-another-user"></a><span data-ttu-id="7f553-223">将改进操作重新分配给其他用户</span><span class="sxs-lookup"><span data-stu-id="7f553-223">Reassign improvement actions to another user</span></span>

<span data-ttu-id="7f553-224">您可以将改进操作从一个用户重新分配到另一个用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-224">You can reassign improvement actions from one user to another.</span></span> <span data-ttu-id="7f553-225">重新分配操作时，文档上载历史记录不会更改，但最初上载文档的用户的名称不再显示在改进操作中。</span><span class="sxs-lookup"><span data-stu-id="7f553-225">When you reassign an action, the document upload history doesn't change, but the name of the user who originally uploaded the documentation no longer appears within the improvement action.</span></span>

<span data-ttu-id="7f553-226">**按照以下步骤将改进操作重新分配给其他用户：**</span><span class="sxs-lookup"><span data-stu-id="7f553-226">**Follow the steps below to reassign improvement actions to another user:**</span></span>

1. <span data-ttu-id="7f553-227">从 Microsoft 365 合规中心中的任意位置选择[左侧导航上的"设置"。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f553-227">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7f553-228">在设置页上，选择合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="7f553-228">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="7f553-229">从 **左侧导航中选择** "管理用户历史记录"。</span><span class="sxs-lookup"><span data-stu-id="7f553-229">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="7f553-230">通过搜索列表电子邮件地址或选择"搜索"并输入该用户的电子邮件地址来查找用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-230">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="7f553-231">从"**选择"** 下拉菜单中，选择"**重新分配改进操作"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-231">From the **Select** drop-down menu, choose **Reassign improvement actions**.</span></span> <span data-ttu-id="7f553-232">将显示 **"重新分配改进操作** "飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="7f553-232">The **Reassign improvement actions** flyout pane will appear.</span></span>

6. <span data-ttu-id="7f553-233">在 **"搜索用户** "字段中，输入要为其分配改进操作的用户的名称或 *电子邮件地址*。</span><span class="sxs-lookup"><span data-stu-id="7f553-233">In the **Search users** field, enter the name or email address of the user you want assign the improvement actions *to*.</span></span>

7. <span data-ttu-id="7f553-234">当你在"将分配到改进操作"下看到预期用户的名称时，请选择该用户，然后选择"**分配操作"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-234">When you see the name of your intended user under **Improvement actions will be assigned to**, select the user, then select **Assign actions**.</span></span>

8. <span data-ttu-id="7f553-235">重新分配完成后，你将在飞出窗格中看到确认消息，确认之前用户的所有改进操作已重新分配到新用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-235">When the reassignment is complete, you’ll see a confirmation message in the flyout pane confirming that all improvement actions from the previous user have been reassigned to the new user.</span></span> <span data-ttu-id="7f553-236">如果收到重新分配失败通知，请关闭窗口并重试。</span><span class="sxs-lookup"><span data-stu-id="7f553-236">If you receive a reassignment failure notice, close the window and try again.</span></span> <span data-ttu-id="7f553-237">若要关闭飞出窗格，请选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-237">To close the flyout pane, select **Done**.</span></span>

<span data-ttu-id="7f553-238">新接受者将收到已分配给改进操作的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f553-238">The new assignee receives an email that they've been assigned to an improvement action.</span></span> <span data-ttu-id="7f553-239">电子邮件包含指向改进操作的详细信息页面的直接链接。</span><span class="sxs-lookup"><span data-stu-id="7f553-239">The email contains a direct link into the improvement action's details page.</span></span>
 
 > [!NOTE]
> <span data-ttu-id="7f553-240">如果重新分配具有挂起更新的操作，如果在重新分配后接受更新，则指向重新分配电子邮件中的操作的直接链接将中断。</span><span class="sxs-lookup"><span data-stu-id="7f553-240">If you reassign an action that has a pending update, the direct link to the action in the reassignment email will break if the update is accepted after reassignment.</span></span> <span data-ttu-id="7f553-241">可以通过在接受更新后将操作重新分配给用户来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="7f553-241">You can fix this by re-assigning the action to the user after the update is accepted.</span></span> <span data-ttu-id="7f553-242">详细了解改进 [操作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="7f553-242">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

#### <a name="delete-user-history"></a><span data-ttu-id="7f553-243">删除用户历史记录</span><span class="sxs-lookup"><span data-stu-id="7f553-243">Delete user history</span></span>

<span data-ttu-id="7f553-244">删除用户的历史记录将删除他们作为改进操作的所有者，并且会将其姓名从合规性管理器中的所有其他字段中删除。</span><span class="sxs-lookup"><span data-stu-id="7f553-244">Deleting a user’s history will remove them as an owner of improvement actions, and will remove their name from all other fields in Compliance Manager.</span></span> <span data-ttu-id="7f553-245">删除用户的历史记录时，在分配新用户之前，他们拥有的改进操作不会显示"分配给"值。</span><span class="sxs-lookup"><span data-stu-id="7f553-245">When you delete a user’s history, the improvement actions they owned will not display an **Assigned to** value until a new user is assigned.</span></span> <span data-ttu-id="7f553-246">上载到改进操作的任何文档将显示已删除的用户，以更改已删除用户的名称。</span><span class="sxs-lookup"><span data-stu-id="7f553-246">Any documents uploaded to the improvement action will show **User removed** in place of the deleted user’s name.</span></span> <span data-ttu-id="7f553-247">删除用户历史记录是永久性的。</span><span class="sxs-lookup"><span data-stu-id="7f553-247">Deleting user history is permanent.</span></span>

<span data-ttu-id="7f553-248">若要删除用户的历史记录，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7f553-248">To delete a user’s history, follow the steps below:</span></span>

1. <span data-ttu-id="7f553-249">从 Microsoft 365 合规中心中的任意位置选择[左侧导航上的"设置"。](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f553-249">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="7f553-250">在设置页上，选择合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="7f553-250">On the settings page, select **Compliance Manager**.</span></span>

3. <span data-ttu-id="7f553-251">从 **左侧导航中选择** "管理用户历史记录"。</span><span class="sxs-lookup"><span data-stu-id="7f553-251">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="7f553-252">通过搜索列表电子邮件地址或选择"搜索"并输入该用户的电子邮件地址来查找用户。</span><span class="sxs-lookup"><span data-stu-id="7f553-252">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="7f553-253">从"**选择"** 下拉菜单中，选择"删除 **历史记录"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-253">From the **Select** drop-down menu, choose **Delete history**.</span></span>

6. <span data-ttu-id="7f553-254">将出现一个要求您确认永久删除用户历史记录的窗口。</span><span class="sxs-lookup"><span data-stu-id="7f553-254">A window appears asking you to confirm the permanent deletion of the user’s history.</span></span> <span data-ttu-id="7f553-255">若要继续删除，请选择"删除 **历史记录"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-255">To continue with deletion, select **Delete history**.</span></span> <span data-ttu-id="7f553-256">若要在不删除历史记录的情况下保留，请选择"取消 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-256">To leave without deleting the history, select **Cancel**.</span></span>

7. <span data-ttu-id="7f553-257">你将返回到"管理用户历史记录"页，顶部会显示一条确认消息，指出该用户的历史记录已删除。</span><span class="sxs-lookup"><span data-stu-id="7f553-257">You’ll arrive back at the **Manage user history** page with a confirmation message at the top that the history for the user was deleted.</span></span>

## <a name="understand-the-compliance-manager-dashboard"></a><span data-ttu-id="7f553-258">了解合规性管理器仪表板</span><span class="sxs-lookup"><span data-stu-id="7f553-258">Understand the Compliance Manager dashboard</span></span>

<span data-ttu-id="7f553-259">合规性管理器仪表板旨在为您提供当前合规性状况的概览。</span><span class="sxs-lookup"><span data-stu-id="7f553-259">The Compliance Manager dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="7f553-260">![合规性管理器 - 仪表板](../media/compliance-manager-dashboard.png "合规性管理器仪表板")</span><span class="sxs-lookup"><span data-stu-id="7f553-260">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="7f553-261">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="7f553-261">Overall compliance score</span></span>

<span data-ttu-id="7f553-262">合规性分数特别推荐在最上面。</span><span class="sxs-lookup"><span data-stu-id="7f553-262">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="7f553-263">它根据完成解决关键数据保护标准和法规的改进操作可达到的分数来显示百分比。</span><span class="sxs-lookup"><span data-stu-id="7f553-263">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span> <span data-ttu-id="7f553-264">Microsoft 操作 [中的](compliance-manager-assessments.md#microsoft-actions-tab)分数（管理我的 Microsoft）也计入合规性分数中。</span><span class="sxs-lookup"><span data-stu-id="7f553-264">Points from [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab), which are managed my Microsoft, also count toward your compliance score.</span></span>

<span data-ttu-id="7f553-265">当你首次访问合规性管理器时，你的初始分数基于 [Microsoft 365 数据保护基线](compliance-manager-assessments.md#data-protection-baseline-default-assessment)。</span><span class="sxs-lookup"><span data-stu-id="7f553-265">When you come to Compliance Manager for the first time, your initial score is based on the [Microsoft 365 data protection baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment).</span></span> <span data-ttu-id="7f553-266">此基线评估可供所有组织使用，是一组包含常见行业法规和标准的控制措施。</span><span class="sxs-lookup"><span data-stu-id="7f553-266">This baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="7f553-267">合规性管理器可扫描现有的 Microsoft 365 解决方案，并基于当前的隐私和安全设置进行初始评估。</span><span class="sxs-lookup"><span data-stu-id="7f553-267">Compliance Manager scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="7f553-268">添加与组织相关的评估时，分数将变得更加有意义。</span><span class="sxs-lookup"><span data-stu-id="7f553-268">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

<span data-ttu-id="7f553-269">**了解更多信息：**[了解如何计算合规性分数](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="7f553-269">**Learn more:** [Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="7f553-270">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="7f553-270">Key improvement actions</span></span>

<span data-ttu-id="7f553-271">本部分列出了你现在可以采取的最大改进措施，以对整体合规性分数产生最大正面影响。</span><span class="sxs-lookup"><span data-stu-id="7f553-271">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="7f553-272">选择 **"查看所有改进操作** "以转到您的改进操作页面。</span><span class="sxs-lookup"><span data-stu-id="7f553-272">Select **View all improvement actions** to go to your improvement actions page.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="7f553-273">影响分数的解决方案</span><span class="sxs-lookup"><span data-stu-id="7f553-273">Solutions that affect your score</span></span>

<span data-ttu-id="7f553-274">本节重点介绍包含可直接影响分数的改进操作的解决方案，以及这些解决方案中未完成的改进操作的数量。</span><span class="sxs-lookup"><span data-stu-id="7f553-274">This section highlights solutions containing improvement actions that can positively impact your score, and the number of outstanding improvement actions in those solutions.</span></span> <span data-ttu-id="7f553-275">选择 **"查看所有解决方案** "以访问您的解决方案页面。</span><span class="sxs-lookup"><span data-stu-id="7f553-275">Select **View all solutions** to visit your solutions page.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="7f553-276">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="7f553-276">Compliance score breakdown</span></span>

<span data-ttu-id="7f553-277">本部分以两种不同的方式为你提供分数的更详细视图：</span><span class="sxs-lookup"><span data-stu-id="7f553-277">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="7f553-278">**类别**：显示数据保护类别（如"保护信息"或"管理设备"）中总分数的百分比。</span><span class="sxs-lookup"><span data-stu-id="7f553-278">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="7f553-279">**评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）评估的进度百分比。</span><span class="sxs-lookup"><span data-stu-id="7f553-279">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="7f553-280">筛选仪表板视图</span><span class="sxs-lookup"><span data-stu-id="7f553-280">Filtering your dashboard view</span></span>

<span data-ttu-id="7f553-281">可以筛选仪表板视图，以便仅查看与特定法规和标准、解决方案、操作类型、评估组或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="7f553-281">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="7f553-282">通过此方式筛选视图还将筛选仪表板上的分数，显示根据筛选条件在可能的总分数中已实现的分数。</span><span class="sxs-lookup"><span data-stu-id="7f553-282">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="7f553-283">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="7f553-283">To apply filters:</span></span>

1. <span data-ttu-id="7f553-284">选择 **仪表板** 右上角的"筛选"。</span><span class="sxs-lookup"><span data-stu-id="7f553-284">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="7f553-285">从"筛选器"飞出 **窗格中选择** 筛选条件，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-285">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="7f553-286">应用筛选器后，你将看到实时调整的分数。</span><span class="sxs-lookup"><span data-stu-id="7f553-286">After you apply a filter, you’ll see your score adjusted in real time.</span></span> <span data-ttu-id="7f553-287">合规性分数百分比和细分信息以及改进操作和解决方案现在仅与筛选器条件涵盖的数据相关。</span><span class="sxs-lookup"><span data-stu-id="7f553-287">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="7f553-288">如果注销合规性管理器，则重新登录时将保留筛选的视图。</span><span class="sxs-lookup"><span data-stu-id="7f553-288">If you sign out of Compliance Manager, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="7f553-289">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="7f553-289">To remove filters:</span></span>

- <span data-ttu-id="7f553-290">在合规性 **分数上方的** "应用的筛选器"标题中，选择要删除的单个筛选器旁边的 **"X";** 或</span><span class="sxs-lookup"><span data-stu-id="7f553-290">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="7f553-291">选择 **仪表板** 右上角的"筛选器"，然后在"筛选器"飞出窗格中，选择"**清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-291">Select **Filter** on the upper-right side of your dashboard, then on the **Filters** flyout pane, select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="7f553-292">"改进操作"页</span><span class="sxs-lookup"><span data-stu-id="7f553-292">Improvement actions page</span></span>

<span data-ttu-id="7f553-293">[改进操作](compliance-manager-improvement-actions.md) 是由组织管理的操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-293">[Improvement actions](compliance-manager-improvement-actions.md) are actions managed by your organization.</span></span> <span data-ttu-id="7f553-294">使用改进操作有助于集中您的合规性活动，并符合数据保护法规和标准。</span><span class="sxs-lookup"><span data-stu-id="7f553-294">Working with improvement actions helps to centralize your compliance activities and align with data protection regulations and standards.</span></span> <span data-ttu-id="7f553-295">每个改进操作都提供了详细的实施指南和链接，将你引导到适当的解决方案中。</span><span class="sxs-lookup"><span data-stu-id="7f553-295">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="7f553-296">可以将改进操作分配给贵组织的用户，以执行实施和测试工作。</span><span class="sxs-lookup"><span data-stu-id="7f553-296">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="7f553-297">您还可以在改进操作中存储文档、备注和记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="7f553-297">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="7f553-298">查看改进操作</span><span class="sxs-lookup"><span data-stu-id="7f553-298">View your improvement actions</span></span>

<span data-ttu-id="7f553-299">合规性管理器仪表板显示关键 **改进操作。**</span><span class="sxs-lookup"><span data-stu-id="7f553-299">The Compliance Manager dashboard shows your **key improvement actions.**</span></span> <span data-ttu-id="7f553-300">若要查看所有改进操作，请选择仪表板上的"改进操作"选项卡，将您带到您的改进操作页面。</span><span class="sxs-lookup"><span data-stu-id="7f553-300">To view all of your improvement actions, select the Improvement actions tab on your dashboard, which brings you to your improvement actions page.</span></span> <span data-ttu-id="7f553-301">还可以在仪表板上的关键改进操作列表下方选择"查看所有改进操作"，以进入改进操作页面。</span><span class="sxs-lookup"><span data-stu-id="7f553-301">You can also select View all improvement actions underneath the list of key improvement actions on your dashboard to get to your improvement actions page.</span></span>

<span data-ttu-id="7f553-302">"改进操作"页显示组织管理的所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-302">The improvement actions page shows all of the improvement actions that are managed by your organization.</span></span> <span data-ttu-id="7f553-303">可在每项评估中查看由 Microsoft 管理的操作， ([Microsoft 行动](compliance-manager-assessments.md#microsoft-actions-tab)) 。</span><span class="sxs-lookup"><span data-stu-id="7f553-303">Actions that are managed by Microsoft can be viewed within each assessment (learn more about [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab)).</span></span>

<span data-ttu-id="7f553-304">如果您的改进操作页上有一个很长的操作列表，则筛选视图可能会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="7f553-304">If you have a long list of actions on your improvement actions page, it may be helpful to filter your view.</span></span> <span data-ttu-id="7f553-305">选择 **操作** 列表右上角的"筛选"。</span><span class="sxs-lookup"><span data-stu-id="7f553-305">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="7f553-306">当出现 **"筛选器** "飞出窗格时，根据法规和标准、解决方案和组选择条件。</span><span class="sxs-lookup"><span data-stu-id="7f553-306">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="7f553-307">您还可以通过在右上角选择"组"来自定义视图。</span><span class="sxs-lookup"><span data-stu-id="7f553-307">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="7f553-308">从下拉菜单中，选择以按组、解决方案、类别、操作类型或状态进行查看。</span><span class="sxs-lookup"><span data-stu-id="7f553-308">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="7f553-309">此页面的默认视图不会显示测试状态为"已通过"的改进 **操作**。</span><span class="sxs-lookup"><span data-stu-id="7f553-309">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="7f553-310">若要查看已通过测试的操作，请选中"筛选器 **"** 飞出窗格中的"通过"框。</span><span class="sxs-lookup"><span data-stu-id="7f553-310">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="7f553-311">仅测试状态为 **"已通过"的操作** 计入分数。</span><span class="sxs-lookup"><span data-stu-id="7f553-311">Only actions with a test status of **Passed** count toward your score.</span></span> <span data-ttu-id="7f553-312">某些操作可能会显示挂起 **的更新标签。**</span><span class="sxs-lookup"><span data-stu-id="7f553-312">Some actions may show a **pending update label.**</span></span> <span data-ttu-id="7f553-313">详细了解改进 [操作的更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。</span><span class="sxs-lookup"><span data-stu-id="7f553-313">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

<span data-ttu-id="7f553-314">"改进操作"页显示每个改进操作的以下数据点：</span><span class="sxs-lookup"><span data-stu-id="7f553-314">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="7f553-315">**已实现** 点数：通过完成操作在可用总数中实现的点数</span><span class="sxs-lookup"><span data-stu-id="7f553-315">**Points achieved**: the number of points achieved out of the total available by completing the action</span></span>
- <span data-ttu-id="7f553-316">**法规**：与操作相关的法规或标准</span><span class="sxs-lookup"><span data-stu-id="7f553-316">**Regulations**: the regulations or standards pertaining to the action</span></span>
- <span data-ttu-id="7f553-317">**组**：将操作分配到的组</span><span class="sxs-lookup"><span data-stu-id="7f553-317">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="7f553-318">**解决方案**：可以执行该操作的解决方案</span><span class="sxs-lookup"><span data-stu-id="7f553-318">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="7f553-319">**评估**：包含行动的评估</span><span class="sxs-lookup"><span data-stu-id="7f553-319">**Assessments**: the assessments that contain the action</span></span>
- <span data-ttu-id="7f553-320">**类别**：相关的数据保护类别 (例如，保护信息、管理设备等) </span><span class="sxs-lookup"><span data-stu-id="7f553-320">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="7f553-321">**测试状态**：</span><span class="sxs-lookup"><span data-stu-id="7f553-321">**Test status**:</span></span>
    - <span data-ttu-id="7f553-322">**无** - 未记录状态更新</span><span class="sxs-lookup"><span data-stu-id="7f553-322">**None** – no status update recorded</span></span>
    - <span data-ttu-id="7f553-323">**未评估** - 测试尚未开始</span><span class="sxs-lookup"><span data-stu-id="7f553-323">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="7f553-324">**已通过** - 实现已成功测试</span><span class="sxs-lookup"><span data-stu-id="7f553-324">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="7f553-325">**风险较低失败** - 测试失败，风险低</span><span class="sxs-lookup"><span data-stu-id="7f553-325">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="7f553-326">**中风险失败** - 测试失败，中等风险</span><span class="sxs-lookup"><span data-stu-id="7f553-326">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="7f553-327">**高风险失败** - 测试失败，高风险</span><span class="sxs-lookup"><span data-stu-id="7f553-327">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="7f553-328">**超出范围** - 操作不在评估范围内，不会影响分数</span><span class="sxs-lookup"><span data-stu-id="7f553-328">**Out of scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="7f553-329">**要检测** - 对于手动测试，指示已实现但未测试操作;对于自动测试，指示操作正在等待自动化结果</span><span class="sxs-lookup"><span data-stu-id="7f553-329">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="7f553-330">**无法检测到** - 无法确定自动状态</span><span class="sxs-lookup"><span data-stu-id="7f553-330">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="7f553-331">**部分测试** – 自动评分，表示部分分数</span><span class="sxs-lookup"><span data-stu-id="7f553-331">**Partially tested** – automated scoring that awards partial points</span></span>

<span data-ttu-id="7f553-332">**了解更多信息：**[了解如何分配和执行改进操作。](compliance-manager-improvement-actions.md)</span><span class="sxs-lookup"><span data-stu-id="7f553-332">**Learn more:** [See how to assign and perform work on improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="7f553-333">"解决方案"页</span><span class="sxs-lookup"><span data-stu-id="7f553-333">Solutions page</span></span>

<span data-ttu-id="7f553-334">"解决方案"页显示按解决方案组织的挣值和潜在点数的共享。</span><span class="sxs-lookup"><span data-stu-id="7f553-334">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="7f553-335">从此视图中查看剩余点和改进操作可帮助您了解哪些解决方案需要立即关注。</span><span class="sxs-lookup"><span data-stu-id="7f553-335">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="7f553-336">通过选择合规性管理器仪表板 **上的"解决方案** "选项卡查找解决方案页面。</span><span class="sxs-lookup"><span data-stu-id="7f553-336">Find the solutions page by selecting the **Solutions** tab on your Compliance Manager dashboard.</span></span> <span data-ttu-id="7f553-337">还可以在仪表板右上角 **的**"解决方案"下方选择"查看影响分数的所有解决方案"。</span><span class="sxs-lookup"><span data-stu-id="7f553-337">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="7f553-338">筛选解决方案视图</span><span class="sxs-lookup"><span data-stu-id="7f553-338">Filtering your solutions view</span></span>

<span data-ttu-id="7f553-339">筛选解决方案视图：</span><span class="sxs-lookup"><span data-stu-id="7f553-339">To filter your view of solutions:</span></span>

1. <span data-ttu-id="7f553-340">选择 **评估** 列表左上角的"筛选"。</span><span class="sxs-lookup"><span data-stu-id="7f553-340">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="7f553-341">在" **筛选器** "飞出窗格中，在所需条件旁边放置 (标准和法规、解决方案、操作类型、合规性管理器组、类别) 。</span><span class="sxs-lookup"><span data-stu-id="7f553-341">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="7f553-342">选择" **应用"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="7f553-342">Select the **Apply** button.</span></span> <span data-ttu-id="7f553-343">筛选器窗格将关闭，并且你将看到已筛选视图。</span><span class="sxs-lookup"><span data-stu-id="7f553-343">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="7f553-344">您还可以通过从评估列表上方的"组"下拉菜单中选择分组类型，来修改视图以查看按组、产品或法规的评估。</span><span class="sxs-lookup"><span data-stu-id="7f553-344">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-action-from-the-solution-page"></a><span data-ttu-id="7f553-345">从解决方案页面采取措施</span><span class="sxs-lookup"><span data-stu-id="7f553-345">Taking action from the solution page</span></span>

<span data-ttu-id="7f553-346">"解决方案"页显示与改进操作有关的组织解决方案。</span><span class="sxs-lookup"><span data-stu-id="7f553-346">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="7f553-347">此表列出了每个解决方案对总体分数的贡献、该解决方案中实现和可能实现的分数，以及该解决方案中分组的可增加分数的剩余改进操作数。</span><span class="sxs-lookup"><span data-stu-id="7f553-347">The table lists each solution’s contribution to your overall score, the points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="7f553-348">可以通过两种方法从此屏幕采取措施：</span><span class="sxs-lookup"><span data-stu-id="7f553-348">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="7f553-349">在预期解决方案行的"剩余操作" **列下，** 选择超链接编号。</span><span class="sxs-lookup"><span data-stu-id="7f553-349">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="7f553-350">你将看到改进操作屏幕的筛选视图，其中显示了该解决方案的未经测试的改进操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-350">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="7f553-351">在预期解决方案行的"打开解决方案"列下，选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f553-351">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="7f553-352">你将在 Microsoft 365 和 Office 365 安全与合规中心内看到解决方案或位置，你可以在这里采取建议的操作。</span><span class="sxs-lookup"><span data-stu-id="7f553-352">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="7f553-353">评估页面</span><span class="sxs-lookup"><span data-stu-id="7f553-353">Assessments page</span></span>

<span data-ttu-id="7f553-354">评估页面列出了你 [为](compliance-manager-assessments.md) 组织设置的所有评估。</span><span class="sxs-lookup"><span data-stu-id="7f553-354">The assessments page lists all the [assessments](compliance-manager-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="7f553-355">合规性分数分母由所有跟踪评估确定。</span><span class="sxs-lookup"><span data-stu-id="7f553-355">Your compliance score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="7f553-356">当你添加更多评估时，你将看到改进操作页上列出了更多改进操作，并且合规性分数分母增加。</span><span class="sxs-lookup"><span data-stu-id="7f553-356">As you add more assessments, you'll see more improvement actions listed on your improvement actions page, and your compliance score denominator increases.</span></span>

<span data-ttu-id="7f553-357">页面 **顶部附近的** 已激活模板计数器显示在可供组织使用的模板总数中当前使用的活动评估模板的数量。</span><span class="sxs-lookup"><span data-stu-id="7f553-357">The **activated templates** counter near the top of the page shows the number of active assessment templates currently in use out of the total number of templates available for your organization to use.</span></span> <span data-ttu-id="7f553-358">有关详细信息 [，请参阅](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) 模板类型。</span><span class="sxs-lookup"><span data-stu-id="7f553-358">See [Template type](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) for more information.</span></span>

<span data-ttu-id="7f553-359">"评估"页汇总了有关每个评估的关键信息：</span><span class="sxs-lookup"><span data-stu-id="7f553-359">The assessments page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="7f553-360">**评估**：评估名称</span><span class="sxs-lookup"><span data-stu-id="7f553-360">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="7f553-361">**状态**：</span><span class="sxs-lookup"><span data-stu-id="7f553-361">**Status**:</span></span>
    - <span data-ttu-id="7f553-362">**完成** - 所有控件的状态为"已通过"，或至少传递一个控件，其余控件处于"超出范围"</span><span class="sxs-lookup"><span data-stu-id="7f553-362">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="7f553-363">**不完整** – 至少一个控件的状态为"失败"</span><span class="sxs-lookup"><span data-stu-id="7f553-363">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="7f553-364">**无** - 所有控件均未经过测试</span><span class="sxs-lookup"><span data-stu-id="7f553-364">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="7f553-365">**进行** 中 - 改进操作具有任何其他状态，包括"正在进行"、"部分信用"或"未检测"</span><span class="sxs-lookup"><span data-stu-id="7f553-365">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="7f553-366">**评估进度**：完成时完成的工作百分比，以成功测试的控制措施数为基准</span><span class="sxs-lookup"><span data-stu-id="7f553-366">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="7f553-367">**改进操作**：满足控件实施要求已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="7f553-367">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="7f553-368">**Microsoft 操作**：满足 Microsoft 控件实现已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="7f553-368">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="7f553-369">**组**：评估所属组的名称</span><span class="sxs-lookup"><span data-stu-id="7f553-369">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="7f553-370">**产品**：关联的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="7f553-370">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="7f553-371">**法规**：适用于评估的法规标准、策略或法律</span><span class="sxs-lookup"><span data-stu-id="7f553-371">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="7f553-372">筛选评估视图</span><span class="sxs-lookup"><span data-stu-id="7f553-372">Filtering your assessments view</span></span>

<span data-ttu-id="7f553-373">若要筛选你查看评估：</span><span class="sxs-lookup"><span data-stu-id="7f553-373">To filter you view of assessments:</span></span>

1. <span data-ttu-id="7f553-374">选择 **评估** 列表左上角的"筛选"。</span><span class="sxs-lookup"><span data-stu-id="7f553-374">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="7f553-375">在" **筛选器"** 飞出窗格中，检查所需的条件。</span><span class="sxs-lookup"><span data-stu-id="7f553-375">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="7f553-376">选择" **应用"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="7f553-376">Select the **Apply** button.</span></span> <span data-ttu-id="7f553-377">筛选器窗格将关闭，并且你将看到已筛选视图。</span><span class="sxs-lookup"><span data-stu-id="7f553-377">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="7f553-378">您还可以通过从评估列表上方的"组"下拉菜单中选择分组类型，来修改视图以查看按组、产品或法规的评估。</span><span class="sxs-lookup"><span data-stu-id="7f553-378">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="7f553-379">默认评估</span><span class="sxs-lookup"><span data-stu-id="7f553-379">Default assessment</span></span>

<span data-ttu-id="7f553-380">默认情况下，你将在评估页面上看到数据保护[](compliance-manager-assessments.md#data-protection-baseline-default-assessment)基线评估。</span><span class="sxs-lookup"><span data-stu-id="7f553-380">By default, you'll see the [Data Protection Baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment) assessment on the assessments page.</span></span> <span data-ttu-id="7f553-381">合规性管理器还提供了多个用于生成 [评估](compliance-manager-templates-list.md) 的预建模板。</span><span class="sxs-lookup"><span data-stu-id="7f553-381">Compliance Manager also provides several pre-built [templates](compliance-manager-templates-list.md) for building assessments.</span></span>

## <a name="assessment-templates-page"></a><span data-ttu-id="7f553-382">评估模板页</span><span class="sxs-lookup"><span data-stu-id="7f553-382">Assessment templates page</span></span>

<span data-ttu-id="7f553-383">模板是在合规性管理器中创建评估的框架。</span><span class="sxs-lookup"><span data-stu-id="7f553-383">A template is a framework for creating an assessment in Compliance Manager.</span></span> <span data-ttu-id="7f553-384">评估模板页显示模板列表和关键详细信息。</span><span class="sxs-lookup"><span data-stu-id="7f553-384">The assessment templates page displays a list of templates and key details.</span></span> <span data-ttu-id="7f553-385">该列表包括合规性管理器提供的模板，以及组织已修改或创建的任何模板。</span><span class="sxs-lookup"><span data-stu-id="7f553-385">The list includes templates provided by Compliance Manager as well as any templates your organization has modified or created.</span></span> <span data-ttu-id="7f553-386">你可以应用筛选器以根据认证、产品范围、国家/地区、行业以及创建者来查找模板。</span><span class="sxs-lookup"><span data-stu-id="7f553-386">You can apply filters to find a template based on certification, product scope, country, industry, and who created it.</span></span>

<span data-ttu-id="7f553-387">页面 **顶部附近的** 已激活模板计数器显示在可供组织使用的模板总数中当前使用的活动评估模板的数量。</span><span class="sxs-lookup"><span data-stu-id="7f553-387">The **activated templates** counter near the top of the page shows the number of active assessment templates currently in use out of the total number of templates available for your organization to use.</span></span> <span data-ttu-id="7f553-388">有关详细信息 [，请参阅](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) 模板类型。</span><span class="sxs-lookup"><span data-stu-id="7f553-388">See [Template type](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) for more information.</span></span>

<span data-ttu-id="7f553-389">Select a template from its row to bring up its details page， which contains a description of the template and further information about certification， scope， and controls details.</span><span class="sxs-lookup"><span data-stu-id="7f553-389">Select a template from its row to bring up its details page, which contains a description of the template and further information about certification, scope, and controls details.</span></span> <span data-ttu-id="7f553-390">在此页中，您可以选择相应的按钮来创建评估、将模板数据导出到 Excel 或修改模板。</span><span class="sxs-lookup"><span data-stu-id="7f553-390">From this page you can select the appropriate buttons to create an assessment, export the template data to Excel, or modify the template.</span></span>

<span data-ttu-id="7f553-391">**了解更多信息：**[了解如何使用评估模板](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="7f553-391">**Learn more:** [Read how to work with assessment templates](compliance-manager-templates.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="7f553-392">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7f553-392">Next step</span></span>
<span data-ttu-id="7f553-393">通过设置评估 [自定义合规性管理器](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="7f553-393">Customize Compliance Manager by [setting up assessments](compliance-manager-assessments.md).</span></span>