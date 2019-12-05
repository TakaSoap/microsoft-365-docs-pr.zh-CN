---
title: Microsoft 合规性分数设置
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
description: 了解如何登录、设置权限以及了解 Microsoft 合规性分数的仪表板，这有助于简化和自动化风险评估。
ms.openlocfilehash: 03bcc5663e3b57728eb4ba791bbcba9593e5afc7
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831175"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="3c149-103">Microsoft 合规性分数（预览）设置</span><span class="sxs-lookup"><span data-stu-id="3c149-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3c149-104">开始之前</span><span class="sxs-lookup"><span data-stu-id="3c149-104">Before you begin</span></span>

<span data-ttu-id="3c149-105">您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性分数的用户。</span><span class="sxs-lookup"><span data-stu-id="3c149-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="3c149-106">我们建议全局管理员登录并设置用户权限，如第一次访问合规性得分时所述。</span><span class="sxs-lookup"><span data-stu-id="3c149-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="3c149-107">登录</span><span class="sxs-lookup"><span data-stu-id="3c149-107">Sign in</span></span>

1. <span data-ttu-id="3c149-108">请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员帐户**登录**。</span><span class="sxs-lookup"><span data-stu-id="3c149-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="3c149-109">在左侧导航窗格中选择 "**合规性分数**"。</span><span class="sxs-lookup"><span data-stu-id="3c149-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="3c149-110">然后，您应看到[符合性分数仪表板与您的分数](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="3c149-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="3c149-111">设置用户权限并分配角色</span><span class="sxs-lookup"><span data-stu-id="3c149-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="3c149-112">合规性分数使用基于角色的访问控制（RBAC）权限模型。</span><span class="sxs-lookup"><span data-stu-id="3c149-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="3c149-113">只有分配有角色的用户才可以访问合规性分数，并且每个用户允许的操作受角色类型的限制。</span><span class="sxs-lookup"><span data-stu-id="3c149-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="3c149-114">设置权限的位置</span><span class="sxs-lookup"><span data-stu-id="3c149-114">Where to set permissions</span></span>

<span data-ttu-id="3c149-115">您的组织的全局管理员可以在 Microsoft 365 合规性中心或 Azure Active Directory （Azure AD）中设置用户权限。</span><span class="sxs-lookup"><span data-stu-id="3c149-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3c149-116">一旦在这两个位置中设置了角色，用户就能够访问合规性分数（以及合规性管理器）。</span><span class="sxs-lookup"><span data-stu-id="3c149-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="3c149-117">请注意，现有合规性管理器角色**不会**转移到合规性分数。</span><span class="sxs-lookup"><span data-stu-id="3c149-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="3c149-118">这意味着，如果之前在合规性管理器中分配了一个角色，该角色将不会向您授予对合规性分数的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3c149-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="3c149-119">全局管理员需要在 Microsoft 365 合规性中心或 Azure AD 中为你设置权限和角色，以便你可以访问合规性分数。</span><span class="sxs-lookup"><span data-stu-id="3c149-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="3c149-120">角色类型</span><span class="sxs-lookup"><span data-stu-id="3c149-120">Role types</span></span>

<span data-ttu-id="3c149-121">下表显示了每个 Microsoft 365 合规性中心角色如何映射到现有合规性管理器角色，以及每个角色所允许的功能。</span><span class="sxs-lookup"><span data-stu-id="3c149-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="3c149-122">用户可以：</span><span class="sxs-lookup"><span data-stu-id="3c149-122">User can:</span></span> | <span data-ttu-id="3c149-123">Microsoft 365 合规性中心角色</span><span class="sxs-lookup"><span data-stu-id="3c149-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="3c149-124">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="3c149-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="3c149-125">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="3c149-125">**Read but not edit data**</span></span>| <span data-ttu-id="3c149-126">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="3c149-126">Azure AD global reader</span></span>  | <span data-ttu-id="3c149-127">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="3c149-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="3c149-128">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="3c149-128">**Read but not edit data**</span></span>| <span data-ttu-id="3c149-129">安全读者</span><span class="sxs-lookup"><span data-stu-id="3c149-129">Security reader</span></span> | <span data-ttu-id="3c149-130">合规性管理器阅读器</span><span class="sxs-lookup"><span data-stu-id="3c149-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="3c149-131">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="3c149-131">**Edit data**</span></span>| <span data-ttu-id="3c149-132">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-132">Compliance administrator</span></span> | <span data-ttu-id="3c149-133">合规性管理器参与者</span><span class="sxs-lookup"><span data-stu-id="3c149-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="3c149-134">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="3c149-134">**Edit test results**</span></span>| <span data-ttu-id="3c149-135">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-135">Compliance administrator</span></span> | <span data-ttu-id="3c149-136">合规性管理器评估员</span><span class="sxs-lookup"><span data-stu-id="3c149-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="3c149-137">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="3c149-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="3c149-138">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-138">Compliance administrator</span></span><br><span data-ttu-id="3c149-139">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-139">Compliance data administrator</span></span><br><span data-ttu-id="3c149-140">安全管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-140">Security administrator</span></span> | <span data-ttu-id="3c149-141">合规性管理器管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="3c149-142">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="3c149-142">**Assign users**</span></span>| <span data-ttu-id="3c149-143">全局管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-143">Global administrator</span></span> | <span data-ttu-id="3c149-144">门户管理员</span><span class="sxs-lookup"><span data-stu-id="3c149-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="3c149-145">当您从符合性分数转到合规性管理器以完成任务（例如，管理评估）时，浏览器将打开一个新选项卡，并显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="3c149-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="3c149-146">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="3c149-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="3c149-147">登录您的帐户，选择 "**登录**以访问合规性管理器";您无需重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="3c149-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="3c149-148">如何在 Microsoft 365 合规性中心中设置权限和角色</span><span class="sxs-lookup"><span data-stu-id="3c149-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="3c149-149">要在 Microsoft 365 合规性中心中设置权限，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3c149-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="3c149-150">请转到[Microsoft 365 合规性中心](https://compliance.microsoft.com)并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3c149-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="3c149-151">在左侧导航窗格中选择 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="3c149-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="3c149-152">在此处，您可以查看角色和分配权限。</span><span class="sxs-lookup"><span data-stu-id="3c149-152">From here, you can view roles and assign permissions.</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="3c149-153">了解合规性分数仪表板</span><span class="sxs-lookup"><span data-stu-id="3c149-153">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="3c149-154">合规性分数仪表板旨在向您提供当前合规性状况的一览视图。</span><span class="sxs-lookup"><span data-stu-id="3c149-154">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="3c149-155">![合规性分数-仪表板](media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="3c149-155">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="3c149-156">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="3c149-156">Overall compliance score</span></span>

<span data-ttu-id="3c149-157">你的合规性分数，在顶部突出重点，显示了根据完成提高操作（解决关键数据保护标准和法规）实现的积分的百分比。</span><span class="sxs-lookup"><span data-stu-id="3c149-157">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span> 

<span data-ttu-id="3c149-158">首次遇到合规性得分时，最初的分数基于内置的 Microsoft 365 数据保护基准，这是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="3c149-158">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="3c149-159">由于合规性分数会扫描您的现有 Microsoft 365 解决方案的系统，因此它会根据您的组织当前启用的隐私和安全设置对合规性状态进行初始评估。</span><span class="sxs-lookup"><span data-stu-id="3c149-159">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="3c149-160">在添加与您的组织相关的评估时，分数会变得更有意义。</span><span class="sxs-lookup"><span data-stu-id="3c149-160">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="3c149-161">了解有关[如何计算你的分数的](compliance-score-methodology.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="3c149-161">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="3c149-162">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="3c149-162">Key improvement actions</span></span>

<span data-ttu-id="3c149-163">此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。</span><span class="sxs-lookup"><span data-stu-id="3c149-163">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="3c149-164">它列出了未完成或因具有高风险的评估而失败的操作。</span><span class="sxs-lookup"><span data-stu-id="3c149-164">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="3c149-165">影响你的成绩的解决方案</span><span class="sxs-lookup"><span data-stu-id="3c149-165">Solutions that affect your score</span></span>

<span data-ttu-id="3c149-166">此部分显示哪些解决方案包含的操作具有最大的积极影响得分的机会，以及每个解决方案中有多少未解决的改进操作。</span><span class="sxs-lookup"><span data-stu-id="3c149-166">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="3c149-167">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="3c149-167">Compliance Score breakdown</span></span>

<span data-ttu-id="3c149-168">本节提供了以两种不同的方式更详细地查看分数：</span><span class="sxs-lookup"><span data-stu-id="3c149-168">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="3c149-169">**类别**：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。</span><span class="sxs-lookup"><span data-stu-id="3c149-169">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="3c149-170">**评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。</span><span class="sxs-lookup"><span data-stu-id="3c149-170">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="3c149-171">筛选你的仪表板视图</span><span class="sxs-lookup"><span data-stu-id="3c149-171">Filtering your dashboard view</span></span>

<span data-ttu-id="3c149-172">您可以筛选仪表板视图，以仅查看与特定法规和标准、解决方案、操作类型、组或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="3c149-172">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, groups, or data protection categories.</span></span> <span data-ttu-id="3c149-173">以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。</span><span class="sxs-lookup"><span data-stu-id="3c149-173">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="3c149-174">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="3c149-174">To apply filters:</span></span>

1. <span data-ttu-id="3c149-175">选择仪表板右上侧的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="3c149-175">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="3c149-176">从飞出的 "**筛选**器" 窗格中选择筛选条件，然后选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="3c149-176">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="3c149-177">你将看到实时调整了你的分数，你将只会看到符合你的筛选器条件的改进操作、解决方案和分数细分信息。</span><span class="sxs-lookup"><span data-stu-id="3c149-177">You will see your score adjusted in real-time, and you will only see improvement actions, solutions, and score breakdown information that correspond to your filter criteria.</span></span> <span data-ttu-id="3c149-178">如果你注销合规性分数，则在重新登录时将保留你的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="3c149-178">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="3c149-179">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="3c149-179">To remove filters:</span></span>

- <span data-ttu-id="3c149-180">在 "**应用的筛选器**" 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的**X** ;和</span><span class="sxs-lookup"><span data-stu-id="3c149-180">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="3c149-181">选择仪表板右上侧的 "**筛选器**"，然后选择 "**清除筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="3c149-181">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="3c149-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3c149-182">Next step</span></span>

<span data-ttu-id="3c149-183">访问[合规性分数](working-with-compliance-score.md)以了解如何采取行动以提高成绩的工作流。</span><span class="sxs-lookup"><span data-stu-id="3c149-183">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>