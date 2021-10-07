---
title: 在 Android 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上配置适用于终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 配置
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4db57a39d6270608a5107a77f41ce11fdd139c78
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186628"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>在 Android 功能上配置适用于终结点的 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>在 Android 上通过 Defender for Endpoint 进行条件访问

Android 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 启用基于设备风险级别的设备合规性和条件访问策略。 Defender for Endpoint 是一种移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。

若要详细了解如何在 Android 和条件访问上设置适用于终结点的 Defender，请参阅[Defender for Endpoint 和 Intune。](/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>配置自定义指示器

> [!NOTE]
> Android 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。

Android 上的 Defender for Endpoint 使管理员能够配置自定义指示器以支持 Android 设备。 若要详细了解如何配置自定义指示器，请参阅管理 [指示器](manage-indicators.md)。

## <a name="configure-web-protection"></a>配置 Web 保护
Android 上的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。 此功能在管理中心Microsoft Endpoint Manager可用。

> [!NOTE]
> Android 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。
> 有关详细信息，请参阅在运行 [Android 的设备上配置 Web 保护](/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="configure-privacy-for-malware-threat-report"></a>配置恶意软件威胁报告的隐私

> [!NOTE]
> Android 版 Defender for Endpoint 的隐私控件目前处于预览阶段，在商业发行之前可能会进行重大修改。

恶意软件威胁报告的隐私控制可用于禁用从恶意软件威胁报告 (名称和程序包) 应用详细信息集合。 这使组织能够灵活地选择是否在检测到恶意应用时收集应用名称。 *此功能当前仅适用于在 Android 设备管理员模式下 **注册** 的设备。*

使用以下步骤为目标用户启用它：

1. In [Microsoft Endpoint Manager admin center，](https://go.microsoft.com/fwlink/?linkid=2109431) go to **Devices**  >  **Configuration profiles** Create  >  **profile** and enter the following settings：

   - **平台**：选择 Android 设备管理员
   - **配置文件：** 选择"自定义"，然后单击创建

2. 在"基础知识"部分，指定配置文件的名称和说明。
3. 在配置设置中，选择添加 **OMA-URI** 设置：

   - **名称**：为此 OMA-URI 设置输入唯一的名称和说明，以便你稍后可以轻松找到它。
   - **OMA-URI：./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - 数据类型：在下拉列表中选择"整数"。
   - 值：输入 1 以启用隐私 (默认情况下，该值为 0) 

4. 单击 **"** 下一步"，并将此配置文件分配给目标设备/用户。

启用上述隐私控制不会影响设备合规性检查或条件访问，例如，具有恶意应用的设备的风险级别始终为"中等"。

## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
