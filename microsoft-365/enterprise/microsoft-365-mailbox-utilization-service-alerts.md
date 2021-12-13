---
title: 邮箱使用率服务警报
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: 使用邮箱使用率服务警报监视达到其邮箱配额的保留邮箱。
ms.openlocfilehash: 311be4159d45b19ce1123baa840eebdf844840ec
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421362"
---
# <a name="service-alerts-for-mailbox-utilization-in-exchange-online-monitoring"></a>Exchange Online 监视中邮箱利用率的服务警报

我们发布了新的 Exchange Online 服务警报，通知处于保留状态、有达到或超出配额的风险的邮箱。 这些服务警报提供组织中可能需要管理员干预的邮箱数量的可见性。

这些服务警报显示在Microsoft 365 管理中心。 若要查看这些服务警报，请转到运行状况服务  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**运行状况**</a>Exchange Online  >  然后单击"**活动问题"** 选项卡。下面是邮箱利用率服务警报的示例。

:::image type="content" alt-text="邮箱利用率服务警报。" source="../media/MailboxUtilizationServiceAlert.png" lightbox="../media/MailboxUtilizationServiceAlert.png":::

若要显示即将达到存储配额的邮箱列表 (邮箱使用情况报告 *) ，* 请单击以下屏幕截图中的突出显示链接。 此链接显示在服务警报中。

:::image type="content" alt-text="链接到邮箱使用情况报告。" source="../media/LinkToMailboxUsageReport.png" lightbox="../media/LinkToMailboxUsageReport.png":::

或者，指向邮箱使用情况报告的直接 URL 是 <https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage/MailboxUsage> 。

## <a name="what-do-these-service-alerts-indicate"></a>这些服务警报表示什么？

