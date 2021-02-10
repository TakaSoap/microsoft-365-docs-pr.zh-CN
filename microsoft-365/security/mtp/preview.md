---
title: Microsoft 365 Defender 中的预览功能
description: 了解 Microsoft 365 安全中心的新功能
keywords: 预览, 新, m365 安全中心, 安全, 365, 功能
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9156025990e8da61006ac1d3b81a71be5580e00c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167379"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender 预览版功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
>预览版本未经服务级别协议提供，不建议用于生产工作负载。 某些功能可能不受支持或可能具有受限功能。

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender 服务将不断更新，以包含新功能增强功能和功能。

了解 Microsoft 365 Defender 预览版中的新功能，并首先通过打开预览体验来试用即将推出的功能。

有关新功能的可用详细信息，请参阅 [Microsoft 365 Defender](whats-new.md)中的新增功能。

## <a name="turn-on-preview-features"></a>启用预览功能
你将有权访问即将推出的功能，你可以提供反馈以帮助在功能全面发布之前改进整体体验。

启用预览体验设置，以率先体验即将推出的功能。

1. 在导航窗格中，选择“**设置**”。

2. 选择 **Microsoft 365 Defender**。

3. 选择“**预览功能**” > “**启用预览功能**”。 

4. 选择“**保存**”。

当看到 **启用预览功能**”复选框处于选中状态时，你会知道已开启了预览功能。 

## <a name="preview-features"></a>预览功能
当前预览版中提供以下功能和增强功能：

### <a name="improved-microsoft-365-security-center"></a>改进的 Microsoft 365 安全中心
改进的 [Microsoft 365 安全](https://security.microsoft.com) 中心现已在公共预览版中提供。 这一全新体验将 Defender for Endpoint、Defender for Office 365、Microsoft 365 Defender 等引入 Microsoft 365 安全中心。 这是管理安全控制的新主页。 [了解新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。

- **[Microsoft 365 Defender 威胁分析](threat-analytics.md)** 报告 - 威胁分析可帮助你响应活动攻击并最大限度地减少其影响。 还可以了解 Microsoft 365 Defender 解决方案阻止的攻击尝试，采取预防措施来降低进一步曝光的风险，提高恢复能力。 作为统一安全体验的一部分，威胁分析现在适用于 Microsoft Defender for Endpoint 和 Microsoft Defender for Office E5 许可证持有者。
- **[Microsoft 365 Defender API](api-overview.md)** - 顶级 Microsoft 365 Defender API 将使您能够基于共享事件和高级搜寻表自动执行工作流。 
- **[在高级搜寻中采取操作](advanced-hunting-take-action.md)**- 快速包含威胁或解决你在高级搜寻中发现的威胁 [或遭到入侵的资产](advanced-hunting-overview.md)。
- **[门户内架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— 直接在安全中心获取有关高级搜寻架构表的信息。 除了表和列说明之外，此参考还包括受支持的事件类型和 (`ActionType` 查询) 值。
- **[DeviceFromIP ()](advanced-hunting-devicefromip-function.md)** 函数 — 获取有关在给定时间范围内分配了特定 IP 地址或地址的设备的信息。
