---
title: 从 Google Workspace 迁移业务电子邮件和日历
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将电子邮件、联系人和日历从 Google Workspace 迁移到 Microsoft 365 商业版。
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794582"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>从 Google Workspace 迁移业务电子邮件和日历

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

可以使用管理员运行从 Google Workspace 迁移到 Exchange Online。 您可以一次迁移所有邮件，也可以分阶段迁移邮件。 以下步骤显示如何一次迁移电子邮件数据。 有关详细信息，请参阅["执行 G 套件迁移"。](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

迁移过程需要几个步骤，可能需要几个小时到几天的时间，具体取决于要迁移的数据量。

## <a name="try-it"></a>试一试！

### <a name="create-a-google-service-account"></a>创建 Google 服务帐户

1. 使用 Chrome 浏览器，登录 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com) 
1. 在新建的选项卡或窗口中，导航到" [服务帐户"](https://console.developers.google.com/iam-admin/serviceaccounts) 页。 
1. 选择 **"创建项目**"，命名该项目，然后选择"**创建"。** 
1. 选择 **"创建服务帐户**"，输入名称，选择 **"创建**，然后 **完成"。** 
1. 打开" **操作** "菜单， **选择"编辑**"，然后记下唯一 ID。 此过程稍后将需要此 ID。 
1. 打开 **"显示域范围的委派"** 部分。 
1. 选择 **"启用 G Suite 域范围委派**"，输入同意屏幕的产品名称，然后选择"**保存"。** 

    > [!NOTE]
> 迁移过程不会使用产品名称，但需要将其保存在对话框中。     

1. 再次打开 **"操作**"菜单，然后选择"**创建密钥"。** 
1. 选择 **JSON，** 然后 **创建**。 

     私钥将保存到你的设备的下载文件夹中。
 
1. 选择“**关闭**”。 

### <a name="enable-api-usage-for-the-project"></a>为项目启用 API 用法

1. 导航到 [API 页面](https://console.developers.google.com/apis/library)。 
1. 在搜索栏中，输入 **Gmail API。**
1. 选择它，然后选择"**启用"。**
1. 对 Google 日历 API 和联系人 API 重复此过程。 

### <a name="grant-access-to-the-service-account"></a>授予对服务帐户的访问权限

1. 返回到 Google Workspace 管理控制台。 
1. 选择 **"** 安全性"，向下滚动并打开 **API 控件**。 
1. 向下滚动并选择 **"管理域范围的委派"。**
1. 选择 **"添加新** "，然后输入之前记下的客户端 ID。
1. 然后输入 Google API 的 OAuth 范围。 可在步骤 5 [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 以下选项：

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. 选择 **"授权"。** 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>为发送到 Microsoft 365 的邮件创建子域

1. 返回到 **Google Workspace 管理** 控制台。
1. 选择 **"域****"，"** 管理域"，然后 **添加域别名**。 
1. 输入域别名，如 `m365.contoso.com` 。
1. 然后选择 **"继续"并验证域所有权**。 

    域验证通常只需几分钟，但最多可能需要 48 小时。

1. 转到 [Microsoft 365 管理中心](https://admin.microsoft.com)。
1. 在 **Microsoft 365** 管理中心的左侧导航中，选择"显示所有、设置、域"，然后 **添加域**。  
1. 输入之前创建的子域，然后选择"**使用此域"。** 
1. 若要连接域，请选择"继续 **"。** 
1. 向下滚动并记下 MX 记录、CNAME 记录和 TXT 记录。 
1. 返回到 **Google 管理控制台**。
1. 选择 **"域**"，**选择"管理域****"，"验证详细信息**"，然后 **"管理域"。** 
1. 在左侧导航中，选择 **DNS** 并向下滚动到 **自定义资源记录**。 
1. 打开记录类型下拉列表并选择 **MX，** 输入或复制并粘贴之前记录的 MX 记录信息，然后选择"**添加"。** 
1. 对 CNAME 记录和 TXT 记录重复此过程。 

    可能需要一些时间，这些更改生效。  

1. 返回到你在 **Microsoft 365** 管理中心中离开的地方，然后选择"**继续"。** 

现在，你的域已设置。  

### <a name="create-email-aliases-in-microsoft-365"></a>在 Microsoft 365 中创建电子邮件别名

在开始迁移之前，需要为具有新子域的用户创建电子邮件别名。 

1. 若要开始下一步，请在Microsoft 365 管理中心的"添加域"向导中，选择"**转到活动用户"。** 
1. 选择用户，然后管理 **用户名和电子邮件**。 
1. 从 **"** 域"下拉列表中，选择之前创建的子域。 
1. 输入用户名，选择 **"添加****"，"保存更改**"，然后关闭窗口。 

    为每个用户重复此过程。 

### <a name="start-the-migration-process"></a>启动迁移过程

完成后，即可进行迁移。 

1. 在 **Microsoft 365** 管理中心的左侧导航中，向下滚动到管理 **中心**，然后选择 **Exchange。** 
1. 在 **"收件人"** 下，选择 **"迁移**"，选择 **"新建****"，"** 迁移到 Exchange Online"，选择 **"G 套件迁移**"，然后选择"**下一步"。** 
1. 创建包含要迁移的邮箱列表的 CSV 文件。 确保文件采用以下格式： 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      有关详细信息 [，请参阅](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)aka.ms/GoogleWorkspaceMigration。 

1. 选择 **"文件**"，导航到 CSV 文件，选择它，选择"**打开**"，然后选择"**下一步"。** 
1. 验证要用于测试的管理员电子邮件地址。 
1. 选择 **"** 文件"，导航到之前创建的 JSON 文件 (通常位于计算机上下载文件夹中，) ，选择"打开"，然后选择"下一 **步"。**  
1. 在"新建迁移批处理 **名称"字段中输入名称**。
1. 输入在"目标传递域"字段中创建的 **子域，****选择"下** 一步"，然后选择"**新建"。** 
1. 保存信息后，选择"确定 **"。** 

    现在可以查看迁移的状态。 

1. 经过一段时间后，根据要迁移的用户数，选择"刷新 **"。** 
1. 在状态更改为"已同步 **"** 后，选择 **"完成此迁移批处理**"，然后选择"**是"。** 
1. 该过程完成后，状态将更改为 **"已完成"。** 
1. 如果需要，可以选择"查看 **详细信息** "，了解有关迁移的详细信息。 
1. 选择“**关闭**”。 
1. 打开 Outlook 以验证来自 Google Workspace 的所有电子邮件已成功迁移。
也可以对日历项目和联系人重复此操作。