---
title: 从实时响应库中删除文件
description: 了解如何从实时响应库中删除文件。
keywords: api， 图形 api， 受支持的 api， 从库中删除
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 23625c8b7160d604df5f3a8b1b1387fc31027acf
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526810"
---
#  <a name="delete-a-file-from-the-live-response-library"></a>从实时响应库中删除文件  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

从实时响应库中删除文件。

## <a name="limitations"></a>限制

1.  此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。

| 权限类型                    | 权限     | 权限显示名称        |
|------------------------------------|----------------|--------------------------------|
| Application                        | Library.Manage | 管理实时响应库 |
| 委派（工作或学校帐户） | Library.Manage | 管理实时响应库 |

## <a name="http-request"></a>HTTP 请求

删除 https://api.securitycenter.microsoft.com/api/libraryfiles/{fileName}

## <a name="request-headers"></a>请求标头

| 名称            | 类型   | 说明               |
|-----------------|--------|---------------------------|
| Authorization   | 字符串 | Bearer\<token>\. 必需。 |

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

-   如果库中存在文件并成功删除 204 无内容。

-   如果未找到指定的文件名 404 未找到。

## <a name="example"></a>示例

请求

下面是一个请求示例。

```HTTP
DELETE https://api.securitycenter.microsoft.com/api/libraryfiles/script1.ps1
```

## <a name="related-topic"></a>相关主题
- [运行实时响应](run-live-response.md) 