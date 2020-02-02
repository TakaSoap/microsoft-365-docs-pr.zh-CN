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
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662178"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a><span data-ttu-id="adff9-102">审阅集的高级电子数据展示仪表板（预览）</span><span class="sxs-lookup"><span data-stu-id="adff9-102">Advanced eDiscovery dashboard for review sets (preview)</span></span>

<span data-ttu-id="adff9-103">在高级电子数据展示中的某些情况下，您可能会遇到大量需要审阅的文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="adff9-103">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="adff9-104">在开始审核过程之前，您可能希望快速分析文档集，以确定可帮助您开发您的审阅策略的趋势或关键统计信息。</span><span class="sxs-lookup"><span data-stu-id="adff9-104">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="adff9-105">为此，您可以使用高级电子数据展示仪表板进行审阅，以快速分析您的文档集。</span><span class="sxs-lookup"><span data-stu-id="adff9-105">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="adff9-106">步骤1：在审阅集仪表板上创建小部件</span><span class="sxs-lookup"><span data-stu-id="adff9-106">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="adff9-107">在安全 & 合规性中心中，转到**电子数据展示 > 高级电子数据展示**以显示您的组织中的案例列表。</span><span class="sxs-lookup"><span data-stu-id="adff9-107">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="adff9-108">选择现有事例。</span><span class="sxs-lookup"><span data-stu-id="adff9-108">Select an existing case.</span></span>
  
3. <span data-ttu-id="adff9-109">单击 "**查看集**" 选项卡，然后选择一种审阅集。</span><span class="sxs-lookup"><span data-stu-id="adff9-109">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="adff9-110">在 "**单个结果**" 下拉列表中，单击 "**搜索配置文件视图**"。</span><span class="sxs-lookup"><span data-stu-id="adff9-110">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](media/dashboardpivot.png)

   <span data-ttu-id="adff9-112">将显示 "**搜索配置文件视图**" 页;第一次显示此页时，将显示三个默认小部件。</span><span class="sxs-lookup"><span data-stu-id="adff9-112">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![仪表板](media/dashboardonly.png)
  
5. <span data-ttu-id="adff9-114">单击**新的小组件**，然后选择以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="adff9-114">Click the **New  widget** and then select one of the following items:</span></span>

   !["新建小组件" 下拉列表](media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="adff9-116">**从库中选择：** 显示小部件的默认库。</span><span class="sxs-lookup"><span data-stu-id="adff9-116">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="adff9-117">单击一个小组件，然后单击 "**添加**" 将其添加到 "**搜索配置文件视图**" 页面上的小部件。</span><span class="sxs-lookup"><span data-stu-id="adff9-117">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="adff9-118">**创建自定义小组件：** 显示可用于设置自定义小组件的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="adff9-118">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="adff9-119">若要创建自定义小组件，请在 "**添加小组件**" 飞出页面上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adff9-119">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![创建小组件](media/addwidget.png)

    <span data-ttu-id="adff9-121">a.</span><span class="sxs-lookup"><span data-stu-id="adff9-121">a.</span></span> <span data-ttu-id="adff9-122">键入小部件的名称，它将显示在小部件标题栏中。</span><span class="sxs-lookup"><span data-stu-id="adff9-122">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="adff9-123">命名小组件是必需的，但它有助于标识小部件数据。</span><span class="sxs-lookup"><span data-stu-id="adff9-123">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="adff9-124">b.</span><span class="sxs-lookup"><span data-stu-id="adff9-124">b.</span></span> <span data-ttu-id="adff9-125">在 "**选择数据透视**" 下拉列表中选择将用于小部件数据的属性。</span><span class="sxs-lookup"><span data-stu-id="adff9-125">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="adff9-126">此列表中的项目是审阅集中项目的可搜索属性。</span><span class="sxs-lookup"><span data-stu-id="adff9-126">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="adff9-127">有关这些属性的说明，请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="adff9-127">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="adff9-128">本主题的 "可**搜索字段名称**" 列中列出了小组件的数据透视选项。</span><span class="sxs-lookup"><span data-stu-id="adff9-128">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="adff9-129">c.</span><span class="sxs-lookup"><span data-stu-id="adff9-129">c.</span></span> <span data-ttu-id="adff9-130">选择图表类型以显示所选数据透视属性中的数据。</span><span class="sxs-lookup"><span data-stu-id="adff9-130">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="adff9-131">单击 "**添加**" 以创建自定义小组件并将其显示在 "**搜索配置文件视图**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="adff9-131">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="adff9-132">步骤2：创建审阅集搜索查询</span><span class="sxs-lookup"><span data-stu-id="adff9-132">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="adff9-133">单击小组件标题栏中的 " **...** "，然后单击 "**应用条件**"。</span><span class="sxs-lookup"><span data-stu-id="adff9-133">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![仪表板](media/searchprofilehome.png)

2. <span data-ttu-id="adff9-135">在弹出页面上，单击 "小部件键" 或 "小部件" 图表上的元素以创建筛选器。</span><span class="sxs-lookup"><span data-stu-id="adff9-135">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![CreateFilter](media/applyconditionfilter.png)

3. <span data-ttu-id="adff9-137">对其他小部件（多个小部件）重复步骤1-2。</span><span class="sxs-lookup"><span data-stu-id="adff9-137">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="adff9-138">完成后，单击 "**另存为查询**" 将您的条件保存为审阅集的新搜索查询。</span><span class="sxs-lookup"><span data-stu-id="adff9-138">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![查询](media/savequery.png)

5. <span data-ttu-id="adff9-140">关闭**搜索配置文件视图**以返回到 "搜索结果" 视图。</span><span class="sxs-lookup"><span data-stu-id="adff9-140">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="adff9-141">如果已创建任何可视化筛选器，则生成的查询将应用于所显示的搜索结果，并且在 "**已保存的查询**" 下将显示在步骤4中保存的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="adff9-141">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="adff9-142">有关审阅集查询的详细信息，请参阅[在审阅集中查询数据](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="adff9-142">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>
