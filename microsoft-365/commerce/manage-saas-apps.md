---
title: 为组织管理软件型服务应用
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
- AdminSurgePortfolio
- commerce_subscriptions
- admindeeplinkMAC
search.appverid: MET150
description: 了解如何在应用中激活和管理第三方Microsoft 365 管理中心。
ms.date: 04/15/2021
ms.openlocfilehash: 4df8dd65656bf70329c0ea09911bc7ca4cd40f57
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171263"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a>管理组织的第三方应用订阅

可以在新应用中管理第三方应用的许可证和<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a> 更新的功能包括增强订阅管理、改进了对计费信息的访问，以及提高了管理帐单的灵活性。 订阅管理基于 Microsoft 更新的商务平台。 这适用于客户直接从第三方提供商购买的软件即服务应用。

## <a name="how-to-get-software-as-a-service-apps"></a>如何获取软件型服务应用

有几种购买第三方应用的方法。

- **直接购买** – 客户可以直接从 [Azure Marketplace 或](https://azuremarketplace.microsoft.com/marketplace/) [AppSource 购买订阅](https://appsource.microsoft.com/)。
- **合作伙伴购买** – 通过合作伙伴中心与合作伙伴合作购买订阅。
- **Microsoft 建议** – 响应来自 Microsoft 销售部门（包括第三方应用）的建议。

客户购买应用并接受 Microsoft 客户协议后，就可以在 Microsoft 365 管理中心 或 适用于企业的 Microsoft Store。

应用提供商通过统一费率或为用户购买许可证来销售他们的应用。

- **统一** 费率 – 也称为基于网站的定价，应用按月或按年定价。 在应用程序页面上，许可证数量在"无限制"中列出。
- **许可证** – 应用按许可证定价。 客户将许可证分配给其组织的每个用户

## <a name="supported-regions"></a>支持的区域

以下区域支持第三方应用：

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

管理员必须先激活第三方应用，然后才能将其分配给用户。 这些应用将在第三方发布者的门户中激活。

1. In the admin center， go to the **Billing**  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.
2. 查找并选择要管理的应用。
3. 在 **设置 &操作"下**，选择 **发布者门户中的"管理"。**

你将定向到应用发布者的网站，可在其中激活应用。

## <a name="manage-third-party-apps"></a>管理第三方应用

管理员在两个位置管理第三方应用：Microsoft 365 管理中心和第三方应用提供商的门户。

以下是您可以在每个门户中执行哪些操作。

| Microsoft 365 管理中心 | 应用发布者门户 |
| --- | --- |
| 更改许可证数量 <br> 管理帐单支付方式 <br> 管理帐单支付方式 <br> 更改信用卡 (付款方式)  <br> 查看发票 <br> 取消应用订阅 | 针对每个应用 (设置一次应用)  <br> 向用户分配许可证 <br> 技术支持 |

激活应用后，除非取消、过期或付款未保持最新，否则该应用将保持活动状态。 这些事件将应用状态更改为禁用。 禁用应用后，无法将其重新激活。 若要继续使用该应用，请购买该应用的另一个副本。

## <a name="assign-licenses"></a>分配许可证

管理员需要在将第三方应用分配给用户之前激活它们。 它们将在第三方发布者的门户中激活。 在应用页面上的"设置 &**操作"** 下，选择用于分配许可证的链接。

1. In the admin center， go to the **Billing**  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.
2. 查找并选择要管理的应用。
3. 在 **设置 &操作**"下，选择在 **发布者门户中管理的链接**。

## <a name="change-license-quantity"></a>更改许可证数量

管理员可以更改其组织拥有的许可证数量。 这仅适用于使用基于席位的定价购买的应用。

1. In the admin center， go to the **Billing**  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.
2. 查找并选择要管理的应用。
3. 选择 **"更改许可证数量"。**

## <a name="manage-payment-methods"></a>管理支付方式

每个软件即服务应用都分配有一个计费配置文件。 通过计费配置文件，你可以自定义发票中包含的产品以及如何支付发票费用。 包括：

- **付款方式** - 信用卡或支票/支票转移
- **联系人信息** – 帐单邮寄地址和联系人姓名
- **角色** – 允许你更改计费配置文件、支付帐单或使用计费配置文件上的付款方式进行购买的角色。

有关计费配置文件详细信息，请参阅 [了解计费配置文件](/microsoft-store/billing-profile)。

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a>更改软件型服务应用订阅的计费配置文件

1. In the admin center， go to the **Billing**  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.
2. 查找并选择要管理的应用。
3. 在"计费 **配置文件"旁边，** 选择"编辑 **"。**

有关发票详细信息，请参阅 [了解帐单或发票](billing-and-payments/understand-your-invoice.md)。

## <a name="cancel-a-software-as-a-service-app-subscription"></a>取消软件为服务型应用订阅

你可以从应用页面取消软件即服务应用。

1. In the admin center， go to the **Billing**  >  **Your products**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.
2. 查找并选择要管理的应用。
3. 在 **"设置 &操作"** 下，选择"**取消订阅"。**
