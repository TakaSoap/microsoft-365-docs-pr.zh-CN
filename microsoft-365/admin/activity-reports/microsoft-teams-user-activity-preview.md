---
title: Microsoft 团队用户活动中的 microsoft 365 报告
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 了解如何获取 Microsoft 团队用户活动报告，并深入了解组织中的团队活动。
ms.openlocfilehash: 32252ed89dd9447b5df59ee733088349c559a320
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104506"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 团队用户活动中的 microsoft 365 报告

Microsoft 365 " **报告** " 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 用户活动报表中，可深入了解组织中的 Microsoft Teams 活动。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>如何获取 Microsoft Teams 用户活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。
2. 在仪表板主页中，单击 Microsoft 团队活动卡片上的 " **查看更多** " 按钮。
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>解读 Microsoft Teams 用户活动报表

您可以通过选择 " **用户活动** " 选项卡来查看团队报告中的用户活动。 <br/>![Microsoft 365 报表-Microsoft 团队用户活动。](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

选择 " **选择列** " 可在报告中添加或删除列。  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 **音频时间**、**视频时间**和**屏幕共享时间**的导出格式遵循 ISO8601 日期格式。

|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。   <br/> |
|通道邮件   <br/> |在指定时间段内用户在团队聊天中发布的唯一消息数。  <br/> |
|聊天消息   <br/> |在指定时间段内，用户在私人聊天中发布的唯一邮件数。  <br/> |
|会议总数   <br/> |用户在指定时间段内参与的联机会议的数量。  <br/> |
|1:1 调用   <br/> | 用户在指定时间段内参与的1:1 呼叫数。  <br/> |
| (UTC) 的上次活动日期  <br/> |用户参与 Microsoft 团队活动的最后日期。<br/> |
|会议是临时参与的   <br/> | 在指定时间段内用户参与的日历上未计划的会议数。  <br/> |
|以即席方式组织的会议 <br/> |在指定时间段内，用户组织的日历上未计划的会议数。 <br/>|
|安排的会议  <br/> |用户在指定时间段内组织的已安排会议数。  <br/> |
|已许可 |如果用户已被授权使用团队，则选择此选项。|
|其他活动|用户被视为处于活动状态，但其值为零：聊天消息、1:1 呼叫、频道消息、会议总数和会议组织的指标值。 示例操作是当用户打开频道消息 post 但不进行回复，或者当收到专用邮件且未响应时，将对其进行读取。 |
|||