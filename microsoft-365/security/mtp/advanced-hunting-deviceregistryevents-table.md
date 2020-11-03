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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1f7df85838654473fea593b235785b4320ea7164
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842672"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="f7773-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="f7773-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f7773-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f7773-105">**Applies to:**</span></span>
- <span data-ttu-id="f7773-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7773-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f7773-107">`DeviceRegistryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关创建和修改注册表项的信息。</span><span class="sxs-lookup"><span data-stu-id="f7773-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="f7773-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="f7773-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f7773-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="f7773-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="f7773-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f7773-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f7773-111">列名称</span><span class="sxs-lookup"><span data-stu-id="f7773-111">Column name</span></span> | <span data-ttu-id="f7773-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="f7773-112">Data type</span></span> | <span data-ttu-id="f7773-113">说明</span><span class="sxs-lookup"><span data-stu-id="f7773-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f7773-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f7773-114">datetime</span></span> | <span data-ttu-id="f7773-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="f7773-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f7773-116">string</span><span class="sxs-lookup"><span data-stu-id="f7773-116">string</span></span> | <span data-ttu-id="f7773-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f7773-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f7773-118">string</span><span class="sxs-lookup"><span data-stu-id="f7773-118">string</span></span> | <span data-ttu-id="f7773-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f7773-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="f7773-120">string</span><span class="sxs-lookup"><span data-stu-id="f7773-120">string</span></span> | <span data-ttu-id="f7773-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="f7773-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="f7773-122">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="f7773-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="f7773-123">string</span><span class="sxs-lookup"><span data-stu-id="f7773-123">string</span></span> | <span data-ttu-id="f7773-124">将录制的操作应用于的注册表项</span><span class="sxs-lookup"><span data-stu-id="f7773-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="f7773-125">string</span><span class="sxs-lookup"><span data-stu-id="f7773-125">string</span></span> | <span data-ttu-id="f7773-126">应用录制的操作的注册表值的数据类型，如二进制或字符串</span><span class="sxs-lookup"><span data-stu-id="f7773-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="f7773-127">string</span><span class="sxs-lookup"><span data-stu-id="f7773-127">string</span></span> | <span data-ttu-id="f7773-128">将录制的操作应用于的注册表值的名称</span><span class="sxs-lookup"><span data-stu-id="f7773-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="f7773-129">string</span><span class="sxs-lookup"><span data-stu-id="f7773-129">string</span></span> | <span data-ttu-id="f7773-130">录制的操作所应用于的注册表值的数据</span><span class="sxs-lookup"><span data-stu-id="f7773-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="f7773-131">string</span><span class="sxs-lookup"><span data-stu-id="f7773-131">string</span></span> | <span data-ttu-id="f7773-132">注册表值在被修改之前的原始名称</span><span class="sxs-lookup"><span data-stu-id="f7773-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="f7773-133">string</span><span class="sxs-lookup"><span data-stu-id="f7773-133">string</span></span> | <span data-ttu-id="f7773-134">注册表值在被修改之前的原始数据</span><span class="sxs-lookup"><span data-stu-id="f7773-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="f7773-135">string</span><span class="sxs-lookup"><span data-stu-id="f7773-135">string</span></span> | <span data-ttu-id="f7773-136">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="f7773-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="f7773-137">string</span><span class="sxs-lookup"><span data-stu-id="f7773-137">string</span></span> | <span data-ttu-id="f7773-138">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="f7773-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="f7773-139">string</span><span class="sxs-lookup"><span data-stu-id="f7773-139">string</span></span> | <span data-ttu-id="f7773-140">运行负责事件的进程的帐户 (SID) 的安全标识符</span><span class="sxs-lookup"><span data-stu-id="f7773-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="f7773-141">string</span><span class="sxs-lookup"><span data-stu-id="f7773-141">string</span></span> | <span data-ttu-id="f7773-142">启动事件的过程 (图像文件) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="f7773-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="f7773-143">string</span><span class="sxs-lookup"><span data-stu-id="f7773-143">string</span></span> | <span data-ttu-id="f7773-144">SHA-256 启动事件的过程 (图像文件) 。</span><span class="sxs-lookup"><span data-stu-id="f7773-144">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="f7773-145">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="f7773-145">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="f7773-146">string</span><span class="sxs-lookup"><span data-stu-id="f7773-146">string</span></span> | <span data-ttu-id="f7773-147">启动事件的过程 (映像文件) 的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="f7773-147">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="f7773-148">string</span><span class="sxs-lookup"><span data-stu-id="f7773-148">string</span></span> | <span data-ttu-id="f7773-149">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="f7773-149">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="f7773-150">int</span><span class="sxs-lookup"><span data-stu-id="f7773-150">int</span></span> | <span data-ttu-id="f7773-151">启动事件的进程的进程 ID (PID) </span><span class="sxs-lookup"><span data-stu-id="f7773-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="f7773-152">string</span><span class="sxs-lookup"><span data-stu-id="f7773-152">string</span></span> | <span data-ttu-id="f7773-153">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="f7773-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="f7773-154">datetime</span><span class="sxs-lookup"><span data-stu-id="f7773-154">datetime</span></span> | <span data-ttu-id="f7773-155">启动启动事件的进程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="f7773-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="f7773-156">string</span><span class="sxs-lookup"><span data-stu-id="f7773-156">string</span></span> | <span data-ttu-id="f7773-157">包含启动事件的过程 (图像文件) 的文件夹</span><span class="sxs-lookup"><span data-stu-id="f7773-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="f7773-158">int</span><span class="sxs-lookup"><span data-stu-id="f7773-158">int</span></span> | <span data-ttu-id="f7773-159">生成负责事件的进程的父进程 (PID) 的进程 ID</span><span class="sxs-lookup"><span data-stu-id="f7773-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="f7773-160">string</span><span class="sxs-lookup"><span data-stu-id="f7773-160">string</span></span> | <span data-ttu-id="f7773-161">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="f7773-161">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="f7773-162">datetime</span><span class="sxs-lookup"><span data-stu-id="f7773-162">datetime</span></span> | <span data-ttu-id="f7773-163">负责启动事件的进程的父项的日期和时间</span><span class="sxs-lookup"><span data-stu-id="f7773-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="f7773-164">string</span><span class="sxs-lookup"><span data-stu-id="f7773-164">string</span></span> | <span data-ttu-id="f7773-165">启动事件的进程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="f7773-165">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="f7773-166">Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。</span><span class="sxs-lookup"><span data-stu-id="f7773-166">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="f7773-167">这些完整性级别会影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="f7773-167">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="f7773-168">string</span><span class="sxs-lookup"><span data-stu-id="f7773-168">string</span></span> | <span data-ttu-id="f7773-169">指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动该事件的进程</span><span class="sxs-lookup"><span data-stu-id="f7773-169">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="f7773-170">long</span><span class="sxs-lookup"><span data-stu-id="f7773-170">long</span></span> | <span data-ttu-id="f7773-171">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="f7773-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f7773-172">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用</span><span class="sxs-lookup"><span data-stu-id="f7773-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="f7773-173">string</span><span class="sxs-lookup"><span data-stu-id="f7773-173">string</span></span> | <span data-ttu-id="f7773-174">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="f7773-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f7773-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="f7773-175">Related topics</span></span>
- [<span data-ttu-id="f7773-176">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="f7773-176">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f7773-177">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="f7773-177">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f7773-178">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="f7773-178">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f7773-179">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="f7773-179">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f7773-180">了解架构</span><span class="sxs-lookup"><span data-stu-id="f7773-180">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f7773-181">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="f7773-181">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
