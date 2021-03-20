---
title: 在 Microsoft 365 中管理用户对应用的同意
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
description: 了解用户同意应用，以及如何启用应用以允许第三方应用访问用户的 Microsoft 365 信息。
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914554"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>在 Microsoft 365 中管理用户对应用的同意

此设置控制用户是否可以同意使用 OpenID Connect 和 OAuth 2.0 进行登录和请求访问数据的应用。 可以从你自己的组织创建应用，也可以来自另一个 Office 365 组织或第三方。

如果启用此设置，这些应用将要求用户授予访问组织数据的权限，用户可以选择是否允许。 如果关闭此设置，则管理员必须先同意这些应用，用户才能使用它们。 在这种情况下，请考虑在 Azure 门户中设置管理员同意工作流，以便用户可以发送管理员批准请求以使用任何阻止的应用。

用户可以仅向其拥有的、访问其 Office 365 信息的应用授予访问权限。 他们无法向应用授予对任何其他用户的信息的访问权限。

## <a name="turning-user-consent-on-or-off"></a>打开或关闭用户同意
<a name="__toc379982114"> </a>

下面将了解如何打开或关闭用户对应用的同意。

1. 在管理中心中，转到 **"设置** \> **""组织** 设置""服务"页，  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743)然后选择"**用户同意应用"。**

2. 在" **用户同意应用"页上** ，选择打开或关闭用户同意的选项。

## <a name="more-info"></a>详细信息
<a name="__toc379982114"> </a>

若要了解如何在 Azure Active Directory 中配置同意设置，请阅读 [配置管理员同意工作流](/azure/active-directory/manage-apps/configure-admin-consent-workflow)。

若要了解如何管理用户对应用的同意，请阅读 [管理对应用程序的同意和评估同意请求](/azure/active-directory/manage-apps/manage-consent-requests)。