---
title: 有关加密的技术参考详细信息
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 了解 Office 365 中用于加密的各种证书、技术和 TLS 密码套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e4b2923d2b250e85efa7fdc50a995db397d670
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814364"
---
# <a name="technical-reference-details-about-encryption"></a>有关加密的技术参考详细信息

请参阅这篇文章，了解用于 [在 Office 365 中加密的证书、技术和 TLS 密码套件](encryption.md)。 本文还提供有关计划的弃用的详细信息。
  
- 如果要查找概述信息，请参阅 [Office 365 中的加密](encryption.md)。
- 如果要查找设置信息，请参阅"在 Office [365 企业版中设置加密"。](set-up-encryption.md)
- 有关特定版本的 Windows 支持的加密套件的信息，请参阅[TLS/SSL 或 Schannel SSP 文件中的 (式套) 。 ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 证书所有权和管理

无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>当前的加密标准和计划的弃用情况

为了继续为 Office 365 提供最佳的加密，Microsoft 会定期审查支持的加密标准。 有时，我们需要在旧标准过期时分解，进而安全性较低。 本主题介绍当前支持的加密套件和其他标准，以及有关计划弃用的详细信息。 

## <a name="fips-compliance-for-office-365"></a>FIPS 合规性 Office 365

Office 365 支持的所有加密套件都使用 FIPS 140-2 下可接受的算法。 Office 365 通过 Schannel 渠道从 Windows (继承 FIPS) 。 有关 Schannel 的信息，请参阅 ["Schannel SSP 服务器中 (TLS/SSL (套件 ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)) 。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支持的 TLS 版本

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。 Office 365 支持 TLS 版本 1.2 (TLS 1.2) 。

目前不支持 TLS (1.3) TLS 1.3 通信。
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>支持 TLS 1.0 和 1.1 弃用以及这是什么意思

自 2018 年 10 月 31 日起，Office 365 不再支持 TLS 1.0 和 1.1。 这意味着对于使用 TLS 1.0 和 1.1 连接到 Office 365 的客户端、设备或服务，Microsoft 将不再修复其出现的新问题。 GCC 高和 DoD 环境的官方弃用，以 2020 年 1 月 15 日为止。 对于世界和 GCC 环境，已弃用 TLS 1.0 和 1.1 以及 GCC 环境，开始于 2020 年 10 月 15 日。 

应确保所有客户端到服务器和浏览器服务器组合都使用 TLS 1.2 和现代密码套件维护与 Office 365 和 Microsoft 365 服务的安全连接。 你可能必须更新某些客户端-服务器和浏览器-服务器组合。 有关这对你有什么影响的信息，请参阅["准备好在 Office 365 中使用 TLS 1.2"。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>弃用对 3DES 的支持

自 2018 年 10 月 31 日起，Office 365 不再支持使用 3DES 加密套件来与 Office 365 进行通信。 更具体地说，Office 365 不再支持以TLS_RSA_WITH_3DES_EDE_CBC_SHA套件。 自 2019 年 2 月 28 日起，此密码套件已在 Office 365 中禁用。 在此日期之后，客户端和服务器必须至少支持一个更安全的密码 (请参阅本主题中所支持的 TLS 密码套件 ([请参阅 Office 365) 。](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>在 Office 365 中弃用 SHA-1 证书支持

自 2016 年 6 月起，Office 365 不再接受出站或入站连接的 SHA-1 证书。 如果你当前正在使用证书链中 SHA-1 的证书，你将需要更新链，以使用 SHA-2 (安全哈希算法 2) 或更强大的哈希算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持的 TLS 加密套件

密码套件是 TLS 用于建立安全连接的加密算法集合。 Office 365 支持的密码套件按强度顺序从最强的密码套件开始依次在下表列出。 当 Office 365 收到一个连接请求时，Office 365 会先尝试使用最上面的密码套件进行连接。 然后，如果不成功，Office 365 会尝试列表中的第二个加密套件，依此类推。 当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。

> [!IMPORTANT]
> 请注意，TLS 版本弃用，因此不应在提供较新版本时使用已弃用*should not be used*的版本。 目前不支持 TLS 1.3。 如果旧版服务不需要 TLS 1.0 或 1.1，则应禁用它们。

| 加密套件 | 密钥交换算法/强度 | 完美向后的密码 | 密码/强度 | 身份验证算法 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |

以下是以下密码套件，在弃用日期之前，仍将支持 TLS 1.0 和 1.1 协议。 对于弃用日期为 2020 年 1 月 15 日的 GCC 高和 DoD 环境，对于全球和 GCC 环境（这一日期已为 2020 年 10 月 15 日）。

| 协议 | 密码套件名称 | 密钥交换算法/强度 | 完美向后连续支持 | 身份验证算法/强度 | 密码/强度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |
   
## <a name="related-topics"></a>相关主题
[Windows 10 v1903 中的 TLS 证书套件](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)
  
[设置 Office 365 企业版中的加密](set-up-encryption.md)
  
[Windows 中 TLS 1.0 的 Schannel 实现安全状态更新：2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[适用于 Windows IT 中心设备的 TLS/SSL 加密 (改进) ](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[在 Office 365 和 Office 365 GCC 中准备 TLS 1.2](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
