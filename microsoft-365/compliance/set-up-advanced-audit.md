---
title: 在"管理"中设置Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置高级审核，以便可以在用户帐户泄露时执行取证调查或调查其他与安全相关的事件。
ms.openlocfilehash: 34ae98eaafcc3eeb3d6a25a457f017999b8c6078
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192063"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>在"管理"中设置Microsoft 365

如果组织具有支持高级审核的订阅和最终用户许可，请执行以下步骤来设置和使用高级审核中的附加功能。

![设置高级审核的工作流。](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>步骤 1：为用户设置高级审核

“高级审核”功能，如记录重要事件（如 MailItemsAccessed 和 Send）功能，需要为用户分配适当的 E5 许可证。 此外，必须为这些用户启用“高级审核”应用程序/服务计划。 要验证“高级审核”应用程序是否已分配给用户，请对每个用户执行以下步骤：

1. In the Microsoft 365 管理中心， go to **Users**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Active users**</a>， and select a user.

2. 在用户属性浮出页面上，单击“**许可证和应用**”。

3. 在 **"许可证** "部分，验证用户是否分配有 E5 许可证或分配有相应的附加许可证。 有关支持高级审核的许可证列表，请参阅 [高级审核许可要求](auditing-solutions-overview.md#advanced-audit-1)。

4. 展开“**应用程序**”部分，并验证是否选中了“**Microsoft 365 高级审核**”复选框。

5. 如果未选中复选框，请选中它，然后单击"保存 **更改"。**

   MailItemsAccessed 和 Send 的审核记录日志记录将在 24 小时内开始。 您必须执行步骤 3 才能开始记录其他两个高级审核事件：SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。

对于使用基于组的许可将许可证分配给用户组的组织，必须为组禁用 Microsoft 365 高级审核的许可分配。 保存所做的更改后，请验证是否已为组禁用 Microsoft 365 高级审核。 然后，重新为组启用许可分配。 有关基于组的许可的说明，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

此外，如果已自定义登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新高级审核事件将不会在这些邮箱上自动审核。 有关更改为每个登录类型审核的邮箱操作的信息，请参阅[管理邮箱审核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的“更改或还原默认记录的邮箱操作”部分。

## <a name="step-2-enable-advanced-audit-events"></a>步骤 2：启用高级审核事件

当用户在 Exchange Online 和 SharePoint Online 中执行搜索时，必须启用 SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint) 两个高级审核事件。 ( 若要为用户审核这两个事件，请对 ([PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中每个用户) 运行Exchange Online命令：

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

在多地理位置环境中，必须在用户邮箱所在的林中运行以前的 **Set-Mailbox** 命令。 若要标识用户的邮箱位置，请运行以下命令： 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

如果用于启用搜索查询审核的命令之前在不同于用户邮箱所在的林中运行的林中，则必须通过运行 来从用户邮箱中删除 SearchQueryInitiated 值，然后将其添加到用户邮箱所在的林中的用户邮箱中。 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`

## <a name="step-3-set-up-audit-retention-policies"></a>步骤 3：设置审核保留策略

除了将 Exchange、SharePoint 和 Azure AD 审核记录保留一年的默认策略外，可以创建其他审核日志保留策略以满足组织安全操作、IT 和合规团队的要求。 有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。

## <a name="step-4-search-for-advanced-audit-events"></a>步骤 4：搜索高级审核事件

现在，你已为组织设置了高级审核，可以在执行取证调查时搜索关键的高级审核事件和其他活动。 完成步骤 1 和步骤 2 后，可以在调查遭到入侵的帐户和其他类型的安全或合规性调查期间，在 审核日志 中搜索高级审核事件和其他活动。 有关使用 MailItemsAccessed 高级审核事件对遭到入侵的用户帐户进行取证调查详细信息，请参阅使用高级审核调查遭到入侵 [的帐户](mailitemsaccessed-forensics-investigations.md)。
