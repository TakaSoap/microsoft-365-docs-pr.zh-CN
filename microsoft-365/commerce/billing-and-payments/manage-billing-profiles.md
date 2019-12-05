---
title: 管理计费配置文件
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解计费配置文件如何支持发票。
keywords: 计费配置文件、发票、费用、管理费用
ms.openlocfilehash: 3dbdbb57b46b915891640483bde56ebc8ad1cff6
ms.sourcegitcommit: 95a07b328166f637a481c8b5c53669eaf8ff0db8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39837386"
---
# <a name="manage-billing-profiles"></a>管理计费配置文件
对于从 Microsoft 购买产品和服务的商业客户，计费配置文件允许您自定义发票中包含的项目以及支付发票的方式。

计费配置文件包括以下信息：

- 与配置文件相关**的帐单帐户名称** &ndash;
- **支付方式** &ndash;信用卡或借记卡、银行帐户、支票或电汇转帐
- **联系人信息** &ndash;帐单地址和联系人姓名
- **发票设置** &ndash;货币根据计费帐户所在的国家/地区、可选的 PO 号以及将发票作为电子邮件附件接收的选项。
- 允许您更改帐单配置文件、支付帐单或使用付费配置文件上的付款方式进行购买的**权限** &ndash;权限

使用计费配置文件控制购买和自定义发票。 为使用记帐配置文件购买的产品生成月度发票。 您可以自定义发票，例如更新采购订单编号和电子邮件发票首选项。

在您首次购买过程中，会自动为您的帐单帐户创建一个记帐配置文件。 您可以在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">计费配置文件</a>" 页上创建帐单配置文件以设置更多发票。 例如，在对组织中的每个部门进行购买时，您可以使用不同的记帐配置文件。 在下一个帐单日期，您将收到每个记帐配置文件的发票。

## <a name="billing-profile-roles"></a>计费配置文件角色

计费配置文件上的角色具有控制采购的权限，并查看和管理发票。 将这些角色分配给跟踪、组织和支付发票的用户，如组织中的采购团队的成员。

| 角色                          | 说明                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 计费配置文件所有者         | 管理计费配置文件的所有内容                                           |
| 帐单档案文件参与者   | 管理帐单配置文件中除权限之外的所有内容                         |
| 计费配置文件读者        | 记帐配置文件中所有内容的只读视图                                 |
| 发票管理器               | 查看和支付帐单，并在计费配置文件中提供所有内容的只读视图   |

## <a name="view-billing-profiles"></a>查看帐单配置文件

1. 在 "管理中心" 中，转到 "**计费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">帐单 & 付款</a>" 页。

2. 选择 "**帐单配置文件**"，然后从列表中选择帐单配置文件。

    - 在 "**概述**" 选项卡上，您可以编辑帐单档案文件详细信息，打开或关闭 "通过电子邮件发送发票"。

    - 在 "**权限**" 选项卡上，您可以向用户分配用于支付发票的角色。

    - 在 " **azure 信用额度余额**" 选项卡上，azure 客户可以查看该记帐配置文件使用的 Azure 信用的交易余额历史记录。

    - 在 " **Azure 积分**" 选项卡上，azure 客户可以查看与该计费配置文件关联的 azure 信用列表及其到期日期。

    > [!NOTE]
    > 如果你没有任何 Azure 信用，你将看不到**azure 信用余额**或**azure 积分**选项卡。

## <a name="need-help-contact-support"></a>需要帮助? 请联系支持人员。

如果你在 Azure 费用方面遇到疑问或需要帮助，请<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用 azure 支持创建支持请求</a>。

如果您在 Microsoft 365 管理中心中有关于付费配置文件的问题或需要帮助，请[联系业务产品支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。
