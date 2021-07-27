---
title: 在 iOS 功能上部署 Microsoft Defender for Endpoint
description: 介绍如何在 iOS 功能上部署 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 配置， 功能， ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b6851c54d961bbb41229f8ae08bad372228629c0
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542426"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>在注销的 iOS 设备上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> iOS 上的 Defender for Endpoint 使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>在应用保护策略中配置 Microsoft Defender for Endpoint 风险信号 (MAM) 

Microsoft Defender for Endpoint 可以配置为发送要用于应用保护策略 (APP（也称为 iOS/iPadOS 上的 MAM) MAM） 中的威胁信号。 借助此功能，也可使用 Microsoft Defender for Endpoint 保护从注销的设备访问公司数据。

使用 Microsoft Defender for Endpoint 设置应用保护策略的步骤如下：

1. 设置从你的 Microsoft Endpoint Manager 到 Microsoft Defender for Endpoint 的连接。 在 [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 中，转到"设置) "下的"跨平台) "或"终结点安全 Microsoft Defender  >    >  **for**   >  **Endpoint** ("下的"适用于终结点的 Microsoft Defender (租户管理连接器和令牌"，然后打开适用于 iOS 的应用保护策略 设置 下的切换。
1. 选择“**保存**”。 应看到"**连接状态**"现在设置为"**已启用"。**
1. 创建应用保护策略：Microsoft Defender for Endpoint 连接器设置完成后，导航到"策略 (下的应用应用保护策略) 以创建新策略或更新现有  >  策略。
1. 选择组织为策略 **所需的** 平台、应用、数据保护、访问要求设置。
1. 在 **"条件启动**  >  **设备条件**"下，你将找到设置 **"允许的最大设备威胁级别"。** 需要将此功能配置为"低、中、高"或"安全"。 可用操作为"阻止 **访问"或**"**擦除数据"。** 你可能会看到信息对话框，以确保在此设置生效之前已经设置了连接器。 如果连接器已设置，可以忽略此对话框。
1. 完成分配并保存策略。

有关 MAM 或应用保护策略的更多详细信息，请参阅 [iOS 应用保护策略设置](/mem/intune/apps/app-protection-policy-settings-ios)。

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>为 MAM 或注销的设备上部署 Microsoft Defender for Endpoint

iOS 上的 Microsoft Defender for Endpoint 支持应用保护策略方案，并且适用于 Apple 应用商店。

当为应用配置应用保护策略以包含来自 Microsoft Defender for Endpoint 的设备风险信号时，将在使用此类应用时重定向用户以安装 Microsoft Defender for Endpoint。 或者，用户还可以直接从 Apple 应用商店安装应用的最新版本。
