---
title: 管理自助注册订阅
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
description: 了解如何为你的组织管理免费的自助服务注册订阅。
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376301"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助注册订阅

## <a name="what-are-self-service-sign-up-subscriptions"></a>什么是自助式注册订阅？

您的组织中的用户可以注册的有限数量的免费自助注册订阅。 用户只能注册，并对自己使用自助注册订阅。 通过阻止用户进行注册以及删除用户已注册的免费订阅来管理自助登录订阅。 有关自助注册和可用订阅的详细信息，请参阅 [在组织中使用自助服务注册](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>查看自助注册订阅的列表

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在 " **产品** " 选项卡上，选择 "筛选器" 图标，然后选择 " **自由**"。 将显示所有自助服务注册订阅的列表。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>这些订阅与自助服务购买订阅有何不同？

自助服务注册订阅是免费的，可用于比自助服务购买订阅更大的产品列表。 当用户注册自助服务购买订阅时，他们负责付费。 自助服务购买订阅仅适用于 Power Platform 产品 (Power BI、电源应用和电源自动化) 、项目和 Visio。 有关详细信息，请参阅 [自助式购买常见问题解答](self-service-purchase-faq.md)。

## <a name="block-users-from-signing-up"></a>阻止用户注册

将 [**set-msolcompanysettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) Cmdlet 与 **AllowAdHocSubscriptions** 参数一起使用，可控制用户是否可以注册自助服务注册订阅。 有关详细信息，请参阅 [如何控制自助服务设置？](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>删除自助注册订阅

> [!IMPORTANT]
> 删除自助注册订阅时，将阻止所有用户访问其数据和电子邮件，并删除所有数据和电子邮件。

1. 在管理中心中，转到 **“账单”** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“你的产品”</a>页面。
2. 在 " **产品** " 选项卡上，选择 "筛选器" 图标，然后选择 " **自由**"。
3. 选择要删除的自助注册订阅。 
4. 在 "订阅详细信息" 页上的 " **订阅和付款设置** " 部分中，选择 " **删除订阅**"。
5. 在 " **删除订阅** " 窗格中，选中 "" 复选框，然后选择 " **删除订阅**"。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有一个可阻止目录删除的自助服务注册订阅

单个用户可以注册的自助注册产品也可以在 Azure AD 目录中创建来宾用户进行身份验证。 为避免数据丢失，这些自助服务产品将阻止目录删除，直到从目录中完全删除。 只有 Azure AD 管理员才能删除它们。有关详细信息，请参阅 [删除 Azure Active directory 中的目录](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)。