---
title: 高级搜寻中的 FileProfile () 函数Microsoft 365 Defender
description: 了解如何使用 FileProfile () 丰富有关高级搜寻查询结果中文件的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
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
ms.openlocfilehash: c7ad9678f797fd3e8df34b40fe39fea5672e13d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704473"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

函数 `FileProfile()` 是高级搜寻中的扩充 [函数](advanced-hunting-overview.md) ，用于将以下数据添加到查询找到的文件。

| 列 | 数据类型 | 说明 |
|------------|---------------|-------------|
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `SHA256` | string | 已应用录制操作的文件的 SHA-256 |
| `MD5` | string | 已记录操作所应用到的文件的 MD5 哈希 |
| `FileSize` | int | 文件大小（以字节为单位） |
| `GlobalPrevalence` | int | Microsoft 全局观察到的实体实例数 |
| `GlobalFirstSeen` | datetime | Microsoft 全局首次观测到实体的日期和时间 |
| `GlobalLastSeen` | datetime | Microsoft 全局上次观测到实体的日期和时间 |
| `Signer` | string | 有关文件签名者的信息 |
| `Issuer` | string | 有关 CA 证书颁发机构 (的信息)  |
| `SignerHash` | string | 标识签名者的唯一哈希值 |
| `IsCertificateValid` | boolean | 用于对文件进行签名的证书是否有效 |
| `IsRootSignerMicrosoft` | boolean | 指示根证书的签名者是否是 Microsoft |
| `SignatureState` | string | 文件签名的状态：SignedValid - 使用有效签名对文件进行签名，SignedInvalid - 文件已签名，但证书无效，未签名 - 文件未签名，未知 - 无法检索有关文件的信息
| `IsExecutable` | boolean | 文件是否是可移植可执行文件 (PE) 文件 |
| `ThreatName` | string | 找到的任何恶意软件或其他威胁的检测名称 |
| `Publisher` | string | 发布该文件的组织的名称 |
| `SoftwareName` | string | 软件产品的名称 |

## <a name="syntax"></a>语法

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>参数

- **x**—要使用的文件 ID 列 `SHA1` `SHA256` ：、、 `InitiatingProcessSHA1` 或 `InitiatingProcessSHA256` ;函数使用 `SHA1` （如果未指定）
- **y**— 限制要扩充的记录数，1-1000;函数使用 100（如果未指定）


>[!TIP]
> 扩充函数仅在可用时显示补充信息。 信息的可用性各不相同，具体取决于许多因素。 确保在查询或创建自定义检测中使用 FileProfile () 时考虑这一点。 为了获得最佳结果，我们建议将 FileProfile () 函数与 SHA1 一同使用。

## <a name="examples"></a>示例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Project SHA1 列并扩充它

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>丰富前 500 条记录并列出低程度文件

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [获取更多查询示例](advanced-hunting-shared-queries.md)
