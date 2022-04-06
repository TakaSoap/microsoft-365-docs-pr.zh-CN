---
title: Microsoft Defender 商业版中的防火墙
description: 了解Microsoft Defender 商业版中的Windows Defender防火墙，包括配置设置
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: fb506a1d2cc28329f9d6ef9975a10b0661379bb9
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664603"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Microsoft Defender 商业版中的防火墙

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

Microsoft Defender 商业版包含防火墙功能[Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 防火墙保护可通过规则保护设备，这些规则确定允许哪些网络流量进入或从设备流出。 

可以使用防火墙保护来指定是允许还是阻止不同位置设备上的连接。 例如，防火墙设置可以允许连接到公司内部网络的设备上的入站连接，但在设备位于具有不受信任设备的网络上时阻止这些连接。

**本文介绍**：

- [Defender for Business 中的默认防火墙设置](#default-firewall-settings-in-defender-for-business)

- [可以在 Defender for Business 中配置的防火墙设置](#firewall-settings-you-can-configure-in-defender-for-business)

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="default-firewall-settings-in-defender-for-business"></a>Defender for Business 中的默认防火墙设置

Microsoft Defender 商业版包括默认防火墙策略和设置，以帮助保护公司设备从第一天开始。 公司设备加入Microsoft Defender 商业版后，默认防火墙策略的工作原理如下：

- 默认情况下，无论位置如何，都允许来自设备的出站连接。
- 设备连接到公司的网络时，默认情况下会阻止所有入站连接。
- 当设备连接到公用网络或专用网络时，默认情况下会阻止所有入站连接。

在Microsoft Defender 商业版中，可以定义阻止或允许传入连接的异常。 通过创建自定义规则来定义这些异常。 请参阅 [管理防火墙策略的自定义规则](mdb-custom-rules-firewall.md)。

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>可以在 Defender for Business 中配置的防火墙设置

Microsoft Defender 商业版包括通过Windows Defender防火墙保护防火墙。 下表列出了可在Microsoft Defender 商业版中为防火墙保护配置的设置。 <br/><br/>

| 设置 | 说明 |
|--|--|
| **域网络** | 域网络配置文件适用于公司的网络。 域网络的防火墙设置适用于在同一网络上的其他设备上启动的入站连接。 默认情况下，传入连接设置为 **阻止所有** 连接。  |
| **公用网络** | 公共网络配置文件适用于可在公共位置（如咖啡店或机场）使用的网络。 公共网络的防火墙设置适用于在同一网络上的其他设备上启动的入站连接。 由于公用网络可以包含你不知道或不信任的设备，所以默认情况下，传入连接设置为 **"全部阻止** "。  |
| **专用网络** | 专用网络配置文件适用于专用位置（例如你的家庭）中的网络。 专用网络的防火墙设置适用于在同一网络上的其他设备上启动的入站连接。 通常，在专用网络上，假定同一网络上的所有其他设备都是受信任的设备。 但是，默认情况下，传入连接设置为 **阻止所有** 连接。 |
| **自定义规则** | [自定义规则](mdb-custom-rules-firewall.md) 允许阻止或允许特定连接。 例如，假设要阻止连接到专用网络的设备上的所有传入连接，但通过设备上的特定应用进行连接除外。 在这种情况下，你将设置 **专用网络** 来阻止所有传入连接，然后添加自定义规则来定义异常。 <br/><br/>可以使用自定义规则来定义特定文件或应用、Internet 协议 (IP) 地址或一系列 IP 地址的异常。 <br/><br/>根据要创建的自定义规则的类型，下面是一些可以使用的示例值： <br/><br/>应用程序文件路径： `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP：有效的 IPv4/IPv6 地址，例如 `192.168.11.0` 或 `192.168.1.0/24` <br/><br/>IP：有效的 IPv4/IPv6 地址范围，格式类似于 `192.168.1.0-192.168.1.9` (，不包含任何空格)  |

## <a name="next-steps"></a>后续步骤

- [在Microsoft Defender 商业版中管理防火墙设置](mdb-custom-rules-firewall.md)

- [详细了解Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)