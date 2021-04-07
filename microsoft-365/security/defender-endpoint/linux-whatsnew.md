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
ms.openlocfilehash: 7a55d254c20506913d0995bffc941a67bb34a38e
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615431"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>适用于 Linux 的 Microsoft Defender 终结点的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0) 

- Microsoft Defender for Endpoint for Linux 现已在预览版中提供给美国政府客户。 有关详细信息，请参阅 [Microsoft Defender for Endpoint for US Government customers](gov.md)。
- 修复了在具有一个使用有一个使用有一个更新的文件系统的系统上使用适用于 Linux 的 Microsoft Defender for Endpoint 导致操作系统挂起的问题
- 性能改进& Bug 修复

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0) 

- Bug 修复&性能改进

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0) 

- 针对将整个装入点添加到防病毒排除列表的情况的性能改进。 在此版本之前，源自装入点的文件活动仍由产品进行处理。 从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能
- 向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。 若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`
- Bug 修复&性能改进

## <a name="1011853"></a>101.18.53

- 适用于 Linux 的 EDR 现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- 添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () 
- 使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录
- Bug 修复&性能改进

## <a name="1011299"></a>101.12.99

- Bug 修复&性能改进

## <a name="1010476"></a>101.04.76

- Bug 修复

## <a name="1010348"></a>101.03.48

- Bug 修复

## <a name="1010255"></a>101.02.55

- 修复了产品有时在重启/升级后无法开始的问题
- 修复了跨产品升级持续保留代理设置的问题

## <a name="1010075"></a>101.00.75

- 添加了对以下文件系统类型的支持 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` ：、、、、 `udf` 和 `vfat`
- 命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。
- Bug 修复&性能改进

## <a name="1009070"></a>100.90.70

> [!WARNING]
> 从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。 这是因为文件路径有重大更改。 临时解决方案是删除较旧的程序包，然后安装较新的程序包。 此问题在较新版本中不存在。

- 防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)
- 添加了通过 [命令行工具](linux-support-perf.md) `mdatp` 解决性能问题的能力
- 使程序包安装更可靠的改进
- Bug 修复&性能改进
