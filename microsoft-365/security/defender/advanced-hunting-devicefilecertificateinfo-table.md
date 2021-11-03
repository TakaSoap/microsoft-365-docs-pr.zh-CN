---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 数字签名， 证书， 文件签名， DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 362cacee7734653d6ca0f868e565a38b806fd31c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664469"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

高级 `DeviceFileCertificateInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关文件签名证书的信息。 此表使用定期对终结点上的文件执行的证书验证活动获取的数据。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `IsSigned` | boolean | 指示文件是否已签名 |
| `SignatureType` | string | 指示签名信息是作为嵌入内容读取到文件本身中，还是从外部目录文件中读取 |
| `Signer` | string | 有关文件签名者的信息 |
| `SignerHash` | string | 标识签名者的唯一哈希值 |
| `Issuer` | string | 有关 CA 证书颁发机构 (的信息)  |
| `IssuerHash` | string | 标识证书颁发机构的唯一哈希值 (CA)  |
| `CertificateSerialNumber` | string | CA 证书颁发机构唯一的证书 (标识符)  |
| `CrlDistributionPointUrls` | string |  JSON 数组，列出包含证书的网络共享 URL 和 CCL (吊销)  |
| `CertificateCreationTime` | datetime | 创建证书的日期和时间 |
| `CertificateExpirationTime` | datetime | 证书设置为过期的日期和时间 |
| `CertificateCountersignatureTime` | datetime | 对证书进行反签名的日期和时间 |
| `IsTrusted` | boolean | 根据 WinVerifyTrust 函数的结果指示文件是否受信任，该函数将检查未知根证书信息、无效签名、吊销的证书和其他可怀疑的属性 |
| `IsRootSignerMicrosoft` | boolean | 指示根证书的签名者是否是 Microsoft |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。 | 

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
