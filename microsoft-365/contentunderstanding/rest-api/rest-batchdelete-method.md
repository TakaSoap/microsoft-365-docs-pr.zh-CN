---
title: 批处理删除
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
description: 使用 REST API 从一个或多个库中删除应用的文档理解模型。
ms.openlocfilehash: 52154c5f963ddb466b1544925ffe225fd6b8ff67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60187049"
---
# <a name="batchdelete"></a>批处理删除

从一个或多个库中删除应用的文档理解模型。 请注意，必须先从所有库删除模型才能将其删除（请参阅 [示例](rest-batchdelete-method.md#examples)）。

## <a name="http-request"></a>HTTP 请求

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>URI 参数

无

## <a name="request-headers"></a>请求标头

| 标头 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|当前网站的相应摘要。|

## <a name="request-body"></a>请求正文

| Name | 必需 | 类型 | 说明 |
|--------|-------|--------|------------|
|出版物|是|MachineLearningPublicationEntityData[]|MachineLearningPublicationEntityData 集合，其中每个集合均指定了模型和目标文档库。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Name | 必需 | 类型 | 说明 |
|--------|-------|--------|------------|
|ModelUniqueId|是|字符串|模型文件的唯一 ID。|
|TargetSiteUrl|是|字符串|目标库网站的完整 URL。|
|TargetWebServerRelativeUrl|是|字符串|目标库的 Web 的服务器相应的 URL。|
|TargetLibraryServerRelativeUrl|是|字符串|目标库的服务器相应的 URL。|

## <a name="response"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|200 OK||这是一个自定义 API，用于支持从多文档库中删除模型。如果部分成功，仍可返回 200 OK，调用方需要检查响应正文，以了解模型是否已成功从文档库中删除。|

## <a name="response-body"></a>响应正文

| 名称   | 类型  | 说明|
|--------|-------|------------|
|TotalSuccesses|int|从文档库中成功删除的模型的总数。|
|TotalFailures|int|未能从文档库中删除的模型的总数。|
|详细信息|MachineLearningPublicationResult[]|MachineLearningPublicationResult 的集合，其中每个集合均指定了从文档库中删除模型的详细结果。|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| 名称   | 类型  | 说明|
|--------|-------|------------|
|StatusCode|int|HTTP 状态代码。|
|ErrorMessage|string|将模型应用到文档库时会显示错误内容的错误消息。|
|出版物|MachineLearningPublicationEntityData|它指定了模型信息和目标文档库。| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| 名称 | 类型 | 说明 |
|--------|--------|------------|
|ModelUniqueId|字符串|模型文件的唯一 ID。|
|TargetSiteUrl|字符串|目标库网站的完整 URL。|
|TargetWebServerRelativeUrl|字符串|目标库的 Web 的服务器相应的 URL。|
|TargetLibraryServerRelativeUrl|字符串|目标库的服务器相应的 URL。|

## <a name="examples"></a>示例

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>从存储库网站中的合同文档库中删除模型

此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

#### <a name="sample-request"></a>示例请求

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>示例响应

在响应中，TotalFailures 和 TotalSuccesses 指从指定库中删除模型的失败和成功次数。

**状态代码：** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
