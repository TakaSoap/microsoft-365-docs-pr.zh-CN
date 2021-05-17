---
title: Mac 上的 Microsoft Defender for Endpoint 的新增功能
description: 了解 Mac 上早期版本的 Microsoft Defender for Endpoint 的主要更改。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， macos， whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: a1e07ac2e2e544605f04e9090177004db64d2f04
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994993"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="97fb7-104">Mac 上的 Microsoft Defender for Endpoint 的新增功能</span><span class="sxs-lookup"><span data-stu-id="97fb7-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="97fb7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="97fb7-105">**Applies to:**</span></span>
- [<span data-ttu-id="97fb7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="97fb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="97fb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97fb7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="97fb7-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="97fb7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97fb7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="97fb7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="97fb7-110">在 macOS 11 (Sur) 上，Microsoft Defender for Endpoint 需要额外的配置文件。</span><span class="sxs-lookup"><span data-stu-id="97fb7-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="97fb7-111">如果你是从 macOS 早期版本升级的现有客户，请确保部署此页中列出的其他 [配置文件](mac-sysext-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="97fb7-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="97fb7-112">101.27.50 (20.121022.12750.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-112">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="97fb7-113">修复以适应 macOS Catalina 和更早版本 Apple 证书过期。</span><span class="sxs-lookup"><span data-stu-id="97fb7-113">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="97fb7-114">此修补程序还原 TVM &威胁 (漏洞) 功能。</span><span class="sxs-lookup"><span data-stu-id="97fb7-114">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="97fb7-115">101.25.69 (20.121022.12569.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-115">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="97fb7-116">macOS 上的 Microsoft Defender for Endpoint 现在可供美国政府客户预览使用。</span><span class="sxs-lookup"><span data-stu-id="97fb7-116">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="97fb7-117">有关详细信息，请参阅 [Microsoft Defender for Endpoint for US Government customers](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="97fb7-117">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="97fb7-118">性能改进 (专为使用 XCode 模拟器应用修复错误) &的情况。</span><span class="sxs-lookup"><span data-stu-id="97fb7-118">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="97fb7-119">101.23.64 (20.121021.12364.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-119">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="97fb7-120">向命令行工具添加了一个新选项，用于查看有关上次按需扫描的信息。</span><span class="sxs-lookup"><span data-stu-id="97fb7-120">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="97fb7-121">若要查看有关上次按需扫描的信息，请运行 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="97fb7-121">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="97fb7-122">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-122">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="97fb7-123">101.22.79 (20.121012.12279.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-123">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="97fb7-124">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-124">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="97fb7-125">101.19.88 (20.121011.11988.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-125">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="97fb7-126">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-126">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="97fb7-127">101.19.48 (20.120121.11948.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-127">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="97fb7-128">此版本已弃用旧的命令行工具语法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-128">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="97fb7-129">有关新语法的信息，请参阅 [Resources](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="97fb7-129">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="97fb7-130">添加了一个新的命令行开关以禁用网络扩展 `mdatp system-extension network-filter disable` ：。</span><span class="sxs-lookup"><span data-stu-id="97fb7-130">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="97fb7-131">此命令可用于解决与 Mac 上的 Microsoft Defender for Endpoint 相关的网络问题</span><span class="sxs-lookup"><span data-stu-id="97fb7-131">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="97fb7-132">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-132">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="97fb7-133">101.19.21 (20.120101.11921.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-133">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="97fb7-134">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-134">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="97fb7-135">101.15.26 (20.120102.11526.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-135">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="97fb7-136">改进了在 macOS 11 Big Sur 上运行的代理的可靠性</span><span class="sxs-lookup"><span data-stu-id="97fb7-136">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="97fb7-137">添加了一个新的命令行开关 () 自定义扫描过程中忽略 `--ignore-exclusions` AV 排除 `mdatp scan custom` () </span><span class="sxs-lookup"><span data-stu-id="97fb7-137">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="97fb7-138">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-138">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="97fb7-139">101.13.75 (20.120101.11375.0) </span><span class="sxs-lookup"><span data-stu-id="97fb7-139">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="97fb7-140">删除了 Microsoft Defender for Endpoint 触发 macOS 11 (大 Sur) 清单到内核内核错误时的条件</span><span class="sxs-lookup"><span data-stu-id="97fb7-140">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="97fb7-141">修复了在 Mac 11 和 Big Sur (运行时 Endpoint Security 系统扩展) </span><span class="sxs-lookup"><span data-stu-id="97fb7-141">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="97fb7-142">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-142">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="97fb7-143">101.10.72</span><span class="sxs-lookup"><span data-stu-id="97fb7-143">101.10.72</span></span>

- <span data-ttu-id="97fb7-144">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-144">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="97fb7-145">101.09.61</span><span class="sxs-lookup"><span data-stu-id="97fb7-145">101.09.61</span></span>

- <span data-ttu-id="97fb7-146">添加了用于禁用 [发送反馈选项的新托管首选项](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="97fb7-146">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="97fb7-147">"状态"菜单图标现在在管理产品设置时显示正常状态。</span><span class="sxs-lookup"><span data-stu-id="97fb7-147">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="97fb7-148">以前，状态菜单图标显示警告或错误状态，即使产品设置由管理员管理</span><span class="sxs-lookup"><span data-stu-id="97fb7-148">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="97fb7-149">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-149">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="97fb7-150">101.09.50</span><span class="sxs-lookup"><span data-stu-id="97fb7-150">101.09.50</span></span>

- <span data-ttu-id="97fb7-151">该产品版本已在 macOS Big Sur 11 beta 9 上经过验证</span><span class="sxs-lookup"><span data-stu-id="97fb7-151">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="97fb7-152">命令行工具的新 `mdatp` 语法现在是默认语法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-152">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="97fb7-153">有关新语法详细信息，请参阅[macOS](mac-resources.md#configuring-from-the-command-line)上的 Microsoft Defender for Endpoint 的资源</span><span class="sxs-lookup"><span data-stu-id="97fb7-153">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="97fb7-154">**2021** 年 1 月 1 日将从产品中删除旧的命令行工具语法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-154">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="97fb7-155">使用新的参数扩展 () ，该参数允许将诊断日志 `mdatp diagnostic create` `--path [directory]` 保存到其他目录</span><span class="sxs-lookup"><span data-stu-id="97fb7-155">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="97fb7-156">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-156">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="97fb7-157">101.09.49</span><span class="sxs-lookup"><span data-stu-id="97fb7-157">101.09.49</span></span>

- <span data-ttu-id="97fb7-158">用户界面改进，用于区分由 IT 管理员管理的排除项与本地用户定义的排除项</span><span class="sxs-lookup"><span data-stu-id="97fb7-158">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="97fb7-159">按需扫描期间改进的 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="97fb7-159">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="97fb7-160">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-160">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="97fb7-161">101.07.23</span><span class="sxs-lookup"><span data-stu-id="97fb7-161">101.07.23</span></span>

- <span data-ttu-id="97fb7-162">向 输出添加了新字段，用于检查被动模式的状态和EDR `mdatp --health` ID</span><span class="sxs-lookup"><span data-stu-id="97fb7-162">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="97fb7-163">`mdatp --health` 将在将来的 `mdatp health` 产品更新中替换为 。</span><span class="sxs-lookup"><span data-stu-id="97fb7-163">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="97fb7-164">修复了在用户界面中自动提交示例未标记为托管的错误</span><span class="sxs-lookup"><span data-stu-id="97fb7-164">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="97fb7-165">添加了用于控制防病毒扫描历史记录中项目的保留的新设置。</span><span class="sxs-lookup"><span data-stu-id="97fb7-165">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="97fb7-166">现在可以指定 [在扫描历史记录](mac-preferences.md#antivirus-scan-history-retention-in-days) 中保留项目的天数，并指定扫描历史记录中 [的最大项目数](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="97fb7-166">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="97fb7-167">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-167">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="97fb7-168">101.06.63</span><span class="sxs-lookup"><span data-stu-id="97fb7-168">101.06.63</span></span>

- <span data-ttu-id="97fb7-169">解决了版本 中引入的性能回归 `101.05.17` 问题。</span><span class="sxs-lookup"><span data-stu-id="97fb7-169">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="97fb7-170">该回归与修复一起引入，以消除一些客户在访问 SMB 共享时观察到的内核错误。</span><span class="sxs-lookup"><span data-stu-id="97fb7-170">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="97fb7-171">我们已还原此代码更改，并正在调查消除内核内核错误的替代方法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-171">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="97fb7-172">101.05.17</span><span class="sxs-lookup"><span data-stu-id="97fb7-172">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97fb7-173">我们正在为命令行工具开发新的增强 `mdatp` 语法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-173">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="97fb7-174">新语法当前是预览体验成员 -快和预览体验成员 - 慢更新频道中的默认语法。</span><span class="sxs-lookup"><span data-stu-id="97fb7-174">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="97fb7-175">我们鼓励你使用这种新语法来自我激励。</span><span class="sxs-lookup"><span data-stu-id="97fb7-175">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="97fb7-176">我们将继续支持旧语法与新语法并行，并针对即将推出的几个月中的旧语法弃用计划提供更多通信。</span><span class="sxs-lookup"><span data-stu-id="97fb7-176">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="97fb7-177">解决了访问 SMB 文件共享时有时发生的内核内核问题</span><span class="sxs-lookup"><span data-stu-id="97fb7-177">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="97fb7-178">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-178">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="97fb7-179">101.05.16</span><span class="sxs-lookup"><span data-stu-id="97fb7-179">101.05.16</span></span>

- <span data-ttu-id="97fb7-180">对快速扫描逻辑的改进，可显著减少扫描的文件数</span><span class="sxs-lookup"><span data-stu-id="97fb7-180">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="97fb7-181">添加了 [对命令行](mac-resources.md#how-to-enable-autocompletion) 工具的自动完成支持</span><span class="sxs-lookup"><span data-stu-id="97fb7-181">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="97fb7-182">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-182">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="97fb7-183">101.03.12</span><span class="sxs-lookup"><span data-stu-id="97fb7-183">101.03.12</span></span>

- <span data-ttu-id="97fb7-184">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-184">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="97fb7-185">101.01.54</span><span class="sxs-lookup"><span data-stu-id="97fb7-185">101.01.54</span></span>

- <span data-ttu-id="97fb7-186">有关与时间机兼容性的改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-186">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="97fb7-187">辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-187">Accessibility improvements</span></span>
- <span data-ttu-id="97fb7-188">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-188">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="97fb7-189">101.00.31</span><span class="sxs-lookup"><span data-stu-id="97fb7-189">101.00.31</span></span>

- <span data-ttu-id="97fb7-190">为 [Intune 用户改进了产品载入体验](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="97fb7-190">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="97fb7-191">防病毒 [排除项现在支持通配符](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="97fb7-191">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="97fb7-192">添加了从 macOS 上下文菜单触发防病毒扫描的能力。</span><span class="sxs-lookup"><span data-stu-id="97fb7-192">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="97fb7-193">现在，你可以右键单击查找器中的文件或文件夹，然后选择使用 **Microsoft Defender for Endpoint 扫描**</span><span class="sxs-lookup"><span data-stu-id="97fb7-193">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="97fb7-194">安装程序现在明确不允许就地产品降级。</span><span class="sxs-lookup"><span data-stu-id="97fb7-194">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="97fb7-195">如果需要降级，请先卸载现有版本并重新配置设备</span><span class="sxs-lookup"><span data-stu-id="97fb7-195">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="97fb7-196">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-196">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="97fb7-197">100.90.27</span><span class="sxs-lookup"><span data-stu-id="97fb7-197">100.90.27</span></span>

- <span data-ttu-id="97fb7-198">现在可以在 macOS [上](mac-updates.md#set-the-channel-name) 为 Microsoft Defender for Endpoint 设置与系统范围的更新通道不同的更新通道</span><span class="sxs-lookup"><span data-stu-id="97fb7-198">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="97fb7-199">新产品图标</span><span class="sxs-lookup"><span data-stu-id="97fb7-199">New product icon</span></span>
- <span data-ttu-id="97fb7-200">其他用户体验改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-200">Other user experience improvements</span></span>
- <span data-ttu-id="97fb7-201">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-201">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="97fb7-202">100.86.92</span><span class="sxs-lookup"><span data-stu-id="97fb7-202">100.86.92</span></span>

- <span data-ttu-id="97fb7-203">有关与时间机兼容性的改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-203">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="97fb7-204">解决了产品有时在卸载期间未清理所有 `/Library/Application Support/Microsoft/Defender` 文件的问题</span><span class="sxs-lookup"><span data-stu-id="97fb7-204">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="97fb7-205">通过 Microsoft AutoUpdate 更新 Microsoft 产品时降低了产品的 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="97fb7-205">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="97fb7-206">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-206">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="97fb7-207">100.86.91</span><span class="sxs-lookup"><span data-stu-id="97fb7-207">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="97fb7-208">为了确保对 macOS 设备进行最完整的保护，并且与 Apple 停止向低于 [current – 2] 的操作系统版本交付 macOS 本机安全更新一致，macOS Sierra [10.12] 将不再支持 MDATP for Mac 部署和更新。</span><span class="sxs-lookup"><span data-stu-id="97fb7-208">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="97fb7-209">MDATP For Mac 更新和增强功能将传递到运行版本 Catalina [10.15]、Mojave [10.14] 和 High Sierra [10.13] 的设备。</span><span class="sxs-lookup"><span data-stu-id="97fb7-209">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="97fb7-210">如果你已经将 MDATP for Mac 部署到 Sierra [10.12] 设备，请升级到最新的 macOS 版本以消除丢失保护的风险。</span><span class="sxs-lookup"><span data-stu-id="97fb7-210">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="97fb7-211">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-211">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="97fb7-212">100.83.73</span><span class="sxs-lookup"><span data-stu-id="97fb7-212">100.83.73</span></span>

- <span data-ttu-id="97fb7-213">为 IT 管理员添加了更多有关排除[管理](mac-preferences.md#exclusion-merge-policy)、威胁类型[](mac-preferences.md#threat-type-settings-merge-policy)设置管理和禁止[威胁操作的控制](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="97fb7-213">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="97fb7-214">当设备上未启用"完全磁盘访问"时，现在状态菜单中将显示一条警告</span><span class="sxs-lookup"><span data-stu-id="97fb7-214">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="97fb7-215">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-215">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="97fb7-216">100.82.60</span><span class="sxs-lookup"><span data-stu-id="97fb7-216">100.82.60</span></span>

- <span data-ttu-id="97fb7-217">解决了产品无法开始关注定义更新的问题。</span><span class="sxs-lookup"><span data-stu-id="97fb7-217">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="97fb7-218">100.80.42</span><span class="sxs-lookup"><span data-stu-id="97fb7-218">100.80.42</span></span>

- <span data-ttu-id="97fb7-219">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-219">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="97fb7-220">100.79.42</span><span class="sxs-lookup"><span data-stu-id="97fb7-220">100.79.42</span></span>

- <span data-ttu-id="97fb7-221">修复了 Mac 上的 Microsoft Defender for Endpoint 有时干扰时间计算机的问题</span><span class="sxs-lookup"><span data-stu-id="97fb7-221">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="97fb7-222">向命令行实用工具添加了一个新开关，用于测试与后端服务的连接</span><span class="sxs-lookup"><span data-stu-id="97fb7-222">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="97fb7-223">添加了在用户界面中查看完整威胁历史记录 (可以从"保护历史记录"视图访问) </span><span class="sxs-lookup"><span data-stu-id="97fb7-223">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="97fb7-224">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-224">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="97fb7-225">100.72.15</span><span class="sxs-lookup"><span data-stu-id="97fb7-225">100.72.15</span></span>

- <span data-ttu-id="97fb7-226">Bug 修复</span><span class="sxs-lookup"><span data-stu-id="97fb7-226">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="97fb7-227">100.70.99</span><span class="sxs-lookup"><span data-stu-id="97fb7-227">100.70.99</span></span>

- <span data-ttu-id="97fb7-228">解决了在启用实时保护时影响某些用户升级到 macOS 加泰罗尼亚语的能力的问题。</span><span class="sxs-lookup"><span data-stu-id="97fb7-228">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="97fb7-229">此个别问题由 Microsoft Defender for Endpoint 在Catalina 升级包中锁定文件，同时扫描它们以发现威胁导致升级序列失败导致的。</span><span class="sxs-lookup"><span data-stu-id="97fb7-229">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="97fb7-230">100.68.99</span><span class="sxs-lookup"><span data-stu-id="97fb7-230">100.68.99</span></span>

- <span data-ttu-id="97fb7-231">添加了将防病毒功能配置为在被动模式下 [运行的功能](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="97fb7-231">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="97fb7-232">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-232">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="97fb7-233">100.65.28</span><span class="sxs-lookup"><span data-stu-id="97fb7-233">100.65.28</span></span>

- <span data-ttu-id="97fb7-234">增加了对 macOS 加泰罗尼亚语的支持</span><span class="sxs-lookup"><span data-stu-id="97fb7-234">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="97fb7-235">macOS 10.15 (Catalina) 新增了安全和隐私增强功能。</span><span class="sxs-lookup"><span data-stu-id="97fb7-235">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="97fb7-236">从此版本开始，默认情况下，应用程序无法访问磁盘上的某些位置 (如文档、下载、桌面等) 未经明确同意。</span><span class="sxs-lookup"><span data-stu-id="97fb7-236">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="97fb7-237">如果没有此同意，Microsoft Defender for Endpoint 将无法完全保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="97fb7-237">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="97fb7-238">授予此同意的机制取决于你部署适用于终结点的 Microsoft Defender 的方式：</span><span class="sxs-lookup"><span data-stu-id="97fb7-238">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="97fb7-239">有关手动部署，请参阅手动部署主题 [中的更新](mac-install-manually.md#how-to-allow-full-disk-access) 说明。</span><span class="sxs-lookup"><span data-stu-id="97fb7-239">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="97fb7-240">有关托管部署，请参阅基于[JAMF](mac-install-with-jamf.md)的部署和基于Microsoft Intune[部署主题中的更新](mac-install-with-intune.md#create-system-configuration-profiles)说明。</span><span class="sxs-lookup"><span data-stu-id="97fb7-240">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="97fb7-241">Bug 修复&性能改进</span><span class="sxs-lookup"><span data-stu-id="97fb7-241">Performance improvements & bug fixes</span></span>
