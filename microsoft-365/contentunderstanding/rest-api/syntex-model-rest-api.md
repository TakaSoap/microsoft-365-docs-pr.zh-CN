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
localization_priority: Priority
description: SharePoint Syntex 文档理解模型 REST API 概述。
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904169"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="59d64-103">SharePoint Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="59d64-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="59d64-104">可使用 SharePoint REST 接口创建文档理解模型、将模型应用到一个或多个库或将其从中删除，以及获取或更新有关模型的信息。</span><span class="sxs-lookup"><span data-stu-id="59d64-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="59d64-105">SharePoint Online（和本地 SharePoint 2016 及更高版本）REST 服务支持使用 OData $batch 查询选项，将多个请求合并到一个服务调用中。</span><span class="sxs-lookup"><span data-stu-id="59d64-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="59d64-106">有关详细信息和代码示例链接，请参阅[使用 REST API 发出批处理请求](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="59d64-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59d64-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="59d64-107">Prerequisites</span></span>

<span data-ttu-id="59d64-108">开始前，请务必先熟悉以下内容：</span><span class="sxs-lookup"><span data-stu-id="59d64-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="59d64-109">了解 SharePoint REST 服务</span><span class="sxs-lookup"><span data-stu-id="59d64-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="59d64-110">使用 SharePoint REST 终结点完成基本操作</span><span class="sxs-lookup"><span data-stu-id="59d64-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="59d64-111">REST 命令</span><span class="sxs-lookup"><span data-stu-id="59d64-111">REST commands</span></span>

<span data-ttu-id="59d64-112">以下 REST 命令可用于处理 Syntex 文档理解模型：</span><span class="sxs-lookup"><span data-stu-id="59d64-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="59d64-113">[创建模型](rest-createmodel-method.md)–创建模型及其关联的内容类型。</span><span class="sxs-lookup"><span data-stu-id="59d64-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="59d64-114">[GetByUniqueId](rest-getbyuniqueid-method.md) - 获取或更新有关 SharePoint Syntex 文档理解模型的信息。</span><span class="sxs-lookup"><span data-stu-id="59d64-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="59d64-115">[GetByTitle](rest-getbytitle-method.md) - 使用模型标题获取或更新有关 SharePoint Syntex 文档理解模型的信息。</span><span class="sxs-lookup"><span data-stu-id="59d64-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="59d64-116">[应用模型](rest-applymodel-method.md) - 将经过培训的文档理解模型应用（或同步）到一个或多个库。</span><span class="sxs-lookup"><span data-stu-id="59d64-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="59d64-117">[获取模型和库信息](rest-getmodelandlibraryinfo.md) - 获取有关模型及应用该模型的库的信息。</span><span class="sxs-lookup"><span data-stu-id="59d64-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="59d64-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) - 更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）。</span><span class="sxs-lookup"><span data-stu-id="59d64-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="59d64-119">[BatchDelete](rest-batchdelete-method.md) – 从一个或多个库中删除应用的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="59d64-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="59d64-120">[创建分类请求](rest-createclassificationrequest.md) - 创建使用应用的模型对一个指定文件或多个文件进行分类的请求。</span><span class="sxs-lookup"><span data-stu-id="59d64-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="59d64-121">应用场景</span><span class="sxs-lookup"><span data-stu-id="59d64-121">Scenarios</span></span>

<span data-ttu-id="59d64-122">请注意：下面的一些应用场景示例无法通过方法名称直观体现。</span><span class="sxs-lookup"><span data-stu-id="59d64-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="59d64-123">有关详细信息，请参阅各文章。</span><span class="sxs-lookup"><span data-stu-id="59d64-123">For more information, see each article.</span></span>

<span data-ttu-id="59d64-124">创建模型方法仅创建模型对象及其关联的内容类型。</span><span class="sxs-lookup"><span data-stu-id="59d64-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="59d64-125">你需要先在内容中心对模型进行训练，才能将模型应用到库。</span><span class="sxs-lookup"><span data-stu-id="59d64-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="59d64-126">应用模型方法用于对目标库上的模型进行配置，以对文档进行分类并选择性地提取其他信息。</span><span class="sxs-lookup"><span data-stu-id="59d64-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="59d64-127">此 API 也支持将模型批次应用到多个库。</span><span class="sxs-lookup"><span data-stu-id="59d64-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="59d64-128">删除模型方法仅从之前应用该模型的一个或多个库中将其删除。</span><span class="sxs-lookup"><span data-stu-id="59d64-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="59d64-129">如果要删除模型，必须先从应用该模型的所有库中将其删除。</span><span class="sxs-lookup"><span data-stu-id="59d64-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="59d64-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59d64-130">See also</span></span>

[<span data-ttu-id="59d64-131">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="59d64-131">Document understanding overview</span></span>](../document-understanding-overview.md)

