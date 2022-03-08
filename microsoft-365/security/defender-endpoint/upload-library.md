---
title: 将文件上载到实时响应库
description: 了解如何将文件上载到实时响应库。
keywords: api， 图形 api， 受支持的 api， 上载到库
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b2c50999b7aab3588239f3965e41543680c9aad6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330776"
---
#  <a name="upload-files-to-the-live-response-library"></a>将文件上载到实时响应库  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

将文件上载到实时响应库。

## <a name="limitations"></a>限制

1.  文件最大大小限制为 20MB。

2.  此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。


| 权限类型                    | 权限     | 权限显示名称        |
|------------------------------------|----------------|--------------------------------|
| 应用程序                        | Library.Manage | 管理实时响应库 |
| 委派（工作或学校帐户） | Library.Manage | 管理实时响应库 |

## <a name="http-request"></a>HTTP 请求

上传

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>请求标头

|  名称   |    类型    |       说明                         |
|-----------------|--------|--------------------------------|
| Authorization   | String | Bearer\<token>。 必需。      |
| Content-Type    | string | multipart/form-data。 必需。 |

## <a name="request-body"></a>请求正文

在请求正文中，向表单数据对象提供以下参数：

| 参数         |     类型         |       说明                                        |
|-----------------------|--------------|------------------------------------------------------------|
| 文件                  | 文件内容 | 要上载到实时响应库的文件。必填 |
| 说明           | String       | 文件的说明。                                  |
| ParametersDescription | String       |  (脚本) 所需的可选参数。 默认值为空字符串。                |
| OverrideIfExists      | Boolean      |  (可选) 是否覆盖文件（如果该文件已存在）。 默认值为空字符串。          |



## <a name="response"></a>响应

-   如果成功，此方法在响应正文中返回 200 - OK 响应代码和上载的实时响应库实体。

-   如果未成功：此方法返回 400 - 错误请求。  
    错误的请求通常指示正文不正确。

## <a name="example"></a>示例

请求

下面是使用请求的一个示例。

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>相关主题

-  [运行实时响应](run-live-response.md) 