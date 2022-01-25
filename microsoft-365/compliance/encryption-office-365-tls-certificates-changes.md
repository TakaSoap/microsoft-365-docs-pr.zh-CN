---
title: Office TLS 证书更改
description: 如何准备即将对 TLS 证书Office更改。
author: pshelton-skype
ms.author: pshelton
manager: toddbeckett
ms.topic: article
audience: Developer
ms.date: 1/21/2021
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.openlocfilehash: c104f5bdc28966d080318ce0559dfe5acbfec8ea
ms.sourcegitcommit: 39838c1a77d4e23df56af74059fb95970223f718
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62187265"
---
# <a name="office-tls-certificate-changes"></a>Office TLS 证书更改

Microsoft 365更新为消息传递、会议、电话、语音和视频提供服务，以使用来自另一组根证书颁发机构或 CA (TLS) 。 进行此更改是因为当前根 CA 将于 2025 年 5 月到期。

受影响的产品包括：
- Microsoft Teams
- Skype
- Skype for Business Online
- Microsoft Dynamics 365
- GroupMe
- Kaizala
- Azure Communication Services

受影响的终结点包括 (，但不限于以下) ：
- *.teams.microsoft.com
- *.skype.com
- *.skypeforbusiness.com
- *.groupme.com
- *.communication.azure.com
- *.operatorconnect.microsoft.com

此更改不会影响美国政府、中国或德国国家/地区云实例中使用的证书、域Microsoft 365。

本文中所有证书信息之前在加密Microsoft 365 [](./encryption-office-365-certificate-chains.md) 2020 年 10 月之前提供。

## <a name="when-will-this-change-happen"></a>何时会发生此更改？

服务将从 2022 年 1 月开始转换到新的根证书库，一直持续到 2022 年 10 月。

## <a name="what-is-changing"></a>更改了哪些方面？

如今，服务中使用的大多数 TLS 证书Microsoft 365到以下根 CA：

