---
title: 第 1 阶段：Microsoft 365 企业版的网络基础结构
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的网络基础结构的步骤。
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399956"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>第 1 阶段：Microsoft 365 企业版的网络基础结构

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 企业版包括 Office 365 和 Microsoft Intune，作为企业管理 + 安全性 (EMS) 一部分。 这两种基于云的服务都依赖于来自客户端设备通过 Internet 或专用电路的连接的安全性、性能和可靠性。 为了托管这些服务并将其提供给世界各地的客户，Microsoft 设计了一个强调性能和集成的网络基础架构。 

在这个阶段，将遍历创建与 Microsoft 365 企业版云服务的高性能连接的关键注意事项。有关概述，请参阅 [Office 365 网络原则](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

>[!Note]
>如果已部署网络基础结构，请查看这一阶段的[退出条件](networking-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件和可选条件。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>计划和部署 Microsoft 365 企业版网络基础结构 

使用以下步骤构建满足 Microsoft 365 企业版各项要求和能力的网络基础结构。

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[准备用于 Microsoft 365 的·网络](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[配置每个办公室的本地 Internet 连接](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[避免网络回流](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[配置流量旁路](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[优化客户端和 Office 365 服务性能](networking-optimize-tcp-performance.md)|


在完成这些步骤后，请转到这一阶段的[退出条件](networking-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

[针对 Microsoft Office 365 优化网络性能](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)，深入了解 Microsoft，了解公司如何做好准备，针对 Office 365 云服务优化 Microsoft 网络。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

了解 Contoso Corporation（虚构但具代表性的跨国企业）如何针对 Microsoft 365 云服务[优化其网络](contoso-networking.md)。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[准备用于 Microsoft 365 的·网络](networking-provide-bandwidth-cloud-services.md)|

