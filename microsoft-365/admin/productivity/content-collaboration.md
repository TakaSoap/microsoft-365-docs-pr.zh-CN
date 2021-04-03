---
title: Microsoft Productivity Score - 内容协作
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: 内容协作的详细信息 - 人员体验生产力分数。
ms.openlocfilehash: dedd39a84580f26e80e5586e07fb64c8a6d35573
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580854"
---
# <a name="content-collaboration--people-experiences"></a>内容协作 – 人员体验

生产力分数通过 Microsoft 365 的使用和支持它的技术体验，提供组织数字化转型之旅的见解。 你的组织的分数反映了人员和技术体验指标，并可以与类似你组织的基准进行比较。 内容协作类别是人员体验度量的一部分。 若要了解更多信息，请查看生产力 [分数概述并](productivity-score.md) 阅读 Microsoft [隐私声明](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>先决条件

若要开始使用内容协作见解，需要获得组织中人员的许可：

- OneDrive for Business
- SharePoint
- Exchange Online

有关详细信息，请参阅 [向用户分配许可证](../manage/assign-licenses-to-users.md)。

 在用户过去 28 天内至少活跃于上述产品一次后，你将开始看到见解。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>为什么组织&#39;协作分数很重要

数字转型的一个关键方面是人们如何协作处理文件。 借助 Microsoft 365 上的内容，用户可以随时随地访问、创建、修改和协作处理内容。 研究表明，当用户使用联机文件进行协作时，每个人每周平均节省 100 分钟。 [请参阅证据](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)。

## <a name="how-we-calculate-the-content-collaboration-score"></a>如何计算内容协作分数

我们提供主要见解，其中包含组织中内容协作的关键指标。 然后，下面详述的评分框架将用于这些指标来计算组织的分数。

### <a name="primary-insight"></a>主要见解

Microsoft OneDrive for Business 和 SharePoint 可帮助用户跨设备和应用程序在 Microsoft 365 中轻松创建、读取和发现其个人内容和共享内容。 它们还允许用户安全地共享和协作处理内容。 主要见解包含来自可以使用 OneDrive for Business 和 SharePoint 的每个人的信息。 此外，它还详细说明了有多少人阅读、创建和协作处理 OneDrive for Business 和 SharePoint 中存储的内容。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="通信协作分数的主要见解。":::


此信息考虑的类型包括 Word、Excel、PowerPoint、OneNote 和 PDF 文件。

1. **标头：** 显示组织中的有权访问 OneDrive 或 SharePoint 并协作使用内容的人的百分比。
2. **正文：** 提供有关联机读取和创建文件的行为如何链接到对文件进行协作的信息。
3. **可视化 (当前状态) ：**
    - 蓝色部分表示通过 OneDrive 或 SharePoint 启用文件协作的百分比的水平栏，这些人员是过去28 天内在线文件的读者、创建者或协作者。

        定义如下：</br>
        **读者：** 访问或下载 OneDrive 或 SharePoint 中的联机文件的人。</br>
        **创建者：** 创建、修改、上载、同步、签入、复制或移动联机 OneDrive 或 SharePoint 文件的人。</br>
        **协作者：** 使用 OneDrive 或 SharePoint 与联机文件协作的人。 如果其中一个人在 28 天窗口中创建或修改联机 Office 应用或 PDF 后读取或编辑联机 Office 应用或 PDF，则两个人是协作者。

        > [!NOTE]
        > 可视化中考虑的文件是联机并保存到 OneDrive 或 SharePoint 的 Word、Excel、PowerPoint、OneNote 或 PDF 文件。 

    - 突出显示 (分数的) /分母值用于计算以每个水平线表示的百分比。
    
      - **读者：**</br>
          - 数字：过去 28 天内访问或下载 OneDrive 或 SharePoint 中的联机文件的人数</br>
          - 分母：过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的人数</br>
      - **创建者：**</br>
        - 数字：过去 28 天内在 OneDrive 或 SharePoint 中创建、修改、上载、同步、签入、复制或移动联机文件的人数</br>
        - 分母：过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的人数。 </br> 
      - **协作者：**</br>
        - 数字：过去 28 天内在 OneDrive 或 SharePoint 中协作处理联机文件的人数</br>
        - 分母：过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的人数

    - 每个读者、创建者和协作者的对等基准值也显示为百分比。 换句话说，创建者数量的值显示为有权访问 OneDrive 或 SharePoint 的百分比。
    
1. **指向资源的链接：** 选择此链接可查看逐份打印的视频和其他相关帮助内容。


#### <a name="trend-visualization-of-primary-insight"></a>主要见解的趋势可视化

趋势可视化图显示了过去 180 天内读者、创建者和协作者的主要见解关键指标的趋势线。 图表上的每个数据点都是最近 28 天的活动聚合。 每个创建者数据点都提供过去 28 天内在 x 轴上每个日期标记为创建者的所有人员计数。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="包含协作主要见解趋势的图表。":::

### <a name="scoring-framework"></a>记分框架

组织的内容协作分数以 (组织) 聚合级别衡量，无论用户是一直阅读、创建或协作处理联机 Office 文件（如 Word、Excel、PowerPoint、OneNote 或 PDF）;还是在 OneDrive 或 SharePoint 中。

未在单个用户级别提供分数。


## <a name="explore-how-your-organization-collaborates"></a>探索组织如何协作

我们还为您提供了可帮助您了解组织如何协作处理内容的信息。 这些额外的指标不会直接影响工作效率分数，但有助于创建作为数字转型一部分的行动计划，以帮助优化人们的工作方式。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>在 OneDrive 或 SharePoint 中创建文件

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="显示 OneDrive 或 SharePoint 中创建文件人数的图表":::

1. **标头：** 突出显示在 OneDrive 或 SharePoint 上创建文件的 Microsoft 365 Office 应用程序活跃用户百分比。
2. **正文：** 提供有关 OneDrive 和 SharePoint 中内容创建的价值的信息。
3. **可视化：** 可视化中的细分表示使用应用程序在 OneDrive 和 SharePoint Microsoft Office文件的程度，如下所示：
      - **OneDrive：** 蓝色 (条) 部分，而条形上的分数表示在 OneDrive 上创建内容的 Office 应用程序活跃人员百分比，如下所示：
        - 数字：过去 28 天内在 OneDrive 中创建、修改、上传、同步、签入、复制或移动联机 Office 文件的人数。</br>
        - 分母：过去 28 天内有权访问 OneDrive 或 SharePoint 并访问 Office 文件的人数。
      - **SharePoint：** 蓝色 (条的) 部分，而条形上的分数表示在 Office 应用程序上处于活动状态并创建 SharePoint 上内容的人的百分比，如下：</br>
         - 数字：过去 28 天内在 SharePoint 上创建、修改、上载、同步、签入、复制或移动联机 Office 文件 (Microsoft Word、Excel、PowerPoint 或 OneNote) 数。</br>
        - 分母：过去 28 天内有权访问 OneDrive 或 SharePoint 并访问 Office 文件的人数。

4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="use-of-attachments-in-email"></a>电子邮件中的附件使用

:::image type="content" source="../../media/emailattachments.png" alt-text="使用电子邮件附件。":::

1. **标头：** 突出显示未保存到 OneDrive 或 SharePoint 的电子邮件中使用附件的百分比。
2. **正文：** 从协作和安全角度提供有关共享联机文件链接的价值的信息。
3. **可视化：** 可视化的细分旨在表示电子邮件中附加内容的人使用不同模式（而不是在 OneDrive 或 SharePoint 上 (文件）的程度;指向联机文件的链接;和电子邮件中嵌入) ：
      - **附加文件：** 蓝色 (条的) 部分，而条形上的分数 (numerator/denominator) 表示电子邮件中使用附件的百分比。
        - 数字：将文件附加到过去 28 天内未保存到 OneDrive 或 SharePoint 的电子邮件中的人数。
        - Denominator： ？ Denominator： The number of people who have access to Exchange and OneDrive， SharePoint， or both within the last 28 days.
      - **指向联机文件的链接：** 蓝色 (条的) 部分，而条形上的分数 (numerator/denominator) 表示使用附件并将链接附加到电子邮件中的文件的百分比。
        - 数字：最近 28 天内将联机文件链接 (保存到 OneDrive 或 SharePoint) 电子邮件的数量。
        - Denominator： ？ Denominator： The number of people who have access to Exchange and OneDrive， SharePoint， or both within the last 28 days.
      - **在电子邮件中嵌入链接：** 蓝色 (条) 部分的颜色，而条形上的分数表示在电子邮件正文中嵌入链接的人的百分比。
        - 数字：在电子邮件正文中嵌入链接的联机文件 (最近 28 天内保存到 OneDrive 或 SharePoint) 的数量。
        - Denominator： ？ Denominator： The number of people who have access to Exchange and OneDrive，SharePoint， or both within the last 28 days.
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="sharing-of-online-files"></a>共享联机文件

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="显示在线共享文件人数的图表。":::

1. **标头：** 突出显示在外部共享文件的 OneDrive 或 SharePoint 的访问权限的百分比。
2. **正文：** 提供有关管理员的信息&#39;更改组织中文件共享设置以启用最适合贵组织的协作级别。
3. **可视化：** 表示有权访问 OneDrive 或 SharePoint 的人在内部或外部共享文件的程度：
      - **外部：** 蓝色 (条的) 部分和条形上的分数 (numerator/denominator) 表示有权访问 OneDrive 或 SharePoint 且正在外部共享文件的人的百分比。
        -  数字：过去 28 天内与外部共享文件的人数
        - 分母：过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
      - **仅内部：** 蓝色 (条的) 部分和条形上的分数 (numerator/denominator) 表示有权访问 OneDrive 或 SharePoint 且仅在内部共享文件的人的百分比。
        - Numerator：过去 28 天内仅在内部共享文件的人数
        - 分母：过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="number-of-files-collaborated-on"></a>协作处理的文件数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="显示协作最多的文件的图表。":::

1. **标头：** 这突出显示了有权访问 OneDrive 或 SharePoint 并协作处理 4 个或多个文件的人的百分比。
2. **正文：** 这将提供有关用户如何利用联机文件进行更好的协作的信息。
3. **可视化：** 这显示有权访问 OneDrive 或 SharePoint 的人的分布，基于他们协作处理的文件数。 这通过以下 4 个类别 (，栏的蓝色部分和分数表示有权访问属于该类别的 OneDrive 或 SharePoint) ：
      - **无协作：**
        - **分子：** 过去 28 天内未协作处理任何文件的人数
        - **分母：** 最近 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
      - **协作处理 1-3 个文件：**
        - **分子：** 最近 28 天内协作处理 1-3 个文件的人数。
        - **分母：** 过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
      - **协作处理 4-10 个文件：**
        - **分子：** 最近 28 天内协作处理 4-10 个文件的人数
        - **分母：** 过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
      - **协作处理 11 个或多个文件：**
        - **分子：** 最近 28 天内协作处理 11 个或多个文件的人数
        - **分母：** 过去 28 天内至少 1 天内有权访问 OneDrive 或 SharePoint 的总数。
        
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive 和 SharePoint 的网络性能强度

:::image type="content" source="../../media/networkperfstrength.png" alt-text="显示 OneDrive 和 SharePoint 的网络性能的图表。":::

1. **标头：** 突出显示所有测试设备中与 OneDrive 和 SharePoint 网络连接不佳的设备百分比。 
2. **正文：** 提供有关网络连接性能为什么对协作很重要的信息。 
3. **可视化：** 显示与 OneDrive 和 SharePoint 相关的不同网络连接性能级别的设备的百分比：
      - **81-100 (最佳) ：** 条形图的深绿色 (颜色) 部分表示性能最佳的设备的百分比。
      - **61-80：** 条形的绿色 (颜色) 表示网络性能分数在 60-80 之间的设备的百分比。 
      - **41-60： (** 的橙色颜色) 表示网络性能分数在 40-60 之间的设备的百分比。 
      - **21-40：** 条形 (红色) 表示网络性能分数在 20-40 之间的设备的百分比。 
      - **0-20：** 条形 (深红色) 表示网络性能分数在 0 到 20 之间最差的设备百分比。 

## <a name="related-content"></a>相关内容

[Microsoft 365 应用运行状况 –](apps-health.md) 技术 (文章) \
[通信 – 人员体验](communication.md) (文章) \
[会议 – 人员体验](meetings.md) (文章) \
[移动性 – 人员体验](mobility.md) (文章) \
[工作效率分数的隐私控件](privacy.md) (文章) \
[团队合作 – 人员体验](teamwork.md) (文章) 
