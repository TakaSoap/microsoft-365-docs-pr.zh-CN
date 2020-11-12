---
title: 管理用户同意 Microsoft 365 中的应用程序
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解用户对应用程序的同意，以及如何将其打开以允许第三方应用访问用户的 Microsoft 365 信息。
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999558"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>管理用户同意 Microsoft 365 中的应用程序

此设置控制用户是否可以同意使用 OpenID Connect 和 OAuth 2.0 的应用进行登录，并请求访问数据。 可以从您自己的组织中创建应用程序，也可以通过其他 Office 365 组织或第三方来创建。

如果启用此设置，则这些应用将向用户询问您的组织的数据的访问权限，并且用户可以选择是否允许。 如果关闭此设置，则管理员必须先同意这些应用，然后用户才能使用它们。 在这种情况下，请考虑在 Azure 门户中设置管理员同意工作流，以便用户可以发送管理员批准的请求，以使用任何已阻止的应用。

用户可以仅向其拥有的、访问其 Office 365 信息的应用授予访问权限。 他们无法向应用授予对任何其他用户的信息的访问权限。

## <a name="turning-user-consent-on-or-off"></a>打开或关闭用户同意
<a name="__toc379982114"> </a>

下面介绍了如何打开或关闭应用程序的用户同意。

1. 在管理中心中，转到 " **设置** \> **组织设置**  >  [服务](https://go.microsoft.com/fwlink/p/?linkid=2053743)" 页面，然后选择 " **用户同意应用** "。

2. 在 " **用户同意应用程序** " 页上，选择打开或关闭用户同意的选项。

## <a name="more-info"></a>详细信息
<a name="__toc379982114"> </a>

若要了解如何在 Azure active directory 中配置同意设置，请参阅 [配置管理员同意工作流](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)。

若要了解如何管理用户对应用的同意，请阅读 [对应用程序的同意和评估同意请求的管理](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)。