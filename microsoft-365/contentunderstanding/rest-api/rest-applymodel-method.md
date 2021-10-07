---
title: 批处理应用模型
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
description: 使用 REST API 将文档理解模型应用至一个或多个库。
ms.openlocfilehash: a31f0b499259759558dc062b7a6e9e469c93d2df
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60187073"
---
# <a name="batch-apply-model"></a>批处理应用模型

将经过培训的文档理解模型应用（或同步）到一个或多个库（请参阅 [示例](rest-applymodel-method.md#examples)）。

## <a name="http-request"></a>HTTP 请求

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|_metadata|是|字符串|在 SPO 上设置对象元。 始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}。|
|出版物|是|MachineLearningPublicationEntityData[]|MachineLearningPublicationEntityData 集合，其中每个集合均指定了模型和目标文档库。|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Name | 必需 | 类型 | 说明 |
|--------|-------|--------|------------|
|ModelUniqueId|是|字符串|模型文件的唯一 ID。|
|TargetSiteUrl|是|字符串|目标库网站的完整 URL。|
|TargetWebServerRelativeUrl|是|字符串|目标库的 Web 的服务器相应的 URL。|
|TargetLibraryServerRelativeUrl|是|字符串|目标库的服务器相应的 URL。|
|ViewOption|否|string|指定是否将新模型视图设置为库默认值。|

## <a name="response"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|201 已创建||这是一个自定义 API，用于支持将模型应用至多个文档库。如果部分成功，仍可返回已创建的 201，调用方需要检查响应正文，以了解模型是否已成功应用至文档库。|

## <a name="response-body"></a>响应正文

| 名称   | 类型  | 说明|
|--------|-------|------------|
|TotalSuccesses|int|成功应用至文档库的模型的总数。|
|TotalFailures|int|未能应用至文档库的模型的总数。|
|详细信息|MachineLearningPublicationResult[]|MachineLearningPublicationResult 的集合，其中每个集合均指定了将模型应用至文档库的详细结果。|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>从存储库网站中的合同文档库中应用模型

此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。

#### <a name="sample-request"></a>示例请求

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>示例响应

在响应中，TotalFailures 和 TotalSuccesses 指应用于指定库的模型的失败和成功次数。

**状态代码：** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
