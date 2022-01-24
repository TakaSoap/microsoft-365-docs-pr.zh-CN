---
title: 将帐户从 Microsoft Defender for Endpoint 重定向到Microsoft 365 Defender
description: 如何将帐户和会话从 Defender for Endpoint 重定向到Microsoft 365 Defender。
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 64a9926253ea699fa6cc62d1ec2d80d07f25fd29
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172268"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>将帐户从 Microsoft Defender for Endpoint 重定向到Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender
- Defender for Endpoint

为了与 Microsoft 使用 SIEM 进行威胁防护的跨域方法以及扩展检测和响应 (XDR) 一致，我们将 Microsoft Defender 高级威胁防护重新品牌化为适用于终结点的 Microsoft Defender，并统一到单个集成门户：Microsoft 365 Defender。

本指南介绍如何通过启用自动Microsoft 365 Defender从以前的 Microsoft Defender 终结点门户或 (securitycenter.windows.com 或 securitycenter.microsoft.com) 重定向到 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">。</a>

> [!NOTE]
> Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商 ([MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)授予访问权限，其方式与在 Microsoft Defender 安全中心 中授予访问权限[的方式相同](./mssp-access.md)。

## <a name="what-to-expect"></a>预期结果

启用自动重定向后，在 securitycenter.windows.com 或 securitycenter.microsoft.com 访问前 Microsoft Defender 终结点门户的帐户将自动路由到位于<security.microsoft.com>的 Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>。

详细了解更改了哪些功能[：Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)。

这包括通过浏览器直接访问以前的门户的重定向，包括指向以前的 securitycenter.windows.com 门户的链接（如电子邮件通知中的链接，以及 SIEM API 调用返回的链接）。  

 电子邮件通知或 SIEM API 中的外部链接当前包含指向这两个门户的链接。 启用重定向后，两个链接将Microsoft 365 Defender，直到最终删除旧链接。 我们鼓励你采用指向该链接的新Microsoft 365 Defender。

有关链接和路由的详细信息，请参阅下表。
## <a name="siem-api-routing"></a>SIEM API 路由

| 属性 | 重定向关闭时的目标 | 重定向打开时的目标 |
|---------|---------|---------|
| LinkToWDATP | 警报页 securitycenter.windows.com | 警报页 security.microsoft.com |
| IncidentLinkToWDATP | 事件页面中 securitycenter.windows.com | 事件页面中 security.microsoft.com |
| LinkToMTP | 警报页 security.microsoft.com | 警报页 security.microsoft.com |
| IncidentLinkToMTP | 事件页面中 security.microsoft.com | 事件页面中 security.microsoft.com |

## <a name="email-alert-notifications"></a>电子邮件通知

| 属性 | 重定向为 OFF 时的目标** | 重定向打开时的目标 |
|---------|---------|---------|
| 警报页面 | 警报页 securitycenter.windows.com | 警报页 security.microsoft.com |
| 事件页面 |事件页面中 securitycenter.windows.com | 事件页面中 security.microsoft.com |
| Defender for Cloud 门户中的警报页面 | 警报页 security.microsoft.com | 警报页 security.microsoft.com |
| Defender for Cloud 门户中的事件页面 | 事件页面中 security.microsoft.com | 事件页面中 security.microsoft.com |

## <a name="when-does-this-take-effect"></a>这何时生效？

启用后，此更新可能会立即对一些帐户生效。 但是，重定向可能需要更长时间才能传播到组织的每一个帐户。 应用此设置时的活动会话中的帐户不会从其会话中弹出，并且仅在结束当前会话并再次登录后Microsoft 365 Defender路由到 Microsoft 365 Defender。  

### <a name="set-up-portal-redirection"></a>设置门户重定向

若要开始将帐户路由到Microsoft 365 Defender：

1. 确保你是全局管理员或拥有安全管理员权限Azure Active Directory。

2. 登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>。

3. 导航到 **设置**  >    >  **终结点常规**  >  **门户重定向或**[单击此处](https://security.microsoft.com/preferences2/portal_redirection)。  

4. 将"自动重定向"设置切换为 **"打开"。**

5. 单击 **"启用**"将自动重定向应用于Microsoft 365 Defender。

>[!IMPORTANT]
>启用此设置不会终止活动用户会话。 应用此设置时，活动会话中的帐户只有在结束当前会话并再次登录Microsoft 365 Defender才能定向到当前会话。

>[!NOTE]
>您必须是全局管理员或具有安全管理员权限Azure Active Directory才能启用或禁用此设置。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？

如果某些操作对没有用，或者你无法通过 Microsoft 365 Defender完成，我们希望听到有关它的声音。 如果遇到重定向问题，我们鼓励你使用"提供反馈提交"表单告知我们。

若要还原到以前的 Microsoft Defender 终结点门户：

1. 以全局<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>或 Azure Active directory 中的安全管理员权限使用 和 帐户登录。

2. 导航到 **设置**  >    >  **终结点常规**  >  **门户重定向，** 或 [在此处打开页面](https://security.microsoft.com/preferences2/portal_redirection)。  

3. 将"自动重定向"设置切换为 **"关"。**

4. 当 **系统&** 时，单击"禁用共享反馈"。

可以随时再次启用此设置。 

禁用后，帐户将不再路由到 security.microsoft.com，并且你将再次有权访问以前的门户-securitycenter.windows.com 或 securitycenter.microsoft.com。 

## <a name="related-information"></a>相关信息
- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR 与 SIEM 信息图](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [关于Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft 安全门户和管理中心](portals.md)
