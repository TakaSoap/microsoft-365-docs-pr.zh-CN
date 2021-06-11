---
title: 获取实时响应结果
description: 了解如何按其索引检索特定实时响应命令结果。
keywords: api， 图形 api， 受支持的 api， 上传到库
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879661"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="67867-104">获取实时响应结果</span><span class="sxs-lookup"><span data-stu-id="67867-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67867-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="67867-105">**Applies to:**</span></span>
- [<span data-ttu-id="67867-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67867-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="67867-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="67867-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67867-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="67867-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="67867-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="67867-109">API description</span></span>

<span data-ttu-id="67867-110">按索引检索特定实时响应命令结果。</span><span class="sxs-lookup"><span data-stu-id="67867-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="67867-111">限制</span><span class="sxs-lookup"><span data-stu-id="67867-111">Limitations</span></span>

1.  <span data-ttu-id="67867-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="67867-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="67867-113">权限</span><span class="sxs-lookup"><span data-stu-id="67867-113">Permissions</span></span>

<span data-ttu-id="67867-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="67867-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="67867-115">若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="67867-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="67867-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="67867-116">Permission type</span></span>                    | <span data-ttu-id="67867-117">权限</span><span class="sxs-lookup"><span data-stu-id="67867-117">Permission</span></span>           | <span data-ttu-id="67867-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="67867-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="67867-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="67867-119">Application</span></span>                        | <span data-ttu-id="67867-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="67867-120">Machine.LiveResponse</span></span> | <span data-ttu-id="67867-121">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="67867-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="67867-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="67867-122">Delegated (work or school account)</span></span> | <span data-ttu-id="67867-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="67867-123">Machine.LiveResponse</span></span> | <span data-ttu-id="67867-124">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="67867-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="67867-125">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="67867-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="67867-126">请求标头</span><span class="sxs-lookup"><span data-stu-id="67867-126">Request headers</span></span>

| <span data-ttu-id="67867-127">名称</span><span class="sxs-lookup"><span data-stu-id="67867-127">Name</span></span>      | <span data-ttu-id="67867-128">类型</span><span class="sxs-lookup"><span data-stu-id="67867-128">Type</span></span> | <span data-ttu-id="67867-129">说明</span><span class="sxs-lookup"><span data-stu-id="67867-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="67867-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="67867-130">Authorization</span></span> | <span data-ttu-id="67867-131">String</span><span class="sxs-lookup"><span data-stu-id="67867-131">String</span></span>   | <span data-ttu-id="67867-p103">Bearer {token}。必需。</span><span class="sxs-lookup"><span data-stu-id="67867-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="67867-134">请求正文</span><span class="sxs-lookup"><span data-stu-id="67867-134">Request body</span></span>

<span data-ttu-id="67867-135">Empty</span><span class="sxs-lookup"><span data-stu-id="67867-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="67867-136">响应</span><span class="sxs-lookup"><span data-stu-id="67867-136">Response</span></span>

<span data-ttu-id="67867-137">如果成功，此方法返回 200 正常响应代码，该对象包含指向 value 属性中的命令 *结果* 的链接。</span><span class="sxs-lookup"><span data-stu-id="67867-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="67867-138">此链接的有效期为 30 分钟，应该立即用于将程序包下载到本地存储。</span><span class="sxs-lookup"><span data-stu-id="67867-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="67867-139">另一个调用可以重新创建已过期的链接，并且无需再次运行实时响应。</span><span class="sxs-lookup"><span data-stu-id="67867-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="67867-140">*Runscript 脚本属性：*</span><span class="sxs-lookup"><span data-stu-id="67867-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="67867-141">属性</span><span class="sxs-lookup"><span data-stu-id="67867-141">Property</span></span>  | <span data-ttu-id="67867-142">说明</span><span class="sxs-lookup"><span data-stu-id="67867-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="67867-143">name</span><span class="sxs-lookup"><span data-stu-id="67867-143">name</span></span>          | <span data-ttu-id="67867-144">已执行的脚本名称</span><span class="sxs-lookup"><span data-stu-id="67867-144">Executed script name</span></span>                  |
| <span data-ttu-id="67867-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="67867-145">exit_code</span></span>     | <span data-ttu-id="67867-146">已执行的脚本退出代码</span><span class="sxs-lookup"><span data-stu-id="67867-146">Executed script exit code</span></span>             |
| <span data-ttu-id="67867-147">script_output</span><span class="sxs-lookup"><span data-stu-id="67867-147">script_output</span></span> | <span data-ttu-id="67867-148">已执行的脚本标准输出</span><span class="sxs-lookup"><span data-stu-id="67867-148">Executed script standard output</span></span>       |
| <span data-ttu-id="67867-149">script_error</span><span class="sxs-lookup"><span data-stu-id="67867-149">script_error</span></span>  | <span data-ttu-id="67867-150">已执行的脚本标准错误输出</span><span class="sxs-lookup"><span data-stu-id="67867-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="67867-151">示例</span><span class="sxs-lookup"><span data-stu-id="67867-151">Example</span></span>

<span data-ttu-id="67867-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="67867-152">**Request**</span></span>

<span data-ttu-id="67867-153">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="67867-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="67867-154">**响应**</span><span class="sxs-lookup"><span data-stu-id="67867-154">**Response**</span></span>

<span data-ttu-id="67867-155">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="67867-155">Here is an example of the response.</span></span>

<span data-ttu-id="67867-156">HTTP/1.1 200 正常</span><span class="sxs-lookup"><span data-stu-id="67867-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="67867-157">Content-type： application/json</span><span class="sxs-lookup"><span data-stu-id="67867-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="67867-158">*文件内容：*</span><span class="sxs-lookup"><span data-stu-id="67867-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="67867-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="67867-159">Related topics</span></span>

- [<span data-ttu-id="67867-160">获取计算机操作 API</span><span class="sxs-lookup"><span data-stu-id="67867-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="67867-161">取消计算机操作</span><span class="sxs-lookup"><span data-stu-id="67867-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="67867-162">运行实时响应</span><span class="sxs-lookup"><span data-stu-id="67867-162">Run live response</span></span>](run-live-response.md) 
