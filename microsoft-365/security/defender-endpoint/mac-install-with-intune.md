---
title: macOS 上的 Microsoft Defender for Endpoint 的基于 Intune 的部署
description: 使用 Microsoft Intune 在 macOS 上安装 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: 7486bde0886506a5966a95cdb0b85fc009858801
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689745"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上的 Microsoft Defender for Endpoint 的基于 Intune 的部署

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> 本文档介绍在 macOS 设备上部署和配置 Microsoft Defender for Endpoint 的旧方法。 本机体验现已在 MEM 控制台中提供。 MEM 控制台中本机 UI 的发布为管理员提供了一种更简单的方式来配置和部署应用程序并将其发送到 macOS 设备。 <br> <br>
>博客文章 [MEM 简化了适用于 macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) 的 Microsoft Defender for Endpoint 的部署，介绍了新功能。 若要配置应用，请转到 Microsoft InTune 中 [macOS](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos)上的 Microsoft Defender for Endpoint 的设置。 若要部署应用，请转到使用 [Microsoft Intune 将 Microsoft Defender for Endpoint](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)添加到 macOS 设备。

**适用于：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)

本主题介绍如何通过 Intune 在 macOS 上部署 Microsoft Defender for Endpoint。 要成功部署，需要完成以下所有步骤：

