---
title: 将帐户从 Microsoft Defender for Office 365 重定向到新的 Microsoft 365 安全中心
description: 如何从 Defender for Office 365 重定向到 Microsoft 365 安全中心。
keywords: Microsoft 365 安全中心，Microsoft 365 安全中心入门，安全中心重定向
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055553"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>将帐户从 Microsoft Defender for Office 365 重定向到 Microsoft 365 安全中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender
- Defender for Office 365

本文介绍如何通过启用从以前的 Microsoft 安全与合规中心 (protection.office.com 或 securitycenter.microsoft.com) 到 Microsoft 365 安全中心 (security.microsoft.com) 的自动重定向，将帐户路由到 Microsoft 365 安全中心。

>[!NOTE]
> 门户重定向功能仅适用于 Office 365 E5 和 Microsoft Defender for Office P2 客户

## <a name="what-to-expect"></a>预期结果
启用和激活自动重定向后，访问 Office 365 安全与合规中心 (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 安全中心 (https://security.microsoft.com) 。  

详细了解更改了哪些功能[：Microsoft 365 安全中心中的 Microsoft Defender for Office 365。](microsoft-365-security-center-mdo.md)

启用自动重定向后，当用户使用 Office 365 安全与合规中心中的安全功能时，他们将被路由到 Microsoft 365 安全中心。

其中包括威胁管理部分以及威胁管理仪表板和报告的功能。 Office 365 安全与合规中心中与安全不相关的项目不会重定向到 Microsoft 365 安全中心。

合规性相关项目可在 Microsoft 365 合规中心内找到，与邮件流相关的项目可在 Exchange 管理中心找到。

重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。 Office 365 安全警报显示在 Microsoft 365 安全中心和 Office 365 安全与合规中心中，无需重定向。  

### <a name="set-up-portal-redirection"></a>设置门户重定向
若要开始将帐户路由到 Microsoft 365 安全中心，security.microsoft.com：

1. 请确保你是全局管理员或在 Azure Active directory 中具有安全管理员权限。
2. [登录到](https://security.microsoft.com/) Microsoft 365 安全中心。
3. 导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。  
4. 将"自动重定向"设置切换为 **"打开"。**
5. 单击 **"** 启用"以将自动重定向应用到 Microsoft 365 安全中心门户。

> [!NOTE]
> 启用重定向后，应用此设置时的活动会话中的帐户不会从会话弹出，并且仅在结束当前会话并再次登录后路由到 Microsoft 365 安全中心。

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？
如果无法通过 Microsoft 365 安全中心门户完成某些操作或无法完成某些操作，我们希望使用门户反馈选项来收听。 如果遇到任何重定向问题，我们鼓励你通过私人预览版直接与你的 PM 好友联系，或者通过"提供反馈提交"表单告诉我们。

还原到以前的门户：

1. [以全局](https://security.microsoft.com/) 管理员或 Azure Active Directory 中的安全管理员权限使用 和 帐户登录 Microsoft 365 安全中心。

2. 导航到 **设置**  >  **终结点**  >  **常规**  >  **门户重定向**。  

3. 将"自动重定向"设置切换为 **"关"。**

4. 当 **系统&** 时，单击"禁用共享反馈"。

可以随时再次启用此设置。

禁用后，帐户将不再路由到 security.microsoft.com，并且你将再次有权访问以前的门户 -securitycenter.windows.com 或 securitycenter.microsoft.com。

## <a name="related-information"></a>相关信息
- [Microsoft 365 安全中心概述](overview-security-center.md)
- [Microsoft 365 安全中心中的 Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 与 SIEM 信息图](https://afrait.com/blog/xdr-versus-siem/) 
- [新 Defender](https://afrait.com/blog/the-new-defender/) 
- [关于 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全门户和管理中心](portals.md)