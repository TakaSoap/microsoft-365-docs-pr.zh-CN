---
title: '管理管理员管理员 (自助服务) '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: 管理员可以了解如何管理其组织中用户购买的自助服务。
ms.date: 03/26/2021
ms.openlocfilehash: 854a013779f9d1b3d141b1770860740f633e8130
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371912"
---
# <a name="manage-self-service-purchases-admin"></a>管理自助购买（管理员）

作为管理员，你可以查看组织中人员购买的自助服务。 你会看到产品名称、购买者名称、购买的订阅、到期日期、购买价格以及每个自助购买的已分配用户。 如果组织要求，可以通过 PowerShell 关闭按产品进行自助购买。 对于通过自助购买或集中购买的产品，具有相同的数据管理和访问策略。

还可以控制贵组织的用户是否可以进行自助购买。 有关详细信息，请参阅将 [AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。

## <a name="view-self-service-subscriptions"></a>查看自助服务订阅

::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">你的产品</a>”页面。
::: moniker-end

2. 在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**
3. 若要查看有关订阅的更多详细信息，请从列表中选择一个。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>查看谁拥有自助服务购买订阅的许可证

> [!NOTE]
> 作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。 你可以 [接管自助购买订阅](#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

 1. 在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。

::: moniker-end

2. 选择筛选器图标，然后选择 **"自助服务"。**
3. 选择一个产品以查看分配给人员的许可。
    > [!NOTE]
    > 如果产品有多个购买，则该产品仅列出一次，"可用数量"列显示为该产品购买的所有订阅总数。
4. " **用户** "列表按进行自助购买的用户的姓名进行分组。
5. 若要导出具有这些订阅许可证的用户列表，请选择要导出的订阅，然后选择"导出 **用户"。**

## <a name="disable-or-enable-self-service-purchases"></a>禁用或启用自助服务购买

您可以禁用或启用组织中用户的自助购买。 **MSCommerce** PowerShell 模块包括 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，可用于控制组织中用户是否可以进行自助服务购买以及针对哪些产品进行购买。

您可以使用 **MSCommerce** PowerShell 模块：

- 查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是按产品启用还是禁用
- 查看适用产品的列表以及自助服务购买是启用还是禁用
- 查看或修改特定产品的当前设置以启用或禁用它

有关详细信息，请参阅将 [AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。

## <a name="centralize-licenses-under-a-single-subscription"></a>在单个订阅下集中许可证

可以通过分配给自助服务购买的用户的现有协议分配现有许可证或购买其他订阅。 分配这些集中购买的许可证后，你可以请求购买者取消其现有订阅。

::: moniker range="o365-worldwide"

1. In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到 **账单** > **购买服务** 页面。

::: moniker-end

2. 找到并选择要购买的产品，然后选择"购买 **"。**
3. 完成其余步骤以完成购买。
4. 按照查看 [谁拥有](#view-who-has-licenses-for-a-self-service-purchase-subscription) 自助购买订阅的许可证中的步骤导出要下一步引用的用户列表。
5. 将许可证分配给在其他订阅中拥有许可证的每个人。 有关完整步骤，请参阅 [向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)。
6. 与购买自助服务购买订阅的人联系，并要求他们 [取消订阅](manage-self-service-purchases-users.md#cancel-a-subscription)。

## <a name="take-over-a-self-service-purchase-subscription"></a>接管自助服务购买订阅

你可以接管组织中用户购买的自助服务购买订阅。 当你接管自助服务购买订阅时，你有两个选项：

1. 将用户移动到其他订阅并取消原始订阅。
2. 取消自助购买订阅，并删除已分配用户的许可证。

### <a name="move-users-to-a-different-subscription"></a>将用户移动到其他订阅

将用户移动到其他订阅时，旧订阅将自动取消。 最初购买自助服务购买订阅的用户将收到一封电子邮件，指出订阅已取消。

> [!NOTE]
> 对于要移动用户的订阅中的每个用户，你必须拥有可用的许可证。

::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到" **帐单** > **""你的产品"** 页面。

::: moniker-end

2. 在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**
3. 选择要接管的订阅。
4. 在订阅详细信息页面上的订阅 **和** 设置部分中，选择 **控制此订阅**。
5. 在右侧窗格中，选择"**移动用户"。**
6. 选择要将用户移动到的产品，然后选择"**移动用户"。**
7. 在"**将用户移动到"** 框中，选择"**移动用户"。** 移动过程可能需要几分钟。 不要在进程运行时关闭浏览器。
8. 移动过程完成后，关闭" **移动已完成"窗格**。
9. 在订阅详细信息页面上，自助 **购买的** 订阅的订阅状态将显示为 **已删除**。

### <a name="cancel-a-self-service-purchase-subscription"></a>取消自助购买订阅

当你选择取消自助购买订阅时，具有许可证的用户将失去对该产品的访问权限。 最初购买自助服务购买订阅的用户将收到一封电子邮件，指出订阅已取消。

::: moniker range="o365-worldwide"

1. 在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到" **帐单** > **""你的产品"** 页面。

::: moniker-end

2. 在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**
3. 选择想要取消的订阅。
4. 在订阅详细信息页面上的订阅 **和** 设置部分中，选择 **控制此订阅**。
5. 在右侧窗格中，选择"取消 **订阅"。**
6. 从下拉列表中选择取消原因，然后选择取消 **订阅**。
7. 在 **"确定要取消？"框中，** 选择"取消 **订阅"。**
8. 关闭右窗格。
9. 在订阅详细信息页面上， **订阅状态** 将显示为 **已删除**。

## <a name="need-help-contact-us"></a>需要帮助？ 请联系我们。

有关自助服务购买的常见问题，请参阅 [自助服务购买常见问题](self-service-purchase-faq.yml)解答。

如果你有问题或需要自助服务购买帮助， [请联系支持](../../admin/get-help-support.md)人员。
