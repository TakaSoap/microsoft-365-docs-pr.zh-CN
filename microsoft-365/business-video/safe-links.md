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
ms.openlocfilehash: 7e6b4507cd363a448812b48e3eafc7f4c077be3c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59171162"
---
# <a name="manage-safe-links"></a>管理保险箱链接

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365（以前称为Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意网站的攻击，当用户单击应用中的链接时Office站点。

## <a name="try-it"></a>试一试！

1. 转到管理 [中心，然后选择](https://admin.microsoft.com)"设置 **"。**
2. 向下滚动以 **提升对高级威胁的保护**。 选择 **"管理**"，然后选择 **保险箱链接"。**
3. 选择 **"全局设置"，** 在"阻止 **以下 URL"** 中，输入要阻止的 URL。
4. 选择 **"** 在 Office 365 应用中使用 保险箱 链接"，选择"当用户单击 Office 365 应用中的受保护链接时不跟踪 **"，** 然后选择"不允许用户单击到 Office 365 应用中 **的原始 URL"。** 如果设置了默认策略，则可能已经选择了这些策略。 选择“**保存**”。

保险箱现在配置了链接。 最多允许更改 30 分钟生效。

当用户收到包含链接的电子邮件时，将扫描这些链接。 如果认为链接是安全的，则这些链接是可单击的。 但是，如果链接位于阻止列表中，用户将看到一条消息，表明该链接已被阻止。
