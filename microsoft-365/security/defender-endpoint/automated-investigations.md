---
title: 使用自动调查来调查和修正威胁
description: 了解Microsoft Defender for Endpoint中的自动调查流。
keywords: 自动化、调查、检测、Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.date: 11/24/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: eadf9fe7f6112d1219f085662686b2a930b3ff28
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789791"
---
# <a name="overview-of-automated-investigations"></a>自动调查概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

想要了解其工作原理？ 观看以下视频：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

自动化调查中的技术使用各种检查算法，并基于安全分析师使用的流程。 AIR 功能旨在检查警报并立即采取措施解决违规问题。 AIR 功能可显著减少警报量，使安全操作能够专注于更复杂的威胁和其他高价值计划。 所有修正操作（无论是挂起还是已完成）都会在 [操作中心](auto-investigation-action-center.md)进行跟踪。 在操作中心，挂起的操作 (批准或拒绝) ，并且可以根据需要撤消已完成的操作。

本文概述了 AIR，并包含指向后续步骤和其他资源的链接。

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automated-investigations-abovefoldlink)。

## <a name="how-the-automated-investigation-starts"></a>自动化调查是如何开始的

当触发警报或安全操作员启动调查时，可以启动自动调查。

<br>

****

|情况|发生的情况|
|---|---|
|触发警报|通常，自动调查在触发 [警报](review-alerts.md) 并创建 [事件](view-incidents-queue.md) 时启动。 例如，假设恶意文件驻留在设备上。 检测到该文件时，将触发警报并创建事件。 自动调查过程从设备开始。 由于其他设备上的文件相同，因此会生成其他警报，因此会将其添加到关联的事件和自动调查中。|
|手动开始调查|安全运营团队可以手动启动自动调查。 例如，假设安全操作员正在查看设备列表，并注意到设备具有高风险级别。 安全操作员可以选择列表中的设备以打开其浮出控件，然后选择 **“启动自动调查**”。|
|

## <a name="how-an-automated-investigation-expands-its-scope"></a>自动化调查如何扩展其范围

当调查正在进行时，从设备生成的任何其他警报将添加到正在进行的自动调查中，直到调查完成。 此外，如果在其他设备上看到相同的威胁，则会将这些设备添加到调查中。

如果在另一台设备中看到一个有罪的实体，自动调查过程会扩大其范围以包括该设备，并且一般安全 playbook 将从该设备开始。 如果在此扩展过程中从同一实体找到 10 台或更多设备，则该扩展操作需要审批，并且在 **“挂起操作** ”选项卡上可见。

## <a name="how-threats-are-remediated"></a>如何修正威胁

触发警报并运行自动调查时，将为所调查的每一份证据生成一个判决。 判决可以是：

- *恶意*;
- *可疑*;或
- *未找到任何威胁*。

做出判决后，自动调查可能会导致一项或多项修正行动。 修正操作的示例包括将文件发送到隔离区、停止服务、删除计划任务等。 若要了解详细信息，请参阅 [修正操作](manage-auto-investigation.md#remediation-actions)。

根据组织的 [自动化设置级别](automation-levels.md) 以及其他安全设置，修正操作可能自动发生，或者仅在安全运营团队批准后才发生。 可能影响自动修正的其他安全设置包括 [防止可能不需要的应用程序](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA) 。

所有修正操作（无论是挂起还是已完成）都会在 [操作中心](auto-investigation-action-center.md)进行跟踪。 如有必要，安全运营团队可以撤消修正操作。 若要了解详细信息，请参阅 [自动调查后的审查和批准修正操作](/microsoft-365/security/defender-endpoint/manage-auto-investigation)。

> [!TIP]
> 查看Microsoft 365 Defender门户中新的统一调查页面。 若要了解详细信息，请参阅 [ (NEW！) 统一调查页](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。

## <a name="requirements-for-air"></a>AIR 的要求

组织必须具有 Defender for Endpoint (查看[Microsoft Defender for Endpoint) 的最低要求](minimum-requirements.md)。

> [!NOTE]
> 自动调查和响应需要Microsoft Defender 防病毒在被动模式或主动模式下运行。 如果禁用或卸载Microsoft Defender 防病毒，自动调查和响应将无法正常运行。

目前，AIR 仅支持以下 OS 版本：

- Windows Server 2012 R2 (预览版) 
- Windows Server 2016 (预览) 
- Windows Server 2019
- Windows Server 2022
- Windows 10版本 1709 (OS 内部版本 16299.1085，[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更高版本
- Windows 10版本 1803 (使用 [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更高版本的 OS 内部版本 17134.704
- Windows 10版本 [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) 或更高版本
- Windows 11

## <a name="next-steps"></a>后续步骤

- [详细了解自动化级别](automation-levels.md)
- [请参阅交互式指南：使用Microsoft Defender for Endpoint调查和修正威胁](https://aka.ms/MDATP-IR-Interactive-Guide)
- [在Microsoft Defender for Endpoint中配置自动调查和修正功能](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>另请参阅

- [PUA 保护](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [自动调查和响应Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Microsoft 365 Defender 中的自动调查和响应](/microsoft-365/security/defender/m365d-autoir)
