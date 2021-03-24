---
title: Microsoft Cloud App Security 集成概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 通过转发所有云应用网络活动与 Cloud App Security 集成。
keywords: 云， 应用， 网络， 可见性， 使用情况
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055965"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Defender for Endpoint 中的 Microsoft Cloud App Security 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) 是一个全面的解决方案，通过允许您控制和限制对云应用的访问权限，同时对云中存储的数据强制执行合规性要求，可了解云应用和服务。 有关详细信息，请参阅[Cloud App Security。](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

>[!NOTE]
>此功能随 E5 许可证一起提供[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)，适用于运行 Windows 10 版本 1809 或更高版本的设备上企业移动性 + 安全性。

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint 和 Cloud App Security 集成 

Cloud App Security 发现依赖于从企业防火墙和代理服务器转发到它的云流量日志。 Microsoft Defender for Endpoint 通过收集和转发所有云应用网络活动与 Cloud App Security 集成，从而提供云应用使用情况的可见度。 监控功能内置于设备中，可提供网络活动的完全覆盖。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


集成对现有云应用安全发现提供了以下重大改进： 

- 可在任何位置使用 - 由于网络活动直接从终结点收集，因此无论设备位于公司网络内部还是外部，设备都可用，因为它不再依赖于通过企业防火墙或代理服务器路由的流量。 

- 开箱即用，无需配置 - 将云流量日志转发到 Cloud App Security 需要防火墙和代理服务器配置。 借助 Defender for Endpoint 和 Cloud App Security 集成，无需任何配置。 只需在 Microsoft Defender 安全中心设置中打开它，你可继续操作。 

- 设备上下文 - 云流量日志缺少设备上下文。 Defender for Endpoint 网络活动通过设备上下文报告 (哪些设备访问了云应用) ，因此你能够准确了解 (设备) 网络活动的发生位置，以及执行网络活动的 () 用户。 

有关云发现详细信息，请参阅 [使用发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>相关主题

- [配置 Microsoft Cloud App Security 集成](microsoft-cloud-app-security-config.md)
