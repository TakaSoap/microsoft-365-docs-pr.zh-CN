---
title: 执行内部管理员操作
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何在 Microsoft 365 中验证你的电子邮件和域所有权以接过非托管租户
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814464"
---
# <a name="perform-an-internal-admin-takeover"></a>执行内部管理员操作

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 

如果你是管理员，并且想要使用自助服务用户注册创建的非托管租户，可以用内部管理员转到此方法。

> [!NOTE]
> 自助注册使用 Azure AD 的用户会将用户添加到非托管或"影子"Azure AD 目录，并创建非托管租户。 非托管租户是没有全局管理员的目录。 若要确定租户是否由托管或非托管，请参阅["确定租户类型"。](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>步骤 1：验证您的电子邮件地址

> [!NOTE]
> 如果你的租户启用了自助服务，则用户可以自行订阅免费服务，例如 Power BI。 这些步骤假定自助式用户订阅已创建你想要作为管理员认为的非托管租户。第一步是在非托管租户中创建用户上下文，使用 Power BI 来说明管理员接入路径。

1. 要注册 Power BI，请转到[Power BI](https://powerbi.com)网站，然后选择"**开始**使用  >  Power BI 专业版 (CTrial (Ca power BI Pro"框) 。**Start free trial** 

2. 使用组织域名的用户帐户进行注册， (如 `powerbiadmin@contoso.com`) 。 如果你的帐户已在使用中，请使用当前密码登录。

3. 检查您的电子邮件 **中是否有验证码，** 输入代码以验证您的电子邮件地址。
    
## <a name="step-2-create-a-new-account"></a>步骤 2：创建新帐户

1. 输入验证代码时，你将转到可创建新帐户的页面。 
    
2. 使用您想要使用的帐户填写用户名和密码字段，然后选择"开始 **"。** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤 3：验证域所有权并成为管理员

1. 此 **时将会打开"** 成为管理员"向导。 如果没有启动该向导，请查找管理 **磁贴** 并选择它。 

2. 选择 **"是"，我想是管理员**。

3. 向域注册机构添加 TXT 记录以验证你是否拥有要完全覆盖过的域。 该向导将提供要添加的 TXT 记录、提供注册机构网站的链接及分步说明链接。
    
4. 将 TXT 记录添加到注册机构网站后，返回向导并选择 **"确定"，我添加了记录**。
    
> [!NOTE]
> 处理卷影租户不会影响任何现有信息或服务。 但是，如果域中的任何用户注册了需要许可证的服务，作为取对管理员角色的一部分，系统会要求你为他们购买许可证。 管理员设置过程完成后，你可以购买或删除许可证。
  
## <a name="related-articles"></a>相关文章

YouTube： [为 Power BI 和 Microsoft 365 执行 IT 管理员角色角色的 3 个步骤](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD 中的管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[在组织中使用自助式注册](self-service-sign-up.md)
  
[了解 Power BI 服务管理员角色](https://docs.microsoft.com/power-bi/service-admin-role)

