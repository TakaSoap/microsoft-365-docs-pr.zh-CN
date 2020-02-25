---
title: Microsoft 365 使用情况报告中的活动用户
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 了解 Microsoft 365 使用情况分析、活动报告和采用指标的活动用户。
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238671"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 使用情况报告中的活动用户

## <a name="active-user-in-usage-reports"></a>使用情况报表中的活动用户

Microsoft [365 使用情况分析](usage-analytics.md)的 microsoft 365 产品的活动用户和[管理中心的活动报告](../activity-reports/activity-reports.md)定义如下。 
  
|**产品**|**活动用户的定义**|**注释**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |已读取或发送电子邮件的任何用户。  <br/> |没有表示任何日历信息，这将在将来的更新版本中进行添加。  <br/> |
|SharePoint Online  <br/> |通过创建、修改、查看、删除、内部或外部共享，或与任何网站上的客户端同步来与文件进行交互，或在任何网站上查看页面的任何用户。  <br/> |Microsoft 365 使用情况分析模板应用中的 SharePoint Online 的活动用户指标仅反映对 SharePoint 团队网站或组网站执行文件活动的用户。 模板应用程序将进行更新，以将定义与管理中心的使用情况报告上的定义进行同步。  <br/> |
|OneDrive for Business  <br/> |通过创建、修改、查看、删除、内部或外部共享，或与客户端同步来与文件进行交互的任何用户。  <br/> ||
|Yammer  <br/> |在 Yammer 上对消息进行阅读、发布或点赞的任何用户。  <br/> ||
|Skype for Business  <br/> |参与对等会话（包括即时消息、音频和视频通话、应用程序共享和文件传输）或组织或参加会议的任何用户。  <br/> ||
|Office  <br/> |在至少一个设备上激活 Microsoft 365 Pro Plus、Visio Pro 或 Project Pro 订阅的任何用户。  <br/> ||
|Microsoft 365 组  <br/> |具有邮箱活动（如果已向组发送邮件）的任何组成员  <br/> |将使用组网站文件活动和 Yammer 组活动（组网站上的文件活动和发布到与组关联的 Yammer 组的邮件）增强此定义。此数据当前在 Microsoft 365 使用情况分析模板应用中不可用  <br/> |
|Microsoft Teams  <br/> |参与聊天消息、私人聊天消息、通话、会议或其他活动的任何用户。 其他活动定义为用户的其他团队活动的数量，其中包括（但不限于）：为邮件、应用程序、文件、搜索、关注团队和频道以及 favoriting。  <br/> ||
   
## <a name="adoption-metrics"></a>采用指标

[Microsoft 365 使用情况分析](usage-analytics.md)包含与活动用户相关的其他采用指标，以显示一段时间内产品的采用情况。 这些指标在所选的月、年和产品中有效，定义如下。 
  
|**多重**|**说明**|
|:-----|:-----|
|EnabledUsers  <br/> |每月启用使用产品的用户数。  <br/> |
|ActiveUsers  <br/> |该月的活动用户数。  <br/> |
|MoMReturningUsers  <br/> |在上个月中也处于活动状态的处于活动状态的用户数（以月为单位）。  <br/> |
|FirstTimeUsers  <br/> |之前从未使用过该服务的月份中处于活动状态的用户数。  <br/> |
|CumulativeActiveUsers  <br/> |当月内活动的用户数加上上个月中的任何一个月。  <br/> |
|ActiveUsers （%）  <br/> |相对于该月启用的用户数，舍入为最接近10的用户百分比和月中的活动。  <br/> |
|MoMReturningUsers （%）  <br/> |与活动用户数相比，在上个月中也处于活动状态的月份，舍入为最接近10的用户的百分比。  <br/> |
   
MoMReturningUsers、FirstTimeUsers、 &amp; CumulativeActiveUsers 重置起始1月1日2018，并包含 Microsoft 团队。
  
