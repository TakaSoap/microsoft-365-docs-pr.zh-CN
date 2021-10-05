---
title: 将设备载入到 Microsoft Defender for Endpoint 服务
description: 载入Windows设备、服务器、Windows设备，并了解如何运行检测测试。
keywords: 载入， Microsoft Defender for Endpoint onboarding， sccm， 组策略， mdm， 本地脚本， 检测测试
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
ms.openlocfilehash: 49109b7671cc4ecd1891cb942dcd6b678d7b5c11
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124525"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>将设备载入到 Microsoft Defender for Endpoint 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

你需要转到 Defender for Endpoint 门户的载入部分，以载入任何受支持的设备。 根据设备，将指导你执行相应步骤，并提供适当的适用于设备的管理和部署工具选项。

通常，若要将设备载入服务：

- 验证设备是否满足 [最低要求](minimum-requirements.md)
- 根据设备，按照 Defender for Endpoint 门户的载入部分中提供的配置步骤操作
- 为设备使用适当的管理工具和部署方法
- 运行检测测试，验证设备是否正确载入并报告给服务

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>载入工具选项

下表列出了基于需要载入的终结点的可用工具。

|端点|工具选项|
|---|---|
|**Windows**|[本地脚本 (最多 10 台设备) ](configure-endpoints-script.md) <p> [组策略](configure-endpoints-gp.md) <p> [Microsoft Endpoint Manager/移动设备管理器](configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <p> [VDI 脚本](configure-endpoints-vdi.md) <p> [与 Azure Defender 集成](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[本地脚本](mac-install-manually.md) <p> [Microsoft Endpoint Manager](mac-install-with-intune.md) <p> [JAMF Pro](mac-install-with-jamf.md) <p> [移动设备管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[本地脚本](linux-install-manually.md) <p> [百分百](linux-install-with-puppet.md) <p> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[基于应用](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](android-intune.md)|

## <a name="in-this-section"></a>本节内容

主题|说明
:---|:---
[载入以前版本的 Windows](onboard-downlevel.md)|将 Windows 7 和 Windows 8.1设备载入到 Defender for Endpoint。
[载入Windows设备](configure-endpoints.md)|你需要载入设备，以向 Defender for Endpoint 服务报告。 了解可用于在企业中配置设备的工具和方法。
[载入服务器](configure-server-endpoints.md)|将 Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) 版本 1803 和更高版本、Windows Server 2019 及更高版本以及 Windows Server 2019 核心版本载入 Defender for Endpoint。
[载入非 Windows 设备](configure-endpoints-non-windows.md)|Defender for Endpoint 为用户和非 Windows平台提供了集中式安全Windows体验。 你将能够查看来自各种受支持操作系统 (操作系统) Microsoft Defender 安全中心更好地保护组织的网络。 此体验利用第三方安全产品的传感器数据。
[在新载入的设备上运行检测测试](run-detection-test.md)|在新载入的设备上运行脚本，验证它是否正确报告给 Defender for Endpoint 服务。
[配置代理和 Internet 设置](configure-proxy-internet.md)|通过配置代理和 Internet 连接设置，启用与 Defender for Endpoint 云服务的通信。
[解决载入问题](troubleshoot-onboarding.md)|了解如何解决载入期间可能出现的问题。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)。
