---
title: 管理员中心的 Microsoft 365 报告-Yammer 组活动报告
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: 获取 Yammer 组活动报表，了解在您的组织中创建和使用的 Yammer 组的数目以及它们的活动。
ms.openlocfilehash: 0b7dbfe7b578987103c63a9975ea61eb442297e8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618928"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>管理员中心的 Microsoft 365 报告-Yammer 组活动报告

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看 [报表概述主题](activity-reports.md)。 在 Yammer 组活动报表中，可深入了解组织中 Yammer 组的活动并查看创建和使用了多少个 Yammer 组。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>如何获取 Yammer 组活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报表**" 下拉下，选择 " **Yammer** \> **组活动**"。
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Yammer 组活动报表说明

可通过查看" **组** "和" **活动** "图表，了解 Yammer 组活动。<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **Yammer 组活动** "报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。 <br/> |
|3.  <br/> |" **组** "视图显示已存在的总组数以及执行了组会话活动的组数。  <br/> |
|4.  <br/> |" **活动** "视图显示在组中发布、阅读及点赞的 Yammer 消息数。  <br/> |
|5.  <br/> | 在" **组** "图表中，Y 轴表示总组数或活动组数。  <br/>  在" **活动** "图表，Y 轴表示 Yammer 组的特定活动数。  <br/>  三个图表的 X 轴都表示为此特定报表选定的日期范围。  <br/> |
|6.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**组**" 图表中，选择 "**总计**" 或 "**活动**  ![的汇总" 和 "活动的图标"，只查看与每个图标](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png)相关的信息。 更改选择不会更改网格表中的信息。  <br/> |
|7.  <br/> | 显示的组列表由最大（180天）报表时间范围内存在的（未删除）所有组来确定。 活动计数（已收到的邮件）可能因日期选择不同而有所变化。  <br/> 注意：在添加之前，可能无法在列中看到以下列表中的所有项。<br/>" **组名** "表示组的名称。  <br/> " **组管理员** "表示组管理员或所有者的姓名。  <br/> " **已删除** "表示已删除的 Yammer 组数。如果该组被删除，但在报告时间段中有活动，它将显示在网格中，并显示设置为 true 的标记。  <br/> " **类型** "表示组的类型：公共类或专用类  <br/> **连接到 Office 365**指示 Yammer 组是否也是 Microsoft 365 组。  <br/> "**上次活动日期**" 是邮件被阅读、投递或赞的最晚日期。  <br/> " **成员** "表示组中的成员人数。  <br/> " **已发布** "表示报告时间段内 Yammer 组中发布的消息数。  <br/> " **已读** "表示报告时间段内 Yammer 组中的已读消息数。  <br/> " **已赞** "表示报告时间段内 Yammer 组中的已赞消息数。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告中](activity-reports.md)的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|8.  <br/> |选择要在报告中添加或删除列的**列**。  <br/> ![Yammer groups activity - choose columns](../../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

