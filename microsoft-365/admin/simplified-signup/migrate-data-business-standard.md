---
title: 将数据迁移到 Microsoft 365 商业标准版订阅
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 将Outlook、OneDrive和Teams数据迁移到Microsoft 365 商业标准版
ms.openlocfilehash: 7868212bbd3d96e71d606fb3df0071018ded1c31
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783394"
---
# <a name="migrate-data-to-my-microsoft-365-business-standard-subscription"></a>将数据迁移到 Microsoft 365 商业标准版订阅

按照本文中的步骤将OneDrive、Outlook和Teams数据移动到Microsoft 365 商业标准版订阅。

> [!IMPORTANT]
> 你仍然可以将数据保留在个人帐户中。 创建新的业务电子邮件帐户并迁移数据后，个人帐户中的数据将不会过期。 可以将所有数据移动到新的业务帐户，也可以移动部分数据。 例如，可以将工作文档移动到业务帐户，但将个人家庭照片保留在个人帐户中。

## <a name="move-files-to-onedrive-for-business"></a>将文件移到业务OneDrive

本部分介绍如何将存储在Microsoft 365个人帐户中的文件移动到Microsoft 365业务帐户。 将两个OneDrive帐户同步到设备后，可以轻松地在两个OneDrive文件夹之间拖放文件。

1. 在Windows通知区域中选择OneDrive白云图标，并确保OneDrive个人帐户同步到设备。

    :::image type="content" source="../../media/ssu-onedrive-icons.png" alt-text="屏幕截图：在Windows通知区域中选择白云图标":::

    > [!NOTE]
    > 可能需要选择通知区域旁边的 **“显示隐藏图标”** 箭头才能查看OneDrive图标。 如果该图标未显示在通知区域中，则OneDrive可能不会运行。 选择 **“开始”**，在搜索框中键入OneDrive，然后在搜索结果中选择OneDrive。

2. 若要添加新的业务帐户，请选择 **“帮助& 设置** > **设置**。

    :::image type="content" source="../../media/ssu-onedrive-help-settings.png" alt-text="屏幕截图：选择“帮助& 设置”以添加帐户":::

3. 在 **设置** 中，选择 **AccountAdd** >  帐户。

4. 启动OneDrive安装程序时，输入新的业务帐户，然后选择 **“登录**”。

    :::image type="content" source="../../media/ssu-setup-onedrive.png" alt-text="屏幕截图：在“设置OneDrive页上输入电子邮件地址":::

    > [!NOTE]
    > 如果之前尚未使用当前Microsoft 365个人帐户设置OneDrive，请按照上述步骤在设备上设置个人帐户并同步文件，然后再转到后续步骤。

### <a name="drag-and-drop-files-in-onedrive"></a>在OneDrive中拖放文件

将Microsoft 365个人帐户和业务帐户同步到设备后，现在可以将文件从个人OneDrive文件夹移动到新业务OneDrive文件夹。

1. 在文件资源管理器中，打开包含文件的同步OneDrive文件夹。

2. 选择所需的文件并将其从OneDrive个人文件夹拖动到新的OneDrive业务文件夹。

    :::image type="content" source="../../media/ssu-onedrive-files-to-work-folder.png" alt-text="屏幕截图：将文件拖放到新的业务OneDrive文件夹":::

### <a name="notes-about-moving-files-from-onedrive-personal-to-onedrive-for-work"></a>有关将文件从个人OneDrive移动到工作OneDrive的说明

- 如果要移动大量文件，建议将文件分批移动，每个文件不超过 100 个。

- 从OneDrive个人移动到OneDrive工作的文件被识别为新文件，因此，这些文件不会保留元数据详细信息，例如“修改”和“修改者”。

- 如果之前在OneDrive中共享文件，则需要在新OneDrive中再次共享这些文件，以便在移动后进行工作。 此外，共享这些文件后，建议从OneDrive中删除原始文件。 这样，用户将无法引用之前与他们共享的文件的过期副本。

## <a name="step-set-up-outlook-for-email"></a>观看：设置 Outlook，以使用电子邮件功能

1. 在 Windows“开始”菜单上，搜索并选择“Outlook”。

    （如果使用的是 Mac，请从工具栏打开 Outlook 或使用 Finder 进行查找。）

    如果刚刚安装了 Outlook，请在欢迎页面上选择“**下一步**”。

2. 选择“**文件**”\>“**信息**”\>“**添加帐户**”。

3. 输入你的 Microsoft 电子邮件地址并选择“**连接**”。

