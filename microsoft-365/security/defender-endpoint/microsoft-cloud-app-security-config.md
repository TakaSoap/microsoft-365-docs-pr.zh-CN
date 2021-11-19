---
title: 为云应用集成配置 Microsoft Defender
ms.reviewer: ''
description: 了解如何启用设置以启用 Microsoft Defender for Endpoint 与 Microsoft Defender for Cloud Apps 集成。
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
ms.openlocfilehash: 88952a3f2c8173b20b8ee81322a0312144197ad5
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111599"
---
# <a name="configure-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中为云应用配置 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

若要从适用于终结点的 Microsoft Defender 云应用发现信号中获益，请打开 Microsoft Defender for Cloud Apps 集成。

> [!NOTE]
> 此功能将随 E5 许可证一起提供[，企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)运行 Windows 10。 版本 1709 (OS 内部版本 16299.1085（带[KB4493441](https://support.microsoft.com/help/4493441)) ，Windows 10，版本 1803 (OS 内部版本 17134.704，具有[KB4493464](https://support.microsoft.com/help/4493464)) ，Windows 10 版本 1809 (OS 内部版本 17763.379[KB4489899](https://support.microsoft.com/help/4489899)) 或更高版本Windows 10版本。

> 有关 [Microsoft Defender for Endpoint](/cloud-app-security/mde-integration) 与 Microsoft Defender for Cloud Apps 的详细集成，请参阅 Microsoft Defender for Endpoint 与 Microsoft Defender for Cloud Apps 集成。

## <a name="enable-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中启用 Microsoft Defender for Cloud Apps

1. 在导航窗格中，选择 **首选项设置** \> **高级功能**。
2. 选择 **"Microsoft Defender 云应用"，** 将开关切换到 **"开"。**
3. 单击 **保存首选项**。

激活后，Microsoft Defender for Endpoint 将立即开始将发现信号转发到 Defender for Cloud Apps。

## <a name="view-the-data-collected"></a>查看收集的数据

若要查看和访问 Microsoft Cloud Apps Security 中的 Microsoft Defender 终结点数据，请参阅调查 [适用于云应用的 Defender 中的设备](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。

有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

如果你对试用 Microsoft Defender for Cloud Apps 感兴趣，请参阅 [Microsoft Defender for Cloud Apps 试用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>相关主题

- [Microsoft Defender for Cloud Apps 集成](microsoft-cloud-app-security-integration.md)
