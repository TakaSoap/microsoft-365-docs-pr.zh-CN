---
title: 打开安全默认值
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 了解安全默认值如何通过提供预配置的安全设置来帮助保护组织免受与标识相关的攻击。
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170794"
---
# <a name="turn-on-security-defaults"></a>打开安全默认值

安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。 这些设置包括在所有管理员和用户帐户 (MFA) 多重身份验证。 对于大多数组织来说，安全默认值提供了良好的附加登录安全级别。

有关安全默认值及其强制策略详细信息，请参阅 [什么是安全默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果订阅是在 2019 年 10 月 22 日当天或之后创建的，则可能会自动启用安全默认值，你应该 &mdash; 检查设置以确认。

若要在 Azure AD Azure Active Directory (启用) 或检查它们是否已启用：

1. 使用全局管理员<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>登录帐户。

2. 在左侧窗格中，选择"全部 **显示**"，然后在"管理中心"**下，选择****"Azure Active Directory"。**

3. 在管理中心左侧窗格中 **，Azure Active Directory选择****"Azure Active Directory"。**

4. 从仪表板的左侧菜单中的"管理"**部分**，选择"属性 **"。**

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="显示&quot;Azure Active Directory&quot;菜单项位置的&quot;管理中心&quot;屏幕截图。":::

5. 在"属性"页 **底部**，选择"**管理安全性默认值"。**

6. 在右侧窗格中，你将看到" **启用安全性默认设置"** 设置。 如果 **选择了** "是"，则已启用安全默认值，无需执行任何进一步的操作。 如果当前未启用安全默认值，请选择"是"以启用它们，然后选择"保存 **"。**

> [!NOTE]
> 如果一直使用条件访问策略，则需要在使用安全默认值之前将其关闭。
>
> 可以使用安全默认值或条件访问策略，但不能同时使用这两者。

## <a name="consider-using-conditional-access"></a>考虑使用条件访问

如果您的组织具有复杂的安全要求，或者您需要更精细地控制安全策略，则应考虑使用条件访问而非安全默认值来实现类似或更高的安全状况。 

条件访问允许你创建和定义对登录事件做出反应的策略，并请求执行其他操作，然后再向用户授予应用程序或服务的访问权限。 条件访问策略可以精细具体化，使用户能够随时随地高效工作，还可以保护组织。

安全默认值可供所有客户使用，而条件访问需要以下计划之一的许可证：

- Azure Active Directory Premium P1 或 P2
- Microsoft 365 商业高级版
- Microsoft 365 E3 或 E5
- Enterprise移动性&安全性 E3 或 E5

如果要使用条件访问配置与安全默认值启用的策略等效的策略，请查看以下分步指南：

- [要求对管理员执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [需要 MFA 进行 Azure 管理](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [阻止传统身份验证](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [要求对所有用户执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [需要 Azure AD MFA 注册](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)- 需要 Azure AD Identity Protection，这是 azure AD 标识保护Azure Active Directory Premium P2

若要详细了解条件访问，请参阅 [什么是条件访问？](/azure/active-directory/conditional-access/overview) 有关创建条件访问策略的信息，请参阅 [创建条件访问策略](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。

> [!NOTE]
> 如果你有提供条件访问但尚未创建任何条件访问策略的计划或许可证，则欢迎使用安全默认值。 但是，您需要先关闭安全默认值，然后才能使用条件访问策略。
