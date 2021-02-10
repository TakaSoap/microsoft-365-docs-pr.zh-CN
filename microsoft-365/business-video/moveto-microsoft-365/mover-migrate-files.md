---
title: '将 Google 文件迁移到 Microsoft 365 商业版 '
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
description: 了解如何使用 Mover 将 Google 文件迁移到 Microsoft 365 商业版。
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166155"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>将 Google 文件迁移到 Microsoft 365 商业版 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

迁移到 Microsoft 365 商业版时，需要从 Google Drive 迁移文件。 可以使用 Mover 应用从个人驱动器和共享驱动器移动文件。 有关详细信息，请参阅 [Mover 云迁移](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)。

> [!NOTE]
> Mover 将创建文件副本，将副本移动到 Microsoft 365 商业版。 原始文件也将留在 Google Drives 中。

## <a name="before-you-start"></a>准备工作

所有用户都应已登录到 Microsoft 365 商业版并设置其 OneDrive for Business。 为此，请转到 [office.com，使用](https://office.com)Microsoft 365 商业版凭据登录，然后选择 OneDrive。

## <a name="try-it"></a>试一试！

### <a name="install-mover"></a>安装 Mover

1. 登录 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)

1. 选择 **应用**  >  **Google 工作区市场应用**  >  **将应用添加到域安装列表**。

1. 搜索 Mover 并选择它。

1. 选择 **"域安装**"，然后 **继续**。

1. 查看权限，选中复选框以同意条款，然后选择"允许"，选择"下一步"，然后选择"**完成"。**

### <a name="create-connectors-and-run-the-migration"></a>创建连接器并运行迁移

1. 返回到 **Google Workspace Marketplace 应用**。
1. 刷新浏览器，然后选择 **Mover** 应用。
1. 向下滚动并选择通用导航链接。
1. Select **Authorize New Connector，** locate **G Suite (Admin) ，** and choose **Authorize**.
1. 如果需要 **，请更改** 显示名称，然后选择"授权 **"。**
1. 选择 Google 管理员帐户，查看权限，然后选择"**允许"。**

    Mover 显示发现的团队驱动器数和用户驱动器数。 

1. 在 **"选择目标**"下，**选择"授权新连接器**"，找到 **Office 365，** 然后选择"**授权"。**
1. 若要向 Azure Active Directory 中的 Mover 应用授予权限， [请导航到](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。
1. Select **Office 365 Mover**， **Permissions，** **Grant admin consent for your company.**
1. 选择您的帐户，查看权限，然后选择"接受 **"。**
1. 选择 **"** 属性"并验证 **用户分配是否必需？** 已打开。
1. 返回到 Mover 应用，更改显示名称，如果需要，请选择"授权 **"，然后选择** Microsoft 管理员帐户。

    Mover 将通知你发现的 SharePoint Online (或 SPO) 用户的数量。
1. 选择 **"继续迁移设置**"， **选择"添加用户"，** 然后 **自动发现并添加用户**。

    Mover 应用将尝试将驱动器从 Google 中的源路径映射到 Microsoft 365 中的目标路径。 

    如果驱动器未自动映射，请将其目标路径添加到 CSV 文件，稍后我们将使用该路径将共享驱动器迁移到 SharePoint 文档库。 

1. 在这种情况下，我们添加了一个称为"迁移文件"的 SharePoint 网站，并记下了文档页的 URL。 
1. 然后，我们使用源路径、目标路径和标记的格式创建了 CSV 文件。 

    有关详细信息 [，请参阅](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)aka.ms/movercsv。

    添加目标路径 URL 时，删除共享文档之后的所有内容。 例如，此完整 URL 无效： `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    将其更改为：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV 文件准备就绪后，选择" **迁移** 操作 **"，"** 添加到迁移 **"，选择要上载的文件**。
1. 导航到 CSV 文件，选择它，然后选择"打开 **"。**
1. 选择要迁移其文件的用户驱动器，然后选择"**开始迁移用户"。**
1. 查看迁移信息，选择何时开始迁移，同意条款和条件，然后选择"**继续"。** 

Mover 应用将在迁移过程完成时通知你。
