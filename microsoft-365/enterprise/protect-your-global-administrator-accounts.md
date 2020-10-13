---
title: 保护你的 Microsoft 365 全局管理员帐户
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
description: 本文提供了有关保护对 Microsoft 365 订阅的全局管理员访问权限的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15c497e02b139ea6af4aabba9f3e9ab65a1205be
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445403"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>保护你的 Microsoft 365 全局管理员帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365 订阅的安全违规（包括信息收集和网络钓鱼攻击）通常通过威胁 Microsoft 365 全局管理员帐户的凭据来实现。 云中的安全性是您和 Microsoft 之间的合作关系：
  
- Microsoft 云服务是基于信任和安全性的基础建立的。 Microsoft 为您提供安全控件和功能，以帮助保护您的数据和应用程序。
    
- 你拥有自己的数据和标识，并负责保护它们、本地资源的安全性以及你控制的云组件的安全性。
    
Microsoft 提供的功能可帮助保护你的组织，但只有在你使用它们时才有效。 如果不使用它们，可能会受到攻击。 为了保护您的全局管理员帐户，Microsoft 在这里为您提供详细说明，以帮助你执行以下操作：
  
1. 创建专用的 Microsoft 365 全局管理员帐户，并仅在必要时使用它们。
    
2. 为专用 Microsoft 365 全局管理员帐户配置多重身份验证，并使用最强的辅助身份验证形式。
    
> [!Note]
> 虽然本文重点介绍了全局管理员帐户，但您应考虑是否需要以相同的方式保护订阅中的数据（如电子数据展示管理员或安全或合规性管理员帐户）的其他帐户。 <br > 全局管理员帐户可在不添加任何许可证的情况下创建。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>第 1 步： 创建专用的 Microsoft 365 全局管理员帐户，并仅在必要时使用

与需要全局管理员权限的用户帐户分配角色相比，管理任务相对较少。 因此，请执行以下步骤，而不是使用已分配有全局管理员角色的日常用户帐户。
  
1. 确定已分配全局管理员角色的用户帐户集。 你可以在 Microsoft 365 管理中心或以下 Azure Active (Azure AD) Directory PowerShell for Graph 命令中执行此操作：
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. 使用已分配有全局管理员角色的用户帐户登录到 Microsoft 365 订阅。
    
