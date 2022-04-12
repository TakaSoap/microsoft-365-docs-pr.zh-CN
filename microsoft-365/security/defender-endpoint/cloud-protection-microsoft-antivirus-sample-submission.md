---
title: 云保护和示例提交Microsoft Defender 防病毒
description: 了解云提供的保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒、下一代技术、防病毒示例提交、下一代 av、机器学习、反恶意软件、安全性、Defender、云、云传递的保护
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
ms.date: 02/24/2022
ms.collection: M365-security-compliance
ms.openlocfilehash: 9192ecae72156531b0c5dccc360b2e2ea7bd343a
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789043"
---
# <a name="cloud-protection-and-sample-submission-at-microsoft-defender-antivirus"></a>云保护和示例提交Microsoft Defender 防病毒

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒使用许多智能机制来检测恶意软件。 最强大的功能之一是能够应用云的强大功能来检测恶意软件并执行快速分析。 云保护和自动示例提交与Microsoft Defender 防病毒协同工作，以帮助防范新威胁和新出现的威胁。 

如果检测到可疑或恶意文件，则会将示例发送到云服务进行分析，同时Microsoft Defender 防病毒阻止该文件。 一旦确定（快速发生）文件就会被Microsoft Defender 防病毒释放或阻止。 

本文概述了云保护和自动提交示例Microsoft Defender 防病毒。 若要了解有关云保护的详细信息，请参阅[云保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)。

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>云保护和示例提交如何协同工作

若要了解云保护与示例提交的工作原理，了解 Defender for Endpoint 如何防范威胁会很有帮助。 Microsoft 智能安全Graph监视来自大量传感器网络的威胁数据。 Microsoft 分层基于云的机器学习模型，这些模型可以根据来自客户端的信号以及智能安全Graph中庞大的传感器和数据网络来评估文件。 此方法使 Defender for Endpoint 能够阻止许多前所未见的威胁。 

下图描述了云保护和示例提交流的Microsoft Defender 防病毒：

:::image type="content" source="images/cloud-protection-flow.png" alt-text="云传递的保护流" lightbox="images/cloud-protection-flow.png":::

Microsoft Defender 防病毒和云保护使用以下方法，在首次看到时自动阻止大多数前所未有的新威胁：

1. 基于客户端的轻型机器学习模型，阻止了新的和未知的恶意软件。

2. 本地行为分析，停止基于文件和无文件的攻击。

3. 高精度防病毒，通过泛型和启发式技术检测常见恶意软件。

