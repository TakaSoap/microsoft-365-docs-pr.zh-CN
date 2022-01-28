---
title: Linux 上的 Microsoft Defender for Endpoint 的新增功能
description: Linux 上的 Microsoft Defender for Endpoint 的主要更改列表。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， whatsnew， release
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 4091a5945bbd754fb78bb957c46bd2ea5636e64d
ms.sourcegitcommit: 2c3b737e71038f843ef9e9ff4d5b99d6110b8ec5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2022
ms.locfileid: "62265471"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Linux 上的 Microsoft Defender for Endpoint 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="1015662-30121122156620"></a>101.56.62 (30.121122.15662.0) 

- 修复了 101.53.02 中引入并影响多个客户的产品崩溃

## <a name="1015302-30121112153020"></a>101.53.02 (30.121112.15302.0) 

- Bug 修复&性能改进

## <a name="1015257-30121092152570"></a>101.52.57 (30.121092.15257.0) 

- 添加了检测应用程序使用的易受攻击的 log4j Java的功能。 定期检查计算机以运行具有已加载的 log4j Java进程。 该信息将报告给 Microsoft Defender 终结点后端，并公开在门户的漏洞管理区域中。

## <a name="1014776-30121092147760"></a>101.47.76 (30.121092.14776.0) 

- 向命令行工具添加了一个新开关，以控制在按需扫描过程中是否扫描存档。 这可以通过 进行配置 `mdatp config scan-archives --value [enabled/disabled]`。 默认情况下，这设置为 `enabled`。
- 错误修补程序

## <a name="1014513-30121082145130"></a>101.45.13 (30.121082.14513.0) 

- 从此版本开始，我们将为以下部分提供 Microsoft Defender for Endpoint 支持： 
  - RHEL6.7-6.10 和 CentOS6.7-6.10 版本。
  - Amazon Linux 2
  - Fedora 33 或更高版本
- 错误修补程序


## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0) 

- 向命令行工具添加了新开关：
  - 控制按需扫描的并行度。 这可以通过 进行配置 `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`。 默认情况下，使用 的并行 `2` 度。
  - 控制启用还是禁用安全智能更新后的扫描。 这可以通过 进行配置 `mdatp config scan-after-definition-update --value [enabled/disabled]`。 默认情况下，这设置为 `enabled`。
- 更改产品日志级别现在需要提升
- 错误修补程序

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0) 

- Bug 修复&性能改进

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0) 

- Bug 修复&性能改进

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0) 

- 从此版本开始，在通过命令行客户端触发的按需防病毒扫描期间检测到的威胁将自动修正。 扫描期间通过用户界面触发的威胁仍然需要手动操作。
- `mdatp diagnostic real-time-protection-statistics` 现在支持两个其他开关：
  - `--sort`：按扫描的文件总数对输出进行降序排序
  - `--top N`：显示前 N 个 (仅在指定了 `--sort` 值时) 
- Bug 修复&性能改进

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0) 

- Linux 上的 Microsoft Defender for Endpoint 现在可供美国政府客户预览使用。 有关详细信息，请参阅 [适用于美国政府终结点客户的 Microsoft Defender](gov.md)。
- 修复了在 LINUX 上使用 Microsoft Defender for Endpoint（在带一个使用有一个使用有一个更新的系统）的系统上导致操作系统挂起的问题
- 性能改进& Bug 修复

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0) 

- Bug 修复&性能改进

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0) 

- 针对将整个装入点添加到防病毒排除列表的情况的性能改进。 在此版本之前，源自装入点的文件活动仍由产品进行处理。 从此版本开始，将禁止排除装入点的文件活动，从而提升产品性能
- 向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。 若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`
- Bug 修复&性能改进

## <a name="1011853"></a>101.18.53

- EDR Linux 版本现已[普遍可用](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- 添加了一个新的命令行开关 (`--ignore-exclusions`) 自定义扫描过程中忽略 AV 排除 `mdatp scan custom` () 
- 使用 `mdatp diagnostic create` 新的参数扩展 `--path [directory]` () ，该参数允许将诊断日志保存到其他目录
- Bug 修复&性能改进

## <a name="1011299"></a>101.12.99

- Bug 修复&性能改进

## <a name="1010476"></a>101.04.76

- 错误修补程序

## <a name="1010348"></a>101.03.48

- 错误修补程序

## <a name="1010255"></a>101.02.55

- 修复了产品有时在重启/升级后无法开始的问题
- 修复了跨产品升级持续保留代理设置的问题

## <a name="1010075"></a>101.00.75

- 添加了对以下文件系统类型的支持：`ecryptfs``nfs``fuseblk``fuse``overlay``ramfs``jfs`、、`reiserfs`、`udf`、 和`vfat`
- 命令行工具 [的新语法](linux-resources.md#configure-from-the-command-line)。
- Bug 修复&性能改进

## <a name="1009070"></a>100.90.70

> [!WARNING]
> 从低于 100.90.70 的产品版本升级已安装的程序包时，基于 Red Hat 和 SLES 分发的更新可能会失败。 这是因为文件路径有重大更改。 临时解决方案是删除较旧的程序包，然后安装较新的程序包。 此问题在较新版本中不存在。

- 防病毒 [排除项现在支持通配符](linux-exclusions.md#supported-exclusion-types)
- 添加了通过[命令行工具](linux-support-perf.md)`mdatp`解决性能问题的能力
- 使程序包安装更可靠的改进
- Bug 修复&性能改进
