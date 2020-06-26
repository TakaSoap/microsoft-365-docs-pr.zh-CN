---
title: 高级搜寻架构中的 DeviceRegistryEvents 表
description: 了解可以从高级搜寻架构的 DeviceRegistryEvents 表中查询的注册表事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、registryevents、registry、DeviceRegistryEvents、key、key、value
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
ms.openlocfilehash: 35544866b9ebad94b14300b3734ddb2335fd657e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899001"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="5bfaf-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="5bfaf-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="5bfaf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5bfaf-105">**Applies to:**</span></span>
- <span data-ttu-id="5bfaf-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5bfaf-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5bfaf-107">`DeviceRegistryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关创建和修改注册表项的信息。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="5bfaf-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5bfaf-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5bfaf-110">列名称</span><span class="sxs-lookup"><span data-stu-id="5bfaf-110">Column name</span></span> | <span data-ttu-id="5bfaf-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="5bfaf-111">Data type</span></span> | <span data-ttu-id="5bfaf-112">说明</span><span class="sxs-lookup"><span data-stu-id="5bfaf-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5bfaf-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5bfaf-113">datetime</span></span> | <span data-ttu-id="5bfaf-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5bfaf-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5bfaf-115">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-115">string</span></span> | <span data-ttu-id="5bfaf-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="5bfaf-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5bfaf-117">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-117">string</span></span> | <span data-ttu-id="5bfaf-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5bfaf-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="5bfaf-119">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-119">string</span></span> | <span data-ttu-id="5bfaf-120">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="5bfaf-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="5bfaf-121">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-121">string</span></span> | <span data-ttu-id="5bfaf-122">将录制的操作应用于的注册表项</span><span class="sxs-lookup"><span data-stu-id="5bfaf-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="5bfaf-123">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-123">string</span></span> | <span data-ttu-id="5bfaf-124">应用录制的操作的注册表值的数据类型，如二进制或字符串</span><span class="sxs-lookup"><span data-stu-id="5bfaf-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="5bfaf-125">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-125">string</span></span> | <span data-ttu-id="5bfaf-126">将录制的操作应用于的注册表值的名称</span><span class="sxs-lookup"><span data-stu-id="5bfaf-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="5bfaf-127">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-127">string</span></span> | <span data-ttu-id="5bfaf-128">录制的操作所应用于的注册表值的数据</span><span class="sxs-lookup"><span data-stu-id="5bfaf-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="5bfaf-129">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-129">string</span></span> | <span data-ttu-id="5bfaf-130">注册表值在被修改之前的原始名称</span><span class="sxs-lookup"><span data-stu-id="5bfaf-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="5bfaf-131">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-131">string</span></span> | <span data-ttu-id="5bfaf-132">注册表值在被修改之前的原始数据</span><span class="sxs-lookup"><span data-stu-id="5bfaf-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="5bfaf-133">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-133">string</span></span> | <span data-ttu-id="5bfaf-134">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="5bfaf-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="5bfaf-135">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-135">string</span></span> | <span data-ttu-id="5bfaf-136">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="5bfaf-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="5bfaf-137">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-137">string</span></span> | <span data-ttu-id="5bfaf-138">运行负责事件的进程的帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="5bfaf-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="5bfaf-139">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-139">string</span></span> | <span data-ttu-id="5bfaf-140">启动事件的过程（图像文件）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5bfaf-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="5bfaf-141">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-141">string</span></span> | <span data-ttu-id="5bfaf-142">SHA-256，其中启动了事件的进程（图像文件）。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="5bfaf-143">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="5bfaf-144">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-144">string</span></span> | <span data-ttu-id="5bfaf-145">启动事件的进程（图像文件）的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="5bfaf-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="5bfaf-146">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-146">string</span></span> | <span data-ttu-id="5bfaf-147">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="5bfaf-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="5bfaf-148">int</span><span class="sxs-lookup"><span data-stu-id="5bfaf-148">int</span></span> | <span data-ttu-id="5bfaf-149">启动事件的进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="5bfaf-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="5bfaf-150">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-150">string</span></span> | <span data-ttu-id="5bfaf-151">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="5bfaf-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="5bfaf-152">datetime</span><span class="sxs-lookup"><span data-stu-id="5bfaf-152">datetime</span></span> | <span data-ttu-id="5bfaf-153">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5bfaf-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="5bfaf-154">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-154">string</span></span> | <span data-ttu-id="5bfaf-155">包含启动事件的进程（图像文件）的文件夹</span><span class="sxs-lookup"><span data-stu-id="5bfaf-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="5bfaf-156">int</span><span class="sxs-lookup"><span data-stu-id="5bfaf-156">int</span></span> | <span data-ttu-id="5bfaf-157">生成负责事件的进程的父进程的进程 ID （PID）</span><span class="sxs-lookup"><span data-stu-id="5bfaf-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="5bfaf-158">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-158">string</span></span> | <span data-ttu-id="5bfaf-159">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="5bfaf-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="5bfaf-160">datetime</span><span class="sxs-lookup"><span data-stu-id="5bfaf-160">datetime</span></span> | <span data-ttu-id="5bfaf-161">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5bfaf-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="5bfaf-162">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-162">string</span></span> | <span data-ttu-id="5bfaf-163">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-163">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="5bfaf-164">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-164">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="5bfaf-165">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="5bfaf-165">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="5bfaf-166">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-166">string</span></span> | <span data-ttu-id="5bfaf-167">指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型</span><span class="sxs-lookup"><span data-stu-id="5bfaf-167">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="5bfaf-168">long</span><span class="sxs-lookup"><span data-stu-id="5bfaf-168">long</span></span> | <span data-ttu-id="5bfaf-169">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="5bfaf-169">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5bfaf-170">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="5bfaf-170">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="5bfaf-171">string</span><span class="sxs-lookup"><span data-stu-id="5bfaf-171">string</span></span> | <span data-ttu-id="5bfaf-172">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="5bfaf-172">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bfaf-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="5bfaf-173">Related topics</span></span>
- [<span data-ttu-id="5bfaf-174">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="5bfaf-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5bfaf-175">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5bfaf-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5bfaf-176">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="5bfaf-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5bfaf-177">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="5bfaf-177">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5bfaf-178">了解架构</span><span class="sxs-lookup"><span data-stu-id="5bfaf-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5bfaf-179">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="5bfaf-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
