---
title: 从另一个帐户删除域
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何加入由自助服务用户注册在 Microsoft 365 中创建的非托管Microsoft 365。
ms.openlocfilehash: 0a7cf07a70e241c0b40f28159f31b0c86766bc1d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325665"
---
# <a name="perform-an-internal-admin-takeover"></a>执行内部管理员接管

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果你是管理员，并且想要接管由自助用户注册创建的非托管帐户，可以通过执行内部管理员接管来完成此操作。

> [!NOTE]
> 自助注册任何使用 Azure AD 将用户添加到非托管或"影子"Azure AD目录并创建非托管帐户。 非托管帐户是一个没有全局管理员的目录。 若要确定帐户是托管帐户还是非托管帐户，请参阅确定 [租户类型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="before-you-begin"></a>准备工作

有时，无法将域添加到组织帐户，因为其他人已使用该域名Microsoft 365注册了域。 但是，你可以从另一个非托管帐户中删除该域，并将其添加到你的组织管理帐户。

但是，必须先加入非托管帐户并成为该帐户的管理员，然后才能从另一个帐户中删除域并将其添加到你的帐户。 然后，你将从非托管帐户中删除域、重新登录你的帐户，然后将域添加到你的管理帐户。

本文中的步骤仅概述了如何加入其他帐户 (步骤 1 和 2) 并按照管理员接管向导中的步骤操作，成为非托管帐户的管理员 (步骤 3) 。

成为非托管帐户管理员后，可以从非托管帐户中删除域，并将其添加到你的帐户。 

## <a name="step-1-verify-your-email-address"></a>步骤 1：验证电子邮件地址

> [!NOTE]
> 如果在你的帐户中启用了自助服务，用户可以自行订阅免费服务Power BI服务。 这些服务专门用于自助服务用户订阅创建了你想要以管理员角色接管的非托管帐户的情况。在步骤 1 中，使用 Power BI 启动管理员接管向导，为要删除的域创建用户帐户，以便你可以成为非托管域帐户的管理员。

1. 若要注册Power BI，请转到"Power BI ["](https://powerbi.com)网站，然后选择"开始 **免费** > 启动 **免费试用" (**"与Power BI Pro共享") 。 

2. 使用使用组织的域名的用户帐户进行注册 (如) `powerbiadmin@contoso.com` 。 如果你的帐户已在使用中，请使用当前密码登录。

3. 检查电子邮件的 **验证代码并** 输入代码以验证您的电子邮件地址。

## <a name="step-2-create-a-new-account-for-admin-access"></a>步骤 2：新建管理员访问帐户

1. 输入验证码后，你将进入一个页面，可在其中创建新帐户。

2. 使用想要使用的帐户填写用户名和密码字段，然后选择"开始 **"**。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤 3：验证域所有权并成为管理员

1. 完成步骤 2 后，也可以选择左侧导航窗格中 (中心图标，然后转到浏览器并键入) `https://admin.microsoft.com` 。

    你将被重定向到管理员接管向导。

1. 选择 **"** 下一步"，通过将 TXT 记录添加到域注册机构来验证您是否拥有要接管的域。 

    该向导将向您提供要添加的 TXT 记录，并提供指向注册机构网站的链接以及指向分步说明的链接。

1. 在" **你现在是管理员"页面上** ，选择" **转到管理中心"**。

    现在，您具有从另一个帐户删除域所需的管理员权限。 
## <a name="related-content"></a>相关内容

YouTube：执行 IT 管理员接管 Power BI [Microsoft 365 (](https://www.youtube.com/watch?v=xt5EsrQBZZk)视频) \
[管理员接管Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (文章) \
[在组织中使用自助服务注册 (](self-service-sign-up.md) 文章) \
[了解Power BI管理员角色 (](/power-bi/service-admin-role)文章) 
