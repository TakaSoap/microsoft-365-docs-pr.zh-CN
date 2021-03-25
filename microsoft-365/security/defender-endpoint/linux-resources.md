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
ms.openlocfilehash: 7196053ffef3dffc3c737d0df26a5d12bdfe8a4c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187753"
---
# <a name="resources"></a><span data-ttu-id="9996e-104">资源</span><span class="sxs-lookup"><span data-stu-id="9996e-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9996e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9996e-105">**Applies to:**</span></span>
- [<span data-ttu-id="9996e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9996e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9996e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9996e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9996e-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9996e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9996e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9996e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="9996e-110">收集诊断信息</span><span class="sxs-lookup"><span data-stu-id="9996e-110">Collect diagnostic information</span></span>

<span data-ttu-id="9996e-111">如果可以重现问题，请首先增加日志记录级别，运行系统一段时间，然后将日志记录级别还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="9996e-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="9996e-112">提高日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="9996e-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="9996e-113">重现问题。</span><span class="sxs-lookup"><span data-stu-id="9996e-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="9996e-114">运行以下命令以备份适用于终结点日志的 Defender。</span><span class="sxs-lookup"><span data-stu-id="9996e-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="9996e-115">这些文件将存储在 .zip 存档内部。</span><span class="sxs-lookup"><span data-stu-id="9996e-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="9996e-116">在操作成功后，此命令还会输出备份的文件路径：</span><span class="sxs-lookup"><span data-stu-id="9996e-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="9996e-117">还原日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="9996e-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="9996e-118">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="9996e-118">Log installation issues</span></span>

<span data-ttu-id="9996e-119">如果在安装过程中发生错误，安装程序将只报告常规故障。</span><span class="sxs-lookup"><span data-stu-id="9996e-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="9996e-120">详细日志将保存到 `/var/log/microsoft/mdatp_install.log` 。</span><span class="sxs-lookup"><span data-stu-id="9996e-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="9996e-121">如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。</span><span class="sxs-lookup"><span data-stu-id="9996e-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="9996e-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="9996e-122">Uninstall</span></span>

<span data-ttu-id="9996e-123">有几种方法可以卸载适用于 Linux 的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="9996e-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="9996e-124">如果你使用的是配置工具（如"开发工具"，请按照配置工具的程序包卸载说明操作）。</span><span class="sxs-lookup"><span data-stu-id="9996e-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="9996e-125">手动卸载</span><span class="sxs-lookup"><span data-stu-id="9996e-125">Manual uninstallation</span></span>

- <span data-ttu-id="9996e-126">`sudo yum remove mdatp` For RHEL and variants (CentOS and Oracle Linux) .</span><span class="sxs-lookup"><span data-stu-id="9996e-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="9996e-127">`sudo zypper remove mdatp` 用于 SLES 和变量。</span><span class="sxs-lookup"><span data-stu-id="9996e-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="9996e-128">`sudo apt-get purge mdatp` 用于 Ubuntu 和 Debian 系统。</span><span class="sxs-lookup"><span data-stu-id="9996e-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="9996e-129">从命令行配置</span><span class="sxs-lookup"><span data-stu-id="9996e-129">Configure from the command line</span></span>

<span data-ttu-id="9996e-130">可以通过命令行完成重要任务，如控制产品设置和触发按需扫描。</span><span class="sxs-lookup"><span data-stu-id="9996e-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="9996e-131">全局选项</span><span class="sxs-lookup"><span data-stu-id="9996e-131">Global options</span></span>

<span data-ttu-id="9996e-132">默认情况下，命令行工具以可读格式输出结果。</span><span class="sxs-lookup"><span data-stu-id="9996e-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="9996e-133">此外，该工具还支持将结果输出为 JSON，这适用于自动化方案。</span><span class="sxs-lookup"><span data-stu-id="9996e-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="9996e-134">若要将输出更改为 JSON，请 `--output json` 传递给以下任一命令。</span><span class="sxs-lookup"><span data-stu-id="9996e-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="9996e-135">支持的命令</span><span class="sxs-lookup"><span data-stu-id="9996e-135">Supported commands</span></span>

<span data-ttu-id="9996e-136">下表列出了一些最常见方案的命令。</span><span class="sxs-lookup"><span data-stu-id="9996e-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="9996e-137">从 `mdatp help` 终端运行以查看受支持命令的完整列表。</span><span class="sxs-lookup"><span data-stu-id="9996e-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="9996e-138">Group</span><span class="sxs-lookup"><span data-stu-id="9996e-138">Group</span></span>                 |<span data-ttu-id="9996e-139">方案</span><span class="sxs-lookup"><span data-stu-id="9996e-139">Scenario</span></span>                                                |<span data-ttu-id="9996e-140">命令</span><span class="sxs-lookup"><span data-stu-id="9996e-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="9996e-141">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-141">Configuration</span></span>         |<span data-ttu-id="9996e-142">打开/关闭实时保护</span><span class="sxs-lookup"><span data-stu-id="9996e-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="9996e-143">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-143">Configuration</span></span>         |<span data-ttu-id="9996e-144">打开/关闭云保护</span><span class="sxs-lookup"><span data-stu-id="9996e-144">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="9996e-145">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-145">Configuration</span></span>         |<span data-ttu-id="9996e-146">打开/关闭产品诊断</span><span class="sxs-lookup"><span data-stu-id="9996e-146">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="9996e-147">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-147">Configuration</span></span>         |<span data-ttu-id="9996e-148">打开/关闭自动提交示例</span><span class="sxs-lookup"><span data-stu-id="9996e-148">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="9996e-149">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-149">Configuration</span></span>         |<span data-ttu-id="9996e-150">打开/关闭 AV 被动模式</span><span class="sxs-lookup"><span data-stu-id="9996e-150">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="9996e-151">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-151">Configuration</span></span>         |<span data-ttu-id="9996e-152">添加/删除文件扩展名的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="9996e-152">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="9996e-153">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-153">Configuration</span></span>         |<span data-ttu-id="9996e-154">添加/删除文件的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="9996e-154">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="9996e-155">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-155">Configuration</span></span>         |<span data-ttu-id="9996e-156">添加/删除目录的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="9996e-156">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="9996e-157">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-157">Configuration</span></span>         |<span data-ttu-id="9996e-158">添加/删除某个进程的防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="9996e-158">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="9996e-159">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-159">Configuration</span></span>         |<span data-ttu-id="9996e-160">列出所有防病毒排除项</span><span class="sxs-lookup"><span data-stu-id="9996e-160">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="9996e-161">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-161">Configuration</span></span>         |<span data-ttu-id="9996e-162">向允许列表添加威胁名称</span><span class="sxs-lookup"><span data-stu-id="9996e-162">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="9996e-163">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-163">Configuration</span></span>         |<span data-ttu-id="9996e-164">从允许列表中删除威胁名称</span><span class="sxs-lookup"><span data-stu-id="9996e-164">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="9996e-165">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-165">Configuration</span></span>         |<span data-ttu-id="9996e-166">列出所有允许的威胁名称</span><span class="sxs-lookup"><span data-stu-id="9996e-166">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="9996e-167">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-167">Configuration</span></span>         |<span data-ttu-id="9996e-168">打开 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="9996e-168">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="9996e-169">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-169">Configuration</span></span>         |<span data-ttu-id="9996e-170">关闭 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="9996e-170">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="9996e-171">配置</span><span class="sxs-lookup"><span data-stu-id="9996e-171">Configuration</span></span>         |<span data-ttu-id="9996e-172">打开 PUA 保护的审核模式</span><span class="sxs-lookup"><span data-stu-id="9996e-172">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="9996e-173">诊断</span><span class="sxs-lookup"><span data-stu-id="9996e-173">Diagnostics</span></span>           |<span data-ttu-id="9996e-174">更改日志级别</span><span class="sxs-lookup"><span data-stu-id="9996e-174">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="9996e-175">诊断</span><span class="sxs-lookup"><span data-stu-id="9996e-175">Diagnostics</span></span>           |<span data-ttu-id="9996e-176">生成诊断日志</span><span class="sxs-lookup"><span data-stu-id="9996e-176">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="9996e-177">健康</span><span class="sxs-lookup"><span data-stu-id="9996e-177">Health</span></span>                |<span data-ttu-id="9996e-178">检查产品的运行状况</span><span class="sxs-lookup"><span data-stu-id="9996e-178">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="9996e-179">Protection</span><span class="sxs-lookup"><span data-stu-id="9996e-179">Protection</span></span>            |<span data-ttu-id="9996e-180">扫描路径</span><span class="sxs-lookup"><span data-stu-id="9996e-180">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="9996e-181">Protection</span><span class="sxs-lookup"><span data-stu-id="9996e-181">Protection</span></span>            |<span data-ttu-id="9996e-182">执行快速扫描</span><span class="sxs-lookup"><span data-stu-id="9996e-182">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="9996e-183">Protection</span><span class="sxs-lookup"><span data-stu-id="9996e-183">Protection</span></span>            |<span data-ttu-id="9996e-184">执行完全扫描</span><span class="sxs-lookup"><span data-stu-id="9996e-184">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="9996e-185">Protection</span><span class="sxs-lookup"><span data-stu-id="9996e-185">Protection</span></span>            |<span data-ttu-id="9996e-186">取消正在进行的按需扫描</span><span class="sxs-lookup"><span data-stu-id="9996e-186">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="9996e-187">Protection</span><span class="sxs-lookup"><span data-stu-id="9996e-187">Protection</span></span>            |<span data-ttu-id="9996e-188">请求安全智能更新</span><span class="sxs-lookup"><span data-stu-id="9996e-188">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="9996e-189">保护历史记录</span><span class="sxs-lookup"><span data-stu-id="9996e-189">Protection history</span></span>    |<span data-ttu-id="9996e-190">打印完整保护历史记录</span><span class="sxs-lookup"><span data-stu-id="9996e-190">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="9996e-191">保护历史记录</span><span class="sxs-lookup"><span data-stu-id="9996e-191">Protection history</span></span>    |<span data-ttu-id="9996e-192">获取威胁详细信息</span><span class="sxs-lookup"><span data-stu-id="9996e-192">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="9996e-193">隔离管理</span><span class="sxs-lookup"><span data-stu-id="9996e-193">Quarantine management</span></span> |<span data-ttu-id="9996e-194">列出所有隔离的文件</span><span class="sxs-lookup"><span data-stu-id="9996e-194">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="9996e-195">隔离管理</span><span class="sxs-lookup"><span data-stu-id="9996e-195">Quarantine management</span></span> |<span data-ttu-id="9996e-196">从隔离区中删除所有文件</span><span class="sxs-lookup"><span data-stu-id="9996e-196">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="9996e-197">隔离管理</span><span class="sxs-lookup"><span data-stu-id="9996e-197">Quarantine management</span></span> |<span data-ttu-id="9996e-198">将检测为威胁的文件添加到隔离区</span><span class="sxs-lookup"><span data-stu-id="9996e-198">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="9996e-199">隔离管理</span><span class="sxs-lookup"><span data-stu-id="9996e-199">Quarantine management</span></span> |<span data-ttu-id="9996e-200">从隔离区中删除检测为威胁的文件</span><span class="sxs-lookup"><span data-stu-id="9996e-200">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="9996e-201">隔离管理</span><span class="sxs-lookup"><span data-stu-id="9996e-201">Quarantine management</span></span> |<span data-ttu-id="9996e-202">从隔离区还原文件</span><span class="sxs-lookup"><span data-stu-id="9996e-202">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="9996e-203">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="9996e-203">Endpoint Detection and Response</span></span> |<span data-ttu-id="9996e-204">设置早期预览 (未使用的) </span><span class="sxs-lookup"><span data-stu-id="9996e-204">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="9996e-205">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="9996e-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="9996e-206">设置 group-id</span><span class="sxs-lookup"><span data-stu-id="9996e-206">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="9996e-207">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="9996e-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="9996e-208">Set/Remove 标记，仅 `GROUP` 受支持</span><span class="sxs-lookup"><span data-stu-id="9996e-208">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="9996e-209">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="9996e-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="9996e-210">根 (列表) </span><span class="sxs-lookup"><span data-stu-id="9996e-210">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="9996e-211">适用于终结点的 Microsoft Defender 门户信息</span><span class="sxs-lookup"><span data-stu-id="9996e-211">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="9996e-212">在 Defender for Endpoint 门户中，你将看到两类信息：</span><span class="sxs-lookup"><span data-stu-id="9996e-212">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="9996e-213">防病毒警报，包括：</span><span class="sxs-lookup"><span data-stu-id="9996e-213">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="9996e-214">Severity</span><span class="sxs-lookup"><span data-stu-id="9996e-214">Severity</span></span>
  - <span data-ttu-id="9996e-215">扫描类型</span><span class="sxs-lookup"><span data-stu-id="9996e-215">Scan type</span></span>
  - <span data-ttu-id="9996e-216">设备信息 (主机名、设备标识符、租户标识符、应用版本和操作系统类型) </span><span class="sxs-lookup"><span data-stu-id="9996e-216">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="9996e-217">文件信息 (名称、路径、大小和哈希) </span><span class="sxs-lookup"><span data-stu-id="9996e-217">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="9996e-218">威胁信息 (名称、类型和状态) </span><span class="sxs-lookup"><span data-stu-id="9996e-218">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="9996e-219">设备信息，包括：</span><span class="sxs-lookup"><span data-stu-id="9996e-219">Device information, including:</span></span>
  - <span data-ttu-id="9996e-220">设备标识符</span><span class="sxs-lookup"><span data-stu-id="9996e-220">Device identifier</span></span>
  - <span data-ttu-id="9996e-221">租户标识符</span><span class="sxs-lookup"><span data-stu-id="9996e-221">Tenant identifier</span></span>
  - <span data-ttu-id="9996e-222">应用版本</span><span class="sxs-lookup"><span data-stu-id="9996e-222">App version</span></span>
  - <span data-ttu-id="9996e-223">主机名称</span><span class="sxs-lookup"><span data-stu-id="9996e-223">Hostname</span></span>
  - <span data-ttu-id="9996e-224">操作系统类型</span><span class="sxs-lookup"><span data-stu-id="9996e-224">OS type</span></span>
  - <span data-ttu-id="9996e-225">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="9996e-225">OS version</span></span>
  - <span data-ttu-id="9996e-226">计算机模型</span><span class="sxs-lookup"><span data-stu-id="9996e-226">Computer model</span></span>
  - <span data-ttu-id="9996e-227">处理器体系结构</span><span class="sxs-lookup"><span data-stu-id="9996e-227">Processor architecture</span></span>
  - <span data-ttu-id="9996e-228">设备是否是虚拟机</span><span class="sxs-lookup"><span data-stu-id="9996e-228">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="9996e-229">已知问题</span><span class="sxs-lookup"><span data-stu-id="9996e-229">Known issues</span></span>

- <span data-ttu-id="9996e-230">你可能会在 Microsoft Defender 安全中心门户的机器信息页中看到"无传感器数据，通信受损"，即使产品正在正常工作。</span><span class="sxs-lookup"><span data-stu-id="9996e-230">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="9996e-231">我们正在解决此问题。</span><span class="sxs-lookup"><span data-stu-id="9996e-231">We are working on addressing this issue.</span></span>
- <span data-ttu-id="9996e-232">登录的用户不会显示在 Microsoft Defender 安全中心门户中。</span><span class="sxs-lookup"><span data-stu-id="9996e-232">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="9996e-233">在 SUSE 分发中，如果 *libatomic1* 安装失败，应验证操作系统是否注册：</span><span class="sxs-lookup"><span data-stu-id="9996e-233">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
