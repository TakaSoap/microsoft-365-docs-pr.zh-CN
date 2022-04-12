---
title: Microsoft 365 管理中心组报表
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: 获取Microsoft 365组报告以了解这些组及其活动。
ms.openlocfilehash: d4130d577341bbc8c4516234964ea9e805be81ee
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781668"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365管理中心中的报表 - Microsoft 365组

Microsoft 365报表仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在Microsoft 365组报表中，可以深入了解组织中组的活动，并了解正在创建和使用的组数。
  
## <a name="how-to-get-to-the-groups-report"></a>如何访问组报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

2. 在仪表板主页上，单击活动用户（Microsoft 365 应用版或活动用户）上的“**查看更多**”按钮Microsoft 365服务卡，以访问Office 365报表页。
  
## <a name="interpret-the-groups-report"></a>解释组报表

可以通过选择“**组活动**”选项卡来查看Office 365报表中的激活。

:::image type="content" alt-text="Microsoft 365报表 - Microsoft Office 365组活动。" source="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png" lightbox="../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png":::

选择 **要** 从报表中添加或删除列的列。

:::image type="content" alt-text="Office 365组活动报表 - 选择列。" source="../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png":::

还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可以查看 **这些组** 报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果在报表中选择特定日期，表将显示自当前日期（而不是生成报 (表) 日期）最多 28 天的数据。

|跃点数|定义|
|:-----|:-----|
|组名称 |组的名称。 |
|Deleted |已删除的组数。 如果该组被删除，但在报告时间段中有活动，它将显示在网格中，并显示设置为 true 的标记。 |
|组所有者 |组所有者的名称。 |
|上次活动日期 (UTC)  |组收到消息的最新日期。 - 这是在电子邮件对话、Yammer或网站中发生的活动的最新日期。 |
|类型 |组的类型。 可以是私有组，也可以是公用组。 |
|在Exchange中收到的电子邮件 |组接收的消息数。|
|Exchange (总) 中的电子邮件 |组邮箱中的项目总数。 |
|用于Exchange (MB) 的邮箱存储 |组邮箱使用的存储。 |
|SharePoint文件 (总)  |存储在SharePoint组站点中的文件数。 |
|SharePoint文件 (活动)  |SharePoint组网站中针对在报告期间内在内部或外部) 查看或修改、同步、共享 (的文件数。 |
|用于SharePoint (MB) 的站点存储总数 |报告期间使用的存储量（以 MB 为单位）。 |
|已发布) Yammer (消息 |报告期间在Yammer组中发布的消息数。 |
|Yammer (读取) 中的消息 |报告期间在Yammer组中读取的对话数。 |
|Yammer (中的消息喜欢)  |报告期间Yammer组中喜欢的消息数。 |
|Members |组中的成员数。 |
|外部成员 |组中的外部用户数。|


## <a name="related-content"></a>相关内容

[Microsoft 365管理中心中的报](activity-reports.md)表 (文章) \
[安全&合规中心中的智能报表和见解 (](/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance) 文章) \
[Microsoft 365管理中心中的报表 - 活动用户](../../admin/activity-reports/active-users-ww.md) (文章) 

