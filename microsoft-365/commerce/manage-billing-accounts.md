---
title: 管理计费帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 了解有关计费帐户以及如何管理这些帐户的信息。
ms.openlocfilehash: 3c99f3f22fb0eb13c4f9cab06a4037fe057b6fb4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638203"
---
# <a name="manage-billing-accounts"></a>管理计费帐户

在你注册以试用或购买 Microsoft 产品时，将创建一个帐单帐户。 您可以使用付费帐户管理帐户设置、发票、付款方式和购买。 您可以访问多个记帐帐户。 例如，您直接注册了 Microsoft 365，或者您有权访问组织的企业协议、Microsoft 产品 & 服务协议或 Microsoft 客户协议。 对于上述每个方案，您都有一个单独的帐单帐户。

Microsoft 365 admin center 目前支持以下类型的计费帐户：

- Microsoft Online Services 程序：当您直接注册 Microsoft 365 订阅时，将创建此帐单帐户。
- Microsoft Products & Services 协议 (MPSA) 计划：当您的组织签署 MPSA 批量许可协议以购买软件和在线服务时，将创建此帐单帐户。
- Microsoft 客户协议：当组织与 Microsoft 代表、授权合作伙伴或单独购买时，将创建此帐单帐户。

" <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">记帐帐户</a> " 页面提供了使用 Microsoft 的商业帐户视图。 默认情况下，您的组织至少有一个与协议关联的帐单帐户，该帐户在直接购买时或通过批量许可排列接受。

## <a name="understand-billing-account-details"></a>了解帐单帐户详细信息

" **付费帐户** 详细信息" 页的顶部是您的帐户配置文件，其中包含有关您的组织的法律和税务信息。 您可以更新您的配置文件，以更改您的合法地址和电话号码。 此帐户是支付所购买产品的法定法人。

下表列出了您在 **记帐帐户** 详细信息页面中看到的重要术语。

| 字段名 | Description |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 售出地址 | 负责在发票上付款和标识的法人。 此处提供的地址用于确定您的税率，除非您在购买过程中选择提供备选送货地址。 有关详细信息，请参阅 [税务信息](billing-and-payments/tax-information.md)。 |
| 段落 | 一个只读字段，用于标识组织的业务部门 (商业、教育、政府或非盈利) 。 |
| 帐户状态 | 一个只读字段，用于指定你的商业帐户与 Microsoft 的状态。 |
| 税号 | 如果你不在美国，则必须提供 VAT 或当地的等价国家/地区。 有关详细信息，请参阅 [税务信息](billing-and-payments/tax-information.md)。 |
| 本 | 在创建计费帐户（通过直接购买或批量许可安排）时，组织的签字人接受或签署一个协议，该协议描述了帐户 & 条件的条款。 如果适用，此视图列出协议历史记录。 如果需要接受更新的术语，则显示 " **审批协议** " 的链接。 |
| 计费配置文件 | 计费配置文件定义发票的属性，如接收帐单的用户、帐单的交货方式、付款期限和采购订单编号。 若要在组织中分发帐单，可以创建多个记帐配置文件，并在购买时标识相应的记帐配置文件。 有关计费配置文件以及如何使用它们为组织生成更灵活的记帐选项的详细信息，请 [管理计费配置文件](billing-and-payments/manage-billing-profiles.md)。 |

> [!NOTE]
> 如果要更改 **售出** 的名称或地址，但看不到 **编辑** 链接，则必须  [与支持人员联系](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) 以更改它。 对 **售出** 的名称更改的请求将需要进行信用检查。 在联系支持人员时，请准备好以下文档之一：
>
> - 外部通知文档，指示公司名称或公司结构中的任何更改
> - 政府颁发的文档或注册信件
> - 打印出本地公司的注册表
>
> 支持可帮助解决仅客户名称更改的名称和地址更改，但该实体保持不变。 提供的文档应清楚地表明只有实体的名称发生了更改。 如果更改与客户关联的任何交易记录（如业务销售或剥离或 "spinoff"）相关，请联系你的 Microsoft 卖家。

## <a name="shipping-addresses"></a>送货地址

此部分列出了与您的付费帐户关联的送货地址。 在购买产品时，您可以使用此地址来确定购买或使用购买的位置。 送货地址是可编辑的。 您可以添加送货地址或更新现有地址。 此地址用于确定购买的税率。

## <a name="understand-access-to-billing-accounts"></a>了解对帐单帐户的访问权限

你可以通过角色和权限向其他人提供对 Microsoft 365 管理中心中的帐单帐户的访问权限。 只有付费帐户所有者可以授予对帐单帐户的访问权限。 您可以向用户分配以下角色之一：

- **帐单帐户所有者** &mdash; 可以分配权限、编辑帐户、签署协议和查看帐户。
- **帐单帐户参与者** &mdash; 可以编辑帐户、签署协议和查看帐户。
- **帐单帐户读取器** &mdash; 可以查看帐户。

> [!Note]
> 帐单帐户角色仅适用于付费帐户，不适用于其他 Microsoft 365 管理中心方案。

## <a name="related-articles"></a>相关文章

[税务信息](billing-and-payments/tax-information.md)

[管理计费对象信息](billing-and-payments/manage-billing-profiles.md)