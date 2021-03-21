---
title: 数据移动期间和数据移动之后
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: 数据移动是 Microsoft 将租户的服务和关联数据移动到新的数据中心地理位置时发生的后端操作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14563a695e5c092f9bddfbdfdcb758f90cea32c0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929416"
---
# <a name="during-and-after-your-data-move"></a>数据移动期间和数据移动之后

数据移动是一种后端操作，对最终用户的影响最小。 当 Microsoft 将租户的每个服务和关联数据移动到新的数据中心地理位置时，无需任何操作。 数据传输和验证会提前在后台进行，对用户的影响最小。
  
> [!NOTE]
> 对于每个服务，移动在不同的时间发生。 因此，你将在不同时间看到描述的每个服务的缩减功能。 
  
查看 Microsoft 365 消息中心，确认何时完成每个 Exchange Online、SharePoint Online 和 Teams 聊天服务的移动。 如下表所示，注册期结束后最多可能需要 24 个月才能完成核心客户数据在其余位置移动到新的数据中心地理位置。   

|**具有注册国家/地区的客户**|**完成的所有移动**|
|:-----|:-----|
|澳大利亚、新西兰、斐济  <br/> |2022 年 7 月 1 日  <br/> |
|日本  <br/> |2022 年 7 月 1 日  <br/> |
|印度  <br/> |2022 年 7 月 1 日  <br/> |
|加拿大  <br/> |2022 年 7 月 1 日  <br/> |
|韩国  <br/> |2022 年 7 月 1 日  <br/> |
|英国  <br/> |2022 年 7 月 1 日  <br/> |
|法国  <br/> |2022 年 7 月 1 日  <br/> |
|阿拉伯联合酋长国  <br/> |2022 年 7 月 1 日  <br/> |
|南非  <br/> |2022 年 7 月 1 日  <br/> |
|瑞士、列支敦士登  <br/> |2022 年 7 月 1 日  <br/> |
|挪威  <br/> |2022 年 11 月 1 日  <br/> |
|德国  <br/> |2023 年 5 月 1 日  <br/> |
|巴西  <br/> |2023 年 6 月 1 日  <br/> |

## <a name="exchange-online"></a>Exchange Online

由于将每个用户移动到单个租户的新数据中心地理位置需要一些时间，因此在移动期间，某些用户仍将位于旧数据中心地理位置，而其他用户将位于新的数据中心地理位置。 这意味着涉及访问多个邮箱的一些功能在移动过程的一段时间（可以持续几周）内可能无法完全工作。 以下各节介绍了这些功能。
  
### <a name="open-shared-folder-in-outlook-web-access"></a>在 Outlook Web Access 中打开"共享文件夹"

一些用户从另一个邮箱打开共享邮件文件夹 (该邮箱文件夹的用户具有对 Outlook Web Access 中的) 的读取或写入权限（使用"共享文件夹"功能）。 下表介绍了在邮箱移动过程中对共享文件夹的访问权限的工作方式。 请注意，对共享邮箱具有完全权限的用户可以在移动过程中使用 Outlook Web Access 打开邮箱。 
  
|**配置**|**说明**|
|:-----|:-----|
|用户对另一个邮箱具有邮箱文件夹权限  <br/> |可能有限。  <br/> 如果用户 A 和邮箱 B 在租户移动过程中不在同一地理位置，则如果用户 A 仅对邮箱 B 中的特定文件夹具有权限，则用户 A 无法打开 Outlook Web Access 中的邮箱 B 文件夹。  <br/> 若要添加共享文件夹，请在左侧导航面板中右键单击用户名，然后选择"**添加共享文件夹"。**  <br/> |
|对另一个邮箱具有完全邮箱权限的用户  <br/> |完全支持。  <br/> 如果用户 A 具有对邮箱 B 的"完全访问"权限，则用户 A 可以单击 Outlook Web Access 中左侧导航面板中的共享文件夹，打开一个显示邮箱 B 的窗口。 用户可以在移动过程中使用 Outlook Web Access 打开共享邮箱，而没有任何负面影响。 此限制仅适用于邮箱中的文件夹级共享。           |
  
