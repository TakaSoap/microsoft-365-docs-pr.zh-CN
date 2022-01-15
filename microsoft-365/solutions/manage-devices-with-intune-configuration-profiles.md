---
title: 步骤 5. 在 Microsoft Intune 中部署设备配置文件
ms.author: bcarter
author: brendacarter
f1.keywords:
- configuration profiles
- Windows security baselines for Intune
- customize configuration profiles
manager: dougeby
audience: ITPro
description: 开始使用配置文件，使用 Intune 在设备上强制实施安全设置，以将这些安全控制权转移到云。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: d44d70c50db5c086e24af575677d5d51e1b33357
ms.sourcegitcommit: 23166424125b80b2d615643f394a3c023cba641d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2022
ms.locfileid: "62049247"
---
# <a name="step-5-deploy-device-profiles-in-microsoft-intune"></a>步骤 5. 在 Microsoft Intune 中部署设备配置文件

Microsoft Intune 包含可在组织中的不同设备上启用或禁用的设置和功能。 这些设置和功能将添加到“配置文件”。 可以为不同的设备和不同的平台（包括 iOS/iPadOS、Android 设备管理员、Android Enterprise 和 Windows）创建配置文件。 然后，使用 Intune 将配置文件应用于或“分配”给设备。

本文提供有关配置文件入门的指南。 


![管理设备的步骤](../media/devices/intune-mdm-step-4.png#lightbox)

使用配置文件，能够配置重要保护并使设备合规，以便它们可以访问你的资源。 以前，这些种类的配置更改是通过使用 Active Directory 域服务中的组策略设置来配置的。 新式安全策略包括将安全控制移动到云，而在云中强制实施这些控制并不依赖于本地资源和访问权限。 Intune 配置文件就是将这些安全控制转换到云的方法。 

要了解可以创建的配置文件种类，请参阅 [使用 Microsoft Intune 中的设备配置文件在设备上应用功能和设置](/mem/intune/configuration/device-profiles)。

## <a name="deploy-windows-security-baselines-for-intune"></a>为 Intune 部署 Windows 安全基线

首先，如果要将设备配置与 Microsoft 安全基线保持一致，建议使用 Microsoft Endpoint Manager 中的安全基线。 此方法的优点是，你可以依赖 Microsoft 在发布 Windows 10 和 11 功能时保持基线为最新状态。 

部署适用于 Intune 的 Windows 安全基线，适用于 Windows 10 和 Windows 11。 请参阅 [使用安全基线在 Intune 中配置 Windows 设备](/mem/intune/protect/security-baselines)，以了解可用的基线。

目前，只需部署最合适的 MDM 安全基线。 请参阅 [管理 Microsoft Intune 中的安全基线配置文件](/mem/intune/protect/security-baselines-configure)，以创建配置文件并选择基线版本。

稍后，在设置 Microsoft Defender for Endpoint 并连接 Intune 时，部署 Defender for Endpoint 基线。 本系列的下一篇文章对此主题进行了介绍：[第 6 步 - 监视设备风险和对安全基线的符合性](manage-devices-with-intune-monitor-risk.md)。

请务必了解这些安全基线并不符合 CIS 或 NIST，但与它们的建议非常相似。 有关详细信息，请参阅 [Intune 安全基线是否符合 CIS 或 NIST](/mem/intune/protect/security-baselines)？

## <a name="customize-configuration-profiles-for-your-organization"></a>自定义组织的配置文件

除了部署预配置的基线之外，许多企业规模的组织还实施配置文件以实现更精细的控制。 此配置有助于减少对本地 Active Directory 环境中组策略对象的依赖，并将安全控制权移动到云中。 

可以使用配置文件进行配置的许多设置可以分为四个类别，如下所示。

![Intune 设备配置文件类别](../media/devices/intune-device-profile-categories.png#lightbox)

下表对该图进行了说明。


|类别 |说明 |示例  |
|---------|---------|---------|
|设备功能     | 设备上的控制功能。 此类别仅适用于 iOS/iPadOS 和 macOS 设备。        | Airprint、通知、锁屏界面消息        |
|设备限制     | 控制设备上的安全性、硬件、数据共享和其他设置        | 需要 PIN、数据加密        |
|访问权限配置     |  配置设备以访问组织的资源        | 电子邮件配置文件、VPN 配置文件、Wi-Fi 设置、证书        |
|自定义警报     | 设置自定义配置或执行自定义配置操作       | 设置 OEM 设置、执行 PowerShell 脚本        |
|    |         |         |

为组织自定义配置文件时，请使用以下指南：
- 通过减少策略总体数量来简化安全治理策略。
- 将设置分组到上面列出的类别中，或分组到对组织有意义的类别。
- 将安全控制从组策略对象 (GPO) 移动到 Intune 配置文件时，请考虑为每个 GPO 配置的设置是否仍然相关，并且是否需要为整体云安全策略做出贡献。 条件访问和可跨云服务（包括 Intune）配置的许多策略提供比在最初设计自定义 GPO 的本地环境中可以配置的更复杂的保护。
- 利用组策略分析比较当前 GPO 设置并将其映射到 Microsoft Endpoint Manager 中的功能。 请参阅在 Microsoft Endpoint Manager 中 [使用组策略分析来分析本地组策略对象 (GPO)](/mem/intune/configuration/group-policy-analytics)。
- 使用自定义配置文件时，请务必使用以下指南：[使用 Intune 中的自定义设置创建配置文件](/mem/intune/configuration/custom-settings-configure)。

## <a name="additional-resources"></a>其他资源

如果不确定从何处入手设备配置文件，则以下操作可能会有所帮助：

- [引导式方案](/mem/intune/fundamentals/guided-scenarios-overview) 
- [安全基线](/mem/intune/protect/security-baselines)

如果你的环境包括本地 GPO，则以下功能将是向云的良好转换：

- [组策略分析](/mem/intune/configuration/group-policy-analytics)
- [管理员模板 (ADMX)](/mem/intune/configuration/administrative-templates-windows)
- [设置目录](/mem/intune/configuration/settings-catalog)


## <a name="next-steps"></a>后续步骤
转到 [第 6 步 - 监视设备风险和对安全基线的符合性](manage-devices-with-intune-monitor-risk.md)。
