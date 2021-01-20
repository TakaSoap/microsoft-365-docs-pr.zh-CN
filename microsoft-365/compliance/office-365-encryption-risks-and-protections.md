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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: 本文将介绍 Office 365 面临的风险以及可用于保护的加密技术。
ms.openlocfilehash: e6ba5d20d8ef710117e4630db69b2c46289f1d9a
ms.sourcegitcommit: 64262f6f42dcce6a4608b2e3c7ca6190b7009093
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905251"
---
# <a name="encryption-risks-and-protections"></a>加密风险和保护

Microsoft 遵循的控制和合规性框架侧重于 Microsoft 365 服务和客户数据面临的风险。 Microsoft 实施了一大组基于技术和流程的方法 (称为控制措施，) 这些风险。 通过控制措施识别、评估和缓解风险是一个持续的过程。 

在云服务的各个层（如设施、网络、服务器、应用程序、 (（如 Microsoft 管理员) 和数据）中实施控制措施形成深度防御策略。 此策略的关键是在不同层实施许多不同的控制措施，以防范相同或类似的风险情况。 这种多层方法可提供故障安全保护，以防由于某种原因导致控件失败。

下面列出了一些风险方案和当前可用的可缓解这些风险方案的加密技术。 在许多情况下，这些方案还通过 Office 365 中实现的其他控件得到缓解。

| 加密技术 | 服务 | 密钥管理 | 风险方案 | 值 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online 和 Skype for Business | Microsoft | 磁盘或服务器被盗或回收不当。 | BitLocker 提供了一种故障安全方法，用于防止因服务器/磁盘驱动器中回收的硬件被盗 (丢失) 。 |
| 服务加密 | SharePoint Online、Skype for Business 和 OneDrive for Business;Exchange Online (路线图)  | Microsoft | 内部或外部黑客尝试以 blob 访问单个文件/数据。 | 如果不访问密钥，将无法解密加密的数据。 帮助降低黑客访问数据的风险。 |
| 客户密钥 | SharePoint Online、OneDrive for Business、Exchange Online 和 Skype for Business | 客户 | N/A (此功能设计为合规性功能;不作为任何风险的缓解。)  | 帮助客户履行内部法规和合规性义务，以及离开服务并撤销 Microsoft 对数据的访问权限的能力 |
| Microsoft 365 和客户端之间的 TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Teams 和 Yammer | Microsoft、Customer | 中间人或其他攻击，通过 Internet 点击 Microsoft 365 和客户端计算机之间的数据流。 | 此实现为 Microsoft 和客户提供了价值，并确保数据完整性，因为它在 Microsoft 365 和客户端之间流动。 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、OneDrive for Business 和 Skype for Business | Microsoft | 中间人或其他攻击，以点击位于不同 Microsoft 数据中心的 Microsoft 365 服务器之间的客户数据流。 | 此实现是保护数据免受 Microsoft 数据中心之间攻击的另一种方法。 |
| Microsoft 365 (Azure 信息保护中心中包含的 Azure 权限管理)  | Exchange Online、SharePoint Online 和 OneDrive for Business | 客户 | 数据由不应具有数据访问权限的人控制。 | Azure 信息保护使用 Azure RMS，它通过使用加密、标识和授权策略为客户提供价值，以帮助保护跨多个设备的文件和电子邮件。 Azure RMS 为客户提供了价值，其中所有来自 Microsoft 365、符合特定条件的电子邮件 (即发送到特定地址) 的所有电子邮件在发送给其他收件人之前可自动加密。 |
| S/MIME | Exchange Online | 客户 | 电子邮件属于不是预期收件人的人。 | S/MIME 通过确保使用 S/MIME 加密的电子邮件仅能由电子邮件的直接收件人解密，为客户提供价值。 |
| Office 365 邮件加密 | Exchange Online、SharePoint Online | 客户 | 电子邮件（包括受保护的附件）在 Microsoft 365 内部或外部属于不是电子邮件预期收件人的人。 | OME 为客户提供了价值，其中所有来自 Microsoft 365 并符合特定条件的电子邮件 (即发送到特定地址) 的所有电子邮件在发送给其他内部或外部收件人之前将自动加密。 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 客户 | 电子邮件在从 Microsoft 365 租户传输到另一合作伙伴组织期间通过中间人或其他攻击截获。 | 此方案为客户提供了价值，这样他们可以在加密 SMTP 通道内的 Microsoft 365 租户和合作伙伴的电子邮件组织之间发送/接收所有电子邮件。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>多租户环境中可用的加密技术

