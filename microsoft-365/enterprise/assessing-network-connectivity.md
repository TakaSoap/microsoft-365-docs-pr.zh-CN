---
title: 评估 Microsoft 365 网络连接
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 旨在允许全球客户使用 Internet 连接连接到服务。 随着服务的发展，Microsoft 365 的安全性、性能和可靠性会基于客户使用 Internet 与服务建立连接而得到改进。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905472"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>评估 Microsoft 365 网络连接

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Microsoft 365 旨在允许全球客户使用 Internet 连接连接到服务。 随着服务的发展，Microsoft 365 的安全性、性能和可靠性会基于客户使用 Internet 与服务建立连接而得到改进。
  
作为部署项目的一部分，计划使用 Microsoft 365 的客户应评估其现有和预测的 Internet 连接需求。 对于企业级部署，可靠且大小合适的 Internet 连接是使用 Microsoft 365 功能和方案的关键部分。
  
网络评估可以由许多不同的人员和组织执行，具体取决于你的大小和首选项。 评估的网络范围也可能有所不同，具体取决于你在部署过程中处于何处。 为了帮助你更好地了解执行网络评估需要执行的操作，我们生成了一个网络评估指南，可帮助你了解可用的选项。 此评估将确定需要向部署项目添加哪些步骤和资源，以便成功采用 Microsoft 365。
  
全面的网络评估将提供可能的网络设计挑战解决方案以及实施详细信息。 一些网络评估将显示，通过对现有网络和 Internet 出口基础结构进行细微的配置或设计更改，可以适应与 Microsoft 365 的最佳网络连接。

