---
title: Contoso 的 Microsoft 365 企业应用版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Microsoft 365 企业应用版。
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907670"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 的 Microsoft 365 企业应用版部署

Contoso 将电脑升级到 Windows 10 企业版和 Microsoft 365 企业应用版，以实现更有效的协作、更好的安全性和更现代桌面体验。 在评估其基础结构和业务需求后，Contoso 确定了这些部署的关键要求：

- 所有电脑都应运行 Microsoft 365 企业应用版。
- 如果可能，部署应使用现有管理工具和基础结构。
- 部署必须在用户设备上支持多种语言和现有体系结构。
- 电脑应保持最新和安全，并尽量减少 IT 管理成本，并尽量减少对用户的影响。

## <a name="deployment-tools"></a>部署工具

根据要求，Contoso 选择通过 Configuration Manager (Current Branch 部署 Windows 10 企业版和 Microsoft 365 企业应用) 。 Configuration Manager 可针对大型环境进行扩展，并提供对安装、更新和设置的广泛控制。 它还具有内置功能，使部署和管理 Office 更加轻松和高效，包括：

- 对等缓存，在部署到远程位置的设备时，可帮助实现有限的网络容量。
- Office 客户端管理仪表板，可轻松部署 Office 和监视更新，并授予管理员对最新部署和管理功能的访问权限。
- 智能语言包部署，包括自动部署与操作系统相同的语言。
- 在部署期间从客户端删除现有版本的 Office 的完全支持且易于使用的方法。

除了 Configuration Manager 之外，Contoso 还使用 Readiness Toolkit for Office 外接程序和 [VBA（Microsoft](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)免费提供的工具）来评估其 Office 宏和外接程序的兼容性问题。

## <a name="managing-deployment-and-updates"></a>管理部署和更新

Microsoft 365 企业应用版有一个新的发布模型：Office 即服务。 服务模型使使用新功能保持最新状态变得容易。 但通常需要 IT 部门更改其部署和测试新版本。 为了最大限度地减少兼容性问题并确保其计算机保持最新，Contoso 分两个阶段部署了 Windows 和 Office：

- 首先，他们在整个组织中将 Microsoft 365 企业应用版部署到一小组具有代表性的设备。 此试点组用于测试 Microsoft 365 企业应用版的应用、加载项和硬件。
- 四个月后，在解决了试点组中有关应用、加载项和硬件的所有关键问题后，Contoso 将 Microsoft 365 企业应用版部署到组织中的剩余设备（广泛组）。

Contoso 启用了云中的自动更新，而不是使用 Configuration Manager 管理 Office 更新。 基于云的更新可减少管理开销，同时确保设备保持最新状态。

Contoso 对功能更新采用与用于部署 Office 相同的两阶段方法：试点组中设备接收功能更新的时间比组织中其余组织的设备早四个月 (广泛组) 。 若要为 Office 启用此功能，Contoso 使用了两个推荐的 [更新频道](/DeployOffice/overview-update-channels)：

- 试点组更新的 Enterprise 半年频道（预览）。
- Semi-Annual企业频道获取广泛组更新

因为半年 Enterprise 频道（预览）发布 Microsoft 365 企业应用版的时间比半年 Enterprise 频道早 4 个月，所以，Contoso 有时间来验证更新，无需对其进行管理。

## <a name="deployment-process"></a>部署过程

为完成 Office 的部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：

1. 在部署之前，Contoso 使用 Readiness Toolkit for Office 外接程序和 VBA 测试其应用和 Office 外接程序，以评估其与 Microsoft 365 企业应用版之间的兼容性。
1. 在 Configuration Manager 中，他们在客户端设备上启用了对等缓存，这有助于在部署到远程位置的客户端设备时具有有限的网络容量。 
1. Contoso 在 Configuration Manager 中将两个部署组定义为设备集合：试点组和广泛组。 试点组包括一小组跨组织的代表设备，用于在 Windows 10 企业版和 Microsoft 365 企业应用版中对应用、加载项和硬件进行其他测试。
1. 他们使用 Office 客户端管理仪表板和 Office 365 安装程序向导创建了 Office 的部署包，这两者都是 Configuration Manager 控制台的一部分。 他们生成了两个 Microsoft 365 企业应用版程序包，一个适用于 Semi-Annual 企业频道 (预览版) 上的试点组，一个适用于 Semi-Annual 企业频道上的广泛组。
2. 每个 Office 包都包含英语、法语和德语语言包。 如果设备需要 Office 包中未包含的语言，该语言包会自动从 Office 内容交付网络和 CDN (下载) 。
3. 在安装 Microsoft 365 企业应用版前，它们使用 Office 包中的内置功能来自动删除所有现有的 Office 的 MSI 版本。
4. 在 Configuration Manager 中，他们跨网络将 Windows 和 Office 包部署到分发点。 然后，他们运行 Configuration Manager 部署任务序列，将试点 Microsoft 365 企业应用版程序包部署到试点组。
5. 在解决了试点组的兼容性问题后，Contoso 运行任务序列，将 Microsoft 365 企业应用版包部署到广泛组。

因为 Contoso 选择从云中自动更新设备，所以无需在 Configuration Manager 中管理过程。 其设备会直接从基于云的自动更新，该更新通道是在初始部署中定义的。

下面是 Contoso Microsoft 365 企业应用版安装和持续更新部署体系结构。

![Microsoft 365 企业应用版 Contoso 部署基础结构](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>后续步骤

了解 Contoso 如何使用 Microsoft 365 企业版中的 [Microsoft Intune](contoso-mdm.md) 来管理其设备和他们在组织中运行的应用。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业应用版](/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)