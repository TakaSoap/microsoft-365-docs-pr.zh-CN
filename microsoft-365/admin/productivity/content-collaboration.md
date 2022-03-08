---
title: Microsoft Productivity Score - 内容协作
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 12ef0d1f56e8aa122942394e9214b501c85ababd
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324923"
---
# <a name="content-collaboration--people-experiences"></a>内容协作 – 人员体验

生产力分数通过组织对数字转型的Microsoft 365和支持它的技术体验提供见解。 你的组织的分数反映了人员和技术体验指标，可以与类似你组织的基准进行比较。 内容协作类别是人员体验度量的一部分。 若要了解更多信息，请查看生产力 [分数概述并](productivity-score.md) 阅读 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

## <a name="prerequisites"></a>先决条件

若要开始使用内容协作见解，需要获得组织中人员的许可：

- OneDrive for Business
- SharePoint
- Exchange Online

有关详细信息，请参阅 [向用户分配许可证](../manage/assign-licenses-to-users.md)。

 在用户过去 28 天内至少活跃于上述产品一次后，你将开始看到见解。

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>为什么组织&#39;协作分数很重要

数字转型的一个关键方面是人们如何协作处理文件。 使用内容在Microsoft 365，人员可以随时随地访问、创建、修改和协作处理内容。 研究表明，当用户使用联机文件进行协作时，每个人每周平均节省 100 分钟。

## <a name="how-we-calculate-the-content-collaboration-score"></a>如何计算内容协作分数

我们提供主要见解，其中包含组织中内容协作的关键指标。 然后，下面详述的评分框架将用于这些指标来计算组织的分数。

