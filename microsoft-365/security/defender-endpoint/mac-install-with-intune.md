---
title: 适用于 Mac 上的 Microsoft Defender for Endpoint 的基于 Intune 的部署
description: 使用 Microsoft Intune 在 Mac 上安装 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: 077411e5af5825efcf81d19ce8cb72ef850ae17b
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054316"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d7fcb-104">macOS 上的 Microsoft Defender for Endpoint 的基于 Intune 的部署</span><span class="sxs-lookup"><span data-stu-id="d7fcb-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7fcb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-105">**Applies to:**</span></span>

- [<span data-ttu-id="d7fcb-106">macOS 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7fcb-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="d7fcb-107">本主题介绍如何通过 Intune 在 macOS 上部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="d7fcb-108">要成功部署，需要完成以下所有步骤：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="d7fcb-109">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="d7fcb-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="d7fcb-110">客户端设备设置</span><span class="sxs-lookup"><span data-stu-id="d7fcb-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="d7fcb-111">批准系统扩展</span><span class="sxs-lookup"><span data-stu-id="d7fcb-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="d7fcb-112">创建系统配置文件</span><span class="sxs-lookup"><span data-stu-id="d7fcb-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="d7fcb-113">发布应用程序</span><span class="sxs-lookup"><span data-stu-id="d7fcb-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="d7fcb-114">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="d7fcb-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="d7fcb-115">在开始使用之前，请参阅 [macOS](microsoft-defender-endpoint-mac.md) 上的 Microsoft Defender for Endpoint 主页，了解当前软件版本的先决条件和系统要求说明。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="d7fcb-116">概述</span><span class="sxs-lookup"><span data-stu-id="d7fcb-116">Overview</span></span>

<span data-ttu-id="d7fcb-117">下表总结了通过 Intune 部署和管理 Mac 上的 Microsoft Defender for Endpoint 需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="d7fcb-118">下面提供了更详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="d7fcb-119">步骤</span><span class="sxs-lookup"><span data-stu-id="d7fcb-119">Step</span></span> | <span data-ttu-id="d7fcb-120">示例文件名</span><span class="sxs-lookup"><span data-stu-id="d7fcb-120">Sample file names</span></span> | <span data-ttu-id="d7fcb-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="d7fcb-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="d7fcb-122">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="d7fcb-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="d7fcb-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="d7fcb-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="d7fcb-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="d7fcb-125">批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="d7fcb-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="d7fcb-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="d7fcb-127">不适用</span><span class="sxs-lookup"><span data-stu-id="d7fcb-127">N/A</span></span> |
| [<span data-ttu-id="d7fcb-128">批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="d7fcb-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="d7fcb-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="d7fcb-130">不适用</span><span class="sxs-lookup"><span data-stu-id="d7fcb-130">N/A</span></span> |
| [<span data-ttu-id="d7fcb-131">授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="d7fcb-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="d7fcb-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="d7fcb-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="d7fcb-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="d7fcb-134">网络扩展策略</span><span class="sxs-lookup"><span data-stu-id="d7fcb-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="d7fcb-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="d7fcb-136">不适用</span><span class="sxs-lookup"><span data-stu-id="d7fcb-136">N/A</span></span> |
| [<span data-ttu-id="d7fcb-137">配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="d7fcb-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="d7fcb-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="d7fcb-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="d7fcb-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="d7fcb-140">Microsoft Defender for Endpoint 配置设置</span><span class="sxs-lookup"><span data-stu-id="d7fcb-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="d7fcb-141">**注意：** 如果计划运行适用于 macOS 的第三方 AV，请设置为 `passiveMode` `true` 。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="d7fcb-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="d7fcb-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="d7fcb-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="d7fcb-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="d7fcb-144">配置 Microsoft Defender for Endpoint 和 MS AutoUpdate (MAU) 通知</span><span class="sxs-lookup"><span data-stu-id="d7fcb-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="d7fcb-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="d7fcb-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="d7fcb-146">com.microsoft.autoupdate2 或 com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="d7fcb-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="d7fcb-147">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="d7fcb-147">Download the onboarding package</span></span>

<span data-ttu-id="d7fcb-148">从以下网站下载Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="d7fcb-149">In Microsoft Defender 安全中心， go to **设置**  >  **Device Management**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="d7fcb-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="d7fcb-150">将操作系统设置为 **macOS，** 将部署方法设置为 **移动设备管理 /Microsoft Intune**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![载入设置屏幕截图](images/atp-mac-install.png)

3. <span data-ttu-id="d7fcb-152">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="d7fcb-153">将其另 _存WindowsDefenderATPOnboardingPackage.zip_ 同一目录。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="d7fcb-154">提取文件.zip内容：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-154">Extract the contents of the .zip file:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="d7fcb-155">创建系统配置文件</span><span class="sxs-lookup"><span data-stu-id="d7fcb-155">Create System Configuration profiles</span></span>

<span data-ttu-id="d7fcb-156">下一步是创建 Microsoft Defender for Endpoint 所需的系统配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="d7fcb-157">在管理 [Microsoft Endpoint Manager中，](https://endpoint.microsoft.com/)打开 **"设备**  >  **配置配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="d7fcb-158">载入 blob</span><span class="sxs-lookup"><span data-stu-id="d7fcb-158">Onboarding blob</span></span>

<span data-ttu-id="d7fcb-159">此配置文件包含 Microsoft Defender for Endpoint 的许可证信息，如果没有它，它将报告其未获得许可。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="d7fcb-160">选择 **"配置文件"下的\*\*\*\*"创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="d7fcb-161">选择 **平台** = **macOS** **，配置文件类型** = **模板**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="d7fcb-162">**模板名称** =**自定义**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="d7fcb-163">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-164">![自定义配置文件创建](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="d7fcb-165">为配置文件选择一个名称，例如"适用于 macOS 的 MDE 载入"。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-165">Choose a name for the profile, e.g., "MDE onboarding for macOS".</span></span> <span data-ttu-id="d7fcb-166">点击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-167">![自定义配置文件 - 名称](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="d7fcb-168">为配置文件名称选择一个名称，例如"适用于 macOS 的 MDE 载入"。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-168">Choose a name for the configuration profile name, e.g., "MDE onboarding for macOS".</span></span>
1. <span data-ttu-id="d7fcb-169">选择"intune/WindowsDefenderATPOnboarding.xml从上述载入程序包中提取的配置文件文件"作为配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-170">![从文件导入自定义配置文件的配置](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="d7fcb-171">点击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-171">Click **Next**.</span></span>
1. <span data-ttu-id="d7fcb-172">在"分配"选项卡上 **分配** 设备。单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-173">![自定义配置文件 - 分配](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="d7fcb-174">查看 和 **创建**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-174">Review and **Create**.</span></span>
1. <span data-ttu-id="d7fcb-175">打开 **设备**  >  **配置文件 ，** 你可以在那里查看你创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-176">![自定义配置文件 - 完成](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="d7fcb-177">批准系统扩展</span><span class="sxs-lookup"><span data-stu-id="d7fcb-177">Approve System Extensions</span></span>

<span data-ttu-id="d7fcb-178">MacOS 10.15 或更高版本 (macOS 10.15) 此配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="d7fcb-179">它将在较旧的 macOS 上被忽略。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="d7fcb-180">选择 **"配置文件"下的\*\*\*\*"创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="d7fcb-181">选择 **平台** = **macOS** **，配置文件类型** = **模板**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="d7fcb-182">**模板名称** =**扩展**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="d7fcb-183">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-183">Click **Create**.</span></span>
1. <span data-ttu-id="d7fcb-184">在 **"基本"** 选项卡中，为此新配置文件命名。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="d7fcb-185">在" **配置设置"** 选项卡中，展开" **系统扩展"，** 在"允许的系统扩展"部分 **添加以下** 条目：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="d7fcb-186">捆绑包标识符</span><span class="sxs-lookup"><span data-stu-id="d7fcb-186">Bundle identifier</span></span>         | <span data-ttu-id="d7fcb-187">团队标识符</span><span class="sxs-lookup"><span data-stu-id="d7fcb-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="d7fcb-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="d7fcb-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="d7fcb-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="d7fcb-189">UBF8T346G9</span></span>
    <span data-ttu-id="d7fcb-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="d7fcb-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="d7fcb-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="d7fcb-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-192">![系统扩展设置](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="d7fcb-193">在"**分配"** 选项卡中，将此配置文件分配给"所有 **&所有用户"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="d7fcb-194">查看并创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="d7fcb-195">内核扩展</span><span class="sxs-lookup"><span data-stu-id="d7fcb-195">Kernel Extensions</span></span>

<span data-ttu-id="d7fcb-196">macOS 10.15 和加泰罗尼亚语或 (版) 此配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="d7fcb-197">它将在较新的 macOS 上被忽略。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="d7fcb-198">Apple 芯片 (M1) 设备不支持 KEXT。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="d7fcb-199">在这些设备上安装包含 KEXT 策略的配置文件将失败。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="d7fcb-200">选择 **"配置文件"下的\*\*\*\*"创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="d7fcb-201">选择 **平台** = **macOS** **，配置文件类型** = **模板**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="d7fcb-202">**模板名称** =**扩展**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="d7fcb-203">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-203">Click **Create**.</span></span>
1. <span data-ttu-id="d7fcb-204">在 **"基本"** 选项卡中，为此新配置文件命名。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="d7fcb-205">在"**配置设置"** 选项卡中，展开 **"内核扩展"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="d7fcb-206">将 **团队标识符设置为** **UBF8T346G9，** 然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-207">![内核扩展设置](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="d7fcb-208">在"**分配"** 选项卡中，将此配置文件分配给"所有 **&所有用户"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="d7fcb-209">查看并创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="d7fcb-210">完全磁盘访问</span><span class="sxs-lookup"><span data-stu-id="d7fcb-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="d7fcb-211">macOS 10.15 (Catalina) 新增了安全和隐私增强功能。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="d7fcb-212">从此版本开始，默认情况下，应用程序无法访问磁盘上的某些位置 (如文档、下载、桌面等) 未经明确同意。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="d7fcb-213">如果没有此同意，Microsoft Defender for Endpoint 将无法完全保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="d7fcb-214">此配置文件授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d7fcb-215">如果你之前通过 Intune 配置了适用于 Endpoint 的 Microsoft Defender，我们建议你通过此配置文件更新部署。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="d7fcb-216">从我们的 GitHub [存储库中下载](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles) [**fulldisk.mobileconfig。**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="d7fcb-217">按照上面有关 [载入 blob](#onboarding-blob) 的说明操作，使用"MDE 完全磁盘访问"作为配置文件名称，将已下载 **的 fulldisk.mobileconfig** 用作配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDE Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="d7fcb-218">网络筛选器</span><span class="sxs-lookup"><span data-stu-id="d7fcb-218">Network Filter</span></span>

<span data-ttu-id="d7fcb-219">作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心 门户。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="d7fcb-220">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="d7fcb-221">从我们的 GitHub 存储库中下载 [**netfilter.mobileconfig。**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) [](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="d7fcb-222">按照上面有关 [载入 blob](#onboarding-blob) 的说明操作，使用"MDE 网络筛选器"作为配置文件名称，将下载的 **netfilter.mobileconfig** 用作配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDE Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="d7fcb-223">通知</span><span class="sxs-lookup"><span data-stu-id="d7fcb-223">Notifications</span></span>

<span data-ttu-id="d7fcb-224">此配置文件用于允许 macOS 和 Microsoft 自动更新上的 Microsoft Defender for Endpoint 在 macOS 10.15 或加泰罗尼亚语或更高版本 (UI) 通知。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="d7fcb-225">从我们的 GitHub[存储库中下载 notif.mobileconfig。](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles) [](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="d7fcb-226">按照上面有关 [载入 blob](#onboarding-blob) 的说明操作，使用"MDE 通知"作为配置文件名称，并下载 **notif.mobileconfig** 作为配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDE Notifications" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="d7fcb-227">查看状态</span><span class="sxs-lookup"><span data-stu-id="d7fcb-227">View Status</span></span>

<span data-ttu-id="d7fcb-228">将 Intune 更改传播到已注册的设备后，你可以看到它们列在监视  >  **设备状态下**：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7fcb-229">![监视器中的设备状态视图](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="d7fcb-230">发布应用程序</span><span class="sxs-lookup"><span data-stu-id="d7fcb-230">Publish application</span></span>

<span data-ttu-id="d7fcb-231">此步骤支持将 Microsoft Defender for Endpoint 部署到注册的计算机。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="d7fcb-232">在管理 [Microsoft Endpoint Manager中，打开](https://endpoint.microsoft.com/)**应用。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-233">![准备创建应用程序](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="d7fcb-234">选择"按平台> macOS >添加"。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="d7fcb-235">选择 **"应用类型** = **""macOS"，** 单击"**选择"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-236">![指定应用程序类型](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="d7fcb-237">保留默认值，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-238">![应用程序属性](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="d7fcb-239">添加分配，单击下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-240">![Intune 作业信息屏幕截图](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="d7fcb-241">查看 和 **创建**。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-241">Review and **Create**.</span></span>
1. <span data-ttu-id="d7fcb-242">你可以按 **平台**  >    >  **macOS** 访问应用，在所有应用程序列表中查看它。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-243">![应用程序列表](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="d7fcb-244"> (可以在 [Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)页面上找到 Defender 部署 .) </span><span class="sxs-lookup"><span data-stu-id="d7fcb-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="d7fcb-245">你必须创建所有必需的配置文件，并推送到所有计算机，如上所述。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="d7fcb-246">客户端设备设置</span><span class="sxs-lookup"><span data-stu-id="d7fcb-246">Client device setup</span></span>

<span data-ttu-id="d7fcb-247">除了标准安装之外，你无需为 Mac 设备公司门户[预配](/intune-user-help/enroll-your-device-in-intune-macos-cp)。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="d7fcb-248">确认设备管理。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-249">![确认设备管理屏幕截图](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="d7fcb-250">选择 **"打开系统首选项"，** 在列表中找到"**管理配置文件**"，然后选择"批准 **..."。** 你的管理配置文件将显示为 **"已验证"：**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![管理配置文件屏幕截图](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="d7fcb-252">选择 **"继续** "并完成注册。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="d7fcb-253">你现在可以注册更多设备。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-253">You may now enroll more devices.</span></span> <span data-ttu-id="d7fcb-254">完成系统配置和应用程序包的预配后，还可以稍后注册它们。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="d7fcb-255">在 Intune 中，打开 **"**  >  **管理设备**  >  **""所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="d7fcb-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="d7fcb-256">你可以在此处查看列出的设备：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d7fcb-257">![添加设备屏幕截图](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="d7fcb-258">验证客户端设备状态</span><span class="sxs-lookup"><span data-stu-id="d7fcb-258">Verify client device state</span></span>

1. <span data-ttu-id="d7fcb-259">将配置文件部署到设备后，在 Mac 设备上打开系统  >  首选项配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-260">![系统首选项屏幕截图](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![系统首选项配置文件屏幕截图](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="d7fcb-262">确认存在并安装了以下配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="d7fcb-263">管理 **配置文件** 应为 Intune 系统配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="d7fcb-264">_Wdav-config_ 和 _wdav-kext_ 是在 Intune 中添加的系统配置文件：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![配置文件屏幕截图](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="d7fcb-266">你还应在右上角看到"适用于终结点的 Microsoft Defender"图标：</span><span class="sxs-lookup"><span data-stu-id="d7fcb-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d7fcb-267">![状态栏中的 Microsoft Defender for Endpoint 图标屏幕截图](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="d7fcb-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d7fcb-268">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d7fcb-268">Troubleshooting</span></span>

<span data-ttu-id="d7fcb-269">问题：未找到许可证。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-269">Issue: No license found.</span></span>

<span data-ttu-id="d7fcb-270">解决方案：按照上述步骤使用 WindowsDefenderATPOnboarding.xml。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="d7fcb-271">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="d7fcb-271">Logging installation issues</span></span>

<span data-ttu-id="d7fcb-272">若要详细了解如何在发生错误时查找安装程序创建的自动生成的日志，请参阅记录 [安装问题](mac-resources.md#logging-installation-issues)。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="d7fcb-273">卸载</span><span class="sxs-lookup"><span data-stu-id="d7fcb-273">Uninstallation</span></span>

<span data-ttu-id="d7fcb-274">请参阅 [卸载](mac-resources.md#uninstalling) ，详细了解如何从客户端设备中删除 macOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d7fcb-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
