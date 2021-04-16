---
title: 将设备载入到 Microsoft Defender for Endpoint 服务
description: 载入 Windows 10 设备、服务器、非 Windows 设备，并了解如何运行检测测试。
keywords: 载入， 适用于终结点载入的 Microsoft Defender， windows atp 载入， sccm， 组策略， mdm， 本地脚本， 检测测试
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4aa3e30f34e7d9dc362cc0bbb277aaee5834b4fe
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861367"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>将设备载入到 Microsoft Defender for Endpoint 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

你需要转到 Defender for Endpoint 门户的载入部分，以载入任何受支持的设备。 根据设备，将指导你执行相应步骤，并提供适当的适用于设备的管理和部署工具选项。 

通常，若要将设备载入服务：

- 验证设备是否满足 [最低要求](minimum-requirements.md)
- 根据设备，按照 Defender for Endpoint 门户的载入部分中提供的配置步骤操作
- 为设备使用适当的管理工具和部署方法
- 运行检测测试，验证设备是否正确载入并报告给服务

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>载入工具选项
下表列出了基于需要载入的终结点的可用工具。

| 终结点     | 工具选项                       |
|--------------|------------------------------------------|
| **Windows**  |  [本地脚本 (最多 10 台设备) ](configure-endpoints-script.md) <br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/移动设备管理器](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md)   |
| **macOS**    | [本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md) |
| **Linux Server** | [本地脚本](linux-install-manually.md) <br> [百分百](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [基于应用](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>本节内容
主题 | 说明
:---|:---
[载入以前版本的 Windows](onboard-downlevel.md)| 将 Windows 7 和 Windows 8.1 设备载入到 Defender for Endpoint。 
[载入 Windows 10 设备](configure-endpoints.md) | 你需要载入设备，以向 Defender for Endpoint 服务报告。 了解可用于在企业中配置设备的工具和方法。
[载入服务器](configure-server-endpoints.md) |  将 Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) 版本 1803 和更高版本、Windows Server 2019 及更高版本以及 Windows Server 2019 核心版载入 Defender for Endpoint。
[载入非 Windows 设备](configure-endpoints-non-windows.md) | Defender for Endpoint 为 Windows 和非 Windows 平台提供了集中式安全操作体验。 你将能够在 Microsoft Defender 安全中心内查看各种受支持操作系统 (操作系统) 警报，并更好地保护组织的网络。 此体验利用第三方安全产品的传感器数据。 
[在新载入的设备上运行检测测试](run-detection-test.md) | 在新载入的设备上运行脚本，验证它是否正确报告给 Defender for Endpoint 服务。
[配置代理和 Internet 设置](configure-proxy-internet.md)| 通过配置代理和 Internet 连接设置，启用与 Defender for Endpoint 云服务的通信。
[解决载入问题](troubleshoot-onboarding.md) | 了解如何解决载入期间可能出现的问题。

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
