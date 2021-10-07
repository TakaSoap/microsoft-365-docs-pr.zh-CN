---
title: BitLocker for Encryption
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
description: 了解用户Office 365 BitLocker 加密，从而减少由于计算机和磁盘丢失或被盗而发生数据盗窃的可能性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343a5966dc24954e98d7d31977aacbc09daaba11
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197565"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>用于加密的 BitLocker 和 Distributed Key Manager (DKM)

Microsoft 服务器使用 BitLocker 在卷级别加密包含客户数据的其余磁盘驱动器。 BitLocker 加密是内置于 Windows。 BitLocker 是一种技术，当其他过程或控制 (（例如访问控制或硬件) 的回收）出现故障时，用于防范威胁，这可能会导致某人获得对包含客户数据的磁盘的物理访问权限。 在这种情况下，BitLocker 消除了由于丢失、被盗或不当停用计算机和磁盘而发生数据盗窃或泄露的可能性。

BitLocker 使用高级加密标准 (AES) 256 位加密部署在包含 Exchange Online、SharePoint Online 和 Skype for Business 中客户数据的磁盘上。 磁盘扇区使用全卷加密密钥 (FVEK) 进行加密，该密钥使用卷主密钥 (VMK) 进行加密，而卷主密钥又绑定到服务器中的受信任平台模块 (TPM) 。 VMK 直接保护 FVEK，因此，保护 VMK 变得至关重要。 下图演示了给定服务器服务器的 BitLocker 密钥保护链示例， (使用 Exchange Online 服务器) 。

下表介绍了给定服务器服务器的 BitLocker 密钥保护链 (在这种情况下，Exchange Online服务器) 。

| 密钥保护程序 | GRANULARITY | 如何生成？ | 存储在何处？ | 保护 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位外部密钥 | 每台服务器 | BitLocker API | TPM 或机密保险箱 | 密码箱/访问控制 |
|  |  |  | 邮箱服务器注册表 | TPM 加密 |
| 48 位数字密码 | 每个磁盘 | BitLocker API | Active Directory | 密码箱/访问控制 |
| X.509 证书作为数据恢复代理 (DRA) 也称为公钥保护程序 | 环境 (，例如Exchange Online多租户)  | Microsoft CA | 生成系统 | 没有用户具有私钥的完整密码。 密码受到物理保护。 |


BitLocker 密钥管理涉及管理用于解锁/恢复 Microsoft 数据中心中的加密磁盘的恢复密钥。 Microsoft 365 将主密钥存储在安全的共享中，只有经过筛选和批准的个人才能访问。 密钥的凭据存储在访问控制数据的安全存储库中 (我们称为"机密存储") ，这需要高级提升和管理批准，以使用实时访问提升工具访问。

BitLocker 支持两个管理类别的密钥：

- BitLocker 管理的密钥通常生存期较短，并且与服务器或给定磁盘上安装的操作系统实例的生存期绑定。 这些密钥会在服务器重新安装或磁盘格式化期间删除并重置。

- BitLocker 恢复密钥，在 BitLocker 外部管理，但用于磁盘解密。 BitLocker 将恢复密钥用于重新安装操作系统且已存在加密数据磁盘的场景。 恢复密钥也由 Exchange Online 中的托管可用性监视探测使用，响应者可能需要在其中解锁磁盘。

受 BitLocker 保护的卷使用完整卷加密密钥进行加密，而完整卷加密密钥又使用卷主密钥进行加密。 BitLocker 使用符合 FIPS 的算法来确保从不会以清晰方式通过线路存储或发送加密密钥。 客户静态数据保护的 Microsoft 365 实现不会偏离默认的 BitLocker 实现。
