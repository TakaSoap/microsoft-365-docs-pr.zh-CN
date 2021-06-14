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
localization_priority: Priority
description: 使用 REST API 从一个或多个库中删除应用的文档理解模型。
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904161"
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
|ModelUniqueId|是|字符串|模型文件的唯一 ID。|
TargetSiteUrl|是|字符串|目标库网站的完整 URL。|
TargetWebServerRelativeUrl|是|字符串|目标库的 Web 的服务器相应的 URL。|
TargetLibraryServerRelativeUrl|是|字符串|目标库的服务器相应的 URL。|
ViewOption|否|string|指定是否将新模型视图设置为库默认值。|

## <a name="response"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|200 OK| |成功|


## <a name="examples"></a>示例

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>从存储库网站中的合同文档库中删除模型

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
