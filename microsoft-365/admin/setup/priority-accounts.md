---
title: 管理和监视优先级帐户
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: 监视发送到或发送自对业务影响较高的帐户的失败和延迟的电子邮件。
ms.openlocfilehash: b8762885cc54859cf927653abb14858c0094ea12
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201345"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理和监视优先级帐户

在Microsoft 365组织中，都会有一些至关重要的人，如主管人员、领导、经理或其他有权访问敏感、专有或高优先级信息的用户。

为了帮助你的组织保护这些帐户，你现在可以将特定用户指定为优先帐户，并利用特定于应用的功能，这些功能可以提供额外的保护。 将来，更多应用和功能将支持优先帐户，首先，我们宣布有两项功能：优先级帐户保护和高级邮件 **流监视**。 

- **优先级帐户** 保护 - 适用于Office 365 (高级威胁Office 365的 Microsoft Defender) 支持优先帐户作为标记，可在警报、报告和调查的筛选器中使用。 有关详细信息，请查看 Microsoft [Defender 中的用户标记Office 365。](../../security/office-365-security/user-tags.md)

  一个自然问题是，"不是所有用户都成为优先级吗？ 为什么不将所有用户指定为优先级帐户？ 是的，所有用户都是优先级，但优先级帐户保护提供了以下附加优势：

  - **其他启发：** 我们对 Microsoft 数据中心中的邮件流的分析表明，公司主管的邮件流模式不同于普通员工。 优先级帐户保护提供了专为公司主管定制的其他启发，不会使普通员工受益。
  - **报告的其他** 可见性：实际上，警报、报告和 (中已提供了) 或所有受影响用户的信息。 作为筛选器的优先级帐户标记允许你专门定向调查。

- **高级版邮件** Flow监视 - 正常邮件流对于业务成功至关重要，传递延迟或失败会对业务产生负面影响。 您可以选择失败或延迟电子邮件的阈值，在超出该阈值时接收警报，并查看优先级帐户的电子邮件问题报告。 有关详细信息，请查看新式 EAC 中的优先级 [帐户电子邮件问题报告](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

有关优先级帐户的安全最佳做法，请参阅安全 [建议优先级帐户](../../security/office-365-security/security-recommendations-for-priority-accounts.md)。

## <a name="before-you-begin"></a>准备工作

本主题 **中所述** 的优先级帐户保护功能仅适用于满足以下要求的组织：

- Microsoft Defender for Office 365 计划 2，包括Office 365 E3、Office 365 E5、Microsoft 365 E5或Microsoft 365 E5 安全性。

本主题 **高级版** 邮件Flow监视功能仅适用于满足以下要求的组织：

- 贵组织的许可证数量至少需要为 5，000（来自以下产品之一）或以下产品的组合：Office 365 E3、Microsoft 365 E3、Office 365 E5 Microsoft 365 E5。 例如，你的组织可以具有 3,000 个 Office 365 E3 许可证，2,500 个 Microsoft 365 E5，即总计拥有 5,500 个合格产品许可证。
- 你的组织需要具有至少 50 个每月活动用户，用于一个或多个核心工作负载- Teams、One Drive for Business、SharePoint Online、Exchange Online 和 Office 应用。

> [!NOTE]
> 你可以监视最多 250 个优先级帐户。

将优先级帐户保护应用于邮箱时，还应将优先级帐户保护应用于有权访问邮箱 (例如 CEO 和管理 CEO 日历管理员的 CEO 行政助理) 。

### <a name="add-priority-accounts-from-the-setup-page"></a>从"设置"页添加优先级帐户

从设置页面 **添加优先级帐户**。

1. 转到 上 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Microsoft 365 管理中心。

2. 转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**

3. 选择 **"入门"** 或"**管理"。**

4. 在 **"添加优先级帐户** "页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名或电子邮件地址。 还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。

5. 选择用户，然后选择"保存 **"。**

您还可以从"活动用户"页面添加优先级帐户。

### <a name="add-priority-accounts-from-active-users-page"></a>"从活动用户添加优先级帐户"页

从"活动用户"页面添加优先级帐户。

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

2. 转到"**用户**""活动用户"，然后选择三  >  个点 (页面) 显示更多操作。 选择 **管理优先级帐户**。

3. 选择 **"添加帐户**"，在" **添加优先级** 帐户"页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名。

4. 选择用户，然后选择"保存 **"。**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>从优先级帐户列表中删除用户

1. 转到 上 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Microsoft 365 管理中心。

2. 转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**

3. 在"**监视你的大多数帐户"页面上**，选择"管理 **此功能"下的****"优先级帐户"。**

4. 在"**优先级帐户**"页上，选择要从列表中删除的一个或多个用户，然后选择"**删除帐户"。**

## <a name="related-topics"></a>相关主题

[在 Microsoft 365 中使用优先级帐户](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
