---
title: 使用 QR 代码登录到 Outlook 移动应用
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: 了解如何使用 QR 代码进行身份验证并下载 Outlook 移动版。
ms.openlocfilehash: a648722877580899f9747afa20bd758be2589a7ab2fb794a636614b032e063cf
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824391"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>使用 QR 代码登录到 Outlook 移动应用

> [!IMPORTANT]
> 此功能仅适用于已在 Microsoft 365 管理中心中启用目标发布的组织。 要启用目标发布并详细了解其工作原理，请参阅 [设置标准或目标发布选项](release-options-in-office-365.md)。 我们将在未来几周内通过公共预览版扩展到更多组织。 公共预览版提供对 Microsoft 365 功能的提前访问。

作为 Microsoft 365 管理员，你可以让用户在其移动设备上登录到 Outlook for Android 或 iOS 应用，而无需输入其用户名和密码。 通过扫描 QR 代码，用户可以安全地进行身份验证并登录到 Outlook 移动版。

在 Outlook 网页版或其他桌面 Outlook 应用程序中，用户可能会看到通知，提示他们可以在其移动设备上使用 Outlook。 管理员可以使用 Exchange PowerShell 管理这些通知。 如果用户选择向自己发送短信以在其移动设备上下载应用，则其计算机上将显示 QR 代码。 他们将能够扫描 QR 代码以登录到其手机或平板电脑上的 Outlook。 此 QR 代码是一个生存期较短的令牌，只能兑换一次。

仅当满足以下条件时才会生成通知：

1. 已为租户启用 QR 代码体验（默认情况下启用此体验）。

2. 用户尚未使用 Outlook for iOS 和 Android。

3. 用户在阅读窗格中具有空状态（未选择“自动打开第一封电子邮件”选项）。

4. 用户未关闭通知。

> [!NOTE]
> 在某些情况下，用户必须在其计算机上重新进行身份验证才能生成 QR 代码。

## <a name="use-exchange-powershell"></a>使用 Exchange PowerShell

默认情况下，启用此功能。 要禁用此功能，请执行以下步骤。

1. [连接到 Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
2. 使用 PowerShell，可以禁用提示用户有关 Outlook 移动应用的通知。 此操作还会阻止显示 QR 代码登录流。

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>相关内容

[设置标准发布或目标发布选项](release-options-in-office-365.md)（文章\）
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)（文章）
