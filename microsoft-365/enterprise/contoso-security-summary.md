---
title: Contoso Corporation 的 Microsoft 365 企业版安全性摘要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用 Microsoft 365 企业版的安全功能。
ms.openlocfilehash: b49312b94aef35afc5febeae0fd4dc71b7c642af
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672678"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation 的 Microsoft 365 企业版安全性摘要

若要获取 IT 安全部门签核的 Microsoft 365 企业版部署，需要执行彻底的安全审阅。以下是 Contoso 针对云的安全要求：

- 对访问云资源的员工使用最强身份验证方法
- 确保电脑和移动设备以安全的方式连接和访问应用程序
- 保护电脑和电子邮件免受恶意软件的攻击
- 对基于云的数字资产的权限定义哪些用户可访问哪些内容及他们可执行哪些操作，并被设计为最小特权访问权限
- 对敏感和高度管控的数字资产进行标记和加密，并将其存储在安全位置
- 通过其他加密和权限对高度管控的数字资产进行保护
- IT 安全人员可从中央仪表板监控当前安全状态，并收到有关安全事件的通知，以做出快速响应和采取缓解措施。

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contoso 实现 Microsoft 365 安全就绪情况的方式

Contoso 使用以下步骤为其 Microsoft 365 企业版部署的安全性做准备：

1. 限制云的管理员帐户

   Contoso 对现有的 Active Directory 域服务 (AD DS) 管理员帐户进行了广泛审阅，并设置了一系列的专用云管理员帐户和组。

2. 按三个级别执行数据分类分析

   Contoso 进行了仔细的审阅并确定了三个用来确定 Microsoft 365 企业版功能的级别，以保护 Contoso 最有价值的数据。

3. 确定数据级别的访问策略、保留策略和信息保护策略

   基于数据级别，Contoso 已确定将用于限定转移到云的未来 IT 工作负载的详细要求。

根据安全最佳做法和 Microsoft 365 企业版部署要求，Contoso 的安全管理员和 IT 部门已部署许多安全特性和功能，如以下部分中所述。

## <a name="identity--access-management"></a>标识和访问管理 

- 使用 MFA 和 PIM 的专用全局管理员帐户

  Contoso 创建三种专用全局管理员帐户，它们使用强密码，并使用 Azure 多重身份验证 (MFA) 和 Azure Active Directory (Azure AD) Privileged Identity Management (PIM) 对其进行保护，而非向日常用户帐户分配全局管理员角色。 PIM 仅在 Microsoft 365 企业版 E5 中提供。

  仅针对特定管理任务执行使用全局管理员帐户登录，只有指定人员才知道密码，且只能在使用 Azure AD PIM 配置的时间范围内使用。 

  对于适合该 IT 人员的作业功能和职责的帐户，Contoso 的安全管理员向其分配了更低的管理员角色。

  有关详细信息，请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

- 用于所有用户帐户的 MFA

  MFA 通过要求用户在正确输入密码后在其智能手机上确认电话呼叫、短信或应用通知为登录过程添加了额外的保护。使用 MFA，即使帐户密码被泄露，也可针对未授权登录保护 Azure AD 用户帐户。

   - 若要防止 Microsoft 365 订阅泄漏，Contoso 要求对所有全局管理员帐户使用 MFA。
   - 为防止钓鱼攻击（攻击者会泄露组织中受信任的个人的凭据并发送恶意电子邮件），Contoso 对所有用户帐户（包括经理和行政人员）都启用了 MFA。 

- 使用条件访问策略更安全地访问设备和应用程序

  Contoso 将[条件访问策略](microsoft-365-policies-configurations.md)用于标识、设备、Exchange Online 和 SharePoint。标识条件访问策略包括对高风险用户要求进行密码更改以及阻止客户端使用不支持新式身份验证的应用。设备条件策略包括定义批准的应用和要求使用合规的电脑和移动设备。Exchange Online 条件访问策略包括阻止 ActiveSync 客户端和设置 Office 365 邮件加密。SharePoint 条件访问策略包括对敏感和高度管控的网站提供额外的保护。

