---
title: 访问并备份以往用户的数据的访问
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 了解当某人离开你的组织时，如何保留员工的文件和电子邮件。
ms.openlocfilehash: 2bf32aa9e7a3dcc76ae2114240bff07d697ce29d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387197"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="bea2c-103">访问并备份以往用户的数据的访问</span><span class="sxs-lookup"><span data-stu-id="bea2c-103">Get access to and back up a former user's data</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bea2c-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="bea2c-104">The admin center is changing.</span></span> <span data-ttu-id="bea2c-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="bea2c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end


<span data-ttu-id="bea2c-106">当员工离开组织时，您可能希望访问其数据（文档和电子邮件），并对其进行查看、备份或将其提供给新员工。</span><span class="sxs-lookup"><span data-stu-id="bea2c-106">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="bea2c-107">访问以前的用户的 OneDrive 文档</span><span class="sxs-lookup"><span data-stu-id="bea2c-107">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="bea2c-108">如果删除用户的许可证，但不删除该帐户，则可以为自己提供对用户的 OneDrive 中的内容的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bea2c-108">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="bea2c-109">如果您删除用户帐户，默认情况下您有30天的时间来访问以前的用户的 OneDrive 数据。</span><span class="sxs-lookup"><span data-stu-id="bea2c-109">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="bea2c-110">[了解如何为已删除的用户设置 OneDrive 保留](/onedrive/set-retention)。</span><span class="sxs-lookup"><span data-stu-id="bea2c-110">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="bea2c-111">如果您不在这段时间内[还原用户帐户](/office365/admin/add-users/restore-user)，其 OneDrive 内容将被删除。</span><span class="sxs-lookup"><span data-stu-id="bea2c-111">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="bea2c-112">若要保留以前的用户的 OneDrive 文件，请先授予自己对其 OneDrive 的访问权限，然后移动要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="bea2c-112">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="bea2c-113">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="bea2c-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="bea2c-114">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bea2c-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="bea2c-115">选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="bea2c-115">Select a user.</span></span>

3. <span data-ttu-id="bea2c-116">在右侧窗格中，选择 " **OneDrive**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-116">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="bea2c-117">在 "**获取对文件的访问权限**" 下，选择 "**创建指向文件的链接**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-117">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="bea2c-118">选择要打开文件位置的链接。</span><span class="sxs-lookup"><span data-stu-id="bea2c-118">Select the link to open the file location.</span></span> <span data-ttu-id="bea2c-119">将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。</span><span class="sxs-lookup"><span data-stu-id="bea2c-119">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="bea2c-120">您可以一次移动或复制最多 500 MB 的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bea2c-120">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="bea2c-121">移动或复制具有版本历史记录的文档时，仅移动最新版本。</span><span class="sxs-lookup"><span data-stu-id="bea2c-121">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bea2c-122">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bea2c-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="bea2c-123">选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="bea2c-123">Select a user.</span></span>

3. <span data-ttu-id="bea2c-124">在右侧窗格中，展开 " **OneDrive 设置**"，然后在 "**访问**" 下，选择 "**访问文件**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-124">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="bea2c-125">选择要打开文件位置的链接。</span><span class="sxs-lookup"><span data-stu-id="bea2c-125">Select the link to open the file location.</span></span> <span data-ttu-id="bea2c-126">将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。</span><span class="sxs-lookup"><span data-stu-id="bea2c-126">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="bea2c-127">您可以一次移动或复制最多 500 MB 的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bea2c-127">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="bea2c-128">移动或复制具有版本历史记录的文档时，仅移动最新版本。</span><span class="sxs-lookup"><span data-stu-id="bea2c-128">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bea2c-129">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="bea2c-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="bea2c-130">选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="bea2c-130">Select a user.</span></span>

