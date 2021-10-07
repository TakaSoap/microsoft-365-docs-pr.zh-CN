---
title: Microsoft 365加密链 - DOD 和 GCC High
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/16/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 查看 DOD 和 GCC High root 证书的完整列表， (CA) Microsoft 365。
ms.openlocfilehash: 5db850f59223238bdd9e749f442caf9eab93ea29
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197601"
---
# <a name="microsoft-365-encryption-chains---dod-and-gcc-high"></a>Microsoft 365加密链 - DOD 和 GCC High

Microsoft 365利用许多不同的证书提供程序。 下面介绍了 **DOD** 和 Microsoft 365高客户在访问 Microsoft 365 时可能会遇到的已知根证书的完整GCC。 有关可能需要在您自己的基础结构中安装的证书的信息，请参阅 Plan for [third-party SSL certificates for Microsoft 365](../enterprise/plan-for-third-party-ssl-certificates.md)。

以下证书信息适用于所有 **DOD 和 GCC高客户**。

Last updated： **10/16/2020**

> [!NOTE]
> 有关适用于全球客户的 **证书信息，** 请参阅Microsoft 365 [加密链](encryption-office-365-certificate-chains.md)。

| **证书类型** | **P7b 下载** | **CRL 终结点** | **OCSP 终结点** |
| --- | --- | --- | --- | --- |
| 公共信任根证书和中间证书 | [Microsoft 365P7B (ITAR 证书) ](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/m365_chain_certs_itar20201012.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

展开下面的根部分和中间部分以查看有关证书提供程序的其他详细信息。

## <a name="microsoft-365-certificate-details"></a>**Microsoft 365证书详细信息**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **主题** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| --- | --- |
| **序列号** | 02：00：00：B9 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 5 月 12 日 18：46：00 2000 UTC |
| **Validity Not After** | 5 月 12 日 23：59：00 2025 UTC |
| **主题密钥标识符** | e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **SHA-256 (指纹)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **固定 (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o= |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert 云服务 CA-1**

| **主题** | CN=DigiCert 云服务 CA-1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| **序列号** | 01：9E：C1：C6：BD：3F：59：7B：B2：0C：33：38：E5：51：D8：77 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 04 年 8 月 12：00：00 2015 UTC |
| **Validity Not After** | 04 年 8 月 12：00：00 2030 UTC |
| **主题密钥标识符** | dd：51：d0：a2：31：73：a9：73：ae：8f：b4：01：7e：5d：8c：57：cb：9f：f0：f7 |
| **颁发机构密钥标识符** | keyid：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **SHA-256 (指纹)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **固定 (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE= |
| **CRL URL** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert 云服务 CA-1**

| **主题** | CN=DigiCert 云服务 CA-1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root CA， OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 0F：17：1A：48：C6：F2：23：80：92：18：CD：2E：D6：DD：C0：E8 |
| **公钥长度** | RSA 2048 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2020 年 9 月 24 日，星期四，下午 5：00 |
| **有效期直到** | 2030 年 9 月 24 日，星期二，下午 4：59 |
| **主题密钥标识符** | DD51D0A23173A973AE8FB4017E5D8C57CB9FF0F7 |
| **颁发机构密钥标识符** | KeyID：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | B3F6B64A07BB9611F47174407841F564FB991F29 |
| **SHA-256 (指纹)** | 5F88694615E4C61686E106B84C3338C6720C535F60D36F61282ED15E1977DD44 |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**DigiCert 全局根 CA**

| **主题** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **序列号** | 08：3B：E0：56：90：42：46：B1：A1：75：6A：C9：59：91：C7：4A |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 11 月 10 日 00：00：00 2006 UTC |
| **Validity Not After** | 11 月 10 日 00：00：00 2031 UTC |
| **主题密钥标识符** | 03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **颁发机构密钥标识符** | keyid：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **SHA-256 (指纹)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **固定 (SHA-256)** | r/mIkG3eEpVdm+u/ko/cwxzOMo1bk4TyHIlByibiA5E= |

### <a name="digicert-global-root-g2"></a>**DigiCert 全局根 G2**

| **主题** | CN=DigiCert 全局根 G2<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root G2，OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 03：3A：F1：E6：A7：11：A9：A0：BB：28：64：B1：1D：09：FA：E5 |
| **公钥长度** | RSA 2048 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2013 年 8 月 1 日，星期四，上午 5：00 |
| **有效期直到** | 2038 年 1 月 15 日，星期五 4：00 AM |
| **主题密钥标识符** | 4E2254201895E6E36EE60FFAFAB912ED06178F39 |
| **颁发机构密钥标识符** | KeyID：4e：22：54：20：18：95：e6：e3：6e：e6：0f：fa：fa：b9：12：ed：06：17：8f：39 |
| **SHA-1 (指纹)** | DF3C24F9BFD666761B268073FE06D1CC8D4F82A4 |
| **SHA-256 (指纹)** | CB3CCBB76031E5E0138F8DD39A23F9DE47FFC35E43C1144CEA27D46A5AB1CB5F |

### <a name="digicert-high-assurance-ev-root-ca"></a>**DigiCert 高保证 EV 根 CA**

| **主题** | CN=DigiCert High Assurance EV Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **序列号** | 02：AC：5C：26：6A：0B：40：9B：8F：0B：79：F2：AE：46：25：77 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 11 月 10 日 00：00：00 2006 UTC |
| **Validity Not After** | 11 月 10 日 00：00：00 2031 UTC |
| **主题密钥标识符** | b1：3e：c3：69：03：f8：bf：47：01：d4：98：26：1a：08：02：ef：63：64：2b：c3 |
| **颁发机构密钥标识符** | keyid：b1：3e：c3：69：03：f8：bf：47：01：d4：98：26：1a：08：02：ef：63：64：2b：c3 |
| **SHA-1 (指纹)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **SHA-256 (指纹)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **固定 (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18= |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**DigiCert SHA2 扩展验证服务器 CA**

| **主题** | CN=DigiCert SHA2 扩展验证服务器 CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **序列号** | 0C：79：A9：44：B0：8C：11：95：20：92：61：5F：E2：6B：1D：83 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | Oct 22 00：00：00 2013 UTC |
| **Validity Not After** | Oct 22 00：00：00 2028 UTC |
| **主题密钥标识符** | 3D：D3：50：A5：D6：A0：AD：企业版：F3：4A：60：0A：65：D3：21：D4：F8：F8：D6：0F |
| **颁发机构密钥标识符** | keyID：b1：3e：c3：69：03：f8：bf：47：01：d4：98：26：1a：08：02：ef：63：64：2b：c3 |
| **SHA-1 (指纹)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **SHA-256 (指纹)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="digicert-sha2-secure-server-ca"></a>**DigiCert SHA2 安全服务器 CA**

| **主题** | CN=DigiCert SHA2 Secure Server CA<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root CA， OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 01：FD：A3：EB：6E：CA：75：C8：88：43：8B：72：4B：CF：BC：91 |
| **公钥长度** | RSA 2048 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2013 年 3 月 8 日，星期五 4：00 AM |
| **有效期直到** | 2023 年 3 月 8 日，星期三 4：00 AM |
| **主题密钥标识符** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **颁发机构密钥标识符** | KeyID：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **SHA-256 (指纹)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**DigiCert SHA2 安全服务器 CA**

| **主题** | CN=DigiCert SHA2 Secure Server CA<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root CA， OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 02：74：2E：AA：17：CA：8E：21：C7：17：BB：1F：FC：FD：0C：A0 |
| **公钥长度** | RSA 2048 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2020 年 9 月 22 日，星期二，下午 5：00 |
| **有效期直到** | 2030 年 9 月 22 日，星期日 4：59 PM |
| **主题密钥标识符** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **颁发机构密钥标识符** | KeyID：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | 626D44E704D1CEABE3BF0D53397464AC8080142C |
| **SHA-256 (指纹)** | C1AD7778796D20BCA65C889A2655021156528BB62FF5FA43E1B8E5A83E3D2EAA |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="digicert-tls-rsa-sha256-2020-ca1"></a>**DigiCert TLS RSA SHA256 2020 CA1**

| **主题** | CN=DigiCert TLS RSA SHA256 2020 CA1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root CA， OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 0A：35：08：D5：5C：29：2B：01：7D：F8：AD：65：C0：0F：F7：E4 |
| **公钥长度** | RSA 2048 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2020 年 9 月 23 日，星期三 5：00 PM |
| **有效期直到** | 2030 年 9 月 23 日，星期一，下午 4：59 |
| **主题密钥标识符** | B76BA2EAA8AA848C79EAB4DA0F98B2C59576B9F4 |
| **颁发机构密钥标识符** | KeyID：03：de：50：35：56：d1：4c：bb：66：f0：a3：e2：1b：1b：c3：97：b2：3d：d1：55 |
| **SHA-1 (指纹)** | 6938FD4D98BAB03FAADB97B34396831E3780AEA1 |
| **SHA-256 (指纹)** | 25768713D3B459F9382D2A594F85F34709FD2A8930731542A4146FFB246BEC69 |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="entrust-root-certification-authority"></a>**委托根证书颁发机构**

| **主题** | CN=进行根证书颁发机构<br>OU=" (c) 2006 Entrust， Inc."<br>OU=www.entrust.net/CPS 通过参考纳入<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **序列号** | 45：6B：50：54 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 11 月 27 日 12：23：42 2006 UTC |
| **Validity Not After** | 11 月 27 日 12：53：42 2026 UTC |
| **主题密钥标识符** | 68：90：E4：67：A4：A6：53：80：C7：86：66：A4：F1：F7：4B：43：FB：84：BD：6D |
| **颁发机构密钥标识符** | keyID：68：90：e4：67：a4：a6：53：80：c7：86：66：a4：f1：f7：4b：43：fb：84：bd：6d |
| **SHA-1 (指纹)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **SHA-256 (指纹)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**代理根证书颁发机构 - G2**

| **主题** | CN=进行根证书颁发机构 - G2<br>OU= &quot; (c) 2009 Authorized， Inc. - 仅授权使用&quot;<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **序列号** | 4A：53：8C：28 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 07 年 7 月 17：25：54 2009 UTC |
| **Validity Not After** | 07.12.17：55：54 2030 UTC |
| **主题密钥标识符** | 6a：72：26：7a：d0：1e：ef：7d：e7：3b：69：51：d4：6c：8d：9f：90：12：66：ab |
| **SHA-1 (指纹)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **SHA-256 (指纹)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **固定 (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U= |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **主题** | CN=Entrust.net Certification Authority (2048) <br>OU= (c) 1999 Entrust.net Limited<br>OU=www.entrust.net/CPS \_ 2048 incorp. by ref. (limit s liab.) <br>O=Entrust.net |
| --- | --- |
| **序列号** | 38：63：DE：F8 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 12 月 24 日 UTC 17：50：51 |
| **Validity Not After** | UTC 时间 2029 年 7 月 24 日 14：15：12 |
| **主题密钥标识符** | 55：e4：81：d1：11：80：be：d8：89：b9：08：a3：31：f9：a1：24：09：16：b9：70 |
| **SHA-1 (指纹)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **SHA-256 (指纹)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **固定 (SHA-256)** | 为改进系统性能，可存储到的行数 |

### <a name="entrust-certification-authority---l1c"></a>**证书颁发机构 - L1C**

| **主题** | CN=Entrust Certification Authority - L1C<br>OU= &quot; (c) 2009 Entrust, Inc.&quot;<br>OU=www.entrust.net/rpa 通过参考纳入<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **颁发者** | CN=Entrust.net Certification Authority (2048) <br>OU= (c) 1999 Entrust.net Limited<br>OU=www.entrust.net/CPS \_ 2048 incorp. by ref. (限制 liab.) <br>O=Entrust.net |
| **序列号** | 4C：0E：8C：39 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 2011 年 11 月 11 日 UTC 15：40：40 |
| **Validity Not After** | 111 02：51：17 2021 UTC |
| **主题密钥标识符** | 1e：f1：ab：89：06：f8：49：0f：01：33：77：ee：14：7a：ee：19：7c：93：28：4d |
| **颁发机构密钥标识符** | keyid：55：e4：81：d1：11：80：be：d8：89：b9：08：a3：31：f9：a1：24：09：16：b9：70 |
| **SHA-1 (指纹)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **SHA-256 (指纹)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **固定 (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS+Ui0bQ94= |
| **CRL URL** | http://crl.entrust.net/2048ca.crl |
| **OCSP URL** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**证书颁发机构 - L1E**

| **主题** | CN=Entrust Certification Authority - L1E<br>OU= &quot; (c) 2009 Entrust, Inc.&quot;<br>OU=www.entrust.net/rpa 通过参考纳入<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **颁发者** | CN=Entrust.net Certification Authority (2048) <br>OU= (c) 1999 Entrust.net Limited<br>OU=www.entrust.net/CPS \_ 2048 incorp. by ref. (liab.) <br>O=Entrust.net |
| **序列号** | 4C：0E：C9：18 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha1RSA |
| **Validity Not Before** | 2011 年 11 月 11 日 UTC 15：40：40 |
| **Validity Not After** | 111 02：51：17 2021 UTC |
| **主题密钥标识符** | 5B：41：8A：B2：C4：43：C1：BD：BF：C8：54：41：55：9D：E0：96：AD：FF：B9：A1 |
| **颁发机构密钥标识符** | keyid：68：90：e4：67：a4：a6：53：80：c7：86：66：a4：f1：f7：4b：43：fb：84：bd：6d |
| **SHA-1 (指纹)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **SHA-256 (指纹)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **CRL URL** | http://crl.entrust.net/rootca1.crl |
| **OCSP URL** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**代理证书颁发机构 - L1K**

| **主题** | CN=Entrust Certification Authority - L1K<br>OU= &quot; (c) 2012 Authorized， Inc. - 仅授权使用&quot;<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **颁发者** | CN=进行根证书颁发机构 - G2<br>OU= &quot; (c) 2009 Authorized， Inc. - 仅授权使用&quot;<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| **序列号** | 0E：E9：4C：C3：00：00：00：00：51：D3：77：85 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | Oct 05 19：13：56 2015 UTC |
| **Validity Not After** | 05 12 月 5 日 19：43：56 2030 UTC |
| **主题密钥标识符** | 82：a2：70：74：dd：bc：53：3f：cf：7b：d4：f7：cd：7f：a7：60：c6：0a：4c：bf |
| **颁发机构密钥标识符** | keyid：6a：72：26：7a：d0：1e：ef：7d：e7：3b：69：51：d4：6c：8d：9f：90：12：66：ab |
| **SHA-1 (指纹)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **SHA-256 (指纹)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **固定 (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc= |
| **CRL URL** | http://crl.entrust.net/g2ca.crl |
| **OCSP URL** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**代理证书颁发机构 - L1M**

| **主题** | CN=Entrust Certification Authority - L1M， OU= &quot; (c) 2014 Authorized， Inc. - 仅授权使用&quot;<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **颁发者** | CN=进行根证书颁发机构 - G2<br>OU= &quot; (c) 2009 Authorized， Inc. - 仅授权使用&quot;<br>OU=请参阅 www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| **序列号** | 61：A1：E7：D2：00：00：00：00：51：D3：66：A6 |
| **公钥长度** | RSA 2048 位 (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2014 年 12 月 15 日 07：25：03 UTC |
| **Validity Not After** | Oct 15 08：55：03 2030 UTC |
| **主题密钥标识符** | C3：F7：D0：B5：2A：30：AD：AF：0D：91：21：70：39：54：DD：BC：89：70：C7：3A |
| **颁发机构密钥标识符** | keyid：6a：72：26：7a：d0：1e：ef：7d：e7：3b：69：51：d4：6c：8d：9f：90：12：66：ab |
| **SHA-1 (指纹)** | CC136695639065FAB47074D28C55314C66077E90 |
| **SHA-256 (指纹)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **CRL URL** | http://crl.entrust.net/g2ca.crl |
| **OCSP URL** | http://ocsp.entrust.net |

### <a name="microsoft-azure-tls-issuing-ca-01"></a>**Microsoft AzureTLS 颁发 CA 01**

| **主题** | CN=Microsoft Azure TLS 颁发 CA 01<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root G2，OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 0A：AF：A6：C5：CA：63：C4：51：41：EA：3B：E1：F7：C7：53：17 |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha384RSA |
| **Validity Not Before** | 2020 年 7 月 29 日，星期三 5：30 AM |
| **有效期直到** | 2024 年 6 月 27 日，星期四，下午 4：59 |
| **主题密钥标识符** | 0F205DD7A15795DB92CF2BD0C7C27704CE728076 |
| **颁发机构密钥标识符** | KeyID：4e：22：54：20：18：95：e6：e3：6e：e6：0f：fa：fa：b9：12：ed：06：17：8f：39 |
| **SHA-1 (指纹)** | 2F2877C5D778C31E0F29C7E371DF5471BD673173 |
| **SHA-256 (指纹)** | 24C7299864E0A2A6964F551C0E8DF2461532FA8C48E4DBBB6080716691F190E5 |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-02"></a>**Microsoft AzureTLS 颁发 CA 02**

| **主题** | CN=Microsoft Azure TLS 颁发 CA 02<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root G2，OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 0C：6A：E9：7C：CE：D5：99：83：86：90：A0：0A：9E：A5：32：14 |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha384RSA |
| **Validity Not Before** | 2020 年 7 月 29 日，星期三 5：30 AM |
| **有效期直到** | 2024 年 6 月 27 日，星期四，下午 4：59 |
| **主题密钥标识符** | 00AB91FC216226979AA8791B61419060A96267FD |
| **颁发机构密钥标识符** | KeyID：4e：22：54：20：18：95：e6：e3：6e：e6：0f：fa：fa：b9：12：ed：06：17：8f：39 |
| **SHA-1 (指纹)** | E7EEA674CA718E3BEFD90858E09F8372AD0AE2AA |
| **SHA-256 (指纹)** | 15A98761EBE011554DA3A46D206B0812CB2EB69AE87AAA11A6DD4CB84ED5142A |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-05"></a>**Microsoft AzureTLS 颁发 CA 05**

| **主题** | CN=Microsoft Azure TLS 颁发 CA 05<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root G2，OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 0D：7B：ED：E9：7D：82：09：96：7A：52：63：1B：8B：DD：18：BD |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha384RSA |
| **Validity Not Before** | 2020 年 7 月 29 日，星期三 5：30 AM |
| **有效期直到** | 2024 年 6 月 27 日，星期四，下午 4：59 |
| **主题密钥标识符** | C7B29C7F1CE3B85AEFE9681AA85D94C126526A68 |
| **颁发机构密钥标识符** | KeyID：4e：22：54：20：18：95：e6：e3：6e：e6：0f：fa：fa：b9：12：ed：06：17：8f：39 |
| **SHA-1 (指纹)** | 6C3AF02E7F269AA73AFD0EFF2A88A4A1F04ED1E5 |
| **SHA-256 (指纹)** | D6831BA43607F5AC19778D627531562AF55145F191CAB5EFA0E0005442B302 |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-06"></a>**Microsoft AzureTLS 颁发 CA 06**

| **主题** | CN=Microsoft Azure TLS 颁发 CA 06<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=DigiCert Global Root G2，OU=www.digicert.com， O=DigiCert Inc， C=US |
| **序列号** | 02：E7：91：71：FB：80：21：E9：3F：E2：D9：83：83：4C：50：C0 |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha384RSA |
| **Validity Not Before** | 2020 年 7 月 29 日，星期三 5：30 AM |
| **有效期直到** | 2024 年 6 月 27 日，星期四，下午 4：59 |
| **主题密钥标识符** | D5C1673AC2A39DF477525B59123829E65568BBA5 |
| **颁发机构密钥标识符** | KeyID：4e：22：54：20：18：95：e6：e3：6e：e6：0f：fa：fa：b9：12：ed：06：17：8f：39 |
| **SHA-1 (指纹)** | 30E01761AB97E59A06B41EF20AF6F2DE7EF4F7B0 |
| **SHA-256 (指纹)** | 48FF8B494668C752304B48BFE818758987DEF6582E5F09B921F4B60BB3D6A8DD |
| **CRL URL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **主题** | CN=Microsoft IT TLS CA 1<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **序列号** | 08：B8：7A：50：1B：BE：9C：DA：2D：16：4D：3E：39：51：BF：55 |
| **公钥长度** | RSA 4096 bits (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2016 年 5 月 20 日 12：51：28 UTC |
| **Validity Not After** | 2024 年 5 月 20 日 12：51：28 UTC |
| **主题密钥标识符** | 58：88：9f：d6：dc：9c：48：22：b7：14：3e：ff：84：88：e8：e6：85：ff：fa：7d |
| **颁发机构密钥标识符** | keyid：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **SHA-256 (指纹)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **固定 (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd+J3+b2LiybIw= |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **主题** | CN=Microsoft IT TLS CA 2<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **序列号** | 0F：2C：10：C9：5B：06：C0：93：7F：B8：D4：49：F8：3E：85：69 |
| **公钥长度** | RSA 4096 bits (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2016 年 5 月 20 日 12：51：57 UTC |
| **Validity Not After** | 2024 年 5 月 20 日 12：51：57 UTC |
| **主题密钥标识符** | 91：9e：3b：44：6c：3d：57：9c：42：77：2a：34：d7：4f：d1：cc：4a：97：2c：da |
| **颁发机构密钥标识符** | keyid：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **SHA-256 (指纹)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **固定 (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H+TT7s= |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **主题** | CN=Microsoft IT TLS CA 4<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **序列号** | 0B：6A：B3：B0：3E：B1：A9：F6：C4：60：92：6A：A8：CD：FE：B3 |
| **公钥长度** | RSA 4096 bits (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2016 年 5 月 20 日 12：52：38 UTC |
| **Validity Not After** | 2024 年 5 月 20 日 12：52：38 UTC |
| **主题密钥标识符** | 7a：7b：8c：c1：cf：e7：a0：ca：1c：d4：6b：fa：fb：e1：33：c3：0f：1a：a2：9d |
| **颁发机构密钥标识符** | keyid：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **SHA-256 (指纹)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **固定 (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE++mV7FgIcbn4WhMz1I2k= |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **主题** | CN=Microsoft IT TLS CA 5<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **序列号** | 08：88：CD：52：5F：19：24：44：4D：14：A5：82：91：DE：B9：52 |
| **公钥长度** | RSA 4096 bits (e 65537)  |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2016 年 5 月 20 日 12：53：03 UTC |
| **Validity Not After** | 2024 年 5 月 20 日 12：53：03 UTC |
| **主题密钥标识符** | 08：fe：25：9f：74：ea：87：04：c2：bc：bb：8e：a8：38：5f：33：c6：d1：6c：65 |
| **颁发机构密钥标识符** | keyid：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **SHA-256 (指纹)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **固定 (SHA-256)** | RCbqB+W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc= |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-01"></a>**Microsoft RSA TLS CA 01**

| **主题** | CN=Microsoft RSA TLS CA 01<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root， OU=CyberTrust， O=Baltimore， C=IE |
| **序列号** | 0F：14：96：5F：20：20：69：99：4F：D5：C7：AC：78：89：41：E2 |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2020 年 7 月 21 日，星期二，下午 4：00 |
| **有效期直到** | 2024 年 10 月 8 日，星期二，上午 12：00 |
| **主题密钥标识符** | B5760C3011CEC792424D4CC75C2CC8A90CE80B64 |
| **颁发机构密钥标识符** | KeyID：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | 703D7A8F0EBF55AAA59F98EAF4A206004EB2516A |
| **SHA-256 (指纹)** | 04EEEA8E50B4775B3C24797262917EE50002EC4C75B56CDF3EE1C18CFCA5BA52 |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-02"></a>**Microsoft RSA TLS CA 02**

| **主题** | CN=Microsoft RSA TLS CA 02<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **颁发者** | CN=Baltimore CyberTrust Root， OU=CyberTrust， O=Baltimore， C=IE |
| **序列号** | 0F：A7：47：22：C5：3D：88：C8：0F：58：9E：FB：1F：9D：4A：3A |
| **公钥长度** | RSA 4096 位 |
| **签名算法** | sha256RSA |
| **Validity Not Before** | 2020 年 7 月 21 日，星期二，下午 4：00 |
| **有效期直到** | 2024 年 10 月 8 日，星期二，上午 12：00 |
| **主题密钥标识符** | FF2F7FE106F438F32DED258D98C2FE0EF66CFCFA |
| **颁发机构密钥标识符** | KeyID：e5：9d：59：30：82：47：58：cc：ac：fa：08：54：36：86：7b：3a：b5：04：4d：f0 |
| **SHA-1 (指纹)** | B0C2D2D13CDD56CDAA6AB6E2C04440BE4A429C75 |
| **SHA-256 (指纹)** | 05E4005DB0C382F3BD66B47729E9011577601BF6F7B287E9A52CED710D258346 |
| **CRL URL** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URL** | http://ocsp.digicert.com |