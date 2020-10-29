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
description: 设置 Microsoft 合规性管理器用户权限和角色，并配置自动执行的操作测试。 管理用户历史记录和筛选你的仪表板视图。
ms.openlocfilehash: 141ddc8ac371b1a36c69ee79b5438408f8da19e8
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791890"
---
# <a name="get-started-with-compliance-manager"></a><span data-ttu-id="f9334-104">合规性管理器入门</span><span class="sxs-lookup"><span data-stu-id="f9334-104">Get started with Compliance Manager</span></span>

<span data-ttu-id="f9334-105">**本文内容：** 本文将帮助您设置合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="f9334-105">**In this article:** This article helps you set up Compliance Manager.</span></span> <span data-ttu-id="f9334-106">了解如何 **访问** 合规性管理器、 **设置角色和权限** 以及配置 **改进操作的自动测试** 。</span><span class="sxs-lookup"><span data-stu-id="f9334-106">Learn how to **access** Compliance Manager, **set roles and permissions** , and configure **automatic testing of improvement actions** .</span></span> <span data-ttu-id="f9334-107">浏览 **合规性管理器仪表板** 并了解主要页面： "改进操作" 页、"解决方案" 页、"评估" 页和 "评估模板" 页。</span><span class="sxs-lookup"><span data-stu-id="f9334-107">Walk through **your Compliance Manager dashboard** and understand the main pages: the improvement actions page, the solutions page, the assessments page, and the assessment templates page.</span></span>

## <a name="who-can-access-compliance-manager"></a><span data-ttu-id="f9334-108">谁可以访问合规性管理器</span><span class="sxs-lookup"><span data-stu-id="f9334-108">Who can access Compliance Manager</span></span>

