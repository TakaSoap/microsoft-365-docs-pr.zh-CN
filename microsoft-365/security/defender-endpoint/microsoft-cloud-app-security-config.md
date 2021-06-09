---
title: 配置 Microsoft Cloud App Security 集成
ms.reviewer: ''
description: 了解如何打开设置以启用 Microsoft Defender for Endpoint 与 Microsoft Cloud App Security。
keywords: 云， 应用， 安全性， 设置， 集成， 发现， 报告
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844750"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在Microsoft Cloud App Security Microsoft Defender for Endpoint 中配置策略

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


若要从适用于终结点的 Microsoft Defender 云应用发现信号中获益，请打开Microsoft Cloud App Security集成。

>[!NOTE]
>此功能将在运行[Windows 10](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上随 企业移动性 + 安全性 一起提供) 。 Windows 10，版本 1803 (OS 内部版本 17134.704，包含[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10、版本 1809 (OS 内部版本 17763.379（具有[KB4489899](https://support.microsoft.com/help/4489899)) 或更高版本 Windows 10 版本）。

> 请参阅[Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for Microsoft Defender for Endpoint with Microsoft Cloud App Security。 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>启用Microsoft Cloud App Security在 Microsoft Defender for Endpoint 中启用

1. 在导航窗格中，选择 **首选项设置**  >  **高级功能**。
2. 选择 **Microsoft Cloud App Security，** 将开关切换到 **开**。
3. 单击 **保存首选项**。

激活后，Microsoft Defender for Endpoint 将立即开始将发现信号转发到云应用安全。

## <a name="view-the-data-collected"></a>查看收集的数据

若要查看和访问 Microsoft Cloud Apps Security 中的 Microsoft Defender 终结点数据，请参阅调查 云应用安全 中的[设备](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。


有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

如果你有兴趣尝试使用Microsoft Cloud App Security，请参阅Microsoft Cloud App Security[试用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>相关主题
- [Microsoft Cloud App Security集成](microsoft-cloud-app-security-integration.md)
