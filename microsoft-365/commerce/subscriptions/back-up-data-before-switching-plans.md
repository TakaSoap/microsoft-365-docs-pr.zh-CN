---
title: 在切换 Office 365 for business 计划之前备份数据
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: 在切换 Office 365 订阅或用户离开组织之前，备份 Outlook、OneDrive、Yammer 和 SharePoint 内容。
ms.openlocfilehash: 16fb6972869c3caf010c25cbe043dbf79f458531
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238251"
---
# <a name="back-up-data-before-switching-office-365-for-business-plans"></a>在切换 Office 365 for business 计划之前备份数据

如果用户将切换到与数据相关的服务或用户离开组织的另一个订阅，则在将其存储在 Office 365 中的数据的副本在切换到新订阅之前可以进行下载。
  
## <a name="save-a-copy-of-outlook-information"></a>保存 Outlook 信息副本

如果用户具有 Outlook，他们可以先将[电子邮件、联系人和日历导出或备份到 outlook .pst 文件](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)，然后再切换其计划。 
  
在切换到新计划后，用户可以[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>保存存储在 OneDrive for Business 中的文件

在切换到其他订阅之前，用户可以将[文件和文件夹从 OneDrive 或 SharePoint 下载](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)到其他位置（如其计算机硬盘上的文件夹）或组织网络上的文件共享。 
  
## <a name="save-yammer-information"></a>保存 Yammer 信息

管理员可以将所有邮件、注释、文件、主题、用户和组导出为 .zip 文件。 有关详细信息，请参阅[从 Yammer Enterprise 导出数据](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 此外，开发人员还可以使用[YAMMER API](https://go.microsoft.com/fwlink/p/?linkid=842495)执行此操作。 
  
## <a name="how-to-save-sharepoint-information"></a>如何保存 SharePoint 信息

如果用户从具有 SharePoint Online 的订阅切换到不具有该订阅的订阅，则**sharepoint**磁贴将不再显示在其 Office 365 菜单中。 
  
但是，只要新订阅与从中交换的订阅位于同一组织内，用户仍可以访问 SharePoint 团队网站。 他们可以使用团队网站的直接 URL 查看和更新笔记本、文档、任务和日历。
  
> [!TIP]
> 建议用户在切换订阅之前转到团队网站，并在浏览器中将 URL 另存为收藏项或书签。 
  
默认情况下，团队网站的 URL 采用以下形式：
  
```
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

其中_ \<，\> orgDomain_是组织的 URL。 
  
例如，如果组织的域是 contoso.onmicrosoft.com，则团队网站的直接 URL 将为https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx。
  
当然，用户也可以随时将 SharePoint Online 文档从 SharePoint 团队网站下载到本地计算机或其他位置。