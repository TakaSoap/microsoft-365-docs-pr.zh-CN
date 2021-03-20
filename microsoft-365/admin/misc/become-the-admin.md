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
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何验证电子邮件和域所有权以接管 Microsoft 365 中的非托管租户
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914842"
---
# <a name="perform-an-internal-admin-takeover"></a>执行内部管理员接管

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 

如果你是管理员，并且想要接管由自助用户注册创建的非托管租户，可以通过内部管理员接管来完成此操作。

> [!NOTE]
> 任何使用 Azure AD 的云服务的自助注册都会将用户添加到非托管或"影子"Azure AD 目录，并创建非托管租户。 非托管租户是一个没有全局管理员的目录。 若要确定租户是托管租户还是非托管租户，请参阅确定 [租户类型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>步骤 1：验证电子邮件地址

> [!NOTE]
> 如果在租户中启用了自助服务，用户可以自行订阅免费服务，如 Power BI。 这些步骤假定自助服务用户订阅已创建你想要以管理员角色接管的非托管租户。第一步，在非托管租户中创建用户上下文，使用 Power BI 演示管理员接管路径。

1. 若要注册 Power BI，请转到 Power BI 网站，然后选择"与[Power BI](https://powerbi.com)专业版共享 (免费启动免费试用版  >  ) 。 

2. 使用使用组织的域名的用户帐户进行注册， (如 `powerbiadmin@contoso.com`) 。 如果你的帐户已在使用中，请使用当前密码登录。

3. 检查电子邮件的 **验证代码并** 输入代码以验证您的电子邮件地址。
    
## <a name="step-2-create-a-new-account"></a>步骤 2：创建新帐户

1. 输入验证码后，你将进入一个页面，可在其中创建新帐户。 
    
2. 使用想要使用的帐户填写用户名和密码字段，然后选择"开始 **"。** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤 3：验证域所有权并成为管理员

1. " **成为管理员"** 向导将打开。 如果向导未启动，请查找"管理 **"** 磁贴并选择它。 

2. 选择 **是，我想成为管理员**。

3. 通过将 TXT 记录添加到域注册机构，验证您是否拥有要接管的域。 该向导将向您提供要添加的 TXT 记录，并提供指向注册机构网站的链接以及指向分步说明的链接。
    
4. 将 TXT 记录添加到注册机构站点后，返回到向导并选择"好的，**我已添加记录"。**
    
> [!NOTE]
> 接管卷影租户不会影响任何现有信息或服务。 但是，如果域中的任何用户已注册需要许可证的服务，则作为接管管理员角色的一部分，将要求您购买许可证。 管理设置过程完成后，你可以购买或删除许可证。
  
## <a name="related-articles"></a>相关文章

YouTube：执行 Power BI 和[Microsoft 365 IT](https://www.youtube.com/watch?v=xt5EsrQBZZk)管理员接管的 3 个步骤

[Azure AD 中的管理员接管](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[在组织中使用自助式注册](self-service-sign-up.md)
  
[了解 Power BI 服务管理员角色](/power-bi/service-admin-role)