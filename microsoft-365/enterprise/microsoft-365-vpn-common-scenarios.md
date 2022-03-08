---
title: 用于服务器的常见 VPN 拆分隧道Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: 用于服务器的常见 VPN 拆分隧道Microsoft 365
ms.openlocfilehash: 26f4cf10de3282c5257592a26ea61d073a0d3cd4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330804"
---
# <a name="common-vpn-split-tunneling-scenarios-for-microsoft-365"></a>用于服务器的常见 VPN 拆分隧道Microsoft 365

>[!NOTE]
>本文是一组文章的一部分，这些文章Microsoft 365远程用户的优化。

>- 有关使用 VPN 拆分隧道优化远程Microsoft 365连接的概述，请参阅[概述：适用于远程用户的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)。
>- 有关实现 VPN 拆分隧道的详细指南，请参阅[实现 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。
>- 有关在 VPN 拆分隧道Teams保护媒体流量的指南，请参阅 [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md)。
>- 若要了解如何在 VPN 环境中配置 Stream 和实时事件，请参阅 VPN 环境中 Stream 和 [实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)。
>- 有关为中国用户Microsoft 365全球租户性能的信息，请参阅Microsoft 365[中国用户的性能优化](microsoft-365-networking-china.md)。

在下面的列表中，你将看到在企业环境中看到的最常见的 VPN 方案。 大多数客户通常运行模型 1（VPN 强制隧道）。 本节将帮助您快速安全地过渡到模型 **2**，这可以通过相对少的工作实现，并且对网络性能和用户体验具有巨大优势。

| 模型 | 说明 |
| --- | --- |
| [1. VPN 强制隧道](#1-vpn-forced-tunnel) | 100% 的流量进入 VPN 隧道，包括本地、Internet 以及所有 O365/M365 |
| [2. VPN 强制隧道（有几个例外）](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | 默认情况下使用 VPN 隧道（默认路由指向 VPN），有几个最重要的豁免场景允许直接访问 |
| [3. VPN 强制隧道（有多个例外）](#3-vpn-forced-tunnel-with-broad-exceptions) | 默认情况下，使用 VPN 隧道 (默认路由指向 VPN) ，但允许直接进入 VPN 通道 (如所有 Microsoft 365、All Salesforce、All Zoom)  |
| [4. VPN 选择性隧道](#4-vpn-selective-tunnel) | VPN 隧道仅用于基于公司网络的服务。 默认路由 (Internet，所有基于 Internet 的服务) 直接路由。 |
| [5. 无 VPN](#5-no-vpn) | #2 的变体。 所有 (企业网络服务都通过现代安全方法（如 Zscaler ZPA、Azure Active Directory (Azure AD) 代理/MCAS 等）)  |

## <a name="1-vpn-forced-tunnel"></a>1. VPN 强制隧道

大多数企业客户最常见的开始方案。 使用强制 VPN，这意味着无论终结点是否驻留在企业网络内，100% 的流量将定向到企业网络。 然后， (Internet) 流量（如 Microsoft 365 或 Internet 浏览）的任何外部流量都回发回本地安全设备（如代理）。 在当前近 100% 的用户远程工作的当前情况中，此模型对 VPN 基础结构造成高负载，并且可能会显著妨碍所有公司流量的性能，进而使企业在危机时高效运行。

![VPN 强制Tunnel模型 1。](../media/vpn-split-tunneling/vpn-model-1.png)

## <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN 强制隧道（有几个受信任的异常）

企业在企业下运营的效率明显提高。 此模型允许几个高负载和延迟敏感的受控和定义的终结点绕过 VPN 隧道并直接转到 Microsoft 365 服务。 这显著提高了卸载服务的性能，还减少了 VPN 基础结构上的负载，从而允许仍然需要它的元素以较低的资源争用运行。 正是此模型，本文侧重于协助过渡到 ，因为它允许快速执行简单的已定义操作，并产生大量积极结果。

![拆分Tunnel VPN 模型 2。](../media/vpn-split-tunneling/vpn-model-2.png)

## <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN 强制隧道（有多个例外）

扩大模型 2 的范围。 它不再直接发送一小组定义的终结点，而是直接将所有流量发送到受信任的服务（如 Microsoft 365 和 SalesForce）。 这可进一步减少公司 VPN 基础结构的负载，并提高已定义服务的性能。 由于此模型可能需要更多时间来评估和实施是否可行，因此在成功实施模型 2 后，稍后可能会反复执行一个步骤。

![拆分Tunnel VPN 模型 3。](../media/vpn-split-tunneling/vpn-model-3.png)

## <a name="4-vpn-selective-tunnel"></a>4. VPN 选择性隧道

反转第三个模型，因为只有标识为具有企业 IP 地址的流量通过 VPN 隧道发送，因此 Internet 路径是其他所有内容的默认路由。 此模型要求组织能够很好地适应[零信任](https://www.microsoft.com/security/zero-trust?rtc=1)路径，以便能够安全地实现此模型。 应该注意到，随着更多服务从企业网络移入云，此模型或一些变体可能会随着时间的推移成为必需的默认值。

Microsoft 在内部使用此模型。 有关 Microsoft 实现 VPN 拆分隧道的信息，请参阅运行 VPN：Microsoft 如何保持远程 [工作人员连接](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)。

![拆分Tunnel VPN 模型 4。](../media/vpn-split-tunneling/vpn-model-4.png)

## <a name="5-no-vpn"></a>5. 无 VPN

型号 2 的更高级版本，其中任何内部服务都是通过新式安全方法或 SDWAN 解决方案发布的，如 Azure AD Proxy、Defender for Cloud Apps、Zscaler ZPA 等。

![拆分Tunnel VPN 模型 5。](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="related-articles"></a>相关文章

[概述：用于服务器的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[为用户实现 VPN 拆分Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[保护Teams VPN 拆分隧道的媒体流量](microsoft-365-vpn-securing-teams.md)

[VPN 环境中 Stream 和实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365中国用户优化性能](microsoft-365-networking-china.md)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365网络和性能优化](network-planning-and-performance.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 全球网络](/azure/networking/microsoft-global-network)
