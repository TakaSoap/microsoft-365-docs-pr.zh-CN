---
title: 保护用于 VPN 拆分隧道的 Teams 媒体流量
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
description: 保护用于 VPN 拆分隧道的 Teams 媒体流量
ms.openlocfilehash: 715d5e02ef01db9ef1c75a063ef5a2771d425f5c
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64715376"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>保护用于 VPN 拆分隧道的 Teams 媒体流量

>[!NOTE]
>本文是解决远程用户Microsoft 365优化的一组文章的一部分。

>- 有关使用 VPN 拆分隧道优化远程用户Microsoft 365连接的概述，请[参阅概述：用于Microsoft 365的 VPN 拆分隧道](microsoft-365-vpn-split-tunnel.md)。
>- 有关实现 VPN 拆分隧道的详细指南，请参阅[为Microsoft 365实现 VPN 拆分隧道](microsoft-365-vpn-implement-split-tunnel.md)。
>- 有关 VPN 拆分隧道方案的详细列表，请参阅[适用于Microsoft 365的常见 VPN 拆分隧道方案](microsoft-365-vpn-common-scenarios.md)。
>- 有关如何在 VPN 环境中配置流和实时事件的信息，请参阅 [VPN 环境中流和实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)。
>- 有关优化中国用户Microsoft 365全球租户性能的信息，[请参阅Microsoft 365中国用户的性能优化](microsoft-365-networking-china.md)。

某些Microsoft Teams管理员可能需要详细了解如何使用拆分隧道模型Teams调用流运行，以及如何保护连接。

## <a name="configuration"></a>配置

对于调用和会议，只要路由表中正确地提供了Teams媒体所需的优化 IP 子网，当Teams调用 [GetBestRoute 函](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute)数以确定哪个本地接口与它应该用于特定目标的路由相对应时，将在上面列出的 Microsoft IP 块中为 Microsoft 目标返回本地接口。

某些 VPN 客户端软件允许基于 URL 进行路由操作。 但是，Teams 媒体流量没有与之关联的 URL，因此必须使用 IP 子网来控制此流量路由。

在某些情况下（通常与 Teams 客户端配置无关），即使有正确的路由，媒体流量仍会遍历 VPN 隧道。 如果遇到这种情况，则使用防火墙规则阻止Teams IP 子网或端口使用 VPN 就足够了。

>[!IMPORTANT]
>若要确保在所有 VPN 方案中通过所需方法路由Teams媒体流量，请确保用户运行Microsoft Teams客户端版本 **1.3.00.13565** 或更高版本。 此版本包括对客户端检测可用网络路径的方式的改进。

信号流量通过 HTTPS 执行，且与媒体流量不区分延迟，在 URL/IP 数据中标记为 **"允许** "，因此可以根据需要安全地通过 VPN 客户端路由。

>[!NOTE]
>Microsoft Edge **96 及更高版本** 还支持对等流量的 VPN 拆分隧道。 例如，这意味着客户可以从 Edge 上Teams Web 客户端的 VPN 拆分隧道中获益。 想要为在 Edge 上运行的网站设置它的客户可以通过执行禁用 Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略的额外步骤来实现它。

### <a name="security"></a>安全

避免拆分隧道的一个常见论点是，这样做不太安全，即 任何未通过 VPN 隧道的流量都不会从应用于 VPN 隧道的任何加密方案中获益，因此安全性会降低。

对此的主要反对意见是，媒体流量已经通过 _安全实时传输协议 (SRTP)_ 进行了加密，该协议是实时传输协议 (RTP) 的一个配置文件，它为 RTP 流量提供保密性、身份验证和重播攻击保护。 SRTP 本身依赖于随机生成的会话密钥，该密钥通过 TLS 安全信令通道进行交换。 [本安全指南](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)中详细介绍了这一点，但主要部分是媒体加密。

媒体流量是使用 SRTP 加密的，SRTP 使用安全随机数生成器生成的会话密钥，并使用信令 TLS 通道进行交换。 此外，在中介服务器和其内部下一个跃点之间的双向媒体也使用 SRTP 进行加密。

Skype for Business Online 生成用户名/密码，可用于通过 _围绕 NAT 使用中继遍历 (TURN)_ 来安全访问媒体中继。 媒体中继通过 TLS 安全 SIP 信道交换用户名/密码。 值得注意的是，尽管 VPN 隧道可能用于将客户端连接到公司网络，但在离开公司网络到达服务时，流量仍需要以 SRTP 形式流动。

有关Teams如何缓解常见安全问题的信息，例如 _NAT (STUN) 放大攻击的会话遍历实用程序_，可在 [5.1 实施者的安全注意事项](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)中找到。

还可以阅读有关远程工作场景中的新式安全控制：[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

### <a name="testing"></a>测试

策略就绪后，应确认它按预期工作。 可通过多种方法来测试路径是否已正确设置为使用本地 Internet 连接：

- 运行[Microsoft 365连接测试](https://aka.ms/netonboard)，该测试将为你运行连接测试，包括上述跟踪路由。 我们还将 VPN 测试添加到此工具中，这些工具还应提供其他见解。

- 拆分隧道范围内终结点的简单 **跟踪器** 应显示所采用的路径，例如：

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  然后，应会看到一条通过本地 ISP 到此终结点的路径，该路径应解析为我们为拆分隧道配置的Teams范围内的 IP。

- 以使用 Wireshark 之类的工具进行网络捕获为例。 在呼叫期间筛选 UDP，应看到流量流向 Teams **优化** 范围中的 IP。 如果 VPN 隧道用于此流量，则媒体流量在跟踪中将不可见。

## <a name="additional-support-logs"></a>其他支持日志

如果需要更多数据来排除故障，或正在请求 Microsoft 支持部门的协助，获取以下信息可帮助你加快查找解决方案。 Microsoft 支持的 **TSS Windows基于 CMD 的通用故障排除脚本工具集** 可以帮助你以简单的方式收集相关日志。 可在 <https://aka.ms/TssTools>中找到有关使用的工具和说明。

## <a name="related-articles"></a>相关文章

[概述：用于Microsoft 365的 VPN 拆分隧道](microsoft-365-vpn-split-tunnel.md)

[为Microsoft 365实现 VPN 拆分隧道](microsoft-365-vpn-implement-split-tunnel.md)

[适用于Microsoft 365的常见 VPN 拆分隧道方案](microsoft-365-vpn-common-scenarios.md)

[VPN 环境中流和实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365中国用户的性能优化](microsoft-365-networking-china.md)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365网络和性能优化](network-planning-and-performance.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 全局网络](/azure/networking/microsoft-global-network)