4. 如果在终结点上运行的Microsoft Defender 防病毒需要更多智能来验证可疑文件的意图，则提供基于云的高级保护。

   1. 如果Microsoft Defender 防病毒无法明确确定，文件元数据将发送到云保护服务。 通常在毫秒内，云保护服务可以根据元数据确定文件是否为恶意威胁。  

      - 文件元数据的云查询可能是行为、Web 标记或其他未确定明确判断的特征的结果。
      - 发送一个小的元数据有效负载，目的是做出恶意软件或不威胁的判断。 元数据不包括 PII)  (个人身份信息。 文件名等信息经过哈希处理。
      - 可以是同步的，也可以是异步的。 对于同步，在云做出判决之前，文件不会打开。 对于异步，在云保护执行分析时，文件将打开。
      - 元数据可以包括 PE 属性、静态文件属性、动态和上下文属性，以及更多 (请参阅 [发送到云保护服务) 的元数据示例](#examples-of-metadata-sent-to-the-cloud-protection-service) 。

   2. 检查元数据后，如果Microsoft Defender 防病毒云保护无法得出结论性结论，则可以请求文件示例进行进一步检查。 此请求遵循示例提交的设置配置：

      1. **自动发送安全示例** (默认) 
         - 保险箱样本被视为通常不包含 PII 数据，例如：.bat、.scr、.dll、.exe。
         - 如果文件可能包含 PII，则用户将收到允许提交文件示例的请求。
         - 此选项是Windows、macOS 和 Linux 上的默认选项。

      2. **始终提示**
         - 如果已配置，则始终会在提交文件之前提示用户同意
         - 此设置在 macOS 云保护中不可用

      3. **自动发送所有示例**
         - 如果已配置，则会自动发送所有示例
         - 如果希望示例提交包含嵌入在 Word 文档中的宏，则必须选择“自动发送所有示例”
         - 此设置在 macOS 云保护中不可用

      4. **不发送**
         - 根据文件示例分析防止“一见钟情”
         - “不发送”等效于 macOS 策略中的“已禁用”设置
         - 即使禁用了示例提交，也发送元数据进行检测

   3. 将元数据和/或文件提交到云保护后，可以使用 **示例**、 **引爆** 或 **大数据分析** 机器学习模型来做出判断。 关闭云提供的保护将仅将分析限制为客户端可通过本地机器学习模型和类似函数提供的内容。

> [!IMPORTANT]
> [ (BAFS) ](configure-block-at-first-sight-microsoft-defender-antivirus.md) 提供引爆和分析，以确定文件或进程是否安全时，一见钟情。 BAFS 可以暂时延迟文件的打开，直到做出判决。 如果禁用示例提交，则还会禁用 BAFS，并且文件分析仅限于元数据。 建议保持示例提交和 BAFS 已启用。 若要了解详细信息，请参阅 [什么是“一见钟情”？](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>云保护级别

默认情况下，Microsoft Defender 防病毒启用云保护。 尽管可以为组织配置保护级别，但我们建议你保持云保护的启用状态。 请参阅[指定云提供的Microsoft Defender 防病毒保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)。

## <a name="sample-submission-settings"></a>示例提交设置

除了配置云保护级别，还可以配置示例提交设置。 可以从多个选项中进行选择：

- **自动发送安全示例**  (默认行为) 
- **自动发送所有示例**  
- **不发送示例**  

有关使用Intune、Configuration Manager、GPO 或 PowerShell 的配置选项的信息，请参阅 [Microsoft Defender 防病毒 打开云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>发送到云保护服务的元数据示例

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="在Microsoft Defender 防病毒门户中发送到云保护的元数据示例" lightbox="images/cloud-protection-metadata-sample.png":::

下表列出了云保护发送用于分析的元数据示例：

| 类型 | 属性 |
|:---|:---|
| 计算机属性 | `OS version` <br/> `Processor` <br/> `Security settings` |
| 动态属性和上下文属性 | **处理和安装** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**行为** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| 静态文件属性 | **部分哈希和完整哈希** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**文件属性** <br/>`FileName` <br/> `FileSize` <br/><br/> **签名者信息** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>示例被视为客户数据

如果你想知道示例提交会发生什么情况，Defender for Endpoint 会将所有文件示例视为客户数据。 Microsoft 遵循组织在加入 Defender for Endpoint 时选择的地理和数据保留选项。 

此外，Defender for Endpoint 已获得多个符合性认证，表明继续遵守一组复杂的合规性控制：

- ISO 27001
- ISO 27018
- SOC I、II、III
- PCI

有关详细信息，请参阅以下资源：

- [Azure 符合性产品/服务](/azure/storage/common/storage-compliance-offerings) 
- [服务信任门户](https://servicetrust.microsoft.com)
- [Microsoft Defender for Endpoint数据存储和隐私](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>其他文件示例提交方案

还有两种情况：Defender for Endpoint 可能会请求与Microsoft Defender 防病毒云保护无关的文件示例。 下表描述了这些方案：

| 应用场景 | 说明 |
|:---|:---|
|Microsoft 365 Defender门户中的手动文件示例集合 | 将设备载入 Defender for Endpoint 时，可以为[终结点检测和响应 (EDR) ](overview-endpoint-detection-response.md)配置设置。 例如，有一个设置可以从设备启用示例集合，这很容易与本文中所述的示例提交设置混淆。 <br/><br/>EDR设置控制通过Microsoft 365 Defender门户请求时来自设备的文件示例收集，并受已建立的角色和权限的约束。 此设置可以允许或阻止终结点中的文件收集，以获取Microsoft 365 Defender门户中的深度分析等功能。 如果未配置此设置，则默认设置是启用示例集合。 <br/><br/>了解 Defender for Endpoint 配置设置，请参阅：[在 Defender for Endpoint 中载入Windows 10设备的工具和方法](configure-endpoints.md) |
| 自动调查和响应内容分析 | 当 [自动调查](automated-investigations.md) 在设备上运行时 (配置为自动运行以响应警报或手动运行) 时，可以从终结点收集标识为可疑的文件以供进一步检查。 如有必要，可在Microsoft 365 Defender门户中禁用用于自动调查的文件内容分析功能。 <br/><br/> 还可以修改文件扩展名，以添加或删除将在自动调查期间自动提交的其他文件类型的扩展名。 <br/><br/> 若要了解详细信息，请参阅 [“管理自动化文件上传](manage-automation-file-uploads.md)”。 |

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

[下一代保护概述](next-generation-protection.md)

[为Microsoft Defender 防病毒检测配置修正。](configure-remediation-microsoft-defender-antivirus.md)
