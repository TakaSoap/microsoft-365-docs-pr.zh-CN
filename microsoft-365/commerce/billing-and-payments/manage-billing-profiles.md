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
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667770"
---
# <a name="understand-billing-profiles"></a>了解计费配置文件

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

对于从 Microsoft 购买产品和服务的商业客户，帐单配置文件允许您自定义发票中包含的项目以及支付发票方式。

计费配置文件包括以下信息：

- **计费帐户** &ndash; 配置文件相关的计费帐户的名称
- **付款方式** &ndash; 信用卡或借记卡、银行帐户、支票或银行帐户转移
- **联系人信息** &ndash; 帐单地址和联系人姓名
- **发票设置** &ndash; 基于计费帐户的国家/地区、可选 PO 编号以及作为电子邮件附件接收发票的选项的货币
- **权限** &ndash; 允许您更改计费配置文件、支付帐单或使用计费配置文件上的付款方式进行购买的权限

使用计费配置文件来控制购买并自定义发票。 为使用计费配置文件购买的产品生成每月发票。 你可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。

在首次购买期间，系统会自动为帐单帐户创建计费配置文件。 您可以在"计费配置文件"页上创建计费 <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">配置文件</a> ，以设置更多发票。 例如，当您为组织的每个部门进行购买时，可以使用不同的计费配置文件。 下一个计费日期，你将收到每个计费配置文件的发票。

## <a name="billing-profile-roles"></a>计费配置文件角色

帐单配置文件上的角色具有控制购买以及查看和管理发票的权限。 向跟踪、组织和支付发票的用户分配这些角色，例如组织中采购团队成员。

| 角色                          | 说明                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 计费配置文件所有者         | 管理帐单配置文件的所有内容                                           |
| 计费配置文件参与者   | 管理除帐单配置文件中的权限之外的所有内容                         |
| 计费配置文件读取器        | 计费配置文件中所有内容只读视图                                 |
| 发票经理               | 查看和支付帐单，并且具有计费配置文件中所有内容只读视图   |

## <a name="view-billing-profiles"></a>查看计费配置文件

1. 在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。

2. 选择 **"** 计费配置文件"，然后从列表中选择计费配置文件。

    - 在 **"概述** "选项卡上，可以编辑计费配置文件详细信息，并通过电子邮件打开或关闭发送发票。

    - 在 **"权限"** 选项卡上，可以将角色分配给用户以支付发票。

    - 在 **"Azure 信用平衡** "选项卡上，Azure 客户可以看到该计费配置文件使用的 Azure 信用的事务余额历史记录。

    - 在 **"Azure 信用额度** "选项卡上，Azure 客户可以看到与该计费配置文件关联的 Azure 信用列表及其到期日期。

    > [!NOTE]
    > 如果你没有 Azure 信用额度，你将看不到 **Azure** 信用额度或 **Azure 信用** 选项卡。

## <a name="need-help-contact-support"></a>需要帮助? 请联系支持人员。

如果对 Azure 费用有疑问或需要帮助，请通过 Azure 支持创建 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">支持请求</a>。

如果你在 Microsoft 365 管理中心中对帐单配置文件有疑问或需要帮助，请联系 [商业版产品的支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。
