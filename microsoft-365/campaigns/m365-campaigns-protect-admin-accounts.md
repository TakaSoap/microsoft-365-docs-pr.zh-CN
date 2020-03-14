---
title: 保护您的管理员帐户
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 了解如何设置和保护管理员帐户。
ms.openlocfilehash: b74d9d2d69549bcaa476a346ba2a61fc24e0b3f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633750"
---
# <a name="protect-your-administrator-accounts"></a>保护您的管理员帐户

由于管理员帐户具有提升的权限，因此它们对于黑客和网络罪犯来说都是非常有用的目标。 本文内容：

- 如何为紧急情况设置其他管理员帐户。
- 如何保护这些帐户。
 
当你注册 Microsoft 365 商业版并输入你的信息时，你将自动成为全局管理员。全局管理员拥有对用户帐户和 Microsoft 管理中心中所有其他设置的最终控制权，但有许多不同类型的管理员帐户具有不同级别的访问权限。 有关每种管理员角色的不同访问级别的信息，请参阅[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。


## <a name="create-additional-admin-accounts"></a>创建其他管理员帐户

仅使用管理员帐户进行管理。 管理员应具有单独的用户帐户，以便定期使用 Office 应用，并且仅在需要管理帐户和设备以及在处理其他管理功能时使用其管理帐户。 最好将 Microsoft 365 商业版许可证从管理员帐户中删除，这样您就不必为他们付费。

你将需要至少设置一个额外的全局管理员帐户，以向其他受信任的员工授予管理员访问权限。 您还可以为用户管理创建单独的管理员帐户（此角色称为 "**用户管理管理员**"）。 有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

若要创建其他管理员帐户，请执行以下操作：

 1. 转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>"，然后选择左侧导航中的 "**用户** \> **活动用户**"。

    ![选择左侧导航中的 "用户" 和 "活动用户"](../media/Activeusers.png)

2. 在 "**活动用户**" 页上，选择页面顶部的 "**添加用户**"，并在新的 "**用户**" 面板上输入名称和其他信息。
3. 展开 "**角色**" 部分，然后选择 "**全局管理员**" 以向此用户授予全局管理员访问权限。 您还可以选择 "**自定义管理员**" 并选择显示的任意角色。

    在 "**备选电子邮件地址**" 文本框中输入备用电子邮件。 如果您被锁定，可以使用此地址来恢复您的密码信息。对于全局管理员，还将向此地址发送帐单声明。

    ![选择管理员角色](../media/adminroles.png)
    
4. 在 "**产品许可证**" 部分，将 " **Microsoft 365 业务**" 的选择器移到 "**关闭**"，并将 "**创建不含产品许可证的用户** **" 设为**

    ![选择产品许可证](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>创建紧急管理员帐户

此外，还应创建一个不是通过多重身份验证（MFA）设置的备份帐户，这样您就不会意外锁定自己（例如，如果您使用另一种形式的验证丢失了您的电话）。 请确保此帐户的密码为短语或至少为16个字符长。 这通常称为 "断开玻璃帐户"。

## <a name="create-a-user-account-for-yourself"></a>为自己创建一个用户帐户

使用您的用户帐户参与与您的组织的协作，包括检查邮件。 这意味着您的管理员凭据可能类似于*Chavez<span></span>@Contoso* ，并且您的常规用户帐户可能类似于*<span></span>小红 @Contoso .com*。

若要创建新用户帐户，请执行以下操作：
1. 转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理中心</a>"，然后选择左侧导航中的 "**用户** \> **活动用户**"。
2. 在 "**活动用户**" 页上，选择页面顶部的 "**添加用户**"，并在新的 "**用户**" 面板上输入名称和其他信息。
3. 展开 "**角色**" 部分，然后选择 "**用户" （无管理访问权限）**。
1. 在 "**产品许可证**" 部分，将 " **Microsoft 365 企业**" 的选择器移到 **"打开**"。 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>为多因素身份验证注册每个帐户


## <a name="additional-recommendations"></a>其他建议

- 请确保同时为多因素身份验证设置了管理员帐户。 我们将在[配置条件访问策略](m365-campaigns-conditional-access.md)中介绍如何执行此操作。
- 使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。 您还可以在私有或 incognito 浏览器窗口中使用。
- 完成管理任务后，请务必注销浏览器会话。
