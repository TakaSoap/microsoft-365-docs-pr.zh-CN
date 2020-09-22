---
title: 'Microsoft 威胁防护中的 FileProfile ( # A1 函数在高级搜寻中'
description: '了解如何使用 FileProfile ( # A1 丰富有关高级搜索查询结果中的文件的信息'
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、FileProfile、文件配置文件、函数、扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3fc563c762e7cd00888665b63e66159e4d3d9612
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196973"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

`FileProfile()`函数是[高级](advanced-hunting-overview.md)搜索中的一个扩充函数，可将以下数据添加到查询找到的文件中。

| 列 | 数据类型 | 说明 |
|------------|-------------|-------------|
| SHA1 | string | 录制操作所应用到的文件的 SHA-1 |
| SHA256 | string | 将所录制操作应用于的文件的 SHA-256 |
| MD5 | string | 将录制的操作应用于的文件的 MD5 哈希值 |
| FileSize | int | 文件大小（以字节为单位） |
| GlobalPrevalence | int | 由 Microsoft 全局监视的实体的实例数 |
| GlobalFirstSeen | datetime | Microsoft 全球首次观测实体的日期和时间 |
| GlobalLastSeen | datetime | 上次 Microsoft 全局观察实体的日期和时间 |
| 签字 | string | 有关文件签名者的信息 |
| 颁发者 | string | 有关颁发证书颁发机构 (CA) 的信息 |
| SignerHash | string | 标识签名者的唯一哈希值 |
| IsCertificateValid | boolean | 用于对文件进行签名的证书是否有效 |
| IsRootSignerMicrosoft | boolean | 指示根证书的签名者是否为 Microsoft |
| IsExecutable | boolean | 文件是否为可移植可执行文件 (PE) 文件 |
| ThreatName | string | 发现的任何恶意软件或其他威胁的检测名称 |
| Publisher | string | 发布文件的组织的名称 |
| SoftwareName | string | 软件产品的名称 |

## <a name="syntax"></a>语法

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>参数

- **x** —要使用的文件 ID 列 `SHA1` ： `SHA256` 、 `InitiatingProcessSHA1` 或 `InitiatingProcessSHA256` ; `SHA1` 如果未指定，则使用函数
- **y** -限制为要丰富的记录数，1-1000;函数使用100（如果未指定）

## <a name="examples"></a>示例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>仅投影 SHA1 列并浓缩它

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>浓缩前500条记录并列出低传播文件

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
