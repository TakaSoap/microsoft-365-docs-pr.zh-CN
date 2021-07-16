---
title: 适用于终结点的试点 Defender 评估
description: 启用你的Microsoft 365 Defender试验实验室或试验环境。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457657"
---
# <a name="pilot-mde-evaluation"></a>试点 MDE 评估

>[!NOTE]
>为了引导您完成典型部署，此方案将仅涉及 Microsoft Endpoint Configuration Manager。 Defender for Endpoint 支持使用其他载入工具，但不在部署指南中介绍这些方案。 有关详细信息，请参阅 [将设备载入到 Microsoft Defender for Endpoint](onboard-configure.md)。

## <a name="step-1-check-license-state"></a>步骤 1. 检查许可证状态

可通过管理中心或管理门户检查许可证状态及其是否Microsoft Azure **设置**。

1. 若要查看许可证，请转到 Microsoft Azure **门户** 并导航到"Microsoft Azure [门户许可证"部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![Azure 许可页面的图像](images/atp-licensing-azure-portal.png)

1. 或者，在管理中心中，导航到"**帐单**  >  **""订阅"。**

    在屏幕上，你将看到所有预配的许可证及其当前 **状态**。

    ![帐单许可证的图像](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>步骤 2. 使用任何受支持的管理工具载入终结点

规划 [部署](deployment-strategy.md) 主题概述了部署 Defender for Endpoint 所需的常规步骤。  

观看此视频，快速概览载入过程并了解可用的工具和方法。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

确定体系结构后，需要决定使用哪种部署方法。 你选择的部署工具会影响将终结点载入到服务中。

### <a name="onboarding-tool-options"></a>载入工具选项

下表列出了基于需要载入的终结点的可用工具。

| 终结点     | 工具选项                       |
|--------------|------------------------------------------|
| **Windows**  |  [本地脚本 (最多 10 台设备) ](../defender-endpoint/configure-endpoints-script.md) <br> [组策略](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/移动设备管理器](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI 脚本](../defender-endpoint/configure-endpoints-vdi.md) <br> [与 Azure Defender 集成](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [本地脚本](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [移动设备管理](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [本地脚本](../defender-endpoint/linux-install-manually.md) <br> [百分百](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [基于应用](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)               |
