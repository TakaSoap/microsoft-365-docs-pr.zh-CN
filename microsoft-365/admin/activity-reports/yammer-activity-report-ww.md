---
title: 管理中心中的 Microsoft 365 报表 - Yammer 活动报告
f1.keywords:
- NOCSH
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 获取 Yammer 活动报告，详细了解使用 Yammer 发布、喜欢或阅读消息的用户数量。
ms.openlocfilehash: 636e5fae9a71fc819a032743e06127dace25f0a4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579490"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>管理中心中的 Microsoft 365 报表 - Yammer 活动报告

作为 Microsoft 365管理员，"报告"仪表板将显示有关组织中产品使用情况的数据。 查看 [管理中心中的活动报告](activity-reports.md)。 使用" **Yammer 活动报表** "，可以通过查看使用 Yammer 发布、点赞或阅读消息的唯一用户数以及组织中生成的活动数来了解使用 Yammer 的组织的参与级别。 
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>如何访问 Yammer 活动报告？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 Yammer **卡上的"** 查看更多"按钮。

  
## <a name="interpret-the-yammer-activity-report"></a>Yammer 活动报表说明

You can view the activities in the Yammer report by choosing the **Activity** tab.<br/>![Microsoft 365 报表 - Microsoft Yammer 活动报告。](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![Yammer 活动报告 - 选择列](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。 此网格显示使用 Microsoft 365 帐户登录 Yammer 的用户，或者使用单一登录登录网络的用户。 <br/> |
|显示名称  <br/> |用户的全名。 可以显示实际的电子邮件地址或采用匿名字段。  <br/> |
|用户状态  <br/> |三个值之一：Activated、Deleted 或 Suspended。 这些报表显示已激活、已挂起和已删除用户的数据。 报表并不反映待定用户，因为待定用户无法发布、阅读或点赞消息。  <br/> |
|UTC 时间 (状态)   <br/> |Yammer 中更改用户状态的日期。  <br/> |
|上次活动日期 (UTC)   <br/> | 用户发布、阅读或点帖消息的最后日期。  <br/> |
|已发布  <br/> |用户指定的时间段内发布的消息数。 <br/>|
|阅读  <br/> |用户指定的时间段读取的对话数。  <br/> |
|已赞  <br/> |用户指定的时间段内喜欢的消息数。  <br/>|
|分配的产品  <br/> |分配给此用户的产品。|
|||