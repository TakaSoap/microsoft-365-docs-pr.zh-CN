---
title: 高级搜寻架构中的 DeviceNetworkEvents 表
description: 了解可以从高级搜寻架构的 DeviceNetworkEvents 表中查询的网络连接事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、devicenetworkevents、NetworkCommunicationEvents、网络连接、远程 ip、本地 ip
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 8a385989bc7fd21a136124fdd4658ef64538c82a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414090"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="48ba0-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="48ba0-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="48ba0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="48ba0-105">**Applies to:**</span></span>
- <span data-ttu-id="48ba0-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="48ba0-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="48ba0-107">`DeviceNetworkEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关网络连接和相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="48ba0-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="48ba0-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="48ba0-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="48ba0-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="48ba0-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="48ba0-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="48ba0-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="48ba0-111">列名称</span><span class="sxs-lookup"><span data-stu-id="48ba0-111">Column name</span></span> | <span data-ttu-id="48ba0-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="48ba0-112">Data type</span></span> | <span data-ttu-id="48ba0-113">说明</span><span class="sxs-lookup"><span data-stu-id="48ba0-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="48ba0-114">datetime</span><span class="sxs-lookup"><span data-stu-id="48ba0-114">datetime</span></span> | <span data-ttu-id="48ba0-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="48ba0-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="48ba0-116">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-116">string</span></span> | <span data-ttu-id="48ba0-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="48ba0-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="48ba0-118">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-118">string</span></span> | <span data-ttu-id="48ba0-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="48ba0-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="48ba0-120">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-120">string</span></span> | <span data-ttu-id="48ba0-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="48ba0-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="48ba0-122">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="48ba0-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="48ba0-123">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-123">string</span></span> | <span data-ttu-id="48ba0-124">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="48ba0-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="48ba0-125">int</span><span class="sxs-lookup"><span data-stu-id="48ba0-125">int</span></span> | <span data-ttu-id="48ba0-126">要连接到的远程设备上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="48ba0-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="48ba0-127">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-127">string</span></span> | <span data-ttu-id="48ba0-128">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="48ba0-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="48ba0-129">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-129">string</span></span> | <span data-ttu-id="48ba0-130">分配给在通信期间使用的本地计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="48ba0-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="48ba0-131">int</span><span class="sxs-lookup"><span data-stu-id="48ba0-131">int</span></span> | <span data-ttu-id="48ba0-132">通信期间使用的本地计算机上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="48ba0-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="48ba0-133">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-133">string</span></span> | <span data-ttu-id="48ba0-134">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="48ba0-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="48ba0-135">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-135">string</span></span> | <span data-ttu-id="48ba0-136">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="48ba0-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="48ba0-137">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-137">string</span></span> | <span data-ttu-id="48ba0-138">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="48ba0-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="48ba0-139">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-139">string</span></span> | <span data-ttu-id="48ba0-140">启动事件的过程 (图像文件) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="48ba0-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="48ba0-141">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-141">string</span></span> | <span data-ttu-id="48ba0-142">SHA-256 启动事件的过程 (图像文件) 。</span><span class="sxs-lookup"><span data-stu-id="48ba0-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="48ba0-143">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="48ba0-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="48ba0-144">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-144">string</span></span> | <span data-ttu-id="48ba0-145">启动事件的过程 (映像文件) 的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="48ba0-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="48ba0-146">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-146">string</span></span> | <span data-ttu-id="48ba0-147">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="48ba0-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="48ba0-148">int</span><span class="sxs-lookup"><span data-stu-id="48ba0-148">int</span></span> | <span data-ttu-id="48ba0-149">启动事件的进程的进程 ID (PID) </span><span class="sxs-lookup"><span data-stu-id="48ba0-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="48ba0-150">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-150">string</span></span> | <span data-ttu-id="48ba0-151">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="48ba0-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="48ba0-152">datetime</span><span class="sxs-lookup"><span data-stu-id="48ba0-152">datetime</span></span> | <span data-ttu-id="48ba0-153">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="48ba0-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="48ba0-154">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-154">string</span></span> | <span data-ttu-id="48ba0-155">包含启动事件的过程 (图像文件) 的文件夹</span><span class="sxs-lookup"><span data-stu-id="48ba0-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="48ba0-156">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-156">string</span></span> | <span data-ttu-id="48ba0-157">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="48ba0-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="48ba0-158">int</span><span class="sxs-lookup"><span data-stu-id="48ba0-158">int</span></span> | <span data-ttu-id="48ba0-159">生成负责事件的进程的父进程 (PID) 的进程 ID</span><span class="sxs-lookup"><span data-stu-id="48ba0-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="48ba0-160">datetime</span><span class="sxs-lookup"><span data-stu-id="48ba0-160">datetime</span></span> | <span data-ttu-id="48ba0-161">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="48ba0-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="48ba0-162">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-162">string</span></span> | <span data-ttu-id="48ba0-163">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="48ba0-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="48ba0-164">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-164">string</span></span> | <span data-ttu-id="48ba0-165">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="48ba0-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="48ba0-166">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-166">string</span></span> | <span data-ttu-id="48ba0-167">运行负责事件的进程的帐户 (SID) 的安全标识符</span><span class="sxs-lookup"><span data-stu-id="48ba0-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="48ba0-168">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-168">string</span></span> | <span data-ttu-id="48ba0-169">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="48ba0-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="48ba0-170">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="48ba0-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="48ba0-171">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="48ba0-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="48ba0-172">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-172">string</span></span> | <span data-ttu-id="48ba0-173">指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动该事件的进程</span><span class="sxs-lookup"><span data-stu-id="48ba0-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="48ba0-174">long</span><span class="sxs-lookup"><span data-stu-id="48ba0-174">long</span></span> | <span data-ttu-id="48ba0-175">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="48ba0-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="48ba0-176">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="48ba0-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="48ba0-177">string</span><span class="sxs-lookup"><span data-stu-id="48ba0-177">string</span></span> | <span data-ttu-id="48ba0-178">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="48ba0-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="48ba0-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="48ba0-179">Related topics</span></span>
- [<span data-ttu-id="48ba0-180">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="48ba0-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48ba0-181">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="48ba0-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="48ba0-182">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="48ba0-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="48ba0-183">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="48ba0-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="48ba0-184">了解架构</span><span class="sxs-lookup"><span data-stu-id="48ba0-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="48ba0-185">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="48ba0-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
