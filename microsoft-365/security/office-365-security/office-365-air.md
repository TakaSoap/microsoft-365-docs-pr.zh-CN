---
title: Office 365 中的自动化调查和响应（空气）
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 开始使用 Office 365 中的自动调查和响应功能高级威胁防护计划2。
ms.custom: air
ms.openlocfilehash: c06874ea5d55334d9049d6c5d9d5c55a499dae06
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288470"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365 中的自动化调查和响应（空气）

[Office 365 高级威胁防护](office-365-atp.md)计划2包括功能强大的自动化调查和响应（空气）功能，可节省安全运营团队的时间和精力。 当触发某些警报时，一个或多个安全行动手册将启动，并且自动调查过程开始。 这使安全操作团队能够将重点放在高优先级的任务上，而不会失去触发警报的可见性。 

## <a name="the-overall-flow-of-air"></a>空气的整体流动

将触发警报，并启动安全行动手册，这将启动自动调查。 或者，安全分析员在使用威胁资源管理器时触发自动调查。 自动调查将运行，并且通常会确定某些修正操作。 这些操作由安全操作团队进行审阅和批准，并且调查完成。 

下表逐步介绍了空气的整体流动，具体步骤如下：

|步骤  |发生的情况  |
|---------|---------|
|1     |一个警报由 Office 事件触发，[安全行动手册](automated-investigation-response-office.md#security-playbooks)启动对选定警报的自动调查。 <br/><br/>或者，安全分析员可以在使用[威胁资源管理器](threat-explorer.md)[的同时触发自动调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。        |
|双面     |自动调查运行时，它会收集有关电子邮件和与该电子邮件相关的实体的其他数据–文件、Url 和收件人。  由于触发了新的相关警报，调查的范围可能会增加。         |
|第三章     |在自动调查期间和之后，可以查看[详细信息和结果](air-view-investigation-results.md)。 结果包括[建议的操作](air-remediation-actions.md)，可采取这些操作来响应和修正发现的任何威胁。 此外，还可以使用[行动手册日志](air-view-investigation-results.md#playbook-log)来跟踪所有调查活动。<br/><br/>如果您的组织使用的是自定义报告解决方案或第三方解决方案，则可以[使用 Office 365 管理活动 API](air-custom-reporting.md)来查看有关自动调查和威胁的信息。         |
|4     |您的安全操作团队将检查[调查结果和建议](air-view-investigation-results.md)，并[批准修正操作](air-remediation-actions.md#approve-or-reject-pending-actions)。 在 Office 365 中，不会自动执行任何操作。 仅在组织的安全团队进行审批时才采取更正措施。         |

在自动调查过程期间和之后，安全团队可以执行以下操作：

- [查看与调查相关的警报的详细信息](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [查看调查的结果详细信息](air-view-investigation-results.md#view-details-of-an-investigation)
- [查看和批准作为调查结果的操作](air-remediation-actions.md#approve-or-reject-pending-actions)

若要了解详细信息，请参阅[AIR 的工作原理](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。

## <a name="how-to-get-air"></a>如何获取空中

Office 365 AIR 包含在以下订阅中：

- Microsoft 365 E5
- Office 365 E5
- Microsoft 威胁防护
- Office 365 高级威胁防护（计划 2）

如果你没有这些订阅，请[启动免费试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。

若要了解有关功能可用性的详细信息，请访问[跨高级威胁防护（ATP）计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-permissions-to-use-air-capabilities"></a>使用空中功能所需的权限

通过某些角色（如下表中所述的角色）授予权限： 

|任务 |需要 #a0 个角色 |
|--|--|
|设置空中功能 |以下角色之一： <br/>- **全局管理员**<br/>- **安全管理员** <br/>可以在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中或在[Office 365 安全 & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配这些角色。 |
|批准或拒绝建议的操作|在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中或在[Office 365 安全 & 合规中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配的以下角色之一：<br/>- **全局管理员** <br/>- **安全管理员**<br/>- **安全读者** <br/>--- 和 ---<br/>- **搜索和清除**（此角色仅在[Office 365 安全 & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配。 您可能需要在其中创建新的角色组，并将搜索和清除角色添加到该新角色组。

## <a name="related-articles"></a>相关文章

- [Microsoft 威胁防护中的自动调查和响应](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Microsoft Defender 高级威胁防护中的自动化调查和修正](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)