---
title: 适用于审阅集的高级电子数据展示仪表板
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用高级电子数据展示仪表板进行审阅集以快速分析您的文档集，以确定可帮助您开发您的审阅策略的趋势或关键统计信息。
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741695"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>适用于审阅集的高级电子数据展示仪表板

在高级电子数据展示中的某些情况下，您可能会遇到大量需要审阅的文档和电子邮件。 在开始审核过程之前，您可能希望快速分析文档集，以确定可帮助您开发您的审阅策略的趋势或关键统计信息。 为此，您可以使用高级电子数据展示仪表板进行审阅，以快速分析您的文档集。

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>步骤1：在审阅集仪表板上创建小部件

1. 在安全 & 合规性中心中，转到**电子数据展示 > 高级电子数据展示**以显示您的组织中的案例列表。
  
2. 选择现有事例。
  
3. 单击 "**查看集**" 选项卡，然后选择一种审阅集。
  
4. 在 "**单个结果**" 下拉列表中，单击 "**搜索配置文件视图**"。 

   ![DashbordPivot](../media/dashboardpivot.png)

   将显示 "**搜索配置文件视图**" 页;第一次显示此页时，将显示三个默认小部件。

   ![仪表板](../media/dashboardonly.png)
  
5. 单击**新的小组件**，然后选择以下项目之一：

   !["新建小组件" 下拉列表](../media/NewWidgetDropdownBox.png)

   - **从库中选择：** 显示小部件的默认库。 单击一个小组件，然后单击 "**添加**" 将其添加到 "**搜索配置文件视图**" 页面上的小部件。
  
   - **创建自定义小组件：** 显示可用于设置自定义小组件的飞出页面。 

6. 若要创建自定义小组件，请在 "**添加小组件**" 飞出页面上执行以下操作：

   ![创建小组件](../media/addwidget.png)

    a. 键入小部件的名称，它将显示在小部件标题栏中。 命名小组件是必需的，但它有助于标识小部件数据。

    b. 在 "**选择数据透视**" 下拉列表中选择将用于小部件数据的属性。 此列表中的项目是审阅集中项目的可搜索属性。 有关这些属性的说明，请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。 本主题的 "可**搜索字段名称**" 列中列出了小组件的数据透视选项。

    c. 选择图表类型以显示所选数据透视属性中的数据。

  6. 单击 "**添加**" 以创建自定义小组件并将其显示在 "**搜索配置文件视图**" 页面上。

## <a name="step-2-create-a-review-set-search-query"></a>步骤2：创建审阅集搜索查询

1. 单击小组件标题栏中的 " **...** "，然后单击 "**应用条件**"。

   ![仪表板](../media/searchprofilehome.png)

2. 在弹出页面上，单击 "小部件键" 或 "小部件" 图表上的元素以创建筛选器。

   ![CreateFilter](../media/applyconditionfilter.png)

3. 对其他小部件（多个小部件）重复步骤1-2。 

4. 完成后，单击 "**另存为查询**" 将您的条件保存为审阅集的新搜索查询。

   ![Query](../media/savequery.png)

5. 关闭**搜索配置文件视图**以返回到 "搜索结果" 视图。

   如果已创建任何可视化筛选器，则生成的查询将应用于所显示的搜索结果，并且在 "**已保存的查询**" 下将显示在步骤4中保存的搜索查询。 有关审阅集查询的详细信息，请参阅[在审阅集中查询数据](review-set-search.md)。
