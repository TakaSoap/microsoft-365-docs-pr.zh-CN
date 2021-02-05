---
title: 自定义 Microsoft 365 使用情况分析中的报告
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 了解如何在浏览器和 Power BI Desktop 中自定义报告。
ms.openlocfilehash: 0375b61b6922c99acf927a4283571451deabaf14
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114293"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="17e29-103">自定义 Microsoft 365 使用情况分析中的报告</span><span class="sxs-lookup"><span data-stu-id="17e29-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="17e29-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="17e29-104">The admin center is changing.</span></span> <span data-ttu-id="17e29-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="17e29-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="17e29-106">Microsoft 365 使用情况分析在 Power BI 中提供了一个仪表板，可提供用户采用和使用 Microsoft 365 的见解。</span><span class="sxs-lookup"><span data-stu-id="17e29-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="17e29-107">这个仪表板只是与使用情况数据进行交互的起点。</span><span class="sxs-lookup"><span data-stu-id="17e29-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="17e29-108">可以自定义报表，从而获得更加个性化的见解。</span><span class="sxs-lookup"><span data-stu-id="17e29-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="17e29-109">还可以使用 Power BI Desktop 将报表连接到其他数据源来进一步自定义报表，以获得有关业务的更加丰富的见解。</span><span class="sxs-lookup"><span data-stu-id="17e29-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="17e29-110">在浏览器中自定义报表</span><span class="sxs-lookup"><span data-stu-id="17e29-110">Customizing reports in the browser</span></span>

<span data-ttu-id="17e29-111">以下两个示例显示了如何修改现有视觉对象以及如何创建新的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="17e29-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="17e29-112">修改现有视觉对象</span><span class="sxs-lookup"><span data-stu-id="17e29-112">Modify an existing visual</span></span>

