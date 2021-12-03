---
title: 了解非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: 了解如何通过将邮箱转换为非活动邮箱来保留以前员工的邮箱内容。
ms.openlocfilehash: 0cc8e7fd980d48be44da824bad84343231c166ea
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284621"
---
# <a name="learn-about-inactive-mailboxes"></a>了解非活动邮箱

你的组织可能需要在前员工离开组织后保留其电子邮件。 根据组织的保留要求，可能需要在雇佣关系终止后将邮箱内容保留数月或数年，或者可能需要无限期地保留邮箱内容。 不管你需要保留邮件多久，你都可以创建非活跃邮箱来保留先前员工的邮箱。

## <a name="what-are-inactive-mailboxes"></a>什么是非活动邮箱？

当员工离开组织 (或长期离开) ，可以删除其Microsoft 365帐户。 删除帐户后，员工的邮箱数据将保留 30 天。 在此期间，您仍可以通过取消删除帐户来恢复邮箱数据。 30 天后，数据将永久删除。

但是，如果在删除邮箱帐户之前对邮箱应用了保留Microsoft 365，则邮箱将转换为非活动邮箱。 以下各节包含有关可应用于电子数据展示保留Microsoft 365保留的信息。

当组织出于法规或其他原因需要保留以前员工的邮箱内容时，非活动邮箱非常有用。 虽然本文档中列出的任何类型的保留将在删除用户对象时强制使邮箱变为非活动状态，但我们建议通过应用 Microsoft 365 保留策略或保留标签执行此操作，确认已应用保留，然后删除相应的 Microsoft 365[](#confirming-a-hold-is-applied-to-a-mailbox)帐户。 此时，非活动邮箱的内容在删除用户帐户之前指定的保留期内保留。 您仍可以在 30 天内恢复相应的用户帐户，但在 30 天后，邮箱作为非活动邮箱保留在 Microsoft 365 中，直到删除保留策略或保留标签。

> [!IMPORTANT]
> 如前所述，我们建议您使用Microsoft 365保留来创建非活动邮箱：
> - In-Place管理Exchange中的保留现已停用。 自 2020 年 7 月 1 日起，无法在 In-Place 中创建新的保留Exchange Online。 从 2020 年 10 月 1 日起，就地保留的保留期无法再更改。 应用了"保留In-Place的任何非活动邮箱都只能通过删除"保留"In-Place删除。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱将继续保留。 有关保留停用In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
> 
> - [诉讼保留](create-a-litigation-hold.md) 仍受支持，作为在删除用户帐户后保留邮箱内容并使其处于非活动状态的替代方法。 但是，作为较旧的技术，我们建议你改为Microsoft 365保留。

如果对同一内容存在多个保留，则保留[](retention.md#the-principles-of-retention-or-what-takes-precedence)原则适用，并且内容将保留最长。

### <a name="confirming-a-hold-is-applied-to-a-mailbox"></a>确认对邮箱应用了保留

无论是应用 Microsoft 365 保留策略、保留标签、电子数据展示保留、诉讼保留，还是应用现有 In-Place 保留，都可以使用 PowerShell 确认保留已成功应用于邮箱。 如果最近配置了保留，可能需要等到该保留应用于邮箱。

为了防止意外或无意删除，我们建议您在删除用户帐户之前确认保留。 如果未应用保留，则邮箱不会转换为非活动邮箱。

有关说明，请参阅[如何标识邮箱中置于Exchange Online的类型](identify-a-hold-on-an-exchange-online-mailbox.md)。

## <a name="inactive-mailboxes-and-microsoft-365-retention"></a>非活动邮箱Microsoft 365保留

如果将Microsoft 365策略应用于邮箱，或者邮箱中的一个或多个电子邮件项目应用了保留标签，然后删除了 Microsoft 365 用户帐户，则邮箱将转换为非活动邮箱。 对于要创建的非活动邮箱：

- 必须将保留设置配置为保留 [内容，或保留然后删除内容](retention-settings.md#settings-for-retaining-and-deleting-content)。 如果将保留操作配置为仅删除内容，则删除用户帐户时邮箱不会变为非活动状态。 对于非活动邮箱，我们建议使用"保留后删除"选项。

- 必须将保留设置[应用于与邮箱](retention-settings.md#locations)关联的保留Exchange位置：
    - Exchange 电子邮件
    - Microsoft 365 组
    - Skype for Business
    - Exchange 公用文件夹
    - Teams 通道消息
    - Teams 聊天
    - Teams 专用频道消息
    - yammer 社区消息
    - Yammer 用户消息

有关 Microsoft 保留详细信息，请参阅 [了解保留策略和保留标签](retention.md)。

如果Microsoft 365保留用于创建非活动邮箱，则保留策略或保留标签中的保留设置将继续应用于非活动邮箱。 这意味着，如果保留设置配置为保留然后删除内容，则当保留期过期时，项目将移动到"可恢复的项目"文件夹，然后最终从非活动邮箱中清除。 如果未将保留设置配置为已删除项目，则用户 (在邮箱变为非活动) 之前未永久删除的项目将不会移至"可恢复的项目"文件夹，并且将在邮箱变为非活动状态后无限期保留。

> [!TIP]
> 可以使用 *ComplianceTagHoldApplied* 属性来确定邮箱中是否有应用了一个或多个保留标签以保留或保留然后删除内容的项目。 有关详细信息，请参阅标识保留邮箱，因为保留标签已应用于文件夹 [或项目](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)。

### <a name="using-adaptive-policy-scopes-to-manage-retention-of-inactive-mailboxes"></a>使用自适应策略作用域管理非活动邮箱的保留

使用 [自适应策略作用域](retention.md#adaptive-or-static-policy-scopes-for-retention)，可以专门将保留设置应用于非活动邮箱。 此配置的好处包括：

- 你可以符合组织的法规或策略，要求有效员工和以前的员工具有不同的保留期。

- 可以将保留设置配置为仅在满足组织对以前员工的要求时保留邮箱内容。

- 您可以快速确定分配给组织中非活动邮箱的保留策略，从而在必要时更轻松地更改保留设置。 

- 永久删除非活动邮箱更容易，因为您可以基于非活动邮箱的属性或属性配置自适应范围以[](retention-settings.md#to-configure-an-adaptive-scope)将其排除，以将其从策略中删除。 否则，在删除Exchange Online之前，必须使用[PowerShell。](delete-an-inactive-mailbox.md#remove-an-inactive-mailbox-from-a-retention-policy) [](delete-an-inactive-mailbox.md#before-you-delete-an-inactive-mailbox)

> [!NOTE]
> 根据自适应策略范围的配置，非活动邮箱可能会包含也可能不包含在内。  若要专门面向或排除自适应策略作用域中的非活动邮箱，请参阅电子邮件Exchange[公用文件夹Exchange配置信息](retention-settings.md#locations)。

### <a name="using-static-policy-scopes-and-inactive-mailboxes"></a>使用静态策略作用域和无效邮箱

如果不将自适应策略作用域与[](retention.md#adaptive-or-static-policy-scopes-for-retention)保留Microsoft 365，而是使用静态作用域，请考虑以下事项： [](retention.md#adaptive-or-static-policy-scopes-for-retention)

- 使用默认 **所有收件人** 配置但不支持 [特定包含或排除](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions) 时，静态策略作用域将包含非活动邮箱。 但是，如果在应用策略时包含或排除具有活动邮箱的收件人，并且该邮箱随后变为非活动状态，则将继续应用或排除保留设置。 在此方案中， [特定包含和排除限制](retention-limits.md) 仍然适用。
    
    > [!NOTE]
    > 这还意味着，使用Microsoft 365作用域（应用于"所有收件人"的默认选择）的任何新的保留设置将自动包括所有现有的非活动邮箱。

- 如果将"所有收件人"的默认选择更改为包含特定收件人，则策略的保留设置将不再应用于任何非活动邮箱，这些邮箱现在有资格自动删除。

- 如果要释放应用于非活动邮箱的保留策略，请参阅 [发布保留策略](retention.md#releasing-a-policy-for-retention)。

> [!CAUTION]
> 使用保留Microsoft 365使邮箱变为非活动状态时，在删除相应的用户帐户之前，不要更改或删除邮箱的用户主体名称 (UPN) 。 此外，不要更改派生自 UPN (的主 SMTP 地址) 或先从与邮箱关联的辅助 SMTP 地址列表中移除此电子邮件地址，然后再使邮箱变为非活动状态。
> 
> 如果更改在应用) 保留设置时分配给邮箱的 UPN 或电子邮件地址 (然后删除用户帐户使邮箱变为非活动状态，则如果不再需要保留非活动邮箱，将无法删除该邮箱。 这是因为无法通过使用 UPN 或电子邮件地址 (来标识非活动邮箱) 这不同于最初将保留设置应用于邮箱时已存在的非活动邮箱) 。 有关删除非活动邮箱的信息，[请参阅删除非](delete-an-inactive-mailbox.md)活动Office 365。

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>非活动邮箱和电子数据展示案例保留

如果与 Microsoft 365 合规中心 中的电子数据展示案例[](./get-started-core-ediscovery.md)关联的保留置于邮箱上，然后删除邮箱或用户帐户，则邮箱将变为非活动邮箱。 但是，我们不建议使用电子数据展示案例保留来使邮箱处于非活动状态。 这是因为电子数据展示事例适用于与安全问题相关的特定、有时间限制的事例。 有时，法律案件可能会结束，并且将删除与该案件关联的保留，并关闭电子数据展示案例。 事实上，如果非活动邮箱上置于的保留与电子数据展示案例关联，然后释放该保留或关闭 (或删除) ，则非活动邮箱将被永久删除。 此外，无法创建基于时间电子数据展示保留。 这意味着非活动邮箱中的内容将永久保留，或者一直保留到删除保留并删除非活动邮箱。 因此，我们建议对非Microsoft 365邮箱使用保留策略。

有关电子数据展示保留和保留Microsoft 365，请参阅何时使用保留策略和保留标签[或电子数据展示保留](retention.md#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)。

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>非活动邮箱和自动扩展存档

无法恢复或还原使用自动扩展存档配置的非活动邮箱。 如果需要通过自动扩展存档从非活动邮箱恢复数据，建议您使用内容搜索工具从邮箱导出数据，然后导入另一个邮箱。 有关搜索非活动邮箱和导出搜索结果的分步说明，请参阅：

- [内容搜索](content-search.md)

- [导出内容搜索结果](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>非活动邮箱Exchange MRM 保留策略

如果对 Exchange Online) 中的Exchange保留策略 (邮件记录管理或 MRM 功能，则删除用户帐户时不会创建非活动邮箱。

但是，如果此 MRM 保留策略在邮箱处于非活动状态之前应用于该邮箱，则任何删除策略 (使用 Delete **操作**) 配置的 MRM 保留标记将继续在非活动邮箱上进行处理。 这意味着，在保留期到期时，用 MRM 删除策略标记的项目将[](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)移动到"可恢复的项目"文件夹。 在保留期过期时，这些项目会从非活动邮箱中清除。 如果没有为非活动邮箱指定保留期，则"恢复项目"文件夹中的项目将无限期保留。

相反，任何存档策略 (分配给非活动邮箱的 MRM 保留策略中包含的使用 **MoveToArchive** 操作) 配置的 MRM 保留标记。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。 这些项目不会移到存档邮箱或其中的“可恢复的项目”文件夹内。 它们将被无限期保留。

## <a name="next-steps"></a>后续步骤

若要使邮箱变为非活动邮箱并管理它，例如恢复、还原和删除邮箱，请参阅创建 [和管理非活动邮箱](create-and-manage-inactive-mailboxes.md)。
