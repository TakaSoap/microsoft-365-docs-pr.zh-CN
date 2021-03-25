---
title: machineAction 资源类型
description: 了解 Microsoft Defender for Endpoint 中 MachineAction 资源类型的方法和属性。
keywords: api， 受支持的 api， 获取， machineaction， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187378"
---
# <a name="machineaction-resource-type"></a><span data-ttu-id="44eb5-104">MachineAction 资源类型</span><span class="sxs-lookup"><span data-stu-id="44eb5-104">MachineAction resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44eb5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="44eb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="44eb5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="44eb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="44eb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44eb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="44eb5-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="44eb5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44eb5-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="44eb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="44eb5-110">有关详细信息，请参阅响应 [操作](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="44eb5-110">For more information, see [Response Actions](respond-machine-alerts.md).</span></span> 

| <span data-ttu-id="44eb5-111">方法</span><span class="sxs-lookup"><span data-stu-id="44eb5-111">Method</span></span>                                                            | <span data-ttu-id="44eb5-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="44eb5-112">Return Type</span></span>                        | <span data-ttu-id="44eb5-113">说明</span><span class="sxs-lookup"><span data-stu-id="44eb5-113">Description</span></span>                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [<span data-ttu-id="44eb5-114">列出 MachineActions</span><span class="sxs-lookup"><span data-stu-id="44eb5-114">List MachineActions</span></span>](get-machineactions-collection.md)           | [<span data-ttu-id="44eb5-115">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-115">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-116">列出 [计算机操作](machineaction.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="44eb5-116">List [Machine Action](machineaction.md) entities.</span></span>           |
| [<span data-ttu-id="44eb5-117">获取 MachineAction</span><span class="sxs-lookup"><span data-stu-id="44eb5-117">Get MachineAction</span></span>](get-machineaction-object.md)                  | [<span data-ttu-id="44eb5-118">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-118">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-119">获取单个 [Machine Action](machineaction.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="44eb5-119">Get a single [Machine Action](machineaction.md) entity.</span></span>     |
| [<span data-ttu-id="44eb5-120">收集调查包</span><span class="sxs-lookup"><span data-stu-id="44eb5-120">Collect investigation package</span></span>](collect-investigation-package.md) | [<span data-ttu-id="44eb5-121">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-121">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-122">从计算机收集调查 [包](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="44eb5-122">Collect investigation package from a [machine](machine.md).</span></span> |
| [<span data-ttu-id="44eb5-123">获取调查包 SAS URI</span><span class="sxs-lookup"><span data-stu-id="44eb5-123">Get investigation package SAS URI</span></span>](get-package-sas-uri.md)       | [<span data-ttu-id="44eb5-124">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-124">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-125">获取用于下载调查包的 URI。</span><span class="sxs-lookup"><span data-stu-id="44eb5-125">Get URI for downloading the investigation package.</span></span>          |
| [<span data-ttu-id="44eb5-126">隔离计算机</span><span class="sxs-lookup"><span data-stu-id="44eb5-126">Isolate machine</span></span>](isolate-machine.md)                             | [<span data-ttu-id="44eb5-127">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-127">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-128">将 [计算机](machine.md) 与网络隔离。</span><span class="sxs-lookup"><span data-stu-id="44eb5-128">Isolate [machine](machine.md) from network.</span></span>                 |
| [<span data-ttu-id="44eb5-129">解除计算机隔离</span><span class="sxs-lookup"><span data-stu-id="44eb5-129">Release machine from isolation</span></span>](unisolate-machine.md)            | [<span data-ttu-id="44eb5-130">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-130">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-131">解除 [计算机](machine.md) 隔离。</span><span class="sxs-lookup"><span data-stu-id="44eb5-131">Release [machine](machine.md) from Isolation.</span></span>               |
| [<span data-ttu-id="44eb5-132">限制应用执行</span><span class="sxs-lookup"><span data-stu-id="44eb5-132">Restrict app execution</span></span>](restrict-code-execution.md)              | [<span data-ttu-id="44eb5-133">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-133">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-134">限制应用程序执行。</span><span class="sxs-lookup"><span data-stu-id="44eb5-134">Restrict application execution.</span></span>                             |
| [<span data-ttu-id="44eb5-135">删除应用限制</span><span class="sxs-lookup"><span data-stu-id="44eb5-135">Remove app restriction</span></span>](unrestrict-code-execution.md)            | [<span data-ttu-id="44eb5-136">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-136">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-137">删除应用程序执行限制。</span><span class="sxs-lookup"><span data-stu-id="44eb5-137">Remove application execution restriction.</span></span>                   |
| [<span data-ttu-id="44eb5-138">运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="44eb5-138">Run antivirus scan</span></span>](run-av-scan.md)                              | [<span data-ttu-id="44eb5-139">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-139">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-140">如果适用，请Windows Defender (AV) 。</span><span class="sxs-lookup"><span data-stu-id="44eb5-140">Run an AV scan using Windows Defender (when applicable).</span></span>    |
| [<span data-ttu-id="44eb5-141">载出计算机</span><span class="sxs-lookup"><span data-stu-id="44eb5-141">Offboard machine</span></span>](offboard-machine-api.md)                       | [<span data-ttu-id="44eb5-142">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-142">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-143">从 Microsoft Defender [for](machine.md) Endpoint 载出计算机。</span><span class="sxs-lookup"><span data-stu-id="44eb5-143">Offboard [machine](machine.md) from Microsoft Defender for Endpoint.</span></span> |
| [<span data-ttu-id="44eb5-144">停止和隔离文件</span><span class="sxs-lookup"><span data-stu-id="44eb5-144">Stop and quarantine file</span></span>](stop-and-quarantine-file.md)           | [<span data-ttu-id="44eb5-145">计算机操作</span><span class="sxs-lookup"><span data-stu-id="44eb5-145">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="44eb5-146">停止执行计算机上的文件并将其删除。</span><span class="sxs-lookup"><span data-stu-id="44eb5-146">Stop execution of a file on a machine and delete it.</span></span>        |

<br>

## <a name="properties"></a><span data-ttu-id="44eb5-147">属性</span><span class="sxs-lookup"><span data-stu-id="44eb5-147">Properties</span></span>

| <span data-ttu-id="44eb5-148">属性</span><span class="sxs-lookup"><span data-stu-id="44eb5-148">Property</span></span>            | <span data-ttu-id="44eb5-149">类型</span><span class="sxs-lookup"><span data-stu-id="44eb5-149">Type</span></span>           | <span data-ttu-id="44eb5-150">说明</span><span class="sxs-lookup"><span data-stu-id="44eb5-150">Description</span></span>                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="44eb5-151">ID</span><span class="sxs-lookup"><span data-stu-id="44eb5-151">ID</span></span>                  | <span data-ttu-id="44eb5-152">Guid</span><span class="sxs-lookup"><span data-stu-id="44eb5-152">Guid</span></span>           | <span data-ttu-id="44eb5-153">计算机 [操作实体的](machineaction.md) 标识。</span><span class="sxs-lookup"><span data-stu-id="44eb5-153">Identity of the [Machine Action](machineaction.md) entity.</span></span>                                                                                                                                                     |
| <span data-ttu-id="44eb5-154">type</span><span class="sxs-lookup"><span data-stu-id="44eb5-154">type</span></span>                | <span data-ttu-id="44eb5-155">枚举</span><span class="sxs-lookup"><span data-stu-id="44eb5-155">Enum</span></span>           | <span data-ttu-id="44eb5-156">操作的类型。</span><span class="sxs-lookup"><span data-stu-id="44eb5-156">Type of the action.</span></span> <span data-ttu-id="44eb5-157">可能的值包括："RunAntiVirusScan"、"Offboard"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"和"UnrestrictCodeExecution"</span><span class="sxs-lookup"><span data-stu-id="44eb5-157">Possible values are: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" and "UnrestrictCodeExecution"</span></span> |
| <span data-ttu-id="44eb5-158">scope</span><span class="sxs-lookup"><span data-stu-id="44eb5-158">scope</span></span>               | <span data-ttu-id="44eb5-159">string</span><span class="sxs-lookup"><span data-stu-id="44eb5-159">string</span></span>         | <span data-ttu-id="44eb5-160">操作的范围。</span><span class="sxs-lookup"><span data-stu-id="44eb5-160">Scope of the action.</span></span> <span data-ttu-id="44eb5-161">"完全"或"选择性"用于隔离，"快速"或"完全"用于防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="44eb5-161">"Full" or "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.</span></span>                                                                                                   |
| <span data-ttu-id="44eb5-162">requestor</span><span class="sxs-lookup"><span data-stu-id="44eb5-162">requestor</span></span>           | <span data-ttu-id="44eb5-163">String</span><span class="sxs-lookup"><span data-stu-id="44eb5-163">String</span></span>         | <span data-ttu-id="44eb5-164">执行该操作的人的身份。</span><span class="sxs-lookup"><span data-stu-id="44eb5-164">Identity of the person that executed the action.</span></span>                                                                                                                                                               |
| <span data-ttu-id="44eb5-165">requestorComment</span><span class="sxs-lookup"><span data-stu-id="44eb5-165">requestorComment</span></span>    | <span data-ttu-id="44eb5-166">String</span><span class="sxs-lookup"><span data-stu-id="44eb5-166">String</span></span>         | <span data-ttu-id="44eb5-167">发出操作时写入的注释。</span><span class="sxs-lookup"><span data-stu-id="44eb5-167">Comment that was written when issuing the action.</span></span>                                                                                                                                                              |
| <span data-ttu-id="44eb5-168">状态</span><span class="sxs-lookup"><span data-stu-id="44eb5-168">status</span></span>              | <span data-ttu-id="44eb5-169">枚举</span><span class="sxs-lookup"><span data-stu-id="44eb5-169">Enum</span></span>           | <span data-ttu-id="44eb5-170">命令的当前状态。</span><span class="sxs-lookup"><span data-stu-id="44eb5-170">Current status of the command.</span></span> <span data-ttu-id="44eb5-171">可能的值包括："Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"和"Canceled"。</span><span class="sxs-lookup"><span data-stu-id="44eb5-171">Possible values are: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" and "Canceled".</span></span>                                                                                 |
| <span data-ttu-id="44eb5-172">machineId</span><span class="sxs-lookup"><span data-stu-id="44eb5-172">machineId</span></span>           | <span data-ttu-id="44eb5-173">String</span><span class="sxs-lookup"><span data-stu-id="44eb5-173">String</span></span>         | <span data-ttu-id="44eb5-174">已 [执行](machine.md) 该操作的虚拟机的 ID。</span><span class="sxs-lookup"><span data-stu-id="44eb5-174">ID of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                              |
| <span data-ttu-id="44eb5-175">machineId</span><span class="sxs-lookup"><span data-stu-id="44eb5-175">machineId</span></span>           | <span data-ttu-id="44eb5-176">String</span><span class="sxs-lookup"><span data-stu-id="44eb5-176">String</span></span>         | <span data-ttu-id="44eb5-177">已 [执行](machine.md) 该操作计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="44eb5-177">Name of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                            |
| <span data-ttu-id="44eb5-178">creationDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="44eb5-178">creationDateTimeUtc</span></span> | <span data-ttu-id="44eb5-179">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="44eb5-179">DateTimeOffset</span></span> | <span data-ttu-id="44eb5-180">创建该操作的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="44eb5-180">The date and time when the action was created.</span></span>                                                                                                                                                                 |
| <span data-ttu-id="44eb5-181">lastUpdateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="44eb5-181">lastUpdateTimeUtc</span></span>   | <span data-ttu-id="44eb5-182">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="44eb5-182">DateTimeOffset</span></span> | <span data-ttu-id="44eb5-183">上次更新操作状态的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="44eb5-183">The last date and time when the action status was updated.</span></span>                                                                                                                                                     |
| <span data-ttu-id="44eb5-184">relatedFileInfo</span><span class="sxs-lookup"><span data-stu-id="44eb5-184">relatedFileInfo</span></span>     | <span data-ttu-id="44eb5-185">类</span><span class="sxs-lookup"><span data-stu-id="44eb5-185">Class</span></span>          | <span data-ttu-id="44eb5-186">包含两个属性。</span><span class="sxs-lookup"><span data-stu-id="44eb5-186">Contains two Properties.</span></span> <span data-ttu-id="44eb5-187">string ```fileIdentifier``` ```fileIdentifierType``` ，Enum，可能的值："Sha1"、"Sha256"和"Md5"。</span><span class="sxs-lookup"><span data-stu-id="44eb5-187">string ```fileIdentifier```, Enum ```fileIdentifierType``` with the possible values: "Sha1", "Sha256" and "Md5".</span></span>                                                                         |


## <a name="json-representation"></a><span data-ttu-id="44eb5-188">Json 表示形式</span><span class="sxs-lookup"><span data-stu-id="44eb5-188">Json representation</span></span>

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
