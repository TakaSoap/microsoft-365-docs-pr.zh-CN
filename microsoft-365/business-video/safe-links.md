---
title: 管理保险箱链接
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何管理保险箱链接，以保护你的企业免受恶意站点的攻击。
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580626"
---
# <a name="manage-safe-links"></a>管理保险箱链接

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意站点的攻击，当用户单击应用中Office链接。

## <a name="try-it"></a>试一试！

1. 转到管理 [中心，然后选择](https://admin.microsoft.com)"设置 **"。**
1. 向下滚动以 **提升对高级威胁的保护**。 选择 **"查看****、管理**"，然后选择 **"ATP 保险箱链接"。**
1. 在 **"应用于整个组织的策略"下**，选择" **默认策略** "，然后选择"编辑 **"** 图标。
1. 输入要阻止的 URL。
1. 在 **iOS 和 Android Office应用中选择Office安全链接**"选择 **"当用户单击安全链接时不跟踪";** 并选择 **"不允许用户通过安全链接单击到原始 URL"。** 如果设置了默认策略，则可能已经选择了这些策略。 选择“**保存**”。
1. 在 **"适用于特定收件人的策略"下**，选择 **"推荐的安全链接** 规则"，然后选择"编辑 **"** 图标。
1. 选择 **"** 设置"，向下滚动，输入不希望检查的 URL，然后选择"添加 **"** 图标。
1. 选择 **"应用到"，** 然后选择您的域名。 选择您希望规则应用于的其他任何域。 选择 **"添加****"，"确定**"，然后选择"**保存"。**

ATP 保险箱链接现已配置。 最多允许更改 30 分钟生效。

当用户收到包含链接的电子邮件时，将扫描这些链接。 如果认为链接是安全的，则这些链接是可单击的。 但是，如果链接位于阻止列表中，用户将看到一条消息，表明该链接已被阻止。