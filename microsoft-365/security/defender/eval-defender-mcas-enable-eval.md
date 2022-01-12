---
title: 为 Microsoft Defender for Cloud Apps 启用评估环境
description: 了解 Microsoft Defender 中适用于云应用的 Defender 体系结构Office 365并了解 Microsoft 365 Defender 产品之间的交互。
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9d0418b2f183884793be3c2d8a72f571d0072a61
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61933140"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>为 Microsoft Defender for Cloud Apps 启用评估环境

**适用于：**

- Microsoft 365 Defender

本文是设置 Microsoft Defender for Cloud Apps 评估环境过程中第 2 步（第 [2](eval-defender-mcas-overview.md) 步）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-mcas-overview.md)。

本文将引导你完成访问 Defender for Cloud Apps 门户和配置收集云应用流量数据所需的集成的过程。

若要发现环境中使用的云应用，你可以执行以下一项或两项操作：

- 与 Microsoft Defender for Endpoint 集成，快速启动并运行云发现。 此本机集成使你能够立即开始在网络内和Windows 10 Windows 11设备上收集云流量数据。
- 若要发现连接到网络的所有设备访问的所有云应用，请在你的防火墙和其他代理上部署 Defender for Cloud Apps 日志收集器。 这将从终结点收集数据，并将其发送到 Defender for Cloud Apps 进行分析。 云应用的 Defender 在本机与一些第三方代理集成，实现更多功能。

本文包括这两种方法的指南。

使用以下步骤设置 Microsoft Defender for Cloud Apps。

![在 Microsoft Defender 评估环境中启用 Microsoft Microsoft Defender 云应用的步骤。](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [步骤 1.连接 Defender for Cloud Apps 门户](#step-1)
- [步骤 2.与 Microsoft Defender for Endpoint 集成](#step-2)
- [步骤 3.在防火墙和其他代理上部署 Defender for Cloud Apps 日志收集器](#step-3)
- [步骤 4.查看云发现仪表板以查看组织中使用的应用](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>步骤 1. 连接 Defender for Cloud Apps 门户

若要验证许可并连接到适用于云应用的 Defender 门户，请参阅 [快速入门：Microsoft Defender for Cloud Apps 入门](/cloud-app-security/getting-started-with-cloud-app-security)。

如果无法立即连接到门户，可能需要将 IP 地址添加到防火墙的允许列表中。 请参阅 [Defender for Cloud Apps 的基本设置](/cloud-app-security/general-setup)。

如果仍有问题，请查看网络 [要求](/cloud-app-security/network-requirements)。

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>步骤 2. 与 Microsoft Defender for Endpoint 集成

Microsoft Defender for Cloud Apps 与 Microsoft Defender for Endpoint 本地集成。 集成简化了云发现的推出，将云发现功能扩展到企业网络之外，并启用基于设备的调查。 此集成显示从 IT 托管的云应用和服务Windows 10和Windows 11访问。

如果你已设置 Microsoft Defender for Endpoint，则配置与 Defender for Cloud Apps 的集成是应用中的Microsoft 365 Defender。 启用集成后，你可以返回到 Defender for Cloud Apps 门户，并查看云发现仪表板中的丰富数据。

若要完成这些任务，请参阅[Microsoft Defender for Endpoint integration with Microsoft Defender for Cloud Apps。](/cloud-app-security/mde-integration)

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>步骤 3. 在防火墙和其他代理上部署 Defender for Cloud Apps 日志收集器

要覆盖连接到网络的所有设备，请将 Defender for Cloud Apps 日志收集器部署到防火墙和其他代理上，以从终结点收集数据并将其发送到 Defender for Cloud Apps 进行分析。

如果你使用 SWG 中的以下安全 Web 网关 (，) Defender for Cloud Apps 提供无缝部署和集成：

- Zscaler
- iboss
- Corrata
- Menlo 安全性

有关与这些网络设备集成的信息，请参阅设置 [云发现](/cloud-app-security/set-up-cloud-discovery)。

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>步骤 4. 查看云发现仪表板以查看组织中使用的应用

云发现仪表板旨在让你深入了解如何在组织中使用云应用。 它概述了使用的应用类型、打开的警报以及组织中应用程序的风险级别。

若要开始使用云发现仪表板，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

## <a name="next-steps"></a>后续步骤

步骤 3/3： [试用 Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md)

返回到评估 Microsoft [Defender for Cloud Apps 的概述](eval-defender-mcas-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
