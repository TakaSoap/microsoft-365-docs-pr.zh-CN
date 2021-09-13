---
title: Mac 上的 Microsoft Defender for Endpoint 的资源
description: 适用于 Mac 版 Microsoft Defender for Endpoint 的资源，包括如何卸载它、如何收集诊断日志、CLI 命令以及产品的已知问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: 7d09ce01bc8d9409d4537df8eaabb50915538aa6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196023"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上的 Microsoft Defender for Endpoint 的资源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="collecting-diagnostic-information"></a>收集诊断信息

如果可以重现问题，请提高日志记录级别，运行系统一段时间，将日志记录级别还原为默认值。

1. 提高日志记录级别：

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. 重现问题

3. 运行 `sudo mdatp diagnostic create` 以备份适用于终结点的 Microsoft Defender 日志。 这些文件将存储在存档.zip中。 此命令还会在操作成功后输出备份的文件路径。

   > [!TIP]
   > 默认情况下，诊断日志将保存到 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。 若要更改保存诊断日志的目录，请传递给以下命令， `--path [directory]` `[directory]` 将 替换为所需的目录。

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. 还原日志记录级别：

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>记录安装问题

如果在安装过程中发生错误，安装程序将只报告常规故障。

详细日志将保存到 `/Library/Logs/Microsoft/mdatp/install.log` 。 如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。

## <a name="uninstalling"></a>卸载

有几种方法可以卸载 macOS 上的 Microsoft Defender for Endpoint。 请注意，尽管集中管理的卸载在 JAMF 上可用，但它尚不可用于Microsoft Intune。

### <a name="interactive-uninstallation"></a>交互式卸载

- 打开 **Finder > Applications**。 右键单击 **Microsoft Defender for Endpoint >移动到回收站**。

### <a name="from-the-command-line"></a>从命令行

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>从命令行配置

可以通过命令行完成重要任务，如控制产品设置和触发按需扫描：

|组|方案|命令|
|---|---|---|
|配置|打开/关闭实时保护|`mdatp config real-time-protection --value [enabled/disabled]`|
|配置|打开/关闭云保护|`mdatp config cloud --value [enabled/disabled]`|
|配置|打开/关闭产品诊断|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|配置|打开/关闭自动提交示例|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|配置|向允许列表添加威胁名称|`mdatp threat allowed add --name [threat-name]`|
|配置|从允许列表中删除威胁名称|`mdatp threat allowed remove --name [threat-name]`|
|配置|列出所有允许的威胁名称|`mdatp threat allowed list`|
|配置|打开 PUA 保护|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|配置|关闭 PUA 保护|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|配置|打开 PUA 保护的审核模式|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|配置|打开/关闭 passiveMode|`mdatp config passive-mode --value enabled [enabled/disabled]`|
|诊断|更改日志级别|`mdatp log level set --level [error/warning/info/verbose]`|
|诊断|生成诊断日志|`mdatp diagnostic create --path [directory]`|
|健康|检查产品的运行状况|`mdatp health`|
|健康|检查spefic产品属性|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|Protection|扫描路径|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|Protection|执行快速扫描|`mdatp scan quick`|
|Protection|执行完全扫描|`mdatp scan full`|
|Protection|取消正在进行的按需扫描|`mdatp scan cancel`|
|Protection|请求安全智能更新|`mdatp definitions update`|
|EDR|将组标记添加到设备。 EDR标记用于管理设备组。 有关详细信息，请访问 /microsoft-365/security/defender-endpoint/machine-groups|`mdatp edr tag set --name GROUP --value [name]`|
|EDR|从设备中删除组标记|`mdatp edr tag remove --tag-name [name]`|
|EDR|添加组 ID|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>如何启用自动完成

若要在 Bash 中启用自动完成，请运行以下命令并重新启动终端会话：

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

在 zsh 中启用自动完成：

- 检查是否已在设备上启用自动完成：

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- 如果上述命令未生成任何输出，可以使用以下命令启用自动完成：

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- 运行以下命令以在 macOS 上为 Microsoft Defender for Endpoint 启用自动完成，并重新启动终端会话：

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>客户端 Microsoft Defender for Endpoint 隔离目录

`/Library/Application Support/Microsoft/Defender/quarantine/` 包含由 隔离的文件 `mdatp` 。 这些文件以威胁跟踪 Id 命名。 当前 trackingIds 显示为 `mdatp threat list` 。

## <a name="microsoft-defender-for-endpoint-portal-information"></a>适用于终结点的 Microsoft Defender 门户信息

[EDR macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)的新功能现已到达，位于 Microsoft Defender for Endpoint 博客上，提供有关 Microsoft Defender for Endpoint 安全中心中预期内容的详细指南。
