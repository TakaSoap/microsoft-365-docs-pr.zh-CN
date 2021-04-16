---
title: 部署适用于 Mac 的 Microsoft Defender for Endpoint 的更新
description: 控制企业环境中适用于 Mac 的 Microsoft Defender for Endpoint 的更新。
keywords: microsoft， defender， atp， mac， 更新， 部署
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
ms.openlocfilehash: 9d373594771efe4eb647c007db3a26efe83e330e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860311"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1ee2d-104">在 macOS 上部署 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="1ee2d-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1ee2d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-105">**Applies to:**</span></span>

- [<span data-ttu-id="1ee2d-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ee2d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="1ee2d-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ee2d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ee2d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ee2d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1ee2d-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1ee2d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1ee2d-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1ee2d-111">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="1ee2d-112">若要更新 macOS 上的 Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="1ee2d-113">默认情况下，MAU 每天自动检查更新，但你可以将更新更改为每周、每月或手动。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![MAU 屏幕截图](images/MDATP-34-MAU.png)

<span data-ttu-id="1ee2d-115">如果决定使用软件分发工具部署更新，应配置 MAU 以手动检查软件更新。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="1ee2d-116">你可以部署首选项，以配置 MAU 检查组织中 Mac 的更新方式和时间。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="1ee2d-117">使用 msupdate</span><span class="sxs-lookup"><span data-stu-id="1ee2d-117">Use msupdate</span></span>

<span data-ttu-id="1ee2d-118">MAU 包括一个称为 *msupdate* 的命令行工具，该工具专为 IT 管理员设计，以便他们可以更精确地控制何时应用更新。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="1ee2d-119">有关如何使用此工具的说明，请参阅 Update Office for Mac [by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="1ee2d-120">在 MAU 中，macOS 上的 Microsoft Defender for Endpoint 的应用程序标识符是 *WDAV00*。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="1ee2d-121">若要在 macOS 上下载并安装 Microsoft Defender for Endpoint 的最新更新，请从"终端"窗口执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1ee2d-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="1ee2d-122">设置 Microsoft AutoUpdate 的首选项</span><span class="sxs-lookup"><span data-stu-id="1ee2d-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="1ee2d-123">本节介绍可用于配置 MAU 的最常见首选项。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="1ee2d-124">可以通过企业使用的管理控制台将这些设置部署为配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="1ee2d-125">以下各节显示了配置文件的示例。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="1ee2d-126">设置频道名称</span><span class="sxs-lookup"><span data-stu-id="1ee2d-126">Set the channel name</span></span>

<span data-ttu-id="1ee2d-127">通道确定通过 MAU 提供的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="1ee2d-128">中的设备可以在 和 中的设备 `Beta` 之前试用 `Preview` 新功能 `Current` 。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="1ee2d-129">`Current`渠道包含最稳定的产品版本。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1ee2d-130">在 Microsoft AutoUpdate 版本 4.29 之前，频道具有不同的名称：</span><span class="sxs-lookup"><span data-stu-id="1ee2d-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="1ee2d-131">`Beta` 被命名为 `InsiderFast` (Insider Fast) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="1ee2d-132">`Preview` 被命名为 `External` (Insider Slow) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="1ee2d-133">`Current` 已命名 `Production`</span><span class="sxs-lookup"><span data-stu-id="1ee2d-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="1ee2d-134">为了预览新功能并提供早期反馈，建议将企业中某些设备配置为 `Beta` 或 `Preview` 。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="1ee2d-135">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-135">Section</span></span>|<span data-ttu-id="1ee2d-136">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-137">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-138">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-138">**Key**</span></span> | <span data-ttu-id="1ee2d-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="1ee2d-139">ChannelName</span></span> |
| <span data-ttu-id="1ee2d-140">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-140">**Data type**</span></span> | <span data-ttu-id="1ee2d-141">String</span><span class="sxs-lookup"><span data-stu-id="1ee2d-141">String</span></span> |
| <span data-ttu-id="1ee2d-142">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-142">**Possible values**</span></span> | <span data-ttu-id="1ee2d-143">Beta</span><span class="sxs-lookup"><span data-stu-id="1ee2d-143">Beta</span></span> <br/> <span data-ttu-id="1ee2d-144">预览</span><span class="sxs-lookup"><span data-stu-id="1ee2d-144">Preview</span></span> <br/> <span data-ttu-id="1ee2d-145">Current</span><span class="sxs-lookup"><span data-stu-id="1ee2d-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="1ee2d-146">此设置更改通过 Microsoft AutoUpdate 更新的所有应用程序的通道。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="1ee2d-147">若要仅为 macOS 上的 Microsoft Defender for Endpoint 更改通道，请用所需通道替换后执行 `[channel-name]` 以下命令：</span><span class="sxs-lookup"><span data-stu-id="1ee2d-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="1ee2d-148">设置更新检查频率</span><span class="sxs-lookup"><span data-stu-id="1ee2d-148">Set update check frequency</span></span>

<span data-ttu-id="1ee2d-149">更改 MAU 搜索更新频繁。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="1ee2d-150">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-150">Section</span></span>|<span data-ttu-id="1ee2d-151">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-152">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-153">**Key**</span></span> | <span data-ttu-id="1ee2d-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="1ee2d-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="1ee2d-155">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-155">**Data type**</span></span> | <span data-ttu-id="1ee2d-156">整数</span><span class="sxs-lookup"><span data-stu-id="1ee2d-156">Integer</span></span> |
| <span data-ttu-id="1ee2d-157">**默认值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-157">**Default value**</span></span> | <span data-ttu-id="1ee2d-158">720 (分钟) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-158">720 (minutes)</span></span> |
| <span data-ttu-id="1ee2d-159">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-159">**Comment**</span></span> | <span data-ttu-id="1ee2d-160">此值以分钟数设置。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="1ee2d-161">更改 MAU 与更新的交互方式</span><span class="sxs-lookup"><span data-stu-id="1ee2d-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="1ee2d-162">更改 MAU 搜索更新时如何。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="1ee2d-163">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-163">Section</span></span>|<span data-ttu-id="1ee2d-164">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-165">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-166">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-166">**Key**</span></span> | <span data-ttu-id="1ee2d-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="1ee2d-167">HowToCheck</span></span> |
| <span data-ttu-id="1ee2d-168">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-168">**Data type**</span></span> | <span data-ttu-id="1ee2d-169">String</span><span class="sxs-lookup"><span data-stu-id="1ee2d-169">String</span></span> |
| <span data-ttu-id="1ee2d-170">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-170">**Possible values**</span></span> | <span data-ttu-id="1ee2d-171">手动</span><span class="sxs-lookup"><span data-stu-id="1ee2d-171">Manual</span></span> <br/> <span data-ttu-id="1ee2d-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="1ee2d-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="1ee2d-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="1ee2d-173">AutomaticDownload</span></span> |
| <span data-ttu-id="1ee2d-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-174">**Comment**</span></span> |  <span data-ttu-id="1ee2d-175">请注意，如果可能，AutomaticDownload 将执行下载并静默安装。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="1ee2d-176">更改"检查更新"按钮是否已启用</span><span class="sxs-lookup"><span data-stu-id="1ee2d-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="1ee2d-177">更改本地用户是否可以单击 Microsoft AutoUpdate 用户界面中的"检查更新"选项。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="1ee2d-178">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-178">Section</span></span>|<span data-ttu-id="1ee2d-179">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-180">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-181">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-181">**Key**</span></span> | <span data-ttu-id="1ee2d-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="1ee2d-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="1ee2d-183">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-183">**Data type**</span></span> | <span data-ttu-id="1ee2d-184">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ee2d-184">Boolean</span></span> |
| <span data-ttu-id="1ee2d-185">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-185">**Possible values**</span></span> | <span data-ttu-id="1ee2d-186">为 (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-186">True (default)</span></span> <br/> <span data-ttu-id="1ee2d-187">False</span><span class="sxs-lookup"><span data-stu-id="1ee2d-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="1ee2d-188">禁用预览体验成员复选框</span><span class="sxs-lookup"><span data-stu-id="1ee2d-188">Disable Insider checkbox</span></span>

<span data-ttu-id="1ee2d-189">设置为 true 可进行"加入 Office 预览体验计划..."。复选框不可用/灰度为用户。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="1ee2d-190">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-190">Section</span></span>|<span data-ttu-id="1ee2d-191">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-192">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-193">**Key**</span></span> | <span data-ttu-id="1ee2d-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="1ee2d-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="1ee2d-195">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-195">**Data type**</span></span> | <span data-ttu-id="1ee2d-196">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ee2d-196">Boolean</span></span> |
| <span data-ttu-id="1ee2d-197">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-197">**Possible values**</span></span> | <span data-ttu-id="1ee2d-198">False (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-198">False (default)</span></span> <br/> <span data-ttu-id="1ee2d-199">True</span><span class="sxs-lookup"><span data-stu-id="1ee2d-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="1ee2d-200">限制从 MAU 发送的遥测</span><span class="sxs-lookup"><span data-stu-id="1ee2d-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="1ee2d-201">设置为 false 可发送最小检测信号数据、无应用程序使用情况和无环境详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="1ee2d-202">节</span><span class="sxs-lookup"><span data-stu-id="1ee2d-202">Section</span></span>|<span data-ttu-id="1ee2d-203">值</span><span class="sxs-lookup"><span data-stu-id="1ee2d-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="1ee2d-204">**域**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="1ee2d-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-205">**Key**</span></span> | <span data-ttu-id="1ee2d-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="1ee2d-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="1ee2d-207">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-207">**Data type**</span></span> | <span data-ttu-id="1ee2d-208">Boolean</span><span class="sxs-lookup"><span data-stu-id="1ee2d-208">Boolean</span></span> |
| <span data-ttu-id="1ee2d-209">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1ee2d-209">**Possible values**</span></span> | <span data-ttu-id="1ee2d-210">为 (默认值) </span><span class="sxs-lookup"><span data-stu-id="1ee2d-210">True (default)</span></span> <br/> <span data-ttu-id="1ee2d-211">False</span><span class="sxs-lookup"><span data-stu-id="1ee2d-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="1ee2d-212">配置文件示例</span><span class="sxs-lookup"><span data-stu-id="1ee2d-212">Example configuration profile</span></span>

<span data-ttu-id="1ee2d-213">以下配置文件用于：</span><span class="sxs-lookup"><span data-stu-id="1ee2d-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="1ee2d-214">将设备放在 Beta 渠道中</span><span class="sxs-lookup"><span data-stu-id="1ee2d-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="1ee2d-215">自动下载和安装更新</span><span class="sxs-lookup"><span data-stu-id="1ee2d-215">Automatically download and install updates</span></span>
- <span data-ttu-id="1ee2d-216">在用户界面中启用"检查更新"按钮</span><span class="sxs-lookup"><span data-stu-id="1ee2d-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="1ee2d-217">允许设备上的用户注册预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="1ee2d-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="1ee2d-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="1ee2d-218">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
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

### <a name="intune"></a><span data-ttu-id="1ee2d-219">Intune</span><span class="sxs-lookup"><span data-stu-id="1ee2d-219">Intune</span></span>

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
            <string>Beta</string>
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

<span data-ttu-id="1ee2d-220">若要配置 MAU，可以从企业使用的管理工具部署此配置文件：</span><span class="sxs-lookup"><span data-stu-id="1ee2d-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="1ee2d-221">从 JAMF 中，上传此配置文件，将首选项域设置为 *com.microsoft.autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="1ee2d-222">从 Intune 中，上载此配置文件，将自定义配置文件名称设置为 *com.microsoft.autoupdate2*。</span><span class="sxs-lookup"><span data-stu-id="1ee2d-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="1ee2d-223">资源</span><span class="sxs-lookup"><span data-stu-id="1ee2d-223">Resources</span></span>

- [<span data-ttu-id="1ee2d-224">msupdate 参考</span><span class="sxs-lookup"><span data-stu-id="1ee2d-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
