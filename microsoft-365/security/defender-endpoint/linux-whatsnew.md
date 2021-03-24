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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055005"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="9ce8a-104">适用于 Linux 的 Microsoft Defender 终结点的新增功能</span><span class="sxs-lookup"><span data-stu-id="9ce8a-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="9ce8a-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="9ce8a-105">101.18.53</span></span>

- <span data-ttu-id="9ce8a-106">适用于 Linux 的 EDR 现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="9ce8a-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="9ce8a-107">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="9ce8a-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="9ce8a-108">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="9ce8a-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="9ce8a-109">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="9ce8a-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="9ce8a-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="9ce8a-110">101.12.99</span></span>

- <span data-ttu-id="9ce8a-111">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="9ce8a-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="9ce8a-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="9ce8a-112">101.04.76</span></span>

- <span data-ttu-id="9ce8a-113">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="9ce8a-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="9ce8a-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="9ce8a-114">101.03.48</span></span>

- <span data-ttu-id="9ce8a-115">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="9ce8a-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="9ce8a-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="9ce8a-116">101.02.55</span></span>

- <span data-ttu-id="9ce8a-117">修复了产品有时在重启/升级后无法开始的问题</span><span class="sxs-lookup"><span data-stu-id="9ce8a-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="9ce8a-118">修复了跨产品升级持续保留代理设置的问题</span><span class="sxs-lookup"><span data-stu-id="9ce8a-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="9ce8a-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="9ce8a-119">101.00.75</span></span>

- <span data-ttu-id="9ce8a-120">添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`</span><span class="sxs-lookup"><span data-stu-id="9ce8a-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="9ce8a-121">命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="9ce8a-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="9ce8a-122">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="9ce8a-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="9ce8a-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="9ce8a-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="9ce8a-124">从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="9ce8a-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="9ce8a-125">这是因为文件路径有重大更改。</span><span class="sxs-lookup"><span data-stu-id="9ce8a-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="9ce8a-126">临时解决方案是删除较旧的程序包，然后安装较新的程序包。</span><span class="sxs-lookup"><span data-stu-id="9ce8a-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="9ce8a-127">此问题在较新版本中不存在。</span><span class="sxs-lookup"><span data-stu-id="9ce8a-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="9ce8a-128">防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="9ce8a-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="9ce8a-129">添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力</span><span class="sxs-lookup"><span data-stu-id="9ce8a-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="9ce8a-130">使程序包安装更可靠的改进</span><span class="sxs-lookup"><span data-stu-id="9ce8a-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="9ce8a-131">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="9ce8a-131">Performance improvements & bug fixes</span></span>
