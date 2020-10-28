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
description: 了解用于 Office 365 中的加密的各种证书、技术和 TLS 密码套件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb45f325095143e6f66d9cd2bfa6f3875fb03043
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769172"
---
# <a name="technical-reference-details-about-encryption"></a>有关加密的技术参考详细信息

请参阅本文，了解用于 [Office 365 中用于加密](encryption.md)的证书、技术和 TLS 密码套件。 此外，本文还提供有关计划的 deprecations 的详细信息。

- 如果你正在寻找概述信息，请参阅 [Office 365 中的加密](encryption.md)。
- 如果你正在寻找安装程序信息，请参阅 [在 Office 365 企业版中设置加密](set-up-encryption.md)。
- 有关 Windows 特定版本支持的密码套件的信息，请参阅 [TLS/SSL 中的密码套件 (SCHANNEL SSP) ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 证书所有权和管理

无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。

## <a name="current-encryption-standards-and-planned-deprecations"></a>当前加密标准和计划的 deprecations

为了继续为 Office 365 提供一流的加密，Microsoft 会定期审查受支持的加密标准。 有时，我们需要弃用旧的标准，因为它们已过期，因此安全性较低。 本主题介绍当前支持的密码套件和其他标准以及有关计划的 deprecations 的详细信息。

## <a name="fips-compliance-for-office-365"></a>适用于 Office 365 的 FIPS 合规性

Office 365 支持的所有密码套件使用 FIPS 140-2 可接受的算法。 Office 365 通过 Schannel) 从 Windows (继承 FIPS 验证。 有关 Schannel 的信息，请参阅 [TLS/SSL 中的密码套件 (SCHANNEL SSP) ](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支持的 TLS 版本

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。 Office 365 支持 TLS 版本 1.2 (TLS 1.2) 。

TLS 版本 1.3 (TLS 1.3) 目前不受支持。

## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>支持 TLS 1.0 和1.1 弃用，以及这对你来说意味着什么

自2018年10月31日起，Office 365 不再支持 TLS 1.0 和1.1。 这意味着对于使用 TLS 1.0 和 1.1 连接到 Office 365 的客户端、设备或服务，Microsoft 将不再修复其出现的新问题。 适用于 GCC 高和 DoD 的正式弃用环境开始2020年1月15日。 在全球和 GCC 环境2020中，过时的 TLS 1.0 和1.1 将于年10月15日开始。

应确保所有客户端服务器和浏览器的组合都使用 TLS 1.2 和新式密码套件来维护与 Office 365 和 Microsoft 365 服务的安全连接。 你可能必须更新某些客户端-服务器和浏览器-服务器组合。 有关这对你有何影响的信息，请参阅在 [Office 365 中强制使用 TLS 1.2 的准备工作](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

## <a name="deprecating-support-for-3des"></a>对3DES 的弃用支持

自2018年10月31日起，Office 365 不再支持使用3DES 密码套件与 Office 365 通信。 更具体地说，Office 365 不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。 从2019年2月28日起，此密码套件在 Office 365 中已禁用。 在此日期之后，与 Office 365 通信的客户端和服务器必须至少支持本主题中列出的一个更安全的密码 (请参阅 [Office 365 支持的 TLS 密码套件](#tls-cipher-suites-supported-by-office-365)) 。

## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>在 Office 365 中弃用 SHA-1 证书支持

从6月2016，Office 365 不再为出站或入站连接接受 SHA-1 证书。 如果你当前在证书链中使用 SHA-1 证书，则需要更新链以使用 SHA-1 (安全哈希算法 2) 或更强的哈希算法。

## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持的 TLS 密码套件

密码套件是 TLS 用于建立安全连接的加密算法集合。 Office 365 支持的密码套件按强度顺序从最强的密码套件开始依次在下表列出。 当 Office 365 收到连接请求时，Office 365 将首先尝试使用最上面的密码套件进行连接。 然后，如果失败，Office 365 将尝试列表中的第二个密码套件，依次向下表中。 当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。

> [!IMPORTANT]
> 请注意，TLS 版本弃用，如果有更新的版本，则 *不应使用* 此版本。 目前不支持 TLS 1.3。 如果您的旧服务不需要 TLS 1.0 或1.1，则应禁用它们。

| 密码套件 | 密钥交换算法/强度 | 完全向前保密 | 密码/强度 | 身份验证算法 |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|是 <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|是 <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |否 <br/> |AES/256 <br/>|RSA/112 <br/> |

以下是在其弃用日期之前仍支持 TLS 1.0 和1.1 协议的以下密码套件。 对于 GCC 的高和 DoD 环境，弃用日期为2020年1月15日，在全球和 GCC 环境中，日期为10月15日，即2020。

| 协议 | 密码套件名称 | 密钥交换算法/强度 | 完全向前保密支持 | 身份验证算法/强度 | 密码/强度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |否  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |否   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-topics"></a>相关主题
[Windows 10 v1903 中的 TLS 密码套件](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 中的加密](encryption.md)

[设置 Office 365 企业版中的加密](set-up-encryption.md)

[加密风险和保护](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections?view=o365-worldwide)

[在 Windows 安全状态更新中，TLS 1.0 的 Schannel 实现：11月24日，2015](https://support.microsoft.com/kb/3117336)

[ (Windows IT 中心) 的 TLS/SSL 加密增强功能 ](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)

[在 Office 365 和 Office 365 GCC 中准备 TLS 1.2](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
