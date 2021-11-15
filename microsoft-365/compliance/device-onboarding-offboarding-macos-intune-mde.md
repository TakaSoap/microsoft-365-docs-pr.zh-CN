---
title: '使用 Microsoft Defender for Endpoint 客户的 Microsoft Intune 将 macOS 设备载入和 (预览版) '
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
description: '了解如何使用适用于 MDE Microsoft 365预览版中的 MDE Microsoft Intune将 macOS (载入和) '
ms.openlocfilehash: a1d647fae55b091b8c12df885ce28aa4f1275a1a
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962995"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview"></a>使用适用于 Microsoft Defender for Endpoint 客户的 Intune 将 macOS 设备载入和卸载到合规性解决方案（预览版）

> [!IMPORTANT]
> 如果你 ***将*** Microsoft Defender for Endpoint (MDE) macOS 设备，请使用此过程

<!--## Get registered

To get access to this feature, you must register your tenant with Microsoft. See, [get registered for Microsoft 365 macOS support](https://aka.ms/EndpointDLPIgnite21-Previews).-->

**适用于：**

- 将 MDE 部署到其 macOS 设备的客户。
- [Microsoft 365终结点数据丢失防护 （DLP）](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>准备工作

- 确保你的[macOS 设备已载入 Intune，](/mem/intune/fundamentals/deployment-guide-platform-macos)并注册了公司门户[应用](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
- 确保你有权访问Microsoft Endpoint Manager[中心](https://endpoint.microsoft.com/#home)
- 这支持 macOS 版本 Catalina 10.15 及更高版本
- 在 macOS 设备上安装 v95+ Edge 浏览器 

## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>使用 Microsoft 365 将 macOS 设备载入到 Microsoft Intune

使用以下步骤将 macOS 设备载入合规性解决方案（如果已经部署了 MDE）。

1. 此过程需要这些文件。

|文件所需的 |source |
|---------|---------|
|辅助功能 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
完全磁盘访问     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> 您可以单独下载 *.mobileconfig* 文件，也可以将这些文件下载到包含以下项的 [单个](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 组合文件中：
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> 
>
>如果其中任何一个文件已更新，则需要再次下载组合的文件或单独下载单个更新的文件。

### <a name="create-system-configuration-profiles"></a>创建系统配置文件

1. 打开Microsoft Endpoint Manager  >  **中心"设备**  >  **配置文件"。**

1. 选择： **创建配置文件**。 

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

1. 打开 **设备**  >  **配置文件，** 你应该会看到你创建的配置文件。

1. 在 **"配置文件"** 页中，选择刚创建的配置文件（此示例中为 *AccessibilityformacOS）* 并选择"设备状态"以查看设备列表和配置文件的部署状态。

### <a name="update-configuration-profiles"></a>更新配置文件

1. 使用 **fulldisk.mobileconfig** 文件更新现有完整磁盘访问配置文件。

1. 使用这些值更新 exisiting MDE 首选项配置文件
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```

## <a name="offboard-macos-devices-using-intune"></a>使用 Intune 的载出 macOS 设备

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

1. 在 **Microsoft Endpoint Manager中心**，打开 **设备**  >  **配置文件**，你应该会看到你已创建的配置文件。

2. 在配置文件 **页** 中，选择 MDE 首选项配置文件。

1. 删除这些设置：
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```
3. **保存**。