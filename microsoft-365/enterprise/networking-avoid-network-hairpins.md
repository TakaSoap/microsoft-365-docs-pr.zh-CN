---
title: 第 3 步：避免网络回流
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并删除网络回流以获得更佳性能。
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583421"
---
# <a name="step-3-avoid-network-hairpins"></a>第 3 步：避免网络回流

*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![阶段 1：网络](../media/deploy-foundation-infrastructure/networking_icon-small.png)

当绑定到目标的流量先定向到另一个中间位置（例如本地安全堆栈、云访问代理或基于云的 Web 网关）时，会出现[网络发夹](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。 下面是一个示例。

![网络发夹示例](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

网络发夹也可能是由于网络服务提供商在 Internet 上路由不畅所致。 

发夹会增加延迟，并且可能会将流量重定向到地理位置较远的位置。

要优化 Microsoft 365 基于云的服务的流量性能，请检查提供本地 Internet 连接的 ISP 是否与该位置附近的 Microsoft 全球网络具有直接对等关系。这些连接中没有回流。

如果将基于云的网络或安全服务用于 Microsoft 365 流量，请确保评估回流效果并确保了解其对性能的影响。检查以下内容：

- 服务提供商的数量和位置，通过这些服务提供商将流量转发到分公司和 Microsoft 全球网络对等点 
- 服务提供商与 ISP 和 Microsoft 的网络对等关系的质量 
- 服务提供商基础结构中回程的性能影响

如有可能，配置边缘路由器以直接发送受信任的 Microsoft 365 流量，而不是通过处理 Internet 流量的第三方云或基于云的网络安全供应商进行代理或隧道传输。 

![绕过网络发夹的示例](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

如果要测试与 Microsoft 全球网络入口点的有多近，以及测试与组织网络连接 ISP 的接点有多近，请使用 [Office 365 网络载入工具](https://connectivity.office.com/)。

作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step3)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 4 步](../media/stepnumbers/Step4.png)|[配置流量旁路](networking-configure-proxies-firewalls.md)|
