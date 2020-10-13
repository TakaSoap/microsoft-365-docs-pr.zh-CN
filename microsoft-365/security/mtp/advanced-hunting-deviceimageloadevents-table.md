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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: adcfe0bb3cf42c5890e6ccc063bbaf3ba21827af
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431095"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="0da91-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="0da91-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0da91-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0da91-105">**Applies to:**</span></span>
- <span data-ttu-id="0da91-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="0da91-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="0da91-107">`DeviceImageLoadEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 DLL 加载事件的信息。</span><span class="sxs-lookup"><span data-stu-id="0da91-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="0da91-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="0da91-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0da91-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="0da91-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0da91-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0da91-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0da91-111">列名称</span><span class="sxs-lookup"><span data-stu-id="0da91-111">Column name</span></span> | <span data-ttu-id="0da91-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="0da91-112">Data type</span></span> | <span data-ttu-id="0da91-113">说明</span><span class="sxs-lookup"><span data-stu-id="0da91-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0da91-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0da91-114">datetime</span></span> | <span data-ttu-id="0da91-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="0da91-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0da91-116">string</span><span class="sxs-lookup"><span data-stu-id="0da91-116">string</span></span> | <span data-ttu-id="0da91-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="0da91-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0da91-118">string</span><span class="sxs-lookup"><span data-stu-id="0da91-118">string</span></span> | <span data-ttu-id="0da91-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0da91-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="0da91-120">string</span><span class="sxs-lookup"><span data-stu-id="0da91-120">string</span></span> | <span data-ttu-id="0da91-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="0da91-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="0da91-122">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0da91-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="0da91-123">string</span><span class="sxs-lookup"><span data-stu-id="0da91-123">string</span></span> | <span data-ttu-id="0da91-124">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="0da91-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0da91-125">string</span><span class="sxs-lookup"><span data-stu-id="0da91-125">string</span></span> | <span data-ttu-id="0da91-126">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="0da91-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="0da91-127">string</span><span class="sxs-lookup"><span data-stu-id="0da91-127">string</span></span> | <span data-ttu-id="0da91-128">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="0da91-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="0da91-129">string</span><span class="sxs-lookup"><span data-stu-id="0da91-129">string</span></span> | <span data-ttu-id="0da91-130">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="0da91-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="0da91-131">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="0da91-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="0da91-132">string</span><span class="sxs-lookup"><span data-stu-id="0da91-132">string</span></span> | <span data-ttu-id="0da91-133">将录制的操作应用于的文件的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="0da91-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="0da91-134">string</span><span class="sxs-lookup"><span data-stu-id="0da91-134">string</span></span> | <span data-ttu-id="0da91-135">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="0da91-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="0da91-136">string</span><span class="sxs-lookup"><span data-stu-id="0da91-136">string</span></span> | <span data-ttu-id="0da91-137">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="0da91-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="0da91-138">string</span><span class="sxs-lookup"><span data-stu-id="0da91-138">string</span></span> | <span data-ttu-id="0da91-139">运行负责事件的进程的帐户 (SID) 的安全标识符</span><span class="sxs-lookup"><span data-stu-id="0da91-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="0da91-140">string</span><span class="sxs-lookup"><span data-stu-id="0da91-140">string</span></span> | <span data-ttu-id="0da91-141">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="0da91-141">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="0da91-142">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="0da91-142">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="0da91-143">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="0da91-143">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="0da91-144">string</span><span class="sxs-lookup"><span data-stu-id="0da91-144">string</span></span> | <span data-ttu-id="0da91-145">指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动该事件的进程</span><span class="sxs-lookup"><span data-stu-id="0da91-145">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="0da91-146">string</span><span class="sxs-lookup"><span data-stu-id="0da91-146">string</span></span> | <span data-ttu-id="0da91-147">启动事件的过程 (图像文件) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="0da91-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="0da91-148">string</span><span class="sxs-lookup"><span data-stu-id="0da91-148">string</span></span> | <span data-ttu-id="0da91-149">SHA-256 启动事件的过程 (图像文件) 。</span><span class="sxs-lookup"><span data-stu-id="0da91-149">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="0da91-150">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="0da91-150">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="0da91-151">string</span><span class="sxs-lookup"><span data-stu-id="0da91-151">string</span></span> | <span data-ttu-id="0da91-152">启动事件的过程 (映像文件) 的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="0da91-152">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="0da91-153">string</span><span class="sxs-lookup"><span data-stu-id="0da91-153">string</span></span> | <span data-ttu-id="0da91-154">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="0da91-154">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="0da91-155">int</span><span class="sxs-lookup"><span data-stu-id="0da91-155">int</span></span> | <span data-ttu-id="0da91-156">启动事件的进程的进程 ID (PID) </span><span class="sxs-lookup"><span data-stu-id="0da91-156">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="0da91-157">string</span><span class="sxs-lookup"><span data-stu-id="0da91-157">string</span></span> | <span data-ttu-id="0da91-158">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="0da91-158">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="0da91-159">datetime</span><span class="sxs-lookup"><span data-stu-id="0da91-159">datetime</span></span> | <span data-ttu-id="0da91-160">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="0da91-160">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="0da91-161">string</span><span class="sxs-lookup"><span data-stu-id="0da91-161">string</span></span> | <span data-ttu-id="0da91-162">包含启动事件的过程 (图像文件) 的文件夹</span><span class="sxs-lookup"><span data-stu-id="0da91-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="0da91-163">int</span><span class="sxs-lookup"><span data-stu-id="0da91-163">int</span></span> | <span data-ttu-id="0da91-164">生成负责事件的进程的父进程 (PID) 的进程 ID</span><span class="sxs-lookup"><span data-stu-id="0da91-164">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="0da91-165">string</span><span class="sxs-lookup"><span data-stu-id="0da91-165">string</span></span> | <span data-ttu-id="0da91-166">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="0da91-166">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="0da91-167">datetime</span><span class="sxs-lookup"><span data-stu-id="0da91-167">datetime</span></span> | <span data-ttu-id="0da91-168">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="0da91-168">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="0da91-169">long</span><span class="sxs-lookup"><span data-stu-id="0da91-169">long</span></span> | <span data-ttu-id="0da91-170">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="0da91-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0da91-171">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="0da91-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="0da91-172">string</span><span class="sxs-lookup"><span data-stu-id="0da91-172">string</span></span> | <span data-ttu-id="0da91-173">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="0da91-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0da91-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="0da91-174">Related topics</span></span>
- [<span data-ttu-id="0da91-175">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0da91-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0da91-176">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="0da91-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0da91-177">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="0da91-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0da91-178">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="0da91-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0da91-179">了解架构</span><span class="sxs-lookup"><span data-stu-id="0da91-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0da91-180">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="0da91-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
