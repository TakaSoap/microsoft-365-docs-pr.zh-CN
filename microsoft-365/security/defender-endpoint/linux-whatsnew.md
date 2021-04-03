---
title: 适用于 Linux 的 Microsoft Defender 终结点的新增功能
description: 适用于 Linux 的 Microsoft Defender ATP 的主要更改列表。
keywords: microsoft， defender， atp， linux， whatsnew， release
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580998"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="d9adf-104">适用于 Linux 的 Microsoft Defender 终结点的新增功能</span><span class="sxs-lookup"><span data-stu-id="d9adf-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="d9adf-105">101.25.63 (30.121022.12563.0) </span><span class="sxs-lookup"><span data-stu-id="d9adf-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="d9adf-106">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="d9adf-107">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="d9adf-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="d9adf-108">针对将整个装入点添加到防病毒排除列表的情况的性能改进。</span><span class="sxs-lookup"><span data-stu-id="d9adf-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="d9adf-109">在此版本之前，源自装入点的文件活动仍由产品进行处理。</span><span class="sxs-lookup"><span data-stu-id="d9adf-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="d9adf-110">从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能</span><span class="sxs-lookup"><span data-stu-id="d9adf-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="d9adf-111">向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。</span><span class="sxs-lookup"><span data-stu-id="d9adf-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="d9adf-112">若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="d9adf-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="d9adf-113">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="d9adf-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="d9adf-114">101.18.53</span></span>

- <span data-ttu-id="d9adf-115">适用于 Linux 的 EDR 现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="d9adf-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="d9adf-116">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="d9adf-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="d9adf-117">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="d9adf-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="d9adf-118">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="d9adf-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="d9adf-119">101.12.99</span></span>

- <span data-ttu-id="d9adf-120">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="d9adf-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="d9adf-121">101.04.76</span></span>

- <span data-ttu-id="d9adf-122">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="d9adf-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="d9adf-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="d9adf-123">101.03.48</span></span>

- <span data-ttu-id="d9adf-124">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="d9adf-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="d9adf-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="d9adf-125">101.02.55</span></span>

- <span data-ttu-id="d9adf-126">修复了产品有时在重启/升级后无法开始的问题</span><span class="sxs-lookup"><span data-stu-id="d9adf-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="d9adf-127">修复了跨产品升级持续保留代理设置的问题</span><span class="sxs-lookup"><span data-stu-id="d9adf-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="d9adf-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="d9adf-128">101.00.75</span></span>

- <span data-ttu-id="d9adf-129">添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="d9adf-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="d9adf-130">命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="d9adf-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="d9adf-131">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="d9adf-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="d9adf-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="d9adf-133">从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="d9adf-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="d9adf-134">这是因为文件路径有重大更改。</span><span class="sxs-lookup"><span data-stu-id="d9adf-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="d9adf-135">临时解决方案是删除较旧的程序包，然后安装较新的程序包。</span><span class="sxs-lookup"><span data-stu-id="d9adf-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="d9adf-136">此问题在较新版本中不存在。</span><span class="sxs-lookup"><span data-stu-id="d9adf-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="d9adf-137">防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="d9adf-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="d9adf-138">添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力</span><span class="sxs-lookup"><span data-stu-id="d9adf-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="d9adf-139">使程序包安装更可靠的改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="d9adf-140">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="d9adf-140">Performance improvements & bug fixes</span></span>
