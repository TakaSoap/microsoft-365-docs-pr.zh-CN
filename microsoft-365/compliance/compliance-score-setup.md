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
description: 了解如何登录、设置权限以及了解 Microsoft 合规性分数的仪表板，这有助于简化和自动化风险评估。
ms.openlocfilehash: a97fa1c0598fcab1660d71581fed2be8dafe8911
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595749"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="adaf9-103">Microsoft 合规性分数（预览）设置</span><span class="sxs-lookup"><span data-stu-id="adaf9-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="adaf9-104">开始之前</span><span class="sxs-lookup"><span data-stu-id="adaf9-104">Before you begin</span></span>

<span data-ttu-id="adaf9-105">您的组织的 Microsoft 365 全局管理员可能是第一个访问合规性分数的用户。</span><span class="sxs-lookup"><span data-stu-id="adaf9-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="adaf9-106">我们建议全局管理员登录并设置用户权限，如第一次访问合规性得分时所述。</span><span class="sxs-lookup"><span data-stu-id="adaf9-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="adaf9-107">登录</span><span class="sxs-lookup"><span data-stu-id="adaf9-107">Sign in</span></span>

1. <span data-ttu-id="adaf9-108">请转到[microsoft 365 合规性中心](https://compliance.microsoft.com/)并使用 microsoft 365 全局管理员帐户**登录**。</span><span class="sxs-lookup"><span data-stu-id="adaf9-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="adaf9-109">在左侧导航窗格中选择 "**合规性分数**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="adaf9-110">然后，您应看到[符合性分数仪表板与您的分数](#understand-the-compliance-score-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="adaf9-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="adaf9-111">设置用户权限并分配角色</span><span class="sxs-lookup"><span data-stu-id="adaf9-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="adaf9-112">合规性分数使用基于角色的访问控制（RBAC）权限模型。</span><span class="sxs-lookup"><span data-stu-id="adaf9-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="adaf9-113">只有分配有角色的用户才可以访问合规性分数，并且每个用户允许的操作受角色类型的限制。</span><span class="sxs-lookup"><span data-stu-id="adaf9-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="adaf9-114">设置权限的位置</span><span class="sxs-lookup"><span data-stu-id="adaf9-114">Where to set permissions</span></span>

<span data-ttu-id="adaf9-115">您的组织的全局管理员可以在 Microsoft 365 合规性中心或 Azure Active Directory （Azure AD）中设置用户权限。</span><span class="sxs-lookup"><span data-stu-id="adaf9-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="adaf9-116">一旦在这两个位置中设置了角色，用户就能够访问合规性分数（以及合规性管理器）。</span><span class="sxs-lookup"><span data-stu-id="adaf9-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="adaf9-117">请注意，现有合规性管理器角色**不会**转移到合规性分数。</span><span class="sxs-lookup"><span data-stu-id="adaf9-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="adaf9-118">这意味着，如果之前在合规性管理器中分配了一个角色，该角色将不会向您授予对合规性分数的访问权限。</span><span class="sxs-lookup"><span data-stu-id="adaf9-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="adaf9-119">全局管理员需要在 Microsoft 365 合规性中心或 Azure AD 中为你设置权限和角色，以便你可以访问合规性分数。</span><span class="sxs-lookup"><span data-stu-id="adaf9-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="adaf9-120">角色类型</span><span class="sxs-lookup"><span data-stu-id="adaf9-120">Role types</span></span>

<span data-ttu-id="adaf9-121">下表显示了每个 Microsoft 365 合规性中心角色如何映射到现有合规性管理器角色，以及每个角色所允许的功能。</span><span class="sxs-lookup"><span data-stu-id="adaf9-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="adaf9-122">用户可以：</span><span class="sxs-lookup"><span data-stu-id="adaf9-122">User can:</span></span> | <span data-ttu-id="adaf9-123">Microsoft 365 合规性中心角色</span><span class="sxs-lookup"><span data-stu-id="adaf9-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="adaf9-124">合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="adaf9-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="adaf9-125">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="adaf9-125">**Read but not edit data**</span></span>| <span data-ttu-id="adaf9-126">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="adaf9-126">Azure AD global reader</span></span>  | <span data-ttu-id="adaf9-127">Azure AD 全局读取器</span><span class="sxs-lookup"><span data-stu-id="adaf9-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="adaf9-128">**读取但不编辑数据**</span><span class="sxs-lookup"><span data-stu-id="adaf9-128">**Read but not edit data**</span></span>| <span data-ttu-id="adaf9-129">安全读者</span><span class="sxs-lookup"><span data-stu-id="adaf9-129">Security reader</span></span> | <span data-ttu-id="adaf9-130">合规性管理器阅读器</span><span class="sxs-lookup"><span data-stu-id="adaf9-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="adaf9-131">**编辑数据**</span><span class="sxs-lookup"><span data-stu-id="adaf9-131">**Edit data**</span></span>| <span data-ttu-id="adaf9-132">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-132">Compliance administrator</span></span> | <span data-ttu-id="adaf9-133">合规性管理器参与者</span><span class="sxs-lookup"><span data-stu-id="adaf9-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="adaf9-134">**编辑测试结果**</span><span class="sxs-lookup"><span data-stu-id="adaf9-134">**Edit test results**</span></span>| <span data-ttu-id="adaf9-135">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-135">Compliance administrator</span></span> | <span data-ttu-id="adaf9-136">合规性管理器评估员</span><span class="sxs-lookup"><span data-stu-id="adaf9-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="adaf9-137">**管理评估、模板和租户数据**</span><span class="sxs-lookup"><span data-stu-id="adaf9-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="adaf9-138">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-138">Compliance administrator</span></span><br><span data-ttu-id="adaf9-139">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-139">Compliance data administrator</span></span><br><span data-ttu-id="adaf9-140">安全管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-140">Security administrator</span></span> | <span data-ttu-id="adaf9-141">合规性管理器管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="adaf9-142">**分配用户**</span><span class="sxs-lookup"><span data-stu-id="adaf9-142">**Assign users**</span></span>| <span data-ttu-id="adaf9-143">全局管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-143">Global administrator</span></span> | <span data-ttu-id="adaf9-144">门户管理员</span><span class="sxs-lookup"><span data-stu-id="adaf9-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="adaf9-145">当您从符合性分数转到合规性管理器以完成任务（例如，管理评估）时，浏览器将打开一个新选项卡，并显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="adaf9-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="adaf9-146">在标题为 "已成为 Microsoft 云服务客户" 的顶部部分？</span><span class="sxs-lookup"><span data-stu-id="adaf9-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="adaf9-147">登录您的帐户，选择 "**登录**以访问合规性管理器";您无需重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="adaf9-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="adaf9-148">如何在 Microsoft 365 合规性中心中设置权限和角色</span><span class="sxs-lookup"><span data-stu-id="adaf9-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="adaf9-149">要在 Microsoft 365 合规性中心中设置权限，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adaf9-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="adaf9-150">请转到[Microsoft 365 合规性中心](https://compliance.microsoft.com)并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="adaf9-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="adaf9-151">在左侧导航窗格中选择 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="adaf9-152">在此处，您可以查看角色和分配权限。</span><span class="sxs-lookup"><span data-stu-id="adaf9-152">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="adaf9-153">配置自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="adaf9-153">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="adaf9-154">默认情况下，所有新租户都启用了[安全分数](../security/mtp/microsoft-secure-score.md)自动更新。</span><span class="sxs-lookup"><span data-stu-id="adaf9-154">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="adaf9-155">这意味着，安全得分监控的所有操作将自动更新合规性分数中相同操作的状态。</span><span class="sxs-lookup"><span data-stu-id="adaf9-155">This means that all actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="adaf9-156">全局管理员可以管理此设置，以关闭所有操作的自动更新，或者分别设置各个操作的更新。</span><span class="sxs-lookup"><span data-stu-id="adaf9-156">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="adaf9-157">在公共预览过程中，需要转到 Microsoft 服务信任门户（其中合规性管理器位于其中）以管理安全分数更新。</span><span class="sxs-lookup"><span data-stu-id="adaf9-157">During public preview, you will need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="adaf9-158">若要管理自动安全得分更新，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="adaf9-158">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="adaf9-159">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="adaf9-159">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="adaf9-160">在服务信任门户顶部菜单栏上的 "**更多**" 下，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-160">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="adaf9-161">在 "**安全分数**" 选项卡中，选择相应的按钮以**打开所有操作**、为**所有操作**禁用或设置 "**每个操作"。**</span><span class="sxs-lookup"><span data-stu-id="adaf9-161">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="adaf9-162">如果选择 **"每个操作设置"，请**执行以下额外步骤，为单个操作打开安全得分更新：</span><span class="sxs-lookup"><span data-stu-id="adaf9-162">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="adaf9-163">从顶部菜单中选择 "**合规性管理器**" （注意：不要选择 "合规性管理器（经典）"）。</span><span class="sxs-lookup"><span data-stu-id="adaf9-163">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="adaf9-164">选择屏幕右上角的 "**租户管理**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-164">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="adaf9-165">在 "**客户操作**" 窗格上，使用 "**受影响的操作**" 列下的省略号（**...**）查找预期操作。</span><span class="sxs-lookup"><span data-stu-id="adaf9-165">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="adaf9-166">单击省略号，然后选择 "**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="adaf9-166">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="adaf9-167">将 "**安全分数连续更新**" 切换开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="adaf9-167">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="adaf9-168">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="adaf9-168">Select **Save.**</span></span> <span data-ttu-id="adaf9-169">现已为该操作启用安全分数连续监控。</span><span class="sxs-lookup"><span data-stu-id="adaf9-169">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="adaf9-170">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="adaf9-170">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="adaf9-171">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="adaf9-171">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="adaf9-172">阅读有关[管理安全得分更新](compliance-manager-release-notes.md#secure-score)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="adaf9-172">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="adaf9-173">了解合规性分数仪表板</span><span class="sxs-lookup"><span data-stu-id="adaf9-173">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="adaf9-174">合规性分数仪表板旨在向您提供当前合规性状况的一览视图。</span><span class="sxs-lookup"><span data-stu-id="adaf9-174">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="adaf9-175">![合规性分数-仪表板](media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="adaf9-175">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="adaf9-176">总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="adaf9-176">Overall compliance score</span></span>

<span data-ttu-id="adaf9-177">你的合规性分数，在顶部突出重点，显示了根据完成提高操作（解决关键数据保护标准和法规）实现的积分的百分比。</span><span class="sxs-lookup"><span data-stu-id="adaf9-177">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span>

<span data-ttu-id="adaf9-178">首次遇到合规性得分时，最初的分数基于内置的 Microsoft 365 数据保护基准，这是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="adaf9-178">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="adaf9-179">由于合规性分数会扫描您的现有 Microsoft 365 解决方案的系统，因此它会根据您的组织当前启用的隐私和安全设置对合规性状态进行初始评估。</span><span class="sxs-lookup"><span data-stu-id="adaf9-179">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="adaf9-180">在添加与您的组织相关的评估时，分数会变得更有意义。</span><span class="sxs-lookup"><span data-stu-id="adaf9-180">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="adaf9-181">了解有关[如何计算你的分数的](compliance-score-methodology.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="adaf9-181">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="adaf9-182">关键改进操作</span><span class="sxs-lookup"><span data-stu-id="adaf9-182">Key improvement actions</span></span>

<span data-ttu-id="adaf9-183">此部分列出了您现在可以执行的首要改进操作，以对您的总体合规性分数产生最大的积极影响。</span><span class="sxs-lookup"><span data-stu-id="adaf9-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="adaf9-184">它列出了未完成或因具有高风险的评估而失败的操作。</span><span class="sxs-lookup"><span data-stu-id="adaf9-184">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="adaf9-185">影响你的成绩的解决方案</span><span class="sxs-lookup"><span data-stu-id="adaf9-185">Solutions that affect your score</span></span>

<span data-ttu-id="adaf9-186">此部分显示哪些解决方案包含的操作具有最大的积极影响得分的机会，以及每个解决方案中有多少未解决的改进操作。</span><span class="sxs-lookup"><span data-stu-id="adaf9-186">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="adaf9-187">合规性分数细分</span><span class="sxs-lookup"><span data-stu-id="adaf9-187">Compliance Score breakdown</span></span>

<span data-ttu-id="adaf9-188">本节提供了以两种不同的方式更详细地查看分数：</span><span class="sxs-lookup"><span data-stu-id="adaf9-188">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="adaf9-189">**类别**：显示数据保护类别中整体得分的百分比，例如 "保护信息" 或 "管理设备"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-189">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="adaf9-190">**评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）的评估进度的百分比。</span><span class="sxs-lookup"><span data-stu-id="adaf9-190">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="adaf9-191">筛选你的仪表板视图</span><span class="sxs-lookup"><span data-stu-id="adaf9-191">Filtering your dashboard view</span></span>

<span data-ttu-id="adaf9-192">您可以筛选仪表板视图，以仅查看与特定管理法规和标准、解决方案、操作类型、[设置的评估组](working-with-compliance-manager.md#groups)或数据保护类别相关的项目。</span><span class="sxs-lookup"><span data-stu-id="adaf9-192">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="adaf9-193">以这种方式筛选视图还将筛选仪表板上的分数，并根据筛选条件显示已实现的总积分数。</span><span class="sxs-lookup"><span data-stu-id="adaf9-193">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="adaf9-194">应用筛选器：</span><span class="sxs-lookup"><span data-stu-id="adaf9-194">To apply filters:</span></span>

1. <span data-ttu-id="adaf9-195">选择仪表板右上侧的 "**筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-195">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="adaf9-196">从飞出的 "**筛选**器" 窗格中选择筛选条件，然后选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-196">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="adaf9-197">应用筛选器后，您将看到实时调整的分数。</span><span class="sxs-lookup"><span data-stu-id="adaf9-197">Once a filter is applied, you will see your score adjusted in real-time.</span></span> <span data-ttu-id="adaf9-198">合规性分数百分比和细目信息以及改进操作和解决方案现在仅适用于您的筛选器条件所覆盖的数据。</span><span class="sxs-lookup"><span data-stu-id="adaf9-198">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="adaf9-199">如果你注销合规性分数，则在重新登录时将保留你的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="adaf9-199">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="adaf9-200">若要删除筛选器：</span><span class="sxs-lookup"><span data-stu-id="adaf9-200">To remove filters:</span></span>

- <span data-ttu-id="adaf9-201">在 "**应用的筛选器**" 标题高于您的合规性分数后，选择要删除的单个筛选器旁边的**X** ;和</span><span class="sxs-lookup"><span data-stu-id="adaf9-201">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="adaf9-202">选择仪表板右上侧的 "**筛选器**"，然后选择 "**清除筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="adaf9-202">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="adaf9-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="adaf9-203">Next step</span></span>

<span data-ttu-id="adaf9-204">访问[合规性分数](working-with-compliance-score.md)以了解如何采取行动以提高成绩的工作流。</span><span class="sxs-lookup"><span data-stu-id="adaf9-204">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>