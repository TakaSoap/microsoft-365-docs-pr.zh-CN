---
title: 步骤 2：保护你的特权标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解管理员帐户并为其配置最大保护。
ms.openlocfilehash: 0be82fc6f431001c69e79a0a26007c54a87424c3
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353084"
---
# <a name="step-2-secure-your-privileged-identities"></a>步骤 2：保护你的特权标识

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>保护全局管理员帐户

*这是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。 为此，你必须：

- 使用特别[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建专用全局管理员帐户，并在必要时使用它们。
- 根据需要通过向 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。

对于专用全局管理员帐户，还必须：

1. 在测试用户帐户上测试每个用户帐户或基于条件访问的多重身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。
2. 为每个专用的 Office 365 全局管理员帐户配置 MFA，并使用组织中可用的最强形式的辅助身份验证。有关详细信息，请参阅[多重身份验证](identity-multi-factor-authentication.md#identity-mfa)。
2. 使用条件访问策略要求对全局管理员帐户进行 MFA。有关详细信息，请参阅[保护管理员帐户](identity-access-prerequisites.md#protecting-administrator-accounts)。

有关配置的详细信息，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)。

> [!Note]
> 组织应使用仅限云标识来创建特权帐户（如全局管理员），以便应对网络攻击等的紧急情况。有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。

此部分的结果是：

- 订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。 使用 Azure Active Directory PowerShell Graph 命令验证这部分： 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。

> [!Note]
> 有关安装 Azure Active Directory PowerShell Graph 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：保护全局管理员帐户](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>设置按需全局管理员

*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

在此部分中，将安装 Azure AD Privileged Identity Management (PIM)，以减少全局管理员帐户易受恶意用户攻击的时间。 PIM 将在必要时按需、实时分配全局管理员角色。  

全局管理员帐户成为符合条件的管理员，而不再是永久管理员。有人需要全局管理员角色时，才会激活它。然后完成激活过程，以将全局管理员角色在特定时间内添加到全局管理员帐户。当时间到期后，PIM 会从全局管理员帐户删除全局管理员角色。

可从 Microsoft 365 Enterprise E5 包含的 Azure Active Directory Premium P2 中获取 PIM。或者可以为全局管理员帐户单独购买 Azure Active Directory Premium P2 许可证。

若要为 Azure AD 租户和全局管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pim)。


## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [配置混合标识](identity-azure-ad-connect.md) |

