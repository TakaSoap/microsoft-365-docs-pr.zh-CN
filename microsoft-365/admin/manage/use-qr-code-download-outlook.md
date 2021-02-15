---
title: 使用 QR 代码登录 Outlook 移动应用
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
description: 了解如何使用 QR 代码进行身份验证和下载 Outlook 移动版。
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242350"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 代码登录 Outlook 移动应用

> [!IMPORTANT]
> 此功能仅适用于在 Microsoft 365 管理中心中打开定向发布的组织。 若要打开定向发布并了解有关其工作方式的详细信息，请参阅 ["设置标准"或](release-options-in-office-365.md)"定向发布"选项。 我们将通过公共预览版在几周内扩展到更多组织。 公共预览版可提前访问 Microsoft 365 功能。

作为 Microsoft 365 管理员，你可以允许用户登录到其移动设备上的 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。 通过扫描 QR 代码，用户可以安全地进行身份验证并登录到 Outlook 移动版。

在 Outlook 网页版或其他桌面 Outlook 应用程序中，用户可能会看到通知，通知他们可以在移动设备上使用 Outlook。 管理员可以使用 Exchange Powershell 管理这些通知。 如果用户选择向自己发送短信以在移动设备上下载应用，QR 代码将显示在其计算机上。 他们将能够扫描 QR 代码以登录到其手机或平板电脑上的 Outlook。 此 QR 代码是只能兑换一次短期令牌。

> [!NOTE]
> 在某些情况下，用户必须在计算机上重新进行身份验证，以生成 QR 代码。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

默认情况下，启用此功能。 若要禁用此功能，请按照以下步骤操作。

1. [连接到 Exchange PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. 使用 PowerShell，可以禁用通知用户有关 Outlook 移动应用的通知。 这还会阻止显示 QR 代码登录流。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

相关主题

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
