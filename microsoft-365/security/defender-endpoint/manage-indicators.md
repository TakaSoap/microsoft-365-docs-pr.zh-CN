---
title: 创建指示器
ms.reviewer: ''
description: 创建文件哈希、IP 地址、URL 或域的指示器，以定义实体的检测、防护和排除。
keywords: 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: d6ddd0cbc8a8903ded4f95fc75e4a8ffcde7c5b2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159386"
---
# <a name="create-indicators"></a>创建指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
>
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

ICS (泄露) 是每个终结点保护解决方案中的重要功能。 此功能使 SecOps 能够设置检测指标列表，并阻止 (和响应) 。

创建定义实体的检测、防护和排除的指示器。 你可以定义要采取的操作以及何时应用该操作的持续时间，以及要应用该操作的设备组的范围。

当前支持的源是 Defender for Endpoint 的云检测引擎、自动调查和修正引擎，以及终结点防护引擎 (Microsoft Defender 防病毒) 。

## <a name="cloud-detection-engine"></a>云检测引擎

Defender for Endpoint 的云检测引擎会定期扫描收集的数据并尝试匹配你设置的指示器。 当存在匹配时，将按照你为 IoC 指定的设置来采取措施。

## <a name="endpoint-prevention-engine"></a>终结点防护引擎

保护代理会遵守相同的指示器列表。 这意味着，如果 Microsoft Defender AV 是配置的主要 AV，将按照设置处理匹配的指示器。 例如，如果操作为"警报和阻止"，Microsoft Defender AV 将阻止文件执行 (并修正) 并引发相应的警报。 另一方面，如果操作设置为"允许"，Microsoft Defender AV 将不会检测也不会阻止文件运行。

## <a name="automated-investigation-and-remediation-engine"></a>自动调查和修正引擎

自动调查和修正的行为相同。 如果指示器设置为"允许"，自动调查和修正将忽略它的"错误"裁定。 如果设置为"阻止"，自动调查和修正将视为"错误"。

EnableFileHashComputation 设置在文件扫描期间计算证书和文件 IoC 的文件哈希。 它支持对哈希和证书属于受信任应用程序的 IoC 强制。 它将通过允许或阻止文件设置同时启用和禁用。 EnableFileHashComputation 通过组策略手动启用，默认情况下处于禁用状态。

当前支持的操作包括：

- 允许
- 仅警报
- 警报和阻止
- Warn

>[!NOTE]
> 如果用户打开有风险的应用，则使用警告模式将提示用户显示警告。 该提示不会阻止他们使用该应用，但你可以提供一条自定义消息和指向描述应用相应使用情况的公司页面的链接。 用户仍可以绕过警告，并如果需要继续使用该应用。 有关详细信息，请参阅管理 [Microsoft Defender for Endpoint 发现的应用](/cloud-app-security/mde-govern)。

你可以为：

- [Files](indicator-file.md)
- [IP 地址、URL/域](indicator-ip-domain.md)
- [证书](indicator-certificates.md)

> [!NOTE]
>
> 每个租户限制为 15，000 个指示器。 文件和证书指示器不会阻止为 Microsoft Defender 防病毒 定义的[排除](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)项。 当指示器处于被动模式Microsoft Defender 防病毒不支持指示器。

## <a name="public-preview-for-automated-investigation-and-remediation-engine"></a>自动调查和修正引擎的公共预览版

> [!IMPORTANT]
> 本节中 (自动调查和修正引擎的公共预览 **版) 预** 发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

在 IoC (创建新指示器) ，现在可以使用以下一个或多个操作：

- 允许 – 允许 IoC 在你的设备上运行。
- 审核 – IoC 运行时将触发警报。
- 阻止执行 - 不允许运行 IoC。
- 阻止和修正 - 不允许运行 IoC，并且修正操作将应用于 IoC。

下表确切显示了每个 IoC 类型中每个 (可用的) 操作：

| IoC 类型 | 可用操作 |
|:---|:---|
| [Files](indicator-file.md) | 允许 <br> Audit <br> 阻止和修正 |
| [IP 地址](indicator-ip-domain.md) | 允许 <br> Audit <br> 阻止执行 |
| [URL 和域](indicator-ip-domain.md) | 允许 <br> Audit <br> 阻止执行 |
| [证书](indicator-certificates.md) | 允许 <br> 阻止和修正 |

例如，最初的三个 IoC 响应操作是"允许"、"仅警报"和"警报和阻止"。 作为更新的一部分，预先存在的 IoC 的功能不会更改。 但是，已重命名指示器以匹配当前支持的响应操作：

- "仅警报"响应操作已重命名为"审核"，并启用生成警报设置。
- 使用可选生成警报设置将"警报和阻止"响应重命名为"阻止和修正"。

IoC API 架构和提前搜寻的威胁 ID 已更新，以与 IoC 响应操作重命名保持一致。 API 方案更改适用于所有 IoC 类型。

> [!Note]
> 对于文件指示器，对阻止操作发出警报是可选的。
>
> 每个租户限制为 15，000 个指示器。 文件和证书指示器不会阻止为Microsoft Defender 防病毒。 当指示器处于被动模式Microsoft Defender 防病毒不支持指示器。
>
> 根据新的更新操作和警报设置 (ICS) 新指示器的格式已更改。 我们建议下载可在导入面板底部找到的新 CSV 格式。

## <a name="related-topics"></a>相关主题

- [创建上下文 IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [使用 Microsoft Defender 终结点指示器 API](ti-indicator.md)
- [使用合作伙伴集成解决方案](partner-applications.md)
