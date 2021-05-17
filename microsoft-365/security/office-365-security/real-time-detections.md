---
title: Microsoft Defender for Office 365 中的威胁资源管理器和实时检测基础知识
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用资源管理器或实时检测高效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300106"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>威胁资源管理器和实时检测基本信息

本文内容：

- [威胁资源管理器和实时检测之间的差异](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [所需的许可证和权限](#required-licenses-and-permissions)

> [!NOTE]
> 这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。 本系列中的其他两篇文章是 [威胁](threat-hunting-in-threat-explorer.md) 资源管理器中的威胁搜寻和威胁 [资源管理器中的电子邮件安全](email-security-in-microsoft-defender.md)。

本文介绍了威胁探索和实时检测报告，以及所需的许可证和权限的区别。

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果你的组织拥有适用于 [Office 365](defender-for-office-365.md)的 Microsoft Defender，并且你拥有权限，可以使用称为资源管理器 **(** 的威胁资源管理器 **)** 或实时检测来检测和修正威胁。 [](#required-licenses-and-permissions)

在安全 **&中心**，转到"**威胁** 管理"，**然后选择资源管理器**_或_**实时检测**。

<br>

****

|借助 Microsoft Defender for Office 365 计划 2，可以看到：|借助 Microsoft Defender for Office 365 计划 1，可以看到：|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

使用这些工具，你可以：

- 查看 Microsoft 365 安全功能检测到的恶意软件。
- 查看网络钓鱼 URL 并单击裁定数据。
- 从资源管理器中的视图启动自动调查和响应过程。
- 调查恶意电子邮件等。

有关详细信息，请参阅使用威胁 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>威胁资源管理器和实时检测之间的差异

- *实时检测是* Defender for Office 365 计划 1 中可用的报告工具。 *威胁资源管理器* 是适用于 Office 365 计划 2 的 Defender 中提供的威胁搜寻和修正工具。
- 实时检测报告允许你实时查看检测。 威胁资源管理器也这样做，但它提供给定攻击的其他详细信息（如突出显示攻击活动）并赋予安全运营团队修正威胁 (包括触发自动调查和响应[调查) 。](automated-investigation-response-office.md)
- " *所有* 电子邮件"视图在威胁资源管理器中可用，但不包括在实时检测报告中。
- 威胁资源管理器中包含丰富的筛选功能和修正操作。 有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

必须具有适用于 [Office 365](defender-for-office-365.md) 的 Microsoft Defender，以使用资源管理器或实时检测：

- 但资源管理器仅包含在 Defender for Office 365 计划 2 中。
- 实时检测报告包含在 Defender for Office 365 计划 1 中。

安全操作团队需要为应受 Office 365 Defender 保护的所有用户分配许可证，并注意资源管理器和实时检测显示许可用户的检测数据。

若要查看和使用资源管理器 *或* 实时检测，必须具有以下项：

- 对于安全与&中心：

  - 组织管理
  - 安全 (可以在 Azure Active Directory 管理中心管理中心 <https://aad.portal.azure.com> () 
  - 安全读取者

- 对于 Exchange Online：

  - 组织管理
  - 仅查看组织管理
  - 仅查看收件人
  - 合规性管理

若要详细了解角色和权限，请参阅以下资源：

- [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能权限](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>详细信息
- [威胁资源管理器在电子邮件实体页面上收集电子邮件详细信息](mdo-email-entity-page.md)
- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意文件](mdo-for-spo-odb-and-teams.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威胁防护中的自动调查和响应](automated-investigation-response-office.md)