---
title: Mac 上的 Microsoft Defender for Endpoint 的资源
description: 适用于 Mac 版 Microsoft Defender for Endpoint 的资源，包括如何卸载它、如何收集诊断日志、CLI 命令以及产品的已知问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
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
  - m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
---

# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上的 Microsoft Defender for Endpoint 的资源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="collecting-diagnostic-information"></a>收集诊断信息

如果可以重现问题，请提高日志记录级别，运行系统一段时间，将日志记录级别还原为默认值。

1. 提高日志记录级别：

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 重现问题

3. 运行 `sudo mdatp diagnostic create` 以备份适用于终结点的 Microsoft Defender 日志。 这些文件将存储在一个.zip中。 此命令还会在操作成功后输出备份的文件路径。

   > [!TIP]
   > 默认情况下，诊断日志将保存到 `/Library/Application Support/Microsoft/Defender/wdavdiag/`。 若要更改保存诊断日志的目录，请传递给 `--path [directory]` 以下命令，将 `[directory]` 替换为所需的目录。

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

详细日志将保存到 `/Library/Logs/Microsoft/mdatp/install.log`。 如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。

## <a name="uninstalling"></a>卸载

有几种方法可以卸载 macOS 上的 Microsoft Defender for Endpoint。 请注意，尽管集中管理的卸载在 JAMF 上可用，但它尚不可用于Microsoft Intune。

### <a name="interactive-uninstallation"></a>交互式卸载

- 打开 **Finder > 应用程序**。 右键单击 **Microsoft Defender for Endpoint >移动到回收站**。

### <a name="supported-output-types"></a>支持的输出类型

支持表和 JSON 格式输出类型。 对于每个命令，都有一个默认输出行为。 可以使用以下命令修改首选输出格式的输出：

`-output json`

`-output table`

### <a name="from-the-command-line"></a>从命令行

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>从命令行配置

可以通过命令行完成重要任务，如控制产品设置和触发按需扫描：

|Group|应用场景|命令|
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
|配置|打开/关闭防病毒被动模式|`mdatp config passive-mode --value [enabled/disabled]`|
|配置|配置按需扫描的并行度|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|配置|在安全智能更新后打开/关闭扫描|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|配置|仅按需扫描 (/关闭存档) |`mdatp config scan-archives --value [enabled/disabled]`|
|诊断|更改日志级别|`mdatp log level set --level [error/warning/info/verbose]`|
|诊断|生成诊断日志|`mdatp diagnostic create --path [directory]`|
|运行状况|检查产品的运行状况|`mdatp health`|
|运行状况|检查spefic产品属性|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|保护|扫描路径|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保护|执行快速扫描|`mdatp scan quick`|
|保护|执行完全扫描|`mdatp scan full`|
|保护|取消正在进行的按需扫描|`mdatp scan cancel`|
|保护|请求安全智能更新|`mdatp definitions update`|
|EDR|Set/Remove 标记，仅支持 GROUP|`mdatp edr tag set --name GROUP --value [name]`|
|EDR|从设备中删除组标记|`mdatp edr tag remove --tag-name [name]`|
|EDR|添加组 ID|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>如何启用自动完成

若要在 Bash 中启用自动完成，请运行以下命令并重新启动终端会话：

```bash
echo "source /Applications/Microsoft\ Defender.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
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

   sudo ln -svf "/Applications/Microsoft Defender.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>客户端 Microsoft Defender for Endpoint 隔离目录

`/Library/Application Support/Microsoft/Defender/quarantine/` 包含由 隔离的文件 `mdatp`。 这些文件以威胁跟踪 Id 命名。 当前 trackingIds 显示为 `mdatp threat list`。

## <a name="microsoft-defender-for-endpoint-portal-information"></a>适用于终结点的 Microsoft Defender 门户信息

[EDR macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801) 的新功能现已在 Microsoft Defender for Endpoint 博客上提供在适用于终结点安全中心的 Microsoft Defender 中预期内容的详细指导。
