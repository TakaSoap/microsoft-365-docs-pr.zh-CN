---
title: 按设备 ID 获取缺少的 KB
description: 按设备 ID 检索缺少的安全更新
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 设备 ID， 威胁&漏洞管理 api， mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4364e6a38d4597a95d4d9a1f05dcce6fce5797ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500695"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="af6a5-104">按设备 ID 获取缺少的 KB</span><span class="sxs-lookup"><span data-stu-id="af6a5-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af6a5-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="af6a5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="af6a5-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="af6a5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af6a5-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="af6a5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="af6a5-108">检索缺少的 (安全更新) 设备 ID</span><span class="sxs-lookup"><span data-stu-id="af6a5-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="af6a5-109">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="af6a5-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="af6a5-110">请求标头</span><span class="sxs-lookup"><span data-stu-id="af6a5-110">Request header</span></span>

<span data-ttu-id="af6a5-111">名称</span><span class="sxs-lookup"><span data-stu-id="af6a5-111">Name</span></span> | <span data-ttu-id="af6a5-112">类型</span><span class="sxs-lookup"><span data-stu-id="af6a5-112">Type</span></span> | <span data-ttu-id="af6a5-113">说明</span><span class="sxs-lookup"><span data-stu-id="af6a5-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="af6a5-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="af6a5-114">Authorization</span></span> | <span data-ttu-id="af6a5-115">字符串</span><span class="sxs-lookup"><span data-stu-id="af6a5-115">String</span></span> | <span data-ttu-id="af6a5-116">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="af6a5-116">Bearer {token}.</span></span> <span data-ttu-id="af6a5-117">**必需**。</span><span class="sxs-lookup"><span data-stu-id="af6a5-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="af6a5-118">请求正文</span><span class="sxs-lookup"><span data-stu-id="af6a5-118">Request body</span></span>

<span data-ttu-id="af6a5-119">Empty</span><span class="sxs-lookup"><span data-stu-id="af6a5-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="af6a5-120">响应</span><span class="sxs-lookup"><span data-stu-id="af6a5-120">Response</span></span>

<span data-ttu-id="af6a5-121">如果成功，此方法返回 200 OK，正文中指定的设备缺少 kb 数据。</span><span class="sxs-lookup"><span data-stu-id="af6a5-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="af6a5-122">示例</span><span class="sxs-lookup"><span data-stu-id="af6a5-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="af6a5-123">请求</span><span class="sxs-lookup"><span data-stu-id="af6a5-123">Request</span></span>

<span data-ttu-id="af6a5-124">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="af6a5-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="af6a5-125">响应</span><span class="sxs-lookup"><span data-stu-id="af6a5-125">Response</span></span>

<span data-ttu-id="af6a5-126">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="af6a5-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="af6a5-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="af6a5-127">Related topics</span></span>

- [<span data-ttu-id="af6a5-128">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="af6a5-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="af6a5-129">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="af6a5-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
