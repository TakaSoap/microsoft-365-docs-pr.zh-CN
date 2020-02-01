---
title: 高级搜寻架构中的 DeviceFileEvents 表
description: 了解高级搜寻架构的 DeviceFileEvents 表中与文件相关的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、filecreationevents、DeviceFileEvents、文件、路径哈希、sha1、sha256、md5
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
ms.openlocfilehash: 035efb5b2404708010f5fbfd4c419d59df088393
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600469"
---
# <a name="devicefileevents"></a><span data-ttu-id="a475c-104">DeviceFileEvents</span><span class="sxs-lookup"><span data-stu-id="a475c-104">DeviceFileEvents</span></span>

<span data-ttu-id="a475c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a475c-105">**Applies to:**</span></span>
- <span data-ttu-id="a475c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a475c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a475c-107">`DeviceFileEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关文件创建、修改和其他文件系统事件的信息。</span><span class="sxs-lookup"><span data-stu-id="a475c-107">The `DeviceFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file creation, modification, and other file system events.</span></span> <span data-ttu-id="a475c-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="a475c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a475c-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a475c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a475c-110">列名称</span><span class="sxs-lookup"><span data-stu-id="a475c-110">Column name</span></span> | <span data-ttu-id="a475c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="a475c-111">Data type</span></span> | <span data-ttu-id="a475c-112">说明</span><span class="sxs-lookup"><span data-stu-id="a475c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a475c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a475c-113">datetime</span></span> | <span data-ttu-id="a475c-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a475c-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a475c-115">string</span><span class="sxs-lookup"><span data-stu-id="a475c-115">string</span></span> | <span data-ttu-id="a475c-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a475c-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a475c-117">string</span><span class="sxs-lookup"><span data-stu-id="a475c-117">string</span></span> | <span data-ttu-id="a475c-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a475c-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="a475c-119">string</span><span class="sxs-lookup"><span data-stu-id="a475c-119">string</span></span> | <span data-ttu-id="a475c-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="a475c-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="a475c-121">string</span><span class="sxs-lookup"><span data-stu-id="a475c-121">string</span></span> | <span data-ttu-id="a475c-122">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="a475c-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="a475c-123">string</span><span class="sxs-lookup"><span data-stu-id="a475c-123">string</span></span> | <span data-ttu-id="a475c-124">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="a475c-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="a475c-125">string</span><span class="sxs-lookup"><span data-stu-id="a475c-125">string</span></span> | <span data-ttu-id="a475c-126">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a475c-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="a475c-127">string</span><span class="sxs-lookup"><span data-stu-id="a475c-127">string</span></span> | <span data-ttu-id="a475c-128">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="a475c-128">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="a475c-129">通常不填充此字段—使用 SHA1 列（如果可用）</span><span class="sxs-lookup"><span data-stu-id="a475c-129">This field is usually not populated—use the SHA1 column when available</span></span> |
| `MD5` | <span data-ttu-id="a475c-130">string</span><span class="sxs-lookup"><span data-stu-id="a475c-130">string</span></span> | <span data-ttu-id="a475c-131">将录制的操作应用于的文件的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="a475c-131">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileOriginUrl` | <span data-ttu-id="a475c-132">string</span><span class="sxs-lookup"><span data-stu-id="a475c-132">string</span></span> | <span data-ttu-id="a475c-133">从中下载文件的 URL</span><span class="sxs-lookup"><span data-stu-id="a475c-133">URL where the file was downloaded from</span></span> |
| `FileOriginReferrerUrl` | <span data-ttu-id="a475c-134">string</span><span class="sxs-lookup"><span data-stu-id="a475c-134">string</span></span> | <span data-ttu-id="a475c-135">链接到下载文件的网页的 URL</span><span class="sxs-lookup"><span data-stu-id="a475c-135">URL of the web page that links to the downloaded file</span></span> |
| `FileOriginIP` | <span data-ttu-id="a475c-136">string</span><span class="sxs-lookup"><span data-stu-id="a475c-136">string</span></span> | <span data-ttu-id="a475c-137">从中下载文件的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a475c-137">IP address where the file was downloaded from</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a475c-138">string</span><span class="sxs-lookup"><span data-stu-id="a475c-138">string</span></span> | <span data-ttu-id="a475c-139">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="a475c-139">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a475c-140">string</span><span class="sxs-lookup"><span data-stu-id="a475c-140">string</span></span> | <span data-ttu-id="a475c-141">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="a475c-141">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a475c-142">string</span><span class="sxs-lookup"><span data-stu-id="a475c-142">string</span></span> | <span data-ttu-id="a475c-143">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="a475c-143">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a475c-144">string</span><span class="sxs-lookup"><span data-stu-id="a475c-144">string</span></span> | <span data-ttu-id="a475c-145">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="a475c-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a475c-146">string</span><span class="sxs-lookup"><span data-stu-id="a475c-146">string</span></span> | <span data-ttu-id="a475c-147">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a475c-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a475c-148">string</span><span class="sxs-lookup"><span data-stu-id="a475c-148">string</span></span> | <span data-ttu-id="a475c-149">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="a475c-149">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a475c-150">string</span><span class="sxs-lookup"><span data-stu-id="a475c-150">string</span></span> | <span data-ttu-id="a475c-151">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="a475c-151">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a475c-152">int</span><span class="sxs-lookup"><span data-stu-id="a475c-152">int</span></span> | <span data-ttu-id="a475c-153">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="a475c-153">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a475c-154">string</span><span class="sxs-lookup"><span data-stu-id="a475c-154">string</span></span> | <span data-ttu-id="a475c-155">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="a475c-155">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a475c-156">datetime</span><span class="sxs-lookup"><span data-stu-id="a475c-156">datetime</span></span> | <span data-ttu-id="a475c-157">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a475c-157">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a475c-158">string</span><span class="sxs-lookup"><span data-stu-id="a475c-158">string</span></span> | <span data-ttu-id="a475c-159">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="a475c-159">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a475c-160">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="a475c-160">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a475c-161">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="a475c-161">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a475c-162">string</span><span class="sxs-lookup"><span data-stu-id="a475c-162">string</span></span> | <span data-ttu-id="a475c-163">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="a475c-163">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a475c-164">int</span><span class="sxs-lookup"><span data-stu-id="a475c-164">int</span></span> | <span data-ttu-id="a475c-165">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="a475c-165">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a475c-166">string</span><span class="sxs-lookup"><span data-stu-id="a475c-166">string</span></span> | <span data-ttu-id="a475c-167">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="a475c-167">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a475c-168">datetime</span><span class="sxs-lookup"><span data-stu-id="a475c-168">datetime</span></span> | <span data-ttu-id="a475c-169">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a475c-169">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="a475c-170">long</span><span class="sxs-lookup"><span data-stu-id="a475c-170">long</span></span> | <span data-ttu-id="a475c-171">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="a475c-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a475c-172">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="a475c-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a475c-173">string</span><span class="sxs-lookup"><span data-stu-id="a475c-173">string</span></span> | <span data-ttu-id="a475c-174">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="a475c-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `SensitivityLabel` | <span data-ttu-id="a475c-175">string</span><span class="sxs-lookup"><span data-stu-id="a475c-175">string</span></span> | <span data-ttu-id="a475c-176">应用于电子邮件、文件或其他内容的标签以对其进行分类以实现信息保护</span><span class="sxs-lookup"><span data-stu-id="a475c-176">Label applied to an email, file, or other content to classify it for information protection</span></span> |
| `SensitivitySubLabel` | <span data-ttu-id="a475c-177">string</span><span class="sxs-lookup"><span data-stu-id="a475c-177">string</span></span> | <span data-ttu-id="a475c-178">选项应用于电子邮件、文件或其他内容以对其进行分类以进行信息保护;敏感度子标签按敏感度标签分组，但单独处理</span><span class="sxs-lookup"><span data-stu-id="a475c-178">Sublabel applied to an email, file, or other content to classify it for information protection; sensitivity sublabels are grouped under sensitivity labels but are treated independently</span></span> |
| `IsAzureInfoProtectionApplied` | <span data-ttu-id="a475c-179">boolean</span><span class="sxs-lookup"><span data-stu-id="a475c-179">boolean</span></span> | <span data-ttu-id="a475c-180">指示文件是否由 Azure 信息保护进行加密</span><span class="sxs-lookup"><span data-stu-id="a475c-180">Indicates whether the file is encrypted by Azure Information Protection</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a475c-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="a475c-181">Related topics</span></span>
- [<span data-ttu-id="a475c-182">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a475c-182">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a475c-183">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a475c-183">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a475c-184">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="a475c-184">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a475c-185">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="a475c-185">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a475c-186">了解架构</span><span class="sxs-lookup"><span data-stu-id="a475c-186">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a475c-187">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="a475c-187">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
