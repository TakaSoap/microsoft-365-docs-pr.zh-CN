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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: 了解当某人离开你的组织时，如何保留员工的文件和电子邮件。
ms.openlocfilehash: f7132b927c05b8339f20b268b48847291e9c710e
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140629"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>访问并备份以往用户的数据的访问

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理员中心正在更改。 如果你的体验与此处提供的详细信息不匹配，请参阅[关于新的 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end


当员工离开组织时，您可能希望访问其数据（文档和电子邮件），并对其进行查看、备份或将其提供给新员工。
  
    
## <a name="access-a-former-users-onedrive-documents"></a>访问以前的用户的 OneDrive 文档

如果删除用户的许可证，但不删除该帐户，则可以为自己提供对用户的 OneDrive 中的内容的访问权限。 如果您删除用户帐户，默认情况下您有30天的时间来访问以前的用户的 OneDrive 数据。 [了解如何为已删除的用户设置 OneDrive 保留](/onedrive/set-retention)。 如果您不在这段时间内[还原用户帐户](/office365/admin/add-users/restore-user)，其 OneDrive 内容将被删除。 

若要保留以前的用户的 OneDrive 文件，请先授予自己对其 OneDrive 的访问权限，然后移动要保留的文件。 

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。  
    
2. 选择一个用户。

3. 在右侧窗格中，选择 " **OneDrive**"。 在 "**获取对文件的访问权限**" 下，选择 "**创建指向文件的链接**"。

4. 选择要打开文件位置的链接。 将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。 

> [!NOTE]
> 您可以一次移动或复制最多 500 MB 的文件和文件夹。<br/>
> 移动或复制具有版本历史记录的文档时，仅移动最新版本。  

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。  

2. 选择一个用户。

3. 在右侧窗格中，展开 " **OneDrive 设置**"，然后在 "**访问**" 下，选择 "**访问文件**"。

4. 选择要打开文件位置的链接。 将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。 

> [!NOTE]
> 您可以一次移动或复制最多 500 MB 的文件和文件夹。<br/>
> 移动或复制具有版本历史记录的文档时，仅移动最新版本。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。 

2. 选择一个用户。

3. 在右侧窗格中，展开 " **OneDrive 设置**"，然后在 "**访问**" 下，选择 "**访问文件**"。

4. 选择要打开文件位置的链接。 将文件下载到您的计算机上，或者选择 "**移动到**" 或 "**复制到**" 将它们移动或复制到您自己的 OneDrive 或共享库。  

> [!NOTE]
> 您可以一次移动或复制最多 500 MB 的文件和文件夹。<br/>
> 移动或复制具有版本历史记录的文档时，仅移动最新版本。  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>撤销对用户的 OneDrive 的管理员访问权限

作为全局管理员，你可以为自己提供对用户的 OneDrive 中的内容的访问权限，但您可能想要在不再需要时删除您的访问权限。 

::: moniker range="o365-worldwide"

1. 以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理员中心</a>。 

    如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。

::: moniker-end

::: moniker range="o365-germany"

1. 以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理员中心</a>。

    如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。

::: moniker-end

::: moniker range="o365-21vianet"

1. 以全局管理员或 SharePoint 管理员身份登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理员中心</a>。

    如果您收到一条消息，表明您没有访问管理中心的权限，则您的组织中没有管理员权限。

::: moniker-end

2. 在左窗格中，选择 "**管理中心** \> " " **SharePoint**"。 （你可能需要选择“**全部显示**”以查看管理中心列表）。

3. 如果看到经典 SharePoint 管理中心，请选择页面顶部的“**立即打开**”，打开新的 SharePoint 管理中心。

4. 在左窗格中，选择 "**更多功能**"。

5. 在 "**用户配置文件**" 下，选择 "**打开**"。

6. 在 "**人员**" 下，选择 "**管理用户配置文件**"。

7. 输入用户的名称，然后选择 "**查找**"。

8. 右键单击该用户，然后选择 "**管理网站集所有者**"。

9. 删除不再需要访问用户数据的人员，然后选择 **"确定"**。

    
## <a name="access-the-outlook-data-of-a-former-user"></a>访问以前用户的 Outlook 数据

若要保存以前员工的电子邮件、日历、任务和联系人，请将信息导出到 Outlook 数据文件（.pst）。
  
1. [将前员工的电子邮件添加](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)到你的 Outlook （如果[重置用户的密码](reset-passwords.md)，则可以将其设置为仅你知道的内容。）
    
2. 在 Outlook 中，选择 "**文件**"。
    
    ![这就是功能区在 Outlook 2016 中的外观。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. 选择 **" &amp;打开导出** \> **导入/导出**"。
    
    ![Backstage 视图中的导入/导出命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. 选择 "**导出到文件**"，然后选择 "**下一步**"。
    
    !["导入和导出向导" 中的 "导出到文件" 选项](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. 选择 " **Outlook 数据文件（.pst）**"，然后选择 "**下一步**"。
    
6. 选择要导出的帐户，方法是选择名称或电子邮件地址，例如邮箱-Anne Weiler 或 anne@contoso.com。 如果要导出帐户中的所有内容（包括邮件、日历、联系人、任务和便笺），请确保选中 "**包含子文件夹**" 复选框。 
    
    > [!NOTE]
    > 您可以一次导出一个帐户。 如果要在导出一个帐户后导出多个帐户，请重复这些步骤。 
  
    !["导出 Outlook 数据文件" 对话框，其中选中了 top 文件夹并包含选中的子文件夹](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. 选择“**下一步**”。
    
8. 选择 "**浏览**" 以选择保存 Outlook 数据文件（.pst）的位置。 键入文件名 *，然后*选择 **"确定"** 以继续。 
    
    > [!NOTE]
    > 如果您以前使用过导出，则将显示上一个文件夹位置和文件名。 在选择 **"确定"** 之前键入*其他文件名*。 
  
9. 如果要导出到现有 Outlook 数据文件 (.pst)，请在" **选项**"下指定文件中已存在导出项目时要执行的操作。
    
10. 选择“完成”****。
    
如果不创建新的 Outlook 数据文件（.pst）或使用受密码保护的文件，Outlook 将立即开始导出。
  
   - 如果要创建 Outlook 数据文件（.pst），可选密码可帮助保护文件。 在出现 **"创建 Outlook 数据文件**" 对话框时，在 "**密码**" 和 "**验证密码**" 框中键入*密码*，然后选择 **"确定"**。 在 " **Outlook 数据文件密码**" 对话框中，键入*密码*，然后选择 **"确定"**。
    
  - 如果要导出到受密码保护的现有 Outlook 数据文件（.pst）中，请在 " **Outlook 数据文件密码**" 对话框中，键入*密码*，然后选择 **"确定"**。
    
请参阅如何在 Outlook 2010 中[将电子邮件、联系人和日历导出或备份到 outlook .pst 文件](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)。 
  
  
  > [!NOTE]
  > 默认情况下，你的电子邮件在12个月内可脱机使用。 如果需要，请参阅如何[增加可脱机使用的数据](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。
 
## <a name="give-another-user-access-to-a-former-users-email"></a>向另一个用户授予对以前用户的电子邮件的访问权限 

若要将前一个员工的电子邮件、日历、任务和联系人的访问权限授予另一个员工，请将该信息导入到另一个员工的 Outlook 收件箱。

> [!NOTE]
> 您还可以[将前一个用户的邮箱转换为共享邮箱，或将](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)[以前的员工的电子邮件转发给另一个员工](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。

  
1. 在 Outlook 中，转到 "**文件** \> ** &amp;打开导出** \> **导入/导出**"。
    
    这将启动 "导入和导出向导"。
    
2. 选择 "**从另一程序或文件导入**"，然后选择 "**下一步**"。
    
    ![导入和导出向导](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. 选择 " **Outlook 数据文件（.pst）**"，然后选择 "**下一步**"。
    
4. 浏览到要导入的 .pst 文件。
    
5. 在 "**选项**" 下，选择要处理重复项的方式
    
6. 选择“**下一步**”。
    
7. 如果为 Outlook 数据文件（.pst）分配了密码，请输入密码，然后选择 **"确定"**。
    
8. 设置用于导入项目的选项。 通常不需要更改默认设置。
    
9. 选择“完成”****。

> [!NOTE]
> 访问现有用户的 OneDrive 和电子邮件数据的步骤保持相同。
    
> [!TIP]
> 如果只想导入或还原 Outlook 数据文件（.pst）中的几个项目，则可以打开 Outlook 数据文件。 然后，在导航窗格中，将 "Outlook 数据文件" 文件夹中的项目拖到现有的 Outlook 文件夹中。 
  
  
## <a name="related-articles"></a>相关文章
[从 Office 365 中删除以前的员工](remove-former-employee.md)

[在 OneDrive 帐户上添加和删除管理员](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[还原已删除的 OneDrive](/onedrive/restore-deleted-onedrive)
  
[OneDrive 保留和删除](/onedrive/retention-and-deletion)
  