3. 最多可创建四个专用全局管理员用户帐户。 **使用强密码，长度至少为12个字符。** 有关详细信息，请参阅 [创建强密码](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 。 将新帐户的密码存储在安全的位置。 
    
4. 将全局管理员角色分配给每个新的专用全局管理员用户帐户。
    
5. 注销 Microsoft 365。
    
6. 使用新的专用全局管理员用户帐户之一进行登录。
    
7. 对于从第1步中为其分配了全局管理员角色的每个现有用户帐户：
    
  - 删除全局管理员角色。
    
  - 将管理员角色分配给适合该用户的工作职能和责任的帐户。 有关 Microsoft 365 中的各种管理员角色的详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。
    
8. 注销 Microsoft 365。
    
结果应为：
  
- 订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。 使用以下 PowerShell 命令对此进行验证：
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- 所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。
    
从现在起，您只需使用专用全局管理员帐户，即可为需要全局管理员权限的任务进行登录。 所有其他 Microsoft 365 管理都必须通过向用户帐户分配其他管理角色来完成。
  
> [!NOTE]
> 这需要额外的步骤才能注销为您的日常用户帐户，并使用专用全局管理员帐户登录。 但这只需要偶尔执行全局管理员操作。 请考虑在全局管理员帐户泄露之后恢复 Microsoft 365 订阅需要执行更多步骤。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>第 2 步： 为专用 Microsoft 365 全局管理员帐户配置多重身份验证

多重身份验证 (MFA) 需要除帐户名称和密码之外的其他信息。 Microsoft 365 支持以下其他验证方法：
  
- Microsoft Authenticator 应用

- 电话联络
    
- 通过短信发送的随机生成的验证代码
    
- 智能卡（虚拟或物理）
    
- 生物识别设备
    
>[!Note]
>对于必须遵守美国国家标准和技术协会 (NIST) 标准的组织，限制使用电话呼叫或基于短邮件的其他验证方法。 有关详细信息，请单击 [此处](https://pages.nist.gov/800-63-FAQ/#q-b01) 。
>

如果你是一位仅使用在云中存储的用户帐户的小型企业 (仅限云身份模型) ，请 [将 mfa 设置](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 为使用电话呼叫或为每个专用全局管理员帐户发送到智能手机的短信验证代码配置 mfa。
    
如果您是更大的组织，并且使用的是 Microsoft 365 混合标识模型，则可以使用更多的验证选项。 如果你已为更强的辅助身份验证方法准备好安全基础结构，请 [设置 MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) 并为每个专用全局管理员帐户配置相应的验证方法。
  
如果所需的强验证方法的安全基础结构未就绪且无法在 Microsoft 365 MFA 中正常运行，强烈建议您使用 Microsoft 身份验证应用、电话呼叫或发送到智能手机的电子邮件验证代码，将专用全局管理员帐户配置为使用 MFA 作为临时安全措施。 请勿离开专用全局管理员帐户，而不会通过 MFA 提供额外的保护。
  
有关详细信息，请参阅适用 [于 Microsoft 365 的 MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)。
  
若要使用 MFA 和 PowerShell 连接到 Microsoft 365 服务，请参阅以下文章：

- [适用于 Microsoft 365 的 PowerShell （针对用户帐户、组和许可证）](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>针对企业组织的其他保护

使用这些其他方法可确保全局管理员帐户以及使用它执行的配置尽可能安全。
  
### <a name="privileged-access-workstation"></a>特权访问工作站

若要确保高特权任务的执行尽可能安全，请使用特权访问工作站 (PAW) 。 PAW 是一台专用计算机，仅用于敏感配置任务，如需要全局管理员帐户的 Microsoft 365 配置。 由于此计算机不会每天用于 Internet 浏览或电子邮件，因此它会更好地受到 Internet 攻击和威胁的保护。
  
有关如何设置 PAW 的说明，请参阅 [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) 。

若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

您可以使用 Azure AD 特权标识管理 (PIM) 在需要时实时分配全局管理员角色，而不是将全局管理员帐户永久分配给全局管理员角色，而不是将全局管理员帐户分配给全局管理员角色。
  
全局管理员帐户从永久管理员转到符合条件的管理员。 全局管理员角色处于非活动状态，直到有人需要它。 然后，完成激活过程，将全局管理员角色添加到全局管理员帐户中的预先确定的一段时间。 当时间过期时，PIM 将从全局管理员帐户中删除全局管理员角色。
  
使用 PIM 和此过程可大大减少全局管理员帐户易受恶意用户攻击和使用的时间量。

可从 Microsoft 365 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。 或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。
  
有关详细信息，请参阅 [AZURE AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。
  

### <a name="privileged-access-management"></a>特权访问管理

租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改租户中的组织邮箱设置。

在此步骤中，你将在租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的数据和配置设置进行的访问提供额外的安全性。要开始在组织中使用特权访问，需要执行三个基本步骤：

- 创建审批者的组
- 启用特权访问
- 创建审批策略

"特权访问管理" 使贵组织能够以零为依据的权限运行，并针对因此类管理访问而引发的漏洞提供防御措施层。 特权访问需要审批以执行任何定义了关联的审批策略的任务。 需要执行审批策略中包括的任务的用户必须请求并授予访问审批权限。

若要启用特权访问管理，请参阅 [Configure 特许 access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)。

有关详细信息，请参阅 [特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>适用于 Microsoft 365 日志记录的安全信息和事件管理 (SIEM) 软件

在服务器上运行的 SIEM 软件对应用程序和网络硬件创建的安全警报和事件执行实时分析。 若要允许您的 SIEM 服务器在其分析和报告功能中包含 Microsoft 365 安全警报和事件，请将 Azure AD 集成到您的 SEIM 中。 请参阅 [Azure 日志集成简介](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)。

## <a name="next-step"></a>后续步骤

如果你正在为 Microsoft 365 订阅设置标识，请参阅：

- [仅限云的](cloud-only-identities.md) 标识（如果使用仅限云标识）
- 如果使用的是混合标识，则[准备进行目录同步](prepare-for-directory-synchronization.md)

  
## <a name="see-also"></a>另请参阅

[Microsoft 365 安全路线图](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
