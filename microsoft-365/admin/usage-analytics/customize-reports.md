---
title: 自定义使用情况Microsoft 365中的报告
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 了解如何在浏览器和浏览器中自定义Power BI Desktop。
ms.openlocfilehash: 32cf44c8d72160a583a841e26c2ad6934bd7eef2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175727"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>自定义使用情况Microsoft 365中的报告

Microsoft 365使用情况分析提供了一个Power BI仪表板，可深入了解用户如何采用和使用Microsoft 365。 这个仪表板只是与使用情况数据进行交互的起点。 可以自定义报表，从而获得更加个性化的见解。

还可以使用 Power BI Desktop 将报表连接到其他数据源来进一步自定义报表，以获得有关业务的更加丰富的见解。

## <a name="customizing-reports-in-the-browser"></a>在浏览器中自定义报表

以下两个示例显示了如何修改现有视觉对象以及如何创建新的视觉对象。

### <a name="modify-an-existing-visual"></a>修改现有视觉对象

本示例演示如何修改"激活/许可 **"** 报告中 **的"激活"选项卡** 。

1. 在" **激活/许可"** 报告中，选择" **激活"** 选项卡。

2. 通过选择顶部的"编辑 **"** 按钮，通过"编辑"按钮进入编辑 ![ Power BI。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 按钮。

    ![单击右上方导航栏上的"编辑报表"。](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. 在右上方，选择"**复制此页面"。**

    ![选择"复制此页"。](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. 在右下角，选择显示基于操作系统（如 Android、iOS、Mac 等）激活的用户数的任何条形图。

5. 在 **右侧"可视化"** 区域中，若要从视觉对象中删除 **Mac Count，** 请选择它旁边的 **X。**

    ![删除 Mac 计数。](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>创建新的视觉对象

以下示例演示如何创建新的视觉对象，以按月跟踪新的 Yammer 用户。

1. 使用左侧 **导航导航** 转到"产品使用情况"报告，**然后选择"Yammer** 选项卡。

2. 通过选择"编辑模式"中的 ![ "更多页面"按钮切换到Power BI。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 和编辑。

3. 在页面底部，选择 ![页面中的"添加页面"Power BI。](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) 创建新页面。

4. 在右侧 **"可视化"** 区域中，选择最上面 (的堆积条形图，从左到左) 。

    ![选择"条形图"。](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. 选择可视化效果的右下角，并拖动使其变大。

6. 在右侧 **"字段** "区域中，展开 **"日历"** 表。

7. 将" **MonthName**"拖动到字段区域，该区域位于" **可视化效果**"区域中" **坐标轴**"标题的正下方。

    ![拖动"月份名称"。](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. 在右侧的" **字段**"区域中，展开" **TenantProductUsage**"表。

9. 将" **FirstTimeUsers**"拖动到字段区域，该区域位于" **值**"标题的正下方。

10. 将" **产品**"拖动到" **筛选器**"区域，该区域位于" **视觉级筛选器**"标题的正下方。

11. 在出现的" **筛选器类型**"区域中，选中" **Yammer**"复选框。

    ![选中Yammer复选框。](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. 在可视化效果列表正下方，选择 Visualizaions 中的"格式"Power BI ![ 图标 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。。

13. 展开标题并将" **标题文本**"值更改为" **每月首次使用 Yammer 的用户**"。

14. 将" **文本大小**"值更改为" **12**"。

15. 通过编辑右下角页面的名称来更改新页面的标题。

16. 单击顶部的"阅读视图"，然后单击"保存"，以保存 **报告**。

## <a name="customizing-the-reports-in-power-bi-desktop"></a>自定义 Power BI Desktop 中的报表

对于大多数客户而言，在 Power BI Web 版中修改报表和图表视觉对象已经足够。但是，对于某些客户而言，可能需要将此数据与其他数据源联接，以获得与其业务上下文有关的更加丰富的见解，在这种情况下，可以使用 Power BI Desktop 自定义并生成其他报表。可以免费下载 [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797)。

### <a name="use-the-reporting-apis"></a>使用报告 API

你可以从为这些报告提供Microsoft 365直接连接到 ODATA 报告 API。

1. 转到" **获取数据**"\>" **其他**"\>" **ODATA 源**"\>" **连接**"。

2. 在"URL"窗口中，输入 <i></i> "https:// reports.office.com/pbi/v1.0/" \<tenantid\>

    **注意：** 报告 API 为预览版，在进入生产阶段之前可能会更改。

    ![桌面版 OData Power BI URL。](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. 输入你的Microsoft 365 (或学校) 管理员凭据，以在Microsoft 365时进行身份验证。

    有关[允许](usage-analytics.md#faq)谁访问应用采用模板应用报告Microsoft 365常见问题解答。

4. 授权连接后，将看到显示可连接到的数据集的"导航器"窗口。

    全选 **，然后选择加载**。

    这会将数据下载到 Power BI Desktop。保存该文件，然后可以开始创建所需报表。

    ![报告 API 中提供的 ODATA 值。](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>使用Microsoft 365分析模板

您还可以使用与Power BI使用情况分析报告相对应的 Microsoft 365 模板文件作为连接数据的起点。 使用 pbit 文件的优点是它已建立连接字符串。 也可以利用已创建的所有自定义度量值，在基础架构所返回数据的基础上进一步进行构建。

可以从 Microsoft Power BI下载模板[文件](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)。 下载模板Power BI后，请按照以下步骤开始：

1. 打开 pbit 文件。

2. 在对话框中输入租户 ID 值。

    ![输入租户 ID 以打开 pbit 文件。](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. 输入管理员凭据以在系统Microsoft 365进行身份验证。

     有关允许谁访问使用情况分析Microsoft 365详细信息。

    获得授权后，将刷新 Power BI 文件中的数据。

    数据加载可能需要一些时间，完成加载后，可以将文件保存为 .pbix 文件，并继续自定义报表或向此报表添加其他数据源。

4. 请遵循[开始使用 Power BI](/power-bi/fundamentals/desktop-getting-started) 文档，了解如何生成报表、将其发布到 Power BI 服务以及与组织共享。按照此路径进行自定义和共享可能需要其他 Power BI 许可证。请参阅 Power BI [授权指南](https://go.microsoft.com/fwlink/p/?linkid=849803)了解详细信息。
