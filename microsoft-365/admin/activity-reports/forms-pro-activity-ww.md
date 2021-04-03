---
title: 管理中心中的 Microsoft 365 报表 - Dynamics 365 客户语音活动
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
description: 了解如何使用 Microsoft 365 管理中心中的 Microsoft 365 报告仪表板获取 Microsoft Dynamics 365 客户语音活动报告。
ms.openlocfilehash: 1647379216d5021ab3fa6b55f1c5f32f57cdac91
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579658"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>管理中心中的 Microsoft 365 报表 - Dynamics 365 客户语音活动

Microsoft 365 **报表** 仪表板显示组织中各产品的活动概述。 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，通过查看每个授权使用 Microsoft Dynamics 365 客户语音的用户与 Dynamics 365 客户语音的交互，可以了解他们的活动。 它还通过查看用户所回复的"专业调查"和"专业调查"数量，帮助您了解进行协作的级别。 
  
> [!NOTE]
> 你必须是 Microsoft 365 中的全局管理员、全局读者或报告读者，或者 Exchange、SharePoint、Teams 服务、Teams 通信或 Skype for Business 管理员才能查看报告。  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>如何访问 Dynamics 365 客户语音活动报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 Dynamics 365 客户语音卡上的"查看更多"按钮。 
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>解释 Dynamics 365 客户语音活动报告

You can view the activities in the Dynamics 365 Customer Voice report by choosing the **Activity** tab.<br/>![Microsoft 365 报告 - Microsoft Dynamics 365 客户语音活动报告。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![Dynamics 365 客户语音活动报告 - 选择列](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

您还可以通过选择"导出"链接将报告数据导出到 Excel .csv **文件中。** 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |在 Microsoft Forms 上执行活动的用户的电子邮件地址。  <br/> |
|上次活动日期 (UTC)   <br/> |用户对所选日期范围执行表单活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/>这将筛选该表，以仅显示特定天执行活动的用户的文件活动数据。  <br/> |
|创建的调查数量  <br/> |用户创建的调查数量。   <br/> |
|调查答复数  <br/> |向其中分发调查的响应者的响应数。|
|||