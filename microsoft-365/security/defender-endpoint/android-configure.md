---
title: 在 Android 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上配置适用于终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 配置
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935313"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>在 Android 功能上配置适用于终结点的 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>在 Android 上通过 Defender for Endpoint 进行条件访问  
Android 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 支持根据设备风险级别强制执行设备合规性和条件访问策略。 Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。

若要详细了解如何在 Android 和条件访问上设置适用于终结点的 Defender，请参阅[Defender for Endpoint 和 Intune。](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>配置自定义指示器  

> [!NOTE]
> Android 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

Android 上的 Defender for Endpoint 使管理员能够配置自定义指示器以支持 Android 设备。 若要详细了解如何配置自定义指示器，请参阅管理 [指示器](manage-indicators.md)。

## <a name="configure-web-protection"></a>配置 Web 保护
Android 上的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。 此功能在管理中心Microsoft Endpoint Manager可用。

> [!NOTE]
> Android 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。 有关详细信息，请参阅在运行 [Android 的设备上配置 Web 保护](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="related-topics"></a>相关主题
- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
