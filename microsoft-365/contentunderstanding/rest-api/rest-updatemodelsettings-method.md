---
title: UpdateModelSettings
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
description: 使用 REST API 更新 SharePoint Syntex 文档理解模型的可用模型设置。
ms.openlocfilehash: f6489208b292237936776a2cfa98a5c1c42e64a9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168646"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）（请参阅[示例](rest-updatemodelsettings-method.md#examples)）。

## <a name="http-request"></a>HTTP 请求

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI 参数

|名称 |位置 |必需|类型|说明|
|-----|---|--------|----|-----------|
|modelFileName|查询|True|string|Syntex 模型文件的名称。|

## <a name="request-headers"></a>请求标头

| 标头 | 值 |
|--------|-------|
|Accept|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|当前网站的相应摘要。|

## <a name="request-body"></a>请求正文

|名称    |类型   |说明 |
|--------|-------|-------|
|ModelSettings|字符串|模型设置的 JSON。|
|说明|string|模型说明。|
|RetentionLabel| |关联标签的信息（标签 ID 和名称）。|

## <a name="responses"></a>响应

| 名称   | 类型  | 说明|
|--------|-------|------------|
|200 OK| |成功|

## <a name="examples"></a>示例

### <a name="update-model-settings-for-contoso-contract"></a>Contoso 合同更新模型设置

此示例中，更新了模型说明和“标准保留”保留标签。 保留标签的 ID 为 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。

#### <a name="sample-request"></a>示例请求

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>示例响应

**状态代码：** 200

## <a name="see-also"></a>另请参阅

[Syntex 文档理解模型 REST API](syntex-model-rest-api.md)
