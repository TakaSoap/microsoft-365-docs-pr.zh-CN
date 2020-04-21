---
title: 执行内部管理员接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何验证你的电子邮件和域所有权，以在 Microsoft 365 中接管非托管租户
ms.openlocfilehash: 1772ba9929433c87603d4b9d7027419063fd2fca
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627940"
---
# <a name="perform-an-internal-admin-takeover"></a>执行内部管理员接管

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 

如果你是管理员，并且想要接管自助服务用户注册创建的非托管租户，则可以使用内部管理员接管执行此操作。

> [!NOTE]
> 为使用 Azure AD 的任何云服务注册自助服务会将用户添加到非托管或 "卷影" Azure AD 目录，并创建非托管租户。 非托管租户是没有全局管理员的目录。 若要确定租户是否为托管或非托管，请参阅[确定租户类型](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>步骤1：验证您的电子邮件地址

> [!NOTE]
> 如果在租户中启用了自助服务，则用户可以自行订阅免费服务，例如 Power BI。 这些步骤假定自助服务用户订阅已创建要作为管理员接管的非托管租户。在第一步中，使用 Power BI 演示管理接管路径，在非托管租户中创建用户上下文。

1. 若要注册 power bi，请转到[power bi 网站](https://powerbi.com)，然后选择 **"启动免费** > **启动免费试用版**" （在 "与 Power BI Pro 共享" 框中）。 

2. 使用您的组织的域名（如`powerbiadmin@contoso.com`）注册用户帐户。 如果你的帐户已在使用中，请使用你的当前密码登录。

3. 检查您的电子邮件中的**验证代码**，并输入验证您的电子邮件地址的代码。
    
## <a name="step-2-create-a-new-account"></a>步骤2：创建新帐户

1. 当您输入验证代码时，您将进入一个页面，可以在其中创建新帐户。 
    
2. 在 "用户名" 和 "密码" 字段中填写要使用的帐户，然后选择 "**启动**"。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤3：验证域所有权并成为管理员

1. 即会打开 "**管理员**向导"。 如果向导不启动，请查找 "**管理**" 磁贴并选择它。 

2. 选择 **"是，我想要成为管理员"**。

3. 通过向域注册机构添加 TXT 记录来验证您是否拥有要接管的域。 向导将为你提供要添加的 TXT 记录，并提供指向你的注册机构网站的链接以及指向分步说明的链接。
    
4. 将 TXT 记录添加到注册器网站后，返回到向导，然后选择 "确定 **"，我已添加记录**。
    
> [!NOTE]
> 对卷影租户进行接管不会影响任何现有信息或服务。 但是，如果域中的任何用户已注册需要许可证的服务，则系统将要求你为其购买许可证，作为接管管理员角色的一部分。 管理员设置过程完成后，您可以添加或删除许可证。 
  
## <a name="related-articles"></a>相关文章

YouTube：为[POWER BI 和 Microsoft 365 执行 IT 管理员接管的3个步骤](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD 中的管理员接管](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[获取有关域的帮助](../get-help-with-domains/get-help-with-domains.md)

[在你的组织中使用自助服务注册](self-service-sign-up.md)
  
[了解 Power BI 服务管理员角色](https://docs.microsoft.com/power-bi/service-admin-role)

