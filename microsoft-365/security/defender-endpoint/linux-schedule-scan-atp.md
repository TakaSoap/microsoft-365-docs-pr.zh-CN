---
title: '如何使用 Microsoft Defender for Endpoint (Linux) '
description: 了解如何为 Microsoft Defender for Endpoint (Linux) 安排自动扫描时间，以更好地保护组织的资产。
keywords: 'microsoft， defender， atp， linux， 扫描， 防病毒， microsoft defender for endpoint (linux) '
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
ms.openlocfilehash: d3f5d4c490e28c7985a0420fa5013a8e0f51a167
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055823"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="89da7-104">使用 Microsoft Defender for Endpoint (Linux) </span><span class="sxs-lookup"><span data-stu-id="89da7-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="89da7-105">若要运行 Linux 扫描，请参阅支持 [的命令](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。</span><span class="sxs-lookup"><span data-stu-id="89da7-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="89da7-106">Linux (和 Unix) 具有一个称为 **crontab** (类似于任务计划程序) 运行计划任务的工具。</span><span class="sxs-lookup"><span data-stu-id="89da7-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="89da7-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="89da7-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="89da7-108">若要获取所有时区的列表，请运行以下命令： `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="89da7-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="89da7-109">时区示例：</span><span class="sxs-lookup"><span data-stu-id="89da7-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="89da7-110">设置 Cron 作业</span><span class="sxs-lookup"><span data-stu-id="89da7-110">To set the Cron job</span></span>
<span data-ttu-id="89da7-111">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="89da7-111">Use the following commands:</span></span>

<span data-ttu-id="89da7-112">**备份 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="89da7-113">其中 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="89da7-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="89da7-114">在编辑或删除之前，请执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="89da7-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="89da7-115">若要编辑 crontab，并添加一个新作业作为根用户：</span><span class="sxs-lookup"><span data-stu-id="89da7-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="89da7-116">默认编辑器为 VIM。</span><span class="sxs-lookup"><span data-stu-id="89da7-116">The default editor is VIM.</span></span>

<span data-ttu-id="89da7-117">你可能会看到：</span><span class="sxs-lookup"><span data-stu-id="89da7-117">You might see:</span></span>

<span data-ttu-id="89da7-118">0 \* \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="89da7-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="89da7-119">按"插入"</span><span class="sxs-lookup"><span data-stu-id="89da7-119">Press “Insert”</span></span>

<span data-ttu-id="89da7-120">添加以下条目：</span><span class="sxs-lookup"><span data-stu-id="89da7-120">Add the following entries:</span></span>

<span data-ttu-id="89da7-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="89da7-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="89da7-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="89da7-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="89da7-123">本示例中，我们设置为 00 分钟，即 2 a.m。</span><span class="sxs-lookup"><span data-stu-id="89da7-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="89da7-124"> (24 小时制的 24 小时制) 、月中的任意一天、任何一个月的星期六。</span><span class="sxs-lookup"><span data-stu-id="89da7-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="89da7-125">这意味着它将于星期六的上午 2：00 运行。</span><span class="sxs-lookup"><span data-stu-id="89da7-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="89da7-126">太平洋 (UTC –8) 。</span><span class="sxs-lookup"><span data-stu-id="89da7-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="89da7-127">按"Esc"</span><span class="sxs-lookup"><span data-stu-id="89da7-127">Press “Esc”</span></span>

<span data-ttu-id="89da7-128">键入不带双引号的"：wq"。</span><span class="sxs-lookup"><span data-stu-id="89da7-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="89da7-129">w == 写入，q == quit</span><span class="sxs-lookup"><span data-stu-id="89da7-129">w == write, q == quit</span></span>

<span data-ttu-id="89da7-130">若要查看 cron 作业，请键入 `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="89da7-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="89da7-132">**检查 cron 作业运行**</span><span class="sxs-lookup"><span data-stu-id="89da7-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="89da7-133">**检查 mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="89da7-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="89da7-134">对于使用"Ansible"、"用户"或"时形"的</span><span class="sxs-lookup"><span data-stu-id="89da7-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="89da7-135">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="89da7-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="89da7-136">在 Ansible 中设置 cron 作业</span><span class="sxs-lookup"><span data-stu-id="89da7-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="89da7-137">有关详细信息，请参阅 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)。</span><span class="sxs-lookup"><span data-stu-id="89da7-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="89da7-138">在管理中设置裁剪</span><span class="sxs-lookup"><span data-stu-id="89da7-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="89da7-139">有关详细信息，请参阅 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)。</span><span class="sxs-lookup"><span data-stu-id="89da7-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="89da7-140">在"创建"中设置 cron 作业</span><span class="sxs-lookup"><span data-stu-id="89da7-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="89da7-141">资源类型：cron</span><span class="sxs-lookup"><span data-stu-id="89da7-141">Resource Type: cron</span></span>

<span data-ttu-id="89da7-142">有关详细信息，请参阅 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)。</span><span class="sxs-lookup"><span data-stu-id="89da7-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="89da7-143">使用改进实现自动化：Cron 作业和计划任务</span><span class="sxs-lookup"><span data-stu-id="89da7-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="89da7-144">有关详细信息，请参阅 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。</span><span class="sxs-lookup"><span data-stu-id="89da7-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="89da7-145">其他信息</span><span class="sxs-lookup"><span data-stu-id="89da7-145">Additional information</span></span>

<span data-ttu-id="89da7-146">**获取有关 crontab 的帮助**</span><span class="sxs-lookup"><span data-stu-id="89da7-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="89da7-147">**获取当前用户的 crontab 文件列表**</span><span class="sxs-lookup"><span data-stu-id="89da7-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="89da7-148">**获取其他用户的 crontab 文件列表**</span><span class="sxs-lookup"><span data-stu-id="89da7-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="89da7-149">**备份 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="89da7-150">在编辑或删除之前，请执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="89da7-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="89da7-151">**还原 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="89da7-152">**编辑 crontab 并作为根用户添加新作业**</span><span class="sxs-lookup"><span data-stu-id="89da7-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="89da7-153">**编辑 crontab 并添加新作业**</span><span class="sxs-lookup"><span data-stu-id="89da7-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="89da7-154">**编辑其他用户的 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="89da7-155">**删除所有 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="89da7-156">**删除其他用户的 crontab 条目**</span><span class="sxs-lookup"><span data-stu-id="89da7-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="89da7-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="89da7-157">**Explanation**</span></span>

<span data-ttu-id="89da7-158">+—————-分钟 (值：0 – 59)  (特殊字符： 、 – \* /) </span><span class="sxs-lookup"><span data-stu-id="89da7-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="89da7-159">|+————-小时 (值：0 – 23)  (特殊字符： 、 – \* /) </span><span class="sxs-lookup"><span data-stu-id="89da7-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="89da7-160">| |+———-月中的 (值：1 – 31)  (特殊字符： 、 – \* / L W C) </span><span class="sxs-lookup"><span data-stu-id="89da7-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="89da7-161">| | |+——-月 (值：1 – 12)  (特殊字符：，- \* / ) </span><span class="sxs-lookup"><span data-stu-id="89da7-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="89da7-162">| | | |+-- 一周中的 (值：0 – 6)  (Sunday=0 或 7)  (特殊字符： 、 – \* / L W C) </span><span class="sxs-lookup"><span data-stu-id="89da7-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="89da7-163">| | | | |\*\*\*\*\*要执行的命令</span><span class="sxs-lookup"><span data-stu-id="89da7-163">| | | | |\*\*\*\*\*command to be executed</span></span>


