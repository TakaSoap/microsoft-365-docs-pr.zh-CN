---
title: 在 macOS 上手动部署 Microsoft Defender for Endpoint
description: 从命令行手动在 macOS 上安装 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: 0e8faf95df6691828558175412a1de8aa844d93f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688593"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="e7322-104">在 macOS 上手动部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7322-104">Manual deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7322-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e7322-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7322-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7322-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7322-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7322-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7322-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="e7322-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7322-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e7322-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="e7322-110">本主题介绍如何手动在 macOS 上部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="e7322-110">This topic describes how to deploy Microsoft Defender for Endpoint on macOS manually.</span></span> <span data-ttu-id="e7322-111">要成功部署，需要完成以下所有步骤：</span><span class="sxs-lookup"><span data-stu-id="e7322-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="e7322-112">下载安装和载入程序包</span><span class="sxs-lookup"><span data-stu-id="e7322-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="e7322-113">macOS (10.15 及早期版本的应用程序安装) </span><span class="sxs-lookup"><span data-stu-id="e7322-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="e7322-114">macOS 11 (更高版本的应用程序安装) </span><span class="sxs-lookup"><span data-stu-id="e7322-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="e7322-115">客户端配置</span><span class="sxs-lookup"><span data-stu-id="e7322-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="e7322-116">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="e7322-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="e7322-117">在开始使用之前，请参阅 [macOS](microsoft-defender-endpoint-mac.md) 上的 Microsoft Defender for Endpoint 主页，了解当前软件版本的先决条件和系统要求说明。</span><span class="sxs-lookup"><span data-stu-id="e7322-117">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="e7322-118">下载安装和载入程序包</span><span class="sxs-lookup"><span data-stu-id="e7322-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="e7322-119">从 Microsoft Defender 安全中心下载安装和载入程序包：</span><span class="sxs-lookup"><span data-stu-id="e7322-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="e7322-120">在 Microsoft Defender 安全中心中，转到"设备>**设置>载入"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="e7322-121">在页面的第 1 部分中，将操作系统设置为 **macOS，** 将 Deployment 方法设置为 **本地脚本**。</span><span class="sxs-lookup"><span data-stu-id="e7322-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="e7322-122">在页面的第 2 部分中，选择 **下载安装程序包**。</span><span class="sxs-lookup"><span data-stu-id="e7322-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="e7322-123">将其另存为 wdav.pkg 到本地目录。</span><span class="sxs-lookup"><span data-stu-id="e7322-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="e7322-124">在页面的第 2 部分中，选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="e7322-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="e7322-125">将其另存WindowsDefenderATPOnboardingPackage.zip同一目录。</span><span class="sxs-lookup"><span data-stu-id="e7322-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender 安全中心屏幕截图](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="e7322-127">在命令提示符下，验证您是否具有这两个文件。</span><span class="sxs-lookup"><span data-stu-id="e7322-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="e7322-128">macOS (10.15 及早期版本的应用程序安装) </span><span class="sxs-lookup"><span data-stu-id="e7322-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="e7322-129">若要完成此过程，你必须在设备上拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e7322-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="e7322-130">导航到 Finder 中下载的 wdav.pkg 并打开它。</span><span class="sxs-lookup"><span data-stu-id="e7322-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![应用安装屏幕截图1](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="e7322-132">选择 **"继续**"，同意许可条款，在系统提示时输入密码。</span><span class="sxs-lookup"><span data-stu-id="e7322-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![应用安装屏幕截图2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="e7322-134">系统将提示你允许从 Microsoft 安装驱动程序， ("系统扩展被阻止"或"安装已保留"或两者同时安装。</span><span class="sxs-lookup"><span data-stu-id="e7322-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="e7322-135">必须允许安装驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e7322-135">The driver must be allowed to be installed.</span></span>

   ![应用安装屏幕截图3](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="e7322-137">选择 **"打开安全首选项"** 或"打开系统首选项 **>安全&隐私"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="e7322-138">选择 **"允许"：**</span><span class="sxs-lookup"><span data-stu-id="e7322-138">Select **Allow**:</span></span>

    ![安全和隐私窗口屏幕截图](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="e7322-140">继续安装。</span><span class="sxs-lookup"><span data-stu-id="e7322-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="e7322-141">如果未选择"允许 **"，** 则安装将在 5 分钟后继续。</span><span class="sxs-lookup"><span data-stu-id="e7322-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="e7322-142">Microsoft Defender for Endpoint 将加载，但某些功能（如实时保护）将被禁用。</span><span class="sxs-lookup"><span data-stu-id="e7322-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="e7322-143">请参阅 [内核扩展问题](mac-support-kext.md) 疑难解答，了解如何解决此问题。</span><span class="sxs-lookup"><span data-stu-id="e7322-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="e7322-144">macOS 可能会请求在首次安装 Microsoft Defender for Endpoint 时重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e7322-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e7322-145">在重新启动设备之前，实时保护将不可用。</span><span class="sxs-lookup"><span data-stu-id="e7322-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="e7322-146">macOS 11 (更高版本的应用程序安装) </span><span class="sxs-lookup"><span data-stu-id="e7322-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="e7322-147">若要完成此过程，你必须在设备上拥有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e7322-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="e7322-148">导航到 Finder 中下载的 wdav.pkg 并打开它。</span><span class="sxs-lookup"><span data-stu-id="e7322-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![应用安装屏幕截图4](images/big-sur-install-1.png)

2. <span data-ttu-id="e7322-150">选择 **"继续**"，同意许可条款，在系统提示时输入密码。</span><span class="sxs-lookup"><span data-stu-id="e7322-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="e7322-151">在安装过程结束时，你将被提升为批准产品使用的系统扩展。</span><span class="sxs-lookup"><span data-stu-id="e7322-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="e7322-152">选择 **"打开安全首选项"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-152">Select **Open Security Preferences**.</span></span>

    ![系统扩展审批](images/big-sur-install-2.png)

4. <span data-ttu-id="e7322-154">从"**安全&隐私"** 窗口中，选择"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![系统扩展安全首选项1](images/big-sur-install-3.png)

5. <span data-ttu-id="e7322-156">对通过 Mac 上的 Microsoft Defender for Endpoint 分发的所有系统扩展重复步骤 3 & 4。</span><span class="sxs-lookup"><span data-stu-id="e7322-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint on Mac.</span></span>

6. <span data-ttu-id="e7322-157">作为终结点检测和响应功能的一部分，Mac 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="e7322-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="e7322-158">当系统提示授予 Microsoft Defender 终结点权限以筛选网络流量时，请选择"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![系统扩展安全首选项2](images/big-sur-install-4.png)

7. <span data-ttu-id="e7322-160">打开 **"系统** 首选项&隐私"并导航到"隐私"选项卡。授予 Microsoft Defender ATP 和 Microsoft Defender ATP 终结点安全扩展的"完全磁盘  >  **访问权限"。**   </span><span class="sxs-lookup"><span data-stu-id="e7322-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![完全磁盘访问](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="e7322-162">客户端配置</span><span class="sxs-lookup"><span data-stu-id="e7322-162">Client configuration</span></span>

1. <span data-ttu-id="e7322-163">将 wdav.pkg 和 MicrosoftDefenderATPOnboardingMacOs.py 复制到 macOS 上部署 Microsoft Defender for Endpoint 的设备。</span><span class="sxs-lookup"><span data-stu-id="e7322-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint on macOS.</span></span>

    <span data-ttu-id="e7322-164">客户端设备不与客户端org_id。</span><span class="sxs-lookup"><span data-stu-id="e7322-164">The client device isn't associated with org_id.</span></span> <span data-ttu-id="e7322-165">请注意 *，org_id* 属性为空。</span><span class="sxs-lookup"><span data-stu-id="e7322-165">Note that the *org_id* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="e7322-166">运行 Python 脚本以安装配置文件：</span><span class="sxs-lookup"><span data-stu-id="e7322-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="e7322-167">验证设备现在是否与组织关联，并报告有效的组织 ID：</span><span class="sxs-lookup"><span data-stu-id="e7322-167">Verify that the device is now associated with your organization and reports a valid org ID:</span></span>

    ```bash
    mdatp health --field org_id
    ```

    <span data-ttu-id="e7322-168">安装后，你将在右上角的 macOS 状态栏中看到 Microsoft Defender 图标。</span><span class="sxs-lookup"><span data-stu-id="e7322-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e7322-169">![状态栏中的 Microsoft Defender 图标屏幕截图](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="e7322-169">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>


## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="e7322-170">如何：允许完全磁盘访问</span><span class="sxs-lookup"><span data-stu-id="e7322-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="e7322-171">macOS 10.15 (Catalina) 新增了安全和隐私增强功能。</span><span class="sxs-lookup"><span data-stu-id="e7322-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="e7322-172">从此版本开始，默认情况下，应用程序无法访问磁盘上的某些位置 (如文档、下载、桌面等) 未经明确同意。</span><span class="sxs-lookup"><span data-stu-id="e7322-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="e7322-173">如果没有此同意，Microsoft Defender for Endpoint 将无法完全保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="e7322-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

1. <span data-ttu-id="e7322-174">若要授予同意，请打开 **系统首选项**  >  **安全&**  >  **隐私**  >  **隐私完全磁盘访问**。</span><span class="sxs-lookup"><span data-stu-id="e7322-174">To grant consent, open **System Preferences** > **Security & Privacy** > **Privacy** > **Full Disk Access**.</span></span> <span data-ttu-id="e7322-175">单击锁定图标以在 (对话框底部进行更改) 。</span><span class="sxs-lookup"><span data-stu-id="e7322-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="e7322-176">选择"适用于终结点的 Microsoft Defender"。</span><span class="sxs-lookup"><span data-stu-id="e7322-176">Select Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="e7322-177">运行 AV 检测测试，验证设备是否正确载入并报告给服务。</span><span class="sxs-lookup"><span data-stu-id="e7322-177">Run an AV detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="e7322-178">对新载入的设备执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7322-178">Perform the following steps on the newly onboarded device:</span></span>

    1. <span data-ttu-id="e7322-179">确保通过运行以下命令 (1 的结果来启用实时) ：</span><span class="sxs-lookup"><span data-stu-id="e7322-179">Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. <span data-ttu-id="e7322-180">打开"终端"窗口。</span><span class="sxs-lookup"><span data-stu-id="e7322-180">Open a Terminal window.</span></span> <span data-ttu-id="e7322-181">复制并执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e7322-181">Copy and execute the following command:</span></span>

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. <span data-ttu-id="e7322-182">文件应已由 Defender for Endpoint for Mac 隔离。</span><span class="sxs-lookup"><span data-stu-id="e7322-182">The file should have been quarantined by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="e7322-183">使用以下命令列出所有检测到的威胁：</span><span class="sxs-lookup"><span data-stu-id="e7322-183">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

3. <span data-ttu-id="e7322-184">运行 EDR 检测测试，验证设备是否正确载入并报告给服务。</span><span class="sxs-lookup"><span data-stu-id="e7322-184">Run an EDR detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="e7322-185">对新载入的设备执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7322-185">Perform the following steps on the newly onboarded device:</span></span>

   1. <span data-ttu-id="e7322-186">在浏览器（如 Microsoft Edge for Mac 或 Safari）中。</span><span class="sxs-lookup"><span data-stu-id="e7322-186">In your browser such as Microsoft Edge for Mac or Safari.</span></span>

   1. <span data-ttu-id="e7322-187">下载 MDATP MacOS DIY.zip https://aka.ms/mdatpmacosdiy 并从中提取。</span><span class="sxs-lookup"><span data-stu-id="e7322-187">Download MDATP MacOS DIY.zip from https://aka.ms/mdatpmacosdiy and extract.</span></span>

      <span data-ttu-id="e7322-188">系统可能会提示你：</span><span class="sxs-lookup"><span data-stu-id="e7322-188">You may be prompted:</span></span>

      > <span data-ttu-id="e7322-189">是否要允许下载"mdatpclientanalyzer.blob.core.windows.net"？</span><span class="sxs-lookup"><span data-stu-id="e7322-189">Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?</span></span><br/>
      > <span data-ttu-id="e7322-190">你可以更改哪些网站可以下载网站首选项中的文件。</span><span class="sxs-lookup"><span data-stu-id="e7322-190">You can change which websites can download files in Websites Preferences.</span></span>

4. <span data-ttu-id="e7322-191">单击"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-191">Click **Allow**.</span></span>

5. <span data-ttu-id="e7322-192">打开 **下载**。</span><span class="sxs-lookup"><span data-stu-id="e7322-192">Open **Downloads**.</span></span>

6. <span data-ttu-id="e7322-193">你应该会看到 **MDATP MacOS DIY**。</span><span class="sxs-lookup"><span data-stu-id="e7322-193">You should see **MDATP MacOS DIY**.</span></span>

   > [!TIP]
   > <span data-ttu-id="e7322-194">如果双击，将收到以下消息：</span><span class="sxs-lookup"><span data-stu-id="e7322-194">If you double-click, you will get the following message:</span></span>
   > 
   > > <span data-ttu-id="e7322-195">**无法打开"MDATP MacOS DIY"，因为开发人员无法验证程序。**</span><span class="sxs-lookup"><span data-stu-id="e7322-195">**"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**</span></span><br/>
   > > <span data-ttu-id="e7322-196">macOS 无法验证此应用程序是否不含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e7322-196">macOS cannot verify that this app is free from malware.</span></span><br/>
   > > <span data-ttu-id="e7322-197">**\[ 移动到回收 \]\*\*\*\*\[ 站取消 \]**</span><span class="sxs-lookup"><span data-stu-id="e7322-197">**\[Move to Trash\]** **\[Cancel\]**</span></span> 
  
7. <span data-ttu-id="e7322-198">Click **Cancel**.</span><span class="sxs-lookup"><span data-stu-id="e7322-198">Click **Cancel**.</span></span>

8. <span data-ttu-id="e7322-199">右键单击 **"MDATP MacOS DIY"，** 然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7322-199">Right-click **MDATP MacOS DIY**, and then click **Open**.</span></span> 

    <span data-ttu-id="e7322-200">系统应显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="e7322-200">The system should display the following message:</span></span>

    > <span data-ttu-id="e7322-201">**macOS 无法验证 **MDATP MacOS DIY 的开发人员**。确定要打开它吗？**</span><span class="sxs-lookup"><span data-stu-id="e7322-201">**macOS cannot verify the developer of **MDATP MacOS DIY**. Are you sure you want to open it?**</span></span><br/>
    > <span data-ttu-id="e7322-202">通过打开此应用，你将覆盖系统安全，这样可能会向可能损害 Mac 或隐私的恶意软件公开计算机和个人信息。</span><span class="sxs-lookup"><span data-stu-id="e7322-202">By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.</span></span>

10. <span data-ttu-id="e7322-203">单击“打开”。</span><span class="sxs-lookup"><span data-stu-id="e7322-203">Click **Open**.</span></span>

    <span data-ttu-id="e7322-204">系统应显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="e7322-204">The system should display the following message:</span></span>

    > <span data-ttu-id="e7322-205">Microsoft Defender ATP - macOS EDR DIY 测试文件</span><span class="sxs-lookup"><span data-stu-id="e7322-205">Microsoft Defender ATP - macOS EDR DIY test file</span></span><br/>
    > <span data-ttu-id="e7322-206">MDATP 门户中将提供相应的警报。</span><span class="sxs-lookup"><span data-stu-id="e7322-206">Corresponding alert will be available in the MDATP portal.</span></span>

11. <span data-ttu-id="e7322-207">单击“打开”。</span><span class="sxs-lookup"><span data-stu-id="e7322-207">Click **Open**.</span></span>

    <span data-ttu-id="e7322-208">几分钟后，将引发名为"macOS EDR 测试警报"的警报。</span><span class="sxs-lookup"><span data-stu-id="e7322-208">In a few minutes an alert named "macOS EDR Test Alert" should be raised.</span></span>

12. <span data-ttu-id="e7322-209">转到 Microsoft Defender 安全中心 https://SecurityCenter.microsoft.com) (。</span><span class="sxs-lookup"><span data-stu-id="e7322-209">Go to Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).</span></span>

13. <span data-ttu-id="e7322-210">转到警报队列。</span><span class="sxs-lookup"><span data-stu-id="e7322-210">Go to the Alert Queue.</span></span>

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="显示严重性、类别、检测源和折叠操作菜单的 macOS EDR 测试警报示例。":::
    
    <span data-ttu-id="e7322-212">查看警报详细信息和设备时间线，并执行常规调查步骤。</span><span class="sxs-lookup"><span data-stu-id="e7322-212">Look at the alert details and the device timeline, and perform the regular investigation steps.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="e7322-213">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="e7322-213">Logging installation issues</span></span>

<span data-ttu-id="e7322-214">请参阅 [记录](mac-resources.md#logging-installation-issues) 安装问题，详细了解如何在发生错误时查找安装程序创建的自动生成的日志。</span><span class="sxs-lookup"><span data-stu-id="e7322-214">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="e7322-215">卸载</span><span class="sxs-lookup"><span data-stu-id="e7322-215">Uninstallation</span></span>

<span data-ttu-id="e7322-216">请参阅 [卸载](mac-resources.md#uninstalling) ，了解有关如何从客户端设备中删除适用于 macOS 的 Microsoft Defender for Endpoint 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e7322-216">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
