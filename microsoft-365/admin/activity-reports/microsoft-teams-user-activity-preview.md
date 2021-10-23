---
title: 管理中心中的 Microsoft 365 报表 - Microsoft Teams 用户活动
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 了解如何获取Microsoft Teams活动报告，并深入了解Teams活动。
ms.openlocfilehash: 6c30575cd333ea1ad161fceefcee4e8ba3737762
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553132"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>管理中心中的 Microsoft 365 报表 - Microsoft Teams 用户活动

"Microsoft 365 **报表**"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 用户活动报表中，可深入了解组织中的 Microsoft Teams 活动。
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何获取 Microsoft Teams 用户活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。
2. 在仪表板主页上，单击 **活动卡片上的**"查看更多Microsoft Teams按钮。

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解读 Microsoft Teams 用户活动报表

You can view the user activity in the Teams by choosing the **User activity** tab. <br/>![Microsoft 365报表 - Microsoft Teams活动。](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![Teams活动报表 - 选择列。](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

您还可以通过选择"导出"链接将报告数据导出到Excel .csv **文件**。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 音频时间 **、视频时间和** 屏幕共享时间导出的格式 **遵循** ISO8601 持续时间格式。

可查看" **Microsoft Teams 用户活动**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的某一天，则此表将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。

为了确保数据质量，我们将对过去三天执行每日数据有效性检查，并且将填补检测到的任何缺陷。 您可能会注意到过程中历史数据的差异。

|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。   <br/> |
|频道消息   <br/> |用户指定时段内在团队聊天中发布的唯一消息数。  <br/> |
|聊天消息   <br/> |用户指定的时间段在私人聊天中发布的唯一消息数。  <br/> |
|会议总数   <br/> |用户指定时间段参与的联机会议数。  <br/> |
|1：1 呼叫   <br/> | 用户在指定时段参与的 1：1 呼叫数。  <br/> |
|上次活动日期 (UTC)   <br/> |用户上次参与活动Microsoft Teams日期。<br/> |
|临时参与的会议   <br/> | 用户指定时间段参与临时会议的数量。  <br/> |
|临时组织的会议 <br/> |用户指定的时间段组织临时会议的数量。 <br/>|
|组织的会议总数  <br/> |用户指定的时间段组织的一次性计划会议、定期会议、临时会议和未分类会议的总和。  <br/> |
|参与的会议总数  <br/> |用户指定时间段参与的一次性计划、定期、临时和未分类会议的总和。  <br/> |
|安排的一次会议  <br/> |用户指定的时间段组织的一次计划会议的数量。  <br/> |
|安排定期会议  <br/> |用户指定的时间段组织的定期会议数。  <br/> |
|安排的会议一次参与  <br/> |用户在指定时段参与的一次计划会议的数量。  <br/> |
|已参与的计划定期会议  <br/> |用户指定的时间段参与的定期会议数。  <br/> |
|已授权  <br/> |如果用户已获得使用许可证，则选择Teams。 <br/>|
|其他活动  <br/>|用户处于活动状态，但执行了其他活动，而不是报告中提供的公开操作类型 (发送或回复频道消息和聊天消息、安排或参与一对一通话和会议) 。 示例操作包括用户更改Teams状态或Teams打开频道消息帖子但不回复的情况。  <br/>|
|未分类会议 <br/>|不能分类为计划、定期或临时的。 这些数量短，由于篡改的遥测信息，大多数无法识别。 |
|||
