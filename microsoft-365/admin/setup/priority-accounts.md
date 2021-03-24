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
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: 监视发送到或发送自对业务影响较高的帐户的失败和延迟的电子邮件。
ms.openlocfilehash: 0bba1f87f80de9fea249ce2604e83ceeadfb79ee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050638"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理和监视优先级帐户

每个 Microsoft 365 组织中都有一些必要的人员，如主管人员、领导、经理或其他有权访问敏感、专有或高优先级信息的用户。

为了帮助你的组织保护这些帐户，你现在可以将特定用户指定为优先帐户，并利用特定于应用的功能，这些功能可以提供额外的保护。 将来，更多应用和功能将支持优先帐户，首先，我们宣布有两项功能：优先级帐户保护和高级邮件 **流监视**。 

- 优先级帐户保护 **-** Microsoft Defender for Office 365 (以前是 Office 365 高级威胁防护) 支持将优先级帐户作为标记，这些标记可用于警报、报告和调查的筛选器。 有关详细信息，请查看 Microsoft [Defender for Office 365](../../security/defender-365-security/user-tags.md)中的用户标记。
- **高级邮件流监视** - 正常邮件流对于业务成功至关重要，传递延迟或失败会对业务产生负面影响。 您可以选择失败或延迟电子邮件的阈值，在超出该阈值时接收警报，并查看优先级帐户的电子邮件问题报告。 有关详细信息，请查看新式 EAC 中的优先级帐户电子邮件 [问题报告](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

有关优先级帐户的安全最佳做法，请参阅安全 [建议优先级帐户](../../security/defender-365-security/security-recommendations-for-priority-accounts.md)。

## <a name="before-you-begin"></a>准备工作

本主题 **中所述** 的优先级帐户保护功能仅适用于满足以下要求的组织：

- Microsoft Defender for Office 365 计划 2，包括 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全中心。

本主题 **中所述** 的高级邮件流监视功能仅适用于满足以下要求的组织：

- 贵组织的许可证计数至少需要为 10，000（来自以下产品之一）或以下产品的组合：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。 例如，你的组织可以拥有 3000 个 Office 365 E3 许可证和 8500 个 Microsoft 365 E5，总共 11，500 个许可证来自符合条件的产品。
- 你的组织需要拥有至少50 个 Exchange Online 月活跃用户。

> [!NOTE]
> 你可以监视最多 250 个优先级帐户。

### <a name="add-priority-accounts-from-the-setup-page"></a>从"设置"页添加优先级帐户

从设置页面 **添加优先级帐户**。

1. 转到 Microsoft 365 管理中心，位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**

3. 选择 **"入门"** 或"**管理"。**

4. 在 **"添加优先级帐户"** 页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名或电子邮件地址。 还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。

5. 选择用户，然后选择"保存 **"。**

您还可以从"活动用户"页面添加优先级帐户。

### <a name="add-priority-accounts-from-active-users-page"></a>"从活动用户添加优先级帐户"页

从"活动用户"页面添加优先级帐户。

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

2. 转到 **"用户**  >  **""** 活动用户"，然后选择页面顶部的"..."。 选择 **管理优先级帐户**。

3. 选择 **"添加帐户**"，在" **添加优先级** 帐户"页上的搜索字段中，键入要添加到优先级帐户列表的人的姓名。

4. 选择用户，然后选择"保存 **"。**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>从优先级帐户列表中删除用户

1. 转到 Microsoft 365 管理中心，位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到"**设置**  >  **组织知识"，** 然后选择"监视最重要的帐户 **"下的"查看"。**

3. 在"**监视你的大多数帐户"页面上**，选择"管理 **此功能"下的****"优先级帐户"。**

4. 在"**优先级帐户**"页上，选择要从列表中删除的一个或多个用户，然后选择"**删除帐户"。**

## <a name="related-topics"></a>相关主题

[在 Microsoft 365 中使用优先级帐户](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)