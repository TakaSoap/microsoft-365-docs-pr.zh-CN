---
title: 保护组织免受 Web 威胁
description: 了解 Microsoft Defender for Endpoint 中的 Web 保护及其如何保护你的组织。
keywords: Web 保护， Web 威胁防护， Web 浏览， 安全， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.openlocfilehash: 3ba4c4dbb2b5b8315fb09023b9fa0c0e29c4fd1c3b3f95da0328522a7d839ffc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53884243"
---
# <a name="protect-your-organization-against-web-threats"></a>保护组织免受 Web 威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

Web 威胁防护是 [Defender](web-protection-overview.md) for Endpoint 中的 Web 保护的一部分。 它 [使用网络保护](network-protection.md) 保护你的设备免受 Web 威胁。 通过与 chrome Microsoft Edge Firefox 等热门第三方浏览器集成，Web 威胁防护无需 Web 代理即可阻止 Web 威胁，并可在设备离开或位于本地时保护设备。 Web 威胁防护会停止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及自定义指示器列表中阻止 [的网站的访问](manage-indicators.md)。

> [!NOTE]
> 设备可能需要一小时才能收到新的自定义指示器。

## <a name="prerequisites"></a>先决条件

Web 保护使用网络保护在 web 和第三Microsoft Edge Web 浏览器上提供 Web 浏览安全性。

若要在设备上打开网络保护，请运行：

- 在 Web 网络保护下编辑 Defender for Endpoint **&，** 以在部署或重新部署网络保护之前启用网络保护。 [了解如何查看和分配 Defender for Endpoint 安全基线](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- 使用 Intune 设备配置、SCCM、组策略或 MDM 解决方案打开网络保护。 [阅读有关启用网络保护的更多信息](enable-network-protection.md)

> [!NOTE]
> 如果将网络保护设置为"仅 **审核"，** 则阻止将不可用。 此外，你将能够仅检测并记录访问恶意和不需要的网站Microsoft Edge尝试。

## <a name="related-topics"></a>相关主题

- [Web 保护功能概述](web-protection-overview.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
- [响应 web 威胁](web-protection-response.md)
- [网络保护](network-protection.md)
