---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警报问题
description: 解决 Linux 上的 Microsoft Defender for Endpoint 中缺少的事件或警报问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 事件
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
ms.openlocfilehash: d27a3cfb2d3c068a1d2b26ffba6b0061b143503f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60699289"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>解决 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警报问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)

本文提供了一些常规步骤，以减少事件门户中缺少Microsoft 365 Defender[警报](https://security.microsoft.com/)。

在 **设备上** 正确安装 Microsoft Defender for Endpoint 后 _，将在门户_ 中生成设备页面。 可以在设备页面的时间线选项卡或高级搜寻页面中查看所有记录的事件。 本节解决缺失某些或所有预期事件的情况。
例如，如果缺少 _所有 CreatedFile_ 事件。

## <a name="missing-network-and-login-events"></a>缺少网络和登录事件

Microsoft Defender for Endpoint 利用 `audit` linux 中的框架跟踪网络和登录活动。

1. 确保审核框架正常工作。

    ```bash
    service auditd status
    ```

    预期输出：

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. 如果 `auditd` 标记为已停止，请启动它。

    ```bash
    service auditd start
    ```

**在 SLES** 系统上，SYSCALL 审核默认情况下可能处于禁用状态，并可以说明 `auditd` 缺少事件。

1. 若要验证 SYSCALL 审核是否未禁用，请列出当前的审核规则：

    ```bash
    sudo auditctl -l
    ```

    如果存在以下行，请将其删除或编辑它以允许 Microsoft Defender for Endpoint 跟踪特定的 SYSCALLs。

    ```output
    -a task, never
    ```

    审核规则位于 `/etc/audit/rules.d/audit.rules` 。

## <a name="missing-file-events"></a>缺少文件事件

文件事件通过框架 `fanotify` 收集。 如果缺少某些或所有文件事件，请确保在设备上启用并且 `fanotify` 文件系统受 [支持](microsoft-defender-endpoint-linux.md#system-requirements)。

列出计算机上具有以下项的文件系统：

```bash
df -Th
```
