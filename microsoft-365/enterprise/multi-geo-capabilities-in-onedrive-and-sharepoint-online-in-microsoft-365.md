---
title: OneDrive 和 SharePoint Online 中的多地理位置功能
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: 利用 OneDrive Online 中的多地理位置功能将 Microsoft 365 的触及范围扩展到多个地理区域。
ms.openlocfilehash: 778efca6035dad05ec9bc77298b888e50f381ca1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330029"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>OneDrive 和 SharePoint Online 中的多地理位置功能

OneDrive 和 SharePoint Online 中的多地理位置功能支持控制共享资源，如 SharePoint 团队网站和 Microsoft 365 组邮箱（存储在指定地理位置中的其余位置）。

每个用户、组邮箱和 SharePoint 站点都有一个首选数据位置 (PDL)，表示要在其中存储相关数据的地理位置。 可将用户的个人数据（Exchange 邮箱和 OneDrive）以及用户创建的任何 Microsoft 365 组或 SharePoint 站点存储在指定地理位置，以满足数据驻留要求。 你可以[为每个地理位置指定不同的管理员](add-a-sharepoint-geo-admin.md)。

用户在使用 Microsoft 365 服务（包括 Office 应用程序、OneDrive 和搜索）时将能获得无缝体验。 有关详细信息，请参阅[多地理位置环境中的用户体验](multi-geo-user-experience.md)。

## <a name="onedrive"></a>OneDrive

管理员可依据用户的 PDL 配置每个用户的 OneDrive，或[将其移至](move-onedrive-between-geo-locations.md)附属位置。 个人文件随后保留在该地理位置中，不过可以将这些文件与其他地理位置中的用户共享。

## <a name="sharepoint-sites-and-groups"></a>SharePoint 网站和组

多地理位置功能的管理通过管理中心<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理中心。</a> 可在[相应的博客文章](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)中找到详细信息。

当用户在多地理环境中创建与 SharePoint 组连接的网站时，他们的 PDL 将用于确定网站及其关联的组邮箱的创建地理位置。 （如果尚未设置用户的 PDL 值，或已将其设置为未配置为附属位置的地理位置，则会在中心位置创建站点和邮箱。）

Microsoft 365、Exchange、OneDrive、SharePoint 和 Teams 服务不是多地理位置服务。 但是Microsoft 365创建的所有组都将使用创建者的 PDL 及其 Exchange 组邮箱进行配置，SharePoint 网站将在相应的地理位置中预配。 

## <a name="managing-the-multi-geo-environment"></a>管理多地理位置环境

通过管理中心设置和管理多地理位置SharePoint<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">管理。</a> 

![管理中心中地理位置页面SharePoint屏幕截图。](../media/sharepoint-multi-geo-admin-center.png)

（诸如移动 SharePoint 站点或 OneDrive 站点的某些操作需要 Microsoft PowerShell。）

## <a name="see-also"></a>另请参阅

[SharePoint 和 Microsoft 365 组中的多地理位置](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[管理多地理位置环境](administering-a-multi-geo-environment.md)

[多地理位置环境中的 SharePoint 存储配额](sharepoint-multi-geo-storage-quota.md)

[在多地理位置环境中管理 Exchange Online 邮箱](administering-exchange-online-multi-geo.md)
