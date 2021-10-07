---
title: 禁用 TLS 1.0 和 1.1 Microsoft 365
description: 介绍 TLS 1.0 和 1.1 弃用和禁用Microsoft 365。
author: workshay
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3084232f267a1180425d2daa3fcd2ba2fbcbd063
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167098"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>禁用 TLS 1.0 和 1.1 Microsoft 365

> [!IMPORTANT]
> 由于 COVID-19，我们暂时停止对商业客户禁用 TLS 1.0 和 1.1。 由于供应链已进行调整，并且某些国家/地区已开放备份，我们于 2020 年 10 月 15 日重新启动了 TLS 1.2 强制推出。 部署将持续几周和几个月。

自 2018 年 10 月 31 日起，Microsoft 365 服务已弃用传输层安全性 (TLS) 1.0 和 1.1 协议。 对最终用户的影响很小。 此更改已公布两年以上，2017 年 12 月发布第一个公开通知。 本文仅介绍与 Office 365 服务相关的 Office 365 本地客户端，但也适用于 Office 和 Office Online Server/Office Web Apps 的本地 TLS 问题。

对于SharePoint和OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。 有关信息，请参阅[如何在客户端上启用 TLS 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Office 365和 TLS 概述

客户端Office依赖于 WINHTTP Windows Web (来) TLS 协议发送和接收流量。 如果Office Web 服务可以使用 TLS 1.2，客户端可以使用 TLS 1.2。 所有Office客户端都可以使用 TLS 协议，因为 TLS 和 SSL 协议是操作系统的一部分，而不是特定于 Office 客户端。

### <a name="on-windows-8-and-later-versions"></a>在 Windows 8 及更高版本上

默认情况下，如果没有将网络设备配置为拒绝 TLS 1.2 流量，则 TLS 1.2 和 1.1 协议可用。

### <a name="on-windows-7"></a>在 Windows 7 上

没有 KB 更新，TLS 1.1 和 1.2 [3140245](https://support.microsoft.com/help/3140245) 不可用。 更新可解决此问题并添加以下注册表子项：

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 2018 年 10 月 31 日起，7 个没有此更新的用户会受到影响。 [KB 3140245](https://support.microsoft.com/help/3140245) 详细介绍了如何更改 WINHTTP 设置以启用 TLS 协议。

#### <a name="more-information"></a>更多信息

KB 文章介绍 **的 DefaultSecureProtocols** 注册表项的值决定了可以使用哪些网络协议：

|DefaultSecureProtocols 值|协议已启用|
|-|-|
|0x00000008|默认情况下启用 SSL 2.0|
|0x00000020|默认情况下启用 SSL 3.0|
|0x00000080|默认情况下启用 TLS 1.0|
|0x00000200|默认情况下启用 TLS 1.1|
|0x00000800|默认情况下启用 TLS 1.2|

## <a name="office-clients-and-tls-registry-keys"></a>Office客户端和 TLS 注册表项

你可以参考 KB 4057306准备在 Office 365 中强制使用[TLS 1.2。](https://support.microsoft.com/help/4057306) 这是一篇适用于 IT 管理员的常规文章，也是有关 TLS 1.2 更改的官方文档。

下表显示了 2018 年 10 月 31 Office 365客户端中相应的注册表项值。

|2018 Office 365 2018 年 10 月 31 日之后为服务启用的协议|十六进制值|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> 请勿使用 SSL 2.0 和 3.0 协议，这两种协议也可使用 **DefaultSecureProtocols** 密钥进行设置。 SSL 2.0 和 3.0 被视为过时的不安全协议。 最佳做法是结束使用 SSL 2.0 和 SSL 3.0，尽管最终决定使用哪一项最能满足你的产品需求。 有关 SSL 3.0 漏洞详细信息，请参阅 [KB 3009008](https://support.microsoft.com/help/3009008)。

可以在编程模式下使用Windows计算器设置相同的引用注册表项值。 有关详细信息，请参阅[KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows。](https://support.microsoft.com/help/3140245)

无论是否安装了 Windows 7 更新[ (KB 3140245](https://support.microsoft.com/help/3140245)) ，DefaultSecureProtocols 注册表子项不存在，必须通过组策略对象 (GPO) 手动添加。 也就是说，除非您必须自定义启用或限制哪些安全协议，否则不需要此密钥。 只需更新 Windows 7 SP1 ([KB 3140245) 。](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>更新和配置.NET Framework以支持 TLS 1.2

你需要更新通过 TLS 1.0 或 TLS 1.1 调用 Microsoft 365 API 的应用程序，以使用 TLS 1.2。 .NET 4.5 默认为 TLS 1.1。 若要更新 .NET 配置，请参阅如何在客户端上启用[TLS (TLS) 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>更多信息

有关详细信息，请参阅在 Office 365 中为强制使用[TLS 1.2 做准备](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

## <a name="references"></a>参考

以下资源提供指导，以帮助确保客户端使用的是 TLS 1.2 或更高版本，并禁用 TLS 1.0 和 1.1：

- 对于连接到 Office 365 的 Windows 7 客户端，请确保 TLS 1.2 是 Windows WinHTTP 中的默认安全协议。 有关详细信息，请参阅[KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as default secure protocols in WinHTTP in Windows。](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)
- 若要通过删除 TLS 1.0 和 1.1 依赖项来解决弱 TLS 使用情况，请参阅 Microsoft 上的 [TLS 1.2 支持](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。
- [新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)可更加方便地在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上查找通过使用弱安全协议连接服务的客户端。
- 获取有关如何解决 [TLS 1.0 问题的信息](https://www.microsoft.com/download/details.aspx?id=55266)。
- 有关安全性方法的一般信息，请转到[Office 365 信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。
- [准备 TLS 1.0/1.1 弃用 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 指南，第 1 部分：为 TLS 1.2 做好准备](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 指南，第 2 部分：启用 TLS 1.2 并识别不使用它的客户端](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 指南，第 3 部分：关闭 TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [在 Office Online Server 中启用 TLS 1.1 和 TLS 1.2 支持](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

