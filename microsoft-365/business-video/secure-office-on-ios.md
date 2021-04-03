---
title: 保护 iOS 上的 Office 应用
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: 了解如何使用 Microsoft 365 商业高级版保护 iOS 上的 Office 应用。
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580458"
---
# <a name="secure-office-apps-on-ios"></a>保护 iOS 上的 Office 应用

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

可以设置要求移动用户输入 PIN 或指纹进行登录的用户访问策略，并加密存储在其设备上的工作文件。

## <a name="try-it"></a>试一试！

1. 登录到 Microsoft 365 管理中心。
1. 在 **"策略"** 下，选择 **"添加策略"。**
1. 在"**添加策略"** 窗格中，在"策略名称"下输入名称，然后选择"策略类型"下想要 **的策略类型**。
1. 打开 **"管理用户如何在移动设备上访问 Office 文件"，** 然后确保以下三个设置已打开：
    - **需要 PIN 或指纹才能访问 Office 应用**
    - **在设备丢失或被盗时保护工作文件**
    - **加密工作文件**

1. 在 **"这些应用中的文件将受到保护"下**，选择要在移动设备上保护的 Office 应用。
1. 在“**谁将收到这些设置?**”下方，将默认选中所有用户，但可以选择“**更改**”以选择所创建的任何安全组。
1. 选择“**添加**”，策略即创建完毕。
1. 在“**添加策略**”页面上，选择“**关闭**”。
1. 在管理中心主页上，选择“**策略**”并在“**策略**”页面上查看策略，确认已添加新策略。