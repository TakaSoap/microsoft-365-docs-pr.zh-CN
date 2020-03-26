---
title: Office 365 加密链-DOD 和 GCC 高
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/24/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 查看 Office 365 中 DOD 和 GCC 高根证书和证书颁发机构（Ca）的完整列表。
ms.openlocfilehash: 615a62b2ae2a954580ebf82f4c1b70748c991a71
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951900"
---
# <a name="office-365-encryption-chains---dod-and-gcc-high"></a>Office 365 加密链-DOD 和 GCC 高

Office 365 利用了许多不同的证书提供程序。 下面介绍了在访问 Office 365 时， **DOD 和 GCC 高级客户**可能会遇到的已知 Office 365 根证书的完整列表。 有关您可能需要在自己的基础结构中安装的证书的信息，请参阅[Plan for 第三方 SSL 证书（适用于 Office 365](https://docs.microsoft.com/office365/enterprise/plan-for-third-party-ssl-certificates)）。

以下证书信息适用于**所有 DOD 和 GCC 高级客户**。

>[!NOTE]
>有关适用于**全球客户**的证书信息，请参阅[Office 365 加密链](encryption-office-365-certificate-chains.md)。

| **证书类型** | **P7b 下载** | **CRL 终结点** | **OCSP 终结点** |
| --- | --- | --- | --- | --- |
| 公开信任的根证书和中间证书 | [Office 365 ITAR 证书捆绑（P7B）](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/O365_Chain_Certs_ITAR20200304.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

展开下面的根和中间部分，查看有关证书提供程序的其他详细信息。

## <a name="office-365-certificate-details"></a>**Office 365 证书详细信息**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **主题** | CN = 巴尔的摩 CyberTrust 根<br>OU = CyberTrust<br>O = 巴尔的摩<br>C = IE |
| --- | --- |
| **序列号** | 02：00：00： B9 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 5月 12 18:46:00 2000 UTC |
| **不晚的有效性** | 5月 12 23:59:00 2025 UTC |
| **主题密钥标识符** | e5：9d：59：30：82：47：47：47：58：47：（ac： fa：08：54：36： f0 |
| **指纹（SHA-1）** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **指纹（SHA-256）** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **Pin （SHA-256）** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert 云服务 CA-1**

| **主题** | CN = DigiCert 云服务 CA-1<br>O = DigiCert Inc。<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = DigiCert 全局根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C = 美国 |
| **序列号** | 01：9E： C1： C6： BD：3F：59：7B： B2：0C：33：38： E5：51： D8：77：77 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 8月 04 12:00:00 2015 UTC |
| **不晚的有效性** | 8月 04 12:00:00 2030 UTC |
| **主题密钥标识符** | dd：51： d0： a2：31：8f： a9：： ae：： b4：01：7e：5d：8c：57： cb：： f0： f7 |
| **颁发机构密钥标识符** | keyid：03：50：50：35：56： f0： d1：4c： bb：： a3：： e2：1b：1b：1b：？：： |
| **指纹（SHA-1）** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **指纹（SHA-256）** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **Pin （SHA-256）** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **CRL Url** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**DigiCert 全局根 CA**

| **主题** | CN = DigiCert 全局根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C = 美国 |
| --- | --- |
| **序列号** | 08：3B： E0：56：90：42：46： B1： A1：75：6A：59：59：91： C7：4A |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 10 00:00:00 2006 年11月 |
| **不晚的有效性** | 10 00:00:00 2031 年11月 |
| **主题密钥标识符** | 03：50：35：35：56： d1： d1： f0：（66：： a3：： e2：1b：1b：1b：）： b2：：3d： d1：55 |
| **颁发机构密钥标识符** | keyid：03：50：50：35：56： f0： d1：4c： bb：： a3：： e2：1b：1b：1b：？：： |
| **指纹（SHA-1）** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **指纹（SHA-256）** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **Pin （SHA-256）** | r/mIkG3eEpVdm + u/ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-high-assurance-ev-root-ca"></a>**DigiCert 高确定性 EV 根 CA**

| **主题** | CN = DigiCert 高确定性 EV 根 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C = 美国 |
| --- | --- |
| **序列号** | 02： AC：5C：26：40：9B：40：40：40：：8F：0B： |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 10 00:00:00 2006 年11月 |
| **不晚的有效性** | 10 00:00:00 2031 年11月 |
| **主题密钥标识符** | b1：3e： c3：69：03： f8： bf：47：01： d4：98：26：1a：1：08：02： ef：63：64：2b： c3 |
| **颁发机构密钥标识符** | keyid： b1：3e： c3：69：03：03： bf：47：01： d4：98：26：03：03：02：02：1：63：64：2b： c3 |
| **指纹（SHA-1）** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **指纹（SHA-256）** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **Pin （SHA-256）** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**DigiCert SHA2 扩展验证服务器 CA**

| **主题** | CN = DigiCert SHA2 扩展验证服务器 CA<br>OU = digicert<br>O = DigiCert Inc。<br>C = 美国 |
| --- | --- |
| **序列号** | 0C：79： A9：44：44：8C：11：95：20：92：61：5F： E2：6B：1D：83 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | Oct 22 00:00:00 2013 UTC |
| **不晚的有效性** | Oct 22 00:00:00 2028 UTC |
| **主题密钥标识符** | 3D： D3：50： A5： D6： D6：0F：0A： AD： AD： EE： F3：60：：65： D3： |
| **颁发机构密钥标识符** | keyID： b1：3e： c3：69：03：03： bf：47：01： d4：98：26：03：03：02：02：1：63：64：2b： c3 |
| **指纹（SHA-1）** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **指纹（SHA-256）** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="entrust-root-certification-authority"></a>**Entrust 根证书颁发机构**

| **主题** | CN = Entrust 根证书颁发机构<br>OU = "（c） 2006 Entrust，Inc."<br>OU = entrust/CPS 是通过引用并入的<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **序列号** | 45：6B：50：54 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 27 12:23:42 2006 年11月 |
| **不晚的有效性** | 27 12:53:42 2026 年11月 |
| **主题密钥标识符** | 68：90： E4：67： A4： A4： A6：6D：： C7：86：66：： A4：： |
| **颁发机构密钥标识符** | keyID：68：90： e4：67： a4： a4： a6：：6d： c7：86：66： a4：： |
| **指纹（SHA-1）** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **指纹（SHA-256）** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Entrust 根证书颁发机构-G2**

| **主题** | CN = Entrust 根证书颁发机构-G2<br>OU =&quot;（c） 2009 Entrust （inc.）仅供授权使用&quot;<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **序列号** | 4A：53：8C：28 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 07年 07 17:25:54 2009 UTC |
| **不晚的有效性** | Dec 07 17:55:54 2030 UTC |
| **主题密钥标识符** | 6a：72：26：7a： d0：： d0： e7： d0：1e： ef：7d：：12：12：51：6c：8d：：：90：12：66： ab |
| **指纹（SHA-1）** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **指纹（SHA-256）** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **Pin （SHA-256）** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **主题** | CN = Entrust 证书颁发机构（2048）<br>OU = （c） 1999 Entrust.net 限制<br>OU = entrust/CPS\_2048 合并。 by ref。（限制 s liab。）<br>O = Entrust |
| --- | --- |
| **序列号** | 38：63： DE： F8 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | Dec 24 17:50:51 1999 UTC |
| **不晚的有效性** | 07年 24 14:15:12 2029 UTC |
| **主题密钥标识符** | 55： e4：81： d1：11：80：11：80：80：80：9：9：9： d8：89： |
| **指纹（SHA-1）** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **指纹（SHA-256）** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **Pin （SHA-256）** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Entrust 证书颁发机构-L1C**

| **主题** | CN = Entrust 证书颁发机构-L1C<br>OU =&quot;（c） 2009 Entrust，inc.。&quot;<br>OU = entrust/rpa 是通过引用并入的<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = Entrust 证书颁发机构（2048）<br>OU = （c） 1999 Entrust.net 限制<br>OU = entrust/CPS\_2048 合并。 by ref. （限制 liab。）<br>O = Entrust |
| **序列号** | 4C：0E：8C：39 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 11 15:40:40 2011 年11月 |
| **不晚的有效性** | 11 02:51:17 2021 年11月 |
| **主题密钥标识符** | 1e： f1： ab：89：06：0f：06：06：06：06：（：01：1：01：7a：：14：： |
| **颁发机构密钥标识符** | keyid：55： e4：81： d1：11：11：11：11：80：9：9：89： b9：以下： |
| **指纹（SHA-1）** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **指纹（SHA-256）** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **Pin （SHA-256）** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **CRL Url** | http://crl.entrust.net/2048ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Entrust 证书颁发机构-L1E**

| **主题** | CN = Entrust 证书颁发机构-L1E<br>OU =&quot;（c） 2009 Entrust，inc.。&quot;<br>OU = entrust/rpa 是通过引用并入的<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = Entrust 证书颁发机构（2048）<br>OU = （c） 1999 Entrust.net 限制<br>OU = entrust/CPS\_2048 合并。 by ref. （限制 liab。）<br>O = Entrust |
| **序列号** | 4C：0E：的 C9：18 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha1RSA |
| **不早的有效期** | 11 15:40:40 2011 年11月 |
| **不晚的有效性** | 11 02:51:17 2021 年11月 |
| **主题密钥标识符** | 5B：41：8A： B2：？ C4：43：？ C4：43：43： C1： BD： BF： C8：54：41：9D：：： FF： |
| **颁发机构密钥标识符** | keyid：68：90： e4：67： a4： a4： a6：：6d： c7：86：66： a4：： |
| **指纹（SHA-1）** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **指纹（SHA-256）** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **CRL Url** | http://crl.entrust.net/rootca1.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Entrust 证书颁发机构-L1K**

| **主题** | CN = Entrust 证书颁发机构-L1K<br>OU =&quot;（c） 2012 Entrust （inc.）仅供授权使用&quot;<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = Entrust 根证书颁发机构-G2<br>OU =&quot;（c） 2009 Entrust （inc.）仅供授权使用&quot;<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| **序列号** | 0E： E9：4C： C3：：00：00：00：00：00：00：00：51： |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | Oct 05 19:13:56 2015 UTC |
| **不晚的有效性** | Dec 05 19:43:56 2030 UTC |
| **主题密钥标识符** | 82： a2：70：74： dd：3f： bc： bc：7f：：：7b： f7： cd-r：： a7：60： c6：0a：4c： bf |
| **颁发机构密钥标识符** | keyid：6a：72：26：7a： d0： e7： ef：：7d：：3b：69：51：66：6c：8d：：：12：66： ab |
| **指纹（SHA-1）** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **指纹（SHA-256）** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **Pin （SHA-256）** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **CRL Url** | http://crl.entrust.net/g2ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Entrust 证书颁发机构-L1M**

| **主题** | CN = Entrust 证书颁发机构-L1M，OU&quot;= （c） 2014 Entrust，inc.-仅供授权使用&quot;<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = Entrust 根证书颁发机构-G2<br>OU =&quot;（c） 2009 Entrust （inc.）仅供授权使用&quot;<br>OU = 请参阅 www.entrust.net/legal-terms<br>O =&quot;Entrust，inc.。&quot;<br>C = 美国 |
| **序列号** | 61： A1： E7： D2： D2：00：00：00：00：00：00：51： D3：66： A6 |
| **公用密钥长度** | RSA 2048 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | Dec 15 07:25:03 2014 UTC |
| **不晚的有效性** | Oct 15 08:55:03 2030 UTC |
| **主题密钥标识符** | C3： F7： D0： B5：2A：0D：：（AD：）：：91：21：39：39：54： DD： BC：89：70： C7：3A |
| **颁发机构密钥标识符** | keyid：6a：72：26：7a： d0： e7： ef：：7d：：3b：69：51：66：6c：8d：：：12：66： ab |
| **指纹（SHA-1）** | CC136695639065FAB47074D28C55314C66077E90 |
| **指纹（SHA-256）** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **CRL Url** | http://crl.entrust.net/g2ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **主题** | CN = Microsoft IT TLS CA 1<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 华盛顿<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = 巴尔的摩 CyberTrust 根<br>OU = CyberTrust<br>O = 巴尔的摩<br>C = IE |
| **序列号** | 08： B8：7A：50：1B：1B：9C： DA：2D：16：4D：3E：39：51： BF：55 |
| **公用密钥长度** | RSA 4096 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 5月 20 12:51:28 2016 UTC |
| **不晚的有效性** | 5月 20 12:51:28 2024 UTC |
| **主题密钥标识符** | 58：88： e6： d6： dc：9c：48：48：22：14：3e： ff：84：88： e8：：85： ff： fa：7d |
| **颁发机构密钥标识符** | keyid：9d：59：59：30：59：59：30：82：47：58：% cc： ac： fa：08：54：36：54： f0 |
| **指纹（SHA-1）** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **指纹（SHA-256）** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **Pin （SHA-256）** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **主题** | CN = Microsoft IT TLS CA 2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 华盛顿<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = 巴尔的摩 CyberTrust 根<br>OU = CyberTrust<br>O = 巴尔的摩<br>C = IE |
| **序列号** | 0F：2C：10： B8：7F：：：49：49：3E：：85：69： |
| **公用密钥长度** | RSA 4096 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 5月 20 12:51:57 2016 UTC |
| **不晚的有效性** | 5月 20 12:51:57 2024 UTC |
| **主题密钥标识符** | 91：9e：3b：44：6c：3d：57：57：9c：42：2a：34：34：34：4f：： cc：： |
| **颁发机构密钥标识符** | keyid：9d：59：59：30：59：59：30：82：47：58：% cc： ac： fa：08：54：36：54： f0 |
| **指纹（SHA-1）** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **指纹（SHA-256）** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **Pin （SHA-256）** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **主题** | CN = Microsoft IT TLS CA 4<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 华盛顿<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = 巴尔的摩 CyberTrust 根<br>OU = CyberTrust<br>O = 巴尔的摩<br>C = IE |
| **序列号** | 0B：6A： B3：3E： B1： B1： B1： F6： C4：60：92：6A： A8： CD： FE： B3 |
| **公用密钥长度** | RSA 4096 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 5月 20 12:52:38 2016 UTC |
| **不晚的有效性** | 5月 20 12:52:38 2024 UTC |
| **主题密钥标识符** | 7a：7b：8c： c1： e7：： c1：：： a0： ca：：： d4：6b：： fb： e1：33： c3：0f：1a： a2：9d |
| **颁发机构密钥标识符** | keyid：9d：59：59：30：59：59：30：82：47：58：% cc： ac： fa：08：54：36：54： f0 |
| **指纹（SHA-1）** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **指纹（SHA-256）** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **Pin （SHA-256）** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **主题** | CN = Microsoft IT TLS CA 5<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 华盛顿<br>C = 美国 |
| --- | --- |
| **颁发者** | CN = 巴尔的摩 CyberTrust 根<br>OU = CyberTrust<br>O = 巴尔的摩<br>C = IE |
| **序列号** | 08：88： CD：52：5F：19：19：19：19：24：44：4D：78：82： |
| **公用密钥长度** | RSA 4096 位（e 65537） |
| **签名算法** | sha256RSA |
| **不早的有效期** | 5月 20 12:53:03 2016 UTC |
| **不晚的有效性** | 5月 20 12:53:03 2024 UTC |
| **主题密钥标识符** | 2008年8： fe：25：9f：74：（ea）：8e： c2： bc： bb：：：5f：38： |
| **颁发机构密钥标识符** | keyid：9d：59：59：30：59：59：30：82：47：58：% cc： ac： fa：08：54：36：54： f0 |
| **指纹（SHA-1）** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **指纹（SHA-256）** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **Pin （SHA-256）** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |
