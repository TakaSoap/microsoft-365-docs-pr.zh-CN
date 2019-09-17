---
title: 第 4 步：配置流量旁路
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
description: 了解并配置 Web 浏览器和边缘设备，以便流量绕过受信任的 Office 365 位置。
ms.openlocfilehash: fbc4956525e2661ce791c6ec81b449dba685d0f0
ms.sourcegitcommit: 1ca1062ccddd7a46fa0bb4af6ee5f0eb141e7280
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2019
ms.locfileid: "36999036"
---
# <a name="step-4-configure-traffic-bypass"></a>第 4 步：配置流量旁路

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

由于一般的 Internet 流量可能存在风险，因此典型组织网络通过代理服务器、SSL 中断和检查、数据包检查设备和数据丢失防护系统等边缘设备实施安全性。了解有关使用第三方网络设备或 Office 365 流量解决方案的网络侦听设备的一些问题。

但是，Microsoft 365 基于云的服务使用的 DNS 域名和 IP 地址是众所周知的。此外，流量和服务本身受到许多安全功能的保护。由于已经应用了安全性和保护功能，因此边缘设备无需重复此过程。Microsoft 365 流量的中间目标和重复安全性处理可能会显著降低性能。

消除中间目标和重复安全性处理的第一步是识别 Microsoft 365 流量。Microsoft 已定义以下类型的 DNS 域名和 IP 地址范围，称为终结点：

- **优化** - 必需连接到每项 Office 365 服务，并代表超过 75% 的 Microsoft 365 带宽、连接和数据量。 这些终结点代表对网络性能、延迟和可用性最敏感的 Microsoft 365 方案。
- **允许** - 若要连接到特定 Microsoft 365 服务和功能，但不像“优化”类别终结点那样对网络性能和延迟敏感，必须使用这种类别。
 - **默认** - 代表不需要任何优化的 Microsoft 365 服务和依赖项。 可以将“默认”类别终结点视为正常 Internet 流量。

可在 [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints) 中查找 DNS 域名和 IP 地址范围。

Microsoft 建议：

- 使用本地计算机 Internet 浏览器上的代理自动配置 (PAC) 脚本绕过代理服务器以获取 Microsoft 365 基于云的服务的 DNS 域名。有关 Microsoft 365 PAC 脚本的最新信息，请参阅 [Get-Pacfile PowerShell 脚本](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)。
- 
- 分析边缘设备以确定重复处理，然后对其进行配置以将流量转发到“优化”和“允许”终结点而不进行处理。这称为流量旁路。 

边缘设备包括防火墙、SSL 中断和检查、数据包检查设备和数据丢失防护系统。要配置和更新边缘设备的配置，可以使用脚本或 REST 调用来使用 Office 365 终结点 Web 服务的结构化终结点列表。有关详细信息，请参阅 [Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/zh-CN/office365/enterprise/office-365-ip-web-service#exporting-a-proxy-pac-file)。

请注意，你只是绕过了针对 Microsoft 365“优化”和“允许”类别终结点的流量的正常代理和网络安全处理。所有其他常规 Internet 流量都将被代理，并受现有网络安全处理的约束。


作为临时检查点，可查看这一步的[退出条件](networking-exit-criteria.md#crit-networking-step4)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[优化客户端和 Office 365 服务性能](networking-optimize-tcp-performance.md) |



