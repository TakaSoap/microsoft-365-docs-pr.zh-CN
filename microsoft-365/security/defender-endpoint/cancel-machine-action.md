---
title: 取消计算机操作 API
description: 了解如何取消已启动计算机操作
keywords: api、 图形 api、
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
ms.collection: m365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fc4191043e19df7fea4f350d85acd78d2eca1551
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322907"
---
# <a name="cancel-machine-action-api"></a>取消计算机操作 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

取消尚未在最终状态中启动 (、已取消、失败) 。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。

|权限类型|权限|权限显示名称|
|---|---|---|
|应用程序|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|收集取证 <br>隔离计算机<br>限制代码执行<br>  扫描计算机<br>  卸载计算机<br> 停止和隔离<br> 在特定的计算机上运行实时响应|
|委派（工作或学校帐户）|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|收集取证<br> 隔离计算机<br>  限制代码执行<br> 扫描计算机<br>卸载计算机<br> 停止和隔离<br> 在特定的计算机上运行实时响应|

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>请求标头

|名称|类型|说明|
|---|---|---|
|Authorization|String|Bearer {token}。必需。|
|Content-Type|string|application/json. Required.|

## <a name="request-body"></a>请求正文

|参数|类型|说明|
|---|---|---|
|评论|字符串|要与取消操作关联的注释。|

## <a name="response"></a>响应

如果成功，此方法使用 Machine Action 实体返回 200 OK 响应代码。 如果未找到具有指定 ID 的机器操作实体 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```

```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>相关主题

- [获取计算机操作 API](get-machineaction-object.md)
