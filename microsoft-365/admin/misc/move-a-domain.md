---
title: 移动在非托管帐户中验证的域
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
description: 了解如何加入非托管帐户以从帐户中删除域，以及将域添加到帐户。
ms.openlocfilehash: 3902853ea070f09e975b16a730d2b58209858853
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156574"
---
# <a name="move-a-domain-verified-in-an-unmanaged-account"></a>移动在非托管帐户中验证的域

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果你是管理员，并且尝试将域添加到 Microsoft 365 帐户，但因域验证了非托管帐户而受阻，那么你可以成为非托管帐户的管理员，以删除该域并将其添加到你的帐户。

> [!NOTE]
> 任何使用 Azure AD 的云服务的自助注册会将用户添加到非托管或"影子"Azure AD目录并创建非托管帐户。 非托管帐户是一个没有全局管理员的目录。 若要确定帐户是托管帐户还是非托管帐户，请参阅确定 [租户类型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。
  
## <a name="before-you-begin"></a>准备工作

有时，无法将域添加到组织帐户，因为其他人已使用该域名Microsoft 365注册了域。 但是，你可以从另一个非托管帐户中删除该域，并将其添加到你的组织帐户。

首先，你需要加入非托管帐户，并作为该帐户的管理员 (步骤 1 - 3) 。 然后，可以在步骤 4 (中删除域) 登录到组织帐户，然后通过步骤) 5 (将域添加到你的帐户。

## <a name="step-1-get-an-invitation-to-join-the-unmanaged-account"></a>步骤 1：获取加入非托管帐户的邀请

尝试将域添加到帐户后，您可能会收到一条消息，表明某人已使用电子邮件地址Microsoft 365注册了域。 步骤 1 是请求加入另一个帐户的邀请，并开始执行管理员接管过程。

1. 转到 **"Microsoft 365 管理中心 >设置**  >    >  **+ 添加域**"，然后添加域名。

1. 如果看到由于其他人已使用域的电子邮件地址注册而无法添加域的邮件，请输入您的帐户用户名，然后选择"将邀请发送给 **我"。**

1. 注销当前帐户，以便你可以登录到非托管帐户。

    检查电子邮件，获得邀请，帮助你加入非托管帐户，然后选择电子邮件中提供的链接。

    输入 **电子邮件中的** 验证码以验证您的电子邮件地址。

## <a name="step-2-complete-signup-with-email-instructions"></a>步骤 2：使用电子邮件说明完成注册

1. 输入验证码后，你将进入一个页面，可在其中创建新帐户。

2. 使用您想要使用的帐户填写用户名和密码字段，然后完成创建帐户的步骤。

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>步骤 3：验证域所有权并成为管理员

1. 完成步骤 2 后，也可以选择左侧导航窗格中 (中心图标，然后转到浏览器并键入 `https://admin.microsoft.com`) 。

    你将被重定向到管理员接管向导。

1. 选择 **"** 下一步"，通过将 TXT 记录添加到域注册机构来验证您是否拥有要接管的域。

    该向导将向您提供要添加的 TXT 记录，并提供指向注册机构网站的链接以及指向分步说明的链接。

1. 在"**你现在是管理员"页面上**，选择 **"转到管理中心"。**

    现在，您具有从以前非托管帐户删除域所需的管理员权限。

## <a name="step-4-remove-a-domain-from-the-unmanaged-account"></a>步骤 4：从非托管帐户删除域

1. 转到 **"用户**"步骤 2 中加入的帐户的活动用户，然后为登录使用的用户名选择"显示  >  名称"。

1. 在 **"****用户名"** 下，选择"管理用户名"，然后通过从下拉列表中选择"onmicrosoft.com 域"将用户移动到 onmicrosoft 域。

1. 注销帐户，然后使用新的 重新登录 `username@account.onmicrosoft.com` 。

1. 选择 **设置**  >  **域**"，找到要添加到其他帐户的域，然后选择"删除 **域"。**

    如果系统要求你选择另一个域作为默认域，请选择"onmicrosoft.com 域"。

    如果其他用户正在使用域，则必须删除他们。 从"自动删除" **选项中进行选择**，手动将用户移动到您的域，或完全删除用户。

   > [!NOTE]
   > 请重新检查，因为从帐户中删除域可能需要一些时间。 当域从帐户消失时，删除完成。

1. 注销帐户。

## <a name="step-5-add-the-domain-to-your-account"></a>步骤 5：将域添加到帐户

1. 登录到要添加域的帐户。

1. 选择 **设置** 域 + 添加域"，然后输入域名以继续执行向导步骤以验证此帐户中的域所有权并完成将域添加到  >    >  帐户。
  
## <a name="related-content"></a>相关内容

[执行内部管理员接管](become-the-admin.md) (文章) 
