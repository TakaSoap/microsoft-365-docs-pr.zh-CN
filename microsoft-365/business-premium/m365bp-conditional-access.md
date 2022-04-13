---
title: 为Microsoft 365 商业高级版启用安全默认值
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解安全默认值如何通过为Microsoft 365 商业高级版提供预配置的安全设置来帮助保护组织免受与标识相关的攻击。
ms.openlocfilehash: 58477da3d44844c763dff95d35fc71753afc7ce2
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824501"
---
# <a name="turn-on-security-defaults-for-microsoft-365-business-premium"></a>为Microsoft 365 商业高级版启用安全默认值

安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。 这些设置包括为所有管理员和用户帐户启用多重身份验证 (MFA) 。 对于大多数组织来说，安全默认值提供一定级别的附加登录安全性。

有关安全默认值及其强制实施的策略的详细信息， [请参阅什么是安全默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果订阅是在 2019 年 10 月 22 日或之后创建的，则可能已自动启用安全默认值，应&mdash;检查设置以确认。

若要在Azure Active Directory (Azure AD) 中启用安全默认值，或检查是否已启用安全默认值：

1. 使用安全管理员、条件访问管理员或全局管理员凭据登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>。

2. 在左窗格中，选择 **“全部显示”，** 然后在 **管理中心** 下选择 **Azure Active Directory**。

3. 在 **Azure Active Directory管理中心的** 左窗格中，选择 **Azure Active Directory**。

4. 在“ **管理** ”部分的“仪表板”左侧菜单中，选择 **“属性**”。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="显示“属性”菜单项位置的Azure Active Directory管理中心的屏幕截图。":::

5. 在“ **属性”** 页底部，选择 **“管理安全性默认值**”。

6. 在右窗格中，你将看到 **“启用安全性默认** 设置”。 如果选择了 **“是** ”，则已启用安全默认值，无需执行进一步操作。 如果当前未启用安全默认值，请选择 **“是** ”以启用它们，然后选择 **“保存**”。

> [!NOTE]
> 如果一直在使用条件访问策略，则需要在使用安全默认值之前将其关闭。
>
> 可以使用安全默认值或条件访问策略，但不能同时使用这两种策略。

## <a name="consider-using-conditional-access"></a>考虑使用条件访问

如果你的组织具有复杂的安全要求，或者需要对安全策略进行更精细的控制，则应考虑使用条件访问而不是安全默认值来实现类似或更高的安全状况。 

条件访问允许你创建和定义对登录事件做出反应的策略，并在向用户授予对应用程序或服务的访问权限之前请求其他操作。 条件访问策略可以是精细且具体的，使用户能够随时随地高效工作，同时保护组织。

安全默认值适用于所有客户，而条件访问需要以下计划之一的许可证：

- Azure Active Directory Premium P1或 P2
- Microsoft 365 商业高级版
- Microsoft 365 E3 或 E5
- Enterprise移动性&安全 E3 或 E5

如果要使用条件访问配置与安全默认值启用的策略等效的策略，请查看以下分步指南：

- [要求对管理员执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

- [需要 MFA 进行 Azure 管理](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)

- [阻止传统身份验证](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

- [要求对所有用户执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

- [需要Azure AD MFA 注册](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - 需要Azure AD标识保护，这是Azure Active Directory Premium P2的一部分

若要详细了解条件访问， [请参阅什么是条件访问？](/azure/active-directory/conditional-access/overview) 有关创建条件访问策略的详细信息，请参阅 [“创建条件访问”策略](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。

> [!NOTE]
> 如果你的计划或许可证提供条件访问，但尚未创建任何条件访问策略，则欢迎使用安全默认值。 但是，需要先关闭安全默认值，然后才能使用条件访问策略。
