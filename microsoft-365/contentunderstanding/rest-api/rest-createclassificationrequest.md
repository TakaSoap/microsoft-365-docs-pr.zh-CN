---
title: 创建文件分类请求
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
description: 使用 REST API 创建请求，使用训练后的文档理解模型对一个或多个文件进行分类。
ms.openlocfilehash: 9f57799a9d1b631be5586dd285dc02cff1237b98
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186989"
---
# <a name="create-file-classification-request"></a>创建文件分类请求

创建一个请求，以使用应用的文档理解模型对一个或多个文件进行分类（有关详细信息，请参阅 [示例](rest-createclassificationrequest.md#examples)。）

SharePoint Online 的 REST 服务（以及本地 SharePoint 2016 及更高版本）支持多个请求的组合。 使用 OData $batch 查询选项，将多个请求合并到一个服务调用中。 此方法可用于一次将数百个文档的分类工作项排入队列。

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
|TargetSiteId|guid|要分类的文件所在的站点的 ID。 当 TargetSiteUrl 具有值时，可以省略此值。 |
|TargetSiteUrl|字符串|要分类的文件所在的站点的完整 URL。 当 TargeSiteId 具有值时，可以省略此值。|
|TargetWebId|guid|要分类的文件所在的 Web 的 ID。 当 TargetWebServerRelativeUrl 具有值时，可以省略此值。 |
|TargetWebServerRelativeUrl|字符串|要分类的文件所在的 Web 的服务器相对 URL。 当 TargetWebId 具有值时，可以省略此值。  |
|TargetUniqueId|guid|要分类的文件夹的 ID。 当 TargetServerRelativeUrl 具有值时，可以省略此值。 |
|TargetServerRelativeUrl|string|要分类的文件的服务器相对 URL 位于。 当 TargetUniqueId 具有值时，可以省略此值。|

## <a name="responses"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|201 已创建| |响应是自定义的。 如果出现故障，它仍可能返回 201 Created。 调用方应进一步检查响应正文以确定确切结果。|

## <a name="examples"></a>示例

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>将请求对 ID 为“e6cff8b7-c90c-4564-b5b8-033449090932”的文件进行分类

#### <a name="sample-request"></a>示例请求

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
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

```JSON
{
    "ErrorMessage":  null,
    "StatusCode":  201
}
```

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