> [!NOTE]
> 2021 年 4 月 22 日，我们更改了协作者指标的计算方式。 这会影响主要[见解、](#primary-insight)[文件协作](#number-of-files-collaborated-on)见解和内容协作分数的度量方式。 此更改有助于减少来自非人工代理 (Microsoft) 其他第三方应用程序的机器人）的数据的干扰，从而获得更准确且可操作的分数。

### <a name="primary-insight"></a>主要见解

Microsoft OneDrive for Business 和 SharePoint 可帮助用户跨设备和应用程序在 Microsoft 365 中轻松创建、读取和发现其个人内容和共享内容。 它们还允许用户安全地共享和协作处理内容。 主要见解包含所有能够使用 OneDrive for Business 和 SharePoint。 此外，它还详细说明了有多少人阅读、创建和协作处理存储在OneDrive for Business SharePoint。

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="通信协作分数的主要见解。":::


此信息考虑的类型包括 Word、Excel、PowerPoint、OneNote 和 PDF 文件。

1. **标头：** 显示您组织中的有权访问协作内容OneDrive SharePoint用户百分比。
2. **正文：** 提供有关联机读取和创建文件的行为如何链接到对文件进行协作的信息。
3. **可视化 (当前状态) ：**
    - 蓝色部分表示通过 OneDrive 或 SharePoint 启用文件协作的百分比的水平栏，这些人员是过去 28 天内在线文件的读者、创建者或协作者。

        定义如下：</br>
        **读者：** 访问或下载联机文件OneDrive或SharePoint。</br>
        **创建者：** 创建、修改、上载、同步、签入、复制或联机移动或OneDrive或SharePoint人员。</br>
        **协作者：** 通过使用联机或联机文件进行OneDrive SharePoint。 如果其中一个人在 28 天窗口中创建或修改联机 Office 应用或 PDF 后读取或编辑联机文档或 PDF，则两个人是协作者。

        > [!NOTE]
        > 可视化中考虑的文件为 Word、Excel、PowerPoint、OneNote 或 PDF 文件，它们联机并保存到 OneDrive 或 SharePoint。 

    - 突出显示 (分数的) /分母值用于计算每个水平条中表示的百分比。
    
      - **读者：**</br>
          - 数字：过去 28 天内在 OneDrive 或 SharePoint 访问或下载联机文件的人数</br>
          - 分母：过去 28 天内OneDrive或SharePoint至少 1 天</br>
      - **创建者：**</br>
        - 数字：过去 28 天内在 OneDrive 或 SharePoint 创建、修改、上载、同步、签入、复制或移动联机文件的人数</br>
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天的访问权限。 </br> 
      - **协作者：**</br>
        - 数字：过去 28 天内在 OneDrive 或 SharePoint 中协作处理联机文件的人数</br>
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 次访问次数

    - 每个读者、创建者和协作者的对等基准值也显示为百分比。 换句话说，创建者数量的值以有权访问创作者或创作者OneDrive的百分比SharePoint。
    
1. **指向资源的链接：** 选择此链接可查看整理的视频和其他相关帮助内容。


#### <a name="trend-visualization-of-primary-insight"></a>主要见解的趋势可视化

趋势可视化图显示了过去 180 天内读者、创建者和协作者的主要见解关键指标的趋势线。 图表上的每个数据点都是最近 28 天的活动聚合。 每个创建者数据点都提供过去 28 天内在 x 轴上的每个日期标记为创建者的所有人员计数。

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="包含协作主要见解趋势的图表。":::

### <a name="scoring-framework"></a>记分框架

组织的内容协作分数以 (组织) 聚合级别衡量，无论用户是否一致地阅读、创建或协作联机 Office 文件（如 Word、Excel、PowerPoint、OneNote 或 PDF，或在 OneDrive 或 SharePoint 中）。

未在单个用户级别提供分数。

## <a name="explore-how-your-organization-collaborates"></a>探索组织如何协作

我们还为您提供了可帮助您了解组织如何协作处理内容的信息。 这些额外的指标不会直接影响工作效率分数，但有助于创建作为数字转型一部分的行动计划，以帮助优化人们的工作方式。

### <a name="creating-files-in-onedrive-or-sharepoint"></a>在 OneDrive 或 SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="显示以用户或用户OneDrive创建文件的SharePoint。":::

1. **标头：** 突出显示在应用程序上或Microsoft 365 Office创建文件的活动OneDrive SharePoint。
2. **正文：** 提供有关在网站和网站中创建内容OneDrive SharePoint。
3. **可视化：** 可视化中的细分表示使用 Microsoft Office 应用在 OneDrive 和 SharePoint 创建文件的程度，如下所示：
      - **OneDrive：** (的蓝色) 部分，而条形上的分数表示 Office 应用程序上创建内容的活动OneDrive如下所示：
        - 数字：过去 28 天内在 OneDrive 内创建、修改、上载、同步、签入、复制或移动联机 Office 文件的人数。</br>
        - 分母：过去 28 天内OneDrive或SharePoint访问办公室文件的数量。
      - **SharePoint：** (的蓝色) 部分，而条形上的分数表示在 Office 应用程序上处于活动状态并创建内容在 SharePoint 上的百分比：</br>
         - 数字：过去 28 天内在 SharePoint 上创建、修改、上载、同步、签入、复制或移动联机 Office 文件 (Microsoft Word、Excel、PowerPoint 或 OneNote 文件) 用户数。</br>
        - 分母：过去 28 天内OneDrive或SharePoint访问Office文件的数量。

4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="use-of-attachments-in-email"></a>电子邮件中的附件使用

**电子邮件中的附件使用** 了解在电子邮件中附加物理文件（而不是指向云中内容的链接）的用户数，并监视此数量在一段时间的减少。

:::image type="content" source="../../media/emailattachments.png" alt-text="使用电子邮件附件。":::

1. **标头：** 突出显示电子邮件中未保存到联机文件使用附件的百分比。
2. **正文：** 从协作和安全角度提供有关共享联机文件链接的价值的信息。
3. **可视化：** 可视化的细分旨在表示电子邮件中附加内容的人使用不同模式（未保存到联机文件的 (文件、指向联机文件的链接) ：
      - **附加文件：** 蓝色 (条的) 部分，而条形上的分数 (numerator/denominator) 表示电子邮件中使用附件的百分比。
        - 数字：将文件附加到过去 28 天内未保存到联机文件的电子邮件中的人数。
        - 分母：过去 28 天内有权访问 Exchange 和 OneDrive、SharePoint 或两者的人的数量。
      - **指向联机文件的链接：** 蓝色 (条的) 部分，而条形上的分数 (numerator/denominator) 表示使用附件并将链接附加到电子邮件中的文件的百分比。
        - 数字：过去 28 天内向电子邮件附加联机文件链接的人数。
        - 分母：过去 28 天内有权访问 Exchange 和 OneDrive、SharePoint 或两者的人的数量。
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="sharing-of-online-files"></a>共享联机文件

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="显示在线共享文件人数的图表。":::

1. **标头：** 突出显示具有外部共享文件访问权限OneDrive SharePoint用户数的百分比。
2. **正文：** 提供有关管理员的信息&#39;更改组织中文件共享设置以启用最适合贵组织的协作级别。
3. **可视化：** 表示有权访问用户或用户OneDrive SharePoint或外部共享文件的程度：
      - **外部：** 蓝色 (条的) 部分和条形上的分数 (numerator/分母) 表示有权访问 OneDrive 或 SharePoint 且正在外部共享文件的人的百分比。
        -  数字：过去 28 天内与外部共享文件的人数
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天拥有访问权限的总数。
      - **仅内部：** 蓝色 (条的) 部分，而条形上的分数 (numerator/分母) 表示有权访问 OneDrive 或 SharePoint 且仅在内部共享文件的人的百分比。
        - Numerator：过去 28 天内仅在内部共享文件的人数
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天拥有访问权限的总数。
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="number-of-files-collaborated-on"></a>协作处理的文件数

:::image type="content" source="../../media/intensityofcollab.png" alt-text="显示协作最多的文件的图表。":::

1. **标头：** 突出显示对 4 个或多个文件OneDrive或SharePoint用户的访问权限的百分比。
2. **正文：** 提供有关用户如何利用联机文件进行更好的协作的信息。
3. **可视化：** 显示有权访问 OneDrive 或 SharePoint 的SharePoint，基于他们协作处理的文件数。 这通过以下 4 个类别 (，栏的蓝色部分和分数表示有权访问属于该类别的 OneDrive 或 SharePoint 的百分比) ：
      - **无协作：**
        - 数字：过去 28 天内未协作处理任何文件的人数。
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天的访问权限的总数。
      - **协作处理 1-3 个文件：**
        - 数字：最近 28 天内协作处理 1-3 个文件的人数。
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天拥有访问权限的总数。
      - **协作处理 4-10 个文件：**
        - 数字：最近 28 天内协作处理 4-10 个文件的人数。
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天拥有访问权限的总数。
      - **协作处理 11 个或多个文件：**
        - 数字：最近 28 天内协作处理 11 个或多个文件的人数。
        - 分母：过去 28 天内OneDrive或SharePoint至少 1 天拥有访问权限的总数。
        
4. **指向资源的链接：** 选择此链接可查看帮助内容。

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>OneDrive 和 SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="显示 OneDrive 和 SharePoint 的网络性能的图表。":::

1. **标头：** 突出显示所有已测试设备中与 OneDrive 和 SharePoint。 
2. **正文：** 提供有关网络连接性能为什么对协作很重要的信息。 
3. **可视化：** 显示与移动设备和移动设备相关的不同网络连接性能级别的OneDrive SharePoint：
      - **81-100 (** 最佳) ：条形图的深绿色 (颜色) 部分表示性能最佳的设备的百分比。
      - **61-80**： (颜色) 颜色表示网络性能分数在 60-80 之间的设备的百分比。 
      - **41-60**： (的橙色) 表示网络性能分数在 40-60 之间的设备的百分比。 
      - **21-40**： (的红色) 表示网络性能分数介于 20 到 40 之间的设备的百分比。 
      - **0-20**：条形 (深红色) 表示网络性能分数在 0 到 20 之间最差的设备百分比。 

## <a name="related-content"></a>相关内容

[Microsoft 365应用运行状况 – 技术体验 (](apps-health.md)文章) \
[通信 – 人员体验](communication.md) (文章) \
[会议 – 人员体验](meetings.md) (文章) \
[移动性 – 人员体验](mobility.md) (文章) \
[工作效率分数的隐私控件](privacy.md) (文章) \
[团队合作 – 人员体验](teamwork.md) (文章) 
