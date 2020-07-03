---
title: Office 中的弃用 TLS 1.0 和 1.1 365 GCC High and DoD
description: 讨论了 Microsoft 如何在 Office 365 和准备好使用 TLS 1.2 的情况下，在 GCC 的高和 DoD 环境中停止支持 TLS 1.1 和1.0。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024813"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Office 中的弃用 TLS 1.0 和 1.1 365 GCC High and DoD

> [!IMPORTANT]
> 世界正处于病毒大流行之中，Microsoft 意识到这对我们的客户和合作伙伴会有很大影响。 为了减轻商业客户的负担，我们暂时停止了 TLS 1.0 和 1.1 的任何强制弃用。 在当前危机稳定后，将基于修订后的时间表发送更新。 （本文经过修订以反映更改。）

## <a name="summary"></a>摘要

为了符合联邦风险和授权管理程序（FedRAMP）的最新合规性标准，我们将迁移到 Microsoft Office 365 for GCC High and DoD 环境中的弃用传输层安全性（TLS）版本1.1 和1.0。 此更改之前已通过 Microsoft 支持部门宣布，以 [准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

我们了解您的数据的安全性非常重要，我们承诺对可能影响您的服务使用的更改的透明性。

尽管[MICROSOFT TLS 1.0 实现](https://support.microsoft.com/help/3117336)没有已知的安全漏洞，但我们仍将致力于 FedRAMP 合规性标准。 因此，在从2020年1月15日起，在 GCC 高和 DoD 环境中，我们将弃用 TLS 1.1 和 365 1.0。 有关如何删除 TLS 1.1 和1.0 依赖项的信息，请参阅以下白皮书：

[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)

在为 TLS 1.1 和1.0 的此更改做准备时，建议改用 TLS 版本1.2。 有关详细信息，请参阅[在 Office 365 中强制使用 TLS 1.2 的准备工作](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

## <a name="more-information"></a>更多信息

从2020年1月15日开始，在 GCC 高和 DoD 环境中的 Office 365 将弃用 TLS 1.1 和1.0。

在2020年1月15日，客户端服务器和浏览器服务器的所有组合都应使用 TLS 版本1.2 （或更高版本），以确保所有连接都可以在不向 Office 365 服务发出问题的情况下进行。 这可能需要对客户端服务器和浏览器服务器的某些组合进行更新。

如果您未在2020更新到 TLS 1.2 （或更高版本），则在尝试连接到 Office 365 时，将会遇到问题。 此外，还需要更新到 TLS 1.2 （或更高版本）作为解决方法的一部分。

我们知道以下客户端无法使用 TLS 1.2：

- Android 4.3 和更低的版本
- Firefox 版本 5.0 及更低版本
- Windows 7 和更早版本上的 Internet Explorer 8 –10
- Windows Phone 8.0 上的 Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 和早期版本

我们建议您更新客户端以确保您保持对 Office 365 GCC 高和 DoD 的无中断访问。

尽管当前对 Microsoft Online services 连接的分析表明，大多数服务和终结点都看到的不只是 TLS 1.1 和1.0 使用，但我们正在提供此更改的通知，以便您可以在支持 TLS 1.1 和1.0 结尾之前，根据需要更新任何受影响的客户端或服务器。 如果要对混合方案或 Active Directory 联合身份验证服务（AD FS）使用任何内部部署基础结构，请确保基础结构可以同时支持使用 TLS 1.2 （或更高版本）的入站和出站连接。

除了在使用列出的不能使用 TLS 1.2 的客户端时可能会遇到的故障之外，删除 TLS 1.1 和1.0 将使您无法使用以下 Microsoft 产品：

- Lync 电话

## <a name="references"></a>参考

以下支持文章介绍了有助于确保客户端使用 TLS 1.2 的指南和参考：

[准备在 Office 365 中使用 TLS 1.2 的必备](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
