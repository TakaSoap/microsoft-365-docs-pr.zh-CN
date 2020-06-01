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
localization_priority: Normal
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
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432375"
---
# <a name="set-up-multi-factor-authentication"></a>设置多重身份验证
  
根据您对[Microsoft 365 中的多重身份验证（MFA）和支持](multi-factor-authentication-microsoft-365.md)的理解，可以将其设置并将其部署到您的组织中。

在开始之前，请先确定这些特殊条件是否适用于您，并采取适当的措施：

- 如果你的 Windows 设备上有 Office 2013 客户端，请[启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。

- 如果您具有具有 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。 有关详细信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>步骤1：决定要求用户使用 MFA 的方法

> [!NOTE]
> 您必须是全局管理员才能设置或修改 MFA。 有三种方法可以要求用户使用 MFA 进行登录。有关详细信息，请参阅[Microsoft 365 中的 MFA 支持](multi-factor-authentication-microsoft-365.md)。

- 安全性默认值（针对小型企业版推荐）

  如果你在2019年10月21日之后购买了订阅或试用，并且意外提示您进行 MFA，则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。
  
  每个新 Microsoft 365 订阅将自动启用安全默认设置。 这意味着，每个用户都必须设置 MFA 并在其移动设备上安装 Microsoft 身份验证器应用。

  所有用户都必须使用 Microsoft 身份验证器应用作为其附加验证方法，并阻止旧版身份验证。 

- 条件访问策略（针对企业推荐）

  用户在 MFA 注册过程中选择其他验证方法。

- 每用户帐户（不推荐）

  用户在 MFA 注册过程中选择其他验证方法。

## <a name="step-2-test-mfa-on-your-pilot-users"></a>步骤 2. 在试点用户上测试 MFA

如果您使用的是条件访问策略或每用户 MFA （不推荐），请选择您的企业或组织中的 "试点用户" 以测试 MFA 注册和登录。例如：

- 对于条件访问策略，创建试点用户组和要求对组成员和所有应用进行 MFA 的策略。 然后，将您的试点用户的帐户添加到组中。

- 对于每用户 MFA，请一次为你的试点用户的用户帐户启用 MFA。

与您的试点用户合作，以解决为您的组织准备平稳推出的问题和问题。

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>第 3 步。 通知贵组织即将推出 MFA

使用电子邮件通知、hallway 海报、团队会议或正式培训以确保员工了解：

- 为什么登录需要进行 MFA
- [如何注册以获取其附加验证方法](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [注册后如何登录](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [如何更改其其他验证方法](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [如何处理像新的智能手机这样的情况](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

最重要的是，请确保你***的员工了解何时强制实施 MFA 要求***，以使其不会令他们感到吃惊。

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>第 4 步。 向你的组织或用户推出 MFA 要求

根据所选的 MFA 要求方法，将 MFA 身份验证部署到您的试点测试人员之外的员工。

### <a name="security-defaults"></a>安全性默认值

您可以在 Azure 门户的 Azure Active Directory （Azure AD）的**属性**窗格中启用或禁用安全默认设置。

1.  使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。
2.  转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
3.  在页面底部，选择“**管理安全性默认值**”。
4.  选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。

如果您使用的是[基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，下面介绍如何移动到使用安全默认设置。

1.  转到 "[条件访问策略" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。
2.  选择启用的每个基准策略，并将 "**启用策略**" 设置为 "**关闭** **"** 。
2.  转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。
4.  在页面底部，选择“**管理安全性默认值**”。
5.  选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。

### <a name="conditional-access-policies"></a>条件访问策略

创建、配置和启用相应的策略，其中包括需要进行 MFA 登录的用户组。

### <a name="per-user-mfa-not-recommended"></a>每用户 MFA （不推荐）

为对应于你的部署的 MFA 启用用户帐户。

### <a name="supporting-your-employees"></a>为你的员工提供支持

在你的员工注册并开始使用 MFA 登录时，请确保你的 IT 专家、IT 部门或技术支持人员能够快速回答问题并解决问题。

有关对[MFA 登录进行疑难解答的信息](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)，请参阅本文。 


