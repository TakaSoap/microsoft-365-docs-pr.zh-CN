---
title: Advanced eDiscovery审阅集的仪表板
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用Advanced eDiscovery仪表板查看集来快速分析文档集，以确定将帮助您制定审阅策略的趋势或关键统计信息。
ms.openlocfilehash: b7bc487e95c2dbae1a65aaad94face6bee19d39b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175475"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscovery审阅集的仪表板

在某些情况下，Advanced eDiscovery可能需要查看大量文档和电子邮件。 在开始审阅过程之前，您可能需要快速分析文档集，以确定将帮助您制定审阅策略的趋势或关键统计信息。 为此，可以使用审阅Advanced eDiscovery仪表板来快速分析文档集。

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>步骤 1：在审阅集仪表板上创建小组件

1. 在Microsoft 365 合规中心中，转到"**电子** 数据展示> Advanced eDiscovery以显示组织中事例的列表。
  
2. 选择现有案例。
  
3. 单击" **审阅集"** 选项卡，然后选择审阅集。
  
4. 在“**单独的结果**”下拉列表中，单击“**搜索配置文件**”。 

   ![DashbordPivot。](../media/dashboardpivot.png)

   将显示 **"搜索配置文件视图** "页;第一次显示此页面时，将显示三个默认小组件。

   ![仪表板。](../media/dashboardonly.png)
  
5. 单击" **新建"小** 组件，然后选择下列项目之一：

   !["新建小组件"下拉列表。](../media/NewWidgetDropdownBox.png)

   - **从库中选择：** 显示小部件的默认库。 单击小组件，然后单击 **"添加"** 将其添加到"搜索配置文件视图"页上 **的小部件** 。
  
   - **创建自定义小组件：** 显示可用于设置自定义小部件的飞出页。 

6. 若要创建自定义小组件，在"添加小组件"飞出 **页面上** 执行以下操作：

   ![创建小组件。](../media/addwidget.png)

    a. 键入小部件的名称，该名称将显示在小组件标题栏中。 命名小组件是必需的，但有助于标识小组件数据。

    b. 在"选择数据透视 **表** "下拉列表中选择一个将用于小组件数据的属性。 此列表中的项目是审阅集内项目的可搜索属性。 有关这些属性的说明，请参阅 Document [metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md)。 本主题的"可搜索字段名称"列中列出了小部件的透视选项。

    c. 选择图表类型以显示选定透视属性的数据。

  6. 单击 **"** 添加"创建自定义小部件，并显示在" **搜索配置文件视图"** 页上。

## <a name="step-2-create-a-review-set-search-query"></a>步骤 2：创建审阅集搜索查询

1. 单击 **小** 组件标题栏中的"..."，然后单击"**应用条件"。**

   ![仪表板。](../media/searchprofilehome.png)

2. 在飞出页面上，单击小组件键或小组件图表上的元素以创建筛选器。

   ![CreateFilter。](../media/applyconditionfilter.png)

3. 对其他小组件多个小组件重复步骤 1-2。 

4. 完成后，单击"另存为 **查询** "，将条件另存为审阅集的新搜索查询。

   ![查询。](../media/savequery.png)

5. 关闭 **搜索配置文件视图** 以返回到搜索结果视图。

   如果已创建任何可视化筛选器，则生成的查询将应用于显示的搜索结果，步骤 4 中保存的搜索查询将显示在"保存的查询 **"下**。 有关审阅集查询详细信息，请参阅查询 [审阅集内的数据](review-set-search.md)。
