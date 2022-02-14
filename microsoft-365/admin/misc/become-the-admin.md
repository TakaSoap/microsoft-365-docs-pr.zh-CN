---
title: 执行内部管理员接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
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
description: 了解如何验证电子邮件和域所有权以接管由自助用户登录帐户创建的非托管Microsoft 365。
ms.openlocfilehash: 1201ea967fb829e43433cb5ed49f073b1d862728
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805996"
---
# <a name="perform-an-internal-admin-takeover"></a>执行内部管理员接管

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果你是管理员，并且想要接管由自助用户注册创建的非托管帐户，可以按照本文中的步骤执行内部管理员接管。

> [!NOTE]
> 自助注册任何使用 Azure AD 将用户添加到非托管或"影子"Azure AD目录并创建非托管帐户。 非托管帐户是一个没有全局管理员的目录。 若要确定帐户是托管帐户还是非托管帐户，请参阅确定 [租户类型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="before-you-begin"></a>开始之前

当用户使用电子邮件地址Microsoft 365服务时，系统会自动为用户创建一个帐户。 如果管理员想要管理帐户上的用户或购买其他 Microsoft 365 服务，他们必须通过执行以下步骤来接管管理员，成为帐户的管理员。

## <a name="step-1-verify-your-email-address"></a>步骤 1：验证电子邮件地址

> [!NOTE]
> 如果在你的帐户中启用了自助服务，用户可以自行订阅免费服务，Power BI服务。 这些服务专门用于自助服务用户订阅创建了你想要以管理员角色接管的非托管帐户的情况。在步骤 1 中，使用 Power BI 启动管理员接管向导，为要删除的域创建用户帐户，以便你可以成为非托管域帐户的管理员。

1. 若要注册Power BI，请转到"Power BI ["](https://powerbi.com)网站，然后选择"开始 **免费** > 启动免费试用" ("与用户共享Power BI Pro") 。 

2. 使用使用组织的域名的用户帐户进行注册， (如) `powerbiadmin@contoso.com` 。 如果你的帐户已在使用中，请使用当前密码登录。

3. 检查电子邮件的 **验证代码并** 输入代码以验证您的电子邮件地址。

## <a name="step-2-create-a-new-account-for-admin-access"></a>步骤 2：新建管理员访问帐户

1. 输入验证码后，你将进入一个页面，可在其中创建新帐户。

2. 使用您想要使用的帐户填写用户名和密码字段，然后完成创建帐户的步骤。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤 3：验证域所有权并成为管理员

1. 完成步骤 2 后，也可以选择左侧导航窗格中 (中心图标，然后转到浏览器并键入) `https://admin.microsoft.com` 。

    你将被重定向到管理员接管向导。

2. 选择 **"** 下一步"，通过将 TXT 记录添加到域注册机构来验证您是否拥有要接管的域。

    该向导将向您提供要添加的 TXT 记录，并提供指向注册机构网站的链接以及指向分步说明的链接。

3. 在" **你现在是管理员"页面上** ，选择" **转到管理中心"**。

    你拥有管理中心帐户所需的管理员权限。 例如，可以管理帐户用户和组、购买新订阅和进行用户分配以及管理帐户域。

    如果要从此帐户中删除域，以便可以将其添加到另一个帐户，请参阅从另一个 [帐户删除域](remove-a-domain-from-another-account.md)。
  
## <a name="related-content"></a>相关内容

YouTube[：执行 IT](https://www.youtube.com/watch?v=xt5EsrQBZZk) 管理员接管 Power BI Microsoft 365 (视频) \
[管理员接管Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (文章) \
[在组织中使用自助服务注册 (](self-service-sign-up.md) 文章) \
[了解Power BI管理员角色 (](/power-bi/service-admin-role)文章) 