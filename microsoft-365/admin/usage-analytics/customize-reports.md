---
title: 在 Microsoft 365 使用情况分析中自定义报告
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 了解如何在浏览器和 Power BI Desktop 中自定义报告。
ms.openlocfilehash: 5fc3b399638b2f1e9b1b2726fbf58e22eda33e01
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240425"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="feaed-103">在 Microsoft 365 使用情况分析中自定义报告</span><span class="sxs-lookup"><span data-stu-id="feaed-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="feaed-104">Microsoft 365 使用情况分析在 Power BI 中提供了一个仪表板，可深入了解用户采用和使用 Microsoft 365 的方式。</span><span class="sxs-lookup"><span data-stu-id="feaed-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="feaed-105">这个仪表板只是与使用情况数据进行交互的起点。</span><span class="sxs-lookup"><span data-stu-id="feaed-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="feaed-106">可以自定义报表，从而获得更加个性化的见解。</span><span class="sxs-lookup"><span data-stu-id="feaed-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="feaed-107">还可以使用 Power BI Desktop 将报表连接到其他数据源来进一步自定义报表，以获得有关业务的更加丰富的见解。</span><span class="sxs-lookup"><span data-stu-id="feaed-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="feaed-108">在浏览器中自定义报表</span><span class="sxs-lookup"><span data-stu-id="feaed-108">Customizing reports in the browser</span></span>

<span data-ttu-id="feaed-109">以下两个示例显示了如何修改现有视觉对象以及如何创建新的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="feaed-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="feaed-110">修改现有视觉对象</span><span class="sxs-lookup"><span data-stu-id="feaed-110">Modify an existing visual</span></span>

<span data-ttu-id="feaed-111">此示例演示如何在**激活/许可**报告中修改**激活**选项卡。</span><span class="sxs-lookup"><span data-stu-id="feaed-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="feaed-112">在**激活/许可**报告中，单击 "**激活**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="feaed-112">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="feaed-113">通过单击 "Power BI ![](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png)中的其他页面" 按钮上的 "**编辑**" 按钮，进入编辑模式。</span><span class="sxs-lookup"><span data-stu-id="feaed-113">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="feaed-115">在右上部，单击 "**复制此页面**"。</span><span class="sxs-lookup"><span data-stu-id="feaed-115">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="feaed-117">在右下角，单击显示根据 OS （如 Android、iOS、Mac 等 OS 激活的用户计数）的任意条形图。</span><span class="sxs-lookup"><span data-stu-id="feaed-117">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="feaed-118">在右侧的**可视化**区域中，若要从 visual 中删除**Mac 计数**，请单击它旁边的**X** 。</span><span class="sxs-lookup"><span data-stu-id="feaed-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![删除 Mac 计数](../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="feaed-120">创建新的视觉对象</span><span class="sxs-lookup"><span data-stu-id="feaed-120">Create a new visual</span></span>

