---
title: 与外部用户共享日历
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 在组织中启用日历Microsoft 365 管理中心以便用户可以与组织内外的任何人共享其日历。
ms.openlocfilehash: 00ae4b96c54ae6b1471a90f598b9f96821947db3
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530447"
---
# <a name="share-calendars-with-external-users"></a>与外部用户共享日历

有时，用户必须安排与组织外部人员的会议。 为了简化查找常见会议时间的过程，Microsoft 365使日历可供这些人员使用。 这些用户需要查看组织中用户的忙/闲时间，但没有组织的Microsoft 365帐户。

您可以为组织中所有用户启用日历共享Microsoft 365 管理中心。 启用共享后，你的用户可以Outlook Web App组织内外的任何人共享其日历。 组织内部人员可以查看共享日历及其日历。 组织外部的人员将收到可用于查看日历的 URL。 贵组织的用户决定何时共享以及共享多少。

> [!NOTE]
> 如果要与使用 Exchange Server 2013（内部部署解决方案）的组织共享日历，Exchange 管理员需要设置与云的身份验证关系。 这称为联合，必须满足最低软件要求。 有关详细信息，请参阅[共享](/exchange/sharing-exchange-2013-help)。
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>启用日历共享Microsoft 365 管理中心

1. In the admin center， go to **设置** \> **Org settings**， and on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"> **Services** tab，</a>select **Calendar**.
  
3. 在 **"日历**"页上，选择是否允许用户与组织外部拥有日历或Microsoft 365 Exchange。 选择是否允许匿名用户 (没有凭据的用户) 通过电子邮件邀请访问日历。

4. 选择要为用户提供的日历信息类型。 你可以允许所有信息，或仅将信息限制为时间或时间、主题和位置。

## <a name="external-sharing-sync-interval"></a>外部共享同步间隔

目前不支持在租户外进行即时同步。 虽然可以在这些配置中共享，但会定期进行同步。 有两种类型的跨租户共享：

1. **Microsoft 365如果** Microsoft 365外部 (，则向另一位用户) ：将创建一个完全共享日历，但大约每三小时进行一次同步。 最终将为此设置启用即时同步。

2. **Microsoft 365到 Outlook.com** 用户：如果禁用外部共享，则与另一Microsoft 365共享也属于此组。 ICS URL 在共享时生成，收件人可以使用它添加到任何日历服务。 使用 ICS 订阅，收件人的日历服务将选择何时同步 ICS 订阅以接收新更新。 如果收件人是 Outlook.com 或 Microsoft 365 用户，则大约每三小时进行一次同步。

## <a name="invite-people-to-access-calendars"></a>邀请其他人访问日历

启用共享后，日历所有者可以将邀请扩展到特定用户。 有关说明，请参阅[在日历Outlook Web App。](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)

## <a name="related-content"></a>相关内容

[打开或关闭网站](/sharepoint/change-external-sharing-site) 外部共享 (文章) \
[视频Microsoft 365 管理中心 (](../admin-overview/admin-center-overview.md)概述) \
[管理电子邮件和日历](/admin) (链接页) 