## <a name="watch-set-up-outlook-for-email"></a>观看：设置 Outlook，以使用电子邮件功能

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
请参阅[设置 Outlook，使用电子邮件功能](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)，了解有关详细信息。
  
### <a name="import-email"></a>使用 Outlook

如果通过另一电子邮件帐户使用 Outlook，可将之前的电子邮件、日历和联系人导入新的 Microsoft 帐户。
  
1. **导出旧的电子邮件**

    在 Outlook 中，选择“**文件**”\>“**打开并导出**”\>“**导入/导出**”。

    选择“**导出到文件**”，然后按照以下步骤导出 Outlook 数据文件 (.pst) 和任何子文件夹。

2. **导入旧的电子邮件**

    在 Outlook 中，再次选择“**文件**”\>“**打开并导出**”\>>“**导入/导出**”。

    这一次，选择“**从另一程序或文件导入**”并按照以下步骤导入“导出旧的电子邮件”时创建的备份文件。

### <a name="watch-import-and-redirect-email"></a>观看：导入和重定向电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
请参阅[使用 Outlook 导入电子邮件](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)，了解有关详细信息。

还可以使用 Exchange 管理中心导入每个人的电子邮件。 有关详细信息，请参阅[迁移多个电子邮件帐户](/Exchange/mailbox-migration/mailbox-migration)。

## <a name="move-data-from-your-personal-microsoft-teams-account-to-new-teams-for-work-account"></a>将数据从个人Microsoft Teams帐户移动到工作帐户的新Teams

1. 打开 Microsoft Teams，选择个人资料图标，然后 **添加工作或学校帐户**。

2. 按照步骤将新帐户添加到Teams进行工作。 有关详细信息，请查看[登录并开始使用Teams](https://support.microsoft.com/office/sign-in-and-get-started-with-teams-6723dc43-dbc0-46e6-af49-8a2d1c5cb937)。

### <a name="access-teams-chats"></a>访问Teams聊天

开始将Teams与新工作帐户配合使用时，不会迁移数据。 查看旧聊天的最佳方式是并排打开旧Teams帐户和新工作帐户。 为此，可选择Teams右上角的 ME 图标并选择要打开的帐户。 可以开始将Teams与同事一起使用新工作帐户。 请务必告知与你聊天的其他用户，开始使用工作帐户的新Teams与你联系。

### <a name="microsoft-teams-meetings"></a>Microsoft Teams会议

设置新的Microsoft Teams帐户后，可以在Teams日历中重新创建会议。 请记住删除旧Teams帐户中的原始会议。 这将允许你访问更丰富的功能 -例如，日程安排时的日历可用性，以及记录会议的功能。 只能从自己的Teams日历中删除会议，因此请确保你让与你会面的人员知道你将重新创建会议。 当你转换为为会议使用新的Teams帐户时，如果应参加会议的人员缺失，请与他们联系，以确保他们没有加入旧的会议链接。

### <a name="migrating-contacts"></a>迁移联系人

若要从个人Teams帐户迁移联系人，请查找联系人的电子邮件地址，并将用户添加到新的Teams帐户中进行工作。

## <a name="related-content"></a>相关内容

[将电子邮件从 Gmail 或其他电子邮件提供商导入或迁移到Microsoft 365](../setup/migrate-email-and-contacts-admin.md)

<!--## Download desktop apps

Download Microsoft 365 apps by following the steps in this article.

1. Open any of your Microsoft 365 apps, like Word, Excel or PowerPoint, select your profile icon and then **Sign in with a different account**. Follow the steps and choose **Next** to set up Outlook.

2. Open Outlook, enter your new email address, and select **Connect**. Follow the steps and choose **Next** to set up OneDrive.

3. Select the OneDrive cloud icon from your taskbar and follow the steps to move your files to your new OneDrive for Business folder. Select **Next** to set up Microsoft Teams.

4. Open Teams, select your profile icon, and then **Add work or school account**. Follow the steps to add your new account to Teams. Select **I'm done** when Teams is set up.-->

<!--## Next steps

## Accept a new invitation to change your personal email account to a business email account

Your email looks like this to set up your business user account. When you get this email, you'll have to complete a few steps before you can start using your new user account.

(**Add screenshot here**)

1. From the invitation email, select **Accept**.

2. On the **Join Microsoft 365 Business...** page, select **Next**.

3. On the Sign up page, make sure you use the email used in the invitation email, and create a password. Select **Create account**.

3. Choose **Accept** on the **Terms and Conditions** page.

1. On the Review permissions page, choose **Accept**.

1. On the Welcome to Microsoft 365 page, you can download Office desktop and mobile apps, and set up OneDrive.-->