一些评估将指示与 Microsoft 365 的网络连接将需要在网络组件方面进行额外投资。 例如，跨分支机构和多个地理区域的企业网络可能需要投资 SD-WAN 解决方案或优化的路由基础结构以支持到 Microsoft 365 的 Internet 连接。 有时，评估将指示与 Microsoft 365 的网络连接受 Skype for Business Online 媒体质量等方案的法规或性能 [要求的影响](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。 这些额外的要求可能会导致 Internet 连接基础结构、路由优化和专门的直接连接方面的投资。

帮助您评估网络的一些资源：

- 有关 [Microsoft 365 网络](microsoft-365-networking-overview.md) 的概念信息，请参阅 Microsoft 365 网络连接概述。
- 请参阅 [Microsoft 365](./microsoft-365-network-connectivity-principles.md) 网络连接原则，了解安全管理 Microsoft 365 流量和获得最佳性能的连接原则。
- 注册 [Microsoft FastTrack，](https://www.microsoft.com/fasttrack) 获得 Microsoft 365 规划、设计和部署指导协助。 
- 请参阅下面的 [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 连接测试部分，以运行基本连接测试，这些测试提供有关可在给定用户位置和 Microsoft 365 之间进行网络连接改进的特定指南。

> [!NOTE]
> 需要 Microsoft 授权才能使用适用于 Office 365 的 ExpressRoute。 当客户的法规要求要求直接连接时，Microsoft 将审核每个客户请求，并仅授权 ExpressRoute for Office 365 使用。 如果你有此类要求，请提供文本摘录和指向法规的 Web 链接，您解释该法规意味着 [ExpressRoute for Office 365](https://aka.ms/O365ERReview) 请求表单中需要直接连接才能开始 Microsoft 审查。 尝试为 Office 365 创建路由筛选器的未经授权的订阅将收到 [一条错误消息](https://support.microsoft.com/kb/3181709)。
  
规划 Microsoft 365 网络评估时要考虑的要点：
  
- Microsoft 365 是一种通过公共 Internet 运行的安全、可靠、高性能服务。 我们将继续投资以增强服务的这些方面。 所有 Microsoft 365 服务均通过 Internet 连接提供。

- 我们正在不断优化 Microsoft 365 的核心方面，例如可用性、全球范围和基于 Internet 的连接的性能。 例如，许多 Microsoft 365 服务利用一组扩展的面向 Internet 的边缘节点。 此边缘网络为通过 Internet 的连接提供最佳邻近感应和性能。

- 当考虑将 Microsoft 365 用于任何包含的服务（如 Teams 或 Skype for Business Online 语音、视频或会议功能）时，客户应该使用 [Microsoft FastTrack](https://www.microsoft.com/fasttrack)完成端到端网络评估并满足连接要求。

如果你正在评估 Microsoft 365，并且不确定从何处开始进行网络评估，或发现需要协助解决的网络设计挑战，请与你的 Microsoft 帐户团队合作。

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 连接测试

[Microsoft 365](https://aka.ms/netonboard)连接测试是概念证明 (POC) 网络评估工具，该工具针对 Microsoft 365 租户运行基本连接测试，并针对最佳 Microsoft 365 性能提供特定的网络设计建议。 该工具重点介绍常见的大型企业网络外围设计选择，这些选项对于 Internet Web 浏览很有用，但会影响大型 SaaS 应用程序（如 Microsoft 365）的性能。

网络载入工具执行以下操作：

- 检测位置，也可以指定要测试的位置
- 检查网络出口的位置
- 测试到最近的 Microsoft 365 服务前端的网络路径
- 使用可下载的 Windows 10 应用程序提供高级测试，该应用程序提供与代理服务器、防火墙和 DNS 相关的外围网络设计建议。 该工具还运行 Skype for Business Online、Microsoft Teams、SharePoint Online 和 Exchange Online 的性能测试。

该工具包含两个组件：一个收集基本连接信息的基于浏览器的 UI，以及一个可下载的运行高级测试并返回其他评估数据的 Windows 10 应用程序。

基于浏览器的工具显示以下信息：

- 结果和影响选项卡
  - 使用中的服务前端在地图上的位置
  - 可提供最佳连接的其他服务前门地图上的位置
  - 相对于你附近的其他 Microsoft 365 客户的性能
- "详细信息和解决方案"选项卡
  - 按城市的国家/地区的用户位置
  - 按城市、省/市/市/地区和国家/地区表示的网络出口位置
  - 用户到网络出口的距离
  - Microsoft 365 Exchange Online 服务前端位置
  - 用户位置的最佳 Microsoft 365 Exchange Online () 配置
  - 拥有更佳性能的你区中的客户

高级测试可下载应用程序提供以下附加信息：

- 详细信息和解决方案选项卡 (附加) 
  - 用户的默认网关
  - 客户端 DNS 服务器
  - 客户端 DNS 递归解析程序
  - Exchange Online DNS 服务器
  - SharePoint Online DNS 服务器
  - 代理服务器标识
  - 媒体连接检查
  - 媒体质量数据包丢失
  - 媒体质量延迟
  - 媒体质量抖动
  - 媒体质量数据包重新排序
- 与多个特定于功能终结点的连接测试
- 包括 Exchange Online、SharePoint Online 和 Teams 服务的 tracert 和延迟数据的网络路径诊断

你可以阅读有关 Microsoft 365 连接测试的信息，并可在更新 [后的 Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) 连接测试 POC 和新的网络设计建议博客文章提供反馈。 有关此工具和其他 Microsoft 365 网络更新的未来更新的信息将发布至 Office [365 网络](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) 博客。
  
以下是可用于返回的简短链接[ https://aka.ms/o365networkconnectivity ：。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>相关主题

[Microsoft 365 网络连接概述](microsoft-365-networking-overview.md)

[Microsoft 365 网络连接原则](./microsoft-365-network-connectivity-principles.md)

[管理 Office 365 终结点](managing-office-365-endpoints.md)

[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)

[Office 365 IP 地址和 URL Web 服务](microsoft-365-ip-web-service.md)

[Microsoft 365 网络和性能调整](network-planning-and-performance.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)