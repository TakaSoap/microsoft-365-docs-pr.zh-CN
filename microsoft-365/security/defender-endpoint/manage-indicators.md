---
title: 创建指示器
ms.reviewer: ''
description: 为定义实体检测、预防和排除的文件哈希、IP 地址、URL 或域创建指示器。
keywords: 管理、允许、阻止、阻止、清理、恶意、文件哈希、ip 地址、URL、域
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
ms.openlocfilehash: 55f9529d511435eb66f2791fe8a177a9fa35a8a5
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666319"
---
# <a name="create-indicators"></a>创建指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
>
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

 (IoC) 匹配的泄露指示器是每个终结点保护解决方案中的基本功能。 此功能使 SecOps 能够设置检测和阻止 (防护和响应) 的指示器列表。

创建用于定义实体检测、预防和排除的指示器。 可以定义要执行的操作以及何时应用操作的持续时间，以及要应用该操作的设备组的范围。

目前支持的源包括 Defender for Endpoint 的云检测引擎、自动调查和修正引擎以及终结点防护引擎 (Microsoft Defender 防病毒) 。

## <a name="cloud-detection-engine"></a>云检测引擎

Defender for Endpoint 的云检测引擎定期扫描收集的数据，并尝试匹配设置的指示器。 当存在匹配项时，将根据为 IoC 指定的设置执行操作。

## <a name="endpoint-prevention-engine"></a>终结点防护引擎

预防代理会遵守相同的指标列表。 这意味着，如果 Microsoft Defender AV 是配置的主 AV，则会根据设置处理匹配的指示器。 例如，如果操作为"警报和阻止"，Microsoft Defender AV 将阻止文件执行 (阻止和修正) 并引发相应的警报。 另一方面，如果操作设置为"允许"，Microsoft Defender AV 将不会检测或阻止该文件运行。

## <a name="automated-investigation-and-remediation-engine"></a>自动调查和修正引擎

自动调查和修正的行为相同。 如果指示器设置为"允许"，自动调查和修正将忽略其"错误"判决。 如果设置为"阻止"，自动调查和修正会将其视为"错误"。

EnableFileHashComputation 设置在文件扫描期间计算证书和文件 IoC 的文件哈希。 它支持 IoC 强制实施属于受信任应用程序的哈希和证书。 它将同时启用并禁用允许或阻止文件设置。 EnableFileHashComputation 是通过组策略手动启用的，默认情况下处于禁用状态。

在 IoC)  (创建新指示器时，可使用以下一个或多个操作：

- 允许 - IoC 将被允许在设备上运行。
- 审核 - IoC 运行时将触发警报。
- 警告 - IoC 将提示用户可以绕过的警告 
- 阻止执行 - 不允许运行 IoC。
- 阻止和修正 - 不允许运行 IoC，并且将向 IoC 应用修正操作。

>[!NOTE]
> 如果用户打开有风险的应用，则使用警告模式会提示用户发出警告。 提示不会阻止他们使用应用，但你可以提供自定义消息和指向描述应用适当使用情况的公司页面的链接。 用户仍然可以绕过警告，并在需要时继续使用应用。 有关详细信息，请参阅[Microsoft Defender for Endpoint发现的治理应用](/cloud-app-security/mde-govern)。

可以为以下内容创建指示器：

- [Files](indicator-file.md)
- [IP 地址、URL/域](indicator-ip-domain.md)
- [证书](indicator-certificates.md)

下表准确显示了每个指示器可用的操作 (IoC) 类型：

| IoC 类型 | 可用操作 |
|:---|:---|
| [Files](indicator-file.md) | 允许 <br> Audit <br> 阻止和修正 |
| [IP 地址](indicator-ip-domain.md) | 允许 <br> Audit <br> 阻止执行 <br> 警告 |
| [URL 和域](indicator-ip-domain.md) | 允许 <br> Audit <br> 阻止执行<br> 警告 |
| [证书](indicator-certificates.md) | 允许 <br> 阻止和修正 |

预先存在的 IoC 的功能不会改变。 但是，这些指示器已重命名，以匹配当前支持的响应操作：

- "仅警报"响应操作已重命名为"审核"，并启用了生成警报设置。
- 使用可选生成警报设置，将"警报和阻止"响应重命名为"阻止和修正"。

已更新 IoC API 架构和威胁 ID，以便与重命名 IoC 响应操作保持一致。 API 方案更改适用于所有 IoC 类型。

> [!Note]
> 每个租户的限制为 15，000 个指标。 文件和证书指示器不会阻止[为Microsoft Defender 防病毒定义的排除项](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。 当指标处于被动模式时，Microsoft Defender 防病毒不支持指示器。
>
>  (IoC) 导入新指示器的格式已根据新的更新操作和警报设置进行更改。 建议下载可在导入面板底部找到的新 CSV 格式。

## <a name="related-topics"></a>相关主题

- [创建上下文 IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [使用Microsoft Defender for Endpoint指示器 API](ti-indicator.md)
- [使用合作伙伴集成解决方案](partner-applications.md)
