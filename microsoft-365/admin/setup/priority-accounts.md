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
description: 监视发送到或来自具有高业务影响的帐户的电子邮件失败和延迟。
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477609"
---
# <a name="manage-and-monitor-priority-accounts"></a>管理和监视优先级帐户

在每个 Microsoft 365 组织中，有必要的人，如主管、领导、经理或其他对敏感、专有或高优先级信息具有访问权限的用户。

为了帮助您的组织保护这些帐户，您现在可以将特定用户指定为优先级帐户，并利用特定于应用程序的功能为他们提供额外的保护。 在将来，更多的应用和功能将支持优先级帐户，开始时，我们已宣布了两个功能： **优先级帐户保护** 和 **高级邮件流监控**。

- **优先级帐户保护** -Microsoft Defender for office 365 (以前的 Office 365 高级威胁防护) 支持将优先级帐户用作可在警报、报告和调查的筛选器中使用的标记。 有关详细信息，请参阅 [Microsoft Defender For Office 365 中的用户标记](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)。
- **高级邮件流监控** -正常的邮件流可能对业务成功非常关键，且传递延迟或故障可能对业务产生负面影响。 您可以为失败或延迟的电子邮件选择阈值，在超过该阈值时接收通知，并查看优先级帐户的电子邮件问题报告。 有关详细信息，请参阅 [新式 EAC 中的优先级帐户报告的电子邮件问题](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。

## <a name="before-you-begin"></a>准备工作

本主题中所述的 **优先级帐户保护** 功能仅适用于满足以下要求的组织：

- Microsoft Defender for Office 365 计划2，包括具有 Office 365 E3、Office 365 E5、Microsoft 365 E5 或 Microsoft 365 E5 安全性的 Office Defender。

本主题中介绍的 " **高级邮件流监控** " 功能仅适用于满足以下要求的组织：

- 您的组织需要的许可证计数至少为10000，或者是以下产品的一种或以下产品的组合： Office 365 E3，Microsoft 365 E3，Office 365 E5，Microsoft 365 E5。 例如，您的组织可以拥有3000个 Office 365 E3 许可证并 8500 Microsoft 365 E5，以提供符合条件的产品的全部11500许可证。
- 您的组织需要至少50个每月活动 Exchange Online 用户。

> [!NOTE]
> 您可以监控最高为250的优先级帐户。

### <a name="add-priority-accounts-from-the-setup-page"></a>从 "设置" 页面添加优先级帐户

从 " **设置" 页面** 添加优先级帐户。

1. 转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到 "**设置**  >  **组织知识**"，然后选择 "**监视最重要的帐户**" 下的 "**查看**"。

3. 选择 " **开始** " 或 " **管理**"。

4. 在 " **添加优先级帐户** " 页上的 "搜索" 字段中，键入要添加到 "优先级帐户" 列表中的人员的姓名或电子邮件地址。 您还可以为失败或延迟的电子邮件设置电子邮件阈值，并获取优先级帐户的每周问题报告。

5. 选择用户并选择 " **保存**"。

您还可以从 "活动用户" 页面添加优先级帐户。

### <a name="add-priority-accounts-from-active-users-page"></a>从活动用户添加优先级帐户页面

从 "活动用户" 页面添加优先级帐户。

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

2. 转到 "**用户**  >  **活动用户**" **...** ，然后选择页面顶部的 "..."。 选择 " **管理优先级帐户**"。

3. 选择 " **添加帐户**"，并在 " **添加优先级帐户** " 页上的 "搜索" 字段中，键入要添加到 "优先级帐户" 列表中的人员的姓名。

4. 选择用户并选择 " **保存**"。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>从 "优先级帐户" 列表中删除用户

1. 转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到 "**设置**  >  **组织知识**"，然后选择 "**监视最重要的帐户**" 下的 "**查看**"。

3. 在 "**监视你的大多数帐户**" 页上，选择 "**管理此功能**" 下的 "**优先级帐户**"。

4. 在 " **优先级帐户** " 页上，选择要从列表中删除的一个或一组用户，然后选择 " **删除帐户**"。

## <a name="related-topics"></a>相关主题

[在 Microsoft 365 中使用优先级帐户](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)