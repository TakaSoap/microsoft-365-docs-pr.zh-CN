---
title: '将 Google 文件迁移到 Microsoft 365 for Business '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 了解如何使用 Mover 将 Google Microsoft 365迁移到企业。
ms.openlocfilehash: 4bec723d024468f76bdfcc60934eb42c445fe0f5
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825578"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>将 Google 文件迁移到 Microsoft 365 for Business 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

当您迁移到 Microsoft 365 for business 时，您需要将文件从 Google 云端硬盘。 可以使用 Mover 应用从个人驱动器和共享驱动器移动文件。 有关详细信息，请参阅 [Mover 云迁移](/sharepointmigration/mover-plan-migration)。

> [!NOTE]
> Mover 将创建文件副本，将副本移动到Microsoft 365中。 原始文件也将留在 Google Drives 中。

## <a name="before-you-start"></a>准备工作

所有用户都应登录到企业Microsoft 365并设置其OneDrive for Business。 为此，请转到"office.com"[](https://office.com)，使用 Microsoft 365 企业凭据登录，然后选择"OneDrive"。

## <a name="try-it"></a>试一试！

### <a name="install-mover"></a>安装 Mover

1. 登录到 Google Workspace 管理控制台，[admin.google.com。](https://admin.google.com)

1. Choose **AppsGoogle** >  **Workspace Marketplace appsAdd** >  **app to Domain Install list**.

1. 搜索 Mover 并选择它。

1. 选择 **"域安装"**，然后选择" **继续"**。

1. 查看权限，选中复选框以同意条款，然后选择"允许"，**选择"下** 一步"，然后选择"完成 **"**。

### <a name="create-connectors-and-run-the-migration"></a>创建连接器并运行迁移

1. 返回到 **Google Workspace Marketplace 应用**。
1. 刷新浏览器，然后选择 **Mover** 应用。
1. 向下滚动并选择通用导航链接。
1. 选择 **"授权新连接器"**，找到 **"G Suite (Admin)**"，然后选择"授权 **"**。
1. 如果需要 **，请更改** 显示名称，然后选择"授权 **"**。
1. 选择 Google 管理员帐户，查看权限，然后选择"允许 **"**。

    Mover 显示发现的团队驱动器和用户驱动器的数量。 

1. 在 **"选择目标**"下，选择"**授权新** 连接器"，**Office 365**"授权 **"**。
1. 若要在你的应用中向 Mover 应用授予Azure Active Directory，[请导航到](https://aka.ms/Office365MoverAuth) aka.ms/Office365MoverAuth。
1. 选择 **Office 365 Mover**、**权限**、**为公司授予管理员许可**。
1. 选择你的帐户，查看权限，**然后选择接受。**
1. 选择 **"** 属性"，并验证 **"需要用户分配** ？"是否打开。
1. 返回到 Mover 应用，更改显示名称，如果需要，请选择 **授权，然后选择** Microsoft 管理员帐户。

    Mover 将通知你已发现SharePoint Online (或 SPO) 用户的数量。
1. 选择 **"继续迁移设置"**， **选择"添加用户"**，然后选择" **自动发现和添加用户"**。

    Mover 应用将尝试将驱动器从 Google 中的源路径映射到 Microsoft 365。 

    如果驱动器未自动映射，请将其目标路径添加到 CSV 文件，我们稍后会使用该路径将共享驱动器迁移到SharePoint库。 

1. 在这种情况下，我们添加了一SharePoint迁移文件的网站，并记下了文档页面的 URL。 
1. 然后，我们使用"源路径"、"目标路径"和"标记"格式创建了 CSV 文件。 

    有关详细信息， [请参阅 aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv)。

    添加目标路径 URL 时，删除共享文档之后的所有内容。 例如，此完整 URL 无效： `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    将其更改为：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV 文件准备就绪后，选择"迁移操作"**、"添加到** 迁移"**和"选择要上载的文件"**。
1. 导航到 CSV 文件，选择它，然后选择"打开 **"**。
1. 选择要迁移其文件的用户驱动器，然后选择"开始 **迁移用户"**。
1. 查看迁移信息，选择开始迁移时间，同意条款和条件，然后选择"继续 **"**。

Mover 应用将在迁移过程完成时通知你。