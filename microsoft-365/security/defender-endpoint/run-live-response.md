---
title: 在设备上运行实时响应命令
description: 了解如何在设备上运行实时响应命令序列。
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879652"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="575a1-104">在设备上运行实时响应命令</span><span class="sxs-lookup"><span data-stu-id="575a1-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="575a1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="575a1-105">**Applies to:**</span></span>
- [<span data-ttu-id="575a1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="575a1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="575a1-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="575a1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="575a1-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="575a1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="575a1-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="575a1-109">API description</span></span>

<span data-ttu-id="575a1-110">在设备上运行一系列实时响应命令</span><span class="sxs-lookup"><span data-stu-id="575a1-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="575a1-111">限制</span><span class="sxs-lookup"><span data-stu-id="575a1-111">Limitations</span></span>

1.  <span data-ttu-id="575a1-112">此 API 的速率限制是每分钟 10 次调用 (HTTP 429 请求响应) 。</span><span class="sxs-lookup"><span data-stu-id="575a1-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="575a1-113">25 个并发运行的 (超过限制的请求将收到"429 - 请求过多"响应) 。</span><span class="sxs-lookup"><span data-stu-id="575a1-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="575a1-114">如果计算机不可用，会话将排入队列最多 3 天。</span><span class="sxs-lookup"><span data-stu-id="575a1-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="575a1-115">RunScript 命令在 10 分钟后超时。</span><span class="sxs-lookup"><span data-stu-id="575a1-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="575a1-116">当实时响应命令失败时，将不会执行所有关注的操作。</span><span class="sxs-lookup"><span data-stu-id="575a1-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="575a1-117">权限</span><span class="sxs-lookup"><span data-stu-id="575a1-117">Permissions</span></span>

<span data-ttu-id="575a1-118">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="575a1-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="575a1-119">若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="575a1-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="575a1-120">权限类型</span><span class="sxs-lookup"><span data-stu-id="575a1-120">Permission type</span></span>                    | <span data-ttu-id="575a1-121">权限</span><span class="sxs-lookup"><span data-stu-id="575a1-121">Permission</span></span>           | <span data-ttu-id="575a1-122">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="575a1-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="575a1-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="575a1-123">Application</span></span>                        | <span data-ttu-id="575a1-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="575a1-124">Machine.LiveResponse</span></span> | <span data-ttu-id="575a1-125">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="575a1-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="575a1-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="575a1-126">Delegated (work or school account)</span></span> | <span data-ttu-id="575a1-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="575a1-127">Machine.LiveResponse</span></span> | <span data-ttu-id="575a1-128">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="575a1-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="575a1-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="575a1-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="575a1-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="575a1-130">Request headers</span></span>

| <span data-ttu-id="575a1-131">名称</span><span class="sxs-lookup"><span data-stu-id="575a1-131">Name</span></span>      | <span data-ttu-id="575a1-132">类型</span><span class="sxs-lookup"><span data-stu-id="575a1-132">Type</span></span> | <span data-ttu-id="575a1-133">说明</span><span class="sxs-lookup"><span data-stu-id="575a1-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="575a1-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="575a1-134">Authorization</span></span> | <span data-ttu-id="575a1-135">String</span><span class="sxs-lookup"><span data-stu-id="575a1-135">String</span></span>   | <span data-ttu-id="575a1-136">Bearer\<token>\.</span><span class="sxs-lookup"><span data-stu-id="575a1-136">Bearer\<token>\.</span></span> <span data-ttu-id="575a1-137">必填。</span><span class="sxs-lookup"><span data-stu-id="575a1-137">Required.</span></span>   |
| <span data-ttu-id="575a1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="575a1-138">Content-Type</span></span>  | <span data-ttu-id="575a1-139">string</span><span class="sxs-lookup"><span data-stu-id="575a1-139">string</span></span>   | <span data-ttu-id="575a1-p104">application/json. Required.</span><span class="sxs-lookup"><span data-stu-id="575a1-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="575a1-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="575a1-142">Request body</span></span>

| <span data-ttu-id="575a1-143">参数</span><span class="sxs-lookup"><span data-stu-id="575a1-143">Parameter</span></span> | <span data-ttu-id="575a1-144">类型</span><span class="sxs-lookup"><span data-stu-id="575a1-144">Type</span></span> | <span data-ttu-id="575a1-145">说明</span><span class="sxs-lookup"><span data-stu-id="575a1-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="575a1-146">评论</span><span class="sxs-lookup"><span data-stu-id="575a1-146">Comment</span></span>       | <span data-ttu-id="575a1-147">字符串</span><span class="sxs-lookup"><span data-stu-id="575a1-147">String</span></span>   | <span data-ttu-id="575a1-148">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="575a1-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="575a1-149">命令</span><span class="sxs-lookup"><span data-stu-id="575a1-149">Commands</span></span>      | <span data-ttu-id="575a1-150">数组</span><span class="sxs-lookup"><span data-stu-id="575a1-150">Array</span></span>    | <span data-ttu-id="575a1-151">要运行的命令。</span><span class="sxs-lookup"><span data-stu-id="575a1-151">Commands to run.</span></span> <span data-ttu-id="575a1-152">允许的值为 PutFile、RunScript、GetFile。</span><span class="sxs-lookup"><span data-stu-id="575a1-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="575a1-153">命令：</span><span class="sxs-lookup"><span data-stu-id="575a1-153">Commands:</span></span>

| <span data-ttu-id="575a1-154">命令类型</span><span class="sxs-lookup"><span data-stu-id="575a1-154">Command Type</span></span> | <span data-ttu-id="575a1-155">参数</span><span class="sxs-lookup"><span data-stu-id="575a1-155">Parameters</span></span>                                                                          | <span data-ttu-id="575a1-156">说明</span><span class="sxs-lookup"><span data-stu-id="575a1-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="575a1-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="575a1-157">PutFile</span></span>      | <span data-ttu-id="575a1-158">项：FileName</span><span class="sxs-lookup"><span data-stu-id="575a1-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="575a1-159">值：\<file name\></span><span class="sxs-lookup"><span data-stu-id="575a1-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="575a1-160">将库中的文件置于设备。</span><span class="sxs-lookup"><span data-stu-id="575a1-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="575a1-161">文件保存在工作文件夹中，在设备默认重启时将被删除。</span><span class="sxs-lookup"><span data-stu-id="575a1-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="575a1-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="575a1-162">RunScript</span></span>    | <span data-ttu-id="575a1-163">键：ScriptName</span><span class="sxs-lookup"><span data-stu-id="575a1-163">Key: ScriptName</span></span><br><span data-ttu-id="575a1-164">值：\<Script from library\></span><span class="sxs-lookup"><span data-stu-id="575a1-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="575a1-165">键：Args</span><span class="sxs-lookup"><span data-stu-id="575a1-165">Key: Args</span></span>  <br> <span data-ttu-id="575a1-166">值：\<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="575a1-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="575a1-167">在设备上从库中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="575a1-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="575a1-168">Args 参数将传递给您的脚本。</span><span class="sxs-lookup"><span data-stu-id="575a1-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="575a1-169">10 分钟后超时。</span><span class="sxs-lookup"><span data-stu-id="575a1-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="575a1-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="575a1-170">GetFile</span></span>      | <span data-ttu-id="575a1-171">键：路径</span><span class="sxs-lookup"><span data-stu-id="575a1-171">Key: Path</span></span> <br> <span data-ttu-id="575a1-172">值：\<File path\></span><span class="sxs-lookup"><span data-stu-id="575a1-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="575a1-173">从设备收集文件。</span><span class="sxs-lookup"><span data-stu-id="575a1-173">Collect file from a device.</span></span> <span data-ttu-id="575a1-174">注意：路径中的反杠必须转义。</span><span class="sxs-lookup"><span data-stu-id="575a1-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="575a1-175">响应</span><span class="sxs-lookup"><span data-stu-id="575a1-175">Response</span></span>

-   <span data-ttu-id="575a1-176">如果成功，此方法返回 200，确定。</span><span class="sxs-lookup"><span data-stu-id="575a1-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="575a1-177">Action 实体。</span><span class="sxs-lookup"><span data-stu-id="575a1-177">Action entity.</span></span> <span data-ttu-id="575a1-178">如果未找到具有指定 ID 的机器 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="575a1-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="575a1-179">示例</span><span class="sxs-lookup"><span data-stu-id="575a1-179">Example</span></span>

<span data-ttu-id="575a1-180">**请求**</span><span class="sxs-lookup"><span data-stu-id="575a1-180">**Request**</span></span>

<span data-ttu-id="575a1-181">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="575a1-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="575a1-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="575a1-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="575a1-183">**响应**</span><span class="sxs-lookup"><span data-stu-id="575a1-183">**Response**</span></span>

<span data-ttu-id="575a1-184">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="575a1-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="575a1-185">Content-type： application/json</span><span class="sxs-lookup"><span data-stu-id="575a1-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="575a1-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="575a1-186">Related topics</span></span>
- [<span data-ttu-id="575a1-187">获取计算机操作 API</span><span class="sxs-lookup"><span data-stu-id="575a1-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="575a1-188">获取实时响应结果</span><span class="sxs-lookup"><span data-stu-id="575a1-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="575a1-189">取消计算机操作</span><span class="sxs-lookup"><span data-stu-id="575a1-189">Cancel machine action</span></span>](cancel-machine-action.md)
