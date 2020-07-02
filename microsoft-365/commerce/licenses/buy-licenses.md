---
title: 购买或删除订阅许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何购买更多许可证或减少 Microsoft 365 for business 订阅的许可证数量。
ms.date: 07/01/2020
ms.openlocfilehash: 85861379bbce30c3c071a47529d516d7d5170e39
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015895"
---
# <a name="buy-or-remove-subscription-licenses"></a>购买或删除订阅许可证

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

您可以通过以下步骤购买更多许可证或减少订阅的许可证数量。

## <a name="before-you-begin"></a>准备工作

- 您必须是全局管理员或帐单管理员才能购买许可证。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。
- 您可以[添加用户并同时分配许可证](../../admin/add-users/add-users.md)。

## <a name="buy-or-remove-licenses-for-your-business-subscription"></a>为你的业务订阅购买或删除许可证

::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 查找要为其购买或删除许可证的订阅，然后选择 "**添加/删除许可证**"。 [如果看不到 "添加/删除许可证" 链接，该怎么办？](#what-if-you-dont-see-the-addremove-licenses-link)
3. 在 "**许可证总数**" 框中，输入此订阅所需的许可证总数，然后选择 "**提交更改**"。 例如，如果您有100个许可证，并且想要添加5个，请输入105。 如果要删除其中5个，请输入95。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>”页面。
2. 在 "**订阅**" 页上，选择要为其购买或删除许可证的订阅，然后选择 "**添加/删除许可证**"。 [如果看不到 "添加/删除许可证" 链接，该怎么办？](#what-if-you-dont-see-the-addremove-licenses-link)
3. 在 "**许可证总数**" 框中，输入此订阅所需的许可证总数，然后选择 "**提交** \> **关闭**"。 例如，如果您有100个许可证，并且想要添加5个，请输入105。 如果要删除五个许可证，请输入95。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>”页面。
2. 在 "**订阅**" 页上，选择要为其购买或删除许可证的订阅，然后选择 "**添加/删除许可证**"。 [如果看不到 "添加/删除许可证" 链接，该怎么办？](#what-if-you-dont-see-the-addremove-licenses-link)
3. 在 "**许可证总数**" 框中，输入此订阅所需的许可证总数，然后选择 "**提交** \> **关闭**"。 例如，如果有 100 个许可证并需要再添加 5 个，请输入 105。 如果要删除5个，请输入95。

::: moniker-end

> [!NOTE]
> 如果当前已向用户分配了所有许可证，则无法减少订阅的许可证数。 若要减少许可证数量，请首先[从用户中取消分配一个或多个许可证](../../admin/manage/remove-licenses-from-users.md)，然后从订阅中删除许可证。

## <a name="what-if-you-dont-see-the-addremove-licenses-link"></a>如果看不到 "添加/删除许可证" 链接，该怎么办？

此表介绍 "**添加/删除许可证**" 链接不可用的原因，以及您可以执行的操作。

|原因  |说明  |解决方案  |
|---------|---------|---------|
|正在等待信用检查。 |如果信用检查挂起，您将看到 "挂起的信用检查" 消息。 在信用检查完成之前，你无法购买许可证。  | 稍后再次查看以查看是否已完成信用检查。 信用检查通常需要两个工作日才能完成。<br/>在信用检查完成后，您应该会看到 "**添加/删除许可证**" 链接。 |
|您使用产品密钥激活了订阅。| 如果订阅是使用25个字符的产品密钥购买和激活的，则会看到 "预付" 文本。  |请参阅[向使用产品密钥支付的订阅添加许可证](add-licenses-using-product-key.md)。 |
|您通过合作伙伴购买了订阅。 | 如果订阅是通过合作伙伴购买的，则会看到 "批量许可服务中心（VLSC）" 链接。 | 请参阅[向通过批量许可服务中心购买的订阅添加许可证](add-licenses-bought-through-vlsc.md)。 |
|您通过转销商购买了订阅。|| 如果订阅是通过云解决方案提供商（CSP）合作伙伴购买的，请联系你的 CSP 合作伙伴以购买更多许可证。        |
|你有试用版订阅。 |试用版的 Microsoft 365 显示文本 "试用版"。 | 首先购买试用订阅，然后可以添加更多许可证。 请参阅[从免费试用版购买 Microsoft 365 for business 订阅](../buy-a-subscription-from-your-free-trial.md)。|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>你需要了解的有关为你的业务订阅购买许可证的相关信息

### <a name="license-availability"></a>许可证可用性

- **如果你有付费配置文件**：为订阅购买更多许可证后，就会立即收取与你的帐单配置文件关联的信用卡费用。 许可证立即可供您分配给用户。 [什么是付费配置文件？](../billing-and-payments/manage-billing-profiles.md)
- **如果你没有帐单配置文件**：如果你通过信用卡或借记卡或银行帐户支付订阅，则在收到订单确认后，你购买的任何新许可证都将立即可用。 如果通过发票支付，可能必须等待完成信用检查才能使用新许可证。
  > [!NOTE]
  > 某些国家或地区不支持银行帐户支付。
- **如果你使用产品密钥预付订阅**：你可以通过添加信用卡或借记卡或银行帐户来添加更多许可证，以涵盖新许可证的额外成本。 购买新许可证后，我们将添加第二个订阅，其中包含刚添加的新许可证的数量。 例如，如果您有一个具有五个许可证的预付订阅，然后购买了10个以上的许可证，则会看到列出了两个订阅：一个具有五个预付许可证，另一个具有10个新许可证。

### <a name="changing-your-payment-method"></a>更改支付方式

- **如果你有付费配置文件**：为订阅购买更多许可证后，就会立即收取与你的帐单配置文件关联的信用卡费用。 [什么是付费配置文件？](../billing-and-payments/manage-billing-profiles.md)
- **如果您没有帐单配置文件：** 如果通过信用卡、借记卡或银行帐户支付，则购买新许可证的费用将在两天内显示在付款方式中。

### <a name="billing-statements"></a>计费语句

- 在付费期限中间添加的许可证将显示在下一张发票上。 如果你每年支付，则会在一个月内为这些更改开票。
- 在下一个帐单声明中，将扣除原始许可证数量的前一项费用。 我们将按原始数量的许可证为时间段添加按比例计费的费用，并为新许可证计数添加费用。 此外，还会对你的计费期间的剩余许可证计数收取费用。

## <a name="next-steps"></a>后续步骤

如果你为你的订阅购买了更多许可证，应执行的下一步是[将这些许可证分配给组织中的用户](../../admin/manage/assign-licenses-to-users.md)。

如果你由于某人已离开你的组织而减少了你的订阅的许可证数，则可能需要删除该用户的帐户。 若要了解详细信息，请参阅[删除以前的员工](../../admin/add-users/remove-former-employee.md)。

## <a name="related-content"></a>相关内容

[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)（文章） \
[了解订阅和许可证](subscriptions-and-licenses.md)（文章） \
[试用或购买 Microsoft 365 订阅](../try-or-buy-microsoft-365.md)（文章）