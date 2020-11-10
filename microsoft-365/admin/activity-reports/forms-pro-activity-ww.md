---
title: Microsoft 365 在管理中心中报告-Dynamics 365 客户语音活动
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 了解如何使用 Microsoft 365 管理中心中的 Microsoft 365 报告仪表板获取 Microsoft Dynamics 365 客户语音活动报告。
ms.openlocfilehash: 0a854c7a89977a96e11d8ec28fd7789e8418c1cf
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988899"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365 在管理中心中报告-Dynamics 365 客户语音活动

Microsoft 365 " **报告** " 仪表板显示组织中各产品的活动概述。 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，您可以通过查看与 Dynamics 365 客户语音的交互，了解使用 Microsoft Dynamics 365 客户语音的每个用户的活动。 它还可以通过查看创建的 Pro 调查数和用户响应的 Pro 调查，来帮助您了解协作的级别。 
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  
 
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>如何获取 Dynamics 365 客户语音活动报告

1. 在管理中心，转到“ **报表** ”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页中，单击 Dynamics 365 Customer Voice 卡片上的 " **查看更多** " 按钮。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>解释 Dynamics 365 Customer Voice 活动报告

您可以通过选择 " **活动** " 选项卡来查看 Dynamics 365 客户语音报告中的活动。<br/>![Microsoft 365 报告-Microsoft Dynamics 365 客户语音活动报告。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

选择 " **选择列** " 可在报告中添加或删除列。  <br/> ![Dynamics 365 客户语音活动报告-选择列](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

您还可以通过选择 " **导出** " 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |在 Microsoft 表单上执行活动的用户的电子邮件地址。  <br/> |
| (UTC) 的上次活动日期  <br/> |上次用户在所选日期范围内执行表单活动的日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/>此操作将筛选表，以便仅为在特定日期执行活动的用户显示文件活动数据。  <br/> |
|已创建调查的数量  <br/> |用户创建的调查数。   <br/> |
|调查响应的数量  <br/> |调查向其分配到的响应者的响应数。|
|||