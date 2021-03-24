---
title: 使用适用于 Mac 的 Microsoft Defender ATP (MDM) 不同的移动设备管理部署
description: 在其他管理解决方案上安装 Microsoft Defender ATP for Mac。
keywords: microsoft， defender， atp， mac， 安装， 部署， macos， 加泰罗尼亚语， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 28e57f1749ea9dce22e1a8a210f73cc3c7993738
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056103"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a>使用适用于 Mac 的 Microsoft Defender for Endpoint (MDM) 系统部署不同的移动设备管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

在开始使用之前，请参阅 [主 Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) 页面，了解当前软件版本的先决条件和系统要求。

## <a name="approach"></a>方法

> [!CAUTION]
> 目前，Microsoft 仅支持 Intune 和 JAMF 部署和管理 Microsoft Defender for Endpoint for Mac。 Microsoft 对下面提供的信息不做出明示或暗示的担保。

如果你的组织使用未正式支持的移动设备管理 (MDM) 解决方案，这并不意味着你无法部署或运行 Microsoft Defender for Endpoint for Mac。

适用于 Mac 的 Microsoft Defender for Endpoint 不依赖于任何供应商特定的功能。 它可以与支持以下功能的任何 MDM 解决方案一同使用：

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

配置所需应用程序 [包](mac-install-with-jamf.md)的部署，安装程序包 (wdav.pkg) [从 Microsoft Defender 安全中心下载](mac-install-with-jamf.md)。

若要将程序包部署到企业，请使用与 MDM 解决方案关联的说明。

### <a name="license-settings"></a>许可证设置

设置 [系统配置文件](mac-install-with-jamf.md)。 MDM 解决方案可能称其为"自定义设置配置文件"，因为适用于 Mac 的 Microsoft Defender for Endpoint 不是 macOS 的一部分。

使用属性列表 jamf/WindowsDefenderATPOnboarding.plist，可从从 Microsoft Defender 安全中心下载的载入 [包中提取](mac-install-with-jamf.md)。
您的系统可能支持 XML 格式的任意属性列表。 在这种情况下，你可以像现在一样上传 jamf/WindowsDefenderATPOnboarding.plist 文件。
或者，可能需要先将属性列表转换为其他格式。

通常，自定义配置文件具有 ID、名称或域属性。 必须完全使用"com.microsoft.wdav.atp"作为此值。
MDM 使用它将设置文件部署到客户端设备的 **/Library/Managed Preferences/com.microsoft.wdav.atp.plist，Defender** 使用此文件加载载入信息。

### <a name="kernel-extension-policy"></a>内核扩展策略

设置 KEXT 或内核扩展策略。 使用团队标识符 **UBF8T346G9** 允许 Microsoft 提供的内核扩展。

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

作为终结点检测和响应功能的一部分，Microsoft Defender for Mac 终结点会检查套接字流量，将此信息报告给 Microsoft Defender 安全中心门户。 以下策略允许网络扩展执行此功能。

- 筛选器类型：插件
- 插件捆绑包标识符： `com.microsoft.wdav`
- 筛选数据提供程序捆绑包标识符： `com.microsoft.wdav.netext`
- 筛选数据提供程序指定的要求： `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- 筛选器套接字： `true`

## <a name="check-installation-status"></a>检查安装状态

在 [客户端设备上运行 Microsoft Defender for Endpoint](mac-install-with-jamf.md) 以检查载入状态。
