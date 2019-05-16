---
title: 第 2 步：配置每个办公室的本地 Internet 连接
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 理解并配置 DNS 解析，以获得更好的性能。
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073262"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>第 2 步：配置每个办公室的本地 Internet 连接

** 此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

在第 2 步中，确保每个办公室都具有本地 Internet 连接并使用本地 DNS 服务器。要求这两个元素均降低连接延迟，并确保本地客户端计算机与 Microsoft 365 基于云的服务的最近入口点建立连接。

在大型组织的传统网络中，Internet 流量通过网络主干网传输到中央 Internet 连接。这不适用于优化全局分布式软件即服务 (SaaS) 基础结构的性能，该基础结构包含 Microsoft 365 中的 Office 365 和企业移动性 + 安全性 (EMS) 产品。

Microsoft 全球网络包括适用于全球 Microsoft 365 的云服务集的前端服务器。为了获得最佳性能，本地客户端应访问地理位置最靠近它们的前端服务器，而不是通过网络主干网发送流量并将流量发送到最靠近组织中央 Internet 连接的前端服务器。

为了将客户端请求定向到地理位置最近的前端服务器，Microsoft DNS 服务器使用与客户端初始连接请求相对应的 DNS 查询。因此，为了实现最低网络延迟：

- 组织的所有办公室都应具有本地 Internet 连接，以便[优化](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)类别网络流量。
- 每个本地 Internet 连接应使用地区本地 DNS 服务器来处理来自该位置的出站 Internet 流量。

有关详细信息，请参阅[本地出口网络连接](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)。 

作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step2)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[避免网络回流](networking-avoid-network-hairpins.md)|
