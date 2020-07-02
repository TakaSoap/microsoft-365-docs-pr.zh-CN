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
ms.openlocfilehash: e12250c6f78759b2298bfb5ebba6ae79918a0fd9
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023389"
---
# <a name="working-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="c41ae-103">使用 Microsoft 合规性管理器（预览）</span><span class="sxs-lookup"><span data-stu-id="c41ae-103">Working with Microsoft Compliance Manager (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c41ae-104">Microsoft 合规性管理器是一个仪表板和管理工具，提供了有关数据保护和合规性的摘要 stature 以及改进数据保护和合规性的建议。</span><span class="sxs-lookup"><span data-stu-id="c41ae-104">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="c41ae-105">合规性管理器中提供的客户操作是建议。</span><span class="sxs-lookup"><span data-stu-id="c41ae-105">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="c41ae-106">在实现之前，你的组织可以评估这些建议在其各自的法规环境中的有效性。</span><span class="sxs-lookup"><span data-stu-id="c41ae-106">It is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="c41ae-107">合规性管理器中提供的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="c41ae-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="c41ae-108">Access 合规性管理器</span><span class="sxs-lookup"><span data-stu-id="c41ae-108">Access Compliance Manager</span></span>

<span data-ttu-id="c41ae-109">可从 Microsoft 服务信任门户访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="c41ae-109">Compliance Manager is accessible from the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="c41ae-110">拥有 Microsoft 帐户或 Azure Active Directory 组织帐户的任何人都可以访问合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="c41ae-110">Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>

