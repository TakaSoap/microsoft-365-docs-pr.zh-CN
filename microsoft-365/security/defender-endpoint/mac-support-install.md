---
title: 解决 Mac 上 Microsoft Defender for Endpoint 的安装问题
description: 解决 Mac 上的 Microsoft Defender for Endpoint 中的安装问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装
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
ms.openlocfilehash: 8371129ff1b64681aee018802205a5f5a359fd86
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209473"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>解决 macOS 上 Microsoft Defender for Endpoint 的安装问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="installation-failed"></a>安装失败

对于手动安装，安装向导的"摘要"页显示"安装过程中出错。 安装程序遇到导致安装失败的错误。 请与软件制造商联系寻求帮助。" 对于 MDM 部署，它显示为常规安装失败。

尽管我们不会向最终用户显示确切的错误，但我们在 中日志文件安装进度。 `/Library/Logs/Microsoft/mdatp/install.log` 每个安装会话都附加到此日志文件。 只能用于 `sed` 输出上次安装会话：

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

本示例中，实际原因的前缀为 `[ERROR]` 。
安装失败，因为不支持这些版本之间的降级。

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP 安装日志缺失或未更新

在极少数情况下，安装不会在 MDATP 的 /Library/Logs/Microsoft/mdatp/install.日志文件。
当没有客户端 UI 部署时，可以通过查询 macOS 日志来验证安装是否 (分析可能的错误，这些日志在 MDM 部署中) 。 建议您使用一个较窄的时间窗口来运行查询，并按日志记录进程名称进行筛选，因为将会存在大量信息。

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
