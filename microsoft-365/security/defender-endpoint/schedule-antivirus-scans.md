---
title: 使用扫描计划定期快速和完全Microsoft Defender 防病毒
description: 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 常规
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 91e3acee5fb3ab2542c2beed4681f07959e9fe05
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167990"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

除了始终打开、实时保护和按需防病毒扫描之外，还可以[](run-scan-microsoft-defender-antivirus.md)设置定期计划防病毒扫描。 可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后或终结点未使用时发生[](manage-protection-updates-microsoft-defender-antivirus.md)。 如果需要，还可以设置特殊扫描以完成修正操作。

## <a name="what-do-you-want-to-do"></a>要执行什么操作？

- [了解快速扫描、完整扫描和自定义扫描](#quick-scan-full-scan-and-custom-scan)
- [使用组策略计划防病毒扫描](schedule-antivirus-scans-group-policy.md)
- [使用Windows PowerShell计划防病毒扫描](schedule-antivirus-scans-powershell.md)
- [使用 Windows Management Instrumentation 安排防病毒扫描](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- 默认情况下，Microsoft Defender 防病毒扫描前 15 分钟检查更新。 你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。

- 如果在计划的完全扫描期间设备已拔下并按电池运行，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。 Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。

## <a name="quick-scan-full-scan-and-custom-scan"></a>快速扫描、完全扫描和自定义扫描

设置计划扫描时，可以指定扫描应为完全扫描还是快速扫描。 在大多数情况下，建议使用快速扫描。

<br>

****

|快速扫描|完全扫描|自定义扫描|
|---|---|---|
| (推荐) 快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。 <p> 与始终启用实时保护相结合，可在打开和关闭文件时以及用户导航到文件夹时查看文件，快速扫描可帮助提供强大的保护，防止因系统和内核级别恶意软件而启动的恶意软件。 <p> 在大多数情况下，快速扫描已足够，是计划扫描的推荐选项。|完整扫描首先运行快速扫描，然后继续针对所有已装载的固定磁盘和可移动/网络驱动器进行连续文件扫描 (如果完全扫描配置为) 。 <p> 完整扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据的数量和类型。 <p> 完全扫描完成后，新的安全智能可用，然后需要新的扫描以确保新安全智能不会检测到任何其他威胁。 <p> 由于完全扫描所涉及的时间和资源，Microsoft 通常不建议安排完全扫描。|自定义扫描是在指定的文件和文件夹上运行的快速扫描。 例如，你可以选择扫描 USB 驱动器或设备本地驱动器上的特定文件夹。|
|

> [!NOTE]
> 默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。

## <a name="how-do-i-know-which-scan-type-to-choose"></a>我如何知道要选择哪个扫描类型？

使用下表选择扫描类型。

<br>

****

|应用场景|推荐的扫描类型|
|---|---|
|想要设置定期计划扫描|快速扫描 <p> 快速扫描检查设备上的过程、内存、配置文件和特定位置。 与 [始终开启的](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护相结合，快速扫描有助于为以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。 实时保护在打开和关闭文件时以及用户导航到文件夹时检查文件。|
|在单个设备上检测到恶意软件等威胁|快速扫描 <p> 在大多数情况下，快速扫描将捕获并清理检测到的恶意软件。|
|想要运行 [按需扫描](run-scan-microsoft-defender-antivirus.md)|快速扫描|
|你想要确保便携式设备（如 USB 驱动器）不包含恶意软件|自定义扫描 <p> 自定义扫描使你能够选择特定位置、文件夹或文件，并运行快速扫描。|
|

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>关于快速和完整扫描，我还需要了解哪些信息？

- 恶意文件可以存储在快速扫描中未包含的位置。 但是，始终启用实时保护会检查所有打开和关闭的文件，以及用户访问的文件夹中的任何文件。 实时保护和快速扫描相结合有助于提供强大的恶意软件防护。

- 具有云保护的 [On-access Protection](cloud-protection-microsoft-defender-antivirus.md) 有助于确保使用最新的安全智能和云机器学习模型扫描系统上访问的所有文件。

- 当实时保护检测到恶意软件并且最初未确定受影响文件的范围时，Microsoft Defender 防病毒在修正过程中启动完全扫描。

- 完全扫描可以检测其他扫描未检测到的恶意文件，例如快速扫描。 但是，完整扫描可能需要一段时间，并使用有价值的系统资源来完成。

- 如果设备长时间处于脱机状态，则完整扫描可能需要更长时间才能完成。
