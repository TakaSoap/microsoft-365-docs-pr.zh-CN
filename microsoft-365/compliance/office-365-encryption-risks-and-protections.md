---
title: 加密风险和保护
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: 本文将介绍保护风险Office 365加密技术。
ms.openlocfilehash: fc1792c11bfbe0451eb2a835b3b02504ab05546f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190661"
---
# <a name="encryption-risks-and-protections"></a>加密风险和保护

Microsoft 遵循一个控制和合规性框架，重点关注针对 Microsoft 365 和客户数据的风险。 Microsoft 实施了一大组基于技术和流程的方法， (称为控制措施) 来缓解这些风险。 通过控制措施识别、评估和缓解风险是一个持续的过程。 

在云服务的各个层（如设施、网络、服务器、应用程序、 (（如 Microsoft 管理员）和数据) 控件的实现构成了深度防御策略。 此策略的关键是在不同层实施许多不同的控件，以防范相同或类似的风险方案。 这种多层方法可提供故障安全保护，以防由于某种原因导致控件失败。

下面列出了一些风险方案和当前可用的可缓解这些风险方案的加密技术。 在许多情况下，这些场景也会通过在 Office 365 中实现的其他控件Office 365。

| 加密技术 | 服务 | 密钥管理 | 风险方案 | 值 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online 和 Skype for Business | Microsoft | 磁盘或服务器被盗或回收不当。 | BitLocker 提供了一种故障安全方法，用于防止由于服务器/磁盘服务器上被盗或错误回收的硬件 (丢失) 。 |
| 服务加密 | SharePoint联机、Skype for Business和OneDrive for Business;Exchange Online (路线图)  | Microsoft | 内部或外部黑客尝试以 blob 访问单个文件/数据。 | 如果不访问密钥，将无法解密加密数据。 有助于降低黑客访问数据的风险。 |
| 客户密钥 | SharePoint联机、OneDrive for Business、Exchange Online 和 Skype for Business | 客户 | N/A (此功能设计为合规性功能;不能作为任何风险的缓解。)  | 帮助客户履行内部法规和合规性义务，以及离开服务并撤销 Microsoft 对数据的访问权限的能力 |
| 客户端和客户端Microsoft 365 TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Teams 和 Yammer | Microsoft，客户 | 中间人攻击或其他攻击，通过 Internet Microsoft 365和客户端计算机之间的数据流。 | 此实现为 Microsoft 和客户都提供了价值，并确保数据完整性，因为它Microsoft 365客户端之间流动。 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、OneDrive for Business 和 Skype for Business | Microsoft | 中间人攻击或其他攻击，以点击位于不同 Microsoft 数据中心Microsoft 365服务器之间的客户数据流。 | 此实现是保护数据免受 Microsoft 数据中心之间攻击的另一种方法。 |
| Azure 权限管理 (Azure 信息Microsoft 365或 Azure 信息保护)  | Exchange Online、SharePoint Online 和 OneDrive for Business | 客户 | 数据由不应具有数据访问权限的人掌握。 | Azure 信息保护使用 Azure RMS，它通过使用加密、标识和授权策略为客户提供价值，以帮助保护跨多个设备的文件和电子邮件。 Azure RMS 为客户提供了价值，其中所有来自 Microsoft 365 的电子邮件都符合特定条件 (即发送到特定地址) 的所有电子邮件在发送给其他收件人之前可自动加密。 |
| S/MIME | Exchange Online | 客户 | 电子邮件由不是预期收件人的人掌握。 | S/MIME 通过确保使用 S/MIME 加密的电子邮件仅能由电子邮件的直接收件人解密，为客户提供价值。 |
| Office 365 邮件加密 | Exchange Online、SharePoint Online | 客户 | 电子邮件（包括受保护的附件）由不是电子邮件预期接收人Microsoft 365外部人员掌握。 | OME 为客户提供了价值，其中来自 Microsoft 365 的所有符合特定条件的电子邮件 (即发送到特定地址) 的所有电子邮件在发送给其他内部或外部收件人之前将自动加密。 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 客户 | 电子邮件在从 Microsoft 365 租户传输到另一合作伙伴组织期间通过中间人或其他攻击被截获。 | 此方案会为客户提供价值，这样他们就可以在加密的 SMTP 通道Microsoft 365其 Microsoft 365 租户与合作伙伴的电子邮件组织之间发送/接收所有电子邮件。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>多租户环境中可用的加密技术

