---
title: 管理Office功能显示在新增功能中
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用 Microsoft 365 管理中心中的"Office 中的新增功能"，确定当用户在 Windows > 上的 Office 应用 中选择"帮助""Office 应用 新增功能"时要显示或隐藏的 Microsoft 365 功能。 Office
ms.openlocfilehash: 395038bebda407771802a61ba5aefc350c7c5cd1
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929475"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>管理Office功能显示在新增功能中

当发布Office功能时，当用户在 Windows 上的应用中选择"帮助""新增功能"时，Office收到一条  >  Windows。

可以使用管理中心中的"Office中的新增功能"控制显示用户Microsoft 365消息。 如果您决定向用户隐藏功能消息，则始终可以稍后返回，并决定向用户显示它。

> [!NOTE]
> - 向用户隐藏功能消息不会在功能策略中Office 应用。
> - 必须分配有全局管理员角色或 Office 应用管理员角色，才能使用"Office **新增功能**。

## <a name="show-or-hide-new-features"></a>显示或隐藏新功能 

1. In the Microsoft 365 admin center， under **设置，** choose **Org settings**.
2. 在"**服务"** 选项卡上，选择"服务 **中的新增Office"。**
3. 单击功能名称时，将显示一个飞出面板，并包含以下信息：
     - 功能简短说明。
     - 指向文章的链接，以了解有关该功能的更多内容。
     - 功能Office应用程序的列表。
     - 第一 (版本) 该功能可用于该频道。
4. 选择 **"向用户隐藏"。** 或者，如果你之前隐藏该功能，请选择"**向用户显示"。**

还可以选择"管理哪些功能Office **功能** 显示在"新增功能"页上，**然后选择"隐藏**"或"显示 **"。**

> [!NOTE]
> - 如果某个功能在多个应用Office，将该功能设置为 **隐藏** 将隐藏所有这些应用中的功能Office消息。
> - 默认情况下，所有功能消息都向用户显示。 这是所有功能的默认状态，只有选择隐藏或显示功能消息时，状态才发生更改。
> - 还可以从管理中心Office"管理中心"Microsoft 365 应用版"新增功能 [https://config.office.com](https://config.office.com) () 。 此功能位于自定义  >  **新增管理下**。

## <a name="list-of-features"></a>功能列表

可以筛选"管理哪些功能Office **功能显示在"新增功能"页上**。 可以按频道、应用程序或状态或它们的组合进行筛选。

根据以下计划在页面上显示新功能：

|频道|日期|采取行动|
|:-----|:-----|:-----|
|**Current** <br/> |当月 15 日  <br/> |1 - 每月发布前的 3 周 <br/> |
|**月度企业版** <br/> |当月的第一天  <br/> |在引入新功能的主要版本前两周 |
|**半年预览Enterprise (预览)** <br/> |9 月 1 日到 3 月 1 日 <br/> | 在引入新功能的主要版本前 2 周|
|**半年Enterprise** <br/> |1 月 1 日到 7 月 1 日 <br/> | 在引入新功能的主要版本前 2 周<br/> |

有关何时向每个更新频道发布新版本的信息，请参阅更新历史记录Microsoft 365 应用版 ([按](/officeupdates/update-history-microsoft365-apps-by-date)日期) 。

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>将"Office中的新增功能"卡片添加到管理中心主页

1. 在"Microsoft 365"页面上 **，选择页面** 顶部的"添加卡片"
2. 找到 **"管理Office功能显示在"新增功能"** 中，然后选择它。
3. 卡片位于主页上后，可以选择"Office中的新增功能"来显示[或隐藏组织](#show-or-hide-new-features)的功能。


## <a name="related-articles"></a>相关文章

[Office新增管理现已普遍可用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)
