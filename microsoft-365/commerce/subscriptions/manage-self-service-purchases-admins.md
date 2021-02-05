---
title: '管理管理员和管理员 (自助服务) '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 管理员可以了解如何管理其组织中用户购买的自助服务。
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114689"
---
# <a name="manage-self-service-purchases-admin"></a>管理自助购买（管理员）

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

作为管理员，你可以看到组织中人员购买的自助服务。 你将看到产品名称、购买者名称、购买的订阅、到期日期、购买价格以及每个自助购买的已分配用户。 如果组织要求，可以通过 PowerShell 关闭按产品进行自助购买。 对于通过自助购买或集中购买的产品，具有相同的数据管理和访问策略。

您还可以控制贵组织的用户是否可以进行自助购买。 有关详细信息，请参阅对[MSCommerce PowerShell 模块使用 AllowSelfServicePurchase。](allowselfservicepurchase-powershell.md)

## <a name="view-self-service-subscriptions"></a>查看自助服务订阅

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在"**产品**"选项卡上，选择筛选器图标，然后选择 **"自助服务"。**
3. 若要查看有关订阅的更多详细信息，请从列表中选择一个。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>查看谁拥有自助服务购买订阅的许可证

1. 在管理中心，转到"帐单  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证"</a>页。
2. 选择筛选器图标，然后选择 **"自助服务"。**
3. 选择一个产品以查看分配给人员的许可。
    > [!NOTE]
    > 如果产品有多个购买，则该产品仅列出一次，"可用数量"列显示为该产品购买的所有订阅总数。
4. 用户 **列表** 按进行自助购买的用户的姓名进行分组。
5. 若要导出具有这些订阅许可证的用户列表，请选择要导出的订阅，然后选择"**导出用户"。**

## <a name="disable-or-enable-self-service-purchases"></a>禁用或启用自助服务购买

您可以禁用或启用组织中用户的自助购买。 **MSCommerce** PowerShell 模块包含 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，它使您能够控制组织中用户是否可以进行自助服务购买以及针对哪些产品进行自助购买。

可以使用 **MSCommerce** PowerShell 模块：

- 查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是按产品启用还是禁用
- 查看适用产品的列表，以及自助服务购买是启用还是禁用
- 查看或修改特定产品的当前设置以启用或禁用它

有关详细信息，请参阅对[MSCommerce PowerShell 模块使用 AllowSelfServicePurchase。](allowselfservicepurchase-powershell.md)

## <a name="centralize-licenses-under-a-single-subscription"></a>集中单个订阅下的许可证

可以通过分配给自助服务购买的用户的现有协议分配现有许可证或购买其他订阅。 分配这些集中购买的许可证后，可以请求购买者取消其现有订阅。

1. 在管理中心，转到" **帐单** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务"</a> 页。
2. 找到并选择要购买的产品，然后选择"购买 **"。**
3. 完成其余步骤以完成购买。
4. 按照" [查看谁](#view-who-has-licenses-for-a-self-service-purchase-subscription) 拥有自助购买订阅的许可证"中的步骤导出下一步中要引用的用户列表。
5. 将许可证分配给在其他订阅中拥有许可证的每个人。 有关完整步骤，请参阅"[向用户分配许可证"。](../../admin/manage/assign-licenses-to-users.md)
6. 联系购买自助服务购买订阅的人，并要求他们 [取消订阅](manage-self-service-purchases-users.md#cancel-a-subscription)。

## <a name="take-over-a-self-service-purchase-subscription"></a>接管自助服务购买订阅

你可以接管组织中用户购买的自助服务购买订阅。 当你接管自助服务购买订阅时，你有两个选项：

1. 将用户移动到其他订阅并取消原始订阅。
2. 取消自助服务购买订阅并从分配的用户中删除许可证。

### <a name="move-users-to-a-different-subscription"></a>将用户移动到其他订阅

将用户移动到其他订阅时，将自动取消旧订阅。 最初购买自助服务购买订阅的用户会收到一封电子邮件，指出订阅已取消。

> [!NOTE]
> 对于要移动到的订阅中的每个用户，你必须拥有可用的许可证。

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在"**产品**"选项卡上，选择筛选器图标，然后选择 **"自助服务"。**
3. 选择要接管的订阅。
4. 在订阅详细信息页面上的"订阅 **和** 设置"部分，选择 **"控制此订阅"。**
5. 在右侧窗格中，选择"**移动用户"。**
6. 选择要将用户移动到的产品，然后选择"**移动用户"。**
7. 在 **"将用户移动到"** 框中，选择"**移动用户"。** 移动过程可能需要几分钟。 不要在进程运行时关闭浏览器。
8. 移动过程完成后，关闭"移动 **完成"窗格**。
9. 在订阅详细信息页面上，自助购买的订阅的订阅状态将显示为 **"已删除"。**

### <a name="cancel-a-self-service-purchase-subscription"></a>取消自助服务购买订阅

当你选择取消自助服务购买订阅时，具有许可证的用户将失去对该产品的访问权限。 最初购买自助服务购买订阅的用户会收到一封电子邮件，指出订阅已取消。

1. 在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。
2. 在"**产品**"选项卡上，选择筛选器图标，然后选择 **"自助服务"。**
3. 选择要取消的订阅。
4. 在订阅详细信息页面上的"订阅 **和** 设置"部分，选择 **"控制此订阅"。**
5. 在右侧窗格中，选择 **"取消订阅"。**
6. 从下拉列表中选择取消的原因，然后选择"取消 **订阅"。**
7. 在 **"确定要取消吗？"框中**，选择"**取消订阅"。**
8. 关闭右窗格。
9. 在订阅详细信息页面上，**订阅状态** 将显示为 **"已删除"。**

## <a name="need-help-contact-us"></a>需要帮助? 联系我们。

有关自助服务购买的常见问题，请参阅 [自助服务购买常见问题解答](self-service-purchase-faq.md)。

如果对自助购买有疑问或需要帮助，请联系 [支持人员](../../admin/contact-support-for-business-products.md)。