1. [下载安装和载入程序包](#download-installation-and-onboarding-packages)
1. [客户端设备设置](#client-device-setup)
1. [批准系统扩展](#approve-system-extensions)
1. [创建系统配置文件](#create-system-configuration-profiles)
1. [发布应用程序](#publish-application)

## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

在开始使用之前，请参阅 [macOS](microsoft-defender-endpoint-mac.md) 上的 Microsoft Defender for Endpoint 主页，了解当前软件版本的先决条件和系统要求说明。

## <a name="overview"></a>概述

下表总结了通过 Intune 部署和管理适用于 Mac 的 Microsoft Defender for Endpoint 需要执行的步骤。 下面提供了更详细的步骤。

| 步骤 | 示例文件名 | BundleIdentifier |
|-|-|-|
| [下载安装和载入程序包](#download-installation-and-onboarding-packages) | WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml | com.microsoft.wdav.atp |
| [批准适用于终结点的 Microsoft Defender 的系统扩展](#approve-system-extensions) | MDATP_SysExt.xml | 不适用 |
| [批准适用于终结点的 Microsoft Defender 内核扩展](#download-installation-and-onboarding-packages) | MDATP_KExt.xml | 不适用 |
| [授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限](#create-system-configuration-profiles-step-8) | MDATP_tcc_Catalina_or_newer.xml | com.microsoft.wdav.tcc |
| [网络扩展策略](#create-system-configuration-profiles-step-9) | MDATP_NetExt.xml | 不适用 |
| [配置 Microsoft AutoUpdate (MAU) ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | MDATP_Microsoft_AutoUpdate.xml | com.microsoft.autoupdate2 |
| [Microsoft Defender for Endpoint 配置设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> **注意：** 如果计划运行适用于 macOS 的第三方 AV，请设置为 `passiveMode` `true` 。 | MDATP_WDAV_and_exclusion_settings_Preferences.xml | com.microsoft.wdav |
| [配置 Microsoft Defender for Endpoint 和 MS AutoUpdate (MAU) 通知](#create-system-configuration-profiles-step-10) | MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig | com.microsoft.autoupdate2 或 com.microsoft.wdav.tray |

## <a name="download-installation-and-onboarding-packages"></a>下载安装和载入程序包

从 Microsoft Defender 安全中心下载安装和载入程序包：

1. 在 Microsoft Defender 安全中心中，**转到"设置**  >  **""设备管理**  >  **""载入"。**

2. 将操作系统设置为 **macOS，** 将部署方法设置为 **移动设备管理 /Microsoft Intune**。

    ![载入设置屏幕截图](images/atp-mac-install.png)

3. 选择 **下载安装程序包**。 将其另存为 _wdav.pkg_ 到本地目录。

4. 选择 **下载载入程序包**。 将其另 _存WindowsDefenderATPOnboardingPackage.zip_ 同一目录。

5. 从 **下载 IntuneAppUtil。** [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos)

6. 在命令提示符下，验证您是否具有这三个文件。
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. 提取 .zip 文件的内容：

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

8. 使 IntuneAppUtil 成为可执行文件：

    ```bash
    chmod +x IntuneAppUtil
    ```

9. 从 wdav.pkg 创建 wdav.pkg.intunemac 程序包：

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

## <a name="client-device-setup"></a>客户端设备设置

除了标准公司门户安装之外，不需要对 Mac 设备进行 [任何特殊预配](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)。

1. 确认设备管理。

   ![确认设备管理屏幕截图](images/mdatp-3-confirmdevicemgmt.png)

    选择 **"打开系统首选项"，** 在列表中找到"**管理配置文件**"，然后选择"批准 **..."。** 你的管理配置文件将显示为 **"已验证"：**

    ![管理配置文件屏幕截图](images/mdatp-4-managementprofile.png)

2. 选择 **"继续** "并完成注册。

   你现在可以注册更多设备。 完成系统配置和应用程序包的预配后，还可以稍后注册它们。

3. 在 Intune 中，打开 **"**  >  **管理设备**  >  **""所有设备"。** 你可以在此处查看列出的设备：

   > [!div class="mx-imgBorder"]
   > ![添加设备屏幕截图](images/mdatp-5-alldevices.png)

## <a name="approve-system-extensions"></a>批准系统扩展

批准系统扩展：

1. 在 Intune 中，打开 **"管理**  >  **设备配置"。** 选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**

2. 选择配置文件的名称。 将 **Platform=macOS** 更改为 **Profile type=Extensions**。 选择“创建”。

3. 在 **"基本"** 选项卡中，为此新配置文件命名。

4. 在" **配置设置** "选项卡中，在"允许的系统扩展" **部分添加以下** 条目：

    捆绑包标识符         | 团队标识符
    --------------------------|----------------
    com.microsoft.wdav.epsext | UBF8T346G9
    com.microsoft.wdav.netext | UBF8T346G9

    > [!div class="mx-imgBorder"]
    > !["基本"选项卡上的"配置"设置中的扩展设置的屏幕截图](images/mac-system-extension-intune2.png)

5. 在"**分配"** 选项卡中，将此配置文件分配给"所有 **&所有用户"。**

6. 查看并创建此配置文件。

## <a name="create-system-configuration-profiles"></a>创建系统配置文件

1. 在 Intune 中，打开 **"管理**  >  **设备配置"。** 选择 **"管理**  >  **配置文件**  >  **""创建配置文件"。**

2. 选择配置文件的名称。 将 **Platform=macOS** 更改为 **配置文件类型=自定义**。 选择"**配置"。**

3. 打开配置文件并上传 intune/kext.xml。 此文件在前一部分中创建。

4. 选择“**确定**”。

    ![从文件导入自定义配置文件的配置](images/mdatp-6-systemconfigurationprofiles.png)

5. 选择 **"管理**  >  **工作分配"。** 在"**包含"** 选项卡中，**选择"分配给&所有设备"。**

6. 对更多配置文件重复步骤 1 至 5。

7. 创建另一个配置文件，为它命名，然后上载 intune/WindowsDefenderATPOnboarding.xml文件。

8. 从 [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)存储库下载 **fulldisk.mobileconfig** 并将其另存为 **tcc.xml。** 创建另一个配置文件，提供任意名称，然后向该文件上载此文件。<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a>

   > [!CAUTION]
   > macOS 10.15 (Catalina) 新增了安全和隐私增强功能。 从此版本开始，默认情况下，应用程序无法访问磁盘上的某些位置 (如文档、下载、桌面等) 未经明确同意。 如果没有此同意，Microsoft Defender for Endpoint 将无法完全保护你的设备。
   >
   > 此配置文件授予对 Microsoft Defender for Endpoint 的完全磁盘访问权限。 如果你之前通过 Intune 配置了适用于 Endpoint 的 Microsoft Defender，我们建议你通过此配置文件更新部署。

9. 作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。 以下策略允许网络扩展执行此功能。 从 [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)存储库下载 **netfilter.mobileconfig，** 将其另存为netext.xml，然后使用与前面部分中相同的步骤部署它。 <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. 若要允许 macOS 和 Microsoft 自动更新上的 Microsoft Defender for Endpoint 在 macOS 10.15 (Catalina) 上的 UI 中显示通知，请从 `notif.mobileconfig` [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) 存储库下载并作为自定义负载导入。 <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. 选择 **"管理>分配"。**  在"**包含"** 选项卡中，**选择"分配给&所有设备"。**

将 Intune 更改传播到已注册的设备后，你可以看到它们列在监视  >  **设备状态下**：

> [!div class="mx-imgBorder"]
> ![监视器中的设备状态视图](images/mdatp-7-devicestatusblade.png)

## <a name="publish-application"></a>发布应用程序

1. 在 Intune 中，打开"管理 **>客户端应用"** 边栏选项卡。 选择 **"添加>应用"。**

2. 选择 **"应用类型=其他/业务线应用"。**

3. 选择 **file=wdav.pkg.intunemac**。 选择 **"确定** "上载。

4. 选择 **"** 配置"并添加所需信息。

5. 使用 **macOS High Sierra 10.14** 作为最低操作系统。

6. 将 *忽略应用版本设置为***是**。 其他设置可以是任意值。

    > [!CAUTION]
    > 将 *"忽略应用* 版本 **"** 设置为"否"会影响应用程序通过 Microsoft AutoUpdate 接收更新的能力。 有关 [产品更新方法的其他](mac-updates.md) 信息，请参阅在 macOS 上部署适用于终结点的 Microsoft Defender 更新。
    >
    > 如果 Intune 上传的版本低于设备上的版本，将安装较低版本，从而有效地降级适用于 Endpoint 的 Microsoft Defender。 这可能会导致应用程序无法正常工作。 有关 [产品更新方法的其他](mac-updates.md) 信息，请参阅在 macOS 上部署适用于终结点的 Microsoft Defender 更新。 如果你部署了 Microsoft Defender for Endpoint， *忽略应用* 版本设置为 **否**，请将其更改为 **是**。 如果客户端设备上仍无法安装 Microsoft Defender for Endpoint，请卸载 Microsoft Defender for Endpoint 并推送更新的策略。
     
    > [!div class="mx-imgBorder"]
    > ![应用程序添加中的应用程序信息显示](images/mdatp-8-intuneappinfo.png)

7. 选择 **"确定"** 和"**添加"。**

    > [!div class="mx-imgBorder"]
    > ![通知窗口中显示的设备状态](images/mdatp-9-intunepkginfo.png)

8. 上载程序包可能需要一些时间。 完成后，从列表中选择程序包，然后转到 **分配和****添加组**。

    > [!div class="mx-imgBorder"]
    > ![客户端应用屏幕截图](images/mdatp-10-clientapps.png)

9. 将 **"工作分配类型"****更改为"必需"。**

10. 选择 **"包含的组"。** 选择 **"使此应用成为所有设备必需的设备=是"。** 选择 **"选择要包含的** 组"并添加包含要面向的用户的组。 选择 **"确定"** 和"**保存"。**

    > [!div class="mx-imgBorder"]
    > ![Intune 作业信息屏幕截图](images/mdatp-11-assignments.png)

11. 一段时间之后，应用程序将发布到所有注册的设备。 你可以看到它列在 **监视设备，** 在  >  **设备安装状态下**：

    > [!div class="mx-imgBorder"]
    > ![Intune 设备状态屏幕截图](images/mdatp-12-deviceinstall.png)

## <a name="verify-client-device-state"></a>验证客户端设备状态

1. 将配置文件部署到设备后，在 Mac 设备上打开系统  >  首选项配置文件。

    ![系统首选项屏幕截图](images/mdatp-13-systempreferences.png)<br/>
    ![系统首选项配置文件屏幕截图](images/mdatp-14-systempreferencesprofiles.png)

2. 确认存在并安装了以下配置文件。 管理 **配置文件** 应为 Intune 系统配置文件。 _Wdav-config_ 和 _wdav-kext_ 是在 Intune 中添加的系统配置文件： ![ 配置文件屏幕截图](images/mdatp-15-managementprofileconfig.png)

3. 你还应在右上角看到 Microsoft Defender 图标：

    > [!div class="mx-imgBorder"]
    > ![状态栏中的 Microsoft Defender 图标屏幕截图](images/mdatp-icon-bar.png)

## <a name="troubleshooting"></a>疑难解答

问题：未找到许可证

解决方案：按照上述步骤使用 WindowsDefenderATPOnboarding.xml

## <a name="logging-installation-issues"></a>记录安装问题

若要详细了解如何在发生错误时查找安装程序创建的自动生成的日志，请参阅记录 [安装问题](mac-resources.md#logging-installation-issues)。

## <a name="uninstallation"></a>卸载

请参阅 [卸载](mac-resources.md#uninstalling) ，详细了解如何从客户端设备中删除 macOS 上的 Microsoft Defender for Endpoint。
