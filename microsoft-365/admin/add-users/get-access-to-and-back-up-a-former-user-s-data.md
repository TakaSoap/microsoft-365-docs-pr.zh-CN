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
description: 了解如何在员工离开组织时保留员工的文件和电子邮件。
ms.openlocfilehash: 17911e4a4551bba07d2c2ad034941bba737dcc1d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755602"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="d9961-103">访问并备份以往用户的数据的访问</span><span class="sxs-lookup"><span data-stu-id="d9961-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="d9961-104">当员工离开组织时，你可能需要访问其数据 (文档和电子邮件) 并查看、备份或向新员工提供数据。</span><span class="sxs-lookup"><span data-stu-id="d9961-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="d9961-105">访问以前用户的 OneDrive 文档</span><span class="sxs-lookup"><span data-stu-id="d9961-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="d9961-106">如果删除用户许可证但不删除帐户，可以授予自己访问用户 OneDrive 中内容的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d9961-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="d9961-107">如果删除用户帐户，则默认情况下你有 30 天的时间访问前用户的 OneDrive 数据。</span><span class="sxs-lookup"><span data-stu-id="d9961-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="d9961-108">[了解如何为已删除的用户设置 OneDrive 保留。](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="d9961-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="d9961-109">如果此时不 [还原](/office365/admin/add-users/restore-user) 用户帐户，其 OneDrive 内容将被删除。</span><span class="sxs-lookup"><span data-stu-id="d9961-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="d9961-110">若要保留以前用户的 OneDrive 文件，请首先向自己授予访问 OneDrive 的访问权限，然后移动要保留的文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9961-111">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d9961-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="d9961-112">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d9961-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="d9961-113">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d9961-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d9961-114">选择用户。</span><span class="sxs-lookup"><span data-stu-id="d9961-114">Select a user.</span></span>

3. <span data-ttu-id="d9961-115">在右侧窗格中，选择 **"OneDrive"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-115">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="d9961-116">在 **"获取对文件的访问权限"下**，**选择"创建指向文件的链接"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-116">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="d9961-117">选择链接以打开文件位置。</span><span class="sxs-lookup"><span data-stu-id="d9961-117">Select the link to open the file location.</span></span> <span data-ttu-id="d9961-118">将文件下载到计算机，或选择"移动到"或"复制"以将其移动或复制到你自己的 OneDrive 或共享库。</span><span class="sxs-lookup"><span data-stu-id="d9961-118">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9961-119">一次可以移动或复制多达 500 MB 的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9961-119">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="d9961-120">在移动或复制具有版本历史记录的文档时，只会移动最新版本。</span><span class="sxs-lookup"><span data-stu-id="d9961-120">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="d9961-121">撤销管理员对用户的 OneDrive 的访问权限</span><span class="sxs-lookup"><span data-stu-id="d9961-121">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="d9961-122">作为全局管理员，你可以将自己访问用户的 OneDrive 中的内容，但你可能想要在不再需要它时删除你的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d9961-122">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9961-123">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9961-123">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9961-124">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9961-124">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9961-125">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9961-125">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="d9961-126">在左窗格中，选择"**管理中心** \> **""SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-126">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="d9961-127">（你可能需要选择“**全部显示**”以查看管理中心列表）。</span><span class="sxs-lookup"><span data-stu-id="d9961-127">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="d9961-128">如果显示经典 SharePoint 管理中心，请选择页面顶部的"现在打开它"以打开 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9961-128">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="d9961-129">在左窗格中，选择"**更多功能"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-129">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="d9961-130">在 **"用户配置文件"下**，选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-130">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="d9961-131">在 **"人员**"下，选择 **"管理用户配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-131">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="d9961-132">输入用户的名称，然后选择"查找 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-132">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="d9961-133">右键单击用户，然后选择"管理 **网站集所有者"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-133">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="d9961-134">删除不再需要访问用户数据的用户，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-134">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="d9961-135">访问以前用户的 Outlook 数据</span><span class="sxs-lookup"><span data-stu-id="d9961-135">Access the Outlook data of a former user</span></span>

