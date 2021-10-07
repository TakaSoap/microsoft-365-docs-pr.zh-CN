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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了为 Microsoft 365 提供安全、隐私和合规性信息Office 365信任中心，您可能还想知道 Microsoft 如何帮助保护存储在其数据中心中的机密。 我们使用名为分布式密钥管理器技术 (DKM) 。
ms.openlocfilehash: 01c254da55e4e9c27b2a4d8423a8f3d4dce3812c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194425"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何进行电子邮件保密

本文介绍了 Microsoft 如何保护其数据中心中的电子邮件密码。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我们如何保护你提供的机密信息？

除了为[Office 365](./get-started-with-service-trust-portal.md)提供安全、隐私和合规性信息的 Office 365 信任中心外，你可能还想知道 Microsoft 如何帮助保护你在数据中心中提供机密。 我们使用名为分布式密钥管理器技术 (DKM) 。
  
[分布式密钥 (](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) DKM) 是一项客户端功能，它使用一组密钥加密和解密信息。 只有 Active Directory 域服务中特定安全组的成员可以访问这些密钥，以便解密由 DKM 加密的数据。 在Exchange Online中，只有运行 Exchange 进程的某些服务帐户是该安全组的一部分。 作为数据中心中标准操作过程一部分，不会向人员提供属于此安全组的凭据，因此，人员无法访问可解密这些密钥的密钥。
  
为了进行调试、故障排除或审核，数据中心管理员必须请求提升的访问权限，才能获取属于安全组的临时凭据。 此过程需要多个级别的法律审批。 如果授予访问权限，将记录并审核所有活动。 此外，仅在一组时间间隔内授予访问权限，在此时间间隔后，该时间间隔将自动过期。
  
为了提供额外的保护，DKM 技术包括自动密钥滚动和存档。 这还可确保您可以继续访问旧内容，而无需无限期地依赖同一密钥。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>在哪里Exchange Online DKM？

Microsoft 使用[分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)加密数据中心Exchange Online密钥。 例如：
  
- 已连接帐户的电子邮件帐户凭据。 连接帐户是 Hotmail、Gmail 和 Yahoo！ 邮件帐户。

- 客户密钥。 如果你将服务加密与客户密钥一同 [使用](customer-key-overview.md)，你将使用 [Azure 密钥](/azure/key-vault/key-vault-whatis) 保管库来保护你的密钥。

## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)
  
[有关加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[安全与合规中心 &amp; 中的服务保证](./service-assurance.md)
