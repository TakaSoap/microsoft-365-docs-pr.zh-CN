---
title: Microsoft 365 Defender 中的自动调查和响应
description: 在 Microsoft 365 Defender 中大致了解自动调查和响应功能（也称为自我修复）
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930326"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。
>

## <a name="how-automated-investigation-and-self-healing-works"></a>自动调查和自我修复的工作原理

在触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 Microsoft 365 Defender 中的自动调查和响应功能以及自我修复可提供帮助。

观看以下视频，了解自我修复的工作原理：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，使用自我修复功能自动调查和响应适用于你的设备、电子邮件&内容和标识。
 
> [!TIP]
> 本文介绍自动调查和响应的工作原理。 若要配置这些功能，请参阅在 [Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中配置自动调查和响应功能。

## <a name="your-own-virtual-analyst"></a>你自己的虚拟分析师

想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。 这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。 如果此方案看起来像科学虚构，则不是！ 此类虚拟分析师是 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。

通过自动调查和响应，安全运营团队可以显著提高组织处理安全警报和事件的能力。 通过自动调查和响应，你可以降低调查和修正活动的成本，并利用威胁防护套件的最大功能。 自动调查和响应可帮助你的安全运营团队：

1. 确定是否需要针对威胁执行操作；
2. 执行（或建议执行）任何必要的修正操作；
3. 确定应进行哪些其他调查；以及
4. 根据需要对其他警报重复此过程。

## <a name="the-automated-investigation-process"></a>自动调查流程

**警报** > **事件** > **自动调查** > **裁定** > **修正操作**

触发的警报将创建一个事件，可以启动自动调查。 该调查可能会导致执行一项或多项修正操作。 在 Microsoft 365 Defender 中，每个自动调查将跨 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的信号关联起来，如下表所示： 

|实体 |威胁防护服务  |
|---------|---------|
|设备（也称为终结点）     |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件内容（邮箱中的文件和邮件）     |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

每项调查都会 (*调查* 的每个证据) 恶意、可疑或无威胁"裁定。 根据威胁的类型和结果裁定，修正操作会自动执行，或在组织的安全运营团队批准后执行。 "[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。 

> [!NOTE]
> 不是每个警报都会触发自动调查，而不是每个调查都会触发自动修正操作;这一切都取决于如何为组织配置自动调查和响应。 请参阅 [在 Microsoft 365 Defender 中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。


## <a name="next-steps"></a>后续步骤

- [请参阅 Microsoft 365 Defender 中自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [为组织配置自动调查和响应](mtp-configure-auto-investigation-response.md)
- [详细了解操作中心](mtp-action-center.md)
