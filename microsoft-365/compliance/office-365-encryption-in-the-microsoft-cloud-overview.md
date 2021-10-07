---
title: Microsoft 云中的加密
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
description: 本文概述了在 Microsoft 云中用于保护客户数据安全的各种形式的加密。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c888c1958eb5265c31ae981e42a96eeeeb57f3ef
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194377"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft 云中的加密

Microsoft 企业云服务中的客户数据受多种技术和流程的保护，包括各种加密形式。  (此文档中的客户数据包括Exchange Online内容、电子邮件正文、日历条目、 和电子邮件附件的内容，如果适用，Skype for Business 内容) 、SharePoint Online 网站内容和网站中存储的文件以及上传到 OneDrive for Business 或 Skype for Business.) Microsoft 的文件在其产品和服务中使用多个加密方法、协议和密码，以帮助为客户提供安全路径，以便客户数据在云服务中传输，并帮助保护我们云服务中存储的客户数据的机密性。 Microsoft 使用一些可用的最强、最安全的加密协议来阻止未经授权访问客户数据。 正确的密钥管理也是加密最佳做法的一个基本要素，Microsoft 致力于确保所有 Microsoft 管理的加密密钥都得到正确保护。

Microsoft 企业云服务中存储的客户数据使用一种或多种加密形式进行保护。  (我们的加密策略的验证及其实施由多个第三方审核员独立验证，有关这些审核的报告可在服务信任门户[.) ](https://aka.ms/stp)

Microsoft 提供对处于其余和传输中的客户数据进行加密的服务器端技术。 例如，对于静态客户数据，Microsoft Azure 使用[BitLocker](/windows/device-security/bitlocker/bitlocker-overview)和[DM-Crypt，Microsoft 365](https://en.wikipedia.org/wiki/Dm-crypt)使用 BitLocker、Azure 存储[Service Encryption、](/azure/)分布式密钥管理器[ (](./exchange-online-secures-email-secrets.md) DKM) 和 Microsoft 365 服务加密。 对于传输中的客户数据，Azure、Office 365、Microsoft 商业支持、Microsoft Dynamics 365、Microsoft Power BI 和 Visual Studio Team Services 使用行业标准的安全传输协议，例如 Internet 协议安全性 (IPsec) 和传输层安全性 (TLS) 、Microsoft 数据中心之间以及用户设备和 Micr 之间osoft 数据中心。

除了 Microsoft 提供的加密安全基线级别之外，我们的云服务还包括您可以管理的加密选项。 例如，你可以为 Azure 虚拟机与虚拟机及其用户之间的 (启用) 加密。 借助 [Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/)，可以使用行业标准 IPsec 协议加密企业 VPN 网关和 Azure 之间的流量。 还可以对虚拟网络上的 VM 之间的通信进行加密。 此外，[新的Office 365 邮件加密](set-up-new-message-encryption-capabilities.md)功能允许您向任何人发送加密邮件。

遵循公钥基础结构操作安全标准（Microsoft 安全策略的一个组件），Microsoft[](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)使用 Windows 操作系统中包含的加密功能实现证书和身份验证机制。 这些机制包括使用符合美国联邦信息处理标准 [ (](https://csrc.nist.gov/publications/PubsFIPS.html) FIPS) 140-2 标准的加密模块。 您可以使用加密模块验证计划 CMVP 搜索 Microsoft 的相关 NIST [证书编号](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)。

> [注意]若要以资源访问 Microsoft 安全策略，必须使用工作或学校帐户登录。 如果还没有订阅， [可以注册免费试用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 是专门用于验证实现加密的产品模块而非使用它们的产品的标准。 可以将在服务中实现的加密模块认证为满足哈希强度、密钥管理等要求。 用于保护 Microsoft 云服务中数据的机密性、完整性或可用性的加密模块和密码符合 FIPS 140-2 标准。

Microsoft 通过每个新版本的 Windows 操作系统验证云服务中使用的基础加密模块：

- Azure 和 Azure 美国政府
- Dynamics 365 和 Dynamics 365 美国政府
- Office 365、Office 365 美国政府版和 Office 365 美国政府国防部版

静态客户数据的加密由多种服务端技术提供，包括 Exchange Online、Skype for Business、OneDrive for Business 和 SharePoint Online 中的 BitLocker、DKM、Azure 存储 服务加密和服务加密. Office 365服务加密包括使用存储在 Azure 密钥保管库中的客户管理的加密密钥的选项。 此客户管理的密钥[选项称为客户](./customer-key-overview.md)密钥，可用于 Exchange Online、SharePoint Online、Skype for Business 和 OneDrive for Business。

对于传输中的客户数据，Office 365默认情况下使用 TLS 与客户端计算机协商安全会话，以确保客户数据的安全。 例如，Office 365安全会话与 Skype for Business、Outlook 和 Outlook 网页版、移动客户端和 Web 浏览器协商。

 (默认情况下，所有面向客户的服务器都协商 TLS 1.2。) 

## <a name="related-links"></a>相关链接

- [Azure 中的加密](office-365-azure-encryption.md)
- [用于加密的 BitLocker 和 Distributed Key Manager (DKM)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服务加密](office-365-service-encryption.md)
- [Office 365Skype for Business、OneDrive for Business、SharePoint Online 和 Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [传输中的数据的加密](/compliance/assurance/assurance-encryption-in-transit)
- [客户管理的加密功能](office-365-customer-managed-encryption-features.md)
- [加密风险和保护](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)