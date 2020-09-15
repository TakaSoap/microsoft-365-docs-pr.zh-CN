---
title: 支持的 Microsoft 威胁防护 Api
description: 支持的 Microsoft 威胁防护 Api
keywords: MTP、Api、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650144"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="2bb53-104">支持的 Microsoft 威胁防护 Api</span><span class="sxs-lookup"><span data-stu-id="2bb53-104">Supported Microsoft Threat Protection APIs</span></span> 
<span data-ttu-id="2bb53-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2bb53-105">**Applies to:**</span></span>
- <span data-ttu-id="2bb53-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="2bb53-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2bb53-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="2bb53-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2bb53-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2bb53-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="2bb53-109">终结点 Uri：</span><span class="sxs-lookup"><span data-stu-id="2bb53-109">End Point URIs:</span></span>

- <span data-ttu-id="2bb53-110">服务基 URI 为： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bb53-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="2bb53-111">为获得更好的性能，你可以使用服务器近距离你的地理位置：</span><span class="sxs-lookup"><span data-stu-id="2bb53-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="2bb53-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bb53-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="2bb53-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bb53-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="2bb53-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bb53-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="2bb53-115">令牌获取的资源应为： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bb53-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="2bb53-116">Path 下的所有 Api ```/api``` 都是 OData api。</span><span class="sxs-lookup"><span data-stu-id="2bb53-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="2bb53-117">举例. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="2bb53-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="2bb53-118">可用 Api 的列表：</span><span class="sxs-lookup"><span data-stu-id="2bb53-118">List of available APIs:</span></span>

<span data-ttu-id="2bb53-119">主题</span><span class="sxs-lookup"><span data-stu-id="2bb53-119">Topic</span></span> | <span data-ttu-id="2bb53-120">说明</span><span class="sxs-lookup"><span data-stu-id="2bb53-120">Description</span></span>
:---|:---
[<span data-ttu-id="2bb53-121">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="2bb53-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="2bb53-122">从 API 运行高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="2bb53-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="2bb53-123">事件 Api</span><span class="sxs-lookup"><span data-stu-id="2bb53-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="2bb53-124">运行与事件相关的 API 调用，例如：列出事件、更新事件等。</span><span class="sxs-lookup"><span data-stu-id="2bb53-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
