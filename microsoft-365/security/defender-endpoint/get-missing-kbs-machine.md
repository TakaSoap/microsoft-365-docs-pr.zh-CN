---
title: 按设备 ID 获取缺少的 KB
description: 按设备 ID 检索缺少的安全更新
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 设备 ID， 威胁& 漏洞管理 api， Microsoft Defender for Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 97cad51938c4ff3498234dbf2e9d69fd48a52367
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771869"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="63fc6-104">按设备 ID 获取缺少的 KB</span><span class="sxs-lookup"><span data-stu-id="63fc6-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63fc6-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="63fc6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="63fc6-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="63fc6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="63fc6-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="63fc6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="63fc6-108">检索缺少的 (安全更新) 设备 ID</span><span class="sxs-lookup"><span data-stu-id="63fc6-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="63fc6-109">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="63fc6-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="63fc6-110">请求标头</span><span class="sxs-lookup"><span data-stu-id="63fc6-110">Request header</span></span>

<span data-ttu-id="63fc6-111">名称</span><span class="sxs-lookup"><span data-stu-id="63fc6-111">Name</span></span> | <span data-ttu-id="63fc6-112">类型</span><span class="sxs-lookup"><span data-stu-id="63fc6-112">Type</span></span> | <span data-ttu-id="63fc6-113">说明</span><span class="sxs-lookup"><span data-stu-id="63fc6-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="63fc6-114">Authorization</span><span class="sxs-lookup"><span data-stu-id="63fc6-114">Authorization</span></span> | <span data-ttu-id="63fc6-115">String</span><span class="sxs-lookup"><span data-stu-id="63fc6-115">String</span></span> | <span data-ttu-id="63fc6-116">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="63fc6-116">Bearer {token}.</span></span> <span data-ttu-id="63fc6-117">**必需**。</span><span class="sxs-lookup"><span data-stu-id="63fc6-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="63fc6-118">请求正文</span><span class="sxs-lookup"><span data-stu-id="63fc6-118">Request body</span></span>

<span data-ttu-id="63fc6-119">Empty</span><span class="sxs-lookup"><span data-stu-id="63fc6-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="63fc6-120">响应</span><span class="sxs-lookup"><span data-stu-id="63fc6-120">Response</span></span>

<span data-ttu-id="63fc6-121">如果成功，此方法返回 200 OK，正文中指定的设备缺少 kb 数据。</span><span class="sxs-lookup"><span data-stu-id="63fc6-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="63fc6-122">示例</span><span class="sxs-lookup"><span data-stu-id="63fc6-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="63fc6-123">请求</span><span class="sxs-lookup"><span data-stu-id="63fc6-123">Request</span></span>

<span data-ttu-id="63fc6-124">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="63fc6-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="63fc6-125">响应</span><span class="sxs-lookup"><span data-stu-id="63fc6-125">Response</span></span>

<span data-ttu-id="63fc6-126">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="63fc6-126">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="63fc6-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="63fc6-127">Related topics</span></span>

- [<span data-ttu-id="63fc6-128">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="63fc6-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="63fc6-129">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="63fc6-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
