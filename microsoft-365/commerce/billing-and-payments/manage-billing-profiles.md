---
title: 了解计费配置文件
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: 了解计费配置文件如何支持发票。
ms.openlocfilehash: 7f4c0aed1bccd0e5df5b09e15e6201933e937993
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576945"
---
# <a name="understand-billing-profiles"></a>了解计费配置文件

对于从 Microsoft 购买产品和服务的商业客户，帐单配置文件允许您自定义发票中包含的项目以及如何支付发票费用。

计费配置文件包括以下信息：

- **计费帐户** &ndash; 配置文件相关的计费帐户的名称
- **付款方式** &ndash; 信用卡或借记卡、银行帐户、支票或数据传输
- **联系人信息** &ndash; 帐单邮寄地址和联系人姓名
- **发票设置** &ndash; 基于计费帐户的国家/地区、可选 PO 编号以及接收作为电子邮件附件的发票的选项的货币
- **权限** &ndash; 允许您更改计费配置文件、支付帐单或使用帐单配置文件上的付款方式进行购买的权限

使用计费配置文件来控制你的购买并自定义你的发票。 为使用计费配置文件购买的产品生成每月发票。 你可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。

首次购买时，系统会自动为帐单帐户创建计费配置文件。 可以在"计费配置文件"页上创建计费 <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">配置文件</a> 以设置更多发票。 例如，为组织的每个部门进行购买时，可以使用不同的计费配置文件。 下一个计费日期，你将收到每个计费配置文件的发票。

## <a name="billing-profile-roles"></a>计费配置文件角色

帐单配置文件上的角色具有控制购买以及查看和管理发票的权限。 向跟踪、组织和支付发票的用户分配这些角色，例如组织中采购团队成员。

| Role                          | 说明                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 计费配置文件所有者         | 管理计费配置文件的所有内容                                           |
| 计费配置文件参与者   | 管理计费配置文件中的权限之外的所有内容                         |
| 计费配置文件读取器        | 帐单配置文件中所有项的只读视图                                 |
| 发票管理器               | 查看和支付帐单，并且对帐单配置文件中所有内容具有只读视图   |

## <a name="view-billing-profiles"></a>查看计费配置文件

1. 在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。

2. 选择 **"计费配置文件**"，然后从列表中选择计费配置文件。

    - 在" **概述** "选项卡上，可以编辑计费配置文件详细信息，并通过电子邮件打开或关闭发送发票。

    - 在 **"权限"** 选项卡上，可以将角色分配给用户以支付发票。

    - 在 **"Azure 信用余额** "选项卡上，Azure 客户可以看到该计费配置文件使用的 Azure 信用的交易余额历史记录。

    - 在 **"Azure 信用额度** "选项卡上，Azure 客户可以看到与该计费配置文件关联的 Azure 信用列表及其到期日期。

    > [!NOTE]
    > 如果你没有任何 Azure 信用额度，你将看不到 **Azure** 信用余额或 **Azure 信用** 表。

## <a name="need-help-contact-support"></a>需要帮助？ 请联系支持人员。

如果对 Azure 费用有疑问或需要帮助，请通过 Azure 支持 创建 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">支持请求</a>。

如果对 Microsoft 365 管理中心中的帐单配置文件有疑问或需要帮助，请联系 [商业版产品支持人员](/office365/admin/contact-support-for-business-products)。