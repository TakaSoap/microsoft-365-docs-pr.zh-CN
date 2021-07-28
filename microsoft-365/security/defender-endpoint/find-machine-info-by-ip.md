---
title: 通过内部 IP API 查找设备信息
description: 使用此 API 创建与通过内部 IP 查找特定时间戳周围的设备条目相关的调用。
keywords: ip， api， 图形 api， 受支持的 api， 查找设备， 设备信息
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 440eb0d44d1faa0589e1c7315528d68c6c5dc1a5
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53619623"
---
# <a name="find-device-information-by-internal-ip-api"></a>通过内部 IP API 查找设备信息

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

通过内部 IP 查找设备。

> [!NOTE]
> 时间戳必须在最近 30 天内。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Machine.Read.All|"读取所有计算机配置文件"
应用程序|Machine.ReadWrite.All|"读取和写入所有计算机信息"

## <a name="http-request"></a>HTTP 请求

```http
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|字符串|Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且计算机存在 - 200 正常。
如果未找到计算机 - 404 未找到。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

响应将返回时间戳之前和之后 16 分钟内报告此 IP 地址的所有设备的列表。

```json
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
...
}
```
