---
title: 自助服务购买常见问题解答
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
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 查找有关自助式购买的常见问题的解答。
ms.openlocfilehash: cc0a059c745c64c9c196deccf771fffa30a5fe63
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403206"
---
# <a name="self-service-purchase-faq"></a>自助服务购买常见问题解答

> [!NOTE]
> 本文中的信息仅适用于 Microsoft Power Platform （Power BI、Power Apps 和 Power 自动化）订阅。

在多个国家和地区的电源平台现可使用自助服务购买。

## <a name="general"></a>常规

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Microsoft 宣布的针对电源平台产品的自助服务购买有哪些变化？

在11月19日，我们向 IT 管理员提供了一种通过 PowerShell 基于每个产品关闭自助购买的方法。 若要了解如何使用它，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

若要提供更多的时间来为此更改做准备，我们正在更新 Power BI 产品的自助服务购买功能启动，以在1月14日为所有商业云客户提供。  

从2020年1月14日起，将提供适用于美国商业云客户的 Power Platform 产品（Power BI、Power Apps 和 Power 自动化）的自助服务购买、订阅和许可证管理功能。 自助式购买为用户提供了一种尝试新技术的机会，让他们能够开发最终会对更大的组织带来好处的解决方案。 目前，美国政府、非盈利或教育版的租户将无法使用此功能。 集中采购和 IT 团队可查看通过<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>购买和部署自助服务购买解决方案的所有用户，并将能够通过 PowerShell 基于每个产品禁用自助购买。

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>为什么 Microsoft 为电源平台产品添加自助服务购买选项？

在当今世界，最终用户和部门越来越多地寻求和购买技术解决方案。 我们已收到来自这些客户的多个请求，以启用 Power Platform 产品的自助服务购买。 我们正在对此客户需求做出响应，同时平衡 IT 管理员的需求，在组织内的个人采用第三方解决方案而没有其知识的情况下，经常会失去可视性和控制能力。 使用适用于电源平台产品的自助服务功能，IT 管理员可以完全了解在其组织内进行的所有自助服务购买，并且在组织级别设置的数据管理策略将会对通过自助服务购买的订阅产生累算。 管理员还可以通过现有协议和定价为分配到自助购买的用户分配电源平台产品的现有许可证或购买其他订阅。 在分配这些集中购买的许可证之后，管理员可以请求购买者取消其现有订阅。 Microsoft 正在探索为将来的管理员简化和简化此过程的方法。

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>哪些电源平台产品可用于自助购买？

Microsoft 已为美国的客户启动了针对 Power Platform （Power BI、Power Apps 和 Power 自动化）的自助服务购买，在未来的几个月内将推出更多市场。 目前，美国政府、非盈利或教育版的租户将无法使用此功能。

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>是否会为电源平台产品之外的服务启用自助服务购买？

目前，只有 Power Platform 系列产品通过 "自助式购买" 提供。

## <a name="making-a-self-service-purchase"></a>进行自助服务购买

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>客户如何购买自助服务？

客户将能够从 Microsoft Power BI、Power Apps 和 Power 自动化网站进行自助在线购买。 将首先要求客户输入电子邮件地址，以确保他们是现有 Azure Active Directory （AD）租户中的用户。 然后，它们将通过使用其 Azure AD 凭据定向到 "登录"。 登录后，将要求客户选择他们要购买的订阅数并提供信用卡付款。 购买完成后，他们将能够开始使用其订阅。 购买者还可以访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的受限视图，在这里，他们可以让组织中的其他人使用该产品。

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>自助服务购买的付款选项是什么？

目前，信用卡是唯一可用的支付方式。 不支持通过开票付款。

### <a name="who-can-buy-through-self-service-purchase"></a>谁可以通过自助购买购买？

在托管 Azure AD 租户中具有非来宾用户帐户的任何用户都可以购买。 目前，此功能将不可用于政府、非盈利或教育的租户。 如果这适用于您的组织，则此时无需执行任何其他操作即可控制自助购买。

组织或市场中不符合自助购买条件的用户将看到一条消息，询问他们现在是与 IT 管理员联系。

### <a name="can-guest-users-buy-through-self-service-purchase"></a>来宾用户是否可以通过自助购买服务购买？

否，来宾用户无法在其为来宾的租户中完成自助服务购买。

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>是否可以通过自助购买从本地 Active Directory 购买的用户进行同步？

如果用户在符合条件的 Azure AD 租户中具有活动用户帐户，则可以完成自助购买。

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>谁可以由自助服务购买者将许可证分配给？

