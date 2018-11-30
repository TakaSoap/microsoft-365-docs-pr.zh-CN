---
title: 第 10 步：简化用户登录
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 无缝单一登录（无缝 SSO）。
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865942"
---
# <a name="step-10-simplify-user-sign-in"></a>第 10 步：简化用户登录

** 此步骤对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将设置 Azure Active Directory 无缝单一登录（Azure AD 无缝 SSO），以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码（在许多情况下，还无需键入用户名）。这可使用户更便于访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。

将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。

请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure AD 无缝单一登录](single-sign-on-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这一步的[退出条件](identity-exit-criteria.md#crit-identity-sso)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [自定义 Office 365 登录页](identity-customize-office-365-sign-in.md) |

