---
title: Microsoft 威胁防护中的自动调查和响应
description: 了解 Microsoft 威胁防护中的自动化调查和响应功能（也称为自我修复）概述
keywords: 自动化、调查、警报、触发、操作、修正、自我修复
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: f2a0a439996f13cea3823815aceb9dd1c235e2f2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962661"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动调查和响应

**适用于：**
- Microsoft 威胁防护

随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 Microsoft 威胁防护中的自动化调查和响应功能（通过自我修复）可能会有所帮助。

观看以下视频，了解自我修复的工作原理：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 威胁防护中，通过自愈功能进行的自动化调查和响应可在您的设备、电子邮件 & 内容和标识之间工作。 Microsoft 威胁防护将功能汇集在一起： 
- [Microsoft Defender 高级威胁防护中的自动化调查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Office 365 高级威胁防护中的自动化调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Azure 高级威胁检测](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
本文介绍了自动化调查和响应的工作方式。 若要配置这些功能，请参阅 [在 Microsoft 威胁防护中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。

## <a name="your-virtual-analyst"></a>你的虚拟分析师

想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。 这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。 如果此方案听起来像科学 fiction，则不是！ 此类虚拟分析员是你的 Microsoft 威胁防护套件的一部分，其名称是 *自动调查和响应*。

自动化调查和响应使安全操作团队能够显著提高组织处理安全警报和事件的能力。 通过自动调查和响应，可以降低处理调查和补救活动的成本，并充分利用威胁防护套件。 自动调查和响应通过以下方式帮助您的安全运营团队：

1. 确定是否需要针对威胁执行操作；
2. 执行（或建议执行）任何必要的修正操作；
3. 确定应进行哪些其他调查；以及
4. 根据需要对其他警报重复此过程。

## <a name="the-automated-investigation-process"></a>自动调查流程

**警报** > **事件** > **自动调查** > **裁定** > **修正操作**

触发的警报创建一个事件，该事件可以开始进行自动调查。 该调查可能会导致执行一项或多项修正操作。 在 Microsoft 威胁防护中，每次自动调查都会将 Azure 高级威胁防护 (Azure ATP)、Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 和 Office 365 高级威胁防护 (Office 365 ATP) 之间的信号相关联，如下表所示： 

|实体 |威胁防护服务  |
|---------|---------|
|设备（也称为终结点）     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件内容（邮箱中的文件和邮件）     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

每个调查都会为调查) 的每个证据生成 verdicts (*恶意*、 *可疑*或不会 *发现的威胁* 。 根据威胁的类型和得到的结论，将自动执行更正操作，或在组织的安全操作团队批准时执行。 "[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。 

> [!NOTE]
> 并不是每个警报都会触发自动调查，并且并非每个调查都会导致自动修正操作;这一切都取决于为您的组织配置自动调查和响应的方式。 请参阅 [在 Microsoft 威胁防护中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)。


## <a name="next-steps"></a>后续步骤

- [请参阅 Microsoft 威胁防护中的自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [为你的组织配置自动调查和响应](mtp-configure-auto-investigation-response.md)
- [详细了解操作中心](mtp-action-center.md)
