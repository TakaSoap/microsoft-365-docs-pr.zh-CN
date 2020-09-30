---
title: 我的订阅结束后对我的数据和访问权限有何影响？
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: 了解当 Microsoft 365 for business 订阅过期、被禁用或取消时数据会发生什么情况。
ms.openlocfilehash: 2c8b21274d7e3e776e62a9a185309d6e742ac2b3
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309178"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Microsoft 365 for business 订阅结束时我的数据和访问会发生什么情况？

如果你的订阅结束（因为它已过期或你决定取消），则在订阅完全关闭之前，你对 Microsoft 365 服务、应用程序和客户数据的访问会经历多个状态，或 *deprovisioned*。 如果你知道这一进展，你将能够更好地将你的订阅恢复到处于活动状态过晚的状态，或者，如果你离开 Microsoft 365，请先备份你的数据，然后再将其最终删除。

请阅读此重要信息，然后再联系 [Microsoft 365 支持部门](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)。
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>订阅过期时数据会发生什么情况？

- 如果你的订阅已过期，则会经历以下阶段：已过期/已禁用/Deprovisioned。 过期的阶段在订阅到达其结束日期后立即开始。
- 如果您关闭年度订阅的定期帐单，它会经历与过期订阅相同的阶段。 第一阶段的开始是每年订阅的周年纪念，而不是在关闭订阅的定期记帐设置的日期上启动的。
- 如果取消每月订阅，则会在取消) 时立即禁用 (。 这意味着您的用户将立即失去对 Microsoft 365 资产的访问权限，并且只有管理员才能在接下来的90天访问数据。

下表介绍了付费 Microsoft 365 for business 订阅过期时的预期效果。

| **Active**                                                             | **过期 <br/> (30 天 \*) **                                                | **已禁用 <br/> (90 天 \*) **                                               | **已取消设置**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *所有可访问的数据*                                               | *所有可访问的数据*                                                     | *仅供管理员访问的数据*                                             | **删除了数据删除的 <br/> Azure Active Directory （如果未被其他服务使用）** |
| 用户具有对 Microsoft 365、文件和应用程序的常规访问权限   | 用户具有对 Microsoft 365、文件和应用程序的常规访问权限              | 用户无法访问 Microsoft 365、文件或应用程序                        | 用户无法访问 Microsoft 365、文件或应用程序                                     |
| 管理员具有对 Microsoft 365、数据和 Office 应用程序的常规访问权限 | 管理员可以访问管理中心                                           | 管理员可以访问管理中心，但不能向用户分配许可证       | 管理员可以访问管理中心来购买和管理其他订阅             |
|                                                                        | 全局管理员或帐单管理员可以在管理中心重新激活订阅 | 全局管理员或帐单管理员可以在管理中心重新激活订阅 |                                                                                           |

* 在大多数国家和地区，大多数产品提供。
  
> [!NOTE]
> **什么是 "客户数据"？** 客户数据（如 [Microsoft Online 服务条款](https://go.microsoft.com/fwlink/p/?LinkId=613649)中所定义）是指所有数据，包括所有的数据，包括由客户通过 microsoft 365 服务提供给 microsoft 的所有文本、声音或图像文件。 若要了解有关客户数据保护的详细信息，请参阅 [Microsoft 服务信任门户入门](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal)。

## <a name="what-happens-if-i-cancel-a-subscription"></a>如果我取消订阅会发生什么情况？

如果您在期限结束日期之前取消了订阅，订阅将跳过已过期状态并直接移到禁用状态，在大多数国家和地区中，大多数订阅为90天。 建议您在取消之前 [备份数据](back-up-data-before-switching-plans.md) ，但作为管理员，您仍可以访问和备份您的组织的数据，同时处于禁用状态。 你留下的任何客户数据都可能在取消的 90 天之后、180 天之前被删除。
  
如果取消订阅，则会为你和你的用户提供预期。
  
- **管理员访问** 管理员仍可以登录并访问管理中心，并根据需要购买其他订阅。 作为全局或帐单管理员，你有90天的时间来 [重新激活订阅](reactivate-your-subscription.md) 的所有数据都完好无损。

- **用户访问** 您的用户不能使用 OneDrive for Business 等服务，也不能访问客户数据，例如，电子邮件或工作组网站上的文档。 Word 和 Excel 等 Office 应用程序最终将进入只读的缩减功能模式，并显示 [未经授权的产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。

若要了解如何取消，请参阅 [取消订阅](cancel-your-subscription.md)。
  
> [!IMPORTANT]
> 如果您希望在典型禁用的时段之前删除订阅数据，则可以 [关闭您的帐户](../close-your-account.md)。
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>如果我的订阅即将过期，我的选项是什么？

订阅处于活动状态时，您和最终用户对数据具有常规访问权限，如电子邮件和 OneDrive for Business，以及 Office 应用程序等服务。 作为管理员，你将在你的订阅临近到期日期时通过电子邮件和管理中心收到一系列通知。
  
订阅的到期日期真正到来之前，你有一些选择：

::: moniker range="o365-worldwide"
  
- **为订阅启用定期帐单。**

  - 如果 **定期记帐** 已打开，则无需执行任何操作。 你的订阅将自动记帐，并根据你当前的付款频率向你收取额外的一年或一个月。 如果您已关闭 **定期付费** 的任何原因，您始终可以 [重新启用定期付费](renew-your-subscription.md)。

  - 如果使用预付卡购买了 Microsoft 365 的商业应用程序，则可以为订阅 [启用定期帐单](renew-your-subscription.md) 。

  - 如果你是一位预付一年期免费订阅的批量许可客户，请联系你的合作伙伴购买新的产品密钥。 你将通过电子邮件收到说明，以在 [批量许可服务中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)中激活你的密钥。 若要了解如何查找新合作伙伴或以前使用过的合作伙伴，请参阅 [查找合作伙伴或经销商](../../admin/manage/find-your-partner-or-reseller.md)。

  - 如果你有 Microsoft 365 应用程序的商业版，请参阅 [管理你的订阅的定期帐单](renew-your-subscription.md)。

- **允许订阅过期。**

  - 如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭 [定期付费](renew-your-subscription.md)。 您的订阅将在其到期日期结束，并且您可以忽略所有相关的电子邮件通知。

  - 如果您是与合作伙伴合作的开放式批量许可客户，您可以通过不采取任何措施让订阅过期。

  - 如果你是 Office 365 小型企业高级版客户，并且你预付 Office 365 并使用产品密钥激活它，则可以通过不采取任何措施让你的订阅过期。

- **在订阅过期之前取消。** 有关详细信息，请参阅 [取消订阅](cancel-your-subscription.md)。
  
::: moniker-end

::: moniker range="o365-germany"
  
- **管理订阅的定期帐单。**

  - 如果 **定期记帐** 已打开，则无需执行任何操作。 系统将自动对你的订阅计费，并且将根据你当前的付款频率，向你另外收取一年或一个月的费用。 如果您已关闭 **定期付费** 的任何原因，您始终可以 [重新启用定期付费](renew-your-subscription.md)。

  - 如果使用预付卡购买了 Microsoft 365 的商业应用程序，则可以为订阅 [启用定期帐单](renew-your-subscription.md) 。

  - 如果你是一位预付一年期免费订阅的批量许可客户，请联系你的合作伙伴购买新的产品密钥。 你将通过电子邮件收到说明，以在 [批量许可服务中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)中激活你的密钥。 若要了解如何查找新合作伙伴或以前使用过的合作伙伴，请参阅 [查找合作伙伴或经销商](../../admin/manage/find-your-partner-or-reseller.md)。

  - 如果你有 Microsoft 365 应用程序的商业版，请参阅 [续订订阅](renew-your-subscription.md)。

- **允许订阅过期。**

  - 如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭 [定期付费](renew-your-subscription.md)。 你的订阅将在到期日期后过期，你可以忽略所有相关的电子邮件通知。

  - 如果您是与合作伙伴合作的开放式批量许可客户，您可以通过不采取任何措施让订阅过期。

  - 如果你是 Office 365 小型企业高级版客户，并且你预付 Office 365 并使用产品密钥激活它，则可以通过不采取任何措施让你的订阅过期。

- **在订阅过期之前取消。** 有关详细信息，请参阅 [取消订阅](cancel-your-subscription.md)。
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **续订订阅。** 如果 **定期记帐** 已打开，则无需执行任何操作。 系统将自动对你的订阅计费，并且将根据你当前的付款频率，向你另外收取一年或一个月的费用。 如果您已关闭 **定期付费** 的任何原因，您始终可以 [重新启用定期付费](renew-your-subscription.md)。

- **允许订阅过期。** 如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭 [定期付费](renew-your-subscription.md)。 你的订阅将在到期日期后过期，你可以忽略所有相关的电子邮件通知。

- **在订阅过期之前取消。** 有关详细信息，请参阅 [取消订阅](cancel-your-subscription.md)。

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>我的订阅过期后会发生什么？
如果你的订阅过期，它会在最终删除前经历多个状态。 如果您想要继续执行该服务，或在决定不再需要订阅时备份您的数据，这将使您（作为管理员、重新激活的时间）。
  
以下是你的订阅处于每种状态时的预期效果。
  
### <a name="state-expired"></a>状态：已过期
  
::: moniker range="o365-worldwide"

 **预期内容：** 过期状态将为大多数订阅（包括在大多数国家和地区中通过 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)购买的订阅）持续30天。 对于批量许可产品，除了 Microsoft 开放之外，过期状态将持续90天。

::: moniker-end

::: moniker range="o365-germany"

 **预期内容：** 过期状态将为大多数订阅（包括在大多数国家和地区中通过 [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)购买的订阅）持续30天。 对于批量许可产品，除了 Microsoft 开放之外，过期状态将持续90天。

::: moniker-end

::: moniker range="o365-21vianet"

 **预期内容：** 在大多数国家和地区，过期状态为大多数订阅的30天。

::: moniker-end

在此状态下，用户可以正常访问 Microsoft 365 门户、Office 应用程序和服务（如电子邮件和 SharePoint Online）。
  
作为管理员，你仍然可以访问管理中心。 别担心，全局或帐单管理员可以 [重新激活订阅](reactivate-your-subscription.md) 并继续使用 Microsoft 365。 如果你不重新激活，请 [备份你的数据](back-up-data-before-switching-plans.md)。
  
### <a name="state-disabled"></a>状态：已禁用
  
::: moniker range="o365-worldwide"

 **预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则它将进入禁用状态，这在大多数国家和地区中会在大多数订阅中持续90天。 对于批量许可产品，禁用状态将持续30天。

::: moniker-end

::: moniker range="o365-germany"

 **预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则它将进入禁用状态，这在大多数国家和地区中会在大多数订阅中持续90天。 对于批量许可产品，禁用状态将持续30天。

::: moniker-end

::: moniker range="o365-21vianet"

 **预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则会在大多数国家和地区中将其移至禁用状态，即大多数订阅的90天。

::: moniker-end

::: moniker range="o365-worldwide"

在此状态下，您的访问会显著降低。 您的用户无法登录，或者无法访问电子邮件或 SharePoint Online 等服务。 Office 应用程序最终将移动到只读、缩减功能模式，并显示未 [授权的产品通知](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。 您仍可以登录并进入管理中心，但不能向用户分配许可证。 您的客户数据（包括所有用户数据、电子邮件和工作组网站上的文件）仅供您和其他管理员使用。

::: moniker-end

作为全局管理员或帐单管理员，你可以 [重新激活订阅](reactivate-your-subscription.md) ，并继续使用 Microsoft 365，让你的所有客户数据保持不变。 如果你选择不重新激活，请 [备份你的数据](back-up-data-before-switching-plans.md)。

### <a name="state-deprovisioned"></a>状态： Deprovisioned
  
 **预期内容：** 如果您在您的订阅处于宽限期或已禁用状态时不重新激活它，则该订阅是 deprovisioned。
  
管理员和用户不再有权访问订阅附带的服务或 Office 应用程序。 所有客户数据（从用户数据到文档和电子邮件）都将被永久删除且不可恢复。
  
此时，无法重新激活订阅。 但是，作为全局或帐单管理员，你仍可以访问管理中心来管理其他订阅，或购买新订阅以满足你的业务需求。
  
> [!NOTE]
> 添加已 deprovisioned 的相同类型的新订阅不会还原与 deprovisioned 订阅关联的数据。

### <a name="what-happens-when-my-trial-ends"></a>我的试用版结束时会发生什么？

试用版结束后，将无法继续使用 Microsoft 365 免费版。 您有几个选项：

::: moniker range="o365-worldwide"

- **购买 Microsoft 365。** 试用期到期后，它会移动到宽限期，在大多数国家和地区，在大多数国家和地区) 购买 Microsoft 365，这会将您的时间 (一段时间。 若要了解如何将试用版转换为付费订阅，请参阅 [购买试用版的 Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md)。

::: moniker-end

::: moniker range="o365-germany"

- **购买 Microsoft 365。** 试用期到期后，它会移动到宽限期，在大多数国家和地区，在大多数国家和地区) 购买 Microsoft 365，这会将您的时间 (一段时间。 若要了解如何将试用版转换为付费订阅，请参阅 [购买试用版的 Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md)。

::: moniker-end

::: moniker range="o365-21vianet"

- **购买 Office 365。** 试用期到期后，它会移动到宽限期，并在大多数国家和地区) 购买 Office 365，从而为您提供了30天 (的时间。 若要了解如何将试用版转换为付费订阅，请参阅 [购买或尝试订阅由世纪互联运营的 Office 365](../../admin/services-in-china/buy-or-try-subscriptions.md)。

::: moniker-end

- **延长试用版。** 需要更多时间来评估 Microsoft 365？ 在某些情况下，您可以 [延长试用版](../extend-your-trial.md)。

- **取消试用版或让其过期。** 如果你决定不购买 Microsoft 365，你可以让你的试用版过期或 [取消](cancel-your-subscription.md)。 备份要保留的任何数据。 30天宽限期后不久，你的试用帐户信息和数据将被永久删除。

> [!NOTE]
> 此页面上的信息受 [Microsoft 策略免责声明和更改通知](https://go.microsoft.com/fwlink/p/?LinkId=613651)的制约。 定期返回到此网站以查看任何更改。

## <a name="related-content"></a>相关内容 

[取消订阅](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (文章) \
[续订 Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (文章) \
[重新激活订阅](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (文章) 