3. <span data-ttu-id="bea2c-131">在右侧窗格中，展开 " **OneDrive 设置**"，然后在 "**访问**" 下，选择 "**访问文件**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-131">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="bea2c-132">选择要打开文件位置的链接。</span><span class="sxs-lookup"><span data-stu-id="bea2c-132">Select the link to open the file location.</span></span> <span data-ttu-id="bea2c-133">将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。</span><span class="sxs-lookup"><span data-stu-id="bea2c-133">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="bea2c-134">您可以一次移动或复制最多 500 MB 的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bea2c-134">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="bea2c-135">移动或复制具有版本历史记录的文档时，仅移动最新版本。</span><span class="sxs-lookup"><span data-stu-id="bea2c-135">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="bea2c-136">撤销对用户的 OneDrive 的管理员访问权限</span><span class="sxs-lookup"><span data-stu-id="bea2c-136">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="bea2c-137">作为全局管理员，你可以为自己提供对用户的 OneDrive 中的内容的访问权限，但您可能想要在不再需要时删除您的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bea2c-137">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bea2c-138">以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理员中心</a>。</span><span class="sxs-lookup"><span data-stu-id="bea2c-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="bea2c-139">如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bea2c-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bea2c-140">以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理员中心</a>。</span><span class="sxs-lookup"><span data-stu-id="bea2c-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="bea2c-141">如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bea2c-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bea2c-142">以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理员中心</a>。</span><span class="sxs-lookup"><span data-stu-id="bea2c-142">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="bea2c-143">如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="bea2c-143">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="bea2c-144">在左窗格中，选择 "**管理中心**" " \> **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-144">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="bea2c-145">（你可能需要选择“**全部显示**”以查看管理中心列表）。</span><span class="sxs-lookup"><span data-stu-id="bea2c-145">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="bea2c-146">如果看到经典 SharePoint 管理中心，请选择页面顶部的“**立即打开**”，打开新的 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="bea2c-146">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="bea2c-147">在左窗格中，选择 "**更多功能**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-147">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="bea2c-148">在 "**用户配置文件**" 下，选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-148">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="bea2c-149">在 "**人员**" 下，选择 "**管理用户配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-149">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="bea2c-150">输入用户的名称，然后选择 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-150">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="bea2c-151">右键单击该用户，然后选择 "**管理网站集所有者**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-151">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="bea2c-152">删除不再需要访问用户数据的人员，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bea2c-152">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="bea2c-153">访问以前用户的 Outlook 数据</span><span class="sxs-lookup"><span data-stu-id="bea2c-153">Access the Outlook data of a former user</span></span>

