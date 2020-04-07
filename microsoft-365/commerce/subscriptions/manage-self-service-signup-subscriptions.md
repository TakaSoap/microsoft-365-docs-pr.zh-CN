---
title: 管理自助注册订阅
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: 了解如何为你的组织管理免费的自助服务注册订阅。
ms.openlocfilehash: 056ae95f9f5067ea3fa86164b620c72c84e3aad4
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43154126"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助注册订阅

## <a name="what-are-self-service-sign-up-subscriptions"></a>什么是自助式注册订阅？

您的组织中的用户可以注册的有限数量的免费自助注册订阅。 用户只能注册，并对自己使用自助注册订阅。 这些订阅显示在 "**产品 & 服务**" 页上，标记为 "**免费**"，并显示 "这是公司中的用户激活的免费订阅" 一条注释。 您可以通过阻止用户进行注册以及删除用户已注册的免费订阅来管理自助注册订阅。 有关自助注册和可用订阅的详细信息，请参阅[在组织中使用自助服务注册](../../admin/misc/self-service-sign-up.md)。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>这些订阅与自助服务购买订阅有何不同？

自助注册订阅是免费的，可用于比自助服务购买订阅更大的产品列表。 当用户注册自助服务购买订阅时，他们负责付费。 此外，自助购买订阅仅适用于 Power Platform 产品（Power BI、电源应用和电源自动化）。 有关详细信息，请参阅[自助式购买常见问题解答](self-service-purchase-faq.md)。

## <a name="block-users-from-signing-up"></a>阻止用户注册

将[**set-msolcompanysettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) Cmdlet 与**AllowAdHocSubscriptions**参数一起使用，可控制用户是否可以注册自助服务注册订阅。 有关详细信息，请参阅[如何控制自助服务设置？](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>删除自助注册订阅

> [!IMPORTANT]
> 删除自助注册订阅时，将阻止所有用户访问其数据和电子邮件，并删除所有数据和电子邮件。

1. 在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。
2. 查找要删除的自助注册订阅。 在 "**设置" & "操作**" 部分，选择 "**删除订阅**"。
3. 在 "**删除订阅**" 窗格中，选中 "" 复选框，然后选择 "**删除订阅**"。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有一个可阻止目录删除的自助服务注册订阅

单个用户可以注册的自助注册产品也可以在 Azure AD 目录中创建来宾用户进行身份验证。 为避免数据丢失，这些自助服务产品将阻止目录删除，直到从目录中完全删除。 它们只能由 Azure AD 管理员删除。有关详细信息，请参阅[删除 Azure Active directory 中的目录](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)。