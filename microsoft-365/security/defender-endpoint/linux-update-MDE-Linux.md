---
title: '如何计划 Microsoft Defender 终结点更新 (Linux) '
description: 了解如何计划 Microsoft Defender 终结点 (Linux) 以更好地保护组织的资产。
keywords: 'microsoft， defender， Microsoft Defender for Endpoint， linux， 扫描， 防病毒， 适用于终结点的 microsoft defender (linux) '
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730866"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="24158-104">计划更新 Microsoft Defender for Endpoint （Linux）</span><span class="sxs-lookup"><span data-stu-id="24158-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="24158-105">若要在 Linux 上的 Microsoft Defender for Endpoint 上运行更新，请参阅在 Linux 上部署 [Microsoft Defender for Endpoint 的更新](/microsoft-365/security/defender-endpoint/linux-updates)。</span><span class="sxs-lookup"><span data-stu-id="24158-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="24158-106">Linux (和 Unix) 具有一个称为 **crontab** (类似于任务计划程序) 运行计划任务的工具。</span><span class="sxs-lookup"><span data-stu-id="24158-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="24158-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="24158-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="24158-108">若要获取所有时区的列表，请运行以下命令： `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="24158-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="24158-109">时区示例：</span><span class="sxs-lookup"><span data-stu-id="24158-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="24158-110">设置 Cron 作业</span><span class="sxs-lookup"><span data-stu-id="24158-110">To set the Cron job</span></span>
<span data-ttu-id="24158-111">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="24158-111">Use the following commands:</span></span>

<span data-ttu-id="24158-112">**备份 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="24158-113">其中 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="24158-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="24158-114">在编辑或删除之前，请执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="24158-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="24158-115">若要编辑 crontab，并添加一个新作业作为根用户：</span><span class="sxs-lookup"><span data-stu-id="24158-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="24158-116">默认编辑器为 VIM。</span><span class="sxs-lookup"><span data-stu-id="24158-116">The default editor is VIM.</span></span>

<span data-ttu-id="24158-117">你可能会看到：</span><span class="sxs-lookup"><span data-stu-id="24158-117">You might see:</span></span>

<span data-ttu-id="24158-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="24158-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="24158-119">And</span><span class="sxs-lookup"><span data-stu-id="24158-119">And</span></span>

<span data-ttu-id="24158-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="24158-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="24158-121">请参阅 [使用 Microsoft Defender for Endpoint (Linux) ](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="24158-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="24158-122">按"插入"</span><span class="sxs-lookup"><span data-stu-id="24158-122">Press “Insert”</span></span>

<span data-ttu-id="24158-123">添加以下条目：</span><span class="sxs-lookup"><span data-stu-id="24158-123">Add the following entries:</span></span>

<span data-ttu-id="24158-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="24158-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="24158-125">!CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="24158-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="24158-126">!SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="24158-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="24158-127">!Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="24158-127">!Ubuntu and Debian systems</span></span>

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="24158-128">在以上示例中，我们将它设置为 00 分钟、上午 6 点 (小时（24 小时制) 、每月的任何一天、星期日）。[$ (date + \% d) -le 15] == 不运行，除非它等于或小于第 3 周的第 15 (天) 。</span><span class="sxs-lookup"><span data-stu-id="24158-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="24158-129">这意味着它将在每月的第 3 个星期 (7) 上午 6：00 运行一次。</span><span class="sxs-lookup"><span data-stu-id="24158-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="24158-130">太平洋 (UTC -8) 。</span><span class="sxs-lookup"><span data-stu-id="24158-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="24158-131">按"Esc"</span><span class="sxs-lookup"><span data-stu-id="24158-131">Press “Esc”</span></span>

<span data-ttu-id="24158-132">在双引号中键入"：wq"。</span><span class="sxs-lookup"><span data-stu-id="24158-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="24158-133">w == 写入，q == quit</span><span class="sxs-lookup"><span data-stu-id="24158-133">w == write, q == quit</span></span>

<span data-ttu-id="24158-134">若要查看 cron 作业，请键入 `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="24158-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="更新 MDE linux":::

<span data-ttu-id="24158-136">检查 cron 作业运行： `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="24158-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="24158-137">检查 mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="24158-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="24158-138">对于使用"Ansible"、"用户"或"时形"的</span><span class="sxs-lookup"><span data-stu-id="24158-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="24158-139">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="24158-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="24158-140">在 Ansible 中设置 cron 作业</span><span class="sxs-lookup"><span data-stu-id="24158-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="24158-141">有关详细信息，请参阅 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)。</span><span class="sxs-lookup"><span data-stu-id="24158-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="24158-142">在管理中设置裁剪</span><span class="sxs-lookup"><span data-stu-id="24158-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="24158-143">有关详细信息，请参阅 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)。</span><span class="sxs-lookup"><span data-stu-id="24158-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="24158-144">在"创建"中设置 cron 作业</span><span class="sxs-lookup"><span data-stu-id="24158-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="24158-145">资源类型：cron</span><span class="sxs-lookup"><span data-stu-id="24158-145">Resource Type: cron</span></span>

<span data-ttu-id="24158-146">有关详细信息，请参阅 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)。</span><span class="sxs-lookup"><span data-stu-id="24158-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="24158-147">使用改进实现自动化：Cron 作业和计划任务</span><span class="sxs-lookup"><span data-stu-id="24158-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="24158-148">有关详细信息，请参阅 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。</span><span class="sxs-lookup"><span data-stu-id="24158-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="24158-149">其他信息</span><span class="sxs-lookup"><span data-stu-id="24158-149">Additional information</span></span>

<span data-ttu-id="24158-150">**获取有关 crontab 的帮助**</span><span class="sxs-lookup"><span data-stu-id="24158-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="24158-151">**获取当前用户的 crontab 文件列表**</span><span class="sxs-lookup"><span data-stu-id="24158-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="24158-152">**获取其他用户的 crontab 文件列表**</span><span class="sxs-lookup"><span data-stu-id="24158-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="24158-153">**备份 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="24158-154">在编辑或删除之前，请执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="24158-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="24158-155">**还原 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="24158-156">**编辑 crontab 并作为根用户添加新作业**</span><span class="sxs-lookup"><span data-stu-id="24158-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="24158-157">**编辑 crontab 并添加新作业**</span><span class="sxs-lookup"><span data-stu-id="24158-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="24158-158">**编辑其他用户的 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="24158-159">**删除所有 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="24158-160">**删除其他用户的 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="24158-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="24158-161">**说明**</span><span class="sxs-lookup"><span data-stu-id="24158-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

