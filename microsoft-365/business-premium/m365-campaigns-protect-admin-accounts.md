---
title: 保护管理员帐户
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 32522596fc41c209d7c05173d75b36ab331fae5c
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766220"
---
# <a name="protect-your-administrator-accounts"></a>保护管理员帐户

由于管理员帐户具有提升的特权，因此它们是黑客和网络犯罪有价值的目标。 本文内容：

- 如何为紧急情况设置其他管理员帐户。
- 如何保护这些帐户。

注册并输入Microsoft 365时，将自动成为全局管理员。全局管理员对 Microsoft 管理中心中的用户帐户和所有其他设置具有最终控制权，但有很多不同类型的管理员帐户具有不同的访问权限。 有关 [每种管理员角色](/office365/admin/add-users/about-admin-roles) 的不同访问级别的信息，请参阅有关管理员角色的信息。

## <a name="create-additional-admin-accounts"></a>创建其他管理员帐户

仅将管理员帐户用于管理。 管理员应具有单独的用户帐户，用于常规使用 Office 应用，并且仅在管理帐户和设备以及处理其他管理功能时，在必要时使用其管理帐户。 此外，从管理员帐户中删除Microsoft 365许可证也是一个好主意，这样你不必支付这些许可证费用。

你需要设置至少一个额外的全局管理员帐户，以向另一个受信任员工授予管理员访问权限。 还可以为用户管理创建单独的管理员帐户 (此角色称为用户管理 **管理员**) 。 有关详细信息，请参阅 [管理员角色](/office365/admin/add-users/about-admin-roles)。

创建其他管理员帐户：

 1. 转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧**\>导航中的"用户 **"**"活动用户"。

    ![选择"用户"，然后选择左侧导航中的"活动用户"。](../media/Activeusers.png)

 2. 在 **"活动用户**"页上，选择页面顶部的"添加用户"，在"新建用户"面板中输入名称和其他信息。
 3. 展开" **角色"** 部分，然后选择" **全局管理员** "为此用户授予全局管理员访问权限。 还可以选择" **自定义管理员"** 并选择显示的任何角色。

    在"备用电子邮件地址" **文本框中输入备用** 电子邮件。 如果锁定，可以使用此地址恢复密码信息。对于全局管理员，帐单也会发送到此地址。

    ![选择管理员角色。](../media/adminroles.png)

 4. 在"**产品许可证"** 部分，将 Microsoft 365 **Business** 的选择器移到 **"** 关闭"，将"创建没有产品许可证的用户"**移动到****"开"**。

    ![选择产品许可证。](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>创建紧急管理员帐户

您还应该创建一个未设置多重身份验证 (MFA) 的备份帐户，以便不会意外锁定 (例如，如果你丢失了用作第二种验证) 形式的手机。 确保此帐户的密码是短语或至少 16 个字符长。 这通常称为"中断式帐户"。

## <a name="create-a-user-account-for-yourself"></a>为自己创建用户帐户

使用用户帐户与组织协作，包括检查邮件。 这意味着您的管理员凭据可能类似于  *Alice.Chavez <span></span>@Contoso.org* 并且您的常规用户帐户可能类似于 *Alice <span></span>@Contoso.com*。

创建新用户帐户：

1. 转到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">中心，</a>**然后选择左侧**\>导航中的"用户 **"**"活动用户"。
2. 在 **"活动用户**"页上，选择页面顶部的"添加用户"，在"新建用户"面板中输入名称和其他信息。
3. 展开" **角色"** 部分，然后选择" **(没有管理访问权限)**。
4. 在"**产品许可证"** 部分，将"Microsoft 365 **选择器"** 移至 **"打开"**。

## <a name="turn-on-security-defaults"></a>打开安全默认值

安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。 这些设置包括在所有管理员和用户帐户 (MFA) 多重身份验证。 有关安全默认值和如何启用安全默认值的信息，请参阅启用 [安全默认值](m365-campaigns-conditional-access.md)。

## <a name="additional-recommendations"></a>其他建议

- 使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。 还可以在专用或隐身浏览器窗口中使用。
- 完成管理员任务后，请务必注销浏览器会话。
