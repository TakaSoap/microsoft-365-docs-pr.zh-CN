---
title: 高级搜寻架构中的 DeviceImageLoadEvents 表
description: 了解高级搜寻架构的 DeviceImageLoadEvents 表中的 DLL 加载事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、imageloadevents、DeviceImageLoadEvents、DLL 加载库、文件图像
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d2ff86977343aac1fdb5c201e3eb786bf968e545
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210454"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="9cbf4-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="9cbf4-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="9cbf4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9cbf4-105">**Applies to:**</span></span>
- <span data-ttu-id="9cbf4-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9cbf4-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9cbf4-107">`DeviceImageLoadEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 DLL 加载事件的信息。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="9cbf4-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9cbf4-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9cbf4-110">列名称</span><span class="sxs-lookup"><span data-stu-id="9cbf4-110">Column name</span></span> | <span data-ttu-id="9cbf4-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="9cbf4-111">Data type</span></span> | <span data-ttu-id="9cbf4-112">说明</span><span class="sxs-lookup"><span data-stu-id="9cbf4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9cbf4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9cbf4-113">datetime</span></span> | <span data-ttu-id="9cbf4-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="9cbf4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9cbf4-115">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-115">string</span></span> | <span data-ttu-id="9cbf4-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="9cbf4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9cbf4-117">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-117">string</span></span> | <span data-ttu-id="9cbf4-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9cbf4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="9cbf4-119">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-119">string</span></span> | <span data-ttu-id="9cbf4-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="9cbf4-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="9cbf4-121">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-121">string</span></span> | <span data-ttu-id="9cbf4-122">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="9cbf4-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="9cbf4-123">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-123">string</span></span> | <span data-ttu-id="9cbf4-124">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="9cbf4-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9cbf4-125">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-125">string</span></span> | <span data-ttu-id="9cbf4-126">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="9cbf4-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="9cbf4-127">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-127">string</span></span> | <span data-ttu-id="9cbf4-128">将录制的操作应用于的文件的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="9cbf4-128">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="9cbf4-129">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-129">string</span></span> | <span data-ttu-id="9cbf4-130">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="9cbf4-130">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="9cbf4-131">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-131">string</span></span> | <span data-ttu-id="9cbf4-132">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="9cbf4-132">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="9cbf4-133">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-133">string</span></span> | <span data-ttu-id="9cbf4-134">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="9cbf4-134">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="9cbf4-135">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-135">string</span></span> | <span data-ttu-id="9cbf4-136">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-136">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="9cbf4-137">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-137">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="9cbf4-138">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="9cbf4-138">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="9cbf4-139">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-139">string</span></span> | <span data-ttu-id="9cbf4-140">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="9cbf4-140">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="9cbf4-141">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-141">string</span></span> | <span data-ttu-id="9cbf4-142">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="9cbf4-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="9cbf4-143">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-143">string</span></span> | <span data-ttu-id="9cbf4-144">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="9cbf4-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="9cbf4-145">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-145">string</span></span> | <span data-ttu-id="9cbf4-146">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="9cbf4-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="9cbf4-147">int</span><span class="sxs-lookup"><span data-stu-id="9cbf4-147">int</span></span> | <span data-ttu-id="9cbf4-148">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="9cbf4-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="9cbf4-149">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-149">string</span></span> | <span data-ttu-id="9cbf4-150">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="9cbf4-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="9cbf4-151">datetime</span><span class="sxs-lookup"><span data-stu-id="9cbf4-151">datetime</span></span> | <span data-ttu-id="9cbf4-152">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="9cbf4-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="9cbf4-153">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-153">string</span></span> | <span data-ttu-id="9cbf4-154">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="9cbf4-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="9cbf4-155">int</span><span class="sxs-lookup"><span data-stu-id="9cbf4-155">int</span></span> | <span data-ttu-id="9cbf4-156">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="9cbf4-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="9cbf4-157">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-157">string</span></span> | <span data-ttu-id="9cbf4-158">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="9cbf4-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="9cbf4-159">datetime</span><span class="sxs-lookup"><span data-stu-id="9cbf4-159">datetime</span></span> | <span data-ttu-id="9cbf4-160">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="9cbf4-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="9cbf4-161">long</span><span class="sxs-lookup"><span data-stu-id="9cbf4-161">long</span></span> | <span data-ttu-id="9cbf4-162">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="9cbf4-162">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9cbf4-163">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="9cbf4-163">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="9cbf4-164">string</span><span class="sxs-lookup"><span data-stu-id="9cbf4-164">string</span></span> | <span data-ttu-id="9cbf4-165">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="9cbf4-165">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9cbf4-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="9cbf4-166">Related topics</span></span>
- [<span data-ttu-id="9cbf4-167">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="9cbf4-167">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9cbf4-168">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="9cbf4-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9cbf4-169">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="9cbf4-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9cbf4-170">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="9cbf4-170">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9cbf4-171">了解架构</span><span class="sxs-lookup"><span data-stu-id="9cbf4-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9cbf4-172">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="9cbf4-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
