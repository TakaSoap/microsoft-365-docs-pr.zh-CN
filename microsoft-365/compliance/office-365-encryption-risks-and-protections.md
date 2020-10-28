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
description: 在本文中，您将了解有关 Office 365 的风险和可用于保护的加密技术。
ms.openlocfilehash: a9abf3dcc6cbd1bdb237c6ccecbbbaa4d42fda2b
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769182"
---
# <a name="encryption-risks-and-protections"></a>加密风险和保护

Microsoft 遵循控制和合规性框架，重点关注 Microsoft 365 服务和客户数据的风险。 Microsoft 实施了大量基于技术和过程的方法， (将其称为控件) 来缓解这些风险。 通过控件确定、评估和缓解风险是一个持续的过程。 

云服务（如设施、网络、服务器、应用程序）的各个层中的控件的实现，用户 (例如 Microsoft 管理员) 和数据构成纵深防御策略。 此策略的关键是，许多不同的控件都是在不同的层实现的，以防止出现相同或类似的风险方案。 如果由于某种原因控件失败，这种多层方法将提供失效安全保护。

下面列出了一些风险方案和可缓解它们的当前可用加密技术。 在许多情况下，也可以通过 Office 365 中实现的其他控件来缓解这些情况。

| 加密技术 | 服务 | 密钥管理 | 风险方案 | 值 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online 和 Skype for Business | Microsoft | 磁盘或服务器被盗或错误地回收。 | BitLocker 提供了一种防故障方法，可防止因被盗或错误回收的硬件 (服务器/磁盘) 而导致数据丢失。 |
| 服务加密 | SharePoint Online、Skype for Business 和 OneDrive for business;Exchange Online (路线图)  | Microsoft | 内部或外部黑客尝试以 blob 的形式访问各个文件/数据。 | 在不访问密钥的情况下，无法解密加密的数据。 帮助缓解黑客访问数据的风险。 |
| 客户密钥 | SharePoint Online、OneDrive for Business、Exchange Online 和 Skype for Business | 客户 | N/A (此功能旨在实现合规性功能;不作为任何风险的缓解措施。 )  | 帮助客户满足内部法规和合规性义务，以及保留服务的能力，并撤销 Microsoft 对数据的访问权限 |
| Microsoft 365 与客户端之间的 TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、团队和 Yammer | Microsoft、客户 | 通过 Internet 点击 Microsoft 365 与客户端计算机之间的数据流的中间人或其他攻击。 | 此实现为 Microsoft 和客户提供了价值，并确保数据完整性在 Microsoft 365 和客户端之间流动。 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、OneDrive for business 和 Skype for Business | Microsoft | 在位于不同 Microsoft 数据中心的 Microsoft 365 服务器之间点击客户数据流的中间人或其他攻击。 | 此实现是保护数据免受 Microsoft 数据中心之间的攻击的另一种方法。 |
| Microsoft 365 或 Azure 信息保护中包含的 azure 权限管理 ()  | Exchange Online、SharePoint Online 和 OneDrive for Business | 客户 | 数据落入不应访问数据的人的手中。 | Azure 信息保护使用 Azure RMS，它通过使用加密、标识和授权策略为客户提供价值，以帮助保护跨多个设备的文件和电子邮件。 Azure RMS 向客户提供了一些价值，在该电子邮件中，所有来自 Microsoft 365 的电子邮件都符合特定条件 (例如，所有电子邮件发送到特定地址) 在发送给其他收件人之前，可以自动对其进行加密。 |
| S/MIME | Exchange Online | 客户 | 电子邮件落入不是预期收件人的人的手中。 | S/MIME 通过确保使用 S/MIME 加密的电子邮件只能由电子邮件的直接收件人解密来为客户提供价值。 |
| Office 365 邮件加密 | Exchange Online、SharePoint Online | 客户 | 电子邮件（包括受保护的附件）在 Microsoft 365 以内或之外的人手中不是电子邮件的预期收件人。 | OME 为客户提供了一些价值，其中来自 Microsoft 365 的所有电子邮件都与特定条件相匹配 (也就是说，在将所有电子邮件发送到其他内部或外部收件人之前，会自动对所有电子邮件进行加密) 。 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 客户 | 在从 Microsoft 365 租户传输到另一个合作伙伴组织时，会通过中间人或其他攻击截获电子邮件。 | 此方案为客户提供了价值，以便他们可以在其 Microsoft 365 租户及其合作伙伴的电子邮件组织内加密的 SMTP 通道中发送/接收所有电子邮件。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>多租户环境中提供的加密技术

