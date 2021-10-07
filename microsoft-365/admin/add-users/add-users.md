---
title: 添加用户并分配许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 每个团队成员都需要用户帐户，然后才能登录和访问 Microsoft 365 商业版。了解如何添加用户和分配许可证。
ms.date: 07/01/2020
ms.openlocfilehash: eee8b2bb9484dfba34a278f7ee2b9b0077dda7e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161926"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>同时添加用户和分配许可证

团队中的每个人都需要一个用户账户，然后才能登录和访问 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。添加用户账户的最简单方法是在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 中逐一添加。完成该步骤后，用户就拥有了 Microsoft 365 许可证、登录凭据和 Microsoft 365 邮箱。

## <a name="before-you-begin"></a>开始之前

你必须是全局管理员、许可证管理员或用户管理员才能添加用户并分配许可证。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="add-a-user-in-the-admin-simplified-view"></a>在管理员简化视图中添加用户

如果在管理中心看到此页面，则位于 **管理员简化视图** 上。 请按照以下步骤添加用户。

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="屏幕截图: 简化管理中心视图":::

::: moniker range="o365-worldwide"

1. 请转到位于 <https://admin.microsoft.com> 的管理中心。

::: moniker-end

::: moniker range="o365-germany"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。

::: moniker-end 

2. 选择 **“为其他人员创建账户”**。
3. 在 **“添加用户帐户”** 页面，填写要用于登录的名字和姓氏、显示名称以及用户名。
4. 在 **“最多 5 个电子邮件地址”** 文本框中添加用户电子邮件地址。 这将确保新用户获得其登录 Microsoft 365 服务时所需的信息。
5. 若要保存此信息，请选择 **“添加用户”** 和 **“下载登录信息”**。

## <a name="watch-add-users-in-the-dashboard-view"></a>监视: 在仪表板视图中添加用户

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 视频中使用的步骤显示添加用户的不同起点，但剩余步骤与以下程序相同。

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>在仪表板视图中一次添加一个用户

:::image type="content" source="../../media/classic-admin-center.png" alt-text="屏幕截图: 管理中心仪表板视图":::

::: moniker range="o365-worldwide"

1. 转到位于 <https://admin.microsoft.com> 的管理中心。

::: moniker-end

::: moniker range="o365-germany"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。

::: moniker-end 

2. 转到“**用户**” > “**活动用户**”，然后选择“**添加用户**”。
3. 在“**设置基本信息**”窗格中，填写基本用户信息，然后选择“**下一步**”。
    - **姓名** 填写名字和姓氏、显示名和用户名。
    - **域** 为用户的账户选择域。例如，如果用户的用户名是 Jakob，且该域为 contoso.com，他们将通过使用 jakob@contoso.com。
    - **密码设置** 选择使用自动生成的密码或为用户创建你自己的强密码。
    - 用户必须在 90 天后更改密码。 也可以选择 **要求此用户在首次登录时更改其密码**。
    - 选择是否希望添加用户时通过电子邮件发送密码。
4. 在“**分配产品许可证**”窗格中，为用户选择位置和相应的许可证。 如果没有可用的许可证，仍然可以添加用户并购买其他许可证。 展开“**应用**”并选择或取消选择应用，以限制用户拥有许可证的应用。 选择“**下一步**”。
5. 在“**可选设置**”窗格中，展开“**角色**”以使此用户成为管理员。展开“**个人资料信息**”以添加有关用户的其他信息。
6. 选择“**下一步**”，查看新用户的设置，按自己的喜好更改，然后依次选择“**完成添加**”和“**关闭**”。

## <a name="add-multiple-users-at-the-same-time"></a>同时添加多个用户

可以使用以下任意方法同时添加多个用户：

- **使用电子表格批量添加人员。** 请参阅 [同时添加若干用户](../../enterprise/add-several-users-at-the-same-time.md)。
- **自动添加帐户并分配许可证。** 请参阅 [通过 Microsoft 365 PowerShell 创建用户账户](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)。 如果可以熟练使用 Windows PowerShell cmdlet，请选择此方法。
- **使用 ActiveDirectory？** [设置 Microsoft 365 的目录同步](../../enterprise/set-up-directory-synchronization.md)。 在 Microsoft 365 中，使用 Azure AD Connect 工具复制 Active Directory 用户帐户（和其他 Active Directory 对象）。 同步只添加用户帐户。 你必须向同步用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。
- **从 Exchange 迁移？** 请参阅 [将多个电子邮件帐户迁移到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。 通过使用直接转换、分阶段或混合 Exchange 方法将多个邮箱迁移到 Microsoft 365 时，将在迁移期间自动添加用户。 迁移只添加用户帐户。 你必须向用户分配许可证，然后他们才能使用电子邮件和其他 Office 应用。 如果不向用户分配许可证，则其邮箱在 30 天的宽限期后将处于禁用状态。 了解如何在 Microsoft 365 管理中心内 [向用户分配许可证](../manage/assign-licenses-to-users.md)。

## <a name="next-steps"></a>后续步骤

添加用户后，你收到一封来自 Microsoft 的电子邮件通知。 该电子邮件包含对应人员的用户 ID 和密码，使其可以登录到 Microsoft 365。 使用常规流程告知新密码。 与新用户共享 [员工快速入门指南](../../business-video/employee-quick-setup.md)，以设置一些内容，例如怎样从 [在电脑或 Mac 上下载和安装 Office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)，以及如何 [在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相关内容

[向 Microsoft 365 添加新员工](add-new-employee.md)（文章）\
[同时向 Microsoft 365 网站添加若干用户](../../enterprise/add-several-users-at-the-same-time.md)（文章）\
[在 Microsoft 365 网站中还原用户](restore-user.md)（文章）\
[向用户分配许可证](../manage/assign-licenses-to-users.md)
[从组织删除用户](delete-a-user.md)（文章）
