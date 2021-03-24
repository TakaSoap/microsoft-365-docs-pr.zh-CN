---
title: 威胁和漏洞管理中的曝光评分
description: 威胁和漏洞管理暴露分数反映了组织对网络安全威胁的易受攻击程度。
keywords: 曝光分数， mdatp 曝光分数， mdatp 电视曝光分数， 组织曝光分数， 电视组织曝光分数， 威胁和漏洞管理， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc7abd678d6f2d317d02c4ed2b8028e7e270b055
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056505"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a>曝光评分 - 威胁和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

你的曝光分数显示在 Microsoft Defender 安全中心的威胁 [和](tvm-dashboard-insights.md) 漏洞管理仪表板中。 它反映了你的组织对网络安全威胁的易受攻击程度。 低曝光分数意味着你的设备更容易被利用。

- 快速了解和识别有关组织中安全状态的高层次要点。
- 检测和响应需要调查或操作以改进当前状态的区域。
- 与对等方和管理人员就安全工作的影响进行沟通。

卡片可让你高级查看一段时间的曝光分数趋势。 图表中的任何峰值都直观地指示高网络安全威胁暴露，你可以进一步调查。

![曝光分数卡](images/tvm_exp_score.png)

## <a name="how-it-works"></a>运作方式

曝光分数分为以下级别：

- 0–29：低曝光分数
- 30–69：中等曝光分数
- 70–100：高曝光分数

你可以根据优先的安全建议修正问题 [，](tvm-security-recommendation.md) 以减少曝光评分。 每个软件都有一些缺陷，这些缺陷会转换为建议，并基于组织的风险确定优先级。

## <a name="reduce-your-threat-and-vulnerability-exposure"></a>减少威胁和漏洞暴露

通过修正安全建议降低威胁 [和漏洞暴露](tvm-security-recommendation.md)。 通过修正最高安全建议（可在威胁和漏洞管理仪表板中查看）来对曝光评分 [产生最大影响](tvm-dashboard-insights.md)。

## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 设备安全分数](tvm-microsoft-secure-score-devices.md)
- [安全性建议](tvm-security-recommendation.md)
- [事件时间线](threat-and-vuln-mgt-event-timeline.md)
