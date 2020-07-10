---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何为你的组织设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083534"
---
# <a name="set-up-multi-factor-authentication"></a>设置多重身份验证
  
根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。

开始之前，请确定这些特殊条件是否适用于你并采取相应的行动：

- 如果 Windows 设备上有 Office 2013 客户端，则[启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。

- 如果具有带 Active Directory 联合身份验证服务 (AD FS) 的第三方目录服务，请设置 Azure MFA 服务器。 有关详细信息，请参阅[具有 Azure 多重身份验证的高级方案和第三方 VPN 解决方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

必要时，系统将要求其他所有用户执行额外的身份验证。 有关详细信息，请访问[双因素验证方法和设置](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>步骤 1：确定要求用户使用 MFA 的方法

> [!NOTE]
> 你必须是全局管理员才能设置或修改 MFA。 可通过三种方式要求用户使用 MFA 进行登录。有关详细信息，请参阅 [Microsoft 365 中的 MFA 支持](multi-factor-authentication-microsoft-365.md)。

- 安全性默认值（对于小型企业推荐）

  如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且系统意外提示你进行 MFA，则将自动为你的订阅启用[安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。
  
  每个新的 Microsoft 365 订阅都将自动启用安全性默认值。 这意味着每位用户都必须在其移动设备上设置 MFA 并安装 Microsoft Authenticator 应用。

  所有用户都必须使用 Microsoft Authenticator 应用作为其额外验证方法，而旧式身份验证会被阻止。 

- 条件访问策略（推荐用于企业）

  在 MFA 注册期间，用户可选择其他验证方法。

- 每用户帐户（不推荐）

  在 MFA 注册期间，用户可选择其他验证方法。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>步骤 2. 对引导用户测试 MFA

如果你使用的是条件访问策略或每用户 MFA（不推荐），请在你的企业或组织中选择引导用户以测试 MFA 注册和登录。例如：

- 对于条件访问策略，请创建一个引导用户组和要求对组成员和所有应用进行 MFA 的策略。 然后，将引导用户的帐户添加到组中。

- 对于每用户 MFA，每次对引导用户的用户帐户启用 MFA。

与引导用户协作解决难题和问题，以便你的组织做好平稳推广准备。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>步骤 3. 告知你的组织即将进行 MFA

使用电子邮件通知、走廊海报、团队会议或正式培训来确保员工理解：

- 为什么需要 MFA 才能登录
- [如何注册以获取更多验证方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [注册后如何登录](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何更改其他验证方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [如何处理新智能手机等情况](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

最重要的是，请确保员工了解***何时将要实施 MFA 要求***，以免让他们感到惊讶。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>步骤 4. 向你的组织或用户推出 MFA 要求

根据所选的 MFA 要求方法，向试点测试人员以外的员工推广 MFA 身份验证。

### <a name="security-defaults"></a>安全性默认值

可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。

1.  使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。
2.  转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3.  在页面底部，选择“**管理安全性默认值**”。
4.  选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

如果已在使用[基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，下面是转为使用安全性默认值的方式。

1.  转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2.  选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。
2.  转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4.  在页面底部，选择“**管理安全性默认值**”。
5.  选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

### <a name="conditional-access-policies"></a>条件访问策略

创建、配置和启用相应的策略，其中包括需要使用 MFA 进行登录的用户组。

### <a name="per-user-mfa-not-recommended"></a>每用户 MFA（不推荐）

针对你的推广为用户帐户启用 MFA。

### <a name="supporting-your-employees"></a>为员工提供支持

随着你的员工注册并开始使用 MFA 进行登录，请确保你的 IT 专家、IT 部门或支持人员能够快速回答问题并解决问题。

请参阅本文以获取[有关 MFA 登录疑难解答的信息](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)。 


