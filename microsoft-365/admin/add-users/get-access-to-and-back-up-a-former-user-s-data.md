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
ms.locfileid: "51759986"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>访问并备份以往用户的数据的访问


当员工离开组织时，你可能需要访问其数据 (文档和电子邮件) 并查看、备份或向新员工提供数据。
  
    
## <a name="access-a-former-users-onedrive-documents"></a>访问以前用户的 OneDrive 文档

如果删除用户许可证但不删除帐户，可以授予自己访问用户 OneDrive 中内容的访问权限。 如果删除用户帐户，则默认情况下你有 30 天的时间访问前用户的 OneDrive 数据。 [了解如何为已删除的用户设置 OneDrive 保留。](/onedrive/set-retention) 如果此时不 [还原](/office365/admin/add-users/restore-user) 用户帐户，其 OneDrive 内容将被删除。 

若要保留以前用户的 OneDrive 文件，请首先向自己授予访问 OneDrive 的访问权限，然后移动要保留的文件。 

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

 1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

::: moniker-end

2. 选择用户。

3. 在右侧窗格中，选择 **"OneDrive"。** 在 **"获取对文件的访问权限"下**，**选择"创建指向文件的链接"。**

4. 选择链接以打开文件位置。 将文件下载到计算机，或选择"移动到"或"复制"以将其移动或复制到你自己的 OneDrive 或共享库。 

> [!NOTE]
> 一次可以移动或复制多达 500 MB 的文件和文件夹。<br/>
> 在移动或复制具有版本历史记录的文档时，只会移动最新版本。  

## <a name="revoke-admin-access-to-a-users-onedrive"></a>撤销管理员对用户的 OneDrive 的访问权限

作为全局管理员，你可以将自己访问用户的 OneDrive 中的内容，但你可能想要在不再需要它时删除你的访问权限。 

 ::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end

::: moniker range="o365-germany"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。

::: moniker-end 

2. 在左窗格中，选择"**管理中心** \> **""SharePoint"。** （你可能需要选择“**全部显示**”以查看管理中心列表）。

3. 如果显示经典 SharePoint 管理中心，请选择页面顶部的"现在打开它"以打开 SharePoint 管理中心。

4. 在左窗格中，选择"**更多功能"。**

5. 在 **"用户配置文件"下**，选择"打开 **"。**

6. 在 **"人员**"下，选择 **"管理用户配置文件"。**

7. 输入用户的名称，然后选择"查找 **"。**

8. 右键单击用户，然后选择"管理 **网站集所有者"。**

9. 删除不再需要访问用户数据的用户，然后选择"确定 **"。**

    
## <a name="access-the-outlook-data-of-a-former-user"></a>访问以前用户的 Outlook 数据

若要保存前员工的电子邮件、日历、任务和联系人，将信息导出到 Outlook 数据文件 (.pst) 。
  
1. [将前员工的电子邮件添加到](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)Outlook (如果重置用户密码，可以将其[](reset-passwords.md)设置为只知道) 
    
2. 在 Outlook 中，选择"**文件"。**
    
    ![这是功能区在 Outlook 2016 中的外观。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. 选择 **"打开 &amp; 导出** \> **导入/导出"。**
    
    ![Backstage 视图中的"导入/导出"命令](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. 选择 **"导出到文件"，** 然后选择"下一 **步"。**
    
    ![导入和导出向导中的"导出到文件"选项](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. 选择 **"Outlook 数据文件 (.pst) "，** 然后选择"下一 **步"。**
    
6. 通过选择名称或电子邮件地址（如 Mailbox - Anne Weiler 或 anne@contoso.com）选择要导出的帐户。 如果要导出帐户中的所有内容，包括邮件、日历、联系人、任务和备注，请确保选中"包括子文件夹"复选框。  
    
    > [!NOTE]
    > 可以一次导出一个帐户。 如果要导出多个帐户，在导出一个帐户后，重复这些步骤。 
  
    ![选中顶部文件夹并选中"包含子文件夹"的"导出 Outlook 数据文件"对话框](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. 选择“下一步”。
    
8. 选择 **"浏览** "以选择将 Outlook 数据文件保存到 (.pst) 。 键入  *文件名，* 然后选择" **确定"** 继续。 
    
    > [!NOTE]
    > 如果之前使用过导出，则显示上一个文件夹位置和文件名。 在选择  *"确定"之前，*  键入其他 **文件名**。 
  
9. 如果要导出到现有 Outlook 数据文件 (.pst)，请在" **选项**"下指定文件中已存在导出项目时要执行的操作。
    
10. 选择“完成”。
    
Outlook 将立即开始导出，除非已创建 (.pst) 或使用了密码保护的文件。
  
   - 如果要创建 Outlook 数据文件 (.pst) ，则可选密码可以帮助保护文件。 当出现 **"创建 Outlook 数据文件**"对话框时，在"密码"和"验证密码"框中键入密码，然后选择"确定 **"。** 在 **"Outlook 数据文件密码**"对话框中，键入 *密码*，然后选择"确定 **"。**
    
  - 如果要导出到受密码保护的现有 Outlook 数据文件 (.pst) ，请在 **"Outlook 数据文件** 密码"对话框中键入密码，然后选择"确定 **"。**
    
请参阅如何在 Outlook 2010 中将电子邮件、联系人和日历导出或备份到 [Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 文件。 
  
  
  > [!NOTE]
  > 默认情况下，您的电子邮件在 12 个月内脱机可用。 如果需要，请参阅如何 [增加脱机可用的数据](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)。
 
## <a name="give-another-user-access-to-a-former-users-email"></a>向其他用户授予对以前用户的电子邮件的访问权限 

若要向另一名员工授予对前员工的电子邮件、日历、任务和联系人的访问权限，将信息导入另一个员工的 Outlook 收件箱。

> [!NOTE]
> 还可以将 [以前用户的邮箱转换为](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) 共享邮箱，或将以前员工的电子邮件转发 [给另一名员工](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)。

  
1. 在 Outlook 中，**转到"文件** \> **""打开 &amp; "导出** \> **""导入/导出"。**
    
    这将启动导入和导出向导。
    
2. 选择 **"从另一个程序或文件导入**"，然后选择"下一 **步"。**
    
    ![导入和导出向导](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. 选择 **"Outlook 数据文件 (.pst) "，** 然后选择"下一 **步"。**
    
4. 浏览到要导入的 .pst 文件。
    
5. 在 **"选项**"下，选择如何处理重复项
    
6. 选择“下一步”。
    
7. 如果将密码分配给 Outlook 数据文件 (.pst) ，请输入密码，然后选择"确定 **"。**
    
8. 设置用于导入项目的选项。 默认设置通常不需要更改。
    
9. 选择“完成”。

> [!NOTE]
> 访问现有用户的 OneDrive 和电子邮件数据的步骤保持不变。
    
> [!TIP]
> 如果您想要导入或还原 Outlook 数据文件 (.pst) 几个项目，您可以打开 Outlook 数据文件。 然后，在导航窗格中，将 Outlook 数据文件文件夹中的项目拖动到现有的 Outlook 文件夹中。 
  
  
## <a name="related-articles"></a>相关文章
[从 Office 365 中删除以前的员工](remove-former-employee.md)

[在 OneDrive 帐户上添加和删除管理员](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[还原已删除的 OneDrive](/onedrive/restore-deleted-onedrive)
  
[OneDrive 保留和删除](/onedrive/retention-and-deletion)
