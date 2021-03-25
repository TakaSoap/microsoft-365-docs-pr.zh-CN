---
title: 保护组织免受 Web 威胁
description: 了解 Microsoft Defender ATP 中的 Web 保护及其如何保护你的组织。
keywords: Web 保护， Web 威胁防护， Web 浏览， 安全， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185977"
---
# <a name="protect-your-organization-against-web-threats"></a>保护组织免受 Web 威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 威胁防护是 [Defender](web-protection-overview.md) for Endpoint 中的 Web 保护的一部分。 它 [使用网络保护](network-protection.md) 保护你的设备免受 Web 威胁。 通过与 Microsoft Edge 和热门第三方浏览器（如 Chrome 和 Firefox）集成，Web 威胁防护无需 Web 代理即可阻止 Web 威胁，并可在设备离开或位于本地时保护设备。 Web 威胁防护会停止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及自定义指示器列表中阻止 [的网站的访问](manage-indicators.md)。

>[!Note]
>设备可能需要一小时才能收到新的客户指标。

## <a name="prerequisites"></a>先决条件
Web 保护使用网络保护在 Microsoft Edge 和第三方 Web 浏览器上提供 Web 浏览安全性。

若要在设备上打开网络保护，请运行：
- 在 Web 网络保护下编辑 Defender for Endpoint **&，** 以在部署或重新部署网络保护之前启用网络保护。 [了解如何查看和分配 Defender for Endpoint 安全基线](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- 使用 Intune 设备配置、SCCM、组策略或 MDM 解决方案打开网络保护。 [阅读有关启用网络保护的更多信息](enable-network-protection.md)  

>[!Note]
>如果将网络保护设置为"仅 **审核"，** 则阻止将不可用。 此外，你将能够检测并记录仅在 Microsoft Edge 上访问恶意和不需要的网站的尝试。

## <a name="related-topics"></a>相关主题

- [Web 保护概述](web-protection-overview.md)
- [Web 威胁防护](web-threat-protection.md)
- [监视 Web 安全](web-protection-monitoring.md)
- [响应 Web 威胁](web-protection-response.md)
- [网络保护](network-protection.md)
