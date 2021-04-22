---
title: 管理中心中的 Microsoft 365 报表 - Microsoft 365 组
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: 获取 Microsoft 365 组报告，了解组及其活动。
ms.openlocfilehash: d123e3beb55ba6e636084fabe995f4dd0ff56707
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939134"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>管理中心中的 Microsoft 365 报表 - Microsoft 365 组

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft 365 组报告中，你可以深入了解组织中组的活动，并查看创建和使用的组数。
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。  
  
## <a name="how-to-get-to-the-groups-report"></a>如何访问组报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

2. 从选项中选择" **活动用户** **- Microsoft 365** 服务"下的"查看更多"。
3. 从"**选择报告"** 下拉列表中，选择 **"Office 365** \> **组活动"。**
  
## <a name="interpret-the-groups-report"></a>解释组报告

可以通过查看组、活动、文件和存储图表获取 **组活动的视图**。    
  
![Microsoft 365 报告 - 组活动](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|Item|说明|
|:-----|:-----|
|1.  <br/> |可查看 **Microsoft 365** 组报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的特定日期，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。  <br/> |
|2.  <br/> |每个报告中的数据通常涵盖过去 24 至 48 小时的数据。  <br/> |
|3.  <br/> |" **组** "视图根据查看的电子邮件对话、Yammer 帖子和 SharePoint 文件活动和 SharePoint 页面显示任何给定天中存在的组总数以及该天的活动组数。  <br/> |
|4.  <br/> |" **活动** "视图显示组工作负荷下的组活动数。 可以查看在报告时段内任意一天所有组的组邮箱接收到的 Exchange 电子邮件。 还可以查看跨与组关联的 Yammer 组发布、阅读和点帖的消息。 <br/> |
|5.  <br/> |" **文件** "视图显示与组关联的所有组网站中的总文件和活动文件数。  <br/> |
|6.  <br/> |" **存储** "视图显示所有组邮箱和组网站上使用的存储总量。  <br/> |
|7.  <br/> | 在" **组** "图表上，Y 轴表示组的数量（可以视为总数或活动组数）。  <br/>  在 **"活动** "图表上，Y 轴表示在组中执行活动次数。  <br/>  在" **文件** "图表上，Y 轴表示文件总数或活动文件数。  <br/>  在" **存储** "图表上，Y 轴表示组邮箱或网站使用的总存储。  <br/>  三个图表的 X 轴都表示为此特定报表选定的日期范围。  <br/> |
|8.  <br/> |通过选择图例中的项目，可以筛选在图表上看到的系列。 例如，在"组 **"** 图表上，选择"组总数"或"活动总数"和"活动组数"，以仅 ![ ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) 查看与每个组有关的信息。 更改选择不会更改网格表中的信息。  <br/> |
|9.  <br/> | 显示的组列表由最大（180 天）报告时间范围内存在的（未删除）所有组确定。活动计数（电子邮件对话、 Yammer 帖子和 SharePoint 文件活动）会因日期选择不同而有所变化。  <br/> 注意：在添加以下列表中的所有项目之前，可能不会在列中看到这些项目。<br/>" **组名** "表示组的名称。  <br/> " **已删除** "表示已删除的组数。如果该组被删除，但在报告时段中有活动，它将显示在网格中，并显示设置为 true 的标记。  <br/> " **组所有者** "表示组所有者的姓名。  <br/> **上次活动** 日期是组收到邮件的最近日期。 - 这是电子邮件对话、Yammer 或网站中活动发生的最新日期。  <br/> " **类型** "表示组的类型。可以是私有组，也可以是公用组。  <br/> " **成员** "表示组中的成员人数。  <br/> " **外部成员** "是该组中外部用户的数量。  <br/> **Exchange** <br/> " **收到的电子邮件** "表示组收到的邮件数。  <br/> " **邮箱总项目数** "表示组邮箱中的项目数。  <br/> " **使用的邮箱存储** "表示组邮箱使用的存储。  <br/> **SharePoint 文件** <br/> " **文件总数** "表示 SharePoint 组网站中存储的文件数。  <br/> " **活动文件** "表示报告时段内在 SharePoint 组网站中对其执行操作（查看或修改、同步、内部或外部共享）的文件数  <br/> " **使用的网站存储(MB)** "表示报告时段内使用的存储量（以 MB 为单位）。  <br/> **Yammer 消息** <br/> " **已发布** "表示报告时间段内 Yammer 组中发布的消息数。  <br/> " **已读** "表示报告时间段内 Yammer 组中的已读消息数。  <br/> " **已赞** "表示报告时间段内 Yammer 组中的已赞消息数。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看 Microsoft  [365](activity-reports.md)管理中心的活动报告中的如何隐藏用户级别详细信息？部分。  <br/> |
|10,  <br/> |选择或点击 **列标题** 旁边的"更多操作"按钮"移动 OWA 更多操作"， ![ 以在报表中添加 ](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) 或删除列。  <br/> ![组报告 - 选择列](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|11,  <br/> |您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||


