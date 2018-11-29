---
title: 步骤 5：优化客户端和 Office 365 服务性能
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 配置 TCP 设置和 Office 365 服务以提高性能。
ms.openlocfilehash: 40f99f1b50a324af0650382de165dcfd3df97b0c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865605"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>步骤 5：优化客户端和 Office 365 服务性能

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

你可以微调传输控制协议 (TCP) 在客户端设备和 Office 365 服务之间的工作方式，以提高性能。

对于客户端设备，可以在客户端设备上更改以下 TCP 设置以优化 TCP 性能：

- [TCP 窗口缩放](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/)，以使客户端设备在要求确认前发送更多数据
- [TCP 空闲时间](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/)，以使客户端设备更高效地处理打开的连接
- [TCP 最大段大小](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/)，以使客户端设备在数据包中发送数据的最大块
- [TCP 选择性确认](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/)，以使客户端设备更高效地确认接收的数据

有关 Office 365 服务，请参阅其他资源以优化性能：

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype for Business Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

作为临时检查点，请查看对应于此步骤的[退出条件](networking-exit-criteria.md#crit-networking-step5)。

## <a name="next-step"></a>后续步骤

[网络基础结构退出条件](networking-exit-criteria.md)
