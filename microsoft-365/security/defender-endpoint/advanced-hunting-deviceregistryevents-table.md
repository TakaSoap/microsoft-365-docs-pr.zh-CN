---
title: 高级搜寻架构中的 DeviceRegistryEvents 表
description: 了解可以从高级搜寻架构的 DeviceRegistryEvents 表查询的注册表事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， deviceregistryevents， 注册表， 键， 子项， 值， RegistryEvents
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
ms.openlocfilehash: 39ea04e2faa43d230ecdc281967b6a9e8f8c9abe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056146"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="a54a2-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="a54a2-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a54a2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a54a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="a54a2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a54a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a54a2-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a54a2-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a54a2-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a54a2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="a54a2-109">高级 `DeviceRegistryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关创建和修改注册表项的信息。</span><span class="sxs-lookup"><span data-stu-id="a54a2-109">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="a54a2-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="a54a2-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a54a2-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="a54a2-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="a54a2-112">列名称</span><span class="sxs-lookup"><span data-stu-id="a54a2-112">Column name</span></span> | <span data-ttu-id="a54a2-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="a54a2-113">Data type</span></span> | <span data-ttu-id="a54a2-114">说明</span><span class="sxs-lookup"><span data-stu-id="a54a2-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a54a2-115">datetime</span><span class="sxs-lookup"><span data-stu-id="a54a2-115">datetime</span></span> | <span data-ttu-id="a54a2-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a54a2-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a54a2-117">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-117">string</span></span> | <span data-ttu-id="a54a2-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a54a2-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a54a2-119">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-119">string</span></span> | <span data-ttu-id="a54a2-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="a54a2-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="a54a2-121">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-121">string</span></span> | <span data-ttu-id="a54a2-122">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="a54a2-122">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="a54a2-123">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-123">string</span></span> | <span data-ttu-id="a54a2-124">已记录操作所应用到的注册表项</span><span class="sxs-lookup"><span data-stu-id="a54a2-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="a54a2-125">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-125">string</span></span> | <span data-ttu-id="a54a2-126">已记录操作所应用到的注册表值的数据类型（如二进制或字符串）</span><span class="sxs-lookup"><span data-stu-id="a54a2-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="a54a2-127">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-127">string</span></span> | <span data-ttu-id="a54a2-128">已记录操作所应用到的注册表值的名称</span><span class="sxs-lookup"><span data-stu-id="a54a2-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="a54a2-129">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-129">string</span></span> | <span data-ttu-id="a54a2-130">已记录操作应用于的注册表值的数据</span><span class="sxs-lookup"><span data-stu-id="a54a2-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="a54a2-131">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-131">string</span></span> | <span data-ttu-id="a54a2-132">修改前注册表值的原始名称</span><span class="sxs-lookup"><span data-stu-id="a54a2-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="a54a2-133">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-133">string</span></span> | <span data-ttu-id="a54a2-134">修改前注册表值的原始数据</span><span class="sxs-lookup"><span data-stu-id="a54a2-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a54a2-135">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-135">string</span></span> | <span data-ttu-id="a54a2-136">运行负责事件的进程的帐户的域</span><span class="sxs-lookup"><span data-stu-id="a54a2-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a54a2-137">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-137">string</span></span> | <span data-ttu-id="a54a2-138">运行负责事件的进程的帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="a54a2-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a54a2-139">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-139">string</span></span> | <span data-ttu-id="a54a2-140">安全 (SID) 运行负责事件的进程的帐户的 SID 标识符</span><span class="sxs-lookup"><span data-stu-id="a54a2-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a54a2-141">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-141">string</span></span> | <span data-ttu-id="a54a2-142">启动事件 (映像) 的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a54a2-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a54a2-143">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-143">string</span></span> | <span data-ttu-id="a54a2-144">启动事件的进程 (MD5) 文件哈希</span><span class="sxs-lookup"><span data-stu-id="a54a2-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a54a2-145">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-145">string</span></span> | <span data-ttu-id="a54a2-146">启动事件的进程的名称</span><span class="sxs-lookup"><span data-stu-id="a54a2-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a54a2-147">int</span><span class="sxs-lookup"><span data-stu-id="a54a2-147">int</span></span> | <span data-ttu-id="a54a2-148">进程 ID (PID) 启动事件的过程的 PID</span><span class="sxs-lookup"><span data-stu-id="a54a2-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a54a2-149">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-149">string</span></span> | <span data-ttu-id="a54a2-150">用于运行启动事件的进程的命令行</span><span class="sxs-lookup"><span data-stu-id="a54a2-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a54a2-151">datetime</span><span class="sxs-lookup"><span data-stu-id="a54a2-151">datetime</span></span> | <span data-ttu-id="a54a2-152">启动事件的过程的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a54a2-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a54a2-153">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-153">string</span></span> | <span data-ttu-id="a54a2-154">包含启动事件 (进程) 文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="a54a2-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a54a2-155">int</span><span class="sxs-lookup"><span data-stu-id="a54a2-155">int</span></span> | <span data-ttu-id="a54a2-156">进程 ID (PID) 生成负责事件的进程的父进程的 PID</span><span class="sxs-lookup"><span data-stu-id="a54a2-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a54a2-157">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-157">string</span></span> | <span data-ttu-id="a54a2-158">生成负责事件的进程的父进程的名称</span><span class="sxs-lookup"><span data-stu-id="a54a2-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a54a2-159">datetime</span><span class="sxs-lookup"><span data-stu-id="a54a2-159">datetime</span></span> | <span data-ttu-id="a54a2-160">启动负责事件的进程的父级的日期和时间</span><span class="sxs-lookup"><span data-stu-id="a54a2-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a54a2-161">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-161">string</span></span> | <span data-ttu-id="a54a2-162">启动事件的过程的完整性级别。</span><span class="sxs-lookup"><span data-stu-id="a54a2-162">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a54a2-163">Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。</span><span class="sxs-lookup"><span data-stu-id="a54a2-163">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a54a2-164">这些完整性级别影响对资源的权限</span><span class="sxs-lookup"><span data-stu-id="a54a2-164">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a54a2-165">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-165">string</span></span> | <span data-ttu-id="a54a2-166">指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升</span><span class="sxs-lookup"><span data-stu-id="a54a2-166">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="a54a2-167">long</span><span class="sxs-lookup"><span data-stu-id="a54a2-167">long</span></span> | <span data-ttu-id="a54a2-168">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="a54a2-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a54a2-169">若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用</span><span class="sxs-lookup"><span data-stu-id="a54a2-169">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a54a2-170">string</span><span class="sxs-lookup"><span data-stu-id="a54a2-170">string</span></span> | <span data-ttu-id="a54a2-171">应用程序防护用于隔离浏览器活动的虚拟化容器的标识符</span><span class="sxs-lookup"><span data-stu-id="a54a2-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a54a2-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="a54a2-172">Related topics</span></span>
- [<span data-ttu-id="a54a2-173">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="a54a2-173">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a54a2-174">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a54a2-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a54a2-175">了解架构</span><span class="sxs-lookup"><span data-stu-id="a54a2-175">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
