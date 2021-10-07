---
title: 使用 Microsoft 365 商业高级版管理 Windows 10 专业版设备策略
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 了解如何使用 Microsoft 365 商业高级版管理 Windows 10 专业版设备策略。
ms.openlocfilehash: 3424e8c5075c019a986f071a041ce16775b29e5f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189713"
---
# <a name="manage-windows-10-pro-device-policies"></a>管理 Windows 10 专业版设备策略

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

使用 Microsoft 365 商业版，可确保 Windows Defender 防病毒功能在 Windows 10 设备上处于激活状态，而且 Microsoft 更新可自动下载到用户设备上。

## <a name="try-it"></a>试一试！

1. 登录到 1。 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">"Microsoft 365 管理中心"。</a>
1. 在“**策略**”下方，选择“添加策略”。
1. 在“**添加策略**”窗格的“**策略名称**”下方输入名称，然后在“**策略类型**”下选择“**Windows 10 设备配置**”。
1. 选择“**保护 Windows 10 设备**”即可查看子选项。
1. 确保“**使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁**”和“**让 Windows 10 设备自动保持最新状态**”处于打开状态。
1. 在“**谁将收到这些设置?**”下方，将默认选中所有用户，但可以选择“**更改**”以选择所创建的任何安全组。
1. 选择“**添加**”，策略即创建完毕。
1. 在“**添加策略**”页面上，选择“**关闭**”。
1. 在管理中心主页上，选择“**策略**”并在“**策略**”页面上查看策略，确认已添加新策略。
1. 要验证策略是否已生效，请在用户的 Windows 10 设备上转到 Windows 更新，选择“**高级选项**”，然后确认设置显示为灰色。

    然后，单击“**选择更新交付方式**”，并确认设置显示是否为灰色并显示以下消息：**某些设置由组织隐藏或管理**。

