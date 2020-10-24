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
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754340"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 的 Microsoft 365 企业应用版部署

Contoso 将他们的电脑升级到 Windows 10 企业版和 Microsoft 365 应用程序以实现更有效的协作、更好的安全性和更新式的桌面体验。在评估其基础结构和业务需求之后，Contoso 确定了部署的这些关键要求：

- 所有电脑都应运行适用于企业的 Microsoft 365 应用。
- 如果可能，部署应使用现有的管理工具和基础结构。
- 部署必须支持用户设备上的多种语言和现有体系结构。
- 电脑应保持最新并最小化 IT 管理成本和对用户的影响最小。

## <a name="deployment-tools"></a>部署工具

根据其要求，Contoso 选择通过 Configuration Manager 将 Windows 10 企业版和 Microsoft 365 应用程序部署到 Configuration Manager (当前分支) 。Configuration Manager 可扩展为大型环境，并提供对安装、更新和设置的广泛控制。它还具有内置功能，使您可以更轻松、更高效地部署和管理 Office，包括：

- 对等缓存，在部署到远程位置的设备时，此缓存可帮助有限的网络容量。
- Office 客户端管理仪表板，使管理员可以轻松地部署 Office 和监视器更新，并使管理员能够访问最新的部署和管理功能。
- 智能语言包部署，包括自动部署与操作系统相同的语言。
- 在部署过程中从客户端删除 Office 的现有版本的完全受支持且易于使用的方法。

除了配置管理器，Contoso 还使用 [office 外接程序和 VBA 的准备工具包](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)，从 Microsoft 获取免费工具，以评估 Office 宏和外接程序的兼容性问题。

## <a name="managing-deployment-and-updates"></a>管理部署和更新

适用于企业的 Microsoft 365 应用程序具有新的版本模型： Office 服务。利用服务模型，可以轻松保持最新的新功能。但通常需要 IT 部门来更改部署和测试新版本的方式。若要最大限度地减少兼容性问题，并确保其计算机保持最新，Contoso 在以下两个阶段部署了 Windows 和 Office：

- 首先，他们将 Microsoft 365 应用程序部署到整个组织中的一小部分代表性设备。 此试点组用于测试适用于企业的 Microsoft 365 应用程序的应用、加载项和硬件。
- 四个月后，在解决了试点组中有关应用、加载项和硬件的所有关键问题后，Contoso 将 Microsoft 365 企业应用版部署到组织中的剩余设备（广泛组）。

Contoso 启用了来自云的自动更新，而不是使用配置管理器管理 Office 更新。 基于云的更新可减少管理开销，同时确保设备保持最新。

Contoso 对功能更新的使用相同的两阶段方法，因为它们用于部署 Office：引导组中的设备接收到的功能更新早于组织中其他地方的设备的四个月 (广泛的组) 。 若要为 Office 启用此项，Contoso 使用了两个推荐的 [更新通道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：

- 试点组更新的 Enterprise 半年频道（预览）。
- 为广泛的组更新 Semi-Annual 企业渠道

因为半年 Enterprise 频道（预览）发布 Microsoft 365 企业应用版的时间比半年 Enterprise 频道早 4 个月，所以，Contoso 有时间来验证更新，无需对其进行管理。

## <a name="deployment-process"></a>部署过程

为完成 Office 的部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：

1. 在部署之前，Contoso 使用 Office 外接程序和 VBA 的准备情况工具包来测试其应用和 Office 加载项，以评估与 Microsoft 365 应用程序的兼容性，以供企业使用。
1. 在配置管理器中，他们在其客户端设备上启用了对等缓存，这有助于在远程位置部署到客户端设备时具有有限的网络容量。 
1. Contoso 在配置管理器中将两个部署组定义为设备集合：一个试点组和一个广泛的组。 在整个组织中包含一小组代表设备的试点组用于对应用、外接程序和具有 Windows 10 企业版的 Microsoft 365 应用程序的硬件进行额外测试。
1. 他们通过使用 Office 客户端管理仪表板和 Office 365 安装程序向导（这两个都是 Configuration Manager 控制台的一部分）为 Office 创建了部署程序包。 他们为企业包构建了两个 Microsoft 365 应用程序，一个用于 Semi-Annual 企业频道 (Preview) 上的试点组，另一个用于 Semi-Annual 企业频道上的广泛组。
2. 每个 Office 程序包包括英语、法语和德语语言包。 如果设备需要的语言不包含在 Office 程序包中，则会自动从 Office 内容传递网络 (CDN) 下载该语言包。
3. 在安装 Microsoft 365 企业应用版前，它们使用 Office 包中的内置功能来自动删除所有现有的 Office 的 MSI 版本。
4. 在配置管理器中，他们将 Windows 和 Office 包部署到其网络中的分发点。 然后，他们运行 Configuration Manager 部署任务序列，以将 Microsoft 365 应用程序的试点 Microsoft 应用程序包部署到试点组。
5. 在他们解决了试点组的兼容性问题之后，Contoso 运行任务序列以将适用于企业的 Microsoft 365 应用程序包部署到广泛的组中。

因为 Contoso 选择从云中自动更新设备，所以无需在 Configuration Manager 中管理过程。 他们的设备将根据初始部署中定义的更新通道，直接从云自动更新。

以下是 Contoso Microsoft 365 应用程序的企业安装和持续更新部署体系结构。

![适用于企业的 Microsoft 365 应用的 Contoso 部署基础结构](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>后续步骤

了解 Contoso 如何在 Microsoft 365 for 企业版中 [使用 Microsoft Intune](contoso-mdm.md) 来管理其设备以及他们在组织中运行的应用程序。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
