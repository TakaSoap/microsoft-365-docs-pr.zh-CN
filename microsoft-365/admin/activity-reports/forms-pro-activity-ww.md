---
title: Microsoft Dynamics 365 客户语音活动报告
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 了解如何使用Microsoft 365 管理中心中的“Microsoft 365报表”仪表板获取 Microsoft Dynamics 365 客户语音活动报表。
ms.openlocfilehash: 19e2a0d0514b9d5722ec9649c08a4d6a97025873
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781942"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365管理中心中的报表 - Dynamics 365 客户语音活动

Microsoft 365报表仪表板显示组织中各产品的活动概述。 让用户深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，通过查看每个获得 Microsoft Dynamics 365 客户语音许可的用户与 Dynamics 365 客户语音的交互，可以了解其活动。 它还通过查看创建的Pro调查的数量并Pro用户响应的调查，帮助你了解协作级别。 
  
## <a name="how-to-get-to-the-dynamics-365-customer-voice-activity-report"></a>如何访问 Dynamics 365 客户语音活动报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 Dynamics 365 客户语音卡上的 **“查看更多** ”按钮。
  
## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>解释 Dynamics 365 客户语音活动报告

可以通过选择“活动”选项卡来查看 Dynamics 365 客户语音报表中的 **活动** 。<br/>![Microsoft 365报表 - Microsoft Dynamics 365 客户语音活动报告。](../../media/a7e57d18-1ac8-4d4b-bd70-83361505dc3e.png)

选择 **要** 从报表中添加或删除列的列。  <br/> ![Dynamics 365 客户语音活动报告 - 选择列。](../../media/5ab66f4b-32eb-4c9b-9683-1157ae9e2c0a.png)

还可以通过选择“**导** 出”链接将报表数据导出到Excel .csv文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可以查看 **Dynamics 365 客户语音活动** 报告，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果在报表中选择特定日期，表将显示自当前日期（而不是生成报 (表) 日期）最多 28 天的数据。
  
|Item|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |在Microsoft Forms上执行活动的用户的电子邮件地址。  <br/> |
|上次活动日期 (UTC)   <br/> |用户为所选日期范围执行了表单活动的最新日期。 要查看指定日期发生的活动，请直接在图表中选择该日期。<br/>这将筛选表，仅显示在该特定日执行活动的用户的文件活动数据。  <br/> |
|创建的调查数  <br/> |用户创建的调查数。   <br/> |
|调查响应数  <br/> |调查向其分发的答复者答复的数目。|
|||