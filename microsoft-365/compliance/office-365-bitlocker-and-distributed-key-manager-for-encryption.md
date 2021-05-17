---
title: BitLocker加密
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
description: 了解用户Office 365加密BitLocker，从而减少由于计算机和磁盘丢失或被盗而发生数据盗窃的可能性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033620"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>用于加密的 BitLocker 和 Distributed Key Manager (DKM)

Microsoft 服务器BitLocker在卷级别加密包含客户其余数据的磁盘驱动器。 BitLocker加密是内置于数据保护Windows。 BitLocker 是一种技术，当其他过程或控制 (（例如访问控制或硬件) 的回收）出现故障时，用于防范威胁，这可能会导致某人获得对包含客户数据的磁盘的物理访问权限。 在这种情况下，BitLocker丢失、被盗或不当停用的计算机和磁盘，从而消除数据被盗或泄露的可能性。

BitLocker在包含 Exchange Online、SharePoint Online 和 Skype for Business 中客户数据的磁盘上使用高级加密标准 (AES) 256 位加密进行部署。 磁盘扇区使用全卷加密密钥 (FVEK) 进行加密，该密钥使用卷主密钥 (VMK) 进行加密，而卷主密钥又绑定到服务器中的受信任平台模块 (TPM) 。 VMK 直接保护 FVEK，因此，保护 VMK 变得至关重要。 下图演示了给定服务器BitLocker使用 BitLocker 服务器保护链的示例 (使用 Exchange Online 服务器) 。

下表介绍了给定服务器BitLocker的密钥保护链 (，即Exchange Online服务器) 。

| 密钥保护程序 | GRANULARITY | 如何生成？ | 存储在何处？ | 保护 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位外部密钥 | 每台服务器 | BitLockerAPI | TPM 或密码保险箱 | 密码箱/访问控制 |
|  |  |  | 邮箱服务器注册表 | TPM 加密 |
| 48 位数字密码 | 每个磁盘 | BitLockerAPI | Active Directory | 密码箱/访问控制 |
| X.509 证书作为数据恢复代理 (DRA) 也称为公钥保护程序 | 环境 (，例如Exchange Online多租户)  | Microsoft CA | 生成系统 | 没有用户具有私钥的完整密码。 密码受到物理保护。 |


BitLocker管理涉及管理用于解锁/恢复 Microsoft 数据中心中的加密磁盘的恢复密钥。 Microsoft 365将主密钥存储在安全共享中，只有经过筛选和批准的个人才能访问。 密钥的凭据存储在访问控制数据的安全存储库中 (我们称之为"机密存储") ，这需要高级提升和管理批准，以使用实时访问提升工具访问。

BitLocker支持分为两种管理类别的密钥：

- BitLocker托管的密钥，这些密钥通常是短期的，并绑定到安装在服务器或给定磁盘上的操作系统实例的生命周期。 这些密钥在服务器重新安装或磁盘格式化期间被删除和重置。

- BitLocker恢复密钥，这些密钥在BitLocker但用于磁盘解密。 BitLocker操作系统和加密数据磁盘已存在的方案使用恢复密钥。 恢复密钥还由托管可用性监视探测器Exchange Online响应程序可能需要解锁磁盘的探测器。

BitLocker保护的卷使用完整卷加密密钥进行加密，而该密钥又使用卷主密钥进行加密。 BitLocker FIPS 兼容的算法来确保从不会以清晰方式通过线路存储或发送加密密钥。 客户Microsoft 365 rest-protection 的默认实现不会偏离默认的BitLocker实现。
