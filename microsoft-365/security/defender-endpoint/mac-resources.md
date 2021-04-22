---
title: Mac 上的 Microsoft Defender for Endpoint 的资源
description: 适用于 Mac 版 Microsoft Defender for Endpoint 的资源，包括如何卸载它、如何收集诊断日志、CLI 命令以及产品的已知问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: 34feeec0f8c34748678862b9aa7b20f84087eb5e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934521"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="2496e-104">macOS 上的 Microsoft Defender for Endpoint 的资源</span><span class="sxs-lookup"><span data-stu-id="2496e-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2496e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2496e-105">**Applies to:**</span></span>
- [<span data-ttu-id="2496e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2496e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2496e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2496e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2496e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2496e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2496e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2496e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="2496e-110">收集诊断信息</span><span class="sxs-lookup"><span data-stu-id="2496e-110">Collecting diagnostic information</span></span>

<span data-ttu-id="2496e-111">如果可以重现问题，请提高日志记录级别，运行系统一段时间，将日志记录级别还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="2496e-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="2496e-112">提高日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="2496e-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="2496e-113">重现问题</span><span class="sxs-lookup"><span data-stu-id="2496e-113">Reproduce the problem</span></span>

3. <span data-ttu-id="2496e-114">运行 `sudo mdatp diagnostic create` 以备份适用于终结点的 Microsoft Defender 日志。</span><span class="sxs-lookup"><span data-stu-id="2496e-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="2496e-115">这些文件将存储在 .zip 存档中。</span><span class="sxs-lookup"><span data-stu-id="2496e-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="2496e-116">此命令还会在操作成功后输出备份的文件路径。</span><span class="sxs-lookup"><span data-stu-id="2496e-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="2496e-117">默认情况下，诊断日志将保存到 `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。</span><span class="sxs-lookup"><span data-stu-id="2496e-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="2496e-118">若要更改保存诊断日志的目录，请传递给以下命令， `--path [directory]` `[directory]` 将 替换为所需的目录。</span><span class="sxs-lookup"><span data-stu-id="2496e-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="2496e-119">还原日志记录级别：</span><span class="sxs-lookup"><span data-stu-id="2496e-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="2496e-120">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="2496e-120">Logging installation issues</span></span>

<span data-ttu-id="2496e-121">如果在安装过程中发生错误，安装程序将只报告常规故障。</span><span class="sxs-lookup"><span data-stu-id="2496e-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="2496e-122">详细日志将保存到 `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="2496e-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="2496e-123">如果在安装过程中遇到问题，请将此文件发送给我们，以便我们可以帮助诊断原因。</span><span class="sxs-lookup"><span data-stu-id="2496e-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="2496e-124">卸载</span><span class="sxs-lookup"><span data-stu-id="2496e-124">Uninstalling</span></span>

<span data-ttu-id="2496e-125">有几种方法可以卸载 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="2496e-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="2496e-126">请注意，尽管集中管理的卸载在 JAMF 上可用，但它尚不可用于 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="2496e-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="2496e-127">交互式卸载</span><span class="sxs-lookup"><span data-stu-id="2496e-127">Interactive uninstallation</span></span>

- <span data-ttu-id="2496e-128">打开 **Finder > Applications**。</span><span class="sxs-lookup"><span data-stu-id="2496e-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="2496e-129">右键单击 **Microsoft Defender for Endpoint >移动到回收站**。</span><span class="sxs-lookup"><span data-stu-id="2496e-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="2496e-130">从命令行</span><span class="sxs-lookup"><span data-stu-id="2496e-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="2496e-131">从命令行配置</span><span class="sxs-lookup"><span data-stu-id="2496e-131">Configuring from the command line</span></span>

<span data-ttu-id="2496e-132">可以通过命令行完成重要任务，如控制产品设置和触发按需扫描：</span><span class="sxs-lookup"><span data-stu-id="2496e-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="2496e-133">Group</span><span class="sxs-lookup"><span data-stu-id="2496e-133">Group</span></span>        |<span data-ttu-id="2496e-134">方案</span><span class="sxs-lookup"><span data-stu-id="2496e-134">Scenario</span></span>                                   |<span data-ttu-id="2496e-135">命令</span><span class="sxs-lookup"><span data-stu-id="2496e-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="2496e-136">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-136">Configuration</span></span>|<span data-ttu-id="2496e-137">打开/关闭实时保护</span><span class="sxs-lookup"><span data-stu-id="2496e-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="2496e-138">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-138">Configuration</span></span>|<span data-ttu-id="2496e-139">打开/关闭云保护</span><span class="sxs-lookup"><span data-stu-id="2496e-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="2496e-140">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-140">Configuration</span></span>|<span data-ttu-id="2496e-141">打开/关闭产品诊断</span><span class="sxs-lookup"><span data-stu-id="2496e-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="2496e-142">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-142">Configuration</span></span>|<span data-ttu-id="2496e-143">打开/关闭自动提交示例</span><span class="sxs-lookup"><span data-stu-id="2496e-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="2496e-144">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-144">Configuration</span></span>|<span data-ttu-id="2496e-145">向允许列表添加威胁名称</span><span class="sxs-lookup"><span data-stu-id="2496e-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="2496e-146">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-146">Configuration</span></span>|<span data-ttu-id="2496e-147">从允许列表中删除威胁名称</span><span class="sxs-lookup"><span data-stu-id="2496e-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="2496e-148">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-148">Configuration</span></span>|<span data-ttu-id="2496e-149">列出所有允许的威胁名称</span><span class="sxs-lookup"><span data-stu-id="2496e-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="2496e-150">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-150">Configuration</span></span>|<span data-ttu-id="2496e-151">打开 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="2496e-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="2496e-152">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-152">Configuration</span></span>|<span data-ttu-id="2496e-153">关闭 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="2496e-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="2496e-154">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-154">Configuration</span></span>|<span data-ttu-id="2496e-155">打开 PUA 保护的审核模式</span><span class="sxs-lookup"><span data-stu-id="2496e-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="2496e-156">配置</span><span class="sxs-lookup"><span data-stu-id="2496e-156">Configuration</span></span>|<span data-ttu-id="2496e-157">打开/关闭 passiveMode</span><span class="sxs-lookup"><span data-stu-id="2496e-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="2496e-158">诊断</span><span class="sxs-lookup"><span data-stu-id="2496e-158">Diagnostics</span></span>  |<span data-ttu-id="2496e-159">更改日志级别</span><span class="sxs-lookup"><span data-stu-id="2496e-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="2496e-160">诊断</span><span class="sxs-lookup"><span data-stu-id="2496e-160">Diagnostics</span></span>  |<span data-ttu-id="2496e-161">生成诊断日志</span><span class="sxs-lookup"><span data-stu-id="2496e-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="2496e-162">健康</span><span class="sxs-lookup"><span data-stu-id="2496e-162">Health</span></span>       |<span data-ttu-id="2496e-163">检查产品的运行状况</span><span class="sxs-lookup"><span data-stu-id="2496e-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="2496e-164">健康</span><span class="sxs-lookup"><span data-stu-id="2496e-164">Health</span></span>       |<span data-ttu-id="2496e-165">检查spefic产品属性</span><span class="sxs-lookup"><span data-stu-id="2496e-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="2496e-166">Protection</span><span class="sxs-lookup"><span data-stu-id="2496e-166">Protection</span></span>   |<span data-ttu-id="2496e-167">扫描路径</span><span class="sxs-lookup"><span data-stu-id="2496e-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="2496e-168">Protection</span><span class="sxs-lookup"><span data-stu-id="2496e-168">Protection</span></span>   |<span data-ttu-id="2496e-169">执行快速扫描</span><span class="sxs-lookup"><span data-stu-id="2496e-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="2496e-170">Protection</span><span class="sxs-lookup"><span data-stu-id="2496e-170">Protection</span></span>   |<span data-ttu-id="2496e-171">执行完全扫描</span><span class="sxs-lookup"><span data-stu-id="2496e-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="2496e-172">Protection</span><span class="sxs-lookup"><span data-stu-id="2496e-172">Protection</span></span>   |<span data-ttu-id="2496e-173">取消正在进行的按需扫描</span><span class="sxs-lookup"><span data-stu-id="2496e-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="2496e-174">Protection</span><span class="sxs-lookup"><span data-stu-id="2496e-174">Protection</span></span>   |<span data-ttu-id="2496e-175">请求安全智能更新</span><span class="sxs-lookup"><span data-stu-id="2496e-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="2496e-176">EDR</span><span class="sxs-lookup"><span data-stu-id="2496e-176">EDR</span></span>          |<span data-ttu-id="2496e-177">将组标记添加到设备。</span><span class="sxs-lookup"><span data-stu-id="2496e-177">Add group tag to device.</span></span> <span data-ttu-id="2496e-178">EDR 标记用于管理设备组。</span><span class="sxs-lookup"><span data-stu-id="2496e-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="2496e-179">有关详细信息，请访问 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="2496e-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="2496e-180">EDR</span><span class="sxs-lookup"><span data-stu-id="2496e-180">EDR</span></span>          |<span data-ttu-id="2496e-181">从设备中删除组标记</span><span class="sxs-lookup"><span data-stu-id="2496e-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="2496e-182">EDR</span><span class="sxs-lookup"><span data-stu-id="2496e-182">EDR</span></span>          |<span data-ttu-id="2496e-183">添加组 ID</span><span class="sxs-lookup"><span data-stu-id="2496e-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="2496e-184">如何启用自动完成</span><span class="sxs-lookup"><span data-stu-id="2496e-184">How to enable autocompletion</span></span>

<span data-ttu-id="2496e-185">若要在 Bash 中启用自动完成，请运行以下命令并重新启动终端会话：</span><span class="sxs-lookup"><span data-stu-id="2496e-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="2496e-186">在 zsh 中启用自动完成：</span><span class="sxs-lookup"><span data-stu-id="2496e-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="2496e-187">检查是否已在设备上启用自动完成：</span><span class="sxs-lookup"><span data-stu-id="2496e-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="2496e-188">如果上述命令未生成任何输出，可以使用以下命令启用自动完成：</span><span class="sxs-lookup"><span data-stu-id="2496e-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="2496e-189">运行以下命令以在 macOS 上为 Microsoft Defender for Endpoint 启用自动完成，并重新启动终端会话：</span><span class="sxs-lookup"><span data-stu-id="2496e-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="2496e-190">客户端 Microsoft Defender for Endpoint 隔离目录</span><span class="sxs-lookup"><span data-stu-id="2496e-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="2496e-191">`/Library/Application Support/Microsoft/Defender/quarantine/` 包含由 隔离的文件 `mdatp` 。</span><span class="sxs-lookup"><span data-stu-id="2496e-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="2496e-192">这些文件以威胁跟踪 Id 命名。</span><span class="sxs-lookup"><span data-stu-id="2496e-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="2496e-193">当前 trackingIds 显示为 `mdatp threat list` 。</span><span class="sxs-lookup"><span data-stu-id="2496e-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="2496e-194">适用于终结点的 Microsoft Defender 门户信息</span><span class="sxs-lookup"><span data-stu-id="2496e-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="2496e-195">[适用于 macOS 的 EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)功能现已到达，位于 Microsoft Defender for Endpoint 博客上，提供有关 Microsoft Defender for Endpoint Security Center 中预期内容的详细指南。</span><span class="sxs-lookup"><span data-stu-id="2496e-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
