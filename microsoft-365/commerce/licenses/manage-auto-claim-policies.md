---
title: 管理自动声明策略
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
description: 了解如何创建和管理自动声明策略，这些策略会自动将许可证分配给特定应用的用户。
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: d6cb3d78de914e84e831947089aeadf277e72ddf
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321091"
---
# <a name="manage-auto-claim-policies"></a>管理自动声明策略

自动声明策略允许用户在首次登录应用时自动声明产品的许可证。 作为管理员，通常手动或通过使用基于组的许可向用户分配许可证。 通过使用自动声明策略，您可以管理用户可以自动声明许可证的产品。 还可以控制这些许可证来自哪些产品。

> [!IMPORTANT]
> 自动声明策略当前仅适用于Microsoft Teams。 将来将有更多的产品可供使用。

## <a name="before-you-begin"></a>准备工作

您必须是全局管理员、用户管理员或许可证管理员才能创建和管理自动声明策略。 有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>打开或关闭自动声明策略功能

默认情况下，自动声明策略功能已关闭。 必须先打开该功能，然后才能使用该功能。 启用该功能后，可以创建自动声明策略。

### <a name="turn-on-auto-claim-policies"></a>启用自动声明策略

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 在页面的中心，选择" **打开设置"** 按钮。

### <a name="turn-off-auto-claim-policies"></a>关闭自动声明策略

只有全局管理员可以关闭自动声明策略设置。

1. In the admin center， go to the **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.
2. 在表底部附近，选择 **"用户拥有的应用和服务"**。
3. 在右侧窗格中，清除"允许用户在首次登录时自动声明许可证 **"框**。

如果已有活动策略，但不希望更多用户申请许可证， [请关闭该策略](#turn-a-policy-on-or-off)。 关闭自动声明策略后，再多用户就不再能够声明许可证。 已声明许可证的用户不会丢失其许可证。

## <a name="create-an-auto-claim-policy"></a>创建自动声明策略

" <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a> 选项卡列出了您创建的策略。 在此选项卡上，你可以看到：策略的名称、与策略关联的应用、分配给策略的产品、可用许可证的数量以及策略的状态。

创建自动声明策略时，可以添加备份产品。 如果主产品没有许可证，则使用备份产品向用户分配许可证。 您最多可以添加四个备份产品并 [更改其使用顺序](#change-the-assigning-order-for-backup-products)。 若要了解更多信息，请参阅 [添加或删除备份产品](#add-or-remove-backup-products)。

> [!NOTE]
> 目前，只能创建一个自动声明策略。 随着更多产品能够使用此功能，可以创建的策略数量将会增加。

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择 **"添加策略"**。
3. 在" **命名此自动声明策略** "页上，输入策略的名称，然后选择"下一步 **"**。
4. 在 **"设置自动声明应用** 和产品"页上，选择要为其分配许可证的应用和订阅。
5. 如果要添加备份产品，请选择" **向** 此策略添加备份产品"，然后从列表中选择该产品。
6. 选择“**下一步**”。
7. 在" **选择应用"** 页上，清除或选择许可证中要排除或包含的应用的框，然后选择"下一步 **"**。
8. 如果添加了一个或多个备份产品，请对每个产品重复步骤 7。 否则，请转到步骤 9。
9. 在" **查看并完成"** 页上，验证新策略信息，进行必要的更改，然后选择"创建 **策略"**。
10. 选择“**关闭**”。

## <a name="turn-a-policy-on-or-off"></a>打开或关闭策略

关闭策略后，其他用户无法根据该策略声明许可证。 更改不会影响已根据该策略声明许可证的用户。

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的"打开或 **关闭此策略**"下，选中或清除复选框。
4. 选择 **"保存** "以关闭详细信息窗格。

## <a name="edit-the-policy-friendly-name"></a>编辑策略友好名称

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的"策略名称 **"** 部分，选择"编辑 **"**。
4. 输入新的策略名称，然后选择"保存 **"**。
5. 选择 **"保存** "以关闭详细信息窗格。

## <a name="add-or-remove-backup-products"></a>添加或删除备份产品

创建策略时，需要向策略中添加产品。 然后，许可证将自动分配给该许可证池中的用户。 您随时都可以添加或删除自动声明策略的产品。 如果已有一个与策略关联的产品，则添加的任何产品都将被视为备份产品。 当使用第一个产品的可用许可证数量时，策略将使用列表中的下一个备份产品来分配许可证。 [您可以根据你的需求对产品列表](#change-the-assigning-apps-and-services)重新排序。

删除备份产品时，它不再用于分配许可证。 具有现有许可证的用户仍拥有该许可证，但任何新用户无法接收该产品的许可证。

> [!NOTE]
> 自动声明策略必须至少包含一个产品。 无法从策略中删除所有产品。 如果不想再分配来自特定自动声明策略的许可证， [请关闭该策略](#view-an-auto-claim-policy-report)。

### <a name="add-a-backup-product"></a>添加备份产品

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的底部，选择 **"向此策略添加备份产品"**。
    > [!NOTE]
    > 如果你看不到此链接，这是因为你只有一个与帐户关联的产品。
4. 在 **"添加产品"** 窗格中，使用下拉列表选择要添加到策略的产品，然后选择"添加 **"**。
5. 选择 **"保存** "以关闭详细信息窗格。

### <a name="remove-a-backup-product"></a>删除备份产品

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的底部，选择" **删除产品"**。
4. 在 **"从策略中删除** 产品"窗格中，选择要删除的策略的框，然后选择"保存 **"**。
5. 关闭详细信息窗格。

## <a name="change-the-assigning-apps-and-services"></a>更改分配的应用和服务

每个产品都有一组与其关联的应用和服务。 对于自动声明策略中的每种产品，可以指定在自动为用户分配产品许可证时要包含的应用和服务。

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的"应用和服务 **"下**，选择"编辑 **"**。
4. 在"**应用和服务**"窗格中，从"产品"下拉列表中选择单个产品，或选择"**所有产品"**。
5. 选中或清除希望用户拥有或无法访问的应用和服务框。
6. 完成后，选择"保存 **"**，然后关闭详细信息窗格。

## <a name="change-the-assigning-order-for-backup-products"></a>更改备份产品的分配顺序

如果为策略分配了备份产品，可以在用户登录应用时更改用于分配许可证的顺序。

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择要编辑的策略。
3. 在详细信息窗格中的"产品许可证"部分，选择要移动的产品旁边的框，然后选择"**上** 移"或"**下移"**。
4. 对要重新排序的每个产品重复步骤 3。
5. 完成产品重新排序后，选择"保存"关闭详细信息窗格。

## <a name="view-an-auto-claim-policy-report"></a>查看自动声明策略报告

1. 在管理中心，转到"帐单 **"**\>"许可证 **"页面，** 然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。
2. 选择“查看报表”。 " **自动声明策略报告"** 页列出了过去 90 天内从每个策略分配的所有许可证。 默认情况下，页面显示过去 90 天。
3. 若要更改显示的时间段，请选择" **过去 30** 天"下拉列表。 可以查看过去 1、7、30 和 90 天的报告。

## <a name="next-steps"></a>后续步骤

你可以定期返回到自动声明 **策略** 选项卡，以查看已根据你创建的策略声明许可证的用户列表。

## <a name="related-content"></a>相关内容

[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)
[购买或删除订阅许可证 (](buy-licenses.md) 文章) \
[了解本文 (](subscriptions-and-licenses.md) 订阅和) 
