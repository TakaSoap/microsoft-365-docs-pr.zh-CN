---
title: 将帐户从Office 365合规中心重定向到新的Microsoft 365 Defender
description: 如何从 Defender for Office 365 重定向到Microsoft 365 Defender。
keywords: Microsoft 365 Defender、安全Microsoft 365 Defender重定向入门
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.custom:
- admindeeplinkDEFENDER
- admindeeplinkEXCHANGE
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fc49494d924129ed2771bc399467f3e9101e7620
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172351"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>将帐户从Office 365合规中心重定向到Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender
- Defender for Office 365

本文介绍如何通过启用从以前的 Office 365 安全与合规中心 Microsoft 365 Defender 自动重定向到 (protection.office.com) ，将帐户Microsoft 365 Defender (security.microsoft.com) 。

## <a name="what-to-expect"></a>预期结果

启用并激活自动重定向后，访问 Office 365 Security and Compliance (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">。</a>

详细了解更改了哪些功能[：Microsoft Defender for Office 365 Microsoft 365 Defender](microsoft-365-security-center-mdo.md)。

启用自动重定向后，当用户使用 Microsoft 365 Defender 安全与合规中心中的Office 365功能时，用户将被路由到用户。

这些功能包括威胁管理部分、警报 (查看警报和警报策略) 以及威胁管理仪表板和报告。 安全Office 365安全与合规中心内与安全不相关的项目不会重定向到Microsoft 365 Defender。

合规性相关项目可以在管理中心Microsoft 365 合规中心，并且可以在管理中心内找到与Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">项</a>。

重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。

### <a name="set-up-portal-redirection"></a>设置门户重定向

自 2021 年 10 月开始，门户重定向现在自动完成，或默认执行。 但是，如果需要暂时禁用它，将执行这些步骤。

<!--To start routing accounts to Microsoft 365 Defender at <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">security.microsoft.com</a>:

1. Make sure you're a global administrator or have security administrator permissions in Azure Active directory.
2. Sign in to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.
3. Go to **Settings** > **Email & collaboration** > **Portal redirection**.  
4. Toggle the Automatic redirection setting to **On**.
5. Click **Enable** to apply automatic redirection to Microsoft 365 Defender.

> [!NOTE]
> After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.-->

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？

If something isn't working for you or if there's anything you're unable to complete through Microsoft 365 Defender， we want to hear about it using the portal feedback option. 如果遇到重定向问题，请告诉我们。

还原到以前的门户：

1. 以全局<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>或 Azure Active directory 中的安全管理员权限使用 和 帐户登录。

2. 转到 **"设置**  >  **电子邮件&协作**  >  **门户重定向"。**

3. 将"自动重定向"设置切换为 **"关"。**

4. 当 **系统&** 时，单击"禁用共享反馈"。

可以随时再次启用此设置。

## <a name="related-information"></a>相关信息
- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 与 SIEM 信息图](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [关于Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全门户和管理中心](portals.md)
