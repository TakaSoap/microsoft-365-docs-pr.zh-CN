---
title: 受支持的 Microsoft 威胁防护 API
description: 受支持的 Microsoft 威胁防护 API
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203691"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="8a05e-104">受支持的 Microsoft 威胁防护 API</span><span class="sxs-lookup"><span data-stu-id="8a05e-104">Supported Microsoft Threat Protection APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8a05e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8a05e-105">**Applies to:**</span></span>
- <span data-ttu-id="8a05e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8a05e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8a05e-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="8a05e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8a05e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8a05e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="8a05e-109">终结点 Uri：</span><span class="sxs-lookup"><span data-stu-id="8a05e-109">End Point URIs:</span></span>

- <span data-ttu-id="8a05e-110">服务基 URI 为： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a05e-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="8a05e-111">为获得更好的性能，你可以使用服务器近距离你的地理位置：</span><span class="sxs-lookup"><span data-stu-id="8a05e-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="8a05e-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a05e-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="8a05e-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a05e-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="8a05e-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a05e-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="8a05e-115">令牌获取的资源应为： https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a05e-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="8a05e-116">Path 下的所有 Api ```/api``` 都是 OData api。</span><span class="sxs-lookup"><span data-stu-id="8a05e-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="8a05e-117">举例. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="8a05e-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="8a05e-118">可用 Api 的列表：</span><span class="sxs-lookup"><span data-stu-id="8a05e-118">List of available APIs:</span></span>

<span data-ttu-id="8a05e-119">主题</span><span class="sxs-lookup"><span data-stu-id="8a05e-119">Topic</span></span> | <span data-ttu-id="8a05e-120">说明</span><span class="sxs-lookup"><span data-stu-id="8a05e-120">Description</span></span>
:---|:---
[<span data-ttu-id="8a05e-121">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="8a05e-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="8a05e-122">从 API 运行高级搜寻查询。</span><span class="sxs-lookup"><span data-stu-id="8a05e-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="8a05e-123">事件 API</span><span class="sxs-lookup"><span data-stu-id="8a05e-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="8a05e-124">运行与事件相关的 API 调用，例如：列出事件、更新事件等。</span><span class="sxs-lookup"><span data-stu-id="8a05e-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
