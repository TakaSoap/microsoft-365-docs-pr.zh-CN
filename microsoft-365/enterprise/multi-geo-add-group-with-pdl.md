---
title: 创建具有Microsoft 365首选数据位置的组
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: 了解如何在多地理位置Microsoft 365具有指定首选数据位置的组。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.openlocfilehash: 7de00ad0d94cda0a47f4981d78ebc07cedab6ada
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318797"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>创建具有Microsoft 365首选数据位置的组

当多地理位置环境中的用户创建 Microsoft 365 组时，组首选数据位置 (PDL) 会自动设置为用户的组首选数据位置。 全局管理员、SharePoint 管理员和 Exchange 管理员可在其所选的任何区域中创建组。 

如果需要使用特定 PDL 创建组，可以使用 <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint</a> 管理中心或 Microsoft PowerShell cmdlet Exchange Online New-UnifiedGroup组。 执行此操作时，将在指定 PDL 中设置组邮箱以及与该组相关联的 SharePoint 站点。

若要使用Microsoft 365的 PDL 创建组，请转到SharePoint创建组网站的地理位置中的管理中心<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank"></a>。

例如：

如果想要在澳大利亚位置创建一个组站点，可转到 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. 选择“**+创建**”。
2. 按照流程创建组站点。

将在与你发起站点创建请求的 SharePoint 管理中心相对应的地理位置中预配组站点。 

使用 Exchange PowerShell 

连接到 Exchange Online PowerShell，并传递包含地理位置代码的 *-MailBoxRegion* 参数。

例如： 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![使用语法New-UnifiedGroup PowerShell cmdlet 的屏幕截图。](../media/multi-geo-new-group-with-pdl-powershell.png)

请注意，SharePoint 组站点设置是按需进行的。 将在组所有者或成员首次试图访问站点时对其进行设置。

## <a name="geo-location-codes"></a>地理位置代码

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>相关主题

[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

[使用 api 创建具有特定首选数据位置Graph组](/graph/api/group-post-groups)
