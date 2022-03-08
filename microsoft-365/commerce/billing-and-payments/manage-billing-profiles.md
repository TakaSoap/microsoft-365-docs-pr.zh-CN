---
title: 了解计费配置文件
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1.keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: 了解计费配置文件如何支持发票。
ms.date: 04/02/2021
ms.openlocfilehash: 472b5c4754d686877077133467e33592b5c0b85e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311855"
---
# <a name="understand-billing-profiles"></a>了解计费配置文件

计费配置文件包含付款方式、帐单邮寄信息和其他发票设置，如采购订单编号和电子邮件发票首选项。 使用计费配置文件支付从 Microsoft 购买的产品。 当用户进行自助购买时，将自动创建计费配置文件。 每个计费配置文件将单独开票。

> [!NOTE]
>
> 计费配置文件不适用于从 Microsoft.com 购买产品和服务的客户或客户的"购买服务"Microsoft 365 管理中心。

## <a name="what-are-billing-profile-roles"></a>什么是计费配置文件角色？

帐单配置文件上的角色具有控制购买以及查看和管理发票的权限。 向跟踪、组织和支付发票的用户分配这些角色。 例如，您组织中采购工作组的成员。

| Role                         | 说明                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 计费配置文件所有者        | 管理计费配置文件的所有内容                                          |
| 计费配置文件参与者  | 管理计费配置文件中的权限之外的所有内容                        |
| 计费配置文件读取器       | 帐单配置文件中所有项的只读视图                                |
| 发票管理器              | 查看和支付帐单，并且对帐单配置文件中所有内容具有只读视图  |

## <a name="view-my-billing-profiles"></a>查看我的计费配置文件

> [!NOTE]
>
> 如果按照以下步骤操作，并且计费配置文件列表为空，则意味着你没有计费配置文件，并且无法使用此功能。

1. 在管理中心，转到“**账单**”\> “<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">账单和付款</a>”页。
2. 选择" **计费配置文件** "选项卡，然后从列表中选择计费配置文件。

每个计费配置文件包括以下信息：

- **计费配置文件名称和状态** &ndash; 计费配置文件的唯一名称，以及计费配置文件是处于活动状态还是已禁用进行购买。
- **发票设置** &ndash; 基于计费帐户的国家/地区的货币、有关发票频率和日期的信息、作为电子邮件附件接收发票的选项以及可选的 PO 编号字段
- **付款方式** &ndash; 显示配置文件的主付款方式和备份付款方式（如果有）
- **计费帐户** &ndash; 配置文件相关的计费帐户的名称。 有关计费帐户详细信息，请参阅 [了解计费帐户](../manage-billing-accounts.md)。
- **联系人信息** &ndash; 帐单邮寄地址、联系人姓名和电子邮件地址
- **计费配置文件角色** &ndash; 分配了其中一个计费配置文件角色以执行该配置文件操作的用户列表。 例如，支付帐单、添加 PO 编号或替换用于进行购买的付款方式。

> [!NOTE]
>
> 只能将计费配置文件角色分配给贵组织的用户。

## <a name="need-help-contact-support"></a>需要帮助？ 联系支持人员

如果对 Azure 费用有疑问或需要帮助，请 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">通过 Azure 支持创建支持请求</a>。

如果对帐单配置文件有疑问或需要帮助，Microsoft 365 管理中心[联系支持人员](../../admin/get-help-support.md)。

## <a name="related-content"></a>相关内容

[How to pay for your subscription with a billing profile (](pay-for-subscription-billing-profile.md) article) \
[了解帐单帐户](../manage-billing-accounts.md) (文章) \
[管理付款方式 (](manage-payment-methods.md) 文章) 
