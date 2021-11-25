---
title: 在 Mac 上部署 Microsoft Defender for Endpoint 更新
description: 控制企业环境中 Mac 上的 Microsoft Defender for Endpoint 的更新。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 更新， 部署
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ee8ea26c53bf5ae56c558f7aaa956974474dd101
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171433"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上部署 Microsoft Defender for Endpoint 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。

若要更新 macOS 上的 Microsoft Defender for Endpoint，使用名为 Microsoft AutoUpdate (MAU) 程序。 默认情况下，MAU 每天自动检查更新，但你可以将更新更改为每周、每月或手动。

![MAU 屏幕截图。](images/MDATP-34-MAU.png)

如果决定使用软件分发工具部署更新，应配置 MAU 以手动检查软件更新。 你可以部署首选项，以配置 MAU 检查组织中 Mac 更新方式和检查时间。

## <a name="use-msupdate"></a>使用 msupdate

MAU 包括一个称为 *msupdate* 的命令行工具，该工具专为 IT 管理员设计，以便他们可以更精确地控制何时应用更新。 有关如何使用此工具的说明，请参阅 Update Office for Mac [by using msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate)。

在 MAU 中，macOS 上的 Microsoft Defender for Endpoint 的应用程序标识符是 *WDAV00*。 若要在 macOS 上下载并安装 Microsoft Defender for Endpoint 的最新更新，请从"终端"窗口执行以下命令：

```dos
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>设置 Microsoft AutoUpdate 的首选项

本节介绍可用于配置 MAU 的最常见首选项。 可以通过企业使用的管理控制台将这些设置部署为配置文件。 以下各节显示了配置文件的示例。

### <a name="set-the-channel-name"></a>设置频道名称

通道确定通过 MAU 提供的更新的类型和频率。 中的设备可以在 和 中的设备 `Beta` 之前试用 `Preview` 新功能 `Current` 。

`Current`渠道包含最稳定的产品版本。

> [!IMPORTANT]
> 在 Microsoft AutoUpdate 版本 4.29 之前，频道具有不同的名称：
>
> - `Beta` 已 (`InsiderFast` Insider Fast) 
> - `Preview` 被命名为 `External` (Insider Slow) 
> - `Current` 已命名 `Production`

> [!TIP]
> 为了预览新功能并提供早期反馈，建议将企业中某些设备配置为 `Beta` 或 `Preview` 。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|ChannelName|
|**数据类型**|String|
|**可能的值**|Beta <p> 预览 <p> Current|
|||

> [!WARNING]
> 此设置更改通过 Microsoft AutoUpdate 更新的所有应用程序的通道。 若要仅为 macOS 上的 Microsoft Defender for Endpoint 更改通道，在将 替换为所需通道后执行 `[channel-name]` 以下命令：
>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>设置更新检查频率

更改 MAU 搜索更新频繁。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|UpdateCheckFrequency|
|**数据类型**|整数|
|**默认值**|720 (分钟) |
|**Comment**|此值以分钟数设置。|
|||

### <a name="change-how-mau-interacts-with-updates"></a>更改 MAU 与更新的交互方式

更改 MAU 搜索更新时如何。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|HowToCheck|
|**数据类型**|String|
|**可能的值**|手动 <p> AutomaticCheck <p> AutomaticDownload|
|**Comment**|请注意，如果可能，AutomaticDownload 将执行下载并静默安装。|
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>更改"检查更新"按钮是否已启用

更改本地用户是否可以单击 Microsoft AutoUpdate 用户界面中的"检查更新"选项。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|EnableCheckForUpdatesButton|
|**数据类型**|Boolean|
|**可能的值**|为 (默认值)  <p> False|
|||

### <a name="disable-insider-checkbox"></a>禁用预览体验成员复选框

设置为 true 将"加入 Office预览体验计划..."。复选框不可用/灰度为用户。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|DisableInsiderCheckbox|
|**数据类型**|Boolean|
|**可能的值**|False (默认值)  <p> True|
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>限制从 MAU 发送的遥测

设置为 false 可发送最小检测信号数据、无应用程序使用情况和无环境详细信息。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.autoupdate2`|
|**键**|SendAllTelemetryEnabled|
|**数据类型**|布尔值|
|**可能的值**|为 (默认值)  <p> False|
|||

## <a name="example-configuration-profile"></a>配置文件示例

以下配置文件用于：

- 将设备放在生产渠道中
- 自动下载和安装更新
- 在用户界面中启用"检查更新"按钮
- 允许设备上的用户注册预览体验成员频道

> [!WARNING]
> 以下配置是一个示例配置，如果不适当审阅设置和定制配置，则不应在生产中使用。

> [!TIP]
> 为了预览新功能并提供早期反馈，建议将企业中某些设备配置为 `Beta` 或 `Preview` 。

### <a name="jamf"></a>JAMF

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

### <a name="intune"></a>Intune

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

若要配置 MAU，可以从企业使用的管理工具部署此配置文件：

- 从 JAMF 中，上传此配置文件，将首选项域设置为 *com.microsoft.autoupdate2*。
- 从 Intune 中，上载此配置文件，将自定义配置文件名称设置为 *com.microsoft.autoupdate2*。

## <a name="resources"></a>资源

- [msupdate 参考](/deployoffice/mac/update-office-for-mac-using-msupdate)
