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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198773"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="917ac-104">适用于 Linux 的 Microsoft Defender 终结点的新增功能</span><span class="sxs-lookup"><span data-stu-id="917ac-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="917ac-105">101.23.64 (30.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="917ac-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="917ac-106">针对将整个装入点添加到防病毒排除列表的情况的性能改进。</span><span class="sxs-lookup"><span data-stu-id="917ac-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="917ac-107">在此版本之前，源自装入点的文件活动仍由产品进行处理。</span><span class="sxs-lookup"><span data-stu-id="917ac-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="917ac-108">从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能</span><span class="sxs-lookup"><span data-stu-id="917ac-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="917ac-109">向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。</span><span class="sxs-lookup"><span data-stu-id="917ac-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="917ac-110">若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="917ac-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="917ac-111">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="917ac-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="917ac-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="917ac-112">101.18.53</span></span>

- <span data-ttu-id="917ac-113">适用于 Linux 的 EDR 现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="917ac-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="917ac-114">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="917ac-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="917ac-115">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="917ac-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="917ac-116">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="917ac-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="917ac-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="917ac-117">101.12.99</span></span>

- <span data-ttu-id="917ac-118">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="917ac-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="917ac-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="917ac-119">101.04.76</span></span>

- <span data-ttu-id="917ac-120">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="917ac-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="917ac-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="917ac-121">101.03.48</span></span>

- <span data-ttu-id="917ac-122">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="917ac-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="917ac-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="917ac-123">101.02.55</span></span>

- <span data-ttu-id="917ac-124">修复了产品有时在重启/升级后无法开始的问题</span><span class="sxs-lookup"><span data-stu-id="917ac-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="917ac-125">修复了跨产品升级持续保留代理设置的问题</span><span class="sxs-lookup"><span data-stu-id="917ac-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="917ac-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="917ac-126">101.00.75</span></span>

- <span data-ttu-id="917ac-127">添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="917ac-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="917ac-128">命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="917ac-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="917ac-129">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="917ac-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="917ac-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="917ac-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="917ac-131">从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="917ac-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="917ac-132">这是因为文件路径有重大更改。</span><span class="sxs-lookup"><span data-stu-id="917ac-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="917ac-133">临时解决方案是删除较旧的程序包，然后安装较新的程序包。</span><span class="sxs-lookup"><span data-stu-id="917ac-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="917ac-134">此问题在较新版本中不存在。</span><span class="sxs-lookup"><span data-stu-id="917ac-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="917ac-135">防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="917ac-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="917ac-136">添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力</span><span class="sxs-lookup"><span data-stu-id="917ac-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="917ac-137">使程序包安装更可靠的改进</span><span class="sxs-lookup"><span data-stu-id="917ac-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="917ac-138">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="917ac-138">Performance improvements & bug fixes</span></span>
