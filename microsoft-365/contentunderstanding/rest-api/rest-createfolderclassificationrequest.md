---
title: 创建文件夹分类请求
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
ms.localizationpriority: high
description: 使用REST API创建请求，以使用训练的文档理解模型对整个文件夹进行分类。
ms.openlocfilehash: ea5748b5eb376872738d30b142927314abfe9d3e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186869"
---
# <a name="create-folder-classification-request"></a>创建文件夹分类请求

使用应用的文档理解模型创建在非高峰时段对整个文件夹进行分类的请求。 （有关详细信息，请参阅[示例](rest-createfolderclassificationrequest.md#examples)。）此 API 可用于通过为其根文件夹创建工作项来对整个文档库进行分类。

## <a name="http-request"></a>HTTP 请求

```http
POST /_api/machinelearning/workItems HTTP/1.1
```

## <a name="uri-parameters"></a>URI 参数

无

## <a name="request-headers"></a>请求标头

| 标头 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|当前网站的适当摘要|

## <a name="request-body"></a>请求正文

|名称    |类型   |说明 |
|--------|-------|------------|
|_元数据|字符串 |在 SPO 上设置对象元。 始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|要分类的文件夹所在的站点的 ID。 当 TargetSiteUrl 具有值时，可以省略此值。 |
|TargetSiteUrl|字符串|要分类的文件夹所在的站点的完整 URL。 当 TargeSiteId 具有值时，可以省略此值。|
|TargetWebId|guid|要分类的文件夹所在的 Web 的 ID。 当 TargetWebServerRelativeUrl 具有值时，可以省略此值。 |
|TargetWebServerRelativeUrl|字符串|要分类的文件夹所在的 Web 的服务器相对 URL。 当 TargetWebId 具有值时，可以省略此值。  |
|TargetUniqueId|guid|要分类的文件夹的 ID。 当 TargetServerRelativeUrl 具有值时，可以省略此值。 |
|TargetServerRelativeUrl|string|要分类的文件夹的服务器相对 URL 位于此位置。 当 TargetUniqueId 具有值时，可以省略此值。|
|IsFolder|boolean|指示要分类的内容是否为文件夹的标志。 在创建文件夹分类工作项时，请始终将此设置为 true。 |


## <a name="responses"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|201 已创建| |响应是自定义的。 如果出现故障，它仍可能返回 201 Created。 调用方应进一步检查响应正文以确定确切结果。|

## <a name="response-body"></a>响应正文

| 名称   | 类型  | 说明|
|--------|-------|------------|
|StatusCode |int |HTTP 状态代码。如果不是 200 或 201，则 API 应该已失败。|
|ErrorMessage |string |将模型应用到文档库时告知错误的错误消息。|

## <a name="examples"></a>示例

### <a name="enqueue-a-request-to-classify-a-whole-folder-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>将请求对 ID 为“e6cff8b7-c90c-4564-b5b8-033449090932”的整个文件夹进行分类


#### <a name="sample-request"></a>示例请求

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932",
    "IsFolder": true 
}
```

#### <a name="sample-response"></a>示例响应

**状态代码：** 201

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
