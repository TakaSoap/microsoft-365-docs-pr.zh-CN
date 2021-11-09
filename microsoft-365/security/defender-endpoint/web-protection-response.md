---
title: 在 Microsoft Defender for Endpoint 中响应 Web 威胁
description: 响应与恶意和不需要的网站相关的警报。 了解 Web 威胁防护如何通过最终用户的 Web 浏览器和通知通知Windows通知
keywords: Web 保护， Web 威胁防护， Web 浏览， 警报， 响应， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器， 通知， 最终用户， Windows 通知， 阻止页面，
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b893c6d823ae2582dfe59122861776023acf026
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883421"
---
# <a name="respond-to-web-threats"></a>响应 web 威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

通过 Microsoft Defender for Endpoint 中的 Web 保护，你可以高效地调查和响应与自定义指示器列表中的恶意网站和网站相关的警报。

## <a name="view-web-threat-alerts"></a>查看 Web 威胁警报

Microsoft Defender for Endpoint 针对恶意 [或](manage-alerts.md) 可疑 Web 活动生成以下警报：

- **网络保护阻止的** 可疑连接：当在阻止模式下网络保护停止尝试访问自定义指示器列表中的恶意网站或网站时，将生成 *此* 警报
- **网络保护检测到的** 可疑连接：当网络保护在仅审核模式下检测到尝试访问自定义指示器列表中的恶意网站或网站时 *，将生成此* 警报

每个警报都提供以下信息：

- 尝试访问阻止的网站的设备
- 用于发送 Web 请求的应用程序或程序
- 自定义指示器列表中的恶意 URL 或 URL
- 针对响应器的建议操作

![与 Web 威胁防护相关的警报的图像。](images/wtp-alert.png)

> [!NOTE]
> 为了减少警报量，Microsoft Defender for Endpoint 每天将同一设备上同一域的 Web 威胁检测合并为单个警报。 仅生成一个警报，并计入 [Web 保护报告](web-protection-monitoring.md)。

## <a name="inspect-website-details"></a>检查网站详细信息

您可以通过在警报中选择网站的 URL 或域来深入探究。 这将打开一个包含各种信息的特定 URL 或域的页面，其中包括：

- 尝试访问网站的设备
- 与网站相关的事件和警报
- 在组织的活动中查看网站频率

    ![域或 URL 实体详细信息页面的图像。](images/wtp-website-details.png)

[详细了解 URL 或域实体页面](investigate-domain.md)

## <a name="inspect-the-device"></a>检查设备

还可以检查尝试访问阻止的 URL 的设备。 在警报页面上选择设备名称将打开一个包含有关设备的综合信息的页面。

[了解有关设备实体页面的信息](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>为最终用户Windows Web 浏览器和通知

借助 Microsoft Defender for Endpoint 中的 Web 保护，最终用户将阻止其使用 Microsoft Edge或其他浏览器访问恶意或不需要的网站。 由于阻止是由网络 [保护执行的](network-protection.md)，因此他们将从 Web 浏览器看到一个常规错误。 他们还将看到来自用户Windows。

![显示Microsoft Edge 403 错误和错误通知Windows的图像。 ](images/wtp-browser-blocking-page.png)
*Web 威胁在 Microsoft Edge*

![Chrome Web 浏览器的图像，显示安全连接警告和Windows通知。 ](images/wtp-chrome-browser-blocking-page.png)
*在 Chrome 上阻止的 Web 威胁*

## <a name="related-topics"></a>相关主题

- [Web 保护功能概述](web-protection-overview.md)
- [Web 内容筛选](web-content-filtering.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
