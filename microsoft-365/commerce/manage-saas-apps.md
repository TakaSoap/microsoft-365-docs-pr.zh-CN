---
title: 管理组织的 SAAS 应用
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid: MET150
description: 了解如何在Microsoft 365 管理中心中激活和管理第三方应用。
ms.date: 04/15/2021
ms.openlocfilehash: c85a0c93ee7f17953f7877cc1fd97765e0e63afd
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713858"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a>管理组织的第三方应用订阅

可以在新<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中管理第三方应用的许可证和计费。 更新后的功能包括增强的订阅管理、改进对计费信息的访问，以及提高管理账单的灵活性。 订阅管理基于 Microsoft 更新的商业平台。 这适用于客户直接购买或从第三方提供商购买的软件即服务应用。

## <a name="how-to-get-software-as-a-service-apps"></a>如何获取软件即服务应用

有几种方法可以购买第三方应用。

- **直接购买** – 客户可以直接从 [Azure 市场](https://azuremarketplace.microsoft.com/marketplace/) 或 [AppSource](https://appsource.microsoft.com/) 购买订阅。
- **合作伙伴购买** – 通过合作伙伴中心与合作伙伴合作购买订阅。
- **Microsoft 建议** - 响应 Microsoft Sales 提出的包含第三方应用的建议。

客户购买应用并接受Microsoft 客户协议后，他们可以在Microsoft 365 管理中心或适用于企业的 Microsoft Store中对其进行管理。

应用提供商以统一费率或通过为用户购买许可证来销售其应用。

- **统一费率** – 也称为基于站点的定价，应用按月或年价格定价。 在应用页上，许可证数量按"无限制"列出。
- **许可证** – 应用按许可证定价。 客户为组织中的每个用户分配许可证

## <a name="supported-regions"></a>支持的区域

以下区域提供对第三方应用的支持：

- 阿根廷
- 澳大利亚
- 加拿大
- 智利
- 法国
- 德国
- 希腊
- 波多黎各
- 南非
- 英国
- 美国
- 西欧

## <a name="activate-third-party-apps"></a>激活第三方应用

管理员必须先激活第三方应用，然后再将其分配给用户。 这些应用在第三方发布者的门户中激活。

1. 在管理中心，转到 **BillingYour** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">productsApps</a> >  页面。
2. 查找并选择要管理的应用。
3. 在 **设置 &操作** 下，**在发布者的门户中选择"管理**"。

你将被定向到应用发布者的网站，你可以在其中激活应用。

## <a name="manage-third-party-apps"></a>管理第三方应用

管理员在两个位置管理第三方应用：Microsoft 365 管理中心和第三方应用提供程序的门户。

下面是你可以在每个门户中执行的操作。

| Microsoft 365 管理中心 | 应用发布者门户 |
| --- | --- |
| 更改许可证数量 <br> 管理账单的支付方式 <br> 管理账单的支付方式 <br> 更改信用卡)  (付款方式 <br> 查看发票 <br> 取消应用订阅 | 为每个应用设置应用 (一次)  <br> 向用户分配许可证 <br> 技术支持 |

激活应用后，除非已取消、过期或付款未保持最新状态，否则该应用将保持活动状态。 这些事件将应用状态更改为已禁用。 禁用应用后，无法重新激活它。 若要继续使用该应用，请购买该应用的另一个副本。

## <a name="assign-licenses"></a>分配许可证

管理员需要先激活第三方应用，然后再将其分配给用户。 它们已在第三方发布者门户中激活。 在应用页上，**在设置 &操作** 下，选择要分配许可证的链接。

1. 在管理中心，转到 **BillingYour** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">productsApps</a> >  页面。
2. 查找并选择要管理的应用。
3. 在 **设置 &操作** 下，在 **发布者的门户中** 选择"管理"链接。

## <a name="change-license-quantity"></a>更改许可证数量

管理员可以更改其组织拥有的许可证数。 这仅适用于使用基于座位的定价购买的应用。

1. 在管理中心，转到 **BillingYour** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">productsApps</a> >  页面。
2. 查找并选择要管理的应用。
3. 选择 **"更改许可证数量**"。

## <a name="manage-payment-methods"></a>管理支付方式

软件即服务应用各分配有一个计费配置文件。 通过计费配置文件，可以自定义发票中包含的产品以及发票的付款方式。 包括：

- **付款方式** - 信用卡或支票/电汇
- **联系人信息** - 计费地址和联系人姓名
- **角色** – 允许您更改计费配置文件、支付账单或使用计费配置文件上的付款方式进行购买的角色。

有关计费配置文件的详细信息，请参阅 ["了解计费配置文件](/microsoft-store/billing-profile)"。

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a>更改软件即服务应用订阅上的计费配置文件

1. 在管理中心，转到 **BillingYour** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">productsApps</a> >  页面。
2. 查找并选择要管理的应用。
3. 在 **计费配置文件** 旁边，选择 **"编辑**"。

有关发票的详细信息，请参阅 [了解帐单或发票](billing-and-payments/understand-your-invoice.md)。

## <a name="cancel-a-software-as-a-service-app-subscription"></a>取消软件即服务应用订阅

可以从应用页中取消软件即服务应用。

1. 在管理中心，转到 **BillingYour** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">productsApps</a> >  页面。
2. 查找并选择要管理的应用。
3. 在 **设置 &操作下**，选择 **"取消订阅**"。