## <a name="sharepoint-online"></a>SharePoint Online

移动 SharePoint Online 时，还会移动以下服务的数据：
  
- OneDrive for Business
    
- Microsoft 365 视频服务
    
- 浏览器中的 Office
    
- 适用于企业的 Microsoft 365 应用
    
- Visio Pro for Microsoft 365
    
完成 SharePoint Online 数据移动后，您可能会看到以下一些效果。
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 视频服务

- 视频数据移动所花的时间比 SharePoint Online 中其余内容的移动要长。
    
- 移动 SharePoint Online 内容后，将存在一个无法播放视频的时间框架。
    
- 我们将从以前的数据中心删除转换代码的副本，并再次将其转码到新数据中心。
    
### <a name="search"></a>搜索

在移动 SharePoint Online 数据的过程中，我们会将搜索索引和搜索设置迁移到新位置。 完成 SharePoint  Online 数据移动之前，我们将继续从原始位置的索引为用户提供服务。 In the new location， search automatically starts crawling your content after we've completed moving your SharePoint Online data. 从现在起，我们将从迁移的索引中为用户提供服务。 迁移后对内容所做的更改不会包含在迁移索引中，直到爬网选取它们。 大多数客户不会注意到，完成 SharePoint Online 数据移动后，结果新鲜度较低，但一些客户在前 24-48 小时内的新鲜度可能会降低 
  
以下搜索功能受到影响：
  
- 搜索结果和搜索Web 部件：在爬网选取它们之前，结果不包括迁移后发生的更改。 
    
- Delve：Delve 不包括在爬网选取它们之前迁移后发生的更改。
    
- 网站的热门程度和搜索报告：新位置中的 Excel 报表计数仅包括迁移的计数以及我们完成 SharePoint Online 数据移动后运行的使用情况报告中的计数。 临时期间的任何计数将丢失且无法恢复。 此时间段通常为几天。 一些客户可能遭受更短或更长的损失。
    
- 视频门户：视频门户的查看计数和统计信息取决于 Excel 报表的统计信息，因此视频门户的查看计数和统计信息在与 Excel 报表相同的时段内丢失。
    
- 电子数据展示：在爬网选取更改之前，不会显示迁移期间更改的项目。
    
- 数据丢失防护 (DLP) ：在爬网选取更改之前，不会对发生更改的项目强制执行策略。

## <a name="microsoft-teams"></a>Microsoft Teams

除了 Exchange Online、SharePoint Online 和 OneDrive for Business 之外，Microsoft 还将 Teams 聊天服务数据迁移到本地数据中心。

- Teams 聊天消息，包括私人消息和频道消息。
- 聊天中使用的 Teams 图像。

Teams 文件存储在 SharePoint Online 中，Teams 聊天文件存储在 OneDrive for Business 中。 语音邮件、日历、聊天历史记录和联系人存储在 Exchange Online 中。 在许多情况下，Exchange Online、SharePoint Online 和 OneDrive for Business 已由本地数据中心地理位置的客户使用，也是符合条件的客户国家/地区 Microsoft 365 迁移计划的一部分。

## <a name="skype-for-business"></a>Skype for Business

Skype for Business 移动功能不再可用。  [Skype for Business Online 将于](/lifecycle/announcements/skype-for-business-online-retirement) 2021 年 7 月 31 日停用。 此后，服务将无法再访问。 
  
## <a name="related-topics"></a>相关主题 
 
[如何请求数据移动](request-your-data-move.md)
    
[数据移动常见问题解答](data-move-faq.md)
  
[新的数据中心地理位置Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[按区域表示的 Azure 服务](https://azure.microsoft.com/regions/)