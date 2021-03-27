---
title: 适用于适用于 Mac 的 Microsoft Defender for Endpoint 的基于 Intune 的部署
description: 使用 Microsoft Intune 安装适用于 Mac 的 Microsoft Defender for Endpoint。
keywords: microsoft， defender， atp， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
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
ms.openlocfilehash: bd74f3a487de4febecb2086cb126c50b8432c342
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379543"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="76519-104">适用于适用于 Mac 的 Microsoft Defender for Endpoint 的基于 Intune 的部署</span><span class="sxs-lookup"><span data-stu-id="76519-104">Intune-based deployment for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> <span data-ttu-id="76519-105">本文档介绍在 macOS 设备上部署和配置 Microsoft Defender for Endpoint 的旧方法。</span><span class="sxs-lookup"><span data-stu-id="76519-105">This documentation explains the legacy method for deploying and configuring Microsoft Defender for Endpoint on macOS devices.</span></span> <span data-ttu-id="76519-106">本机体验现已在 MEM 控制台中提供。</span><span class="sxs-lookup"><span data-stu-id="76519-106">The native experience is now available in the MEM console.</span></span> <span data-ttu-id="76519-107">MEM 控制台中本机 UI 的发布为管理员提供了一种更简单的方式来配置和部署应用程序并将其发送到 macOS 设备。</span><span class="sxs-lookup"><span data-stu-id="76519-107">The release of the native UI in the MEM console provide admins with a much simpler way to configure and deploy the application and send it down to macOS devices.</span></span> <br> <br>
><span data-ttu-id="76519-108">博客文章 [MEM 简化了适用于 macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) 的 Microsoft Defender for Endpoint 的部署，介绍了新功能。</span><span class="sxs-lookup"><span data-stu-id="76519-108">The blog post [MEM simplifies deployment of Microsoft Defender for Endpoint for macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explains the new features.</span></span> <span data-ttu-id="76519-109">若要配置应用，请转到 [Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos)中适用于 Mac 的 Microsoft Defender for Endpoint 的设置。</span><span class="sxs-lookup"><span data-stu-id="76519-109">To configure the app, go to [Settings for Microsoft Defender for Endpoint for Mac in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span></span> <span data-ttu-id="76519-110">若要部署应用，请转到使用 [Microsoft Intune 将 Microsoft Defender for Endpoint](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)添加到 macOS 设备。</span><span class="sxs-lookup"><span data-stu-id="76519-110">To deploy the app, go to [Add Microsoft Defender for Endpoint to macOS devices using Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span></span>

<span data-ttu-id="76519-111">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="76519-111">**Applies to:**</span></span>

- [<span data-ttu-id="76519-112">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="76519-112">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="76519-113">本主题介绍如何通过 Intune 部署适用于 Mac 的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="76519-113">This topic describes how to deploy Microsoft Defender for Endpoint for Mac through Intune.</span></span> <span data-ttu-id="76519-114">要成功部署，需要完成以下所有步骤：</span><span class="sxs-lookup"><span data-stu-id="76519-114">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="76519-115">下载安装和载入程序包</span><span class="sxs-lookup"><span data-stu-id="76519-115">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
1. [<span data-ttu-id="76519-116">客户端设备设置</span><span class="sxs-lookup"><span data-stu-id="76519-116">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="76519-117">批准系统扩展</span><span class="sxs-lookup"><span data-stu-id="76519-117">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="76519-118">创建系统配置文件</span><span class="sxs-lookup"><span data-stu-id="76519-118">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="76519-119">发布应用程序</span><span class="sxs-lookup"><span data-stu-id="76519-119">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="76519-120">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="76519-120">Prerequisites and system requirements</span></span>

<span data-ttu-id="76519-121">在开始使用之前，请参阅 [主 Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) 页面，了解当前软件版本的先决条件和系统要求。</span><span class="sxs-lookup"><span data-stu-id="76519-121">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="76519-122">概述</span><span class="sxs-lookup"><span data-stu-id="76519-122">Overview</span></span>

<span data-ttu-id="76519-123">下表总结了通过 Intune 部署和管理适用于 Mac 的 Microsoft Defender for Endpoint 需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="76519-123">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint for Macs, via Intune.</span></span> <span data-ttu-id="76519-124">下面提供了更详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="76519-124">More detailed steps are available below.</span></span>

| <span data-ttu-id="76519-125">步骤</span><span class="sxs-lookup"><span data-stu-id="76519-125">Step</span></span> | <span data-ttu-id="76519-126">示例文件名</span><span class="sxs-lookup"><span data-stu-id="76519-126">Sample file names</span></span> | <span data-ttu-id="76519-127">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="76519-127">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="76519-128">下载安装和载入程序包</span><span class="sxs-lookup"><span data-stu-id="76519-128">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="76519-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="76519-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="76519-130">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="76519-130">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="76519-131">批准适用于终结点的 Microsoft Defender 的系统扩展</span><span class="sxs-lookup"><span data-stu-id="76519-131">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="76519-132">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="76519-132">MDATP_SysExt.xml</span></span> | <span data-ttu-id="76519-133">不适用</span><span class="sxs-lookup"><span data-stu-id="76519-133">N/A</span></span> |
| [<span data-ttu-id="76519-134">批准适用于终结点的 Microsoft Defender 内核扩展</span><span class="sxs-lookup"><span data-stu-id="76519-134">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="76519-135">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="76519-135">MDATP_KExt.xml</span></span> | <span data-ttu-id="76519-136">不适用</span><span class="sxs-lookup"><span data-stu-id="76519-136">N/A</span></span> |
| [<span data-ttu-id="76519-137">授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限</span><span class="sxs-lookup"><span data-stu-id="76519-137">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#create-system-configuration-profiles-step-8) | <span data-ttu-id="76519-138">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="76519-138">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="76519-139">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="76519-139">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="76519-140">网络扩展策略</span><span class="sxs-lookup"><span data-stu-id="76519-140">Network Extension policy</span></span>](#create-system-configuration-profiles-step-9) | <span data-ttu-id="76519-141">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="76519-141">MDATP_NetExt.xml</span></span> | <span data-ttu-id="76519-142">不适用</span><span class="sxs-lookup"><span data-stu-id="76519-142">N/A</span></span> |
| [<span data-ttu-id="76519-143">配置 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="76519-143">Configure Microsoft AutoUpdate (MAU)</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | <span data-ttu-id="76519-144">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="76519-144">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="76519-145">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="76519-145">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="76519-146">Microsoft Defender for Endpoint 配置设置</span><span class="sxs-lookup"><span data-stu-id="76519-146">Microsoft Defender for Endpoint configuration settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> <span data-ttu-id="76519-147">**注意：** 如果计划运行适用于 macOS 的第三方 AV，请设置为 `passiveMode` `true` 。</span><span class="sxs-lookup"><span data-stu-id="76519-147">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="76519-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="76519-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="76519-149">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="76519-149">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="76519-150">配置 Microsoft Defender for Endpoint 和 MS AutoUpdate (MAU) 通知</span><span class="sxs-lookup"><span data-stu-id="76519-150">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](#create-system-configuration-profiles-step-10) | <span data-ttu-id="76519-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="76519-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="76519-152">com.microsoft.autoupdate2 或 com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="76519-152">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="76519-153">下载安装和载入程序包</span><span class="sxs-lookup"><span data-stu-id="76519-153">Download installation and onboarding packages</span></span>

<span data-ttu-id="76519-154">从 Microsoft Defender 安全中心下载安装和载入程序包：</span><span class="sxs-lookup"><span data-stu-id="76519-154">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="76519-155">在 Microsoft Defender 安全中心中，**转到"设置**  >  **""设备管理**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="76519-155">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="76519-156">将操作系统设置为 **macOS，** 将部署方法设置为 **移动设备管理 /Microsoft Intune**。</span><span class="sxs-lookup"><span data-stu-id="76519-156">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![载入设置屏幕截图](images/atp-mac-install.png)

3. <span data-ttu-id="76519-158">选择 **下载安装程序包**。</span><span class="sxs-lookup"><span data-stu-id="76519-158">Select **Download installation package**.</span></span> <span data-ttu-id="76519-159">将其另存为 _wdav.pkg_ 到本地目录。</span><span class="sxs-lookup"><span data-stu-id="76519-159">Save it as _wdav.pkg_ to a local directory.</span></span>

4. <span data-ttu-id="76519-160">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="76519-160">Select **Download onboarding package**.</span></span> <span data-ttu-id="76519-161">将其另 _存WindowsDefenderATPOnboardingPackage.zip_ 同一目录。</span><span class="sxs-lookup"><span data-stu-id="76519-161">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

5. <span data-ttu-id="76519-162">从 **下载 IntuneAppUtil。** [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos)</span><span class="sxs-lookup"><span data-stu-id="76519-162">Download **IntuneAppUtil** from [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos).</span></span>

6. <span data-ttu-id="76519-163">在命令提示符下，验证您是否具有这三个文件。</span><span class="sxs-lookup"><span data-stu-id="76519-163">From a command prompt, verify that you have the three files.</span></span>
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. <span data-ttu-id="76519-164">提取 .zip 文件的内容：</span><span class="sxs-lookup"><span data-stu-id="76519-164">Extract the contents of the .zip files:</span></span>

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

8. <span data-ttu-id="76519-165">使 IntuneAppUtil 成为可执行文件：</span><span class="sxs-lookup"><span data-stu-id="76519-165">Make IntuneAppUtil an executable:</span></span>

    ```bash
    chmod +x IntuneAppUtil
    ```

9. <span data-ttu-id="76519-166">从 wdav.pkg 创建 wdav.pkg.intunemac 程序包：</span><span class="sxs-lookup"><span data-stu-id="76519-166">Create the wdav.pkg.intunemac package from wdav.pkg:</span></span>

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a><span data-ttu-id="76519-167">客户端设备设置</span><span class="sxs-lookup"><span data-stu-id="76519-167">Client device setup</span></span>

<span data-ttu-id="76519-168">除了标准公司门户安装之外，不需要对 Mac 设备进行 [任何特殊预配](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)。</span><span class="sxs-lookup"><span data-stu-id="76519-168">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="76519-169">确认设备管理。</span><span class="sxs-lookup"><span data-stu-id="76519-169">Confirm device management.</span></span>

   ![确认设备管理屏幕截图](images/mdatp-3-confirmdevicemgmt.png)

    <span data-ttu-id="76519-171">选择 **"打开系统首选项"，** 在列表中找到"**管理配置文件**"，然后选择"批准 **..."。** 你的管理配置文件将显示为 **"已验证"：**</span><span class="sxs-lookup"><span data-stu-id="76519-171">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![管理配置文件屏幕截图](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="76519-173">选择 **"继续** "并完成注册。</span><span class="sxs-lookup"><span data-stu-id="76519-173">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="76519-174">你现在可以注册更多设备。</span><span class="sxs-lookup"><span data-stu-id="76519-174">You may now enroll more devices.</span></span> <span data-ttu-id="76519-175">完成系统配置和应用程序包的预配后，还可以稍后注册它们。</span><span class="sxs-lookup"><span data-stu-id="76519-175">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="76519-176">在 Intune 中，打开 **"**  >  **管理设备**  >  **""所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="76519-176">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="76519-177">你可以在此处查看列出的设备：</span><span class="sxs-lookup"><span data-stu-id="76519-177">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="76519-178">![添加设备屏幕截图](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="76519-178">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="approve-system-extensions"></a><span data-ttu-id="76519-179">批准系统扩展</span><span class="sxs-lookup"><span data-stu-id="76519-179">Approve System Extensions</span></span>

<span data-ttu-id="76519-180">批准系统扩展：</span><span class="sxs-lookup"><span data-stu-id="76519-180">To approve the system extensions:</span></span>

1. <span data-ttu-id="76519-181">在 Intune 中，打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="76519-181">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="76519-182">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="76519-182">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="76519-183">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="76519-183">Choose a name for the profile.</span></span> <span data-ttu-id="76519-184">将 **Platform=macOS** 更改为 **Profile type=Extensions**。</span><span class="sxs-lookup"><span data-stu-id="76519-184">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="76519-185">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="76519-185">Select **Create**.</span></span>

3. <span data-ttu-id="76519-186">在 **"基本"** 选项卡中，为此新配置文件命名。</span><span class="sxs-lookup"><span data-stu-id="76519-186">In the **Basics** tab, give a name to this new profile.</span></span>

4. <span data-ttu-id="76519-187">在" **配置设置** "选项卡中，在"允许的系统扩展" **部分添加以下** 条目：</span><span class="sxs-lookup"><span data-stu-id="76519-187">In the **Configuration settings** tab, add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="76519-188">捆绑包标识符</span><span class="sxs-lookup"><span data-stu-id="76519-188">Bundle identifier</span></span>         | <span data-ttu-id="76519-189">团队标识符</span><span class="sxs-lookup"><span data-stu-id="76519-189">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="76519-190">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="76519-190">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="76519-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="76519-191">UBF8T346G9</span></span>
    <span data-ttu-id="76519-192">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="76519-192">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="76519-193">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="76519-193">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-194">!["基本"选项卡上的"配置"设置中的扩展设置的屏幕截图](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="76519-194">![Screenshot of the extension settings in Configuration settings on the Basics tab](images/mac-system-extension-intune2.png)</span></span>

5. <span data-ttu-id="76519-195">在"**分配"** 选项卡中，将此配置文件分配给"所有 **&所有用户"。**</span><span class="sxs-lookup"><span data-stu-id="76519-195">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>

6. <span data-ttu-id="76519-196">查看并创建此配置文件。</span><span class="sxs-lookup"><span data-stu-id="76519-196">Review and create this configuration profile.</span></span>

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="76519-197">创建系统配置文件</span><span class="sxs-lookup"><span data-stu-id="76519-197">Create System Configuration profiles</span></span>

1. <span data-ttu-id="76519-198">在 Intune 中，打开 **"管理**  >  **设备配置"。**</span><span class="sxs-lookup"><span data-stu-id="76519-198">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="76519-199">选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="76519-199">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="76519-200">选择配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="76519-200">Choose a name for the profile.</span></span> <span data-ttu-id="76519-201">将 **Platform=macOS** 更改为 **配置文件类型=自定义**。</span><span class="sxs-lookup"><span data-stu-id="76519-201">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="76519-202">选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="76519-202">Select **Configure**.</span></span>

3. <span data-ttu-id="76519-203">打开配置文件并上传 intune/kext.xml。</span><span class="sxs-lookup"><span data-stu-id="76519-203">Open the configuration profile and upload intune/kext.xml.</span></span> <span data-ttu-id="76519-204">此文件在前一部分中创建。</span><span class="sxs-lookup"><span data-stu-id="76519-204">This file was created in one of the preceding sections.</span></span>

4. <span data-ttu-id="76519-205">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="76519-205">Select **OK**.</span></span>

    ![从文件导入自定义配置文件的配置](images/mdatp-6-systemconfigurationprofiles.png)

5. <span data-ttu-id="76519-207">选择 **"管理**  >  **工作分配"。**</span><span class="sxs-lookup"><span data-stu-id="76519-207">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="76519-208">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="76519-208">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

6. <span data-ttu-id="76519-209">对更多配置文件重复步骤 1 至 5。</span><span class="sxs-lookup"><span data-stu-id="76519-209">Repeat steps 1 through 5 for more profiles.</span></span>

7. <span data-ttu-id="76519-210">创建另一个配置文件，为它命名，然后上载 intune/WindowsDefenderATPOnboarding.xml文件。</span><span class="sxs-lookup"><span data-stu-id="76519-210">Create another profile, give it a name, and upload the intune/WindowsDefenderATPOnboarding.xml file.</span></span>

8. <span data-ttu-id="76519-211">从 [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)存储库下载 **fulldisk.mobileconfig** 并将其另存为 **tcc.xml。**</span><span class="sxs-lookup"><span data-stu-id="76519-211">Download **fulldisk.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and save it as **tcc.xml**.</span></span> <span data-ttu-id="76519-212">创建另一个配置文件，提供任意名称，然后向该文件上载此文件。<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span><span class="sxs-lookup"><span data-stu-id="76519-212">Create another profile, give it any name and upload this file to it.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span></span>

   > [!CAUTION]
   > <span data-ttu-id="76519-213">macOS 10.15 (Catalina) 新增了安全和隐私增强功能。</span><span class="sxs-lookup"><span data-stu-id="76519-213">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="76519-214">从此版本开始，默认情况下，应用程序无法访问磁盘上的某些位置 (如文档、下载、桌面等) 未经明确同意。</span><span class="sxs-lookup"><span data-stu-id="76519-214">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="76519-215">如果没有此同意，Microsoft Defender for Endpoint 将无法完全保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="76519-215">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="76519-216">此配置文件授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限。</span><span class="sxs-lookup"><span data-stu-id="76519-216">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="76519-217">如果你之前通过 Intune 配置了适用于 Endpoint 的 Microsoft Defender，我们建议你通过此配置文件更新部署。</span><span class="sxs-lookup"><span data-stu-id="76519-217">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

9. <span data-ttu-id="76519-218">作为终结点检测和响应功能的一部分，Microsoft Defender for Mac 终结点会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="76519-218">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="76519-219">以下策略允许网络扩展执行此功能。</span><span class="sxs-lookup"><span data-stu-id="76519-219">The following policy allows the network extension to perform this functionality.</span></span> <span data-ttu-id="76519-220">从 [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)存储库下载 **netfilter.mobileconfig，** 将其另存为netext.xml，然后使用与前面部分中相同的步骤部署它。</span><span class="sxs-lookup"><span data-stu-id="76519-220">Download **netfilter.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig), save it as netext.xml and deploy it using the same steps as in the previous sections.</span></span> <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. <span data-ttu-id="76519-221">若要允许 Microsoft Defender for Endpoint for Mac 和 Microsoft 自动更新在 macOS 10.15 (Catalina) 上的 UI 中显示通知，请从 `notif.mobileconfig` [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) 存储库下载并作为自定义负载导入。</span><span class="sxs-lookup"><span data-stu-id="76519-221">To allow Microsoft Defender for Endpoint for Mac and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina), download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) and import it as a custom payload.</span></span> <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. <span data-ttu-id="76519-222">选择 **"管理>分配"。**</span><span class="sxs-lookup"><span data-stu-id="76519-222">Select **Manage > Assignments**.</span></span>  <span data-ttu-id="76519-223">在"**包含"** 选项卡中，**选择"分配给&所有设备"。**</span><span class="sxs-lookup"><span data-stu-id="76519-223">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

<span data-ttu-id="76519-224">将 Intune 更改传播到已注册的设备后，你可以看到它们列在监视  >  **设备状态下**：</span><span class="sxs-lookup"><span data-stu-id="76519-224">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="76519-225">![监视器中的设备状态视图](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="76519-225">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="76519-226">发布应用程序</span><span class="sxs-lookup"><span data-stu-id="76519-226">Publish application</span></span>

1. <span data-ttu-id="76519-227">在 Intune 中，打开"管理 **>客户端应用"** 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="76519-227">In Intune, open the **Manage > Client apps** blade.</span></span> <span data-ttu-id="76519-228">选择 **"添加>应用"。**</span><span class="sxs-lookup"><span data-stu-id="76519-228">Select **Apps > Add**.</span></span>

2. <span data-ttu-id="76519-229">选择 **"应用类型=其他/业务线应用"。**</span><span class="sxs-lookup"><span data-stu-id="76519-229">Select **App type=Other/Line-of-business app**.</span></span>

3. <span data-ttu-id="76519-230">选择 **file=wdav.pkg.intunemac**。</span><span class="sxs-lookup"><span data-stu-id="76519-230">Select **file=wdav.pkg.intunemac**.</span></span> <span data-ttu-id="76519-231">选择 **"确定** "上载。</span><span class="sxs-lookup"><span data-stu-id="76519-231">Select **OK** to upload.</span></span>

4. <span data-ttu-id="76519-232">选择 **"** 配置"并添加所需信息。</span><span class="sxs-lookup"><span data-stu-id="76519-232">Select **Configure** and add the required information.</span></span>

5. <span data-ttu-id="76519-233">使用 **macOS High Sierra 10.14** 作为最低操作系统。</span><span class="sxs-lookup"><span data-stu-id="76519-233">Use **macOS High Sierra 10.14** as the minimum OS.</span></span>

6. <span data-ttu-id="76519-234">将 \*忽略应用版本设置为\***是**。</span><span class="sxs-lookup"><span data-stu-id="76519-234">Set *Ignore app version* to **Yes**.</span></span> <span data-ttu-id="76519-235">其他设置可以是任意值。</span><span class="sxs-lookup"><span data-stu-id="76519-235">Other settings can be any arbitrary value.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="76519-236">将 *"忽略应用* 版本 **"** 设置为"否"会影响应用程序通过 Microsoft AutoUpdate 接收更新的能力。</span><span class="sxs-lookup"><span data-stu-id="76519-236">Setting *Ignore app version* to **No** impacts the ability of the application to receive updates through Microsoft AutoUpdate.</span></span> <span data-ttu-id="76519-237">有关 [产品更新方法的其他](mac-updates.md) 信息，请参阅部署适用于 Mac 的 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="76519-237">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span>
    >
    > <span data-ttu-id="76519-238">如果 Intune 上传的版本低于设备上的版本，将安装较低版本，从而有效地降级适用于 Endpoint 的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="76519-238">If the version uploaded by Intune is lower than the version on the device, then the lower version will be installed, effectively downgrading Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="76519-239">这可能会导致应用程序无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="76519-239">This could result in a non-functioning application.</span></span> <span data-ttu-id="76519-240">有关 [产品更新方法的其他](mac-updates.md) 信息，请参阅部署适用于 Mac 的 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="76519-240">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span> <span data-ttu-id="76519-241">如果你部署了 Microsoft Defender for Endpoint， *忽略应用* 版本设置为 **否**，请将其更改为 **是**。</span><span class="sxs-lookup"><span data-stu-id="76519-241">If you deployed Microsoft Defender for Endpoint with *Ignore app version* set to **No**, please change it to **Yes**.</span></span> <span data-ttu-id="76519-242">如果客户端设备上仍无法安装 Microsoft Defender for Endpoint，请卸载 Microsoft Defender for Endpoint 并推送更新的策略。</span><span class="sxs-lookup"><span data-stu-id="76519-242">If Microsoft Defender for Endpoint still cannot be installed on a client device, then uninstall Microsoft Defender for Endpoint and push the updated policy.</span></span>
     
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-243">![应用程序添加中的应用程序信息显示](images/mdatp-8-intuneappinfo.png)</span><span class="sxs-lookup"><span data-stu-id="76519-243">![Display of App information in App add](images/mdatp-8-intuneappinfo.png)</span></span>

7. <span data-ttu-id="76519-244">选择 **"确定"** 和"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="76519-244">Select **OK** and **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-245">![通知窗口中显示的设备状态](images/mdatp-9-intunepkginfo.png)</span><span class="sxs-lookup"><span data-stu-id="76519-245">![Device status shown in Notifications window](images/mdatp-9-intunepkginfo.png)</span></span>

8. <span data-ttu-id="76519-246">上载程序包可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="76519-246">It may take a few moments to upload the package.</span></span> <span data-ttu-id="76519-247">完成后，从列表中选择程序包，然后转到 **分配和\*\*\*\*添加组**。</span><span class="sxs-lookup"><span data-stu-id="76519-247">After it's done, select the package from the list and go to **Assignments** and **Add group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-248">![客户端应用屏幕截图](images/mdatp-10-clientapps.png)</span><span class="sxs-lookup"><span data-stu-id="76519-248">![Client apps screenshot](images/mdatp-10-clientapps.png)</span></span>

9. <span data-ttu-id="76519-249">将 **"工作分配类型"\*\*\*\*更改为"必需"。**</span><span class="sxs-lookup"><span data-stu-id="76519-249">Change **Assignment type** to **Required**.</span></span>

10. <span data-ttu-id="76519-250">选择 **"包含的组"。**</span><span class="sxs-lookup"><span data-stu-id="76519-250">Select **Included Groups**.</span></span> <span data-ttu-id="76519-251">选择 **"使此应用成为所有设备必需的设备=是"。**</span><span class="sxs-lookup"><span data-stu-id="76519-251">Select **Make this app required for all devices=Yes**.</span></span> <span data-ttu-id="76519-252">选择 **"选择要包含的** 组"并添加包含要面向的用户的组。</span><span class="sxs-lookup"><span data-stu-id="76519-252">Select **Select group to include** and add a group that contains the users you want to target.</span></span> <span data-ttu-id="76519-253">选择 **"确定"** 和"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="76519-253">Select **OK** and **Save**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-254">![Intune 作业信息屏幕截图](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="76519-254">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

11. <span data-ttu-id="76519-255">一段时间之后，应用程序将发布到所有注册的设备。</span><span class="sxs-lookup"><span data-stu-id="76519-255">After some time the application will be published to all enrolled devices.</span></span> <span data-ttu-id="76519-256">你可以看到它列在 **监视设备，** 在  >  **设备安装状态下**：</span><span class="sxs-lookup"><span data-stu-id="76519-256">You can see it listed in **Monitor** > **Device**, under **Device install status**:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-257">![Intune 设备状态屏幕截图](images/mdatp-12-deviceinstall.png)</span><span class="sxs-lookup"><span data-stu-id="76519-257">![Intune device status screenshot](images/mdatp-12-deviceinstall.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="76519-258">验证客户端设备状态</span><span class="sxs-lookup"><span data-stu-id="76519-258">Verify client device state</span></span>

1. <span data-ttu-id="76519-259">将配置文件部署到设备后，在 Mac 设备上打开系统  >  首选项配置文件。</span><span class="sxs-lookup"><span data-stu-id="76519-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    <span data-ttu-id="76519-260">![系统首选项屏幕截图](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="76519-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span><br/>
    <span data-ttu-id="76519-261">![系统首选项配置文件屏幕截图](images/mdatp-14-systempreferencesprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="76519-261">![System Preferences Profiles screenshot](images/mdatp-14-systempreferencesprofiles.png)</span></span>

2. <span data-ttu-id="76519-262">确认存在并安装了以下配置文件。</span><span class="sxs-lookup"><span data-stu-id="76519-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="76519-263">管理 **配置文件** 应为 Intune 系统配置文件。</span><span class="sxs-lookup"><span data-stu-id="76519-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="76519-264">_Wdav-config_ 和 _wdav-kext_ 是在 Intune 中添加的系统配置文件： ![ 配置文件屏幕截图](images/mdatp-15-managementprofileconfig.png)</span><span class="sxs-lookup"><span data-stu-id="76519-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune: ![Profiles screenshot](images/mdatp-15-managementprofileconfig.png)</span></span>

3. <span data-ttu-id="76519-265">你还应在右上角看到 Microsoft Defender 图标：</span><span class="sxs-lookup"><span data-stu-id="76519-265">You should also see the Microsoft Defender icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="76519-266">![状态栏中的 Microsoft Defender 图标屏幕截图](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="76519-266">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="76519-267">疑难解答</span><span class="sxs-lookup"><span data-stu-id="76519-267">Troubleshooting</span></span>

<span data-ttu-id="76519-268">问题：未找到许可证</span><span class="sxs-lookup"><span data-stu-id="76519-268">Issue: No license found</span></span>

<span data-ttu-id="76519-269">解决方案：按照上述步骤使用 WindowsDefenderATPOnboarding.xml</span><span class="sxs-lookup"><span data-stu-id="76519-269">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="76519-270">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="76519-270">Logging installation issues</span></span>

<span data-ttu-id="76519-271">若要详细了解如何在发生错误时查找安装程序创建的自动生成的日志，请参阅记录 [安装问题](mac-resources.md#logging-installation-issues)。</span><span class="sxs-lookup"><span data-stu-id="76519-271">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="76519-272">卸载</span><span class="sxs-lookup"><span data-stu-id="76519-272">Uninstallation</span></span>

<span data-ttu-id="76519-273">请参阅 [卸载](mac-resources.md#uninstalling) ，了解有关如何从客户端设备中删除 Microsoft Defender for Mac 终结点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76519-273">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for Mac from client devices.</span></span>