1. <span data-ttu-id="c41ae-111">转到 [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3)。</span><span class="sxs-lookup"><span data-stu-id="c41ae-111">Go to [https://servicetrust.microsoft.com/ComplianceManager/V3](https://servicetrust.microsoft.com/ComplianceManager/V3).</span></span>

2. <span data-ttu-id="c41ae-112">使用 Microsoft 服务帐户（即 Office 365、Microsoft 365 或 Azure Active Directory （Azure AD）用户帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="c41ae-112">Sign in with your Microsoft service account, which is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-113">在服务信任门户中，选择 "**合规性管理器**"，它是具有最新功能的预览版本。</span><span class="sxs-lookup"><span data-stu-id="c41ae-113">In the Service Trust Portal, select **Compliance Manager**, which is the preview version with the most current features.</span></span> <span data-ttu-id="c41ae-114">请勿选择**合规性管理器（经典）**，其中包含本文档未涵盖的早期版本功能。</span><span class="sxs-lookup"><span data-stu-id="c41ae-114">Do not select **Compliance Manager (classic)**, which contains early-release features not covered by this documentation.</span></span>

## <a name="administration"></a><span data-ttu-id="c41ae-115">管理</span><span class="sxs-lookup"><span data-stu-id="c41ae-115">Administration</span></span>

<span data-ttu-id="c41ae-116">只有全局管理员可以使用特定的管理功能，并且只有在使用全局管理员帐户登录时才可见。</span><span class="sxs-lookup"><span data-stu-id="c41ae-116">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="c41ae-117">全局管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-117">The global administrator can:</span></span>
- [<span data-ttu-id="c41ae-118">分配用户角色</span><span class="sxs-lookup"><span data-stu-id="c41ae-118">Assign user roles</span></span>](#assigning-compliance-manager-roles-to-users)
- [<span data-ttu-id="c41ae-119">打开和关闭自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="c41ae-119">Turn on and off automatic Secure Score updates</span></span>](#controlling-automatic-secure-score-updates)
- [<span data-ttu-id="c41ae-120">配置用户隐私设置</span><span class="sxs-lookup"><span data-stu-id="c41ae-120">Configure user privacy settings</span></span>](#configuring-user-privacy-settings)
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="c41ae-121">向用户分配合规性管理器角色</span><span class="sxs-lookup"><span data-stu-id="c41ae-121">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="c41ae-122">一旦管理员将合规性管理器角色分配给其他用户，这些用户就可以在合规性管理器中查看数据，并执行角色所确定的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-122">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="c41ae-123">管理员还可以通过向用户分配[Azure Active Directory （AZURE AD）中的全局读取器角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)，授予对合规性管理器的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="c41ae-123">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="c41ae-124">每个合规性管理器角色都具有略有不同的权限。</span><span class="sxs-lookup"><span data-stu-id="c41ae-124">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="c41ae-125">您可以查看分配给每个角色的权限，查看哪些用户是哪些角色，以及通过服务信任门户在该角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-125">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="c41ae-126">选择 "**管理**" 菜单项，然后选择 "要查看的**设置**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-126">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理菜单：选择的设置](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="c41ae-128">若要在合规性管理器角色中添加或删除用户，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-128">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="c41ae-129">转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c41ae-129">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="c41ae-130">使用 Azure Active Directory 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c41ae-130">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="c41ae-131">在 "服务信任门户" 顶部菜单栏上，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-131">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="c41ae-132">在 "**选择角色**" 下拉列表中，选择要管理的角色。</span><span class="sxs-lookup"><span data-stu-id="c41ae-132">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="c41ae-133">“**选择角色**”页上会列出已添加到每个角色的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-133">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="c41ae-134">若要将用户添加到此角色，请选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-134">To add users to this role, select **Add**.</span></span> <span data-ttu-id="c41ae-135">在 "**添加用户**" 对话框中，选择 "用户" 字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-135">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="c41ae-136">您可以在可用用户列表中滚动，也可以开始键入用户名，以根据您的搜索词筛选列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-136">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="c41ae-137">选择要将该帐户添加到使用该角色预配的 "**添加用户**" 列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-137">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="c41ae-138">如果要同时添加多个用户，请开始键入用户名以筛选列表，然后选择要添加到列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-138">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="c41ae-139">选择 "**保存**" 将所选角色设置给这些用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-139">Select **Save** to provision the selected role to these users.</span></span> 

    ![合规性管理器-添加用户](../media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="c41ae-141">若要从此角色中删除用户，请选择 "用户"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-141">To remove users from this role, select the users and select **Delete**.</span></span>

    ![合规性管理器-删除用户](../media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="c41ae-143">控制自动安全得分更新</span><span class="sxs-lookup"><span data-stu-id="c41ae-143">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="c41ae-144">可以为所有操作自动启用安全分数更新，对所有操作关闭这些更新，或通过执行以下步骤设置单个操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-144">Secure Score updates can be turned on automatically for all actions, turned off for all actions, or set by individual action by following these steps.</span></span>

1. <span data-ttu-id="c41ae-145">使用全局管理员帐户登录到[服务信任门户](https://servicetrust.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c41ae-145">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="c41ae-146">在服务信任门户顶部菜单栏上的 "**更多**" 下，选择 "**管理员**"，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-146">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="c41ae-147">在 "**安全分数**" 选项卡中，选择相应的按钮以**打开所有操作**、为**所有操作**禁用或设置 "**每个操作"。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-147">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="c41ae-148">如果选择 **"每个操作设置"，请**执行以下额外步骤，为单个操作打开安全得分更新：</span><span class="sxs-lookup"><span data-stu-id="c41ae-148">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="c41ae-149">从顶部菜单中选择 "**合规性管理器**" （注意：不要选择 "合规性管理器（经典）"）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-149">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="c41ae-150">选择屏幕右上角的 "**租户管理**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-150">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="c41ae-151">在 "**客户操作**" 窗格上，使用 "**受影响的操作**" 列下的省略号（**...**）查找预期操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-151">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="c41ae-152">单击省略号，然后选择 "**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-152">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="c41ae-153">将 "**安全分数连续更新**" 切换开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-153">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="c41ae-154">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-154">Select **Save.**</span></span> <span data-ttu-id="c41ae-155">现已为该操作启用安全分数连续监控。</span><span class="sxs-lookup"><span data-stu-id="c41ae-155">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="c41ae-156">**注意：** 只有全局管理员才能打开或关闭所有操作的自动更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-156">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="c41ae-157">合规性管理器管理员可以为单个操作启用自动更新，而不是全局执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-157">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

### <a name="configuring-user-privacy-settings"></a><span data-ttu-id="c41ae-158">配置用户隐私设置</span><span class="sxs-lookup"><span data-stu-id="c41ae-158">Configuring user privacy settings</span></span>

<span data-ttu-id="c41ae-159">某些法规要求组织能够删除用户历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-159">Certain regulations require an organization to be able to delete user history data.</span></span> <span data-ttu-id="c41ae-160">若要启用此功能，**用户隐私设置**功能允许管理员执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-160">To enable this, the **User Privacy Settings** functions allow administrators to:</span></span>
  
- [<span data-ttu-id="c41ae-161">搜索用户</span><span class="sxs-lookup"><span data-stu-id="c41ae-161">Search for a user</span></span>](#search-for-a-user)

- [<span data-ttu-id="c41ae-162">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="c41ae-162">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)

- [<span data-ttu-id="c41ae-163">重新分配行动项</span><span class="sxs-lookup"><span data-stu-id="c41ae-163">Reassign action items</span></span>](#reassign-action-items)

- [<span data-ttu-id="c41ae-164">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="c41ae-164">Delete user data history</span></span>](#delete-user-data-history)
    
![合规性管理器管理员 —“用户隐私设置”功能](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
#### <a name="search-for-a-user"></a><span data-ttu-id="c41ae-166">搜索用户</span><span class="sxs-lookup"><span data-stu-id="c41ae-166">Search for a user</span></span>

<span data-ttu-id="c41ae-167">若要搜索用户帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-167">To search for a user account:</span></span>
  
1. <span data-ttu-id="c41ae-168">键入别名（@ 符号左侧的信息）并通过单击右侧的域后缀列表选择域名，从而输入用户电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c41ae-168">Enter the user email address by typing in the alias (the information to the left of the @ symbol) and choosing the domain name by clicking the domain suffix list on the right.</span></span> <span data-ttu-id="c41ae-169">如果您的组织具有多个注册的域，则可以仔细检查电子邮件地址域名后缀以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="c41ae-169">If your organization has multiple registered domains, you can double check the email address domain name suffix to ensure that it is correct.</span></span>
    
2. <span data-ttu-id="c41ae-170">正确输入了用户名后，选择 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-170">When you have the username correctly entered, select **Search**.</span></span>
    
3. <span data-ttu-id="c41ae-171">如果找不到用户帐户，页面上将显示错误消息 "未找到用户"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-171">If the user account is not found, the error message 'User not found' will be displayed on the page.</span></span> <span data-ttu-id="c41ae-172">检查用户的电子邮件地址信息，根据需要进行更正并选择 "**搜索**"，再试一次。</span><span class="sxs-lookup"><span data-stu-id="c41ae-172">Check the user's email address information, make corrections as necessary and select **Search** to try again.</span></span>
    
4. <span data-ttu-id="c41ae-173">如果找到了用户帐户，按钮文本会从“**搜索**”更改为“**清除**”，这表明返回的用户帐户是下方显示的附加功能的操作上下文，运行这些功能会应用于此用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-173">If user account is found, the text of the button changes from **Search** to **Clear**, which indicates that the returned user account is the operating context for the additional functions that will be displayed below, that running those functions will apply to this user account.</span></span>
    
5. <span data-ttu-id="c41ae-174">若要清除搜索结果并搜索其他用户，请选择 "**清除**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-174">To clear search results and search for a different user, select **Clear**.</span></span>
    
#### <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="c41ae-175">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="c41ae-175">Export a report of account data history</span></span>

<span data-ttu-id="c41ae-176">识别用户帐户后，可能要生成与此帐户链接的依赖项报告。</span><span class="sxs-lookup"><span data-stu-id="c41ae-176">Once the user account has been identified, you may wish to generate a report of dependencies that exist linked to this account.</span></span> <span data-ttu-id="c41ae-177">通过此信息，可以重新分配未完成的操作项目，或确保可访问之前上传的证据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-177">This information allows you to reassign open action items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="c41ae-178">若要生成并导出报告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-178">To generate and export a report:</span></span>
  
1. <span data-ttu-id="c41ae-179">选择 "**导出**" 以生成和下载当前分配给返回的用户帐户的合规性管理器控件操作项的报告以及该用户上载的文档列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-179">select **Export** to generate and download a report of the Compliance Manager control action items currently assigned to the returned user account and the list of documents uploaded by that user.</span></span> <span data-ttu-id="c41ae-180">如果没有分配的操作或上载的文档，则错误消息将显示 "此用户没有数据"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-180">If there are no assigned actions or uploaded documents, an error message displays "No data for this user."</span></span>

2. <span data-ttu-id="c41ae-181">报告在活动浏览器窗口的后台下载。</span><span class="sxs-lookup"><span data-stu-id="c41ae-181">The report downloads in the background of the active browser window.</span></span> <span data-ttu-id="c41ae-182">如果看不到 "下载" 弹出窗口，请查看浏览器下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="c41ae-182">If you don't see a download pop up, check your browser download history.</span></span>

3. <span data-ttu-id="c41ae-183">打开文档即可查看报告数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-183">Open the document to review the report data.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-184">This is not a historical report that retains and displays state changes to action item assignment history.</span><span class="sxs-lookup"><span data-stu-id="c41ae-184">This is not a historical report that retains and displays state changes to action item assignment history.</span></span> <span data-ttu-id="c41ae-185">The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report).</span><span class="sxs-lookup"><span data-stu-id="c41ae-185">The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="c41ae-186">For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user.</span><span class="sxs-lookup"><span data-stu-id="c41ae-186">For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user.</span></span>
  
#### <a name="reassign-action-items"></a><span data-ttu-id="c41ae-187">重新分配行动项</span><span class="sxs-lookup"><span data-stu-id="c41ae-187">Reassign action items</span></span>

<span data-ttu-id="c41ae-188">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below.</span><span class="sxs-lookup"><span data-stu-id="c41ae-188">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below.</span></span> <span data-ttu-id="c41ae-189">This action does not change document upload history for the returned user account.</span><span class="sxs-lookup"><span data-stu-id="c41ae-189">This action does not change document upload history for the returned user account.</span></span>
  
 <span data-ttu-id="c41ae-190">若要向其他用户重新分配行动项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-190">To reassign action items to another user:</span></span>
  
1. <span data-ttu-id="c41ae-191">单击输入框，浏览并选择组织内的另一名用户，向其分配已返回用户的行动项。</span><span class="sxs-lookup"><span data-stu-id="c41ae-191">Click the input box to browse for and select another user within the organization to whom the returned user's action items should be assigned.</span></span>
    
2. <span data-ttu-id="c41ae-192">选择“替换”\*\*\*\*，将所有控制措施行动项从已返回用户重新分配给新选择的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-192">Select **Replace** to reassign all control action items from the returned user to the newly selected user.</span></span>
    
3. <span data-ttu-id="c41ae-193">此时将显示确认对话框，"这将把所有控制措施项从当前用户重新分配给选定的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-193">A confirmation dialog box appears stating, "This will reassign all control action items from the current user to the selected user.</span></span> <span data-ttu-id="c41ae-194">此操作无法撤消。</span><span class="sxs-lookup"><span data-stu-id="c41ae-194">This action cannot be undone.</span></span> <span data-ttu-id="c41ae-195">你确定要继续吗?”</span><span class="sxs-lookup"><span data-stu-id="c41ae-195">Are you sure you want to continue?"</span></span>
    
4. <span data-ttu-id="c41ae-196">若要继续，请选择 **"确定"**，否则选择 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-196">To continue, select **OK**, otherwise select **Cancel**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c41ae-197">All action items (both active and completed) will be assigned to the newly selected user.</span><span class="sxs-lookup"><span data-stu-id="c41ae-197">All action items (both active and completed) will be assigned to the newly selected user.</span></span> <span data-ttu-id="c41ae-198">However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user.</span><span class="sxs-lookup"><span data-stu-id="c41ae-198">However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user.</span></span> 
  
<span data-ttu-id="c41ae-199">Changing the document upload history to remove the previously assigned user will have to be done as a manual process.</span><span class="sxs-lookup"><span data-stu-id="c41ae-199">Changing the document upload history to remove the previously assigned user will have to be done as a manual process.</span></span> <span data-ttu-id="c41ae-200">In that case, the administrator will need to:</span><span class="sxs-lookup"><span data-stu-id="c41ae-200">In that case, the administrator will need to:</span></span>
  
1. <span data-ttu-id="c41ae-201">打开以前下载的“导出”报告。</span><span class="sxs-lookup"><span data-stu-id="c41ae-201">Open the previously downloaded Export report.</span></span>
  
2. <span data-ttu-id="c41ae-202">标识并转到相应控制措施行动项。</span><span class="sxs-lookup"><span data-stu-id="c41ae-202">Identify and navigate to the desired control action item.</span></span>
  
3. <span data-ttu-id="c41ae-203">选择 "**管理文档**" 以导航到该控件的证据存储库。</span><span class="sxs-lookup"><span data-stu-id="c41ae-203">Select **Manage Documents** to navigate to the evidence repository for that control.</span></span>
  
4. <span data-ttu-id="c41ae-204">下载文档。</span><span class="sxs-lookup"><span data-stu-id="c41ae-204">Download the document.</span></span>
  
5. <span data-ttu-id="c41ae-205">从证据存储库中删除此文档。</span><span class="sxs-lookup"><span data-stu-id="c41ae-205">Delete the document in the evidence repository.</span></span>
  
6. <span data-ttu-id="c41ae-206">重新上载文档。</span><span class="sxs-lookup"><span data-stu-id="c41ae-206">Re-upload the document.</span></span> <span data-ttu-id="c41ae-207">该文档现在将具有新的上传日期、时间和 "上载者" 用户名。</span><span class="sxs-lookup"><span data-stu-id="c41ae-207">The document will now have a new upload date, time, and "Uploaded by" username.</span></span>
  
#### <a name="delete-user-data-history"></a><span data-ttu-id="c41ae-208">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="c41ae-208">Delete user data history</span></span>

<span data-ttu-id="c41ae-209">This sets control action items to 'unassigned' for all action items assigned to the returned user.</span><span class="sxs-lookup"><span data-stu-id="c41ae-209">This sets control action items to 'unassigned' for all action items assigned to the returned user.</span></span> <span data-ttu-id="c41ae-210">This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user</span><span class="sxs-lookup"><span data-stu-id="c41ae-210">This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user</span></span>
  
 <span data-ttu-id="c41ae-211">若要删除用户帐户行动项和文档上传历史记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-211">To delete the user account action item and document upload history:</span></span>
  
1. <span data-ttu-id="c41ae-212">选择“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c41ae-212">Select **Delete**.</span></span>

2. <span data-ttu-id="c41ae-213">确认对话框将显示： "这将删除所选用户的所有控制措施项分配和文档上载历史记录。</span><span class="sxs-lookup"><span data-stu-id="c41ae-213">A confirmation dialog displays: "This will remove all control action item assignments and the document upload history for the selected user.</span></span> <span data-ttu-id="c41ae-214">此操作无法撤消。</span><span class="sxs-lookup"><span data-stu-id="c41ae-214">This action cannot be undone.</span></span> <span data-ttu-id="c41ae-215">你确定要继续吗?”</span><span class="sxs-lookup"><span data-stu-id="c41ae-215">Are you sure you want to continue?"</span></span>
    
3. <span data-ttu-id="c41ae-216">若要继续，请选择 **"确定"**，否则选择 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-216">To continue, select **OK**, otherwise select **Cancel**.</span></span>

## <a name="groups"></a><span data-ttu-id="c41ae-217">组</span><span class="sxs-lookup"><span data-stu-id="c41ae-217">Groups</span></span>

<span data-ttu-id="c41ae-218">组是允许您组织评估的容器，并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。</span><span class="sxs-lookup"><span data-stu-id="c41ae-218">Groups are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span>

<span data-ttu-id="c41ae-219">您可以按符合您的方式对评估进行分组，如按年、标准、服务或组织的团队、部门或地理位置。</span><span class="sxs-lookup"><span data-stu-id="c41ae-219">You can group Assessments in a way that is logical to you, such as by year, standard, service, or based on your organization's teams, divisions, or geographies.</span></span> <span data-ttu-id="c41ae-220">以下是两个组及其基础评估的示例：</span><span class="sxs-lookup"><span data-stu-id="c41ae-220">Below are examples of two groups and their underlying Assessments:</span></span>
  
- <span data-ttu-id="c41ae-221">**FFIEC 是评估2020**</span><span class="sxs-lookup"><span data-stu-id="c41ae-221">**FFIEC IS Assessments 2020**</span></span>
  - <span data-ttu-id="c41ae-222">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="c41ae-222">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="c41ae-223">Intune + FFIEC 为</span><span class="sxs-lookup"><span data-stu-id="c41ae-223">Intune + FFIEC IS</span></span>
- <span data-ttu-id="c41ae-224">**“数据安全和隐私”评估**</span><span class="sxs-lookup"><span data-stu-id="c41ae-224">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="c41ae-225">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="c41ae-225">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="c41ae-226">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="c41ae-226">Office 365 + ISO 27018:2014</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-227">我们建议您在添加新评估*之前*为您的组织确定一个分组策略。</span><span class="sxs-lookup"><span data-stu-id="c41ae-227">We recommend determining a grouping strategy for your organization *before* adding new Assessments.</span></span>

<span data-ttu-id="c41ae-228">若要开始，请为您设置一个包含数据保护基准的**默认**组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-228">To get you started, a **Default** group is set up for you that contains the Data Protection Baseline.</span></span> <span data-ttu-id="c41ae-229">此基准是一组包含常见行业法规和标准（[了解详细信息](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-229">This baseline is a set of controls that includes common industry regulations and standards ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="c41ae-230">如何创建组</span><span class="sxs-lookup"><span data-stu-id="c41ae-230">How to create a group</span></span>

<span data-ttu-id="c41ae-231">不能将组创建为独立实体。</span><span class="sxs-lookup"><span data-stu-id="c41ae-231">Groups cannot be created as standalone entities.</span></span> <span data-ttu-id="c41ae-232">一个组必须始终包含至少一个评估，因此，若要创建一个组，必须首先创建一个评估以放置在该组中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-232">A group must always contain at least one Assessment, so in order to create a group, you must first create an Assessment to put in the group.</span></span>

<span data-ttu-id="c41ae-233">按照以下步骤创建组：</span><span class="sxs-lookup"><span data-stu-id="c41ae-233">Follow the steps below to create a group:</span></span>

1. <span data-ttu-id="c41ae-234">通过在仪表板顶部附近选择 " **+ 添加评估**" 来创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-234">Create a new Assessment by selecting **+ Add Assessment** near the top of your dashboard.</span></span>
2. <span data-ttu-id="c41ae-235">从 "**评估**" 弹出窗口中，输入评估的标题，然后从下拉菜单中选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-235">From the **Assessment** flyout pane, enter a title for your Assessment and select a template from the drop-down menu.</span></span>
3. <span data-ttu-id="c41ae-236">在 "**请选择一个组或添加新组**" 中，选择 "**添加新组**"，然后在下面的字段中输入您的组名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-236">At **Please select a group or add a new group**, select **Add a new group** and enter your group name in the field below.</span></span>
4. <span data-ttu-id="c41ae-237">若要从现有组中复制信息，请切换**是否要从现有组中复制数据？** 切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-237">To copy information from an existing group, toggle the **Would you like to copy the data from an existing group?** switch to **On.**</span></span> <span data-ttu-id="c41ae-238">从下面的下拉菜单中选择要复制的组，并选中要在新组中将其传输到新评估中的任何字段的复选框。</span><span class="sxs-lookup"><span data-stu-id="c41ae-238">Select the group you want to copy from the drop-down menu underneath, and select the checkboxes of any fields you want to carry over to the new Assessment in your new group.</span></span>
5. <span data-ttu-id="c41ae-239">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c41ae-239">Select **Save**.</span></span> <span data-ttu-id="c41ae-240">完成后，浮出控件窗格将关闭，您将在仪表板上看到您的新组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-240">When completed, the flyout pane closes and you'll see your new group on your dashboard.</span></span>

<span data-ttu-id="c41ae-241">使用组时需要了解的内容：</span><span class="sxs-lookup"><span data-stu-id="c41ae-241">What to know when working with groups:</span></span>
  
- <span data-ttu-id="c41ae-242">组名（也称为*组 id*）在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-242">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="c41ae-243">组没有任何安全属性。</span><span class="sxs-lookup"><span data-stu-id="c41ae-243">Groups do not have any security properties.</span></span> <span data-ttu-id="c41ae-244">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="c41ae-244">All permissions are associated with Assessments.</span></span>
- <span data-ttu-id="c41ae-245">将评估添加到组后，不能更改分组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-245">Once you add an Assessment to a group, the grouping cannot be changed.</span></span> <span data-ttu-id="c41ae-246">您可以重命名评估组，这将更改与该组关联的所有评估的评估分组的名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-246">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span>
- <span data-ttu-id="c41ae-247">在同一组中的不同评估中的相关评估控件在完成后将自动更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-247">Related Assessment controls in different Assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="c41ae-248">如果将新评估添加到现有组中，则会将该组中评估的常见信息复制到新评估中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-248">If you add a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="c41ae-249">组可以包含对同一认证或法规的评估，但每个组只能包含针对特定产品认证对的一个评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-249">Groups can contain Assessments for the same certification or regulation, but each group can only contain one Assessment for a specific product-certification pair.</span></span> <span data-ttu-id="c41ae-250">例如，组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-250">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="c41ae-251">仅当一个组与同一个产品的对应证书或法规不同时，该组才可以包含对同一产品的多个评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-251">A group can contain multiple Assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="c41ae-252">隐藏评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c41ae-252">Hiding an Assessment breaks the relationship between that Assessment and the group.</span></span> <span data-ttu-id="c41ae-253">其他相关评估的任何进一步更新不再在隐藏评估中反映出来。</span><span class="sxs-lookup"><span data-stu-id="c41ae-253">Any further updates to other related Assessments are no longer reflected in the hidden assessment.</span></span> <span data-ttu-id="c41ae-254">（[了解如何隐藏评估。](#hide-a-template-or-an-assessment)）</span><span class="sxs-lookup"><span data-stu-id="c41ae-254">([Learn how to hide Assessments.](#hide-a-template-or-an-assessment))</span></span>
- <span data-ttu-id="c41ae-255">无法删除组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-255">Groups cannot be deleted.</span></span>
- <span data-ttu-id="c41ae-256">对显示在多个组中的措施项进行更改时，该更改将反映在该措施项的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-256">When a change is made to an Action Item that appears in multiple Groups, that change is reflected in all instances of that Action Item.</span></span>

## <a name="tenant-management-of-dimensions-owners--customer-actions"></a><span data-ttu-id="c41ae-257">对维度、所有者、& 客户操作的租户管理</span><span class="sxs-lookup"><span data-stu-id="c41ae-257">Tenant management of dimensions, owners, & customer actions</span></span>

<span data-ttu-id="c41ae-258">**租户管理**界面使您能够管理以下组织范围的设置：</span><span class="sxs-lookup"><span data-stu-id="c41ae-258">The **Tenant Management** interface enables you to manage these organization-wide settings:</span></span>

- <span data-ttu-id="c41ae-259">**维：** 查看可用于为筛选器创建自定义透视的模板、评估和操作项的元数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-259">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="c41ae-260">**所有者：** 填充可与操作关联的责任方列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-260">**Owners:** Populate a list of responsible parties that can be associated with actions.</span></span>
- <span data-ttu-id="c41ae-261">**客户操作：** 管理合规性管理器（预览版）中包含的操作项的完整列表，并为与安全得分集成的操作启用/禁用安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="c41ae-261">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="c41ae-262">从屏幕右上角选择 "**租户管理**" 以打开管理界面，并使用以下步骤来管理**维度**、**所有者**和**客户操作**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-262">Select **Tenant Management** from the upper-right corner of your screen to open the management interface, and use the steps below to manage  **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="c41ae-263">Dimensions</span><span class="sxs-lookup"><span data-stu-id="c41ae-263">Dimensions</span></span>

<span data-ttu-id="c41ae-264">维度是提供有关模板、评估或措施项的信息的元数据的集合。</span><span class="sxs-lookup"><span data-stu-id="c41ae-264">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="c41ae-265">维度使用键和值的概念，其中维度键表示属性，维度值表示属性的有效值。</span><span class="sxs-lookup"><span data-stu-id="c41ae-265">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="c41ae-266">例如，在合规性管理器中有三种类型的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-266">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="c41ae-267">它们由**操作目的**的维度键和**预防**、**侦探**和**纠正**的维度值定义。</span><span class="sxs-lookup"><span data-stu-id="c41ae-267">They are defined by a Dimension Key of **Action Purpose** and Dimension Values of **Preventative**, **Detective**, and **Corrective**.</span></span>

### <a name="owners"></a><span data-ttu-id="c41ae-268">Owners</span><span class="sxs-lookup"><span data-stu-id="c41ae-268">Owners</span></span>

<span data-ttu-id="c41ae-269">所有者用于标识负责每个控件的人员。</span><span class="sxs-lookup"><span data-stu-id="c41ae-269">Owners are used to identify the person responsible for each control.</span></span> <span data-ttu-id="c41ae-270">所有内置控件由 Microsoft、客户或这两者拥有。</span><span class="sxs-lookup"><span data-stu-id="c41ae-270">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="c41ae-271">您可以创建可用于在组织中指定更精确的职责的所有者的自定义值。</span><span class="sxs-lookup"><span data-stu-id="c41ae-271">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="c41ae-272">例如，可以创建代表组织中的特定组、团队或业务单位的所有者。</span><span class="sxs-lookup"><span data-stu-id="c41ae-272">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="c41ae-273">添加所有者</span><span class="sxs-lookup"><span data-stu-id="c41ae-273">Add an Owner</span></span>

1. <span data-ttu-id="c41ae-274">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-274">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="c41ae-275">选择 " **+ 添加所有者**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-275">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="c41ae-276">提供所有者的名称和说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-276">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="c41ae-277">说明显示在 "所有者" 列中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-277">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="c41ae-278">编辑所有者</span><span class="sxs-lookup"><span data-stu-id="c41ae-278">Edit an Owner</span></span>

<span data-ttu-id="c41ae-279">您不能编辑所有者名称，但可以修改 "Owner" 列中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="c41ae-279">You can't edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="c41ae-280">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-280">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="c41ae-281">找到要编辑的所有者，选择其旁边的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-281">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="c41ae-282">根据需要修改说明，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-282">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="c41ae-283">删除所有者</span><span class="sxs-lookup"><span data-stu-id="c41ae-283">Delete an Owner</span></span>

1. <span data-ttu-id="c41ae-284">打开 "**租户管理**" 并选择 "**所有者**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-284">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="c41ae-285">找到要删除的所有者，选择其旁边的省略号（...），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-285">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="c41ae-286">当出现确认消息时，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-286">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="c41ae-287">客户操作</span><span class="sxs-lookup"><span data-stu-id="c41ae-287">Customer Actions</span></span>

<span data-ttu-id="c41ae-288">"客户操作" 区域显示合规性管理器中所有模板和评估的所有客户操作（预览）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-288">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

<span data-ttu-id="c41ae-289">![合规性管理器-添加用户](../media/compliance-manager-customer-actions.png "合规性管理器客户操作")</span><span class="sxs-lookup"><span data-stu-id="c41ae-289">![Compliance Manager — add users](../media/compliance-manager-customer-actions.png "Compliance Manager Customer Actions")</span></span>

<span data-ttu-id="c41ae-290">您可以一目了然地看到操作的标题、所有者、类别、强制和分数，并确定它是否与安全得分集成。</span><span class="sxs-lookup"><span data-stu-id="c41ae-290">At a glance, you can see an Action's title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="c41ae-291">您可以展开操作并选择 "**读取更多**"，以读取操作说明并访问说明中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-291">You can expand an Action and select **Read More** to read the Action's description and access any links in the description.</span></span> <span data-ttu-id="c41ae-292">您还可以使用此接口基于每个操作启用和禁用安全得分集成，并添加自定义操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-292">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="c41ae-293">具有安全得分集成功能的操作旁边有一个省略号（...）（请注意，自定义操作旁边还有一个省略号）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-293">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="c41ae-294">启用或禁用安全分数集成</span><span class="sxs-lookup"><span data-stu-id="c41ae-294">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="c41ae-295">选择要修改的操作的省略号（...），然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-295">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="c41ae-296">切换交换机以确保安全分数连续更新为 "开" 或 "关"，以通过安全分数启用或禁用连续监控。</span><span class="sxs-lookup"><span data-stu-id="c41ae-296">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="c41ae-297">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c41ae-297">Select **Save**.</span></span>

<span data-ttu-id="c41ae-298">当组织首次部署 Microsoft 365 或 Office 365 时，将需要大约7天的时间来完全收集数据，并将其划分到你的成绩中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-298">When organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="c41ae-299">在这段时间内，将安全分数连续更新开关设置为**Off**并手动设置要**实现**的操作，则会将该操作计为成绩。</span><span class="sxs-lookup"><span data-stu-id="c41ae-299">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="c41ae-300">在最初的七天之后，将安全分数连续更新打开将启用从该点继续进行监视。</span><span class="sxs-lookup"><span data-stu-id="c41ae-300">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>

<span data-ttu-id="c41ae-301">安全分数集成不支持的任何操作都可以手动实现。</span><span class="sxs-lookup"><span data-stu-id="c41ae-301">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="c41ae-302">手动实现将考虑该操作的组的分数。</span><span class="sxs-lookup"><span data-stu-id="c41ae-302">A manual implementation will factor into the score for that action's group.</span></span>

## <a name="assessments"></a><span data-ttu-id="c41ae-303">评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-303">Assessments</span></span>

<span data-ttu-id="c41ae-304">本节介绍如何查看和使用评估，包括如何添加新的评估、导出、复制现有评估中的信息，以及如何通过版本控制对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-304">This section explains how to view and work with your Assessments, including how to add new ones, export them, copy information from existing Assessments, and keep them updated through versioning.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-305">你现在可以在合规性分数中创建评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-305">You can now create assessments in Compliance Score.</span></span> <span data-ttu-id="c41ae-306">[查看指南和说明](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="c41ae-306">[View guidance and instructions](compliance-score-assessments.md).</span></span>

### <a name="view-an-assessment-and-action-details"></a><span data-ttu-id="c41ae-307">查看评估和操作详细信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-307">View an Assessment and Action details</span></span>
  
<span data-ttu-id="c41ae-308">在 "**评估**" 仪表板中，选择要打开的评估名称，并查看 "操作项" 和 "控件信息"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-308">In the **Assessments** dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="c41ae-309">下面的示例展示了 Office 365 和 ISO 27001 的评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-309">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="c41ae-310">第一个视图演示合规性管理器（预览版）中的新操作项视图。</span><span class="sxs-lookup"><span data-stu-id="c41ae-310">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![合规性管理器操作项目视图](../media/compliance-manager-action-items.png)

<span data-ttu-id="c41ae-312">操作按字母顺序列出，并为每个操作分配一个分数和一个所有者。</span><span class="sxs-lookup"><span data-stu-id="c41ae-312">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="c41ae-313">选择 "**阅读更多**" 链接以阅读每个操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c41ae-313">Select  the **Read More** link to read the details of each Action.</span></span>

![合规性管理器操作项目视图](../media/compliance-manager-actions-read-more.png)

<span data-ttu-id="c41ae-315">选择 "**查看**" 链接以管理、分配、实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-315">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="c41ae-316">下面是一个操作示例。</span><span class="sxs-lookup"><span data-stu-id="c41ae-316">Below is an example Action.</span></span>

![合规性管理器操作视图](../media/compliance-manager-action.png)

<span data-ttu-id="c41ae-318">使用以下字段来管理操作工作流：</span><span class="sxs-lookup"><span data-stu-id="c41ae-318">Use the following fields to manage the Action workflow:</span></span>

- <span data-ttu-id="c41ae-319">**为用户分配：** 选择此字段以选择或输入应为其分配此操作的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-319">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="c41ae-320">您可以在列表中滚动，或键入名称以查找它，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="c41ae-320">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="c41ae-321">**管理文档：** 您可以在 Office 文档、图像文件和屏幕截图、CSV 或 TXT 中的 PowerShell 输出以及 Pdf 中上载实现证据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-321">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="c41ae-322">**实现状态：** 用于指示操作的当前实现状态。</span><span class="sxs-lookup"><span data-stu-id="c41ae-322">**Implementation Status:** Used to indicate the Action's current implementation status.</span></span> <span data-ttu-id="c41ae-323">可能的值尚未实现、实现、替代实施、规划且不在范围内。</span><span class="sxs-lookup"><span data-stu-id="c41ae-323">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="c41ae-324">**实施日期：** 执行操作的日期。</span><span class="sxs-lookup"><span data-stu-id="c41ae-324">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="c41ae-325">**测试结果：** 用于指示实现验证的结果。</span><span class="sxs-lookup"><span data-stu-id="c41ae-325">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="c41ae-326">可能的值未评估、传递、失败-低风险、失败-中等风险、失败-高风险以及不在范围内。</span><span class="sxs-lookup"><span data-stu-id="c41ae-326">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="c41ae-327">**测试日期：** 验证发生的日期。</span><span class="sxs-lookup"><span data-stu-id="c41ae-327">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="c41ae-328">**实现说明：** 输入您的组织的实现详细信息，以及您想要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="c41ae-328">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="c41ae-329">**测试计划：** 输入此操作的测试计划详细信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="c41ae-329">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="c41ae-330">**其他信息：** 输入有关此操作或在组织中实现此操作的方式的任何其他信息，以及要包括的任何注释。</span><span class="sxs-lookup"><span data-stu-id="c41ae-330">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="c41ae-331">在 "**控件信息**" 仪表板上，您可以在评估和模板级别查看控件的信息。</span><span class="sxs-lookup"><span data-stu-id="c41ae-331">On the **Controls Info** dashboard, you can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="c41ae-332">下面是用于评估的控件信息仪表板的一个示例。</span><span class="sxs-lookup"><span data-stu-id="c41ae-332">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![合规性管理器控制信息视图](../media/compliance-manager-controls-info.png)

<span data-ttu-id="c41ae-334">对于评估，"控制信息" 仪表板将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="c41ae-334">For Assessments, the Controls Info dashboard displays the following information:</span></span>

- <span data-ttu-id="c41ae-335">一个**组**下拉列表，用于选择要查看的组（使用多个组时）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-335">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="c41ae-336">一个**评估**下拉列表，用于选择要查看的评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-336">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="c41ae-337">有关所选评估的元数据，包括：</span><span class="sxs-lookup"><span data-stu-id="c41ae-337">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="c41ae-338">**评估的控制措施**的进度指示器，其中显示了已评估的控制总数的控制次数。</span><span class="sxs-lookup"><span data-stu-id="c41ae-338">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="c41ae-339">评估的当前**合规性分数**，显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="c41ae-339">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="c41ae-340">有关评估中使用的**认证**和**产品**的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c41ae-340">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="c41ae-341">评估的当前**状态**和上次**修改**日期。</span><span class="sxs-lookup"><span data-stu-id="c41ae-341">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="c41ae-342">用于评估的**范围内的服务**的列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-342">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="c41ae-343">控件的详细信息，按控件系列分组，并提供指向客户操作和 Microsoft 实现详细信息的链接：</span><span class="sxs-lookup"><span data-stu-id="c41ae-343">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="c41ae-344">**您的操作**将显示您可以执行以满足部分或全部控件要求的客户操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-344">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control's requirements.</span></span> <span data-ttu-id="c41ae-345">许多控件具有与之关联的多个操作，并且与控件关联的所有操作都显示在此处。</span><span class="sxs-lookup"><span data-stu-id="c41ae-345">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="c41ae-346">此处的操作与操作仪表板中列出的 UI 相同。</span><span class="sxs-lookup"><span data-stu-id="c41ae-346">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="c41ae-347">**Microsoft 操作**显示 microsoft 内部框架中应用于所选证书控制的控件列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-347">**Microsoft Actions** displays the list of controls from Microsoft's internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="c41ae-348">对于每个内部控件，选择 "已**实施**" 以查看 Microsoft 的实施和测试详细信息，以及测试结果和测试日期，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c41ae-348">For each internal control, select **Implemented** to see Microsoft's implementation and test details, along with the test result and test date, as shown below.</span></span>

![合规性管理器 Microsoft 操作视图](../media/compliance-manager-microsoft-action.png)

### <a name="add-an-assessment"></a><span data-ttu-id="c41ae-350">添加评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-350">Add an Assessment</span></span>
  
1. <span data-ttu-id="c41ae-351">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-351">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="c41ae-352">当边栏打开时，请输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="c41ae-352">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="c41ae-353">**标题（必需）：** 输入评估的标题</span><span class="sxs-lookup"><span data-stu-id="c41ae-353">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="c41ae-354">**请选择一个模板（必需）：** 选择标准或自定义模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-354">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="c41ae-355">**请选择组或添加新组（必需）：** 选择现有组或选择添加新组，并提供唯一的组名称</span><span class="sxs-lookup"><span data-stu-id="c41ae-355">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="c41ae-356">**是否要复制现有组中的数据？（可选）：** 切换控件以启用组副本，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-356">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="c41ae-357">**选择一个组（可选）：** 如果已启用组副本，请选择要复制的组</span><span class="sxs-lookup"><span data-stu-id="c41ae-357">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="c41ae-358">**实现详细信息（可选）：** 选择以将实现详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="c41ae-358">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="c41ae-359">**测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组</span><span class="sxs-lookup"><span data-stu-id="c41ae-359">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="c41ae-360">**文档（可选）：** 选择以将文档复制到新组</span><span class="sxs-lookup"><span data-stu-id="c41ae-360">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="c41ae-361">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-361">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="c41ae-362">新评估显示在评估仪表板上，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="c41ae-362">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="c41ae-363">评估的标题。</span><span class="sxs-lookup"><span data-stu-id="c41ae-363">The title of the Assessment.</span></span>
- <span data-ttu-id="c41ae-364">评估的维度，包括认证、环境和应用于评估的产品。</span><span class="sxs-lookup"><span data-stu-id="c41ae-364">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="c41ae-365">创建日期的日期和上次修改日期的日期。</span><span class="sxs-lookup"><span data-stu-id="c41ae-365">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="c41ae-366">评估分数显示为百分比。</span><span class="sxs-lookup"><span data-stu-id="c41ae-366">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="c41ae-367">此分数自动包含来自 Microsoft 托管控件和安全得分的分数。</span><span class="sxs-lookup"><span data-stu-id="c41ae-367">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="c41ae-368">进度指示器，显示已评估的 Microsoft 托管控件和客户托管的控件的数量。</span><span class="sxs-lookup"><span data-stu-id="c41ae-368">Progress indicators that show the number of assessed Microsoft-managed and customer-managed controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="c41ae-369">从现有评估复制信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-369">Copying information from existing Assessments</span></span>

<span data-ttu-id="c41ae-370">创建评估时，可以选择从现有组复制信息。</span><span class="sxs-lookup"><span data-stu-id="c41ae-370">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="c41ae-371">通过复制，您可以将输入到复制的评估中的信息应用于新评估中的相同控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-371">Copying allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="c41ae-372">例如，如果您的组织中有与 FFIEC 相关的所有评估的组，则可以从现有评估中复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="c41ae-372">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="c41ae-373">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-373">Implementation Details</span></span>
- <span data-ttu-id="c41ae-374">测试计划 & 其他信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-374">Test Plan & Additional Information</span></span>
- <span data-ttu-id="c41ae-375">文档</span><span class="sxs-lookup"><span data-stu-id="c41ae-375">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="c41ae-376">将信息从现有评估复制到新评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-376">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="c41ae-377">在 "评估" 仪表板中，选择 " **+ 添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-377">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="c41ae-378">在 "**添加评估**" 窗口中，填写以下信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-378">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="c41ae-379">**标题（必需）：** 输入评估的标题。</span><span class="sxs-lookup"><span data-stu-id="c41ae-379">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="c41ae-380">**请选择一个模板（必需）：** 选择标准或自定义模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-380">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="c41ae-381">**请选择组或添加新组（必需）：** 选择 "**添加新组**" 并提供一个唯一的组名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-381">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="c41ae-382">**是否要复制现有组中的数据？（可选）：** 将控件切换到 "打开" 以启用组副本，然后：-**选择一个组（可选）：** 如果已启用组副本，请从组中选择要复制的组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-382">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="c41ae-383">- **实现详细信息（可选）：** 选择将实现详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-383">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="c41ae-384">- **测试计划 & 其他信息（可选）：** 选择以将测试计划和其他信息详细信息复制到新组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-384">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="c41ae-385">- **文档（可选）：** 选择以将文档复制到新组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-385">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="c41ae-386">选择 "**保存**" 以创建评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-386">Select **Save** to create the Assessment.</span></span>

### <a name="versioning-alerts-for-assessment-updates"></a><span data-ttu-id="c41ae-387">评估更新的版本控制警报</span><span class="sxs-lookup"><span data-stu-id="c41ae-387">Versioning alerts for Assessment updates</span></span>

<span data-ttu-id="c41ae-388">如果有可供评估的更新，则会出现一个警报图标，通知您更新已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="c41ae-388">When an update is available for an Assessment, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="c41ae-389">当您单击该图标时，将弹出一个窗口，说明更新并提示您接受。</span><span class="sxs-lookup"><span data-stu-id="c41ae-389">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="c41ae-390">下面是针对评估的版本控制警报的一个示例：</span><span class="sxs-lookup"><span data-stu-id="c41ae-390">Below is an example of the versioning alert for an Assessment:</span></span>

<span data-ttu-id="c41ae-391">![合规性分数-版本控制警报](../media/compliance-score-assessment-version.png "评估版本更新警报")</span><span class="sxs-lookup"><span data-stu-id="c41ae-391">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="c41ae-392">选择警报图标可显示一个弹出窗格，其中介绍了更新并提示您接受：</span><span class="sxs-lookup"><span data-stu-id="c41ae-392">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="c41ae-393">![合规性分数-版本化飞出](../media/compliance-score-assessment-version-accept.png "评估更新确认窗格")</span><span class="sxs-lookup"><span data-stu-id="c41ae-393">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

<span data-ttu-id="c41ae-394">强烈建议您在收到更新通知时接受所有更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-394">We strongly recommend accepting all updates when you receive update notifications.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="c41ae-395">导出评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-395">Export an Assessment</span></span>

<span data-ttu-id="c41ae-396">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-396">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="c41ae-397">报告是在创建报告的日期和时间的评估的快照。</span><span class="sxs-lookup"><span data-stu-id="c41ae-397">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="c41ae-398">该报告包含有关评估、控制实施状态、控制测试日期、测试结果的所有 Microsoft 和客户托管控件的详细信息，并提供了指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-398">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="c41ae-399">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="c41ae-399">Export an Assessment report</span></span>
  
1. <span data-ttu-id="c41ae-400">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c41ae-400">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="c41ae-401">在要导出的评估的下拉菜单中，选择 "**组**和**评估**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-401">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="c41ae-402">选择 "**导出**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c41ae-402">Select the **Export** button.</span></span>

<span data-ttu-id="c41ae-403">在浏览器会话中，会将评估报告作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="c41ae-403">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="c41ae-404">Excel 文件的文件名称默认为评估的标题。</span><span class="sxs-lookup"><span data-stu-id="c41ae-404">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="c41ae-405">隐藏模板或评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-405">Hide a Template or an Assessment</span></span>

<span data-ttu-id="c41ae-406">当您完成模板或评估且不再出于合规性目的而需要时，您可以将其从视图中隐藏。</span><span class="sxs-lookup"><span data-stu-id="c41ae-406">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="c41ae-407">如果模板或评估处于隐藏状态，则会将其从默认视图中删除，并且必须选中 "**包含隐藏**的" 复选框以显示它。</span><span class="sxs-lookup"><span data-stu-id="c41ae-407">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="c41ae-408">![合规性管理器隐藏的模板视图](../media/compliance-manager-hidden-template.png "合规性管理器隐藏模板")</span><span class="sxs-lookup"><span data-stu-id="c41ae-408">![Compliance Manager Hidden Template View](../media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c41ae-409">隐藏的评估不会保留其到已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-409">Hidden Assessments don't retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="c41ae-410">强烈建议您先导出评估，然后再将其隐藏，以保留指向报告中的证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-410">We highly recommended that you export an Assessment before hiding it to retain links to evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="c41ae-411">隐藏模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-411">Hiding a Template</span></span>

1. <span data-ttu-id="c41ae-412">打开 "**模板**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-412">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="c41ae-413">找到要隐藏的模板，并在其所在行的省略号处，选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-413">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="c41ae-414">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-414">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="c41ae-415">隐藏评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-415">Hide an Assessment</span></span>

1. <span data-ttu-id="c41ae-416">打开 "**评估**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-416">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="c41ae-417">从下拉列表中选择包含您要隐藏的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-417">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="c41ae-418">找到要隐藏的评估，然后在省略号上选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-418">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="c41ae-419">当您看到确认消息时，请选择 "**隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-419">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="c41ae-420">查看隐藏评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-420">View hidden Assessments</span></span>
  
1. <span data-ttu-id="c41ae-421">打开 "**评估**仪表板" 选项卡，然后选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c41ae-421">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="c41ae-422">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-422">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="c41ae-423">取消隐藏评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-423">Unhide an Assessment</span></span>

1. <span data-ttu-id="c41ae-424">在 "**评估**" 选项卡上，选中 "**包含隐藏**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c41ae-424">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="c41ae-425">隐藏评估显示在**隐藏评估**部分中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-425">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="c41ae-426">找到要取消隐藏的评估，然后在省略号上选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-426">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="c41ae-427">当您看到确认消息时，请选择 "**取消隐藏**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-427">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="c41ae-428">控件和操作</span><span class="sxs-lookup"><span data-stu-id="c41ae-428">Controls and Actions</span></span>

<span data-ttu-id="c41ae-429">控件和操作是合规性管理器（预览版）中使用的主要数据透视。</span><span class="sxs-lookup"><span data-stu-id="c41ae-429">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="c41ae-430">在早期版本的合规性管理器中存在的控制轴已得到增强，可在相同的控制系列中显示 Microsoft 和 customer 控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-430">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="c41ae-431">此 "合并" 视图使以每个控件为基础查看完整的共享职责模型变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="c41ae-431">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="c41ae-432">操作透视是合规性管理器（预览版）中的新操作，旨在提供 Microsoft 建议的所有操作的简化视图。</span><span class="sxs-lookup"><span data-stu-id="c41ae-432">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="c41ae-433">控件</span><span class="sxs-lookup"><span data-stu-id="c41ae-433">Controls</span></span>

<span data-ttu-id="c41ae-434">可以从 "控件信息" 仪表板查看控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-434">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="c41ae-435">控件表示标准、认证、法规或框架中的要求。</span><span class="sxs-lookup"><span data-stu-id="c41ae-435">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="c41ae-436">若要跨多个标准、法规等满足这些要求，并将它们与操作相关联，则所有内容都被视为控制框架。</span><span class="sxs-lookup"><span data-stu-id="c41ae-436">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="c41ae-437">例如，像控制框架一样，法规（如 HIPAA）已按节细分，合规性管理器中的 HIPAA 控件使用与这些节相同的编号方案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c41ae-437">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![合规性管理器 Microsoft 控件详细信息](../media/compliance-manager-control-details.png)

<span data-ttu-id="c41ae-439">有三种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="c41ae-439">There are three types of controls:</span></span>

1. <span data-ttu-id="c41ae-440">**Microsoft 托管控件：** 这些控件只是 microsoft 有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-440">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="c41ae-441">它们显示在 "现成" 模板中，并已添加到 Microsoft 的合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-441">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="c41ae-442">**客户管理的控件：** 这些控件只是客户有责任的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-442">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="c41ae-443">它们显示在 "现成" 模板中，并由客户添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-443">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="c41ae-444">**共享管理控件：** 这些控件是在 Microsoft 和客户之间共享责任的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-444">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="c41ae-445">这些模板显示在 "现成" 模板中，由 Microsoft 添加到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-445">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="c41ae-446">客户还可以编辑或禁用 Microsoft 托管的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-446">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="c41ae-447">Actions 项</span><span class="sxs-lookup"><span data-stu-id="c41ae-447">Actions Items</span></span>

<span data-ttu-id="c41ae-448">操作项目是实施标准或法规要求的建议任务，或者用于测试、验证和记录组织的实现要求的任务。</span><span class="sxs-lookup"><span data-stu-id="c41ae-448">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="c41ae-449">操作与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="c41ae-449">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="c41ae-450">每个控件都有一个或多个与之关联的操作，并且每个操作都可以与一个或多个控件相关联。</span><span class="sxs-lookup"><span data-stu-id="c41ae-450">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="c41ae-451">操作是合规性管理器（预览版）中核心工作流的一部分，因为它们是由组织分配、跟踪和验证的对象。</span><span class="sxs-lookup"><span data-stu-id="c41ae-451">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="c41ae-452">分配操作项</span><span class="sxs-lookup"><span data-stu-id="c41ae-452">Assign Action Items</span></span>
  
1. <span data-ttu-id="c41ae-453">在 "**操作项**" 仪表板上，选择包含要分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-453">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="c41ae-454">在 "**评估**" 下拉列表中，选择要为其分配操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-454">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="c41ae-455">找到要分配的操作，并在 "**所有者**" 列中选择要**查看**的链接、\* \* 已实现或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-455">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, \*\*Implemented, or **Test**.</span></span>
4. <span data-ttu-id="c41ae-456">选择 "**分配用户**" 字段，将显示组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-456">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="c41ae-457">滚动列表并选择 "用户" 或 "筛选列表" 以通过键入用户的名称来选择用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-457">Scroll the list and select user or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="c41ae-458">在 "实施说明" 字段中，输入您希望向分配的用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="c41ae-458">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="c41ae-459">选择 "**保存**" 以分配操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-459">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="c41ae-460">重新分配操作项</span><span class="sxs-lookup"><span data-stu-id="c41ae-460">Reassign Action Items</span></span>

<span data-ttu-id="c41ae-461">通过此函数，组织可以通过将操作重新分配给新用户，删除对用户帐户的任何活动的或未完成的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c41ae-461">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="c41ae-462">在 "**操作项**" 仪表板上，选择包含要重新分配其操作的评估的**组**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-462">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="c41ae-463">在 "**评估**" 下拉列表中，选择要重新分配其操作的评估，或从下拉列表中选择 "**全部**" 以查看所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-463">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="c41ae-464">找到要重新分配的操作，并在 "**所有者**" 列中选择要**查看**、**实现**或**测试**的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-464">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="c41ae-465">从 "**分配用户**" 字段中删除现有用户，然后从用户列表中选择其他用户，或通过键入用户名称来筛选列表以选择用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-465">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user's name.</span></span>
5. <span data-ttu-id="c41ae-466">在 "实施说明" 字段中，输入您希望向用户传达的任何注释。</span><span class="sxs-lookup"><span data-stu-id="c41ae-466">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="c41ae-467">选择 "**保存**" 以重新分配该操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-467">Select **Save** to reassign the Action.</span></span>

#### <a name="common-action-items-synch-status-across-groups"></a><span data-ttu-id="c41ae-468">跨组的常见操作项同步状态</span><span class="sxs-lookup"><span data-stu-id="c41ae-468">Common Action Items synch status across Groups</span></span>

<span data-ttu-id="c41ae-469">如果您的组织具有多个评估组，则会有技术操作的行为（即，影响整个组织的操作）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-469">If your organization has multiple groups of assessments, there is a behavior of Technical actions (that is, actions affecting your entire organization).</span></span> <span data-ttu-id="c41ae-470">所有组中的重复操作现在组合到一个单一操作中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-470">Any duplicate actions across groups are now combined into one single action.</span></span> <span data-ttu-id="c41ae-471">该单个操作包含所有上载的笔记和来自以前的重复版本的证据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-471">That single action contains all uploaded notes and evidence from previously duplicate versions.</span></span> <span data-ttu-id="c41ae-472">在一个组或评估中对操作所做的任何更改都将反映在该操作的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-472">Any change made to the action in one group or assessment will be reflected in all instances of that action.</span></span> <span data-ttu-id="c41ae-473">"实现**状态**"、"**实施日期**"、"**测试状态**" 和 "**测试日期**" 字段反映了最新的更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-473">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** fields reflect the most recent updates.</span></span>

## <a name="templates"></a><span data-ttu-id="c41ae-474">模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-474">Templates</span></span>

<span data-ttu-id="c41ae-475">模板是合规性管理器（预览）中与产品和证书（例如，标准、法规、控制框架等）相关联的基本对象。</span><span class="sxs-lookup"><span data-stu-id="c41ae-475">A Template is the base object in Compliance Manager (Preview) that is associated with a product and a certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="c41ae-476">可以从 "**模板**" 仪表板中查看和添加模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-476">Templates can be viewed and added from the **Templates** dashboard.</span></span>

![合规性管理器 Microsoft 模板仪表板](../media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="c41ae-478">仪表板将显示每个模板，以及与模板关联的证书和产品、创建模板的日期和上次修改的日期、客户和 Microsoft 托管控件的数量、模板的最大合规性分数以及模板的状态（例如，已批准、待定审批、导入）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-478">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

### <a name="create-a-template"></a><span data-ttu-id="c41ae-479">创建模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-479">Create a Template</span></span>

<span data-ttu-id="c41ae-480">有三种方法可以使用模板来创建评估：</span><span class="sxs-lookup"><span data-stu-id="c41ae-480">There are three ways to work with Templates to create Assessments:</span></span>

1. <span data-ttu-id="c41ae-481">使用 Microsoft 提供的模板准备使用的模板之一。</span><span class="sxs-lookup"><span data-stu-id="c41ae-481">Use one of the ready to use Templates provided by Microsoft.</span></span>
2. <span data-ttu-id="c41ae-482">通过扩展过程自定义准备好使用模板和您自己的操作和控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-482">Customize a ready to use Template with your own actions and controls through the extension process.</span></span>
3. <span data-ttu-id="c41ae-483">创建您自己的模板并将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-483">Create your own Template and import it into Compliance Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-484">将模板上传到合规性管理器中时，必须由保留管理员角色的两个用户批准，才能发布并可供使用。</span><span class="sxs-lookup"><span data-stu-id="c41ae-484">When you upload a template into Compliance Manager, it must be approved by two users who hold an admin role before it is published and available for use.</span></span>

#### <a name="use-a-ready-to-use-template"></a><span data-ttu-id="c41ae-485">使用已准备好使用模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-485">Use a ready to use Template</span></span>

<span data-ttu-id="c41ae-486">可以在**模板**仪表板上使用模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-486">Ready to use templates are available on your **Templates** dashboard.</span></span> <span data-ttu-id="c41ae-487">查看当前[模板列表](compliance-score-templates.md)，该列表会在每次有新模板时更新。</span><span class="sxs-lookup"><span data-stu-id="c41ae-487">View the current [list of templates](compliance-score-templates.md), which is updated each time a new template is available.</span></span>

#### <a name="customize-a-template-through-the-extension-process"></a><span data-ttu-id="c41ae-488">通过扩展过程自定义模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-488">Customize a Template through the extension process</span></span>

1. <span data-ttu-id="c41ae-489">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-489">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="c41ae-490">在 "模板" 浮出控件窗格中，选中 "**从全局模板创建扩展**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c41ae-490">On the Template flyout pane, select the **Create extension from global template** checkbox.</span></span>
3. <span data-ttu-id="c41ae-491">从下拉式菜单中选择要扩展的模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-491">Select the template you want to extend from the drop-down menu.</span></span>
4. <span data-ttu-id="c41ae-492">如果尚未在 Excel 中设置模板数据的格式，请选择浮出控件窗格中的链接以下载 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-492">If you have not already formatted your template data in Excel, select the link in the flyout pane to download an Excel file.</span></span> <span data-ttu-id="c41ae-493">根据 "[导入模板数据](#import-template-data-with-excel)" 和下面的 Excel 说明填写电子表格，并将其保存到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="c41ae-493">Fill out the spreadsheet according to the [Import Template data with Excel](#import-template-data-with-excel) instructions below and save it to your local drive.</span></span>
5. <span data-ttu-id="c41ae-494">通过选择 "**浏览**" 来上载您的 Excel 文件，以导入自定义模板数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-494">Import your customized template data by selecting **Browse** to upload your Excel file.</span></span>
6. <span data-ttu-id="c41ae-495">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-495">Select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="c41ae-496">对模板所做的更改需要批准拥有管理员角色的两个用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-496">The changes to the template require approval of two users who hold an admin role.</span></span> <span data-ttu-id="c41ae-497">这些用户会收到模板更新的通知。</span><span class="sxs-lookup"><span data-stu-id="c41ae-497">Those users receive a notification of the template updates.</span></span> <span data-ttu-id="c41ae-498">其中一个更改由两个管理员批准，您将在**模板**仪表板上看到更新后的模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-498">One the changes are approved by two admins, you'll see your updated template on your **Templates** dashboard.</span></span>

#### <a name="create-your-own-template-and-import-it-into-compliance-manager"></a><span data-ttu-id="c41ae-499">创建您自己的模板并将其导入到合规性管理器</span><span class="sxs-lookup"><span data-stu-id="c41ae-499">Create your own Template and import it into Compliance Manager</span></span>

1. <span data-ttu-id="c41ae-500">打开 "**模板**" 仪表板，然后选择 " **+ 添加模板**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-500">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="c41ae-501">在 "模板" 浮出控件窗格中，选择 "**创建新模板**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-501">On the Template flyout pane, select **Create a new template**.</span></span>
3. <span data-ttu-id="c41ae-502">通过选择 "**浏览**" 以上传包含数据的 Excel 文件（请参阅以下[Excel 中的导入模板数据](#import-template-data-with-excel)）导入模板数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-502">Import your template data by selecting **Browse** to upload your Excel file containing the data (see [Import Template data with Excel](#import-template-data-with-excel) below).</span></span>
4. <span data-ttu-id="c41ae-503">选择 "**添加到仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-503">Select **Add to Dashboard**.</span></span>
5. <span data-ttu-id="c41ae-504">新模板需要审批两个拥有管理员角色的用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-504">The new template requires approval of two users who hold an admin role.</span></span> <span data-ttu-id="c41ae-505">这些用户会收到通知，指出新模板已准备好进行审批。</span><span class="sxs-lookup"><span data-stu-id="c41ae-505">Those users receive a notification that a new template is ready for approval.</span></span> <span data-ttu-id="c41ae-506">一个模板由两个管理员批准，您将在 "**模板**" 仪表板上看到您的新模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-506">One the template is approved by two admins, you'll see your new template on your **Templates** dashboard.</span></span>

#### <a name="import-template-data-with-excel"></a><span data-ttu-id="c41ae-507">使用 Excel 导入模板数据</span><span class="sxs-lookup"><span data-stu-id="c41ae-507">Import Template data with Excel</span></span>

<span data-ttu-id="c41ae-508">若要修改模板或创建自己的模板，您将使用[Excel 电子表格](https://go.microsoft.com/fwlink/?linkid=2124865)来捕获必要数据并将其上载到合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="c41ae-508">To modify a template or create your own template, you'll use an [Excel spreadsheet](https://go.microsoft.com/fwlink/?linkid=2124865) to capture the necessary data and upload it to Compliance Manager.</span></span> <span data-ttu-id="c41ae-509">此电子表格模板具有必须使用的特定格式和架构，或者不会将其导入到合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-509">This spreadsheet template has a specific format and schema that must be used or it will not import into Compliance Manager.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c41ae-510">如果之前已在合规性管理器中创建或自定义模板，则**此过程最近更新。请仔细查看此部分。**</span><span class="sxs-lookup"><span data-stu-id="c41ae-510">If you've created or customized templates in Compliance Manager before, **this process has been recently updated. Please review this section carefully.**</span></span>

<span data-ttu-id="c41ae-511">电子表格包含四个选项卡，其中三个选项卡是必需的：</span><span class="sxs-lookup"><span data-stu-id="c41ae-511">The spreadsheet contains four tabs, three of which are required:</span></span>

1. <span data-ttu-id="c41ae-512">模板（必需）</span><span class="sxs-lookup"><span data-stu-id="c41ae-512">Template (required)</span></span>
2. <span data-ttu-id="c41ae-513">ControlFamily （必需）</span><span class="sxs-lookup"><span data-stu-id="c41ae-513">ControlFamily (required)</span></span>
3. <span data-ttu-id="c41ae-514">操作（必需）</span><span class="sxs-lookup"><span data-stu-id="c41ae-514">Actions (required)</span></span>
4. <span data-ttu-id="c41ae-515">维度（可选）</span><span class="sxs-lookup"><span data-stu-id="c41ae-515">Dimensions (optional)</span></span>

<span data-ttu-id="c41ae-516">您的电子表格**必须按此顺序包含选项卡**，否则您的数据将无法成功导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-516">Your spreadsheet **must include the tabs in this order**, otherwise your data won't successfully import to a template.</span></span>

##### <a name="template-tab"></a><span data-ttu-id="c41ae-517">模板选项卡</span><span class="sxs-lookup"><span data-stu-id="c41ae-517">Template tab</span></span>

<span data-ttu-id="c41ae-518">"**模板**" 选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-518">The **Template** tab is required.</span></span> <span data-ttu-id="c41ae-519">此选项卡中的信息提供有关模板的元数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-519">The information in this tab provides metadata about the template.</span></span> <span data-ttu-id="c41ae-520">有四个必需的列。</span><span class="sxs-lookup"><span data-stu-id="c41ae-520">There are four required columns.</span></span> <span data-ttu-id="c41ae-521">列必须保留在 Excel 工作表上的顺序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c41ae-521">The columns must retain the order on the Excel sheet as listed below.</span></span> <span data-ttu-id="c41ae-522">您可以在四列**之后**添加自己的列，以提供自己的维度。</span><span class="sxs-lookup"><span data-stu-id="c41ae-522">You can add your own column **after** the four columns to provide your own dimensions.</span></span> <span data-ttu-id="c41ae-523">如果执行此操作，请务必按照[下面的说明](#dimensions-tab)将其添加到 "**维度**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c41ae-523">If you do this, be sure to add them to the **Dimensions** tab using the [instructions below](#dimensions-tab).</span></span>

- <span data-ttu-id="c41ae-524">**title**：这是模板的标题，它必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-524">**title**: This is the title for your template, which must be unique.</span></span> <span data-ttu-id="c41ae-525">它无法与合规性管理器中的其他模板共享名称，无论它是已创建的模板，还是由 Microsoft 提供的预先配置的模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-525">It can't share a name with another template you have in Compliance Manager, whether it's a template you already created, or a pre-configured template provided by Microsoft.</span></span>

- <span data-ttu-id="c41ae-526">**产品**：这是必需的维度。</span><span class="sxs-lookup"><span data-stu-id="c41ae-526">**product**: This is a required dimension.</span></span> <span data-ttu-id="c41ae-527">列出与模板关联的产品。</span><span class="sxs-lookup"><span data-stu-id="c41ae-527">List the product associated with the template.</span></span>

- <span data-ttu-id="c41ae-528">**证书**：这是您要为模板使用的法规。</span><span class="sxs-lookup"><span data-stu-id="c41ae-528">**certification**: This is the regulation you're using for the template.</span></span>

- <span data-ttu-id="c41ae-529">**inScopeServices**：这些服务是此评估解决的产品中的服务（例如，如果您将 Office 365 列为产品，则 Microsoft 团队可能是一个范围内的服务）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-529">**inScopeServices**: These are the services within the product that this assessment addresses (for example, if you listed Office 365 as the product, Microsoft Teams could be an in-scope service).</span></span> <span data-ttu-id="c41ae-530">您可以列出用两个分号分隔的多个服务。</span><span class="sxs-lookup"><span data-stu-id="c41ae-530">You can list multiple services separated by two semi-colons.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-531">关于产品和证书：在导入 "**产品**" 和 "**证书**" 单元格中插入的数据无法在导入电子表格以创建或自定义模板之后进行编辑。</span><span class="sxs-lookup"><span data-stu-id="c41ae-531">Regarding product and certification: The data you insert in the **product** and **certification** cells cannot be edited after you import the spreadsheet to create or customize a template.</span></span> <span data-ttu-id="c41ae-532">此外，组不能包含具有相同的**产品/认证**组合的两个评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-532">Also, a group cannot contain two assessments that have the same **product/certification** combination.</span></span> <span data-ttu-id="c41ae-533">您可以有多个模板具有相同的产品/认证组合。</span><span class="sxs-lookup"><span data-stu-id="c41ae-533">You can have multiple templates that have the same product/certification combination.</span></span>

##### <a name="controlfamily-tab"></a><span data-ttu-id="c41ae-534">ControlFamily 选项卡</span><span class="sxs-lookup"><span data-stu-id="c41ae-534">ControlFamily tab</span></span>

<span data-ttu-id="c41ae-535">**ControlFamily**选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-535">The **ControlFamily** tab is required.</span></span>  <span data-ttu-id="c41ae-536">此选项卡中的必需列（必须遵循示例电子表格中提供的顺序）为：</span><span class="sxs-lookup"><span data-stu-id="c41ae-536">The required columns in this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="c41ae-537">**controlName**：这是来自证书、标准或法规的控件名称，通常是某种类型的 ID。</span><span class="sxs-lookup"><span data-stu-id="c41ae-537">**controlName**: This is the control name from the certification, standard, or regulation, which is typically some type of ID.</span></span> <span data-ttu-id="c41ae-538">控件名称在模板中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-538">Control names must be unique within a template.</span></span> <span data-ttu-id="c41ae-539">电子表格中不能有多个名称相同的控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-539">You can't have multiple controls with the same name in the spreadsheet.</span></span>

- <span data-ttu-id="c41ae-540">**controlFamily**：为 controlFamily 提供一个单词或短语，用于标识广泛的控件分组。</span><span class="sxs-lookup"><span data-stu-id="c41ae-540">**controlFamily**: Provide a word or phrase for the controlFamily, which identifies a broad grouping of controls.</span></span> <span data-ttu-id="c41ae-541">ControlFamily 不一定是唯一的;它可以在电子表格中多次列出。</span><span class="sxs-lookup"><span data-stu-id="c41ae-541">A controlFamily doesn't have to be unique; it can be listed more than once in a spreadsheet.</span></span> <span data-ttu-id="c41ae-542">同一个 controlFamily 也可以在多个模板中列出，尽管它们彼此之间没有关系。</span><span class="sxs-lookup"><span data-stu-id="c41ae-542">The same controlFamily can also be listed in multiple templates, though they have no relation to each other.</span></span> <span data-ttu-id="c41ae-543">每个 controlFamily 必须至少映射到一个控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-543">Every controlFamily must be mapped to at least one control.</span></span>

- <span data-ttu-id="c41ae-544">**controlTitle**：提供控件的标题。</span><span class="sxs-lookup"><span data-stu-id="c41ae-544">**controlTitle**: Provide a title for the control.</span></span> <span data-ttu-id="c41ae-545">尽管 controlName 是参考代码，但标题是一种通常会在法规中看到的 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="c41ae-545">Whereas the controlName is a reference code, the title is a rich text format typically seen in the regulations.</span></span>

- <span data-ttu-id="c41ae-546">**controlDescription**：提供控件的说明。</span><span class="sxs-lookup"><span data-stu-id="c41ae-546">**controlDescription**: Provide a description of the control.</span></span>

- <span data-ttu-id="c41ae-547">**controlActionTitle**：这是要与此控件相关的操作的标题。</span><span class="sxs-lookup"><span data-stu-id="c41ae-547">**controlActionTitle**: This is the title of an action that you want to relate to this control.</span></span> <span data-ttu-id="c41ae-548">您可以添加多个操作，方法是用两个分号隔开，中间没有空格。</span><span class="sxs-lookup"><span data-stu-id="c41ae-548">You can add multiple actions by separating by two semi-colons with no space in between.</span></span> <span data-ttu-id="c41ae-549">您列出的每个控件必须至少包含一个操作，并且该操作必须存在（这意味着您可以在同一电子表格的 "**操作**" 选项卡上列出您列出的操作、存在于其他模板中的操作或由 Microsoft 创建的操作）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-549">Every control you list must include at least one action, and the action must exist (which means you can list an action that you list on the **Actions** tab of the same spreadsheet, an action that exists in a different template, or an action created by Microsoft).</span></span> <span data-ttu-id="c41ae-550">不同的控件可以引用相同的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-550">Different controls can reference the same action.</span></span>

##### <a name="actions-tab"></a><span data-ttu-id="c41ae-551">操作选项卡</span><span class="sxs-lookup"><span data-stu-id="c41ae-551">Actions tab</span></span>

<span data-ttu-id="c41ae-552">"**操作**" 选项卡是必需的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-552">The **Actions** tab is required.</span></span>  <span data-ttu-id="c41ae-553">它指定您的组织的操作，而不是 Microsoft 的操作，这些操作在合规性管理器中已存在。</span><span class="sxs-lookup"><span data-stu-id="c41ae-553">It designates actions of your organization and not the actions of Microsoft, which already exist in Compliance Manager.</span></span> <span data-ttu-id="c41ae-554">此选项卡必需的列必须遵循示例电子表格中提供的顺序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c41ae-554">The required columns for this tab, which must follow the order provided in the sample spreadsheet, are:</span></span>

- <span data-ttu-id="c41ae-555">**actionTitle**：这是您的操作的标题，是必填字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-555">**actionTitle**: This is the title for your action and is a required field.</span></span> <span data-ttu-id="c41ae-556">您提供的标题必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-556">The title you provide must be unique.</span></span> <span data-ttu-id="c41ae-557">**重要说明**：如果您引用您拥有的已存在的操作（如在另一个模板中），并且在后续列中修改了它的任何元素，则这些更改将传播到其他模板中的同一操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-557">**Important**: if you reference an action you own that already exists (such as in another template) and you modify any of its elements in the subsequent columns, those changes will propagate to the same action in other templates.</span></span>

- <span data-ttu-id="c41ae-558">**implementationType**：在此必填字段中，列出以下三种实现类型之一：</span><span class="sxs-lookup"><span data-stu-id="c41ae-558">**implementationType**: In this required field, list one of the three implementation types below:</span></span>
    - <span data-ttu-id="c41ae-559">**操作**-由人员和进程实现以保护组织系统、资产、数据和人员的机密性、完整性和可用性（示例：安全意识和培训）</span><span class="sxs-lookup"><span data-stu-id="c41ae-559">**Operational** - actions implemented by people and processes to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: security awareness and training)</span></span>
    - <span data-ttu-id="c41ae-560">**技术**-通过使用信息系统的硬件、软件或固件组件中包含的技术和机制完成操作，以保护组织系统和数据的机密性、完整性和可用性（示例：多重身份验证）</span><span class="sxs-lookup"><span data-stu-id="c41ae-560">**Technical** - actions completed through the use of technology and mechanisms contained in the hardware, software, or firmware components of the information system to protect the confidentiality, integrity, and availability of organizational systems and data (example: multi-factor authentication)</span></span>
    - <span data-ttu-id="c41ae-561">**文档**-通过记录的策略和程序实现的操作：建立和定义保护组织系统、资产、数据和人员的机密性、完整性和可用性所需的控件（示例：信息安全策略）</span><span class="sxs-lookup"><span data-stu-id="c41ae-561">**Documentation** - actions implemented through documented policies and procedures establishing and defining the controls required to protect the confidentiality, integrity, and availability of organizational systems, assets, data, and personnel (example: an information security policy)</span></span>

- <span data-ttu-id="c41ae-562">**actionScore**：在此必填字段中，为您的操作提供数值分数值。</span><span class="sxs-lookup"><span data-stu-id="c41ae-562">**actionScore**: In this required field, provide a numeric score value for your action.</span></span> <span data-ttu-id="c41ae-563">它必须是介于1到99之间的整数;它不能为0、null 或空。</span><span class="sxs-lookup"><span data-stu-id="c41ae-563">It must be a whole number ranging from 1 to 99; it cannot be 0, null, or blank.</span></span> <span data-ttu-id="c41ae-564">此数字越大，它在改进合规性状态方面的价值越大。</span><span class="sxs-lookup"><span data-stu-id="c41ae-564">The higher the number, the greater its value toward improving your compliance posture.</span></span> <span data-ttu-id="c41ae-565">有关指南，请参阅下文 Microsoft 如何对控件进行评分：</span><span class="sxs-lookup"><span data-stu-id="c41ae-565">For guidance, see below how Microsoft scores its controls:</span></span>

<span data-ttu-id="c41ae-566">![合规性管理器控制点值](../media/compliance-score-controls-scoring.png "合规性管理器控制点值")</span><span class="sxs-lookup"><span data-stu-id="c41ae-566">![Compliance Manager controls point values](../media/compliance-score-controls-scoring.png "Compliance Manager controls point values")</span></span>

- <span data-ttu-id="c41ae-567">**actionDescriptionTitle**：这是说明的标题，并且是必需的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-567">**actionDescriptionTitle**: This is the title of the description and is required.</span></span> <span data-ttu-id="c41ae-568">此描述标题允许您在多个模板中执行相同的操作，并在每个模板中显示不同的说明。</span><span class="sxs-lookup"><span data-stu-id="c41ae-568">This description title allows you to have the same action in multiple templates and surface a different description in each template.</span></span>  <span data-ttu-id="c41ae-569">此字段可帮助您阐明说明所引用的模板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-569">This field helps you clarify what template the description is referencing.</span></span> <span data-ttu-id="c41ae-570">在大多数情况下，您可以在此字段中放置正在创建的模板的名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-570">In most cases, you can put the name of the template you're creating in this field.</span></span>

- <span data-ttu-id="c41ae-571">**actionDescription**：提供操作的说明。</span><span class="sxs-lookup"><span data-stu-id="c41ae-571">**actionDescription**: Provide a description of the action.</span></span> <span data-ttu-id="c41ae-572">您可以应用粗体文本和超链接等格式。</span><span class="sxs-lookup"><span data-stu-id="c41ae-572">You can apply formatting such as bold text and hyperlinks.</span></span> <span data-ttu-id="c41ae-573">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-573">This is required field.</span></span>

- <span data-ttu-id="c41ae-574">**维度-操作目的**：这是可选字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-574">**dimension-Action Purpose**: This is an optional field.</span></span> <span data-ttu-id="c41ae-575">如果包含，则标头必须包含 "dimension-" 前缀。</span><span class="sxs-lookup"><span data-stu-id="c41ae-575">If you include it, the header must include the "dimension-" prefix.</span></span> <span data-ttu-id="c41ae-576">此处包含的任何维度将用作[符合性分数中的筛选器](compliance-score-setup.md#filtering-your-dashboard-view)，并显示在合规性分数的 "改进操作详细信息" 页上。</span><span class="sxs-lookup"><span data-stu-id="c41ae-576">Any dimensions you include here will be used as [filters in Compliance Score](compliance-score-setup.md#filtering-your-dashboard-view) and appear on the improvement actions details page in Compliance Score.</span></span>

##### <a name="dimensions-tab"></a><span data-ttu-id="c41ae-577">维度选项卡</span><span class="sxs-lookup"><span data-stu-id="c41ae-577">Dimensions tab</span></span>

<span data-ttu-id="c41ae-578">"**维度**" 选项卡是可选的。</span><span class="sxs-lookup"><span data-stu-id="c41ae-578">The **Dimensions** tab is optional.</span></span> <span data-ttu-id="c41ae-579">但是，如果在其他位置引用维度，并且在您已创建的模板中或在 Microsoft 模板中不存在该维度，则需要在此处指定它。</span><span class="sxs-lookup"><span data-stu-id="c41ae-579">However, if you reference a dimension elsewhere, you need to specify it here if it does not exist in a template you've already created or in a Microsoft template.</span></span> <span data-ttu-id="c41ae-580">下面列出了此选项卡的列：</span><span class="sxs-lookup"><span data-stu-id="c41ae-580">The columns for this tab are listed below:</span></span>

- <span data-ttu-id="c41ae-581">**dimensionKey**： list as "product"、"认证"、"操作目的"</span><span class="sxs-lookup"><span data-stu-id="c41ae-581">**dimensionKey**: list as "product", "certifications," "action purpose"</span></span>
- <span data-ttu-id="c41ae-582">**dimensionValue**：示例： Office 365、HIPPA、预防性、侦探</span><span class="sxs-lookup"><span data-stu-id="c41ae-582">**dimensionValue**: examples: Office 365, HIPPA, Preventative, Detective</span></span>

<span data-ttu-id="c41ae-583">您可以通过转到 "**租户管理**" 并选择 "**维度**" 选项卡来查看现有维度。此外，无论何时导出现有模板，导出的电子表格都将具有 "**尺寸**" 选项卡，其中列出了模板中使用的所有尺寸。</span><span class="sxs-lookup"><span data-stu-id="c41ae-583">You can view your existing dimensions by going to **Tenant Management** and selecting the **Dimensions** tab. Also, anytime you export an existing template, the exported spreadsheet will have the **Dimensions** tab, which lists all the dimensions used in the template.</span></span>

### <a name="modify-an-existing-template"></a><span data-ttu-id="c41ae-584">修改现有模板</span><span class="sxs-lookup"><span data-stu-id="c41ae-584">Modify an existing Template</span></span>

<span data-ttu-id="c41ae-585">若要使用上面所述的导入过程对创建或自定义的模板进行更改，请使用相同的过程将这些更改导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-585">To make changes to a Template you created or customized using the import process outlined above, you use the same process to import those changes into your Template.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-586">编辑模板组件时，有几个重要的因素需要注意，因此请仔细查看此部分。</span><span class="sxs-lookup"><span data-stu-id="c41ae-586">There are several important factors to be aware of as you edit template components, so please review this section carefully.</span></span>

#### <a name="general-process-for-modifying-a-template"></a><span data-ttu-id="c41ae-587">修改模板的常规过程</span><span class="sxs-lookup"><span data-stu-id="c41ae-587">General process for modifying a Template</span></span>

<span data-ttu-id="c41ae-588">若要对组织的现有模板之一进行更改，常规过程如下：</span><span class="sxs-lookup"><span data-stu-id="c41ae-588">To make changes to one of your organization's existing templates, the general process is:</span></span>

1. <span data-ttu-id="c41ae-589">从 "**模板**" 仪表板中，选择要修改的模板，该模板将调出显示 "**模板**" 选项卡的 "**控件信息**" 仪表板。</span><span class="sxs-lookup"><span data-stu-id="c41ae-589">From your **Templates** dashboard, select the Template you want to modify, which brings up your **Controls Info** dashboard showing your **Template** tab.</span></span>
2. <span data-ttu-id="c41ae-590">从此处选择 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-590">From here, select **Export**.</span></span> <span data-ttu-id="c41ae-591">将下载包含所有模板数据的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="c41ae-591">An Excel sheet with all your template data will download.</span></span>
3. <span data-ttu-id="c41ae-592">若要编辑、添加或删除操作，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="c41ae-592">To edit, add, or remove an action, see the sections below.</span></span>
4. <span data-ttu-id="c41ae-593">完成对 Excel 文件所做的更改后，通过从仪表板中选择模板并选择 "**导入**"，将文件导入到模板中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-593">When you're done making changes to your Excel file, import the file back into the template by selecting the template from your dashboard and selecting **Import**.</span></span> <span data-ttu-id="c41ae-594">您的模板现在将包含所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c41ae-594">Your template will now include the changes you made.</span></span>

#### <a name="to-edit-template-attributes"></a><span data-ttu-id="c41ae-595">编辑模板属性</span><span class="sxs-lookup"><span data-stu-id="c41ae-595">To edit Template attributes</span></span>

<span data-ttu-id="c41ae-596">在 "**模板**" 选项卡上，您可以编辑 "**标题**" 列、" **inScopeServices** " 列以及您可能已添加的任何其他列中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c41ae-596">On the **Templates** tab, you can edit anything in the **title** column, the **inScopeServices** column, and in any other column you may have added.</span></span> <span data-ttu-id="c41ae-597">但是，不能编辑 "**产品**" 或 "**认证**" 列中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c41ae-597">However, you can't edit anything in the **product** or **certification** columns.</span></span>

#### <a name="to-add-an-action-to-a-template"></a><span data-ttu-id="c41ae-598">向模板添加操作</span><span class="sxs-lookup"><span data-stu-id="c41ae-598">To add an action to a Template</span></span>

1. <span data-ttu-id="c41ae-599">转到 "**操作**" 选项卡，并将您的信息添加到现有操作下方的第一个空行中的必填字段中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-599">Go to the **Actions** tab and add your information in the required fields in the first empty row underneath your existing actions.</span></span>
2. <span data-ttu-id="c41ae-600">转到 " **ControlFamily** " 选项卡。查找包含操作所映射到的控件的行。</span><span class="sxs-lookup"><span data-stu-id="c41ae-600">Go to your **ControlFamily** tab. Find the row containing the control your action maps to.</span></span> <span data-ttu-id="c41ae-601">将您的新操作添加到该行中的 " **controlActionTitle** " 列（请记住，使用两个分号分隔此字段中的多个操作，中间没有空格）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-601">Add your new action to the **controlActionTitle** column in that row (remember to separate multiple actions in this field with two semi-colons, no space in between).</span></span>
3. <span data-ttu-id="c41ae-602">将电子表格保存到本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="c41ae-602">Save your spreadsheet to your local machine.</span></span>

#### <a name="to-edit-an-actions-information"></a><span data-ttu-id="c41ae-603">编辑操作的信息</span><span class="sxs-lookup"><span data-stu-id="c41ae-603">To edit an action's information</span></span>

<span data-ttu-id="c41ae-604">您可以更改*除标题之外*的任何操作的信息。</span><span class="sxs-lookup"><span data-stu-id="c41ae-604">You can change any action's information *except for its title*.</span></span> <span data-ttu-id="c41ae-605">您可以编辑从 B 之前的列中的任何单元格，并将该文件重新导入到模板中时，该模板中的操作现在将包含更新后的数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-605">You can edit any cell from columns B onward, and when you import the file back into the template, the actions in that template will now contain the updated data.</span></span>

<span data-ttu-id="c41ae-606">您无法编辑**actionTitle** （column A），因为如果您这样做，合规性管理器会将其视为一个新操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-606">You cannot edit the **actionTitle** (column A) because if you do, Compliance Manager considers this to be a new action.</span></span> <span data-ttu-id="c41ae-607">如果要更改操作的名称，请参阅以下直接说明。</span><span class="sxs-lookup"><span data-stu-id="c41ae-607">If you want to change an action's name, see the instructions immediately below.</span></span>

#### <a name="to-change-the-name-of-an-action"></a><span data-ttu-id="c41ae-608">更改操作的名称</span><span class="sxs-lookup"><span data-stu-id="c41ae-608">To change the name of an action</span></span>

<span data-ttu-id="c41ae-609">如果要更改操作的名称，则必须在电子表格中显式指定要将现有名称替换为新名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-609">If you want to change the name of an action, you have to explicitly designate in the spreadsheet that you are replacing an existing name with a new name.</span></span> <span data-ttu-id="c41ae-610">若要更改操作的名称，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-610">To change an action's name, follow these steps:</span></span>

1. <span data-ttu-id="c41ae-611">在电子表格的 "**操作**" 选项卡中，将一个新列添加到 a 列之后的电子表格中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-611">In the **Actions** tab of your spreadsheet, add a new column to the spreadsheet after column A.</span></span>
2. <span data-ttu-id="c41ae-612">在此新列（现在是列 B）中，将其标头放在第1行： **oldActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-612">In this new column, which is now column B, put as its header in row 1: **oldActionTitle**.</span></span>
3. <span data-ttu-id="c41ae-613">复制 A 列的内容并将其粘贴到 B 列中。这会将现有操作标题（即要更改的内容）放入 B 列中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-613">Copy the contents of column A and paste them into column B. This puts your existing action titles, which are what you want to change, into column B.</span></span>
4. <span data-ttu-id="c41ae-614">在**actionTitle**列中，删除旧名称，并将其替换为您的操作的新名称。</span><span class="sxs-lookup"><span data-stu-id="c41ae-614">In column A, **actionTitle**, delete the old name and replace it with the new name for your action.</span></span>

#### <a name="to-remove-an-action-from-a-template"></a><span data-ttu-id="c41ae-615">从模板中删除操作</span><span class="sxs-lookup"><span data-stu-id="c41ae-615">To remove an action from a Template</span></span>

<span data-ttu-id="c41ae-616">从电子表格的某一行中删除操作**并不会**删除正在编辑的模板中的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-616">Deleting an action from a row in a spreadsheet **does not** remove the action from the template you're editing.</span></span> <span data-ttu-id="c41ae-617">相反，请按照下面的过程操作，删除操作：</span><span class="sxs-lookup"><span data-stu-id="c41ae-617">Instead, follow the process below to remove an action:</span></span>

1. <span data-ttu-id="c41ae-618">在 "**操作**" 选项卡上，插入一个新列作为列 a，并在标题行中放置**操作**，该行号为1。</span><span class="sxs-lookup"><span data-stu-id="c41ae-618">On the **Actions** tab, insert a new column as column A and put **Operation** in the header row, which is row number one.</span></span>
2. <span data-ttu-id="c41ae-619">在要删除的操作所在的行上，将**Delete**放入该行的 A 列中。</span><span class="sxs-lookup"><span data-stu-id="c41ae-619">On the row for the action you want to remove, put **Delete** in column A for that row.</span></span>
3. <span data-ttu-id="c41ae-620">确保控件不会再引用此操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-620">Ensure that this action is no longer referenced by a control.</span></span> <span data-ttu-id="c41ae-621">转到 " **ControlFamily** " 选项卡，在第 F 列中查找您的操作的标题，即**controlActionTitle**。</span><span class="sxs-lookup"><span data-stu-id="c41ae-621">Go to the **ControlFamily** tab and look for your action's title in column F, which is **controlActionTitle**.</span></span>
4. <span data-ttu-id="c41ae-622">当您找到 " **controlActionTitle** " 列中列出的操作时，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="c41ae-622">When you find your action listed in the **controlActionTitle** column, delete it.</span></span>
5. <span data-ttu-id="c41ae-623">将电子表格保存到本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="c41ae-623">Save your spreadsheet to your local machine.</span></span>

<span data-ttu-id="c41ae-624">将电子表格导入回模板时，将从模板中删除您的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-624">When you import your spreadsheet back into the template, your action will be removed from the template.</span></span> <span data-ttu-id="c41ae-625">从模板中移除操作并不会完全删除该操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-625">Removing an action from a template does not completely remove the action.</span></span> <span data-ttu-id="c41ae-626">另一个模板仍可引用该操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-626">That action can still be referenced by another template.</span></span>

<span data-ttu-id="c41ae-627">如果要删除控件引用的最后一个操作，则需要删除该控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-627">If you are removing the last action that a control references, then you need to remove the control.</span></span>

> [!NOTE]
> <span data-ttu-id="c41ae-628">若要删除控件，请执行以下操作：按照上述步骤删除操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-628">To remove a control: Follow the same process for removing an action as outlined above.</span></span> <span data-ttu-id="c41ae-629">在 " **ControlFamily** " 选项卡中，添加 "**操作**" 列并将 "**删除**" 放在要删除的控件旁边。</span><span class="sxs-lookup"><span data-stu-id="c41ae-629">In the **ControlFamily** tab, add an **Operation** column and put **Delete** next to the control you want to remove.</span></span>

### <a name="updates-to-templates"></a><span data-ttu-id="c41ae-630">模板的更新</span><span class="sxs-lookup"><span data-stu-id="c41ae-630">Updates to Templates</span></span>

<span data-ttu-id="c41ae-631">每次通过版本控制过程更新评估时，您的自定义评估将继承这些更新并保留您的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-631">Each time an Assessment is updated through the versioning process, your customized Assessment will inherit those updates and keep your custom controls.</span></span> <span data-ttu-id="c41ae-632">[有关评估更新，请参阅版本控制警报](#versioning-alerts-for-assessment-updates)。</span><span class="sxs-lookup"><span data-stu-id="c41ae-632">See [Versioning alerts for Assessment updates](#versioning-alerts-for-assessment-updates).</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="c41ae-633">将模板导出到 JSON</span><span class="sxs-lookup"><span data-stu-id="c41ae-633">Export a Template to JSON</span></span>

<span data-ttu-id="c41ae-634">合规性管理器（预览版）支持将模板导出为 JavaScript 对象表示法（JSON）格式。</span><span class="sxs-lookup"><span data-stu-id="c41ae-634">Compliance Manager (Preview) supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="c41ae-635">这使您可以与支持 JSON 的其他系统交换合规性管理器数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-635">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="c41ae-636">报告</span><span class="sxs-lookup"><span data-stu-id="c41ae-636">Reports</span></span>

<span data-ttu-id="c41ae-637">您可以将评估导出到您组织中的合规性利益干系人或外部审计员和主管机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="c41ae-637">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="c41ae-638">报告是在导出的日期和时间进行评估的快照。</span><span class="sxs-lookup"><span data-stu-id="c41ae-638">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="c41ae-639">该报告包含 Microsoft 和客户托管的控件的详细信息，用于评估、控制实施状态、控制测试日期、测试结果以及指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="c41ae-639">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="c41ae-640">由于隐藏的评估不会保留指向已上载文档的链接，因此应先导出该评估，然后再将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="c41ae-640">Because hidden Assessments don't retain links to uploaded documents, you should export the Assessment before you hide it.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="c41ae-641">导出评估</span><span class="sxs-lookup"><span data-stu-id="c41ae-641">Export an Assessment</span></span>

1. <span data-ttu-id="c41ae-642">在合规性管理器仪表板中，选择 "**控件信息**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c41ae-642">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="c41ae-643">在下拉菜单中选择要导出的评估的组和评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-643">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="c41ae-644">选择 "导出"。</span><span class="sxs-lookup"><span data-stu-id="c41ae-644">Select Export.</span></span> <span data-ttu-id="c41ae-645">将评估导出作为 Excel 文件下载。</span><span class="sxs-lookup"><span data-stu-id="c41ae-645">The Assessment export is downloaded as an Excel file.</span></span>

<span data-ttu-id="c41ae-646">![合规性管理器评估 Excel 报告](../media/compliance-manager-assessment-report.png "合规性管理器评估 Excel 报告")</span><span class="sxs-lookup"><span data-stu-id="c41ae-646">![Compliance Manager Assessment Excel Report](../media/compliance-manager-assessment-report.png "Compliance Manager assessment Excel report")</span></span>

## <a name="permissions"></a><span data-ttu-id="c41ae-647">权限</span><span class="sxs-lookup"><span data-stu-id="c41ae-647">Permissions</span></span>

<span data-ttu-id="c41ae-648">下表介绍了每个合规性管理器权限及其允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c41ae-648">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="c41ae-649">该表还指示分配了每个权限的角色。</span><span class="sxs-lookup"><span data-stu-id="c41ae-649">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="c41ae-650">**Azure AD 全局读取器**</span><span class="sxs-lookup"><span data-stu-id="c41ae-650">**Azure AD Global Reader**</span></span>|<span data-ttu-id="c41ae-651">**合规性管理器读者**</span><span class="sxs-lookup"><span data-stu-id="c41ae-651">**Compliance Manager Reader**</span></span>|<span data-ttu-id="c41ae-652">**合规性管理器参与者**</span><span class="sxs-lookup"><span data-stu-id="c41ae-652">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="c41ae-653">**合规性管理器评估员**</span><span class="sxs-lookup"><span data-stu-id="c41ae-653">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="c41ae-654">**合规性管理器管理员**</span><span class="sxs-lookup"><span data-stu-id="c41ae-654">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="c41ae-655">**门户管理员**</span><span class="sxs-lookup"><span data-stu-id="c41ae-655">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c41ae-656">**读取数据：** 用户可以读取但不能编辑数据（模板数据和租户管理除外）。</span><span class="sxs-lookup"><span data-stu-id="c41ae-656">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="c41ae-657">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-657">X</span></span> | <span data-ttu-id="c41ae-658">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-658">X</span></span> | <span data-ttu-id="c41ae-659">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-659">X</span></span> | <span data-ttu-id="c41ae-660">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-660">X</span></span> | <span data-ttu-id="c41ae-661">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-661">X</span></span>  | <span data-ttu-id="c41ae-662">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-662">X</span></span> |
|<span data-ttu-id="c41ae-663">**编辑数据：** 除了 "测试结果" 和 "测试日期" 字段（"模板数据" 和 "租户管理" 除外）之外，用户可以编辑所有字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-663">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="c41ae-664">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-664">X</span></span> | <span data-ttu-id="c41ae-665">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-665">X</span></span>  | <span data-ttu-id="c41ae-666">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-666">X</span></span> | <span data-ttu-id="c41ae-667">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-667">X</span></span> |
|<span data-ttu-id="c41ae-668">**编辑测试结果：** 用户可以编辑 "测试结果" 和 "测试日期" 字段。</span><span class="sxs-lookup"><span data-stu-id="c41ae-668">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="c41ae-669">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-669">X</span></span> | <span data-ttu-id="c41ae-670">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-670">X</span></span> | <span data-ttu-id="c41ae-671">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-671">X</span></span> |
|<span data-ttu-id="c41ae-672">**管理评估：** 用户可以创建、存档和删除评估。</span><span class="sxs-lookup"><span data-stu-id="c41ae-672">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="c41ae-673">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-673">X</span></span> | <span data-ttu-id="c41ae-674">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-674">X</span></span> |
|<span data-ttu-id="c41ae-675">**管理主数据：** 用户可以查看、编辑和删除模板数据和租户管理数据。</span><span class="sxs-lookup"><span data-stu-id="c41ae-675">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="c41ae-676">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-676">X</span></span> | <span data-ttu-id="c41ae-677">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-677">X</span></span> |
|<span data-ttu-id="c41ae-678">**管理用户：** 用户可以将组织中的其他用户添加到 Reader、投稿人、评估员和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="c41ae-678">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="c41ae-679">只有组织中具有全局管理员角色的用户才可以在门户管理员角色中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="c41ae-679">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="c41ae-680">X</span><span class="sxs-lookup"><span data-stu-id="c41ae-680">X</span></span> |