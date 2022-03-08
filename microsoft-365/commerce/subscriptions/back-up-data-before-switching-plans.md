---
title: 在更改计划之前备份数据
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 更改Outlook计划OneDrive、Yammer、SharePoint和Microsoft 365内容。
ms.date: 03/17/2021
ms.openlocfilehash: 57f897b353cfe61d5c9cae56c1d367d5e57a29ca
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317929"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>在切换业务Microsoft 365之前备份数据

如果用户将切换到具有较少数据相关服务的另一个订阅，或者用户离开组织，可以在切换到新订阅之前下载存储在 Microsoft 365 中的数据副本。

如果要将用户移动到具有相同或更多服务的订阅，则无需备份用户数据。 请参阅 [将用户移动到其他订阅](./move-users-different-subscription.md)。
  
## <a name="save-a-copy-of-outlook-information"></a>保存信息Outlook副本

如果用户已Outlook，可以在切换计划之前将电子邮件、联系人和日历导出或备份到 [Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) 文件中。
  
切换到新计划后，用户可以从 .pst 文件导入电子邮件、Outlook[日历](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。
  
## <a name="save-files-stored-in-onedrive-for-business"></a>保存存储在OneDrive for Business

在切换到其他订阅之前，用户可以将文件和文件夹从 [OneDrive 或 SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) 下载到其他位置，例如计算机硬盘驱动器上的文件夹或组织网络上的文件共享。
  
## <a name="save-yammer-information"></a>保存Yammer信息

管理员可以将所有邮件、笔记、文件、主题、用户和组导出到.zip文件。 有关详细信息，请参阅从[数据导出Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)。 开发人员可以使用 [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) 来这样做。
  
## <a name="how-to-save-sharepoint-information"></a>如何保存SharePoint信息

如果用户从具有 SharePoint Online 的订阅切换到没有订阅的订阅，SharePoint磁贴将不再显示在其Microsoft 365菜单中。
  
但是，只要新订阅与切换自的订阅位于同一个组织中，用户仍可以访问SharePoint网站。 他们可以使用指向工作组网站的直接 URL 查看和更新笔记本、文档、任务和日历。
  
> [!TIP]
> 我们建议用户在切换订阅之前转到团队网站，并将其 URL 保存为浏览器中的收藏夹或书签。
  
默认情况下，团队网站的 URL 格式为：
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

其中  _\<orgDomain\>_ 是组织的 URL。
  
例如，如果组织的域为 contoso.onmicrosoft.com，则指向团队网站的直接 URL 为 `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`。
  
当然，用户还可以SharePoint网站将联机SharePoint下载到本地计算机或其他位置。
