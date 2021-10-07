---
title: Microsoft 365管理中心中的报告 - Microsoft Teams使用情况
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: 通过从"报告"Microsoft Teams获取组织中使用的 Microsoft Teams 应用使用情况报告，深入了解Microsoft 365使用情况。
ms.openlocfilehash: e268ff759cc77691b4118a725fc2116eb03a2fe5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157442"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365管理中心中的报告 - Microsoft Teams使用情况

"Microsoft 365 **报表**"仪表板显示组织中各产品的活动概述。 它让你能够深入研究各产品级报表，以便更细致地了解每个产品内的活动。 请查看[报表概述主题](activity-reports.md)。 在 Microsoft Teams 应用使用情况报表中，可深入了解组织中使用的 Microsoft Teams 应用。
  
> [!NOTE]
> 您必须是 Microsoft 365 中的全局管理员、全局读取者或报告读取者，或者 Exchange、SharePoint、Teams Service、Teams Communications 或 Skype for Business 管理员才能查看报告。  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>如何获取 Microsoft Teams 应用使用情况报表

1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
2. 在仪表板主页上，单击 **活动卡上的**"查看更多Microsoft Teams按钮。
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>解读 Microsoft Teams 应用使用情况报表

可以通过选择"设备使用情况"选项卡，在Teams **查看设备使用情况**。<br/>![Microsoft 365报表 - Microsoft Teams使用情况。](../../media/e46c7f7c-8371-4a20-ae82-b20df64b0205.png)

选择 **"选择要在** 报表中添加或删除列的列"。  <br/> ![Teams设备报告 - 选择列。](../../media/3358d5d9-931b-4d30-931f-450b2f5717da.png)

您还可以通过选择"导出"链接将报告数据导出到Excel .csv **文件**。 此操作可导出所有用户的数据，使你能够对数据进行简单的排序和筛选，以进一步分析数据。 如果用户数量不足 2000，则可在报表中的表格内进行排序和筛选。 如果用户数超过 2000，则需要导出数据才能进行排序和筛选。 

可查看" **Microsoft Teams 设备使用情况**"报表，了解过去 7 天、30 天、90 天或 180 天的趋势。 但是，如果您选择报告中的特定日期，则表 (7) 将显示自当前日期起最多 28 天的数据 (而不是报告生成日期) 。
  
|项目|说明|
|:-----|:-----|
|**跃点数**|**定义**|
|用户名  <br/> |用户的显示名称。  <br/> |
|Windows  <br/> |如果用户在基于桌面Teams桌面客户端中处于活动状态，Windows选中。  <br/> |
|Mac  <br/> |如果用户在 macOS 计算机上Teams桌面客户端中处于活动状态，则选中。  <br/> |
|iOS  <br/> |如果用户在适用于 iOS 的移动客户端上处于活动状态Teams选中。  <br/> |
|Android 手机  <br/> | 如果用户在适用于 Android 的移动客户端上处于活动状态Teams已选中。  <br/> |
|Chrome OS  <br/> |如果用户在 ChromeOS 计算机上Teams桌面客户端中处于活动状态，则选中。|
|Linux  <br/> | 如果用户在 Linux 计算机上Teams桌面客户端中处于活动状态，则选中。  <br/> |
|Web  <br/> |如果用户在设备上处于活动状态，Teams Web 客户端中选中。|
|上次活动日期 (UTC)   <br/> |用户参与 (活动的) UTC Teams日期。  <br/> |
|已授权|如果用户已获得使用许可证，则选择Teams。|
|||