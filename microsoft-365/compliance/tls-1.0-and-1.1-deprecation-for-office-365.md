---
title: Office 365 的 TLS 1.0 和 1.1 停用
description: 介绍 Office 365 的 TLS 1.0 和 1.1 弃用。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777050"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Office 365 的 TLS 1.0 和 1.1 停用
> [!IMPORTANT]
> 由于 COVID-19，我们暂时停止了对商业客户实施 TLS 1.0 和 1.1 的弃用，但由于供应链已进行调整，并且某些国家/地区开始备份，我们将 TLS 实施重新设定为 2020 年 10 月 15 日，并将在随后的几周和几个月内继续推出。 

从 2018 年 10 月 31 日起，Office 365 服务已弃用传输层安全性 (TLS) 1.0 和 1.1 协议。 预计对最终用户的影响最小。 此更改已公布两年以上，2017 年 12 月发布第一个公开声明。 本文仅用于介绍与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。

## <a name="office-and-tls-overview"></a>Office 和 TLS 概述

Office 客户端依赖 Windows Web 服务 (WINHTTP) TLS 协议发送和接收流量。 如果本地计算机的 Web 服务可以使用 TLS 1.2，Office 客户端可以使用 TLS 1.2。 所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议是操作系统的一部分，而不是特定于 Office 客户端的。

### <a name="on-windows-8-and-later-versions"></a>在 Windows 8 和更高版本上

默认情况下，如果没有将网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和 1.1 协议可用。

### <a name="on-windows-7"></a>在 Windows 7 上

没有 KB [3140245](https://support.microsoft.com/help/3140245) 更新，TLS 1.1 和 1.2 协议不可用。 更新解决了此问题并添加了以下注册表子项：

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 自 2018 年 10 月 31 日起，没有此更新的 Windows 7 用户会受到影响。 [KB 3140245](https://support.microsoft.com/help/3140245) 详细介绍了如何更改 WINHTTP 设置以启用 TLS 协议。

#### <a name="more-information"></a>更多信息

知识库文章 **介绍的 DefaultSecureProtocols** 注册表项的值决定了可以使用哪些网络协议：

|DefaultSecureProtocols 值|协议已启用|
|-|-|
|0x00000008|默认情况下启用 SSL 2.0|
|0x00000020|默认情况下启用 SSL 3.0|
|0x00000080|默认情况下启用 TLS 1.0|
|0x00000200|默认情况下启用 TLS 1.1|
|0x00000800|默认情况下启用 TLS 1.2|

## <a name="office-clients-and-tls-registry-keys"></a>Office 客户端和 TLS 注册表项

你可以参考[KB 4057306 准备在 Office 365 中强制使用 TLS 1.2。](https://support.microsoft.com/help/4057306) 这是一篇供 IT 管理员阅读的常规文章，它是有关 TLS 1.2 更改的官方文档。

下表显示了 2018 年 10 月 31 日之后 Office 365 客户端中相应的注册表项值。

|2018 年 10 月 31 日之后为 Office 365 服务启用的协议|十六进制值|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> 我们不建议使用 SSL 2.0 和 3.0 协议，这两种协议也可使用 **DefaultSecureProtocols** 密钥进行设置。 SSL 2.0 和 3.0 被视为已弃用的协议。 最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管最终决定这样做取决于最能满足产品需求的产品。 有关 SSL 3.0 漏洞详细信息，请参阅[KB 3009008。](https://support.microsoft.com/help/3009008)

可以在编程模式下使用默认的 Windows 计算器来设置相同的引用注册表项值。 有关详细信息，请参阅 [KB 3140245 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2](https://support.microsoft.com/help/3140245)作为默认安全协议。

无论是否安装 Windows 7 更新 ([KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 注册表子项都不存在，必须手动或通过组策略对象 (GPO) 添加。 也就是说，除非必须自定义启用或限制哪些安全协议，否则不需要此密钥。 你只需 Windows 7 SP1 ([KB 3140245) ](https://support.microsoft.com/help/3140245) 更新。
