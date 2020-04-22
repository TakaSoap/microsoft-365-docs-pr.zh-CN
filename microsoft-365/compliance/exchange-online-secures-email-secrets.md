---
title: Exchange Online 如何进行电子邮件保密
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了为 Microsoft 365 提供安全性、隐私和合规性信息的 Office 365 信任中心之外，您可能还需要了解 Microsoft 如何帮助保护您在其数据中心中存储的密码。 我们使用一种称为 "分布式密钥管理器" （DKM）的技术。
ms.openlocfilehash: 17a7fbbd54a725edcd87681f011ddc6633a1f4aa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615976"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何进行电子邮件保密

本文介绍了 Microsoft 如何在其数据中心中保护你的电子邮件机密。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我们如何保护你提供的机密信息的安全？

除了提供[office 365 的安全性、隐私和合规性信息](https://go.microsoft.com/fwlink/?linkid=874644)的 Office 365 信任中心之外，你可能还需要了解 Microsoft 如何帮助保护你在其数据中心中提供的密码。 我们使用一种称为 "分布式密钥管理器" （DKM）的技术。
  
[分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)（DKM）是一种使用一组用于加密和解密信息的密钥的客户端功能。 只有 Active Directory 域服务中特定安全组的成员才能访问这些密钥，以便对由 DKM 加密的数据进行解密。 在 Exchange Online 中，仅在运行 Exchange 进程的特定服务帐户是该安全组的一部分。 作为数据中心中的标准操作过程的一部分，将不会向任何人提供属于此安全组的凭据，因此没有人能够访问可以解密这些机密的密钥。
  
对于调试、故障排除或审核目的，数据中心管理员必须请求提升的访问权限，才能获取属于安全组一部分的临时凭据。 此过程需要多个合法的法律审批级别。 如果授予访问权限，则会记录并审核所有活动。 此外，仅授予对设置的时间间隔的访问权限，在此间隔之后它将自动过期。
  
对于额外保护，DKM 技术包括自动化密钥滚动更新和存档。 这还可确保您可以继续访问较旧的内容，而无需无限期地依赖相同的密钥。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online 在哪里使用 DKM？

Microsoft 使用[分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)在 Exchange Online 数据中心中对机密进行加密。 例如：
  
- 已连接帐户的电子邮件帐户凭据。 已连接帐户是第三方帐户，如 Hotmail、Gmail 和 Yahoo！ 邮件帐户。

- Customer 键。 如果您使用[客户密钥进行服务加密](customer-key-overview.md)，则将使用[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)来保护您的机密。

## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)
  
[有关加密的技术参考详细信息](technical-reference-details-about-encryption.md)
  
[安全&amp;合规中心中的服务保证](https://go.microsoft.com/fwlink/?linkid=874645)
  

