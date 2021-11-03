---
title: '使用 Microsoft 365 预览版将 macOS 设备载入Microsoft Intune (macOS) '
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: '了解如何使用 Microsoft 365 预览版将 macOS 设备载入和Microsoft Intune (合规性) '
ms.openlocfilehash: fb3e89b303c8c17de3eb6826c25d2b54be364b7e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717425"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview"></a>使用 In (tune Microsoft 365预览版将 macOS 设备载入和) 

可以使用 Intune 将 macOS 设备载入到Microsoft 365解决方案中。

> [!IMPORTANT]
> 如果您没有将 Microsoft  Defender for Endpoint (MDE) 部署到 macOS 设备，请使用此过程

## <a name="get-registered"></a>注册

若要获取此功能的访问权限，必须向 Microsoft 注册租户。 请参阅 注册[macOS Microsoft 365。](https://aka.ms/Ignite2021DLP)

**适用于：**

- [Microsoft 365DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>开始之前

- 确保你的[macOS 设备已载入 Intune，](/mem/intune/fundamentals/deployment-guide-platform-macos)并且已注册公司门户[应用](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
- 确保你有权访问Microsoft Endpoint Manager[中心](https://endpoint.microsoft.com/#home)。
- 这支持 macOS 版本 Catalina 10.15 及更高版本。
- 创建要为其分配配置更新的用户组。
- 在 macOS 设备上安装 v95+ Edge 浏览器 


## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>使用 Microsoft 365 将 macOS 设备载入到 Microsoft Intune

将 macOS 设备载入合规性解决方案的过程分为六个阶段。

1. [创建系统配置文件](#create-system-configuration-profiles)
1. [获取设备载入包](#get-the-device-onboarding-package)
1. [部署载入包](#deploy-the-onboarding-package)
1. [启用系统扩展](#enable-system-extension)
1. [获取安装包](#get-the-installation-package)
1. [部署安装包](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>创建系统配置文件

1. 此过程需要这些文件。

|文件所需的 |source |
|---------|---------|
|载入包    |从合规性门户载入 **程序包下载，***文件名DeviceComplianceOnboarding.xml* |
|辅助功能 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
完全磁盘访问     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|网络文件器| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|系统扩展 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|MDE 首选项     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU 首选项|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|安装包     |从合规性门户安装程序包 **下载，** 文件名 *\* wdav.pkg*\* |

> [!TIP]
> 您可以单独下载 *.mobileconfig* 文件，也可以将这些文件下载到包含以下项的 [单个](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 组合文件中：
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - 系统扩展
>
>如果其中任何一个文件已更新，则需要再次下载组合的文件或单独下载单个更新的文件。

<!--2. Copy this code and save it in a file named `com.microsoft.autoupdate2.xml`.

```xml
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
-->

2. 打开Microsoft Endpoint Manager  >  **中心"设备**  >  **配置文件"。**

1. 选择： **创建配置文件** 

1. 选择：
    1. **Platform = macOS**
    1. **配置文件类型 = 模板**
    1. **模板名称 = 自定义**

1. 选择 **"创建"**

1. 为配置文件选择一个名称，如 *本示例中的 AccessibilityformacOS。* 选择 **下一步**。

1. 选择在步骤 1 中下载的 **accessibility.mobileconfig** 文件作为配置文件。

1. 选择 **"下一步"**

1. 在"**分配**"选项卡上，将想要部署这些配置的组添加到 ，然后选择"下一 **步"。**

1. 查看设置并选择" **创建"** 以部署配置。

1. 重复步骤 3-11，为以下项目创建配置文件：
    1. **fulldisk.mobileconfig** 文件
    1. **com.microsoft.autoupdate2.xml** 文件
    1. MDE 首选项 **com.microsoft.wdav.xml** 文件
        1. 设置防病毒引擎 `passive mode`  =  `true` 或 `false` 。 如果 `true` 仅部署 DLP，请使用 。 如果在 `false` MDE 中部署 DLP 和 Microsoft Defender for Endpoint (，) 。
    1. **netfilter.mobileconfig**
 
1. 打开 **设备**  >  **配置文件，** 你应该会看到你创建的配置文件。

1. 在 **"配置文件"** 页中，选择刚创建的配置文件（此示例中为 *AccessibilityformacOS）* 并选择"设备状态"以查看设备列表和配置文件的部署状态。

### <a name="get-the-device-onboarding-package"></a>获取设备载入包

1. 在 **"合规性中心**"**中**  >  **设置"设备载入"，** 然后选择 **"载入"。**
 
1. 对于 **选择操作系统以开始载入过程，请选择** **macOS**。
 
1. 对于 **"部署"方法**，**选择"移动设备管理/Microsoft Intune"。**
 
1. 选择 **"下载载入程序包"。** 这包含文件包中的 *DeviceComplianceOnboarding.xml* 代码。

### <a name="deploy-the-onboarding-package"></a>部署载入包

1. 打开Microsoft Endpoint Manager  >  **中心"设备**  >  **配置文件"。**

1. 选择： **创建配置文件**。 

1. 选择：
    1. **Platform = macOS**
    1. **配置文件类型 = 模板**
    1. **模板名称 = 自定义**

1. 选择 **"创建"**

1. 为配置文件选择一个名称，如 *此示例中的 OnboardingPackage。* 选择 **下一步**。

1. 选择DeviceComplianceOnboarding.xml *文件* 作为配置文件文件。

1. 选择 **"下一步"**

1. 在"**分配**"选项卡上，将想要部署这些配置的组添加到 ，然后选择"下一 **步"。**

1. 查看设置并选择" **创建"** 以部署配置。

### <a name="enable-system-extension"></a>启用系统扩展

1. In the **Microsoft Endpoint Manager center** select **Create Profile** under Configuration **Profiles**

1. 选择：
    1. **Platform = macOS**
    1. **配置文件类型 = 模板**
    1. **模板名称 = 扩展**

1. 选择 **"创建"**

1. 在 **"基本"** 选项卡中，为此新配置文件命名。

1. 在"**配置设置"** 选项卡中，展开 **"系统扩展"。**

1. 在 **"捆绑包标识符** 和 **团队标识符"下**，设置这些值

|捆绑包标识符  |团队标识符  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. 在"**分配**"选项卡上，将想要部署这些配置的组添加到 ，然后选择"下一 **步"。**

1. 选择 **"下一** 步"部署配置。

### <a name="get-the-installation-package"></a>获取安装包

1. 在 **"合规性中心**"**中**  >  **设置"设备载入"，** 然后选择 **"载入"。**
 
1. 对于 **"选择操作系统以开始载入过程"选择** **macOS**
 
1. 对于 **"部署"方法**，**选择"移动设备管理/Microsoft Intune**
 
1. 选择 **"下载安装程序包"。** 这将提供 *wdav.pkg* 文件。

> [!IMPORTANT]
> 部署 *wdav.pkg 之前。* 通过 Intune 打包，必须使用适用于 Mac 的 *Intune 应用* 包装工具重新格式化为 *wdav.pkg.intunemac* 格式。
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>部署 Microsoft DLP 安装包

1. 按照如何将 [macOS](/mem/intune/apps/lob-apps-macos)业务线 (LOB) 应用添加到 Microsoft Intune 中的过程将 *wdav.pkg* 文件转换为正确的格式，并通过 Intune 进行部署。

## <a name="offboard-macos-devices-using-intune"></a>使用 Intune 的载出 macOS 设备

> [!NOTE]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留六个月。

2. 在 **Microsoft Endpoint Manager中心**，打开 **"设备**  >  **配置文件"，** 你应该会看到已创建的配置文件。

1. 在配置文件 **页面中** ，选择 *wdav.pkg.intunemac* 配置文件。

1. 选择 **"** 设备状态"以查看设备列表和配置文件的部署状态

1. 打开 **属性** 和 **工作分配**

1. 从工作分配中删除组。 这将卸载 *wdav.pkg.intunemac* 程序包，然后从合规性解决方案卸载 macOS 设备。
