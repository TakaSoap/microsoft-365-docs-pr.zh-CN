---
title: 为用户实现 VPN 拆分Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/28/2022
audience: Admin
ms.article: conceptual
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
description: 如何为用户实现 VPN 拆分Microsoft 365
ms.openlocfilehash: 59414e32f187dc4e8354dc0c20228a4222fa2754
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281178"
---
# <a name="implementing-vpn-split-tunneling-for-microsoft-365"></a>为用户实现 VPN 拆分Microsoft 365

>[!NOTE]
>本文是一组文章的一部分，这些文章Microsoft 365远程用户的优化。

>- 有关使用 VPN 拆分隧道优化远程Microsoft 365连接的概述，请参阅概述：适用于远程用户的 [VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)。
>- 有关为中国用户Microsoft 365全球租户性能的信息，请参阅Microsoft 365[中国用户优化性能](microsoft-365-networking-china.md)。

多年来，企业一直使用 VPN 来支持其用户的远程体验。 尽管核心工作负载仍位于本地，但通过企业网络上的数据中心路由的远程客户端中的 VPN 是远程用户访问公司资源的主要方法。 为保证这些连接的安全性，企业将沿 VPN 路径构建网络安全解决方案层。 构建此安全是为了保护内部基础结构，并通过将流量重新路由到 VPN 然后通过本地 Internet 外围来保护外部网站的移动浏览。 VPN、网络外围和相关安全基础结构通常是针对定义的流量进行特意构建和扩展的，通常大多数连接都是从企业网络内部启动的，并且大部分连接都位于内部网络边界内。

在相当长的一段时间内，只要远程用户的并发规模适中且遍历 VPN 的流量较低，那么所有来自远程用户设备的连接都被路由回本地网络的 VPN 模型（这称为 _强制隧道_）基本上是可持续的。  一些客户继续使用 VPN 强制隧道作为状态仲裁，即使他们的应用程序从企业外围内部移动到公共 SaaS 云也是如此。

使用强制隧道 VPN 连接到分布式和性能敏感的云应用程序是非优化的，但为了维持安全状态仲裁，一些企业已接受负面影响。 下面是此场景的一个示例图：

![拆分Tunnel VPN 配置。](../media/vpn-split-tunneling/enterprise-network-traditional.png)

此问题多年来一直在增长，许多客户报告网络流量模式发生显著变化。 过去位于本地的流量现在连接到外部云终结点。 许多 Microsoft 客户报告，以前大约 80% 的网络流量是发往某些内部源 (由上图中的虚线表示) 。 2020 年，随着主要工作负载转移到云，这一数字现在约为 20% 或更低，这些趋势在其他企业中并不少见。 随着时间的推移，随着云之旅的发展，上述模型变得越来越麻烦和麻烦，从而阻止组织在进入云第一世界时变得敏捷。

全球 COVID-19 危机升级了此问题，需要立即修正。 确保员工安全的需要对企业 IT 部门提出了前所未有的要求，要求他们支持大规模在家办公的工作效率。 Microsoft 365可以帮助客户满足该需求，但在家工作的用户的高并发性会产生大量 Microsoft 365 流量，如果通过强制隧道 VPN 和本地网络外围进行路由，则会导致快速饱和并运行容量不足的 VPN 基础结构。 在此新现实中，使用 VPN 访问 Microsoft 365 不再是性能障碍，而是一个不仅影响 Microsoft 365 而且仍然必须依赖 VPN 才能运行的关键业务运营的硬墙。

多年来，Microsoft 一直与客户和更广泛的行业紧密协作，从我们自己的服务中为这些问题提供有效的新式解决方案，并与行业最佳做法保持一致。 [Microsoft 365](./microsoft-365-network-connectivity-principles.md) 服务的连接原则旨在高效地为远程用户工作，同时仍允许组织维护安全性和控制其连接性。 这些解决方案也可在有限的工作下快速实施，但是对上述问题产生显著正面影响。

Microsoft 建议用于优化远程工作者连接的策略侧重于快速缓解问题和通过几个简单步骤提供高性能。 这些步骤为绕过瓶颈 VPN 服务器的一些已定义终结点调整旧 VPN 方法。 可在不同的层应用等效的或甚至是更高级的安全模型，而无需在公司网络出口保护所有流量。 在大多数情况下，这可以在数小时内有效实现，然后可扩展为其他工作负载，因为要求要求和时间允许。

## <a name="common-vpn-scenarios"></a>常见 VPN 方案

在下面的列表中，你将看到在企业环境中看到的最常见的 VPN 方案。 大多数客户通常运行模型 1（VPN 强制隧道）。 本节将帮助您快速安全地过渡到模型 **2**，这可以通过相对少的工作实现，并且对网络性能和用户体验具有巨大优势。

