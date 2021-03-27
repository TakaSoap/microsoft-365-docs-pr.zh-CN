---
title: 适用于 Linux 资源的 Microsoft Defender ATP
ms.reviewer: ''
description: 介绍适用于 Linux 的 Microsoft Defender ATP 的资源，包括如何卸载它、如何收集诊断日志、CLI 命令以及产品的已知问题。
keywords: microsoft， defender， atp， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
ms.openlocfilehash: ab5400a197a1f0ac61c8b298a06165d217f44fd1
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394730"
---
# <a name="resources"></a><span data-ttu-id="c605a-104">资源</span><span class="sxs-lookup"><span data-stu-id="c605a-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c605a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c605a-105">**Applies to:**</span></span>
- [<span data-ttu-id="c605a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c605a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c605a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c605a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c605a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="c605a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c605a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c605a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="c605a-110">收集诊断信息</span><span class="sxs-lookup"><span data-stu-id="c605a-110">Collect diagnostic information</span></span>

<span data-ttu-id="c605a-111">如果可以重现问题，请首先增加日志记录级别，运行系统一段时间，然后将日志记录级别还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="c605a-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="c605a-112">提高日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="c605a-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="c605a-113">重现问题。</span><span class="sxs-lookup"><span data-stu-id="c605a-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="c605a-114">运行以下命令以备份适用于终结点日志的 Defender。</span><span class="sxs-lookup"><span data-stu-id="c605a-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="c605a-115">这些文件将存储在 .zip 存档内部。</span><span class="sxs-lookup"><span data-stu-id="c605a-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="c605a-116">在操作成功后，此命令还会输出备份的文件路径：</span><span class="sxs-lookup"><span data-stu-id="c605a-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="c605a-117">还原日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="c605a-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="c605a-118">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="c605a-118">Log installation issues</span></span>

<span data-ttu-id="c605a-119">如果在安装过程中发生错误，安装程序将只报告常规故障。</span><span class="sxs-lookup"><span data-stu-id="c605a-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="c605a-120">详细日志将保存到 `/var/log/microsoft/mdatp_install.log` 。</span><span class="sxs-lookup"><span data-stu-id="c605a-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="c605a-121">如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。</span><span class="sxs-lookup"><span data-stu-id="c605a-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="c605a-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="c605a-122">Uninstall</span></span>

<span data-ttu-id="c605a-123">有几种方法可以卸载适用于 Linux 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c605a-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="c605a-124">如果你使用的是配置工具（如"开发工具"，请按照配置工具的程序包卸载说明操作）。</span><span class="sxs-lookup"><span data-stu-id="c605a-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="c605a-125">手动卸载</span><span class="sxs-lookup"><span data-stu-id="c605a-125">Manual uninstallation</span></span>

- <span data-ttu-id="c605a-126">`sudo yum remove mdatp` For RHEL and variants (CentOS and Oracle Linux) .</span><span class="sxs-lookup"><span data-stu-id="c605a-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="c605a-127">`sudo zypper remove mdatp` 用于 SLES 和变量。</span><span class="sxs-lookup"><span data-stu-id="c605a-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="c605a-128">`sudo apt-get purge mdatp` 用于 Ubuntu 和 Debian 系统。</span><span class="sxs-lookup"><span data-stu-id="c605a-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="c605a-129">从命令行配置</span><span class="sxs-lookup"><span data-stu-id="c605a-129">Configure from the command line</span></span>

<span data-ttu-id="c605a-130">可以通过命令行完成重要任务，如控制产品设置和触发按需扫描。</span><span class="sxs-lookup"><span data-stu-id="c605a-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="c605a-131">全局选项</span><span class="sxs-lookup"><span data-stu-id="c605a-131">Global options</span></span>

<span data-ttu-id="c605a-132">默认情况下，命令行工具以可读格式输出结果。</span><span class="sxs-lookup"><span data-stu-id="c605a-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="c605a-133">此外，该工具还支持将结果输出为 JSON，这适用于自动化方案。</span><span class="sxs-lookup"><span data-stu-id="c605a-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="c605a-134">若要将输出更改为 JSON，请 `--output json` 传递给以下任一命令。</span><span class="sxs-lookup"><span data-stu-id="c605a-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="c605a-135">支持的命令</span><span class="sxs-lookup"><span data-stu-id="c605a-135">Supported commands</span></span>

<span data-ttu-id="c605a-136">下表列出了一些最常见方案的命令。</span><span class="sxs-lookup"><span data-stu-id="c605a-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="c605a-137">从 `mdatp help` 终端运行以查看受支持命令的完整列表。</span><span class="sxs-lookup"><span data-stu-id="c605a-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="c605a-138">Group</span><span class="sxs-lookup"><span data-stu-id="c605a-138">Group</span></span>                 |<span data-ttu-id="c605a-139">方案</span><span class="sxs-lookup"><span data-stu-id="c605a-139">Scenario</span></span>                                                |<span data-ttu-id="c605a-140">命令</span><span class="sxs-lookup"><span data-stu-id="c605a-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="c605a-141">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-141">Configuration</span></span>         |<span data-ttu-id="c605a-142">打开/关闭实时保护</span><span class="sxs-lookup"><span data-stu-id="c605a-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="c605a-143">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-143">Configuration</span></span>         |<span data-ttu-id="c605a-144">打开/关闭行为监视</span><span class="sxs-lookup"><span data-stu-id="c605a-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="c605a-145">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-145">Configuration</span></span>         |<span data-ttu-id="c605a-146">打开/关闭云保护</span><span class="sxs-lookup"><span data-stu-id="c605a-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="c605a-147">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-147">Configuration</span></span>         |<span data-ttu-id="c605a-148">打开/关闭产品诊断</span><span class="sxs-lookup"><span data-stu-id="c605a-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="c605a-149">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-149">Configuration</span></span>         |<span data-ttu-id="c605a-150">打开/关闭自动提交示例</span><span class="sxs-lookup"><span data-stu-id="c605a-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="c605a-151">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-151">Configuration</span></span>         |<span data-ttu-id="c605a-152">打开/关闭 AV 被动模式</span><span class="sxs-lookup"><span data-stu-id="c605a-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="c605a-153">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-153">Configuration</span></span>         |<span data-ttu-id="c605a-154">添加/删除文件扩展名的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="c605a-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="c605a-155">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-155">Configuration</span></span>         |<span data-ttu-id="c605a-156">添加/删除文件的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="c605a-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="c605a-157">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-157">Configuration</span></span>         |<span data-ttu-id="c605a-158">添加/删除目录的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="c605a-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="c605a-159">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-159">Configuration</span></span>         |<span data-ttu-id="c605a-160">添加/删除某个进程的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="c605a-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="c605a-161">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-161">Configuration</span></span>         |<span data-ttu-id="c605a-162">列出所有防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="c605a-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="c605a-163">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-163">Configuration</span></span>         |<span data-ttu-id="c605a-164">向允许列表添加威胁名称</span><span class="sxs-lookup"><span data-stu-id="c605a-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="c605a-165">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-165">Configuration</span></span>         |<span data-ttu-id="c605a-166">从允许列表中删除威胁名称</span><span class="sxs-lookup"><span data-stu-id="c605a-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="c605a-167">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-167">Configuration</span></span>         |<span data-ttu-id="c605a-168">列出所有允许的威胁名称</span><span class="sxs-lookup"><span data-stu-id="c605a-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="c605a-169">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-169">Configuration</span></span>         |<span data-ttu-id="c605a-170">打开 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="c605a-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="c605a-171">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-171">Configuration</span></span>         |<span data-ttu-id="c605a-172">关闭 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="c605a-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="c605a-173">配置</span><span class="sxs-lookup"><span data-stu-id="c605a-173">Configuration</span></span>         |<span data-ttu-id="c605a-174">打开 PUA 保护的审核模式</span><span class="sxs-lookup"><span data-stu-id="c605a-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="c605a-175">诊断</span><span class="sxs-lookup"><span data-stu-id="c605a-175">Diagnostics</span></span>           |<span data-ttu-id="c605a-176">更改日志级别</span><span class="sxs-lookup"><span data-stu-id="c605a-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="c605a-177">诊断</span><span class="sxs-lookup"><span data-stu-id="c605a-177">Diagnostics</span></span>           |<span data-ttu-id="c605a-178">生成诊断日志</span><span class="sxs-lookup"><span data-stu-id="c605a-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="c605a-179">健康</span><span class="sxs-lookup"><span data-stu-id="c605a-179">Health</span></span>                |<span data-ttu-id="c605a-180">检查产品的运行状况</span><span class="sxs-lookup"><span data-stu-id="c605a-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="c605a-181">Protection</span><span class="sxs-lookup"><span data-stu-id="c605a-181">Protection</span></span>            |<span data-ttu-id="c605a-182">扫描路径</span><span class="sxs-lookup"><span data-stu-id="c605a-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="c605a-183">Protection</span><span class="sxs-lookup"><span data-stu-id="c605a-183">Protection</span></span>            |<span data-ttu-id="c605a-184">执行快速扫描</span><span class="sxs-lookup"><span data-stu-id="c605a-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="c605a-185">Protection</span><span class="sxs-lookup"><span data-stu-id="c605a-185">Protection</span></span>            |<span data-ttu-id="c605a-186">执行完全扫描</span><span class="sxs-lookup"><span data-stu-id="c605a-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="c605a-187">Protection</span><span class="sxs-lookup"><span data-stu-id="c605a-187">Protection</span></span>            |<span data-ttu-id="c605a-188">取消正在进行的按需扫描</span><span class="sxs-lookup"><span data-stu-id="c605a-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="c605a-189">Protection</span><span class="sxs-lookup"><span data-stu-id="c605a-189">Protection</span></span>            |<span data-ttu-id="c605a-190">请求安全智能更新</span><span class="sxs-lookup"><span data-stu-id="c605a-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="c605a-191">保护历史记录</span><span class="sxs-lookup"><span data-stu-id="c605a-191">Protection history</span></span>    |<span data-ttu-id="c605a-192">打印完整保护历史记录</span><span class="sxs-lookup"><span data-stu-id="c605a-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="c605a-193">保护历史记录</span><span class="sxs-lookup"><span data-stu-id="c605a-193">Protection history</span></span>    |<span data-ttu-id="c605a-194">获取威胁详细信息</span><span class="sxs-lookup"><span data-stu-id="c605a-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="c605a-195">隔离管理</span><span class="sxs-lookup"><span data-stu-id="c605a-195">Quarantine management</span></span> |<span data-ttu-id="c605a-196">列出所有隔离的文件</span><span class="sxs-lookup"><span data-stu-id="c605a-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="c605a-197">隔离管理</span><span class="sxs-lookup"><span data-stu-id="c605a-197">Quarantine management</span></span> |<span data-ttu-id="c605a-198">从隔离区中删除所有文件</span><span class="sxs-lookup"><span data-stu-id="c605a-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="c605a-199">隔离管理</span><span class="sxs-lookup"><span data-stu-id="c605a-199">Quarantine management</span></span> |<span data-ttu-id="c605a-200">将检测为威胁的文件添加到隔离区</span><span class="sxs-lookup"><span data-stu-id="c605a-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="c605a-201">隔离管理</span><span class="sxs-lookup"><span data-stu-id="c605a-201">Quarantine management</span></span> |<span data-ttu-id="c605a-202">从隔离区中删除检测为威胁的文件</span><span class="sxs-lookup"><span data-stu-id="c605a-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="c605a-203">隔离管理</span><span class="sxs-lookup"><span data-stu-id="c605a-203">Quarantine management</span></span> |<span data-ttu-id="c605a-204">从隔离区还原文件</span><span class="sxs-lookup"><span data-stu-id="c605a-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="c605a-205">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="c605a-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="c605a-206">设置早期预览 (未使用的) </span><span class="sxs-lookup"><span data-stu-id="c605a-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="c605a-207">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="c605a-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="c605a-208">设置 group-id</span><span class="sxs-lookup"><span data-stu-id="c605a-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="c605a-209">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="c605a-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="c605a-210">Set/Remove 标记，仅 `GROUP` 受支持</span><span class="sxs-lookup"><span data-stu-id="c605a-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="c605a-211">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="c605a-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="c605a-212">根 (列表) </span><span class="sxs-lookup"><span data-stu-id="c605a-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="c605a-213">适用于终结点的 Microsoft Defender 门户信息</span><span class="sxs-lookup"><span data-stu-id="c605a-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="c605a-214">在 Defender for Endpoint 门户中，你将看到两类信息：</span><span class="sxs-lookup"><span data-stu-id="c605a-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="c605a-215">防病毒警报，包括：</span><span class="sxs-lookup"><span data-stu-id="c605a-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="c605a-216">Severity</span><span class="sxs-lookup"><span data-stu-id="c605a-216">Severity</span></span>
  - <span data-ttu-id="c605a-217">扫描类型</span><span class="sxs-lookup"><span data-stu-id="c605a-217">Scan type</span></span>
  - <span data-ttu-id="c605a-218">设备信息 (主机名、设备标识符、租户标识符、应用版本和操作系统类型) </span><span class="sxs-lookup"><span data-stu-id="c605a-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="c605a-219">文件信息 (名称、路径、大小和哈希) </span><span class="sxs-lookup"><span data-stu-id="c605a-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="c605a-220">威胁信息 (名称、类型和状态) </span><span class="sxs-lookup"><span data-stu-id="c605a-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="c605a-221">设备信息，包括：</span><span class="sxs-lookup"><span data-stu-id="c605a-221">Device information, including:</span></span>
  - <span data-ttu-id="c605a-222">设备标识符</span><span class="sxs-lookup"><span data-stu-id="c605a-222">Device identifier</span></span>
  - <span data-ttu-id="c605a-223">租户标识符</span><span class="sxs-lookup"><span data-stu-id="c605a-223">Tenant identifier</span></span>
  - <span data-ttu-id="c605a-224">应用版本</span><span class="sxs-lookup"><span data-stu-id="c605a-224">App version</span></span>
  - <span data-ttu-id="c605a-225">主机名称</span><span class="sxs-lookup"><span data-stu-id="c605a-225">Hostname</span></span>
  - <span data-ttu-id="c605a-226">操作系统类型</span><span class="sxs-lookup"><span data-stu-id="c605a-226">OS type</span></span>
  - <span data-ttu-id="c605a-227">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="c605a-227">OS version</span></span>
  - <span data-ttu-id="c605a-228">计算机模型</span><span class="sxs-lookup"><span data-stu-id="c605a-228">Computer model</span></span>
  - <span data-ttu-id="c605a-229">处理器体系结构</span><span class="sxs-lookup"><span data-stu-id="c605a-229">Processor architecture</span></span>
  - <span data-ttu-id="c605a-230">设备是否是虚拟机</span><span class="sxs-lookup"><span data-stu-id="c605a-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="c605a-231">已知问题</span><span class="sxs-lookup"><span data-stu-id="c605a-231">Known issues</span></span>

- <span data-ttu-id="c605a-232">你可能会在 Microsoft Defender 安全中心门户的机器信息页中看到"无传感器数据，通信受损"，即使产品正在正常工作。</span><span class="sxs-lookup"><span data-stu-id="c605a-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="c605a-233">我们正在解决此问题。</span><span class="sxs-lookup"><span data-stu-id="c605a-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="c605a-234">登录的用户不会显示在 Microsoft Defender 安全中心门户中。</span><span class="sxs-lookup"><span data-stu-id="c605a-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="c605a-235">在 SUSE 分发中，如果 *libatomic1* 安装失败，应验证操作系统是否注册：</span><span class="sxs-lookup"><span data-stu-id="c605a-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
