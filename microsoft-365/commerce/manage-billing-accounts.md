---
title: 了解计费帐户
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 了解计费帐户及其用于管理帐户设置、发票、付款方式和购买的方式。
ms.date: 03/17/2021
ms.openlocfilehash: 45f9e9d9a174094badaae8087803fbdb3eec3f3b
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731386"
---
# <a name="understand-billing-accounts"></a>了解计费帐户

注册以尝试或购买 Microsoft 产品时，将创建一个计费帐户。 可以使用计费帐户来管理帐户设置、发票、付款方式和购买。 可以访问多个计费帐户。 例如，你直接注册了Microsoft 365，或者有权访问组织的企业协议、Microsoft 产品&服务协议或Microsoft 客户协议。 对于这些方案中的每种情况，你都有一个单独的计费帐户。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>当前支持以下类型的计费帐户：

- Microsoft Online Services 计划：直接注册Microsoft 365订阅时，将创建此计费帐户。
- Microsoft 产品&服务协议 (MPSA) 计划：此计费帐户是在组织签署 MPSA 批量许可协议以购买软件和联机服务时创建的。
- Microsoft 客户协议：当组织与 Microsoft 代表、授权合作伙伴合作或独立购买时，将创建此计费帐户。

" <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">计费帐户</a> "页提供了 Microsoft 商业帐户的视图。 默认情况下，你的组织至少有一个与协议关联的计费帐户，该协议在直接购买时或通过批量许可安排被接受。

## <a name="understand-billing-account-details"></a>了解计费帐户详细信息

**"计费帐户** 详细信息"页的顶部是帐户配置文件，其中包含有关组织的法律和税务信息。 可以更新配置文件以更改法律地址和电话号码。 此帐户是支付所购买产品费用的法律实体。

下表列出了在 **计费帐户** 详细信息页中看到的重要术语。

| 字段名 | 说明 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 已售到地址 | 负责付款并在发票上标识的法律实体。 除非您在购买过程中选择提供其他送货地址，否则此处提供的地址用于确定税率。 有关详细信息，请参阅[税务信息](billing-and-payments/tax-information.md)。 |
| 用户群 | 一个只读字段，用于标识组织 (商业、教育、政府或非营利性) 的业务部分。 |
| 帐户状态 | 一个只读字段，指定 Microsoft 商业帐户的状态。 |
| 税务 ID | 如果不在美国，则必须提供增值税或本地等效项。 有关详细信息，请参阅[税务信息](billing-and-payments/tax-information.md)。 |
| 协议 | 通过直接购买或批量许可安排创建计费帐户时，组织的签署人接受或签署一份协议，其中概述了该帐户的条款&条件。 如果适用，此视图将列出协议历史记录。 如果需要接受更新的条款，则会显示 **审批协议** 的链接。 |
| 计费配置文件 | 计费配置文件定义发票的属性，例如谁收到帐单、帐单的交付方式、付款条款和 PO 号码。 若要在组织中分配计费，可以在购买时创建多个计费配置文件并标识适当的计费配置文件。 有关计费配置文件以及如何使用它们为组织构建更灵活的计费选项的详细信息， [请了解计费配置文件](billing-and-payments/manage-billing-profiles.md)。 |

> [!NOTE]
> 如果需要更改 **"待售到** 名称"或"地址"，但看不到 **"编辑"** 链接，则必须 [联系支持部门](../admin/get-help-support.md) 进行更改。 要求更改 **已售到** 名称的请求需要信用检查。 完成 [此窗体](https://www.microsoft.com/download/details.aspx?id=102732)，并在联系支持人员时准备好与 Microsoft 共享以下文档之一：
>
> - 政府颁发的文档或登记信
> - 从本地公司的注册表中打印出来
>
> 支持可帮助处理仅更改客户名称但实体保持不变的名称和地址更改。 提供的文档应清楚地显示，只有实体的名称已更改。 如果更改是事务（包括销售业务、更改控件或剥离或"分拆"客户关联）的结果，请与 Microsoft 卖家联系。

## <a name="shipping-addresses"></a>寄送地址

本部分列出了与计费帐户关联的发货地址。 购买时，可以使用此地址标识购买的发货或使用位置。 发货地址是可编辑的。 可以添加发货地址或更新现有地址。 此地址用于确定购买的税率。

## <a name="understand-access-to-billing-accounts"></a>了解对计费帐户的访问权限

可以通过角色和权限向其他人提供对<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中的计费帐户的访问权限。 只有计费帐户所有者才能授予对计费帐户的访问权限。 可以将以下角色之一分配给用户：

- **计费帐户所有者** &mdash; 可以分配权限、编辑帐户、签署协议和查看帐户。
- **计费帐户参与者** &mdash; 可以编辑帐户、签署协议和查看帐户。
- **计费帐户读取器** &mdash; 可以查看帐户。

> [!Note]
> 计费帐户角色仅适用于计费帐户，不适用于其他Microsoft 365 管理中心方案。

## <a name="related-content"></a>相关内容

[税务信息](billing-and-payments/tax-information.md) (文章) \
了解 (文章) 的[计费配置文件](billing-and-payments/manage-billing-profiles.md)
