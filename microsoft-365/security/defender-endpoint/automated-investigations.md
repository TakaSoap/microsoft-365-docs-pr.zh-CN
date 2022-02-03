---
title: 使用自动调查调查和修正威胁
description: 了解 Microsoft Defender for Endpoint 中的自动调查流程。
keywords: 自动化， 调查， 检测， Microsoft Defender for Endpoint
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: 547356fadc05c2359b4c6cd639bc22110bf8be93
ms.sourcegitcommit: babc2dad1c0e08a9237dbe4956ffd21c0214db83
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62346274"
---
# <a name="overview-of-automated-investigations"></a>自动调查概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

想要了解它的工作原理吗？ 观看以下视频：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

自动调查中的技术使用各种检查算法，并且基于安全分析师使用的过程。 AIR 功能旨在检查警报并立即采取措施来解决违规问题。 AIR 功能可显著减少警报量，使安全操作专注于更复杂的威胁和其他高价值计划。 所有修正操作（无论是挂起还是已完成）都跟踪在操作 [中心中](auto-investigation-action-center.md)。 在操作中心中，挂起的操作 (或拒绝) ，如果需要，可以撤消已完成的操作。

本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automated-investigations-abovefoldlink)。

## <a name="how-the-automated-investigation-starts"></a>自动调查的启动方式

当触发警报或安全操作员启动调查时，可以启动自动调查。

<br>

****

|情况|发生的情况|
|---|---|
|触发警报|通常，自动调查在触发[警报并](review-alerts.md)[创建事件时](view-incidents-queue.md)启动。 例如，假设恶意文件驻留在设备上。 检测到该文件时，将触发警报并创建事件。 自动调查过程在设备上开始。 由于其他设备上生成了相同的文件，因此其他警报会添加到关联事件和自动调查。|
|手动启动调查|安全运营团队可以手动启动自动调查。 例如，假设安全操作员正在查看设备列表，并注意到设备具有高风险级别。 安全操作员可以选择列表中的设备以打开其飞出内容，然后选择"启动 **自动调查"**。|
|

## <a name="how-an-automated-investigation-expands-its-scope"></a>自动调查如何扩展其范围

当调查正在运行时，从设备生成的其他任何警报将添加到正在进行的自动调查，直到完成该调查。 此外，如果在其他设备上看到相同的威胁，则这些设备将添加到调查。

如果在另一台设备上看到一个已注册实体，则自动调查过程会扩展其范围以包括该设备，并且通用安全手册将在该设备上启动。 如果在此扩展过程中从同一实体找到 10 台或更多的设备，则扩展操作需要审批，并且显示在"待定操作 **"选项卡上** 。

## <a name="how-threats-are-remediated"></a>如何修正威胁

触发警报并运行自动调查时，将针对调查的每个证据生成裁定。 裁定可以是：

- *恶意*;
- *可疑*;或
- *未找到威胁*。

在做出裁定后，自动调查可能会导致一个或多个修正操作。 修正操作的示例包括将文件发送到隔离区、停止服务、删除计划任务等。 若要了解更多信息，请参阅 [修正操作](manage-auto-investigation.md#remediation-actions)。

根据为 [组织](automation-levels.md) 设置的自动化级别以及其他安全设置，修正操作可以自动执行，或仅在安全运营团队批准后执行。 可影响自动修正的其他安全设置包括 [保护来自](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) PUA (可能不需要) 。

所有修正操作（无论是挂起还是已完成）都跟踪在操作 [中心中](auto-investigation-action-center.md)。 如有必要，安全运营团队可以撤消修正操作。 若要了解更多信息，请参阅 [在自动调查后审阅并批准修正操作](/microsoft-365/security/defender-endpoint/manage-auto-investigation)。

> [!TIP]
> 查看企业门户中新的统一调查Microsoft 365 Defender页面。 若要了解更多信息，请参阅 ([ "新建！) 统一调查"页](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。

## <a name="requirements-for-air"></a>AIR 的要求

你的组织必须具有适用于终结点的 Defender (请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。

目前，AIR 仅支持以下操作系统版本：

- Windows Server 2012 R2 (Preview) 
- Windows Server 2016 (预览) 
- Windows Server 2019
- Windows Server 2022
- Windows 10版本 1709 (版本 16299.1085[（包含 KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更高版本）
- Windows 10版本 1803 (OS 内部版本 17134.704[，包含 KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更高版本
- Windows 10版本 [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) 或更高版本
- Windows 11

## <a name="next-steps"></a>后续步骤

- [详细了解自动化级别](automation-levels.md)
- [请参阅交互式指南：使用 Microsoft Defender for Endpoint 调查和修正威胁](https://aka.ms/MDATP-IR-Interactive-Guide)
- [在 Microsoft Defender for Endpoint 中配置自动调查和修正功能](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>另请参阅

- [PUA 保护](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Microsoft 365 Defender 中的自动调查和响应](/microsoft-365/security/defender/m365d-autoir)
