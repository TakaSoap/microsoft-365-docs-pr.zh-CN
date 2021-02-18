---
title: 保护 Microsoft 365 全局管理员帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: 本文提供有关保护全局管理员对 Microsoft 365 订阅的访问的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f84ca33a620c3ea3c24f46eb29c1a39c28840e7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289635"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>保护 Microsoft 365 全局管理员帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365 订阅的安全漏洞（包括信息收集和网络钓鱼攻击）通常是通过损害 Microsoft 365 全局管理员帐户的凭据而发生的。 云中的安全是你与 Microsoft 之间的合作关系：
  
- Microsoft 云服务建立在信任和安全性的基础上。 Microsoft 提供了安全控件和功能，可帮助你保护数据和应用程序。
    
- 你拥有数据和标识以及保护它们的责任、本地资源的安全性以及你控制的云组件的安全性。
    
Microsoft 提供了可帮助保护组织的功能，但这些功能仅在使用这些功能时有效。 如果不使用它们，你很容易受到攻击。 若要保护全局管理员帐户，Microsoft 将帮助你获得详细说明，以：
  
1. 创建专用的 Microsoft 365 全局管理员帐户，并仅在必要时使用它们。
    
2. 为专用 Microsoft 365 全局管理员帐户配置多重身份验证，并使用最强形式的辅助身份验证。
    
> [!Note]
> 尽管本文侧重于全局管理员帐户，但您应考虑是否应当以相同方式保护具有访问订阅中数据的广泛权限的其他帐户，例如电子数据展示管理员或安全或合规性管理员帐户。 <br > 可以在不添加任何许可证的情况下创建全局管理员帐户。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>步骤 1. 创建专用的 Microsoft 365 全局管理员帐户，并仅在必要时使用它们

需要全局管理员权限的管理任务（如将角色分配给用户帐户）相对较少。 因此，不要使用分配有全局管理员角色的日常用户帐户，而是执行以下步骤：
  
1. 确定已分配全局管理员角色的用户帐户集。 可以在 Microsoft 365 管理中心或以下 Azure Active (Azure AD) Directory PowerShell for Graph 命令中执行此操作：
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. 使用已分配全局管理员角色的用户帐户登录 Microsoft 365 订阅。
    