<span data-ttu-id="feaed-121">以下示例演示如何创建新的视觉对象，以按月跟踪新的 Yammer 用户。</span><span class="sxs-lookup"><span data-stu-id="feaed-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="feaed-122">使用左侧导航转到 "**产品使用情况**" 报表，然后单击 " **Yammer** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="feaed-122">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="feaed-123">单击 Power BI ![](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png)和**edit**中的 "更多页面" 按钮，切换到编辑模式。</span><span class="sxs-lookup"><span data-stu-id="feaed-123">Switch to edit mode by clicking on ![The more page button in Power BI](../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="feaed-124">在页面底部，单击 ""</span><span class="sxs-lookup"><span data-stu-id="feaed-124">At the bottom of the page, click on</span></span> ![Power BI 中的 "添加页面" 按钮](../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="feaed-126">创建新页面。</span><span class="sxs-lookup"><span data-stu-id="feaed-126">to create a new page.</span></span>
  
4. <span data-ttu-id="feaed-127">在右侧的**可视化**区域中，单击**堆积条形图**（顶部行，先于左侧）。</span><span class="sxs-lookup"><span data-stu-id="feaed-127">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![选择条形图](../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="feaed-129">单击可视化效果的右下方，然后拖动以使其变大。</span><span class="sxs-lookup"><span data-stu-id="feaed-129">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="feaed-130">在右侧的 "**字段**" 区域中，展开 "**日历**" 表。</span><span class="sxs-lookup"><span data-stu-id="feaed-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="feaed-131">将" **MonthName**"拖动到字段区域，该区域位于" **可视化效果**"区域中" **坐标轴**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="feaed-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![拖动月份名称](../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="feaed-133">在右侧的" **字段**"区域中，展开" **TenantProductUsage**"表。</span><span class="sxs-lookup"><span data-stu-id="feaed-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="feaed-134">将" **FirstTimeUsers**"拖动到字段区域，该区域位于" **值**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="feaed-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="feaed-135">将" **产品**"拖动到" **筛选器**"区域，该区域位于" **视觉级筛选器**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="feaed-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="feaed-136">在出现的" **筛选器类型**"区域中，选中" **Yammer**"复选框。</span><span class="sxs-lookup"><span data-stu-id="feaed-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![选择 Yammer 复选框](../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="feaed-138">在可视化效果列表的正下方，单击\*\*\*\* Power BI ![Visualizaions](../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)中的 "格式" 图标格式图标。</span><span class="sxs-lookup"><span data-stu-id="feaed-138">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="feaed-139">展开标题并将" **标题文本**"值更改为" **每月首次使用 Yammer 的用户**"。</span><span class="sxs-lookup"><span data-stu-id="feaed-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="feaed-140">将" **文本大小**"值更改为" **12**"。</span><span class="sxs-lookup"><span data-stu-id="feaed-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="feaed-141">通过在右下方编辑页面名称来更改新页面的标题。</span><span class="sxs-lookup"><span data-stu-id="feaed-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="feaed-142">通过单击顶部的 "**阅读视图**"，然后单击 "**保存**" 来保存报告。</span><span class="sxs-lookup"><span data-stu-id="feaed-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="feaed-143">自定义 Power BI Desktop 中的报表</span><span class="sxs-lookup"><span data-stu-id="feaed-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="feaed-p102">对于大多数客户而言，在 Power BI Web 版中修改报表和图表视觉对象已经足够。但是，对于某些客户而言，可能需要将此数据与其他数据源联接，以获得与其业务上下文有关的更加丰富的见解，在这种情况下，可以使用 Power BI Desktop 自定义并生成其他报表。可以免费下载 [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797)。</span><span class="sxs-lookup"><span data-stu-id="feaed-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="feaed-147">使用报告 API</span><span class="sxs-lookup"><span data-stu-id="feaed-147">Use the reporting APIs</span></span>

<span data-ttu-id="feaed-148">您可以从 Microsoft 365 中直接连接到 ODATA 报告 Api，以增强这些报告的功能。</span><span class="sxs-lookup"><span data-stu-id="feaed-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="feaed-149">转到" **获取数据**"\>" **其他**"\>" **ODATA 源**"\>" **连接**"。</span><span class="sxs-lookup"><span data-stu-id="feaed-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="feaed-150">在 "URL" 窗口中，<i></i>输入\<"\>https://reports.office.com/pbi/v1.0/tenantid"</span><span class="sxs-lookup"><span data-stu-id="feaed-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="feaed-151">**注意：** 报告 Api 处于预览阶段，可能会发生更改，直到它们投入生产。</span><span class="sxs-lookup"><span data-stu-id="feaed-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="feaed-153">在收到提示时，输入 Microsoft 365 （组织或学校）管理员凭据以向 Microsoft 365 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="feaed-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="feaed-154">有关允许访问 Microsoft 365 采用模板应用程序报告的成员的详细信息，请参阅[FAQ](usage-analytics.md#faq) 。</span><span class="sxs-lookup"><span data-stu-id="feaed-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="feaed-155">授权连接后，将看到显示可连接到的数据集的"导航器"窗口。</span><span class="sxs-lookup"><span data-stu-id="feaed-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="feaed-156">全选，然后单击" **加载**"。</span><span class="sxs-lookup"><span data-stu-id="feaed-156">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="feaed-p103">这会将数据下载到 Power BI Desktop。保存该文件，然后可以开始创建所需报表。</span><span class="sxs-lookup"><span data-stu-id="feaed-p103">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![报告 API 中可用的 ODATA 值](../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="feaed-160">使用 Microsoft 365 使用情况分析模板</span><span class="sxs-lookup"><span data-stu-id="feaed-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="feaed-161">您还可以使用与 Microsoft 365 使用情况分析报告相对应的 Power BI 模板文件作为连接到数据的起始点。</span><span class="sxs-lookup"><span data-stu-id="feaed-161">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="feaed-162">使用 pbit 文件的优点是它已建立连接字符串。</span><span class="sxs-lookup"><span data-stu-id="feaed-162">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="feaed-163">也可以利用已创建的所有自定义度量值，在基础架构所返回数据的基础上进一步进行构建。</span><span class="sxs-lookup"><span data-stu-id="feaed-163">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="feaed-164">您可以从[下载中心](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)下载 Microsoft 下载中心的 Power BI 模板文件。</span><span class="sxs-lookup"><span data-stu-id="feaed-164">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="feaed-165">下载 Power BI 模板文件后，请按照以下步骤开始：</span><span class="sxs-lookup"><span data-stu-id="feaed-165">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="feaed-166">打开 pbit 文件。</span><span class="sxs-lookup"><span data-stu-id="feaed-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="feaed-167">在对话框中输入租户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="feaed-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="feaed-169">收到提示时，输入您的管理员凭据以向 Microsoft 365 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="feaed-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="feaed-170">有关允许谁访问 Microsoft 365 使用情况分析报告的详细信息。</span><span class="sxs-lookup"><span data-stu-id="feaed-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="feaed-171">获得授权后，将刷新 Power BI 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="feaed-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="feaed-172">数据加载可能需要一些时间，完成加载后，可以将文件保存为 .pbix 文件，并继续自定义报表或向此报表添加其他数据源。</span><span class="sxs-lookup"><span data-stu-id="feaed-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="feaed-p106">请遵循[开始使用 Power BI](https://go.microsoft.com/fwlink/?linkid=849802) 文档，了解如何生成报表、将其发布到 Power BI 服务以及与组织共享。按照此路径进行自定义和共享可能需要其他 Power BI 许可证。请参阅 Power BI [授权指南](https://go.microsoft.com/fwlink/p/?linkid=849803)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="feaed-p106">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

