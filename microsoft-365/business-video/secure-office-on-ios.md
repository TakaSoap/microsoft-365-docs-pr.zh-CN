---
title: 在 iOS 上保护 Office 应用
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
description: 了解如何使用 Microsoft 365 商业高级版保护 iOS 上的 Office 应用。
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701587"
---
# <a name="secure-office-apps-on-ios"></a>在 iOS 上保护 Office 应用

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

可以设置要求移动用户输入 PIN 或指纹才能登录的用户访问策略，并加密存储在其设备上的工作文件。

## <a name="try-it"></a>试一试！

1. 登录到 Microsoft 365 管理中心。
1. 在 **"策略"** 下，**选择"添加策略"。**
1. 在 **"添加策略"** 窗格中，在"策略名称"下输入名称，然后选择"策略类型"下想要 **的策略类型**。
1. 打开 **"管理用户如何在移动设备上** 访问 Office 文件"，然后确保以下三项设置已打开：
    - **需要 PIN 或指纹才能访问 Office 应用**
    - **在设备丢失或被盗时保护工作文件**
    - **加密工作文件**

1. 在这些 **应用中的文件将受到保护下**，选择要在移动设备上保护的 Office 应用。
1. 在 **"谁将获取这些设置？"** 下，默认情况下会选择所有用户，但你可以选择"更改"来选择已创建的任何安全组。
1. 若要完成策略创建，请选择"添加 **"。**
1. 在"**添加策略"** 页上，选择"**关闭"。**
1. 在管理中心主页上，通过选择"策略"并查看"策略"页上的策略，确认已添加 **新** 策略。