---
title: 将非 Windows 设备载入 Microsoft Defender for Endpoint 服务
description: 配置非 Windows 设备，以便它们可以将传感器数据发送到 Microsoft Defender ATP 服务。
keywords: 载入非 Windows 设备， macos， linux， 设备管理， 配置 Windows ATP 设备， 为终结点设备配置 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687873"
---
# <a name="onboard-non-windows-devices"></a>载入非 Windows 设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**
- macOS
- Linux

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint 为 Windows 和非 Windows 平台提供了集中式安全操作体验。 你将能够在 Microsoft Defender 安全中心内查看各种受支持操作系统 (操作系统) 警报，并更好地保护组织的网络。 

你需要了解与 Defender for Endpoint 兼容的确切的 Linux 发行版和 macOS 版本，集成工作。 有关详细信息，请参阅：
- [Linux 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-linux.md#system-requirements)  
- [macOS 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-mac.md#system-requirements)。

## <a name="onboarding-non-windows-devices"></a>载入非 Windows 设备
你需要执行以下步骤来载入非 Windows 设备：
1. 选择你的首选载入方法：

   - 对于 macOS 设备，你可以选择通过 Microsoft Defender ATP 或第三方解决方案载入。 有关详细信息，请参阅[Microsoft Defender for Endpoint for Mac。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - 对于其他非 Windows 设备，选择通过第三方集成载入 **非 Windows 设备**。   
    1. 在导航窗格中，选择 **互操作性**  >  **合作伙伴**。 确保列出了第三方解决方案。
    2. 在 **"合作伙伴应用程序"** 选项卡中，选择支持非 Windows 设备的合作伙伴。
    3. 选择 **"打开合作伙伴** 页面"以打开合作伙伴的页面。 按照页面上提供的说明进行操作。
    4. 创建帐户或订阅合作伙伴解决方案后，应进入一个阶段，要求贵组织的租户全局管理员接受来自合作伙伴应用程序的权限请求。 仔细阅读权限请求，确保它与所需的服务保持一致。 

        
2. 按照第三方解决方案的说明运行检测测试。

## <a name="offboard-non-windows-devices"></a>载出非 Windows 设备

1. 按照第三方文档将第三方解决方案与 Microsoft Defender for Endpoint 断开连接。

2. 删除 Azure AD 租户中第三方解决方案的权限。
   1. 登录到 [Azure 门户](https://portal.azure.com)。
   2. 选择 **"Azure Active Directory >企业应用程序"。**
   3. 选择要离开的应用程序。
   4. 选择" **删除"** 按钮。


## <a name="related-topics"></a>相关主题
- [载入 Windows 10 设备](configure-endpoints.md)
- [载入服务器](configure-server-endpoints.md)
- [配置代理和 Internet 连接设置](configure-proxy-internet.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
