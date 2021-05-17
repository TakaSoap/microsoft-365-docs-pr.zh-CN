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
ms.openlocfilehash: 6aaf370ef0222c6c4a7f920a2a5ed8951f988839
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933561"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="81c8e-104">Linux 上的 Microsoft Defender for Endpoint 的新增功能</span><span class="sxs-lookup"><span data-stu-id="81c8e-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="81c8e-105">101.25.72 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="81c8e-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="81c8e-106">Linux 上的 Microsoft Defender for Endpoint 现在可供美国政府客户预览使用。</span><span class="sxs-lookup"><span data-stu-id="81c8e-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="81c8e-107">有关详细信息，请参阅 [Microsoft Defender for Endpoint for US Government customers](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="81c8e-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="81c8e-108">修复了在 LINUX 上使用 Microsoft Defender for Endpoint（在带一个使用一个系统，而使用一个</span><span class="sxs-lookup"><span data-stu-id="81c8e-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="81c8e-109">性能改进& Bug 修复</span><span class="sxs-lookup"><span data-stu-id="81c8e-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="81c8e-110">101.25.63 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="81c8e-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="81c8e-111">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="81c8e-112">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="81c8e-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="81c8e-113">针对将整个装入点添加到防病毒排除列表的情况的性能改进。</span><span class="sxs-lookup"><span data-stu-id="81c8e-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="81c8e-114">在此版本之前，源自装入点的文件活动仍由产品进行处理。</span><span class="sxs-lookup"><span data-stu-id="81c8e-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="81c8e-115">从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能</span><span class="sxs-lookup"><span data-stu-id="81c8e-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="81c8e-116">向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。</span><span class="sxs-lookup"><span data-stu-id="81c8e-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="81c8e-117">若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="81c8e-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="81c8e-118">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="81c8e-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="81c8e-119">101.18.53</span></span>

- <span data-ttu-id="81c8e-120">EDR Linux 版本现已[发布](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="81c8e-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="81c8e-121">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="81c8e-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="81c8e-122">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="81c8e-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="81c8e-123">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="81c8e-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="81c8e-124">101.12.99</span></span>

- <span data-ttu-id="81c8e-125">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="81c8e-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="81c8e-126">101.04.76</span></span>

- <span data-ttu-id="81c8e-127">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="81c8e-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="81c8e-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="81c8e-128">101.03.48</span></span>

- <span data-ttu-id="81c8e-129">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="81c8e-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="81c8e-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="81c8e-130">101.02.55</span></span>

- <span data-ttu-id="81c8e-131">修复了产品有时在重启/升级后无法开始的问题</span><span class="sxs-lookup"><span data-stu-id="81c8e-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="81c8e-132">修复了跨产品升级持续保留代理设置的问题</span><span class="sxs-lookup"><span data-stu-id="81c8e-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="81c8e-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="81c8e-133">101.00.75</span></span>

- <span data-ttu-id="81c8e-134">添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="81c8e-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="81c8e-135">命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="81c8e-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="81c8e-136">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="81c8e-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="81c8e-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="81c8e-138">从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="81c8e-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="81c8e-139">这是因为文件路径有重大更改。</span><span class="sxs-lookup"><span data-stu-id="81c8e-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="81c8e-140">临时解决方案是删除较旧的程序包，然后安装较新的程序包。</span><span class="sxs-lookup"><span data-stu-id="81c8e-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="81c8e-141">此问题在较新版本中不存在。</span><span class="sxs-lookup"><span data-stu-id="81c8e-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="81c8e-142">防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="81c8e-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="81c8e-143">添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力</span><span class="sxs-lookup"><span data-stu-id="81c8e-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="81c8e-144">使程序包安装更可靠的改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="81c8e-145">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="81c8e-145">Performance improvements & bug fixes</span></span>