自助服务购买者只能将许可证分配给同一 Azure AD 租户中的用户。 买方将能够访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的有限视图，以分配许可证。 他们只具有可见性，并可将许可证分配给他们通过自助服务购买购买的产品，并且仅能够将这些许可证分配给同一 Azure AD 租户中的用户。

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>自助式买方在哪里查看和管理他们的采购？

自助服务购买者可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的受限视图中管理其购买。 购买者可以始终从内置于所有 Microsoft 365 和 Dynamics online 应用的应用启动器中的 "**管理员**" 磁贴进入管理中心。 他们可以查看所做的购买、购买同一服务的其他订阅，以及将这些订阅的许可证分配给组织中的其他用户。 此外，购买者可以查看和支付自己的帐单、更新其付款方式，并取消其订阅。

**面向自助服务购买的有限 Microsoft 365 管理中心的视图：**

![Microsoft 365 管理中心屏幕截图。](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>定价

### <a name="what-is-the-pricing-for-self-service-purchases"></a>自助购买的定价是什么？

适用于自助购买的每个电源平台产品的定价将在 Microsoft 网站上提供，同时还作为签入体验的一部分显示，同时购买自助服务。 这些价格可能与组织在通过合作伙伴提供的集中购买或价格时支付的价格不同。

### <a name="who-is-responsible-for-payment"></a>谁负责付款？

通过自助购买购买订阅的人员将收费，并根据购买的条款和定价负责付款。

## <a name="admin-capabilities"></a>管理员功能

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>管理员对自助购买有哪些功能？

管理员可以在其组织中查看在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>内进行的所有自助服务购买。 他们可以查看每个自助购买的产品、购买者名称、购买订阅、到期日期、订单历史记录、购买价格和分配的用户。 在 Power Platform 管理中心中，管理员还可以查看自助服务购买容量。 如果组织需要，管理员将能够通过 PowerShell 基于每个产品关闭自助购买。 管理员对通过自助购买或集中购买的产品具有相同的数据管理和访问策略。

管理员还可以控制组织中的用户是否可以进行自助服务购买。 有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Microsoft 如何通过启用自助购买来尊重数据治理和合规性？

管理员可以根据其数据治理和合规性要求，控制哪些服务和产品在其租户中已启用。 此外，您的组织已启用的所有数据管理和访问策略将应用于启用自助服务购买的服务。

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>谁负责从自助购买创建的产品数据？

从通过自助购买购买的产品中创建的数据由组织拥有和控制。

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>如何通过 "自助式购买" 集中进行购买？

管理员可以通过现有协议和定价为分配到自助购买的用户分配现有许可证或购买附加的 Power Platform 产品（Power BI、Power Apps 和 Power 自动化）订阅。 在分配这些集中购买的许可证之后，管理员可以请求购买者取消其现有订阅。 Microsoft 正在探索为将来的管理员简化和简化此过程的方法。

### <a name="where-does-the-admin-see-self-service-purchases"></a>管理员在哪里查看自我服务购买？

全局和计费管理员可以通过在**Billing**  >  " <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>" 中付费**产品**以及通过中央采购购买的所有其他订阅，查看通过自助购买购买的订阅。 他们可以将列表筛选为仅通过中央采购购买的订阅，或者包括通过自助购买购买的订阅。

管理员可以查看产品、买方名称、购买订阅、到期日期、订单历史记录、采购价和分配的用户。

## <a name="support-and-training"></a>支持和培训

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>客户的 IT 部门或合作伙伴是否希望支持通过自助购买购买的产品？

IT 部门和合作伙伴不希望为通过自助购买购买的产品提供支持。 Microsoft 将为自助服务购买者提供标准支持。

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>如果自助服务买方呼叫支持，他们是否将使用客户的首要支持事件？

自助服务购买者不会使用客户的首要支持事件接收自助服务购买支持。

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>用户期望如何在通过自助购买的产品上接收有关他们购买的产品的培训？

对用户的广泛培训在 Microsoft Power BI、Power Apps 和 Power 自动化网站上提供。 这些产品具有指导性的学习、文档、示例和强大的社区，可直接从其他用户获取答案和提示。

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>如果用户离开组织，自我服务购买会发生什么情况？

有效的用户将继续在订阅期间完全使用自助购买。 在买方直接取消订阅或管理员请求通过客户支持取消订阅时，订阅仍处于活动状态。 管理员还可以选择将已集中购买的许可证分配给已取消订阅的用户。

## <a name="partners"></a>合作伙伴

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>在自助服务购买中，Microsoft 合作伙伴的角色是什么？

拥有委派管理权限的合作伙伴可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中查看自助购买，就像管理员一样。合作伙伴可以帮助您支持要通过自助购买来集中购买产品的组织。 此外，合作伙伴可以提供用于扩展自助购买功能的解决方案。

## <a name="country-and-region-availability"></a>国家和地区可用性

### <a name="in-which-countries-and-regions-can-i-make-a-self-service-purchase"></a>我可以在哪些国家/地区购买自助服务？

自助服务购买适用于以下国家和地区：阿富汗、芬兰群岛、阿尔巴尼亚、阿尔及利亚美洲萨摩亚、安道尔、安哥拉、Anguilla、Antarctica、安提瓜和巴布达、阿根廷、亚美尼亚、Aruba、澳大利亚、奥地利、阿塞拜疆、巴哈马、巴林、孟加拉、巴巴多斯、白俄罗斯、比利时、保加利亚、伯利兹、Benin、百慕大、、博茨瓦纳、Bonaire、圣斯特歇斯和 Saba、波斯尼亚和黑塞哥维那、博茨瓦纳、Bouvet 岛、巴西、不列颠印度洋领地、英属维尔京群岛、文莱、布基纳法索、布隆迪、佛得角、柬埔寨、喀麦隆、加拿大、开曼群岛、中部非洲共和国、Chad、智利、中国圣诞节岛，科科斯（奇林）群岛，哥伦比亚，哥伦比亚，哥伦比亚，哥伦比亚，哥伦比亚，哥伦比亚，科摩罗，刚果，刚果民主共和国，，Curaçao，斯群岛，科特迪瓦，博茨瓦纳，科特迪瓦，科特迪瓦，Dominica，多米尼加共和国，厄瓜多尔，埃及，，法罗群岛，斐济，，法属波利尼西亚，法属南部领地，Gabon，冈比亚，格鲁吉亚，德国，加纳，直布罗陀，格陵兰，希腊，格林纳达，Guadeloupe，关岛，危地马拉，Guernsey，几内亚，几内亚比绍、圭亚那、海地、赫德和麦克唐纳群岛、洪都拉斯、香港特别行政区、匈牙利、冰岛、印度尼西亚、伊拉克、爱尔兰、曼岛、Jersey、以色列、意大利、牙买加、日本、、约旦、哈萨克斯坦、Kiribati、韩国、Kosovo、科威特、吉尔吉斯斯坦、、澳门特别行政区、马达加斯加、马拉维、马来西亚、马尔代夫、马里、马耳他、马绍尔群岛、马提尼克、毛里塔尼亚、毛里求斯、Mayotte、墨西哥、Micronesia、摩尔多瓦、摩纳哥蒙古、黑山、Montserrat、摩洛哥、莫桑比克、、纳米比亚、Nauru、尼泊尔、荷兰、新喀里多尼亚、新西兰、尼加拉瓜、尼日尔、尼日利亚、Niue、诺福克岛、北方马其顿共和国、北马里亚纳群岛、挪威、阿曼、波多黎各、菲律宾、菲律宾、和，波兰、葡萄牙、波多黎各、卡塔尔、Réunion、罗马尼亚、俄罗斯、卢旺达、圣 Barthélemy、圣基茨和尼维斯圣卢西亚、法属圣马丁、圣皮埃尔和密克隆、圣文森特和格林纳丁斯、萨摩亚、圣马力诺、圣多美和普林西比、沙特阿拉伯、塞内加尔、塞尔维亚、塞舌尔、塞拉利昂、新加坡、圣国、斯洛伐克、斯洛文尼亚、所罗门群岛、圣保罗、和南部、南部和南桑德威奇群岛、南部和南桑德威奇群岛、南苏丹、西班牙、斯里兰卡、圣赫勒拿、阿森松、特里斯坦达库尼亚、苏里南、斯瓦尔巴和扬马延、斯威士兰、瑞典、瑞士、台湾、塔吉克斯坦坦桑尼亚、泰国、Timor、Leste、Togo、Tokelau、汤加、特立尼达和多巴哥、突尼斯、土耳其、土库曼斯坦、特克斯和凯科斯群岛、Tuvalu、美国外部岛、美国维尔京群岛、乌干达、乌克兰、、梵蒂冈、英国、越南、斐济、乌兹别克斯坦、瓦努阿图、梵蒂冈、赞比亚和津巴布韦。