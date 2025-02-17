---
title: 步骤 6. 监视设备风险和对安全基线的符合性
ms.author: bcarter
author: brendacarter
f1.keywords:
- connect Intune to Defender
- monitor device risk
- monitor device compliance
- deploy security baselines
manager: dougeby
audience: ITPro
description: 了解如何将 Microsoft Intune 连接到 Defender for Endpoint，并监视设备风险作为访问条件。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- deploy security baselines
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: af165f3565e3601ac4e8118535af3913c2cb2af8
ms.sourcegitcommit: 6fefc15dd78139316597083b702286097d45d4dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64737439"
---
# <a name="step-6-monitor-device-risk-and-compliance-to-security-baselines"></a>步骤 6. 监视设备风险和对安全基线的符合性

组织部署 Microsoft Defender for Endpoint 后，可以通过将 Microsoft Intune 与 Defender for Endpoint 集成来获得更深入的见解和设备保护。 对于移动设备，这包括监视设备风险作为访问条件的功能。 对于 Windows 设备，可以监视这些设备对安全基线的符合性。 

部署 Microsoft Defender for Endpoint 包括载入终结点。 如果使用 Intune 载入终结点 (推荐)，则已将 Microsoft Intune 连接到 Defender for Endpoint。 如果使用其他方法将终结点载入 Defender for Endpoint，请参阅 [在 Intune 中配置 Microsoft Defender for Endpoint](/mem/intune/protect/advanced-threat-protection-configure) 以确保已在 Intune 和 Microsoft Defender for Endpoint 之间设置服务到服务连接。 


![Defender for Endpoint 和 Microsoft Intune 集成图示](../media/devices/devices-defender-for-endpoint-steps.png#lightbox)

在此图中：
- Microsoft Defender for Endpoint 大大提高了设备威胁防护的复杂性。 
- 虽然 Microsoft Intune 允许你设置应用保护策略和管理设备（包括配置更改），但 Defender for Endpoint 会持续监视设备是否存在威胁，并可以采取自动措施来修正攻击。 
- 可以将 Microsoft Intune 连接到 Defender for Endpoint，以监视设备风险以及安全基线的合规性。

本文包括以下步骤：
- 监视设备风险
- 监视对安全基线的符合性

如果尚未设置 Defender for Endpoint，请与威胁防护管理员协作[设置评估和试点环境](../security/defender/eval-defender-endpoint-overview.md)。 可以与试点组合作，试用本文中的功能。

## <a name="monitor-device-risk-as-a-condition-for-access"></a>监视设备风险作为访问条件

部署 Microsoft Defender for Endpoint 后，可以利用威胁风险信号。 这允许你根据设备的风险评分阻止对设备的访问。 Microsoft 建议允许访问风险分数为中等或更低的设备。

对于 Android 和 iOS/iPadOS，可以在应用保护策略 (APP) 中使用威胁信号。 有关配置此项的信息，请参阅[创建并分配应用保护策略以设置设备风险级别](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)。

对于所有平台，可以在现有设备符合性策略中设置风险级别。请参阅 [创建条件访问策略](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#create-a-conditional-access-policy)。 

## <a name="deploy-security-baselines-and-monitor-compliance-to-these-settings"></a>部署安全基线并监视对这些设置的符合性

适用于：Windows 10、Windows 11

本文，即[第 5 步. 部署配置文件](manage-devices-with-intune-configuration-profiles.md)建议使用适用于 Windows 10 和 Windows 11 的安全基线开始使用配置文件。 Microsoft Defender for Endpoint 还包括安全基线，这些基线提供用于优化 Defender for Endpoint 堆栈中所有安全控件的设置，包括终结点检测和响应 (EDR) 的设置。 这些也使用 Microsoft Intune 进行部署。

理想情况下，载入到 Defender for Endpoint 的设备部署这两个基线：Windows Intune 安全基线，用于在初期保护 Windows，在它之上有 Defender for Endpoint 安全基线，它以最佳方式配置 Defender for Endpoint 安全控制。

若要从有关风险和威胁的最新数据中受益，并随着基线的发展最大程度地减少冲突，请始终在所有产品发布后立即应用最新版本的基线。 

使用 Defender for Endpoint，可以监视对这些基线的符合性。 

![用于监视对安全基线符合性的卡](../media/devices/secconmgmt-baseline-card.png#lightbox)

若要部署安全基线并监视对这些设置的符合性，请使用此表中的步骤。


|步骤  |说明  |
|---------|---------|
|1     |查看关键概念并比较 Microsoft Defender for Endpoint 和 Windows Intune 安全基线。 <br><br>若要了解建议，请参阅[增加对 Microsoft Defender for Endpoint 安全基线的符合性](../security/defender-endpoint/configure-machines-security-baseline.md)。<br><br>请参阅[使用安全基线在 Intune 中配置 Windows 设备](/mem/intune/protect/security-baselines)查看可用安全基线列表以及如何避免冲突。         |
|2     |  为 Intune 部署 Windows 安全基线设置。如果遵循 [步骤 5 中的指南操作部署配置文件 ](manage-devices-with-intune-configuration-profiles.md)，则可能已完成此操作。        |
|3    |  为 Intune 部署 Defender for Endpoint 基线设置。 请参阅[管理 Microsoft Intune 中的安全基线配置文件](/mem/intune/protect/security-baselines-configure)，以创建配置文件并选择基线版本。<br><br>还可以按照此说明操作：[查看并分配 Microsoft Defender for Endpoint 安全基线](../security/defender-endpoint/configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)。     |
|4     | 在 Defender for Endpoint 中，查看[设备配置管理上的安全基线卡](../security/defender-endpoint/configure-machines.md)。          |


## <a name="next-steps"></a>后续步骤
转到[第 7 步. 在终结点上使用信息保护功能实现 DLP](manage-devices-with-intune-dlp-mip.md)。