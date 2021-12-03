---
title: 获取设备安全分数
description: 检索组织设备安全分数。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 69385a5a1da4b9e91084b4fc524334956c2d8403
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300198"
---
# <a name="get-device-secure-score"></a>获取设备安全分数

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索你的 [Microsoft 设备安全分数](tvm-microsoft-secure-score-devices.md)。 设备的 Microsoft 安全分数越高，你的终结点就更能够抵御网络安全威胁攻击。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Score.Read.All|"读取威胁和漏洞管理分数"
委派（工作或学校帐户）|Score.Read|"读取威胁和漏洞管理分数"

## <a name="http-request"></a>HTTP 请求

```http
GET /api/configurationScore
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功，此方法返回 200 OK，响应正文中显示设备安全分数数据。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

> [!NOTE]
> 为简洁起见，可能会截断此处显示的响应列表。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>另请参阅

- [使用 Microsoft Defender for Endpoint 的 OData 查询](exposed-apis-odata-samples.md)
