---
title: 云传递的保护 Microsoft Defender 防病毒示例提交
description: 了解云提供的保护和Microsoft Defender 防病毒
keywords: Microsoft Defender 防病毒， 下一代技术， 防病毒示例提交， 下一代 av， 机器学习， 反恶意软件， 安全性， defender， 云， 云保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: jweston-1
ms.author: v-jweston
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 07/22/2021
ms.openlocfilehash: 347d9a6b5de1d9045baf8d4a0778788a18514600bfc6f56652951e4ad420f1bb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53834226"
---
# <a name="cloud-delivered-protection-antivirus-sample-submission"></a>云提供的保护防病毒示例提交

Microsoft Defender for Endpoint 防病毒 (Defender for Endpoint 防病毒) 使用许多智能机制来检测恶意软件。 最强大的功能之一是能够应用云的强大功能来检测恶意软件。 Defender for Endpoint 防病毒 云保护与终结点上的 Defender for Endpoint 防病毒一起做出决策，并保护终结点免受新出现的威胁。

## <a name="microsoft-defender-for-endpoint-antivirus-cloud-protection-overview"></a>Microsoft Defender for Endpoint 防病毒云保护概述

默认情况下，在 Defender for Endpoint 防病毒中启用云保护。 建议客户不要禁用 Defender 终结点防病毒中的云保护。  启用云保护后，可以选择配置 Defender for Endpoint 防病毒将向云环境提供哪些信息 (包括示例提交) 。 当无法基于其他特征做出高可信度决定时，启用云保护非常有用。
配置示例提交将引发有关其工作方式的问题;例如，数据的存储和使用方式。 提出最多问题的三个云保护示例提交选项为：

- "自动发送安全示例" (默认行为) 
- "自动发送所有示例"。  
- "请勿发送示例。"  

