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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5ac28c083e44ef25a77d49c57ee852e6179381df
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166305"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在Microsoft Cloud App Security Microsoft Defender for Endpoint 中配置策略

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

若要从适用于终结点的 Microsoft Defender 云应用发现信号中获益，请打开Microsoft Cloud App Security集成。

> [!NOTE]
> 此功能将随 E5 许可证一起提供[，企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)运行 Windows 10， 版本 1709 (OS 内部版本 16299.1085（包含[KB4493441](https://support.microsoft.com/help/4493441)) 、Windows 10、版本 1803 (操作系统内部版本 17134.704、KB4493464) 、Windows 10 版本 1809 (OS 内部版本 17763.379） [](https://support.microsoft.com/help/4493464) [KB4489899](https://support.microsoft.com/help/4489899)) 或更高版本Windows 10版本。

> 有关[Microsoft Defender for Endpoint](/cloud-app-security/mde-integration)与 Microsoft Cloud App Security 的详细集成，请参阅 Microsoft Defender for Endpoint Microsoft Cloud App Security。

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender Microsoft Cloud App Security终结点中启用支持

1. 在导航窗格中，选择 **首选项设置** \> **高级功能**。
2. 选择 **Microsoft Cloud App Security，** 将开关切换到 **开**。
3. 单击 **保存首选项**。

激活后，适用于终结点的 Microsoft Defender 将立即开始将发现信号转发云应用安全。

## <a name="view-the-data-collected"></a>查看收集的数据

若要查看和访问 Microsoft Cloud Apps Security 中的 Microsoft Defender for Endpoint 数据，请参阅调查 云应用安全 中的[设备](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。

有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

如果你有兴趣试用，请参阅Microsoft Cloud App Security试用版[Microsoft Cloud App Security。](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)

## <a name="related-topic"></a>相关主题

- [Microsoft Cloud App Security集成](microsoft-cloud-app-security-integration.md)
