---
title: 云保护和云中的示例Microsoft Defender 防病毒
description: 了解云提供的保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒， 下一代技术， 防病毒示例提交， 下一代 av， 机器学习， 反恶意软件， 安全性， defender， 云， 云保护
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 3ffd18a0b2a0e81f2f3a425434f5e786d8dc598d
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171544"
---
# <a name="cloud-protection-and-sample-submission-in-microsoft-defender-antivirus"></a>云保护和云中的示例Microsoft Defender 防病毒

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

Microsoft Defender 防病毒许多智能机制来检测恶意软件。 最强大的功能之一是应用云的强大功能来检测恶意软件和执行快速分析。 云保护和自动提交示例与 Microsoft Defender 防病毒一起帮助抵御新的和新出现的威胁。 

如果检测到可疑或恶意文件，将示例发送到云服务进行分析，Microsoft Defender 防病毒阻止该文件。 一旦确定（这很快就会发生）就会被用户释放或Microsoft Defender 防病毒。 

本文概述了云保护以及云解决方案中的自动Microsoft Defender 防病毒。 若要了解有关云保护的更多信息，请参阅云[保护和Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>云保护和示例提交如何协同工作

若要了解云保护如何与示例提交协同工作，了解 Defender for Endpoint 如何抵御威胁可能会很有帮助。 Microsoft Intelligent Security Graph监视来自大量传感器网络的威胁数据。 Microsoft 层基于云的机器学习模型，可基于来自客户端的信号以及智能安全中心中广泛的传感器和数据网络评估Graph。 此方法使 Defender for Endpoint 能够阻止许多之前未发现的威胁。 

下图描述了云保护流和示例提交Microsoft Defender 防病毒：

:::image type="content" source="images/cloud-protection-flow.png" alt-text="云提供的保护流":::

Microsoft Defender 防病毒和云保护通过以下方法自动阻止大多数首次看到时从未看到过的新威胁：

1. 轻型基于客户端的机器学习模型，可阻止新的和未知的恶意软件。

2. 本地行为分析，停止基于文件和无文件的攻击。

3. 高分辨率防病毒，通过通用和启发式技术检测常见恶意软件。

4. 当在终结点上运行的 Microsoft Defender 防病毒需要更智能来验证可疑文件的意图时，会提供基于云的高级保护。

   1. 如果无法Microsoft Defender 防病毒，文件元数据将发送到云保护服务。 通常，在几毫秒内，云保护服务可以基于元数据确定文件是否是恶意文件。  

      - 文件元数据的云查询可能是行为、Web 标记或其他未确定明确裁定的特征的结果。
      - 发送小型元数据有效负载，目标是达到恶意软件裁定或不是威胁。 元数据不包括个人身份信息 (PII) 。 诸如文件名这样的信息是哈希值。
      - 可以是同步的，也可以异步的。 对于同步，在云呈现裁定之前，文件不会打开。 对于异步，文件将在云保护执行其分析时打开。
      - 元数据可以包括 PE 属性、静态文件属性、动态和上下文属性 (请参阅发送到云保护服务应用程序的[元数据) 。](#examples-of-metadata-sent-to-the-cloud-protection-service)

   2. 在检查元数据后，如果Microsoft Defender 防病毒无法做出结论，它可以请求文件示例以进一步检查。 此请求遵守示例提交的设置配置：

      1. **自动发送安全示例** (默认) 
         - 保险箱被视为通常不包含 PII 数据的示例，例如：.bat、.scr、.dll、.exe。
         - 如果文件可能包含 PII，用户将收到允许提交文件示例的请求。
         - 此选项是 Windows macOS 和 Linux 上的默认选项。

      2. **始终提示**
         - 如果配置，则始终在提交文件之前提示用户征得同意
         - 此设置在 macOS 云保护中不可用

      3. **自动发送所有示例**
         - 如果配置，将自动发送所有示例
         - 如果要将示例提交包括在 Word 文档内嵌入的宏，则必须选择"自动发送所有示例"
         - 此设置在 macOS 云保护上不可用

      4. **不发送**
         - 基于文件示例分析阻止"首次看到时阻止"
         - "不发送"等同于 macOS 策略中的"已禁用"设置
         - 即使示例提交已禁用，也发送元数据进行检测

   3. 将元数据和/或文件提交到云保护后，可以使用示例、爆炸或大数据分析机器学习模型来裁定。  关闭云提供的保护将仅分析客户端通过本地机器学习模型和类似功能提供的功能。

> [!IMPORTANT]
> [BAFS (首次 ](configure-block-at-first-sight-microsoft-defender-antivirus.md) 看到时) 触发和分析，以确定文件或进程是否安全。 BAFS 可能会暂时延迟文件打开，直到到达裁定。 如果禁用示例提交，BAFS 也将禁用，并且文件分析仅限于元数据。 我们建议保持启用示例提交和 BAFS。 若要了解更多信息， [请参阅什么是"首次看到时阻止"？](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>云保护级别

默认情况下，云保护在 Microsoft Defender 防病毒。 我们建议你保持启用云保护，尽管你可以为组织配置保护级别。 请参阅[为用户指定云提供的Microsoft Defender 防病毒。](specify-cloud-protection-level-microsoft-defender-antivirus.md)

## <a name="sample-submission-settings"></a>示例提交设置

除了配置云保护级别之外，还可以配置示例提交设置。 您可以从多个选项中进行选择：

- **自动发送安全 (**  默认行为) 
- **自动发送所有示例**  
- **不发送示例**  

有关使用 Intune、Configuration Manager、GPO 或 PowerShell 的配置选项的信息，请参阅在 Microsoft Defender 防病毒[中启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>发送到云保护服务的元数据示例

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="描述发送到云保护的元数据示例的图像Microsoft Defender 防病毒":::

下表列出了云保护发送进行分析的元数据示例：

| 类型 | 属性 |
|:---|:---|
| 计算机属性 | `OS version` <br/> `Processor` <br/> `Security settings` |
| 动态和上下文属性 | **过程和安装** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**行为** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| 静态文件属性 | **部分哈希和完整哈希** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**文件属性** <br/>`FileName` <br/> `FileSize` <br/><br/> **签名者信息** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>示例被视为客户数据

如果你想知道示例提交会发生什么情况，Defender for Endpoint 会处理所有文件示例作为客户数据。 Microsoft 在载入 Defender for Endpoint 时，将同时遵守组织选择的地理位置和数据保留选项。 

此外，Defender for Endpoint 还收到了多个合规性认证，表明继续遵守一组复杂的合规性控制措施：

- ISO 27001
- ISO 27018
- SOC I、II、III
- 和 PCI

有关更多信息，请参阅以下资源：

- [Azure 合规性产品/服务](/azure/storage/common/storage-compliance-offerings) 
- [服务信任门户](https://servicetrust.microsoft.com)
- [Microsoft Defender for Endpoint 数据存储和隐私](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>其他文件示例提交方案

在另外两种方案中，Defender for Endpoint 可能会请求与云保护不相关的文件Microsoft Defender 防病毒。 下表介绍了这些方案：

| 应用场景 | Description |
|:---|:---|
|Microsoft 365 Defender 门户中的手动文件示例集合 | 将设备载入到 Defender for Endpoint 时，你可以为终结点检测和响应配置[ (EDR) 。 ](overview-endpoint-detection-response.md) 例如，有一个从设备启用示例集合的设置，这很容易与本文中介绍的示例提交设置混淆。 <br/><br/>该EDR设置控制通过 Microsoft 365 Defender 门户请求时来自设备的文件示例集合，并受已建立的角色和权限限制。 此设置可以允许或阻止终结点中的文件集合，以使用门户中的深入分析Microsoft 365 Defender功能。 如果未配置此设置，则默认为启用示例集合。 <br/><br/>了解适用于终结点的 Defender 配置设置，请参阅：在 Defender for Endpoint 中为 Windows 10[设备载入工具和方法](configure-endpoints.md) |
| 自动调查和响应内容分析 | 当[](automated-investigations.md)自动调查在设备上运行时 (当配置为自动运行以响应警报或手动运行) 时，可以从终结点收集标识为可疑的文件，以进一步检查。 如有必要，可在自动调查门户中禁用用于自动调查Microsoft 365 Defender功能。 <br/><br/> 还可以修改文件扩展名，以添加或删除将在自动调查期间自动提交的其他文件类型的扩展名。 <br/><br/> 若要了解更多信息，请参阅 [管理自动化文件上载](manage-automation-file-uploads.md)。 |

## <a name="see-also"></a>另请参阅

[下一代保护概述](next-generation-protection.md)
