---
title: Contoso Microsoft 365企业安全管理摘要
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用企业Microsoft 365功能。
ms.openlocfilehash: f4d35ef3c5b862b42bf0a995f25b29c26eedd408
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152738"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Microsoft 365企业安全管理摘要

为了获得批准，Microsoft 365部署企业版，Contoso IT 安全部门进行了周密的安全检查。 他们确定了云的以下安全要求：

- 对员工访问云资源使用最强身份验证方法。
- 确保电脑和移动设备以安全的方式连接和访问应用程序。
- 保护电脑和电子邮件免受恶意软件的攻击。
- 对基于云的数字资产的权限定义谁可以访问哪些内容以及他们可以做什么，并且专为最小特权访问设计
- 敏感和高度管控的数字资产在安全位置进行标记、加密和存储。
- 高度管控的数字资产受到其他加密和权限的保护。
- IT 安全人员可以从中央仪表板监视当前安全状态，并获取有关安全事件的通知，以便快速响应和缓解。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Contoso 安全准备Microsoft 365路径

Contoso 遵循这些步骤来准备其安全性，以部署Microsoft 365企业版：

1. 限制云的管理员帐户

   Contoso 对现有的 Active Directory 域服务 (AD DS) 进行了广泛审查，并设置了一系列专用云管理员帐户和组。

2. 将数据分为三个安全级别

   Contoso 仔细审阅并确定了三个级别，这三个级别用于Microsoft 365功能保护最有价值的数据。

3. 确定数据级别的访问、保留和信息保护策略

   Contoso 根据数据级别确定了限定移动到云的未来 IT 工作负载的详细要求。

为了遵循安全最佳做法Microsoft 365满足企业部署要求，Contoso 安全管理员及其 IT 部门部署了许多安全特性和功能，如以下各节所述。

## <a name="identity-and-access-management"></a>标识和访问管理 

- 使用 MFA 和 PIM 的专用全局管理员帐户

  Contoso 创建了三个使用强密码的专用全局管理员帐户，而不是将全局管理员角色分配给日常用户帐户。 帐户受 Azure AD 多重身份验证 (MFA) 和 Azure Active Directory (Azure AD) Privileged Identity Management (PIM) 。 *PIM 仅在 Microsoft 365 E5 中提供。*

  使用 Azure **AD DC 管理员或****全局** 管理员帐户登录仅适用于特定管理任务。 密码仅对指定员工已知，并且只能在 Azure AD PIM 中配置的时段内使用。

  Contoso 安全管理员为适合 IT 工作者的工作职能的帐户分配了较低管理员角色。

  有关详细信息，请参阅[关于 Microsoft 365 管理员角色](/office365/admin/add-users/about-admin-roles)。

- 用于所有用户帐户的 MFA

  MFA 为登录过程添加了一层额外的保护。 它要求用户在正确输入密码后确认智能手机上的电话呼叫、短信或应用通知。 通过 MFA，Azure AD 用户帐户受到保护，防止未经授权的登录，即使帐户密码受到威胁。

   - 若要防止泄露订阅Microsoft 365，Contoso 需要所有 **Azure AD DC** 管理员或 **全局管理员帐户** 的 MFA。
   - 为防止钓鱼攻击（攻击者会泄露组织中受信任的个人的凭据并发送恶意电子邮件），Contoso 对所有用户帐户（包括经理和行政人员）都启用了 MFA。

- 使用条件访问策略更安全地访问设备和应用程序

  Contoso 将[条件访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)用于标识、设备、Exchange Online 和 SharePoint。标识条件访问策略包括要求针对高风险用户进行密码更改，以及阻止客户端使用不支持新式验证的应用。设备条件策略包括定义批准的应用和要求使用合规的电脑和移动设备。Exchange Online 条件访问策略包括阻止 ActiveSync 客户端和设置 Office 365 邮件加密。SharePoint 条件访问策略包括对敏感和高度管控的网站提供额外的保护。

