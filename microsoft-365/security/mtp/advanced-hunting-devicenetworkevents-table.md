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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d5d666bef07c6ae8c5a43b641a8e7f6a11f5457a
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899251"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="6994a-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="6994a-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="6994a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6994a-105">**Applies to:**</span></span>
- <span data-ttu-id="6994a-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6994a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="6994a-107">`DeviceNetworkEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关网络连接和相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="6994a-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="6994a-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="6994a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6994a-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6994a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6994a-110">列名称</span><span class="sxs-lookup"><span data-stu-id="6994a-110">Column name</span></span> | <span data-ttu-id="6994a-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="6994a-111">Data type</span></span> | <span data-ttu-id="6994a-112">说明</span><span class="sxs-lookup"><span data-stu-id="6994a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6994a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6994a-113">datetime</span></span> | <span data-ttu-id="6994a-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6994a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6994a-115">string</span><span class="sxs-lookup"><span data-stu-id="6994a-115">string</span></span> | <span data-ttu-id="6994a-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="6994a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6994a-117">string</span><span class="sxs-lookup"><span data-stu-id="6994a-117">string</span></span> | <span data-ttu-id="6994a-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6994a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="6994a-119">string</span><span class="sxs-lookup"><span data-stu-id="6994a-119">string</span></span> | <span data-ttu-id="6994a-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="6994a-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="6994a-121">string</span><span class="sxs-lookup"><span data-stu-id="6994a-121">string</span></span> | <span data-ttu-id="6994a-122">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6994a-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="6994a-123">int</span><span class="sxs-lookup"><span data-stu-id="6994a-123">int</span></span> | <span data-ttu-id="6994a-124">要连接到的远程设备上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="6994a-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6994a-125">string</span><span class="sxs-lookup"><span data-stu-id="6994a-125">string</span></span> | <span data-ttu-id="6994a-126">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6994a-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="6994a-127">string</span><span class="sxs-lookup"><span data-stu-id="6994a-127">string</span></span> | <span data-ttu-id="6994a-128">分配给在通信期间使用的本地计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6994a-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="6994a-129">int</span><span class="sxs-lookup"><span data-stu-id="6994a-129">int</span></span> | <span data-ttu-id="6994a-130">通信期间使用的本地计算机上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="6994a-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="6994a-131">string</span><span class="sxs-lookup"><span data-stu-id="6994a-131">string</span></span> | <span data-ttu-id="6994a-132">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="6994a-132">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="6994a-133">string</span><span class="sxs-lookup"><span data-stu-id="6994a-133">string</span></span> | <span data-ttu-id="6994a-134">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="6994a-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="6994a-135">string</span><span class="sxs-lookup"><span data-stu-id="6994a-135">string</span></span> | <span data-ttu-id="6994a-136">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="6994a-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="6994a-137">string</span><span class="sxs-lookup"><span data-stu-id="6994a-137">string</span></span> | <span data-ttu-id="6994a-138">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="6994a-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="6994a-139">string</span><span class="sxs-lookup"><span data-stu-id="6994a-139">string</span></span> | <span data-ttu-id="6994a-140">SHA-256，其中启动了事件的进程（图像文件）。</span><span class="sxs-lookup"><span data-stu-id="6994a-140">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="6994a-141">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="6994a-141">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="6994a-142">string</span><span class="sxs-lookup"><span data-stu-id="6994a-142">string</span></span> | <span data-ttu-id="6994a-143">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="6994a-143">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="6994a-144">string</span><span class="sxs-lookup"><span data-stu-id="6994a-144">string</span></span> | <span data-ttu-id="6994a-145">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="6994a-145">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="6994a-146">int</span><span class="sxs-lookup"><span data-stu-id="6994a-146">int</span></span> | <span data-ttu-id="6994a-147">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="6994a-147">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="6994a-148">string</span><span class="sxs-lookup"><span data-stu-id="6994a-148">string</span></span> | <span data-ttu-id="6994a-149">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="6994a-149">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="6994a-150">datetime</span><span class="sxs-lookup"><span data-stu-id="6994a-150">datetime</span></span> | <span data-ttu-id="6994a-151">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6994a-151">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="6994a-152">string</span><span class="sxs-lookup"><span data-stu-id="6994a-152">string</span></span> | <span data-ttu-id="6994a-153">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="6994a-153">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="6994a-154">string</span><span class="sxs-lookup"><span data-stu-id="6994a-154">string</span></span> | <span data-ttu-id="6994a-155">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="6994a-155">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="6994a-156">int</span><span class="sxs-lookup"><span data-stu-id="6994a-156">int</span></span> | <span data-ttu-id="6994a-157">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="6994a-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="6994a-158">datetime</span><span class="sxs-lookup"><span data-stu-id="6994a-158">datetime</span></span> | <span data-ttu-id="6994a-159">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="6994a-159">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="6994a-160">string</span><span class="sxs-lookup"><span data-stu-id="6994a-160">string</span></span> | <span data-ttu-id="6994a-161">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="6994a-161">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="6994a-162">string</span><span class="sxs-lookup"><span data-stu-id="6994a-162">string</span></span> | <span data-ttu-id="6994a-163">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="6994a-163">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="6994a-164">string</span><span class="sxs-lookup"><span data-stu-id="6994a-164">string</span></span> | <span data-ttu-id="6994a-165">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="6994a-165">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="6994a-166">string</span><span class="sxs-lookup"><span data-stu-id="6994a-166">string</span></span> | <span data-ttu-id="6994a-167">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="6994a-167">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="6994a-168">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="6994a-168">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="6994a-169">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="6994a-169">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="6994a-170">string</span><span class="sxs-lookup"><span data-stu-id="6994a-170">string</span></span> | <span data-ttu-id="6994a-171">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="6994a-171">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="6994a-172">long</span><span class="sxs-lookup"><span data-stu-id="6994a-172">long</span></span> | <span data-ttu-id="6994a-173">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="6994a-173">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6994a-174">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="6994a-174">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="6994a-175">string</span><span class="sxs-lookup"><span data-stu-id="6994a-175">string</span></span> | <span data-ttu-id="6994a-176">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="6994a-176">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6994a-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="6994a-177">Related topics</span></span>
- [<span data-ttu-id="6994a-178">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="6994a-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6994a-179">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="6994a-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6994a-180">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="6994a-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6994a-181">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="6994a-181">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6994a-182">了解架构</span><span class="sxs-lookup"><span data-stu-id="6994a-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6994a-183">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="6994a-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
