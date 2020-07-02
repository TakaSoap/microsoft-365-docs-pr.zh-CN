---
title: Microsoft 合规性分数（预览）设置
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
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016187"
---
# <a name="compliance-score-preview-setup"></a><span data-ttu-id="a40e4-103">合规性分数（预览）设置</span><span class="sxs-lookup"><span data-stu-id="a40e4-103">Compliance Score (preview) setup</span></span>

<span data-ttu-id="a40e4-104">**本文内容：** 了解如何**访问**合规性分数、设置**角色和权限**，以及如何配置**自动安全得分更新**。</span><span class="sxs-lookup"><span data-stu-id="a40e4-104">**In this article:** Understand how to **access** Compliance Score, set **roles and permissions**, and configure **automatic Secure Score updates**.</span></span> <span data-ttu-id="a40e4-105">本文还介绍了主要合规性分数页面：**您的仪表板**、"改进操作" 页面、"解决方案" 页和 "评估" 页面。</span><span class="sxs-lookup"><span data-stu-id="a40e4-105">This article also explains the main Compliance Score pages: **your dashboard**, the improvement actions page, the solutions page, and the assessments page.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a40e4-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="a40e4-106">Before you begin</span></span>

<span data-ttu-id="a40e4-107">您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性分数的用户。</span><span class="sxs-lookup"><span data-stu-id="a40e4-107">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="a40e4-108">我们建议全局管理员登录并设置用户权限，如第一次访问合规性得分时所述。</span><span class="sxs-lookup"><span data-stu-id="a40e4-108">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="a40e4-109">登录</span><span class="sxs-lookup"><span data-stu-id="a40e4-109">Sign in</span></span>

