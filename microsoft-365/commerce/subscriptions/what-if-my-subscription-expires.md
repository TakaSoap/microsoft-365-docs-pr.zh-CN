---
title: 订阅结束后会对我的数据和访问权限有何影响？
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: 了解 Microsoft 365 for Business 订阅到期、禁用或取消后对我的数据的影响。
ms.date: 09/16/2021
ms.openlocfilehash: 8baebd55217dd5cd38228cca26a7504e5021f06b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322179"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Microsoft 365 for Business 订阅结束后对我的数据和访问有何影响？

如果订阅结束 (无论是因为过期，还是因为你决定取消) 对 Microsoft 365 服务、应用程序和客户数据的访问都会在完全关闭订阅或 *删除* 订阅之前经历多个状态。 如果你意识到这一进展，则会更好地准备好在无法挽回之前将订阅恢复到活动状态，或者 — 如果你要离开 Microsoft 365 — 则可以在最终删除之前备份你的数据。

在联系 [Microsoft 365 支持](../../admin/get-help-support.md) 之前，请阅读这些重要信息。

> [!NOTE]
> 对于某些订阅，只能在购买或续订订阅后的有限时间段内取消。 如果取消时段已过，请在订阅期限结束时关闭定期计费以取消订阅。
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>订阅到期后，对数据会有何影响？

- 如果订阅过期，它会经历以下阶段：已过期 / 已停用 / 已删除。 在订阅到达结束日期后会立即启动“已过期”阶段。
- 如果关闭年度订阅的定期账单，它将经历与过期订阅相同的阶段。 第一阶段的开始为每年订阅的周年纪念，而不是从关闭订阅定期记帐设置的日期开始的。
- 如果取消月度订阅，它将立即失效（在取消之日）。 这意味着你的用户会立即失去对 Microsoft 365 资产的访问权，只有管理员才能在接下来的 90 天内访问数据。

下表解释了当付费的 Microsoft 365 for Business 订阅到期时会产生的预期结果。

| 活动 | 已过期 <br/>(30 天\*) | 已禁用 <br/>(90 天\*) | Deleted |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *所有人都可访问数据*                                               | *所有人都可访问数据*                                                     | *仅管理员可以访问数据*                                             | **已删除数据 <br/> 如果其他服务未使用 Azure Active Directory，则已将其删除** |
| 用户可正常访问 Microsoft 365、文件和应用程序   | 用户可正常访问 Microsoft 365、文件和应用程序              | 用户无法访问 Microsoft 365、文件或应用程序                        | 用户无法访问 Microsoft 365、文件或应用程序                                     |
| 管理员可正常访问 Microsoft 365、数据和 Office 应用程序 | 管理员可以访问管理中心                                           | 管理员可以访问管理中心，但不能向用户分配许可证       | 管理员可以访问管理中心，以购买和管理其他订阅             |
|                                                                        | 全局管理员或帐务管理员可以在管理中心中重新激活订阅 | 全局管理员或帐务管理员可以在管理中心中重新激活订阅 |                                                                                           |

*对于大多数国家和地区的大多数优惠。
  
