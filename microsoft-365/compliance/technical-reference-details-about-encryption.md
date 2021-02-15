---
title: 有关加密的技术参考详情
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 了解 Office 365 和 Microsoft 365 中用于加密的各种证书、技术和传输层安全性 (TLS) 密码套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e6b001b308519fb35e0cc835ac03fb4b27db260
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233138"
---
# <a name="technical-reference-details-about-encryption"></a>有关加密的技术参考详情

请参阅本文，了解 Office [365](encryption.md)中用于加密的证书、技术和 TLS 密码套件。 本文还提供了有关计划弃用的详细信息。
  
- 如果要查找概述信息，请参阅 [Office 365 中的加密](encryption.md)。
- 如果要查找设置信息，请参阅"在 [Office 365](set-up-encryption.md)企业版中设置加密"。
- 有关特定版本的 Windows 支持的加密套件的信息，请参阅 [TLS/SSL (Schannel SSP ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)) 。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 证书所有权和管理

无需购买或维护 Office 365 的证书。 相反，Office 365 使用自己的证书。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>当前加密标准和计划弃用

为了提供一流的加密，Office 365 会定期查看支持的加密标准。 有时，旧标准会随着过时和安全降低而弃用。 本文介绍当前受支持的密码套件以及其他有关计划弃用的标准和详细信息。

## <a name="fips-compliance-for-office-365"></a>Office 365 的 FIPS 合规性

Office 365 支持的所有密码套件都使用 FIPS 140-2 下可接受的算法。 Office 365 通过 Schannel (从 Windows) 。 有关 Schannel 的信息，请参阅[Schannel SSP (TLS/SSL 中的加密) 。 ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支持的 TLS 版本

TLS 和 TLS 之前颁发的 SSL 是加密协议，使用安全证书加密计算机之间的连接，保护网络通信的安全。 Office 365 支持 TLS 版本 1.2 (TLS 1.2) 。

TLS 版本 1.3 (TLS 1.3) 当前不受支持。
  
## <a name="support-for-tls-10-and-11-deprecation"></a>支持 TLS 1.0 和 1.1 弃用

Office 365 于 2018 年 10 月 31 日停止支持 TLS 1.0 和 1.1。 我们已完成在 GCC High 和 DoD 环境中禁用 TLS 1.0 和 1.1。 从 2020 年 10 月 15 日开始，我们针对全球和 GCC 环境禁用 TLS 1.0 和 1.1，并会继续在接下来几周和几个月内推出。

为了维护与 Office 365 和 Microsoft 365 服务的安全连接，所有客户端-服务器和浏览器服务器组合都使用 TLS 1.2 和新式密码套件。 你可能必须更新某些客户端-服务器和浏览器-服务器组合。 有关此更改如何影响你的信息，请参阅准备在[Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>弃用对 3DES 的支持

自 2018 年 10 月 31 日起，Office 365 不再支持使用 3DES 密码套件与 Office 365 通信。 更具体地说，Office 365 不再支持TLS_RSA_WITH_3DES_EDE_CBC_SHA密码套件。 自 2019 年 2 月 28 日起，此密码套件已在 Office 365 中禁用。 与 Office 365 通信的客户端和服务器必须支持一个或多个受支持的密码。 有关受支持的密码的列表，请参阅 [Office 365 支持的 TLS 密码套件](#tls-cipher-suites-supported-by-office-365)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>在 Office 365 中弃用 SHA-1 证书支持

自 2016 年 6 月，Office 365 不再接受出站或入站连接的 SHA-1 证书。 在证书链 (SHA-2) 安全哈希算法 2 或更强大的哈希算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持的 TLS 密码套件

TLS *使用加密套件* 和加密算法集合来建立安全连接。 Office 365 支持下表中列出的密码套件。 该表按强度顺序列出了密码套件，首先列出了最强密码套件。

Office 365 通过首先尝试使用最安全的密码套件进行连接来响应连接请求。 如果连接不起作用，Office 365 将尝试列表中的第二个最安全密码套件，以此类比。 该服务将继续在列表中向下运行，直到接受连接。 同样，当 Office 365 请求连接时，接收服务会选择是否使用 TLS 以及使用哪个密码套件。

> [!IMPORTANT]
> 请注意，TLS 版本已弃用，并且不应在提供较新版本的地方使用已弃用的版本。 TLS 1.3 当前不受支持。 如果旧服务不需要 TLS 1.0 或 1.1，应禁用它们。

| 密码套件 | 密钥交换算法/强度 | 向前保密 | 密码/强度 | 身份验证算法 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |

这些密码套件支持 TLS 1.0 和 1.1 协议，直到其弃用日期。 对于弃用日期为 2020 年 1 月 15 日的 GCC High 和 DoD 环境，以及 2020 年 10 月 15 日的全球和 GCC 环境。

| 协议 | 密码套件名称 | 密钥交换算法/强度 | 向前保密支持 | 身份验证算法/强度 | 密码/强度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>相关文章

[Windows 10 v1903 中的 TLS 密码套件](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)
  
[设置 Office 365 企业版中的加密](set-up-encryption.md)
  
[Windows 安全状态更新中 TLS 1.0 的 Schannel 实现：2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[Windows IT 中心 (TLS/SSL 加密) ](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[在 Office 365 和 Office 365 GCC 中准备 TLS 1.2](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
