---
title: Microsoft 365 for Contoso Corporation 的企业安全摘要
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用适用于企业的 Microsoft 365 的安全功能。
ms.openlocfilehash: 635336b70318acdd4ed013a2705691d160926e84
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649697"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Microsoft 365 for Contoso Corporation 的企业安全摘要

为了获得部署 Microsoft 365 for enterprise 的批准，Contoso IT 安全部门进行了全面的安全审查。 他们发现云的以下安全要求：

- 使用最强大的身份验证方法对云资源的员工访问权限。
- 确保电脑和移动设备以安全的方式连接和访问应用程序。
- 保护电脑和电子邮件免受恶意软件的攻击。
- 基于云的数字资产上的权限定义谁可以访问哪些内容以及可以执行哪些操作，并专为最小特权访问而设计
- 敏感和高度管控的数字资产在安全位置进行标记、加密和存储。
- 高度管控的数字资产受其他加密和权限保护。
- IT 安全人员可以监视中央仪表板中的当前安全状况，并通知安全事件以快速响应和缓解。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 安全就绪的 Contoso 路径

Contoso 按照这些步骤为 Microsoft 365 for 企业版的部署准备好其安全性：

1. 限制云的管理员帐户

   Contoso 对其现有的 Active Directory 域服务进行了广泛审阅 (AD DS) 管理员帐户，并设置专用的云管理员帐户和组的系列。

2. 将数据分类为三个安全级别

   Contoso 进行了仔细检查并确定了三个级别，它们用于标识适用于企业功能的 Microsoft 365，以保护最有价值的数据。

3. 确定数据级别的访问、保留和信息保护策略

   根据数据级别，Contoso 确定了向云迁移未来的 IT 工作负载的详细要求。

为了遵循安全性最佳实践和 Microsoft 365 以实现企业级部署要求，Contoso security administrators and IT 部门部署了许多安全特性和功能，如以下各节中所述。

## <a name="identity-and-access-management"></a>标识和访问管理 

- 使用 MFA 和 PIM 的专用全局管理员帐户

  Contoso 创建了三个具有强密码的专用全局管理员帐户，而不是将全局管理员角色分配给日常用户帐户。 帐户受 Azure 多重身份验证 (MFA) 和 Azure Active Directory (Azure AD) 特权身份管理 (PIM) 。 *PIM 仅在 Microsoft 365 E5 中提供。*

  仅对特定管理任务执行使用全局管理员帐户登录。 密码仅对指定的员工已知，并且只能在 Azure AD PIM 中配置的时段内使用。

  Contoso 安全管理员将较低的管理员角色分配给适合该 IT 工作人员的工作职能的帐户。

  有关详细信息，请参阅[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

- 用于所有用户帐户的 MFA

  MFA 向登录过程添加了一个额外的保护层。 它要求用户在正确输入密码后，在其智能手机上确认电话呼叫、短信或应用程序通知。 通过 MFA，Azure AD 用户帐户受到保护以防未经授权登录，即使帐户密码受到威胁也是如此。

   - 为了防止 Microsoft 365 订阅受到危害，Contoso 要求对所有全局管理员帐户进行 MFA。
   - 为防止钓鱼攻击（攻击者会泄露组织中受信任的个人的凭据并发送恶意电子邮件），Contoso 对所有用户帐户（包括经理和行政人员）都启用了 MFA。

- 使用条件访问策略更安全地访问设备和应用程序

  Contoso 将[条件访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)用于标识、设备、Exchange Online 和 SharePoint。标识条件访问策略包括要求针对高风险用户进行密码更改，以及阻止客户端使用不支持新式验证的应用。设备条件策略包括定义批准的应用和要求使用合规的电脑和移动设备。Exchange Online 条件访问策略包括阻止 ActiveSync 客户端和设置 Office 365 邮件加密。SharePoint 条件访问策略包括对敏感和高度管控的网站提供额外的保护。

- Windows Hello 企业版

  Contoso 部署 [了 Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) ，以最终消除对运行 Windows 10 企业版的 pc 和移动设备上的强双重身份验证的需要密码。

- Windows Defender Credential Guard

  若要阻止在具有管理权限的操作系统中运行的目标攻击和恶意软件，Contoso 通过 AD DS 组策略启用了 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) 。

## <a name="threat-protection"></a>威胁防护

- 使用 Windows Defender 防病毒防止恶意软件的攻击

  Contoso 使用 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)对运行 Windows 10 企业版的电脑和设备进行恶意软件保护和反恶意软件管理。

- 使用 Office 365 高级威胁防护保护电子邮件流和邮箱审核日志记录 

  Contoso 使用 Exchange Online Protection 和 [Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 来抵御通过电子邮件传输的未知恶意软件、病毒和恶意 URL。

  Contoso 还启用了邮箱审核日志记录，以标识登录用户邮箱、发送邮件的用户以及邮箱所有者、委派用户或管理员执行的其他活动。

- 使用 Office 365 威胁调查和响应进行威胁监控和防护

  Contoso 使用 [Office 365 威胁调查和响应](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) 来通过轻松识别和解决攻击来保护用户，并防止未来的攻击。

- 使用 Advanced Threat Analytics 防止复杂攻击

  Contoso 使用 [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) 保护自己免受高级目标攻击。ATA 自动分析、学习和标识正常和异常实体（用户、设备和资源）行为。

## <a name="information-protection"></a>信息保护

- 使用 Azure 信息保护标签来保护敏感和高度管控的数字资产

  Contoso 确定了三个级别的数据保护，并部署了用户应用于数字资产的 [Microsoft 365 敏感标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 。 对于其商业机密和其他知识产权，Contoso 对高度管控数据使用敏感度子标签。 此过程会对内容进行加密，并限制对特定用户帐户和组的访问。

- 使用数据丢失防护功能阻止 Intranet 数据泄露

  Contoso 为 Exchange Online、SharePoint 和 OneDrive for business 配置了 [数据丢失防护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 策略，以防止用户意外或有意地共享敏感数据。

- 使用 Windows 信息保护防止设备数据泄露

  Contoso 使用 [Windows 信息保护 (WIP) ](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) 通过基于 internet 的应用程序和服务以及企业应用程序和企业应用程序中的数据泄露数据，并且员工可以使用这些设备和个人设备上的数据。

- 使用 Microsoft Cloud App Security 进行云监视

  Contoso 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 来映射其云环境、监视其使用情况，并检测安全事件和事件。 *Microsoft Cloud App Security 仅在 Microsoft 365 E5 中提供。*

- 使用 Microsoft Intune 的设备管理

  Contoso 使用 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) 来注册、管理和配置对移动设备及其上运行的应用的访问权限。基于设备的条件访问策略还要求使用获得批准的应用和合规的电脑及移动设备。

## <a name="security-management"></a>安全管理

- Azure 安全中心适用于 IT 人员的安全中心仪表板

  Contoso 使用 [Azure 安全中心](https://azure.microsoft.com/services/security-center/) 来提供安全和威胁防护的统一视图，以跨工作负载管理安全策略并响应 cyberattacks。

- Windows Defender 安全中心适用于用户的安全中心仪表板

  Contoso 将 [Windows 安全应用程序](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 部署到其电脑和运行 Windows 10 企业版的设备，以便用户能够一目了然地查看其安全状态并采取行动。
