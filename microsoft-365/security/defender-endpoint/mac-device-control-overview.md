---
title: macOS 的设备控件
description: 了解如何在 Mac 上配置 Microsoft Defender for Endpoint 以减少来自可移动存储（如 USB 设备）的威胁。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 设备， 控件， usb， 可移动， 媒体
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cb41b0bd3f185237055daa2d282f0a1d6975a49
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765536"
---
# <a name="device-control-for-macos"></a>macOS 的设备控件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="requirements"></a>要求

macOS 的设备控件具有以下先决条件：

> [!div class="checklist"]
>
> - Microsoft Defender for Endpoint (可以试用) 
> - 最低操作系统版本：macOS 11 或更高版本
> - 最低产品版本：101.34.20

## <a name="device-control-policy"></a>设备控制策略

若要为 macOS 配置设备控制，必须创建一个策略，描述要在你的组织中实施的限制。

设备控制策略包含在用于配置所有其他产品设置的配置文件中。 有关详细信息，请参阅配置 [配置文件结构](mac-preferences.md#configuration-profile-structure)。

在配置文件中，设备控制策略在下一节中定义：

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|deviceControl|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

设备控制策略可用于：

- [自定义由设备控件引发通知的 URL 目标](#customize-url-target-for-notifications-raised-by-device-control)
- [允许或阻止可移动设备](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>自定义由设备控件引发通知的 URL 目标

例如，如果已实施的设备控制策略在设备上强制执行 (例如，对可移动媒体设备的访问权限受限) ，则向用户显示一条通知。

![设备控制通知。](images/mac-device-control-notification.png)

当最终用户单击此通知时，在默认浏览器中打开一个网页。 您可以配置最终用户单击通知时打开的 URL。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|navigationTarget|
|**数据类型**|字符串|
|**Comments**|如果未定义，产品将使用指向说明产品所采取操作的通用页面的默认 URL。|
|

### <a name="allow-or-block-removable-devices"></a>允许或阻止可移动设备

设备控制策略的可移动媒体部分用于限制对可移动媒体的访问。

> [!NOTE]
> 当前支持以下类型的可移动媒体，并且可包含在策略中：USB 存储设备。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|removableMediaPolicy|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

该策略的这一部分是分层的，允许实现最大灵活性并涵盖各种用例。 顶级是供应商，由供应商 ID 标识。 对于每个供应商，都有由产品 ID 标识的产品。 最后，对于每个产品，都有表示特定设备的序列号。

```text
|-- policy top level
    |-- vendor 1
        |-- product 1
            |-- serial number 1
            ...
            |-- serial number N
        ...
        |-- product N
    ...
    |-- vendor N
```

若要了解如何查找设备标识符，请参阅查找 [设备标识符](#look-up-device-identifiers)。

策略从最具体的条目到最常规的条目进行评估。 这意味着，当插入设备时，产品会尝试在每个可移动媒体设备的策略中查找最具体的匹配项，并应用该级别的权限。 如果没有匹配项，则应用下一个最佳匹配，一切都将应用到顶级指定的权限，当设备不匹配策略中的其他任何条目时，这是默认设置。

#### <a name="policy-enforcement-level"></a>策略执行级别

在可移动媒体部分下，有一个选项可以设置强制级别，它可以接受下列值之一：

- `audit` - 在此强制级别下，如果对设备的访问权限受到限制，则向用户显示一条通知，但是仍可以使用该设备。 此强制级别可用于评估策略的有效性。
- `block` - 在此强制级别下，用户可以在设备上执行的操作仅限于策略中定义的操作。 此外，会向用户引发通知。

> [!NOTE]
> 默认情况下，强制级别设置为 `audit`。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|enforcementLevel|
|**数据类型**|String|
|**可能的值**|审核 (默认)  <p> block|
|

#### <a name="default-permission-level"></a>默认权限级别

在可移动媒体部分的顶部，你可以为与策略中任何其他内容不匹配的设备配置默认权限级别。

此设置可以设置为：

- `none` - 无法对设备执行任何操作
- 以下值的组合：
  - `read` - 允许对设备执行读取操作
  - `write` - 允许对设备执行写入操作
  - `execute` - 允许对设备执行操作

> [!NOTE]
> 如果 `none` 权限级别存在 ，则 `read`忽略其他 (、 `write`或) `execute` 权限。
>
> 权限 `execute` 仅指执行 Mach-O 二进制文件。 它不包括脚本或其他类型的有效负载的执行。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|permission|
|**数据类型**|字符串数组|
|**可能的值**|无 <p> 阅读 <p> 写入 <p> execute|
|

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>按供应商、产品和序列号限制可移动媒体

如允许 [或阻止](#allow-or-block-removable-devices)可移动设备中所述，USB 设备等可移动媒体可以通过供应商 ID、产品 ID 和序列号进行标识。

在可移动媒体策略的顶层，可以选择在供应商级别定义更精细的限制。

字典 `vendors` 包含一个或多个条目，每个条目由供应商 ID 标识。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|供应商|
|**数据类型**|字典 (嵌套首选项) |
|

对于每个供应商，你可以为来自该供应商的设备指定所需的权限级别。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|permission|
|**数据类型**|字符串数组|
|**可能的值**|与默认 [权限级别相同](#default-permission-level)|
|

此外，还可以选择指定属于已定义更精细权限的供应商的产品集。 字典 `products` 包含一个或多个条目，每个条目由产品 ID 标识。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|products|
|**数据类型**|字典 (嵌套首选项) |
|

对于每个产品，您可以为该产品指定所需的权限级别。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|permission|
|**数据类型**|字符串数组|
|**可能的值**|与默认 [权限级别相同](#default-permission-level)|
|

此外，还可以指定一组可选的序列号，为这些序列号定义更精细的权限。

词典 `serialNumbers` 包含一个或多个条目，每个条目由序列号标识。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|serialNumbers|
|**数据类型**|字典 (嵌套首选项) |
|

对于每个序列号，您可以指定所需的权限级别。

<br>

****

|节|值|
|---|---|
|**域**|`com.microsoft.wdav`|
|**键**|permission|
|**数据类型**|字符串数组|
|**可能的值**|与默认 [权限级别相同](#default-permission-level)|
|

#### <a name="example-device-control-policy"></a>示例设备控制策略

以下示例演示如何将上述所有概念组合到设备控制策略中。 在下面的示例中，请注意可移动媒体策略的层次结构特性。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>navigationTarget</key>
        <string>[custom URL for notifications]</string>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>[enforcement level]</string> <!-- audit / block -->
            <key>permission</key>
            <array>
                <string>[permission]</string> <!-- none / read / write / execute -->
                <!-- other permissions -->
            </array>
            <key>vendors</key>
            <dict>
                <key>[vendor id]</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>[permission]</string> <!-- none / read / write / execute -->
                        <!-- other permissions -->
                    </array>
                    <key>products</key>
                    <dict>
                        <key>[product id]</key>
                        <dict>
                            <key>permission</key>
                            <array>
                                <string>[permission]</string> <!-- none / read / write / execute -->
                                <!-- other permissions -->
                            </array>
                            <key>serialNumbers</key>
                            <dict>
                                <key>[serial-number]</key>
                                <array>
                                    <string>[permission]</string> <!-- none / read / write / execute -->
                                    <!-- other permissions -->
                                </array>
                                <!-- other serial numbers -->
                            </dict>
                        </dict>
                        <!-- other products -->
                    </dict>
                </dict>
                <!-- other vendors -->
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

我们在以下文档中包含了更多设备控制策略示例：

- [Intune 的设备控制策略示例](mac-device-control-intune.md)
- [JAMF 的设备控制策略示例](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>查找设备标识符

若要查找 USB 设备的供应商 ID、产品 ID 和序列号，请执行以下操作：

1. 登录到 Mac 设备。
1. 插入要查找其标识符的 USB 设备。
1. 在 macOS 的顶级菜单中，选择" **关于此 Mac"**。

    ![关于此 Mac。](images/mac-device-control-lookup-1.png)

1. 选择 **"系统报告"**。

    ![系统报告。](images/mac-device-control-lookup-2.png)

1. 从左侧列中，选择 **USB**。

    ![所有 USB 设备的视图。](images/mac-device-control-lookup-3.png)

1. 在 **"USB 设备树**"下，导航到插入的 USB 设备。

    ![USB 设备的详细信息。](images/mac-device-control-lookup-4.png)

1. 将显示供应商 ID、产品 ID 和序列号。 将供应商 ID 和产品 ID 添加到可移动媒体策略时，必须仅在 之后添加部件 `0x`。 例如，在下图中，供应商 ID 为 ， `1000` 产品 ID 为 `090c`。

#### <a name="discover-usb-devices-in-your-organization"></a>发现你的组织的 USB 设备

你可以查看源自 Microsoft Defender for Endpoint 高级搜寻中的 USB 设备的装入、卸载和卷更改事件。 这些事件有助于识别可疑的使用活动或执行内部调查。

```bash
DeviceEvents
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>设备控制策略部署

设备控制策略必须包含在其他产品设置旁边，如在 [macOS 上设置 Microsoft Defender for Endpoint 的首选项中所述](mac-preferences.md)。

可以使用配置文件部署中列出的说明部署 [此配置文件](mac-preferences.md#configuration-profile-deployment)。

## <a name="troubleshooting-tips"></a>疑难解答提示

在通过 Intune 或 JAMF 推送配置文件后，可以通过从终端运行以下命令来检查产品是否成功选取配置文件：

```bash
mdatp device-control removable-media policy list
```

此命令将输出到产品使用的设备控制策略的标准输出。 `Policy is empty`如果打印，请确保 (配置文件) 配置文件确实已从管理控制台推送到设备， (b) 它是一个有效的设备控制策略，如本文档中所述。

在策略已成功传递且插入了一个或多个设备的设备上，可以运行以下命令列出所有设备以及应用于它们的有效权限。

```bash
mdatp device-control removable-media devices list
```

输出示例：

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

在以上示例中，只有一`read``execute`个已插入的可移动媒体设备，并且根据已传递到该设备的设备控制策略具有和权限。

## <a name="related-topics"></a>相关主题

- [Intune 的设备控制策略示例](mac-device-control-intune.md)
- [JAMF 的设备控制策略示例](mac-device-control-jamf.md)
