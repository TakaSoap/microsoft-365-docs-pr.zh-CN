---
title: 在 Microsoft Viva 主题中管理主题发现
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何管理 Microsoft Viva 主题中的主题发现。
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768970"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>在 Microsoft Viva 主题中管理主题发现

可以在 [Microsoft 365](https://admin.microsoft.com)管理中心中管理主题发现设置。 您必须是全局管理员或 SharePoint 管理员才能执行这些任务。

## <a name="to-access-topics-management-settings"></a>若要访问主题管理设置：

1. 在 Microsoft 365 管理中心中，单击"**设置"，** 然后单击"**组织设置"。**
2. 在"**服务"** 选项卡上，单击 **"主题体验"。**

    ![将人员与知识连接](../media/admin-org-knowledge-options-completed.png) 

3. 选择" **主题发现"** 选项卡。有关每个设置的信息，请参阅以下各节。

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>选择 SharePoint 主题源

您可以更改组织中将针对主题进行爬网的 SharePoint 网站。

如果要包含或排除特定的网站列表，可以使用以下 .csv 模板：

``` csv
Site name,URL
```

如果使用网站选取器添加网站，则它们将被添加到要包含或排除的现有网站列表中。 如果上载 .csv 文件，它将覆盖任何现有列表。 如果之前已包含或排除特定网站，则以 .csv 文件下载列表、进行更改并上载新列表。

为主题发现选择站点

1. 在"**主题发现"选项卡上的**"**选择 SharePoint 主题源"下，** 选择"编辑 **"。**
2. 在" **选择 SharePoint 主题源** "页上，选择要在发现期间作为主题源对哪些 SharePoint 网站进行爬网。 这包括：
    - **所有网站**：租户中所有 SharePoint 网站。 这将捕获当前和将来的网站。
    - **全部，所选网站除外**：键入要排除的网站的名称。  还可以上载要选择从发现中退出的网站列表。 将来创建的网站将包含为主题发现源。 
    - **仅选定网站**：键入要包含的网站的名称。 您还可以上载网站列表。 将来创建的网站不会作为主题发现源包含在内。
    - **无网站**：主题不会随 SharePoint 内容自动生成或更新。 现有主题保留在主题中心。

    ![SharePoint 主题源用户界面的屏幕截图](../media/k-manage-select-topic-source.png)
   
3. 单击“**保存**”。

## <a name="exclude-topics-by-name"></a>按名称排除主题

可以通过使用 .csv 文件上载列表来从发现中排除主题。 如果之前已排除主题，可以下载 .csv，进行更改，然后重新上载。

1. 在"**主题发现"选项卡上的**"**排除主题"下**，选择"编辑 **"。**
2. 单击 **"按名称排除主题"。**
3. 如果需要创建列表，请下载 .csv 模板并添加要排除 (请参阅下面的 *使用 .csv*) 。 文件准备就绪后，单击" **浏览** "并上载该文件。 如果存在现有列表，可以下载包含该列表的 .csv。
4. 单击“**保存**”。

    ![排除主题用户界面的屏幕截图](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>使用 .csv 模板

你可以复制下面的 csv 模板：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

在 CSV 模板中，输入有关要排除的主题的以下信息：

- **名称**：键入要排除的主题的名称。 可通过 2 种方法执行此操作：
    - 完全匹配：可以排除确切的名称或缩写 (例如 *Contoso* 或 *ATL*) 。
    - 部分匹配：可以排除其中包含特定单词的所有主题。  例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*
- **代表 (可选**) ：如果要排除首字母缩写词，请键入首字母缩写词代表的单词。
- **MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>另请参阅

[在 Microsoft 365 中管理主题可见性](topic-experiences-knowledge-rules.md)

[在 Microsoft 365 中管理主题权限](topic-experiences-user-permissions.md)

[在 Microsoft 365 中更改主题中心的名称](topic-experiences-administration.md)
