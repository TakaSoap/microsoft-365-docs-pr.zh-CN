---
title: 配置适用于 Android 功能的 Microsoft Defender ATP
description: 介绍如何配置适用于 Android 的 Microsoft Defender ATP
keywords: microsoft， defender， atp， android， 配置
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163443"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>配置适用于 Android 功能的 Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>使用适用于 Android 的 Defender 终结点的条件访问  
Microsoft Defender for Endpoint for Android 以及 Microsoft Intune 和 Azure Active Directory 支持根据设备风险级别强制执行设备合规性和条件访问策略。 Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。

若要详细了解如何为 Android 和条件访问设置适用于终结点的 Defender，请参阅[Defender for Endpoint 和 Intune。](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>配置自定义指示器  

> [!NOTE]
> 适用于 Android 的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

适用于 Android 的 Defender 支持管理员配置自定义指示器以支持 Android 设备。 若要详细了解如何配置自定义指示器，请参阅管理 [指示器](manage-indicators.md)。

## <a name="configure-web-protection"></a>配置 Web 保护
适用于 Android 的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。 此功能在 Microsoft Endpoint Manager 管理中心内可用。

> [!NOTE]
> 适用于 Android 的 Defender 终结点将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。 有关详细信息，请参阅在运行 [Android 的设备上配置 Web 保护](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="related-topics"></a>相关主题
- [适用于 Android 的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 部署适用于 Android 的 Microsoft Defender for Endpoint](android-intune.md)
