---
title: 了解计费帐户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: tugu, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 了解计费帐户及其如何用于管理帐户设置、发票、付款方式和购买。
ms.date: 03/17/2021
ms.openlocfilehash: 07997e8001ee753de2693b62d693e3dc2e2261c9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151322"
---
# <a name="understand-billing-accounts"></a>了解计费帐户

注册以试用或购买 Microsoft 产品时，会创建一个计费帐户。 使用计费帐户管理帐户设置、发票、付款方式和购买。 你可以访问多个计费帐户。 例如，你直接Microsoft 365注册，或者你有权访问组织的 企业协议、Microsoft 产品&服务协议或 Microsoft 客户协议。 对于其中每个方案，你将有一个单独的计费帐户。

当前<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>支持以下类型的计费帐户：

- Microsoft Online Services计划：此计费帐户是在你直接注册订阅时Microsoft 365帐户。
- Microsoft &服务协议 (MPSA) 计划：当你的组织签署 MPSA 批量许可协议以购买软件和联机服务时，将创建此计费帐户。
- Microsoft 客户协议：当你的组织与 Microsoft 代表、授权的合作伙伴合作或单独购买时，将创建此计费帐户。

" <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">计费帐户</a> "页提供 Microsoft 商业帐户的视图。 默认情况下，你的组织至少具有一个与在直接购买时或通过批量许可安排接受的协议相关联的计费帐户。

## <a name="understand-billing-account-details"></a>了解计费帐户详细信息

"计费帐户 **详细信息** "页面的顶部是您的帐户配置文件，其中包含有关组织的法律和税务信息。 你可以更新个人资料以更改你的合法地址和电话号码。 此帐户是支付所购买产品的法律实体。

下表列出了你在"计费帐户详细信息"页面中 **看到的重要术语** 。

| 字段名 | 说明 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 售达地址 | 负责付款的法律实体，在发票上标识。 除非您在购买过程中选择提供其他送货地址，否则此处提供的地址用于确定税率。 有关详细信息，请参阅[税务信息](billing-and-payments/tax-information.md)。 |
| 用户群 | 一个只读字段，用于标识组织的业务 (商业、教育、政府或非营利组织) 。 |
| 帐户状态 | 一个只读字段，用于指定 Microsoft 商业帐户的状态。 |
| 税务 ID | 如果你在美国以外，则必须提供 VAT 或本地等效项。 有关详细信息，请参阅[税务信息](billing-and-payments/tax-information.md)。 |
| 协议 | 当通过直接购买或批量许可安排创建计费帐户时，组织会接受或签署一份概述了帐户&条款的协议。 如果适用，此视图将列出协议历史记录。 如果需要接受更新后的条款，将显示"批准 **协议"** 链接。 |
| 计费配置文件 | 帐单配置文件定义发票的属性，如谁收到帐单、帐单的交付方式、付款期限和 PO 编号。 若要在整个组织中分配计费，可以创建多个计费配置文件，在购买时标识相应的计费配置文件。 有关计费配置文件以及如何使用它们为组织生成更灵活的计费选项的详细信息，请参阅 [了解计费配置文件](billing-and-payments/manage-billing-profiles.md)。 |

> [!NOTE]
> 如果需要更改"售达 **"** 名称或地址，但看不到"编辑"链接，则必须联系支持 [人员以更改](../business-video/get-help-support.md)它。 对"售 **达名称** "更改的请求将需要核实信用。 填写 [此表单](https://www.microsoft.com/download/details.aspx?id=102732)，并准备好在联系支持人员时与 Microsoft 共享以下文档之一：
>
> - 政府颁发的文档或注册信
> - 打印出本地公司的注册表
>
> 如果仅更改客户名称，但实体保持不变，则支持可帮助更改名称和地址。 提供的文档应清楚地显示仅实体的名称已更改。 如果更改是交易的结果，包括出售业务、更改控制措施，或者客户联盟的收购或"出售"，请联系你的 Microsoft 卖家。

## <a name="shipping-addresses"></a>发货地址

此部分列出了与帐单帐户关联的送货地址。 当你进行购买时，可以使用此地址标识你的购买交付或使用位置。 发货地址是可编辑的。 可以添加送货地址或更新现有地址。 此地址用于确定购买的税率。

## <a name="understand-access-to-billing-accounts"></a>了解对计费帐户的访问权限

可以通过角色和权限为其他人提供对<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心帐户的访问权限</a>。 只有计费帐户所有者才能授予对计费帐户的访问权限。 可以将以下角色之一分配给用户：

- **计费帐户所有者** &mdash; 可以分配权限、编辑帐户、签署协议和查看帐户。
- **计费帐户参与者** &mdash; 可以编辑帐户、签署协议和查看帐户。
- **计费帐户读者** &mdash; 可查看帐户。

> [!Note]
> 计费帐户角色仅适用于计费帐户，不适用于其他Microsoft 365 管理中心方案。

## <a name="related-content"></a>相关内容

[税务信息](billing-and-payments/tax-information.md) (文章) \
[了解帐单配置文件](billing-and-payments/manage-billing-profiles.md) (文章) 
