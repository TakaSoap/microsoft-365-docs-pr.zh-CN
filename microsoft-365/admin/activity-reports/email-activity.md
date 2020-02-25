---
title: Microsoft 365 管理中心内的报告-电子邮件活动
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: 了解如何在 Microsoft 365 管理中心使用 Microsoft 365 报告仪表板获取电子邮件活动报告。
ms.openlocfilehash: db5deeecf5ff06620658d5731b65bf022a572184
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238044"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Microsoft 365 管理中心内的报告-电子邮件活动

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。
  
例如，可从"报表"页获取有关组织内电子邮件流量的高级视图，然后可钻取"电子邮件"活动小组件，了解组织内电子邮件活动趋势和按用户的详细信息。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 

## <a name="how-to-get-to-the-email-activity-report"></a>如何访问电子邮件活动报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报告**" 下拉下，选择 " **Exchange** \> **电子邮件活动**"。
  
## <a name="interpret-the-email-activity-report"></a>解读电子邮件活动报表

可通过查看" **活动**"和" **用户**"图表，了解用户电子邮件活动。 
  
![电子邮件活动报告](../media/21c1e082-317e-4b5e-b736-661ca5744def.png)
  
|||
|:-----|:-----|
|1.  <br/> |可查看" **电子邮件活动**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |通过" **活动**"图表可了解组织内进行的电子邮件活动的数量变化趋势。可了解有关电子邮件发送、阅读或接收活动的分布情况。  <br/> |
|4.  <br/> |通过" **用户**"图表可了解生成电子邮件活动的唯一用户数的变化趋势。可查看进行电子邮件发送、阅读或接收活动的用户的变化趋势。  <br/> |
|5.  <br/> | 在" **活动**"图表中，Y 轴表示电子邮件发送、接收和阅读活动数。  <br/>  在" **用户**"活动图表中，Y 轴表示进行电子邮件发送、接收和阅读活动的用户。  <br/>  这两个图表的 X 轴都表示此特定报表的所选日期范围。  <br/> |
|6.  <br/> |您可以通过选择图例中的项目来筛选您在图表上看到的系列。 例如，在 "**活动**" 图表上，为特定的相关数据选择 "**已发送**"、"](../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) **已接收**" 或 "**阅读** ![筛选器图表"，仅查看与每个相关数据相关的信息。 更改选择不会更改网格表中的信息。  <br/> |
|7.  <br/> | 下表详细显示了按用户的电子邮件活动。 表格显示了所有分配有 Exchange 产品的用户及其电子邮件活动。 <br/> <br/> " **用户名**"是用户的电子邮件地址。  <br/> 如果用户为 "**显示名称**"，则为完整名称。  <br/> **已删除**是指当前状态为已删除，但在报告的某个时间段处于活动状态的用户。  <br/> **删除日期**是指删除用户的日期。  <br/> **上次活动日期**表示用户上次执行电子邮件阅读、发送活动的日期。  <br/> " **发送操作**"是为用户记录的电子邮件发送操作的次数。  <br/> " **接收操作**"是为用户记录的电子邮件接收操作的次数。  <br/> " **读取操作**"是为用户记录的电子邮件读取操作的次数。  <br/> 已**分配的产品**是分配给此用户的产品。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|8.  <br/> |您还可以通过选择 "**导出** ![" "导出" 按钮](../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG)链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   
注意： "电子邮件活动" 报告仅适用于与拥有许可证的用户相关联的邮箱。