<span data-ttu-id="17e29-113">此示例演示如何修改激活/许可报告中的 **"激活"选项卡**。</span><span class="sxs-lookup"><span data-stu-id="17e29-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="17e29-114">在 **"激活/许可"** 报告中，选择"激活 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="17e29-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="17e29-115">通过选择顶部的"编辑"按钮，通过 Power BI 按钮中的"更多页面"按钮进入 ![ 编辑 ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 模式。</span><span class="sxs-lookup"><span data-stu-id="17e29-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="17e29-117">在右上方，选择 **"复制此页"。**</span><span class="sxs-lookup"><span data-stu-id="17e29-117">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="17e29-119">在右下角，选择显示基于操作系统（如 Android、iOS、Mac 等）激活的用户数的任何条形图。</span><span class="sxs-lookup"><span data-stu-id="17e29-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="17e29-120">在 **右侧"** 可视化"区域中，若要从视觉对象中删除 **Mac Count，** 请选择其旁边的 **X。**</span><span class="sxs-lookup"><span data-stu-id="17e29-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![删除 Mac 计数](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="17e29-122">创建新的视觉对象</span><span class="sxs-lookup"><span data-stu-id="17e29-122">Create a new visual</span></span>

<span data-ttu-id="17e29-123">以下示例演示如何创建新的视觉对象，以按月跟踪新的 Yammer 用户。</span><span class="sxs-lookup"><span data-stu-id="17e29-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="17e29-124">使用左侧 **导航转到"产品** 使用情况"报告，然后选择 **"Yammer"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="17e29-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="17e29-125">通过选择 Power BI 中的"更多页面"按钮切换到 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 编辑 **模式**。</span><span class="sxs-lookup"><span data-stu-id="17e29-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="17e29-126">在页面底部，选择</span><span class="sxs-lookup"><span data-stu-id="17e29-126">At the bottom of the page, select the</span></span> ![Power BI 中的"添加页面"按钮](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="17e29-128">以创建新页面。</span><span class="sxs-lookup"><span data-stu-id="17e29-128">to create a new page.</span></span>
  
4. <span data-ttu-id="17e29-129">在 **右边的"** 可视化"区域中，从 (上一行选择堆积条形图) 。</span><span class="sxs-lookup"><span data-stu-id="17e29-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![选择条形图](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="17e29-131">选择该可视化效果的右下角并拖动使其变大。</span><span class="sxs-lookup"><span data-stu-id="17e29-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="17e29-132">在 **右侧"** 域"区域中，展开 **"日历"** 表。</span><span class="sxs-lookup"><span data-stu-id="17e29-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="17e29-133">将" **MonthName**"拖动到字段区域，该区域位于" **可视化效果**"区域中" **坐标轴**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="17e29-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![拖动月份名称](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="17e29-135">在右侧的" **字段**"区域中，展开" **TenantProductUsage**"表。</span><span class="sxs-lookup"><span data-stu-id="17e29-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="17e29-136">将" **FirstTimeUsers**"拖动到字段区域，该区域位于" **值**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="17e29-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="17e29-137">将" **产品**"拖动到" **筛选器**"区域，该区域位于" **视觉级筛选器**"标题的正下方。</span><span class="sxs-lookup"><span data-stu-id="17e29-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="17e29-138">在出现的" **筛选器类型**"区域中，选中" **Yammer**"复选框。</span><span class="sxs-lookup"><span data-stu-id="17e29-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![选中 Yammer 复选框](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="17e29-140">在可视化效果列表正下方，选择 Power  BI Visualizaions 中的"格式"图标" ![ 格式"图标 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。</span><span class="sxs-lookup"><span data-stu-id="17e29-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="17e29-141">展开标题并将" **标题文本**"值更改为" **每月首次使用 Yammer 的用户**"。</span><span class="sxs-lookup"><span data-stu-id="17e29-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="17e29-142">将" **文本大小**"值更改为" **12**"。</span><span class="sxs-lookup"><span data-stu-id="17e29-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="17e29-143">通过编辑右下角页面的名称来更改新页面的标题。</span><span class="sxs-lookup"><span data-stu-id="17e29-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="17e29-144">单击顶部的阅读视图，然后保存，以保存 **报告**。</span><span class="sxs-lookup"><span data-stu-id="17e29-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="17e29-145">自定义 Power BI Desktop 中的报表</span><span class="sxs-lookup"><span data-stu-id="17e29-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="17e29-p103">对于大多数客户而言，在 Power BI Web 版中修改报表和图表视觉对象已经足够。但是，对于某些客户而言，可能需要将此数据与其他数据源联接，以获得与其业务上下文有关的更加丰富的见解，在这种情况下，可以使用 Power BI Desktop 自定义并生成其他报表。可以免费下载 [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797)。</span><span class="sxs-lookup"><span data-stu-id="17e29-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="17e29-149">使用报告 API</span><span class="sxs-lookup"><span data-stu-id="17e29-149">Use the reporting APIs</span></span>

<span data-ttu-id="17e29-150">你可以从支持这些报告的 Microsoft 365 直接连接到 ODATA 报告 API 开始。</span><span class="sxs-lookup"><span data-stu-id="17e29-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="17e29-151">转到" **获取数据**"\>" **其他**"\>" **ODATA 源**"\>" **连接**"。</span><span class="sxs-lookup"><span data-stu-id="17e29-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="17e29-152">在 URL 窗口中输入 <i></i> \<tenantid\> "https://reports.office.com/pbi/v1.0/"</span><span class="sxs-lookup"><span data-stu-id="17e29-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="17e29-153">**注意：** 报告 API 为预览版，在进入生产阶段之前可能会更改。</span><span class="sxs-lookup"><span data-stu-id="17e29-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="17e29-155">输入你的 Microsoft 365 (或学校) 管理员凭据，以在系统提示时向 Microsoft 365 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="17e29-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="17e29-156">有关 [允许](usage-analytics.md#faq) 谁访问 Microsoft 365 Adoption 模板应用报告详细信息，请参阅常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="17e29-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="17e29-157">授权连接后，将看到显示可连接到的数据集的"导航器"窗口。</span><span class="sxs-lookup"><span data-stu-id="17e29-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="17e29-158">全选，然后选择"**加载"。**</span><span class="sxs-lookup"><span data-stu-id="17e29-158">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="17e29-159">这会将数据下载到 Power BI Desktop。</span><span class="sxs-lookup"><span data-stu-id="17e29-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="17e29-160">保存该文件，然后可以开始创建所需报表。</span><span class="sxs-lookup"><span data-stu-id="17e29-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![报告 API 中提供的 ODATA 值](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="17e29-162">使用 Microsoft 365 使用情况分析模板</span><span class="sxs-lookup"><span data-stu-id="17e29-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="17e29-163">您还可以使用与 Microsoft 365 使用情况分析报告对应的 Power BI 模板文件作为连接到数据的起点。</span><span class="sxs-lookup"><span data-stu-id="17e29-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="17e29-164">使用 pbit 文件的优点是它已建立连接字符串。</span><span class="sxs-lookup"><span data-stu-id="17e29-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="17e29-165">也可以利用已创建的所有自定义度量值，在基础架构所返回数据的基础上进一步进行构建。</span><span class="sxs-lookup"><span data-stu-id="17e29-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="17e29-166">可以从 Microsoft 下载中心从下载中心下载 Power BI [模板文件](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)。</span><span class="sxs-lookup"><span data-stu-id="17e29-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="17e29-167">下载 Power BI 模板文件后，请按照以下步骤开始：</span><span class="sxs-lookup"><span data-stu-id="17e29-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="17e29-168">打开 pbit 文件。</span><span class="sxs-lookup"><span data-stu-id="17e29-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="17e29-169">在对话框中输入租户 ID 值。</span><span class="sxs-lookup"><span data-stu-id="17e29-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="17e29-171">输入管理员凭据，在系统提示时向 Microsoft 365 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="17e29-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="17e29-172">有关允许谁访问 Microsoft 365 使用情况分析报告的信息。</span><span class="sxs-lookup"><span data-stu-id="17e29-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="17e29-173">获得授权后，将刷新 Power BI 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="17e29-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="17e29-174">数据加载可能需要一些时间，完成加载后，可以将文件保存为 .pbix 文件，并继续自定义报表或向此报表添加其他数据源。</span><span class="sxs-lookup"><span data-stu-id="17e29-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="17e29-p107">请遵循[开始使用 Power BI](https://go.microsoft.com/fwlink/?linkid=849802) 文档，了解如何生成报表、将其发布到 Power BI 服务以及与组织共享。按照此路径进行自定义和共享可能需要其他 Power BI 许可证。请参阅 Power BI [授权指南](https://go.microsoft.com/fwlink/p/?linkid=849803)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="17e29-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