<span data-ttu-id="f9334-109">合规性管理器可供具有 Office 365 和 Microsoft 365 许可证的组织使用。</span><span class="sxs-lookup"><span data-stu-id="f9334-109">Compliance Manager is available to organizations with Office 365 and Microsoft 365 licenses.</span></span> <span data-ttu-id="f9334-110">评估可用性和管理功能取决于许可协议。</span><span class="sxs-lookup"><span data-stu-id="f9334-110">Assessment availability and management capabilities depend on your licensing agreement.</span></span>  <span data-ttu-id="f9334-111">[查看服务说明详细信息](https://go.microsoft.com/fwlink/?linkid=2132371)。</span><span class="sxs-lookup"><span data-stu-id="f9334-111">[View service description details](https://go.microsoft.com/fwlink/?linkid=2132371).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f9334-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="f9334-112">Before you begin</span></span>

<span data-ttu-id="f9334-113">您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性管理器的用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-113">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Manager.</span></span> <span data-ttu-id="f9334-114">我们建议全局管理员登录并设置用户权限，如下文首次访问合规性管理器时所述。</span><span class="sxs-lookup"><span data-stu-id="f9334-114">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Manager for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="f9334-115">登录</span><span class="sxs-lookup"><span data-stu-id="f9334-115">Sign in</span></span>

1. <span data-ttu-id="f9334-116">请转到 [microsoft 365 合规性中心](https://compliance.microsoft.com/) 并使用 microsoft 365 全局管理员帐户 **登录** 。</span><span class="sxs-lookup"><span data-stu-id="f9334-116">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global administrator account.</span></span>
2. <span data-ttu-id="f9334-117">在左侧导航窗格中选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-117">Select **Compliance Manager** on the left navigation pane.</span></span> <span data-ttu-id="f9334-118">你将收到 [合规性管理器仪表板](#understand-the-compliance-manager-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="f9334-118">You'll arrive at your [Compliance Manager dashboard](#understand-the-compliance-manager-dashboard).</span></span>

<span data-ttu-id="f9334-119">指向 access 合规性管理器的直接链接为 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-119">The direct link to access Compliance Manager is [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="f9334-120">设置用户权限并分配角色</span><span class="sxs-lookup"><span data-stu-id="f9334-120">Set user permissions and assign roles</span></span>

<span data-ttu-id="f9334-121">合规性管理器使用基于角色的访问控制 (RBAC) 权限模型。</span><span class="sxs-lookup"><span data-stu-id="f9334-121">Compliance Manager uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="f9334-122">只有分配有角色的用户才可以访问合规性管理器，并且每个用户允许的操作受 [角色类型](#role-types)的限制。</span><span class="sxs-lookup"><span data-stu-id="f9334-122">Only users who are assigned a role may access Compliance Manager, and the actions allowed by each user are restricted by [role type](#role-types).</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="f9334-123">设置权限的位置</span><span class="sxs-lookup"><span data-stu-id="f9334-123">Where to set permissions</span></span>

<span data-ttu-id="f9334-124">拥有组织的全局管理员角色的人员可以在 Microsoft 365 合规性中心中设置用户权限，也可以在 Azure Active Directory (Azure AD) 中设置用户权限。</span><span class="sxs-lookup"><span data-stu-id="f9334-124">The person holding the global admin role for your organization can set user permissions in the Microsoft 365 compliance center, as well as in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="f9334-125">若要在 Microsoft 365 合规性中心中设置权限和分配角色，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f9334-125">To set permissions and assign roles from within the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="f9334-126">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 " **权限** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-126">Select **Permissions** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-127">在顶部附近，选择 **"要在 Office 365 中查看和管理角色" 中的链接，请转到此处。**</span><span class="sxs-lookup"><span data-stu-id="f9334-127">Near the top, select the link at **“To view and manage roles in Office 365, please go here.”**</span></span> <span data-ttu-id="f9334-128">一个新的选项卡将打开到 Office 365 安全 & 合规性中心 ([了解你为什么重定向](microsoft-365-compliance-center.md#frequently-asked-questions)) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-128">A new tab will open to the Office 365 Security & Compliance Center ([learn why you’re redirected](microsoft-365-compliance-center.md#frequently-asked-questions)).</span></span>

3. <span data-ttu-id="f9334-129">查找要向其添加一个或多个用户的角色组，并选中该组名称左侧的框。</span><span class="sxs-lookup"><span data-stu-id="f9334-129">Find the role group to which you want to add one or more users, and check the box to the left of the group name.</span></span> <span data-ttu-id="f9334-130"> (请参阅 [下面的角色和相关功能的列表](#role-types)。</span><span class="sxs-lookup"><span data-stu-id="f9334-130">(See the [list of roles and related functions below](#role-types).</span></span> <span data-ttu-id="f9334-131">对角色名称进行模仿的角色组名称。 ) </span><span class="sxs-lookup"><span data-stu-id="f9334-131">The role group names mimic the role name.)</span></span>

4. <span data-ttu-id="f9334-132">在该组的浮出控件窗格中，选择 " **成员** " 标题下的 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-132">On the flyout pane for that group, select **Edit** under the **Members** header.</span></span>

5. <span data-ttu-id="f9334-133">选择 " **选择成员** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-133">Select **Choose members** .</span></span> <span data-ttu-id="f9334-134">将显示另一个浮出控件窗口。</span><span class="sxs-lookup"><span data-stu-id="f9334-134">Another flyout window will appear.</span></span>

6. <span data-ttu-id="f9334-135">选择 " **+ 添加** " 以选择要添加到组中的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-135">Select **+ Add** to choose one or more users to add to the group.</span></span>

7. <span data-ttu-id="f9334-136">选中您要添加的名称旁边的复选框，然后选择底部的 " **添加** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="f9334-136">Select the checkbox next to the names you want to add, then select the **Add** button at the bottom.</span></span>

8. <span data-ttu-id="f9334-137">完成分配用户后，选择 " **完成** "，然后选择 " **保存** "，然后单击 " **关闭** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-137">When you’re done assigning users, select **Done** , then select **Save** , then **Close** .</span></span>

##### <a name="more-about-the-office-365-secruity--compliance-center"></a><span data-ttu-id="f9334-138">有关 Office 365 Secruity & 合规中心的详细信息</span><span class="sxs-lookup"><span data-stu-id="f9334-138">More about the Office 365 Secruity & Compliance Center</span></span>

<span data-ttu-id="f9334-139">了解有关 [Office 365 安全 & 合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9334-139">Learn more about [permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

<span data-ttu-id="f9334-140">如果您没有访问 Office 365 安全与合规中心的权限，或者您需要在 Microsoft 服务信任门户中访问经典版合规性管理器，则服务信任门户中的管理员设置将提供另一种方法来分配角色 ([查看说明](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-140">If you don't have access to the Office 365 Security and Compliance Center, or if you need to access the classic version of Compliance Manager in the Microsoft Service Trust Portal,  the Admin settings in the Service Trust Portal provides another way to assign roles ([view instructions](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)).</span></span> <span data-ttu-id="f9334-141">请注意，此类角色在功能方面更具限制。</span><span class="sxs-lookup"><span data-stu-id="f9334-141">Be aware that such roles are more limited in their functionality.</span></span>

##### <a name="more-about-azure-ad"></a><span data-ttu-id="f9334-142">有关 Azure AD 的详细信息</span><span class="sxs-lookup"><span data-stu-id="f9334-142">More about Azure AD</span></span>

<span data-ttu-id="f9334-143">若要在 Azure AD 中分配角色和设置权限，请参阅 [向使用 Azure Active Directory 的用户分配管理员角色和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="f9334-143">To assign roles and set permissions in Azure AD, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

<span data-ttu-id="f9334-144">拥有未安装 Office 365 或 Microsoft 365 订阅的 Azure AD 标识的用户将无法访问 Microsoft 365 合规性中心中的合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="f9334-144">Users with Azure AD identities who don't have Office 365 or Microsoft 365 subscriptions won't be able to access Compliance Manager in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f9334-145">若要在访问合规性管理器中寻求帮助，请联系 [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f9334-145">To seek assistance in accessing Compliance Manager, contact [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).</span></span>

### <a name="role-types"></a><span data-ttu-id="f9334-146">角色类型</span><span class="sxs-lookup"><span data-stu-id="f9334-146">Role types</span></span>

<span data-ttu-id="f9334-147">下表显示了合规性管理器中的每个角色所允许的函数。</span><span class="sxs-lookup"><span data-stu-id="f9334-147">The table below shows the functions allowed by each role in Compliance Manager.</span></span> <span data-ttu-id="f9334-148">该表还显示了每个 [AZURE AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 如何映射到合规性管理器角色。</span><span class="sxs-lookup"><span data-stu-id="f9334-148">The table also shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to Compliance Manager roles.</span></span> <span data-ttu-id="f9334-149">用户至少需要合规性管理器读者角色或 Azure AD 全局读取器角色，才能访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="f9334-149">Users will need at least the Compliance Manager reader role, or Azure AD global reader role, to access Compliance Manager.</span></span>


| <span data-ttu-id="f9334-150">用户可以：</span><span class="sxs-lookup"><span data-stu-id="f9334-150">User can:</span></span> | <span data-ttu-id="f9334-151">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="f9334-151">Compliance Manager role</span></span> | <span data-ttu-id="f9334-152">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="f9334-152">Azure AD role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="f9334-153">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="f9334-153">**Read but not edit data**</span></span>| <span data-ttu-id="f9334-154">合规性管理器读者</span><span class="sxs-lookup"><span data-stu-id="f9334-154">Compliance Manager Reader</span></span>  | <span data-ttu-id="f9334-155">Azure AD 全局读取器，安全读取器</span><span class="sxs-lookup"><span data-stu-id="f9334-155">Azure AD Global reader, Security reader</span></span> | 
| <span data-ttu-id="f9334-156">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="f9334-156">**Edit data**</span></span>| <span data-ttu-id="f9334-157">合规性管理器的贡献</span><span class="sxs-lookup"><span data-stu-id="f9334-157">Compliance Manager Contribution</span></span> | <span data-ttu-id="f9334-158">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="f9334-158">Compliance Administrator</span></span> | 
| <span data-ttu-id="f9334-159">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="f9334-159">**Edit test results**</span></span>| <span data-ttu-id="f9334-160">合规性管理器评估</span><span class="sxs-lookup"><span data-stu-id="f9334-160">Compliance Manager Assessment</span></span> | <span data-ttu-id="f9334-161">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="f9334-161">Compliance Administrator</span></span> | 
| <span data-ttu-id="f9334-162">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="f9334-162">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="f9334-163">合规性管理器管理</span><span class="sxs-lookup"><span data-stu-id="f9334-163">Compliance Manager Administration</span></span> | <span data-ttu-id="f9334-164">合规性管理员、合规性数据管理员、安全管理员</span><span class="sxs-lookup"><span data-stu-id="f9334-164">Compliance Administrator, Compliance Data Administrator, Security Administrator</span></span>  | 
| <span data-ttu-id="f9334-165">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="f9334-165">**Assign users**</span></span>| <span data-ttu-id="f9334-166">全局管理员</span><span class="sxs-lookup"><span data-stu-id="f9334-166">Global Administrator</span></span> | <span data-ttu-id="f9334-167">全局管理员</span><span class="sxs-lookup"><span data-stu-id="f9334-167">Global Administrator</span></span> | 

## <a name="settings-for-automated-testing-and-user-history"></a><span data-ttu-id="f9334-168">自动测试和用户历史记录的设置</span><span class="sxs-lookup"><span data-stu-id="f9334-168">Settings for automated testing and user history</span></span>

<span data-ttu-id="f9334-169">Microsoft 365 合规性中心中的合规性管理器设置允许您启用和禁用改进操作的自动测试。</span><span class="sxs-lookup"><span data-stu-id="f9334-169">The Compliance Manager settings in the Microsoft 365 compliance center allow you to enable and disable automatic testing of improvement actions.</span></span> <span data-ttu-id="f9334-170">这些设置还允许您管理与改进操作相关联的用户的数据，其中包括将改进操作重新分配给其他用户的功能。</span><span class="sxs-lookup"><span data-stu-id="f9334-170">The settings also allow you to manage the data of users associated to improvement actions, including the ability to reassign improvement actions to a different user.</span></span>  <span data-ttu-id="f9334-171">只有具有全局管理员或合规性管理器管理员角色的用户才可以访问合规性管理器设置。</span><span class="sxs-lookup"><span data-stu-id="f9334-171">Only people with a global administrator or Compliance Manager Administrator role can access the Compliance Manager settings.</span></span>

### <a name="set-up-automated-testing"></a><span data-ttu-id="f9334-172">设置自动测试</span><span class="sxs-lookup"><span data-stu-id="f9334-172">Set up automated testing</span></span>

<span data-ttu-id="f9334-173">合规性管理器中的某些改进操作也受到 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)的监控。</span><span class="sxs-lookup"><span data-stu-id="f9334-173">Some improvement actions in Compliance Manager are also monitored by [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="f9334-174">您可以设置对联合监控的操作的自动测试，这意味着在安全分数中测试和更新操作时，这些结果将与合规性管理器中的相同操作进行同步，并计入合规性分数。</span><span class="sxs-lookup"><span data-stu-id="f9334-174">You can set up automated testing of actions that are jointly monitored, which means that when an action is tested and updated in Secure Score, those results synch with the same actions in Compliance Manager and count toward your compliance score.</span></span>

<span data-ttu-id="f9334-175">默认情况下，为合规性管理员新建的组织启用自动测试。</span><span class="sxs-lookup"><span data-stu-id="f9334-175">Automatic testing is turned on by default for organizations new to Compliance Manager.</span></span> <span data-ttu-id="f9334-176">当您首次部署 Microsoft 365 或 Office 365 时，需要大约7天的时间来完全收集数据，并将其划分为合规性分数。</span><span class="sxs-lookup"><span data-stu-id="f9334-176">When you first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your compliance score.</span></span>  <span data-ttu-id="f9334-177">如果启用了自动测试，则不会更新操作的测试日期，但其测试状态将会更新。</span><span class="sxs-lookup"><span data-stu-id="f9334-177">When automated testing is turned on, the action’s test date won’t be updated, but its test status will update.</span></span> <span data-ttu-id="f9334-178">在创建新的评估时，分数将自动包含 Microsoft 控制分数和安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="f9334-178">When new assessments are created, scores automatically include Microsoft control scores and Secure Score integration.</span></span>

<span data-ttu-id="f9334-179">您的组织的全局管理员可以随时更改自动测试的设置。</span><span class="sxs-lookup"><span data-stu-id="f9334-179">The global administrator for your organization can change the settings for automated testing at any time.</span></span> <span data-ttu-id="f9334-180">您可以关闭常见改进操作的自动测试，或为单个操作启用自动测试。</span><span class="sxs-lookup"><span data-stu-id="f9334-180">You can turn off automated testing for common improvement actions, or turn it on for individual actions.</span></span> <span data-ttu-id="f9334-181">按照下面的说明更改自动测试设置。</span><span class="sxs-lookup"><span data-stu-id="f9334-181">Follow the instructions below to change your automated testing settings.</span></span>

#### <a name="to-manage-your-automated-testing-settings"></a><span data-ttu-id="f9334-182">若要管理自动测试设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9334-182">To manage your automated testing settings:</span></span>

1. <span data-ttu-id="f9334-183">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-183">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-184">在 "设置" 页上，选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-184">On the settings page, select **Compliance Manager** .</span></span>

3. <span data-ttu-id="f9334-185">从左侧导航栏中选择 " **自动测试** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-185">Select **Automated testing** from the left navigation.</span></span>

4. <span data-ttu-id="f9334-186">选择适用的按钮，为所有改进操作启用自动测试，将所有操作关闭，或通过单个操作打开。</span><span class="sxs-lookup"><span data-stu-id="f9334-186">Select the applicable button to turn on automatic testing for all improvement actions, turn it off for all actions, or turn on by individual action.</span></span>

5. <span data-ttu-id="f9334-187">如果选择 " **打开每个改进操作** "，则会有一个列表显示可供选择的所有可用的提高操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-187">If you select **Turn on per improvement action** , a list will show all the available improvement actions to choose from.</span></span>  <span data-ttu-id="f9334-188">选中您希望自动测试的任何操作旁边的框。</span><span class="sxs-lookup"><span data-stu-id="f9334-188">Check the box next to any action you want automatically tested.</span></span>

6. <span data-ttu-id="f9334-189">选择 " **保存** " 以保存设置。</span><span class="sxs-lookup"><span data-stu-id="f9334-189">Select **Save** to save your settings.</span></span> <span data-ttu-id="f9334-190">您将在屏幕顶部收到一条确认消息，指示您所做的选择已保存。</span><span class="sxs-lookup"><span data-stu-id="f9334-190">You’ll receive a confirmation message at the top of your screen that your selection was saved.</span></span> <span data-ttu-id="f9334-191">如果收到故障通知，请重试。</span><span class="sxs-lookup"><span data-stu-id="f9334-191">If you receive a failure notice, try again.</span></span>

<span data-ttu-id="f9334-192">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="f9334-192">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="f9334-193">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-193">The Compliance Manager Administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="manage-user-history"></a><span data-ttu-id="f9334-194">管理用户历史记录</span><span class="sxs-lookup"><span data-stu-id="f9334-194">Manage user history</span></span>

<span data-ttu-id="f9334-195">" **管理用户历史记录** " 设置可帮助你快速识别合规性管理器中已处理改进操作的用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-195">The **Manage user history** settings help you quickly identify which users have worked with improvement actions in Compliance Manager.</span></span> <span data-ttu-id="f9334-196">与提高操作相关联的可识别用户数据包括任何实现和测试工作已完成、文档上传的文档以及所输入的任何注释。</span><span class="sxs-lookup"><span data-stu-id="f9334-196">The identifiable user data associated with improvement actions includes any implementation and testing work done, documents they uploaded, and any notes they entered.</span></span> <span data-ttu-id="f9334-197">了解和检索此类型的数据可能是组织自己的合规性需求所必需的。</span><span class="sxs-lookup"><span data-stu-id="f9334-197">Understanding and retrieving this type of data may be necessary for your organization’s own compliance needs.</span></span>

<span data-ttu-id="f9334-198">用户历史记录设置还允许您将所有改进操作从一个用户重新分配给另一个用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-198">The user history settings also allow you to reassign all improvement actions from one user to another.</span></span>

<span data-ttu-id="f9334-199">**查找用户历史记录设置：**</span><span class="sxs-lookup"><span data-stu-id="f9334-199">**To find the user history settings:**</span></span>

1. <span data-ttu-id="f9334-200">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 "设置"。</span><span class="sxs-lookup"><span data-stu-id="f9334-200">Select Settings on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-201">在 "设置" 页上，选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-201">On the settings page, select **Compliance Manager** .</span></span>

3. <span data-ttu-id="f9334-202">从左侧导航中选择 " **管理用户历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-202">Select **Manage user history** from the left navigation.</span></span>

<span data-ttu-id="f9334-203">" **管理用户历史记录** " 页显示了一个列表，其中列出了所有用户分配给改进操作的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f9334-203">The **manage user history** page shows a list of all users by email address who are assigned to an improvement action.</span></span> <span data-ttu-id="f9334-204">使用 " **搜索** " 按钮，通过在电子邮件地址中键入来快速查找特定用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-204">Use the **Search** button to quickly find a specific user by typing in their email address.</span></span>

<span data-ttu-id="f9334-205">在每个用户的电子邮件地址的右侧，" **选择** " 下拉菜单提供了导出报表、重新分配改进操作或删除历史记录的选项。</span><span class="sxs-lookup"><span data-stu-id="f9334-205">To the right of each user’s email address, the **Select** drop-down menu provides options to  export a report, reassign improvement actions, or delete history.</span></span> <span data-ttu-id="f9334-206">有关每个选项的详细信息，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="f9334-206">See each section below for details about each option.</span></span>

#### <a name="export-a-report-of-user-history-data"></a><span data-ttu-id="f9334-207">导出用户历史记录数据的报告</span><span class="sxs-lookup"><span data-stu-id="f9334-207">Export a report of user history data</span></span>

<span data-ttu-id="f9334-208">您可以导出一个 Excel 文件，其中包含当前分配给用户的改进操作的列表。</span><span class="sxs-lookup"><span data-stu-id="f9334-208">You can export an Excel file containing a list of improvement actions currently assigned to a user.</span></span>  <span data-ttu-id="f9334-209">该报告还列出了该用户上载的所有证据文件。</span><span class="sxs-lookup"><span data-stu-id="f9334-209">The report also lists any evidence files uploaded by that user.</span></span> <span data-ttu-id="f9334-210">此信息可帮助您重新分配打开的改进操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-210">This information can help you reassign open improvement actions.</span></span>

<span data-ttu-id="f9334-211">该报告反映了在其创建日期后的改进行动的状态。</span><span class="sxs-lookup"><span data-stu-id="f9334-211">The report reflects the improvement action’s status as of its creation date.</span></span> <span data-ttu-id="f9334-212">它并不是对其状态或工作分配的所有以前更改的历史报告 (了解如何 [从 "改进操作" 页) 中导出报告](compliance-manager-improvement-actions.md#export-a-report) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-212">It’s not a historical report of all previous changes to its status or assignment (learn how to [export a report from your improvement actions page](compliance-manager-improvement-actions.md#export-a-report)).</span></span>

<span data-ttu-id="f9334-213">**按照下面的步骤，按用户导出报表：**</span><span class="sxs-lookup"><span data-stu-id="f9334-213">**Follow the steps below to export a report by user:**</span></span>

1. <span data-ttu-id="f9334-214">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-214">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-215">在 "设置" 页上，选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-215">On the settings page, select **Compliance Manager** .</span></span>

3. <span data-ttu-id="f9334-216">从左侧的导航栏中选择 " **管理用户历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-216">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="f9334-217">通过搜索列表电子邮件地址，或通过选择 " **搜索** " 并输入用户的电子邮件地址来查找预期的用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-217">Find your intended user by searching the list email addresses, or by selecting **Search** and entering the user’s email address.</span></span>

5. <span data-ttu-id="f9334-218">从 " **选择** " 下拉菜单中，选择 " **导出报告** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-218">From the **Select** drop-down menu, choose **Export report** .</span></span>

6. <span data-ttu-id="f9334-219">生成报告的 Excel 文件后，可以打开它并将其保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="f9334-219">Once the Excel file of your report is generated, you can open it and save it to your local machine.</span></span>

#### <a name="reassign-improvement-actions-to-another-user"></a><span data-ttu-id="f9334-220">将改进操作重新分配给另一个用户</span><span class="sxs-lookup"><span data-stu-id="f9334-220">Reassign improvement actions to another user</span></span>

<span data-ttu-id="f9334-221">您可以将提高操作从一个用户重新分配给另一个用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-221">You can reassign improvement actions from one user to another.</span></span> <span data-ttu-id="f9334-222">重新分配操作时，文档上载历史记录不会更改，但最初上载文档的用户的名称不再出现在改进操作中。</span><span class="sxs-lookup"><span data-stu-id="f9334-222">When you reassign an action, the document upload history doesn't change, but the name of the user who originally uploaded the documentation no longer appears within the improvement action.</span></span>

<span data-ttu-id="f9334-223">**按照下面的步骤操作，将 "提高" 操作重新分配给另一个用户：**</span><span class="sxs-lookup"><span data-stu-id="f9334-223">**Follow the steps below to reassign improvement actions to another user:**</span></span>

1. <span data-ttu-id="f9334-224">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-224">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-225">在 "设置" 页上，选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-225">On the settings page, select **Compliance Manager** .</span></span>

3. <span data-ttu-id="f9334-226">从左侧的导航栏中选择 " **管理用户历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-226">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="f9334-227">通过搜索列表电子邮件地址或通过选择 " **搜索** " 并输入该用户的电子邮件地址来查找用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-227">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="f9334-228">从 " **选择** " 下拉菜单中，选择 " **重新分配改进操作** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-228">From the **Select** drop-down menu, choose **Reassign improvement actions** .</span></span> <span data-ttu-id="f9334-229">将显示 **重新分配改进操作** 的浮出控件窗格。</span><span class="sxs-lookup"><span data-stu-id="f9334-229">The **Reassign improvement actions** flyout pane will appear.</span></span>

6. <span data-ttu-id="f9334-230">在 " **搜索用户** " 字段中，输入要 *向* 其分配改进操作的用户的姓名或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f9334-230">In the **Search users** field, enter the name or email address of the user you want assign the improvement actions *to* .</span></span>

7. <span data-ttu-id="f9334-231">当您看到 " **改进操作将分配给** " 下一个预期用户的名称时，请选择该用户，然后选择 " **分配操作** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-231">When you see the name of your intended user under **Improvement actions will be assigned to** , select the user, then select **Assign actions** .</span></span>

8. <span data-ttu-id="f9334-232">重新分配完成后，将在弹出窗格中看到一条确认消息，确认已将以前用户的所有改进操作重新分配给新用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-232">When the reassignment is complete, you’ll see a confirmation message in the flyout pane confirming that all improvement actions from the previous user have been reassigned to the new user.</span></span> <span data-ttu-id="f9334-233">如果您收到重新分配失败通知，请关闭该窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="f9334-233">If you receive a reassignment failure notice, close the window and try again.</span></span> <span data-ttu-id="f9334-234">若要关闭弹出窗口窗格，请选择 " **完成** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-234">To close the flyout pane, select **Done** .</span></span>

<span data-ttu-id="f9334-235">新的受理人会收到一封电子邮件，他们已将其分配给改进操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-235">The new assignee receives an email that they've been assigned to an improvement action.</span></span> <span data-ttu-id="f9334-236">该电子邮件包含到改进操作的详细信息页面的直接链接。</span><span class="sxs-lookup"><span data-stu-id="f9334-236">The email contains a direct link into the improvement action's details page.</span></span>
 
 > [!NOTE]
> <span data-ttu-id="f9334-237">如果重新分配具有挂起的更新的操作，如果重新分配后接受更新，则重新分配的电子邮件中的操作的直接链接将会中断。</span><span class="sxs-lookup"><span data-stu-id="f9334-237">If you reassign an action that has a pending update, the direct link to the action in the reassignment email will break if the update is accepted after reassignment.</span></span> <span data-ttu-id="f9334-238">您可以通过在接受更新后将操作重新分配给用户来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="f9334-238">You can fix this by re-assigning the action to the user after the update is accepted.</span></span> <span data-ttu-id="f9334-239">了解有关 [改进操作更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9334-239">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

#### <a name="delete-user-history"></a><span data-ttu-id="f9334-240">删除用户历史记录</span><span class="sxs-lookup"><span data-stu-id="f9334-240">Delete user history</span></span>

<span data-ttu-id="f9334-241">删除用户的历史记录会将其作为改进操作的所有者删除，并将从合规性管理器中的所有其他字段中删除它们的名称。</span><span class="sxs-lookup"><span data-stu-id="f9334-241">Deleting a user’s history will remove them as an owner of improvement actions, and will remove their name from all other fields in Compliance Manager.</span></span> <span data-ttu-id="f9334-242">当您删除用户的历史记录时，他们拥有的提高操作将不会显示 **分配给** 的值，直到分配新用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-242">When you delete a user’s history, the improvement actions they owned will not display an **Assigned to** value until a new user is assigned.</span></span> <span data-ttu-id="f9334-243">上载到 "改进" 操作的任何文档将显示 " **用户已删除** " 以代替已删除的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="f9334-243">Any documents uploaded to the improvement action will show **User removed** in place of the deleted user’s name.</span></span> <span data-ttu-id="f9334-244">删除用户历史记录是永久性的。</span><span class="sxs-lookup"><span data-stu-id="f9334-244">Deleting user history is permanent.</span></span>

<span data-ttu-id="f9334-245">若要删除用户的历史记录，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f9334-245">To delete a user’s history, follow the steps below:</span></span>

1. <span data-ttu-id="f9334-246">从 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)的任意位置选择左侧导航中的 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-246">Select **Settings** on the left navigation from anywhere in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f9334-247">在 "设置" 页上，选择 " **合规性管理器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-247">On the settings page, select **Compliance Manager** .</span></span>

3. <span data-ttu-id="f9334-248">从左侧的导航栏中选择 " **管理用户历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-248">Select **Manage user history** from the navigation at left.</span></span>

4. <span data-ttu-id="f9334-249">通过搜索列表电子邮件地址或通过选择 " **搜索** " 并输入该用户的电子邮件地址来查找用户。</span><span class="sxs-lookup"><span data-stu-id="f9334-249">Find a user by searching the list email addresses, or by selecting **Search** and entering that user’s email address.</span></span>

5. <span data-ttu-id="f9334-250">从 " **选择** " 下拉菜单中，选择 " **删除历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-250">From the **Select** drop-down menu, choose **Delete history** .</span></span>

6. <span data-ttu-id="f9334-251">将显示一个窗口，要求您确认是否永久删除了用户的历史记录。</span><span class="sxs-lookup"><span data-stu-id="f9334-251">A window appears asking you to confirm the permanent deletion of the user’s history.</span></span> <span data-ttu-id="f9334-252">若要继续删除，请选择 " **删除历史记录** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-252">To continue with deletion, select **Delete history** .</span></span> <span data-ttu-id="f9334-253">若要离开而不删除历史记录，请选择 " **取消** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-253">To leave without deleting the history, select **Cancel** .</span></span>

7. <span data-ttu-id="f9334-254">您将在 " **管理用户历史记录** " 页上返回，其中有一条确认消息，用户的历史记录已被删除。</span><span class="sxs-lookup"><span data-stu-id="f9334-254">You’ll arrive back at the **Manage user history** page with a confirmation message at the top that the history for the user was deleted.</span></span>

## <a name="understand-the-compliance-manager-dashboard"></a><span data-ttu-id="f9334-255">了解合规性管理器仪表板</span><span class="sxs-lookup"><span data-stu-id="f9334-255">Understand the Compliance Manager dashboard</span></span>

<span data-ttu-id="f9334-256">合规性管理器仪表板旨在向你提供当前合规性状况的一览视图。</span><span class="sxs-lookup"><span data-stu-id="f9334-256">The Compliance Manager dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="f9334-257">![合规性管理器-仪表板](../media/compliance-manager-dashboard.png "合规性管理器仪表板")</span><span class="sxs-lookup"><span data-stu-id="f9334-257">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="f9334-258">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="f9334-258">Overall compliance score</span></span>

<span data-ttu-id="f9334-259">你的合规性分数在顶部一目了然。</span><span class="sxs-lookup"><span data-stu-id="f9334-259">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="f9334-260">它显示的百分比取决于完成解决关键数据保护标准和法规的提高操作所能实现的积分。</span><span class="sxs-lookup"><span data-stu-id="f9334-260">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span> <span data-ttu-id="f9334-261">来自 [microsoft 操作](compliance-manager-assessments.md#microsoft-actions-tab)的点，这些操作是由 microsoft 托管的，也是按符合性分数计。</span><span class="sxs-lookup"><span data-stu-id="f9334-261">Points from [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab), which are managed my Microsoft, also count toward your compliance score.</span></span>

<span data-ttu-id="f9334-262">当您首次进入合规性管理器时，您的初始分数将基于 [Microsoft 365 数据保护基准](compliance-manager-assessments.md#data-protection-baseline-default-assessment)。</span><span class="sxs-lookup"><span data-stu-id="f9334-262">When you come to Compliance Manager for the first time, your initial score is based on the [Microsoft 365 data protection baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment).</span></span> <span data-ttu-id="f9334-263">对所有组织可用的此基准评估是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="f9334-263">This baseline assessment, which is available to all organizations, is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="f9334-264">合规性管理器扫描您现有的 Microsoft 365 解决方案，并根据您当前的隐私和安全设置为您提供初步评估。</span><span class="sxs-lookup"><span data-stu-id="f9334-264">Compliance Manager scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="f9334-265">在添加与您的组织相关的评估时，您的分数将对您更有意义。</span><span class="sxs-lookup"><span data-stu-id="f9334-265">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

<span data-ttu-id="f9334-266">**了解详细信息：** [了解如何计算合规性分数](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="f9334-266">**Learn more:** [Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="f9334-267">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="f9334-267">Key improvement actions</span></span>

<span data-ttu-id="f9334-268">此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。</span><span class="sxs-lookup"><span data-stu-id="f9334-268">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="f9334-269">选择 " **查看所有改善措施** " 以转到 "改进操作" 页面。</span><span class="sxs-lookup"><span data-stu-id="f9334-269">Select **View all improvement actions** to go to your improvement actions page.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="f9334-270">影响你的成绩的解决方案</span><span class="sxs-lookup"><span data-stu-id="f9334-270">Solutions that affect your score</span></span>

<span data-ttu-id="f9334-271">本节重点介绍了包含可积极影响你的成绩的改进操作的解决方案，以及这些解决方案中未完成的改进操作的数量。</span><span class="sxs-lookup"><span data-stu-id="f9334-271">This section highlights solutions containing improvement actions that can positively impact your score, and the number of outstanding improvement actions in those solutions.</span></span> <span data-ttu-id="f9334-272">选择 " **查看所有解决方案** 以访问解决方案" 页。</span><span class="sxs-lookup"><span data-stu-id="f9334-272">Select **View all solutions** to visit your solutions page.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="f9334-273">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="f9334-273">Compliance score breakdown</span></span>

<span data-ttu-id="f9334-274">本节提供了以两种不同的方式更详细地查看分数：</span><span class="sxs-lookup"><span data-stu-id="f9334-274">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="f9334-275">**类别** ：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。</span><span class="sxs-lookup"><span data-stu-id="f9334-275">**Categories** : shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="f9334-276">**评估** ：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。</span><span class="sxs-lookup"><span data-stu-id="f9334-276">**Assessments** : shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="f9334-277">筛选你的仪表板视图</span><span class="sxs-lookup"><span data-stu-id="f9334-277">Filtering your dashboard view</span></span>

<span data-ttu-id="f9334-278">您可以筛选仪表板视图，以仅查看与特定法规和标准、解决方案、操作类型、评估组或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="f9334-278">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="f9334-279">以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。</span><span class="sxs-lookup"><span data-stu-id="f9334-279">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="f9334-280">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="f9334-280">To apply filters:</span></span>

1. <span data-ttu-id="f9334-281">选择仪表板右上侧的 " **筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-281">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="f9334-282">从 " **筛选器** " 浮出控件窗格中选择筛选条件，然后选择 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-282">Select your filter criteria from the **Filters** flyout pane, then select **Apply** .</span></span>

<span data-ttu-id="f9334-283">在应用筛选器之后，你将看到实时调整的分数。</span><span class="sxs-lookup"><span data-stu-id="f9334-283">After you apply a filter, you’ll see your score adjusted in real time.</span></span> <span data-ttu-id="f9334-284">合规性分数百分比和细目信息以及改进操作和解决方案现在仅适用于您的筛选器条件所覆盖的数据。</span><span class="sxs-lookup"><span data-stu-id="f9334-284">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="f9334-285">如果你注销合规性管理器，则在重新登录时将保留你的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="f9334-285">If you sign out of Compliance Manager, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="f9334-286">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="f9334-286">To remove filters:</span></span>

- <span data-ttu-id="f9334-287">在 " **应用的筛选器** " 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的 **X** ;和</span><span class="sxs-lookup"><span data-stu-id="f9334-287">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="f9334-288">选择仪表板右上侧的 " **筛选器** "，然后在 " **筛选器** " 浮出控件窗格中，选择 " **清除筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-288">Select **Filter** on the upper-right side of your dashboard, then on the **Filters** flyout pane, select **Clear filters** .</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="f9334-289">改进操作页</span><span class="sxs-lookup"><span data-stu-id="f9334-289">Improvement actions page</span></span>

<span data-ttu-id="f9334-290">[改进操作](compliance-manager-improvement-actions.md) 是由您的组织管理的操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-290">[Improvement actions](compliance-manager-improvement-actions.md) are actions managed by your organization.</span></span> <span data-ttu-id="f9334-291">使用改进操作有助于集中化合规性活动并与数据保护法规和标准保持一致。</span><span class="sxs-lookup"><span data-stu-id="f9334-291">Working with improvement actions helps to centralize your compliance activities and align with data protection regulations and standards.</span></span> <span data-ttu-id="f9334-292">每个改进操作都提供了详细的实施指导和将您引导您进入适当解决方案的链接。</span><span class="sxs-lookup"><span data-stu-id="f9334-292">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="f9334-293">可将改进操作分配给组织中的用户，以执行实施和测试工作。</span><span class="sxs-lookup"><span data-stu-id="f9334-293">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="f9334-294">您还可以在 "改进" 操作中存储文档、注释和记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="f9334-294">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="f9334-295">查看改进操作</span><span class="sxs-lookup"><span data-stu-id="f9334-295">View your improvement actions</span></span>

<span data-ttu-id="f9334-296">合规性管理器仪表板显示你的 **主要改进操作。**</span><span class="sxs-lookup"><span data-stu-id="f9334-296">The Compliance Manager dashboard shows your **key improvement actions.**</span></span> <span data-ttu-id="f9334-297">若要查看所有改进操作，请选择仪表板上的 "改善操作" 选项卡，此选项卡将带你转到 "改进操作" 页面。</span><span class="sxs-lookup"><span data-stu-id="f9334-297">To view all of your improvement actions, select the Improvement actions tab on your dashboard, which brings you to your improvement actions page.</span></span> <span data-ttu-id="f9334-298">您还可以选择 "查看仪表板上的关键改进操作列表下的所有改进操作"，以转到 "改进操作" 页面。</span><span class="sxs-lookup"><span data-stu-id="f9334-298">You can also select View all improvement actions underneath the list of key improvement actions on your dashboard to get to your improvement actions page.</span></span>

<span data-ttu-id="f9334-299">"改进操作" 页面显示组织管理的所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-299">The improvement actions page shows all of the improvement actions that are managed by your organization.</span></span> <span data-ttu-id="f9334-300">可以在每个评估中查看由 Microsoft 管理的操作 (了解有关 [microsoft 操作](compliance-manager-assessments.md#microsoft-actions-tab)) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9334-300">Actions that are managed by Microsoft can be viewed within each assessment (learn more about [Microsoft actions](compliance-manager-assessments.md#microsoft-actions-tab)).</span></span>

<span data-ttu-id="f9334-301">如果您的 "改进操作" 页面上有很长的操作列表，则筛选视图可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="f9334-301">If you have a long list of actions on your improvement actions page, it may be helpful to filter your view.</span></span> <span data-ttu-id="f9334-302">选择 "操作" 列表右上角的 " **筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-302">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="f9334-303">当 " **筛选器** " 浮出控件窗格出现时，选择基于法规和标准、解决方案和组的标准。</span><span class="sxs-lookup"><span data-stu-id="f9334-303">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="f9334-304">您还可以通过选择右上角的 " **组** " 来自定义您的视图。</span><span class="sxs-lookup"><span data-stu-id="f9334-304">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="f9334-305">从下拉菜单中，选择按组、解决方案、类别、操作类型或状态进行查看。</span><span class="sxs-lookup"><span data-stu-id="f9334-305">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="f9334-306">此页面的默认视图不显示测试状态为 "已 **通过** " 的提高操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-306">The default view for this page does not show improvement actions with a test status of **Passed** .</span></span> <span data-ttu-id="f9334-307">若要查看已通过测试的操作，请选中 "筛选器浮出控件" 窗格中的 " **传递** " 框。</span><span class="sxs-lookup"><span data-stu-id="f9334-307">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="f9334-308">仅具有已 **通过** 的测试状态与得分接近的操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-308">Only actions with a test status of **Passed** count toward your score.</span></span> <span data-ttu-id="f9334-309">某些操作可能会显示 " **挂起的更新" 标签。**</span><span class="sxs-lookup"><span data-stu-id="f9334-309">Some actions may show a **pending update label.**</span></span> <span data-ttu-id="f9334-310">了解有关 [改进操作更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9334-310">Learn more about [updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).</span></span>

<span data-ttu-id="f9334-311">"改进操作" 页显示每个改进操作的以下数据点：</span><span class="sxs-lookup"><span data-stu-id="f9334-311">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="f9334-312">**实现点** ：完成操作后可用总可用点数</span><span class="sxs-lookup"><span data-stu-id="f9334-312">**Points achieved** : the number of points achieved out of the total available by completing the action</span></span>
- <span data-ttu-id="f9334-313">**法规** ：与操作相关的法规或标准</span><span class="sxs-lookup"><span data-stu-id="f9334-313">**Regulations** : the regulations or standards pertaining to the action</span></span>
- <span data-ttu-id="f9334-314">**组** ：为其分配操作的组</span><span class="sxs-lookup"><span data-stu-id="f9334-314">**Group** : the group to which you assigned the action</span></span>
- <span data-ttu-id="f9334-315">**解决方案** ：可在其中执行操作的解决方案</span><span class="sxs-lookup"><span data-stu-id="f9334-315">**Solutions** : the solution where you can go to perform the action</span></span>
- <span data-ttu-id="f9334-316">**评估** ：包含操作的评估</span><span class="sxs-lookup"><span data-stu-id="f9334-316">**Assessments** : the assessments that contain the action</span></span>
- <span data-ttu-id="f9334-317">**类别** ：相关的数据保护类别 (例如，保护信息、管理设备等 ) </span><span class="sxs-lookup"><span data-stu-id="f9334-317">**Categories** : the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="f9334-318">**测试状态** ：</span><span class="sxs-lookup"><span data-stu-id="f9334-318">**Test status** :</span></span>
    - <span data-ttu-id="f9334-319">**无** –未记录状态更新</span><span class="sxs-lookup"><span data-stu-id="f9334-319">**None** – no status update recorded</span></span>
    - <span data-ttu-id="f9334-320">**未评估** -测试尚未启动</span><span class="sxs-lookup"><span data-stu-id="f9334-320">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="f9334-321">已成功测试已 **通过** 的实施</span><span class="sxs-lookup"><span data-stu-id="f9334-321">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="f9334-322">**失败的低风险** -测试失败，低风险</span><span class="sxs-lookup"><span data-stu-id="f9334-322">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="f9334-323">**失败中等风险** -测试失败，中等风险</span><span class="sxs-lookup"><span data-stu-id="f9334-323">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="f9334-324">**失败的高风险** -测试失败，高风险</span><span class="sxs-lookup"><span data-stu-id="f9334-324">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="f9334-325">**超出范围** -操作不在评估范围内，不会影响你的成绩</span><span class="sxs-lookup"><span data-stu-id="f9334-325">**Out of scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="f9334-326">**若要检测-若要** 进行手动测试，表明已实现操作但未测试;对于自动测试，指示某个操作正在等待自动化结果</span><span class="sxs-lookup"><span data-stu-id="f9334-326">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="f9334-327">**无法检测** -无法确定自动状态</span><span class="sxs-lookup"><span data-stu-id="f9334-327">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="f9334-328">**部分测试** –对部分点获奖的自动化评分</span><span class="sxs-lookup"><span data-stu-id="f9334-328">**Partially tested** – automated scoring that awards partial points</span></span>

<span data-ttu-id="f9334-329">**了解详细信息：** 了解 [如何分配和执行改进操作的工作](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9334-329">**Learn more:** [See how to assign and perform work on improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="f9334-330">解决方案页</span><span class="sxs-lookup"><span data-stu-id="f9334-330">Solutions page</span></span>

<span data-ttu-id="f9334-331">"解决方案" 页显示按解决方案组织的挣和潜在点的份额。</span><span class="sxs-lookup"><span data-stu-id="f9334-331">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="f9334-332">查看此视图中的剩余点和改进操作可帮助您了解哪些解决方案需要更直接关注。</span><span class="sxs-lookup"><span data-stu-id="f9334-332">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="f9334-333">通过选择合规性管理器仪表板上的 " **解决方案** " 选项卡查找 "解决方案" 页。</span><span class="sxs-lookup"><span data-stu-id="f9334-333">Find the solutions page by selecting the **Solutions** tab on your Compliance Manager dashboard.</span></span> <span data-ttu-id="f9334-334">您还可以选择 "查看下面的 **所有解决方案** **，这些解决方案将影响您** 的仪表板的右上部分中的分数。</span><span class="sxs-lookup"><span data-stu-id="f9334-334">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="f9334-335">筛选解决方案视图</span><span class="sxs-lookup"><span data-stu-id="f9334-335">Filtering your solutions view</span></span>

<span data-ttu-id="f9334-336">筛选解决方案视图：</span><span class="sxs-lookup"><span data-stu-id="f9334-336">To filter your view of solutions:</span></span>

1. <span data-ttu-id="f9334-337">选择评估列表左上角的 " **筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-337">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="f9334-338">在 " **筛选器** " 浮出控件窗格中，在所需条件的旁边放置一个复选 (标准和管理法规、解决方案、操作类型、合规性管理器组、类别) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-338">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="f9334-339">选择 " **应用** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="f9334-339">Select the **Apply** button.</span></span> <span data-ttu-id="f9334-340">筛选窗格将关闭，你将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="f9334-340">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="f9334-341">您还可以通过从评估列表上方的 **组** 下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="f9334-341">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-action-from-the-solution-page"></a><span data-ttu-id="f9334-342">从 "解决方案" 页采取操作</span><span class="sxs-lookup"><span data-stu-id="f9334-342">Taking action from the solution page</span></span>

<span data-ttu-id="f9334-343">"解决方案" 页显示已连接到 "改进操作" 的组织解决方案。</span><span class="sxs-lookup"><span data-stu-id="f9334-343">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="f9334-344">该表列出了每个解决方案对总体成绩的贡献、该解决方案中实现的分数，以及在该解决方案中进行了分组以增加成绩的剩余改进操作数。</span><span class="sxs-lookup"><span data-stu-id="f9334-344">The table lists each solution’s contribution to your overall score, the points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="f9334-345">可以通过以下两种方法从该屏幕执行操作：</span><span class="sxs-lookup"><span data-stu-id="f9334-345">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="f9334-346">在预期解决方案的行上，在 " **剩余操作** " 列下，选择超链接编号。</span><span class="sxs-lookup"><span data-stu-id="f9334-346">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="f9334-347">你将看到 "改进操作" 屏幕的筛选视图，其中显示了该解决方案的未经测试的改进操作。</span><span class="sxs-lookup"><span data-stu-id="f9334-347">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="f9334-348">在预期解决方案的行中的 " **打开解决方案** " 列下，选择 " **打开** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-348">On the row of your intended solution, under the **Open solution** column, select **Open** .</span></span> <span data-ttu-id="f9334-349">你将在 Microsoft 365 和 Office 365 安全与合规中心中看到解决方案或位置，你可以采取建议的措施。</span><span class="sxs-lookup"><span data-stu-id="f9334-349">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="f9334-350">评估页</span><span class="sxs-lookup"><span data-stu-id="f9334-350">Assessments page</span></span>

<span data-ttu-id="f9334-351">"评估" 页面列出了您为您的组织设置的所有 [评估](compliance-manager-assessments.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-351">The assessments page lists all the [assessments](compliance-manager-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="f9334-352">您的合规性分数分母由所有跟踪的评估决定。</span><span class="sxs-lookup"><span data-stu-id="f9334-352">Your compliance score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="f9334-353">在添加更多评估时，您将看到 "改进操作" 页面上列出的更多改进操作，并且您的合规性分数分母将增加。</span><span class="sxs-lookup"><span data-stu-id="f9334-353">As you add more assessments, you'll see more improvement actions listed on your improvement actions page, and your compliance score denominator increases.</span></span>

<span data-ttu-id="f9334-354">"评估" 页面汇总了有关每个评估的关键信息：</span><span class="sxs-lookup"><span data-stu-id="f9334-354">The assessments page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="f9334-355">**评估** ：评估的名称</span><span class="sxs-lookup"><span data-stu-id="f9334-355">**Assessment** : name of the assessment</span></span>
- <span data-ttu-id="f9334-356">**状态** ：</span><span class="sxs-lookup"><span data-stu-id="f9334-356">**Status** :</span></span>
    - <span data-ttu-id="f9334-357">**完成** -所有控件的状态均为 "已通过"，或者至少传递了一个，其余部分为 "超出范围"</span><span class="sxs-lookup"><span data-stu-id="f9334-357">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="f9334-358">**不完整** –至少一个控件的状态为 "failed"</span><span class="sxs-lookup"><span data-stu-id="f9334-358">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="f9334-359">**None** -尚未测试所有控件</span><span class="sxs-lookup"><span data-stu-id="f9334-359">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="f9334-360">**进度** 改善操作具有任何其他状态，包括 "正在进行中"、"部分贷方" 或 "未检测到"</span><span class="sxs-lookup"><span data-stu-id="f9334-360">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="f9334-361">**评估进度** ：完成工作所占的百分比（按成功测试的控件数衡量）</span><span class="sxs-lookup"><span data-stu-id="f9334-361">**Assessment progress** : the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="f9334-362">**改进操作** ：满足控件实现的已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="f9334-362">**Your improvement actions** : the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="f9334-363">**Microsoft 操作** ：满足 microsoft 控件实现的已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="f9334-363">**Microsoft actions** : the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="f9334-364">**组** ：评估所属的组的名称</span><span class="sxs-lookup"><span data-stu-id="f9334-364">**Group** : name of the group the assessment belongs to</span></span>
- <span data-ttu-id="f9334-365">**产品** ：关联的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="f9334-365">**Product** : associated Microsoft 365 service</span></span>
- <span data-ttu-id="f9334-366">**法规** ：适用于评估的规章标准、策略或法律</span><span class="sxs-lookup"><span data-stu-id="f9334-366">**Regulation** : the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="f9334-367">筛选评估视图</span><span class="sxs-lookup"><span data-stu-id="f9334-367">Filtering your assessments view</span></span>

<span data-ttu-id="f9334-368">筛选评估的视图：</span><span class="sxs-lookup"><span data-stu-id="f9334-368">To filter you view of assessments:</span></span>

1. <span data-ttu-id="f9334-369">选择评估列表左上角的 " **筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="f9334-369">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="f9334-370">在 " **筛选器** " 浮出控件窗格中，检查所需的条件。</span><span class="sxs-lookup"><span data-stu-id="f9334-370">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="f9334-371">选择 " **应用** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="f9334-371">Select the **Apply** button.</span></span> <span data-ttu-id="f9334-372">筛选窗格将关闭，您将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="f9334-372">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="f9334-373">您还可以通过从评估列表上方的 **组** 下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="f9334-373">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="f9334-374">默认评估</span><span class="sxs-lookup"><span data-stu-id="f9334-374">Default assessment</span></span>

<span data-ttu-id="f9334-375">默认情况下，您将在 "评估" 页上看到 " [数据保护基准](compliance-manager-assessments.md#data-protection-baseline-default-assessment) 评估"。</span><span class="sxs-lookup"><span data-stu-id="f9334-375">By default, you'll see the [Data Protection Baseline](compliance-manager-assessments.md#data-protection-baseline-default-assessment) assessment on the assessments page.</span></span> <span data-ttu-id="f9334-376">合规性管理器还提供了多个用于生成评估的预建 [模板](compliance-manager-templates-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9334-376">Compliance Manager also provides several pre-built [templates](compliance-manager-templates-list.md) for building assessments.</span></span>

## <a name="assessment-templates-page"></a><span data-ttu-id="f9334-377">"评估模板" 页</span><span class="sxs-lookup"><span data-stu-id="f9334-377">Assessment templates page</span></span>

<span data-ttu-id="f9334-378">模板是用于在合规性管理器中创建评估的框架。</span><span class="sxs-lookup"><span data-stu-id="f9334-378">A template is a framework for creating an assessment in Compliance Manager.</span></span> <span data-ttu-id="f9334-379">"评估模板" 页将显示模板和主要详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="f9334-379">The assessment templates page displays a list of templates and key details.</span></span> <span data-ttu-id="f9334-380">此列表包括合规性管理器提供的模板以及你的组织修改或创建的任何模板。</span><span class="sxs-lookup"><span data-stu-id="f9334-380">The list includes templates provided by Compliance Manager as well as any templates your organization has modified or created.</span></span> <span data-ttu-id="f9334-381">您可以应用筛选器，以查找基于证书、产品范围、国家、行业和创建的模板的模板。</span><span class="sxs-lookup"><span data-stu-id="f9334-381">You can apply filters to find a template based on certification, product scope, country, industry, and who created it.</span></span>

<span data-ttu-id="f9334-382">从其行中选择一个模板，以显示其详细信息页，其中包含有关该模板的说明以及有关证书、范围和控件详细信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9334-382">Select a template from its row to bring up its details page, which contains a description of the template and further information about certification, scope, and controls details.</span></span> <span data-ttu-id="f9334-383">在此页面上，您可以选择相应的按钮来创建评估、将模板数据导出到 Excel 或修改模板。</span><span class="sxs-lookup"><span data-stu-id="f9334-383">From this page you can select the appropriate buttons to create an assessment, export the template data to Excel, or modify the template.</span></span>

<span data-ttu-id="f9334-384">**了解详细信息：** 了解 [如何使用评估模板](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="f9334-384">**Learn more:** [Read how to work with assessment templates](compliance-manager-templates.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="f9334-385">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f9334-385">Next step</span></span>
<span data-ttu-id="f9334-386">通过 [设置评估](compliance-manager-assessments.md)来自定义合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="f9334-386">Customize Compliance Manager by [setting up assessments](compliance-manager-assessments.md).</span></span>