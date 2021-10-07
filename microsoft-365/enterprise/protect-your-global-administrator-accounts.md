---
title: 保护你的Microsoft 365全局管理员帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 本文提供有关保护全局管理员对订阅Microsoft 365的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9693a8321643539e21ff10f3c624a0558916eb29
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198345"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>保护你的Microsoft 365全局管理员帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365订阅的安全泄露（包括信息收集攻击和网络钓鱼攻击）通常是通过损害全局管理员帐户的Microsoft 365来完成。 云中的安全是你与 Microsoft 之间的合作关系：
  
- Microsoft 云服务以信任和安全为基础。 Microsoft 提供有助于保护数据和应用程序的安全控件和功能。
    
- 你的数据和身份为个人所有，并且你负责对这些数据和身份、本地资源安全性和所控制的云组件安全性进行保护。
    
Microsoft 提供了可帮助保护组织的功能，但这些功能仅在你使用它们时有效。 如果不使用它们，你很容易受到攻击。 为了保护全局管理员帐户，Microsoft 可在此处帮助你提供详细说明，以：
  
1. 创建专用Microsoft 365全局管理员帐户，并在必要时使用它们。
    
2. 为专用全局管理员帐户Microsoft 365多重身份验证，并使用最强形式的辅助身份验证。
    
> [!Note]
> 尽管本文侧重于全局管理员帐户，但您应考虑是否应该以相同方式保护具有访问订阅中数据的广泛权限的其他帐户，例如电子数据展示管理员帐户或安全或合规性管理员帐户。 <br > 可以在不添加任何许可证的情况下创建全局管理员帐户。
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>步骤 1. 创建专用Microsoft 365全局管理员帐户，并在必要时使用它们

只有相对较少的管理任务（如向用户帐户分配角色）需要全局管理员权限。 因此，不要使用已分配有全局管理员角色的日常用户帐户，而是执行以下步骤：
  
1. 确定已分配全局管理员角色的用户帐户集。 可以在以下 Azure Active Microsoft 365 管理中心 Azure AD (Directory PowerShell for) 命令中Graph此操作：
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. 使用已Microsoft 365全局管理员角色的用户帐户登录你的订阅。
    
