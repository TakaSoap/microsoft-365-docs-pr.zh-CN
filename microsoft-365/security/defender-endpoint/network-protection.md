---
title: 使用网络保护来帮助防止连接到错误站点
description: 通过阻止用户访问已知的恶意和可疑网络地址来保护网络
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 域
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.openlocfilehash: b6069d392da1b8610d018908d172dc27044baffc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054728"
---
# <a name="protect-your-network"></a>保护网络

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

网络保护有助于减少基于 Internet 的事件对设备的攻击面。 它防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。 网络保护扩展了 Microsoft [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的范围，以阻止所有基于域或主机名 (尝试连接到低信誉源 (的出站 HTTP) ) 。

从 Windows 10 版本 1709 开始，Windows 支持网络保护。 

若要详细了解如何启用网络保护，请参阅 [启用网络保护](enable-network-protection.md)。 使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。

> [!TIP]
> 有关网络保护的工作原理 [，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Microsoft Defender ATP 测试站点。

网络保护最适合 [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)，它为你提供有关 Exploit Protection 事件的详细报告，并作为警报调查方案的一部分 [进行阻止](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。

当网络保护阻止连接时，将显示来自操作中心的通知。 安全运营团队 [可以使用](customize-attack-surface-reduction.md#customize-the-notification) 组织的详细信息和联系信息自定义通知。 此外，可以启用和自定义各个攻击面减少规则，以适合要监视的某些技术。

您还可以使用 [审核模式评估](audit-windows-defender.md) 网络保护在启用后对组织的影响。

## <a name="requirements"></a>要求

网络保护需要 Windows 10 专业版或企业版以及 Microsoft Defender 防病毒实时保护。

| Windows 版本 | Microsoft Defender 防病毒 |
|:---|:---|
| Windows 10 版本 1709 或更高版本 <p>Windows Server 1803 或更高版本 | [必须启用 Microsoft Defender 防病毒实时](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md)[保护和云保护](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) |

启用服务后，可能需要配置网络或防火墙，以允许服务和设备之间的连接 (也称为终结点) 。  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>查看 Microsoft Defender 终结点安全中心中的网络保护事件

Microsoft Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。

可以使用高级搜寻查询 Microsoft Defender 的终结点 [数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)。 如果你使用的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻来查看网络保护设置在启用后将如何影响你的环境。

下面是一个示例查询

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>在 Windows 事件查看器中查看网络保护事件

你可以查看 Windows 事件日志以查看网络保护阻止访问恶意 IP 或域 (或审核) IP 或域时创建的事件：

1. [直接复制 XML。](event-views.md)

2. 选择“**确定**”。

此过程将创建一个自定义视图，该视图筛选为只显示与网络保护相关的以下事件：

| 事件 ID | 说明 |
|:---|:---|
| 5007 | 更改设置时的事件 |
| 1125 | 在审核模式下触发网络保护时的事件 |
| 1126 | 在阻止模式下触发网络保护时的事件 |

## <a name="related-articles"></a>相关文章

- [评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作方式以及通常会创建哪些事件。

- [启用网络保护](enable-network-protection.md) |使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。
