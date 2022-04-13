---
title: Microsoft 365 Lighthouse威胁管理页概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用Microsoft 365 Lighthouse) MSP，请了解“威胁管理”页。
ms.openlocfilehash: 94e71d648dac3a285ecef81b4dae29305cf7e98c
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823159"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse威胁管理页概述 

**适用于：**

- Windows 10

Microsoft Defender 防病毒保护租户、用户和设备免受软件威胁，包括病毒、恶意软件和间谍软件。 它是强大的持续保护，内置于Windows 10中，包含在 Microsoft 365 商业高级版 和 Microsoft365E3&nbsp;&nbsp; 中。  
  
若要访问Microsoft 365 Lighthouse中的威胁管理页面，请在左侧导航窗格中选择 **“威胁管理**”，查看客户租户针对威胁的安全状况。 你将看到需要注意的租户、用户和设备，以及有助于降低风险的建议。  
  
## <a name="overview-tab"></a>“概述”选项卡  
  
在“威胁管理”页的“概述”选项卡上，可以监视所有租户的防病毒状态，以确定需要注意的区域。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="“概述”选项卡的屏幕截图。":::

## <a name="threats-tab"></a>“威胁”选项卡

在“威胁管理”页的“威胁”选项卡上，可以看到所有租户中的“活动”、“已缓解”、“已解决”和“允许”威胁。 还可以通过筛选和深入了解哪些设备、用户或租户受到影响，同时在所有租户中修正多个威胁。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="“默认基线”页的屏幕截图。":::
  
可以通过以下方法筛选威胁：

- 威胁状态
- 威胁严重性
- 威胁类型
- 日期范围

下表列出了不同的威胁状态及其定义：<br><br>

| 威胁状态 | 定义 |
|---|---|
| 活动 | 威胁在设备上处于活动状态。 |
| 无状态 | 威胁状态不可用。 在设备上运行完全扫描以Microsoft Defender 防病毒重新设置威胁。 |
| 操作失败 | 设备没有风险。 操作已失败，但潜在威胁已停止，并且未在设备上处于活动状态。 在设备上运行完整扫描。 |
| 所需的手动步骤 | 威胁已停止，但需要手动完成步骤，例如完全扫描或重新启动设备。 |
| 需要完全扫描 | 需要对设备进行完全扫描。 |
| 需要重新启动 | 需要重新启动设备。 |
| 使用非关键故障进行修正 | 威胁已得到修正，不需要采取进一步行动。 |
| 隔离 | 威胁已被隔离。 无需再执行任何操作。 |
| 已删除 | 威胁已成功从设备中删除。 无需再执行任何操作。 |
| 打扫 | Microsoft Defender 防病毒已恢复和消毒文件。 无需再执行任何操作。 |
| Allowed | 管理员允许威胁保留在设备上。 | 

## <a name="antivirus-protection-tab"></a>防病毒保护选项卡

“威胁”管理页上的“防病毒保护”选项卡显示所有租户中的设备及其Microsoft Defender 防病毒保护状态。 可以评估状态，并针对一个或多个可能易受攻击的设备采取措施。 还可以选择设备以查看详细信息，例如设备概述、当前威胁和设备操作状态。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="“防病毒”选项卡的屏幕截图。":::

## <a name="related-content"></a>相关内容

[部署Microsoft 365 Lighthouse基线](m365-lighthouse-deploy-baselines.md) (文章) \
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) 
