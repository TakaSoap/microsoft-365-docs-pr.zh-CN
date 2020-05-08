---
title: Microsoft 威胁防护中的自动化调查和响应功能
description: 简要了解 Microsoft 威胁防护中的自动调查和响应功能
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
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
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166157"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动化调查和响应（空气）功能

**适用于：**
- Microsoft 威胁防护

随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 Microsoft 威胁防护中的自动化调查和响应（空中）功能可能会有所帮助。 AIR 就像是在安全运营中心中拥有虚拟分析员。

## <a name="your-virtual-analyst"></a>你的虚拟分析师

想象一下，你的第 1 层/第 2 层安全运营团队中有一名虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。 这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。 如果此方案听起来像科学 fiction，则不是！ 这种虚拟分析师是 Microsoft 威胁防护套件的一部分，它的名称是“自动调查和响应”** (AIR)。

AIR 使你的安全运营团队能够极大地提高组织处理安全警报和事件的能力。 借助 AIR，可以减少处理调查和修正活动的成本，并充分利用威胁防护套件。 AIR 通过以下方式为安全运营团队提供帮助：

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

每次调查都会为调查的每个证据生成 verdicts （发现*恶意*、*可疑*或*没有威胁*）。 根据威胁的类型和得到的结论，将自动执行更正操作，或在组织的安全操作团队批准时执行。 "[操作中心](mtp-action-center.md)中列出了待处理和已完成的操作。

> [!TIP]
> 如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！ 请参阅[如何在 Microsoft 威胁防护中报告误报/负面的自动调查和响应（空中）功能](mtp-autoir-report-false-positives-negatives.md)。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，自动调查将扩大其范围，以包括该实体，并且将运行常规安全性 Playbook。 

> [!NOTE]
> 并非每个警报都会触发自动调查，也不是每个调查都会导致自动修正操作；这一切都取决于你的组织配置 AIR 的方式。 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的 AIR 要求

| | |
|--|--|
|订阅要求 |以下各项之一： <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 安全<br/>-Microsoft 365 A5 安全性<br/>-Office 365 E5 plus 企业移动性 + 安全性 E5，外加 Windows E5<br/><br/>请参阅[Microsoft 威胁防护许可要求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|网络要求 |- 已启用 [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)<br/>- 已配置 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS)<br/>- [与 Azure ATP 集成的 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 计算机要求 |-Windows 10 版本1709或更高版本（请参阅[windows 10 版本信息](https://docs.microsoft.com/windows/release-information/)）已配置以下威胁 protection services：<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|对电子邮件内容和 Office 文件的保护 |配置了[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|权限 |-若要配置 AIR，必须在任何 Azure Active Directory （[https://portal.azure.com](https://portal.azure.com)）或 Microsoft 365 管理中心中分配全局管理员角色或安全管理员角色（[https://admin.microsoft.com](https://admin.microsoft.com)）。<br/><br/>- 若要使用 AIR 功能，请参阅[操作中心任务所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="next-steps"></a>后续步骤

- [批准或拒绝与自动调查和响应相关的操作](mtp-autoir-actions.md)
- [详细了解操作中心](mtp-action-center.md)