1. <span data-ttu-id="a40e4-110">请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员帐户**登录**。</span><span class="sxs-lookup"><span data-stu-id="a40e4-110">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="a40e4-111">在左侧导航窗格中选择 "**合规性分数**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-111">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="a40e4-112">然后，您应看到[符合性分数仪表板与您的分数](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-112">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="a40e4-113">访问合规性分数的直接链接为 [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) 。</span><span class="sxs-lookup"><span data-stu-id="a40e4-113">The direct link to access Compliance Score is [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="a40e4-114">设置用户权限并分配角色</span><span class="sxs-lookup"><span data-stu-id="a40e4-114">Set user permissions and assign roles</span></span>

<span data-ttu-id="a40e4-115">合规性分数使用基于角色的访问控制（RBAC）权限模型。</span><span class="sxs-lookup"><span data-stu-id="a40e4-115">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="a40e4-116">只有分配有角色的用户才可以访问合规性分数，并且每个用户允许的操作受角色类型的限制。</span><span class="sxs-lookup"><span data-stu-id="a40e4-116">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="a40e4-117">设置权限的位置</span><span class="sxs-lookup"><span data-stu-id="a40e4-117">Where to set permissions</span></span>

<span data-ttu-id="a40e4-118">拥有组织的全局管理员角色的人员可以在[Azure Active Directory （AZURE AD）](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)或[合规性管理器](compliance-manager-overview.md#permissions)中设置用户权限。</span><span class="sxs-lookup"><span data-stu-id="a40e4-118">The person holding the global admin role for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="a40e4-119">一旦在这两个位置中设置了角色，用户就可以访问合规性分数以及合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="a40e4-119">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="a40e4-120">角色类型</span><span class="sxs-lookup"><span data-stu-id="a40e4-120">Role types</span></span>

<span data-ttu-id="a40e4-121">下表显示了每个[AZURE AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)如何映射到现有合规性管理器角色，以及每个角色允许的功能。</span><span class="sxs-lookup"><span data-stu-id="a40e4-121">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="a40e4-122">用户将至少需要 Azure AD 全局读取器角色才能访问合规性分数。</span><span class="sxs-lookup"><span data-stu-id="a40e4-122">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="a40e4-123">用户可以：</span><span class="sxs-lookup"><span data-stu-id="a40e4-123">User can:</span></span> | <span data-ttu-id="a40e4-124">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="a40e4-124">Azure AD role</span></span> | <span data-ttu-id="a40e4-125">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="a40e4-125">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="a40e4-126">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="a40e4-126">**Read but not edit data**</span></span>| <span data-ttu-id="a40e4-127">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="a40e4-127">Azure AD global reader</span></span>  | <span data-ttu-id="a40e4-128">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="a40e4-128">Azure AD global reader</span></span> | 
| <span data-ttu-id="a40e4-129">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="a40e4-129">**Read but not edit data**</span></span>| <span data-ttu-id="a40e4-130">安全读者</span><span class="sxs-lookup"><span data-stu-id="a40e4-130">Security reader</span></span> | <span data-ttu-id="a40e4-131">合规性管理器阅读器</span><span class="sxs-lookup"><span data-stu-id="a40e4-131">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="a40e4-132">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="a40e4-132">**Edit data**</span></span>| <span data-ttu-id="a40e4-133">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-133">Compliance administrator</span></span> | <span data-ttu-id="a40e4-134">合规性管理器参与者</span><span class="sxs-lookup"><span data-stu-id="a40e4-134">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="a40e4-135">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="a40e4-135">**Edit test results**</span></span>| <span data-ttu-id="a40e4-136">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-136">Compliance administrator</span></span> | <span data-ttu-id="a40e4-137">合规性管理器评估员</span><span class="sxs-lookup"><span data-stu-id="a40e4-137">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="a40e4-138">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="a40e4-138">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="a40e4-139">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-139">Compliance administrator</span></span><br><span data-ttu-id="a40e4-140">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-140">Compliance data administrator</span></span><br><span data-ttu-id="a40e4-141">安全管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-141">Security administrator</span></span> | <span data-ttu-id="a40e4-142">合规性管理器管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-142">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="a40e4-143">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="a40e4-143">**Assign users**</span></span>| <span data-ttu-id="a40e4-144">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-144">Global administrator</span></span> | <span data-ttu-id="a40e4-145">门户管理员</span><span class="sxs-lookup"><span data-stu-id="a40e4-145">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="a40e4-146">当您从符合性分数转到合规性管理器以在公共预览过程中完成任务时，浏览器将打开一个新选项卡，并显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="a40e4-146">When you go from Compliance Score to Compliance Manager to complete a task during public preview, your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="a40e4-147">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="a40e4-147">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="a40e4-148">登录您的帐户，选择 "**登录**以访问合规性管理器"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-148">Sign in to your account," select **Sign In** to access Compliance Manager.</span></span> <span data-ttu-id="a40e4-149">您无需重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="a40e4-149">You won't need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="a40e4-150">配置自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="a40e4-150">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="a40e4-151">默认情况下，所有新租户都启用了[安全分数](../security/mtp/microsoft-secure-score-new.md)自动更新。</span><span class="sxs-lookup"><span data-stu-id="a40e4-151">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score-new.md) automatic updates turned on.</span></span> <span data-ttu-id="a40e4-152">安全分数监控的所有操作将自动更新合规性分数中相同操作的状态。</span><span class="sxs-lookup"><span data-stu-id="a40e4-152">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="a40e4-153">全局管理员可以管理此设置，以关闭所有操作的自动更新，或者分别设置各个操作的更新。</span><span class="sxs-lookup"><span data-stu-id="a40e4-153">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="a40e4-154">在公共预览过程中，需要转到 Microsoft 服务信任门户（其中合规性管理器位于其中）以管理安全得分更新。</span><span class="sxs-lookup"><span data-stu-id="a40e4-154">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="a40e4-155">若要管理自动安全得分更新，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a40e4-155">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="a40e4-156">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-156">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="a40e4-157">在服务信任门户顶部菜单栏上的 "**更多**" 下，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-157">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="a40e4-158">在 "**安全分数**" 选项卡中，选择相应的按钮以**打开所有操作**、为**所有操作**禁用或设置 "**每个操作"。**</span><span class="sxs-lookup"><span data-stu-id="a40e4-158">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="a40e4-159">如果选择 **"每个操作设置"，请**执行以下额外步骤，为单个操作打开安全得分更新：</span><span class="sxs-lookup"><span data-stu-id="a40e4-159">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="a40e4-160">从顶部菜单中选择 "**合规性管理器**" （不要选择 "合规性管理器（经典）"）。</span><span class="sxs-lookup"><span data-stu-id="a40e4-160">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic),").</span></span>

5. <span data-ttu-id="a40e4-161">选择屏幕右上角的 "**租户管理**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-161">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="a40e4-162">在 "**客户操作**" 窗格上，使用 "**受影响的操作**" 列下的省略号（**...**）查找预期操作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-162">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="a40e4-163">单击省略号，然后选择 "**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="a40e4-163">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="a40e4-164">将 "**安全分数连续更新**" 切换开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="a40e4-164">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="a40e4-165">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="a40e4-165">Select **Save.**</span></span> <span data-ttu-id="a40e4-166">现已为该操作启用安全分数连续监控。</span><span class="sxs-lookup"><span data-stu-id="a40e4-166">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="a40e4-167">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="a40e4-167">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="a40e4-168">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-168">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="a40e4-169">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="a40e4-169">Learn more</span></span>

<span data-ttu-id="a40e4-170">[阅读有关管理安全得分更新的信息](compliance-manager-release-notes.md#secure-score)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-170">[Read about managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="a40e4-171">了解合规性分数仪表板</span><span class="sxs-lookup"><span data-stu-id="a40e4-171">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="a40e4-172">合规性分数仪表板旨在向您提供当前合规性状况的一览视图。</span><span class="sxs-lookup"><span data-stu-id="a40e4-172">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="a40e4-173">![合规性分数-仪表板](../media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="a40e4-173">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="a40e4-174">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="a40e4-174">Overall compliance score</span></span>

<span data-ttu-id="a40e4-175">你的合规性分数在顶部一目了然。</span><span class="sxs-lookup"><span data-stu-id="a40e4-175">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="a40e4-176">它显示的百分比取决于完成解决关键数据保护标准和法规的提高操作所能实现的积分。</span><span class="sxs-lookup"><span data-stu-id="a40e4-176">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="a40e4-177">首次遇到合规性得分时，最初的分数基于内置的[Microsoft 365 数据保护基准](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)，这是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="a40e4-177">When you come to Compliance Score for the first time, your initial score is based on the built-in [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="a40e4-178">合规性分数扫描您现有的 Microsoft 365 解决方案，并根据您当前的隐私和安全设置为您提供初步评估。</span><span class="sxs-lookup"><span data-stu-id="a40e4-178">Compliance Score scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="a40e4-179">在添加与您的组织相关的评估时，您的分数将对您更有意义。</span><span class="sxs-lookup"><span data-stu-id="a40e4-179">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="a40e4-180">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="a40e4-180">Learn more</span></span>
<span data-ttu-id="a40e4-181">[了解如何计算合规性分数](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-181">[Understand how your compliance score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="a40e4-182">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="a40e4-182">Key improvement actions</span></span>

<span data-ttu-id="a40e4-183">此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。</span><span class="sxs-lookup"><span data-stu-id="a40e4-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="a40e4-184">影响你的成绩的解决方案</span><span class="sxs-lookup"><span data-stu-id="a40e4-184">Solutions that affect your score</span></span>

<span data-ttu-id="a40e4-185">本部分介绍了一些解决方案，其中包含的操作具有最大的积极影响得分的机会，以及每个解决方案中未完成的改进操作的数量。</span><span class="sxs-lookup"><span data-stu-id="a40e4-185">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="a40e4-186">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="a40e4-186">Compliance Score breakdown</span></span>

<span data-ttu-id="a40e4-187">本节提供了以两种不同的方式更详细地查看分数：</span><span class="sxs-lookup"><span data-stu-id="a40e4-187">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="a40e4-188">**类别**：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-188">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="a40e4-189">**评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。</span><span class="sxs-lookup"><span data-stu-id="a40e4-189">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="a40e4-190">筛选你的仪表板视图</span><span class="sxs-lookup"><span data-stu-id="a40e4-190">Filtering your dashboard view</span></span>

<span data-ttu-id="a40e4-191">您可以筛选仪表板视图，以仅查看与特定法规和标准、解决方案、操作类型、评估组或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="a40e4-191">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="a40e4-192">以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。</span><span class="sxs-lookup"><span data-stu-id="a40e4-192">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="a40e4-193">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="a40e4-193">To apply filters:</span></span>

1. <span data-ttu-id="a40e4-194">选择仪表板右上侧的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-194">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="a40e4-195">从 "**筛选器**" 浮出控件窗格中选择筛选条件，然后选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-195">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="a40e4-196">在应用筛选器之后，你将看到实时调整的分数。</span><span class="sxs-lookup"><span data-stu-id="a40e4-196">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="a40e4-197">合规性分数百分比和细目信息以及改进操作和解决方案现在仅适用于您的筛选器条件所覆盖的数据。</span><span class="sxs-lookup"><span data-stu-id="a40e4-197">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="a40e4-198">如果你注销合规性分数，则在重新登录时将保留你的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="a40e4-198">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="a40e4-199">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="a40e4-199">To remove filters:</span></span>

- <span data-ttu-id="a40e4-200">在 "**应用的筛选器**" 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的**X** ;和</span><span class="sxs-lookup"><span data-stu-id="a40e4-200">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="a40e4-201">选择仪表板右上侧的 "**筛选器**"，然后选择 "**清除筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-201">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="a40e4-202">改进操作页</span><span class="sxs-lookup"><span data-stu-id="a40e4-202">Improvement actions page</span></span>

<span data-ttu-id="a40e4-203">[改进操作](compliance-score-improvement-actions.md)可集中管理合规性活动，并帮助您与数据保护法规和标准保持一致。</span><span class="sxs-lookup"><span data-stu-id="a40e4-203">[Improvement actions](compliance-score-improvement-actions.md) centralize your compliance activities and help you align with data protection regulations and standards.</span></span> <span data-ttu-id="a40e4-204">每个改进操作都提供了详细的实施指导和将您引导您进入适当解决方案的链接。</span><span class="sxs-lookup"><span data-stu-id="a40e4-204">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="a40e4-205">可将操作分配给组织中的用户，以执行实施和测试工作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-205">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="a40e4-206">您还可以在 "改进" 操作中存储文档、注释和记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="a40e4-206">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="a40e4-207">查看改进操作</span><span class="sxs-lookup"><span data-stu-id="a40e4-207">View your improvement actions</span></span>

<span data-ttu-id="a40e4-208">合规性分数仪表板显示了**关键改进操作**，这些操作是最重要的问题最多的可用点。</span><span class="sxs-lookup"><span data-stu-id="a40e4-208">The Compliance Score dashboard shows your **key improvement actions**, which are the ones with the most available points that address the most important issues.</span></span>

<span data-ttu-id="a40e4-209">若要查看所有改进操作，请选择仪表板上的 "**改进操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a40e4-209">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard.</span></span> <span data-ttu-id="a40e4-210">或者，选择 "查看仪表板上的关键改进操作列表下的**所有改善操作**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-210">Or, select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span>

<span data-ttu-id="a40e4-211">如果您的操作列表很长，则筛选视图可能很有帮助。</span><span class="sxs-lookup"><span data-stu-id="a40e4-211">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="a40e4-212">选择 "操作" 列表右上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-212">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="a40e4-213">当 "**筛选器**" 浮出控件窗格出现时，选择基于法规和标准、解决方案和组的标准。</span><span class="sxs-lookup"><span data-stu-id="a40e4-213">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="a40e4-214">您还可以通过选择右上角的 "**组**" 来自定义您的视图。</span><span class="sxs-lookup"><span data-stu-id="a40e4-214">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="a40e4-215">从下拉菜单中，选择按组、解决方案、类别、操作类型或状态进行查看。</span><span class="sxs-lookup"><span data-stu-id="a40e4-215">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="a40e4-216">此页面的默认视图不显示测试状态为 "已**通过**" 的提高操作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-216">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="a40e4-217">若要查看已通过测试的操作，请选中 "筛选器浮出控件" 窗格中的 "**传递**" 框。</span><span class="sxs-lookup"><span data-stu-id="a40e4-217">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="a40e4-218">仅具有已**通过**的测试状态与得分接近的操作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-218">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="a40e4-219">"改进操作" 页显示每个改进操作的以下数据点：</span><span class="sxs-lookup"><span data-stu-id="a40e4-219">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="a40e4-220">**得分影响**：完成操作时，整体得分将增加的点数</span><span class="sxs-lookup"><span data-stu-id="a40e4-220">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="a40e4-221">**法规**：与操作相关的法规或标准</span><span class="sxs-lookup"><span data-stu-id="a40e4-221">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="a40e4-222">**组**：为其分配操作的组</span><span class="sxs-lookup"><span data-stu-id="a40e4-222">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="a40e4-223">**解决方案**：可在其中执行操作的解决方案</span><span class="sxs-lookup"><span data-stu-id="a40e4-223">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="a40e4-224">**评估**：评估（它会对控制以满足特定合规性目标进行组织），操作驻留在其中</span><span class="sxs-lookup"><span data-stu-id="a40e4-224">**Assessments**: the assessment (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="a40e4-225">**类别**：相关的数据保护类别（例如，保护信息、管理设备等）</span><span class="sxs-lookup"><span data-stu-id="a40e4-225">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="a40e4-226">**测试状态**：</span><span class="sxs-lookup"><span data-stu-id="a40e4-226">**Test status**:</span></span>
    - <span data-ttu-id="a40e4-227">**无**–未记录状态更新</span><span class="sxs-lookup"><span data-stu-id="a40e4-227">**None** – no status update recorded</span></span>
    - <span data-ttu-id="a40e4-228">**未评估**-测试尚未启动</span><span class="sxs-lookup"><span data-stu-id="a40e4-228">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="a40e4-229">已成功测试已**通过**的实施</span><span class="sxs-lookup"><span data-stu-id="a40e4-229">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="a40e4-230">**失败的低风险**-测试失败，低风险</span><span class="sxs-lookup"><span data-stu-id="a40e4-230">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="a40e4-231">**失败中等风险**-测试失败，中等风险</span><span class="sxs-lookup"><span data-stu-id="a40e4-231">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="a40e4-232">**失败的高风险**-测试失败，高风险</span><span class="sxs-lookup"><span data-stu-id="a40e4-232">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="a40e4-233">**不在范围**内-操作不在评估范围内，也不会影响你的成绩</span><span class="sxs-lookup"><span data-stu-id="a40e4-233">**Not in scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="a40e4-234">**若要检测-若要**进行手动测试，表明已实现操作但未测试;对于自动测试，指示某个操作正在等待自动化结果</span><span class="sxs-lookup"><span data-stu-id="a40e4-234">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="a40e4-235">**无法检测**-无法确定自动状态</span><span class="sxs-lookup"><span data-stu-id="a40e4-235">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="a40e4-236">**部分测试**–对部分点获奖的自动化评分</span><span class="sxs-lookup"><span data-stu-id="a40e4-236">**Partially tested** – automated scoring that awards partial points</span></span>
- <span data-ttu-id="a40e4-237">**实现的分数**：最大可能的最大分数</span><span class="sxs-lookup"><span data-stu-id="a40e4-237">**Points achieved**: number of points earned out of the maximum possible</span></span>

#### <a name="learn-more"></a><span data-ttu-id="a40e4-238">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="a40e4-238">Learn more</span></span>
<span data-ttu-id="a40e4-239">[请参阅如何分配和执行改进操作的操作](compliance-score-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-239">[See how to assign and perform work on improvement actions](compliance-score-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="a40e4-240">解决方案页</span><span class="sxs-lookup"><span data-stu-id="a40e4-240">Solutions page</span></span>

<span data-ttu-id="a40e4-241">"解决方案" 页显示按解决方案组织的挣和潜在点的份额。</span><span class="sxs-lookup"><span data-stu-id="a40e4-241">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="a40e4-242">查看此视图中的剩余点和改进操作可帮助您了解哪些解决方案需要更直接关注。</span><span class="sxs-lookup"><span data-stu-id="a40e4-242">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="a40e4-243">通过选择 "合规性分数" 仪表板上的 "**解决方案**" 选项卡查找 "解决方案" 页。</span><span class="sxs-lookup"><span data-stu-id="a40e4-243">Find the solutions page by selecting the **Solutions** tab on your Compliance Score dashboard.</span></span> <span data-ttu-id="a40e4-244">您还可以选择 "查看下面的**所有解决方案** **，这些解决方案将影响您**的仪表板的右上部分中的分数。</span><span class="sxs-lookup"><span data-stu-id="a40e4-244">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="a40e4-245">筛选解决方案视图</span><span class="sxs-lookup"><span data-stu-id="a40e4-245">Filtering your solutions view</span></span>

<span data-ttu-id="a40e4-246">筛选解决方案视图：</span><span class="sxs-lookup"><span data-stu-id="a40e4-246">To filter your view of solutions:</span></span>

1. <span data-ttu-id="a40e4-247">选择评估列表左上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-247">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="a40e4-248">在 "**筛选器**" 浮出控件窗格中，在所需条件（标准和规章、解决方案、操作类型、合规性管理器组、类别）旁边进行检查。</span><span class="sxs-lookup"><span data-stu-id="a40e4-248">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="a40e4-249">选择 "**应用**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a40e4-249">Select the **Apply** button.</span></span> <span data-ttu-id="a40e4-250">筛选窗格将关闭，你将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="a40e4-250">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="a40e4-251">您还可以通过从评估列表上方的**组**下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="a40e4-251">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solution-page"></a><span data-ttu-id="a40e4-252">从 "解决方案" 页采取操作</span><span class="sxs-lookup"><span data-stu-id="a40e4-252">Taking actions from the solution page</span></span>

<span data-ttu-id="a40e4-253">"解决方案" 页显示已连接到 "改进操作" 的组织解决方案。</span><span class="sxs-lookup"><span data-stu-id="a40e4-253">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="a40e4-254">该表列出了每个解决方案对总体成绩的贡献、在该解决方案中实现的分数提升点，以及在该解决方案中分组的其余改进操作的数量，该解决方案可增加成绩。</span><span class="sxs-lookup"><span data-stu-id="a40e4-254">The table lists each solution’s contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="a40e4-255">可以通过以下两种方法从该屏幕执行操作：</span><span class="sxs-lookup"><span data-stu-id="a40e4-255">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="a40e4-256">在预期解决方案的行上，在 "**剩余操作**" 列下，选择超链接编号。</span><span class="sxs-lookup"><span data-stu-id="a40e4-256">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="a40e4-257">你将看到 "改进操作" 屏幕的筛选视图，其中显示了该解决方案的未经测试的改进操作。</span><span class="sxs-lookup"><span data-stu-id="a40e4-257">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="a40e4-258">在预期解决方案的行中的 "**打开解决方案**" 列下，选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-258">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="a40e4-259">你将在 Microsoft 365 和 Office 365 安全与合规中心中看到解决方案或位置，你可以采取建议的措施。</span><span class="sxs-lookup"><span data-stu-id="a40e4-259">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="a40e4-260">评估页</span><span class="sxs-lookup"><span data-stu-id="a40e4-260">Assessments page</span></span>

<span data-ttu-id="a40e4-261">"评估" 页面列出了您为您的组织设置的所有[评估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="a40e4-261">The assessments page lists all the [assessments](compliance-score-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="a40e4-262">您的合规性分数分母由所有跟踪的评估决定。</span><span class="sxs-lookup"><span data-stu-id="a40e4-262">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="a40e4-263">您添加的评定越多，您在改进操作页面上看到的改进操作越多，分数分母越高。</span><span class="sxs-lookup"><span data-stu-id="a40e4-263">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="a40e4-264">此页面汇总了每个评估的关键信息：</span><span class="sxs-lookup"><span data-stu-id="a40e4-264">This page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="a40e4-265">**评估**：评估的名称</span><span class="sxs-lookup"><span data-stu-id="a40e4-265">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="a40e4-266">**状态**：</span><span class="sxs-lookup"><span data-stu-id="a40e4-266">**Status**:</span></span>
    - <span data-ttu-id="a40e4-267">**完成**-所有控件的状态均为 "已通过"，或者至少传递了一个，其余部分为 "超出范围"</span><span class="sxs-lookup"><span data-stu-id="a40e4-267">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="a40e4-268">**不完整**–至少一个控件的状态为 "failed"</span><span class="sxs-lookup"><span data-stu-id="a40e4-268">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="a40e4-269">**None** -尚未测试所有控件</span><span class="sxs-lookup"><span data-stu-id="a40e4-269">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="a40e4-270">**进度**改善操作具有任何其他状态，包括 "正在进行中"、"部分贷方" 或 "未检测到"</span><span class="sxs-lookup"><span data-stu-id="a40e4-270">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="a40e4-271">**评估进度**：完成工作所占的百分比（按成功测试的控件数衡量）</span><span class="sxs-lookup"><span data-stu-id="a40e4-271">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="a40e4-272">**改进操作**：满足控件实现的已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="a40e4-272">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="a40e4-273">**Microsoft 操作**：满足 microsoft 控件实现的已完成操作的数量</span><span class="sxs-lookup"><span data-stu-id="a40e4-273">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="a40e4-274">**组**：评估所属的组的名称</span><span class="sxs-lookup"><span data-stu-id="a40e4-274">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="a40e4-275">**产品**：关联的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="a40e4-275">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="a40e4-276">**法规**：适用于评估的规章标准、策略或法律</span><span class="sxs-lookup"><span data-stu-id="a40e4-276">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="a40e4-277">筛选评估视图</span><span class="sxs-lookup"><span data-stu-id="a40e4-277">Filtering your assessments view</span></span>

<span data-ttu-id="a40e4-278">筛选评估的视图：</span><span class="sxs-lookup"><span data-stu-id="a40e4-278">To filter you view of assessments:</span></span>

1. <span data-ttu-id="a40e4-279">选择评估列表左上角的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-279">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="a40e4-280">在 "**筛选器**" 浮出控件窗格中，检查所需的条件。</span><span class="sxs-lookup"><span data-stu-id="a40e4-280">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="a40e4-281">选择 "应用" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a40e4-281">Select the Apply button.</span></span> <span data-ttu-id="a40e4-282">筛选窗格将关闭，您将看到筛选出的视图。</span><span class="sxs-lookup"><span data-stu-id="a40e4-282">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="a40e4-283">您还可以通过从评估列表上方的**组**下拉菜单中选择分组类型来修改视图，以查看按组、产品或法规进行的评估。</span><span class="sxs-lookup"><span data-stu-id="a40e4-283">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="a40e4-284">默认评估</span><span class="sxs-lookup"><span data-stu-id="a40e4-284">Default assessment</span></span>

<span data-ttu-id="a40e4-285">默认情况下，你将在 "评估" 页面上看到 " [Microsoft 365 数据保护基准](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)评估"。</span><span class="sxs-lookup"><span data-stu-id="a40e4-285">By default, you'll see the [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) assessment on the assessments page.</span></span> <span data-ttu-id="a40e4-286">合规性分数还提供了几个现成的可供您使用的[模板](compliance-score-templates.md)来生成评估。</span><span class="sxs-lookup"><span data-stu-id="a40e4-286">Compliance Score also provides several ready to use [templates](compliance-score-templates.md) from which to build assessments.</span></span>

## <a name="next-step"></a><span data-ttu-id="a40e4-287">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a40e4-287">Next step</span></span>
<span data-ttu-id="a40e4-288">通过[设置评估](compliance-score-assessments.md)来自定义合规性分数。</span><span class="sxs-lookup"><span data-stu-id="a40e4-288">Customize Compliance Score by [setting up assessments](compliance-score-assessments.md).</span></span>