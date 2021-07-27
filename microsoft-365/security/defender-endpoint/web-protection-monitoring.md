---
title: 在 Microsoft Defender for Endpoint 中监视 Web 浏览安全性
description: 使用 Microsoft Defender for Endpoint 中的 Web 保护监视 Web 浏览安全性
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 19ce05acaf4e06a97014cea3ff57d7c3d8cabfe7
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567064"
---
# <a name="monitor-web-browsing-security"></a>监视 Web 浏览安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

通过 Web 保护，可以通过报告门户中"报告 web > **Web** 保护"下的报告监视Microsoft 365 Defender安全。 该报告包含提供 Web 威胁检测统计信息的卡片。

- **随着时间的推移进行** Web 威胁防护检测 - 此趋势卡片显示在所选时间段（"最近 30 天 (最近 30 天、过去 3 个月、过去 6 个月）内按类型检测到的 Web 威胁) 
 
  :::image type="content" alt-text="显示一段时间的 Web 威胁防护检测的卡片图像" source="images/wtp-blocks-over-time.png" lightbox="images/wtp-blocks-over-time.png":::

- **Web 威胁防护摘要** - 此卡片显示过去 30 天内的 Web 威胁检测总数，显示不同类型的 Web 威胁的分布情况。 选择切片将打开通过恶意或不需要的网站找到的域列表。

  :::image type="content" alt-text="显示 Web 威胁防护摘要的卡片图像" source="images/wtp-summary.png" lightbox="images/wtp-summary.png":::

>[!Note]
>阻止可能最多需要 12 个小时才能反映在卡或域列表中。

## <a name="types-of-web-threats"></a>Web 威胁的类型

Web 保护将恶意和不需要的网站分类为：

- **网络钓鱼** - 包含欺骗性 Web 表单和其他网络钓鱼机制的网站，旨在欺骗用户泄露凭据和其他敏感信息
- **恶意** - 托管恶意软件和攻击代码的网站
- **自定义指示器** - 已添加到用于阻止的自定义指示器列表的 URL [或](manage-indicators.md) 域的网站

## <a name="view-the-domain-list"></a>查看域列表

选择 Web 威胁防护摘要卡中的特定 **Web 威胁** 类别以打开 **"域"** 页面。 此页面显示该威胁类别下的域列表。 该页面提供每个域的以下信息：

- **访问计数** - 域中 URL 的请求数
- **块** - 阻止请求次数
- **访问趋势** - 访问尝试次数的变化
- **威胁类别** - Web 威胁的类型
- **设备** - 尝试访问的设备数

选择一个域以查看尝试访问该域中的 URL 的设备列表和 URL 列表。

## <a name="related-topics"></a>相关主题

- [Web 保护功能概述](web-protection-overview.md)
- [Web 内容筛选](web-content-filtering.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [响应 web 威胁](web-protection-response.md)