| 加密技术 | 实现者 | 密钥 Exchange 算法和强度 | 密钥管理\* | FIPS 140-2 验证 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部密钥存储在密码安全中心以及 Exchange 服务器的注册表中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在密码安全中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在密码安全中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。 SharePoint Online 内容数据库受数据库访问控制和静态加密保护。 在 Azure 数据库使用 TDE SQL加密。 这些密码位于 SharePoint Online 的服务级别，而不是租户级别。 这些 (有时称为主密钥) 存储在称为密钥存储的单独安全存储库中。 TDE 可为活动数据库、数据库备份和事务日志提供处于非活动状态的安全性。 当客户提供可选密钥时，客户密钥将存储在 Azure 密钥保管库中，服务使用该密钥加密租户密钥，该密钥用于加密站点密钥，然后用于加密文件级别密钥。 实质上，当客户提供密钥时，将引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 每个数据段都使用不同的随机生成的 256 位密钥进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也由每个会议的主密钥进行加密。 此外，每个会议还会随机生成主密钥一次。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用由 Microsoft (根据路线图) 控制的加密密钥，或在将客户密钥 (客户密钥) 。 | 是 |
| Microsoft 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) TLS 证书是一个 2048 位 SHA256RSA 证书，由 Baltimore CyberTrust Root 颁发。 <br> <br> Exchange Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是，使用 256 位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 带 AES 256 的 TLS 1.2 <br> <br> [OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/library/dn905447.aspx) | SharePoint Online (*.sharepoint.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | [用于 SIP 通信和 PSOM 数据共享会话的 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business (*.lync.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Skype for Business 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | 带 AES 256 的 TLS 1.2 <br> <br> [有关 Microsoft Teams 的常见问题 – 管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com 的 TLS edge.skype.com) 是一个 2048 位 SHA256RSA 证书，由 Baltimore CyberTrust Root 颁发。 <br> <br> Microsoft Teams 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | 所有 Microsoft 365 服务 | 带 AES 256 的 TLS 1.2 <br> <br> 安全实时传输协议 (SRTP)  | Microsoft 对 Microsoft 数据中心之间的服务器到服务器通信使用内部管理和部署的证书颁发机构。 | 是 |
| Microsoft 365 (Azure 信息保护中心中包含的 Azure 权限管理)  | Exchange Online | 支持 [加密模式 2，](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))即更新和增强的 RMS 加密实现。 它支持 RSA 2048 用于签名和加密，SHA-256 支持签名中的哈希。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2，](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))即更新和增强的 RMS 加密实现。 它支持 RSA 2048 进行签名和加密，SHA-256 支持签名。 | [由 Microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)管理，这是默认设置;或 <br> <br> 客户管理的密钥是 Microsoft 管理的密钥的替代项。 拥有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，无需额外付费。 有关详细信息，请参阅 [实现自带密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 在此配置中，nCipher HSM 用于保护密钥。 有关详细信息，请参阅[nCipher HSMs 和 Azure RMS。](https://www.thales-esecurity.com/msrms/cloud) | 是 |
| S/MIME | Exchange Online | 加密邮件语法 Standard 1.5 (PKCS #7)  | 取决于部署的由客户管理的公钥基础结构。 密钥管理由客户执行，Microsoft 从无法访问用于签名和解密的私钥。 | 是，当配置为使用 3DES 或 AES256 加密传出邮件时 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS (加密模式 [2](https://technet.microsoft.com/library/dn569290.aspx) - RSA 2048 用于签名和加密，SHA-256 用于签名)  | 使用 Azure 信息保护作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 | 是 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 带 AES 256 的 TLS 1.2 | Exchange Online (outlook.office.com) TLS 证书是 2048 位 SHA-256，具有 DigiCert 云服务 CA-1 颁发的 RSA 加密证书。 <br> <br> Exchange Online 的 TLS 根证书是 2048 位 SHA-1，其 RSA 加密证书由 [GlobalSign Root CA - R1 颁发](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections?view=o365-worldwide#tls-certificate-information-for-exchange-online)。 <br> <br> 请注意，出于安全原因，我们的证书会时而更改。 | 是，使用 256 位密码强度的 TLS 1.2 时 |

*\*此表中引用的 TLS 证书用于美国数据中心;非美国数据中心还使用 2048 位 SHA256RSA 证书。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府云社区环境中提供的加密技术

| 加密技术 | 实现者 | 密钥 Exchange 算法和强度 | 密钥管理\* | FIPS 140-2 验证 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部密钥存储在密码安全中心以及 Exchange 服务器的注册表中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在密码安全中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在密码安全中。 密码安全是一个安全的存储库，需要高级提升和批准来访问。 只能使用名为 Lockbox 的内部工具请求和批准访问。 AES 外部密钥也存储在服务器的受信任平台模块中。 48 位数字密码存储在 Active Directory 中，受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。 SharePoint Online 内容数据库受数据库访问控制和静态加密保护。 在 Azure 数据库使用 TDE 执行SQL加密。 这些密码位于 SharePoint Online 的服务级别，而不是租户级别。 这些 (有时称为主密钥) 存储在称为密钥存储的单独安全存储库中。 TDE 可为活动数据库、数据库备份和事务日志提供处于非活动状态的安全性。 当客户提供可选密钥时，客户密钥将存储在 Azure 密钥保管库中，服务使用该密钥来加密租户密钥，该密钥用于加密站点密钥，然后用于加密文件级别密钥。 实质上，当客户提供密钥时，将引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 每段数据都使用不同的随机生成的 256 位密钥进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也由每个会议的主密钥进行加密。 主密钥还会根据每个会议随机生成一次。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用由 Microsoft 控制的加密密钥，或在将客户密钥 (客户密钥时由) 。 | 是 |
| Microsoft 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) TLS 证书是一个 2048 位 SHA256RSA 证书，由 Baltimore CyberTrust Root 颁发。 <br> <br> Exchange Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是，使用 256 位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 带 AES 256 的 TLS 1.2 | SharePoint Online (*.sharepoint.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | 用于 SIP 通信和 PSOM 数据共享会话的 TLS | Skype for Business (*.lync.com) 的 TLS 证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Skype for Business 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | [有关 Microsoft Teams 的常见问题 – 管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams 证书的 TLS (teams.microsoft.com;edge.skype.com) 由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 <br> <br> Microsoft Teams 的 TLS 根证书是由 Baltimore CyberTrust Root 颁发的 2048 位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、Skype for Business | 带 AES 256 的 TLS 1.2 | Microsoft 对 Microsoft 数据中心之间的服务器到服务器通信使用内部管理和部署的证书颁发机构。 | 是 |
|  |  | 安全实时传输协议 (SRTP)  |  |  |
| Azure 权限管理服务 | Exchange Online | 支持 [加密模式 2，](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))即更新和增强的 RMS 加密实现。 它支持 RSA 2048 用于签名和加密，SHA-256 支持签名中的哈希。 | [由 Microsoft 管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2，](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))即更新和增强的 RMS 加密实现。 它支持 RSA 2048 用于签名和加密，SHA-256 支持签名中的哈希。 | [由 Microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)管理，这是默认设置;或 <br> <br> 客户管理的 (也称为 BYOK) ，它是 Microsoft 管理的密钥的替代方法。 拥有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，无需额外付费。 有关详细信息，请参阅 [实现自带密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 <br> <br> 在 BYOK 方案中，nCipher HSM 用于保护密钥。 有关详细信息，请参阅[nCipher HSMs 和 Azure RMS。](https://www.thales-esecurity.com/msrms/cloud) | 是 |
| S/MIME | Exchange Online | 加密邮件语法 Standard 1.5 (PKCS #7)  | 取决于部署的公钥基础结构。 | 是，当配置为使用 3DES 或 AES-256 加密传出邮件时。 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS (加密模式 [2](https://technet.microsoft.com/library/dn569290.aspx) - RSA 2048（用于签名和加密）和 SHA-256（用于签名加密）中的哈希)  | 使用 Azure RMS 作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 <br> <br> 如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。 使用的方法取决于您的本地 AD RMS 部署。 加密模式 1 是原始的 AD RMS 加密实现。 它支持 RSA 1024 进行签名和加密，并支持 SHA-1 签名。 除使用 HSM 的 BYOK 配置外，所有当前版本的 RMS 仍支持此模式。 | 是 |
| 合作伙伴组织的 SMTP TLS | Exchange Online | 带 AES 256 的 TLS 1.2 | Exchange Online (outlook.office.com) TLS 证书是 2048 位 SHA-256，具有 DigiCert 云服务 CA-1 颁发的 RSA 加密证书。 <br> <br> Exchange Online 的 TLS 根证书是 2048 位 SHA-1，其 RSA 加密证书由 [GlobalSign Root CA - R1 颁发](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections?view=o365-worldwide#tls-certificate-information-for-exchange-online)。 <br> <br> 请注意，出于安全原因，我们的证书会时而更改。 | 是，使用 256 位密码强度的 TLS 1.2 时 |

*\*此表中引用的 TLS 证书用于美国数据中心;非美国数据中心还使用 2048 位 SHA256RSA 证书。*
