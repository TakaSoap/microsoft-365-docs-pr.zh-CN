---
title: 第 2 步：保护全局管理员帐户
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
description: 了解管理员帐户并为其配置最大保护。
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866036"
---
# <a name="step-2-protect-global-administrator-accounts"></a>第 2 步：保护全局管理员帐户

*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。为此，你必须：

- 使用特别[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建专用全局管理员帐户，并在必要时使用它们。
- 根据需要通过向 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。

对于专用全局管理员帐户，还必须：

1. 在测试用户帐户上测试每个用户帐户或基于条件访问的多重身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。
2. 为每个专用的 Office 365 全局管理员帐户配置 MFA，并使用组织中可用的最强形式的辅助身份验证。有关详细信息，请参阅[多重身份验证](identity-multi-factor-authentication.md)。
2. 使用条件访问策略要求对全局管理员帐户进行 MFA。有关详细信息，请参阅[保护管理员帐户](identity-access-prerequisites.md#protecting-administrator-accounts)。
4. 使用 Office 365 云应用安全策略来监控全局管理员帐户活动。有关详细信息，请参阅[配置增强的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)。

有关配置的详细信息，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)。

> [!Note]
> 组织应使用仅限云标识来创建特权帐户（如全局管理员），以便应对网络攻击等的紧急情况。有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。

此步骤结果是：

- 订阅中具有全局管理员角色的唯一用户帐户是一组新的专用全局管理员帐户。使用以下 Windows Azure AD V2 PowerShell 命令对此进行验证： 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。

> [!Note]
> 有关安装 Azure AD V2 PowerShell 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：保护全局管理员帐户](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [设置按需全局管理员](identity-privileged-identity-management.md) |

