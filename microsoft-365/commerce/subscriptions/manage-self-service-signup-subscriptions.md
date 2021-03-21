---
title: 管理自助服务注册订阅
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何管理组织的免费自助注册订阅。
ms.openlocfilehash: 5910ed5d65f93a4dab15c681610d4d59d0427fb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920164"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助服务注册订阅

## <a name="what-are-self-service-sign-up-subscriptions"></a>什么是自助服务注册订阅？

您的组织中的用户可以注册有限数量的免费自助注册订阅。 用户只能自行注册和使用自助注册订阅。 通过阻止用户注册以及删除用户已注册的免费订阅，你可以管理自助服务注册订阅。 有关自助注册和可用订阅的信息，请参阅在组织中使用自助服务 [注册](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>查看自助服务注册订阅列表

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在"**产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"。** 将显示所有自助注册订阅的列表。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>这些订阅与自助服务购买订阅如何不同？

自助服务注册订阅是免费的，可用于比自助服务购买订阅更大的产品列表。 当用户注册自助服务购买订阅时，他们负责支付该订阅费用。 自助服务购买订阅仅适用于 Power BI、Power Apps 和 Power Automate (Power Automate) 、Project 和 Visio 等 Power Platform 产品。 有关详细信息，请参阅 [自助服务购买常见问题解答](self-service-purchase-faq.md)。

## <a name="block-users-from-signing-up"></a>阻止用户注册

使用 [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet 和 **AllowAdHocSubscriptions** 参数控制用户是否可以注册自助注册订阅。 有关详细信息，请参阅 [如何控制自助服务设置？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>删除自助服务注册订阅

> [!IMPORTANT]
> 当您删除自助服务注册订阅时，将阻止所有用户访问其数据和电子邮件，并删除所有数据和电子邮件。

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在"**产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"。**
3. 选择要删除的自助服务注册订阅。 
4. On the subscription details page， in the **Subscriptions and payment settings** section， select **Delete subscription**.
5. 在"**删除订阅"** 窗格中，选中复选框，然后选择"删除 **订阅"。**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有一个自助式注册订阅，可阻止删除目录

单个用户可以注册的自助服务注册产品还可以在 Azure AD 目录中创建来宾用户进行身份验证。 为了避免数据丢失，这些自助式产品会阻止删除目录，直到从目录中完全删除。 它们只能由 Azure AD 管理员删除。有关详细信息，请参阅删除 [Azure Active Directory 中的目录](/azure/active-directory/users-groups-roles/directory-delete-howto)。