- Windows Hello 企业版

  Contoso 已部署并要求 [Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)通过对在运行 Windows 10 企业版的电脑和移动设备使用强双因素身份验证来消除输入密码的需要。

- Windows Defender Credential Guard

  为了使用管理权限阻止在操作系统中运行的目标攻击和恶意软件，Contoso 通过 AD DS 组策略启用了 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)。

## <a name="threat-protection"></a>威胁防护

- 使用 Windows Defender 防病毒防止恶意软件的攻击

  Contoso 使用 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)对运行 Windows 10 企业版的电脑和设备进行恶意软件保护和反恶意软件管理。

- 使用 Office 365 高级威胁防护保护电子邮件流和邮箱审核日志记录 

  Contoso 使用 Exchange Online Protection 和 [Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 来抵御通过电子邮件传输的未知恶意软件、病毒和恶意 URL。 

  Contoso 还启用了邮箱审核日志记录，以确定登录用户邮箱、发送邮件的用户，以及由邮箱所有者、受委派用户或管理员执行的其他活动。

- 使用 Office 365 威胁调查和响应进行威胁监控和防护

  Contoso 使用 [Office 365 威胁调查和响应](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)保护其 Office 365 用户，使其能够轻松地标识和解决攻击，并防止进一步攻击。

- 使用 Advanced Threat Analytics 防止复杂攻击

  Contoso 使用 [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) 保护自己免受高级目标攻击。ATA 自动分析、学习和标识正常和异常实体（用户、设备和资源）行为。 

## <a name="information-protection"></a>信息保护

- 使用 Azure 信息保护标签来保护敏感和高度管控的数字资产

  Contoso 确定数据保护的三个级别并部署用户应用于数字资产的 [Office 365 敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)。对于其商业秘密和其他知识产权，Contoso 对加密内容的高度管控数据使用敏感度子标签，并限制对特定用户帐户和组组的访问。

- 使用 Office 365 数据丢失防护阻止 intranet 数据泄露

  Contoso 为 Exchange Online、SharePoint 和 OneDrive for Business 配置了[数据丢失防护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)，以阻止用户无意或有意共享敏感数据。

- 使用 Windows 信息保护防止设备数据泄露

  Contoso 使用 [Windows 信息保护 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) 防止数据通过基于 Internet 的应用和服务、企业所有的设备上的企业应用和数据、以及员工工作时所使用的个人设备泄露。

- 使用 Microsoft Cloud App Security 进行云监视

  Contoso 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 来映射其云环境、监视其使用情况，并检测安全事件和事件。 Microsoft Cloud App Security 仅在 Microsoft 365 企业版 E5 中提供。

- 使用 Microsoft Intune 的设备管理

  Contoso 使用 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) 来注册、管理和配置对移动设备及其上运行的应用的访问权限。基于设备的条件访问策略还要求使用获得批准的应用和合规的电脑及移动设备。

## <a name="security-management"></a>安全管理

- Azure 安全中心适用于 IT 人员的安全中心仪表板

  Contoso 使用 [Azure 安全中心](https://azure.microsoft.com/services/security-center/)来获取统一的安全和威胁防护视图，以跨其工作负载管理安全策略，并响应网络攻击。

- Windows Defender 安全中心适用于用户的安全中心仪表板

  Contoso 已将 [Windows 安全应用](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)部署到运行 Windows 10 企业版的电脑和设备，以便用户能够对其安全状态一目了然并采取操作。


## <a name="next-step"></a>后续步骤

[了解](contoso-sharepoint-online-site-for-highly-confidential-assets.md) Contoso 如何对高度受管制数据创建 SharePoint 网站，以推动研究团队之间的协作。

