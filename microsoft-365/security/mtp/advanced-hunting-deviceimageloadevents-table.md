---
title: 高级搜寻架构中的 DeviceImageLoadEvents 表
description: 了解高级搜寻架构的 DeviceImageLoadEvents 表中的 DLL 加载事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、imageloadevents、DeviceImageLoadEvents、DLL 加载、库、文件图像
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 98aac3d231e2c8630cb4721ee8012054ab90feef
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617136"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="5de04-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="5de04-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="5de04-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5de04-105">**Applies to:**</span></span>
- <span data-ttu-id="5de04-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5de04-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5de04-107">`DeviceImageLoadEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 DLL 加载事件的信息。</span><span class="sxs-lookup"><span data-stu-id="5de04-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="5de04-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="5de04-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5de04-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5de04-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5de04-110">列名称</span><span class="sxs-lookup"><span data-stu-id="5de04-110">Column name</span></span> | <span data-ttu-id="5de04-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="5de04-111">Data type</span></span> | <span data-ttu-id="5de04-112">说明</span><span class="sxs-lookup"><span data-stu-id="5de04-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5de04-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5de04-113">datetime</span></span> | <span data-ttu-id="5de04-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5de04-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5de04-115">string</span><span class="sxs-lookup"><span data-stu-id="5de04-115">string</span></span> | <span data-ttu-id="5de04-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="5de04-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5de04-117">string</span><span class="sxs-lookup"><span data-stu-id="5de04-117">string</span></span> | <span data-ttu-id="5de04-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5de04-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="5de04-119">string</span><span class="sxs-lookup"><span data-stu-id="5de04-119">string</span></span> | <span data-ttu-id="5de04-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="5de04-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="5de04-121">string</span><span class="sxs-lookup"><span data-stu-id="5de04-121">string</span></span> | <span data-ttu-id="5de04-122">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="5de04-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="5de04-123">string</span><span class="sxs-lookup"><span data-stu-id="5de04-123">string</span></span> | <span data-ttu-id="5de04-124">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="5de04-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="5de04-125">string</span><span class="sxs-lookup"><span data-stu-id="5de04-125">string</span></span> | <span data-ttu-id="5de04-126">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5de04-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="5de04-127">string</span><span class="sxs-lookup"><span data-stu-id="5de04-127">string</span></span> | <span data-ttu-id="5de04-128">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="5de04-128">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="5de04-129">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="5de04-129">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="5de04-130">string</span><span class="sxs-lookup"><span data-stu-id="5de04-130">string</span></span> | <span data-ttu-id="5de04-131">将录制的操作应用于的文件的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="5de04-131">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="5de04-132">string</span><span class="sxs-lookup"><span data-stu-id="5de04-132">string</span></span> | <span data-ttu-id="5de04-133">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="5de04-133">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="5de04-134">string</span><span class="sxs-lookup"><span data-stu-id="5de04-134">string</span></span> | <span data-ttu-id="5de04-135">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="5de04-135">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="5de04-136">string</span><span class="sxs-lookup"><span data-stu-id="5de04-136">string</span></span> | <span data-ttu-id="5de04-137">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="5de04-137">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="5de04-138">string</span><span class="sxs-lookup"><span data-stu-id="5de04-138">string</span></span> | <span data-ttu-id="5de04-139">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="5de04-139">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="5de04-140">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="5de04-140">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="5de04-141">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="5de04-141">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="5de04-142">string</span><span class="sxs-lookup"><span data-stu-id="5de04-142">string</span></span> | <span data-ttu-id="5de04-143">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="5de04-143">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="5de04-144">string</span><span class="sxs-lookup"><span data-stu-id="5de04-144">string</span></span> | <span data-ttu-id="5de04-145">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5de04-145">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="5de04-146">string</span><span class="sxs-lookup"><span data-stu-id="5de04-146">string</span></span> | <span data-ttu-id="5de04-147">SHA-256，其中启动了事件的进程（图像文件）。</span><span class="sxs-lookup"><span data-stu-id="5de04-147">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="5de04-148">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="5de04-148">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="5de04-149">string</span><span class="sxs-lookup"><span data-stu-id="5de04-149">string</span></span> | <span data-ttu-id="5de04-150">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="5de04-150">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="5de04-151">string</span><span class="sxs-lookup"><span data-stu-id="5de04-151">string</span></span> | <span data-ttu-id="5de04-152">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="5de04-152">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="5de04-153">int</span><span class="sxs-lookup"><span data-stu-id="5de04-153">int</span></span> | <span data-ttu-id="5de04-154">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="5de04-154">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="5de04-155">string</span><span class="sxs-lookup"><span data-stu-id="5de04-155">string</span></span> | <span data-ttu-id="5de04-156">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="5de04-156">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="5de04-157">datetime</span><span class="sxs-lookup"><span data-stu-id="5de04-157">datetime</span></span> | <span data-ttu-id="5de04-158">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5de04-158">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="5de04-159">string</span><span class="sxs-lookup"><span data-stu-id="5de04-159">string</span></span> | <span data-ttu-id="5de04-160">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="5de04-160">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="5de04-161">int</span><span class="sxs-lookup"><span data-stu-id="5de04-161">int</span></span> | <span data-ttu-id="5de04-162">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="5de04-162">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="5de04-163">string</span><span class="sxs-lookup"><span data-stu-id="5de04-163">string</span></span> | <span data-ttu-id="5de04-164">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="5de04-164">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="5de04-165">datetime</span><span class="sxs-lookup"><span data-stu-id="5de04-165">datetime</span></span> | <span data-ttu-id="5de04-166">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5de04-166">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="5de04-167">long</span><span class="sxs-lookup"><span data-stu-id="5de04-167">long</span></span> | <span data-ttu-id="5de04-168">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="5de04-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5de04-169">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="5de04-169">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="5de04-170">string</span><span class="sxs-lookup"><span data-stu-id="5de04-170">string</span></span> | <span data-ttu-id="5de04-171">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="5de04-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5de04-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="5de04-172">Related topics</span></span>
- [<span data-ttu-id="5de04-173">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="5de04-173">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5de04-174">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5de04-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5de04-175">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="5de04-175">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5de04-176">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="5de04-176">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5de04-177">了解架构</span><span class="sxs-lookup"><span data-stu-id="5de04-177">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5de04-178">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="5de04-178">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
