---
title: 步骤 3：保护和管理用户登录
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 你可以让用户更安全地登录到 Windows 设备和 Microsoft 365。
ms.openlocfilehash: edf51b344ed8f9c8e13587cc2ccf0ba1ed081da6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37075407"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>步骤 3：保护和管理用户登录

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>使用 Windows Hello 企业版

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

Windows 10 企业版中的 Windows Hello 企业版在 Windows 设备上签名时，会将密码替换为强双因素身份验证。 这两个因素是一种与设备和生物识别或 PIN 相关联的新型用户凭据。

有关详细信息，请参阅 [Windows Hello 企业版概述](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>设置 Azure 多因素身份验证

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此步骤中，将设置 Azure 多因素身份验证 (MFA)，为用户登录和事务添加第二层安全性。 用户正确输入密码后，MFA 需要一种附加验证方法。 如果不使用 MFA，则密码是唯一的验证方法。 对于密码而言，其问题在于许多密码很容易被攻击者猜到，或在不知情的情况下与非受信任方共享。

使用 MFA，第二层安全可以是：

- 不易被欺骗或者复制的个人和受信任设备，如智能手机。
- 生物识别属性，如指纹。

将启用 MFA 并使用[条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)配置次要身份验证方法，该方法允许使用 Azure Active Directory (Azure AD) 组向指定的用户组（如试点用户、地理区域或部门）推出 MFA。 请确保用户知道已启用 MFA，以便他们理解要求（如强制使用智能手机进行登录）并可以成功登录。 

有关详细信息，请参阅[规划基于云的 Azure 多因素身份验证部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure 多因素身份验证](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>防止凭据泄露

*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。 Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者破坏用户帐户的凭据。

使用 Azure AD Identity Protection，可以：

|||
|:---------|:---------|
|确定并解决组织身份中的潜在漏洞|Azure AD 使用机器学习功能检测不正常和可疑活动，如登录和登录后活动。 通过使用此数据，Azure AD Identity Protection 会生成报告和警报，帮助你评估问题并执行操作。|
|检测与组织身份相关的可疑操作并自动对其响应|可以配置基于风险的策略，该策略可在达到指定风险级别时自动响应检测到的问题。 除了 Azure AD 与 Microsoft Intune 提供的其他条件性访问控制以外，这些策略也可以自动阻止访问或采取纠正措施，包括密码重置和要求后续登录的 Azure 多因素身份验证。|
|调查可疑事件并使用管理操作加以解决|可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。|

请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。

请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。

此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：

- 解决潜在标识漏洞。
- 检测可能的凭据泄露尝试。
- 调查和解决正在进行的可疑身份活动。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [添加用户帐户](identity-add-user-accounts.md) |