| 模型 | 说明 |
| --- | --- |
| [1. VPN 强制隧道](#1-vpn-forced-tunnel) | 100% 的流量进入 VPN 隧道，包括本地、Internet 以及所有 O365/M365 |
| [2. VPN 强制隧道（有几个例外）](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | 默认情况下使用 VPN 隧道（默认路由指向 VPN），有几个最重要的豁免场景允许直接访问 |
| [3. VPN 强制隧道（有多个例外）](#3-vpn-forced-tunnel-with-broad-exceptions) | 默认情况下，使用 VPN 隧道 (默认路由指向 VPN) ，但允许直接进入 VPN 通道 (如所有 Microsoft 365、All Salesforce、All Zoom)  |
| [4. VPN 选择性隧道](#4-vpn-selective-tunnel) | VPN 隧道仅用于基于公司网络的服务。 默认路由 (Internet，所有基于 Internet 的服务) 直接路由。 |
| [5. 无 VPN](#5-no-vpn) | #2 的变体。 所有 (公司网络服务都通过现代安全方法（如 Zscaler ZPA、Azure Active Directory (Azure AD) 代理/MCAS 等）发布)  |

### <a name="1-vpn-forced-tunnel"></a>1. VPN 强制隧道

大多数企业客户最常见的开始方案。 使用强制 VPN，这意味着无论终结点是否驻留在企业网络内，100% 的流量将定向到企业网络。 任何外部 (Internet) 流量（如 Microsoft 365 或 Internet 浏览）随后会回流到内部部署安全设备（如代理）的后面。 在当前近 100% 的用户远程工作的当前情况中，此模型对 VPN 基础结构造成高负载，并且可能会显著妨碍所有公司流量的性能，进而使企业在危机时高效运行。

![VPN 强制Tunnel模型 1。](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN 强制隧道（有几个受信任的异常）

企业在企业下运营的效率明显提高。 此模型允许几个高负载和延迟敏感的受控和定义的终结点绕过 VPN 隧道并直接转到 Microsoft 365 服务。 这显著提高了卸载服务的性能，还减少了 VPN 基础结构上的负载，从而允许仍然需要它的元素以较低的资源争用运行。 正是此模型，本文侧重于协助过渡到 ，因为它允许快速执行简单的已定义操作，并产生大量积极结果。

![拆分Tunnel VPN 模型 2。](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN 强制隧道（有多个例外）

扩大模型 2 的范围。 它不再直接发送一小组定义的终结点，而是直接将所有流量发送到受信任的服务（如 Microsoft 365 和 SalesForce）。 这可进一步减少公司 VPN 基础结构的负载，并提高已定义服务的性能。 由于此模型可能需要更多时间来评估和实施是否可行，因此在成功实施模型 2 后，稍后可能会反复执行一个步骤。

![拆分Tunnel VPN 模型 3。](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN 选择性隧道

反转第三个模型，因为只有标识为具有企业 IP 地址的流量通过 VPN 隧道发送，因此 Internet 路径是其他所有内容的默认路由。 此模型要求组织能够很好地适应[零信任](https://www.microsoft.com/security/zero-trust?rtc=1)路径，以便能够安全地实现此模型。 应该注意到，随着更多服务从企业网络移入云，此模型或一些变体可能会随着时间的推移成为必需的默认值。

Microsoft 在内部使用此模型。 有关 Microsoft 实现 VPN 拆分隧道的信息，请参阅运行 VPN：Microsoft 如何保持远程 [工作人员连接](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)。

![拆分Tunnel VPN 模型 4。](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. 无 VPN

型号 2 的更高级版本，其中任何内部服务都通过新式安全方法或 SDWAN 解决方案发布，如 Azure AD Proxy、Defender for Cloud Apps、Zscaler ZPA 等。

![拆分Tunnel VPN 模型 5。](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>实现 VPN 拆分隧道

在此部分中，你将发现在常见 VPN 方案中将 VPN 客户端体系结构从 _VPN_ 强制隧道迁移到 _VPN_ 强制隧道所需的简单步骤，这些异常有几个受信任的异常，即 VPN 拆分隧道模型 [#2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions)。[](#common-vpn-scenarios)

下图显示了建议的 VPN 拆分隧道解决方案的工作原理：

![拆分隧道 VPN 解决方案详细信息。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. 标识要优化的终结点

在Microsoft 365 [URL 和 IP](urls-and-ip-address-ranges.md) 地址范围文章中，Microsoft 清楚地标识了需要优化的关键终结点，并将它们分类为 **"优化"**。 目前仅需要优化四个 URL 和 20 个 IP 子网。 这一小组终结点大约占到 Microsoft 365 服务的流量的 70% - 80%，包括延迟敏感终结点（如用于 Teams 的终结点）。 实质上，这是我们需要特别注意的流量，也是对传统网络路径和 VPN 基础结构造成压力的流量。

此类别中的 URL 具有以下特征：

- 为 Microsoft 拥有和托管的终结点，托管在 Microsoft 基础结构上
- 提供了 IP
- 低更改率，预计仍保持较小数量（目前有 20 个 IP 子网）
- 带宽和/或延迟敏感
- 可在服务中提供所需的安全元素，而不是在网络上内联
- 将大约 70-80% 的流量用于Microsoft 365流量

有关终结点Microsoft 365如何分类和管理它们，请参阅管理Microsoft 365[终结点](managing-office-365-endpoints.md)。

#### <a name="optimize-urls"></a>优化 URL

可在下表找到当前的优化 URL。 在大多数情况下，只需在[浏览器 PAC 文件](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)中使用 URL 终结点，其中终结点被配置为直接发送，而不是发送到代理。

| 优化 URL | 端口/协议 | 用途 |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | 这是 Outlook 用于连接到其 Exchange Online Server 并具有较高带宽使用率和连接计数的主要 URL 之一。 以下联机功能需要低网络延迟：即时搜索、其他邮箱日历、忙/闲查找、管理规则和通知、Exchange Online 存档和电子邮件传出发件箱。 |
| <https://outlook.office.com> | TCP 443 | 此 URL 供 Outlook Online Web 访问用于连接到 Exchange Online Server，并且对网络延迟非常敏感。 使用 SharePoint Online 上传和下载大型文件尤其需要连接。 |
| \<tenant\>https://.sharepoint.com | TCP 443 | 这是 SharePoint Online 的主要 URL，并且具有高带宽使用率。 |
| \<tenant\>https://-my.sharepoint.com | TCP 443 | 这是 OneDrive for business 的主要 URL，具有较高的带宽使用率，并且可能会产生来自 OneDrive for Business 同步工具的高连接计数。 |
| Teams 媒体 IP（无 URL） | UDP 3478、3479、3480 和 3481 | 中继发现分配和实时流量 (3478) 、音频 (3479) 、视频 (3480) 和视频屏幕共享 (3481) 。 这些终结点用于Skype for Business Microsoft Teams媒体流量 (通话、会议等) 。 当 Microsoft Teams 客户端建立呼叫时，将提供大多数终结点（并包含在为该服务列出的所需 IP 内）。 若要获得最佳媒体质量，需要使用 UDP 协议。   |

在以上示例中，**租户** 应替换为你的Microsoft 365名称。 例如， **contoso.onmicrosoft.com** _使用 contoso.sharepoint.com_ 和 _contoso-my.sharepoint.com_。

#### <a name="optimize-ip-address-ranges"></a>优化 IP 地址范围

在写入这些终结点所对应的 IP 地址范围时，如下所示。 强烈建议你在应用配置时使用脚本（如此示例[](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category)、[Microsoft 365 IP 和 URL](microsoft-365-ip-web-service.md) Web 服务或 [URL/IP](urls-and-ip-address-ranges.md) 页面）检查是否有更新，并定期制定策略。

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. 通过 VPN 优化对这些终结点的访问

我们已确定这些关键终结点，现在需要将其从 VPN 隧道移出，并允许它们使用用户的本地 Internet 连接直接连接到服务。 完成此操作的方式将因使用的 VPN 产品和计算机平台而异，但大多数 VPN 解决方案将允许简单配置策略来应用此逻辑。 有关 VPN 平台特定的拆分隧道指南，请参阅[常见 VPN 平台的操作指南](#howto-guides-for-common-vpn-platforms)。

如果要手动测试解决方案，可执行以下 PowerShell 示例，以在路由表级别模拟解决方案。 本例将每个 Teams 媒体 IP 子网的路由添加到路由表中。 可以在之前和之后测试 Teams 媒体性能，并观察指定终结点路由的差异。

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>示例：将 Teams 媒体 IP 子网添加到路由表

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

在上面的脚本中，_$intIndex_ 是连接到 Internet 的接口索引（可通过在 PowerShell 中运行 **get-netadapter** 找到；查找 _ifIndex_ 的值），_$gateway_ 是该接口的默认网关（可通过在命令提示符中运行 **ipconfig** 或在 PowerShell 中运行 **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** 找到）。

添加路由后，可通过在命令提示符或 PowerShell 中运行 **route print** 来确认路由表是否正确。 输出应包含添加的路由，显示接口索引（本例为 _22_）和该接口的网关（本例为 _192.168.1.1_）：

![路由打印输出。](../media/vpn-split-tunneling/vpn-route-print.png)

若要为"优化"类别中的所有当前 IP 地址范围添加路由，可以使用以下脚本变体查询 [Microsoft 365 IP 和 URL Web](microsoft-365-ip-web-service.md) 服务中的当前"优化 IP 子网"集，并将其添加到路由表中。

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>示例：将所有优化子网添加到路由表

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

如果无意中添加了错误参数的路由，或者只是希望还原所做的更改，则可以使用以下命令删除刚添加的路由：

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

应配置 VPN 客户端，以便 **优化** IP 的流量以此方式路由。 这允许流量利用本地 Microsoft 资源，如 Microsoft 365 Service Front Door，如 [Azure Front Door](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/)，可提供尽可能接近你的用户的 Microsoft 365 服务和连接终结点。 这使我们能够为位于世界任何位置的用户提供高性能级别，并充分利用 [Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 的世界一流的全局网络，这很可能在用户的直接出口几毫秒内完成。

## <a name="configuring-and-securing-teams-media-traffic"></a>配置和保护 Teams 媒体流量

一些管理员可能需要更详细的信息，了解如何在使用拆分隧道模型的 Teams 中进行呼叫流操作，以及如何保护连接。

### <a name="configuration"></a>配置

对于呼叫和会议，只要路由表中正确放置了 Teams 媒体所需的"优化 IP 子网"，当 Teams 调用 [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) 函数以确定哪个本地接口对应于它应用于特定目的地的路由时，将为上面列出的 Microsoft IP 块中的 Microsoft 目标返回本地接口。

某些 VPN 客户端软件允许基于 URL 进行路由操作。 但是，Teams 媒体流量没有与之关联的 URL，因此必须使用 IP 子网来控制此流量路由。

在某些情况下（通常与 Teams 客户端配置无关），即使有正确的路由，媒体流量仍会遍历 VPN 隧道。 如果遇到这种情况，则使用防火墙规则阻止 ip Teams或端口使用 VPN 就足够了。

>[!IMPORTANT]
>若要Teams VPN 方案中通过所需方法路由媒体流量，请确保用户运行的是 Microsoft Teams 客户端版本 **1.3.00.13565** 或更大版本。 此版本包括客户端检测可用网络路径的改进。

信号流量通过 HTTPS 执行，对延迟没有媒体流量敏感，在 URL/IP 数据中标记为"允许"，因此如果需要，可以安全地通过 VPN 客户端进行路由。

>[!NOTE]
>Microsoft Edge **96 及** 以上设备还支持对等流量的 VPN 拆分隧道。 这意味着客户可以受益于边缘上 Teams Web 客户端的 VPN 拆分隧道。 想要为在 Edge 上运行的网站设置它的客户可以通过执行启用 Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略的其他步骤来实现此目的。

### <a name="security"></a>安全性

避免拆分隧道的一个常见参数是这样做安全性较低，即 任何未通过 VPN 隧道的流量将不会从应用于 VPN 隧道的任何加密方案中获益，因此安全性较低。

对此的主要反对意见是，媒体流量已经通过 _安全实时传输协议 (SRTP)_ 进行了加密，该协议是实时传输协议 (RTP) 的一个配置文件，它为 RTP 流量提供保密性、身份验证和重播攻击保护。 SRTP 本身依赖于随机生成的会话密钥，该密钥通过 TLS 安全信令通道进行交换。 [本安全指南](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)中详细介绍了这一点，但主要部分是媒体加密。

媒体流量是使用 SRTP 加密的，SRTP 使用安全随机数生成器生成的会话密钥，并使用信令 TLS 通道进行交换。 此外，在中介服务器和其内部下一个跃点之间的双向媒体也使用 SRTP 进行加密。

Skype for Business Online 生成用户名/密码，可用于通过 _围绕 NAT 使用中继遍历 (TURN)_ 来安全访问媒体中继。 媒体中继通过 TLS 安全 SIP 信道交换用户名/密码。 值得注意的是，即使 VPN 隧道可用于将客户端连接到企业网络，当流量离开企业网络到达服务时，仍然需要以 SRTP 形式流动。

有关安全Teams消除常见安全问题的信息，如 _NAT (STUN)_ 放大攻击的语音或会话遍历实用程序，请参阅 [5.1](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c) 实施者的安全注意事项。

还可以阅读有关远程工作场景中的新式安全控制：[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

### <a name="testing"></a>测试

策略就位后，应确认它是否正常工作。 可通过多种方法来测试路径是否已正确设置为使用本地 Internet 连接：

- 运行Microsoft 365[连接](https://aka.ms/netonboard)测试，该测试将针对您运行连接测试，包括如上所述的跟踪路由。 我们还将 VPN 测试添加到此工具中，这还应提供其他见解。

- 指向拆分隧道范围内终结点的简单 **tracert** 应显示使用的路径，例如：

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  然后，应看到通过本地 ISP 到此终结点的路径，该路径应解析为Teams拆分隧道配置的范围中的 IP。

- 以使用 Wireshark 之类的工具进行网络捕获为例。 在呼叫期间筛选 UDP，应看到流量流向 Teams **优化** 范围中的 IP。 如果 VPN 隧道正用于此流量，则媒体流量在跟踪中不可见。

### <a name="additional-support-logs"></a>其他支持日志

如果需要更多数据来排除故障，或正在请求 Microsoft 支持部门的协助，获取以下信息可帮助你加快查找解决方案。 Microsoft 支持的 **TSS Windows基于 CMD 的通用 TroubleShooting 脚本** 工具集可帮助您以一种简单方式收集相关日志。 有关使用的工具和说明，请参阅 <https://aka.ms/TssTools>。

## <a name="how-to-optimize-stream--live-events"></a>如何优化流&实时事件

Microsoft 365 实时事件流量 (这包括 Teams 生成的实时事件以及使用外部编码器通过 Teams、Stream 或 Yammer) 生成的事件，并且按需 Stream 流量当前在服务的 [URL/IP](urls-and-ip-address-ranges.md) 列表中被分类为默认与优化。  这些终结点被归类为 **默认** 终结点，因为它们托管在其他服务也可能使用的 CDN 上。 客户通常倾向于代理此类流量，并应用通常在此类终结点上执行的任何安全元素。

许多客户都要求输入将用户直接从本地 Internet 连接连接到 Stream/Live 事件所需的 URL/IP 数据，而不是通过 VPN 基础结构路由高容量和延迟敏感的流量。 通常，如果没有专用命名空间和终结点的准确 IP 信息（未为分类为"默认"的 Microsoft 365提供此信息，则不可能 **实现此操作**。

使用以下步骤为使用强制隧道 VPN 的客户端直接连接 Stream/Live Events 服务。 此解决方案旨在为客户提供一个选项，以避免由于在家工作方案导致网络流量较高时通过 VPN 路由实时事件流量。 如果可能，建议通过检查代理访问服务。

>[!NOTE]
>使用此解决方案时，可能存在未解析为提供的 IP 地址并因此遍历 VPN 的服务元素，但应大量流量（如流式数据）。 此卸载可能会捕获 Live 事件/Stream 范围之外的其他元素，但应限制这些元素，因为它们在直接传输之前必须满足 _FQDN 和_ IP 匹配。

>[!IMPORTANT]
>建议客户通过实时事件的性能提升权衡发送更多流量绕过 VPN 的风险。

若要为实时事件和 Stream Teams强制隧道异常，应应用以下步骤：

### <a name="1-configure-external-dns-resolution"></a>1. 配置外部 DNS 解析

客户端需要外部的递归 DNS 解析可用，以便以下主机名可以解析为 IP 地址。

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** 用于 Stream 事件 ([配置 Microsoft Stream 中的实时流式传输的编码器 - Microsoft Stream |Microsoft Docs](/stream/live-encoder-setup)) 。

**\*.media.azure.net** 和 **\*.bmc.cdn.office.net** 用于 Teams 生成的实时事件 (快速启动事件，RTMP-In 支持的事件 [路线图 ID 84960]) 从 Teams 客户端计划。

 其中一些终结点与 Stream/Live 事件之外的其他元素共享，建议不要仅使用这些 FQDN 配置 VPN 卸载，即使从技术上说，VPN 解决方案 (例如，它在 FQDN 而非 IP) 中运行。

VPN 配置中不需要 FQDN，它们完全用于 PAC 文件与 IP 以直接发送相关流量。

### <a name="2-implement-pac-file-changes-where-required"></a>2. 在需要时 (PAC 文件) 

对于在 VPN 上利用 PAC 文件通过代理路由流量的组织，这通常使用 FQDN 实现。 但是，对于 Stream/Live **\*** 事件，提供的主机名包含通配符（如 .azureedge.net）也包含无法提供完整 IP 列表的其他元素。 因此，如果仅根据 DNS 通配符匹配直接发送请求，则到这些终结点的流量将被阻止，因为步骤 3 中没有通过它的直接路径的 [路由](#3-configure-routing-on-the-vpn-to-enable-direct-egress)。

若要解决此问题，我们可以提供以下 IP，并结合使用它们和示例 PAC 文件中步骤 [1](#1-configure-external-dns-resolution) 中的主机名。 PAC 文件检查 URL 是否与用于 Stream/Live 事件的 URL 匹配，如果匹配，则检查从 DNS 查找返回的 IP 是否与为服务提供的 IP 匹配。 如果 _两_ 者匹配，则直接路由流量。 如果 FQDN/IP (中的任一元素) 不匹配，则流量将发送到代理。 因此，配置可确保解析为 IP 和已定义命名空间作用域之外的 IP 的一切内容都将正常通过 VPN 遍历代理。

#### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>收集当前终结点CDN列表

实时事件使用多个CDN提供商流式传输给客户，以提供最佳覆盖范围、质量和复原能力。 目前，同时Azure CDN Microsoft 和 Verizon 进行下载。 随着时间的推移，可能会由于区域可用性等情况而更改此情况。 本文是让你能够及时了解 IP 范围最新信息的来源。

For Azure CDN from Microsoft， you can download the list [from Download Azure IP Ranges and Service Tags – Public Cloud from Official Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=56519) - you will need to look specifically for the service tag *AzureFrontdoor.Frontend* in the JSON;*addressPrefixes* 将显示 IPv4/IPv6 子网。 随着时间的推移，IP 可能会更改，但服务标记列表始终在被使用之前更新。

For Azure CDN from Verizon (Edgecast) you can find an exhaustive list using [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list) (click **Try It** ) - you will need to look specifically for the **高级版\_Verizon** section. 请注意，此 API 显示源 (和任意) 。 目前，API 没有用于区分源和任意播的机制。

若要在 PAC 文件中实现此操作，可以使用以下示例发送 Microsoft 365 Optimize 流量直通 (推荐最佳做法) 通过 FQDN，以及关键流/实时事件流量通过 FQDN 和返回的 IP 地址的组合直接发送。 需要将 _占位符名称 Contoso_ 编辑为特定租户的名称， _其中 contoso_ 来自 contoso.onmicrosoft.com

##### <a name="example-pac-file"></a>示例 PAC 文件

下面是如何生成 PAC 文件的示例：

1. 将下面的脚本另存为本地硬盘 _Get-TLEPacFile.ps1_。
1. 转到 [Verizon URL](/rest/api/cdn/edge-nodes/list#code-try-0) 并下载生成的 JSON (将其复制到 cdnedgenodes.json) 
1. 将文件放入与脚本相同的文件夹中。
1. 在 PowerShell 窗口中，运行以下命令。 如果需要 SPO URL，请为其他内容更改租户名称。 这是类型 2，因此类型 **1 ("** 优化"和"允许") 。

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac 文件将包含 IPv4/IPv6 (的所有命名空间和 IP) 。

###### <a name="get-tlepacfileps1"></a>Get-TLEPacFile.ps1

```powershell
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

<#PSScriptInfo

.VERSION 1.0.4

.AUTHOR Microsoft Corporation

.GUID 7f692977-e76c-4582-97d5-9989850a2529

.COMPANYNAME Microsoft

.COPYRIGHT
Copyright (c) Microsoft Corporation. All rights reserved.
Licensed under the MIT License.

.TAGS PAC Microsoft Microsoft365 365

.LICENSEURI

.PROJECTURI http://aka.ms/ipurlws

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

#>

<#

.SYNOPSIS

Create a PAC file for Microsoft 365 prioritized connectivity

.DESCRIPTION

This script will access updated information to create a PAC file to prioritize Microsoft 365 Urls for
better access to the service. This script will allow you to create different types of files depending
on how traffic needs to be prioritized.

.PARAMETER Instance

The service instance inside Microsoft 365.

.PARAMETER ClientRequestId

The client request id to connect to the web service to query up to date Urls.

.PARAMETER DirectProxySettings

The direct proxy settings for priority traffic.

.PARAMETER DefaultProxySettings

The default proxy settings for non priority traffic.

.PARAMETER Type

The type of prioritization to give. Valid values are 1 and 2, which are 2 different modes of operation.
Type 1 will send Optimize traffic to the direct route. Type 2 will send Optimize and Allow traffic to
the direct route.

.PARAMETER Lowercase

Flag this to include lowercase transformation into the PAC file for the host name matching.

.PARAMETER TenantName

The tenant name to replace wildcard Urls in the webservice.

.PARAMETER ServiceAreas

The service areas to filter endpoints by in the webservice.

.PARAMETER FilePath

The file to print the content to.

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type1.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance China -Type 2 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type2.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance WorldWide -Lowercase -TenantName tenantName -ServiceAreas Sharepoint

#>

#Requires -Version 2

[CmdletBinding(SupportsShouldProcess=$True)]
Param (
    [Parameter(Mandatory = $false)]
    [ValidateSet('Worldwide', 'Germany', 'China', 'USGovDoD', 'USGovGCCHigh')]
    [String] $Instance = "Worldwide",

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [guid] $ClientRequestId = [Guid]::NewGuid().Guid,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DirectProxySettings = 'DIRECT',

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DefaultProxySettings = 'PROXY 10.10.10.10:8080',

    [Parameter(Mandatory = $false)]
    [ValidateRange(1, 2)]
    [int] $Type = 1,

    [Parameter(Mandatory = $false)]
    [switch] $Lowercase = $false,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $TenantName,

    [Parameter(Mandatory = $false)]
    [ValidateSet('Exchange', 'SharePoint', 'Common', 'Skype')]
    [string[]] $ServiceAreas,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $FilePath,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $CdnEdgeNodesFilePath
)

##################################################################################################################
### Global constants
##################################################################################################################

$baseServiceUrl = "https://endpoints.office.com/endpoints/$Instance/?ClientRequestId={$ClientRequestId}"
$directProxyVarName = "direct"
$defaultProxyVarName = "proxyServer"
$bl = "`r`n"

##################################################################################################################
### Functions to create PAC files
##################################################################################################################

function Get-PacClauses
{
    param(
        [Parameter(Mandatory = $false)]
        [string[]] $Urls,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $ReturnVarName
    )

    if (!$Urls)
    {
        return ""
    }

    $clauses =  (($Urls | ForEach-Object { "shExpMatch(host, `"$_`")" }) -Join "$bl        || ")

@"
    if($clauses)
    {
        return $ReturnVarName;
    }
"@
}

function Get-PacString
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [array[]] $MapVarUrls
    )

@"
// This PAC file will provide proxy config to Microsoft 365 services
//  using data from the public web service for all endpoints
function FindProxyForURL(url, host)
{
    var $directProxyVarName = "$DirectProxySettings";
    var $defaultProxyVarName = "$DefaultProxySettings";

$( if ($Lowercase) { "    host = host.toLowerCase();" })

$( ($MapVarUrls | ForEach-Object { Get-PACClauses -ReturnVarName $_.Item1 -Urls $_.Item2 }) -Join "$bl$bl" )

$( if (!$ServiceAreas -or $ServiceAreas.Contains('Skype')) { Get-TLEPacConfiguration })

    return $defaultProxyVarName;
}
"@ -replace "($bl){3,}","$bl$bl" # Collapse more than one blank line in the PAC file so it looks better.
}

##################################################################################################################
### Functions to get and filter endpoints
##################################################################################################################

function Get-TLEPacConfiguration {
    param ()
    $PreBlock = @"
    // Don't Proxy Teams Live Events traffic

    if(shExpMatch(host, "*.azureedge.net")
    || shExpMatch(host, "*.bmc.cdn.office.net")
    || shExpMatch(host, "*.media.azure.net"))
    {
        var resolved_ip = dnsResolveEx(host);

"@
    $TLESb = New-Object 'System.Text.StringBuilder'
    $TLESb.Append($PreBlock) | Out-Null

    if (![string]::IsNullOrEmpty($CdnEdgeNodesFilePath) -and (Test-Path -Path $CdnEdgeNodesFilePath)) {
        $CdnData = Get-Content -Path $CdnEdgeNodesFilePath -Raw -ErrorAction SilentlyContinue | ConvertFrom-Json | Select-Object -ExpandProperty value | 
            Where-Object { $_.name -eq 'Premium_Verizon'} | Select-Object -First 1 -ExpandProperty properties | 
            Select-Object -ExpandProperty ipAddressGroups
        $CdnData | Select-Object -ExpandProperty ipv4Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
        $CdnData | Select-Object -ExpandProperty ipv6Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
    }
    $AzureIPsUrl = Invoke-WebRequest -Uri "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" -UseBasicParsing -ErrorAction SilentlyContinue  | 
            Select-Object -ExpandProperty Links | Select-Object -ExpandProperty href | 
            Where-Object { $_.EndsWith('.json') -and $_ -match 'ServiceTags' } | Select-Object -First 1
    if ($AzureIPsUrl) {
        Invoke-RestMethod -Uri $AzureIPsUrl -ErrorAction SilentlyContinue | Select-Object -ExpandProperty values | 
            Where-Object { $_.name -eq 'AzureFrontDoor.Frontend' } | Select-Object -First 1 -ExpandProperty properties |
            Select-Object -ExpandProperty addressPrefixes | ForEach-Object {
                if ($TLESb.Length -eq $PreBlock.Length) {
                    $TLESb.Append("        if(") | Out-Null
                }
                else {
                    $TLESb.AppendLine() | Out-Null
                    $TLESb.Append("        || ") | Out-Null
                }
                $TLESb.Append("isInNetEx(resolved_ip, `"$_`")") | Out-Null
            }
    }
    if ($TLESb.Length -gt $PreBlock.Length) {
        $TLESb.AppendLine(")") | Out-Null
        $TLESb.AppendLine("        {") | Out-Null
        $TLESb.AppendLine("            return $directProxyVarName;") | Out-Null
        $TLESb.AppendLine("        }") | Out-Null
    }
    else {
        $TLESb.AppendLine("        // no addresses found for service via script") | Out-Null
    }
    $TLESb.AppendLine("    }") | Out-Null
    return $TLESb.ToString()
}

function Get-Regex
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $Fqdn
    )

    return "^" + $Fqdn.Replace(".", "\.").Replace("*", ".*").Replace("?", ".?") + "$"
}

function Match-RegexList
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $ToMatch,

        [Parameter(Mandatory = $false)]
        [string[]] $MatchList
    )

    if (!$MatchList)
    {
        return $false
    }
    foreach ($regex in $MatchList)
    {
        if ($regex -ne $ToMatch -and $ToMatch -match (Get-Regex $regex))
        {
            return $true
        }
    }
    return $false
}

function Get-Endpoints
{
    $url = $baseServiceUrl
    if ($TenantName)
    {
        $url += "&TenantName=$TenantName"
    }
    if ($ServiceAreas)
    {
        $url += "&ServiceAreas=" + ($ServiceAreas -Join ",")
    }
    return Invoke-RestMethod -Uri $url
}

function Get-Urls
{
    param(
        [Parameter(Mandatory = $false)]
        [psobject[]] $Endpoints
    )

    if ($Endpoints)
    {
        return $Endpoints | Where-Object { $_.urls } | ForEach-Object { $_.urls } | Sort-Object -Unique
    }
    return @()
}

function Get-UrlVarTuple
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $VarName,

        [Parameter(Mandatory = $false)]
        [string[]] $Urls
    )
    return New-Object 'Tuple[string,string[]]'($VarName, $Urls)
}

function Get-MapVarUrls
{
    Write-Verbose "Retrieving all endpoints for instance $Instance from web service."
    $Endpoints = Get-Endpoints

    if ($Type -eq 1)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -eq "Optimize" })
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -ne "Optimize" }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
    elseif ($Type -eq 2)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -in @("Optimize", "Allow")})
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -notin @("Optimize", "Allow") }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
}

##################################################################################################################
### Main script
##################################################################################################################

$content = Get-PacString (Get-MapVarUrls)

if ($FilePath)
{
    $content | Out-File -FilePath $FilePath -Encoding ascii
}
else
{
    $content
}
```

脚本将基于 **AzureFrontDoor.Frontend** 的下载 [URL](https://www.microsoft.com/download/details.aspx?id=56519) 和密钥自动分析 Azure 列表，因此无需手动获取。

同样，建议不要仅使用 FQDN 执行 VPN 卸载;利用 **函数** 中的 FQDN 和 IP 地址有助于将使用此卸载的范围限定为一组有限的终结点，包括 Live Events/Stream。 构建函数的方式将导致对直接匹配客户端列出的 FQDN（即剩余命名空间的 DNS 解析保持不变）执行 DNS 查找。

如果您希望限制卸载与 Live 事件和 Stream **\*** 不相关的终结点的风险，可以从配置中删除 .azureedge.net 域，此风险大部分位于此配置中，因为这是用于所有 Azure CDN 客户的共享域。 这样做的缺点是，使用外部编码器的任何事件将不会得到优化，但在外部编码器内生成/Teams事件。

### <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. 在 VPN 上配置路由以启用直接出口

最后一步是将收集 **CDN** 终结点的当前列表中描述的实时事件 IP 的直接路由添加到 VPN 配置中，以确保流量不会通过强制隧道发送到 VPN。 有关如何为 Microsoft 365 Optimize 终结点进行此操作的详细信息，请参阅实现 [VPN](#implement-vpn-split-tunneling) 拆分隧道部分，此过程与本文档中列出的 Stream/Live 事件 IP 完全相同。

请注意，只有 IP (FQDN) 收集当前终结点CDN[，](#gathering-the-current-lists-of-cdn-endpoints)才应该用于 VPN 配置。

### <a name="stream--live-events-optimization-faq"></a>流&实时事件优化常见问题解答

#### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>这会将我的所有流量直接发送到服务吗？

否，这将发送实时事件或 Stream 视频直接的延迟敏感流流量，任何其他流量如果未解析到发布的 IP，将继续使用 VPN 隧道。

#### <a name="do-i-need-to-use-the-ipv6-addresses"></a>是否需要使用 IPv6 地址？

否，连接只能是 IPv4（如果需要）。

#### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>为什么这些 IP 未在 URL/IP Microsoft 365中发布？

Microsoft 对服务中信息的格式和类型进行严格控制，以确保客户能够可靠地使用该信息来实现基于终结点类别的安全和最佳路由。

由于多种原因，默认终结点类别没有提供 IP 信息 (默认终结点可能超出 Microsoft 控制范围、可能更改过于频繁，或者可能位于与其他元素或) 共享的块中。 因此，默认终结点设计为通过 FQDN 发送到检查代理，如正常的 Web 流量。

在这种情况下，上述终结点可能是非 Microsoft 控制的元素（非实时事件或 Stream）使用的 CDN，因此直接发送流量也意味着解析为这些 IP 的任何其他内容也将从客户端直接发送。 鉴于当前全球危机的独特性质，为满足我们的客户的短期需求，Microsoft 已提供上述信息供客户根据情况使用。

Microsoft 正在努力重新配置实时事件终结点，以允许它们在将来包含在允许/优化终结点类别中。

#### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>是否仅需要允许访问这些 IP？

否，访问 [URL/IP](urls-and-ip-address-ranges.md) 服务中所有必需的标记终结点对于服务运行至关重要。 此外，任何标记为 Stream (ID 为 41-45) 可选终结点。

#### <a name="what-scenarios-will-this-advice-cover"></a>此建议将涵盖哪些方案？

1. Teams App 内生成的实时事件
2. 查看 Stream 托管内容
3. 外部设备 (编码器) 生成的事件

#### <a name="does-this-advice-cover-presenter-traffic"></a>此建议是否涵盖演示者流量？

它不一样，上述建议完全适用于使用服务的人。 从 Teams 内演示将看到演示者的流量流向 URL/IP 服务行 11 中列出的标记为优化的 UDP 终结点，其中具有实施 VPN 拆分隧道一节中列出的详细 [VPN](#implement-vpn-split-tunneling) 卸载建议。

#### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>此配置是否对直接发送实时事件 &amp; 流外的流量有风险？

是，由于用于服务某些元素的共享 FQN，这无法避免。 此流量通常通过公司代理发送，该代理可以应用检查。 在 VPN 拆分隧道方案中，同时使用 FQDN 和 IP 将这种风险范围缩小到最小，但它仍然存在。 客户可以从卸载 **配置中删除 .azureedge.net 域，将此风险降至最低，但此操作将删除 Stream 支持的活动事件 (Teams 计划的外部编码器事件、Teams 中生成的 Yammer 事件、Yammer 计划的外部编码器事件以及 Stream 计划事件或 Stream) 中的按需查看。\*** 在任务中安排和Teams事件不受影响。

## <a name="howto-guides-for-common-vpn-platforms"></a>适用于常见 VPN 平台的操作指南

本部分提供了一些链接，这些链接指向针对此空间中最常见的合作伙伴Microsoft 365流量实施拆分隧道的详细指南。 我们将在其他指南推出时添加这些指南。

- **Windows 10 VPN 客户端**：Microsoft 365本地 VPN 客户端为远程工作者优化 [Windows 10流量](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**：[优化 Office365 的 Anyconnect 拆分隧道](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**：优化Microsoft 365 [VPN 拆分流量Tunnel排除访问路由](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 网络 BIG-IP APM**[：Microsoft 365 BIG-IP APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365) 时通过 VPN 优化远程访问流量
- **Citrix 网关**：[优化 Office365 Citrix 网关 VPN 拆分隧道](https://docs.citrix.com/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **脉冲安全**：[VPN 隧道：如何配置拆分隧道以排除Microsoft 365应用程序](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **检查点 VPN**[：如何为 Tunnel 和其他 SaaS Microsoft 365拆分服务器](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="vpn-split-tunneling-faq"></a>VPN 拆分隧道常见问题解答

Microsoft 安全团队发布了供安全专业人员和 [IT](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) 人员在今天独特的远程工作场景中实现新式安全控制的替代方法（博客文章）概述了安全专业人员和 IT 人员在当今独特的远程工作场景中实现新式安全控制的关键方法。 此外，下面是有关此主题的一些常见客户问题和解答。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>我如何阻止用户访问我不信任的其他租户（他们可能会泄漏数据）？

答案是[称为租户限制的功能](/azure/active-directory/manage-apps/tenant-restrictions)。 身份验证流量不高，也不对延迟特别敏感，因此可以通过 VPN 解决方案发送到应用该功能的本地代理。 此处维护受信任租户的允许列表，如果客户端尝试获取到不受信任的租户的令牌，代理将拒绝请求。 如果租户受信任，则在用户具有正确的凭据和权限的情况下，令牌可供访问。

因此，即使用户可以建立与上述"优化"标记的终结点的 TCP/UDP 连接，但没有有效的令牌来访问有关租户，他们也无法登录和访问/移动任何数据。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>此模型是否允许访问诸如个人 OneDrive 帐户之类的使用者服务？

否，它并不相同，Microsoft 365终结点与使用者服务 (Onedrive.live.com 与示例) 因此拆分隧道不允许用户直接访问使用者服务。 流向使用方终结点的流量将继续使用 VPN 隧道，并且现有策略将继续生效。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>如果流量不再流经本地解决方案，我该如何应用 DLP 并保护我的敏感数据？

为了帮助防止意外泄露敏感信息，Microsoft 365一组[丰富的内置工具](../compliance/information-protection.md)。 可使用 Teams 和 SharePoint 的内置 [DLP 功能](../compliance/dlp-learn-about-dlp.md)来检测未恰当存储或共享的敏感信息。 如果远程工作策略的一部分涉及自带设备办公 (BYOD) 策略，可以使用基于应用的条件访问来防止敏感数据下载到用户的个人设备[](/azure/active-directory/conditional-access/app-based-conditional-access)

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>如何在用户直接连接时评估和保留用户身份验证的控制权？

除了问题 1 中提到的租户限制功能之外，还可以应用[条件访问策略](/azure/active-directory/conditional-access/overview)来动态评估身份验证请求的风险并做出相应的反应。 Microsoft [建议随着时间的推移](https://www.microsoft.com/security/zero-trust?rtc=1)实现零信任模型，我们可以使用Azure AD访问策略在移动和云第一世界保持控制。 可使用条件访问策略对身份验证请求是否成功作出实时决策，具体取决于以下诸多因素：

- 设备，设备是否已知/受信任/已加入域？
- IP – 身份验证请求是否来自已知公司 IP 地址？ 或者来自不信任的国家/地区？
- 应用程序 – 用户是否有权使用此应用程序？

然后，我们可以根据这些策略触发批准、触发 MFA 或阻止身份验证等策略。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>如何防范病毒和恶意软件？

同样，Microsoft 365在服务本身的各个层中为"优化"标记的终结点[提供保护，本文档对此进行概述](/office365/Enterprise/office-365-malware-and-ransomware-protection)。 如前所述，在服务本身中提供这些安全元素比尝试在可能完全了解协议/流量的设备中这样做效率更高。 默认情况下，SharePoint Online [自动扫描文件上传中的](../security/office-365-security/virus-detection-in-spo.md)已知恶意软件

对于上面Exchange的终结点，Exchange Online Protection和 [Microsoft Defender for Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)可以出色地为服务提供流量安全。 [](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>除了优化流量外，我是否可以直接发送更多流量？

应优先考虑标记为 **优化** 的终结点，因为这些终结点将为低级别的工作提供最大好处。 但是，如果需要，服务需要"允许标记的终结点"才能工作，并拥有为在必要时可以使用的终结点提供的 IP 地址。

此外，还有各种供应商提供基于云的代理/安全解决方案，称为安全 _Web_ 网关，可提供用于常规 Web 浏览的中心安全、控制和公司策略应用程序。 这些解决方案在云第一世界（如果高度可用、性能高且预配接近用户）中可以正常工作，通过允许从靠近用户的基于云的位置提供安全 Internet 访问。 这将无需通过 VPN/公司网络进行发夹，用于常规浏览流量，同时仍允许中央安全控制。

但是，即使这些解决方案已就位，Microsoft 仍强烈建议将标记为Microsoft 365的优化流量直接发送到服务。

有关允许直接访问 Azure 虚拟网络的指南，请参阅使用 [Azure VPN 网关点到站点的远程工作](/azure/vpn-gateway/work-remotely-support)。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>为什么需要端口 80？ 流量是否明文发送？

端口 80 仅用于重定向到端口 443 会话之类的操作，不会通过端口 80 发送或访问任何客户数据。 [加密](../compliance/encryption.md)概述了对传输中和静态数据进行加密Microsoft 365流量类型概述了如何使用 SRTP [](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) 来保护Teams流量。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>此建议是否适用于使用全球 Microsoft 365？

**否**，不适用。 上述建议需要注意的一个注意事项是，中国用户连接到全球 Microsoft 365。 由于该区域会经常出现跨境网络拥挤现象，因此直接 Internet 出口性能可能会有变化。 该区域中的大多数客户都使用 VPN 将流量引入公司网络，并利用其经授权的 MPLS 专线或类似于通过优化路径的国家/地区之外的出口。 本文针对中国用户Microsoft 365[进一步概述了这一点](microsoft-365-networking-china.md)。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>拆分隧道配置是否适用于在Teams中运行的信息？

是，有注意事项。 大多数Teams功能在 Get [clients for Microsoft Teams 中列出的浏览器中受支持](/microsoftteams/get-clients#web-client)。

此外，Microsoft Edge **96** 及以上设备通过启用 Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略支持对等流量的 VPN 拆分隧道。 目前，其他浏览器可能不支持对等流量的 VPN 拆分隧道。

## <a name="related-articles"></a>相关文章

[概述：用于服务器的 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365中国用户优化性能](microsoft-365-networking-china.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365网络和性能优化](network-planning-and-performance.md)
