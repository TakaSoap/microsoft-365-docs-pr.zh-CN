---
title: 第 3 步。 部署设备、电脑和其他终结点的终结点管理
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 使用 Microsoft Endpoint Manager 管理管理设备、电脑和其他终结点。
ms.openlocfilehash: 4bc467b3da76a846d6d86e8812c542aa33f5e8b1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141449"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>第 3 步。 部署设备、电脑和其他终结点的终结点管理

使用远程工作者，需要支持越来越多的个人设备。 终结点管理是一种基于策略的安全方法，要求设备在获得对资源的访问权限之前满足特定条件。 Microsoft Endpoint Manager 提供新式工作区和新式管理功能，使你的数据在云中和本地保持安全。 

Endpoint Manager 通过结合以下可能已知和正在使用的服务，提供用于管理移动设备、台式计算机、虚拟机、嵌入式设备和服务器的服务和工具。

![用于终结点管理的组件](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune 旨在帮助你在不管理用于访问组织数据的设备时保护数据。 Intune 应用保护策略与 Azure AD 条件访问相结合，提供对移动设备上的数据的精细控制。 借助 Intune，你还可以定义全面的策略，仅允许适当人员在适当条件下访问你的公司数据，并通过控制其在 Office、Outlook 和其他移动应用中使用数据的方式来确保数据持续受保护。

有关详细信息，请参阅此 [Microsoft Intune 概述](https://docs.microsoft.com/intune/fundamentals/what-is-intune)。

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager 是一种本地管理解决方案，可用于管理网络上或基于 Internet 的台式机、服务器和笔记本电脑。 可通过云使其与 Intune、Azure AD、Microsoft Defender ATP 和其他云服务集成。 使用 Configuration Manager 部署应用程序、软件更新和操作系统。 还可以实时监视客户端上的合规性、查询和操作等。

有关详细信息，请参阅此 [Configuration Manager 概述](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。

## <a name="co-management"></a>协同管理

协同管理使用 Intune 和其他 Microsoft 365 云服务，将现有的 Configuration Manager 投资与云相结合。 由你选择将 Configuration Manager 还是 Intune 作为 7 个不同工作负载组的管理机构。

作为 Endpoint Manager 的一部分，协同管理使用云功能，包括条件访问。 在云中使用 Intune 运行其他任务时，可将某些任务保留为本地。

有关详细信息，请参阅此[协同管理概述](https://docs.microsoft.com/mem/configmgr/comanage/overview)。

## <a name="desktop-analytics"></a>桌面分析

桌面分析是一种基于云的服务，可与 Configuration Manager 集成并为你提供洞察和情报，以便就 Windows 客户端作出明智决策。 它将组织中的数据与连接到 Microsoft 云服务的数百万台设备的数据合并。 借助桌面分析，可以创建在组织中运行的应用程序清单、评估与最新 Windows 10 功能更新的应用兼容性、识别兼容性问题、接收基于已启用云的数据见解的缓解建议、在最小的设备组中创建代表整个应用程序和驱动程序的试验组，并将 Windows 10 部署到试点和生产管理的设备。

有关详细信息，请参阅此[桌面分析概述](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot 是一个零接触、自助式的 Windows 部署平台。 它包括一组用于设置和预配置新设备，以使它们可供高效使用的技术。 还可以使用 Windows Autopilot 来重置、恢复设备并重新调整其用途。 此解决方案可以让 IT 部门通过轻松简单的流程，在几乎不需要管理基础结构的情况下实现上述目标。 从用户的角度来看，只需几个简单操作便可以使其设备准备就绪，以供使用。 从 IT 专业人员的角度来看，最终用户所需的交互将只有连接到网络并验证其凭据。

有关详细信息，请参阅此 [Windows Autopilot 概述](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。

## <a name="admin-technical-resources-for-endpoint-management"></a>用于终结点管理的管理员技术资源

- [注册托管设备以实现安全，利用未托管设备的应用设置，并使用设备和应用策略](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [如何注册用于移动设备管理 (MDM) 的不同类型的设备](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [如何向最终用户讲解 Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>步骤 3 的结果

你正在使用 Endpoint Manager 功能套件来管理移动设备、台式计算机、虚拟机、嵌入式设备和服务器。

## <a name="next-step"></a>后续步骤

继续执行[步骤 4](empower-people-to-work-remotely-teams-productivity-apps.md)，提供对本地应用和服务的远程访问权限。
