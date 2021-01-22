---
title: 客户管理的加密功能
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
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: 本文将介绍可在 Microsoft 365 中管理和配置的加密技术。
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921552"
---
# <a name="customer-managed-encryption-features"></a>客户管理的加密功能

除了 Microsoft 管理的 Microsoft 365 中的加密技术外，Microsoft 365 还适用于可管理和配置的其他加密技术，例如：

- [Azure 权限管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [安全多用途 Internet 邮件扩展](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 邮件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [与合作伙伴组织的安全邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

有关这些技术的其他信息，请参阅 [Microsoft 365 服务说明](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)。

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure 权限 (](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) Azure RMS) 是 Azure 信息保护 [使用的保护技术](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)。 它使用加密、标识和授权策略来帮助保护跨多个平台和设备（手机、平板电脑和电脑）的文件和电子邮件。 信息可以在组织内外受到保护，因为数据仍受保护。 Azure RMS 提供所有文件类型的持久保护，随时随地保护文件，支持企业到企业协作，以及各种 Windows 和非 Windows 设备。 Azure RMS 保护还可以增强 DLP 策略 [ (数据丢失) 保护](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 有关哪些应用程序和服务可以使用 Azure 信息保护中的 Azure 权限管理服务，请参阅应用程序如何支持 [Azure 权限管理服务](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS 与 Microsoft 365 集成，可供所有客户使用。 若要将 Microsoft 365 配置为使用 Azure RMS，请参阅在 SharePoint 管理中心中将 IRM 配置为使用 Azure 权限管理和设置信息权限管理[ (IRM) 。](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx) 如果您运行本地 Active Directory (AD) RMS 服务器，则还可以将 IRM 配置为使用本地 [AD RMS](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)服务器，但我们强烈建议您迁移到 Azure [RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) 以使用新功能，如与其他组织的安全协作。

使用 Azure RMS 保护客户数据时，Azure RMS 使用 2048 位 RSA 非对称密钥和 SHA-256 哈希算法进行完整性加密。 Office 文档和电子邮件的对称密钥是 AES 128 位。 对于受 Azure RMS 保护的每个文档或电子邮件，Azure RMS 将创建一个 AES 密钥 ("内容密钥") ，该密钥嵌入文档中，并且通过文档版本保留。 内容密钥受组织的 RSA 密钥保护 ("Azure 信息保护租户密钥") 作为文档中策略的一部分，并且该策略也由文档作者签名。 此租户密钥通用于受组织的 Azure RMS 保护的所有文档和电子邮件，并且只有组织使用客户管理的租户密钥时，Azure 信息保护管理员才能更改此密钥。 有关 Azure RMS 使用的加密控件详细信息，请参阅 [Azure RMS 如何工作？在底层](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在默认的 Azure RMS 实现中，Microsoft 生成和管理每个租户唯一的根密钥。 客户可以使用名为"自带密钥 [" (BYOK) ](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) 的密钥管理方法，在 Azure RMS 中通过 Azure Key Vault Services 管理其根密钥的生命周期，此方法允许你在本地 HSM (硬件安全模块) 中生成密钥，在转移到 Microsoft 的 FIPS 140-2 级别 2 验证的 HSM 后，可以继续控制此密钥。 不会向任何人员提供对根密钥的访问权限，因为无法导出这些密钥，也无法从保护这些人员的 HSM 中提取这些密钥。 此外，您还可以访问显示随时对根密钥的所有访问的近实时日志。 有关详细信息，请参阅日志记录和分析 [Azure 权限管理使用情况](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 权限管理可帮助缓解威胁，如点击电话、中间人攻击、数据盗窃和无意中违反组织共享策略。 同时，未经授权的用户通过遵循相应数据的策略来阻止任何未经允许的在传输中或处于非安全状态的客户数据访问，从而减轻该数据在有意或无意间落入他人之手的风险，并提供数据丢失防护功能。 如果用作 Azure 信息保护的一部分，Azure RMS 还提供数据分类和标签功能、内容标记、文档访问跟踪和访问吊销功能。 若要详细了解这些功能，请参阅什么是 Azure[信息保护、Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)[信息保护部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)和 Azure 信息保护[快速入门教程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途 Internet 邮件扩展

安全/多用途 Internet 邮件扩展 (S/MIME) 是公钥加密和 MIME 数据数字签名的标准。 S/MIME 在 RFC 3369、3370、3850、3851 等中定义。 它允许用户加密电子邮件并数字签名电子邮件。 使用 S/MIME 加密的电子邮件只能由电子邮件的收件人使用其私钥进行解密，该私钥仅适用于该收件人。 因此，电子邮件不能由电子邮件的收件人外的其他任何人解密。

[Microsoft 支持 S/MIME。](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx) 公共证书分发到客户本地 Active Directory，并存储在可复制到 Microsoft 365 租户的属性中。 与公钥对应的私钥保留在本地，并且永远不会传输到 Office 365。 用户可以使用 Outlook、Web 上的 Outlook 和客户端对组织中两个用户之间的电子邮件进行撰写、加密、解密、Exchange ActiveSync签名。 有关详细信息，请参阅 [Office 365 中的 S/MIME 加密](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 邮件加密

基于[Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)信息保护 (AIP) ) 构建的[Office 365](https://products.office.com/exchange/office-365-message-encryption)邮件加密 (OME) 使你能够向任何人发送加密和受权限保护的邮件。 OME 可缓解威胁，如线路点击和中间人攻击以及其他威胁，例如没有适当权限的未授权用户访问数据。 我们进行了投资，为您提供基于 Azure 信息保护构建的更简单、更直观、安全的电子邮件体验。 你可以保护从 Microsoft 365 发送给组织内外的任何人的邮件。 可以使用任何标识跨一组不同的邮件客户端查看这些邮件，包括 Azure Active Directory、Microsoft 帐户和 Google 标识。 有关组织如何使用加密邮件的信息，请参阅 [Office 365 邮件加密](https://docs.microsoft.com/microsoft-365/compliance/ome)。

## <a name="transport-layer-security"></a>传输层安全性

如果要确保与合作伙伴的安全通信，可以使用入站和出站连接器提供安全和邮件完整性。 可以使用证书在每个连接器上配置强制入站和出站 TLS。 使用加密的 SMTP 通道可以防止数据通过中间人攻击被盗。 有关详细信息，请参阅 [Exchange Online 如何使用 TLS 保护电子邮件连接](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)。

## <a name="domain-keys-identified-mail"></a>已识别邮件的域密钥

Exchange Online Protection (EOP) 和 Exchange Online 支持对 DKIM 邮件中标识的域密钥 (入站) 验证。 DKIM 是一种用于验证邮件是否从它所声称的域发送且不是其他人欺骗的一种方法。 它将电子邮件与负责发送的电子邮件组织链接在一起，是电子邮件加密的更大范例的一部分。 有关此范例的三个部分详细信息，请参阅：

- [设置 SPF 以防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [使用 DKIM 验证从自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [使用 DMARC 验证电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
