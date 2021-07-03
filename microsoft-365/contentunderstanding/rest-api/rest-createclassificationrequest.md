---
title: 创建分类请求
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: 使用 REST API 创建请求，使用训练后的文档理解模型对一个或多个文件进行分类。
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287229"
---
# <a name="create-classification-request"></a>创建分类请求

创建一个请求，使用应用的文档理解模型对一个或多个文件进行分类（请参阅[示例](rest-createclassificationrequest.md#examples)）。

SharePoint Online（和本地 SharePoint 2016 及更高版本）REST 服务支持合并多个请求。 使用 OData $batch 查询选项，将多个请求合并到一个服务调用中。 此方法可用于一次将数百个文档的分类工作项排入队列。

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
|TargetSiteId|guid|要分类的文件所在网站的 ID。|
|TargetWebId|guid|要分类的文件所在 Web 的 ID。|
|TargetUniqueId|guid|要分类的文件的 ID。|

## <a name="responses"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|201 已创建| |成功|

## <a name="examples"></a>示例

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>将对 ID 为"e6cff8b7-c90c-4564-b5b8-033449090932"的文件进行分类的请求排入队列

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

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
