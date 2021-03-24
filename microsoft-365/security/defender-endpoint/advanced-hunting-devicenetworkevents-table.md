---
title: 高级搜寻架构中的 DeviceNetworkEvents 表
description: 了解可以从高级搜寻架构的 DeviceNetworkEvents 表查询的网络连接事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， devicenetworkevents， 网络连接， 远程 ip， 本地 ip， NetworkCommunicationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8c43d8ca790f246415a0419bca0adc3a21c92a84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056157"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="270b9-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="270b9-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="270b9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="270b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="270b9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="270b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="270b9-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="270b9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="270b9-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="270b9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="270b9-109">高级 `DeviceNetworkEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关网络连接和相关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="270b9-109">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="270b9-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="270b9-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="270b9-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="270b9-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="270b9-112">列名称</span><span class="sxs-lookup"><span data-stu-id="270b9-112">Column name</span></span> | <span data-ttu-id="270b9-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="270b9-113">Data type</span></span> | <span data-ttu-id="270b9-114">说明</span><span class="sxs-lookup"><span data-stu-id="270b9-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="270b9-115">datetime</span><span class="sxs-lookup"><span data-stu-id="270b9-115">datetime</span></span> | <span data-ttu-id="270b9-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="270b9-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="270b9-117">string</span><span class="sxs-lookup"><span data-stu-id="270b9-117">string</span></span> | <span data-ttu-id="270b9-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="270b9-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="270b9-119">string</span><span class="sxs-lookup"><span data-stu-id="270b9-119">string</span></span> | <span data-ttu-id="270b9-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="270b9-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="270b9-121">string</span><span class="sxs-lookup"><span data-stu-id="270b9-121">string</span></span> | <span data-ttu-id="270b9-122">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="270b9-122">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="270b9-123">string</span><span class="sxs-lookup"><span data-stu-id="270b9-123">string</span></span> | <span data-ttu-id="270b9-124">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="270b9-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="270b9-125">int</span><span class="sxs-lookup"><span data-stu-id="270b9-125">int</span></span> | <span data-ttu-id="270b9-126">连接到的远程设备的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="270b9-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="270b9-127">string</span><span class="sxs-lookup"><span data-stu-id="270b9-127">string</span></span> | <span data-ttu-id="270b9-128">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="270b9-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="270b9-129">string</span><span class="sxs-lookup"><span data-stu-id="270b9-129">string</span></span> | <span data-ttu-id="270b9-130">分配给通信期间使用的本地设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="270b9-130">IP address assigned to the local device used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="270b9-131">int</span><span class="sxs-lookup"><span data-stu-id="270b9-131">int</span></span> | <span data-ttu-id="270b9-132">通信过程中使用的本地设备的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="270b9-132">TCP port on the local device used during communication</span></span> |
| `Protocol` | <span data-ttu-id="270b9-133">string</span><span class="sxs-lookup"><span data-stu-id="270b9-133">string</span></span> | <span data-ttu-id="270b9-134">使用的 IP 协议，TCP 还是 UDP</span><span class="sxs-lookup"><span data-stu-id="270b9-134">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="270b9-135">string</span><span class="sxs-lookup"><span data-stu-id="270b9-135">string</span></span> | <span data-ttu-id="270b9-136">IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="270b9-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="270b9-137">string</span><span class="sxs-lookup"><span data-stu-id="270b9-137">string</span></span> | <span data-ttu-id="270b9-138">IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="270b9-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="270b9-139">string</span><span class="sxs-lookup"><span data-stu-id="270b9-139">string</span></span> | <span data-ttu-id="270b9-140">启动事件 (映像) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="270b9-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="270b9-141">string</span><span class="sxs-lookup"><span data-stu-id="270b9-141">string</span></span> | <span data-ttu-id="270b9-142">启动事件的进程 (MD5) 文件哈希</span><span class="sxs-lookup"><span data-stu-id="270b9-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="270b9-143">string</span><span class="sxs-lookup"><span data-stu-id="270b9-143">string</span></span> | <span data-ttu-id="270b9-144">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="270b9-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="270b9-145">int</span><span class="sxs-lookup"><span data-stu-id="270b9-145">int</span></span> | <span data-ttu-id="270b9-146">进程 ID (PID) 启动事件的过程的 PID</span><span class="sxs-lookup"><span data-stu-id="270b9-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="270b9-147">string</span><span class="sxs-lookup"><span data-stu-id="270b9-147">string</span></span> | <span data-ttu-id="270b9-148">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="270b9-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="270b9-149">datetime</span><span class="sxs-lookup"><span data-stu-id="270b9-149">datetime</span></span> | <span data-ttu-id="270b9-150">启动事件的过程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="270b9-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="270b9-151">string</span><span class="sxs-lookup"><span data-stu-id="270b9-151">string</span></span> | <span data-ttu-id="270b9-152">包含启动事件 (进程) 文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="270b9-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="270b9-153">string</span><span class="sxs-lookup"><span data-stu-id="270b9-153">string</span></span> | <span data-ttu-id="270b9-154">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="270b9-154">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="270b9-155">int</span><span class="sxs-lookup"><span data-stu-id="270b9-155">int</span></span> | <span data-ttu-id="270b9-156">进程 ID (PID) 生成负责事件的进程的父进程的 PID</span><span class="sxs-lookup"><span data-stu-id="270b9-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="270b9-157">datetime</span><span class="sxs-lookup"><span data-stu-id="270b9-157">datetime</span></span> | <span data-ttu-id="270b9-158">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="270b9-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="270b9-159">string</span><span class="sxs-lookup"><span data-stu-id="270b9-159">string</span></span> | <span data-ttu-id="270b9-160">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="270b9-160">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="270b9-161">string</span><span class="sxs-lookup"><span data-stu-id="270b9-161">string</span></span> | <span data-ttu-id="270b9-162">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="270b9-162">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="270b9-163">string</span><span class="sxs-lookup"><span data-stu-id="270b9-163">string</span></span> | <span data-ttu-id="270b9-164">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="270b9-164">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="270b9-165">string</span><span class="sxs-lookup"><span data-stu-id="270b9-165">string</span></span> | <span data-ttu-id="270b9-166">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="270b9-166">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="270b9-167">Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。</span><span class="sxs-lookup"><span data-stu-id="270b9-167">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="270b9-168">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="270b9-168">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="270b9-169">string</span><span class="sxs-lookup"><span data-stu-id="270b9-169">string</span></span> | <span data-ttu-id="270b9-170">指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升</span><span class="sxs-lookup"><span data-stu-id="270b9-170">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="270b9-171">long</span><span class="sxs-lookup"><span data-stu-id="270b9-171">long</span></span> | <span data-ttu-id="270b9-172">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="270b9-172">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="270b9-173">若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用</span><span class="sxs-lookup"><span data-stu-id="270b9-173">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="270b9-174">string</span><span class="sxs-lookup"><span data-stu-id="270b9-174">string</span></span> | <span data-ttu-id="270b9-175">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="270b9-175">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="270b9-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="270b9-176">Related topics</span></span>
- [<span data-ttu-id="270b9-177">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="270b9-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="270b9-178">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="270b9-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="270b9-179">了解架构</span><span class="sxs-lookup"><span data-stu-id="270b9-179">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
