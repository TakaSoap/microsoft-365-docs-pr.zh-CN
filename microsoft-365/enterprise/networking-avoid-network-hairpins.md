---
title: 第 3 步：避免网络回流
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
description: 了解并删除网络回流以获得更佳性能。
ms.openlocfilehash: eef8770dff6c54da51650b0fb70077fdd125f981
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291516"
---
# <a name="step-3-avoid-network-hairpins"></a>第 3 步：避免网络回流

*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

首次将发往目标的流量定向到其他中间位置（例如本地安全堆栈、云访问代理或基于云的 Web 网关）时，会发生[网络回流](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3)。由于网络服务提供商的原因，Internet 上的路由不良也可能导致网络回流。回流会增加延迟，并可能将流量重定向到地理位置较远的位置。

要优化 Microsoft 365 基于云的服务的流量性能，请检查提供本地 Internet 连接的 ISP 是否与该位置附近的 Microsoft 全球网络具有直接对等关系。这些连接中没有回流。

如果将基于云的网络或安全服务用于 Microsoft 365 流量，请确保评估回流效果并确保了解其对性能的影响。检查以下内容：

- 服务提供商的数量和位置，通过这些服务提供商将流量转发到分公司和 Microsoft 全球网络对等点 
- 服务提供商与 ISP 和 Microsoft 的网络对等关系的质量 
- 服务提供商基础结构中回程的性能影响

如有可能，配置边缘路由器以直接发送受信任的 Microsoft 365 流量，而不是通过处理 Internet 流量的第三方云或基于云的网络安全供应商进行代理或隧道传输。 

作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step3)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[配置流量旁路](networking-configure-proxies-firewalls.md)|
