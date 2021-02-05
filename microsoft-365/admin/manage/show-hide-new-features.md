---
title： "Manage which Office features appear in What's New" f1.keywords：
- NOCSH ms.author：danbrown author： DHB-MSFT manager： audiencetv audience： Admin ms.topic： article ms.service： o365-administration localization_priority： Normal ms.collection：
- M365-subscription-management
- Adm_O365
- Adm_TOC ms.custom：AdminSurgePortfolio search.appverid：
- BCS160
- MET150
- MOE150 description： "Decide which Office features to show or hide when a user chooses Help > What's New in their Office app on Windows by using the "What's new in Office" feature in the Microsoft 365 admin center.
---

# <a name="manage-which-office-features-appear-in-whats-new"></a>管理新增功能中显示哪些 Office 功能

当一个重要的 Office 功能发布时，当用户在 Windows 上的 Office应用中选择"帮助新增功能"时，用户将会收到有关  >  该功能的消息。

可以使用 Microsoft 365 管理中心中的 **Office** 新增功能来控制用户显示哪些功能消息。 如果你决定向用户隐藏功能消息，你稍后可以始终返回，并决定向用户显示它。

> [!NOTE]
> - 向用户隐藏功能消息不会在 Office 应用中禁用该功能。
> - 必须分配有全局管理员角色或 Office 应用管理员角色才能使用 Office 中的 **新增** 功能。

## <a name="show-or-hide-new-features"></a>显示或隐藏新功能 

1. 在 Microsoft 365 管理中心的"设置 **"** 下，选择 **"组织设置"。**
2. 在" **服务"** 选项卡上， **选择 Office 中的新增功能**。
3. 单击功能名称时，将显示一个包含以下信息的飞出面板：
     - 功能简短说明。
     - 指向文章的链接，以了解有关该功能的更多内容。
     - 功能出现的 Office 应用程序。
     - 第一 (版本) 该功能可用于该频道。
4. Choose **Hide from users.** 或者，如果你之前隐藏该功能，请选择"**向用户显示"。**

还可以在"管理哪些 **Office** 功能显示在'新增功能'"页上选择多个功能，然后选择"隐藏 **"** 或"**显示"。**

> [!NOTE]
> - 如果功能在多个 Office 应用中可用，将该功能设置为 **"** 隐藏"将隐藏所有这些 Office 应用中的功能消息。
> - 默认情况下，所有功能消息都向用户显示。 这是所有功能的默认状态，并且只有选择隐藏或显示功能消息时状态才能更改。
> - 您还可以从 Microsoft 365 应用版管理中心 () 。 [https://config.office.com](https://config.office.com) 此功能位于 **"自定义**  >  **新增管理"下**。

## <a name="list-of-features"></a>功能列表

可以筛选"管理哪些 Office 功能显示在' **新增功能'"页上的功能** 。 可以按频道、应用程序或状态或它们的组合进行筛选。

基于以下计划在页面上显示新功能：

||||
|:-----|:-----|:-----|
|**频道** <br/> |"日期" <br/> |**采取措施** <br/> |
|**Current** <br/> |每月 15 日  <br/> |1 - 每月发布前 3 周 <br/> |
|**月度企业版** <br/> |每月第一个  <br/> |在主要版本前两周引入新功能 |
|**半年企业版 (预览)** <br/> |9 月 1 日到 3 月 1 日 <br/> | 在引入新功能的主要版本前 2 周|
|**半年企业版** <br/> |1 月 1 日与 7 月 1 日 <br/> | 在引入新功能的主要版本前 2 周<br/> |

有关何时向每个更新频道发布新版本的信息，请参阅 [Microsoft 365 ](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)应用版的更新历史记录 (按日期) 。

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>将"Office 中的新增功能"卡片添加到管理中心主页

1. 在 Microsoft 365 管理页面上 **，选择页面** 顶部的"添加卡"
2. 找到 **"管理哪些 Office 功能显示在** 列表中的新增功能"中，然后选择它。
3. 卡片在主页上显示后，可以选择 **Office** 中的新增功能来显示或 [隐藏](#show-or-hide-new-features) 组织的功能。


## <a name="related-articles"></a>相关文章

[Office 新增功能管理现已普遍可用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)