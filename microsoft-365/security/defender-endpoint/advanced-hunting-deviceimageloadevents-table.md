---
title: 高级搜寻架构中的 DeviceImageLoadEvents 表
description: 了解高级搜寻架构的 DeviceImageLoadEvents 表中的 DLL 加载事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， deviceimageloadevents， DLL 加载， 库， 文件图像， ImageLoadEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b47996da16b131d1739acd26519447b9167870ec
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498793"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="4e001-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="4e001-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4e001-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4e001-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e001-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e001-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="4e001-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4e001-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e001-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4e001-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="4e001-109">高级 `DeviceImageLoadEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关 DLL 加载事件的信息。</span><span class="sxs-lookup"><span data-stu-id="4e001-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="4e001-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="4e001-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="4e001-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="4e001-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="4e001-112">列名称</span><span class="sxs-lookup"><span data-stu-id="4e001-112">Column name</span></span> | <span data-ttu-id="4e001-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="4e001-113">Data type</span></span> | <span data-ttu-id="4e001-114">说明</span><span class="sxs-lookup"><span data-stu-id="4e001-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4e001-115">datetime</span><span class="sxs-lookup"><span data-stu-id="4e001-115">datetime</span></span> | <span data-ttu-id="4e001-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="4e001-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4e001-117">string</span><span class="sxs-lookup"><span data-stu-id="4e001-117">string</span></span> | <span data-ttu-id="4e001-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="4e001-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4e001-119">string</span><span class="sxs-lookup"><span data-stu-id="4e001-119">string</span></span> | <span data-ttu-id="4e001-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="4e001-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="4e001-121">string</span><span class="sxs-lookup"><span data-stu-id="4e001-121">string</span></span> | <span data-ttu-id="4e001-122">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="4e001-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="4e001-123">string</span><span class="sxs-lookup"><span data-stu-id="4e001-123">string</span></span> | <span data-ttu-id="4e001-124">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="4e001-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="4e001-125">string</span><span class="sxs-lookup"><span data-stu-id="4e001-125">string</span></span> | <span data-ttu-id="4e001-126">包含已记录操作所应用到的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="4e001-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="4e001-127">string</span><span class="sxs-lookup"><span data-stu-id="4e001-127">string</span></span> | <span data-ttu-id="4e001-128">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="4e001-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="4e001-129">string</span><span class="sxs-lookup"><span data-stu-id="4e001-129">string</span></span> | <span data-ttu-id="4e001-130">已记录操作所应用到的文件的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="4e001-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="4e001-131">string</span><span class="sxs-lookup"><span data-stu-id="4e001-131">string</span></span> | <span data-ttu-id="4e001-132">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="4e001-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="4e001-133">string</span><span class="sxs-lookup"><span data-stu-id="4e001-133">string</span></span> | <span data-ttu-id="4e001-134">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="4e001-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="4e001-135">string</span><span class="sxs-lookup"><span data-stu-id="4e001-135">string</span></span> | <span data-ttu-id="4e001-136">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="4e001-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="4e001-137">string</span><span class="sxs-lookup"><span data-stu-id="4e001-137">string</span></span> | <span data-ttu-id="4e001-138">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="4e001-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="4e001-139">Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。</span><span class="sxs-lookup"><span data-stu-id="4e001-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="4e001-140">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="4e001-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="4e001-141">string</span><span class="sxs-lookup"><span data-stu-id="4e001-141">string</span></span> | <span data-ttu-id="4e001-142">指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升</span><span class="sxs-lookup"><span data-stu-id="4e001-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="4e001-143">string</span><span class="sxs-lookup"><span data-stu-id="4e001-143">string</span></span> | <span data-ttu-id="4e001-144">启动事件 (映像) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="4e001-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="4e001-145">string</span><span class="sxs-lookup"><span data-stu-id="4e001-145">string</span></span> | <span data-ttu-id="4e001-146">启动事件的进程 (MD5) 文件哈希</span><span class="sxs-lookup"><span data-stu-id="4e001-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="4e001-147">string</span><span class="sxs-lookup"><span data-stu-id="4e001-147">string</span></span> | <span data-ttu-id="4e001-148">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="4e001-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="4e001-149">int</span><span class="sxs-lookup"><span data-stu-id="4e001-149">int</span></span> | <span data-ttu-id="4e001-150">进程 ID (PID) 启动事件的过程的 PID</span><span class="sxs-lookup"><span data-stu-id="4e001-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="4e001-151">string</span><span class="sxs-lookup"><span data-stu-id="4e001-151">string</span></span> | <span data-ttu-id="4e001-152">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="4e001-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="4e001-153">datetime</span><span class="sxs-lookup"><span data-stu-id="4e001-153">datetime</span></span> | <span data-ttu-id="4e001-154">启动事件的过程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="4e001-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="4e001-155">string</span><span class="sxs-lookup"><span data-stu-id="4e001-155">string</span></span> | <span data-ttu-id="4e001-156">包含启动事件 (进程) 文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="4e001-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="4e001-157">int</span><span class="sxs-lookup"><span data-stu-id="4e001-157">int</span></span> | <span data-ttu-id="4e001-158">进程 ID (PID) 生成负责事件的进程的父进程的 PID</span><span class="sxs-lookup"><span data-stu-id="4e001-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="4e001-159">string</span><span class="sxs-lookup"><span data-stu-id="4e001-159">string</span></span> | <span data-ttu-id="4e001-160">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="4e001-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="4e001-161">datetime</span><span class="sxs-lookup"><span data-stu-id="4e001-161">datetime</span></span> | <span data-ttu-id="4e001-162">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="4e001-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="4e001-163">long</span><span class="sxs-lookup"><span data-stu-id="4e001-163">long</span></span> | <span data-ttu-id="4e001-164">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="4e001-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4e001-165">若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用</span><span class="sxs-lookup"><span data-stu-id="4e001-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="4e001-166">string</span><span class="sxs-lookup"><span data-stu-id="4e001-166">string</span></span> | <span data-ttu-id="4e001-167">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="4e001-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4e001-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="4e001-168">Related topics</span></span>
- [<span data-ttu-id="4e001-169">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="4e001-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4e001-170">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="4e001-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4e001-171">了解架构</span><span class="sxs-lookup"><span data-stu-id="4e001-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
