---
title: 高级搜寻架构中的 DeviceImageLoadEvents 表
description: 了解高级搜寻架构的 DeviceImageLoadEvents 表中的 DLL 加载事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， imageloadevents， DeviceImageLoadEvents， DLL 加载， 库， 文件图像
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c2cc0fe7746c7574b427e3f546050ab4756fb525
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055275"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="6c695-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="6c695-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c695-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c695-105">**Applies to:**</span></span>
- <span data-ttu-id="6c695-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c695-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6c695-107">高级 `DeviceImageLoadEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关 DLL 加载事件的信息。</span><span class="sxs-lookup"><span data-stu-id="6c695-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="6c695-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6c695-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6c695-109">有关表支持的事件类型 () ，请使用安全中心中提供的内置架构 `ActionType` 参考。</span><span class="sxs-lookup"><span data-stu-id="6c695-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="6c695-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6c695-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6c695-111">列名称</span><span class="sxs-lookup"><span data-stu-id="6c695-111">Column name</span></span> | <span data-ttu-id="6c695-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="6c695-112">Data type</span></span> | <span data-ttu-id="6c695-113">说明</span><span class="sxs-lookup"><span data-stu-id="6c695-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6c695-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6c695-114">datetime</span></span> | <span data-ttu-id="6c695-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6c695-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6c695-116">string</span><span class="sxs-lookup"><span data-stu-id="6c695-116">string</span></span> | <span data-ttu-id="6c695-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6c695-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6c695-118">string</span><span class="sxs-lookup"><span data-stu-id="6c695-118">string</span></span> | <span data-ttu-id="6c695-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6c695-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="6c695-120">string</span><span class="sxs-lookup"><span data-stu-id="6c695-120">string</span></span> | <span data-ttu-id="6c695-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="6c695-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="6c695-122">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="6c695-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="6c695-123">string</span><span class="sxs-lookup"><span data-stu-id="6c695-123">string</span></span> | <span data-ttu-id="6c695-124">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="6c695-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6c695-125">string</span><span class="sxs-lookup"><span data-stu-id="6c695-125">string</span></span> | <span data-ttu-id="6c695-126">包含已记录操作所应用到的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="6c695-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6c695-127">string</span><span class="sxs-lookup"><span data-stu-id="6c695-127">string</span></span> | <span data-ttu-id="6c695-128">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="6c695-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="6c695-129">string</span><span class="sxs-lookup"><span data-stu-id="6c695-129">string</span></span> | <span data-ttu-id="6c695-130">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="6c695-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="6c695-131">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="6c695-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="6c695-132">string</span><span class="sxs-lookup"><span data-stu-id="6c695-132">string</span></span> | <span data-ttu-id="6c695-133">已记录操作所应用到的文件的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="6c695-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="6c695-134">string</span><span class="sxs-lookup"><span data-stu-id="6c695-134">string</span></span> | <span data-ttu-id="6c695-135">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="6c695-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="6c695-136">string</span><span class="sxs-lookup"><span data-stu-id="6c695-136">string</span></span> | <span data-ttu-id="6c695-137">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="6c695-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="6c695-138">string</span><span class="sxs-lookup"><span data-stu-id="6c695-138">string</span></span> | <span data-ttu-id="6c695-139">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="6c695-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="6c695-140">string</span><span class="sxs-lookup"><span data-stu-id="6c695-140">string</span></span> | <span data-ttu-id="6c695-141">用户主体 (UPN) 运行负责事件的进程的帐户的名称</span><span class="sxs-lookup"><span data-stu-id="6c695-141">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="6c695-142">string</span><span class="sxs-lookup"><span data-stu-id="6c695-142">string</span></span> | <span data-ttu-id="6c695-143">运行负责事件的进程的用户帐户的 Azure AD 对象 ID</span><span class="sxs-lookup"><span data-stu-id="6c695-143">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="6c695-144">string</span><span class="sxs-lookup"><span data-stu-id="6c695-144">string</span></span> | <span data-ttu-id="6c695-145">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="6c695-145">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="6c695-146">Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。</span><span class="sxs-lookup"><span data-stu-id="6c695-146">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="6c695-147">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="6c695-147">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="6c695-148">string</span><span class="sxs-lookup"><span data-stu-id="6c695-148">string</span></span> | <span data-ttu-id="6c695-149">指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升</span><span class="sxs-lookup"><span data-stu-id="6c695-149">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="6c695-150">string</span><span class="sxs-lookup"><span data-stu-id="6c695-150">string</span></span> | <span data-ttu-id="6c695-151">启动事件 (映像) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="6c695-151">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="6c695-152">string</span><span class="sxs-lookup"><span data-stu-id="6c695-152">string</span></span> | <span data-ttu-id="6c695-153">启动事件 (映像文件) SHA-256。</span><span class="sxs-lookup"><span data-stu-id="6c695-153">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="6c695-154">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="6c695-154">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="6c695-155">string</span><span class="sxs-lookup"><span data-stu-id="6c695-155">string</span></span> | <span data-ttu-id="6c695-156">启动事件的进程 (MD5) 文件哈希</span><span class="sxs-lookup"><span data-stu-id="6c695-156">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="6c695-157">string</span><span class="sxs-lookup"><span data-stu-id="6c695-157">string</span></span> | <span data-ttu-id="6c695-158">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="6c695-158">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="6c695-159">int</span><span class="sxs-lookup"><span data-stu-id="6c695-159">int</span></span> | <span data-ttu-id="6c695-160">进程 ID (PID) 启动事件的过程的 PID</span><span class="sxs-lookup"><span data-stu-id="6c695-160">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="6c695-161">string</span><span class="sxs-lookup"><span data-stu-id="6c695-161">string</span></span> | <span data-ttu-id="6c695-162">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="6c695-162">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="6c695-163">datetime</span><span class="sxs-lookup"><span data-stu-id="6c695-163">datetime</span></span> | <span data-ttu-id="6c695-164">启动事件的过程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6c695-164">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="6c695-165">string</span><span class="sxs-lookup"><span data-stu-id="6c695-165">string</span></span> | <span data-ttu-id="6c695-166">包含启动事件 (进程) 文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="6c695-166">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="6c695-167">int</span><span class="sxs-lookup"><span data-stu-id="6c695-167">int</span></span> | <span data-ttu-id="6c695-168">进程 ID (PID) 生成负责事件的进程的父进程的 PID</span><span class="sxs-lookup"><span data-stu-id="6c695-168">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="6c695-169">string</span><span class="sxs-lookup"><span data-stu-id="6c695-169">string</span></span> | <span data-ttu-id="6c695-170">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="6c695-170">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="6c695-171">datetime</span><span class="sxs-lookup"><span data-stu-id="6c695-171">datetime</span></span> | <span data-ttu-id="6c695-172">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6c695-172">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="6c695-173">long</span><span class="sxs-lookup"><span data-stu-id="6c695-173">long</span></span> | <span data-ttu-id="6c695-174">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="6c695-174">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6c695-175">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="6c695-175">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="6c695-176">string</span><span class="sxs-lookup"><span data-stu-id="6c695-176">string</span></span> | <span data-ttu-id="6c695-177">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="6c695-177">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="6c695-178">long</span><span class="sxs-lookup"><span data-stu-id="6c695-178">long</span></span> | <span data-ttu-id="6c695-179">运行负责事件的进程的文件的大小</span><span class="sxs-lookup"><span data-stu-id="6c695-179">Size of the file that ran the process responsible for the event</span></span> |
| `FileSize` | <span data-ttu-id="6c695-180">long</span><span class="sxs-lookup"><span data-stu-id="6c695-180">long</span></span> | <span data-ttu-id="6c695-181">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="6c695-181">Size of the file in bytes</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6c695-182">相关主题</span><span class="sxs-lookup"><span data-stu-id="6c695-182">Related topics</span></span>
- [<span data-ttu-id="6c695-183">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6c695-183">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c695-184">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6c695-184">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c695-185">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="6c695-185">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6c695-186">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="6c695-186">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6c695-187">了解架构</span><span class="sxs-lookup"><span data-stu-id="6c695-187">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6c695-188">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="6c695-188">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