有关使用 Intune、Configuration Manager、GPO 或 PowerShell 的配置选项的信息，请参阅在 Microsoft Defender 防病毒[中启用云保护](/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。  

## <a name="customer-data-cloud-protection-and-sample-submission"></a>客户数据、云保护和示例提交

当载入 Defender for Endpoint 时，Defender for Endpoint 会处理所有文件示例作为客户数据，同时考虑客户选择的地理位置和数据保留选项。 地理位置和数据保留选项如下所述 [：Microsoft Defender for Endpoint 数据存储和隐私](/security/defender-endpoint/data-storage-privacy#data-storage-location)。
该产品已接收多个合规性认证，表明继续遵守一组复杂的合规性控制措施：

- ISO 27001
- ISO 27018
- SOC I、II、III
- 和 PCI

[Azure 合规性产品/](/azure/compliance/#compliance-offerings) 服务提供了有关这些认证详细信息。 Microsoft Defender for Endpoint 的所有认证项目可在每个关联的 Azure[](https://servicetrust.microsoft.com/)认证报告中的 Microsoft 服务信任门户上找到。

## <a name="cloud-protection-mechanisms"></a>云保护机制

Microsoft Intelligent Security Graph监视来自大量传感器网络的威胁数据。 我们分层构建基于云的机器学习模型，这些模型可以基于来自客户端的信号以及 Intelligent Security Graph 中的传感器和数据网络。 此模型使 Defender for Endpoint 能够阻止许多之前未看到的威胁。

Defender for Endpoint 防病毒和云保护使用以下方法自动阻止大多数首次看到时从未看到过的新威胁：

1. 轻型基于客户端的机器学习模型，可阻止新的和未知的恶意软件。

2. 本地行为分析，停止基于文件和无文件的攻击。

3. 高分辨率防病毒，通过通用和启发式技术检测常见恶意软件。

4. 当终结点上运行的 Defender for Endpoint 防病毒需要更智能来验证可疑文件的意图时，会提供基于云的高级保护。

   1. 如果 Microsoft Defender for Endpoint 防病毒无法作出明确决定，文件元数据将发送到云保护服务。 通常，云保护服务可以在数毫秒内确定文件是安全文件还是恶意文件。  
      - 文件元数据的云查询可能是行为、Web 标记或其他未确定明确裁定的特征的结果。
      - 发送小型元数据有效负载，目的是达到干净与恶意软件裁定的目标
      - 元数据可以包括 PE 属性、静态文件属性、动态和上下文属性，以及图 1 (中) 。
      - 不包括个人身份信息 (个人身份) 。 对文件名等信息进行哈希处理
      - 可以是同步的，也可以异步的。 对于同步，在云呈现裁定之前，文件不会打开。 对于异步，文件将在云执行其分析时打开。

   2. 检查元数据后，如果 Defender for Endpoint 防病毒云保护无法做出结论，它可以请求文件示例以进一步检查。 此请求遵守示例提交的设置配置：

      1. **自动发送安全示例** (默认) 
         - 保险箱被视为通常不包含 PII 数据的示例，例如：.bat、.scr、.dll、.exe。
         - 如果文件可能包含 PII，用户将收到允许提交文件示例的请求。
         - 这是在 Windows macOS 和 Linux 上的默认设置。

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

   3. 将元数据和/或文件提交到 Defender for Endpoint 云后，可以使用示例、触发或大数据分析机器学习模型来裁定。  此模型如图 3 所示。 关闭云保护将仅分析客户端通过本地机器学习模型和类似功能提供的功能。

_图 1 - 发送到 Microsoft Defender 云保护的元数据示例_

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="图 1.发送到 Microsoft Defender 云保护的元数据示例":::

_图 2.云提供的保护流_

:::image type="content" source="images/cloud-protection-flow.png" alt-text="图 2.云提供的保护流":::

_图 3.云提供的保护和分层机器学习_

:::image type="content" source="images/cloud-protection-detection-layered-machine-learning.png" lightbox="images/cloud-protection-detection-layered-machine-learning.png" alt-text="图 3.云提供的保护和分层机器学习":::

> [!Note]
>
> 你可能还听到短语"在 BAFS (时阻止) "。 BAFS 指的是云可以提供的更广泛的分析，包括触发等内容，以提供更准确的结论。 这还包括延迟打开受云保护的文件，直到做出裁定。 如果禁用"示例提交"，将禁用 BAFS，并且无法执行更广泛的分析，并且仅限于分析文件元数据。

## <a name="cloud-delivered-protection-levels"></a>云提供的保护级别

恶意软件检测要求在提供尽可能强大的保护的同时最大限度地减少误报数之间实现平衡。 不同的环境可能具有保护容忍度与误报风险。 云提供的保护级别允许客户定义适用于特定环境的容限级别。 启用云保护时，会自动配置保护级别以提供强检测，而不会增加检测合法文件的风险。 如果要配置其他保护级别，[请参阅指定云](/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)保护级别的Microsoft Defender 防病毒。  

> [!Note]
>
> 更改保护级别可能会导致更高级别的误报，更改前应仔细评估。

## <a name="other-file-sample-submission-scenarios"></a>其他文件示例提交方案

在另外两种方案中，Defender for Endpoint 可能会请求与上述云保护设置不相关的文件示例。  

### <a name="manual-file-sample-collection-by-security-admin-from-defender-for-endpoint-management-portal"></a>安全管理员从 Defender for Endpoint Management Portal 手动收集文件示例

将设备载入到适用于终结点的 Microsoft Defender EDR有一个设置可启用设备中的示例集合，这可能会与上面讨论的设置混淆。 当通过 Defender for Endpoint 管理门户请求时，此设置控制设备中的文件示例集合;它受已建立的角色和权限限制。 此设置可以允许或阻止终结点中的文件收集，以使用 Defender for Endpoint 门户中的深入分析等功能。 如果未配置此设置，则默认为启用示例集合。

[适用于终结点配置的其他 Defender 设置](/configure-endpoints#additional-defender-for-endpoint-configuration-settings)

### <a name="automated-investigation-and-response-content-analysis"></a>自动调查和响应内容分析

当自动调查在设备上运行时 (当配置为自动运行以响应警报或手动运行) 时，可以从终结点收集标识为可疑的文件，以进一步检查。 可以在 Defender for Endpoint 门户中禁用自动调查的文件内容分析功能。 还可以修改文件扩展名，以添加或删除将在自动调查期间自动提交的其他文件类型的扩展名。

[管理自动化文件上载](/manage-automation-file-uploads)