| 加密技术 | 实现者 | 关键Exchange算法和强度 | 密钥管理\* | FIPS 140-2 验证 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部项存储在 Secret 保险箱中，并存储在 Exchange 服务器的注册表中。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在密钥保险箱。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在密钥保险箱。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint内容数据库中。 联机SharePoint数据库受数据库访问控制和静态加密保护。 加密使用 TDE 在 Azure SQL 数据库。 这些密码位于 SharePoint Online 的服务级别，而不是租户级别。 这些 (有时称为主密钥) 存储在称为密钥存储的单独安全存储库中。 TDE 为活动数据库、数据库备份和事务日志提供了处于非活动状态的安全性。 当客户提供可选密钥时，客户密钥将存储在 Azure 密钥保管库中，服务使用该密钥加密租户密钥，租户密钥用于加密站点密钥，然后用于加密文件级别密钥。 实质上，当客户提供密钥时将引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 每段数据都使用不同的随机生成的 256 位密钥进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也由每个会议的主密钥进行加密。 此外，每个会议还会随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用路线图) 上由 Microsoft (控制的加密密钥，或在将客户密钥用于 (时由客户) 。 | 是 |
| 客户端和Microsoft 365/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Exchange Online TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是，使用 256 位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 带 AES 256 的 TLS 1.2 <br> <br> [OneDrive for Business 和 SharePoint Online 中的数据加密](./data-encryption-in-odb-and-spo.md) | SharePoint Online (*.sharepoint.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | [用于 SIP 通信和 PSOM 数据共享会话的 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business (*.lync.com) TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> 用于证书的 TLS 根证书Skype for Business由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | 带 AES 256 的 TLS 1.2 <br> <br> [有关管理员帮助Microsoft Teams常见问题解答](/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com TLS 证书 edge.skype.com) 由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Microsoft Teams TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | 所有Microsoft 365服务 | 带 AES 256 的 TLS 1.2 <br> <br> 安全实时传输协议 (SRTP)  | Microsoft 使用内部管理和部署的证书颁发机构在 Microsoft 数据中心之间进行服务器到服务器通信。 | 是 |
| Azure 权限管理 (Azure 信息Microsoft 365或 Azure 信息保护)  | Exchange Online | 支持 [加密模式 2，](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))这是更新和增强的 RMS 加密实现。 它支持 RSA 2048 签名和加密，SHA-256 用于签名中的哈希。 | [由 Microsoft 管理](/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2，](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))这是更新和增强的 RMS 加密实现。 它支持 RSA 2048 签名和加密，SHA-256 用于签名。 | [由 Microsoft](/azure/information-protection/plan-implement-tenant-key)管理，这是默认设置;或 <br> <br> 客户管理，这是 Microsoft 管理的密钥的替代项。 具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，无需额外付费。 有关详细信息，请参阅 [实现自带密钥](/azure/information-protection/plan-implement-tenant-key)。 在此配置中，nCipher HSM 用于保护密钥。 有关详细信息，请参阅[nCipher HSM 和 Azure RMS。](https://www.thales-esecurity.com/msrms/cloud) | 是 |
| S/MIME | Exchange Online | 加密消息语法 Standard 1.5 (PKCS #7)  | 取决于部署的由客户管理的公钥基础结构。 密钥管理由客户执行，Microsoft 从无法访问用于签名和解密的私钥。 | 是，当配置为使用 3DES 或 AES256 加密传出邮件时 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS (加密模式 [2](./technical-reference-details-about-encryption.md) - RSA 2048 用于签名和加密，SHA-256 用于签名)  | 使用 Azure 信息保护作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 | 是 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 带 AES 256 的 TLS 1.2 | 适用于 Exchange Online (outlook.office.com) 的 TLS 证书是 2048 位 SHA-256，具有 DigiCert 云服务 CA-1 颁发的 RSA 加密证书。 <br> <br> Exchange Online TLS 根证书是 2048 位 SHA-1，其 RSA 加密证书由[GlobalSign Root CA - R1 颁发](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online)。 <br> <br> 请注意，出于安全考虑，我们的证书会时而更改。 | 是，使用 256 位密码强度的 TLS 1.2 时 |

*\*此表中引用的 TLS 证书用于美国数据中心;非美国数据中心还使用 2048 位 SHA256RSA 证书。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府云社区环境中提供的加密技术

| 加密技术 | 实现者 | 关键Exchange算法和强度 | 密钥管理\* | FIPS 140-2 验证 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部项存储在 Secret 保险箱中，并存储在 Exchange 服务器的注册表中。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在密钥保险箱。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在密钥保险箱。 密码保险箱是一个安全存储库，需要高级提升和批准来访问。 只能使用称为"密码箱"的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint内容数据库中。 联机SharePoint数据库受数据库访问控制和静态加密保护。 加密使用 TDE 在 Azure SQL 数据库。 这些密码位于 SharePoint Online 的服务级别，而不是租户级别。 这些 (有时称为主密钥) 存储在称为密钥存储的单独安全存储库中。 TDE 为活动数据库、数据库备份和事务日志提供了处于非活动状态的安全性。 当客户提供可选密钥时，客户密钥将存储在 Azure 密钥保管库中，服务使用该密钥加密租户密钥，该密钥用于加密站点密钥，然后用于加密文件级别密钥。 实质上，当客户提供密钥时将引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 每段数据都使用不同的随机生成的 256 位密钥进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也由每个会议的主密钥进行加密。 此外，每个会议还会随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用由 Microsoft 控制的加密密钥，或在客户密钥 (客户密钥时由客户) 。 | 是 |
| 客户端和Microsoft 365/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Exchange Online TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是，使用 256 位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 带 AES 256 的 TLS 1.2 | SharePoint Online (*.sharepoint.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | 用于 SIP 通信和 PSOM 数据共享会话的 TLS | Skype for Business (*.lync.com) TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Skype for Business TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | [有关管理员帮助Microsoft Teams常见问题解答](/MicrosoftTeams/teams-overview) | 用于证书的 TLS Microsoft Teams (teams.microsoft.com;edge.skype.com) 由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Microsoft Teams TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、Skype for Business | 带 AES 256 的 TLS 1.2 | Microsoft 使用内部管理和部署的证书颁发机构在 Microsoft 数据中心之间进行服务器到服务器通信。 | 是 |
|  |  | 安全实时传输协议 (SRTP)  |  |  |
| Azure 权限管理服务 | Exchange Online | 支持 [加密模式 2，](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))这是更新和增强的 RMS 加密实现。 它支持 RSA 2048 签名和加密，SHA-256 用于签名中的哈希。 | [由 Microsoft 管理](/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2，](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))这是更新和增强的 RMS 加密实现。 它支持 RSA 2048 签名和加密，SHA-256 用于签名中的哈希。 | [由 Microsoft](/azure/information-protection/plan-implement-tenant-key)管理，这是默认设置;或 <br> <br> 客户管理的 (也称为 BYOK) ，它是 Microsoft 托管密钥的替代方法。 具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，无需额外付费。 有关详细信息，请参阅 [实现自带密钥](/azure/information-protection/plan-implement-tenant-key)。 <br> <br> 在 BYOK 方案中，nCipher HSM 用于保护密钥。 有关详细信息，请参阅[nCipher HSM 和 Azure RMS。](https://www.thales-esecurity.com/msrms/cloud) | 是 |
| S/MIME | Exchange Online | 加密消息语法 Standard 1.5 (PKCS #7)  | 取决于部署的公钥基础结构。 | 是，当配置为使用 3DES 或 AES-256 加密传出邮件时。 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS (加密模式 [2](./technical-reference-details-about-encryption.md) - RSA 2048 用于签名和加密，SHA-256 用于签名和加密)  | 使用 Azure RMS 作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 <br> <br> 如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。 使用的方法取决于您的本地 AD RMS 部署。 加密模式 1 是原始的 AD RMS 加密实现。 它支持 RSA 1024 签名和加密，并支持 SHA-1 签名。 除了使用 HSM 的 BYOK 配置之外，所有当前版本的 RMS 仍支持此模式。 | 是 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 带 AES 256 的 TLS 1.2 | Exchange Online (outlook.office.com) TLS 证书是 2048 位 SHA-256，其 RSA 加密证书由 DigiCert 云服务 CA-1 颁发。 <br> <br> Exchange Online TLS 根证书是 2048 位 SHA-1，其 RSA 加密证书由[GlobalSign Root CA - R1 颁发](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online)。 <br> <br> 请注意，出于安全考虑，我们的证书会时而更改。 | 是，使用 256 位密码强度的 TLS 1.2 时 |

*\*此表中引用的 TLS 证书用于美国数据中心;非美国数据中心还使用 2048 位 SHA256RSA 证书。*