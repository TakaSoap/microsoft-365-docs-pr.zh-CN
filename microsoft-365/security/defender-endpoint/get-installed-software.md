---
title: 获取已安装的软件
description: 检索与给定设备 ID 相关的已安装软件的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件清单， 每个设备安装的软件， 威胁 & 漏洞管理 api， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 35cbeedc5d13f5eeb99718b4f98e2d8aabe1e965
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770153"
---
# <a name="get-installed-software"></a><span data-ttu-id="37842-104">获取已安装的软件</span><span class="sxs-lookup"><span data-stu-id="37842-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37842-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="37842-105">**Applies to:**</span></span>
- [<span data-ttu-id="37842-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="37842-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37842-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37842-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37842-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="37842-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="37842-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="37842-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="37842-110">检索与给定设备 ID 相关的已安装软件的集合。</span><span class="sxs-lookup"><span data-stu-id="37842-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="37842-111">权限</span><span class="sxs-lookup"><span data-stu-id="37842-111">Permissions</span></span>
<span data-ttu-id="37842-112">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="37842-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="37842-113">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="37842-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="37842-114">权限类型</span><span class="sxs-lookup"><span data-stu-id="37842-114">Permission type</span></span> |   <span data-ttu-id="37842-115">权限</span><span class="sxs-lookup"><span data-stu-id="37842-115">Permission</span></span>  |   <span data-ttu-id="37842-116">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="37842-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="37842-117">应用程序</span><span class="sxs-lookup"><span data-stu-id="37842-117">Application</span></span> |<span data-ttu-id="37842-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="37842-118">Software.Read.All</span></span> |    <span data-ttu-id="37842-119">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="37842-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="37842-120">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="37842-120">Delegated (work or school account)</span></span> | <span data-ttu-id="37842-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="37842-121">Software.Read</span></span> |    <span data-ttu-id="37842-122">"读取威胁和漏洞管理软件信息"</span><span class="sxs-lookup"><span data-stu-id="37842-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="37842-123">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="37842-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="37842-124">请求标头</span><span class="sxs-lookup"><span data-stu-id="37842-124">Request headers</span></span>

<span data-ttu-id="37842-125">名称</span><span class="sxs-lookup"><span data-stu-id="37842-125">Name</span></span> | <span data-ttu-id="37842-126">类型</span><span class="sxs-lookup"><span data-stu-id="37842-126">Type</span></span> | <span data-ttu-id="37842-127">说明</span><span class="sxs-lookup"><span data-stu-id="37842-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="37842-128">Authorization</span><span class="sxs-lookup"><span data-stu-id="37842-128">Authorization</span></span> | <span data-ttu-id="37842-129">String</span><span class="sxs-lookup"><span data-stu-id="37842-129">String</span></span> | <span data-ttu-id="37842-130">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="37842-130">Bearer {token}.</span></span> <span data-ttu-id="37842-131">**必需**。</span><span class="sxs-lookup"><span data-stu-id="37842-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="37842-132">请求正文</span><span class="sxs-lookup"><span data-stu-id="37842-132">Request body</span></span>
<span data-ttu-id="37842-133">Empty</span><span class="sxs-lookup"><span data-stu-id="37842-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="37842-134">响应</span><span class="sxs-lookup"><span data-stu-id="37842-134">Response</span></span>
<span data-ttu-id="37842-135">如果成功，此方法在正文中返回包含已安装软件信息的 200 OK。</span><span class="sxs-lookup"><span data-stu-id="37842-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="37842-136">示例</span><span class="sxs-lookup"><span data-stu-id="37842-136">Example</span></span>

<span data-ttu-id="37842-137">**请求**</span><span class="sxs-lookup"><span data-stu-id="37842-137">**Request**</span></span>

<span data-ttu-id="37842-138">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="37842-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="37842-139">**响应**</span><span class="sxs-lookup"><span data-stu-id="37842-139">**Response**</span></span>

<span data-ttu-id="37842-140">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="37842-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="37842-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37842-141">See also</span></span>

- [<span data-ttu-id="37842-142">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="37842-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="37842-143">威胁&漏洞软件清单</span><span class="sxs-lookup"><span data-stu-id="37842-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
