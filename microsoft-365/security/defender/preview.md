---
title: 预览 Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430812"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender预览功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

该Microsoft 365 Defender服务会不断更新，以包含新功能增强功能和功能。

了解 Microsoft 365 Defender 预览版本中的新功能，并首先通过打开预览体验来试用即将推出的功能。

有关已普遍提供的新功能详细信息，请参阅 Microsoft 365 Defender[中的新增功能](whats-new.md)。

 ## <a name="what-you-need-to-know"></a>您需要了解哪些信息

使用公共预览版中的功能时，这些功能：

- 功能可能受限或受限。 例如，此功能可能仅适用于一个平台。
- 通常先完成功能更改，然后再在 GA (正式) 。
- 完全受 Microsoft 支持。
- 可能仅在选定的地理区域或云环境中可用。 例如，此功能可能不存在于政府云中。
- 预览版中的单个功能可能具有更多用法和支持限制。 如果是这样，此信息通常会记录在功能文档中。
- 预览版本提供标准支持级别，可用于生产环境。 



## <a name="required-permissions"></a>所需权限

分配了以下 Azure AD Azure Active Directory (角色) 帐户可以启用Microsoft 365 Defender预览功能：

- 全局管理员
- 安全管理员
- 安全操作员

## <a name="turn-on-preview-features"></a>启用预览功能

你有权访问即将推出的功能，可以在这些功能全面发布之前提供反馈以帮助改善整体体验。

启用预览体验设置，以率先体验即将推出的功能。

1. 在导航窗格中，选择“**设置**”。
2. 选择 **"Microsoft 365 Defender"。**
3. 选择“**预览功能**” > “**启用预览功能**”。 
4. 选择“**保存**”。

当看到 **启用预览功能**”复选框处于选中状态时，你会知道已开启了预览功能。 

## <a name="preview-features"></a>预览功能

当前预览版中提供以下功能和增强功能：

- **[查看每个威胁标记的报告](threat-analytics.md#view-reports-per-threat-tags)** - 威胁标记可帮助你专注于特定威胁类别并查看最相关的报告。
- **[流式 API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender支持将高级搜寻提供的所有事件流式处理到事件中心和/或 Azure 存储帐户。
- **[Microsoft 365 Defender API](api-overview.md)** - 顶级Microsoft 365 Defender API 将使您能够基于共享事件和高级搜寻表自动执行工作流。 
- **[在高级搜寻中采取措施](advanced-hunting-take-action.md)** - 快速包含威胁或解决你在高级搜寻中 [发现的攻击资产](advanced-hunting-overview.md)。
- **[门户内架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - 直接在安全中心获取有关高级搜寻架构表的信息。 除了表和列说明之外，此参考还包括受支持的事件类型 (`ActionType` 查询) 查询的值。
- **[DeviceFromIP ()](advanced-hunting-devicefromip-function.md)** 函数 - 获取有关在给定时间范围内分配了特定 IP 地址的设备的信息。
