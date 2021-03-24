---
title: 高级搜寻架构中的 DeviceRegistryEvents 表
description: 了解可以从高级搜寻架构的 DeviceRegistryEvents 表查询的注册表事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 注册表事件， 注册表， DeviceRegistryEvents， key， 子项， 值
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
ms.openlocfilehash: b9bb95f8220327e3be7cc2598f2f49fd868d1b89
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055259"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="47905-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="47905-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="47905-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="47905-105">**Applies to:**</span></span>
- <span data-ttu-id="47905-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47905-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="47905-107">高级 `DeviceRegistryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关创建和修改注册表项的信息。</span><span class="sxs-lookup"><span data-stu-id="47905-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="47905-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="47905-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="47905-109">有关表支持的事件类型 () ，请使用安全中心中提供的内置架构 `ActionType` 参考。</span><span class="sxs-lookup"><span data-stu-id="47905-109">For detailed information about the events types (`ActionType` values) supported by a table, use the  built-in schema reference available in the security center.</span></span>

<span data-ttu-id="47905-110">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="47905-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="47905-111">列名称</span><span class="sxs-lookup"><span data-stu-id="47905-111">Column name</span></span> | <span data-ttu-id="47905-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="47905-112">Data type</span></span> | <span data-ttu-id="47905-113">说明</span><span class="sxs-lookup"><span data-stu-id="47905-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="47905-114">datetime</span><span class="sxs-lookup"><span data-stu-id="47905-114">datetime</span></span> | <span data-ttu-id="47905-115">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="47905-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="47905-116">string</span><span class="sxs-lookup"><span data-stu-id="47905-116">string</span></span> | <span data-ttu-id="47905-117">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="47905-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="47905-118">string</span><span class="sxs-lookup"><span data-stu-id="47905-118">string</span></span> | <span data-ttu-id="47905-119">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="47905-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="47905-120">string</span><span class="sxs-lookup"><span data-stu-id="47905-120">string</span></span> | <span data-ttu-id="47905-121">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="47905-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="47905-122">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="47905-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="47905-123">string</span><span class="sxs-lookup"><span data-stu-id="47905-123">string</span></span> | <span data-ttu-id="47905-124">已记录操作所应用到的注册表项</span><span class="sxs-lookup"><span data-stu-id="47905-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="47905-125">string</span><span class="sxs-lookup"><span data-stu-id="47905-125">string</span></span> | <span data-ttu-id="47905-126">已记录操作所应用到的注册表值的数据类型（如二进制或字符串）</span><span class="sxs-lookup"><span data-stu-id="47905-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="47905-127">string</span><span class="sxs-lookup"><span data-stu-id="47905-127">string</span></span> | <span data-ttu-id="47905-128">已记录操作所应用到的注册表值的名称</span><span class="sxs-lookup"><span data-stu-id="47905-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="47905-129">string</span><span class="sxs-lookup"><span data-stu-id="47905-129">string</span></span> | <span data-ttu-id="47905-130">已记录操作应用于的注册表值的数据</span><span class="sxs-lookup"><span data-stu-id="47905-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryKey` | <span data-ttu-id="47905-131">string</span><span class="sxs-lookup"><span data-stu-id="47905-131">string</span></span> | <span data-ttu-id="47905-132">修改前注册表值的原始注册表项</span><span class="sxs-lookup"><span data-stu-id="47905-132">Original registry key of the registry value before it was modified</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="47905-133">string</span><span class="sxs-lookup"><span data-stu-id="47905-133">string</span></span> | <span data-ttu-id="47905-134">修改前注册表值的原始名称</span><span class="sxs-lookup"><span data-stu-id="47905-134">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="47905-135">string</span><span class="sxs-lookup"><span data-stu-id="47905-135">string</span></span> | <span data-ttu-id="47905-136">修改前注册表值的原始数据</span><span class="sxs-lookup"><span data-stu-id="47905-136">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="47905-137">string</span><span class="sxs-lookup"><span data-stu-id="47905-137">string</span></span> | <span data-ttu-id="47905-138">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="47905-138">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="47905-139">string</span><span class="sxs-lookup"><span data-stu-id="47905-139">string</span></span> | <span data-ttu-id="47905-140">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="47905-140">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="47905-141">string</span><span class="sxs-lookup"><span data-stu-id="47905-141">string</span></span> | <span data-ttu-id="47905-142">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="47905-142">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="47905-143">string</span><span class="sxs-lookup"><span data-stu-id="47905-143">string</span></span> | <span data-ttu-id="47905-144">用户主体 (UPN) 运行负责事件的进程的帐户的名称</span><span class="sxs-lookup"><span data-stu-id="47905-144">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="47905-145">string</span><span class="sxs-lookup"><span data-stu-id="47905-145">string</span></span> | <span data-ttu-id="47905-146">运行负责事件的进程的用户帐户的 Azure AD 对象 ID</span><span class="sxs-lookup"><span data-stu-id="47905-146">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="47905-147">string</span><span class="sxs-lookup"><span data-stu-id="47905-147">string</span></span> | <span data-ttu-id="47905-148">启动事件 (映像) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="47905-148">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="47905-149">string</span><span class="sxs-lookup"><span data-stu-id="47905-149">string</span></span> | <span data-ttu-id="47905-150">启动事件 (映像文件) SHA-256。</span><span class="sxs-lookup"><span data-stu-id="47905-150">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="47905-151">通常不会填充此字段 — 可用时使用 SHA1 列。</span><span class="sxs-lookup"><span data-stu-id="47905-151">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="47905-152">string</span><span class="sxs-lookup"><span data-stu-id="47905-152">string</span></span> | <span data-ttu-id="47905-153">启动事件的进程 (MD5) 文件哈希</span><span class="sxs-lookup"><span data-stu-id="47905-153">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="47905-154">string</span><span class="sxs-lookup"><span data-stu-id="47905-154">string</span></span> | <span data-ttu-id="47905-155">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="47905-155">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="47905-156">long</span><span class="sxs-lookup"><span data-stu-id="47905-156">long</span></span> | <span data-ttu-id="47905-157">运行负责事件的进程的文件的大小</span><span class="sxs-lookup"><span data-stu-id="47905-157">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="47905-158">int</span><span class="sxs-lookup"><span data-stu-id="47905-158">int</span></span> | <span data-ttu-id="47905-159">进程 ID (PID) 启动事件的过程的 PID</span><span class="sxs-lookup"><span data-stu-id="47905-159">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="47905-160">string</span><span class="sxs-lookup"><span data-stu-id="47905-160">string</span></span> | <span data-ttu-id="47905-161">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="47905-161">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="47905-162">datetime</span><span class="sxs-lookup"><span data-stu-id="47905-162">datetime</span></span> | <span data-ttu-id="47905-163">启动事件的过程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="47905-163">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="47905-164">string</span><span class="sxs-lookup"><span data-stu-id="47905-164">string</span></span> | <span data-ttu-id="47905-165">包含启动事件 (进程) 文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="47905-165">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="47905-166">int</span><span class="sxs-lookup"><span data-stu-id="47905-166">int</span></span> | <span data-ttu-id="47905-167">进程 ID (PID) 生成负责事件的进程的父进程的 PID</span><span class="sxs-lookup"><span data-stu-id="47905-167">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="47905-168">string</span><span class="sxs-lookup"><span data-stu-id="47905-168">string</span></span> | <span data-ttu-id="47905-169">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="47905-169">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="47905-170">datetime</span><span class="sxs-lookup"><span data-stu-id="47905-170">datetime</span></span> | <span data-ttu-id="47905-171">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="47905-171">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="47905-172">string</span><span class="sxs-lookup"><span data-stu-id="47905-172">string</span></span> | <span data-ttu-id="47905-173">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="47905-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="47905-174">Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。</span><span class="sxs-lookup"><span data-stu-id="47905-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="47905-175">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="47905-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="47905-176">string</span><span class="sxs-lookup"><span data-stu-id="47905-176">string</span></span> | <span data-ttu-id="47905-177">指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升</span><span class="sxs-lookup"><span data-stu-id="47905-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="47905-178">long</span><span class="sxs-lookup"><span data-stu-id="47905-178">long</span></span> | <span data-ttu-id="47905-179">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="47905-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="47905-180">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用</span><span class="sxs-lookup"><span data-stu-id="47905-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="47905-181">string</span><span class="sxs-lookup"><span data-stu-id="47905-181">string</span></span> | <span data-ttu-id="47905-182">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="47905-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="47905-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="47905-183">Related topics</span></span>
- [<span data-ttu-id="47905-184">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="47905-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="47905-185">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="47905-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="47905-186">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="47905-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="47905-187">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="47905-187">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="47905-188">了解架构</span><span class="sxs-lookup"><span data-stu-id="47905-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="47905-189">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="47905-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