3. 最多创建四个专用全局管理员用户帐户。 **使用长于 12 个字符的强密码。** 有关详细信息 [，请参阅"创建](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 强密码"。 将新帐户的密码存储在安全的位置。 
    
4. 将全局管理员角色分配给每个新的专用全局管理员用户帐户。
    
5. 注销 Microsoft 365。
    
6. 使用新的专用全局管理员用户帐户之一登录。
    
7. 对于从步骤 1 中分配了全局管理员角色的每个现有用户帐户：
    
  - 删除全局管理员角色。
    
  - 将管理员角色分配给适合该用户的工作职能和责任的帐户。 有关 Microsoft 365 中各种管理员角色的信息，请参阅关于 [管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。
    
8. 注销 Microsoft 365。
    
结果应为：
  
- 订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。 使用以下 PowerShell 命令验证这一点：
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- 所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。
    
从这一时刻开始，只需使用需要全局管理员权限的任务的专用全局管理员帐户登录。 所有其他 Microsoft 365 管理都必须通过向用户帐户分配其他管理角色完成。
  
> [!NOTE]
> 这确实需要其他步骤才能作为日常用户帐户进行注销，然后使用专用全局管理员帐户登录。 但只需偶尔对全局管理员操作完成此操作。 请注意，在全局管理员帐户泄露后恢复 Microsoft 365 订阅需要执行更多步骤。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>步骤 2. 为专用 Microsoft 365 全局管理员帐户配置多重身份验证

MFA (多重身份验证) 帐户名称和密码之外的其他信息。 Microsoft 365 支持以下其他验证方法：
  
- Microsoft Authenticator 应用

- 电话联络
    
- 通过短信发送的随机生成的验证码
    
- 智能卡（虚拟或物理）
    
- 生物识别设备
    
>[!Note]
>对于必须遵守国家标准和技术协会 (NIST) 标准的组织，限制使用电话呼叫或基于短信的其他验证方法。 单击此处 [了解](https://pages.nist.gov/800-63-FAQ/#q-b01) 详细信息。
>

如果你是使用仅存储在云中的用户帐户的小型企业 (则使用仅云标识模型) 设置 MFA，以使用每个专用全局管理员帐户的电话呼叫或短信验证码将 MFA 配置为配置[MFA。](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)
    
如果你是使用 Microsoft 365 混合标识模型的较大组织，则具有更多验证选项。 如果已针对更强大的辅助身份验证方法设置了安全基础结构，请设置 [MFA，](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) 并针对相应的验证方法配置每个专用全局管理员帐户。
  
如果 Microsoft 365 MFA 所需的更强大的验证方法的安全基础结构未到位且未正常运行，我们强烈建议使用 Microsoft Authenticator 应用、电话呼叫或发送到智能手机的短信验证代码为全局管理员帐户配置专用全局管理员帐户，作为临时安全措施。 如果没有 MFA 提供的其他保护，请不要保留专用全局管理员帐户。
  
有关详细信息，请参阅[Microsoft 365 的 MFA。](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
  
若要使用 MFA 和 PowerShell 连接到 Microsoft 365 服务，请参阅以下文章：

- [适用于 Microsoft 365 用户帐户、组和许可证的 PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>企业组织的其他保护

使用这些附加方法可确保全局管理员帐户以及使用该帐户执行的配置尽可能安全。
  
### <a name="privileged-access-workstation"></a>特权访问工作站

若要确保执行高度特权任务尽可能安全，请使用 PRIVILEGE (的特权) 。 PAW 是仅用于敏感配置任务的专用计算机，例如需要全局管理员帐户的 Microsoft 365 配置。 由于此计算机不每天用于 Internet 浏览或电子邮件，因此可以更好地防范 Internet 攻击和威胁。
  
有关如何设置 PAW 的说明，请参阅 [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 。

若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

无需将全局管理员帐户永久分配给 全局管理员角色，您可以使用 Azure AD Privileged Identity Management (PIM) 按需、实时分配 全局管理员角色（如果需要）。
  
全局管理员帐户从永久管理员转到符合条件的管理员。 该全局管理员角色在有人需要之前处于非活动状态。 然后完成激活过程，将全局管理员角色预先确定的时间添加到全局管理员帐户。 当时间到期时，PIM 将全局管理员角色全局管理员帐户中删除此帐户。
  
使用 PIM 和此过程可显著减少全局管理员帐户易受恶意用户攻击和使用的时间。

可从 Microsoft 365 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。 或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。
  
有关详细信息，请参阅[Azure AD Privileged Identity Management。](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>特权访问管理

租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改租户中的组织邮箱设置。

在此步骤中，你将在租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的数据和配置设置进行的访问提供额外的安全性。要开始在组织中使用特权访问，需要执行三个基本步骤：

- 创建审批者的组
- 启用特权访问
- 创建审批策略

利用特权访问管理，组织可以零长期特权运行，并针对由于此类长期管理访问权限引发的漏洞提供一层防御。 特权访问需要批准，以执行已定义相关审批策略的任何任务。 需要执行审批策略中包含的任务的用户必须请求并被授予访问权限审批。

若要启用特权访问管理，请参阅["配置特权访问管理"。](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

有关详细信息，请参阅 [Privileged 访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>适用于 Microsoft 365 日志记录 (SIEM) 软件的安全信息和事件管理

在服务器上运行的 SIEM 软件对应用程序和网络硬件创建的安全警报和事件进行实时分析。 若要允许 SIEM 服务器在其分析和报告功能中包括 Microsoft 365 安全警报和事件，请将 Azure AD 集成到 SEIM 中。 请参阅 [Azure 日志集成简介](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)。

## <a name="next-step"></a>后续步骤

如果要为 Microsoft 365 订阅设置标识，请参阅：

- [使用仅](cloud-only-identities.md) 云标识时仅云标识
- [如果使用的是混合](prepare-for-directory-synchronization.md) 标识，则准备进行目录同步

  
## <a name="see-also"></a>另请参阅

[Microsoft 365 安全路线图](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
