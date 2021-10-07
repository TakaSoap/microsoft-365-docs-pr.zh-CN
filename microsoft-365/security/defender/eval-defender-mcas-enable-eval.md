---
title: 启用评估环境Microsoft Cloud App Security
description: 了解 Microsoft Defender 中 MCAS 的体系结构Office 365并了解产品之间的Microsoft 365 Defender交互。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 09a1613b82cfd6d88aae76784d59f99d58c48a07
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60181087"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>启用评估环境Microsoft Cloud App Security


**适用于：**

- Microsoft 365 Defender

本文是设置评估环境的过程中第 2 步（第 2 步，第[2](eval-defender-mcas-overview.md)步Microsoft Cloud App Security）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-mcas-overview.md)。

本文将指导你完成访问云应用门户云应用安全配置收集云应用流量数据所需的集成的过程。

若要发现环境中使用的云应用，你可以执行以下一项或两项操作：

- 与 Microsoft Defender for Endpoint 集成，快速启动并运行云发现。 通过此本机集成，你可以立即开始在 Windows 10 Windows 11 Windows上和从网络外收集云流量数据。
- 若要发现已连接到网络的所有设备访问的所有云应用，云应用安全防火墙和其他代理上部署云日志收集器。 这将从终结点收集数据，并将其发送到云应用安全进行分析。 云应用安全与一些第三方代理进行本机集成，以使用更多功能。

本文包括这两种方法的指南。

使用以下步骤设置Microsoft Cloud App Security。

![在 Microsoft Defender 评估Microsoft Cloud App Security Microsoft 支持的步骤。](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [步骤 1.连接到 云应用安全 门户](#step-1-connect-to-the-cloud-app-security-portal)
- [步骤 2.与 Microsoft Defender for Endpoint 集成](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [步骤 3.将云应用安全日志收集器部署到防火墙和其他代理上](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [步骤 4.查看云发现仪表板以查看组织中使用的应用](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>步骤 1. 连接到 云应用安全 门户

若要验证许可并连接到 云应用安全 门户，请参阅[快速入门：Microsoft Cloud App Security。](/cloud-app-security/getting-started-with-cloud-app-security) 

如果无法立即连接到门户，可能需要将 IP 地址添加到防火墙的允许列表中。 请参阅[基本设置了解云应用安全。](/cloud-app-security/general-setup)

如果仍有问题，请查看网络 [要求](/cloud-app-security/network-requirements)。

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>步骤 2. 与 Microsoft Defender for Endpoint 集成

Microsoft Cloud App Security与 Microsoft Defender for Endpoint 本地集成。 集成简化了云发现的推出，将云发现功能扩展到企业网络之外，并启用基于设备的调查。 此集成显示从 IT 托管的 11 Windows 10和 Windows访问的云应用和服务。 

如果你已设置适用于终结点的 Microsoft Defender，则配置与 云应用安全 的集成是 Microsoft 365 Defender。 启用集成后，你可以返回到云发现云应用安全查看云发现仪表板中的丰富数据。

若要完成这些任务，请参阅[Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration)。 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>步骤 3. 将云应用安全日志收集器部署到防火墙和其他代理上

要覆盖连接到网络的所有设备，请将 云应用安全 日志收集器部署到防火墙和其他代理上，以从终结点收集数据并将其发送到 云应用安全 进行分析。 

如果您使用的是 SWG 中的以下安全 Web 网关 (之) ，云应用安全无缝部署和集成：
- Zscaler
- iboss
- Corrata
- Menlo 安全性

有关与这些网络设备集成的信息，请参阅设置 [云发现](/cloud-app-security/set-up-cloud-discovery)。 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>步骤 4. 查看云发现仪表板以查看组织中使用的应用

云发现仪表板旨在让你深入了解如何在组织中使用云应用。 它概述了使用的应用类型、打开的警报以及组织中应用程序的风险级别。 

若要开始使用云发现仪表板，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

## <a name="next-steps"></a>后续步骤

步骤 3/3：[试点Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

返回到评估结果[概述Microsoft Cloud App Security](eval-defender-mcas-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)