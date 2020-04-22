---
title: 手动更改 Microsoft 365 商业版计划
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
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 通过购买新订阅并确保订阅已列出并处于活动状态来手动更改订阅。
ms.openlocfilehash: 89786b30403a60bd0551351602d6fccc07f3d1a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636579"
---
# <a name="change-plans-manually"></a>手动更改计划

## <a name="step-1-decide-how-to-change-plans"></a>步骤1：决定如何更改计划

将所有用户从一个计划更改为另一个计划的最佳方法是[使用 "升级" 选项卡](upgrade-to-different-plan.md)。有时，这是不可能的。 改为手动更改计划：

- 如果 "**升级**" 选项卡指示您无法升级当前计划。

- 如果选择 "**升级**" 选项卡时，将不会列出所需的计划。

- 如果您不想以相同的方式升级所有用户。 一些企业需要订阅不同计划的不同用户。 对此使用手动更改。

若要继续进行手动更改，请阅读[第2步：](#step-2-buy-a-new-subscription)在本主题中购买新订阅。

> [!IMPORTANT]
> 如果要将数据相关服务的计划更改为与当前计划（降级）少的计划，则需要手动备份任何要保留的数据。 有关详细信息，请参阅[在切换 O365 for business 计划之前备份数据](back-up-data-before-switching-plans.md)。

## <a name="step-2-buy-a-new-subscription"></a>步骤2：购买新订阅

**已购买？** 如果您已有要将用户移动到的订阅，请跳过此步骤并转到本主题中的[步骤3：检查您的新订阅和许可证](#step-3-check-your-new-subscription-and-licenses)。

OR

**购买新的订阅和许可证：** 按照 "[购买其他 Microsoft 365 for business 订阅](../buy-another-subscription.md)" 中的步骤购买新订阅。

请确保您购买了用户当前所在组织的订阅。 例如，检查您要移动的用户的电子邮件地址。 如果他们的电子邮件\@地址包含 contoso.com，则必须购买 contoso.com 的新订阅。
为您要移动的每个用户包含一个许可证。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>步骤3：检查新的订阅和许可证

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品和服务</a>”页面。

2. **验证这两个订阅是否都已列出并处于活动状态**您要将用户移出的订阅和要将用户移动到的订阅必须一起列出。 如果在首次检查时新订阅不在此处，请稍后重试。 检查两个订阅是否都处于活动状态。 [新订阅未列出或未处于活动状态](#the-new-subscription-isnt-listed-or-isnt-active)。

3. **检查是否有针对每个用户的足够许可证**每个用户都需要一个与其订阅相匹配的许可证。 因此，如果要将10个用户移动到 Office 365 企业版 E5，则需要确保十个许可证可用。

4. **是否需要新订阅的更多许可证？**
   转到 "**产品 & 服务**" 页面并[购买更多许可证](../licenses/buy-licenses.md)。

> [旧的许可证是什么？](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>新订阅未列出，或未处于活动状态

- **如果你购买了两个订阅，但未在此处列出**它们，则可能是为不同的组织（针对不同的域）购买了这些订阅。 订阅无法跨组织边界。

- **如果你知道你有其他订阅**，并且未在此处列出或未处于活动状态，请[致电 Microsoft 支持部门](../../admin/contact-support-for-business-products.md)。

### <a name="what-about-the-old-licenses"></a>旧的许可证是什么？

将稍后删除当前订阅的许可证;您只需支付新用户许可证的费用。

## <a name="step-4-reassign-licenses"></a>步骤4：重新分配许可证

### <a name="reassign-a-license-for-one-user"></a>为一个用户重新分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 在 "**活动用户**" 页上，选择要为其分配许可证的用户。

3. 在 "通过 te**许可证和应用**" 选项卡上，展开 "**许可证**"，选择要分配的许可证对应的框，然后选择 "**保存更改**"。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>一次为多个用户重新分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要为其替换现有许可证的用户的名称旁边的圆圈。

3. 在顶部，选择 "**更多选项**（**...**）"，然后选择 "**管理产品许可证**"。

4. 选择" **替换现有的产品许可证分配**"\>" **下一步**"。

5. 将您要分配给这些用户的产品的开关切换到 "**开**" 位置。

    > [!TIP]
    > - 若要限制哪些服务对用户可用，请切换到要为该用户删除的服务的**关闭**位置。 例如，如果您希望用户能够访问除 Skype for Business Online 之外的所有可用服务，则可以将 Skype for business Online 服务的切换切换到 "**关**" 位置。
    > - 这将删除所选用户之前的所有许可证分配。

6. 在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>步骤5：取消订阅或删除不再需要的许可证（可选）

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

如果仅将一些用户移动到其他订阅，请[删除](../licenses/remove-licenses-from-subscription.md)不再需要的许可证。

## <a name="call-support-to-help-you-change-plans"></a>致电支持部门以帮助你更改计划
[致电 Microsoft 支持部门](../../admin/contact-support-for-business-products.md)