邮箱使用率服务警报通知管理员即将达到邮箱存储配额的保留邮箱。 可以置于邮箱上的保留类型包括诉讼保留、电子数据展示保留和 Microsoft 365 保留策略 (配置为保留) 。 当邮箱置于保留状态时， (或自动) 无法从邮箱中永久删除数据。 相反，管理员必须在 Exchange Online (中与数据保留策略相关的组织合规性策略内联配置 MRM 保留策略) 才能将数据从用户的主邮箱移动到存档邮箱。 如果没有，且保留邮箱达到关键或警告状态，管理员必须启用存档邮箱并启用自动[](../compliance/enable-archive-mailboxes.md)扩展存档，然后确保[](../compliance/enable-autoexpanding-archiving.md)分配给将电子邮件从主邮箱移动到存档邮箱) 的邮箱 (的存档策略的保留期足够短。 如果未执行任何操作来解决邮箱利用率服务警报所标识的配额问题，则用户可能无法发送或接收电子邮件或会议邀请。

邮箱使用率服务警报包含有关接近配额的邮箱数量的表。 以下各节介绍了这些表中的信息以及管理员为帮助确保这些邮箱不会超出其配额而可采取的操作。

> [!NOTE]
> 服务警报包含邮箱配额属性的说明，这些属性显示在以下各节所述的表格中的列中。

### <a name="mailboxes-on-hold-without-an-archive"></a>没有存档的保留邮箱

下表列出了即将达到配额但没有启用存档邮箱的保留邮箱数。 表中的每个列标识特定配额和接近该配额的邮箱数。

| # Mailboxes ProhibitSendReceiveQuota (Warning) | # Mailboxes ProhibitSendReceiveQuota (Critical) ** |# Mailboxes RecoverableItemsQuota (Warning) |# Mailboxes RecoverableItemsQuota (Critical) ** |
|:--------------|:--------------|:------------------|:--------------- |
| 2             | 2             | 1                 | 0               |
||||

管理员可以为这些邮箱采取的操作是启用存档邮箱，并确保 MRM 存档策略 (这是 Exchange Online 中将项目移动到存档邮箱) 的 MRM 保留策略，以便项目移动到存档邮箱。 有关详细信息，请参阅设置 [邮箱的存档和删除策略](../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

启用存档邮箱后，建议您考虑增加"可恢复的项目"文件夹的配额。 这有助于防止超过置于保留状态邮箱的"可恢复的项目"文件夹的配额。 有关详细信息，请参阅[增加置于保留状态的邮箱可恢复项目的配额](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

### <a name="mailboxes-on-hold-with-an-archive"></a>具有存档的保留邮箱

下表列出了即将达到配额且已启用存档邮箱的保留邮箱数。

|# Mailboxes ProhibitSendReceiveQuota (Warning)  |# Mailboxes ProhibitSendReceiveQuota (Critical)  |# Mailboxes RecoverableItemsQuota (Warning)  |# Mailboxes RecoverableItemsQuota (Critical) ** |
|:--------------|:--------------|:------------------|:--------------- |
| 1             | 1             | 6                  | 0               |
||||

管理员可以为这些邮箱执行的操作是增加"可恢复的项目"文件夹的配额。 有关详细信息，请参阅[增加置于保留状态的邮箱可恢复项目的配额](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

管理员还应确保将项目移动到存档邮箱的 MRM 存档策略也应用于邮箱，并且存档策略的保留期足够短，以便项目在移动到存档之前不会在主邮箱中保留太长时间。

> [!NOTE]
> MRM 存档策略还会将项目从主邮箱中的"可恢复的项目"文件夹移动到相应存档邮箱中的"可恢复的项目"文件夹。 此功能有助于防止邮箱超出"可恢复的项目"配额的配额。

### <a name="mrm-retention-policies-in-your-organization"></a>组织中 MRM 保留策略

邮箱使用率的服务警报可能还包含一个表，其中包含有关您组织中 MRM 保留策略以及作为保留策略的邮箱是否具有存档邮箱的信息。 有关保留策略详细信息，请参阅保留[标记和保留策略Exchange Online。](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

| RetentionPolicyGuid | MailboxType | HasMoveDumpsterToArchiveTag | HasMovePrimaryToArchiveTag | HasPersonalArchiveTag |  邮箱 |
|:--------------|:--------------|:---------------|:---------------|:---------------|:--------------- |
| 6c041498-1611-5011-a058-1156ce60890c | PrimaryWithArchive | True | False | True | 398 |
| 6c041498-1611-5011-a058-1156ce60890c | 主 | True | False | True | 10  |
| 749ceecc-d49d-4000-a9d5-594dbaea1e56 | PrimaryWithArchive | False | True | False | 7  |
| 269f6a85-1234-4648-8cde-59bbc7bc67d0 | PrimaryWithArchive | True | True | True | 1 |
| 13fb778d-e1cb-4c44-5768-ad4282906c1f | PrimaryWithArchive | True | True  | False | 1 |
|||||||

下表描述了上表中每一列。

- **RetentionPolicyGuid：** 分配给组织中邮箱的保留策略的 GUID。 在上一示例中，同一保留策略有两个单独的行。 第一行指示具有已分配策略的存档的邮箱数。 第二行指示未分配相同策略的存档的邮箱数。

   若要获取有关此列中列出的保留策略详细信息，请运行 PowerShell 中的以下[Exchange Online命令](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-RetentionPolicy <GUID> | FL
   ```

   Name **属性的值是保留** 策略的名称，显示在管理中心的"保留策略"Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">页上</a>。

- **MailboxType：** 指定策略分配到的邮箱类型。 值包括 *没有* (邮箱的主邮箱) *或 PrimaryWithArchive* (存档邮箱) 。 如果此列中的值为 *Primary*，应为邮箱启用存档 ("邮箱"列指示分配了策略) 邮箱数。 否则，存档策略或个人存档标记将不起作用，因为没有要将项目移动到的存档。

- **HasMoveDumpsterToArchiveTag**：指示保留策略包含保留标记，用于将"可恢复的项目"文件夹 (（也称为"垃圾 *站") ）* 中的项目移动到存档中的"可恢复的项目"文件夹。 此类型的保留标记由管理员设置。如果"可恢复的项目"标记的保留期太长，则缩短保留期应该有助于防止邮箱接近"可恢复邮件"文件夹的配额。 例如，如果将保留期设置为 30 天，那么将保留期减少为 3 天或 5 天可能会有所帮助。  有关详细信息，请参阅[增加置于保留状态的邮箱可恢复项目的配额](../compliance/increase-the-recoverable-quota-for-mailboxes-on-hold.md)。

- **HasMovePrimaryToArchiveTag**：指示是否有默认的"移动到存档"保留标记 (也称为保留策略中包含的) 策略标记。  在这种情况下，邮件会从主邮箱中的常规文件夹移动到存档邮箱。 此类型的保留标记由管理员设置。同样，如果此标记的保留期太长，则用户可能遇到持续达到其主邮箱的配额的问题。 缩短存档策略的保留期有助于解决此问题。

- **HasPersonalArchiveTag**：指示保留策略是否包含个人"移动到存档"标记。 如果保留策略包含个人"移动到存档"标记，则用户可以将此标记应用于其邮箱中的文件夹和邮件，以将项目移动到存档。 用户还可以设置收件箱规则，将邮件移动到应用了此标记的文件夹。 在这两种情况下，这都可以帮助将项目移动到存档，以帮助避免达到其主邮箱的配额。

- **Mailboxes**： Indicates the number of mailboxes (those with or without an archive， which is indicated in the **MailboxType** column) the retention policy is assigned to.

## <a name="how-often-will-i-see-these-service-alerts"></a>多久看到一次这些服务警报？

如果不采取措施来解决配额问题，则希望每四天看到一次此类服务警报。 后续服务警报可能包含接近配额的其他邮箱的更高的邮箱计数。 如果您采取措施来解决配额问题，此服务警报将仅在标识了另一个具有配额问题的邮箱时发生。

## <a name="more-information"></a>更多信息

- 有关解决和解决存档邮箱问题的信息，请参阅Microsoft 365[合规性疑难解答](/office365/troubleshoot/microsoft-365-compliance-welcome)。

- 有关标识邮箱上保留的指南，请参阅如何标识邮箱 [上放置的保留类型](../compliance/identify-a-hold-on-an-exchange-online-mailbox.md)。
