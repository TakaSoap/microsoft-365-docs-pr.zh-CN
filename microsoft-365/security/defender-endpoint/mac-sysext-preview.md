---
title: '适用于 Mac 的 Microsoft Defender ATP - 系统扩展 (预览) '
description: 本文包含有关尝试 Microsoft Defender ATP for Mac 的系统扩展功能的说明。 此功能目前处于公共预览阶段。
keywords: microsoft， defender， atp， mac， 内核， 系统， 扩展， 加泰罗尼亚语
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 6becdd995d70c0b8193e8df097c9256dc38c72a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185893"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="4da19-105">适用于 Mac 的 Microsoft Defender for Endpoint - 系统扩展公共预览) </span><span class="sxs-lookup"><span data-stu-id="4da19-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="4da19-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4da19-106">**Applies to:**</span></span>
- [<span data-ttu-id="4da19-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4da19-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4da19-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4da19-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4da19-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4da19-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4da19-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4da19-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4da19-111">为了与 macOS 演变保持一致，我们正在准备利用系统扩展而非内核扩展的 Defender for Endpoint for Mac 更新。</span><span class="sxs-lookup"><span data-stu-id="4da19-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="4da19-112">此更新仅适用于 macOS 10 (10.15.4) macOS 的更高版本。</span><span class="sxs-lookup"><span data-stu-id="4da19-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="4da19-113">此功能目前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="4da19-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="4da19-114">本文介绍了如何在设备上启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4da19-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="4da19-115">可以在自己的设备上本地试用此功能，或者通过管理工具远程配置它。</span><span class="sxs-lookup"><span data-stu-id="4da19-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="4da19-116">这些步骤假定你已在设备上运行 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="4da19-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="4da19-117">有关详细信息，请参阅此[此页面](microsoft-defender-endpoint-mac.md)。</span><span class="sxs-lookup"><span data-stu-id="4da19-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="4da19-118">已知问题</span><span class="sxs-lookup"><span data-stu-id="4da19-118">Known issues</span></span>

- <span data-ttu-id="4da19-119">我们已收到网络扩展干扰 Apple SSO Kerberos 扩展的报告。</span><span class="sxs-lookup"><span data-stu-id="4da19-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="4da19-120">产品的当前版本仍安装内核扩展。</span><span class="sxs-lookup"><span data-stu-id="4da19-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="4da19-121">内核扩展仅用作回退机制，将在此功能达到公共预览版之前删除。</span><span class="sxs-lookup"><span data-stu-id="4da19-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="4da19-122">我们仍在开发在 macOS 11 Big Sur 上正确部署和功能的产品版本。</span><span class="sxs-lookup"><span data-stu-id="4da19-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="4da19-123">部署先决条件</span><span class="sxs-lookup"><span data-stu-id="4da19-123">Deployment prerequisites</span></span>

- <span data-ttu-id="4da19-124">最低 macOS 操作系统版本 **：10.15.4**</span><span class="sxs-lookup"><span data-stu-id="4da19-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="4da19-125">最低产品版本 **：101.03.73**</span><span class="sxs-lookup"><span data-stu-id="4da19-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="4da19-126">你的设备必须在预览体验 **成员快速更新频道中**。</span><span class="sxs-lookup"><span data-stu-id="4da19-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="4da19-127">可以使用以下命令检查更新频道：</span><span class="sxs-lookup"><span data-stu-id="4da19-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="4da19-128">如果你的设备尚未在预览体验成员快速更新频道中，请从终端执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="4da19-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="4da19-129">频道更新将在产品下次启动时生效 (安装下一个产品更新时，或设备在下次启动时) 。</span><span class="sxs-lookup"><span data-stu-id="4da19-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="4da19-130">或者，如果你使用 JAMF 或 Intune (托管) ，你可以远程配置更新通道。</span><span class="sxs-lookup"><span data-stu-id="4da19-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="4da19-131">有关详细信息，请参阅 [部署适用于 Mac 的 Microsoft Defender ATP 更新：设置频道名称](mac-updates.md#set-the-channel-name)。</span><span class="sxs-lookup"><span data-stu-id="4da19-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="4da19-132">部署步骤</span><span class="sxs-lookup"><span data-stu-id="4da19-132">Deployment steps</span></span>

<span data-ttu-id="4da19-133">请按照环境对应的部署步骤以及您尝试此功能的首选方法操作。</span><span class="sxs-lookup"><span data-stu-id="4da19-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="4da19-134">手动部署</span><span class="sxs-lookup"><span data-stu-id="4da19-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="4da19-135">批准系统扩展并启用网络扩展</span><span class="sxs-lookup"><span data-stu-id="4da19-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="4da19-136">满足所有部署先决条件后，重启设备以启动系统扩展审批和激活过程。</span><span class="sxs-lookup"><span data-stu-id="4da19-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="4da19-137">你将看到一系列批准 Defender for Endpoint 系统扩展的系统提示。</span><span class="sxs-lookup"><span data-stu-id="4da19-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="4da19-138">必须批准 **系列** 的所有提示，因为 macOS 需要明确批准 Defender for Mac 终结点在设备上安装的每个扩展。</span><span class="sxs-lookup"><span data-stu-id="4da19-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="4da19-139">对于每个审批，选择 **"打开安全首选项"，** 然后选择" **允许** "以允许系统扩展运行。</span><span class="sxs-lookup"><span data-stu-id="4da19-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4da19-140">必须在后续审批之间关闭并重新打开系统首选项  >  **&隐私** 窗口。</span><span class="sxs-lookup"><span data-stu-id="4da19-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="4da19-141">否则，macOS 将不会显示下一个审批。</span><span class="sxs-lookup"><span data-stu-id="4da19-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4da19-142">产品在返回到内核扩展之前有一分钟超时。</span><span class="sxs-lookup"><span data-stu-id="4da19-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="4da19-143">这可确保设备受到保护。</span><span class="sxs-lookup"><span data-stu-id="4da19-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="4da19-144">如果超过一分钟，请重新启动设备或使用 再次触发审批流来重新启动 `sudo killall -9 wdavdaemon` 守护程序。</span><span class="sxs-lookup"><span data-stu-id="4da19-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![系统扩展审批弹出窗口](images/mac-system-extension-approval.png)

   ![系统扩展审批窗口](images/mac-system-extension-pref.png)

1. <span data-ttu-id="4da19-147">批准系统扩展后，macOS 将提示批准以允许筛选网络流量。</span><span class="sxs-lookup"><span data-stu-id="4da19-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="4da19-148">单击"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="4da19-148">Click **Allow**.</span></span>

   ![网络扩展审批弹出窗口](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="4da19-150">授予对终结点安全系统扩展的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="4da19-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="4da19-151">打开"**系统首选项**  >  **安全&**  >  **隐私"** 选项卡，并授予 Microsoft  Defender 终结点安全扩展的"完全磁盘 **访问权限"。**</span><span class="sxs-lookup"><span data-stu-id="4da19-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![终结点安全系统扩展的完全磁盘访问](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="4da19-153">重新启动设备</span><span class="sxs-lookup"><span data-stu-id="4da19-153">Reboot your device</span></span>

<span data-ttu-id="4da19-154">为了使更改生效，必须重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="4da19-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="4da19-155">验证系统扩展是否正在运行</span><span class="sxs-lookup"><span data-stu-id="4da19-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="4da19-156">从终端运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4da19-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="4da19-157">终端 `endpoint_security_extension` 输出指示产品正在使用系统扩展功能。</span><span class="sxs-lookup"><span data-stu-id="4da19-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="4da19-158">托管部署</span><span class="sxs-lookup"><span data-stu-id="4da19-158">Managed deployment</span></span>

<span data-ttu-id="4da19-159">有关必须[为此新功能部署的新配置文件，请参阅 macOS Catalina 的新配置文件和较新版本的 macOS：JAMF。](mac-sysext-policies.md#jamf)</span><span class="sxs-lookup"><span data-stu-id="4da19-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="4da19-160">除了这些配置文件之外，请确保将目标设备配置为在预览体验成员快速更新频道中，如部署 [先决条件中所述](#deployment-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="4da19-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="4da19-161">在满足所有先决条件且已部署新配置文件的设备上，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4da19-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="4da19-162">如果此命令打印 `endpoint_security_extension` ，则产品正在使用系统扩展功能。</span><span class="sxs-lookup"><span data-stu-id="4da19-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="4da19-163">验证基本方案</span><span class="sxs-lookup"><span data-stu-id="4da19-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="4da19-164">测试欧洲计算机防病毒研究 (EICAR) 检测。</span><span class="sxs-lookup"><span data-stu-id="4da19-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="4da19-165">在终端窗口中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4da19-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="4da19-166">验证 EICAR 文件是否被隔离。</span><span class="sxs-lookup"><span data-stu-id="4da19-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="4da19-167">可以在用户界面中的"保护历史记录"页上，或通过使用以下命令从命令行验证文件的状态：</span><span class="sxs-lookup"><span data-stu-id="4da19-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="4da19-168">测试 EDR 和 DIY (终结点) 和响应。</span><span class="sxs-lookup"><span data-stu-id="4da19-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="4da19-169">在终端窗口中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4da19-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="4da19-170">验证在计算机页面上针对 EICAR 和 EDR DIY 方案在门户中弹出的两个警报。</span><span class="sxs-lookup"><span data-stu-id="4da19-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4da19-171">常见问题</span><span class="sxs-lookup"><span data-stu-id="4da19-171">Frequently asked questions</span></span>

- <span data-ttu-id="4da19-172">问：为什么运行时 `kernel_extension` 仍看到 `mdatp health --field real_time_protection_subsystem` ？</span><span class="sxs-lookup"><span data-stu-id="4da19-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="4da19-173">答：请重新参阅 [部署先决条件](#deployment-prerequisites) 部分，并仔细检查是否满足所有先决条件。</span><span class="sxs-lookup"><span data-stu-id="4da19-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="4da19-174">如果满足所有先决条件，请重启设备并再次检查。</span><span class="sxs-lookup"><span data-stu-id="4da19-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="4da19-175">问：macOS 11 Big Sur 何时受支持？</span><span class="sxs-lookup"><span data-stu-id="4da19-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="4da19-176">答：我们正在努力添加对 macOS 11 的支持。</span><span class="sxs-lookup"><span data-stu-id="4da19-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="4da19-177">我们将向"新增功能" [页面发布更多信息](mac-whatsnew.md) 。</span><span class="sxs-lookup"><span data-stu-id="4da19-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
