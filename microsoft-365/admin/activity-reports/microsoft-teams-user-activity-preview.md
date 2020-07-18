---
title: Microsoft 团队中的 microsoft 365 报表-Microsoft 团队用户活动-预览
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
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167337"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>Microsoft 团队中的 microsoft 365 报表-Microsoft 团队用户活动-预览

Microsoft 365 "**报告**" 仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 用户活动报表中，可深入了解组织中的 Microsoft Teams 活动。
  
> [!NOTE]
> 您必须是 Microsoft 365 或 Exchange、SharePoint、团队服务、团队通信或 Skype for Business 管理员中的全局管理员、全局读取器或报告阅读器才能查看报告。  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>如何访问预览 Microsoft 团队用户活动报告

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。
2. 从 "**选择报表**" 下拉下，选择 " **Microsoft 团队**"。
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>解释预览 Microsoft 团队用户活动报告

您可以通过选择 "**用户活动**" 选项卡，在 "预览团队报告" 中查看用户活动。
  
|||
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的电子邮件地址。 可以显示实际的电子邮件地址或采用匿名字段。   <br/> |
|通道邮件   <br/> |在指定时间段内用户在团队聊天中发布的唯一消息数。  <br/> |
|聊天消息   <br/> |在指定时间段内，用户在私人聊天中发布的唯一邮件数。  <br/> |
|会议总数   <br/> |用户在指定时间段内参与的联机会议的数量。  <br/> |
|1:1 调用   <br/> | 用户在指定时间段内参与的1:1 呼叫数。  <br/> |
|上次活动日期（UTC）  <br/> |用户参与 Microsoft 团队活动的最后日期。<br/> |
|会议是临时参与的   <br/> | 在指定时间段内用户参与的日历上未计划的会议数。  <br/> |
|以即席方式组织的会议 <br/> |在指定时间段内，用户组织的日历上未计划的会议数。 <br/>|
|安排的会议  <br/> |用户在指定时间段内组织的已安排会议数。  <br/> |
|已许可 |如果用户已被授权使用团队，则选择此选项。|
|其他活动|用户被视为处于活动状态，但其值为零：聊天消息、1:1 呼叫、频道消息、会议总数和组织的会议。 示例操作是在将 Microsoft 团队客户端激活到前台时，在撰写邮件区域中执行操作，toast 在 Microsoft 团队客户端中显示，横幅显示在 Microsoft 团队客户端等中。 |
|||