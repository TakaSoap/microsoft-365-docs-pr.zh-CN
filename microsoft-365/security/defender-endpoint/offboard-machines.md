---
title: 从 Microsoft Defender for Endpoint 服务载出设备
description: 从 Microsoft Defender Windows载入设备、服务器Windows非安全设备
keywords: offboarding， Microsoft Defender for Endpoint offboarding， offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c2ec837ebc9fef0aabd2810dbd22db24597c52da
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322599"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>从 Microsoft Defender for Endpoint 服务载出设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)。

按照相应说明进行操作，具体取决于你的首选部署方法。

> [!NOTE]
> 在载出 7 天后，设备的状态将切换到[](fix-unhealthy-sensors.md#inactive-devices)非活动状态。
>
> 已载出设备的数据 (时间线、警报、漏洞等) 将保留在门户中，直到配置的保留[期过期。](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy)
>
> 不带数据 (设备配置文件) 将在设备 [列表中](machines-view-overview.md) 保留不超过 180 天。
>
> 此外，反映组织的 危险和漏洞管理 曝光分数和 Microsoft 设备安全分数的数据不会考虑过去 30 天内未处于活动状态的设备。 [](tvm-exposure-score.md)
>
> 若要仅查看活动设备，可以按[传感器运行状况、](machines-view-overview.md#use-filters-to-customize-the-device-inventory-views)设备标记或计算机 [](machine-tags.md) [组进行筛选](machine-groups.md)。

## <a name="offboard-windows-devices"></a>载出Windows设备

- [使用本地脚本的载出设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [使用组策略的载出设备](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [使用移动设备管理工具的载出设备](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>载出服务器

- [载出服务器](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>载出非Windows设备

- [载出非Windows设备](configure-endpoints-non-windows.md#offboard-non-windows-devices)
