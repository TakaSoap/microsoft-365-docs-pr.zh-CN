---
title: 管理中心中的 Microsoft 365 报表-电子邮件应用程序使用情况
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
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: 了解如何获取电子邮件应用使用情况报告，以了解连接到 Exchange Online 的电子邮件应用和使用的 Outlook 版本。
ms.openlocfilehash: bb75b28e41de37d4f21acedd4705db71f6c2c303
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353783"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>管理中心中的 Microsoft 365 报表-电子邮件应用程序使用情况

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在电子邮件应用使用情况报告中，可以看到有多少电子邮件应用程序连接到 Exchange Online。 还可以查看用户当前使用的 Outlook 应用的版本信息，这样便可跟进使用不受支持的版本安装支持版本的 Outlook 的用户。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint 或 Skype for Business 管理员的全局管理员、全局读取器或报告阅读器才能查看报告。 
 
## <a name="how-to-get-to-the-email-apps-report"></a>如何访问电子邮件应用报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。

    
2. 从 "**选择报告**" 下拉下，选择 " **Exchange** \> **电子邮件应用程序使用情况**"。
  
## <a name="interpret-the-email-apps-report"></a>解释电子邮件应用程序报告

可以通过查看 "**用户**" 和 "**客户端**" 图表来获取电子邮件应用活动的视图。 
  
![使用的电子邮件客户端](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |可以查看 "**电子邮件应用使用情况**" 报表，了解过去7天、30天、90天或180天的趋势。 但是，如果您在报告中选择某一天，该表（7）将显示从当前日期起的最长28天的数据（而不是报告生成的日期）。  <br/> |
|2.  <br/> |每个报告中的数据通常最长为过去24到48小时。  <br/> |
|3.  <br/> |" **用户**"视图显示使用任意电子邮件应用连接到 Exchange Online 的独特用户数。  <br/> |
|4.  <br/> |" **应用**"视图显示选定时间段内各应用的不同用户数。  <br/> |
|5.  <br/> |"**版本**" 视图显示 Windows 中每个版本的 Outlook 的唯一用户数。  <br/> |
|6.  <br/> | 在" **用户**"图表中，Y 轴表示在报告时段内的任意一天连接到应用的独特用户总数。  <br/>  在" **用户**"图表中，X 轴表示在报告时段内使用应用的独特用户数。  <br/>  在" **应用**"图表中，Y 轴表示在报告时段内使用特定应用的不同用户总数。  <br/>  在" **应用**"图表中，X 轴表示所在组织使用的应用列表。  <br/>  在" **版本**"图表中，Y 轴表示使用特定版本的 Outlook 桌面应用的独特用户总数。如果报表无法解析 Outlook 的版本号，则数量将显示为"未定"。  <br/>  在" **版本**"图表中，X 轴表示所在组织使用的应用列表。  <br/> |
|7.  <br/> |您可以通过图例中的 selectingan 项目来筛选您在图表上看到的系列。 例如，在 "**用户**" 图表上，选择 " **Mac 邮件**" 或 " **Outlook** ![电子邮件客户端列表"。 选择电子邮件客户端以获取该客户端上的更多报告数据。](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) 仅查看与各项相关的信息。 更改选择不会更改网格表中的信息。 Mac 邮件、Outlook for Mac、Outlook for Mac、Outlook mobile、Outlook 桌面和 Outlook 网页版都是您的组织中可能存在的电子邮件应用程序的示例。  <br/> |
|8.  <br/> | 添加所有项之后，才能在下表的列中看到这些项。<br/> **Username**是电子邮件应用所有者的名称。  <br/> "**上次活动日期**" 是用户阅读或发送电子邮件的最晚日期。  <br/> " **Mac 邮件**"、" **Mac Outlook**"、" **Outlook**"、" **Outlook 移动版**"、" **Outlook 网页版**"是所在组织可能使用的电子邮件应用示例。  <br/>  如果组织的策略阻止你查看显示了可识别用户信息的报表，可更改所有这些报表的隐私设置。 请查看[Microsoft 365 管理中心的活动报告](activity-reports.md)中的 "**如何隐藏用户级别详细信息？** " 一节。  <br/> |
|9.  <br/> |选择 "**管理列**" 可在报表中添加或删除列。  <br/> ![电子邮件应用使用情况报表-选择列](../../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |您还可以通过选择 "**导出**" 链接将报告数据导出到 Excel .csv 文件中。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。  <br/> |
|||
   

