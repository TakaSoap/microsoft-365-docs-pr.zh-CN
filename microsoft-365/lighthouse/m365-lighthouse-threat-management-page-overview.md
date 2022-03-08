---
title: Microsoft 365 Lighthouse 威胁管理页面概述
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
description: 有关托管服务提供商 (MICROSOFT 365) 的托管服务提供商，请了解"威胁管理"页。
ms.openlocfilehash: e57163ba462e241c74a96db78fe701c024a037ff
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329864"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse 威胁管理页面概述 

**适用于：**

- Windows 10

Microsoft Defender 防病毒保护租户、用户和设备免受软件威胁（包括病毒、恶意软件和间谍软件）的侵害。 它是内置于 Windows 10 中且随 Microsoft 365 商业高级版和 Microsoft365E3&nbsp; 一起提供且强大的持续&nbsp;保护。  
  
To access the Threat management page in Microsoft 365 Lighthouse， select **Threat Management** in the left navigation pane to view your customer tenants' security posture against threats. 你将看到需要你注意的租户、用户和设备，以及有助于降低风险的建议。  
  
## <a name="overview-tab"></a>"概述"选项卡  
  
在"威胁管理"页的"概述"选项卡上，可以监视所有租户中的防病毒状态，以确定需要关注的区域。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="&quot;概述&quot;选项卡的屏幕截图。":::

## <a name="threats-tab"></a>"威胁"选项卡

在"威胁管理"页的"威胁"选项卡上，你可以看到所有租户中的"活动、缓解、已解决和允许的威胁"。 您还可以通过筛选并向下钻取每个威胁来了解哪些设备、用户或租户受到影响，从而同时修正所有租户中的多个威胁。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="&quot;默认基线&quot;页的屏幕截图。":::
  
你可以按：筛选威胁：

- 威胁状态
- 威胁严重性
- 威胁类型
- 日期范围

下表列出了不同的威胁状态及其定义：<br><br>

| 威胁状态 | 定义 |
|--|--|
| 活动 | 威胁在设备上处于活动状态。 |
| 无状态 | 威胁状态不可用。 在设备上运行完全扫描，让 Microsoft Defender 防病毒重新检测威胁。 |
| 操作失败 | 设备没有风险。 操作已失败，但潜在威胁已停止，并且未在设备上处于活动状态。 在设备上运行完全扫描。 |
| 需要手动步骤 | 威胁已停止，但需要手动完成步骤，例如完全扫描或设备重启。 |
| 需要完全扫描 | 需要设备的完整扫描。 |
| 需要重新启动 | 需要重新启动设备。 |
| 使用非关键故障修正 | 威胁已修复，无需执行其他操作。 |
| 已隔离 | 威胁已隔离。 无需执行其他操作。 |
| 已删除 | 已成功从设备中删除威胁。 无需执行其他操作。 |
| 已清理 | Microsoft Defender 防病毒已恢复和禁用文件。 无需执行其他操作。 |
| Allowed | 管理员允许威胁保留在设备上。 | 

## <a name="antivirus-protection-tab"></a>防病毒保护选项卡

"威胁管理"页上的"防病毒保护"选项卡显示所有租户中的设备及其 Microsoft Defender 防病毒保护状态。 你可以评估状态，并针对一个或多个可能易受攻击的设备采取措施。 还可以选择设备查看详细信息，如设备概述、当前威胁和设备操作状态。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="&quot;防病毒&quot;选项卡的屏幕截图。":::

## <a name="related-content"></a>相关内容

[Deploy Microsoft 365 Lighthouse baselines (](m365-lighthouse-deploy-baselines.md) article) \
[Microsoft 365 Lighthouse 常见问题](m365-lighthouse-faq.yml) (文章) 