3. 最多创建四个专用全局管理员用户帐户。 **使用长于 12 个字符的强密码。** 有关详细信息 [，请参阅创建](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 强密码。 将新帐户的密码存储在安全的位置。 
    
4. 将全局管理员角色分配给每个新的专用全局管理员用户帐户。
    
5. 注销Microsoft 365。
    
6. 使用新的专用全局管理员用户帐户之一登录。
    
7. 对于在步骤 1 中分配了全局管理员角色的每个现有用户帐户：
    
  - 删除全局管理员角色。
    
  - 将管理员角色分配给适合该用户的工作职能和责任的帐户。 有关管理员角色中各种管理员角色Microsoft 365，请参阅关于[管理员角色](/office365/admin/add-users/about-admin-roles)。
    
8. 注销Microsoft 365。
    
结果应为：
  
- 订阅中唯一具备全局管理员角色的用户帐户是一组新的专用全局管理员帐户。 通过以下 PowerShell 命令验证这一点：
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- 所有管理订阅的其他日常用户帐户分配有与其工作职责相关联的管理员角色。
    
从现在起，您仅对需要全局管理员权限的任务使用专用全局管理员帐户登录。 所有其他Microsoft 365管理必须通过向用户帐户分配其他管理角色完成。
  
> [!NOTE]
> 这确实需要其他步骤才能作为日常用户帐户进行注销，然后使用专用全局管理员帐户登录。 但是，只需偶尔对全局管理员操作执行此操作。 请注意，在全局管理员帐户Microsoft 365后恢复你的订阅需要执行很多步骤。
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>步骤 2. 为专用全局管理员帐户Microsoft 365多重身份验证

MFA (多重) 需要帐户名称和密码之外的其他信息。 Microsoft 365支持以下其他验证方法：
  
- Microsoft Authenticator 应用

- 电话联络
    
- 通过短信发送的随机生成的验证码
    
- 智能卡（虚拟或物理）
    
- 生物识别设备
    
>[!Note]
>对于必须遵守美国国家标准和技术协会 (NIST) 标准的组织，限制使用电话呼叫或基于短信的其他验证方法。 单击此处 [了解](https://pages.nist.gov/800-63-FAQ/#q-b01) 详细信息。
>

如果你是使用仅存储在云中的用户帐户的小型企业 (仅云标识模型) ，请设置 MFA 以使用每个专用全局管理员帐户向智能手机发送的电话呼叫或短信验证代码配置[MFA。](/office365/admin/security-and-compliance/set-up-multi-factor-authentication)
    
如果你是使用混合标识模型Microsoft 365大型组织，则具有更多验证选项。 如果已设置安全基础结构，以使用更强大的辅助身份验证方法，请设置 [MFA，](../admin/security-and-compliance/set-up-multi-factor-authentication.md) 并为每个专用全局管理员帐户配置适当的验证方法。
  
如果所需的更强的验证方法的安全基础结构未就位且无法用于 Microsoft 365 MFA，我们强烈建议你使用 Microsoft Authenticator 应用、电话呼叫或作为临时安全性发送到智能手机的短信验证代码，使用 MFA 配置专用全局管理员帐户measure。 请不要离开专用全局管理员帐户，而不使用 MFA 提供的其他保护。
  
有关详细信息，请参阅[MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)。
  
若要通过 MFA Microsoft 365 PowerShell 连接到服务，请参阅以下文章：

- [用于Microsoft 365组和许可证的 PowerShell](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>企业组织的其他保护

使用这些附加方法可确保全局管理员帐户以及使用该帐户执行的配置尽可能安全。
  
### <a name="privileged-access-workstation"></a>特权访问工作站

若要确保执行高特权任务尽可能安全，请使用 PRIVILEGE 访问工作站 (PAW) 。 PAW 是仅用于敏感配置任务的专用计算机，例如Microsoft 365全局管理员帐户的专用配置。 由于此计算机不每天用于 Internet 浏览或电子邮件，因此可以更好地防范 Internet 攻击和威胁。
  
有关如何设置 PAW 的说明，请参阅 [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) 。

若要为 Azure AD 租户和管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

无需将全局管理员帐户永久分配给 全局管理员角色，可以使用 Azure AD Privileged Identity Management (PIM) 按需、实时分配 全局管理员角色（如果需要）。
  
全局管理员帐户从永久管理员转到符合条件的管理员。 在全局管理员角色用户需要之前，该邮箱处于非活动状态。 然后完成激活过程，将全局管理员角色预先确定的时间添加到全局管理员帐户。 当时间到期时，PIM 会从全局管理员角色管理员帐户中删除该密码。
  
使用 PIM 和此过程可显著减少全局管理员帐户易受恶意用户攻击和使用的时间。

可从 Microsoft 365 E5 包含的 Azure Active Directory Premium P2 中获取 PIM。 或者，可以为管理员帐户单独购买 Azure Active Directory Premium P2 许可证。
  
有关详细信息，请参阅[Azure AD Privileged Identity Management。](/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>特权访问管理

租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改租户中的组织邮箱设置。

在此步骤中，你将在租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的数据和配置设置进行的访问提供额外的安全性。要开始在组织中使用特权访问，需要执行三个基本步骤：

- 创建审批者的组
- 启用特权访问
- 创建审批策略

利用特权访问管理，组织可以零长期特权运行，并提供一层防御因此类长期管理访问权限引发的漏洞。 特权访问需要经过审批，以执行已定义关联审批策略的任何任务。 需要执行审批策略中包含的任务的用户必须请求并被授予访问权限审批。

若要启用特权访问管理，请参阅配置 [特权访问管理](/office365/securitycompliance/privileged-access-management-configuration)。

有关详细信息，请参阅[Privileged access management。](/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>SIEM 安全信息和事件 (SIEM) 软件进行Microsoft 365日志记录

在服务器上运行的 SIEM 软件对由应用程序和网络硬件创建的安全警报和事件执行实时分析。 若要允许 SIEM 服务器在其分析和Microsoft 365功能中包括安全警报和事件，请将 Azure AD 集成到 SEIM 中。 请参阅[Azure 日志集成](/azure/security/security-azure-log-integration-overview)简介。

## <a name="next-step"></a>后续步骤

如果要为订阅设置标识Microsoft 365，请参阅：

- [使用仅](cloud-only-identities.md) 云标识时仅云标识
- [使用混合标识时](prepare-for-directory-synchronization.md) 准备目录同步

  
## <a name="see-also"></a>另请参阅

[Microsoft 365安全路线图](/office365/securitycompliance/security-roadmap)