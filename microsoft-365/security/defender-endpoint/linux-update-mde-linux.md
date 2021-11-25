---
title: '如何计划 Microsoft Defender 的 Endpoint (Linux) '
description: 了解如何计划 Microsoft Defender 终结点 (Linux) 以更好地保护组织的资产。
keywords: 'microsoft， defender， Microsoft Defender for Endpoint， linux， 扫描， 防病毒， 适用于终结点的 microsoft defender (linux) '
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
ms.openlocfilehash: 7158f5b9a12fe3e2f1e91726d3e64477706d6545
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61169155"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>计划更新 Microsoft Defender for Endpoint （Linux）

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

若要在 Linux 上的 Microsoft Defender for Endpoint 上运行更新，请参阅在 Linux 上部署 [Microsoft Defender for Endpoint 的更新](/microsoft-365/security/defender-endpoint/linux-updates)。

Linux (和 Unix) 具有一个称为 **"crontab" (** 类似于任务计划程序) 运行计划任务的工具。

## <a name="pre-requisite"></a>先决条件

> [!NOTE]
> 若要获取所有时区的列表，请运行以下命令： `timedatectl list-timezones`
>
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
sudo crontab -l > /var/tmp/cron_backup_201118.dat
```

> [!NOTE]
> 其中 201118 == YYMMDD

> [!TIP]
> 在编辑或删除之前，请执行这一操作。

若要编辑 crontab，并添加一个新作业作为根用户：

```bash
sudo crontab -e
```

> [!NOTE]
> 默认编辑器为 VIM。

你可能会看到：

```output
0****/etc/opt/microsoft/mdatp/logrorate.sh
```

And

```output
02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log
```

请参阅 [使用 Microsoft Defender for Endpoint (Linux) ](linux-schedule-scan-atp.md)

按"插入"

添加以下条目：

```bash
CRON_TZ=America/Los_Angeles
```

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>!CentOS 和 Oracle Linux (RHEL 和) 
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo yum update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="sles-and-variants"></a>!SLES 和变量
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo zypper update mdatp >> ~/mdatp_cron_job.log
> ```

> #<a name="ubuntu-and-debian-systems"></a>!Ubuntu 和 Debian 系统
>
> ```bash
> 0 6 * * sun [ $(date +%d) -le 15 ] && sudo apt-get install --only-upgrade mdatp >> ~/mdatp_cron_job.log
> ```

> [!NOTE]
> 在以上示例中，我们将该时间设置为 00 分钟、上午 6 点 (小时（格式为 24 小时) 、每月的任何一天、任意一个月，在星期日）。[$ (date + \% d) -le 15] == 不运行，除非它等于或小于第 3 周的第 15 (天) 。 这意味着它将在每月的第 3 个星期 (7) 上午 6：00 运行一次。 太平洋 (UTC -8) 。

按"Esc"

在双 `:wq` 引号中键入" "。

> [!NOTE]
> w == 写入，q == quit

若要查看 cron 作业，请键入 `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="在 Linux 上更新适用于终结点的 Defender。":::

检查 cron 作业运行：

```bash
sudo grep mdatp /var/log/cron
```

检查 mdatp_cron_job.log

```bash
sudo nano mdatp_cron_job.log
```

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>对于使用"Ansible"、"用户"或"时形"的

使用以下命令：

### <a name="to-set-cron-jobs-in-ansible"></a>在 Ansible 中设置 cron 作业

```bash
cron - Manage cron.d and crontab entries
```

有关详细信息，请参阅 <https://docs.ansible.com/ansible/latest/modules/cron_module.html>。

### <a name="to-set-crontabs-in-chef"></a>在管理中设置裁剪

```bash
cron resource
```

有关详细信息，请参阅 <https://docs.chef.io/resources/cron/>。

### <a name="to-set-cron-jobs-in-puppet"></a>在"创建"中设置 cron 作业

资源类型：cron

有关详细信息，请参阅 <https://puppet.com/docs/puppet/5.5/types/cron.html>。

使用改进实现自动化：Cron 作业和计划任务

有关详细信息，请参阅 <https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/>。

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

<pre>
+—————- minute (values: 0 - 59) (special characters: , - * /)  <br>
| +————- hour (values: 0 - 23) (special characters: , - * /) <br>
| | +———- day of month (values: 1 - 31) (special characters: , - * / L W C)  <br>
| | | +——- month (values: 1 - 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 - 6) (Sunday=0 or 7) (special characters: , - * / L W C) <br>
| | | | |*****command to be executed
</pre>
