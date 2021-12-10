---
title: 启动调查 API
description: 使用此 API 在设备上开始调查。
keywords: api， 图形 api， 受支持的 api， 调查
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
ms.openlocfilehash: efffd6bdb0ab6db5b17a8d6beab09a0d84f5ff6c
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374780"
---
# <a name="start-investigation-api"></a>启动调查 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

在设备上启动自动调查。

有关详细信息 [，请参阅自动](automated-investigations.md) 调查概述。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每小时 50 次调用。

## <a name="requirements-for-air"></a>AIR 的要求

你的组织必须具有适用于终结点的 Defender (请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。

目前，AIR 仅支持以下操作系统版本：

- Windows Server 2019
- Windows Server 2022
- Windows 10版本 1709 (版本 16299.1085（包含[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更高版本）
- Windows 10版本 1803 (操作系统版本 17134.704（包含[KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更高版本）
- Windows 10版本[1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019)或更高版本
- Windows 11

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Alert.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户）|Alert.ReadWrite|"读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.security.microsoft.com/api/machines/{id}/startInvestigation
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

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 201 - [已创建响应](investigation.md) 代码和调查。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```https
POST https://api.security.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