| 加密技术 | 实现者 | 密钥交换算法和强度 | 密钥管理 * | 验证 FIPS 140-2 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部密钥存储在 Exchange 服务器的秘密安全和注册表中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是，适用于使用 AES 256-bit * * 的服务器 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在秘密安全中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在秘密安全中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。 SharePoint Online 内容数据库受数据库访问控制和静态加密的保护。 使用 Azure SQL Database 中的 TDE 执行加密。 这些机密是 SharePoint Online 的服务级别，而不是租户级别。 这些机密 (有时称为主密钥) 存储在单独的安全存储库中，称为 "密钥存储区"。 TDE 为活动数据库和数据库备份和事务日志提供了 rest 的安全性。 当客户提供可选密钥时，客户密钥存储在 Azure Key Vault 中，服务使用密钥来加密租户密钥，该密钥用于加密网站密钥，然后使用它来加密文件级密钥。 实质上，当客户提供密钥时，会引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 使用不同的随机生成的256位密钥对每个数据片段进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也是由每会议主密钥加密的。 每次会议中也随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用 Microsoft (路线图) 或客户 (在) 使用客户密钥时控制的加密密钥。 | 是 |
| Microsoft 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA1RSA 证书。 | 是，当使用带256位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1。2 <br> <br> [OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/library/dn905447.aspx) | SharePoint Online ( * sharepoint.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | [适用于 SIP 通信和 PSOM 数据共享会话的 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business ( *. lync.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Skype for Business 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | 使用 AES 256 的 TLS 1。2 <br> <br> [有关 Microsoft 团队的常见问题-管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 团队 (teams.microsoft.com、edge.skype.com) 的 TLS 证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | 所有 Microsoft 365 服务 | 使用 AES 256 的 TLS 1。2 <br> <br> 安全实时传输协议 (SRTP)  | Microsoft 使用内部托管和部署的证书颁发机构来实现 Microsoft 数据中心之间的服务器到服务器的通信。 | 是 |
| Microsoft 365 或 Azure 信息保护中包含的 azure 权限管理 ()  | Exchange Online | 支持 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，这是一个更新和增强的 RMS 加密实现。 它支持签名和加密的 RSA 2048，以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，这是一个更新和增强的 RMS 加密实现。 它支持签名和加密的 RSA 2048，以及用于签名的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，这是默认设置;和 <br> <br> 客户管理的是 Microsoft 托管密钥的替代方法。 具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，而无需额外付费。 有关详细信息，请参阅 [实现提供自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 在此配置中，将使用 nCipher Hsm 来保护你的密钥。 有关详细信息，请参阅 [NCipher hsm 和 AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密邮件语法标准 1.5 (PKCS #7)  | 取决于已部署的客户管理的公钥基础结构。 客户执行密钥管理，Microsoft 永远无法访问用于签名和解密的私钥。 | 是，当配置为使用3DES 或 AES256 加密传出邮件时 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS ([加密模式 2](https://technet.microsoft.com/library/dn569290.aspx) -用于签名和加密的 RSA 2048，以及用于签名的 SHA-256)  | 使用 Azure 信息保护作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 | 是 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1。2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA1RSA 证书。 | 是，当使用带256位密码强度的 TLS 1.2 时 |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心也使用2048位 SHA256RSA 证书。*

***Exchange Online 多租户环境中的大多数服务器都是通过 AES 256 位加密为 BitLocker 进行部署。使用 AES 128 位的服务器将逐步推出。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府云社区环境中提供的加密技术

| 加密技术 | 实现者 | 密钥交换算法和强度 | 密钥管理 * | 验证 FIPS 140-2 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部密钥存储在 Exchange 服务器的秘密安全和注册表中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在秘密安全中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在秘密安全中。 机密安全是一种受保护的存储库，需要高级别提升和访问权限。 只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。 AES 外部密钥也存储在服务器的受信任的平台模块中。 48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。 SharePoint Online 内容数据库受数据库访问控制和静态加密的保护。 使用 Azure SQL Database 中的 TDE 执行加密。 这些机密是 SharePoint Online 的服务级别，而不是租户级别。 这些机密 (有时称为主密钥) 存储在单独的安全存储库中，称为 "密钥存储区"。 TDE 为活动数据库和数据库备份和事务日志提供了 rest 的安全性。 当客户提供可选密钥时，客户密钥存储在 Azure Key Vault 中，服务使用密钥来加密租户密钥，该密钥用于加密网站密钥，然后使用它来加密文件级密钥。 实质上，当客户提供密钥时，会引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 使用不同的随机生成的256位密钥对每个数据片段进行加密。 加密密钥存储在相应的元数据 XML 文件中，该文件也是由每会议主密钥加密的。 每次会议中也随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用数据加密策略进行加密，该策略使用由 Microsoft 或客户 (在使用客户密钥时所控制的加密密钥) 。 | 是 |
| Microsoft 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会 TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA1RSA 证书。 | 是，当使用带256位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1。2 | SharePoint Online ( * sharepoint.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | 适用于 SIP 通信和 PSOM 数据共享会话的 TLS | Skype for Business ( *. lync.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Skype for Business 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | [有关 Microsoft 团队的常见问题-管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 团队 (teams.microsoft.com 的 TLS 证书;edge.skype.com) 是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | Exchange Online、SharePoint Online、Skype for Business | 使用 AES 256 的 TLS 1。2 | Microsoft 使用内部托管和部署的证书颁发机构来实现 Microsoft 数据中心之间的服务器到服务器的通信。 | 是 |
|  |  | 安全实时传输协议 (SRTP)  |  |  |
| Azure 权限管理服务 | Exchange Online | 支持 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，这是一个更新和增强的 RMS 加密实现。 它支持签名和加密的 RSA 2048，以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持 [加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，这是一个更新和增强的 RMS 加密实现。 它支持签名和加密的 RSA 2048，以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，这是默认设置;和 <br> <br> 客户管理的 (也称为 BYOK) ，这是 Microsoft 管理的密钥的替代方法。 具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，而无需额外付费。 有关详细信息，请参阅 [实现提供自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 <br> <br> 在 BYOK 方案中，nCipher Hsm 用于保护你的密钥。 有关详细信息，请参阅 [NCipher hsm 和 AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密邮件语法标准 1.5 (PKCS #7)  | 取决于部署的公钥基础结构。 | 是，当配置为使用3DES 或 AES-256 加密传出邮件时。 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS ([加密模式 2](https://technet.microsoft.com/library/dn569290.aspx) -RSA 2048 用于签名和加密，而 SHA-256 用于签名中的哈希值)  | 使用 Azure RMS 作为其加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。 <br> <br> 如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式2。 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。 使用的方法取决于您的本地 AD RMS 部署。 加密模式 1 是原始的 AD RMS 加密实现。 它支持针对签名和加密的 RSA 1024，并支持对 SHA-1 进行签名。 除了使用 Hsm 的 BYOK 配置之外，所有当前版本的 RMS 仍将继续支持此模式。 | 是 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1。2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust Root 颁发的2048位 sha1RSA 证书。 <br> <br> 请注意，出于安全考虑，我们的证书会随时更改。 | 是 |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心也使用2048位 SHA256RSA 证书。*
