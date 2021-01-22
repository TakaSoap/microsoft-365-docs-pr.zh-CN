---
title: 高级搜寻架构中的 DeviceNetworkEvents 表
description: 了解可以从高级搜寻架构的 DeviceNetworkEvents 表查询的网络连接事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， devicenetworkevents， NetworkCommunicationEvents， 网络连接， 远程 ip， 本地 ip
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0ed696f36737a4102895369e1254b4215cad4def
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931214"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="d7f3e-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="d7f3e-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7f3e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d7f3e-105">**Applies to:**</span></span>
- <span data-ttu-id="d7f3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f3e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d7f3e-107">高级 `DeviceNetworkEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关网络连接和相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="d7f3e-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="d7f3e-109">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构参考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="d7f3e-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="d7f3e-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d7f3e-111">列名称</span><span class="sxs-lookup"><span data-stu-id="d7f3e-111">Column name</span></span> | <span data-ttu-id="d7f3e-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7f3e-112">Data type</span></span> | <span data-ttu-id="d7f3e-113">说明</span><span class="sxs-lookup"><span data-stu-id="d7f3e-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d7f3e-114">datetime</span><span class="sxs-lookup"><span data-stu-id="d7f3e-114">datetime</span></span> | <span data-ttu-id="d7f3e-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d7f3e-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d7f3e-116">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-116">string</span></span> | <span data-ttu-id="d7f3e-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d7f3e-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d7f3e-118">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-118">string</span></span> | <span data-ttu-id="d7f3e-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d7f3e-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="d7f3e-120">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-120">string</span></span> | <span data-ttu-id="d7f3e-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="d7f3e-122">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="d7f3e-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="d7f3e-123">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-123">string</span></span> | <span data-ttu-id="d7f3e-124">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d7f3e-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="d7f3e-125">int</span><span class="sxs-lookup"><span data-stu-id="d7f3e-125">int</span></span> | <span data-ttu-id="d7f3e-126">连接到的远程设备的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="d7f3e-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="d7f3e-127">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-127">string</span></span> | <span data-ttu-id="d7f3e-128">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d7f3e-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="d7f3e-129">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-129">string</span></span> | <span data-ttu-id="d7f3e-130">分配给通信过程中使用的本地计算机 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d7f3e-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="d7f3e-131">int</span><span class="sxs-lookup"><span data-stu-id="d7f3e-131">int</span></span> | <span data-ttu-id="d7f3e-132">通信过程中使用的本地计算机上 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="d7f3e-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="d7f3e-133">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-133">string</span></span> | <span data-ttu-id="d7f3e-134">通信期间使用的协议</span><span class="sxs-lookup"><span data-stu-id="d7f3e-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="d7f3e-135">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-135">string</span></span> | <span data-ttu-id="d7f3e-136">IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="d7f3e-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="d7f3e-137">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-137">string</span></span> | <span data-ttu-id="d7f3e-138">IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="d7f3e-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="d7f3e-139">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-139">string</span></span> | <span data-ttu-id="d7f3e-140">启动事件 (映像) SHA-1</span><span class="sxs-lookup"><span data-stu-id="d7f3e-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="d7f3e-141">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-141">string</span></span> | <span data-ttu-id="d7f3e-142">启动事件 (映像文件) SHA-256。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="d7f3e-143">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="d7f3e-144">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-144">string</span></span> | <span data-ttu-id="d7f3e-145">启动事件 (映像) 的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="d7f3e-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="d7f3e-146">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-146">string</span></span> | <span data-ttu-id="d7f3e-147">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="d7f3e-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="d7f3e-148">int</span><span class="sxs-lookup"><span data-stu-id="d7f3e-148">int</span></span> | <span data-ttu-id="d7f3e-149">启动 (PID) 进程的进程 ID</span><span class="sxs-lookup"><span data-stu-id="d7f3e-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="d7f3e-150">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-150">string</span></span> | <span data-ttu-id="d7f3e-151">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="d7f3e-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="d7f3e-152">datetime</span><span class="sxs-lookup"><span data-stu-id="d7f3e-152">datetime</span></span> | <span data-ttu-id="d7f3e-153">启动事件的过程启动的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d7f3e-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="d7f3e-154">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-154">string</span></span> | <span data-ttu-id="d7f3e-155">包含启动 (的文件) 进程的文件夹</span><span class="sxs-lookup"><span data-stu-id="d7f3e-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="d7f3e-156">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-156">string</span></span> | <span data-ttu-id="d7f3e-157">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="d7f3e-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="d7f3e-158">int</span><span class="sxs-lookup"><span data-stu-id="d7f3e-158">int</span></span> | <span data-ttu-id="d7f3e-159">进程 ID (PID) 生成负责事件的进程的父进程</span><span class="sxs-lookup"><span data-stu-id="d7f3e-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="d7f3e-160">datetime</span><span class="sxs-lookup"><span data-stu-id="d7f3e-160">datetime</span></span> | <span data-ttu-id="d7f3e-161">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d7f3e-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="d7f3e-162">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-162">string</span></span> | <span data-ttu-id="d7f3e-163">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="d7f3e-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="d7f3e-164">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-164">string</span></span> | <span data-ttu-id="d7f3e-165">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="d7f3e-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="d7f3e-166">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-166">string</span></span> | <span data-ttu-id="d7f3e-167">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="d7f3e-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="d7f3e-168">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-168">string</span></span> | <span data-ttu-id="d7f3e-169">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="d7f3e-170">Windows 根据某些特征（例如是否从 Internet 下载启动）为进程分配完整性级别。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="d7f3e-171">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="d7f3e-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="d7f3e-172">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-172">string</span></span> | <span data-ttu-id="d7f3e-173">指示 UAC 中是否存在用户访问控制的令牌 (，) 启动事件的进程应用的权限提升</span><span class="sxs-lookup"><span data-stu-id="d7f3e-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="d7f3e-174">long</span><span class="sxs-lookup"><span data-stu-id="d7f3e-174">long</span></span> | <span data-ttu-id="d7f3e-175">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="d7f3e-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d7f3e-176">若要标识唯一事件，此列必须与 DeviceName 和时间戳列一起使用</span><span class="sxs-lookup"><span data-stu-id="d7f3e-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="d7f3e-177">string</span><span class="sxs-lookup"><span data-stu-id="d7f3e-177">string</span></span> | <span data-ttu-id="d7f3e-178">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="d7f3e-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d7f3e-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7f3e-179">Related topics</span></span>
- [<span data-ttu-id="d7f3e-180">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d7f3e-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d7f3e-181">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d7f3e-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d7f3e-182">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d7f3e-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d7f3e-183">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="d7f3e-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d7f3e-184">了解架构</span><span class="sxs-lookup"><span data-stu-id="d7f3e-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d7f3e-185">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d7f3e-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
