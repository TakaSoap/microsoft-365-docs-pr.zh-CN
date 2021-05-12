---
title: '即将推出：将 SharePoint 配置为 Microsoft Viva Learning (Preview) '
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 了解如何将 SharePoint 配置为 Microsoft Viva Learning (Preview) 。
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333574"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a>即将推出：将 SharePoint 配置为 Microsoft Viva Learning (Preview) 

> [!NOTE]
> 本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。 

您可以将 SharePoint 配置为学习内容源，使组织自己的内容在 Viva Learning (Preview) 。

## <a name="overview"></a>概述

知识管理员 (或全局管理员) 提供了一个网站 URL，学习服务可在其中创建一个空的集中位置（"学习应用程序内容存储库"，形式为结构化 SharePoint 列表）。 您的组织可以使用此列表来存储指向包含学习内容的跨公司 SharePoint 文件夹的链接。 管理员负责收集并创建文件夹的 URL 列表。 这些文件夹应仅包含可在 Viva Learning (Preview) 中提供的内容。

Viva Learning (Preview) 支持以下文档类型：

- Word、PowerPoint、Excel、PDF
- Audio (.m4a) 
- 视频 (.mov、.mp4、.avi) 

有关详细信息，请参阅 [SharePoint 限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。 

## <a name="permissions"></a>权限

可以从组织的任何 SharePoint 网站收集文档库文件夹 URL。 Viva Learning (Preview) 遵循所有现有内容权限。 因此，只有用户有权访问的内容才能在 Viva Learning (Preview) 中搜索和) 。 这些文件夹中的任何内容都可以搜索，但只能使用单个员工具有权限的内容。

目前不支持从组织存储库中删除内容。

若要删除无意中显示的内容，请按照以下步骤操作：

1.  若要限制对文档库的访问，请选择"**显示操作**"选项，然后选择"**管理访问"。**
     
     ![SharePoint 中的"文档库"页显示"显示操作"选项，其中"管理访问权限"为"高连字"。](../media/learning/learning-sharepoint-permissions2.png)

2.  删除文档库中的原始文档。

有关详细信息，请参阅 [SharePoint 新式体验中的共享和权限](/sharepoint/modern-experience-sharing-permissions)。 

## <a name="learning-service"></a>学习服务

学习服务使用提供的文件夹 URL 从存储在这些文件夹中的所有内容获取元数据。 在集中式存储库中提供文件夹 URL 的 24 小时内，员工可以在 Viva Learning (Preview) 中搜索和使用组织的内容。 对内容的所有更改（包括更新的元数据和权限）也将在 24 小时内应用到学习服务中。

## <a name="configure-sharepoint-as-a-source"></a>将 SharePoint 配置为源

您必须是 Microsoft 365 全局管理员、SharePoint 管理员或知识管理员才能执行这些任务。

若要在 Viva Learning (Preview) 中将 SharePoint 配置为学习内容源，请按照以下步骤操作：

1.  在 Microsoft 365 管理中心的左侧导航中，转到 **"设置**  >  **""组织设置"。**
 
2.  在"**组织设置"** 页上的"服务 **"选项卡上**，选择 **"Viva Learning (Preview) "。**

     ![Microsoft 365 管理中心中的"设置"页面显示"Viva 学习"已列出。](../media/learning/learning-sharepoint-configure1.png)

3.  在 **Viva Learning (Preview)** 面板上的 SharePoint 下，提供您希望 Viva Learning (Preview) 创建集中式存储库的 SharePoint 网站的网站 URL。

     ![Microsoft 365 管理中心中的学习面板显示已选中的 SharePoint。](../media/learning/learning-sharepoint-configure2.png)

4.  SharePoint 列表在提供的 SharePoint 网站中自动创建。

     ![SharePoint 网站中新创建的 SharePoint 列表。](../media/learning/learning-sharepoint-configure3.png)

     在 SharePoint 网站的左侧导航栏中，选择"网站 **内容**  >  **""学习应用程序内容存储库"。** 

     ![显示"网站内容"导航和"了解应用程序内容存储库"部分的 SharePoint 列表。](../media/learning/learning-sharepoint-configure4.png) 

5. 在" **学习应用程序内容存储库"** 页上，使用学习内容文件夹的 URL 填充 SharePoint 列表。

   1. 选择 **"新建** "以查看 **"新建项目"** 面板。 

       ![SharePoint 中的"了解内容存储库"页显示"新建"选项。](../media/learning/learning-sharepoint-configure5.png)
 
   2. 在 **"新建项目** "面板的" **标题** "字段中，添加你选择的目录名称。 在 **"文件夹 URL"** 字段中，将 URL 添加到学习内容文件夹。 选择“**保存**”。

       ![SharePoint 中显示"标题"和"文件夹 URL"字段的"新建项目"面板。](../media/learning/learning-sharepoint-configure6.png)

   3. " **学习应用程序内容存储库"** 页使用新的学习内容进行更新。

       ![SharePoint 中的"了解内容存储库"页显示更新的信息。](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> 为了允许更广泛的访问"学习应用程序内容存储库"，即将在 Viva Learning (Preview) 界面中提供指向列表的链接，用户可以在这里请求访问并最终帮助填充列表。 网站所有者和全局管理员需要授予对列表的访问权限。 访问权限仅特定于列表，不适用于存储列表的网站。 有关详细信息，请参阅本文稍后 [介绍的提供您自己的](#provide-your-own-organizations-content) 组织的内容。

### <a name="folder-url-document-library-curation"></a>文件夹 URL 文档库库的库

Microsoft Graph API (修改日期、创建者、文档名称、内容类型和组织名称) 等默认元数据将自动拉入 Viva Learning (Preview) 中。
 
若要改进内容的总体发现和搜索相关性，建议添加"说明 **"** 列。

若要将 **"说明"** 列添加到文档库页面，请按照以下步骤操作：

1.  在"**文档"** 页上，选择"**添加列"。**

2. 选择"**显示操作**"选项，然后选择"**单行文本"。**

     ![SharePoint 中的"文档"页显示突出显示了单行文本的"显示操作"选项。](../media/learning/learning-sharepoint-curation1.png)

3. 在 **"创建列"面板** 的"名称 **"字段中，** 添加列的描述性名称。 选择“**保存**”。

     ![在 SharePoint 中创建一个显示"名称"和其他字段的列面板。](../media/learning/learning-sharepoint-curation2.png)
 
4. 在" **文档** "页上的" **说明** "列中，添加每个项目的自定义说明。 如果未提供任何说明，Viva Learning (Preview) 将提供一条默认消息，突出显示内容来自自己的 SharePoint 库。 

     ![SharePoint 中的"文档"页，显示"说明"列中的说明。](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a>提供你自己组织的内容

知识管理员可在 SharePoint 中访问其组织的"学习应用程序内容存储库"，可在其中提供对跨组织文档库的引用。 然后，这些库中的内容将在 Viva Learning (Preview) 中显示。

1. 在 Viva Learning (Preview) 中，选择"更多 **选项** (**...) "，** 然后选择"设置 **"。**

     ![显示"更多选项和设置"选项的 SharePoint 库页面。](../media/learning/learning-sharepoint-library-1.png)
     
2. 在 **"设置"** 下，**选择"权限"。**

     ![SharePoint 中的"设置"选项页面，显示"权限"和"检查访问选项"。](../media/learning/learning-sharepoint-library-2.png)

3. 选择 **"检查** 访问权限"以连接到组织的集中式库。
     