<span data-ttu-id="bea2c-154">若要保存以前员工的电子邮件、日历、任务和联系人，请将信息导出到 Outlook 数据文件（.pst）。</span><span class="sxs-lookup"><span data-stu-id="bea2c-154">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="bea2c-155">[将前员工的电子邮件添加](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)到你的 Outlook （如果[重置用户的密码](reset-passwords.md)，则可以将其设置为仅你知道的内容。）</span><span class="sxs-lookup"><span data-stu-id="bea2c-155">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="bea2c-156">在 Outlook 中，选择 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-156">In Outlook, select **File**.</span></span>
    
    ![这就是功能区在 Outlook 2016 中的外观。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="bea2c-158">选择 "**打开 &amp; 导出** \> **导入/导出**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-158">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage 视图中的导入/导出命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="bea2c-160">选择 "**导出到文件**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-160">Select **Export to a file**, and then select **Next**.</span></span>
    
    !["导入和导出向导" 中的 "导出到文件" 选项](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="bea2c-162">选择 " **Outlook 数据文件（.pst）**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-162">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="bea2c-163">选择要导出的帐户，方法是选择名称或电子邮件地址，例如邮箱-Anne Weiler 或 anne@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bea2c-163">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="bea2c-164">如果要导出帐户中的所有内容（包括邮件、日历、联系人、任务和便笺），请确保选中 "**包含子文件夹**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="bea2c-164">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bea2c-165">您可以一次导出一个帐户。</span><span class="sxs-lookup"><span data-stu-id="bea2c-165">You can export one account at a time.</span></span> <span data-ttu-id="bea2c-166">如果要在导出一个帐户后导出多个帐户，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="bea2c-166">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    !["导出 Outlook 数据文件" 对话框，其中选中了 top 文件夹并包含选中的子文件夹](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="bea2c-168">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bea2c-168">Select **Next**.</span></span>
    
8. <span data-ttu-id="bea2c-169">选择 "**浏览**" 以选择保存 Outlook 数据文件（.pst）的位置。</span><span class="sxs-lookup"><span data-stu-id="bea2c-169">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="bea2c-170">键入文件名 *，然后*选择 **"确定"** 以继续。</span><span class="sxs-lookup"><span data-stu-id="bea2c-170">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bea2c-171">如果您以前使用过导出，则将显示上一个文件夹位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="bea2c-171">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="bea2c-172">在选择 **"确定"** 之前键入*其他文件名*。</span><span class="sxs-lookup"><span data-stu-id="bea2c-172">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="bea2c-173">如果要导出到现有 Outlook 数据文件 (.pst)，请在" **选项**"下指定文件中已存在导出项目时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bea2c-173">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="bea2c-174">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bea2c-174">Select **Finish**.</span></span>
    
<span data-ttu-id="bea2c-175">如果不创建新的 Outlook 数据文件（.pst）或使用受密码保护的文件，Outlook 将立即开始导出。</span><span class="sxs-lookup"><span data-stu-id="bea2c-175">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="bea2c-176">如果要创建 Outlook 数据文件（.pst），可选密码可帮助保护文件。</span><span class="sxs-lookup"><span data-stu-id="bea2c-176">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="bea2c-177">在出现 **"创建 Outlook 数据文件**" 对话框时，在 "**密码**" 和 "**验证密码**" 框中键入*密码*，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bea2c-177">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="bea2c-178">在 " **Outlook 数据文件密码**" 对话框中，键入*密码*，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bea2c-178">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="bea2c-179">如果要导出到受密码保护的现有 Outlook 数据文件（.pst）中，请在 " **Outlook 数据文件密码**" 对话框中，键入*密码*，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bea2c-179">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="bea2c-180">请参阅如何在 Outlook 2010 中[将电子邮件、联系人和日历导出或备份到 outlook .pst 文件](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bea2c-180">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="bea2c-181">默认情况下，你的电子邮件在12个月内可脱机使用。</span><span class="sxs-lookup"><span data-stu-id="bea2c-181">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="bea2c-182">如果需要，请参阅如何[增加可脱机使用的数据](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。</span><span class="sxs-lookup"><span data-stu-id="bea2c-182">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="bea2c-183">向另一个用户授予对以前用户的电子邮件的访问权限</span><span class="sxs-lookup"><span data-stu-id="bea2c-183">Give another user access to a former user's email</span></span> 

<span data-ttu-id="bea2c-184">若要将前一个员工的电子邮件、日历、任务和联系人的访问权限授予另一个员工，请将该信息导入到另一个员工的 Outlook 收件箱。</span><span class="sxs-lookup"><span data-stu-id="bea2c-184">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="bea2c-185">您还可以[将前一个用户的邮箱转换为共享邮箱，或将](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)[以前的员工的电子邮件转发给另一个员工](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="bea2c-185">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="bea2c-186">在 Outlook 中，转到 "**文件** \> **打开 &amp; 导出** \> **导入/导出**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-186">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="bea2c-187">这将启动 "导入和导出向导"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-187">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="bea2c-188">选择 "**从另一程序或文件导入**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-188">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![导入和导出向导](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="bea2c-190">选择 " **Outlook 数据文件（.pst）**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bea2c-190">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="bea2c-191">浏览到要导入的 .pst 文件。</span><span class="sxs-lookup"><span data-stu-id="bea2c-191">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="bea2c-192">在 "**选项**" 下，选择要处理重复项的方式</span><span class="sxs-lookup"><span data-stu-id="bea2c-192">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="bea2c-193">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bea2c-193">Select **Next**.</span></span>
    
7. <span data-ttu-id="bea2c-194">如果为 Outlook 数据文件（.pst）分配了密码，请输入密码，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bea2c-194">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="bea2c-195">设置用于导入项目的选项。</span><span class="sxs-lookup"><span data-stu-id="bea2c-195">Set the options for importing items.</span></span> <span data-ttu-id="bea2c-196">通常不需要更改默认设置。</span><span class="sxs-lookup"><span data-stu-id="bea2c-196">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="bea2c-197">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bea2c-197">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="bea2c-198">访问现有用户的 OneDrive 和电子邮件数据的步骤保持相同。</span><span class="sxs-lookup"><span data-stu-id="bea2c-198">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="bea2c-199">如果只想导入或还原 Outlook 数据文件（.pst）中的几个项目，则可以打开 Outlook 数据文件。</span><span class="sxs-lookup"><span data-stu-id="bea2c-199">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="bea2c-200">然后，在导航窗格中，将 "Outlook 数据文件" 文件夹中的项目拖到现有的 Outlook 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bea2c-200">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="bea2c-201">相关文章</span><span class="sxs-lookup"><span data-stu-id="bea2c-201">Related articles</span></span>
[<span data-ttu-id="bea2c-202">从 Office 365 中删除以前的员工</span><span class="sxs-lookup"><span data-stu-id="bea2c-202">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="bea2c-203">在 OneDrive 帐户上添加和删除管理员</span><span class="sxs-lookup"><span data-stu-id="bea2c-203">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="bea2c-204">还原已删除的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="bea2c-204">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="bea2c-205">OneDrive 保留和删除</span><span class="sxs-lookup"><span data-stu-id="bea2c-205">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