| CA 的公用名 | 指纹 (SHA1)  |
|--|--|
| [Baltimore CyberTrust Root](https://cacerts.digicert.com/BaltimoreCyberTrustRoot.crt) | d4de20d05e66fc53fe1a50882c78db2852cae474 |

使用下列中间 A 之一：

| CA 的公用名 | 指纹 (SHA1)  |
|--|--|
| [Microsoft RSA TLS CA 01](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2001.crt) | 703d7a8f0ebf55aaa59f98eaf4a206004eb2516a |
| [Microsoft RSA TLS CA 02](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2002.crt) | b0c2d2d13cdd56cdaa6ab6e2c04440be4a429c75 |

现在，Microsoft 365服务使用的新 TLS 证书将链接至以下根 CA 之一：

| CA 的公用名 | 指纹 (SHA1)  |
|--|--|
| [DigiCert 全局根 G2](https://cacerts.digicert.com/DigiCertGlobalRootG2.crt) | df3c24f9bfd666761b268073fe06d1cc8d4f82a4 |
| [Microsoft RSA 根证书颁发机构 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20RSA%20Root%20Certificate%20Authority%202017.crt) | 73a5e64a3bff8316ff0edccc618a906e4eae4d74 | 
| [Microsoft ECC 根证书颁发机构 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20ECC%20Root%20Certificate%20Authority%202017.crt) | 999a64c37ff47d9fab95f14769891460eec4c3c5 |

使用下列中间 A 之一：

| CA 的公用名 | 指纹 (SHA1)  |
|--|--|
| [Microsoft Azure TLS 颁发 CA 01](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2001%20-%20xsign.crt) | 2f2877c5d778c31e0f29c7e371df5471bd673173 |
| [Microsoft Azure TLS 颁发 CA 02](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2002%20-%20xsign.crt) | e7eea674ca718e3befd90858e09f8372ad0ae2aa |
| [Microsoft Azure TLS 颁发 CA 05](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2005%20-%20xsign.crt) | 6c3af02e7f269aa73afd0eff2a88a4a1f04ed1e5 |
| [Microsoft Azure TLS 颁发 CA 06](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2006%20-%20xsign.crt) | 30e01761ab97e59a06b41ef20af6f2de7ef4f7b0 |

## <a name="will-this-change-affect-me"></a>此更改是否会影响我？

根 CA"DigiCert 全局根 G2"受到操作系统（包括 Windows、macOS、Android 和 iOS）以及 Microsoft Edge、Chrome、Safari 和 Firefox 等浏览器的广泛信任。 我们希望大多数 **Microsoft 365客户不会受到影响**。 

但是 **，如果您的应用程序明确** 指定了可接受的 AA 列表，则应用程序可能会受到影响。 此做法称为"证书固定"。 在可接受 CA 列表中没有新的根 CA 的客户将收到证书验证错误，这可能会影响应用程序的可用性或功能。

下面是检测应用程序是否可能受到影响的一些方法：

- 在源代码中搜索指纹、公用名或此处找到的任何中间证书的其他 [属性](https://www.microsoft.com/pki/mscorp/cps/default.htm)。 如果存在匹配项，则应用程序将受到影响。 若要解决此问题，请更新源代码以添加新 AS 的属性。 最佳做法是，确保可以在短时间内添加或编辑 AA。 行业法规要求在某些情况下在七天内替换 CA 证书，因此实施证书固定的应用程序必须迅速响应这些更改。

- .NET 公开 和 回调函数，这允许开发人员使用自定义逻辑来确定证书是否有效，而不是依赖标准证书Windows `System.Net.ServicePointManager.ServerCertificateValidationCallback` `System.Net.HttpWebRequest.ServerCertificateValidationCallback` 证书存储。 开发人员可以添加用于检查特定公用名或指纹的逻辑，或仅允许特定的根 CA，例如"Baltimore CyberTrust Root"。 如果应用程序使用这些回调函数，则应确保它接受旧的和新的 Root 和中间的 AA。

- 本机应用程序可能正在使用 `WINHTTP_CALLBACK_STATUS_SENDING_REQUEST` ，这允许本机应用程序实现自定义证书验证逻辑。 此通知的使用很少见，并且需要大量自定义代码来实现。 与上述内容类似，请确保应用程序同时接受新旧根和中间证书。 

- 如果你使用与 Microsoft Teams、Skype、Skype for Business Online 或 Microsoft Dynamics API 集成的应用程序，并且不确定它是否使用证书固定，请咨询应用程序供应商。

- 与 Azure 服务通信的不同操作系统和语言运行时可能需要其他步骤来正确构建和验证新的证书链：
   - **Linux：** 许多分发都需要将 CA 添加到 `/etc/ssl/certs` 。 有关特定说明，请参阅分发文档。
   - **Java：** 确保Java密钥存储包含上面列出的 AA。
   - **Windows** 环境中运行：在断开连接的环境中运行的系统需要将新的根 CA 添加到其存储中，并且需要将新的中间 `Trusted Root Certification Authorities` AA 添加到其 `Intermediate Certification Authorities` 存储中。
   - **Android：** 查看你的设备和 Android 版本的文档。
   - **IoT 或嵌入设备**：嵌入式设备（如电视顶盒）通常提供一组有限的根证书颁发机构证书，并且无法轻松更新证书存储。 如果你为自定义嵌入或 IoT 设备编写代码或管理其部署，请确保设备信任新的根证书库。 你可能需要联系设备制造商。

- 如果您的环境防火墙规则只允许对特定终结点进行出站呼叫，则允许以下证书吊销列表 (CRL) 或联机证书状态协议 (OCSP) URL：
   - `http://crl3.digicert.com`
   - `http://crl4.digicert.com`
   - `http://ocsp.digicert.com`
   - `http://crl.microsoft.com`
   - `http://oneocsp.microsoft.com`
   - `http://ocsp.msocsp.com`
   - `http://www.microsoft.com/pkiops`

- 如果受此更改影响，则可能会看到错误消息，这些错误消息取决于您运行的环境类型以及您受到影响的方案。 检查Windows应用程序事件日志、CAPI2 事件日志和自定义应用程序日志，查看如下所示的消息：
   ```output
   An operation failed because the following certificate has validation errors:
   
   Subject Name: CN=teams.microsoft.com
   Issuer Name: CN=Microsoft Azure TLS Issuing CA 01, O=Microsoft Corporation, C=US
   
   Errors:
   
   The root of the certificate chain is not a trusted root authority.
   ```

## <a name="when-can-i-retire-the-old-ca-information"></a>我何时可以停用旧的 CA 信息？

不会吊销当前的根 CA、中间 CA 和叶证书。 根据现有证书的生命周期，至少到 2023 年 10 月需要现有的 CA 公用名和/或指纹。
