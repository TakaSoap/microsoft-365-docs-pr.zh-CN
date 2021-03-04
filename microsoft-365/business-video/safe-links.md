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
description: 了解如何管理安全链接，以保护业务免受恶意网站的攻击。
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422239"
---
# <a name="manage-safe-links"></a>管理安全链接

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）可帮助在用户单击 Office 应用中的链接时保护你的业务免受恶意网站的攻击。

## <a name="try-it"></a>试一试！

1. 转到管理 [中心，](https://admin.microsoft.com)然后选择"**设置"。**
1. 向下滚动以 **增强对高级威胁的保护**。 选择 **"查看****、管理**"，然后选择 **"ATP 安全链接"。**
1. 在 **"适用于整个组织的策略"下**，选择" **默认策略** "，然后选择"编辑 **"** 图标。
1. 输入要阻止的 URL。
1. Select **Use safe links in Office apps， Office for iOS and Android**;select **Do not track when users click safe links**;并选择 **"不允许用户单击指向原始 URL 的安全链接"。** 如果设置默认策略，则可能已经选择了这些策略。 选择“**保存**”。
1. 在 **"适用于特定收件人的策略"下**，选择 **"推荐的安全链接** 规则"，然后选择"编辑 **"** 图标。
1. 选择 **设置**，向下滚动，输入不想检查的 URL，然后选择"添加 **"** 图标。
1. 选择 **"应用于**"，然后选择您的域名。 选择要应用规则的任何其他域。 选择 **"添加****"，"确定**"，然后 **保存**。

ATP 安全链接现已配置。 最多允许 30 分钟更改生效。

当用户收到包含链接的电子邮件时，将扫描这些链接。 如果认为这些链接是安全的，则它们可单击。 但是，如果链接位于阻止列表中，用户将看到一条消息，指出该链接已被阻止。