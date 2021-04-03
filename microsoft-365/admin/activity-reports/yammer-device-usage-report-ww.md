---
title: 管理中心中的 Microsoft 365 报表 - Yammer 设备使用情况报告
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
description: 获取 Yammer 设备使用情况报告，了解用户正在使用 Yammer 的设备。
ms.openlocfilehash: 01749c21dd0f8355556718ee9179244fb250c97a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579466"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-device-usage-report"></a>管理中心中的 Microsoft 365 报表 - Yammer 设备使用情况报告

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
利用 Yammer 设备使用情况报表，了解你的用户正在哪些设备上使用 Yammer。可按设备类型查看每日用户数并按设备类型查看用户数。可查看所选时间段内的这两方面情况。也可查看每个用户的详细信息。
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。  
 
## <a name="how-do-i-get-to-the-yammer-device-usage-report"></a>如何获取 Yammer 设备使用情况报表？

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 Yammer **卡上的"** 查看更多"按钮。
  
## <a name="interpret-the-yammer-device-usage-report"></a>解释 Yammer 设备使用情况报告

You can view the usage in the OneDrive report by choosing the **Device usage** tab.<br/>![Microsoft 365 报告 - Microsoft Yammer 设备使用情况报告。](../../media/e21af4c0-0ad2-4485-8ab1-2f82d7dfa90e.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![Yammer 设备使用情况报告 - 选择列](../../media/fc1fc8db-e197-4878-85c7-7ba0d67b9379.png)

您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。 此网格显示使用 Microsoft 365 帐户登录 Yammer 的用户，或者使用单一登录登录网络的用户。 <br/> |
|显示名称  <br/> |用户的全名。 可以显示实际的电子邮件地址或采用匿名字段。  <br/> |
|用户状态  <br/> |三个值之一：Active、Deleted 或 Suspended。 这些报表显示已激活、已挂起和已删除用户的数据。 报表并不反映待定用户，因为待定用户无法发布、阅读或点赞消息。   <br/> |
|UTC 时间 (状态)   <br/> |Yammer 中更改用户状态的日期。  <br/> |
|上次活动日期 (UTC)   <br/> |用户参与 Yammer (的最后) UTC 日期。  <br/> |
|Web  <br/> |指示用户是否使用过 Web 上的 Yammer。  <br/> |
|Windows Phone  <br/> | 指示用户是否使用 Windows 手机上的 Yammer。  <br/> |
|Android 手机  <br/> |指示用户是否使用 Android 手机上的 Yammer。 <br/>|
|iphone <br/> | 指示用户是否使用 iPhone 上的 Yammer。  <br/> |
|ipad  <br/> |指示用户是否使用 iPad 上的 Yammer。 <br/>|
|other  <br/> |指示用户是否在另一台设备上使用过 Yammer，之前未列出。 <br/>|
|||