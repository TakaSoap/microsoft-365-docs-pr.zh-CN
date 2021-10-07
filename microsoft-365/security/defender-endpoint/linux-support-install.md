---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题
ms.reviewer: ''
description: 解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装
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
ms.openlocfilehash: c90841ac9312fcc5f36ae9807ce757d9268b4cea
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173087"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>解决 Linux 上的 Microsoft Defender for Endpoint 的安装问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

## <a name="verify-if-installation-succeeded"></a>验证安装是否成功

安装错误可能导致包管理器产生有意义的错误消息，也可能没有意义。 若要验证安装是否成功，请运行以下方法获取并检查安装日志：

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

来自具有正确安装日期和时间的上一个命令的输出指示成功。

此外， [检查客户端配置](linux-install-manually.md#client-configuration) 以验证产品的运行状况并检测 EICAR 文本文件。

## <a name="make-sure-you-have-the-correct-package"></a>确保你拥有正确的程序包

请注意，要安装的程序包与主机分发和版本匹配。

<br>

****

|package|distribution|
|---|---|
|mdatp-rhel8。Linux.x86_64.rpm|Oracle、RHEL 和 CentOS 8.x|
|mdatp-sles12。Linux.x86_64.rpm|SuSE Linux Enterprise Server 12.x|
|mdatp-sles15。Linux.x86_64.rpm|SuSE Linux Enterprise Server 15.x|
|mdatp.Linux.x86_64.rpm|Oracle、RHEL 和 CentOS 7.x|
|mdatp.Linux.x86_64.deb|Debian 和 Ubuntu 16.04、18.04 和 20.04|
|

对于 [手动部署](linux-install-manually.md)，请确保已选择正确的发布和版本。

## <a name="installation-failed"></a>安装失败

检查 mdatp 服务是否正在运行：

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>mdatp 服务未运行时疑难解答的步骤

1. 检查是否存在"mdatp"用户：

    ```bash
    id "mdatp"
    ```

    如果没有输出，请运行

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. 尝试使用以下方法启用和重新启动服务：

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. 如果在运行上一个命令时找不到 mdatp.service，请运行：

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    其中 `<systemd_path>` 用于 `/lib/systemd/system` Ubuntu 和 Debian 分发， `/usr/lib/systemd/system` 适用于 Rhel、CentOS、Oracle 和 SLES。
   然后重新运行步骤 2。

4. 如果上述步骤不起作用，请检查是否安装了 SE 提供了实施模式。 如果是这样，请尝试将它设置为允许 (模式) 禁用模式。 可以通过在文件中将 参数设置为"许可"或"禁用"，然后 `SELINUX` `/etc/selinux/config` 重新启动来完成。 有关更多详细信息，请查看 se分页的"人名"页面。
现在，请尝试使用步骤 2 重新启动 mdatp 服务。 在尝试配置更改并重新启动后，出于安全考虑，立即还原配置更改。

5. 如果 `/opt` 目录是符号链接，请为 创建绑定装载 `/opt/microsoft` 。

6. 确保守护程序具有可执行权限。

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    如果守护程序没有可执行权限，请执行以下操作：

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    并重试运行步骤 2。

7. 确保包含 wdavdaemon 的文件系统未装入"noexec"。

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>如果 mdatp 服务正在运行，但 EICAR 文本文件检测不起作用

1. 使用以下方法检查文件系统类型：

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    当前支持的访问活动的文件系统在此处 [列出](microsoft-defender-endpoint-linux.md#system-requirements)。 将不会扫描这些文件系统之外的任何文件。

## <a name="command-line-tool-mdatp-isnt-working"></a>命令行工具"mdatp"无法工作

1. 如果运行命令行工具出错 `mdatp` ， `command not found` 请运行以下命令：

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    然后重试。

    如果上述步骤均无帮助，请收集诊断日志：

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    包含日志的 zip 文件的路径将显示为输出。 使用这些日志联系我们的客户支持人员。
