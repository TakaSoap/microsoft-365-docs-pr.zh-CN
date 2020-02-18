---
title: 步骤1：创建和保护全局管理员帐户
f1.keywords:
- NOCSH
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
description: 全局管理员帐户需要特殊对待，以确保其免受凭据泄露的影响。
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067339"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>步骤 1：创建和保护全局管理员帐户

![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>保护全局管理员帐户

*这是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将通过确保管理员帐户尽可能的安全，以帮助防止对组织的数字攻击。 为此，你必须：

- 使用[强密码](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)创建多个专用全局管理员帐户，并在必要时使用它们。
- 根据需要，通过向这些角色的其他专用帐户或 IT 人员的用户帐户分配特定管理员角色（如 Exchange 管理员或密码管理员）来执行日常管理。

对于专用全局管理员帐户，还必须：

1. 在测试用户帐户上测试每个用户帐户或基于条件访问的 Azure 多因素身份验证 (MFA) 设置，以确保 MFA 能够正确并以可预见的方式工作。 MFA 需要辅助形式的身份验证，如发送到智能手机的验证码。
2. 为需要进行 MFA 的全局管理员帐户创建和启用条件访问策略，并使用组织提供的最强大的辅助身份验证形式。 有关详细信息，请参阅 [Azure 多因素身份验证](identity-access-prerequisites.md#protecting-administrator-accounts)。

有关额外的保护，请参阅[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)。

> [!Note]
> 在网络攻击等紧急情况下，不受限方案的紧急帐户应为仅限云帐户。 你也可以拥有不是仅限云的全局管理员帐户（符合条件的或永久的）。 有关详细信息，请参阅[在 Azure AD 中管理紧急访问管理帐户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。

此部分的结果是：

- 订阅中唯一具备全局管理员角色的用户帐户是专用全局管理员帐户。 使用以下 Azure Active Directory PowerShell Graph 命令验证这部分： 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 所有管理订阅服务的其他用户帐户分配有与其工作职责相关联的管理员角色。

> [!Note]
> 有关安装 Azure Active Directory PowerShell Graph 模块和登录的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  若要在测试实验室环境中练习此配置，请参阅[保护全局管理员帐户测试实验室指南](protect-global-administrator-accounts-microsoft-365-test-environment.md)。 |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-global-admin)。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>设置按需管理员

*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

在此部分中，将安装 Azure AD Privileged Identity Management (PIM)，以减少管理员帐户易受恶意用户攻击的时间。 PIM 将在必要时按需、实时分配管理员角色。  

管理员帐户将成为符合条件的管理员，而不再是永久管理员。 有人需要管理员角色时，才会激活它。 然后完成激活过程，以将管理员角色在特定时间内添加到管理员帐户。 当时间到期后，PIM 会从管理员帐户中删除管理员角色。

可从 Microsoft 365 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。 或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。

若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pim)。


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>特权访问管理

Office 365 租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改 Office 365 租户中的组织邮箱设置。

在此步骤中，你将在 Office 365 租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的 Office 365 数据和配置设置进行的访问提供额外的安全性。若要开始在 Office 365 组织中使用特权访问，需要执行三个基本步骤：

- 创建审批者的组
- 启用特权访问
- 创建审批策略

配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。

若要启用 Office 365 特权访问管理，请参阅[配置 Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。

有关详细信息，请参阅 [Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。


|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  若要在测试实验室环境中练习此配置，请参阅[特权访问管理测试实验室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md)。 |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-pam)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 2 步](../media/stepnumbers/Step2.png)| [保护密码安全](identity-secure-your-passwords.md) |

