---
title: 创建指示器
ms.reviewer: ''
description: 创建文件哈希、IP 地址、URL 或域的指示器，以定义实体的检测、防护和排除。
keywords: 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842238"
---
# <a name="create-indicators"></a>创建指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

ICS (泄露) 是每个终结点保护解决方案中的重要功能。 此功能使 SecOps 能够设置指示器列表，用于检测并阻止 (防护和响应) 。

创建定义实体的检测、防护和排除的指示器。 你可以定义要采取的操作以及何时应用该操作的持续时间，以及要应用该操作的设备组的范围。

当前支持的源是 Defender for Endpoint 的云检测引擎、自动调查和修正引擎以及终结点防护引擎 (Microsoft Defender 防病毒) 。

**云检测引擎**<br>
Defender for Endpoint 的云检测引擎会定期扫描收集的数据并尝试匹配你设置的指示器。 当有匹配时，将按照你为 IoC 指定的设置来采取措施。

**终结点防护引擎**<br>
保护代理会遵守相同的指示器列表。 这意味着，如果 Microsoft Defender AV 是配置的主要 AV，将按照设置处理匹配的指示器。 例如，如果操作为"警报和阻止"，Microsoft Defender AV 将阻止文件执行 (并修正) 并引发相应的警报。 另一方面，如果操作设置为"允许"，Microsoft Defender AV 将不会检测也不会阻止文件运行。

**自动调查和修正引擎**<BR>
自动调查和修正的行为相同。 如果指示器设置为"允许"，自动调查和修正将忽略它的"错误"裁定。 如果设置为"阻止"，自动调查和修正将视为"错误"。

> [!NOTE]
> EnableFileHashComputation 设置在文件扫描期间计算证书和文件 IoC 的文件哈希。 它支持对哈希和证书属于受信任应用程序的 IoC 强制。 它将通过允许或阻止文件设置同时启用和禁用。 EnableFileHashComputation 通过组策略手动启用，默认情况下处于禁用状态。


当前支持的操作包括：
- 允许
- 仅警报
- 警报和阻止


你可以为：
- [Files](indicator-file.md)
- [IP 地址、URL/域](indicator-ip-domain.md)
- [证书](indicator-certificates.md)


> [!NOTE]
> 每个租户限制为 15，000 个指示器。 文件和证书指示器不会阻止[为文件定义排除Microsoft Defender 防病毒。](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) 当指示器处于被动模式Microsoft Defender 防病毒不支持指示器。 


## <a name="related-topics"></a>相关主题

- [创建上下文 IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [使用 Microsoft Defender 终结点指示器 API](ti-indicator.md)
- [使用合作伙伴集成解决方案](partner-applications.md)
