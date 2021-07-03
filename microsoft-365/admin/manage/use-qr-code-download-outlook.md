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
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286701"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 代码登录到 Outlook移动应用

> [!IMPORTANT]
> 此功能仅适用于已在此版本中打开定向发布Microsoft 365 管理中心。 若要打开定向发布并了解其工作方式的详细信息，请参阅 [设置标准或定向发布选项](release-options-in-office-365.md)。 未来几周内，我们将通过公共预览版扩展到更多组织。 公共预览版可提前访问Microsoft 365功能。

作为Microsoft 365管理员，你可以让用户登录到 Outlook for Android 或 iOS 应用，而无需输入用户名和密码。 通过扫描 QR 代码，用户可以安全地进行身份验证并登录到Outlook登录。

在Outlook 网页版或其他桌面Outlook应用程序中，用户可能会看到通知，通知他们可在Outlook设备上使用桌面设备。 管理员可以使用 Powershell 管理Exchange通知。 如果用户选择向自己发送短信以在移动设备上下载应用，QR 代码将显示在其计算机上。 他们将能够扫描 QR 代码，以登录到Outlook或平板电脑上的设备。 此 QR 代码是只能兑换一次短期令牌。

> [!NOTE]
> 在某些情况下，用户必须重新验证其计算机以生成 QR 代码。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

默认情况下，启用此功能。 若要禁用此功能，请按照以下步骤操作。

1. [连接 PowerShell Exchange 。](/powershell/exchange/connect-to-exchange-online-powershell)
2. 使用 PowerShell，可以禁用通知用户有关Outlook通知。 这还会阻止显示 QR 代码登录流。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>相关内容

[设置标准发布选项或定向发布 (](release-options-in-office-365.md) 文章) \
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (文章) 