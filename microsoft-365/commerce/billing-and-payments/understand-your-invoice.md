---
title: 了解发票
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解如何阅读和了解 Microsoft 商业产品的发票。
keywords: 帐单帐户、组织信息、发票
ms.openlocfilehash: dad635df97e9cdf490118adc3a041c876878521b
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141324"
---
# <a name="understand-your-invoice"></a>了解发票

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理员中心正在更改。 如果你的体验与此处提供的详细信息不匹配，请参阅[关于新的 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

发票提供了您的费用摘要和付款说明。 你可以在 Microsoft 365 管理中心[查看你的联机发票](#view-your-online-invoice)。 您还可以将其下载为可移植文档格式（.pdf）以通过电子邮件发送。

如果你只有 Microsoft 365 订阅，请参阅[了解适用于 microsoft 365 商业](understand-your-invoice2.md)版的发票。

## <a name="understand-the-invoice-header"></a>了解发票抬头

第一页的顶部标识谁负责付款、向其发送帐单的目标以及费用汇总。

| 术语 | 描述 |
| --- | --- |
| 售出 |标识负责付款的法人的名称和地址的帐单帐户。 可以在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">记帐帐户</a>" 页上管理此信息，您可以在其中找到帐户协议并管理角色和权限。 |
| 付款人 |标识谁接收发票。 可以在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">计费配置文件</a>" 页上管理此信息。 计费配置文件也显示在 "**发票摘要**" 部分的 "联机发票" 页上。 若要了解有关计费配置文件以及如何使用它们为组织生成更灵活的记帐选项的详细信息，请参阅[管理计费配置文件](manage-billing-profiles.md)。 |
| 计费配置文件 |用于定义发票属性（如付款人、PO 号和付款期限）的计费配置文件的名称。 可以在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">计费配置文件</a>" 页上管理此信息。 有关计费配置文件以及如何使用它们为组织生成更灵活的记帐选项的详细信息，请参阅[管理计费配置文件](manage-billing-profiles.md)。 |
| 发票编号 |用于跟踪目的的、由 Microsoft 生成的唯一发票编号。 |
| 发票日期 |生成发票的日期，通常是在记帐周期结束后的5到12天。 您可以在 "记帐配置文件详细信息" 页上查看您的发票日期。 在帐单期初和发票日期之间发生的费用包括在下个月的发票中，因为它们在下一个帐单期内。 每张发票的帐单期开始和结束日期都在发票 PDF 中的**记帐摘要**中列出。|
| 支付期限 |如何为你的 Microsoft 帐单付费。 *30 天*后，即在发票日期的30天内，按照发票上的说明付费。 |

## <a name="understand-the-billing-summary"></a>了解帐单摘要

**记帐摘要**显示自上次计费期、已应用的任何信用额度、税和到期总额的费用汇总。

| 术语 | 描述 |
| --- | --- |
| 费用|此计费期间购买的产品总数及其相关的费用和税款。 对采购进行聚合，以提供帐单的简明视图。 |
| 制作人员 |从退货中接收的信用 |
| 应用的 Azure 信用 |将自动应用于 Azure 的你的 Azure 信用费用将收取每个帐单期。 如果你没有任何 Azure 信用，此字段将被隐藏。 有关 Azure 信用的详细信息，请参阅[跟踪 Microsoft 客户协议 Azure 信用余额](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)。 |
| Subtotal |税前金额 |
| 税款 |根据帐单配置文件的国家/地区，支付的类型和金额。 如果您无需支付税，发票上不会显示任何税。 |

### <a name="understand-your-charges"></a>了解你的费用

费用页面显示按产品细分的成本。 对于 Azure 客户，费用可能按发票部分进行组织。 有关如何将发票部分用于 Azure 产品的详细信息，请参阅[Microsoft 客户协议帐单帐户入门](https://docs.microsoft.com/azure/billing/billing-mca-overview)中的 "[发票" 部分](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections)。 在每个产品订单中，成本按服务系列划分。

| 术语 |描述 |
| --- | --- |
| 单价 | 用于计算费用的服务的有效单位价格（以定价币种为单位）。 此价格是产品、服务系列、计量器和优惠的独特价格。 |
| 数量 | 计费期间购买或消耗的数量 |
| 费用/片尾 | 应用信用/退款后的费用净额 |
| Azure 信用 | 适用于费用/片尾的 Azure 信用量 |
| 税率 | 税率（取决于国家/地区） |
| 税额 | 根据税率应用到采购的税金金额 |
| 总计 | 购买的到期总金额 |

行项目详细信息取决于所收费产品的类型。 例如，对于 Azure 产品，将显示应用的 Azure 点数的数量。 基于座位的产品显示单价和数量。 发票详细信息概述了已购买的产品、已应用的折扣或片尾、税率和金额以及明细项目总计。

`Total = Charges - Azure Credit + Tax`

每个服务系列的到期总金额是通过从信用/费用中减去 Azure 信用和加税来计算的：

`Total = Charges/Credits - Azure Credit + Tax`

如果你希望更详细了解你的发票上的 Azure 费用，请参阅[查看你的 Microsoft 客户协议发票](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)。

## <a name="understand-the-last-invoice-page"></a>了解 "最后一张发票" 页

### <a name="payment-instructions"></a>付款说明

在发票底部是有关如何支付帐单的说明。 您可以通过有线、支票或在线付款。

### <a name="publisher-information"></a>发布程序信息

如果你的帐单中有第三方服务，则每个发布者的名称和地址都将列在发票底部。

## <a name="view-your-online-invoice"></a>查看你的联机发票

发票可在线使用。 您的联机发票的链接可从您的 PDF 发票和电子邮件通知中获取。 联机发票是可展开的，以便查看发票上的费用并查看每个项目的更多详细信息。 联机发票包括：

- **定价详细** &mdash;信息，包括有关折扣和产品定价的详细信息。

- **在线付款** &mdash;您可以选择将付款从发票联机。

- Azure **cost management** &mdash; For azure 客户，在线发票包含指向 Azure 成本管理的链接。

### <a name="to-view-your-online-invoice"></a>查看联机发票

1. 在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。

2. 若要下载发票的 .pdf 版本，请选择要查看的发票所在行中的 "**下载发票 pdf** "。

3. 若要查看你的联机发票，请从列表中选择一个发票。 您还可以从 "发票详细信息" 页下载 .pdf 文件。

## <a name="need-help-contact-support"></a>需要帮助？ 请联系支持人员。

如果你在使用 Azure 信用时遇到疑问或需要帮助，请<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">创建支持 azure 支持的支持请求</a>。

如果你在 Microsoft 365 管理中心中对发票有任何疑问或需要帮助，请[联系业务产品支持人员](../../admin/contact-support-for-business-products.md)。
