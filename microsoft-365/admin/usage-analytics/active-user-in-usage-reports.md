---
title: 活动用户Microsoft 365使用情况报告中
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 了解活动用户Microsoft 365使用情况分析、活动报告和采用指标。
ms.openlocfilehash: 748bd08e08cc5e8243c3733c4b3f8448e15ab050
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806092"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>活动用户Microsoft 365使用情况报告中

## <a name="active-user-in-usage-reports"></a>使用情况报告中的活动用户

管理中心Microsoft 365使用情况Microsoft 365活动报表的活动用户定义[](usage-analytics.md)如下。[](../activity-reports/activity-reports.md) 
  
|**产品**|**活动用户的定义**|**注释**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |已执行以下任一操作的任何用户：标记为已读、发送邮件、创建约会、发送会议请求、接受 (为暂定) 或拒绝会议请求、取消会议。  <br/> |没有表示任何日历信息，这将在将来的更新版本中进行添加。  <br/> |
|SharePoint Online  <br/> |通过创建、修改、查看、删除、内部或外部共享，或与任何网站上的客户端同步来与文件进行交互，或在任何网站上查看页面的任何用户。  <br/> |SharePoint 使用情况分析模板应用中 Microsoft 365 Online 的活动用户指标仅反映对 SharePoint 团队网站或组网站执行文件活动的用户。 模板应用将进行更新，以将定义同步到管理中心使用情况报告中的定义。  <br/> |
|OneDrive for Business  <br/> |通过创建、修改、查看、删除、内部或外部共享，或与客户端同步来与文件进行交互的任何用户。  <br/> ||
|Yammer  <br/> |在 Yammer 上对消息进行阅读、发布或点赞的任何用户。  <br/> ||
|Skype for Business  <br/> |参与对等会话（包括即时消息、音频和视频通话、应用程序共享和文件传输）或组织或参加会议的任何用户。  <br/> ||
|Office  <br/> |至少一个设备上激活了 Microsoft 365 Pro Plus、Visio Pro Project Pro订阅的任何用户。  <br/> ||
|Microsoft 365 组  <br/> |具有邮箱活动（如果已向组发送邮件）的任何组成员  <br/> |此定义将在组网站上通过组网站文件活动和 Yammer 组活动 (文件活动以及张贴到与组关联的 Yammer 组的消息进行增强。) 此数据当前在 Microsoft 365 使用情况分析模板应用中不可用  <br/> |
|Microsoft Teams  <br/> |参与聊天消息、私人聊天消息、通话、会议或其他活动的任何用户。 其他活动定义为用户进行的其他团队活动的数量，其中一些活动包括但不限于：喜欢消息、应用、处理文件、搜索、跟踪团队和频道以及支持他们。  <br/> ||
   
## <a name="adoption-metrics"></a>采用指标

[Microsoft 365使用情况分析](usage-analytics.md)包含更多与活动用户相关的采用指标，以显示产品在一段时间的采用状况。 这些指标对所选月份、年份和产品有效，定义如下。 
  
|**跃点数**|**说明**|
|:-----|:-----|
|EnabledUsers  <br/> |当月允许使用产品的用户数。  <br/> |
|ActiveUsers  <br/> |当月活跃用户数。  <br/> |
|MoMReturningUsers  <br/> |在上个月内也处于活动状态的月份中的用户数。  <br/> |
|FirstTimeUsers  <br/> |在一个月内从未使用过该服务的活动用户数。  <br/> |
|CumulativeActiveUsers  <br/> |月份中处于活动状态的用户数加上上一月的任何用户数。  <br/> |
|ActiveUsers (%)   <br/> |与当月启用的用户数相比，四舍五入到最接近的十分之一处于活动状态的用户百分比。  <br/> |
|MoMReturningUsers (%)   <br/> |用户百分比，四舍五入到最接近的十分之一，与活动用户数相比，在前一个月内也处于活动状态。  <br/> |
   
MoMReturningUsers、FirstTimeUsers &amp; 和 CumulativeActiveUsers 从 2018 年 1 月 1 日开始重置，Microsoft Teams。
  
