---
title: 管理主题主题Microsoft Viva主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
ms.localizationpriority: medium
description: 了解如何在"主题"中管理Microsoft Viva发现。
ms.openlocfilehash: fb26bccc7feb00611f46c278dd85a3f75a8c4a50
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188993"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>管理主题主题Microsoft Viva主题

可以在管理主题发现设置[Microsoft 365 管理中心。](https://admin.microsoft.com) 您必须是全局管理员或SharePoint才能执行这些任务。

## <a name="to-access-topics-management-settings"></a>要访问主题管理设置，请执行以下操作：

1. 在"Microsoft 365 管理中心中，单击"设置"，**然后单击"****组织设置"。**
2. 在"**服务"** 选项卡上，单击 **"主题体验"。**

    ![连接了解知识。](../media/admin-org-knowledge-options-completed.png) 

3. 选择" **主题发现"** 选项卡。有关每个设置的信息，请参阅以下部分。

    ![knowledge-network-settings.](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>选择SharePoint主题源

可以更改组织中SharePoint主题进行爬网的网站。

如果要包含或排除特定的网站列表，可以使用以下.csv模板：

``` csv
Site name,URL
```

如果使用网站选取器添加网站，这些网站将添加到现有网站列表以包含或排除。 如果上传 .csv 文件，则会覆盖任何现有列表。 如果之前已包含或排除特定网站，则以文件.csv下载列表、进行更改并上载新列表。

为主题发现选择站点

1. 在“**主题发现**”选项卡上，“**SharePoint 主题源**”下方，选择“**编辑**”。
2. 在"**选择SharePoint** 源"页上，SharePoint哪些网站将在发现过程中作为主题源进行爬网。 这包括：
    - **所有网站**：SharePoint租户中所有网站。 这将捕获当前和将来的网站。
    - **全部，所选网站除外**：键入要排除的网站的名称。  还可以上载要选择从发现中退出的网站列表。 将包含未来创建的网站作为主题发现源。 
    - **仅选定网站**：键入要包含的网站的名称。 您还可以上载网站列表。 将不包含未来创建的网站作为发现源。
    - **无网站**：主题不会自动生成或更新SharePoint内容。 现有主题保留在主题中心。

    ![有关SharePoint源用户界面的屏幕截图。](../media/k-manage-select-topic-source.png)
   
3. 单击“**保存**”。

## <a name="exclude-topics-by-name"></a>按名称排除主题

可以通过使用 .csv 文件上传列表，将主题从发现中排除。 如果之前排除过主题，可以下载 .csv、进行更改，然后再次上传。

1. 在“**主题**”选项卡上，“**排除主题**”下方，选择“**编辑**”。
2. 单击 **"按名称排除主题"。**
3. 如果需要创建列表，请下载 .csv 模板并添加要排除的主题 (请参阅下面的使用 .csv 模板) 。  文件准备就绪后，单击" **浏览** "并上载文件。 如果存在现有列表，可以下载包含.csv的列表。
4. 单击“**保存**”。

    ![排除主题用户界面的屏幕截图。](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>使用.csv模板

你可以复制下面的 csv 模板：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

在 CSV 模板中，输入与要排除的主题相关的以下信息：

- **名称**：键入要排除的主题的名称。 可以通过两种方式来执行此操作：
    - 完全匹配：可以排除确切的名称或缩写 (例如 *Contoso* 或 *ATL*) 。
    - 部分匹配：可以排除其中包含特定单词的所有主题。  例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*
- **代表 (可选**) ：如果要排除首字母缩写词，请键入首字母缩写词代表的单词。
- **MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。

    ![排除 CSV 模板中的主题。](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>另请参阅

[管理主题在Microsoft 365](topic-experiences-knowledge-rules.md)

[管理主题权限Microsoft 365](topic-experiences-user-permissions.md)

[更改主题中心的名称Microsoft 365](topic-experiences-administration.md)