<span data-ttu-id="d9961-136">若要保存前员工的电子邮件、日历、任务和联系人，将信息导出到 Outlook 数据文件 (.pst) 。</span><span class="sxs-lookup"><span data-stu-id="d9961-136">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="d9961-137">[将前员工的电子邮件添加到](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)Outlook (如果重置用户密码，可以将其[](reset-passwords.md)设置为只知道) </span><span class="sxs-lookup"><span data-stu-id="d9961-137">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="d9961-138">在 Outlook 中，选择"**文件"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-138">In Outlook, select **File**.</span></span>
    
    ![这是功能区在 Outlook 2016 中的外观。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="d9961-140">选择 **"打开 &amp; 导出** \> **导入/导出"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-140">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Backstage 视图中的"导入/导出"命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="d9961-142">选择 **"导出到文件"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-142">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![导入和导出向导中的"导出到文件"选项](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="d9961-144">选择 **"Outlook 数据文件 (.pst) "，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-144">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="d9961-145">通过选择名称或电子邮件地址（如 Mailbox - Anne Weiler 或 anne@contoso.com）选择要导出的帐户。</span><span class="sxs-lookup"><span data-stu-id="d9961-145">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="d9961-146">如果要导出帐户中的所有内容，包括邮件、日历、联系人、任务和备注，请确保选中"包括子文件夹"复选框。 </span><span class="sxs-lookup"><span data-stu-id="d9961-146">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d9961-147">可以一次导出一个帐户。</span><span class="sxs-lookup"><span data-stu-id="d9961-147">You can export one account at a time.</span></span> <span data-ttu-id="d9961-148">如果要导出多个帐户，在导出一个帐户后，重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d9961-148">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![选中顶部文件夹并选中"包含子文件夹"的"导出 Outlook 数据文件"对话框](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="d9961-150">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d9961-150">Select **Next**.</span></span>
    
8. <span data-ttu-id="d9961-151">选择 **"浏览** "以选择将 Outlook 数据文件保存到 (.pst) 。</span><span class="sxs-lookup"><span data-stu-id="d9961-151">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="d9961-152">键入  *文件名，* 然后选择" **确定"** 继续。</span><span class="sxs-lookup"><span data-stu-id="d9961-152">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d9961-153">如果之前使用过导出，则显示上一个文件夹位置和文件名。</span><span class="sxs-lookup"><span data-stu-id="d9961-153">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="d9961-154">在选择  *"确定"之前，*  键入其他 **文件名**。</span><span class="sxs-lookup"><span data-stu-id="d9961-154">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="d9961-155">如果要导出到现有 Outlook 数据文件 (.pst)，请在" **选项**"下指定文件中已存在导出项目时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d9961-155">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="d9961-156">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="d9961-156">Select **Finish**.</span></span>
    
<span data-ttu-id="d9961-157">Outlook 将立即开始导出，除非已创建 (.pst) 或使用了密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-157">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="d9961-158">如果要创建 Outlook 数据文件 (.pst) ，则可选密码可以帮助保护文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-158">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="d9961-159">当出现 **"创建 Outlook 数据文件**"对话框时，在"密码"和"验证密码"框中键入密码，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-159">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="d9961-160">在 **"Outlook 数据文件密码**"对话框中，键入 *密码*，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-160">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="d9961-161">如果要导出到受密码保护的现有 Outlook 数据文件 (.pst) ，请在 **"Outlook 数据文件** 密码"对话框中键入密码，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-161">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="d9961-162">请参阅如何在 Outlook 2010 中将电子邮件、联系人和日历导出或备份到 [Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-162">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="d9961-163">默认情况下，您的电子邮件在 12 个月内脱机可用。</span><span class="sxs-lookup"><span data-stu-id="d9961-163">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="d9961-164">如果需要，请参阅如何 [增加脱机可用的数据](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。</span><span class="sxs-lookup"><span data-stu-id="d9961-164">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="d9961-165">向其他用户授予对以前用户的电子邮件的访问权限</span><span class="sxs-lookup"><span data-stu-id="d9961-165">Give another user access to a former user's email</span></span> 

<span data-ttu-id="d9961-166">若要向另一名员工授予对前员工的电子邮件、日历、任务和联系人的访问权限，将信息导入另一个员工的 Outlook 收件箱。</span><span class="sxs-lookup"><span data-stu-id="d9961-166">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="d9961-167">还可以将 [以前用户的邮箱转换为](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 共享邮箱，或将以前员工的电子邮件转发 [给另一名员工](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="d9961-167">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="d9961-168">在 Outlook 中，**转到"文件** \> **""打开 &amp; "导出** \> **""导入/导出"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-168">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="d9961-169">这将启动导入和导出向导。</span><span class="sxs-lookup"><span data-stu-id="d9961-169">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="d9961-170">选择 **"从另一个程序或文件导入**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-170">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![导入和导出向导](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="d9961-172">选择 **"Outlook 数据文件 (.pst) "，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-172">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="d9961-173">浏览到要导入的 .pst 文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-173">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="d9961-174">在 **"选项**"下，选择如何处理重复项</span><span class="sxs-lookup"><span data-stu-id="d9961-174">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="d9961-175">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d9961-175">Select **Next**.</span></span>
    
7. <span data-ttu-id="d9961-176">如果将密码分配给 Outlook 数据文件 (.pst) ，请输入密码，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9961-176">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="d9961-177">设置用于导入项目的选项。</span><span class="sxs-lookup"><span data-stu-id="d9961-177">Set the options for importing items.</span></span> <span data-ttu-id="d9961-178">默认设置通常不需要更改。</span><span class="sxs-lookup"><span data-stu-id="d9961-178">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="d9961-179">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="d9961-179">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="d9961-180">访问现有用户的 OneDrive 和电子邮件数据的步骤保持不变。</span><span class="sxs-lookup"><span data-stu-id="d9961-180">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="d9961-181">如果您想要导入或还原 Outlook 数据文件 (.pst) 几个项目，您可以打开 Outlook 数据文件。</span><span class="sxs-lookup"><span data-stu-id="d9961-181">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="d9961-182">然后，在导航窗格中，将 Outlook 数据文件文件夹中的项目拖动到现有的 Outlook 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d9961-182">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="d9961-183">相关文章</span><span class="sxs-lookup"><span data-stu-id="d9961-183">Related articles</span></span>
[<span data-ttu-id="d9961-184">从 Office 365 中删除以前的员工</span><span class="sxs-lookup"><span data-stu-id="d9961-184">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="d9961-185">在 OneDrive 帐户上添加和删除管理员</span><span class="sxs-lookup"><span data-stu-id="d9961-185">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="d9961-186">还原已删除的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9961-186">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="d9961-187">OneDrive 保留和删除</span><span class="sxs-lookup"><span data-stu-id="d9961-187">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
