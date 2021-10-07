---
title: SharePoint Syntex 文档理解模型 REST API
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
description: SharePoint Syntex 文档理解模型 REST API 概述。
ms.openlocfilehash: 882dcdbe3561803d20d698e5d1510dd5232fbbe5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163369"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>SharePoint Syntex 文档理解模型 REST API

可使用 SharePoint REST 接口创建文档理解模型、将模型应用到一个或多个库或将其从中删除，以及获取或更新有关模型的信息。 

SharePoint Online（和本地 SharePoint 2016 及更高版本）REST 服务支持使用 OData $batch 查询选项，将多个请求合并到一个服务调用中。 

有关详细信息和代码示例链接，请参阅[使用 REST API 发出批处理请求](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)。

## <a name="prerequisites"></a>先决条件

开始前，请务必先熟悉以下内容：

- [了解 SharePoint REST 服务](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [使用 SharePoint REST 终结点完成基本操作](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST 命令

以下 REST 命令可用于处理 Syntex 文档理解模型：

- [创建模型](rest-createmodel-method.md)–创建模型及其关联的内容类型。
- [GetByUniqueId](rest-getbyuniqueid-method.md) - 获取或更新有关 SharePoint Syntex 文档理解模型的信息。
- [GetByTitle](rest-getbytitle-method.md) - 使用模型标题获取或更新有关 SharePoint Syntex 文档理解模型的信息。
- [应用模型](rest-applymodel-method.md) - 将经过培训的文档理解模型应用（或同步）到一个或多个库。
- [获取模型和库信息](rest-getmodelandlibraryinfo.md) - 获取有关模型及应用该模型的库的信息。
- [UpdateModelSettings](rest-updatemodelsettings-method.md) - 更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）。
- [BatchDelete](rest-batchdelete-method.md) – 从一个或多个库中删除应用的文档理解模型。
- [创建文件分类请求](rest-createclassificationrequest.md) - 使用应用的模型创建对指定的文件或多个文件进行分类的请求。
- [创建文件夹分类请求](rest-createclassificationrequest.md) - 使用应用的模型创建对整个文件夹进行分类的请求。

## <a name="scenarios"></a>应用场景

请注意：下面的一些应用场景示例无法通过方法名称直观体现。 有关详细信息，请参阅各文章。

创建模型方法仅创建模型对象及其关联的内容类型。 你需要先在内容中心对模型进行训练，才能将模型应用到库。

应用模型方法用于对目标库上的模型进行配置，以对文档进行分类并选择性地提取其他信息。 此 API 也支持将模型批次应用到多个库。

删除模型方法仅从之前应用该模型的一个或多个库中将其删除。 如果要删除模型，必须先从应用该模型的所有库中将其删除。


## <a name="see-also"></a>另请参阅

[文档理解概述](../document-understanding-overview.md)

