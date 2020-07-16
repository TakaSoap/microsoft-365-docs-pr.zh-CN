---
title: Office 365 的 TLS 1.0 和 1.1 停用
description: 介绍了 Office 365 的 TLS 1.0 和1.1 弃用情况。
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
ms.openlocfilehash: 270d04974cec9c36fa31a77bda401375fdac0471
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148144"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Office 365 的 TLS 1.0 和 1.1 停用
> [!IMPORTANT]
> 由于 covid-19，我们暂时停止了针对商业客户的过时强制执行的 TLS 1.0 和1.1，但由于提供链已调整，而某些国家/地区已重新打开，我们正在将 TLS 强制重置为开始 Oct 15、2020。 

从2018年10月31日起，Office 365 服务的传输层安全性（TLS）1.0 和1.1 协议已被弃用。 最终用户的效果应最小。 此更改已在两年的时间内公布，第一次公开发布在12月2017。 本文仅用于涵盖与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。

## <a name="office-and-tls-overview"></a>Office 和 TLS 概述

Office 客户端依赖于 Windows web 服务（WINHTTP）以通过 TLS 协议发送和接收通信。 如果本地计算机的 web 服务可以使用 TLS 1.2，则 Office 客户端可以使用 TLS 1.2。 所有 Office 客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议都是操作系统的一部分，而不是特定于 Office 客户端的。

### <a name="on-windows-8-and-later-versions"></a>在 Windows 8 和更高版本上

默认情况下，如果没有网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和1.1 协议可用。

### <a name="on-windows-7"></a>在 Windows 7 上

如果没有[KB 3140245](https://support.microsoft.com/help/3140245)更新，TLS 1.1 和1.2 协议将不可用。 更新解决了此问题，并添加了以下注册表子项：

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 在2018年10月31日之前，不具有此更新的 Windows 7 用户将受到影响。 [KB 3140245](https://support.microsoft.com/help/3140245)包含有关如何更改 WINHTTP 设置以启用 TLS 协议的详细信息。

#### <a name="more-information"></a>更多信息

知识库文章描述的**DefaultSecureProtocols**注册表项的值决定了可以使用的网络协议：

|DefaultSecureProtocols 值|启用协议|
|-|-|
|0x00000008|默认情况下启用 SSL 2.0|
|0x00000020|默认情况下启用 SSL 3.0|
|0x00000080|默认情况下启用 TLS 1.0|
|0x00000200|默认情况下启用 TLS 1.1|
|0x00000800|默认情况下启用 TLS 1.2|

## <a name="office-clients-and-tls-registry-keys"></a>Office 客户端和 TLS 注册表项

您可以参考[KB 4057306，准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306)。 这是针对 IT 管理员的一般性文章，它是有关 TLS 1.2 更改的正式文档。

下表显示了在2018年10月31日之后 Office 365 客户端中相应的注册表项值。

|在2018年10月31日之后启用了 Office 365 服务协议|十六进制值|
|-|-|
|TLS 1.0 + 1.1 + 1。2|0x00000A80|
|TLS 1.1 + 1。2|0x00000A00|
|TLS 1.0 + 1。2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> 我们建议您不要使用 SSL 2.0 和3.0 协议，也可以使用**DefaultSecureProtocols**项进行设置。 SSL 2.0 和3.0 被视为已弃用的协议。 最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管执行此操作的决策最终取决于最符合您的产品需求的决策。 有关 SSL 3.0 漏洞的详细信息，请参阅[KB 3009008](https://support.microsoft.com/help/3009008)。

您可以使用程序员模式下的默认 Windows 计算器设置相同的引用注册表项值。 有关详细信息，请参阅[KB 3140245 更新以将 tls 1.1 和 tls 1.2 启用为 Windows 中 WinHTTP 中的默认安全协议](https://support.microsoft.com/help/3140245)。

无论是否安装了 Windows 7 更新（[KB 3140245](https://support.microsoft.com/help/3140245)），DefaultSecureProtocols 注册表子项都不存在，必须手动添加或通过组策略对象（GPO）添加。 也就是说，除非您必须自定义启用或限制的安全协议，否则此键不是必需的。 您只需要 Windows 7 SP1 （[KB 3140245](https://support.microsoft.com/help/3140245)）更新。
