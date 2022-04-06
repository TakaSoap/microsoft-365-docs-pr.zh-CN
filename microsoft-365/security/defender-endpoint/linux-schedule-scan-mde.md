---
title: 如何使用 Microsoft Defender for Endpoint (Linux) 计划扫描
description: 了解如何为 Microsoft Defender for Endpoint (Linux) 计划自动扫描时间，以便更好地保护组织的资产。
keywords: 'microsoft， defender， Microsoft Defender for Endpoint， linux， scans， 防病毒， microsoft defender for endpoint (linux) '
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
ms.openlocfilehash: 706284ed0adf49c4da6357b6bb8217d5a14268e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663481"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>使用 Microsoft Defender for Endpoint (Linux) 计划扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


若要运行 Linux 扫描，请参阅 [支持的命令](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。

Linux (和 Unix) 具有类似于任务计划程序) 的名为 **crontab** (的工具，以便能够运行计划任务。

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
> 其中200919 == YRMMDD

> [!TIP]
> 在编辑或删除之前执行此操作。

若要编辑 crontab，并以根用户身份添加新作业：

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
> 在此示例中，我们将其设置为 00 分钟，凌晨 2 点。  (24 小时格式的小时) ，月中的任何一天，任何月份，星期六。 这意味着它将在星期六凌晨2：00运行。 太平洋 (UTC -8) 。

按"Esc"

键入"`:wq`"，不带双引号。

> [!NOTE]
> w == write， q == quit

若要查看 cron 作业，请键入 `sudo crontab -l`

:::image type="content" source="../../media/linux-mdatp-1.png" alt-text="Linux mdatp 页" lightbox="../../media/linux-mdatp-1.png":::

#### <a name="to-inspect-cron-job-runs"></a>检查 cron 作业运行

```bash
sudo grep mdatp /var/log/cron
```

#### <a name="to-inspect-the-mdatp_cron_joblog"></a>检查mdatp_cron_job.log*

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>对于使用 Ansible、Chef 或 Puppet 的用户

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

### <a name="to-set-cron-jobs-in-puppet"></a>在 Puppet 中设置 cron 作业

```bash
Resource Type: cron
```

有关详细信息，请参阅 <https://puppet.com/docs/puppet/5.5/types/cron.html>。

使用 Puppet 自动执行：Cron 作业和计划任务

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
> 在编辑或删除之前执行此操作。

### <a name="to-restore-crontab-entries"></a>还原 crontab 条目

```bash
crontab /var/tmp/cron_backup.dat
```

### <a name="to-edit-the-crontab-and-add-a-new-job-as-a-root-user"></a>编辑 crontab 并以根用户身份添加新作业

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

+—————-分钟 (值：0 - 59)  (特殊字符：，/ \- \* )   <br>
|+————-小时 (值：0 - 23)  (特殊字符：， \- \* /)  <br>
| |+月———-天 (值：1 - 31)  (特殊字符：/ \- \* L W C)   <br>
| | |+——-月 (值：1 - 12)  (特殊字符： / \- \* )   <br>
| | | |+- 一周中的一天 (值：0 - 6)  (星期日=0 或 7)  (特殊字符： / \- \* L W C)  <br>
要执行| | | | |****命令
