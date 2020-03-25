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
ms.openlocfilehash: d5e3327f4b4e066b3e4c14f646ad8db78ff3804a
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929036"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="c406e-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="c406e-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="c406e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c406e-105">**Applies to:**</span></span>
- <span data-ttu-id="c406e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c406e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c406e-107">`DeviceNetworkEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关网络连接和相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="c406e-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="c406e-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="c406e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c406e-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c406e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c406e-110">列名称</span><span class="sxs-lookup"><span data-stu-id="c406e-110">Column name</span></span> | <span data-ttu-id="c406e-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="c406e-111">Data type</span></span> | <span data-ttu-id="c406e-112">说明</span><span class="sxs-lookup"><span data-stu-id="c406e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c406e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c406e-113">datetime</span></span> | <span data-ttu-id="c406e-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="c406e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c406e-115">string</span><span class="sxs-lookup"><span data-stu-id="c406e-115">string</span></span> | <span data-ttu-id="c406e-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="c406e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c406e-117">string</span><span class="sxs-lookup"><span data-stu-id="c406e-117">string</span></span> | <span data-ttu-id="c406e-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c406e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="c406e-119">string</span><span class="sxs-lookup"><span data-stu-id="c406e-119">string</span></span> | <span data-ttu-id="c406e-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="c406e-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="c406e-121">string</span><span class="sxs-lookup"><span data-stu-id="c406e-121">string</span></span> | <span data-ttu-id="c406e-122">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c406e-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="c406e-123">int</span><span class="sxs-lookup"><span data-stu-id="c406e-123">int</span></span> | <span data-ttu-id="c406e-124">要连接到的远程设备上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="c406e-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c406e-125">string</span><span class="sxs-lookup"><span data-stu-id="c406e-125">string</span></span> | <span data-ttu-id="c406e-126">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c406e-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="c406e-127">string</span><span class="sxs-lookup"><span data-stu-id="c406e-127">string</span></span> | <span data-ttu-id="c406e-128">分配给在通信期间使用的本地计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c406e-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="c406e-129">int</span><span class="sxs-lookup"><span data-stu-id="c406e-129">int</span></span> | <span data-ttu-id="c406e-130">通信期间使用的本地计算机上的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="c406e-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="c406e-131">string</span><span class="sxs-lookup"><span data-stu-id="c406e-131">string</span></span> | <span data-ttu-id="c406e-132">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="c406e-132">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="c406e-133">string</span><span class="sxs-lookup"><span data-stu-id="c406e-133">string</span></span> | <span data-ttu-id="c406e-134">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="c406e-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="c406e-135">string</span><span class="sxs-lookup"><span data-stu-id="c406e-135">string</span></span> | <span data-ttu-id="c406e-136">IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播</span><span class="sxs-lookup"><span data-stu-id="c406e-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="c406e-137">string</span><span class="sxs-lookup"><span data-stu-id="c406e-137">string</span></span> | <span data-ttu-id="c406e-138">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="c406e-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="c406e-139">string</span><span class="sxs-lookup"><span data-stu-id="c406e-139">string</span></span> | <span data-ttu-id="c406e-140">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="c406e-140">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="c406e-141">string</span><span class="sxs-lookup"><span data-stu-id="c406e-141">string</span></span> | <span data-ttu-id="c406e-142">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="c406e-142">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="c406e-143">int</span><span class="sxs-lookup"><span data-stu-id="c406e-143">int</span></span> | <span data-ttu-id="c406e-144">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="c406e-144">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="c406e-145">string</span><span class="sxs-lookup"><span data-stu-id="c406e-145">string</span></span> | <span data-ttu-id="c406e-146">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="c406e-146">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="c406e-147">datetime</span><span class="sxs-lookup"><span data-stu-id="c406e-147">datetime</span></span> | <span data-ttu-id="c406e-148">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="c406e-148">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="c406e-149">string</span><span class="sxs-lookup"><span data-stu-id="c406e-149">string</span></span> | <span data-ttu-id="c406e-150">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="c406e-150">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="c406e-151">string</span><span class="sxs-lookup"><span data-stu-id="c406e-151">string</span></span> | <span data-ttu-id="c406e-152">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="c406e-152">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="c406e-153">int</span><span class="sxs-lookup"><span data-stu-id="c406e-153">int</span></span> | <span data-ttu-id="c406e-154">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="c406e-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="c406e-155">datetime</span><span class="sxs-lookup"><span data-stu-id="c406e-155">datetime</span></span> | <span data-ttu-id="c406e-156">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="c406e-156">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="c406e-157">string</span><span class="sxs-lookup"><span data-stu-id="c406e-157">string</span></span> | <span data-ttu-id="c406e-158">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="c406e-158">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="c406e-159">string</span><span class="sxs-lookup"><span data-stu-id="c406e-159">string</span></span> | <span data-ttu-id="c406e-160">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="c406e-160">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="c406e-161">string</span><span class="sxs-lookup"><span data-stu-id="c406e-161">string</span></span> | <span data-ttu-id="c406e-162">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="c406e-162">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="c406e-163">string</span><span class="sxs-lookup"><span data-stu-id="c406e-163">string</span></span> | <span data-ttu-id="c406e-164">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="c406e-164">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="c406e-165">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="c406e-165">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="c406e-166">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="c406e-166">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="c406e-167">string</span><span class="sxs-lookup"><span data-stu-id="c406e-167">string</span></span> | <span data-ttu-id="c406e-168">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="c406e-168">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="c406e-169">long</span><span class="sxs-lookup"><span data-stu-id="c406e-169">long</span></span> | <span data-ttu-id="c406e-170">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="c406e-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c406e-171">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="c406e-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="c406e-172">string</span><span class="sxs-lookup"><span data-stu-id="c406e-172">string</span></span> | <span data-ttu-id="c406e-173">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="c406e-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c406e-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="c406e-174">Related topics</span></span>
- [<span data-ttu-id="c406e-175">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="c406e-175">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c406e-176">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="c406e-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c406e-177">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="c406e-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c406e-178">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="c406e-178">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c406e-179">了解架构</span><span class="sxs-lookup"><span data-stu-id="c406e-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c406e-180">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="c406e-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
