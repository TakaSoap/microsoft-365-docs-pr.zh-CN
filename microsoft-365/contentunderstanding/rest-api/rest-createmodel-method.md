---
title: 创建模型
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
description: 使用 REST API 创建模型及其关联的内容类型。
ms.openlocfilehash: c74eda4e3136e2c391c89fc012628bde2ce172f4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159564"
---
# <a name="create-model"></a>创建模型

创建模型及其关联的内容类型。 请注意，此操作仅创建模型。 它还需要在内容中心接受培训（请参阅[示例](rest-createmodel-method.md#examples)）。

## <a name="http-request"></a>HTTP 请求

```http
POST /_api/machinelearning/models HTTP/1.1
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
|_元数据|  |在 SPO 上设置对象元。 始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|字符串|与模型关联的内容类型组。 默认为“智能文档内容类型”。|
|ContentTypeName|字符串|关联的内容类型名称。 创建的模型文件将具有相同的名称。|

## <a name="responses"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|201 已创建| |成功|

## <a name="examples"></a>示例

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>创建名为“Contoso 合同”的新文档理解模型

#### <a name="sample-request"></a>示例请求

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>示例响应

**状态代码：** 201

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
