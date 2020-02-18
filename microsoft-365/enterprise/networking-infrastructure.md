---
title: 第 1 阶段：Microsoft 365 企业版的网络基础结构
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的网络基础结构的步骤。
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066564"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>第 1 阶段：Microsoft 365 企业版的网络基础结构

![第 1 阶段：网络](../media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 企业版包括 Office 365、Microsoft Intune 以及 Microsoft Azure 的许多标识和安全服务。 所有这些基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。 为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。 

在这个阶段，将遍历创建与 Microsoft 365 企业版云服务的高性能连接的关键注意事项。有关概述，请参阅 [Office 365 网络原则](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

>[!Note]
>如果已部署网络基础结构，请查看这一阶段的[退出条件](networking-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件和可选条件。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>计划和部署 Microsoft 365 企业版网络基础结构 

使用以下步骤构建满足 Microsoft 365 企业版各项要求和能力的网络基础结构。

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)|[准备用于 Microsoft 365 的网络](networking-provide-bandwidth-cloud-services.md)|
|![第 2 步](../media/stepnumbers/Step2.png)|[配置每个办公室的本地 Internet 连接](networking-dns-resolution-same-location.md)|
|![第 3 步](../media/stepnumbers/Step3.png)|[避免网络回流](networking-avoid-network-hairpins.md)|
|![第 4 步](../media/stepnumbers/Step4.png)|[配置流量旁路](networking-configure-proxies-firewalls.md)|
|![第 5 步](../media/stepnumbers/Step5.png)|[优化客户端和 Office 365 服务性能](networking-optimize-tcp-performance.md)|


在完成这些步骤后，请转到这一阶段的[退出条件](networking-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

洞察 Microsoft，了解这家公司如何[针对云服务优化 Microsoft 网络](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

了解 Contoso Corporation（有代表性的虚构跨国企业）如何针对 Microsoft 365 云服务[优化自己的网络设备和 Internet 连接](contoso-networking.md)。

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)|[准备用于 Microsoft 365 的·网络](networking-provide-bandwidth-cloud-services.md)|

