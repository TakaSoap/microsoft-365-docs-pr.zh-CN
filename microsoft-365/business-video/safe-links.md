---
title: 管理安全链接
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: 了解如何管理安全链接，以保护企业免受恶意网站的攻击。
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701589"
---
# <a name="manage-safe-links"></a>管理安全链接

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意网站的攻击，当用户单击 Office 应用中的链接时。

## <a name="try-it"></a>试一试！

1. 转到管理 [中心，](https://admin.microsoft.com)然后选择"**设置"。**
1. 向下滚动以 **增强对高级威胁的保护**。 选择 **"查看****、管理**"，然后选择 **"ATP 安全链接"。**
1. 在 **"应用于整个组织的策略"下**，选择 **"** 默认策略"，然后选择"编辑 **"** 图标。
1. 输入要阻止的 URL。
1. Select **Use safe links in Office apps， Office for iOS and Android**;select **Do not track when users click safe links**;并选择 **"不允许用户单击到原始 URL 的安全链接"。** 如果设置默认策略，则可能已经选择了这些策略。 选择“**保存**”。
1. 在 **"适用于特定收件人的策略**"下，选择 **"推荐的安全链接** 规则"，然后选择"编辑 **"** 图标。
1. 选择 **设置**，向下滚动，输入不希望检查的 URL，然后选择"添加 **"** 图标。
1. 选择 **"应用于**"，然后选择您的域名。 选择要应用规则的其他域。 选择 **"添加****"，"** 确定"，然后 **保存**。

ATP 安全链接现已配置。 最多允许 30 分钟更改生效。

当用户收到包含链接的电子邮件时，将扫描这些链接。 如果认为链接是安全的，可单击这些链接。 但是，如果链接位于阻止列表中，用户将看到一条消息，指出该链接已被阻止。