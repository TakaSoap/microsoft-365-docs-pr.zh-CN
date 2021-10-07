---
title: 修复 Microsoft Defender for Endpoint 中的不正常传感器
description: 修复报告为错误配置或不活动的设备传感器，以便服务从设备接收数据。
keywords: 错误配置， 非活动， 修复传感器， 传感器运行状况， 无传感器数据， 传感器数据， 通信受损， 通信
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: b9cbdc184dd5759821b738cd4e16e1d27fa2132b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205471"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>修复 Microsoft Defender for Endpoint 中的不正常传感器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-fixsensor-abovefoldlink)。

分类为错误配置或非活动的设备可能由于各种原因被标记。 本节提供有关可能导致设备被分类为非活动或错误配置的一些说明。

## <a name="inactive-devices"></a>非活跃设备

非活动设备不一定由于问题而标记。 在设备上采取的以下操作可能导致设备被分类为非活动状态：

### <a name="device-is-not-in-use"></a>设备未在使用中

如果设备出于任何原因未使用七天以上，它将在门户中保持"非活动"状态。

### <a name="device-was-reinstalled-or-renamed"></a>已重新安装或重命名设备
重新安装或重命名的设备将在新设备中生成Microsoft Defender 安全中心。 以前的设备实体在门户中将保持"非活动"状态。 如果重新安装了设备并部署了 Defender for Endpoint 程序包，请搜索新设备名称以验证设备是否正常报告。

### <a name="device-was-offboarded"></a>设备已载出
如果设备已载出，它仍将显示在设备列表中。 七天后，设备运行状况应更改为非活动状态。

### <a name="device-is-not-sending-signals"></a>设备未发送信号
如果设备出于任何原因（包括属于错误配置设备分类的条件）未向任何 Microsoft Defender 终结点通道发送超过 7 天的信号，则设备可视为非活动状态。 

你是否希望设备的状态为"活动"？ [打开支持票证](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。

## <a name="misconfigured-devices"></a>配置错误的设备
可以将错误配置的设备进一步分类为：
- 通信受损
- 无传感器数据

### <a name="impaired-communications"></a>通信受损
此状态表示设备和服务之间的通信有限。

以下建议操作可帮助修复与通信受损的错误配置设备相关的问题：

- [确保设备具有 Internet 连接](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。

- [验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  验证代理配置是否成功完成，WinHTTP 能否发现并通过您环境中代理服务器进行通信，以及代理服务器是否允许流量到 Microsoft Defender for Endpoint 服务 URL。

如果采取更正操作，但设备状态仍配置错误， [请打开支持票证](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

### <a name="no-sensor-data"></a>无传感器数据
状态为"无传感器数据"的错误配置设备与服务通信，但只能报告部分传感器数据。
按照以下操作更正与状态为"无传感器数据"的错误配置设备相关的已知问题：

- [确保设备具有 Internet 连接](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。

- [验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  验证代理配置是否成功完成，WinHTTP 能否发现并通过您环境中代理服务器进行通信，以及代理服务器是否允许流量到 Microsoft Defender for Endpoint 服务 URL。

- [确保诊断数据服务已启用](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
如果设备未正确报告，你可能需要检查Windows 10数据服务是否设置为自动启动，并且正在终结点上运行。

- [确保Microsoft Defender 防病毒策略未禁用此策略](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
如果你的设备运行的是第三方反恶意软件客户端，则 Defender for Endpoint 代理需要启用 Microsoft Defender 防病毒 提前启动反恶意软件 (ELAM) 驱动程序。

如果采取更正操作，但设备状态仍配置错误， [请打开支持票证](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。

## <a name="see-also"></a>另请参阅
- [检查 Microsoft Defender for Endpoint 中的传感器运行状况](check-sensor-status.md)
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [在 Windows 上运行客户端分析器](run-analyzer-windows.md)
- [在 macOS 或 Linux 上运行客户端分析器](run-analyzer-macos-linux.md)
- [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)

