---
title: '如何使用 Microsoft Defender for Endpoint (Linux) '
description: 了解如何为 Microsoft Defender for Endpoint (Linux) 安排自动扫描时间，以更好地保护组织的资产。
keywords: 'microsoft， defender， Microsoft Defender for Endpoint， linux， 扫描， 防病毒， microsoft defender for endpoint (linux) '
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ddb02d67866e675febda59fac15e8e494188a47f
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302489"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>使用 Microsoft Defender for Endpoint (Linux) 

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


若要运行 Linux 扫描，请参阅支持 [的命令](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。

Linux (和 Unix) 具有一个称为 **crontab** (的工具，) 任务计划程序工具可用于运行计划任务。

## <a name="pre-requisite"></a>先决条件

> [!NOTE]
> 若要获取所有时区的列表，请运行以下命令： `timedatectl list-timezones`<br>
> 时区示例：
>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>设置 Cron 作业

使用以下命令：

### <a name="backup-crontab-entries"></a>备份 crontab 条目

```bash
sudo crontab -l > /var/tmp/cron_backup_200919.dat
```

> [!NOTE]
> 其中 200919 == YRMMDD

> [!TIP]
> 在编辑或删除之前，请执行这一操作。

若要编辑 crontab，并添加一个新作业作为根用户：

```bash
sudo crontab -e
```

> [!NOTE]
> 默认编辑器为 VIM。

你可能会看到：

```outbou
0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh
```

按"插入"

添加以下条目：

```bash
CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log
```

> [!NOTE]
> 本示例中，我们设置为 00 分钟，即 2 a.m。  (24 小时制的 24 小时制) 、月中的任意一天、任何一个月的星期六。 这意味着它将于星期六的上午 2：00 运行。 太平洋 (UTC -8) 。

按"Esc"

键入不带 `:wq` 双引号的" "。

> [!NOTE]
> w == 写入，q == quit

若要查看 cron 作业，请键入 `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="linux mdatp。":::

#### <a name="to-inspect-cron-job-runs"></a>检查 cron 作业运行

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>检查 mdatp_cron_job.log*

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>对于使用"Ansible"、"用户"或"时形"的

使用以下命令：

### <a name="to-set-cron-jobs-in-ansible"></a>在 Ansible 中设置 cron 作业

```bash
cron - Manage cron.d and crontab entries

See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.

### To set crontabs in Chef

```bash
cron resource
```bash

```
有关详细信息，请参阅 <https://docs.chef.io/resources/cron/>。

### <a name="to-set-cron-jobs-in-puppet"></a>在"创建"中设置 cron 作业

```bash
Resource Type: cron
```

有关详细信息，请参阅 <https://puppet.com/docs/puppet/5.5/types/cron.html>。

使用改进实现自动化：Cron 作业和计划任务

有关详细信息，请参阅 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。

## <a name="additional-information"></a>其他信息

### <a name="to-get-help-with-crontab"></a>获取有关 crontab 的帮助

```bash
man crontab
```

### <a name="to-get-a-list-of-crontab-file-of-the-current-user"></a>获取当前用户的 crontab 文件列表

```bash
crontab -l
```

### <a name="to-get-a-list-of-crontab-file-of-another-user"></a>获取其他用户的 crontab 文件列表

```bash
crontab -u username -l
```

### <a name="to-backup-crontab-entries"></a>备份 crontab 条目

```bash
crontab -l > /var/tmp/cron_backup.dat
```

> [!TIP]
> 在编辑或删除之前，请执行这一操作。

### <a name="to-restore-crontab-entries"></a>还原 crontab 条目

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>编辑 crontab 并作为根用户添加新作业

```bash
sudo crontab -e
```

### <a name="to-edit-the-crontab-and-add-a-new-job"></a>编辑 crontab 并添加新作业

```bash
crontab -e
```

### <a name="to-edit-other-users-crontab-entries"></a>编辑其他用户的 crontab 条目

```bash
crontab -u username -e
```

### <a name="to-remove-all-crontab-entries"></a>删除所有 crontab 条目

```bash
crontab -r
```

### <a name="to-remove-other-users-crontab-entries"></a>删除其他用户的 crontab 条目

```bash
crontab -u username -r
```

### <a name="explanation"></a>说明

+—————-分钟 (值：0 - 59)  (特殊字符： 、 - * /)   <br>
|+————-小时 (值：0 - 23)  (特殊字符： 、 - * /)  <br>
| |+———-月中的 (值：1 - 31)  (特殊字符： 、 - * / L W C)   <br>
| | |+——-月 (值：1 - 12)  (特殊字符：，- * / )   <br>
| | | |+-- 一周中的 (值：0 - 6)  (Sunday=0 或 7)  (特殊字符： 、 - * / L W C)  <br>
| | | | |*****要执行的命令
