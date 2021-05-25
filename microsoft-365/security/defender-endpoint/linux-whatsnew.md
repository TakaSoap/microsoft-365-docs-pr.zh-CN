---
title: Linux 上的 Microsoft Defender for Endpoint 的新增功能
description: Linux 上的 Microsoft Defender for Endpoint 的主要更改列表。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， whatsnew， release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651124"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="8c262-104">Linux 上的 Microsoft Defender for Endpoint 的新增功能</span><span class="sxs-lookup"><span data-stu-id="8c262-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="8c262-105">101.29.64 (30.121042.12964.0) </span><span class="sxs-lookup"><span data-stu-id="8c262-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="8c262-106">从此版本开始，在通过命令行客户端触发的按需防病毒扫描期间检测到的威胁将自动修正。</span><span class="sxs-lookup"><span data-stu-id="8c262-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="8c262-107">扫描期间通过用户界面触发的威胁仍然需要手动操作。</span><span class="sxs-lookup"><span data-stu-id="8c262-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="8c262-108">`mdatp diagnostic real-time-protection-statistics` 现在支持两个其他开关：</span><span class="sxs-lookup"><span data-stu-id="8c262-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="8c262-109">`--sort`：按扫描的文件总数对输出进行降序排序</span><span class="sxs-lookup"><span data-stu-id="8c262-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="8c262-110">`--top N`：显示前 N 个 (仅在指定了值 `--sort` 时) </span><span class="sxs-lookup"><span data-stu-id="8c262-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="8c262-111">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="8c262-112">101.25.72 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="8c262-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="8c262-113">Linux 上的 Microsoft Defender for Endpoint 现在可供美国政府客户预览使用。</span><span class="sxs-lookup"><span data-stu-id="8c262-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="8c262-114">有关详细信息，请参阅 [Microsoft Defender for Endpoint for US Government customers](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="8c262-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="8c262-115">修复了在 LINUX 上使用 Microsoft Defender for Endpoint（在带一个使用一个系统，而使用一个</span><span class="sxs-lookup"><span data-stu-id="8c262-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="8c262-116">性能改进& Bug 修复</span><span class="sxs-lookup"><span data-stu-id="8c262-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="8c262-117">101.25.63 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="8c262-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="8c262-118">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="8c262-119">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="8c262-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="8c262-120">针对将整个装入点添加到防病毒排除列表的情况的性能改进。</span><span class="sxs-lookup"><span data-stu-id="8c262-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="8c262-121">在此版本之前，源自装入点的文件活动仍由产品进行处理。</span><span class="sxs-lookup"><span data-stu-id="8c262-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="8c262-122">从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能</span><span class="sxs-lookup"><span data-stu-id="8c262-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="8c262-123">向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。</span><span class="sxs-lookup"><span data-stu-id="8c262-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="8c262-124">若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="8c262-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="8c262-125">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="8c262-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="8c262-126">101.18.53</span></span>

- <span data-ttu-id="8c262-127">EDR Linux 版本现已[发布](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="8c262-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="8c262-128">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="8c262-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="8c262-129">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="8c262-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="8c262-130">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="8c262-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="8c262-131">101.12.99</span></span>

- <span data-ttu-id="8c262-132">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="8c262-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="8c262-133">101.04.76</span></span>

- <span data-ttu-id="8c262-134">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="8c262-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="8c262-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="8c262-135">101.03.48</span></span>

- <span data-ttu-id="8c262-136">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="8c262-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="8c262-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="8c262-137">101.02.55</span></span>

- <span data-ttu-id="8c262-138">修复了产品有时在重启/升级后无法开始的问题</span><span class="sxs-lookup"><span data-stu-id="8c262-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="8c262-139">修复了跨产品升级持续保留代理设置的问题</span><span class="sxs-lookup"><span data-stu-id="8c262-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="8c262-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="8c262-140">101.00.75</span></span>

- <span data-ttu-id="8c262-141">添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="8c262-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="8c262-142">命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="8c262-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="8c262-143">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="8c262-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="8c262-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="8c262-145">从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="8c262-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="8c262-146">这是因为文件路径有重大更改。</span><span class="sxs-lookup"><span data-stu-id="8c262-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="8c262-147">临时解决方案是删除较旧的程序包，然后安装较新的程序包。</span><span class="sxs-lookup"><span data-stu-id="8c262-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="8c262-148">此问题在较新版本中不存在。</span><span class="sxs-lookup"><span data-stu-id="8c262-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="8c262-149">防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="8c262-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="8c262-150">添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力</span><span class="sxs-lookup"><span data-stu-id="8c262-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="8c262-151">使程序包安装更可靠的改进</span><span class="sxs-lookup"><span data-stu-id="8c262-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="8c262-152">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="8c262-152">Performance improvements & bug fixes</span></span>
