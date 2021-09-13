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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ab8562eb1ae9a9d45baa31952b0a88ed4a1d9f36
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170024"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>将帐户从Office 365合规中心重定向到Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender
- Defender for Office 365

本文介绍如何通过启用自动重定向Microsoft 365 Defender从以前的 Office 365 安全与合规中心网站将帐户 (protection.office.com) 到 Microsoft 365 Defender (security.microsoft.com) 。

## <a name="what-to-expect"></a>预期结果
启用并激活自动重定向后，访问 Office 365 Security and Compliance (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 Defender (https://security.microsoft.com) 。  

详细了解更改了哪些功能[：Microsoft Defender for Office 365 Microsoft 365 Defender](microsoft-365-security-center-mdo.md)。

启用自动重定向后，当用户使用安全与合规Microsoft 365 Defender安全与合规中心中的Office 365将用户路由到用户。

其中包括威胁管理部分以及威胁管理仪表板和报告的功能。 安全Office 365安全与合规中心内与安全不相关的项目不会重定向到Microsoft 365 Defender。

合规性相关项目可在管理中心Microsoft 365 合规中心，并且可以在管理中心内找到与Exchange项。

重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。 Office 365安全警报同时显示在安全Microsoft 365 Defender安全与Office 365中心，而无需重定向。  

### <a name="set-up-portal-redirection"></a>设置门户重定向
若要开始将帐户路由到Microsoft 365 Defender，security.microsoft.com：

1. 请确保你是全局管理员或在 Azure Active directory 中具有安全管理员权限。
2. [登录到](https://security.microsoft.com/)Microsoft 365 Defender。
3. 导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。  
4. 将"自动重定向"设置切换为 **"打开"。**
5. 单击 **"启用**"将自动重定向应用于Microsoft 365 Defender。

> [!NOTE]
> 启用重定向后，应用此设置时的活动会话中的帐户不会从会话弹出，并且仅在结束当前会话并再次登录后路由到 Microsoft 365 Defender。

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？
如果某些内容无法处理你，或者有任何内容你无法通过 Microsoft 365 Defender，我们希望使用门户反馈选项来收听它。 如果遇到重定向问题，请告诉我们。

还原到以前的门户：

1. [以全局](https://security.microsoft.com/)Microsoft 365 Defender或以 Azure Active directory 中的安全管理员权限使用 和 帐户登录。

2. 导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。

3. 将"自动重定向"设置切换为 **"关"。**

4. 当 **系统&** 时，单击"禁用共享反馈"。

可以随时再次启用此设置。

## <a name="related-information"></a>相关信息
- [Microsoft 365 Defender概述](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 与 SIEM 信息图](https://afrait.com/blog/xdr-versus-siem/) 
- [新 Defender](https://afrait.com/blog/the-new-defender/) 
- [关于Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全门户和管理中心](portals.md)
