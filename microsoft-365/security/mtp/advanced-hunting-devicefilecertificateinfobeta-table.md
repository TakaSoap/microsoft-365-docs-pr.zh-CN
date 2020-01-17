---
title: 高级搜寻架构中的 DeviceFileCertificateInfoBeta 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfoBeta 表中的文件签名信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、数字签名、证书、文件签名DeviceFileCertificateInfoBeta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d5769088f3904bf62d2889f35f236c9410628db
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230200"
---
# <a name="devicefilecertificateinfobeta"></a>DeviceFileCertificateInfoBeta

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceFileCertificateInfoBeta` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关文件签名证书的信息。 此表使用从证书验证活动获取的数据，这些数据定期对终结点上的文件执行。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `IsSigned` | boolean | 指示文件是否已签名 |
| `SignatureType` | string | 指示是否以嵌入方式读取签名信息 | 文件本身的内容或从外部目录文件读取 |
| `Signer` | string | 有关文件签名者的信息 |
| `SignerHash` | string | 标识签名者的唯一哈希值 |
| `Issuer` | string | 有关颁发证书颁发机构（CA）的信息 |
| `IssuerHash` | string | 标识颁发证书颁发机构（CA）的唯一哈希值 |
| `CertificateSerialNumber` | string | 证书对于颁发证书颁发机构（CA）的唯一标识符 |
| `CrlDistributionPointUrls` | string |  JSON 数组，列出包含证书和证书吊销列表（Crl）的网络共享的 Url |
| `CertificateCreationTime` | datetime | 证书的创建日期和时间 |
| `CertificateExpirationTime` | datetime | 将证书设置为过期的日期和时间 |
| `CertificateCountersignatureTime` | datetime | 副署证书的日期和时间 |
| `IsTrusted` | boolean | 指示文件是否受 WinVerifyTrust 函数的结果（检查未知的根证书信息、无效签名、吊销的证书以及其他可疑属性）的信任。 |
| `IsRootSignerMicrosoft` | boolean | 指示根证书的签名者是否为 Microsoft |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用。 | 

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)