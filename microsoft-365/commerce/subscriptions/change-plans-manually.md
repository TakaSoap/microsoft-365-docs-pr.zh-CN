---
title: 手动更改 Microsoft 365 商业版计划
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 通过购买新订阅并确保两个订阅都列出且处于活动状态，手动更改订阅。
ms.openlocfilehash: 1127a48ff23c528e3218bae4ccfd063df5e3c26d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029382"
---
# <a name="change-plans-manually"></a>手动更改计划

## <a name="step-1-decide-how-to-change-plans"></a>步骤 1：确定如何更改计划

将所有用户从一个计划更改为另一个计划的最佳方法 [就是使用"升级"选项卡](upgrade-to-different-plan.md)。有时这不可能。 改为手动更改计划：

- 如果 **"** 升级"选项卡指示无法升级当前计划。

- If， when you select the **Upgrade** tab， the plan you want isn't listed.

- 如果不想以相同方式升级所有用户。 一些企业需要订阅不同计划的不同用户。 对此使用手动更改。

若要继续手动更改，请阅读本主题中的步骤 [2：购买](#step-2-buy-a-new-subscription) 新订阅。

> [!IMPORTANT]
> 如果要更改的计划与数据相关的服务数少于当前计划 (降级) ，则需要手动备份要保留的任何数据。 有关详细信息，请参阅 [在更改计划之前备份数据](back-up-data-before-switching-plans.md)。

## <a name="step-2-buy-a-new-subscription"></a>步骤 2：购买新订阅

**已购买？** 如果你已有想要将用户移动到的订阅，请跳过此步骤并转到"步骤 [3：检查](#step-3-check-your-new-subscription-and-licenses) 本主题中的新订阅和许可证"。

或

**购买新订阅和许可证：** 按照购买其他 [Microsoft 365 商业](../buy-another-subscription.md) 版订阅中的步骤购买新订阅。

请确保为用户现在在同一组织购买订阅。 例如，检查要移动的用户的电子邮件地址。 如果他们的电子邮件地址包含 \@ contoso.com，则必须购买新订阅contoso.com。
包括要移动的每个用户的许可证。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>步骤 3：检查新订阅和许可证

1. 在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。

2. **验证这两个订阅是否列出且处于活动状态** 用户迁移自的订阅和要移动用户的订阅必须一起列出。 如果首次检查时新订阅不存在，请稍后重试。 检查这两个订阅是否处于活动状态。 [未列出新订阅，或该订阅不处于活动状态](#the-new-subscription-isnt-listed-or-isnt-active)。

3. **检查您是否具有足够的许可证供每个用户使用** 每个用户都需要一个匹配其订阅的许可证。 因此，如果你想要将 10 个用户移动到 Microsoft 365 商业高级版，你将需要确保十个许可证可用。

4. **需要新订阅的更多许可证？**
   转到" **你的产品"** 页面并 [购买更多许可证](../licenses/buy-licenses.md)。

> [旧许可证如何？](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新订阅未列出或未处于活动状态

- **如果购买了两个** 订阅，但此处未列出这两个订阅，则它们可能是为不同组织购买 (用于不同域) 。 订阅不能跨越组织边界。

- **如果你知道你有其他订阅**，并且它未在此处列出，或者不是活动的， [请致电 Microsoft 支持人员](../../admin/contact-support-for-business-products.md)。

### <a name="what-about-the-old-licenses"></a>旧许可证如何？

当前订阅的许可证将在以后删除;你稍后将仅支付新用户许可证。

## <a name="step-4-reassign-licenses"></a>步骤 4：重新分配许可证

### <a name="reassign-a-license-for-one-user"></a>为一个用户重新分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在 **"活动用户"** 页上，选择要为其分配许可证的用户。

3. 在"**许可证和应用"** 选项卡上，**展开"** 许可证"，选择要分配的许可证的框，然后选择"保存 **更改"。**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>一次为多个用户重新分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要替换现有许可证的用户姓名旁边的圆圈。

3. At the top， select **More options** (**...**) ， and then choose Manage **product licenses.**

4. 选择" **替换现有的产品许可证分配**"\>" **下一步**"。

5. 将要 **分配给这些用户** 的产品的开关切换到"打开"位置。

    > [!TIP]
    > - 若要限制哪些服务可供用户使用，请切换到要为该用户删除的服务的"关闭"位置。 例如，如果希望用户能够访问除 Skype for Business Online 之外的所有可用服务，可以将 Skype for Business Online 服务的开关切换到"关闭 **"** 位置。
    > - 这将删除所选用户之前的所有许可证分配。

6. 在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>步骤 5：取消订阅或删除不再需要的许可证 (可选) 

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

如果仅将部分用户移动到其他订阅， [请删除](../licenses/remove-licenses-from-subscription.md) 不再需要的许可证。

## <a name="call-support-to-help-you-change-plans"></a>致电支持人员，帮助你更改计划
[致电 Microsoft 支持人员](../../admin/contact-support-for-business-products.md)
