---
title: FileProfile () Microsoft Defender for Endpoint 高级搜寻中的函数
description: 了解如何使用 FileProfile () 丰富有关高级搜寻查询结果中的文件的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， Microsoft Defender ATP， Microsoft Defender for Endpoint， Windows Defender， Windows Defender ATP， Windows Defender 高级威胁防护， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056385"
---
# <a name="fileprofile"></a>FileProfile()

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

函数 `FileProfile()` 是高级搜寻中的扩充 [函数](advanced-hunting-overview.md) ，用于将以下数据添加到查询找到的文件。

Column | 数据类型 | 说明
-|-|-
SHA1 | string | 录制操作所应用到的文件的 SHA-1
SHA256 | string | 已记录操作应用于的文件的 SHA-256
MD5 | string | 已记录操作所应用到的文件的 MD5 哈希
FileSize | int | 文件大小（以字节为单位）
GlobalPrevalence | int | Microsoft 全局观察到的实体实例数
GlobalFirstSeen | datetime | Microsoft 全局首次观测到实体的日期和时间
GlobalLastSeen | datetime | Microsoft 全局上次观测到实体的日期和时间
签名者 | string | 有关文件签名者的信息
颁发者 | string | 有关 CA 证书颁发机构 (的信息) 
SignerHash | string | 标识签名者的唯一哈希值
IsCertificateValid | boolean | 用于对文件进行签名的证书是否有效
IsRootSignerMicrosoft | boolean | 指示根证书的签名者是否是 Microsoft
IsExecutable | boolean | 文件是否是可移植可执行 (PE) 文件
ThreatName | string | 找到的任何恶意软件或其他威胁的检测名称
Publisher | string | 发布该文件的组织的名称
SoftwareName | string | 软件产品的名称

## <a name="syntax"></a>语法

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>参数

- **x** — 要使用的文件 ID 列 `SHA1` ：、 `SHA256` 或 `InitiatingProcessSHA1` `InitiatingProcessSHA256` ;函数使用 `SHA1` （如果未指定）
- **y** — 限制要扩充的记录数，1-1000;函数使用 100（如果未指定）

## <a name="examples"></a>示例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>仅规划 SHA1 列并扩充它

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
- [了解架构](advanced-hunting-schema-reference.md)
