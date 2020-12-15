---
title: 添加用户并分配许可证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何同时向 Microsoft 365 添加用户和分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: 5df0db1cb782cc55bcf3e2b599430a98ea88750c
ms.sourcegitcommit: 8252377f63de188d32ed1ccd37540d92cba3cb65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "49670991"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>同时添加用户和分配许可证

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

团队中的每个人都需要一个用户帐户，然后才能登录和访问 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。 添加用户帐户的最简单方法是在 Microsoft 365 管理中心中一次添加一个用户帐户。 执行此步骤后，用户拥有 Microsoft 365 许可证、登录凭据和 Microsoft 365 邮箱。

## <a name="before-you-begin"></a>准备工作

你必须是全局管理员、许可证管理员或用户管理员才能添加用户和分配许可证。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="watch-add-users-in-the-admin-center"></a>观看：在管理中心添加用户

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 视频中使用的步骤显示了添加用户的不同起点，但其余步骤与以下过程相同。

## <a name="add-users-one-at-a-time"></a>一次添加一个用户

::: moniker range="o365-worldwide"

1. 转到位于 <https://admin.microsoft.com> 的管理中心。
2. 转到 **"用户** > **活动用户"，** 然后选择"**添加用户"。**
3. 在 **"设置基础知识**"窗格中，填写基本用户信息，然后选择"下一 **步"。**
    - **名称** 填写名字和姓氏、显示名称和用户名。
    - **域** 为用户帐户选择域。 例如，如果用户的用户名为 Jakob，并且域contoso.com，他们将使用 jakob@contoso.com。
    - **密码设置** 选择使用自动生成的密码或为用户创建自己的强密码。
    - 用户必须在 90 天后更改其密码。 或者，你可以选择 **要求此用户在首次登录时更改其密码**。
    - 选择添加用户时是否要通过电子邮件发送密码。
4. 在 **"分配产品许可证** "窗格中，为用户选择位置和相应的许可证。 如果没有可用的许可证，仍然可以添加用户并购买更多许可证。 展开 **"** 应用"并选择或取消选择应用，以限制用户拥有其许可证的应用。 选择“**下一步**”。
5. 在 **"可选设置"** 窗格中，展开 **"角色** "，使此用户成为管理员。展开 **配置文件信息** 以添加有关用户的其他信息。
6. 选择 **"下** 一步"，查看新用户的设置，进行您喜欢的任何更改，然后选择"**完成添加"，** 然后选择"**关闭"。**

::: moniker-end

::: moniker range="o365-germany"

1. 转到位于 <https://portal.office.de/adminportal> 的管理中心。
2. 转到 **"用户** > **活动用户"，** 然后选择"**添加用户"。**
3. 在 **"新建用户** "窗格中，填写以下信息。 完成后，选择"添加 **"。**
    - **姓名** 填写名字、姓氏、显示名称和用户名。
    - **域** 例如，如果用户的用户名为 Jakob，并且域contoso.com，则他们通过键入 jakob@contoso.com。
    - **联系信息** 展开以填写移动电话号码、地址等。
    - **密码** 使用自动生成的密码或展开为用户指定强密码。 他们必须在 90 天后更改密码。 也可以选择 **允许此用户在首次登录时更改其密码**。
    - **角色** 如果需要使此用户成为管理员，请展开。
    - **产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <https://portal.partner.microsoftonline.cn> 的管理中心。
2. 转到 **"用户** > **活动用户"，** 然后选择"**添加用户"。**
3. 在 **"新建用户** "窗格中，填写以下信息。 完成后，选择"添加 **"。**
    - **姓名** 填写名字、姓氏、显示名称和用户名。
    - **域** 例如，如果用户的用户名为 Jakob，并且域contoso.com，则他们通过键入 jakob@contoso.com。
    - **联系信息** 展开以填写移动电话号码、地址等。
    - **密码** 使用自动生成的密码或展开为用户指定强密码。 他们必须在 90 天后更改密码。 也可以选择 **允许此用户在首次登录时更改其密码**。
    - **角色** 如果需要使此用户成为管理员，请展开。
    - **产品许可证** 展开此部分，并选择相应的许可证。如果没有可用的许可证，仍然可以添加用户并购买更多许可证。

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>同时添加多个用户

可以使用以下任一方法同时添加多个用户：

- **使用电子表格批量添加用户。** 请参阅["同时添加多个用户"。](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)
- **自动添加帐户并分配许可证。** 请参阅 [使用 Microsoft 365 PowerShell 创建用户帐户](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)。 如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。
- **使用 ActiveDirectory？** [设置 Microsoft 365 的目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)。 使用 Azure AD Connect 工具复制 Active Directory 用户帐户 (Microsoft 365 中) Active Directory 对象。 同步只添加用户帐户。 必须先向同步的用户分配许可证，然后才能使用电子邮件和其他 Office 应用。
- **从 Exchange 迁移？** 请参阅 [将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。 使用直接转换、分步或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，会在迁移过程中自动添加用户。 迁移只添加用户帐户。 必须先向用户分配许可证，用户才能使用电子邮件和其他 Office 应用。 如果未向用户分配许可证，则其邮箱在 30 天的宽限期后将被禁用。 了解如何 [在](../manage/assign-licenses-to-users.md) Microsoft 365 管理中心向用户分配许可证。

## <a name="next-steps"></a>后续步骤

添加用户后，你收到来自 Microsoft 的电子邮件通知。 电子邮件包含用户的用户 ID 和密码，以便他们可以登录到 Microsoft 365。 使用正常过程来传达新密码。 与新用户 [共享"](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) 员工快速入门"指南以设置内容，例如如何在电脑或 Mac 上下载和安装 [Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 应用，以及如何在移动设备上设置 Office 应用 [和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相关内容

[将新员工添加到 Microsoft 365 (](add-new-employee.md) 文章) \
[将多个用户同时添加到 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (文章) \
[在 Microsoft 365](restore-user.md) 中还原 (文章) \
[向用户分配许可证 (](../manage/assign-licenses-to-users.md) 文章) \
[从组织中删除用户 (](delete-a-user.md) 文章) 
