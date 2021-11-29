---
title: 隔离计算机 API
description: 了解如何使用隔离计算机 API 隔离设备以在 Microsoft Defender for Endpoint 中访问外部网络。
keywords: api， 图形 api， 受支持的 api， 隔离设备
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: f01a63dd5a2fa5d5aa56f171617041044a267fbb
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218126"
---
# <a name="isolate-machine-api"></a>隔离计算机 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

将设备与外部网络隔离。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - 完全隔离适用于版本 1703 Windows 10上的设备。
> - 选择性隔离适用于 Windows 10 版本 1709 或更高版本上的设备。
> - 隔离设备时，仅允许某些进程和目标。 因此，完整 VPN 隧道后面的设备在隔离设备后将无法访问 Microsoft Defender for Endpoint 云服务。 我们建议为 Microsoft Defender for Endpoint 使用拆分隧道 VPN，Microsoft Defender 防病毒基于云的保护相关流量。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
Application|Machine.Isolate|"隔离计算机"
委派（工作或学校帐户）|Machine.Isolate|"隔离计算机"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。
Content-Type|string|application/json. 必需。

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数|类型|说明
:---|:---|:---
评论|字符串|要与操作关联的注释。 必需。
IsolationType|String|隔离的类型。 允许的值包括："Full"或"Selective"。

**IsolationType** 控制要执行隔离的类型，可以是下列类型之一：

- 完全：完全隔离
- 选择性：仅限制一组有限的应用程序访问网络 [ (请参阅将](respond-machine-alerts.md#isolate-devices-from-the-network) 设备与网络隔离，了解详细信息) 

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- 若要解除设备隔离，请参阅 [解除设备隔离](unisolate-machine.md)。
