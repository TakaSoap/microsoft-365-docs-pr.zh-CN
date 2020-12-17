---
title: 在 Microsoft 365 中管理主题发现
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何在 Microsoft 365 中管理主题发现。
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698539"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a>在 Microsoft 365 中管理主题发现

可以在 [Microsoft 365](https://admin.microsoft.com)管理中心管理主题发现设置。 您必须是全局管理员或 SharePoint 管理员才能执行这些任务。

## <a name="to-access-topics-management-settings"></a>访问主题管理设置：

1. 在 Microsoft 365 管理中心中，单击"**设置**"，然后单击"**组织设置"。**
2. 在"**服务"** 选项卡上，单击 **"知识网络"。**

    ![将人员连接到知识](../media/admin-org-knowledge-options-completed.png) 

3. 选择 **"主题发现"** 选项卡。有关每个设置的信息，请参阅以下部分。

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>选择 SharePoint 主题源

您可以更改组织中将针对主题进行爬网的 SharePoint 网站。

如果要包含或排除特定网站列表，可以使用以下 .csv 模板：

``` csv
Site name,URL
```

如果使用网站选取器添加网站，则它们将被添加到要包含或排除的现有网站列表中。 如果上载 .csv 文件，它将覆盖任何现有列表。 如果之前已包含或排除特定网站，则以 .csv 文件下载列表、进行更改并上载新列表。

为主题发现选择网站

1. 在 **"主题发现"** 选项卡上的 **"选择 SharePoint 主题源"下**，选择"**编辑"。**
2. 在 **"选择 SharePoint 主题源** "页上，选择要在发现过程中作为主题源对哪些 SharePoint 网站进行爬网。 这包括：
    - **所有网站**：租户中所有 SharePoint 网站。 这将捕获当前和将来的网站。
    - **全部，所选网站除外**：键入要排除的网站的名称。  还可以上载要选择从发现中退出的网站列表。 将来创建的网站将包含为主题发现源。 
    - **仅选定网站**：键入要包含的网站的名称。 还可以上载网站列表。 将来创建的网站不会作为主题发现源包含在内。
    - **无网站**：主题不会自动生成或随 SharePoint 内容一起更新。 现有主题保留在主题中心。

    ![SharePoint 主题源用户界面的屏幕截图](../media/k-manage-select-topic-source.png)
   
3. 单击“**保存**”。

## <a name="exclude-topics-by-name"></a>按名称排除主题

可以通过使用 .csv 文件上载列表来从发现中排除主题。 如果之前已排除主题，可以下载 .csv，进行更改，然后重新上载。

1. 在"**主题发现"** 选项卡上的 **"排除主题**"下，选择 **"编辑"。**
2. 单击 **"按名称排除主题"。**
3. 如果需要创建列表，请下载 .csv 模板，并添加要排除的主题 (请参阅下面的 *.csv* 模板) 。 文件准备就绪后，单击" **浏览** "并上载文件。 如果存在现有列表，可以下载包含该列表的 .csv。
4. 单击“**保存**”。

    ![排除主题用户界面的屏幕截图](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>使用 .csv 模板

你可以复制下面的 csv 模板：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

在 CSV 模板中，输入有关要排除的主题的以下信息：

- **名称**：键入要排除的主题的名称。 可通过 2 种方法执行此操作：
    - 完全匹配：可以包括确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。
    - 部分匹配：可以排除其中具有特定单词的所有主题。  例如 *，arc* 将排除其中带弧字的所有主题，如 *弧形圆*、圆弧 *弧* 线或 *培训弧*。请注意，它将不会排除作为单词的一部分包含的文本的主题，例如 *体系结构。*
- **代表 (可选**) ：如果要排除首字母缩略词，请键入首字母缩写词代表的单词。
- **MatchType-Exact/Partial：** 键入您输入的名称 *是精确匹配* 类型还是 *部分* 匹配类型。

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>另请参阅

[在 Microsoft 365 中管理主题可见性](topic-experiences-knowledge-rules.md)

[在 Microsoft 365 中管理主题权限](topic-experiences-user-permissions.md)

[在 Microsoft 365 中更改主题中心的名称](topic-experiences-administration.md)
