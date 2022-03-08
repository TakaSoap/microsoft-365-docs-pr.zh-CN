---
title: Linux 资源上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍 Linux 上的 Microsoft Defender for Endpoint 的资源，包括如何卸载它、如何收集诊断日志、CLI 命令以及产品的已知问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a32c8c91350218da619de18e0b1b398a93bf7fda
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312628"
---
# <a name="resources"></a>资源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

## <a name="collect-diagnostic-information"></a>收集诊断信息

如果可以重现问题，请首先增加日志记录级别，运行系统一段时间，然后将日志记录级别还原为默认值。

1. 提高日志记录级别：

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 重现问题。

3. 运行以下命令以备份适用于终结点日志的 Defender。 这些文件将存储在存档.zip内部。

   ```bash
   sudo mdatp diagnostic create
   ```

    在操作成功后，此命令还会输出备份的文件路径：

   ```Output
   Diagnostic file created: <path to file>
   ```

4. 还原日志记录级别：

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>记录安装问题

如果在安装过程中发生错误，安装程序将只报告常规故障。

详细日志将保存到 `/var/log/microsoft/mdatp/install.log`。
如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。

## <a name="uninstall"></a>卸载

有几种方法可以卸载 Linux 上的 Defender for Endpoint。 如果你使用的是配置工具（如"开发工具"，请按照配置工具的程序包卸载说明操作）。

### <a name="manual-uninstallation"></a>手动卸载

- `sudo yum remove mdatp` For RHEL and variants (CentOS and Oracle Linux) .
- `sudo zypper remove mdatp` 用于 SLES 和变量。
- `sudo apt-get purge mdatp` 用于 Ubuntu 和 Debian 系统。

## <a name="configure-from-the-command-line"></a>从命令行配置

可以通过命令行完成重要任务，如控制产品设置和触发按需扫描。

### <a name="global-options"></a>全局选项

默认情况下，命令行工具以可读格式输出结果。 此外，该工具还支持将结果输出为 JSON，这适用于自动化方案。 若要将输出更改为 JSON，请传递给 `--output json` 以下任一命令。

### <a name="supported-commands"></a>支持的命令

下表列出了一些最常见方案的命令。 从 `mdatp help` 终端运行以查看受支持命令的完整列表。

<br>

****

|Group|应用场景|命令|
|---|---|---|
|配置|打开/关闭实时保护|`mdatp config real-time-protection --value [enabled\|disabled]`|
|配置|打开/关闭行为监视|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|配置|打开/关闭云保护|`mdatp config cloud --value [enabled\|disabled]`|
|配置|打开/关闭产品诊断|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|配置|打开/关闭自动提交示例|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|配置|打开/关闭 AV 被动模式|`mdatp config passive-mode --value [enabled\|disabled]`|
|配置|添加/删除文件扩展名的防病毒排除项|`mdatp exclusion extension [add\|remove] --name [extension]`|
|配置|添加/删除文件的防病毒排除项|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|配置|添加/删除目录的防病毒排除|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|配置|添加/删除某个进程的防病毒排除项|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|配置|列出所有防病毒排除项|`mdatp exclusion list`|
|配置|向允许列表添加威胁名称|`mdatp threat allowed add --name [threat-name]`|
|配置|从允许列表中删除威胁名称|`mdatp threat allowed remove --name [threat-name]`|
|配置|列出所有允许的威胁名称|`mdatp threat allowed list`|
|配置|打开 PUA 保护|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|配置|关闭 PUA 保护|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|配置|打开 PUA 保护的审核模式|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|配置|配置按需扫描的并行度|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|配置|在安全智能更新后打开/关闭扫描|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|配置|仅按需扫描 (/关闭存档) |`mdatp config scan-archives --value [enabled/disabled]`|
|诊断|更改日志级别|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|诊断|生成诊断日志|`mdatp diagnostic create --path [directory]`|
|运行状况|检查产品的运行状况|`mdatp health`|
|保护|扫描路径|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保护|执行快速扫描|`mdatp scan quick`|
|保护|执行完全扫描|`mdatp scan full`|
|保护|取消正在进行的按需扫描|`mdatp scan cancel`|
|保护|请求安全智能更新|`mdatp definitions update`|
|保护历史记录|打印完整保护历史记录|`mdatp threat list`|
|保护历史记录|获取威胁详细信息|`mdatp threat get --id [threat-id]`|
|隔离管理|列出所有隔离的文件|`mdatp threat quarantine list`|
|隔离管理|从隔离区中删除所有文件|`mdatp threat quarantine remove-all`|
|隔离管理|将检测为威胁的文件添加到隔离区|`mdatp threat quarantine add --id [threat-id]`|
|隔离管理|从隔离区中删除检测为威胁的文件|`mdatp threat quarantine remove --id [threat-id]`|
|隔离管理|从隔离区还原文件|`mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`|
|终结点检测和响应|设置未使用的 (预览) |`mdatp edr early-preview [enable|disable]`|
|终结点检测和响应|设置 group-id|`mdatp edr group-ids --group-id [group-id]`|
|终结点检测和响应|设置/删除标记，仅 `GROUP` 受支持|`mdatp edr tag set --name GROUP --value [tag]`|
|终结点检测和响应|列出根 (排除) |`mdatp edr exclusion list [processes|paths|extensions|all]`|
|
