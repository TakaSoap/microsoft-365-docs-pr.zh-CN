---
title: 在 Mac 上部署 Microsoft Defender for Endpoint 更新
description: 控制企业环境中 Mac 上的 Microsoft Defender for Endpoint 的更新。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 更新， 部署
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
ms.openlocfilehash: e08781455888595d57bd8a9e6f792796ea1853cd
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684203"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c7515-104">在 macOS 上部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="c7515-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c7515-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c7515-105">**Applies to:**</span></span>

- [<span data-ttu-id="c7515-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7515-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c7515-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7515-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7515-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7515-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7515-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c7515-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7515-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c7515-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c7515-111">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="c7515-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="c7515-112">若要更新 macOS 上的 Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。</span><span class="sxs-lookup"><span data-stu-id="c7515-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="c7515-113">默认情况下，MAU 每天自动检查更新，但你可以将更新更改为每周、每月或手动。</span><span class="sxs-lookup"><span data-stu-id="c7515-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU 屏幕截图](images/MDATP-34-MAU.png)

<span data-ttu-id="c7515-115">如果决定使用软件分发工具部署更新，应配置 MAU 以手动检查软件更新。</span><span class="sxs-lookup"><span data-stu-id="c7515-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="c7515-116">你可以部署首选项，以配置 MAU 检查组织中 Mac 的更新方式和时间。</span><span class="sxs-lookup"><span data-stu-id="c7515-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="c7515-117">使用 msupdate</span><span class="sxs-lookup"><span data-stu-id="c7515-117">Use msupdate</span></span>

<span data-ttu-id="c7515-118">MAU 包括一个称为 *msupdate* 的命令行工具，该工具专为 IT 管理员设计，以便他们可以更精确地控制何时应用更新。</span><span class="sxs-lookup"><span data-stu-id="c7515-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="c7515-119">有关如何使用此工具的说明，请参阅 Update Office for Mac [by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)。</span><span class="sxs-lookup"><span data-stu-id="c7515-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="c7515-120">在 MAU 中，macOS 上的 Microsoft Defender for Endpoint 的应用程序标识符是 *WDAV00*。</span><span class="sxs-lookup"><span data-stu-id="c7515-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="c7515-121">若要在 macOS 上下载并安装 Microsoft Defender for Endpoint 的最新更新，请从"终端"窗口执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c7515-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="c7515-122">设置 Microsoft AutoUpdate 的首选项</span><span class="sxs-lookup"><span data-stu-id="c7515-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="c7515-123">本节介绍可用于配置 MAU 的最常见首选项。</span><span class="sxs-lookup"><span data-stu-id="c7515-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="c7515-124">可以通过企业使用的管理控制台将这些设置部署为配置文件。</span><span class="sxs-lookup"><span data-stu-id="c7515-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="c7515-125">以下各节显示了配置文件的示例。</span><span class="sxs-lookup"><span data-stu-id="c7515-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="c7515-126">设置频道名称</span><span class="sxs-lookup"><span data-stu-id="c7515-126">Set the channel name</span></span>

<span data-ttu-id="c7515-127">通道确定通过 MAU 提供的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="c7515-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="c7515-128">中的设备可以在 和 中的设备 `Beta` 之前试用 `Preview` 新功能 `Current` 。</span><span class="sxs-lookup"><span data-stu-id="c7515-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="c7515-129">`Current`渠道包含最稳定的产品版本。</span><span class="sxs-lookup"><span data-stu-id="c7515-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c7515-130">在 Microsoft AutoUpdate 版本 4.29 之前，频道具有不同的名称：</span><span class="sxs-lookup"><span data-stu-id="c7515-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="c7515-131">`Beta` 被命名为 `InsiderFast` (Insider Fast) </span><span class="sxs-lookup"><span data-stu-id="c7515-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="c7515-132">`Preview` 被命名为 `External` (Insider Slow) </span><span class="sxs-lookup"><span data-stu-id="c7515-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="c7515-133">`Current` 已命名 `Production`</span><span class="sxs-lookup"><span data-stu-id="c7515-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="c7515-134">为了预览新功能并提供早期反馈，建议将企业中某些设备配置为 `Beta` 或 `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="c7515-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="c7515-135">节</span><span class="sxs-lookup"><span data-stu-id="c7515-135">Section</span></span>|<span data-ttu-id="c7515-136">值</span><span class="sxs-lookup"><span data-stu-id="c7515-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-137">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-138">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-138">**Key**</span></span> | <span data-ttu-id="c7515-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="c7515-139">ChannelName</span></span> |
| <span data-ttu-id="c7515-140">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-140">**Data type**</span></span> | <span data-ttu-id="c7515-141">String</span><span class="sxs-lookup"><span data-stu-id="c7515-141">String</span></span> |
| <span data-ttu-id="c7515-142">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7515-142">**Possible values**</span></span> | <span data-ttu-id="c7515-143">Beta 版本</span><span class="sxs-lookup"><span data-stu-id="c7515-143">Beta</span></span> <br/> <span data-ttu-id="c7515-144">预览</span><span class="sxs-lookup"><span data-stu-id="c7515-144">Preview</span></span> <br/> <span data-ttu-id="c7515-145">Current</span><span class="sxs-lookup"><span data-stu-id="c7515-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="c7515-146">此设置更改通过 Microsoft AutoUpdate 更新的所有应用程序的通道。</span><span class="sxs-lookup"><span data-stu-id="c7515-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="c7515-147">若要仅为 macOS 上的 Microsoft Defender for Endpoint 更改通道，请用所需通道替换后执行 `[channel-name]` 以下命令：</span><span class="sxs-lookup"><span data-stu-id="c7515-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="c7515-148">设置更新检查频率</span><span class="sxs-lookup"><span data-stu-id="c7515-148">Set update check frequency</span></span>

<span data-ttu-id="c7515-149">更改 MAU 搜索更新频繁。</span><span class="sxs-lookup"><span data-stu-id="c7515-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="c7515-150">节</span><span class="sxs-lookup"><span data-stu-id="c7515-150">Section</span></span>|<span data-ttu-id="c7515-151">值</span><span class="sxs-lookup"><span data-stu-id="c7515-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-152">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-153">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-153">**Key**</span></span> | <span data-ttu-id="c7515-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="c7515-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="c7515-155">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-155">**Data type**</span></span> | <span data-ttu-id="c7515-156">整数</span><span class="sxs-lookup"><span data-stu-id="c7515-156">Integer</span></span> |
| <span data-ttu-id="c7515-157">**默认值**</span><span class="sxs-lookup"><span data-stu-id="c7515-157">**Default value**</span></span> | <span data-ttu-id="c7515-158">720 (分钟) </span><span class="sxs-lookup"><span data-stu-id="c7515-158">720 (minutes)</span></span> |
| <span data-ttu-id="c7515-159">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c7515-159">**Comment**</span></span> | <span data-ttu-id="c7515-160">此值以分钟数设置。</span><span class="sxs-lookup"><span data-stu-id="c7515-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="c7515-161">更改 MAU 与更新的交互方式</span><span class="sxs-lookup"><span data-stu-id="c7515-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="c7515-162">更改 MAU 搜索更新时如何。</span><span class="sxs-lookup"><span data-stu-id="c7515-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="c7515-163">节</span><span class="sxs-lookup"><span data-stu-id="c7515-163">Section</span></span>|<span data-ttu-id="c7515-164">值</span><span class="sxs-lookup"><span data-stu-id="c7515-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-165">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-166">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-166">**Key**</span></span> | <span data-ttu-id="c7515-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="c7515-167">HowToCheck</span></span> |
| <span data-ttu-id="c7515-168">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-168">**Data type**</span></span> | <span data-ttu-id="c7515-169">String</span><span class="sxs-lookup"><span data-stu-id="c7515-169">String</span></span> |
| <span data-ttu-id="c7515-170">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7515-170">**Possible values**</span></span> | <span data-ttu-id="c7515-171">手动</span><span class="sxs-lookup"><span data-stu-id="c7515-171">Manual</span></span> <br/> <span data-ttu-id="c7515-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="c7515-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="c7515-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="c7515-173">AutomaticDownload</span></span> |
| <span data-ttu-id="c7515-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c7515-174">**Comment**</span></span> |  <span data-ttu-id="c7515-175">请注意，如果可能，AutomaticDownload 将执行下载并静默安装。</span><span class="sxs-lookup"><span data-stu-id="c7515-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="c7515-176">更改"检查更新"按钮是否已启用</span><span class="sxs-lookup"><span data-stu-id="c7515-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="c7515-177">更改本地用户是否可以单击 Microsoft AutoUpdate 用户界面中的"检查更新"选项。</span><span class="sxs-lookup"><span data-stu-id="c7515-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="c7515-178">节</span><span class="sxs-lookup"><span data-stu-id="c7515-178">Section</span></span>|<span data-ttu-id="c7515-179">值</span><span class="sxs-lookup"><span data-stu-id="c7515-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-180">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-181">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-181">**Key**</span></span> | <span data-ttu-id="c7515-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="c7515-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="c7515-183">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-183">**Data type**</span></span> | <span data-ttu-id="c7515-184">Boolean</span><span class="sxs-lookup"><span data-stu-id="c7515-184">Boolean</span></span> |
| <span data-ttu-id="c7515-185">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7515-185">**Possible values**</span></span> | <span data-ttu-id="c7515-186">为 (默认值) </span><span class="sxs-lookup"><span data-stu-id="c7515-186">True (default)</span></span> <br/> <span data-ttu-id="c7515-187">False</span><span class="sxs-lookup"><span data-stu-id="c7515-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="c7515-188">禁用预览体验成员复选框</span><span class="sxs-lookup"><span data-stu-id="c7515-188">Disable Insider checkbox</span></span>

<span data-ttu-id="c7515-189">设置为 true 将"加入 Office预览体验计划..."。复选框不可用/灰度为用户。</span><span class="sxs-lookup"><span data-stu-id="c7515-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="c7515-190">节</span><span class="sxs-lookup"><span data-stu-id="c7515-190">Section</span></span>|<span data-ttu-id="c7515-191">值</span><span class="sxs-lookup"><span data-stu-id="c7515-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-192">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-193">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-193">**Key**</span></span> | <span data-ttu-id="c7515-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="c7515-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="c7515-195">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-195">**Data type**</span></span> | <span data-ttu-id="c7515-196">Boolean</span><span class="sxs-lookup"><span data-stu-id="c7515-196">Boolean</span></span> |
| <span data-ttu-id="c7515-197">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7515-197">**Possible values**</span></span> | <span data-ttu-id="c7515-198">False (默认值) </span><span class="sxs-lookup"><span data-stu-id="c7515-198">False (default)</span></span> <br/> <span data-ttu-id="c7515-199">True</span><span class="sxs-lookup"><span data-stu-id="c7515-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="c7515-200">限制从 MAU 发送的遥测</span><span class="sxs-lookup"><span data-stu-id="c7515-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="c7515-201">设置为 false 可发送最小检测信号数据、无应用程序使用情况和无环境详细信息。</span><span class="sxs-lookup"><span data-stu-id="c7515-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="c7515-202">节</span><span class="sxs-lookup"><span data-stu-id="c7515-202">Section</span></span>|<span data-ttu-id="c7515-203">值</span><span class="sxs-lookup"><span data-stu-id="c7515-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c7515-204">**域**</span><span class="sxs-lookup"><span data-stu-id="c7515-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="c7515-205">**键**</span><span class="sxs-lookup"><span data-stu-id="c7515-205">**Key**</span></span> | <span data-ttu-id="c7515-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="c7515-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="c7515-207">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c7515-207">**Data type**</span></span> | <span data-ttu-id="c7515-208">Boolean</span><span class="sxs-lookup"><span data-stu-id="c7515-208">Boolean</span></span> |
| <span data-ttu-id="c7515-209">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c7515-209">**Possible values**</span></span> | <span data-ttu-id="c7515-210">为 (默认值) </span><span class="sxs-lookup"><span data-stu-id="c7515-210">True (default)</span></span> <br/> <span data-ttu-id="c7515-211">False</span><span class="sxs-lookup"><span data-stu-id="c7515-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="c7515-212">配置文件示例</span><span class="sxs-lookup"><span data-stu-id="c7515-212">Example configuration profile</span></span>

<span data-ttu-id="c7515-213">以下配置文件用于：</span><span class="sxs-lookup"><span data-stu-id="c7515-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="c7515-214">将设备放在生产渠道中</span><span class="sxs-lookup"><span data-stu-id="c7515-214">Place the device in the Production channel</span></span>
- <span data-ttu-id="c7515-215">自动下载和安装更新</span><span class="sxs-lookup"><span data-stu-id="c7515-215">Automatically download and install updates</span></span>
- <span data-ttu-id="c7515-216">在用户界面中启用"检查更新"按钮</span><span class="sxs-lookup"><span data-stu-id="c7515-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="c7515-217">允许设备上的用户注册预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="c7515-217">Allow users on the device to enroll into the Insider channels</span></span>


>[!WARNING]
><span data-ttu-id="c7515-218">以下配置是一个示例配置，如果不适当审阅设置和定制配置，则不应在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="c7515-218">The below configuration is an example configuration and should not be used in production without proper review of settings and tailor of configurations.</span></span>

>[!TIP]
><span data-ttu-id="c7515-219">为了预览新功能并提供早期反馈，建议将企业中某些设备配置为 `Beta` 或 `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="c7515-219">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

### <a name="jamf"></a><span data-ttu-id="c7515-220">JAMF</span><span class="sxs-lookup"><span data-stu-id="c7515-220">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="c7515-221">Intune</span><span class="sxs-lookup"><span data-stu-id="c7515-221">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="c7515-222">若要配置 MAU，可以从企业使用的管理工具部署此配置文件：</span><span class="sxs-lookup"><span data-stu-id="c7515-222">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="c7515-223">从 JAMF 中，上传此配置文件，将首选项域设置为 *com.microsoft.autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="c7515-223">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="c7515-224">从 Intune 中，上载此配置文件，将自定义配置文件名称设置为 *com.microsoft.autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="c7515-224">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="c7515-225">资源</span><span class="sxs-lookup"><span data-stu-id="c7515-225">Resources</span></span>

- [<span data-ttu-id="c7515-226">msupdate 参考</span><span class="sxs-lookup"><span data-stu-id="c7515-226">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
