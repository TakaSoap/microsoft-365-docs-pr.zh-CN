---
title: 保护管理员帐户
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 了解如何设置和保护管理员帐户。
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044484"
---
# <a name="protect-your-administrator-accounts"></a>保护管理员帐户

由于管理员帐户具有提升的特权，因此它们是黑客和网络攻击者的有价值的目标。 本文内容：

- 如何为紧急情况设置其他管理员帐户。
- 如何保护这些帐户。

注册 Microsoft 365 并输入信息后，将自动成为全局管理员。全局管理员对 Microsoft 管理中心中的用户帐户和所有其他设置具有最终控制权，但有许多不同类型的管理员帐户具有不同的访问权限。 有关 [每种管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 的不同访问级别的信息，请参阅管理员角色。

## <a name="create-additional-admin-accounts"></a>创建其他管理员帐户

仅将管理员帐户用于管理。 管理员应具有一个单独的用户帐户，用于定期使用 Office 应用，并且仅在管理帐户和设备时以及处理其他管理功能时，才使用其管理帐户。 此外，从管理员帐户中删除 Microsoft 365 许可证也是一个好主意，这样你不必支付这些许可证费用。

你需要设置至少一个额外的全局管理员帐户，以向另一个受信任员工授予管理员访问权限。 还可以为用户管理创建单独的管理员帐户 (此角色称为用户 **管理** 管理员) 。 有关详细信息，请参阅 [有关管理员角色的信息](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

创建其他管理员帐户：

 1. 转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧** 导航 \> **中的**"用户活动用户"。

    ![在左侧导航中选择"用户"，然后选择"活动用户"](../media/Activeusers.png)

 2. 在 **"活动** 用户"页上，选择页面顶部的"添加用户"，在"新建用户"面板中输入名称和其他信息。
 3. 展开" **角色** "部分，然后选择 **"全局管理员** "为此用户授予全局管理员访问权限。 还可以选择 **自定义管理员** 并选择任何显示的角色。

    在备用电子邮件地址文本框 **中输入备用** 电子邮件。 如果锁定，可以使用此地址恢复密码信息。对于全局管理员，还将向此地址发送帐单。

    ![选择管理员角色](../media/adminroles.png)

 4. 在 **"产品许可证**"部分中，将 **Microsoft 365 商业** 版选择器移到 **"** 关闭"，将没有产品许可证的 **"** 创建用户"移动到 **"打开"。**

    ![选择产品许可证](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>创建紧急管理员帐户

还应创建未设置多重身份验证 (MFA) 的备份帐户，以便不会意外锁定 (例如，如果你丢失了用作第二种形式验证) 的电话。 确保此帐户的密码是短语或至少 16 个字符长。 这通常称为"中断式帐户"。

## <a name="create-a-user-account-for-yourself"></a>为自己创建用户帐户

使用用户帐户参与与组织的协作，包括检查邮件。 这意味着你的管理员凭据可能类似于 *Alice.Chavez <span></span> @Contoso.org* 并且你的常规用户帐户可能类似于 *Alice <span></span> @Contoso.com。*

若要创建新的用户帐户，

1. 转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧** 导航 \> **中的**"用户活动用户"。
2. 在 **"活动** 用户"页上，选择页面顶部的"添加用户"，在"新建用户"面板中输入名称和其他信息。
3. 展开"**角色**"部分，然后选择 (**没有管理访问权限的用户) 。**
4. 在"**产品许可证"** 部分，将 **Microsoft 365 商业版选择器移动到****"打开"。**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>注册其中每个帐户进行多重身份验证

确保这些帐户使用的是 [多重身份验证](m365-campaigns-multifactor-authenication.md)。

## <a name="additional-recommendations"></a>其他建议

- 请确保管理员帐户还设置为多重身份验证。 我们将在"配置条件访问策略"中 [向您展示如何这样做](m365-campaigns-conditional-access.md)。
- 使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。 还可以在专用或无法识别的浏览器窗口中使用。
- 完成管理员任务后，请务必注销浏览器会话。
