---
title: 隔离 (中的最终用户垃圾邮件) 隔离Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP 电子邮件中隔离邮件的最终用户Exchange Online Protection () 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d3c7296cff3f3f4f2d10a2c4358a889ac428880
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064071"
---
# <a name="use-quarantine-notifications-to-release-and-report-quarantined-messages"></a>使用隔离通知释放并报告隔离邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。 有关详细信息，请参阅 [EOP 中的隔离邮件](quarantine-email-messages.md)。

_隔离_ 策略根据邮件被隔离的原因来定义允许用户对隔离邮件 (支持的功能) 。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。 隔离策略还控制受影响的收件人 (包括共享邮箱 _) 是否定期_ 收到有关其隔离邮件的隔离通知。 隔离通知是所有受支持的保护功能的最终用户垃圾邮件通知 (，而不仅是反垃圾邮件策略裁定) 。

隔离通知未在名为 AdminOnlyAccessPolicy 或 DefaultFullAccessPolicy 的内置隔离通知中打开。 如果组织具有隔离通知，隔离通知在名为 NotificationEnabledPolicy 的内置隔离 [策略中打开](quarantine-policies.md#full-access-permissions-and-quarantine-notifications)。 否则，若要在隔离策略中打开隔离通知，需要 [创建和配置新的隔离策略](quarantine-policies.md#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)。

此外，为了直接阻止发件人隔离通知，需要为用户启用远程 Powershell。 有关说明，请参阅[启用或禁用对 Exchange Online PowerShell 的访问权限](/powershell/exchange/disable-access-to-exchange-online-powershell)。

管理员还可使用隔离策略中的全局设置来自定义发件人的 显示名称、不同语言的免责声明文本以及隔离通知中使用的公司徽标。 有关说明，请参阅 [配置全局隔离通知设置](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal)。

对于共享邮箱，仅向共享邮箱授予 FullAccess 权限的用户支持隔离通知。 有关详细信息，请参阅使用 [EAC 编辑共享邮箱委派](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

> [!NOTE]
> 默认情况下，由邮件流规则 (（也称为适用于 Office 365 的 Defender 中的传输规则) 或 保险箱 附件策略）隔离为高可信度网络钓鱼、恶意软件或 保险箱 附件策略的邮件仅对管理员可用 (默认情况下，AdminOnlyAccessPolicy 隔离策略使用) 。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)。
>
> 目前，组或高可信度网络钓鱼邮件不支持隔离通知。 

当您收到隔离通知时，以下信息始终可用于每个隔离邮件：

- **发件人**：已隔离邮件的发送名称和电子邮件地址。
- **主题**：隔离邮件的主题行文本。
- **日期**：隔离邮件 (UTC) 日期和时间。

隔离通知中可用的操作取决于邮件被隔离的原因，以及关联的隔离策略分配的权限。 有关详细信息，请参阅隔离 [策略权限详细信息](quarantine-policies.md#quarantine-policy-permission-details)。

默认情况下，对于被隔离为垃圾邮件、高可信度垃圾邮件或批量邮件的邮件，隔离通知中提供以下操作：

- **阻止发件人**：单击此链接将发件人添加到邮箱上的 _阻止发件人列表中_ 。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。
- **释放**：你可以在此处释放邮件，**而无需在** Microsoft 365 Defender 门户中。
- **Review**： Click this link to go to **Quarantine** in the Microsoft 365 Defender portal， where you can (depending on why the message was quarantined) view， release， delete or report your quarantined messages. 有关详细信息，请参阅在 [EOP](find-and-release-quarantined-messages-as-a-user.md)中以用户模式查找并释放隔离邮件。

![示例隔离通知。](../../media/end-user-spam-notification.png)

> [!NOTE]
> 阻止的发件人仍可向您发送邮件。 来自此发件人的任何发送到您的邮箱的邮件将立即移动到"垃圾邮件"文件夹。 以后来自此发件人的邮件将转到"垃圾邮件"文件夹或隔离。 如果要在到达时删除这些邮件，而不是隔离它们，请使用邮件流规则 [ (也称为](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 传输规则) 到达时删除邮件。
