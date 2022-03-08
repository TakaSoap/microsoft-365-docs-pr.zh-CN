---
title: 管理自助服务注册订阅
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jkinma, jmueller
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
search.appverid: MET150
description: 了解如何管理组织的免费自助注册订阅。
ms.date: 03/17/2021
ms.openlocfilehash: be93a09ca63a4ee24945438be59b725e7d41911c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328381"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助服务注册订阅

## <a name="what-are-self-service-sign-up-subscriptions"></a>什么是自助服务注册订阅？

您的组织中的用户可以注册有限数量的免费自助注册订阅。 用户只能自行注册和使用自助注册订阅。 通过阻止用户注册以及删除用户已注册的免费订阅，你可以管理自助服务注册订阅。 有关自助服务注册和可用订阅的信息，请参阅在组织中使用自助服务 [注册](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>查看自助服务注册订阅列表

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在" **产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"**。 将显示所有自助注册订阅的列表。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>这些订阅与自助服务购买订阅如何不同？

自助服务注册订阅是免费的，可用于比自助服务购买订阅更大的产品列表。 当用户注册自助服务购买订阅时，他们负责支付该订阅费用。 自助服务购买订阅仅适用于 Power Platform (Power BI、Power Apps 和 Power Automate) 、Project 和 Visio。 有关详细信息，请参阅 [自助服务购买常见问题](self-service-purchase-faq.yml)解答。

## <a name="block-users-from-signing-up"></a>阻止用户注册

使用 [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet 和 **AllowAdHocSubscriptions** 参数控制用户是否可以注册自助注册订阅。 有关详细信息，请参阅如何 [控制自助服务设置？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>删除自助服务注册订阅

> [!IMPORTANT]
> 当您删除自助服务注册订阅时，将阻止所有用户访问其数据和电子邮件，并删除所有数据和电子邮件。

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在" **产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"**。
3. 选择要删除的自助服务注册订阅。 
4. 在订阅详细信息页面上的订阅 **和付款设置** 部分中，选择删除 **订阅**。
5. 在" **删除订阅"** 窗格中，选中复选框，然后选择"删除 **订阅"**。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有一个自助式注册订阅，可阻止删除目录

单个用户可以注册的自助服务注册产品还会创建来宾用户以在 Azure AD 目录中进行身份验证。 为了避免数据丢失，这些自助式产品会阻止删除目录，直到从目录中完全删除它们。 它们只能由管理员Azure AD删除。有关详细信息，请参阅在目录中[删除Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto)。
