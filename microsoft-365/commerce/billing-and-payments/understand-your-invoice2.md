---
title: 了解 Office 365 商业版发票
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
ms.custom:
- TopSMBIssues
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 0724b428-fb59-4962-8c37-6674166d7507
description: 了解如何在 Office 365 for business 发票上解释费用、帐单和付款信息，以及如何更改采购订单编号。
ms.openlocfilehash: 2cb95b49136c186158d3b8ba3fe868d2c863e0de
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238395"
---
# <a name="understand-your-invoice-for-office-365-for-business"></a>了解 Office 365 商业版发票

每月你都会收到一封电子邮件，告知你的新帐单声明在管理中心中可用。 [了解如何查找和查看你的帐单或发票](view-your-bill-or-invoice.md)。
  
你的发票包含两页。第 1 页是发票摘要，包含有关发票、订单、到期金额、付款方式和联系支持人员的方式等一般信息。
  
![Page 1 of a sample invoice.](../../admin/media/b2f2cf85-a005-4f8a-a7b7-bea231372025.png)
  
第 2 页包含有关每个订阅的帐单活动的详细信息。
  
![Page 2 of a sample invoice.](../../admin/media/808195cb-b1d2-4492-a748-29671ccecdd2.png)
  
有关发票中所含字段和术语的说明，请参阅本文稍后部分中的[发票字段术语](#invoice-field-glossary)。
  
## <a name="understand-billing-concepts"></a>了解帐单概念

在查看发票之前，有必要了解一些关键的帐单概念。
  
### <a name="invoice-balance-vs-order-balance"></a>发票余额和订单余额

 **发票余额** 是指发票上显示的数额，且仅表示针对该特定计费周期的到期金额。 总 **订单余额** 是所有未付款发票的总和。 您可以在管理中心的 "**帐单**" 部分查看订单余额。
  
### <a name="billing-frequency-vs-invoice-frequency"></a>记帐频率和开票频率

 **记帐频率** 是指向你收费的频率。 订阅将根据每月或每年计费，具体取决于订阅购买过程中选择的选项。 **开票频率** 是指你收到发票的频率。 如果你选择每年计费，则每年仅会收到一张发票，除非你的订阅活动需要收费或用信用卡付款。
  
如果你有多个订单，则每份订单都会出具一张发票。
  
## <a name="invoice-field-glossary"></a>发票字段术语

下表介绍了发票上可能显示的字段。此处列出的某些字段可能未在发票中显示，具体取决于是通过发票还是通过信用卡或银行帐户付款。
  
> [!NOTE]
> 在某些国家或地区不提供按银行帐户付款。
  
|**名称**|**说明**|
|:-----|:-----|
|年度价格|订阅每月或每年计费一次。 如果您在购买订阅期间选择了 "年度帐单"，则该发票上的年许可证价格将反映出来。 如果想要更改记帐频率，则必须取消订阅并使用新的记帐频率进行购买。|
|计费周期|计费周期是指自上次发票日期起的时间段。服务期是就你使用服务进行收费的时间段。|
|帐单寄往地址|这是你帐单部门的地址，通常与售达地址相同。 若要更新帐单邮寄地址，请参阅[更改帐单邮寄地址](change-your-billing-addresses.md)。|
|费用|发票的第 1 页将汇总发票计费周期的所有费用。第 2 页显示每个订阅的详细费用。|
|支票|如果你通过发票支付，并且你所在国家/地区支持支票付款，则第 1 页的底部将包括付款寄往地址的相关信息。请参考支票上的发票号。|
|贷项|发票的第 1 页将汇总发票计费周期的所有贷项。第 2 页显示每个订阅的详细贷项。|
|客户 PO 编号|你的采购订单 (PO) 编号。如果你更新 PO 编号，则之后的发票将显示该项。[更改采购订单编号](#change-your-purchase-order-number)<br/> **注释**您不能将 PO 号码添加到现有发票。           |
|天数|每个计费交易都与服务期相关联。"天数"列指示该服务期的天数。|
|折扣|发票的第 1 页将汇总发票计费周期的所有折扣。第 2 页显示每个订阅的详细折扣。|
|截止日期|发票的付款截止日期。如果订阅使用信用卡或银行帐户进行支付，我们将在发票日期后向信用卡或银行帐户收费。<br/> **注释**在某些国家或地区不提供按银行帐户付款。           |
|电子资金转帐|如果选择 "发票" 作为订阅支付方式，则第1页包含用于电子（电线、ACH、SEPA 等）付款的 Microsoft 银行帐户信息。 通常，银行会出具你在发送付款时填写的参考字段。 请参考此字段中显示的发票编号。|
|总计|此行包括所有费用、折扣、贷项、分类汇总和税款的总和，以及发票上针对所有订阅的全部列。|
|发票日期|发票的创建日期。发票日期是指计费周期结束后的日期。例如，如果你的计费周期为 1 月 15 日 - 2 月 14 日，则你的发票日期为 2 月 15 日。|
|发票号|分配给你发票的唯一编号。请参考你付款的发票号。|
|月度价格|订阅每月或每年计费一次。 如果您在购买订阅期间选择了 "每月计费"，则发票上将反映每月的许可证价格。 如果想要更改记帐频率，则必须取消订阅并使用新的记帐频率进行购买。|
|订单编号|每次购买新订阅时，都会创建一份订单。每月都会收到每份订单的发票。|
|付款说明|如果你使用信用卡支付，将会看见"不支付 - 已向存档信用卡收费。"如果通过发票支付，则将看到通过电子资金转帐 (EFT) 和支票（如适用）支付的说明。|
|付款期限|自发票截止付款日期起的天数。标准为 30 天。|
|产品|发票第 1 页中的"联机服务"是用于描述你的订阅的通用名称。第 2 页上将显示每个订阅的名称。|
|数量|服务期间购买的许可证数量。|
|服务期|服务期是就你使用服务进行收费的时间段。帐单期是自上次发票日期后的时间段。|
|服务使用地址|表示正在使用服务的地址，通常与你的售达地址相同。 若要更新服务使用地址，请参阅[更改帐单地址](change-your-billing-addresses.md)。|
|售达地址|你的公司名称和地址。若要更新此信息，请参阅[更改你组织的地址、技术联系人电子邮件和其他信息](../../admin/manage/change-address-contact-and-more.md)。  |
|计算|发票上列出的每个订阅都具有针对所有费用、折扣、贷项、分类汇总和税款的单独分类汇总行，以及所有针对该订阅的列。|
|税款|发票的第 1 页显示税款总额。第 2 页显示所采用的税率，以及各行项目的税款总额。如果你的发票包含税款而你的公司是免税的，请[联系支持人员](../../admin/contact-support-for-business-products.md)。  |
|总计|发票计费周期的到期金额。|

## <a name="change-your-purchase-order-number"></a>更改采购订单编号

如果通过发票付款，可以添加或更改订阅的采购订单 (PO) 编号。
  
> [!NOTE]
> 不得在现有发票上添加 PO 编号。该 PO 编号将显示在以后的所有发票上。

::: moniker range="o365-worldwide"

### <a name="use-the-new-admin-center-to-change-your-purchase-order-number"></a>使用新管理中心更改你的采购订单编号

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品和服务</a>”页面。

2. 如果处于**表格**视图中，请选择 "**卡片**" 切换视图。

3. 查找要更改的订阅。

4. 在 "**记帐**" 部分的 "**发票**" 旁边，选择 "**编辑**"。

5. 在 "**编辑付款详细信息**" 窗格的底部，输入您的订单编号，然后选择 "**保存**"。

### <a name="use-the-old-admin-center-to-change-your-purchase-order-number"></a>使用旧管理中心更改采购订单编号

1. 在管理中心中，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">订阅</a>" 页。

2. 选择要更改的订阅，在 "**付款方式**" 部分，选择 "**更新付款详细信息**"。

3. 在 "**更新付款详细信息**" 窗格中，选择 "**不感谢**"。

4. 在 "**更新付款详细信息**" 窗格的底部，输入您的 PO 号码，选择 "**提交**"，然后单击 "**关闭**"。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>" 页。

2. 选择要更改的订阅，并在 "**付款方式**" 部分，选择 "**更改付款详细信息**"。

3. 在 "**更改付款详细信息**" 窗格的底部，输入您的订单编号，然后选择 "**提交**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>" 页。

2. 选择要更改的订阅，并在 "**付款方式**" 部分，选择 "**更改付款详细信息**"。

3. 在 "**更改付款详细信息**" 窗格的底部，输入您的订单编号，然后选择 "**提交**"。

::: moniker-end

## <a name="related-articles"></a>相关文章

[支付 Office 365 商业版订阅费用](pay-for-your-subscription.md)

[Minecraft:Education Edition 付款方式](https://go.microsoft.com/fwlink/p/?linkid=838761)