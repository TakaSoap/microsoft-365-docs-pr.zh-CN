---
title: 使用 QR 代码登录到 Outlook移动应用
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: 了解如何使用 QR 代码在移动设备上进行身份验证和Outlook下载。
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914962"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 代码登录到 Outlook移动应用

> [!IMPORTANT]
> 此功能仅适用于在管理中心内打开定向发布Microsoft 365使用。 若要打开定向发布并了解其工作方式的详细信息，请参阅 [设置标准或定向发布选项](release-options-in-office-365.md)。 未来几周内，我们将通过公共预览版扩展到更多组织。 公共预览版可提前访问Microsoft 365功能。

作为Microsoft 365管理员，你可以让用户登录到 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。 通过扫描 QR 代码，用户可以安全地进行身份验证并登录到Outlook登录。

在Outlook或其他桌面Outlook应用程序中，用户可能会看到通知，通知他们可在Outlook使用移动设备。 管理员可以使用 Powershell 管理Exchange通知。 如果用户选择向自己发送短信短信，以在移动设备上下载应用，QR 代码将显示在其计算机上。 他们将能够扫描 QR 代码，以登录到Outlook或平板电脑上的设备。 此 QR 代码是只能兑换一次短期令牌。

> [!NOTE]
> 在某些情况下，用户必须在计算机上重新进行身份验证以生成 QR 代码。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

默认情况下，启用此功能。 若要禁用此功能，请按照以下步骤操作。

1. [连接 PowerShell Exchange 。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. 使用 PowerShell，可以禁用通知用户有关Outlook通知。 这还将阻止显示 QR 代码登录流。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

相关主题

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)