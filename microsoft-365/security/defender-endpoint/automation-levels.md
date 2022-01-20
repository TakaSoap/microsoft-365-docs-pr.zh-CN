---
title: 自动调查和修正中的自动化级别
description: 大致了解自动化级别及其在 Microsoft Defender for Endpoint 中如何工作
keywords: 自动化， 调查， 级别， Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 10/22/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: f4baefadc2fe08b7fe909a135228278c8a696f14
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156000"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>自动调查和修正功能中的自动级别

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

可以将 Microsoft Defender for Endpoint (AIR) 功能的自动调查和修正功能配置为多个自动化级别之一。 您的自动化级别会影响是自动执行 AIR 调查之后执行修正操作，还是仅在审批后执行修正操作。

- *完全自动化* (推荐) 意味着自动对确定为恶意的项目执行修正操作。
- *半自动化* 意味着自动执行一些修正操作，但其他修正操作等待审批，然后才能执行。  (请参阅自动化级别[.) ](#levels-of-automation)
- 所有修正操作（无论是挂起还是已完成）都跟踪在操作中心 [https://security.microsoft.com](https://security.microsoft.com) () 。

> [!TIP]
> 为了获得最佳结果，我们建议在配置 AIR 时使用 [完全自动化](configure-automated-investigations-remediation.md)。 过去一年收集和分析的数据显示，使用完全自动化的客户删除的高可信度恶意软件样本比使用较低自动化级别的客户高 40%。 完全自动化可帮助释放安全操作资源，以更加关注你的策略计划。

## <a name="levels-of-automation"></a>自动化级别

下表介绍每个级别的自动化及其工作方式。

<br>

****

|自动化级别|说明|
|---|---|
|**完全 - 自动修正威胁** <br>  (也称为完全 *自动化*) |使用完全自动化，将自动执行修正操作。 可在"历史记录"选项卡上的"操作中心"中查看 [执行的所有](auto-investigation-action-center.md)**修正** 操作。如有必要，可以撤消修正操作。 <p> **_建议使用完全自动化，_* 默认情况下，对于在 2020 年 8 月 16 日或之后使用 Microsoft Defender for Endpoint 创建的租户（尚未定义任何设备组）进行选择。*|
|**Semi - 需要批准任何修正** <br>  (也称为半自动化 *)*|对于这种半自动化级别，任何 *修正操作都需要* 获得批准。 此类待定操作可在操作中心中查看和批准 [，位于](auto-investigation-action-center.md)"挂起 **"选项卡** 上。 <p> *默认情况下，对于在 2020 年 8 月 16 日之前使用 Microsoft Defender for Endpoint 创建的租户（未定义任何设备组）选择此级别的半自动化。*|
|**Semi - 需要批准核心文件夹修正** <br>  (一种 *半自动化)*|借助这种半自动化级别，需要批准对核心文件夹中的文件或可执行文件执行的任何修正操作。 核心文件夹包括操作系统目录，如Windows () 。 `\windows\*` <p> 对于位于非核心文件夹的其他非核心文件夹中的文件或可执行文件 (自动) 操作。 <p> 核心文件夹中文件或可执行文件的挂起操作可以在操作中心中查看和批准，位于"挂起 [](auto-investigation-action-center.md)**"** 选项卡上。 <p> 可以在操作中心中的"历史记录"选项卡上查看对其他文件夹中的文件或可执行 **文件采取的** 操作。 [](auto-investigation-action-center.md)|
|**Semi - 需要审批非临时文件夹修正** <br>  (一种 *半自动化)*|借助这种半自动化级别，需要批准对不在临时文件夹中的文件或可执行 *文件执行所需的* 任何修正操作。 <p> 临时文件夹可以包括以下示例： <ul><li>`\users\*\appdata\local\temp\*`</li><li>`\documents and settings\*\local settings\temp\*`</li><li>`\documents and settings\*\local settings\temporary\*`</li><li>`\windows\temp\*`</li><li>`\users\*\downloads\*`</li><li>`\program files\`</li><li>`\program files (x86)\*`</li><li>`\documents and settings\*\users\*`</li></ul> <p> 可以自动对临时文件夹中的文件或可执行文件执行修正操作。 <p> 对于不在临时文件夹中的文件或可执行文件的挂起操作，可以在操作中心中的"挂起"选项卡上查看 [](auto-investigation-action-center.md)**和** 批准。 <p> 可以在操作中心的"历史记录"选项卡上查看和批准对临时文件夹中的文件或可执行 **文件** 采取的操作 [](auto-investigation-action-center.md)。|
|**无自动响应** <br>  (也称为无 *自动化*) |如果没有自动化，则自动调查不会在组织的设备上运行。 因此，自动调查不会执行任何修正操作或挂起任何修正操作。 但是，其他威胁防护功能（如对[](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)可能不需要的应用程序的保护）可能有效，具体取决于防病毒和下一代保护功能的配置方式。 <p> ***不建议 *使用* "无** 自动化"选项，因为这样可以减少组织设备的安全状况。 [请考虑将自动化级别设置为完全自动化 (或至少半自动化 ](/microsoft-365/security/defender-endpoint/machine-groups)) 。|
|

## <a name="important-points-about-automation-levels"></a>有关自动化级别的要点

- 完全自动化已证明是可靠、高效和安全的，建议所有客户使用。 完全自动化释放关键安全资源，以便他们可以更加关注你的策略计划。

- 新租户 (包括 2020 年 8 月 16 日当天或之后创建) Microsoft Defender for Endpoint 的租户默认设置为完全自动化。

- 如果安全团队已定义具有自动化级别的设备组，则推出的新默认设置不会更改这些设置。

- 你可以保留默认自动化设置，也可以根据组织需求更改这些设置。 若要更改设置， [请设置自动化级别](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)。

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Endpoint 中配置自动调查和修正功能](configure-automated-investigations-remediation.md)
- [访问操作中心](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
