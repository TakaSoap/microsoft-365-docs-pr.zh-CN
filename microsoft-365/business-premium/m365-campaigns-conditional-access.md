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
description: 了解安全默认值如何通过提供预配置的安全设置来帮助保护组织免受与标识相关的攻击。
ms.openlocfilehash: ce8cd568fa452aa6c4ff9b03cf2a17ed57d959b6
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766212"
---
# <a name="turn-on-security-defaults"></a>打开安全默认值

安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。 这些设置包括在所有管理员和用户帐户 (MFA) 多重身份验证。 对于大多数组织来说，安全默认值提供了良好的附加登录安全级别。

有关安全默认值及其强制策略详细信息，请参阅 [什么是安全默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果你的订阅是在 2019&mdash; 年 10 月 22 日当天或之后创建的，则你可能已经自动启用了安全默认值，你应该检查你的设置以确认。

若要启用安全默认值Azure Active Directory (Azure AD) 或检查它们是否已启用：

1. 使用安全管理员<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>条件访问管理员或全局管理员凭据登录网站。

2. 在左侧窗格中，选择"**全部显示**"，**然后在"管理** 中心"下，选择"Azure Active Directory **"**。

3. 在管理中心的左窗格中，**Azure Active Directory选择**"Azure Active Directory **"**。

4. 从仪表板的左侧菜单中的"管理" **部分** ，选择"属性 **"**。

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="显示&quot;Azure Active Directory&quot;菜单项位置的&quot;管理中心&quot;屏幕截图。":::

5. 在"属性"页 **底部** ，选择" **管理安全性默认值"**。

6. 在右侧窗格中，你将看到" **启用安全性默认设置"** 设置。 如果 **选择了** "是"，则已启用安全默认值，无需执行任何进一步的操作。 如果当前未启用安全默认值，请选择"是"以启用它们，然后选择"保存 **"**。

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
- [需要Azure AD MFA 注册](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - 需要Azure AD Identity Protection，这是 Azure Active Directory Premium P2

若要详细了解条件访问，请参阅 [什么是条件访问？](/azure/active-directory/conditional-access/overview) 有关创建条件访问策略的信息，请参阅 [创建条件访问策略](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。

> [!NOTE]
> 如果你有提供条件访问但尚未创建任何条件访问策略的计划或许可证，则欢迎使用安全默认值。 但是，您需要先关闭安全默认值，然后才能使用条件访问策略。
