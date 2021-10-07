---
title: Microsoft Defender for Office 365 中的威胁资源管理器和实时Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用资源管理器或实时检测高效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cced68d084bb5f4625f745dfd0f19db16cece9c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176375"
---
# <a name="explorer-and-real-time-detections-basics"></a>资源管理器和实时检测基础知识

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本文内容：

- [资源管理器和实时检测之间的差异](#differences-between-explorer-and-real-time-detections)
- [所需的许可证和权限](#required-licenses-and-permissions)

> [!NOTE]
> 这是资源管理器 (（也称为威胁资源管理器 **) 、** 电子邮件安全、资源管理器和实时检测基础知识）的 **3** 篇文章系列中的一 **部分 (如** 工具之间的差异以及运行) 所需的权限。 本系列中的其他两篇文章 [是资源管理器中](threat-hunting-in-threat-explorer.md) 的威胁搜寻和资源管理器 [中的电子邮件安全](email-security-in-microsoft-defender.md)。

本文介绍了资源管理器和实时检测报告以及所需的许可证和权限的区别。

如果你的组织拥有适用于 Office 365 的 Microsoft [Defender，](defender-for-office-365.md)并且你拥有 [](#required-licenses-and-permissions)权限，可以使用资源管理器 **(** 也称为威胁资源管理器 **)** 或实时检测来检测和修正威胁。

在Microsoft 365 Defender门户 () ，转到"电子邮件&协作"， <https://security.microsoft.com> 然后选择"**资源管理器**"或 **"实时检测"。**

使用这些工具，你可以：

- 查看由安全Microsoft 365检测到的恶意软件。
- 查看网络钓鱼 URL 并单击裁定数据。
- 从资源管理器中的视图启动自动调查和响应过程。
- 调查恶意电子邮件等。

有关详细信息，请参阅使用 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。

## <a name="differences-between-explorer-and-real-time-detections"></a>资源管理器和实时检测之间的差异

- *实时检测是* Defender for Office 365计划 1 中可用的报告工具。 *威胁资源管理器* 是一款威胁搜寻和修正工具，适用于 Office 365 计划 2。
- 实时检测报告允许你实时查看检测。 威胁资源管理器也这样做，但它提供给定攻击的其他详细信息（如突出显示攻击活动）并赋予安全运营团队修正威胁 (包括触发自动调查和响应调查[) 。](automated-investigation-response-office.md)
- " *所有* 电子邮件"视图在威胁资源管理器中可用，但不包括在实时检测报告中。
- 威胁资源管理器中包含丰富的筛选功能和修正操作。 有关详细信息，请参阅[Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

必须具有[Microsoft Defender for Office 365，](defender-for-office-365.md)以使用资源管理器或实时检测：

- 资源管理器仅包含在计划 2 Office 365 Defender 中。
- 实时检测报告包含在计划 1 的 Defender Office 365中。

安全运营团队需要为应受 Defender for Office 365 保护的所有用户分配许可证，并注意资源管理器和实时检测会显示许可用户的检测数据。

若要查看和使用资源管理器 *或* 实时检测，需要以下权限：

- 在 Defender for Office 365：
  - 组织管理
  - 安全 (可以在安全中心管理中心Azure Active Directory分配 <https://aad.portal.azure.com> () 
  - 安全信息读取者
- 在Exchange Online：
  - 组织管理
  - 仅查看组织管理
  - 仅查看收件人
  - 合规性管理

若要详细了解角色和权限，请参阅以下文章：

- [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)
- [Exchange Online 中的权限](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>更多信息

- [威胁资源管理器在电子邮件实体页面上收集电子邮件详细信息](mdo-email-entity-page.md)
- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威胁防护中的自动调查和响应](automated-investigation-response-office.md)
