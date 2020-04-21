---
title: 配置共享邮箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 创建共享邮箱后，您需要为其用户配置一些设置，如电子邮件转发和自动答复。 稍后，您可能需要更改其他设置，例如邮箱名称或成员。
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629043"
---
# <a name="configure-a-shared-mailbox"></a>配置共享邮箱

[创建共享邮箱](create-a-shared-mailbox.md)后，您需要为邮箱用户配置一些设置，如电子邮件转发和自动答复。 稍后，您可能需要更改其他设置，如邮箱名称、成员或成员权限。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>更改共享邮箱的名称或电子邮件别名，或更改主电子邮件地址

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 **"名称"、"电子邮件" 和 "电子邮件别名**" 旁边的 "**编辑**"。

3. 输入一个新名称，或添加另一个别名。 如果要更改主电子邮件地址，邮箱必须具有多个电子邮件别名。

4. 选择“**保存**”。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>转发共享邮箱收到的电子邮件

您无需将许可证分配给共享邮箱，即可转发发送给它的电子邮件。 您可以将邮件转发到任何有效的电子邮件地址或通讯组列表。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**电子邮件转发** \> **编辑**"。
    
3. 将切换设置为 **"开**"，然后输入一个电子邮件地址以将邮件转发给。 它可以是任何有效的电子邮件地址。 若要转发到多个地址，您需要为地址[创建通讯组](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide)，然后在此框中输入组的名称。
    
4. 选择“**保存**”。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>从共享邮箱发送自动答复

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**自动答复** \> " "**编辑**"。
    
3. 将开关切换到" **开**"，选择将答复发送给组织内部还是外部的人员。

4. 输入要向组织内部的人员发送的答复。 不能添加图像，只能输入文本。

5. 如果*还要*向组织外部的人员发送答复，请选中要获取答复的用户的复选框，然后键入文本。 不能只发送给组织外部的人员而不发送给组织内部的人员。

6. 选择“**保存**”。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>使所有人都能看到已发送的电子邮件（答复邮件）

默认情况下，发送自共享邮箱的邮件不会保存到共享邮箱的"已发送邮件"文件夹中。相反，它们会保存到发件人的"已发送邮件"文件夹中。

如果要允许所有人都能看到已发送的电子邮件，请在管理中心中编辑共享邮箱设置，并选择 "**已发送邮件** \> " "**编辑**"。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>选择共享邮箱可用于访问 Microsoft 电子邮件的应用程序

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**电子邮件应用** \> **编辑**"。

3. 将所有您希望其成员能够使用的应用程序的切换设置为 **"开**"，以访问共享邮箱。 将您不希望其使用的任何应用程序的开关设置为 "**关闭**"。 

4. 选择“**保存**”。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>将共享邮箱置于诉讼保留状态

若要了解有关诉讼保留的详细信息，请参阅[创建诉讼保留](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**诉讼保留** \> **编辑**"。

3. 将切换设置为 **"开**"。 

4. （可选）输入持续时间、有关保留的说明以及包含详细信息的 URL。  

5. 选择“**保存**”。


## <a name="add-or-remove-members"></a>添加或删除成员

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**成员** \> **编辑**"。

3. 执行下列操作之一：
   - 若要添加成员，请选择 "**添加成员**"，搜索或选择要添加的成员，然后选择 "**保存**"。
   - 若要删除成员，请使用搜索框搜索成员（如有必要），选择成员名称旁边的**X** ，然后选择 "**保存**"。 

4. 再次选择 "**保存**"。

## <a name="add-or-remove-permissions-of-members"></a>添加或删除成员的权限

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**成员** \> **自定义权限**"。

3. 选择要为成员更改的权限旁边的 "**编辑**"。 

4. 执行下列操作之一：
   - 若要向其他成员授予该权限，请选择 "**添加权限**"，搜索或选择要添加的成员，然后选择 "**保存**"。
   - 若要删除成员的权限，请使用搜索框搜索成员（如有必要），选择成员名称旁边的**X** ，然后选择 "**保存**"。 

4. 再次选择 "**保存**"。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>在全局地址列表中显示或隐藏共享邮箱

如果选择不在全局地址列表中显示共享邮箱，该邮箱将不会显示在组织的地址列表中，但仍会收到发送给它的电子邮件。 

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**组**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">共享邮箱</a>”页面。

::: moniker-end 

::: moniker range="o365-germany"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

::: moniker range="o365-21vianet"

1. 在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到“**组**”>“**共享邮箱**”页面。 

::: moniker-end

2. 选择要编辑的共享邮箱，然后选择 "**在全局地址列表** \> **编辑**中显示"。

3. 将切换设置为 **"开**" 或 "**关**"。 

4. 选择“**保存**”。

> [!NOTE]
> 将共享邮箱从地址列表中隐藏将使新的共享邮箱成员无法将隐藏邮箱添加到其 Outlook 配置文件中，直到共享邮箱再次显示在地址列表中。 

## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[创建共享邮箱](create-a-shared-mailbox.md)

[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)