> [!NOTE]
>
> **什么是"客户数据"？** 根据 [Microsoft 在线服务条款的定义](https://go.microsoft.com/fwlink/p/?LinkId=613649)，客户数据是指所有数据，包括客户或代表客户通过使用 Microsoft 365 服务向 Microsoft 提供的所有文本、声音或图像文件。 如果要了解有关客户数据保护的更多信息，请参阅 [开始使用 Microsoft 服务信任门户](../../compliance/get-started-with-service-trust-portal.md)。

## <a name="what-happens-if-i-cancel-a-subscription"></a>如果取消订阅会发生什么情况？

如果在期限结束前取消订阅，订阅将跳过已过期阶段，直接进入已停用阶段，这一阶段在大多数国家和地区中对于大多数订阅的时长为 90 天。 我们建议在取消之前 [备份数据](back-up-data-before-switching-plans.md)，但作为管理员，虽然处于禁用期，你仍然可以访问和备份组织的数据。 你留下的任何客户数据都可能在取消的 90 天之后、180 天之前被删除。
  
下面是你取消订阅对你和你的用户会产生的预期结果。
  
- **管理员访问** 管理员仍然可以登录并访问管理中心，并根据需要购买其他订阅。 作为全局管理员或账务管理员，你有 90 天时间可以 [重新激活订阅](reactivate-your-subscription.md) 且保留所有数据完好无损。

- **用户访问权限** 你的用户将无法使用 OneDrive for Business 等服务，也无法访问客户数据，例如，团队网站上的电子邮件或文档。 Office 应用程序，如 Word 和 Excel，最终将进入只读的减少功能模式，并显示 [未授权产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。

要了解如何取消，请参阅 [取消订阅](cancel-your-subscription.md)。
  
> [!IMPORTANT]
> 如果希望在象征性的禁用期结束前删除订阅数据，可以[关闭帐户](../close-your-account.md)。
  
> [!NOTE]
>
> 如果显式删除订阅，则它将跳过过期和禁用阶段，而且会立即删除 SharePoint Online 数据和内容（包括 OneDrive）。

## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>我的订阅即将过期时我有哪些选择？

当订阅处于活动状态时，你和你的终端用户可以正常访问你的数据、电子邮件和 OneDrive for Business 等服务以及 Office 应用程序。 作为管理员，当你的订阅即将到期时，会通过电子邮件和管理中心收到一系列通知。
  
订阅的到期日期真正到来之前，你有一些选择：
  
- **为订阅启用定期计费**。
  - 如果已打开 **定期计费**，则无需执行任何操作。 系统自动对你的订阅计费，并且根据你当前的缴费频率，向你额外收取一年或一个月的费用。 如果由于某种原因关闭了 **定期计费**，可随时 [重新开启定期计费](renew-your-subscription.md)。
  - 如果通过预付卡购买了 Microsoft 365 商业应用版，则可以为你的订阅[打开定期计费](renew-your-subscription.md)。
  - 如果你是使用预付费一年订阅的“开放式批量许可”客户，请与合作伙伴联系以购买新的产品密钥。 你将通过电子邮件收到在[批量许可服务中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)中激活密钥的说明。 若要了解如何查找新合作伙伴或过去合作过的合作伙伴，请参阅[查找合作伙伴或经销商](../../admin/manage/find-your-partner-or-reseller.md)。
  - 如果具有 Microsoft 365 商业应用版，请参阅 [管理订阅的定期计费](renew-your-subscription.md)。
- **让订阅过期。**
  - 如果使用信用卡或发票支付，而又不想继续订阅，请将 [“定时计费”关闭](renew-your-subscription.md)。 你的订阅在到期日结束，可以忽略所有相关的电子邮件通知。
  - 如果是与合作伙伴合作的开放批量授权客户，则无需采取任何行动，让订阅到期。
  - 如果你是 Microsoft 365 商业标准版客户，并且你的订阅是预付费且通过产品密钥激活，则无需采取操作即可让订阅过期。
- **在订阅到期前取消。** 有关详细信息，请参阅 [取消订阅](cancel-your-subscription.md)。

## <a name="what-happens-after-my-subscription-expires"></a>我的订阅到期之后会发生什么情况？

如果让你的订阅过期，在永久删除之前它会经历多个状态。 作为管理员，如果想继续使用该服务，你有时间重新激活；如果决定不再需要该订阅，也有时间备份你的数据。
  
下面介绍订阅在各个状态会产生的预期结果。
  
### <a name="state-expired"></a>状态：已过期

**预期结果：** 大多数订阅的已过期阶段持续 30 天，其中包括在大多数国家和地区通过 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) 购买的订阅。 对于批量许可产品（Microsoft Open 除外），已过期阶段将持续 90 天。

在这种状态下，用户可以正常访问 Microsoft 365 门户、Office 应用程序以及电子邮件和 SharePoint Online 等服务。
  
作为管理员，你仍然可以访问管理中心。 无需担心 — 全局管理员或账务管理员可以 [重新激活订阅](reactivate-your-subscription.md) 并继续使用 Microsoft 365。 如果不重新激活，请 [备份你的数据](back-up-data-before-switching-plans.md)。
  
### <a name="state-disabled"></a>状态：已禁用

**预期结果：** 如果在订阅过期时不重新激活，订阅将进入禁用阶段，在大多数国家和地区中，此阶段将持续 90 天。对于批量许可产品，禁用阶段将持续 30 天。

在此状态下，访问量会大大降低。 用户无法登录，也无法访问电子邮件或 SharePoint Online 等服务。 Office 应用程序最终会进入只读的缩减功能模式，并显示 [未授权产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380)。 你仍然可以登录并进入管理中心，但不能为用户分配许可证。 你的客户数据 (包括团队网站上的所有用户数据、电子邮件和文件) 都仅向你和其他管理员开放。

作为全局管理员或帐务管理员，你可以 [重新激活订阅](reactivate-your-subscription.md) 并继续使用 Microsoft 365，而且在此期间你的所有客户数据保持不变。如果选择不重新激活，请务必 [备份数据](back-up-data-before-switching-plans.md)。

### <a name="state-deleted"></a>状态：已删除
  
**预期结果：** 如果未重新激活处于已过期或已停用的订阅，则将删除订阅。
  
管理员和用户无法访问订阅时所附带的服务或 Office 应用程序。 将永久删除所有客户数据 (从用户数据到文档和电子邮件)，且无法恢复。
  
此时不能重新激活订阅。但是，作为全局管理员或帐单管理员，你仍然可以访问管理中心来管理其他订阅，或购买新订阅以满足你的业务需求。
  
> [!NOTE]
>
> - 添加已删除的相同类型新订阅，不会恢复与已删除订阅相关联的数据。
> - 如果已停用 CSP 许可，则不享有 30 天的已过期阶段，而是立即停用服务。 如果租户没有通过添加新的许可证来重新激活，则数据将在 90 天后删除。

### <a name="what-happens-when-my-trial-ends"></a>试用期结束之后会出现什么情况？

试用结束后，不能继续免费使用 Microsoft 365。您有几个选项：

- **购买 Microsoft 365。** 试用版到期时，将进入已过期阶段，并提供 30 天（针对大多数国家和地区中的大多数订阅）时间以考虑产品购买 Microsoft 365。 若要了解如何将试用版转换为付费订阅，请参阅 [从免费试用版购买订阅](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial)。
- **延长试用期。** 需要更多时间来评估 Microsoft 365？ 在某些情况下，可以 [延长试用期](../extend-your-trial.md)。
- **取消试用或让它过期。** 如果决定不购买 Microsoft 365，可让试用版到期，或 [取消它](cancel-your-subscription.md)。 备份要保留的所有数据。 30 天已过期阶段之后，将会永久删除试用账户信息和数据。

> [!NOTE]
>
> 本页上的信息受 [Microsoft 政策免责声明和变更通知](https://go.microsoft.com/fwlink/p/?LinkId=613651) 的约束。 定期返回本网站查看有无任何变化。

## <a name="related-content"></a>相关内容

[取消订阅](./cancel-your-subscription.md) (文章)\
[续订 Microsoft 365 商业版](./renew-your-subscription.md) (文章)\
[重新激活订阅](./reactivate-your-subscription.md) (文章)
