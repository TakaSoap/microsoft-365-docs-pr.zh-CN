---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 数字签名， 证书， 文件签名， DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055488"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高级 `DeviceFileCertificateInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关文件签名证书的信息。 此表使用定期对终结点上的文件执行的证书验证活动获取的数据。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `IsSigned` | boolean | 指示文件是否已签名 |
| `SignatureType` | string | 指示签名信息是作为嵌入内容读取到文件本身中，还是从外部目录文件中读取 |
| `Signer` | string | 有关文件签名者的信息 |
| `SignerHash` | string | 标识签名者的唯一哈希值 |
| `Issuer` | string | 有关 CA 证书颁发机构 (的信息)  |
| `IssuerHash` | string | 标识证书颁发机构的唯一哈希值 (CA)  |
| `CertificateSerialNumber` | string | 证书颁发机构或 CA 证书颁发机构唯一的 (标识符)  |
| `CrlDistributionPointUrls` | string |  JSON 数组，列出包含证书的网络共享 URL 和 CCL 或证书吊销 (列表)  |
| `CertificateCreationTime` | datetime | 创建证书的日期和时间 |
| `CertificateExpirationTime` | datetime | 证书设置为过期的日期和时间 |
| `CertificateCountersignatureTime` | datetime | 对证书进行反签名的日期和时间 |
| `IsTrusted` | boolean | 根据 WinVerifyTrust 函数的结果指示文件是否受信任，该函数将检查未知根证书信息、无效签名、吊销的证书和其他可怀疑的属性 |
| `IsRootSignerMicrosoft` | boolean | 指示根证书的签名者是否是 Microsoft |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。 |


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
