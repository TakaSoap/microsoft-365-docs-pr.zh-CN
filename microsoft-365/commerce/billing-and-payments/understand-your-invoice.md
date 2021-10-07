---
title: 了解你的帐单或发票
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 了解如何阅读和了解 Microsoft 商业产品的账单或发票。
keywords: 帐单帐户，组织信息，发票
ms.date: 05/04/2021
ms.openlocfilehash: d6b36d547bfa1610339c2818969d0164a585eeb2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203479"
---
# <a name="understand-your-bill-or-invoice"></a>了解你的帐单或发票

发票提供您的费用摘要和付款说明。 您可以在 Microsoft 365 管理中心中[查看您的在线发票](#view-your-online-invoice)。 您也可以以可移植文档格式（.pdf）下载它，以通过电子邮件发送。

若要查看和打印发票，请：

1. 在 **计费** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">“帐单和付款”</a>页面上，选择发票日期范围。
2. 要打印或保存账单的PDF副本，请选择 **下载发票PDF**，然后打印PDF。

有关详细信息，请参阅[查看账单或发票](view-your-bill-or-invoice.md)。

如果您只有Microsoft 365订阅，请参阅 [了解Microsoft 365商业版的账单或发票](understand-your-invoice2.md)。

## <a name="understand-the-invoice-header"></a>了解发票抬头

第一页的顶部标识了谁负责付款，账单发送到何处以及费用摘要。

| 术语 | 描述 |
| --- | --- |
| 售达地址 |计费帐户，用于标识负责付款的法人实体的名称和地址。 可以在“<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">账单账户</a>”页面上管理此信息，您可以在其中找到帐户协议并管理角色和权限。 |
| 帐单寄往地址 |标识谁收到发票。 可以在“ <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帐单配置文件</a>”页面上管理此信息。 帐单资料也显示在在线发票页面的“**发票摘要**”部分中。 要了解有关帐单资料的更多信息，以及如何使用它们为您的组织构建更灵活的帐单选项，请参阅[管理帐单资料](manage-billing-profiles.md)。 |
| 帐单个人资料 |帐单配置文件的名称，用于定义发票属性，例如“**开单至**”，“**采购单号**”和“付款条件”。 可以在“ <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">帐单配置文件</a>”页面上管理此信息。 有关计费配置文件以及如何使用它们为您的组织构建更灵活的计费选项的更多信息，请参阅[管理计费配置文件](manage-billing-profiles.md)。 |
| 发票号 |Microsoft 生成的唯一的发票编号，用于跟踪。 |
| 发票日期 |生成发票的日期，通常在开票周期结束后的5至12天。 您可以在结算资料详细信息页面上查看发票日期。 计费期结束至发票日期之间发生的费用包含在下个月的发票中，因为它们在下一个计费期。 **发票摘要** 上方发票PDF中列出了每个发票的计费期开始日期和结束日期。|
| 支付期限 |您如何支付 Microsoft 帐单。 *净30天* 是指您在发票日期后的30天内按照发票上的说明付款。 |

## <a name="understand-the-billing-summary"></a>了解帐单摘要

**帐单摘要** 显示上一个帐单期间以来的费用摘要，已应用的任何抵免额，税额和应付款总额。

| 术语 | 描述 |
| --- | --- |
| 费用|在此结算周期内购买的产品总数及其相关的费用和税款。 采购汇总以提供您的帐单的简洁视图。 |
| 制作人员 |您从返回中获得的积分 |
| 已应用Azure积分 |自动应用于Azure的Azure信用额度在每个计费期收费。 如果您没有任何Azure积分，则该字段将被隐藏。 有关Azure信用的详细信息，请参阅[跟踪Microsoft客户协议Azure信用余额](/azure/billing/billing-mca-check-azure-credits-balance)。 |
| Subtotal |应付税前金额 |
| 税款 |您要支付的税款类型和金额，具体取决于您的帐单资料所在的国家/地区。 如果您不必纳税，则发票上不会显示税款。 |

### <a name="understand-your-charges"></a>了解你的费用

收费页面显示按产品细分的成本。 对于Azure客户，费用可以按“发票”部分进行组织。 有关Azure产品如何使用发票部分的更多信息，请参见 [Microsoft 客户协议账单帐户入门](/azure/billing/billing-mca-overview)中的[发票部分](/azure/billing/billing-mca-overview#invoice-sections)。 在每个产品订单中，成本按服务系列细分。

| 术语 |描述 |
| --- | --- |
| 单位价格 | 用于计算费用的服务的有效单价（以定价货币计）。 对于产品，服务系列，仪表和报价，此价格是唯一的。 |
| 数量 | 结算期间购买或消费的数量 |
| 费用/点数 | 扣除信用/退款后的净收费额 |
| Azure 额度 | 应用于费用/点数的Azure 额度金额 |
| 税率 | 税率，取决于国家/地区 |
| 税额 | 根据税率应用于采购的税额 |
| 总计 | 购买的总金额 |

订单项的详细信息取决于您要付费的产品类型。 例如，对于Azure产品，将显示所应用的Azure额度。 座椅产品显示单位价格和数量。 发票明细显示购买的产品，已应用的折扣或抵免额，税率和金额以及行项目总计。

> 总计=费用-Azure 额度+税

每个服务系列的应付款总额是通过从信用/费用中减去Azure信用并加税来计算的：

> 总计=费用/额度-Azure 额度+税

如果您希望发票上有Azure费用，请参见[查看Microsoft客户协议发票](/azure/cost-management-billing/understand/review-customer-agreement-bill)。

## <a name="understand-the-last-invoice-page"></a>了解最后的发票页面

### <a name="payment-instructions"></a>付款说明。

发票底部是有关如何付款的说明。 您可以通过电汇，支票或在线方式付款。

### <a name="publisher-information"></a>发布程序信息

如果您的帐单中包含第三方服务，则发票底部会列出每个发布者的名称和地址。

## <a name="view-your-online-invoice"></a>查看在线发票

发票可在线获得。 PDF发票和电子邮件通知均提供指向在线发票的链接。 在线发票是可扩展的，因此您可以查看发票上的费用并查看每个项目的更多详细信息。 在线发票包括：

- **定价详细信息**&mdash;其他信息，包括有关折扣和产品定价的详细信息。
- **在线付款**&mdash;您可以选择从发票在线付款。
- **Azure成本管理**&mdash;对于Azure客户，在线发票包括指向Azure成本管理的链接。

### <a name="to-view-your-online-invoice"></a>查看在线发票

1. 在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。
2. 要下载发票的.pdf版本，请在要查看的发票行中选择 **“下载发票PDF”**。
3. 要查看您的在线发票，请从列表中选择一个发票。 您也可以从发票详细信息页面下载.pdf。

## <a name="invoice-faq"></a>发票常见问题解答

### <a name="when-is-my-invoice-available"></a>我的发票何时可用？

购买后24小时内会生成一些发票。 其他帐单会在结算期结束时生成，包括该期末的所有项目。

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>如何支付发票上的应付金额？

付款说明取决于您的付款方式，并在发票PDF的底部提供。 如果您的付款方式是信用卡，则会在发票日期后的10天内自动收取费用。 如果您通过支票或电汇方式付款，请参阅PDF中 **“付款说明”** 下的信息。

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>“销售至”和“结算至”地址有什么区别？

- **销售至**：负责付款并在发票上标识的法人实体。 除非您在购买过程中选择提供其他送货地址，否则此处提供的地址用于确定税率。 有关详细信息，请参阅[税务信息](tax-information.md)。
- **结算至**：实际发票发送到的地址（如果适用）。 每个法人实体可以有多个 **结算至** 的地址，但是每个账单配置文件只能有一个 **结算至** 的地址。

### <a name="what-are-billed-amount-and-amount-due"></a>什么是“账单金额”和“应付金额”？

- **帐单金额：** 您购买的总金额。
- **应付金额：** 您所欠款项的余额。

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>“服务期”和“计费期”有什么区别？

- **服务期：** 是就你使用服务进行收费的时间段。
- **计费期：** 是指自上次发票日期起的时间段。

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>为什么我不将Azure预付款视为付款方式？

Azure 预付款仅作为付款方式提供给符合条件的 Azure 产品和服务

## <a name="need-help-contact-support"></a>需要帮助？ 联系支持人员

如果您对Azure信用有疑问或需要帮助，<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">请使用Azure支持创建支持请求</a>。

如果您在Microsoft 365管理中心中对发票有疑问或需要帮助，[请与企业产品支持联系](../../business-video/get-help-support.md)。

## <a name="related-content"></a>相关内容

[了解适用于企业Microsoft 365的](understand-your-invoice2.md)帐单 (发票) \
[跟踪 Microsoft 客户协议 Azure 信用平衡](/azure/billing/billing-mca-check-azure-credits-balance) (文章) \
[查看 Microsoft 客户协议发票](/azure/cost-management-billing/understand/review-customer-agreement-bill) (文章) \
[Microsoft 客户协议计费帐户入门 (](/azure/billing/billing-mca-overview) 文章) 