- Windows Hello 企业版

  Contoso 部署了[Windows Hello for Business，](/windows/security/identity-protection/hello-for-business/hello-identity-verification)最终无需在运行 Windows 10 企业版 的 PC 和移动设备上使用强双因素身份验证。

- Windows Defender Credential Guard

  为了使用管理权限阻止在操作系统中运行的目标攻击和恶意软件，Contoso 通过 AD DS Windows Defender启用[Credential Guard。](/windows/security/identity-protection/credential-guard/credential-guard)

## <a name="threat-protection"></a>威胁防护

- 使用 Windows Defender 防病毒防止恶意软件的攻击

  Contoso 使用 [Windows Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)对运行 Windows 10 企业版的电脑和设备进行恶意软件保护和反恶意软件管理。

- 使用 Microsoft Defender for Office 365 保护电子邮件流和邮箱审核Office 365 

  Contoso 使用 Exchange Online Protection 和[Defender for Office 365，](/office365/securitycompliance/office-365-atp)以抵御通过电子邮件传输的未知恶意软件、病毒和恶意 URL。

  Contoso 还启用了邮箱审核日志记录，以标识登录到用户邮箱、发送邮件以及执行由邮箱所有者、委派用户或管理员执行的其他活动的用户。

- 使用 Office 365 威胁调查和响应进行威胁监控和防护

  Contoso 使用[Office 365](/office365/securitycompliance/office-365-ti)调查和响应功能，通过轻松识别和处理攻击来保护用户，并防止未来攻击。

- 使用 Advanced Threat Analytics 防止复杂攻击

  Contoso 使用 [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) 保护自己免受高级目标攻击。ATA 自动分析、学习和标识正常和异常实体（用户、设备和资源）行为。

## <a name="information-protection"></a>信息保护

- 使用 Azure 信息保护标签来保护敏感和高度管控的数字资产

  Contoso 确定了三个级别的数据保护，Microsoft 365[用户](../compliance/sensitivity-labels.md)应用于数字资产的敏感度标签。 对于商业秘密和其他知识产权，Contoso 对高度管控数据使用敏感度子标签。 此过程对内容进行加密，并限制对特定用户帐户和组的访问。

- 使用数据丢失防护功能阻止 Intranet 数据泄露

  Contoso[为](../compliance/dlp-learn-about-dlp.md)Exchange Online、SharePoint 和 OneDrive for Business 配置了数据丢失防护策略，以防止用户意外或有意共享敏感数据。

- 使用 Windows 信息保护防止设备数据泄露

  Contoso 使用 Windows 信息保护[ (WIP) ](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)防止数据通过基于 Internet 的应用和服务、企业应用以及企业拥有的设备以及员工带到工作的个人设备上的数据泄露。

- 使用 Microsoft Cloud App Security 进行云监视

  Contoso 使用 [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) 来映射其云环境、监视其使用情况，并检测安全事件和事件。 *Microsoft Cloud App Security 仅在 Microsoft 365 E5 中提供。*

- 使用 Microsoft Intune 的设备管理

  Contoso 使用 [Microsoft Intune](/intune/introduction-intune) 来注册、管理和配置对移动设备及其上运行的应用的访问权限。基于设备的条件访问策略还要求使用获得批准的应用和合规的电脑及移动设备。

## <a name="security-management"></a>安全管理

- 使用 Azure Defender 的 IT 中心安全仪表板

  Contoso 使用 [Azure Defender](https://azure.microsoft.com/services/security-center/) 提供统一的安全和威胁防护视图，跨其工作负载管理安全策略，并响应网络攻击。

- Windows Defender 安全中心适用于用户的安全中心仪表板

  Contoso 将[](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)Windows 安全中心 应用部署到运行 Windows 10 企业版 电脑和设备，以便用户可以一目了然地查看其安全状态并采取措施。
