---
title: 将帐户从 Office 365 安全与合规中心重定向到新的 Microsoft 365 Defender
description: 如何从 Defender for Office 365 重定向到 Microsoft 365 Defender。
keywords: Microsoft 365Defender， 开始使用 Microsoft 365 Defender， 安全中心重定向
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842514"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>将帐户从安全Office 365中心重定向到 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender
- Defender for Office 365

本文介绍如何通过启用从以前的 Microsoft 365 Office 365 安全与合规中心 (protection.office.com) 到 Microsoft 365 Defender (security.microsoft.com) 的自动重定向，将帐户路由到 Microsoft 365 Defender。

## <a name="what-to-expect"></a>预期结果
启用并激活自动重定向后，访问 Office 365 Security and Compliance (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 Defender (https://security.microsoft.com) 。  

了解有关更改功能[：Microsoft Defender for Office 365 defender Microsoft 365。](microsoft-365-security-center-mdo.md)

启用自动重定向后，当用户使用 Microsoft 365 安全与合规中心中的Office 365时，他们将被路由到 Office 365 Defender。

其中包括威胁管理部分以及威胁管理仪表板和报告的功能。 安全Office 365安全与合规中心内与安全不相关的项目不会重定向到 Microsoft 365 Defender。

合规性相关项目可在合规性Microsoft 365中心内找到，并且可以在管理中心内找到与Exchange项。

重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。 Office 365 Defender 和 Microsoft 365 安全与合规中心Office 365安全警报，无需重定向。  

### <a name="set-up-portal-redirection"></a>设置门户重定向
若要开始将帐户路由到 Microsoft 365 Defender，security.microsoft.com：

1. 请确保你是全局管理员或在 Azure Active directory 中具有安全管理员权限。
2. [登录到](https://security.microsoft.com/)Microsoft 365 Defender。
3. 导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。  
4. 将"自动重定向"设置切换为 **"打开"。**
5. 单击 **"启用**"将自动重定向应用到 Microsoft 365 Defender。

> [!NOTE]
> 启用重定向后，应用此设置时的活动会话中的帐户不会从会话弹出，并且仅在结束当前会话并再次登录后路由到 Microsoft 365 Defender。

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？
如果某些内容无法用于你，或者如果你无法通过 Microsoft 365 Defender 完成某些操作，我们希望使用门户反馈选项来收听它。 如果遇到重定向问题，请告诉我们。

还原到以前的门户：

1. [以全局](https://security.microsoft.com/)Microsoft 365或 Azure Active directory 中的安全管理员权限使用 和 帐户登录 Defender。

2. 导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。   

3. 将"自动重定向"设置切换为 **"关"。**

4. 当 **系统&** 时，单击"禁用共享反馈"。

可以随时再次启用此设置。

禁用后，帐户将不再路由到 security.microsoft.com，并且你将再次有权访问以前的门户-securitycenter.windows.com 或 securitycenter.microsoft.com。

## <a name="related-information"></a>相关信息
- [Microsoft 365Defender 概述](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 与 SIEM 信息图](https://afrait.com/blog/xdr-versus-siem/) 
- [新 Defender](https://afrait.com/blog/the-new-defender/) 
- [关于 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全门户和管理中心](portals.md)
