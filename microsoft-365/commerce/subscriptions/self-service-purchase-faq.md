---
title: 自助服务购买常见问题解答
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
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 查找有关自助式购买的常见问题的解答。
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653697"
---
# <a name="self-service-purchase-faq"></a>自助服务购买常见问题解答

自助服务购买为用户提供了尝试新技术的机会，并开发最终受益于其大型组织的解决方案。 集中采购和 IT 团队可查看通过<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>购买和部署自助服务购买解决方案的所有用户。 管理员可以通过 PowerShell 以每个产品为基础关闭自助购买。 若要了解详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

自助服务购买适用于 Power Platform (Power BI、Power Apps 和 Power) 、Project 和 Visio 的自动运行。

> [!NOTE]
> 自助服务购买不适用于印度，也不适用于政府或教育客户。

## <a name="making-a-self-service-purchase"></a>进行自助服务购买

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>客户如何购买自助服务？

客户可以从产品网站或应用程序购买提示中进行自助在线购买。 首先，客户需要输入电子邮件地址，以确保他们是现有 Azure Active Directory (AD) 租户中的用户。 接下来，使用他们的 Azure AD 凭据引导他们登录。 登录后，系统会要求客户选择要购买的订阅数，并提供信用卡付款。 购买完成后，即可开始使用其订阅。 买方可以访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的有限视图，在其中，他们可以向组织中的其他人员分配产品许可证。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>自助服务购买的付款选项是什么？

目前，信用卡是唯一可用的支付方式。 不支持通过发票付款。

### <a name="who-can-buy-through-self-service-purchase"></a>谁可以通过自助购买购买？

在托管 Azure AD 租户中具有非来宾用户帐户的任何用户都可以进行自我服务购买。 自助服务购买不适用于作为政府或教育组织的租户。 如果这适用于您的组织，则无需执行任何其他操作即可控制自助购买。

不符合自助购买条件的组织或市场中的用户会看到一条消息，要求他们联系其 IT 管理员。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>来宾用户是否可以通过自助购买服务购买？

否，来宾用户无法在其为来宾的租户中完成自助服务购买。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>是否可以通过自助购买从本地 Active Directory 购买的用户进行同步？

如果用户在符合条件的 Azure AD 租户中具有活动用户帐户，则可以完成自助购买。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>谁可以由自助服务购买者将许可证分配给？

自助式购买者只能将许可证分配给同一 Azure AD 租户中的用户。 买方有权访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的有限视图，以分配许可证。 "购买者" 可将许可证分配给他们通过自助服务购买购买的产品，并且只能将这些许可证分配给同一 Azure AD 租户中的用户。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>自助式买方在哪里查看和管理他们的采购？

自助服务购买者可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的受限视图中管理其购买。 购买者可以始终从内置于所有 Microsoft 365 和 Dynamics online 应用的应用启动器中的 "**管理员**" 磁贴进入管理中心。 "购买者" 可以查看他们所做的购买、购买同一服务的其他订阅，以及将这些订阅的许可证分配给组织中的其他用户。 此外，购买者可以查看和支付自己的帐单、更新其付款方式，并取消其订阅。

## <a name="pricing"></a>定价

### <a name="what-is-the-pricing-for-self-service-purchases"></a>自助购买的定价是什么？

在 Microsoft 网站上提供了每个用于自助购买的产品的定价。 在用户进行自助购买时，价格也显示为结帐体验的一部分。 这些价格可能与组织在通过合作伙伴提供的集中购买或价格时支付的价格不同。

### <a name="who-is-responsible-for-payment"></a>谁负责付款？

通过 "自助式购买" 购买订阅的人员是根据购买条款和定价向其收取费用的人员，以及负责付款的人员。

## <a name="admin-capabilities"></a>管理员功能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>管理员对自助购买有哪些功能？

管理员可以在其组织中查看在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>内进行的所有自助服务购买。 他们可以查看每个自助购买的产品、购买者名称、购买订阅、到期日期、订单历史记录、购买价格和分配的用户。 在 Power Platform 管理中心中，管理员还可以查看自助服务购买容量。 如果组织需要，管理员可以通过 PowerShell 以每个产品为基础关闭自助购买。 管理员对通过自助购买或集中购买的产品具有相同的数据管理和访问策略。

管理员还可以控制组织中的用户是否可以进行自助服务购买。 有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Microsoft 如何通过启用自助购买来尊重数据治理和合规性？

管理员可以根据其数据治理和合规性要求，控制其租户中提供的服务和产品。 您的组织打开的所有数据管理和访问策略都适用于可用的自助式购买服务。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>谁负责从自助购买创建的产品数据？

从通过自助购买购买的产品中创建的数据由组织拥有和控制。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>如何通过 "自助式购买" 集中进行购买？

管理员可以通过现有协议和定价为分配到自助购买的用户的现有协议和定价，分配现有许可证或购买其他自助服务购买产品订阅。 在分配这些集中购买的许可证之后，管理员可以请求购买者取消其现有订阅。

### <a name="where-does-the-admin-see-self-service-purchases"></a>管理员在哪里查看自我服务购买？

全局管理员和计费管理员可以通过在**Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的**产品**中付费购买的产品查看购买的订阅。 他们可以筛选 "产品" 列表，以仅显示通过中央采购购买的订阅，或包括通过自助购买购买的订阅。

管理员可以查看产品、买方名称、购买订阅、到期日期、订单历史记录、采购价和分配的用户。

## <a name="support-and-training"></a>支持和培训

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>客户的 IT 部门或合作伙伴是否希望支持通过自助购买购买的产品？

IT 部门和合作伙伴不希望为通过自助购买购买的产品提供支持。 Microsoft 为自助服务购买者提供标准支持。

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>如果自助服务购买者呼叫支持，是否会使用客户的首要支持事件？

自助服务购买者不会使用客户的首要支持事件接收自助服务购买支持。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>用户期望如何在通过自助购买的产品上接收有关他们购买的产品的培训？

产品网站上提供了针对用户的广泛培训。 这些产品具有指导性的学习、文档、示例和强大的社区，可直接从其他用户获取答案和提示。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>如果用户离开组织，自我服务购买会发生什么情况？

如果最初购买自助服务购买产品的人离开了组织，有效用户将继续在订阅期间完全使用产品。 在买方直接取消该订阅或通过客户支持取消订阅的管理员请求之前，订阅将一直保持活动状态。 管理员还可以选择将已集中购买的许可证分配给已取消订阅的用户。

## <a name="partners"></a>合作伙伴

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>在自助服务购买中，Microsoft 合作伙伴的角色是什么？

拥有委派管理权限的合作伙伴可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中查看自助购买，就像管理员一样。合作伙伴可以帮助您支持要通过自助购买来集中购买产品的组织。 此外，合作伙伴可以提供用于扩展自助购买功能的解决方案。