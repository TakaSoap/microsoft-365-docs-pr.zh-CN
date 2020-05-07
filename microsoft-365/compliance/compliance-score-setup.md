---
title: Microsoft 合规性分数设置
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
description: 了解如何设置和开始使用 Microsoft 合规性分数，这有助于简化和自动化风险评估。
ms.openlocfilehash: 7a0030ed417e21484717b6edf12406d2f5e760e5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140857"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="031b0-103">Microsoft 合规性分数（预览）设置</span><span class="sxs-lookup"><span data-stu-id="031b0-103">Microsoft Compliance Score (preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="031b0-104">准备工作</span><span class="sxs-lookup"><span data-stu-id="031b0-104">Before you begin</span></span>

<span data-ttu-id="031b0-105">您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性分数的用户。</span><span class="sxs-lookup"><span data-stu-id="031b0-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="031b0-106">如果首次访问合规性分数，我们建议全局管理员登录并设置以下所述的用户权限。</span><span class="sxs-lookup"><span data-stu-id="031b0-106">We recommend the global admin sign-in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="031b0-107">登录</span><span class="sxs-lookup"><span data-stu-id="031b0-107">Sign in</span></span>

1. <span data-ttu-id="031b0-108">请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员帐户**登录**。</span><span class="sxs-lookup"><span data-stu-id="031b0-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="031b0-109">在左侧导航窗格中选择 "**合规性分数**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="031b0-110">然后，您应看到[符合性分数仪表板与您的分数](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="031b0-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="031b0-111">访问合规性分数的直接链接为： [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)。</span><span class="sxs-lookup"><span data-stu-id="031b0-111">The direct link to access Compliance Score is: [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="031b0-112">设置用户权限并分配角色</span><span class="sxs-lookup"><span data-stu-id="031b0-112">Set user permissions and assign roles</span></span>

<span data-ttu-id="031b0-113">合规性分数使用基于角色的访问控制（RBAC）权限模型。</span><span class="sxs-lookup"><span data-stu-id="031b0-113">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="031b0-114">只有分配有角色的用户才可以访问合规性分数，并且每个用户允许的操作受角色类型的限制。</span><span class="sxs-lookup"><span data-stu-id="031b0-114">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="031b0-115">设置权限的位置</span><span class="sxs-lookup"><span data-stu-id="031b0-115">Where to set permissions</span></span>

<span data-ttu-id="031b0-116">您的组织的全局管理员可以在[Azure Active Directory （AZURE AD）](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)或[合规性管理器](compliance-manager-overview.md#permissions)中设置用户权限。</span><span class="sxs-lookup"><span data-stu-id="031b0-116">The global admin for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="031b0-117">一旦在这两个位置中设置了角色，用户就可以访问合规性分数以及合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="031b0-117">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="031b0-118">角色类型</span><span class="sxs-lookup"><span data-stu-id="031b0-118">Role types</span></span>

<span data-ttu-id="031b0-119">下表显示了每个[AZURE AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)如何映射到现有合规性管理器角色，以及每个角色允许的功能。</span><span class="sxs-lookup"><span data-stu-id="031b0-119">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="031b0-120">用户将至少需要 Azure AD 全局读取器角色才能访问合规性分数。</span><span class="sxs-lookup"><span data-stu-id="031b0-120">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="031b0-121">用户可以：</span><span class="sxs-lookup"><span data-stu-id="031b0-121">User can:</span></span> | <span data-ttu-id="031b0-122">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="031b0-122">Azure AD role</span></span> | <span data-ttu-id="031b0-123">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="031b0-123">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="031b0-124">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="031b0-124">**Read but not edit data**</span></span>| <span data-ttu-id="031b0-125">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="031b0-125">Azure AD global reader</span></span>  | <span data-ttu-id="031b0-126">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="031b0-126">Azure AD global reader</span></span> | 
| <span data-ttu-id="031b0-127">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="031b0-127">**Read but not edit data**</span></span>| <span data-ttu-id="031b0-128">安全读取者</span><span class="sxs-lookup"><span data-stu-id="031b0-128">Security reader</span></span> | <span data-ttu-id="031b0-129">合规性管理器阅读器</span><span class="sxs-lookup"><span data-stu-id="031b0-129">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="031b0-130">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="031b0-130">**Edit data**</span></span>| <span data-ttu-id="031b0-131">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-131">Compliance administrator</span></span> | <span data-ttu-id="031b0-132">合规性管理器参与者</span><span class="sxs-lookup"><span data-stu-id="031b0-132">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="031b0-133">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="031b0-133">**Edit test results**</span></span>| <span data-ttu-id="031b0-134">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-134">Compliance administrator</span></span> | <span data-ttu-id="031b0-135">合规性管理器评估员</span><span class="sxs-lookup"><span data-stu-id="031b0-135">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="031b0-136">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="031b0-136">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="031b0-137">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-137">Compliance administrator</span></span><br><span data-ttu-id="031b0-138">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-138">Compliance data administrator</span></span><br><span data-ttu-id="031b0-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-139">Security administrator</span></span> | <span data-ttu-id="031b0-140">合规性管理器管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-140">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="031b0-141">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="031b0-141">**Assign users**</span></span>| <span data-ttu-id="031b0-142">全局管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-142">Global administrator</span></span> | <span data-ttu-id="031b0-143">门户管理员</span><span class="sxs-lookup"><span data-stu-id="031b0-143">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="031b0-144">当您从符合性分数转到合规性管理器以完成任务（例如，管理评估）时，浏览器将打开一个新选项卡，并显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="031b0-144">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="031b0-145">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="031b0-145">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="031b0-146">登录您的帐户，选择 "**登录**以访问合规性管理器";您无需重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="031b0-146">Sign in to your account," select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="031b0-147">配置自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="031b0-147">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="031b0-148">默认情况下，所有新租户都启用了[安全分数](../security/mtp/microsoft-secure-score.md)自动更新。</span><span class="sxs-lookup"><span data-stu-id="031b0-148">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="031b0-149">安全分数监控的所有操作将自动更新合规性分数中相同操作的状态。</span><span class="sxs-lookup"><span data-stu-id="031b0-149">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="031b0-150">全局管理员可以管理此设置，以关闭所有操作的自动更新，或者分别设置各个操作的更新。</span><span class="sxs-lookup"><span data-stu-id="031b0-150">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="031b0-151">在公共预览过程中，需要转到 Microsoft 服务信任门户（其中合规性管理器位于其中）以管理安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="031b0-151">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="031b0-152">若要管理自动安全得分更新，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="031b0-152">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="031b0-153">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="031b0-153">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="031b0-154">在服务信任门户顶部菜单栏上的 "**更多**" 下，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-154">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="031b0-155">在 "**安全分数**" 选项卡中，选择相应的按钮以**打开所有操作**、为**所有操作**禁用或设置 "**每个操作"。**</span><span class="sxs-lookup"><span data-stu-id="031b0-155">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="031b0-156">如果选择 **"每个操作设置"，请**执行以下额外步骤，为单个操作打开安全得分更新：</span><span class="sxs-lookup"><span data-stu-id="031b0-156">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="031b0-157">从顶部菜单中选择 "**合规性管理器**" （不要选择 "合规性管理器（经典）"，这是旧产品）。</span><span class="sxs-lookup"><span data-stu-id="031b0-157">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic)," which is a legacy product).</span></span>

5. <span data-ttu-id="031b0-158">选择屏幕右上角的 "**租户管理**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-158">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="031b0-159">在 "**客户操作**" 窗格上，使用 "**受影响的操作**" 列下的省略号（**...**）查找预期操作。</span><span class="sxs-lookup"><span data-stu-id="031b0-159">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="031b0-160">单击省略号，然后选择 "**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="031b0-160">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="031b0-161">将 "**安全分数连续更新**" 切换开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="031b0-161">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="031b0-162">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="031b0-162">Select **Save.**</span></span> <span data-ttu-id="031b0-163">现已为该操作启用安全分数连续监控。</span><span class="sxs-lookup"><span data-stu-id="031b0-163">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="031b0-164">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="031b0-164">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="031b0-165">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="031b0-165">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="031b0-166">阅读有关[管理安全得分更新](compliance-manager-release-notes.md#secure-score)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="031b0-166">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="031b0-167">了解合规性分数仪表板</span><span class="sxs-lookup"><span data-stu-id="031b0-167">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="031b0-168">合规性分数仪表板旨在向您提供当前合规性状况的一览视图。</span><span class="sxs-lookup"><span data-stu-id="031b0-168">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="031b0-169">![合规性分数-仪表板](../media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="031b0-169">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="031b0-170">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="031b0-170">Overall compliance score</span></span>

<span data-ttu-id="031b0-171">你的合规性分数在顶部一目了然。</span><span class="sxs-lookup"><span data-stu-id="031b0-171">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="031b0-172">它显示的百分比取决于完成解决关键数据保护标准和法规的提高操作所能实现的积分。</span><span class="sxs-lookup"><span data-stu-id="031b0-172">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="031b0-173">首次遇到合规性得分时，最初的分数基于内置的 Microsoft 365 数据保护基准，这是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="031b0-173">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="031b0-174">由于合规性分数会扫描您的现有 Microsoft 365 解决方案的系统，因此它会根据您的组织当前启用的隐私和安全设置对合规性状态进行初始评估。</span><span class="sxs-lookup"><span data-stu-id="031b0-174">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="031b0-175">在添加与您的组织相关的评估时，分数会变得更有意义。</span><span class="sxs-lookup"><span data-stu-id="031b0-175">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="031b0-176">了解有关[如何计算你的分数的](compliance-score-methodology.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="031b0-176">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="031b0-177">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="031b0-177">Key improvement actions</span></span>

<span data-ttu-id="031b0-178">此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。</span><span class="sxs-lookup"><span data-stu-id="031b0-178">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="031b0-179">影响你的成绩的解决方案</span><span class="sxs-lookup"><span data-stu-id="031b0-179">Solutions that affect your score</span></span>

<span data-ttu-id="031b0-180">本部分介绍了一些解决方案，其中包含的操作具有最大的积极影响得分的机会，以及每个解决方案中未完成的改进操作的数量。</span><span class="sxs-lookup"><span data-stu-id="031b0-180">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="031b0-181">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="031b0-181">Compliance Score breakdown</span></span>

<span data-ttu-id="031b0-182">本节提供了以两种不同的方式更详细地查看分数：</span><span class="sxs-lookup"><span data-stu-id="031b0-182">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="031b0-183">**类别**：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。</span><span class="sxs-lookup"><span data-stu-id="031b0-183">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="031b0-184">**评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。</span><span class="sxs-lookup"><span data-stu-id="031b0-184">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="031b0-185">筛选你的仪表板视图</span><span class="sxs-lookup"><span data-stu-id="031b0-185">Filtering your dashboard view</span></span>

<span data-ttu-id="031b0-186">您可以筛选仪表板视图，以仅查看与特定管理法规和标准、解决方案、操作类型、[设置的评估组](working-with-compliance-manager.md#groups)或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="031b0-186">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="031b0-187">以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。</span><span class="sxs-lookup"><span data-stu-id="031b0-187">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="031b0-188">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="031b0-188">To apply filters:</span></span>

1. <span data-ttu-id="031b0-189">选择仪表板右上侧的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-189">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="031b0-190">从 "**筛选器**" 浮出控件窗格中选择筛选条件，然后选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-190">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="031b0-191">在应用筛选器之后，你将看到实时调整的分数。</span><span class="sxs-lookup"><span data-stu-id="031b0-191">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="031b0-192">合规性分数百分比和细目信息以及改进操作和解决方案现在仅适用于您的筛选器条件所覆盖的数据。</span><span class="sxs-lookup"><span data-stu-id="031b0-192">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="031b0-193">如果你注销合规性分数，则在重新登录时将保留你的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="031b0-193">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="031b0-194">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="031b0-194">To remove filters:</span></span>

- <span data-ttu-id="031b0-195">在 "**应用的筛选器**" 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的**X** ;和</span><span class="sxs-lookup"><span data-stu-id="031b0-195">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="031b0-196">选择仪表板右上侧的 "**筛选器**"，然后选择 "**清除筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="031b0-196">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="031b0-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="031b0-197">Next step</span></span>

<span data-ttu-id="031b0-198">访问[合规性分数](working-with-compliance-score.md)以了解如何采取行动以提高成绩的工作流。</span><span class="sxs-lookup"><span data-stu-id="031b0-198">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>