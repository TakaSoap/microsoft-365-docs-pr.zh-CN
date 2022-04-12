---
title: 启用Microsoft Defender for Endpoint评估
description: 启用Microsoft 365 Defender试用实验室或试点环境，包括检查许可证状态和载入终结点
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2acde87daaff88ec9ce7458218919342a9f1edd8
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782492"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>启用Microsoft Defender for Endpoint评估环境


本文将指导你完成有关使用生产设备为Microsoft Defender for Endpoint设置评估环境的步骤。 


> [!TIP]
> Microsoft Defender for Endpoint还附带了产品内评估实验室，你可以在其中添加预配置的设备并运行模拟来评估平台的功能。 该实验室附带了简化的设置体验，有助于快速展示Microsoft Defender for Endpoint的价值，包括针对高级搜寻和威胁分析等许多功能的指导。 有关详细信息，请参阅 [评估功能](../defender-endpoint/evaluation-lab.md)。 <br> 本文提供的指导与评估实验室的主要区别在于评估环境使用生产设备，而评估实验室使用非生产设备。 

使用以下步骤为Microsoft Defender for Endpoint启用评估。

:::image type="content" source="../../media/defender/m365-defender-endpoint-eval-enable-steps.png" alt-text="在 Microsoft Defender 评估环境中启用Microsoft Defender for Endpoint的步骤" lightbox="../../media/defender/m365-defender-endpoint-eval-enable-steps.png":::

- [步骤 1.检查许可证状态](#step-1-check-license-state)
- [步骤 2.载入终结点](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>步骤 1. 检查许可证状态

首先需要检查许可证状态，以验证它是否已正确预配。 可以通过管理中心或 **Microsoft Azure门户** 执行此操作。


1. 若要查看许可证，请转到 **Microsoft Azure门户** 并导航到 [Microsoft Azure门户许可证部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   :::image type="content" source="../../media/defender/atp-licensing-azure-portal.png" alt-text="Microsoft 365 Defender门户中的“Azure 许可”页" lightbox="../../media/defender/atp-licensing-azure-portal.png":::

1. 或者，在管理中心，导航到 **BillingSubscriptions** > 。

    在屏幕上，你将看到所有预配的许可证及其当前 **状态**。

    :::image type="content" source="../../media/defender/atp-billing-subscriptions.png" alt-text="Microsoft Azure门户中的“计费许可证”页" lightbox="../../media/defender/atp-billing-subscriptions.png":::
    

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步骤 2. 使用任何受支持的管理工具载入终结点

验证许可证状态是否已正确预配后，可以开始将设备载入服务。 

为了评估Microsoft Defender for Endpoint，建议选择几个Windows设备进行评估。

可以选择使用任何受支持的管理工具，但Intune提供最佳集成。 有关详细信息，请参阅[Microsoft Intune中配置Microsoft Defender for Endpoint](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune)。

[“计划”部署](../defender-endpoint/deployment-strategy.md)主题概述了部署 Defender for Endpoint 所需的常规步骤。  

观看此视频，快速了解载入过程，并了解可用的工具和方法。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>载入工具选项

下表列出了基于需要载入的终结点的可用工具。

端点 | 工具选项
:---|:---
**Windows** | [本地脚本 (多达 10 台设备，) ](../defender-endpoint/configure-endpoints-script.md)、[组策略](../defender-endpoint/configure-endpoints-gp.md)、[Microsoft Endpoint Manager/移动设备管理器](../defender-endpoint/configure-endpoints-mdm.md)、[Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md)、[VDI 脚本](../defender-endpoint/configure-endpoints-vdi.md)、[与Microsoft Defender for Cloud](../defender-endpoint/configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)
**macOS** | [本地脚本](../defender-endpoint/mac-install-manually.md)、[Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md)、[JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)、[移动设备管理](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux Server** | [本地脚本](../defender-endpoint/linux-install-manually.md)、  [Puppet](../defender-endpoint/linux-install-with-puppet.md)、  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [基于应用](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>后续步骤
[为Microsoft Defender for Endpoint设置试点](eval-defender-endpoint-pilot.md)
 
返回到[评估Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)概述

返回到评估[和试点Microsoft 365 Defender](eval-overview.md)概述
