---
title: Microsoft 365管理中心中的报表 - 电子邮件活动
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
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: 了解如何使用电子邮件活动报告中的 Microsoft 365 报表仪表板获取Microsoft 365 管理中心。
ms.openlocfilehash: 95742f5a8a2c410d0f9c7a526d565d8eb62b13a5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156026"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365管理中心中的报表 - 电子邮件活动

"Microsoft 365 **报表**"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，可从"报表"页获取有关组织内电子邮件流量的高级视图，然后可钻取"电子邮件"活动小组件，了解组织内电子邮件活动趋势和按用户的详细信息。
  
> [!NOTE]
> 您必须是 Microsoft 365 中的全局管理员、全局读取者或报告读者，或者 Exchange、SharePoint、Teams Service、Teams Communications 或 Skype for Business 管理员才能查看报告。 

## <a name="how-to-get-to-the-email-activity-report"></a>如何访问电子邮件活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。
2. 选择 **"电子邮件活动"** 下的"**查看更多"。** 
3. 从"**电子邮件活动**"下拉列表中，选择 **"Exchange** \> **电子邮件活动"。**
  
## <a name="interpret-the-email-activity-report"></a>解读电子邮件活动报表

可通过查看" **活动**"和" **用户**"图表，了解用户电子邮件活动。 
  
![电子邮件活动报告。](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|项目|说明|
|:-----|:-----|
|1.  <br/> |可查看" **电子邮件活动**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的特定日期，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。  <br/> |
|2.  <br/> |每个报告中的数据通常涵盖过去 24 至 48 小时的数据。  <br/> |
|3.  <br/> |通过" **活动**"图表可了解组织内进行的电子邮件活动的数量变化趋势。 你可以了解电子邮件发送、电子邮件阅读、接收的电子邮件、创建的会议或会议交互活动的拆分。  <br/> |
|4.  <br/> |通过" **用户**"图表可了解生成电子邮件活动的唯一用户数的变化趋势。 你可以查看执行电子邮件发送、电子邮件阅读、电子邮件接收、会议创建或会议交互活动的用户趋势。  <br/> |
|5.  <br/> | 在 **"活动** "图表上，Y 轴表示已发送电子邮件、接收的电子邮件、电子邮件阅读、创建的会议和交互的会议类型的活动计数。  <br/>  在 **"用户** "活动图表中，Y 轴表示用户所发送的电子邮件类型、接收的电子邮件、电子邮件阅读、创建的会议或已交互会议类型的用户执行活动。  <br/>  这两个图表的 X 轴都表示此特定报表的所选日期范围。  <br/> |
|6.  <br/> |通过选择图例中的项目，可以筛选在图表上看到的系列。  <br/> |
|7.  <br/> | 下表详细显示了按用户的电子邮件活动。 表格显示了所有分配有 Exchange 产品的用户及其电子邮件活动。 <br/> <br/> " **用户名**"是用户的电子邮件地址。  <br/> **显示名称** 是完整名称（如果用户）。  <br/> **已删除** 是指当前状态为已删除，但在报告的某个时间段处于活动状态的用户。  <br/> **删除日期** 是指删除用户的日期。  <br/> **上次活动日期** 表示用户上次执行电子邮件阅读、发送活动的日期。  <br/> " **发送操作**"是为用户记录的电子邮件发送操作的次数。  <br/> " **接收操作**"是为用户记录的电子邮件接收操作的次数。  <br/> " **读取操作**"是为用户记录的电子邮件读取操作的次数。  <br/> **会议创建操作** 是记录用户的会议请求发送操作次数。  <br/> **会议交互操作** 是用户记录会议请求接受、暂定、拒绝或取消操作次数。  <br/> **分配的产品** 是分配给此用户的产品。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看活动报告中的活动报告中 **的** 如何隐藏用户级别 [Microsoft 365 管理中心。](activity-reports.md)  <br/> |
|8.  <br/> |选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![电子邮件活动报告 - 选择列。](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |您还可以通过选择"导出"链接将报告数据导出到Excel .csv文件。  此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   
> [!NOTE]
> 电子邮件活动报告仅适用于与拥有许可证的用户关联的邮箱。
