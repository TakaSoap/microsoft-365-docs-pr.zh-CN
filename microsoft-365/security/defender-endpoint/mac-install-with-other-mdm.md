---
title: 使用适用于 Mac 上的 Microsoft Defender for Endpoint 的不同移动设备 (MDM) 系统的部署
description: 在其他管理解决方案上，在 Mac 上安装 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， macos， 加泰罗尼亚语， mojave， 高
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d89d98e6e972707266f3b3ed95db3b78b8a5d161
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159434"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上为 Microsoft Defender for Endpoint (MDM) 部署不同的移动设备管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。
 
## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

在开始使用之前，请参阅 [macOS](microsoft-defender-endpoint-mac.md) 上的 Microsoft Defender for Endpoint 主页，了解当前软件版本的先决条件和系统要求说明。


## <a name="approach"></a>方法

> [!CAUTION]

> 目前，Microsoft 正式仅支持 Intune 和 JAMF 在 macOS 上部署和管理 Microsoft Defender for Endpoint。 Microsoft 对下面提供的信息不做出明示或暗示的担保。

如果你的组织使用未正式支持的移动设备管理 (MDM) 解决方案，这并不意味着你无法在 macOS 上部署或运行 Microsoft Defender for Endpoint。

macOS 上的 Microsoft Defender for Endpoint 不依赖于任何特定于供应商的功能。 它可以与支持以下功能的任何 MDM 解决方案一同使用：

- 将 macOS .pkg 部署到托管设备。
- 将 macOS 系统配置文件部署到托管设备。
- 在托管设备上运行任意管理员配置的工具/脚本。

大多数现代 MDM 解决方案都包括这些功能，但是，它们调用它们的方式可能不同。

但是，你可以部署 Defender，无需上述列表中的最后一项要求：

- 无法集中收集状态
- 如果你决定卸载 Defender，你将需要以管理员角色在本地登录到客户端设备

## <a name="deployment"></a>部署

大多数 MDM 解决方案都使用相同的模型来管理 macOS 设备，使用类似的术语。 将 [基于 JAMF 的部署](mac-install-with-jamf.md) 用作模板。

### <a name="package"></a>程序包

配置所需应用程序[包](mac-install-with-jamf.md)的部署，安装包 (wdav.pkg) 从 Microsoft 365 Defender[门户下载](mac-install-with-jamf.md)。

若要将程序包部署到企业，请使用与 MDM 解决方案关联的说明。

### <a name="license-settings"></a>许可证设置

设置 [系统配置文件](mac-install-with-jamf.md)。 

MDM 解决方案可能称其为"自定义设置配置文件"，因为 macOS 上的 Microsoft Defender for Endpoint 不是 macOS 的一部分。

使用属性列表 jamf/WindowsDefenderATPOnboarding.plist，可从从 Microsoft 365 Defender 门户下载的载入[包中提取](mac-install-with-jamf.md)。
您的系统可能支持 XML 格式的任意属性列表。 在这种情况下，你可以像现在一样上传 jamf/WindowsDefenderATPOnboarding.plist 文件。
或者，可能需要先将属性列表转换为其他格式。

通常，自定义配置文件具有 ID、名称或域属性。 必须完全使用"com.microsoft.wdav.atp"作为此值。
MDM 使用它将设置文件部署到客户端设备的 **/Library/Managed Preferences/com.microsoft.wdav.atp.plist，** 而 Defender 使用此文件加载载入信息。

### <a name="kernel-extension-policy"></a>内核扩展策略

设置 KEXT 或内核扩展策略。 使用团队标识符 **UBF8T346G9** 允许 Microsoft 提供的内核扩展。

> [!CAUTION]
> 如果你的环境包含 Apple 芯片 (M1) 设备，则这些计算机不应接收包含 KEXT 策略的配置文件。
> Apple 在这些计算机上不支持 KEXT，在 M1 计算机上部署此类配置文件将失败。

### <a name="system-extension-policy"></a>系统扩展策略

设置系统扩展策略。 使用团队标识符 **UBF8T346G9** 并批准以下捆绑包标识符：

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>完全磁盘访问策略

授予对以下组件的完全磁盘访问权限：

- Microsoft Defender for Endpoint
    - 标识符： `com.microsoft.wdav`
    - 标识符类型：捆绑包 ID
    - 代码要求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Microsoft Defender for Endpoint Security Extension
    - 标识符： `com.microsoft.wdav.epsext`
    - 标识符类型：捆绑包 ID
    - 代码要求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>网络扩展策略

作为终结点检测和响应功能的一部分，macOS 上的 Microsoft Defender for Endpoint 会检查套接字流量，将此信息报告给 Microsoft 365 Defender 门户。 以下策略允许网络扩展执行此功能。

- 筛选器类型：插件
- 插件捆绑包标识符： `com.microsoft.wdav`
- 筛选数据提供程序捆绑包标识符： `com.microsoft.wdav.netext`
- 筛选数据提供程序指定的要求： `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- 筛选器套接字： `true`

## <a name="check-installation-status"></a>检查安装状态

在 [客户端设备上运行 Microsoft Defender for Endpoint](mac-install-with-jamf.md) 以检查载入状态。
