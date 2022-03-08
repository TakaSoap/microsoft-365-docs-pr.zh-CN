---
title: 在卫星定位中启用 SharePoint 多地理位置功能
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: 本文为全局管理员或SharePoint管理员提供有关在附属SharePoint Multi-Geo启用权限的信息。
ms.openlocfilehash: b542c1ee77c7b4ca7a6179bac5ce5eaa1090606a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330435"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>在卫星定位中启用 SharePoint 多地理位置功能

本文面向 2019 年 3 月 27 日正式发布 SharePoint 多地理位置功能 **以前** 已创建多地理位置卫星位置且未在其卫星地理位置启用 SharePoint 多地理位置的全局或 SharePoint 管理员。 

>[!Note]
>如果你在 **2019** 年 3 月 27 日之后添加了一个新地理位置，则无需执行这些说明，因为新地理位置已经针对 OneDrive 和 SharePoint Multi-Geo 启用。

通过这些说明，可以在卫星位置启用 SharePoint，因此多地理位置卫星用户可以利用 O365 中的 OneDrive 和 SharePoint 多地理位置功能。 

>[!IMPORTANT]
>请注意这是单向启用。 设置 SPO 模式后，则不能将租户还原到仅 OneDrive 多地理位置模式，除非向支持人员上报。 

## <a name="to-set-a-geo-location-into-spo-mode"></a>要将地理位置设置为 SPO 模式

要将地理位置设置为 SPO 模式，请连接到要在 SPO 模式中设置的地理位置：

1.    打开 SharePoint Online Management Shell 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience。](../media/Set-SPO-MultiGeo.jpg)
4.    此操作通常需要约一小时，在此期间，我们会在服务中执行多种发布返回，并重新戳记你的租户。 至少 1 小时后，请执行 Get-SPOMultiGeoExperience。  这将显示此地理位置是否在 SPO 模式下。</br></br>
![Set-SPOMultiGeoExperience。](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>服务中的某些缓存每 24 小时更新一次，因此在最多 24 小时内，卫星地理位置可能间歇地表现出就像仍在 ODB 模式下的行为。 这不会导致任何技术问题。 
 
有关 SharePoint 多地理位置的更多信息，请参阅 [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


