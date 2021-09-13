---
title: 邮件门户中的Microsoft 365 Defender跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理员可以使用邮件门户中的"邮件Microsoft 365 Defender链接来了解邮件发生了什么。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196474"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>邮件门户中的Microsoft 365 Defender跟踪

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

电子邮件门户中的Microsoft 365 Defender跟踪在电子邮件通过你的组织Exchange Online跟踪。 您可以确定服务是否接收、拒绝、延迟或传递了邮件。 它还显示在邮件达到最终状态之前对邮件采取的操作。

您可以使用邮件跟踪中的信息有效回答用户有关邮件发生的情况的问题、解决邮件流问题并验证策略更改。

> [!NOTE]
> 邮件门户中Microsoft 365 Defender跟踪只是一个传递到管理中心内Exchange跟踪。 有关详细信息，请参阅新式邮件[管理](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)中心Exchange跟踪。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，需要知道什么？

- 你需要是组织中组织管理、合规性管理或 **技术支持** 角色 **Exchange Online的成员，** 以使用邮件跟踪。 有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **备注**：用户具有Azure Active Directory角色的成员身份Microsoft 365 管理中心为用户提供了对 Microsoft 365 中其他功能所需的权限。  有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 邮件跟踪结果中显示的邮件的最大数量取决于您选择的报告类型 (请参阅"选择报告类型"部分，了解) 。 [](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) PowerShell 或独立 EOP PowerShell 中的[Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet Exchange Online返回结果中的所有消息。

## <a name="open-message-trace"></a>打开邮件跟踪

在Microsoft 365 Defender门户 <https://security.microsoft.com> () ，转到"电子邮件&**协作** Exchange \> **跟踪"。** 或者，若要直接转到邮件跟踪页面，请使用 <https://admin.exchange.microsoft.com/#/messagetrace> 。

此时，EAC 中的邮件跟踪将打开。 有关详细信息，请参阅新式邮件[管理](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)中心Exchange跟踪。
