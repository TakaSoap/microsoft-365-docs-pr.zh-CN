---
title: File 资源类型
description: 检索最近与文件相关的 Microsoft Defender for Endpoint 警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7fef64136e27b8b9a85163fe9e25fdf59ab6d2aa
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283481"
---
# <a name="file-resource-type"></a>File 资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

表示 Defender for Endpoint 中的文件实体。

## <a name="methods"></a>Methods

方法|返回类型 |说明
:---|:---|:---
[获取文件](get-file-information.md) | [File](files.md) | 获取单个文件 
[列出与文件相关的警报](get-file-related-alerts.md) | [警报](alerts.md)集合 | 获取 [与](alerts.md) 文件关联的警报实体。
[列出与文件相关的计算机](get-file-related-machines.md) | [计算机](machine.md) 集合 | 获取 [与](machine.md) 警报关联的计算机实体。
[文件统计信息](get-file-statistics.md) | 统计信息摘要 | 检索给定文件的普遍程度。


## <a name="properties"></a>属性

|属性 | 类型 | 说明 |
|:---|:---|:---|
|sha1 | String | 文件内容的 Sha1 哈希 |
|sha256 | String | 文件内容的 Sha256 哈希 |
|globalPrevalence | Nullable long | 跨组织的文件普遍程度 |
|globalFirstObserved | DateTimeOffset | 首次观察到文件时 |
|globalLastObserved | DateTimeOffset | 上次观测到该文件的时间 |
|size | Nullable long | 文件大小 |
|fileType | String | 文件类型 |
|isPeFile | Boolean | 如果文件可移植的可执行文件 (例如"DLL"、"EXE"等，则其为 true)  |
|filePublisher | String | 文件发布者 |
|fileProductName | String | 产品名称 |
|signer | String | 文件签名者 |
|issuer | String | 文件颁发者 |
|signerHash | String | 签名证书的哈希 |
|isValidCertificate | Boolean | Microsoft Defender for Endpoint 代理是否成功验证了对证书的签名 |
|determinationType | String | 文件的确定类型 |
|determinationValue | String | 确定值 |

## <a name="json-representation"></a>Json 表示形式

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
