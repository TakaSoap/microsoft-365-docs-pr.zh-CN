---
title: 载入至 Microsoft Defender for Endpoint 服务
description: 了解如何将终结点载入到 Microsoft Defender for Endpoint 服务
keywords: microsoft defender for endpoint， onboard， deploy
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e56bb5f8647e9504c18fdc280b8e85b9764bc6c4
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124270"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>载入至 Microsoft Defender for Endpoint 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

了解部署 Microsoft Defender for Endpoint 的各个阶段以及如何在解决方案中配置功能。

部署适用于终结点的 Defender 的过程分三个阶段：

|[![部署阶段 - 准备。](images/phase-diagrams/prepare.png)](prepare-deployment.md) <br> [阶段 1：准备](prepare-deployment.md)|[![部署阶段 - 设置](images/phase-diagrams/setup.png)](production-deployment.md) <br> [阶段 2：设置](production-deployment.md)|![部署阶段 - 载入](images/phase-diagrams/onboard.png) <br> 阶段 3：开始使用|
|---|---|---|
|||*你在这里！*|

你当前处于载入阶段。

部署适用于终结点的 Defender 需要执行以下步骤：

- 步骤 1：将终结点载入服务
- 步骤 2: 配置功能

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步骤 1：使用任何受支持的管理工具载入终结点

规划 [部署](deployment-strategy.md) 主题概述了部署 Defender for Endpoint 所需的一般步骤。

观看此视频，快速概览载入过程并了解可用的工具和方法。


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

确定体系结构后，需要决定使用哪种部署方法。 你选择的部署工具会影响将终结点载入到服务中。

### <a name="onboarding-tool-options"></a>载入工具选项

下表列出了基于需要载入的终结点的可用工具。

|端点|工具选项|
|---|---|
|**Windows**|[本地脚本 (最多 10 台设备) ](configure-endpoints-script.md) <br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ 移动设备管理器](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md) <br> [与 Azure Defender 集成](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[本地脚本](linux-install-manually.md) <br> [百分百](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[基于应用](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](android-intune.md)|

## <a name="step-2-configure-capabilities"></a>步骤 2: 配置功能

载入终结点后，你将配置各种功能，如终结点检测和响应、下一代保护和攻击面减少。

## <a name="example-deployments"></a>部署示例

在此部署指南中，我们将指导你使用两个部署工具载入终结点以及如何配置功能。

示例部署中的工具包括：

- [使用 Microsoft Endpoint Configuration Manager 载入](onboarding-endpoint-configuration-manager.md)
- [使用 Microsoft Endpoint Manager 载入](onboarding-endpoint-manager.md)

然后，使用上面提到的部署工具，指导你配置以下 Defender for Endpoint 功能：

- 终结点检测和响应配置
- 下一代保护配置
- 攻击面减少配置

## <a name="related-topics"></a>相关主题

- [使用 Microsoft Endpoint Configuration Manager 载入](onboarding-endpoint-configuration-manager.md)
- [使用 Microsoft Endpoint Manager 载入](onboarding-endpoint-manager.md)
- [Microsoft 365 E5 中的安全文档](../office-365-security/safe-docs.md)
