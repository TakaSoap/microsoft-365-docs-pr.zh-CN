---
title: 创建共享邮箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 创建共享邮箱，让企业中的多名人员分担查看和答复发送到同一地址的电子邮件的责任。
ms.openlocfilehash: 3ffe24cc263c6f58899b3c293793aa231132e411
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780261"
---
# <a name="create-a-shared-mailbox"></a>创建共享邮箱 

> [!NOTE]
> 如果你的组织使用的是混合 Exchange 环境，则你应使用本地 Exchange 管理中心 (EAC) 创建和管理共享邮箱。 请参阅[在 Exchange 管理中心创建共享邮箱](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> 如果不确定是应为 Outlook 创建共享邮箱还是 Microsoft 365 组，可参阅[比较组](../create-groups/compare-groups.md)获取一些指导。 请注意，暂无法将共享邮箱迁移到 Microsoft 365 组中。 如果这不是你想要的结果，请通过[在此处投票](https://go.microsoft.com/fwlink/?linkid=871518)告诉我们。

It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.

共享邮箱包含共享日历。 许多小型企业喜欢使用共享日历，方便每个人在其中输入约会。 例如，如果有 3 个人在进行客户访问工作，则他们都可以使用共享日历来输入约会。 这是使每个人都知道他人位置的简便方法。

创建共享邮箱之前，请务必阅读[关于共享邮箱](about-shared-mailboxes.md)了解详细信息。

## <a name="create-a-shared-mailbox-and-add-members"></a>创建共享邮箱并添加成员
  
1. 使用全局管理员帐户或 Exchange 管理员帐户登录。 如果收到消息“**你没有访问此页面或执行此操作的权限**”，则表明你不是管理员。 

::: moniker range="o365-worldwide"

2. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

2. 在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)，转到“**组**”\>“**共享邮箱**”页面。

::: moniker-end

::: moniker range="o365-21vianet"

2. 在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)，转到“**组**”\>“**共享邮箱**”页面。

::: moniker-end
    
3. 在“**共享邮箱**”页面上，选择“**+添加邮箱**”。 输入共享邮箱的名称。 然后向导会选择电子邮件地址，但你也可以编辑电子邮件地址。
    
    ![为共享邮箱命名。](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. 选择“**添加**”。 可能需要几分钟时间，才可以添加成员。

5. 在“**后续步骤**”下，选择“**将成员添加到此邮箱**”。 成员能够查看此共享邮箱收到的邮件及发出的答复。

   ![选择“添加成员”。](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. 选择“**+添加成员**”按钮。 在希望其使用共享邮箱的人员旁添加一个复选标记，然后选择“**保存**”。

   ![向共享邮箱分配成员。](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. 选择“**关闭**”。

你有一个共享邮箱，而且它包含一个共享日历。 现转到下一步：阻止登录共享邮箱帐户。

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>阻止登录共享邮箱帐户

每个共享邮箱都有相应的用户帐户。 注意到你在创建共享邮箱时未被要求提供密码？ 该帐户有一个密码，但密码是系统生成的（未知）。 不得使用该帐户登录共享邮箱。

但如果管理员重置了共享邮箱用户帐户的密码，该怎么办？ 如果攻击者获取了对共享邮箱用户帐户的密码，又该怎么办？ 这将使得用户帐户能够登录共享邮箱并发送电子邮件。 要阻止此操作，需要阻止登录与共享邮箱关联的帐户。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在用户帐户列表中，找到共享邮箱的帐户（例如，将筛选器更改为“**未经授权的用户**”）。

3. 选择该用户以打开其属性窗格，然后 选择“**阻止此用户**”图标 ![“阻止此用户”图标的屏幕截图](../../media/block-user-icon.png)。

   **注意**：如果已阻止该帐户，则将在顶部显示“**已阻止登录**”，并且图标将显示“**取消阻止此用户**”。

4. 在“**阻止此用户?**”窗格中，选择“**阻止用户登录**”，然后选择“**保存更改**”。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 在用户帐户列表中，找到共享邮箱的帐户（例如，将视图更改为“**未经授权的用户**”），然后选择该帐户。

3. 在“属性”浮出控件中，选择“**阻止登录**”。

    **注意：** 如果已阻止该帐户，该按钮将显示“**取消阻止登录**”。

4. 在“**登录状态**”浮出控件中，验证确定已选择“阻止用户登录”，选择“**保存**”，然后选择“**关闭**”。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 在用户帐户列表中，找到共享邮箱的帐户（例如，将视图更改为“**未经授权的用户**”），然后选择该帐户。

3. 在“属性”浮出控件中，选择“**阻止登录**”。

    **注意：** 如果已阻止该帐户，该按钮将显示“**取消阻止登录**”。

4. 在“**登录状态**”浮出控件中，验证确定已选择“阻止用户登录”，选择“**保存**”，然后选择“**关闭**”。
::: moniker-end

有关如何使用 Azure AD PowerShell 阻止登录帐户（包括同时登录多个帐户）的说明，请参阅 [使用 Office 365 PowerShell 阻止用户帐户](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell)。

## <a name="add-the-shared-mailbox-to-outlook"></a>向 Outlook 添加共享邮箱

如果企业启用了自动映射（默认情况下，大部分用户都会启用此功能），共享邮箱将在用户关闭并重启 Outlook 后自动出现在其 Outlook 应用中。 

在用户邮箱（而非共享邮箱）上设置自动映射。   这意味着如果尝试使用安全组来管理有权访问共享邮箱的人员，自动映射将无法正常工作。 因此，如果想要自动映射，必须显式分配权限。 自动映射默认启用。 要了解如何将其关闭，请参阅 [删除共享邮箱的自动映射](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)。

要详细了解 Outlook 中的共享邮箱，请参阅：

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">在 Outlook 中打开和使用共享邮箱</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">将共享邮箱添加到 Outlook 网页版</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">将共享邮箱添加到 Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">在 Outlook for Mac 中打开共享文件夹或邮箱</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">向共享邮箱添加规则</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>在移动设备（手机或平板电脑）上使用共享邮箱

可采用下列两种方式在移动设备上访问共享邮箱：
- 在 <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS 应用</a>或 <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android 移动应用</a>中添加共享邮箱。 
    
    有关说明，请参阅<a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">在 Outlook Mobile 中添加共享邮箱</a>。

- 打开浏览器、登录，然后转到 Outlook 网页版。 可从 Outlook 网页版访问共享邮箱。

    有关说明，请参阅<a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">在 Outlook 网页版中添加共享邮箱</a>。

## <a name="use-the-shared-calendar"></a>使用共享日历

创建共享邮箱时，会自动创建共享日历。 我们希望使用共享邮箱日历（而不是 SharePoint 日历）来跟踪约会和位置。 共享日历与 Outlook 集成，与 SharePoint 日历相比更易于使用。

1. 在 Outlook 应用中，转到日历视图，然后选择共享邮箱。

2. 输入约会后，共享邮箱的每个成员都能看到它们。

3. 共享邮箱的所有成员都可以在该日历上创建、查看和管理约会，就像处理自己的个人约会一样。 共享邮箱的所有成员都可以看到他们对共享日历所做的更改。

## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)





