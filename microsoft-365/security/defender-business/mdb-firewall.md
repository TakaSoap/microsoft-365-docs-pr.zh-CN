---
title: Microsoft Defender for Business 中的防火墙
description: 了解 Microsoft Defender Windows Defender中的防火墙，包括配置设置
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 9644df7d4681a3f425c82f2f47bdb2ad50c75483
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512750"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Microsoft Defender for Business 中的防火墙

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Microsoft Defender for Business 包括具有防火墙Windows Defender[功能](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 防火墙保护通过确定允许哪些网络流量从设备进入或流动的规则来帮助保护设备。 

可以使用防火墙保护指定是允许还是阻止不同位置的设备上的连接。 例如，防火墙设置可以允许连接到公司内部网络的设备的入站连接，但在设备位于不受信任的设备上时阻止这些连接。

**本文介绍**：

- [Defender for Business 中的默认防火墙设置](#default-firewall-settings-in-defender-for-business)

- [可以在 Defender for Business 中配置的防火墙设置](#firewall-settings-you-can-configure-in-defender-for-business)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="default-firewall-settings-in-defender-for-business"></a>Defender for Business 中的默认防火墙设置

Microsoft Defender for Business 包括默认防火墙策略和设置，可帮助保护公司设备自第一天起。 公司设备载入 Microsoft Defender for Business 后，默认防火墙策略将按如下方式工作：

- 默认情况下，允许从设备进行出站连接，而不考虑位置。
- 当设备连接到贵公司的网络时，默认情况下会阻止所有入站连接。
- 当设备连接到公用网络或专用网络时，默认情况下会阻止所有入站连接。

在 Microsoft Defender for Business 中，你可以定义例外以阻止或允许传入连接。 通过创建自定义规则来定义这些例外。 请参阅 [管理防火墙策略的自定义规则](mdb-custom-rules-firewall.md)。

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>可以在 Defender for Business 中配置的防火墙设置

Microsoft Defender for Business 包括通过防火墙Windows Defender保护。 下表列出了可在 Microsoft Defender for Business 中为防火墙保护配置的设置。 <br/><br/>

| Setting | 说明 |
|--|--|
| **域网络** | 域网络配置文件适用于贵公司的网络。 域网络的防火墙设置适用于在同一网络上其他设备上启动的入站连接。 默认情况下，传入连接设置为" **全部阻止"**。  |
| **公共网络** | 公共网络配置文件适用于可在公共场所（如咖啡店或机场）使用的网络。 公用网络的防火墙设置适用于在同一网络上其他设备上启动的入站连接。 由于公共网络可以包含你不知道或不信任的设备，传入连接默认设置为" **全部** 阻止"。  |
| **专用网络** | 专用网络配置文件适用于专用位置（如家庭）的网络。 专用网络的防火墙设置适用于在同一网络上其他设备上启动的入站连接。 通常，在专用网络上，假定同一网络上所有其他设备都是受信任的设备。 但是，默认情况下，传入连接设置为" **全部阻止"**。 |
| **自定义规则** | [自定义规则](mdb-custom-rules-firewall.md) 允许您阻止或允许特定连接。 例如，假设你想要阻止连接到专用网络的设备上的所有传入连接，但通过设备上特定应用进行的连接除外。 在这种情况下，应设置专用 **网络** 以阻止所有传入连接，然后添加自定义规则以定义异常。 <br/><br/>您可以使用自定义规则定义特定文件或应用的例外、Internet 协议 (IP) 地址或一系列 IP 地址。 <br/><br/>根据所创建的自定义规则的类型，以下是可以使用的一些示例值： <br/><br/>应用程序文件路径： `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe` <br/><br/>IP：有效的 IPv4/IPv6 地址，例如 `192.168.1.0` 或 `192.168.1.0/24` <br/><br/>IP：有效的 IPv4/IPv6 `192.168.1.0-192.168.1.9` 地址范围，格式 (不包含空格)  |

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 中管理防火墙设置](mdb-custom-rules-firewall.md)

- [了解有关防火墙Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)