---
title: 了解 Exchange 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解专门适用于 Exchange 电子邮件和 Exchange 公用文件夹的保留行为。
ms.openlocfilehash: db39ab0f1eca1cc03dd0bbb5ffb500658695247a
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292530"
---
# <a name="learn-about-retention-policies-for-exchange"></a>了解 Exchange 的保留策略

本文中的信息是对[了解保留策略](retention-policies.md)的补充，因为它包含特定于 Exchange 的信息。

## <a name="how-a-retention-policy-works-with-exchange-locations"></a>保留策略如何与 Exchange 位置一起工作

对于用户的邮件、日历和其他项目，保留策略在邮箱级别应用。

对于公用文件夹，在文件夹级别（而不是邮箱级别）应用保留策略。 

邮箱和公用文件夹都使用“可恢复的项目”文件夹来保留项目。 只有已分配电子数据展示权限的人员才可以查看其他用户的“可恢复的项目”文件夹中的项目。
  
当用户从“已删除邮件”文件夹以外的文件夹中删除邮件时，默认情况下，该邮件将移动到“已删除邮件”文件夹中。 当用户删从“已删除邮件”文件夹中删除邮件时，该邮件将移动到“可恢复的项目”文件夹中。 但是，用户可以软删除 (SHIFT+DELETE) 任何文件夹中的邮件，这会避开“已删除邮件”文件夹，直接将邮件移到“可恢复的项目”文件夹中。
  
将保留策略应用于 Exchange 位置时，计时器作业会定期评估“可恢复的项目”文件夹中的项目。 如果某个项目与至少一个保留策略的规则不匹配，则将从“可恢复项目”文件夹中永久删除该项目（也称为硬删除）。

计时器作业运行可能需要长达 7 天的时间，并且 Exchange 位置必须至少包含 10 MB。
  
当用户尝试更改邮箱邮件的属性（如主题、正文、附件、发件人和收件人或邮件发送和接收日期）时，在提交更改之前，会将原始邮件的副本保存到“可恢复的项目”文件夹中。 每个后续更改都会执行此操作。 保留期结束时，将永久删除“可恢复的项目”文件夹中的副本。

将保留策略分配给邮箱或公用文件夹后，内容路径取决于保留设置是“保留后删除”、“仅保留”还是“仅删除”。

如果保留设置为“保留后删除”：

![电子邮件和公用文件夹中的保留流关系图](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **如果邮件在保留期限内被用户修改或永久删除**（使用 SHIFT+DELETE 或从“已删除邮件”中删除）：邮件会移动到（被编辑时会复制到）“可恢复的项目”文件夹。 因此会定期运行一个计时器作业，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。 请注意，默认设置是 14 天，但可以将其配置为最多 30 天。
    
2. **如果邮件在保留期限内未被修改或删除**：对邮箱中的所有文件夹定期运行相同的流程，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。 请注意，默认设置是 14 天，但可以将其配置为最多 30 天。 

如果保留设置为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化：

### <a name="content-paths-for-retain-only-retention-settings"></a>“仅保留”保留设置的内容路径

1. **如果有人在保持期内修改或删除项**：则会在“可恢复的项”文件夹中创建原始项的副本，并保留到保持期结束，然后“可恢复的项”文件夹中的副本会在到期后的 14 天后永久删除。 

2. **如果项在保持期内未遭修改或删除**：保持期前后无变化；项仍保留在它的原始位置上。

### <a name="content-paths-for-delete-only-retention-settings"></a>“仅删除”保留设置的内容路径

1. **如果项目在配置的期限内未遭删除**：在保留策略中配置的期限结束时，项目会移到“可恢复的项目”文件夹中。 

2. **如果项目在配置的期限内遭到删除**：项目会立即移到“可恢复的项目”文件夹中。 如果用户从“可恢复的项”文件夹中删除项或清空此文件夹，项就会永久删除。 否则，项会在“可恢复的项”文件夹中保留 14 天后永久删除。 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>从保留策略中排除特定类型的 Exchange 项

使用 PowerShell 可以从保留策略中排除特定类型的 Exchange 项目。 例如，可以排除邮箱中的语音邮件、即时消息对话和其他 Skype for Business Online 内容。 此外，还可以排除日历、便笺和任务项目。 此功能仅可通过 PowerShell 使用；使用 Microsoft 365 合规中心中的向导创建保留策略时，此功能不可用。
  
若要在保留策略中排除 Exchange 项目的选定类型，请将 `ExcludedItemClasses` 参数与 `New-RetentionComplianceRule` 和 `Set-RetentionComplianceRule` cmdlet 一起使用。


### <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

如果某用户离开组织，且此用户的邮箱包含在保留策略内，那么在此用户的 Office 365 帐户遭到删除后，其邮箱会变成非活动状态。 非活动邮箱的内容仍受在邮箱变成非活动状态之前对邮箱应用的所有保留策略约束，且内容支持电子数据展示搜索。 有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a>如何配置 Exchange 的保留策略

请参阅[创建和配置保留策略](create-retention-policies.md)。

对于向导的“**选择位置**”页面，选择下列选项之一：

- **仅将策略应用于 Exchange 电子邮件、公共文件夹、Office 365 组、OneDrive 和 SharePoint 文档中的内容**

- **让我选择特定位置** > **Exchange 电子邮件**和**Exchange 公用文件夹**

